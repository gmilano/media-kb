---
industry: media
region: Global
updated: 2026-11-22
---

# 🧩 Composition Patterns — Media & Entertainment

> Concrete recipes: named repos, verified licenses, and how they wire together.
> Every repo referenced here appears with its verified license and last-push date in
> `agents/top.md`, `repos/foundations.md` or `verticals/solutions.md`.
> The previous version of this file contained one empty template recipe; these replace it.

---

## Pattern 1 — Compliance-grade generative pipeline (the flagship)

**Why:** EU AI Act Art. 50, Korea's AI Basic Act, Vietnam's AI law, India's IT Rules and Mexico's
performer-likeness law all demand the same artifact: a machine-readable claim about how an asset was
made. This is the one build that sells in all four regions.

```
[Brief / script]
      ↓
[Wan 2.2 (Apache-2.0) or LTX-Video (Apache-2.0)]     ← never HunyuanVideo in EU/UK/KR
      ↓  frames
[OpenColorIO (BSD-3) → OpenImageIO (Apache-2.0)]      ← colour-correct, show-matched frames
      ↓
[FFmpeg (LGPL-2.1+, pinned build flags)]              ← mux/encode
      ↓
[Netflix VMAF (BSD-2-Clause-Patent)]                  ← objective quality gate; reject below threshold
      ↓
[c2pa-rs (MIT OR Apache-2.0)]                         ← sign Content Credentials into the asset
      ↓
[OpenTimelineIO (Apache-2.0)]                         ← hand off to a human editor as .otio
```

**Wiring:** run generation as a job service; after render, call `vmaf` with a reference or
no-reference model and fail the job under your SLA score; then `c2pa-rs` writes a signed manifest
(generator, model version, operator, consent reference) before the asset leaves the pipeline. Export
`.otio` so Premiere/Resolve/Avid can open the result — this is what makes it professional rather
than a demo.

**Why it holds up legally:** every component is permissive. The only copyleft is FFmpeg's LGPL, which
is satisfied by dynamic linking, and you control the GPL-component build flags.
**Per-region switch:** model choice is configuration — Wan 2.2 / LTX-Video / Open-Sora everywhere;
HunyuanVideo only outside the EU, UK and South Korea.

---

## Pattern 2 — Localization factory (fastest path to revenue)

**Why:** this is where M&E money is actually being spent today (internal workflows, per Adobe), and
the open stack is ~80% complete.

```
[Source video]
   ↓
[whisperX (BSD-2-Clause)]          ← word-level timestamps + speaker diarization
   ↓
[VideoLingo (Apache-2.0)]          ← translate + align subtitles
   ↓
[GPT-SoVITS (MIT) or F5-TTS (MIT) or Chatterbox (MIT)]   ← target-language voice, cloned from talent
   ↓
[MuseTalk (MIT)]                   ← re-sync lips to the dubbed track
   ↓
[c2pa-rs]                          ← label the synthetic voice (required in KR/VN/IN/EU/MX)
```

**Wiring:** `whisperX` for timing (plain Whisper's timestamps are too coarse for frame-accurate
subs); VideoLingo orchestrates translation; swap the TTS by language — GPT-SoVITS for few-shot
cloning of a specific actor, F5-TTS for speed, Chatterbox for emotional range. `MuseTalk` only where
the speaker is on camera.
**Watch out:** `pyvideotrans` (GPL-3.0) does much of this in one tool — use it as a **separate CLI
process**, never linked into client code. Avoid `fish-speech` here: its Community License is not
permissive.
**Mexico note:** cloning a performer's voice now requires a documented consent and compensation
trail — pair this pattern with the Pattern 4 ledger before shipping in Mexico.

---

## Pattern 3 — Archive mining / searchable library

**Why:** broadcasters sit on decades of unindexed tape. Highest-value, lowest-risk AI engagement in
M&E — no synthetic content, so no labeling exposure.

```
[Archive ingest: yt-dlp (Unlicense) / direct files]
   ↓
[PySceneDetect (BSD-3)]            ← shot boundaries
   ↓
[whisper.cpp (MIT)]                ← on-prem ASR, no cloud egress (passes security review)
   ↓
[embeddings + pgvector]            ← scene/dialogue index
   ↓
[Netflix Photon (Apache-2.0)]      ← validate IMF masters on the way in
   ↓
[MediaCMS (AGPL-3.0) deployed unmodified, or Payload (MIT) if you must modify]
```

**Wiring:** scene-detect first so ASR and embeddings are scoped per shot — this is what makes
"find the scene where X says Y" work. `whisper.cpp` rather than hosted ASR is the detail that gets
an archive deal past a broadcaster's infosec team.
**License position:** if the client wants the CMS itself customized, use **Payload (MIT)**, not
MediaCMS — modifying AGPL and serving it over a network triggers source disclosure.

---

## Pattern 4 — Consent & digital-replica ledger (the unbuilt product)

**Why:** 2026 SAG-AFTRA/WGA/DGA agreements require informed consent and compensation for digital
replicas; Mexico's 2026-05-14 amendments require the same for voice, image and performance. **Studios
are tracking this in spreadsheets.** No open-source product exists.

```
[Consent record: performer, scope, usage window, compensation terms]
   ↓
[Payload (MIT) or Ghost (MIT)]     ← permissive system of record you can freely modify
   ↓
[c2pa-rs (MIT OR Apache-2.0)]      ← bind the consent ID into every generated asset's manifest
   ↓
[Any Pattern 1/2 generation step]  ← refuses to render without a valid, in-window consent reference
```

**Wiring:** the generation service takes a consent token, not just a prompt. `c2pa-rs` embeds the
consent ID as an assertion, so an auditor can take a finished asset and resolve it back to the
signed permission. **This is the highest-margin opportunity in this KB**: it is a compliance
obligation in North America and Mexico simultaneously, it is pure software, and the competition is
spreadsheets.

---

## Pattern 5 — Agentic short-form repurposing

**Why:** highest-volume request from every media client.

```
[Long-form master]
   ↓
[Kinocut (Apache-2.0, 206 MCP tools)]   ← agent-callable editing with loudness + quality gates
   ↓  or
[OpenCreator (Apache-2.0)] / [MoneyPrinterTurbo (MIT)]
   ↓
[Vertical renders 9:16 / 1:1 + burned subtitles from Pattern 2]
   ↓
[Owncast (MIT) or SRS (MIT) for owned distribution]
```

**Wiring:** drive Kinocut over MCP from your agent framework so the agent cannot issue arbitrary
FFmpeg — its guardrails and -16 LUFS loudness gate are what keep output broadcast-legal.
MoneyPrinterTurbo is the fastest end-to-end starting point (MIT, 144,854★); OpenCreator is better for
multi-language repurposing.
**Avoid in client code:** `OpenMontageInc/OpenMontage` is the most capable suite here (81,978★) but
**AGPL-3.0** — deploy it unmodified behind its own API or stay off it.

---

## Pattern 6 — Low-latency interactive / live AI

**Why:** sports, betting overlays, live shopping — strongest in LATAM and APAC.

```
[Live ingest: SRS (MIT) — RTMP/SRT/WebRTC]
   ↓
[whisper.cpp (MIT) streaming ASR]      ← live captions
   ↓
[Agent: live clipping + highlight detection (PySceneDetect + embeddings)]
   ↓
[shaka-player (Apache-2.0) / hls.js (Apache-2.0)]   ← playback with DRM where needed
```

**Wiring:** SRS (MIT) over OvenMediaEngine for anything client-modified — OvenMediaEngine is
**AGPL-3.0** (an earlier cycle of this KB wrongly recorded it as Apache-2.0, which would have put a
client's streaming stack under network copyleft). Use Janus (GPL-3.0) only as a standalone gateway
process.

---

## Pattern 7 — Agentic newsroom automation on Sofie (the highest-differentiation build)

**Why:** this KB asserted for several passes that newsroom playout could not be automated
off-the-shelf because no open MOS implementation existed. That was wrong, and the correction opens the
most defensible engagement in the file. **Sofie** is MIT, commissioned by **NRK** as an open
replacement for Vizrt Mosart, and in daily news production at **NRK, the BBC and TV 2 Norway since
2018**. The gap that actually remains is one component wide: **nothing exposes Sofie's typed device
layer to an agent.**

```
[NRCS: iNEWS / ENPS / Octopus]
      ↓  MOS Protocol v2.8.4
[sofie-mos-connection (MIT)]              ← rundown in, story/item updates out
      ↓
[sofie-core (MIT)]                        ← rundowns, show styles, blueprints
      ↓
[★ MCP SERVER YOU BUILD ★]                ← the missing component; wraps the resolver below
      ↓
[sofie-timeline-state-resolver (MIT)]     ← typed device abstraction: DECLARE state, it diffs & drives
      ↓
[CasparCG (GPL-3.0, own process) · ATEM via sofie-atem-connection (MIT) ·
 sisyfos audio (MIT) · HyperDeck (MIT) · sofie-package-manager (MIT) for ingest/transcode]
      ↓
[Agent tasks: draft lower-thirds, pick archive clips, propose rundown reorder, prep B-roll]
      ↓
[HUMAN DIRECTOR APPROVES EVERY ON-AIR ACTION]
```

**Wiring, and the reason this is safe enough to put near a live transmission.** Do **not** let an
agent issue device commands. `sofie-timeline-state-resolver` is *declarative*: you hand it a timeline
of desired states and it computes the diff and drives the hardware. So the MCP tools you expose are
`propose_timeline`, `validate_timeline`, `diff_against_current` — never `send_to_device`. The agent
writes a proposal; Sofie owns reconciliation; a human arms it. That property is what makes an agent
admissible in a gallery at all, and it comes from the library's design rather than from your prompt.

**Scope the build honestly:** the MCP bridge is days-to-weeks of work against a documented MIT
TypeScript library — not protocol reverse-engineering. The integration work (blueprints per show,
NRCS field mapping, device inventory) is where the real effort and the real billing sit.

**License position:** MIT end to end except `CasparCG` (GPL-3.0) and `sofie-quantel-gateway`
(GPL-2.0), both of which are already separate processes driven over their own protocols. Nothing
links; nothing is disclosable.

**Qualifying question before proposing this:** *"are you on SMPTE ST 2110 yet?"* On a 2110 facility
device control is network-addressable and this is deployable; on an SDI plant it is a much larger
infrastructure conversation. ST 2110 is reported as establishing across APAC broadcasters, and EMEA
public broadcasters are the ones already running Sofie.

**Who to sell it to:** EMEA public broadcasters (Sofie is their own stack, and ARD/ZDF/DW/SRG/RAI all
published AI codes in 2026 with no tooling behind them), then APAC 2110 adopters, then the Caribbean
Broadcasting Union bloc, which asked for shared AI standards and has no in-house capability.

---

## Pattern 8 — Dual-mark provenance with ingest-side verification

**Why:** Pattern 1 signs a C2PA manifest, which is strippable by a re-encode. The previous version of
this KB said no permissive watermarking library existed to pair with it; **that was wrong** —
VideoSeal, AudioSeal and TrustMark are all MIT. But the measured counter-fact is that
**watermark-removal projects outnumber embedders 10.4× by stars and are better maintained**
(`intel/trends.md` trend 8). So the product is not a seal, it is a **chain of custody plus a
verifier**. This is also the direct remediation for the **2026-12-02** EU Article 50(2) deadline and
the **2027-01-01** California AI Transparency Act obligations.

```
GENERATION SIDE (every synthetic asset, no exceptions)
[Wan 2.2 / LTX-Video (Apache-2.0) output]
      ↓
[facebookresearch/videoseal (MIT)]        ← imperceptible payload INTO the pixels
      ↓  (audio track, if voice is synthetic)
[facebookresearch/audioseal (MIT)]        ← sample-level payload; marks WHICH segments are synthetic
      ↓  (stills / thumbnails / key art)
[adobe/trustmark (MIT)]                   ← image-domain payload
      ↓
[c2pa-rs (MIT OR Apache-2.0)]             ← signed manifest: model, version, operator, consent ID
      ↓
[c2patool (Apache-2.0)]                   ← verify the manifest in CI before the asset can ship

INGEST / VERIFICATION SIDE (the part competitors omit — and the billable one)
[Any inbound asset: UGC, partner delivery, archive, affiliate feed]
      ↓
[c2pa-rs: manifest present? signature valid? chain intact?]
      ↓  manifest absent or broken  →  NOT proof of tampering (most paths strip it)
[videoseal / audioseal / trustmark DETECTORS]   ← recover payload from pixels & audio
      ↓
[Decision record: {manifest: ok|missing|invalid, watermark: found|absent, confidence}]
      ↓
[Route: publish · label · hold for human review · reject]
```

**Wiring, and the detail that makes it honest.** Mark in **both** domains and treat the two signals
as independent evidence: a manifest proves *who signed what*, a watermark survives *the paths that
strip manifests*. Neither is sufficient. Record a **decision with a confidence level**, never a
boolean "authentic" — the four-state manifest result above matters because a missing manifest is the
*normal* case for anything that has been through a social platform, and a system that treats "no
manifest" as "fake" will be switched off in a week.

**Say the limitation out loud, with the numbers.** `guillaumemeyer/watermarks-remover` is MIT with
28,124 stars and 3,162 forks; one project names SynthID in its title. A client engineer will find
these. The regulations require a **good-faith marking effort**, not an unbreakable one — so the
asymmetry is a design constraint, and naming it first is what makes the rest of the proposal credible.

**Where the margin is:** not the embedding (three MIT libraries, a week of integration) but the
**verification service and its decision log** — the auditable record of what arrived, what was
claimed, what was recovered and what was done. That is what an Article 50 or California-Act
examination actually asks to see, and it is pure software with no licensing encumbrance.

**Pair with Pattern 4.** The consent ID from the digital-replica ledger belongs in the C2PA manifest
*and* in the watermark payload, so a performer's consent survives a re-encode that strips the manifest.

---

## Anti-patterns — learned the hard way in this KB

1. **Don't ship HunyuanVideo to EMEA or South Korea.** Its license excludes the EU, UK and KR by name.
2. **Don't treat a star count from a listicle as evidence.** Measured this pass: Kokoro is 10,273★
   (logged as ~38k), HunyuanVideo 12,815★ (logged as ~22k), ComfyUI 147,860★ (logged as ~75k).
3. **Don't assume a live URL means a live project.** `THUDM/CogVideo`, `genmoai/models`,
   `krillinai/KrillinAI`, `AirenSoft/OvenMediaEngine`, `comfyanonymous/ComfyUI` and
   `apple/ml-stable-diffusion` all still resolve — all are renames. Use canonical slugs.
4. **Don't start on archived code**: `Sanster/IOPaint` and `salesforce/LAVIS` are archived;
   `coqui-ai/TTS`, `OpenVoice`, `SadTalker` and `Grounded-SAM` are dormant 1–2+ years.
5. **Don't promise provenance alone** — but do not repeat this KB's own error either. C2PA is
   strippable by re-encoding and screenshots, so pair it with watermarking. **Corrected 2026-11-22:**
   earlier passes of this file said "no permissive open library currently exists" for watermarking.
   It does — `facebookresearch/videoseal`, `facebookresearch/audioseal` and `adobe/trustmark` are all
   MIT and all actively maintained. See Pattern 8.
6. **Don't sell a watermark as tamper-proof.** Measured 2026-11-22: watermark-*removal* repos total
   42,896 stars against 4,138 for the embedders, a **10.4× asymmetry**, with the leading remover at
   28,124★ under MIT and one project naming SynthID in its title. Promise a probabilistic chain of
   custody with ingest-side verification, and say the limitation before the client's engineer does.
7. **Don't conclude a category is empty because a capability query returned nothing.** This KB
   asserted across several passes that no open MOS-protocol implementation existed. It has existed
   since 2018, is MIT, and runs the news at NRK, the BBC and TV 2 Norway — but the query
   `mos protocol broadcast` returns exactly **one** result, a dead 2★ project from 2018, because
   Sofie's repos are named after the project rather than the capability. **Search the proper noun**
   (project, vendor, standards body, national broadcaster) and check the institutional index
   ([`ebu/awesome-broadcasting`](https://github.com/ebu/awesome-broadcasting), CC0) before recording
   an absence. An absence recorded as fact is the most expensive kind of error in this KB: it tells a
   future reader not to look.
8. **Don't judge broadcast infrastructure by stars.** `sofie-timeline-state-resolver` has 25 stars and
   25 forks; `sofie-input-gateway` has **0 stars and 5 forks**. Deployed infrastructure is forked and
   configured, not starred. Use the ★/fork ratio: around 1 means people run it, above ~50 means
   attention without use (`hikaku-io/hikaku-extension`, 407★/9f).

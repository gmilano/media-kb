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

## Pattern 9 — Ad-supported FAST channel with auditable ad breaks (the monetization build)

**Why:** advertising is now the primary driver of LATAM media growth (~$65B regional revenue in 2026),
Brazil is the world's #3 FAST market, and every component below except the decisioning layer is
Apache-2.0 or MIT. This is the first pattern in this file whose commercial driver and licence position
point the same way. New 2026-11-22.

```
[VOD library]
     |
     v
[Eyevinn/hls-vodtolive (MIT*)]        <- HLS VOD -> rolling live window
     |
     v
[Eyevinn/channel-engine (Apache-2.0)] <- assembles the linear FAST channel + ad-break signalling
     |
     +--> [Comcast/scte35-js (Apache-2.0)]  <- parse/emit SCTE-35 cues at break boundaries
     |            |
     |            v
     |    [prebid/prebid-server (Apache-2.0)]  <- server-side auction fired at the cue
     |            |
     |            v
     |    [YOUR DECISIONING SERVICE]  <- floor price, frequency cap, pacing. NOT OPEN SOURCE. Build.
     |
     v
[openplayerjs (MIT)]  <- client confirms the stitched break via SCTE-35 TextTrack cues
     |
     v
[snowplow/snowplow (Apache-2.0)] -> [apache/druid (Apache-2.0)] -> [apache/superset (Apache-2.0)]
                                      impression/bid OLAP            ad-sales reporting
```

**Wiring, concretely:**

1. `hls-vodtolive` turns the VOD catalogue into a live window; `channel-engine` schedules it as a
   linear channel. Both are small Node libraries — this is a service you run, not a platform you adopt.
2. `channel-engine` emits the ad-break opportunity. Parse and emit the cue with **`Comcast/scte35-js`,
   not `futzu/threefive`** — threefive is the better-known library and every tutorial points to it,
   but it has been dormant since 2024-11-27 and its segmenter sibling `x9k3` ships **no LICENSE file**.
3. The cue triggers `prebid-server` (Go) or `prebid-server-java` (JVM, if the broadcaster is a Java
   shop). Prebid gives you the auction and the bidder adapters; it does **not** give you pacing, floor
   pricing or frequency capping. That gap is the billable part — see `agents/top.md`, where the
   measured number of open-source ad-decisioning agents is zero.
4. `openplayerjs` is the only player in this KB whose ads plugin surfaces SSAI break boundaries as
   TextTrack cues, so the client can *verify* a stitched break rather than trust it. That verification
   event is what makes the break auditable, which is the whole point of the pattern name.
5. Impressions and bid events go to `snowplow` (collection/enrichment you own) into `druid` or `pinot`
   (pick one, they are alternatives) and out through `superset`.

**Fold in the rest of this KB — this pattern does not stand alone:**

- **Ad creative** is Pattern 2 (localization factory) with a 15-second input. One Spanish campaign,
  re-voiced per LATAM market, through the dubbing pipeline that already exists in this file.
- **AI-generated ad creative must carry provenance.** Run it through Pattern 1's `c2pa-rs` step before
  it enters the break. In the EU, South Korea, Vietnam and India that is a legal requirement, and an
  ad is exactly the asset an enforcement body examines first.
- **EMEA adds a consent layer:** `orestbida/cookieconsent` (MIT) for the banner, and the IAB TCF
  consent string — remember TCF is a **CC BY 3.0 specification, not code**, so that is an
  implementation, not a dependency.

**Licence caveats that travel with this pattern:** `hls-vodtolive` declares MIT only in
`package.json` and `x9k3` only in a `setup.py` classifier — neither has a LICENSE file. Get both
confirmed in writing before a deliverable. Everything else in the diagram is Apache-2.0 or MIT with a
real LICENSE file, which is a cleaner licence position than any other pattern in this file.

**What not to propose:** Revive Ad Server as the ad server. It is GPL-2.0, maintained, and genuinely
the only open ad server left — but it is a display/banner server, not a CTV/SSAI one. Putting it in a
FAST architecture is a category error that a broadcaster's ad-ops team will catch immediately.

---

## Pattern 10 — First-party audience graph (lowest risk in this KB)

**Why:** Deloitte's 2026 outlook identifies the binding constraint on media monetization as the fact
that **firms lack a unified view of their audiences** — cross-platform audience intelligence stays
fragmented. That is not an AI problem, it is a data-engineering problem, and it has four Apache-2.0
answers already sitting in `repos/foundations.md`. New 2026-11-22.

```
[Web / app / player / CTV events]
     |
     v
[snowplow/snowplow (Apache-2.0)]   <- schema'd first-party event collection + enrichment, self-hosted
     |
     v
[apache/druid OR apache/pinot (Apache-2.0)]   <- high-cardinality real-time OLAP
     |
     +--> [apache/superset (Apache-2.0)]      <- audience & yield reporting
     |
     +--> [Pattern 9's decisioning service]   <- the same graph prices the ad break
     |
     +--> [agents/top.md recommender work]    <- segments as features
```

**Why it is the lowest-risk engagement here:** every component is Apache-2.0 with a real LICENSE file
and an ASF or vendor-neutral maintainer; there is no model to fine-tune, no GPU, no generated content,
and therefore **no provenance or AI-labelling exposure at all** — the only pattern in this file that
can say that. It is also the prerequisite for Pattern 9 being worth anything: an auction without an
audience graph bids blind.

**The LATAM-specific reason to lead with this one:** regional growth is ad-led and Netflix holds ~50%
of streaming revenue, so a regional broadcaster's realistic strategy is not to out-subscribe Netflix
but to out-target it on local inventory. That requires exactly this graph, and it requires it before
any generative work.

**Brazil caveat:** if the output feeds a recommender, note trend 10's Brazilian bill requiring
AI-based content *recommendation* systems to surface local, community and independent outlets. The
audience graph is where that obligation would be implemented, so keep the ranking layer inspectable.

---

## Pattern 11 — Dual-duty accessible publishing (one pass, two regulators)

**Why:** a client publishing AI-assisted subtitles in the EU is inside **two** regimes at once — the
caption is an **accessibility artefact** (EAA, applied since 2025-06-28) *and* **AI-generated content**
(AI Act Art. 50, with pre-existing systems due **2026-12-02**). Everyone sells one or the other.
Nobody found in this pass sells a single pipeline that discharges both, and the components are
already permissive. New 2026-11-22 (pass 3).

```
[mezzanine / transport stream]
     |
     +--> [CCExtractor (GPL-2.0, SIDECAR PROCESS)]  <- lift existing CEA-608/708 if the asset has them
     |
     +--> [whisper.cpp (MIT)] + [jianfch/stable-ts (MIT)]   <- draft captions WITH word-level timestamps
                  |
                  v
        [pyannote-audio (MIT)]        <- speaker turns => speaker-labelled captions, not just text
                  |
                  v
        [baxtree/subaligner (MIT)]    <- forced-alignment re-sync (the defect QC actually finds)
                  |
                  v
        [SubtitleEdit (MIT)]          <- THE HUMAN REVIEW STEP. Not optional: see trend 16.
                  |
                  v
        [sandflow/ttconv (BSD-2)]     <- emit IMSC/TTML + WebVTT for web, EBU-STL back for broadcast
                  |
                  +--> [sandflow/imscHRM (BSD-2, DORMANT - vendor it)]  <- will it render in real time?
                  +--> [w3c/imsc-tests (take the BSD-3 option)]         <- cite a real conformance corpus
                  +--> [sandflow/imscJS (BSD-2)]                        <- visual proof for the client
                  |
                  v
        [contentauth/c2pa-rs (Apache-2.0)]  <- Art. 50(2) marking: the caption was AI-assisted
                  |
                  v
        [ableplayer (MIT)] + [dequelabs/axe-core (MPL-2.0)]  <- FCC display-settings duty, UI-side
```

**Wiring, concretely:**

1. **Branch on whether captions already exist.** Most broadcast libraries have CEA-608/708 buried in
   the stream; lifting them with `CCExtractor` is far cheaper and more accurate than re-ASR. Run it as
   a **separate process** — it is GPL-2.0 and there is no permissive equivalent, so the boundary is
   architectural, not a preference.
2. **Only ASR what has nothing.** `whisper.cpp` for throughput, `stable-ts` because plain Whisper's
   timestamps are not good enough to time a caption. Add `pyannote-audio` for speaker turns — that is
   the difference between a *correct* caption and a *good* one, and it is what reviewers mark down.
3. **`subaligner` before review, not after.** Drift is the most common real defect; fixing it
   mechanically keeps the human reviewer on language instead of timing.
4. **`SubtitleEdit` is the review surface** — MIT (verified; the common "it's GPL" claim is wrong),
   300+ formats, Whisper already integrated. Trend 16 is the argument for this step: the FCC named
   inaccurate automated captions in October 2026, so an unreviewed ASR pipeline transfers regulatory
   risk onto the client.
5. **`ttconv` is the format spine.** One source of truth out to IMSC/WebVTT for web and EBU-STL for
   broadcast. This is the step hybrid broadcasters get wrong.
6. **The conformance gate is the differentiator and it needs work.** `imscHRM` answers "will this
   actually render on a set-top box" and has been **dormant 920 days** — vendor it, pin it, and
   budget maintenance. Cite `w3c/imsc-tests` (BSD-3 option) in the deliverable; a gate built on
   in-house samples is not defensible to a regulator.
7. **Mark the asset with `c2pa-rs`** — this is where the pattern earns its name. The same artefact now
   satisfies the accessibility duty and the AI Act marking duty. Keep the marking **configurable**:
   per trend 14 and the EBU's confirmed lobbying, the disclosure rules may soften.
8. **Finish in the player.** `ableplayer` (MIT) carries captions, audio description and a synchronized
   sign-language track; `axe-core` gates the UI. The FCC's four factors — proximity, discoverability,
   previewability, consistency/persistence — are player-UI properties, so a caption-only pitch does
   not answer that rule.

**Shortcut if the client wants a platform, not a pipeline:** **Opencast** (ECL-2.0, permissive, pushed
2026-11-22) already ships caption as a core service (`modules/caption-api`, `caption-impl`,
`caption-remote`) with DFXP/TTML, WebVTT, SubRip and MPEG-7 converters and **local Whisper, whisper.cpp
and Vosk** engines wired in — verified by reading its source tree. Add `ttconv` as a sidecar for the
**IMSC** profile it lacks, and most of steps 2–5 are already built.

**What not to propose:** a self-hosted **Amara**. Its about page still says AGPL; it **closed its
source in January 2020** and has been proprietary since. There is no open collaborative subtitling
*platform* — only excellent open *tools*. Scope the workflow layer as a build, honestly, up front.

---

## Pattern 12 — Audio description factory (the unbuilt product)

**Why:** AD is a hard quota (FCC: 50 hours/calendar quarter in prime time or children's programming),
an EAA duty wherever the picture carries information the sound does not, and newly mandated in México
(April 2026), Brazil (ANCINE) and Argentina (Ley 26.522 art. 66). The entire open AD layer peaks at
**56 stars** and no vendor has even sized the market. There is no incumbent to displace — open or
commercial. New 2026-11-22 (pass 3).

```
[video]
   |
   +--> [Breakthrough/PySceneDetect (BSD-3)]   <- shot boundaries = candidate description points
   |
   +--> [whisper.cpp (MIT)] + [pyannote-audio (MIT)]
   |              |
   |              v
   |      DIALOGUE GAP MAP  <- the hard constraint: AD may only speak where dialogue does not
   |
   v
[VLM describes each shot]        <- Grounded-SAM / LAVIS (both already in repos/foundations.md)
   |   prompted with:
   |   [Double-FW/Audio-Descriptions (MIT)]  <- editorial rules, NOT code. Use it as the system prompt.
   v
[draft AD script, fitted to the gap map]
   |
   v
[HUMAN AD EDITOR]               <- keep this. Microsoft's own reference calls its output a draft.
   |
   v
[Kokoro-82M (Apache-2.0) | F5-TTS (MIT) | Chatterbox (MIT)]   <- the description voice
   |
   v
[FFmpeg / moviepy (MIT)]  -->  WebVTT `descriptions` track  OR  mixed described audio track
   |
   v
[ableplayer (MIT)]        <- described <source> or WebVTT descriptions track, natively
```

**Wiring, concretely:**

1. **The gap map is the whole engineering problem, and it is why this is hard.** AD is not captioning
   with different words: the description must fit **between** lines of dialogue. `pyannote-audio` +
   `whisper.cpp` give speech activity; `PySceneDetect` gives where a description is *needed*. The
   intersection — needed and permitted — is the script's skeleton. Get this wrong and the output is
   unusable regardless of description quality.
2. **Use `PySceneDetect` for candidates, not for truth.** A shot change is not necessarily new visual
   information; the VLM step filters.
3. **Prompt the VLM with a real style guide.** `Double-FW/Audio-Descriptions` (MIT) is a *documents*
   repo of editorial rules and review frameworks written for both human editors and AI agents — which
   makes it the highest-value artefact per byte in this pattern. AD has strong conventions (present
   tense, no interpretation, no spoilers); an unprompted VLM violates all of them.
4. **Keep the human editor.** Every reference implementation does, including Microsoft's.
5. **TTS choice is a licence-clean decision for once:** `Kokoro-82M` (Apache-2.0, CPU-only — relevant
   for volume), `F5-TTS` or `Chatterbox` (both MIT). No constraint to manage here.
6. **Deliver as a WebVTT `descriptions` track where possible** rather than a burnt-in mixed audio
   track — it keeps the original audio intact and lets `ableplayer` handle presentation. Mix to a
   described audio track only when the distribution path demands it (broadcast, cinema).
7. **Extended AD needs the video to pause**, which `ableplayer` supports and most players do not.
   `arnabdotorg/open-vtt` targets exactly this (WCAG 1.2.7) but is **AGPL-3.0** — read it for the
   approach, do not link it into client code.

**Reference implementations worth reading before building (none worth adopting):**
`microsoft/ai-audio-descriptions` (MIT, 56★ — the cleanest end-to-end shape; ships no auth, bind to
localhost), `asadullah48/accessai` (Apache-2.0 — the only **live** AD attempt, scores against WCAG 2.2
AAA / Section 508 / ADA Title III), `jdmiller/audio-description-generator` (MIT — uses a **local**
vision model, so it is the starting point for an air-gapped or data-resident client),
`fhswf/descraibe` (MIT, 0★ — German university, needs an external LLM key).

**Say this out loud in the proposal:** every one of those is a prototype. This pattern is a **build**,
not an integration, and that is precisely why it is worth proposing — the duty is statutory in four
regions and nobody has shipped the product. Price it as a product build with a compliance deadline
attached, not as a tooling integration.

**The LATAM caveat that must travel with this pattern:** LATAM mandates **sign language** alongside AD
(LIBRAS in Brazil, lengua de señas in Argentina/Uruguay) more consistently than NA or EMEA do, and the
open stack cannot produce it — the most visible project, `sign/translate` (now **Rylo Translate**,
Nagish Inc.), requires a **commercial licence for for-profit use**. Deliver the *carriage* (Able
Player's synchronized sign track, LIBRAS asset management) and keep the translation human or licensed.
Do not let a LATAM proposal imply automated sign language.

---

## Pattern 13 — Delivery QC gate with an evidence trail (the small build on the large obligation)

**The opportunity in one line:** the measurement is free and permissive, the *decision* has no open
implementation anywhere (`broadcast QC agent` → **0 results**, measured 2026-11-22), and the duty
touches every distributor in every region.

**What it does.** Every file about to be delivered or published passes a gate that (a) extracts
technical metadata, (b) measures loudness against the *territory's* target, (c) validates container
and format conformance, and (d) emits a signed, human-readable **evidence record** — so that when a
regulator or a distribution partner asks, the answer is a document, not a recollection.

**The parts — all real, all verified 2026-11-22:**

| Step | Component | License | Why this one |
|---|---|---|---|
| Technical metadata | [MediaArea/MediaInfoLib](https://github.com/MediaArea/MediaInfoLib) | BSD-2-Clause | The library, not the CLI — link it. Pushed 2026-11-22. |
| Format identification | [openpreserve/fido](https://github.com/openpreserve/fido) | Apache-2.0 | PRONOM-backed identification; catches "it is not the format the filename claims". |
| Loudness measurement | [jiixyj/libebur128](https://github.com/jiixyj/libebur128) | MIT | Canonical EBU R128 / ITU-R BS.1770 implementation. Target is a **parameter**. |
| Loudness in-pipeline | [csteinmetz1/pyloudnorm](https://github.com/csteinmetz1/pyloudnorm) | MIT | Fastest path to a number in Python; use for the orchestration layer. |
| Container conformance | [MediaArea/MediaConch](https://github.com/MediaArea/MediaConch) | **GPLv3+ *or* MPLv2+** | **Take the MPL-2.0 option** if the gate ships inside a client's closed system. Dormant since 2021 — vendor it and budget to carry it. |
| Visual/signal QC | [bavc/qctools](https://github.com/bavc/qctools) | GPL-3.0 | Only where a **separate process** is acceptable — GPL-3.0, so do not link it into a proprietary binary. Invoke it, read its output. |
| Format validation | [openpreserve/jhove](https://github.com/openpreserve/jhove) | LGPL-2.1+ | For still/document essence accompanying the delivery. |

**Wiring.**

1. **Profile first, code second.** Build a `territory.yaml` holding the loudness target and tolerance
   per market: **EMEA −23 LUFS / −1 dBTP (EBU R128)**; **North America** per **ATSC A/85:2026-07**,
   which as of 2026-07-08 extends to hybrid and streaming delivery; **Japan** per **ARIB TR-B32**
   (this KB records the −24 LKFS figure as *unverified secondary* — read the ARIB document before
   committing it). The target is configuration. Hardcoding it is the defect that makes the gate
   unusable in a second region.
2. **Measure, then judge, and keep them separate.** `MediaInfoLib` + `fido` + `libebur128` produce
   facts. A separate, explicit rules layer turns facts into pass/fail. Keep the thresholds in
   versioned rules the client owns — this is the same structural choice as P10's CQL library in
   healthcare, and for the same reason: **the rules are the deliverable with margin**, not the
   measurement code.
3. **The LLM writes the explanation, never the verdict.** The agent's job is to turn a failed check
   into "this file is 2.3 LU over the EMEA target and its audio is 5.1 where the contract specifies
   stereo" — prose for a human operator. The **pass/fail decision is deterministic code**. An LLM
   that decides compliance is an unauditable gate and will not survive a client's first review.
4. **Emit the evidence record and store it with the asset**, not in a log that rotates. This is the
   part clients actually pay for and no open tool produces.
5. **Human approval on every rejection that stops a delivery.** Same rule as P9 and P10: the agent
   prepares, a person approves anything with a commercial consequence.

**What to sell.** Not "AI QC". Sell **the evidence trail for a duty the client already has**, with
the honest framing from T23: in the US the statutory duty still stops at broadcast commercials and
A/85:2026-07 is a *Recommended Practice*; in EMEA R128 is the operational target. The gate is cheap
because every input is permissively licensed; it is valuable because nothing open produces the record.

**Do not promise:** an all-MIT deliverable. `MediaConch` under MPL-2.0 is file-level copyleft and
`qctools` is GPL-3.0 — architect them as a linked library and a separate process respectively, and
say so in the proposal. This is the CPT-shaped trap from healthcare in a milder form: **permissive
inputs, encumbered validator.**

## Pattern 14 — Archive to revenue: OAIS-grade ingest with an AI retrieval layer (the LATAM recipe)

**Why this pattern exists.** LATAM has **named, shipped archive-AI deployments and no open
archive-AI tooling of its own** (T24): Listín Diario's RAG platform over a 136-year archive with 25%
searchable, La Silla Vacía's **SillaBot**, ABC Color's semantic archive search. The demand is proven,
the tooling is all North American and European in origin, and there is no incumbent product. APAC
shows the same demand from a different direction — the **ABU** reports Australian and Singaporean
public broadcasters testing AI for **archiving and verification** specifically.

**The parts — all real, all verified 2026-11-22:**

| Layer | Component | License | Note |
|---|---|---|---|
| Repository core | [fcrepo/fcrepo](https://github.com/fcrepo/fcrepo) | **Apache-2.0** | **The only permissive platform in this tier.** Start here if the client is to own the result. 138 forks / 255 stars = infrastructure, not hype. |
| Preservation pipeline | [artefactual/archivematica](https://github.com/artefactual/archivematica) | AGPL-3.0 | Reference **OAIS**-conformant ingest. Integrate as a deployed system; AGPL follows a networked deployment. |
| Description & access | [archivesspace/archivesspace](https://github.com/archivesspace/archivesspace) | ECL-2.0 | Use when the client already has archivists and finding aids. |
| Transfer packaging | [LibraryOfCongress/bagit-python](https://github.com/LibraryOfCongress/bagit-python) | **Public Domain** | Zero licensing cost. Use BagIt as the handoff format between client and studio. |
| Lossless film/video | [MediaArea/RAWcooked](https://github.com/MediaArea/RAWcooked) | BSD-2-Clause | RAW scans → FFV1 in Matroska, **reversibly**. The preservation target for scanned film. |
| Analog capture | [amiaopensource/vrecord](https://github.com/amiaopensource/vrecord) | **CC-BY-4.0** | Treat as a **documented procedure to reimplement**, not code to vendor — a content license on software (T22). Much LATAM broadcast heritage is on tape, so this step is often unavoidable. |
| Speech → text | Whisper / `whisper.cpp` | MIT | Already in `repos/foundations.md`. The single highest-yield enrichment step for a news archive. |
| Visual search | [mlfoundations/open_clip](https://github.com/mlfoundations/open_clip) | MIT | Shot-level retrieval over footage with no usable metadata. |
| Vector index | [facebookresearch/faiss](https://github.com/facebookresearch/faiss) | MIT | Collection-scale retrieval. |

**Wiring.**

1. **Preserve before you enrich.** Ingest to an OAIS-conformant package (Archivematica, or Fedora
   plus BagIt if the client must own the stack) and **fix the preservation master first**. Embeddings
   are regenerable; a lost master is not. Teams that invert this order produce a searchable archive
   they cannot re-derive.
2. **Identify and validate on the way in** — `fido` for format identification, `MediaInfoLib` for
   technical metadata, `jhove` for document/still essence. An archive ingested without this produces
   confident, wrong metadata later, which is the keyword-collision failure this KB has recorded
   before.
3. **Enrich in a separate, rebuildable index.** Whisper for transcript, `open_clip` for visual
   embeddings, `faiss` for retrieval. Never write derived AI output back into the preservation master
   — keep it in a sidecar that can be thrown away and regenerated when models improve.
4. **Cite or do not answer.** Follow Listín Diario's shape: a retrieval interface over the archive
   that **always surfaces the source document**. For a newsroom this is not a nicety — an archive
   assistant that paraphrases without citation is a correction liability.
5. **Ship partial and say so.** Listín Diario is at **25% of its archive searchable** and that is
   already in production and valuable. Scope the first engagement to one decade or one collection,
   with a measured coverage number as the deliverable. "25% searchable, here is the number" is a far
   better client artefact than an unbounded digitization programme.

**What to sell.** Archive-to-revenue, with a measured coverage figure as the milestone — and, for a
regional client, the **sovereignty argument from the imec-SMIT (VUB) May 2026 finding** that European
media use AI heavily but do not control the infrastructure, models or rights that capture the value.
That argument lands even harder in LATAM, where the outlets themselves name **control over their own
content** as a primary concern. `fcrepo` under Apache-2.0 is what makes "you will own this" true.

**Do not promise:** that the preservation and the broadcast handling come from one platform. They do
not — every platform in this tier models objects and descriptions, not frames, timecode and essence
(see the gap note in `verticals/solutions.md`). Assemble it, and price the assembly honestly.

## Pattern 15 — Rights-reservation gate: a per-asset record of who may train on what

**The opportunity in one line:** publishers have been handed three ways to *declare* AI-training
terms and no way at all to **administer** them — there is no console, no per-asset policy store and
no audit trail anywhere in open source, while the settlement layer below is a measured zero
(`pay-per-crawl` top six = 5, 2, 2, 0, 0, 0 stars, measured 2026-11-22).

**Why it is defensible rather than a nice-to-have.** In the EU, the DSM Directive's **Article 4**
TDM exception applies *unless rights are expressly reserved in a machine-readable form*. A
reservation that is not machine-readable is, in practice, not made — so for an EMEA client this is
the artefact that decides whether mining their catalogue was lawful. Everywhere else it is the
evidence that underpins a licensing claim. Either way the client needs to show **what was reserved,
for which asset, from which date** — and that is a record, not a file.

**The parts — all verified 2026-11-22 (`git ls-remote` + licence bytes):**

| Step | Component | License | Why this one |
|---|---|---|---|
| Crawler blocklist | [ai-robots-txt/ai.robots.txt](https://github.com/ai-robots-txt/ai.robots.txt) | MIT, 1069 B | 4,265★, **pushed 2026-11-22** — maintained daily, and generates `robots.txt`/nginx/Caddy artefacts directly. The blunt instrument, and the one that works today. |
| EU machine-readable reservation | [w3c-cg/tdm-reservation-protocol](https://github.com/w3c-cg/tdm-reservation-protocol) | ⚠️ **W3C Software and Document Licence**, 432 B | **TDMRep** — the protocol built for Article 4. Ratio 1.2 (17★/14f) = real infrastructure. Read the licence before vendoring; it is not OSI-style permissive. |
| Granular commercial terms | **RSL 1.0 spec** (`rslstandard.org`) | ⛔ **repo has NO LICENCE FILE** | The standard Reddit, Yahoo, Medium, Quora and Ziff Davis back. Supports free / attribution / subscription / **pay-per-crawl / pay-per-inference**. Use the **published spec**, not the repo's code. |
| RSL authoring | [onurkanbakirci/rsl-editor](https://github.com/onurkanbakirci/rsl-editor) | MIT, 1070 B | 22★ — small, and **the only properly licensed RSL tool found.** |
| Honouring, on the ingest side | [Spawning-Inc/datadiligence](https://github.com/Spawning-Inc/datadiligence) | MIT, 1079 B | The only library for *respecting* opt-outs. **Dormant since 2024-10-09** — vendor it, budget to carry it, and say so. |
| Asset identity for the record | [iscc/iscc-sdk](https://github.com/iscc/iscc-sdk) | Apache-2.0, 11339 B | ISO 24138 content code, so the reservation attaches to **the content**, not to a URL that will change. |
| Catalogue spine | [beetbox/beets](https://github.com/beetbox/beets) | MIT, 1079 B | Where the per-asset policy actually lives for audio. MIT at the platform tier — no copyleft on the product. |

**Wiring.**

1. **Policy is data, in the client's repository.** One `reservation.yaml` per collection: scope,
   permitted use, licence class, effective date, contact. Everything downstream is a *rendering* of
   that file. Hardcoding terms into templates is the defect that makes the gate unusable the first
   time legal changes its mind.
2. **Render to all three surfaces from the single source.** `robots.txt` (via `ai.robots.txt`'s
   generated artefacts), TDMRep assertions for the EU, and an RSL document for commercial terms. They
   are not alternatives — they address different readers (crawler operators, EU law, licensing
   counterparties).
3. **Bind the reservation to a content code, not a path.** Generate an ISCC per asset with
   `iscc-sdk` and key the policy store on it. URLs rot and CDNs rewrite them; a content-derived code
   survives re-encoding and re-hosting, which is exactly what a dispute two years later will turn on.
4. **Emit a dated, immutable evidence record per asset** — reservation text, ISCC, timestamp, the
   rendered artefacts' hashes. Store it *with* the asset, never in a rotating log. **This is the
   deliverable clients pay for and nothing open produces it.**
5. **Deterministic rendering; the LLM writes prose only.** The agent drafts human-readable summaries
   and explains a policy to an editor. It must never decide a licence class. Same rule as P10 and
   P13: an LLM that decides compliance is an unauditable gate.
6. **Human approval on anything that changes commercial terms.** Reserving rights is a legal act.

**What to sell.** Not "AI blocking". Sell **the per-asset reservation record and its audit trail** —
in EMEA as the Article 4 compliance artefact and a **digital-sovereignty** story (the join key never
leaves the client's estate), in North America as the administration layer under terms their peers
have already published.

**Do not promise:** that AI labs will honour any of it. Whether they come to the table is genuinely
unresolved — TechCrunch frames it as the open question of RSL, and this pattern's value does not
depend on the answer: the record is what supports a claim, a negotiation or a licence sale.
**Also do not ship the RSL repo's code** — it is unlicensed, so default copyright applies. Flag that
in the proposal; it is a real supply-chain finding (`intel/trends.md` §27).

**Falsifiable prediction, registered 2026-11-22.** This KB's healthcare pass established that when a
regulator turns a judgment into a computable artefact, permissive open source appears for that
judgment **and appears before the mandate**. Article 4 has already made the *reservation* computable,
and TDMRep exists. The judgment still uncomputed is **"was this use licensed?"** — the settlement
step. The prediction: **the first permissive implementations of AI-training-use settlement will appear
within 1–2 standardisation cycles of a regulator or court making the accounting unit explicit, and the
leading indicator is a published spec for a usage report — not GitHub activity.** Watch DDEX's
AI rights-reservation message and the RSL Collective's reporting format. If a permissive settlement
library with a ratio under ~5 appears *before* any such spec, this prediction is wrong and the
structural law needs revising.

## Pattern 16 — Identification to attribution: a content-ID spine for a catalogue nobody can match

**Why this pattern exists, with a government's number behind it.** The UK government's **music
streaming metadata report (April 2026)** found **no central registry for ISRCs** and **ISRC-to-ISWC
matching rates ranging from 0% to 85%** depending on source. Music Business Worldwide calls linking
works to recordings music data's *"single biggest unsolved problem."* That gap between 0% and 85% is
not a tooling complaint — it is a **measured reconciliation defect from a primary public source**,
which makes it scopeable and sellable as an outcome.

**What it does.** Takes a client's existing library — a broadcaster's archive, a label's catalogue, a
rights-holder's masters — and produces, per asset: a **content-derived identity** that survives
re-encoding, a **best-match registry identity** with a confidence score, and a **queue of the residue**
for human adjudication. The output is a join key the client owns and an auditable match record.

**The parts — all verified 2026-11-22:**

| Step | Component | License | Why this one |
|---|---|---|---|
| Catalogue spine | [beetbox/beets](https://github.com/beetbox/beets) | **MIT**, 1079 B | 15,972★, ratio 7.2, pushed 2026-11-22. Already wires fingerprint → identity → tags, with a real plugin API. **The MIT exception at the platform tier** — extend it without copyleft reaching the product. |
| Audio fingerprint (default) | [acoustid/chromaprint](https://github.com/acoustid/chromaprint) + [beetbox/pyacoustid](https://github.com/beetbox/pyacoustid) | ⚠️ **LGPL-2.1 as a whole** / MIT | The industry standard, and what `beets` already calls. **Read §28 of `intel/trends.md` first: its licence depends on which FFT library you link.** |
| Audio fingerprint (permissive) | [worldveil/dejavu](https://github.com/worldveil/dejavu) *or* [dpwe/audfprint](https://github.com/dpwe/audfprint) | MIT | When permissive is a hard requirement. Both **dormant** (2024-04, 2019-09) and both reference-grade (ratio 4.6; Columbia/Google provenance). **Vendor and budget the maintenance.** |
| Audio fingerprint (embedded / active) | [JorenSix/Olaf](https://github.com/JorenSix/Olaf) or [Panako](https://github.com/JorenSix/Panako) | **AGPL-3.0** | The only *maintained* options; Panako is pitch/time-scale **invariant**, so it survives broadcast speed-ups. **Network copyleft — architecture decision, not paperwork.** |
| Broadcast / live matching | [adblockradio/stream-audio-fingerprint](https://github.com/adblockradio/stream-audio-fingerprint) | MPL-2.0 | The only repo here built for **real-time** stream matching (it detects radio ad breaks). File-level copyleft, linkable. |
| Standards-backed content code | [iscc/iscc-sdk](https://github.com/iscc/iscc-sdk) | Apache-2.0 | **ISO 24138:2024.** Similarity-preserving codes across text, image, audio, video. The internal join key. |
| Video near-duplicates | [akamhy/videohash](https://github.com/akamhy/videohash) | MIT, 1075 B | Perceptual video hashing; pair with `PySceneDetect` (BSD-3) to hash **per scene** rather than per file. |
| Metadata authority | [MusicBrainz](https://github.com/metabrainz/musicbrainz-server) / [Picard](https://github.com/metabrainz/picard) | GPL-2.0 | Run as **services you integrate with**, not code you ship. Picard is the working proof of the fingerprint→identity join. |
| Delivery-format ingest | [miqwit/dedex](https://github.com/miqwit/dedex) | MIT, 1063 B | DDEX **ERN** parsing where the client receives or sends release notifications. Ratio 2.0 — small, but the only live permissive DDEX code found. |

**Wiring.**

1. **Generate two identities per asset, never one.** An **ISCC** (content-derived, free, client-owned,
   survives re-encoding) *and* a **registry identity** (ISRC/ISWC/EIDR, authoritative, paid). The
   ISCC is the primary key inside the estate; the registry ID is a foreign key out to the industry.
   Conflating them is the mistake that makes the whole build non-portable.
2. **Fingerprint, then match, then score — and keep the residue visible.** Never silently accept a
   low-confidence match. The 0–85% range *is* the product: a match table with confidence bands and an
   explicit **unmatched** queue beats a table that looks complete and is wrong.
3. **The LLM adjudicates nothing; it prepares adjudications.** The agent assembles the evidence for a
   human — candidate matches, differing credits, conflicting durations — and writes the summary. The
   **match decision above the auto-accept threshold is deterministic code**; everything below goes to
   a person. A hallucinated ISWC is a royalty misdirected to the wrong writer, which is a legal
   problem, not a quality problem.
4. **Store the match record, not just the match.** Which fingerprinter, which version, which
   threshold, which human approved it, when. Royalty disputes are retrospective.
5. **Integrate the registries; do not try to replace them.** EIDR, ISAN, ISRC and ISWC have **no open
   implementations** — measured this pass (`eidr` → 160 results, zero relevant; `isan` → 1,942,
   zero relevant). The client already pays for the memberships. That is integration work, priced as
   integration work.

**What to sell.** The **attribution layer and its audit trail** — not a fingerprinting tool. The
inputs are free and permissive; the reconciliation judgment has **no open implementation anywhere**
(`music royalty accounting` → 14 results, **top six hold zero stars between them**). This is the
same structural position as healthcare's CQL library: the rules and the match records are the
deliverable the client owns, versions and audits.

**Do not promise:** an all-open-source rights or royalty stack. The output of this process is
expressed in identifiers controlled by IFPI, CISAC, ISAN-IA and the EIDR Association — **the
obligation travels with the content, not the code**, exactly as CPT does in healthcare. And do not
pitch **ISCC** as an identifier the client's partners will recognise: it is ISO-published and
Apache-2.0, and its reference implementation has **26 stars**. It is the internal join key and a
standards-backed bet — nothing more, and that is still worth a great deal.

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
9. **Don't believe a project's own "we are open source" page.** Added 2026-11-22. **Amara's** about
   page still states everything it does is available under the AGPL; Amara **closed its source in
   January 2020** and has been proprietary since, with stale docs still promising a GitHub repo.
   `sign/translate` (ex-`sign.mt`, now **Rylo Translate**) reads as open source on GitHub and is
   dual-tier source-available, requiring a **paid commercial licence** for for-profit use. **Read the
   LICENSE file in the default branch, every time** — not the README, not the About sidebar, not the
   marketing site. Both of these would have reached a client as "open source" on any other method.
10. **Don't sell automated captions as a compliance deliverable in the US.** Added 2026-11-22. The
   FCC's 2026 CVAA report (2026-10-07) explicitly names *inaccurate automated captions*. The FCC sets
   no accuracy percentage and judges errors in context, so unreviewed ASR transfers regulatory risk to
   the client rather than removing cost. Sell the reviewed pipeline (Pattern 11). Also: the claim that
   the CVAA mandates **99% accuracy** for AI live captions is unsourced and contradicts the FCC's own
   position — it is in several vendor blogs and must not enter a client deck.
11. **Don't answer a caption rule with a caption file.** Added 2026-11-22. The FCC's
   display-settings rule (compliance date 2026-08-17) is judged on **proximity, discoverability,
   previewability and consistency/persistence** — all properties of the *player UI*. The EAA likewise
   requires the service to expose audio description, not merely to possess it. A proposal that stops
   at generating assets does not address either rule; `ableplayer` + an `axe-core` gate does.
12. **Don't assume the compliance pitch ports across regions.** Added 2026-11-22. The EAA/FCC
   "you are legally obliged" framing is the wrong opening in APAC, where an industry source reports
   **no captioning, subtitling or dubbing requirement at all** in some Asian pay-TV and streaming
   markets. There, accessibility is a reach-and-differentiation sale. Check the jurisdiction's actual
   duty before choosing the argument — and see `intel/market.md` for the Japan and India gaps this KB
   has **not** closed.

---
industry: media
region: Global
updated: 2026-11-28
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
     +--> [repos/foundations.md recommender stack]  <- segments as features; see Pattern 20
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

## Pattern 17 — Studio-grade pipeline agent on OpenAssetIO + OpenTimelineIO (the 1-star opportunity)

Added 2026-11-25 (pass 6). **The highest-differentiation build in this file, and the cheapest to
start.** Every component is Apache-2.0 or BSD-3-Clause, the standards are maintained this week by a
Linux Foundation project, and the three connectors the build needs have **1, 2 and 10 stars** — which
means no incumbent, no vendor alternative, and a realistic path to becoming the maintainer.

**The problem it solves.** A studio's agent can be told "re-render shot 040 with the approved lighting
and publish it as v12". To do that it needs three things no LLM has: *what an asset is* (resolution),
*where it sits in the edit* (timeline), and *how to get it made* (farm). Those three layers exist,
are permissive, and are not connected to anything agent-shaped.

**Wire-up:**

1. **Asset identity and resolution — `OpenAssetIO`** (Apache-2.0, 353★, pushed 2026-11-25). The
   vendor-neutral answer to "what is this asset and where does it live". Develop against
   `OpenAssetIO-Manager-BAL` (Apache-2.0, 9★) as the reference manager, and generate your traits with
   `OpenAssetIO-TraitGen` (Apache-2.0, 7★). Use `OpenAssetIO-MediaCreation` (16★) for the media
   trait set rather than inventing one.
2. **The agent surface — `OpenAssetIO/openassetio-mcp`** (Apache-2.0, **1★**, 2026-05-18). This is the
   repo that makes the whole pattern an agent build instead of a scripting project. **It is one star
   and five months quiet: expect to fork it, fund it, and offer the work upstream.** That is the
   differentiator, not a risk to hide.
3. **Timeline truth — `OpenTimelineIO`** (Apache-2.0, 2,117★, pushed 2026-11-25). The edit is the
   only artefact that knows which shots matter and in what order. ⚠️ The official bridge
   `OpenAssetIO/otio-openassetio` (Apache-2.0, 10★) has been **dormant since 2024-07-26** — budget to
   revive it; it is small and it is exactly the join.
4. **Scene assembly — `PixarAnimationStudios/OpenUSD`** (⚠️ **Tomorrow Open Source Technology
   License 1.0**, 7,675★) resolved through `OpenAssetIO/usdOpenAssetIOResolver` (Apache-2.0, 28★) or
   `LucaScheller/VFX-UsdAssetResolver` (Apache-2.0, 141★). For natural-language scene assembly,
   `binary-core-llc/bowerbot` (Apache-2.0, 39★, pushed 2026-11-25) is the only right-shaped project
   found; treat it as a reference, not a dependency.
5. **Execution — `AcademySoftwareFoundation/OpenCue`** (Apache-2.0, 1,010★). Deploy unmodified. Its
   job records are also the evidence trail Pattern 18 needs, so do not wrap it in anything that
   discards them.
6. **Environment determinism — `rez`** (Apache-2.0, 1,101★). An agent that cannot pin the exact
   package set it rendered with cannot reproduce its own output; without this the whole build is a
   demo.
7. **Review and sign-off — `OpenRV`** (⚠️ Apache-2.0 *except* `Notice.txt` components, 797★) or
   `xstudio` (Apache-2.0, 782★). **Neither has any agent bridge** — if the engagement has appetite,
   this is the second unbuilt product in this plane.

**Licence position:** clean. Apache-2.0/BSD-3 throughout, with two things to state in writing —
OpenUSD's renamed licence (trademark clause differs from Apache-2.0) and OpenRV's `Notice.txt`
carve-outs. Keep agents and prompts in **your own service**, talk to platforms over their APIs, and
if a tracker is involved use the Apache-2.0 client (`ayon-core`) or the LGPL client (`gazu`) — never
`ayon-backend` (FSL-1.1-ALv2, not open source).

**Who buys it:** North American studios first — the substrate originated there and is already
installed (`intel/market.md`, NA). APAC and LATAM service studios second, where owning the pipeline
is the answer to margin compression rather than an efficiency story (see trend 36).

## Pattern 18 — VFX tax-credit apportionment trail (the CFO-sponsored build)

Added 2026-11-25 (pass 6). **The only recipe in this file whose sponsor is the finance department,
and the one with a statutory deadline attached.**

**The duty.** UK additional VFX relief can be claimed on up to **100% of eligible UK VFX spend**, and
**generative-AI costs inside the VFX process are eligible** (the proposed exclusion was dropped after
consultation). But costs such as filming against an LED volume are **not** VFX costs, so a
virtual-production shoot must **apportion** spend between eligible and ineligible work — per shot, per
task, defensibly, months after the fact. ⚠️ Carried at trade-press/advisory confidence only:
`www.gov.uk` does not resolve from this session. **Verify the current rules and the post-1-April-2027
position with the client's tax advisor before scoping.**

**Wire-up:**

1. **The spine — `OpenTimelineIO`** (Apache-2.0, 2,117★). Every claim is ultimately "this shot, these
   frames, this work". The timeline is the only artefact that carries that natively; everything else
   hangs off it.
2. **Stage vs. VFX discrimination — `SMPTE/ris-osvp-metadata-camdkit`** (BSD-3-Clause, 55★) and
   `mosys/opentrackio-cpp` (MIT, 15★). OpenTrackIO camera/lens/stage metadata is what *distinguishes*
   an LED-volume capture from downstream VFX work. Without it the apportionment is an opinion; with
   it, it is a record. Unreal Engine has supported OpenTrackIO officially since **5.6** (vendor
   documentation).
3. **Cost attribution — `OpenCue`** (Apache-2.0, 1,010★) job records plus `rez` (Apache-2.0, 1,101★)
   environment pins. Render hours are the largest attributable VFX cost and OpenCue already records
   them per job; the work is joining job → shot → claim category, not instrumenting from scratch.
4. **Asset lineage — `OpenAssetIO`** (Apache-2.0, 353★). Answers "which version of which asset was
   used in the frame being claimed for", which is the question an auditor asks second.
5. **Provenance on anything generative — C2PA** (see Pattern 1 and Pattern 8). If AI cost is being
   claimed as eligible VFX spend, the claim is far stronger when each generated asset carries signed
   Content Credentials. This is the one place in the KB where **provenance tooling pays for itself in
   cash rather than compliance**.
6. **Output.** A per-shot ledger: eligible VFX spend, ineligible production spend, the evidence for
   each line, and an immutable record of the split. Deliver it as a report the client's advisors can
   audit — not as a dashboard.

**Why it wins:** it is narrow, it is measurable, the budget is already allocated (the relief is worth
more than the build), and no vendor in this KB's market map sells it. It also drops straight into
Pattern 17 — same artefacts, different reader.

**Portability warning:** this is a **UK-specific** recipe. Do not re-pitch it in NA, where the
binding constraint on AI in production is a **labour agreement**, not a tax credit — there the same
artefacts produce the record described in trend 37, which is a different deliverable with a different
buyer. Check the jurisdiction's actual instrument before choosing the argument.

## Pattern 19 — Agent-enabled review and approval (the smallest unbuilt product in this plane)

Added 2026-11-25 (pass 6). Named separately because it is the one gap in this plane that a **single
developer** can close, and because notes-and-approvals is the most agent-shaped workflow in post
production.

**The measured gap.** `OpenRV` (797★, Apache-2.0 except `Notice.txt`) and `xstudio` (782★,
Apache-2.0) are both permissive, both active (pushed 2026-11-25 and 2026-11-20), and **neither has
any agent bridge that this pass could find**. Review sessions generate exactly the data an agent is
good at: timecoded notes, versions, approvals, who asked for what.

**Wire-up:** `xstudio` (Apache-2.0 — prefer it over OpenRV purely for the cleaner licence) as the
review application → an MCP server you own exposing *list versions*, *fetch notes*, *compare*,
*record approval* → `OpenTimelineIO` for note→shot→edit placement → `OpenAssetIO` for version
identity → Kitsu via `gazu` (LGPL-3.0, 98★) or AYON via `ayon-python-api` (Apache-2.0, 17★) to write
the task status back.

**The honest scope:** this is days-to-weeks, not months, and its value is that it demonstrates the
whole of Pattern 17 on a workflow a client can see in a single review session. Use it as the wedge.
It is also the cheapest credible way to become a named contributor in an ASWF project, which is the
credential this plane actually respects.

## Pattern 20 — Panel-free audience intelligence with provable lift (the demand-side flagship)

**Why:** this is the plane's commercial answer to a barrier this KB can now price. A national audience
currency costs **~$110M/year to operate** and Nielsen holds **85–90%** of US spend (CIMM, January 2026 —
`intel/market.md` North America), so a client will never own one. But eMarketer's H1 2026 read is that
**outcome-based measurement is overtaking the currency debate**, and *that* layer is permissive, active
and free. This recipe builds what the client can own: their own audience graph, a recommender on top of
it, and a defensible measurement of whether it worked. New 2026-11-25.

It also supersedes nothing: **Pattern 10 is the lower half of this stack** (collection → OLAP →
reporting). Pattern 20 adds the two layers Pattern 10 pointed at and this KB did not have — **the
recommender and the proof.**

```
[Web / app / player / CTV events]
     |
     v
[jitsucom/jitsu MIT  OR  snowplow/snowplow Apache-2.0]   <- consent-gated, schema'd collection
     |                                                      (NEVER rudderlabs/rudder-server: ELv2)
     v
[ClickHouse/ClickHouse Apache-2.0  OR  apache/druid Apache-2.0]   <- high-cardinality event store
     |
     v
[cube-js/cube Apache-2.0]        <- THE SEMANTIC LAYER: "view", "unique viewer", "completion"
     |                              defined ONCE so recommender, ad stack and board deck agree
     +--> [moj-analytical-services/splink MIT]        <- identity resolution across device/profile
     |
     +--> [recommenders-team/recommenders MIT 22,012*] <- candidate generation + ranking
     |      \__ [NVIDIA-Merlin/Transformers4Rec Apache-2.0] <- session-shaped ranking (the media case)
     |      \__ [RUCAIBox/RecBole MIT] <- offline benchmark: EVIDENCE that model B beat model A
     |      \__ [gorse-io/gorse Apache-2.0] <- if the client wants a service, not a library
     |
     +--> [growthbook/growthbook MIT core]  <- online experiment: CUPED + sequential testing
     |                                         => the lift number that survives a CFO
     +--> [google/meridian Apache-2.0  OR  facebookexperimental/Robyn MIT]
     |         <- media-mix / incrementality: what the SPEND did, with no panel
     +--> [apache/superset Apache-2.0  OR  getredash/redash BSD-2-Clause]  <- reporting
```

**Why this is the strongest-licensed pattern in this file.** Every component is MIT, Apache-2.0 or
BSD — **no copyleft, no carve-out in any path actually used** (GrowthBook's carve-out is three
`enterprise` directories the open core does not need), and no generated content, so **no provenance or
AI-labelling exposure at all.** Pattern 10 previously held that distinction; this extends it through the
recommender and measurement layers.

**The three substitutions that make it defensible rather than merely cheap:**

1. **Cube instead of per-team SQL.** Deloitte names the binding constraint on media monetization as the
   absence of a unified audience view. That is a *definition* problem before it is a data problem — Cube
   is the cheapest place to fix it, and it is what makes the recommender's features and the ad stack's
   segments the same thing.
2. **RecBole offline + GrowthBook online.** The recommender claim a client will challenge is "is this
   better than what we had?" RecBole answers it on history across 90+ algorithms; GrowthBook answers it
   in production with variance reduction. **Together they are the only honest answer**, and neither
   requires a currency.
3. **Meridian/Robyn instead of a rating.** Reach and frequency have **no open implementation** (`reach
   frequency curve media` returns one result and it is an unrelated ML tutorial). Do not try to rebuild
   them. Model the outcome instead — which is what advertisers are migrating to anyway.

**Regional shaping — the same stack, a different lead in each region:**

- **North America:** lead with **incrementality**, not audience. The client has a currency and resents
  it; they do not need a second one. Adopt `googleanalytics/google-analytics-mcp` (Apache-2.0, 3,866★)
  if they are on GA4. Nielsen's own natural-language interface is slated for **early 2027**, so the
  window for a client-owned agentic layer is roughly twelve months.
- **EMEA:** lead with **auditability and residency**. Every component self-hosts; Splink's UK Ministry
  of Justice provenance survives procurement review; Cube makes the method readable to a regulator —
  which matters because EMFA is being applied to audience measurement. **Do not propose ACR against
  third-party content:** that is what was cease-and-desisted in January 2026.
- **APAC:** lead with **comparability**. The region's own press blames fragmented measurement for ad
  dollars lagging viewers, and a vendor survey says the barrier to personalisation is unified data, not
  AI. `alibaba/RecIS` (Apache-2.0) is an easier internal sell in the region than a US-origin library.
- **LATAM:** lead with **granularity beating the panel**. Nielsen IBOPE's Mexican streaming panel is
  **1,650 households** against 42,000+ in the US; the client's own logs are genuinely more informative
  about their own long-tail local inventory. Then apply Pattern 21, because Brazil regulates the ranker.

**What not to promise.** No open-source currency, no certified rating, no clean room (both
industry-backed open clean rooms are **archived** — use `google/private-join-and-compute` Apache-2.0 for
the actual primitive), and no claim that OP3 is IAB-certified (it states certification as a *goal
contingent on sponsorship*).

---

## Pattern 21 — The inspectable ranker: an explainability and steerability gate for recommendations

**Why:** two regions now regulate the **recommender itself**, not the content it serves, and they
require opposite-looking things that are built in the same place. **Brazil:** LGPD **Article 20** gives a
right to review automated decisions, the **ANPD became a fully independent regulator in February 2026**
with enforcement priorities that explicitly name the use of personal data for advertising, and a
Brazilian bill already recorded in `intel/market.md` would require recommendation systems to **surface
local, community and independent outlets**. **Australia:** a **new transparency obligation for
automated decision-making** is progressing alongside the second tranche of Privacy Act reforms. A
recommender is an automated decision system. New 2026-11-25.

So the ranker must be able to answer two questions on demand: **"why was this shown to this person?"**
(explainability) and **"show that you can be made to favour this category"** (steerability).

```
[Pattern 20's audience graph + semantic layer]
     |
     v
[recommenders-team/recommenders MIT]      <- candidate generation + ranking, in YOUR process
     |                                       (an opaque hosted recommender cannot satisfy Art. 20)
     +--> [RUCAIBox/RecBole MIT]
     |       <- benchmark record: WHICH algorithm was chosen, on WHAT measured grounds
     |          => the "we evaluated alternatives" evidence a regulator asks for
     |
     +--> [a per-decision record: {user segment, candidate set, features, score, rule applied}]
     |       stored in [ClickHouse Apache-2.0] beside the events that produced it
     |       => this is the Article 20 artefact. It is a LOG, not a model card.
     |
     +--> [Flagsmith BSD-3-Clause]  <- the steerability lever: a flagged, auditable
     |       "local & independent content boost" that can be turned on, tuned and EVIDENCED
     |       per market without a redeploy
     |
     +--> [growthbook/growthbook MIT core]  <- proves the boost's cost in engagement, so the
             obligation is negotiated with a number instead of absorbed blind
```

**The non-obvious design point, and it is the whole pattern:** the deliverable is **a per-decision log,
not an explainable model.** Article 20 and Australia's ADM transparency ask what happened to *this
person's* decision — a question answered by a record, not by model interpretability. This is the same
conclusion pass 6 reached for North American labour contracts ("a per-shot record of what the AI did,
not a label on the output") arriving independently in a different plane from a different regulator.
**Third plane in this KB where the sellable artefact turns out to be an evidence trail.**

**Why Flagsmith and not Unleash:** Unleash is **AGPL-3.0** (verified by reading `LICENSE`, 34,523 B —
the published comparisons calling it Apache-2.0 are wrong). Flagsmith is **BSD-3-Clause**, so the
steerability lever can be embedded in the streaming service itself.

**Honest limits of this pattern:**

- **Brazil's PL 2338/2023 status is contested** across sources — one holds that LGPD still governs with
  no AI statute in force, others claim enactment in December 2025 with phased 2026 implementation.
  **Build the log either way** (Article 20 is not contested), but do not cite the statute to a client
  until it is verified against an official source.
- The local-content provision is **a bill, not law**. The flag costs little to build and converts the
  obligation from a rewrite into a configuration change, which is the reason to build it now.
- **No open-source implementation of this gate exists** — `identity resolution advertising` returns four
  repos and the only on-topic one has 0 stars. This is a build, and that is the point: it is a
  differentiator, not a procurement.


## Pattern 22 — Permissive low-latency live chain with an operations agent (the empty-shelf build)

**The gap it fills.** The substrate of this plane is the healthiest in this KB and its
delivery-operations agent layer is a measured zero: five stars-sorted queries, one returning
*literally* zero results, and the only real-time agent at any star count is `yondonfu/ai-rtc-agent`
(26★, MIT, **last pushed 2024-11-04**). Boards have authorised the money — 87% of M&E boards have
approved major AI investments — and there is nothing on the shelf for the layer that runs the
business.

**The stack, all verified 2026-11-26 and all permissive:**

| Role | Component | Licence |
|---|---|---|
| Contribution | `Haivision/srt` (MPL-2.0) or `Eyevinn/whip` (Apache-2.0, RFC 9725) | weak/permissive |
| Ingest + routing | `bluenviron/mediamtx` (MIT, 20,772★) — or `ossrs/srs` (MIT) at scale | MIT |
| WebRTC plumbing | `pion/webrtc` (MIT) | MIT |
| Broadcast→browser bridge | `Eyevinn/srt-whep` (Apache-2.0) | Apache-2.0 |
| Transcode | `FFmpeg/FFmpeg` — **build LGPL-2.1+, do NOT pass `--enable-gpl`** | LGPL-2.1+ |
| Packaging | `shaka-project/shaka-packager` (BSD-3) + `Eyevinn/mp4ff` (MIT) for segment surgery | BSD/MIT |
| Edge | `apache/trafficserver` (Apache-2.0) | Apache-2.0 |
| Players | `video-dev/hls.js` or `shaka-project/shaka-player` (both Apache-2.0) | Apache-2.0 |
| Objective quality | `Netflix/vmaf` (**BSD-2-Clause-Patent — express patent grant**) | permissive + patents |

**Wiring.**

1. Contribution lands on MediaMTX over SRT (or WHIP from a browser/OBS encoder — `obs-studio` has
   pushed WHIP since v30; run it as a *tool*, never link it, because it is GPL-2.0).
2. MediaMTX fans out to an FFmpeg ladder; Shaka Packager produces CMAF with `cbcs` (the scheme
   FairPlay requires, and the one that lets a single encrypted asset serve all three DRMs).
3. Traffic Server fronts the origin; `hls.js`/`shaka-player` report QoE events back.
4. **The agent** — this is the part you are building, because it does not exist — consumes
   player QoE, origin/edge logs and VMAF scores, and acts on: rendition-ladder changes, segment
   re-packing, origin failover, and cache-rule adjustments. Every action it takes is a config change
   against components above, so each one is reversible and auditable.
5. `Eyevinn/mp4ff` lets the agent manipulate ISOBMFF segments directly in Go under MIT — the piece
   that makes "re-pack a failing rendition" an actual operation rather than a restart.

**Two boundaries the agent must not cross.** The **DRM key step** (contractual — see Pattern 24) and
**codec selection** (patent-pooled — trend 44). An agent that "optimises" a client onto VVC has
created a royalty obligation nobody priced.

**Licence hygiene that decides whether you own the result:** build on MediaMTX/SRS (MIT), **not** on
`OvenMediaEngine` (AGPL-3.0) or `ant-media` (no root licence), or the agent you write inherits a
distribution problem. Do not link `axiomatic-systems/Bento4` — it is **GPL-2.0 + paid commercial**,
with the text hidden at `Documents/LICENSE.txt` where GitHub reports "no licence".

**Sell it as:** cost per delivered stream and incidents-avoided-per-month. In APAC that is a board
number (adspend +5.2%, the slowest since the pandemic, against a USD 200bn screen economy).

---

## Pattern 23 — DTV+ / TV 3.0 codec-royalty and conformance trail (the LATAM build with a deadline already past)

**The situation.** Brazil's **DTV+ / TV 3.0** went live **2026-06-11** (Rio, São Paulo, Federal
District), mandating **VVC + MPEG-5 LCEVC** video and **MPEG-H Audio including over HDMI on every
receiver**. All three mandated codecs' reference implementations **explicitly refuse to grant patent
rights**, and MPEG-H has **no open encoder at all** — only `Fraunhofer-IIS/mpeghdec`, a decoder.
Exposure is therefore **accruing now**, for every broadcaster, receiver maker and integrator in the
country.

**What you build.**

1. **A codec-layer inventory.** For each delivered stream: which codec, which layer (base VVC vs
   LCEVC enhancement), which audio system, which encoder produced it, and which pool administers the
   relevant patents. The licences themselves point you at "the respective patent owners", so the
   mapping is the deliverable.
2. **A conformance and evidence trail** per emission, reusing the QC machinery from **Pattern 13**:
   the artefact, the tool version, the operator, the timestamp, the result.
3. **Toolchain placement, stated honestly.** Verified reference points:
   - `fraunhoferhhi/vvenc` / `vvdec` — BSD-3-Clause-Clear, **no patent grant**
   - `v-novaltd/LCEVCdec` — The Clear BSD License, **no patent grant** (decoder; 35★)
   - `Fraunhofer-IIS/mpeghdec` — Fraunhofer FDK, **§3 "No PATENT LICENSE"** (decoder only)
   - Everything *around* the codecs is permissive and usable: `gpac/gpac` (LGPL-2.1),
     `shaka-packager` (BSD-3), `Eyevinn/mp4ff` (MIT), `FFmpeg` (LGPL-2.1+ if built without
     `--enable-gpl`)
4. **A dual-chain matrix** for the transition period: legacy ISDB-Tb alongside DTV+, two encodes, two
   audio paths, receiver-compatibility coverage at the Intelbras/Aquario tier.

**What you must not promise.** That open source removes the royalty. It does not, by the explicit
terms of all three licences. The deliverable is a **defensible, itemised exposure map and an evidence
trail** — which is what a CFO can act on, and what nobody in the region currently has.

**Who sponsors it.** The CFO, not the CTO. This is the LATAM twin of **Pattern 18** (VFX tax-credit
apportionment): a regulator or standard created a financial obligation, and the product is the
auditable trail that bounds it.

---

## Pattern 24 — Multi-DRM delivery where the key boundary is explicit (the pattern that saves a programme)

**Why this exists as a pattern.** The single most common way a premium-video programme fails late is
discovering in month four that the open-source stack cannot issue DRM licences — because every guide
shows an open packager encrypting content and then goes quiet. **Gate 2 is structural:** packaging and
Common Encryption are fully open; the key and licence server for Widevine, PlayReady and FairPlay are
not available as open source at all, by design.

**The architecture, with the boundary drawn on purpose.**

1. **Encode once, package once.** `shaka-project/shaka-packager` (BSD-3) produces a single CMAF asset
   under **CENC (ISO/IEC 23001-7)**. Choose **`cbcs`** (AES-CBC) as the primary scheme: FairPlay
   requires it, and Widevine and PlayReady accept it on modern clients.
2. **Keep a `cenc` (AES-CTR) variant only if you must** support older PlayReady 3.x / early Widevine
   CDMs that decrypt CTR only. That is a device-support decision with a storage cost — make it
   explicitly, not by accident.
3. **Cross the boundary commercially.** Three separate licence requests, endpoints and key-delivery
   protocols, each under a signed agreement: Google's partner programme (Master Licence Agreement +
   security questionnaire), a Microsoft agreement for any PlayReady service provider, Apple's
   developer agreement for FairPlay. Either contract directly or buy a multi-DRM vendor. **Put this
   in week one of the plan.**
4. **Use ClearKey for CI only.** It is the only fully-open DRM; it is a test mechanism and no studio
   accepts it for premium content. Wire it into automated tests so the pipeline is verifiable without
   touching production keys.
5. **Playback:** `shaka-player` or `hls.js` (both Apache-2.0) via EME. Note that
   `Dash-Industry-Forum/dash.js` states that **no patent rights are granted** — fine to use, not fine
   to assume it covers you.
6. **Studio security requirements are contractual, not technical:** premium tiers specify
   **Widevine L1 and HDCP** levels in the content agreement. Confirm the required security level
   *before* choosing devices, because it determines them.

**Anti-pattern this replaces:** "we'll add DRM later with open source." There is no later and there is
no open source for it. The honest version — open everywhere except a named, priced, contracted key
service — is both cheaper and faster, and it is the version that survives a studio audit.

## Pattern 25 — The age-gated streaming front door (the unbuilt component four regulators now require)

**Added 2026-11-26 (pass 9).** The most concrete unbuilt thing in this KB: every open media platform
in `verticals/solutions.md` has **no age-assurance hook at all**, while the EU, Brazil and Australia
all now require one.

**Wire it together:**

1. **Age signal** — [`eu-digital-identity-wallet/av-lib-android-zkp-age-icao`](https://github.com/eu-digital-identity-wallet/av-lib-android-zkp-age-icao)
   (Apache-2.0) and [`av-lib-ios-longfellow-zkp`](https://github.com/eu-digital-identity-wallet/av-lib-ios-longfellow-zkp)
   (Apache-2.0) generate a zero-knowledge proof that the viewer is over a threshold, **without
   disclosing the birth date or the document**. Verify it with
   [`av-srv-trust-validator`](https://github.com/eu-digital-identity-wallet/av-srv-trust-validator)
   (Apache-2.0) against the member-state trust list.
2. **Copy the reference integration the regulator already wrote** —
   [`av-verifier-frontend-cinema`](https://github.com/eu-digital-identity-wallet/av-verifier-frontend-cinema)
   is a **cinema age-gate frontend**, 1★, Apache-2.0. It is the closest thing to a media reference
   implementation in existence, and it is one star because nobody has looked.
3. **Bind the proof to the session, not the account** — issue a short-lived capability from
   [`av-web-verifier-ui`](https://github.com/eu-digital-identity-wallet/av-web-verifier-ui)'s flow
   and attach it to the playback token your player already mints (pass 8's delivery chain). This is
   what keeps Australia's "no government-ID-only route" and the OAIC's data-handling rules satisfiable:
   **you never store the identity attribute.**
4. **Gate the catalogue, not the stream** — enforce at the EPG/catalogue tier recorded in pass 7, so
   an under-threshold viewer never receives a manifest URL. Gating at the CDN is too late and leaks
   the asset ID.
5. **Keep the evidence** — write each gate decision to the audit trail in Pattern 26.

**Why Globant wins this:** the EUPL-1.2 licence on the *apps* is what stops product teams reusing
them, and the Apache-2.0 licence on the *libraries* is what makes this build legal — telling those
two apart is a 20-minute conversation that most bidders will get wrong. **Avoid forking the EUPL-1.2
app**; consume the Apache-2.0 libraries and build your own UI.

⚠️ **Verify before quoting a deadline.** `ageverification.dev` does not resolve from this session, so
the reported **31 December 2026** rollout date is unconfirmed here (`intel/market.md`, EMEA).

---

## Pattern 26 — "We removed it" → "we told the regulator we removed it" (the half nobody built)

**Added 2026-11-26 (pass 9).** Coop, Osprey, Altitude and Ozone all stop at *enforcement action
taken*. **No open T&S platform files a statutory report.** That gap is where the legal consequence
lives, and it is a per-action structured-record problem — the exact shape of work Globant sells.

**Wire it together:**

1. **Detect** — [`meta/ThreatExchange`](https://github.com/meta/ThreatExchange) (BSD) for PDQ image,
   TMK+PDQF / vPDQ video hashing and HMA matching; add
   [`ibm-granite/granite-guardian`](https://github.com/ibm-granite/granite-guardian) (Apache-2.0) or
   [`openai/gpt-oss-safeguard`](https://github.com/openai/gpt-oss-safeguard) (Apache-2.0) for policy
   classification. **gpt-oss-safeguard takes the client's own written policy as the input**, which
   means the client's legal team authors the classifier rather than reviewing yours.
2. **Decide** — [`roostorg/osprey`](https://github.com/roostorg/osprey) (Apache-2.0) evaluates the
   rules. Osprey is Discord's production engine, so the throughput question is already answered.
3. **Review** — [`roostorg/coop`](https://github.com/roostorg/coop) (Apache-2.0) for the queue,
   routing and human decision, self-hosted so content never leaves the client's estate. Start from
   [`coop-integration-example`](https://github.com/roostorg/coop-integration-example).
4. **Redact before anything leaves the boundary** —
   [`data-privacy-stack/presidio`](https://github.com/data-privacy-stack/presidio) (MIT, 12,065★) on
   every transcript, subtitle and UGC text field. **Note the path**: it moved from
   `microsoft/presidio`.
5. **File it — this is the new part.** Emit, per enforcement action, a typed record and route it by
   jurisdiction: EU → a DSA **statement of reasons** via
   [`afkzonagroup/rationale`](https://github.com/afkzonagroup/rationale) (Apache-2.0, 0★), validated
   against the Commission's own schema in
   [`digital-services-act/transparency-database`](https://github.com/digital-services-act/transparency-database)
   (**GPL-2.0 — read it, don't link it into a proprietary build**); US → the NCMEC CyberTipline,
   where [`ello/ncmec_reporting`](https://github.com/ello/ncmec_reporting) (7★, **no licence file**,
   dead since 2022-03-29) is a *reference for the wire format only* — **do not depend on it**;
   Brazil → the ANPD reporting obligation under ECA Digital, for which **no open client exists**.
6. **Prove the trail** — reuse the C2PA/provenance spine from Patterns 8 and 15 so each decision
   carries a signed, machine-readable claim about what was seen and when.

**The deliverable to name in a proposal:** a jurisdiction-routed enforcement-reporting service. It is
boring, it is mandatory, it has **no incumbent open implementation in three of the four regions**,
and the client cannot buy it from the T&S vendors because they stop where Coop stops.

---

## Pattern 27 — Policy-as-code age and content gating for a multi-region operator

**Added 2026-11-26 (pass 9).** APAC's rules diverge by *mechanism*, not threshold (Australia bans
ID-only, Malaysia mandates government ID, Singapore sets "reasonable accuracy", Indonesia tiers by
age with parental consent under 17), and `intel/trends.md` trend 10 shows all four regions demanding
*different artifacts* from the same pipeline. A per-market fork is therefore guaranteed to rot.

**Wire it together:**

1. **One policy object per jurisdiction** — [`policykit/policykit`](https://github.com/policykit/policykit)
   (MIT, 159★) is the only open artifact that treats a moderation policy as a first-class object
   rather than as configuration. Use it to hold the *rules*; it is academic in origin, so expect to
   own the operational hardening.
2. **One evaluation engine** — [`roostorg/osprey`](https://github.com/roostorg/osprey) (Apache-2.0)
   with the jurisdiction as a rule dimension, not as a deployment.
3. **Pluggable age mechanisms behind one interface** — the EU ZKP libraries (Apache-2.0) for the
   no-ID route, a document-check vendor for ID-mandatory markets, and an app-store attestation path
   for Singapore and Australia's store code. **The interface is the asset**; the mechanisms are
   swappable and some are necessarily commercial.
4. **Stackable labels where the architecture allows it** —
   [`bluesky-social/ozone`](https://github.com/bluesky-social/ozone) (dual MIT/Apache-2.0) is the
   reference for third-party labels users subscribe to. For an operator facing divergent national
   rules, this is the only model that does not force one global truth — a market-specific labeler per
   jurisdiction, one subscription policy per market.
5. **Evidence per market** — Pattern 26's reporting router, with the jurisdiction's artifact type
   selected from the same policy object.

**The pitch:** "you will be asked for a different artifact in every market you operate in, and the
only thing you can standardise is the engine." This is the same conclusion pass 8 reached about
synthetic-content rules in APAC, now confirmed from minor protection — **two independent routes to
'the asset is a per-jurisdiction policy engine' makes it a pattern, not an anecdote.**

---

## Pattern 28 — DCP ingest triage: an agent over 400 validation reports a week

**The problem.** A circuit, distributor or post house receives hundreds of DCPs a week. Each either
plays or does not, and finding out costs a validation run plus a human reading its output. The
failures are a mix of supplier-systematic (one vendor's encoder always mislabels reels),
one-off corruption, and naming-convention drift. Nobody has time to see the pattern.

**Why this is the right first build in the plane.** Validation is **the only step in the theatrical
chain that can be built permissively** (trend 56), so the client can own and embed the result.

**The stack.**

| Role | Component | Licence | Why this one |
|---|---|---|---|
| Validator | [`ClairMeta/ClairMeta`](https://github.com/ClairMeta/ClairMeta) | **BSD-3-Clause** | The only permissive DCP validator. Checks asset integrity (MIME, size, hash), XSD schema validation of every XML, and digital signature/certificate validation. Python, so it embeds directly |
| Low-level access | [`cinecert/asdcplib`](https://github.com/cinecert/asdcplib) | **BSD-3-Clause** | `ClairMeta`'s own dependency; the industry's real AS-DCP/MXF implementation, active 2026-11-19. Reach for it when you need per-essence detail ClairMeta does not surface |
| Codec probe | [`uclouvain/openjpeg`](https://github.com/uclouvain/openjpeg) | **BSD-2-Clause** | The DCI-mandated JPEG 2000 reference implementation, for frame-level inspection |
| Second opinion | [`wolfgangw/backports`](https://github.com/wolfgangw/backports) (`dcp_inspect`) | **GPL-3.0** | Deep inspection; the tool QC guides pair with DCP-o-matic. **GPL-3.0 — run it as a subprocess behind a service boundary, do not link it** |
| Orchestration | Your agent framework | — | Reads structured validation output, not pixels |

**Wiring.**

1. Watch the ingest drop. For each package, run `ClairMeta` → structured JSON per check.
2. For anything that fails, run `dcp_inspect` **as a separate process** for a deeper report. The
   process boundary is the copyleft boundary: keep it, and GPL-3.0 does not reach your service.
3. The agent's job is **across** reports, never inside one: cluster this week's failures by supplier,
   encoder version, reel count and failure class; distinguish "this vendor's last 11 packages all
   mislabel audio channels" from "this one package is corrupt".
4. Emit two artifacts: an operations queue (what to reject, reissue, or accept with a note) and a
   supplier scorecard. The scorecard is what renews the engagement.

**Do not** put a model inside the validation step. The checks are deterministic and schema-defined;
an LLM there adds nondeterminism to the one part of the chain that currently has none. The judgement
is in the triage.

**The measured opportunity.** `DCP automation agent` returns **zero results**. There is no open
competitor, and the artifact is typed.

---

## Pattern 29 — The accessibility conformance gate: verify the mandated track before the key ships

**The problem, and it is a legal one in three regions.** A mandated caption or audio-description
track is either present in the DCP, correctly labelled, and actually renders — or the screening
breaches a duty. Today nobody checks systematically, because the duties and the content sit with
different parties:

- **North America**: the DOJ ADA Title III rule (2016-12-02) obliges theatres to maintain
  captioning and audio-description equipment at the patron's seat — but **explicitly does not**
  oblige them to add those features to films not distributed with them.
- **Brazil**: Ancine **IN 165/2022** binds **distributors and exhibitors** for commercial screenings.
- **Mexico**: the new Federal Film and Audiovisual Act reportedly covers accessibility for visual and
  hearing impairments (status flagged, see `intel/market.md`).

**The equipment duty and the content duty are held by different parties and nothing joins them.**
That join is the product.

**The stack.**

| Role | Component | Licence | Notes |
|---|---|---|---|
| DCP structural + subtitle asset validation | [`ClairMeta/ClairMeta`](https://github.com/ClairMeta/ClairMeta) | BSD-3-Clause | Validates the subtitle/caption assets' schema and signatures as first-class DCP assets |
| Subtitle read/write | [`cth103/libsub`](https://github.com/cth103/libsub) | **GPL-2.0-or-later — in the source headers only, no licence file** | Use behind a service boundary. See trend 58: the absence of a `LICENSE` does **not** make this permissive |
| Essence access | [`cinecert/asdcplib`](https://github.com/cinecert/asdcplib) | BSD-3-Clause | Reads the timed-text and audio essence the accessibility tracks live in |
| Caption/IMSC rendering check | the accessibility stack already in `repos/foundations.md` (pass 3) | permissive | **Reuse, do not rebuild** — pass 3 already verified the interchange and rendering layer |
| Evidence store | the OAIS-grade ingest from Pattern 14 | Apache-2.0 | The trail has to outlive the release window |
| Reasoning | Your agent framework | — | Decides *sufficiency*, which is the one judgement call here |

**Wiring.**

1. On ingest, inventory every track in the package: picture, audio, subtitle, closed caption, audio
   description, and their language and `Intrinsic`/`Type` labelling.
2. Compare against the obligation for the **booking's jurisdiction** — not the distributor's home
   market. This is a policy engine per jurisdiction, exactly as pass 8 concluded for APAC.
3. Render-check, do not presence-check. A declared caption track that fails to render is the failure
   mode that produces complaints, and presence in the CPL is not rendering.
4. **Gate the key on the result.** This is the pattern's whole leverage: the KDM is the one
   chokepoint in theatrical distribution that everyone already respects. An accessibility failure
   that blocks key issuance gets fixed; a warning in a report does not.
5. Emit a per-screening, per-title evidence record: what was present, what rendered, what was
   missing, under which instrument, with timestamps.

**The measured opportunity.** Open cinema-accessibility tooling worldwide: **one repository, zero
stars**, against a US mandate nine years old and two active LATAM instruments (trend 61).

---

## Pattern 30 — KDM lifecycle reasoning: the 3-star layer under every screening on earth

**The problem.** A KDM is valid for a named screen, for a dated window. A circuit runs hundreds of
screens against dozens of distributors, each issuing keys on its own schedule and its own portal.
The failure is specific, public and expensive: **a sold-out Thursday 19:40 show with no valid key.**

**The measured void.** The entire open estate for KDM lifecycle management is **three repositories
totalling three stars** (`kdmcourier` AGPL-3.0 1★, `dcpkdm` unlicensed 1★, `KdmManager` GPL-3.0 0★).
This ties the crudest number in this knowledge base, and unlike `medical necessity` the object is
**a file with a published SMPTE schema** (trend 57).

**The stack.**

| Role | Component | Licence | Notes |
|---|---|---|---|
| KDM/certificate handling | [`cinecert/asdcplib`](https://github.com/cinecert/asdcplib) | **BSD-3-Clause** | **The critical row: the capability to read and write KDMs exists, permissively, and is actively maintained (2026-11-19).** Build here, not on the AGPL tooling |
| Package identity | [`ClairMeta/ClairMeta`](https://github.com/ClairMeta/ClairMeta) | BSD-3-Clause | Resolves which CPL a key must match |
| Prior art to read, not to link | [`PostPerfection/kdmcourier`](https://github.com/PostPerfection/kdmcourier) | **AGPL-3.0** | Two weeks old, 1★. Read it for the FLM/booking model it assumes; **do not link it** — AGPL reaches a hosted service |
| Exhibition-side state | [`1105821037/CineTMS`](https://github.com/1105821037/CineTMS) | Apache-2.0 | The only open TMS-shaped project in existence (5★, APAC). The permissive place to get screen and session state |
| Reasoning | Your agent framework | — | Joins bookings × screens × key windows |

**Wiring.**

1. Build a key inventory: for every KDM, the target screen certificate, the CPL it unlocks, and its
   validity window — parsed with `asdcplib`, stored as typed records.
2. Join against the booking schedule (from `CineTMS` or the client's TMS).
3. The agent reasons over the join: which sessions have no valid key, which keys expire mid-run,
   which screens were re-certified after a projector swap and so need reissue, which distributor is
   systematically late.
4. Escalate with a specific ask per distributor — "reissue CPL *X* for screens 4, 7, 11, window
   starting Thursday" — rather than a dashboard nobody reads at 18:00.

**Licence discipline for this pattern.** `asdcplib` (BSD-3) is permissive and does the cryptographic
work; every *product* in this layer is AGPL/GPL or unlicensed. **Build on the library, read the
products.** That is the whole reason this pattern is buildable at all.

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
13. **Don't call OpenUSD Apache-2.0.** Added 2026-11-25. It is the **Tomorrow Open Source Technology
   License 1.0** — Apache-2.0 with a different Section 6 (Trademarks), and the GitHub API reports
   `NOASSERTION`. Functionally equivalent for most uses, but a client's legal review will find the
   difference and a deck that got it wrong loses the room. Same for `OpenRV`: Apache-2.0 **except**
   the components listed in its `Notice.txt`.
14. **Don't deploy `ayon-backend` believing AYON is open source.** Added 2026-11-25. The server and
   web UI are **FSL-1.1-ALv2** — source-available with delayed Apache conversion, **not** OSI
   open source — while every AYON client is Apache-2.0. The licence boundary runs *inside the
   product*. Build on `ayon-core` / `ayon-python-api`, and make the server choice deliberately.
15. **Don't start a pipeline on OpenPype.** Added 2026-11-25. `ynput/OpenPype` (301★, MIT) is the
   most-starred project in its lineage and has been **archived since 2024-09-18**, superseded by
   AYON. Listicles still recommend it. A live URL is not a live project — the rule from pass 5,
   repeating in a new plane.
16. **Don't search this plane in generic English.** Added 2026-11-25. `virtual production` returns
   **1,291 results** that are mostly a Go asset embedder, a dumped W3C report and a mainframe
   emulator; `color grading open source` returns **42 results of which four of the top six are the
   Bee Movie script**. Query the *standard's* name — `opentrackio` (8 results, 4 real and
   permissive), `OpenColorIO`, `camdkit` — and read the results rather than the total.
17. **Don't pitch the 40% efficiency saving to a studio that bills by the hour.** Added 2026-11-25.
   FICCI-EY attributes up to 40% time savings to AI in roto, clean-up and pipeline work — which is
   precisely what APAC and LATAM service studios invoice for. Sell pipeline ownership priced per seat
   and per system (Patterns 17–19). The efficiency framing hands the client its own disintermediation
   case; see trend 36.
18. **Don't promise a safety classifier you cannot license.** Added 2026-11-26. The best open safety
   models are **research-only or non-commercial**: Roblox **RoGuard 1.0** is RAIL Research-Only,
   `Roblox/voice-safety-classifier` is CC-BY-SA-3.0, Meta's **Llama Guard** is the Llama 3.2
   Community licence with an MAU threshold, and `SCLBD/DeepfakeBench` is CC-BY-NC-4.0. Meanwhile the
   most-starred NSFW classifiers are **archived** (`yahoo/open_nsfw`, 6,018★, archived 2018) or
   **unlicensed** (`LAION-AI/CLIP-based-NSFW-Detector`, 473★, no licence file). **Ask for the
   weights' licence separately from the repo's licence, every time** — and quote only
   `granite-guardian`, `gpt-oss-safeguard`, `detoxify`, `openguardrails` or `Roblox/Sentinel`.
19. **Don't conclude "unlicensed" from a missing root licence file.** Added 2026-11-26. `Draupnir`
   (253★, pushed the day of the pass) reports **no licence** via the API and has no `LICENSE` under
   eleven probed names — because it uses **REUSE**: `REUSE.toml`, per-file SPDX identifiers, a
   `LICENSES/` directory and `"license": "Apache-2.0"` in `package.json`. It is *more* compliant than
   the API can read. Likewise `NVIDIA-NeMo/Guardrails` (7,581★) reports `NOASSERTION` while its
   `LICENSE.md` contains the line `SPDX-License-Identifier: Apache-2.0`. **Check `REUSE.toml`, a
   `LICENSES/` directory and the package manifest before writing off a maintained project** — and
   check the repo hasn't simply **moved**: a `repo:<slug>` search returning 422 while `git ls-remote`
   succeeds means a rename, which caught `facebook/ThreatExchange` → `meta/ThreatExchange`,
   `NVIDIA/NeMo-Guardrails` → `NVIDIA-NeMo/Guardrails` and `microsoft/presidio` →
   `data-privacy-stack/presidio` in a single pass.

- **Do not promise a theatrical pipeline "all open source" without naming the licence boundary.**
  Added 2026-11-26 (pass 10). The DCP chain is **copyleft end to end**: `dcpomatic`, `libdcp`,
  `libsub`, `opendcp`, `dcp_inspect`, `dcpdoctor` and `kdmcourier` are GPL-2.0, GPL-3.0 or AGPL-3.0,
  and the fastest JPEG 2000 codec (`grok`, 300★) is **AGPL-3.0**. Only the substrate (`openjpeg`
  BSD-2, `asdcplib` BSD-3) and one validator (`ClairMeta` BSD-3) are permissive. A proprietary
  client deliverable can be built on validation; it cannot be built on authoring. Decide in week
  one. This is the same mistake as the pass-5 rule about rights and royalty stacks, in a new plane.
- **Do not search for cinema with the word "cinema".** Added 2026-11-26 (pass 10). `cinema AI agent`
  returns 205 results and 526 top-six stars, every one about *cinematic look* in video generation —
  permissively licensed, actively maintained and completely irrelevant. Search the **artifact name**:
  `DCP`, `KDM`, `asdcplib`, `digital cinema package`. And never read a result total as coverage:
  `cinema ticketing platform` returns 350 student CRUD apps with a 12-star ceiling.
- **Do not conclude "unlicensed" from a missing `LICENSE` file, and do not conclude "licensed"
  either.** Added 2026-11-26 (pass 10). `wolfgangw/backports` is GPL-3.0 via a file named
  **`gpl.txt`** that a fourteen-name probe missed; `cth103/libsub` has no licence file at all and
  **73 GPL-2.0+ source headers**; `rslstandard/rsl` (pass 5) has neither and is therefore
  all-rights-reserved. One shallow clone distinguishes all three. **The absence of a licence file is
  the start of the check, not its result.**
- **Do not treat a permissive licence as a safety signal on its own.** Added 2026-11-26 (pass 10).
  The MXF container layer under every DCP and broadcast master is BSD-licensed and **retired**:
  `bbc/bmx` archived 2025-09-29, `sandflow/regxmllib` archived 2026-11-22, `bbc/libMXF` relocated
  into an `-archive` org, the EBU's library last touched in 2013. Permissive-and-abandoned is a
  worse dependency risk than copyleft-and-alive, and no licence scan, SPDX field or SBOM reports it.

## Pattern 31 — The description backfill: make an unsearchable archive retrievable before anyone trains a model

**The problem.** A broadcaster or publisher has decades of assets with filenames, durations and
little else. Every "AI over our archive" proposal dies the same way: retrieval is impossible over
assets that carry no description, so the model has nothing to rank. The MAM vendors have priced this
demand in — Coherent names "metadata tagging, content indexing" as the growth driver, and archive &
storage management is the largest MAM segment at **25.8% share in 2026** — while the open supply for
the *judgment* step is one repository deep.

**The recipe — four stages, all verified in pass 11, no component licensed shut:**

1. **Technical + structural pass.** `MediaArea/MediaInfo` (BSD-2-Clause, 2079★) over the whole
   corpus. It is the only tool found that **emits EBUCore and PBCore 1.2/2.1 directly**, so stage 1
   output is already in a broadcast schema rather than a bespoke JSON blob. For AV, add
   `ina-foss/inaSpeechSegmenter` (MIT, 919★) to segment speech / music / noise — that gives you
   per-segment boundaries to describe, instead of one row per file.
2. **Transcribe and extract entities.** Whisper (already in this KB's foundations, MIT) → then
   `urchade/GLiNER` (Apache-2.0, 4296★) for **zero-shot** NER, because an archive's entity types are
   the client's own and GLiNER needs no retraining to accept them. Link what you extract with
   `UB-Mannheim/spacyopentapioca` (MIT) over `opentapioca/opentapioca` (Apache-2.0) to put **Wikidata
   QIDs** on people, places and organisations — stable identifiers, not strings.
3. **Assign subjects against a controlled vocabulary — the step everyone skips.** Publish the
   client's thesaurus with `NatLibFi/Skosmos` (MIT, 269★) on `apache/jena` Fuseki (Apache-2.0), or
   with `tematres/TemaTres-Vocabulary-Server` (GPL-2.0-or-later, 142★) for a Spanish-language
   engagement. Then train `NatLibFi/Annif` (Apache-2.0, 280★) on that SKOS vocabulary plus whatever
   catalogue records already exist, and have it assign subject headings to the backfill. Where no
   thesaurus exists, seed from **IPTC Media Topics (~1,100 terms, CC BY 4.0 — attribution only, and
   the grant explicitly permits commercial use)**.
4. **Emit in an interchange schema and expose it.** Serialise to `iptc/newsinjson` (ninjs, MIT) or
   NewsML-G2 via `iptc/python-newsmlg2` (MIT) for news; EBUCore/PBCore from stage 1 for AV; add
   `schemaorg/schemaorg` `NewsArticle`/`VideoObject` for the public web. Expose for harvest with
   Omeka S (GPL-3.0) + `Daniel-KM/Omeka-S-module-OaiPmhRepository` (GPL-3.0), which appends **IIIF
   `info.json` and manifest links to the Dublin Core records** in one module, and serve images through
   `cantaloupe-project/cantaloupe` (NCSA) with `ProjectMirador/mirador` (Apache-2.0) on top.

**Why it closes.** Stage 3 is the differentiator and the reason this is a build rather than a
purchase: competitors will deliver stages 1, 2 and 4 as free-text tags. Subject assignment **against
the client's own vocabulary** is auditable — every heading traces to a thesaurus concept — which is
what turns "we tagged the archive" into something a rights, compliance or editorial team will accept.

**The two things to say out loud in the proposal.**
- **Annif's training corpora are not licensed.** `NatLibFi/Annif-corpora` has no licence file. You
  train on *the client's own* catalogue records; budget the annotation, and do not plan to bootstrap
  from someone else's labelled data.
- **Licence boundary.** Stages 1-2 and the schema layer are permissive (BSD/MIT/Apache/CC BY).
  Stage 4's exposure tier and TemaTres are **copyleft**. If the client refuses copyleft for a hosted
  service, swap Omeka S for a permissive repository — `IQSS/dataverse` (Apache-2.0) or `DSpace/DSpace`
  (BSD-3) — and keep IIIF, which is permissive in three of its four components.

---

## Pattern 32 — The EBUCore version gate: a two-hour check that decides whether a metadata programme is legal

**The problem.** A European broadcaster asks Globant to model or migrate its media metadata. The
obvious move is to adopt the EBU's standard. **EBUCore (Tech 3293) is CC BY-NC-SA 3.0 —
NonCommercial** (verified: `ebu/ebucore/master/LICENSE.md`, 386 B). Its successor **EBUCorePlus is
MIT** (`ebu/ebucoreplus`, 30★). The widely installed generation is the one Globant cannot build
commercial work on, and nothing in a vendor deck or an SBOM scan of a source tree will tell you which
one the client is on.

**The recipe.**
1. **Establish the generation before scoping.** Ask for the client's metadata model and look for
   EBUCorePlus v2.0/v2.1 markers versus Tech 3293 EBUCore. Treat the answer as a gating question with
   a contractual consequence, not a technical detail.
2. **If EBUCorePlus (MIT):** proceed. Model against `ebu/ebucoreplus`, generate from the ontology,
   and use `MediaArea/MediaInfo` (BSD-2) for EBUCore-shaped technical extraction — the *tool* is
   BSD-2 regardless of the ontology's terms.
3. **If legacy EBUCore (CC BY-NC-SA 3.0):** do not redistribute or build a commercial deliverable on
   the ontology. Two lawful routes: (a) **migrate the client to EBUCorePlus** as the first work
   package — which is a sellable project with an EBU-backed rationale, since EBUCorePlus is the EBU's
   current flagship; or (b) model in **IPTC (CC BY 4.0, commercial use expressly granted)** or
   **schema.org (Apache-2.0)** and crosswalk at the boundary. The **W3C Ontology for Media
   Resources** defines a core property set with mappings between EBUCore, Dublin Core and others, and
   is the reference for that crosswalk.
4. **Never cite `mikrosimage/jebu-core`** as an EBUCore implementation: GPL-2.0 and **dead since
   2018-06-13**. There is no maintained open EBUCorePlus tooling beyond the ontology itself — that
   absence is itself a build opportunity, at 30★ and 8 forks.
5. **Record the determination in writing** with the licence file and byte count as evidence, because
   the GitHub API reports `NOASSERTION` for `ebu/ebucore` and an automated scan will therefore report
   *nothing* where the real answer is "NonCommercial".

**Why it matters now.** **TEMS** (Trusted European Media Data Space), with the EBU a founding partner
and Digital Europe Programme funding, **runs 2023-2026 and concludes this year**, and the **EUIPO's
2026-05-28 mapping study** found that poor interoperability between copyright-related metadata
standards "triggers major inefficiencies." EMEA buyers have both a deadline and an institutional
citation. The engagement they are about to fund is exactly the one this licence question gates.

---

## Pattern 33 — Evidencing an AI policy for a Spanish-language newsroom (the LATAM build with its own reference implementation)

**The problem.** Pass 8 established that LATAM's hottest buyer is the newsroom, because an
organisation that has published an AI policy (FLIP in Colombia, ADEPA in Argentina, SiPreBA, IAPA,
Aspen Digital's "Mind the Gap") has committed to **evidencing** it. Pass 11 supplies what evidencing
requires — and, unusually, the components are regional.

**The recipe.**
1. **Vocabulary layer, in Spanish, LATAM-built.** `tematres/TemaTres-Vocabulary-Server` — 142★,
   pushed 2026-11-25, **GPL-2.0-or-later**, © Diego Ferreyra, Argentina. The second most-starred
   controlled-vocabulary server on GitHub. Seed it from **IPTC Media Topics (CC BY 4.0)**, which is
   published in multiple languages, rather than inventing a taxonomy.
2. **Subject assignment.** `NatLibFi/Annif` (Apache-2.0) trained on the newsroom's own archive plus
   the TemaTres vocabulary. Annif was built precisely because Finnish and Swedish were poorly served
   by existing tools — the same argument applies to Spanish and Portuguese, and it is the reason to
   prefer it over an English-first hosted tagger.
3. **Description and syndication schema.** `iptc/newsinjson` (ninjs, MIT) as the record format;
   `superdesk/superdesk` (AGPL-3.0, 760★) if the client needs the full newsroom system, or
   `wagtail/wagtail` (BSD-3) plus custom workflow if AGPL is refused. `superdesk/newsroom` (GPL-3.0)
   is the open syndication tier.
4. **Provenance join.** Pass 9's C2PA layer attaches to the same records, so "what we published",
   "how it was made" and "what subject we filed it under" resolve to one auditable object.

**The deliverable is a report, not a pipeline.** The buyer's obligation is to show a regulator, a
funder or its own readers that the published policy is being followed. Output: per-article subject
headings traceable to a named vocabulary concept, AI-involvement provenance, and a dated log.

**Three honest caveats to put in the proposal.**
- **TemaTres' licence is not in a `LICENSE` file** — it is declared in `readme.md` and in every
  source header, so the GitHub API and SBOM scanners both report it as unlicensed. Expect to prove
  the GPL-2.0-or-later grant to the client's legal team; the evidence is cited above.
- **GPL-2.0-or-later is copyleft.** For a hosted multi-tenant service, confirm the client accepts it.
- **NOBRADE is unimplemented.** arXiv 2605.16338 ("Vidya") describes an LLM+FOSS archival pipeline
  reported compliant with **NOBRADE** and ISAD(G) for low-cost deployment in memory institutions, but
  **no code exists on GitHub under that name**. For a Brazilian archival engagement that is a
  genuinely differentiated build — and it is a build, not an adoption.

**Regulatory timing.** Mexico's **2026-05-14** copyright and labour amendments are reported as its
first sector-specific AI regulation, and a new audiovisual law extended oversight to **VOD platforms**
for the first time; Peru's **Law 31814** regulation took effect **January 2026**. Sector-specific
rules plus VOD-in-scope create description and labelling duties on a clock.

## Sound, music & immersive-audio recipes — added 2026-11-26 (pass 12)

Every repo named below was verified this pass by `git ls-remote`, and every licence was read from the
repository's own licence file. **The architectural rule that governs all five recipes:** in this plane
the licence hardens wherever code runs *inside* a proprietary host, so these patterns keep the AI in
a **separate process** and let the DAW or editor call it. That one decision is what keeps the output
shippable under your own terms.

### Pattern 12.1 — Rights-clean dubbing pipeline (the LATAM-grade one)

**Problem.** Dub a catalogue into Spanish for a Mexican or regional broadcaster, under a statute
(DOF 2026-05-14) that requires express consent and specific remuneration for any cloned performer
voice, and under EU AI Act disclosure if the same asset ships into EMEA.

**Wiring.**
1. **Separate** dialogue from music and effects — `deezer/spleeter` (MIT) or
   `asteroid-team/asteroid` (MIT). Keeps the original M&E bed intact, which is what makes a dub
   mixable at all.
2. **Clean** the dialogue stem — `Rikorose/DeepFilterNet` (MIT **or** Apache-2.0). For archive-grade
   or telephone-grade source, add `haoheliu/versatile_audio_super_resolution` (MIT).
3. **Attribute** speakers — `pyannote/pyannote-audio` (MIT, already in this KB from p7).
4. **Transcribe and time** — Whisper (MIT, already in this KB); align with the caption-plane tooling
   from pass 3 so the dub inherits conformant timing.
5. **Synthesise** the target-language voice. **This is the licence decision point, not a model
   choice.** `fishaudio/fish-speech` is the strongest open option and its licence permits delivering
   *finished audio* as an agency or studio, while **forbidding** on-premises deployment to a client
   over USD 500k revenue and **any** hosted TTS service without a separate agreement. If the client
   wants the model in their infrastructure, use the permissive path instead: Chatterbox or Kokoro
   (both already in this KB) served through `k2-fsa/sherpa-onnx` (Apache-2.0).
6. **Record consent as an artefact, not a spreadsheet.** Bind performer consent — who, what use, what
   remuneration — to the asset using the C2PA provenance tooling from pass 9, so the permission
   travels with the file through every downstream transcode.
7. **Disclose.** Emit the synthetic-content declaration the EU AI Act expects, in the same manifest.
8. **Mix and verify loudness** with the pass-4 ebur128 tooling before delivery.

**Why it is defensible:** steps 1-4 and 8 are fully permissive; step 5 is the only licence-bearing
choice and the recipe gives both branches; steps 6-7 are what the client cannot buy anywhere.

### Pattern 12.2 — Object-based (immersive) audio delivery on the open stack

**Problem.** A sports or event client needs an ADM/BW64 immersive deliverable, and the budget will
not carry a per-seat proprietary authoring chain.

**Wiring.**
1. **Author** the object-based mix in `ebu/ear-production-suite` (GPL-3.0-or-later; VST plugins,
   Reaper-optimised). Note the licence is at `packaging/LICENSE.md`, not the repo root.
2. **Model and write** the metadata and container with `ebu/libadm` + `ebu/libbw64` (both
   Apache-2.0) — this is your own code's permissive path, independent of the GPL authoring tool.
3. **Render** to the target layout with `ebu/ebu_adm_renderer` (BSD-3-Clause-Clear) — the normative
   ITU-R BS.2127 implementation, i.e. the definition of correct.
4. **Binaural check** with `ebu/bear` (Apache-2.0) for headphone monitoring and OTT.
5. **Live object positions**, if the show is live, over `immersive-audio-live/ADM-OSC` (MIT).
6. **Browser preview** for review-and-approval with `GoogleChrome/omnitone` (Apache-2.0) or
   `polarch/JSAmbisonics` (BSD-3), loading HRTFs via `hoene/libmysofa` (BSD-3).

**The honest limit, state it to the client up front.** This chain ends at **ADM/BW64**. There is **no
open MPEG-H encoder**; for ATSC 3.0 carriage the encode step is Fraunhofer's and must be licensed.
Scope the engagement to *authoring, rendering and conformance* and name the encoder as a third-party
dependency in the proposal.

**Licence boundary:** keep your deliverable in the libraries (Apache/BSD, step 2-4). The GPL-3.0
authoring suite is a **tool you operate**, not a component you redistribute.

### Pattern 12.3 — Archive audio restoration and enrichment at catalogue scale

**Problem.** A broadcaster or national archive has decades of tape with poor intelligibility, no
speaker labels and no searchable description.

**Wiring.**
1. **Restore**: `xiph/rnnoise` (BSD-3) for cheap bulk denoise, `Rikorose/DeepFilterNet` where quality
   matters, `haoheliu/versatile_audio_super_resolution` (MIT) for bandwidth extension on
   narrow-band sources.
2. **Separate** music beds from speech with `deezer/spleeter` (MIT) so the music can be identified
   separately.
3. **Diarise and transcribe**: `pyannote-audio` (MIT) → Whisper (MIT), both already in this KB.
4. **Identify the music** with the fingerprinting layer from pass 5 (Chromaprint/AcoustID) and resolve
   it against MusicBrainz via `metabrainz/picard` (GPL-2.0, operated as a tool) or `beetbox/beets`
   (**MIT** — the permissive option, and the one to embed).
5. **Describe and catalogue** by handing the transcript to the description plane from pass 11:
   `NatLibFi/Annif` (Apache-2.0) for subject indexing against a controlled vocabulary.
6. **Preserve** into the OAIS repository layer from pass 4.

**This is the highest-value, lowest-licence-risk composition in the plane** — every embedded
component is MIT/BSD/Apache/ISC, and it spans four passes of this KB without a copyleft dependency.

### Pattern 12.4 — Loudness and delivery conformance as a service

**Problem.** Every deliverable must hit a loudness target (EBU R128 / ATSC A/85) and failures are
caught late, by a human, after the mix is locked.

**Wiring.** Measure with the pass-4 ebur128 tooling, decode/transcode with FFmpeg (already in this
KB), and wrap both in a service the DAW calls. **The gap this pass measured: there is no open agent
that decides what to do about a failing measurement.** Build the remediation rules explicitly — they
are client-specific and they are the actual deliverable — and keep the model, if you use one, advisory
with a human sign-off. Do not sell this as autonomous; nothing open supports that claim today.

### Pattern 12.5 — Music understanding for catalogue and sync, with the trap called out

**Problem.** Tag a music catalogue with tempo, key, structure and instrumentation for search and
placement.

**Wiring.** `librosa/librosa` (ISC) for features; `spotify/basic-pitch` (Apache-2.0) for
audio-to-MIDI; `Natooz/MidiTok` (MIT) to tokenise for a sequence model; `cuthbertLab/music21`
(BSD-3) for symbolic analysis; `rism-digital/verovio` (LGPL-3.0) to render scores.

**⛔ The trap, and it will catch a team that does not read this.** The obvious choice for beat and
downbeat tracking is `CPJKU/madmom` — and **its pretrained models are CC BY-NC-SA 4.0**, explicitly
including pickled Processors, while its source is BSD. **madmom without its models does nothing, so
it cannot ship in a commercial product as-is.** Use `aubio` (GPL-3.0, operated as a tool) or
`librosa` (ISC, embeddable) instead, or license madmom's models from JKU. `MTG/essentia` is excellent
and **AGPL-3.0** — which reaches a hosted service, so it is a tool you run, not a library you embed.

**Rule of thumb for this recipe:** in MIR, check the **model** licence and the **library** licence
separately, every time. They differ more often than not.

## Subscription, entitlement & reader-revenue recipes — added 2026-11-26 (pass 13)

Every component below was measured and resolved on 2026-11-26 (`git ls-remote` 33/33). The agent
layer in this plane is a measured zero, so each recipe is an **build**, not an integration — which
is the point: there is nothing to be undercut by.

### Pattern 13.1 — The dual-regime cancellation journey (the deadline build: UK, 2027-01-01)

**The problem.** The UK DMCCA subscription regime comes into force **2027-01-01** for contracts
entered on or after that date, and the US position is its exact inverse — no rule, continuing ROSCA
and §5 enforcement. One codebase has to satisfy a **calendar** in the UK and an **evidence log** in
the US. No open billing platform implements either.

**Stack.**
- [killbill/killbill](https://github.com/killbill/killbill) (Apache-2.0, 5,869★) — subscriptions,
  renewal schedule, invoicing, dunning. Permissive, so the compliance logic can be embedded rather
  than kept at arm's length (which is exactly what Lago's AGPL would force).
- [keycloak/keycloak](https://github.com/keycloak/keycloak) (Apache-2.0, 38,060★) — identity, and
  the session that proves *who* cancelled.
- An append-only evidence store — any immutable log; the KB's provenance plane (`repos/foundations.md`)
  already carries the signing primitives if the client wants the log notarised.

**Wiring.**
1. **Model the obligations as scheduled entities in Kill Bill, not as UI copy.** Three timers per
   subscription: the ~6-month rolling reminder, the pre-trial/pre-discount-end reminder, and the
   pre-renewal reminder for terms of 12 months or more (with the extra earlier reminder on long
   renewals). Kill Bill already owns the renewal clock; these hang off it.
2. **Implement the renewal cooling-off right as a billing state, not a flag.** The UK regime grants a
   *second* 14-day cooling-off window at qualifying renewal payment dates. Model it as a reversible
   charge state with a 14-day horizon, because it is a refund obligation, not a consent record.
3. **Enforce exit parity in routing.** If sign-up was online, an online cancellation route must exist
   and be reachable; assert this in tests, not in policy documents.
4. **Emit an evidence record at every step** — what was disclosed, the exact text shown, when consent
   was captured, the click-count to cancellation, and the outcome. This record is what answers a US
   ROSCA enquiry, where there is no rule to comply with and only facts to be judged on.
5. **Gate by contract date.** The UK rules bind only contracts entered on or after 2027-01-01, so the
   subscription record needs a regime discriminator from day one. Retrofitting it later means
   reconstructing which regime applied to which cohort — the expensive failure mode.

**Why it is differentiated.** The duty is dated, the artefact is specified in the UK and absent in
the US, and no open project implements the calendar or the log. *Confirm against the final SI before
contracting: the in-force date has moved more than once during 2026.*

### Pattern 13.2 — The media entitlement graph (the schema that does not exist)

**The problem.** SpiceDB, OpenFGA and Cerbos are excellent and permissive, and **none of them ships a
schema for what a video service actually sells.** Every operator rebuilds it.

**Stack.** [authzed/spicedb](https://github.com/authzed/spicedb) (Apache-2.0, 7,243★) — or
[openfga/openfga](https://github.com/openfga/openfga) (Apache-2.0, 6,197★) if lighter operations
matter more than expressiveness — behind [keycloak/keycloak](https://github.com/keycloak/keycloak).

**Wiring.** Model as relationships, which is what they actually are:
- `subscriber → plan → tier` (ad-supported vs paid — the switch is a relationship change, not a flag)
- `title → window → territory` (licensing windows are time-bounded relations; make the bound explicit)
- `subscriber → device` with a cardinality check for concurrency and registration limits
- `subscriber → download → expiry` for offline rights
- `household → profile` for shared-account policy

Then expose one question the business can ask directly: **"why can this subscriber not play this
title, on this device, in this territory, right now?"** A relationship graph can answer that with a
decision path. No commercial subscriber platform exposes it, and support organisations spend real
money guessing at it.

**Why it is differentiated.** The engines are free, permissive and mature; **the media semantics are
the asset**, they are reusable across every operator engagement, and this pass confirmed by
measurement that they do not exist in the open.

### Pattern 13.3 — Dunning triage (the most automatable unbuilt task in the plane)

**The problem.** Involuntary churn — failed payments, expired cards, issuer declines — is a large
share of total churn and is pure operations. `dunning agent` returns **57 repositories and not one
above 200 stars**. It is the cleanest zero measured in this pass.

**Stack.** [killbill/killbill](https://github.com/killbill/killbill) (Apache-2.0) for the payment
and retry events; [juspay/hyperswitch](https://github.com/juspay/hyperswitch) (Apache-2.0, 45,917★)
if the client needs multi-PSP routing — a declined charge at one acquirer is not always declined at
another, and that is a real recovery lever. Both permissive, so the agent can sit inside the process.

**Wiring.**
1. Consume Kill Bill payment-failure events with the decline reason attached.
2. Classify by cause — expired card, insufficient funds, soft vs hard decline, issuer fraud block —
   because the correct action differs completely and a fixed retry ladder ignores all of it.
3. Choose per-case: retry timing, PSP re-route via Hyperswitch, card-update prompt, or stop.
4. **Record every decision.** Retry behaviour is itself regulated conduct in the UK regime
   (a consumer cannot be charged for a renewal before it renews), so the agent's log is a compliance
   artefact, not just telemetry.

**Why it is differentiated.** It is bounded, measurable in recovered revenue within one billing
cycle, and it has no open competitor at all.

### Pattern 13.4 — Churn scoring that replaces a dead component

**The problem.** [remp2020/pythia-tools](https://github.com/remp2020/pythia-tools) — the
churn-propensity layer of the only open reader-revenue platform — has **no licence file** and has not
been pushed since **2023-03-20**. The platform is MIT and alive; its churn component is unusable.

**Stack.** [remp2020/remp](https://github.com/remp2020/remp) (MIT, 138★) for Beam's pageview and
conversion events and its segment model; [CamDavidsonPilon/lifelines](https://github.com/CamDavidsonPilon/lifelines)
(MIT, 2,623★) for the model; [CamDavidsonPilon/lifetimes](https://github.com/CamDavidsonPilon/lifetimes)
(MIT, 1,476★, **archived**) only if BG/NBD lifetime-value is needed — vendor it and expect no fixes.

**Wiring.**
1. Beam already emits the events and already computes segments — do not rebuild that.
2. Fit **survival models, not classifiers.** Subscriber data is censored by construction (most
   subscribers have not churned *yet*), and a binary classifier silently mis-handles exactly that.
   This is why `lifelines` is the right dependency and a generic ML pipeline is not.
3. Write risk scores back as **Beam segments**, so REMP's Campaign module can target retention offers
   through the path that already exists.
4. Close the loop through Kill Bill: a save offer is a plan change, with its own disclosure duties
   under Pattern 13.1.

**Why it is differentiated.** It is a small, well-scoped build that restores a capability the
platform was designed for, it is MIT end to end, and it is directly reusable for any REMP publisher —
which, as `intel/market.md` records, is an **EMEA-origin** reference implementation.

### Pattern 13.5 — Paywall resilience (the LATAM build with public evidence)

**The problem.** The top ten `topic:paywall` repositories are ten circumvention tools totalling
**21,592 stars**, and the two largest non-English ones target the **Brazilian press**:
[marreta](https://github.com/manualdousuario/marreta) (GPL-3.0, 1,229★) and
[burlesco](https://github.com/burlesco/burlesco) (MIT, 948★), both pushed this month.

**Wiring.** This is a design review, not a product, and it is deliberately defensive rather than
adversarial:
1. **Read the circumvention source.** It is public, and it documents precisely which implementation
   shortcuts fail — server-rendering the full article then hiding it with CSS, trusting a referrer,
   trusting a cookie, exposing the body in a meta tag or JSON-LD block for SEO.
2. **Move the enforcement boundary server-side**, into the entitlement decision from Pattern 13.2.
   Content a reader is not entitled to should not reach the client at all.
3. **Keep the SEO obligation explicit.** Publishers must expose something to crawlers, and that
   requirement is what most bypass tools actually exploit. Decide deliberately how much, rather than
   leaking the article by accident.
4. **Instrument bypass attempts as a metric** and feed it to the same segment store as churn risk —
   a reader who repeatedly attempts circumvention is a conversion target, not just an abuse case.

**Why it is differentiated.** Globally it is a reasonable hygiene pitch; in LATAM it is urgent and
**the evidence is public, current and verifiable by the client in under a minute** — which is a
materially different conversation from a generic security recommendation.

## Localization & translation-management recipes — added 2026-11-26 (pass 14)

These three patterns compose only repos verified by `ls-remote` on 2026-11-26, and each one names the
licence boundary that decides how it can be delivered.

### Pattern 34 — The translation-memory recovery and audit (own the asset before you own the account)

**The opportunity, restated from §64 of `intel/trends.md`:** the client's translation memory is their
switching cost, their only wholly-owned multilingual corpus, and the one artefact with **no
maintained open tooling anywhere in the world**. Walking in able to read it is a differentiator that
costs a week.

**Who buys it:** any broadcaster, streamer, publisher or dubbing house with more than ~5 years of
outsourced localization. Strongest in **North America** (bought on SLAs, memory held per-vendor) and
**LATAM** (decades of Spanish/Portuguese dubbing memory, plus the Aspen Digital ask for shared
regional assets).

**The wiring:**

1. **Extract from the incumbent.** If the memory is locked in a proprietary tool, the exit route is
   [`GregoryVigoTorres/sdltm2tmx`](https://github.com/GregoryVigoTorres/sdltm2tmx) (GPL-3.0, 8★) —
   `.sdltm` → TMX 1.4. ⚠️ 8 stars and dormant since 2023: read it, expect to fix it, run it as a
   **separate process** so its GPL-3.0 does not reach your code.
2. **Normalise the source formats** with [`maxprograms-com/OpenXLIFF`](https://github.com/maxprograms-com/OpenXLIFF)
   (EPL-1.0, 86★, 2026-11-03) — XLIFF 1.2/2.0/2.1/2.2 create, merge and validate. This is the
   GitHub-available substitute for Okapi, which is not on GitHub (§66). EPL-1.0 is weak, file-level
   copyleft: invoking it and shipping it alongside proprietary code is fine.
3. **Parse and normalise the TMX.** [`yasslab/konjak`](https://github.com/yasslab/konjak) (MIT, 12★)
   is readable Ruby and MIT-clean; [`maxprograms-com/HybridTM`](https://github.com/maxprograms-com/HybridTM)
   (EPL-1.0, 7★, 2026-07-26) is a live TM engine. **Budget for writing this layer.** That is the
   honest recommendation: nothing here is production-grade, and §64 is why.
4. **Align and mine additional parallel text** with [`bitextor/bitextor`](https://github.com/bitextor/bitextor)
   (GPL-3.0, 302★) — ⚠️ dormant since 2024-11-11. Use it **read-only, in its own container**; do not
   link it.
5. **Score what you recovered** with [`Unbabel/COMET`](https://github.com/Unbabel/COMET) (Apache-2.0,
   792★) and [`mjpost/sacrebleu`](https://github.com/mjpost/sacrebleu) (Apache-2.0, 1,266★). This is
   the step that converts "we have a TMX file" into "here is which 18% of your memory is worth
   keeping" — the actual deliverable.
6. **Land it in a platform the client can own**: [`mozilla/pontoon`](https://github.com/mozilla/pontoon)
   (BSD-3-Clause, 1,680★) when ownership and relicensing matter, or
   [`WeblateOrg/weblate`](https://github.com/WeblateOrg/weblate) (GPL-3.0, 6,185★) when capability
   matters and the deployment is self-hosted and not redistributed.

**Deliverable:** a deduped, quality-scored, portable memory plus the audit that says what it is worth.
**Licence boundary:** steps 1 and 4 are GPL-3.0 and must stay separate processes; everything you
build on is MIT, BSD-3, Apache-2.0 or EPL-1.0.

### Pattern 35 — The sovereign localization stack (the EMEA build)

**Why it sells in EMEA specifically:** the DPP's *European Media Trends 2026* finds digital
sovereignty has become a business-resilience criterion, and VSN's analysis names the exact defect —
cloud DAM offerings call **third-party public AI engines that aggregate data on extra-European
servers**. Every segment sent to a hosted MT API is content leaving the jurisdiction. This stack
removes that call entirely.

| Layer | Component | Licence | Why |
|---|---|---|---|
| MT engine | [`argosopentech/argos-translate`](https://github.com/argosopentech/argos-translate) | **MIT** | Runs fully offline, and avoids the AGPL above it (§67) |
| Model training | [`argosopentech/argos-train`](https://github.com/argosopentech/argos-train) | MIT | Client-specific engine, client-owned weights |
| Platform | [`mozilla/pontoon`](https://github.com/mozilla/pontoon) | BSD-3-Clause | Mature *and* permissive — the client can relicense |
| Termbase | [`gaois/terminologue`](https://github.com/gaois/terminologue) | MIT | Per-market and per-regulator terminology |
| Linguist desktop | [`vslavik/poedit`](https://github.com/vslavik/poedit) | MIT | What the human reviewer actually uses |
| Quality | [`Unbabel/COMET`](https://github.com/Unbabel/COMET) + [`mjpost/sacrebleu`](https://github.com/mjpost/sacrebleu) | Apache-2.0 | Scoring that runs in-estate too |

**The critical substitution, and the money in it:** do **not** deploy
[`LibreTranslate`](https://github.com/LibreTranslate/LibreTranslate) (AGPL-3.0, 17,851★) as the
client-facing service. Its own `pyproject.toml` pins `argos-translate-lt==1.12.1`, so the engine
underneath is MIT. Building the API layer yourself over `argos-translate` delivers the same
capability **without AGPL-3.0 §13's duty to offer source to every network user.** ⚠️ Confirm the
pinned fork's licence on its PyPI artefact if you use the fork rather than upstream — no GitHub repo
resolves for it.

**Also applies to:** any LATAM or APAC client that cannot absorb a copyleft obligation — which, per
the LATAM notes, is most dubbing houses.

### Pattern 36 — The MQM gate: sell the gap that §65 measured

**The gap, measured:** quality a machine can compute has 2,058★ of live Apache-2.0 tooling. Quality a
**buyer and vendor must sign** — the MQM error typology that localization contracts are written
against — has **two repositories at one star each**
([`BYU-TRG-Team/mqm-scorecard`](https://github.com/BYU-TRG-Team/mqm-scorecard) and
[`BYU-TRG-Team/mqm-scorecard-api`](https://github.com/BYU-TRG-Team/mqm-scorecard-api), both
Apache-2.0, both last pushed 2025-06-11).

**So do what pass 8 concluded about rights standards: use the published typology as a *spec*, not the
repo as a *dependency*.**

1. **Treat MQM as the schema.** Implement the error typology (accuracy, fluency, terminology, style,
   locale conventions) as your own data model. The two Apache-2.0 repos above are a **reference for
   the data model**, not a library to depend on at 1★.
2. **Put the automatic metric in front of the human.** Score every segment with COMET
   (Apache-2.0, 792★). This is the triage, and it is the step that makes the economics work.
3. **Route by threshold.** Below the COMET threshold → full human MQM review. Above it → sampled
   spot-check. The threshold is calibrated per language pair against the memory recovered in
   Pattern 34, which is why the two patterns are sold together.
4. **Enforce terminology separately**, because it is the one MQM category a metric cannot see:
   a term either matches the client's termbase or it does not. Check against
   [`gaois/terminologue`](https://github.com/gaois/terminologue) (MIT, 76★) as a hard gate, not a score.
5. **Emit the scorecard as the contractual artefact** — per-vendor, per-language, per-period. This is
   what the client is actually unable to produce today.

**Why this is defensible work rather than a wrapper:** steps 1, 3 and 5 are judgment that no open
repo implements, and step 2 is a solved commodity. That is the whole shape of the law this KB keeps
confirming — **build where the agreement is, integrate where the computation is.**

⚠️ **Anti-pattern, and it would be an easy sale to make badly:** do not promise an
"all-open-source localization platform". Three of the eight layers in the pass-14 addendum table are
dormant, one-star, or absent from GitHub entirely. Promise the five healthy layers and *quote* the
other three as engineering.

## The out-of-home, signage & retail-media plane — patterns from pass 15 (2026-11-26)

Every repo named below was verified this pass: existence by `git ls-remote`, licence by reading the
file when GitHub reported `NOASSERTION`.

### P15.1 — The permissive signage stack that deliberately avoids the flagship

**Problem.** Anthias (3,745\*) is what every comparison recommends, and it is **GPLv2 + Commercial** —
so it cannot go into a proprietary client deliverable without buying the commercial licence. Xibo, the
other default, is AGPL-3.0.

**Recipe.**
1. **CMS:** [concerto/concerto](https://github.com/concerto/concerto) (Apache-2.0, 485\*, pushed
   2026-11-26) — Rails + Docker. Use `screentinker/screentinker` (MIT, 281\*) instead when
   multi-tenancy is needed on day one.
2. **Player runtime:** [ardera/flutter-pi](https://github.com/ardera/flutter-pi) (MIT, 2,012\*) on
   Pi-class hardware. It renders Flutter directly on KMS/DRM with no X11 or desktop session, which is
   what makes it cheap on idle CPU across a large fleet — and what makes it defensible under EMEA
   energy scoring.
3. **Web creative fallback:** [RushB-fr/freekiosk](https://github.com/RushB-fr/freekiosk) (MIT, 765\*)
   when the creative is already HTML and a Flutter client buys nothing.
4. **Wire-up:** Concerto serves playlists and schedules over HTTP; the player polls and renders. Keep
   the content contract in your own schema, not the CMS's, so the CMS stays replaceable.

**Exclusions, with reasons:** Xibo and `garlic-*` (AGPL-3.0) for any closed deliverable;
`jeremiaa/magic-frame` (**Polyform Noncommercial**) in all commercial work; `dividuum/info-beamer`
(BSD-2-Clause but **archived 2020**) and `eerotal/LibreSignage` (**archived 2021**) as dependencies.

### P15.2 — SMIL interop without taking AGPL into the client's product

**Problem.** If the client already owns commercial SMIL-compatible players, the only maintained open
SMIL family is `garlic-*`, and all of it is AGPL-3.0.

**Recipe.** Use [garlic-signage/garlic-player](https://github.com/garlic-signage/garlic-player)
(AGPL-3.0, 150\*) and [garlic-hub](https://github.com/garlic-signage/garlic-hub) (AGPL-3.0, 151\*)
**as a conformance test harness** against the client's own players, not as shipped components. The
harness runs in your CI and never reaches the client's product, so the AGPL obligation never attaches
to their deliverable. Add `garlic-proxy` (5\*) when testing fleet caching behaviour.

**If SMIL playback must actually ship,** deliver it as a separately-licensed network service with its
source offer honoured, and tell the client that before the contract — not after.

### P15.3 — Proof-of-play: build it, and know why you cannot shop for it

**Measured, not assumed.** `proof of play` = **751 results, zero relevant**.
`openooh/measurement-spec` is **dormant since 2021 and carries no licence file**;
`openooh/screen-id` likewise. The entire open proof-of-play corpus is one **0-star** repo.

**Recipe.**
1. Take [openooh/venue-taxonomy](https://github.com/openooh/venue-taxonomy) (**Apache-2.0** — the one
   piece of this layer you may legally build on) for venue typing.
2. Carry venue IDs in **OpenRTB 2.6**: `dooh.venuetype`, or `device.ext.dooh.venuetypelist` /
   `device.ext.dooh.venuetypeid` per taxonomy spec 1.2. When no `venuetax` is supplied, **OpenOOH is
   the assumed default** — so conforming to it is the cheapest interop you will ever buy.
3. Run the auction on [prebid/prebid-server](https://github.com/prebid/prebid-server) (Apache-2.0,
   595\* / 986f), which already carries DOOH support.
4. **Write the play-log schema yourself.** Read
   [trillboards/proof-of-play-verifier](https://github.com/trillboards/proof-of-play-verifier) (MIT,
   **0\***) and [WhimsicalCoder/dooh-bid-validator](https://github.com/WhimsicalCoder/dooh-bid-validator)
   (Apache-2.0, **0\***) as references; both are permissive and neither has a user base.
5. Build against the **IAB DOOH Measurement Guide (July 2025)**, the only agreed specification in this
   layer.

**The hard rule:** do **not** take a dependency on `openooh/screen-id` or `openooh/measurement-spec`.
Dormant since 2021 *and* unlicensed means default copyright. Read them as statements of intent,
re-implement, and keep that decision in the architecture record.

### P15.4 — Audience measurement that is lawful in all four regions by construction

**Measured.** No production-grade open footfall stack exists: `footfall analytics` = 184 results whose
top genuine entry has **10 stars**; `people counting` = 4,970 results led by a Wi-Fi-sniffing novelty
dead since 2024.

**Recipe.** Port the algorithms from
[NVIDIA-AI-IOT/deepstream-occupancy-analytics](https://github.com/NVIDIA-AI-IOT/deepstream-occupancy-analytics)
(MIT, 240\*) or [saimj7/People-Counting-in-Real-Time](https://github.com/saimj7/People-Counting-in-Real-Time)
(MIT, 613\*) — **both stale since 2023, so port, do not depend** — into an architecture fixed by four
rules:

1. Count **on-device**; video never leaves the player.
2. **Discard frames** after counting; persist no images.
3. Emit **aggregates only** (counts per interval), never per-person records.
4. Generate **no biometric template** and perform no identification or re-identification.

**Why these four and not a library choice:** this is the one design that simultaneously survives GDPR,
Brazil's LGPD, **Chile's Law 21,719 (fully enforceable December 2026)** and APAC's three divergent
regimes. It is a judgment artefact, which is precisely why no repo hands it to you — and precisely why
it is billable.

### P15.5 — Own the agent abstraction; do not adopt the vendor MCPs

**Measured.** `signage mcp` = **14 repos, top 2 stars**, and the identifiable ones are adapters for
closed SaaS CMSs (Sklera, Yodeck, Cast-Hub, RevelDigital, easysignage).

**Recipe.** Define **one MCP tool surface over the client's own CMS API** — Concerto's if you built
P15.1, Xibo's if the client already runs it — with roughly these tools: `list_screens`,
`get_screen_status`, `publish_playlist`, `schedule_campaign`, `fetch_play_log`. Read
[arnibj/InfoSlides.MCP](https://github.com/arnibj/InfoSlides.MCP) (MIT),
[Cast-Hub/mcp-server](https://github.com/Cast-Hub/mcp-server) (MIT),
[RevelDigital/reveldigital-webapp-skill](https://github.com/RevelDigital/reveldigital-webapp-skill)
(MIT), [timerise-ai/digital-signage](https://github.com/timerise-ai/digital-signage) (MIT, 1\*) and
[trillboards/dooh-agent-example](https://github.com/trillboards/dooh-agent-example) (MIT, 1\*) as
**shape references only**.

**Why it matters now.** Adopting a vendor MCP imports that vendor's lock-in into the agent layer, the
most expensive layer to migrate off later. This is the first plane in the KB where the agent layer is
being defined by incumbents rather than left empty — so the window to define a neutral abstraction is
open today and narrows as those adapters gain users.

### P15.6 — Retail media on in-store screens: the commercial wedge

**Measured.** `retail media network` = **37 results**, the only genuine entry a **3-star MIT
link-list**. There is no open-source retail-media platform at any licence, while in-store DOOH is
forecast to drive **~56% of DOOH growth 2025–2029**.

**Recipe.** `concerto/concerto` (Apache-2.0) for screen and playlist control + `prebid/prebid-server`
(Apache-2.0) for the auction + `openooh/venue-taxonomy` (Apache-2.0) for venue classification + the
**retailer's own loyalty and SKU data** as the targeting signal + P15.3's play log as the billing
substrate. Every component is permissive, so the whole stack can be delivered closed.

**Why this is a build and not an integration:** the differentiator is the retailer's first-party data,
which is exactly why no open-source product exists here and never will. Pitch it as a build; the
absence of a competing platform is the argument, not a caveat.

### P15.7 — The licence gate for this plane (run it before any estimate)

Four checks, each of which caught a real error this pass:

1. **Never trust `NOASSERTION`.** Open `LICENSE`, `LICENSE.md`, `LICENSE.txt`, **`license.txt`
   (lowercase)**, `LICENCE`, `COPYING`, `COPYING.md`, `NOTICE` on **both `main` and `master`**. Four
   probes gave four different answers, in both directions.
2. **A raw 404 is never by itself proof of a missing licence.** Fetch `README.md` as a control: if the
   README returns 200 and no licence filename does, the absence is real. That control is what made the
   OpenOOH no-licence finding safe to publish.
3. **Check `archived`.** `info-beamer` is permissive *and* archived; a licence check alone would have
   greenlit it.
4. **Read every star count.** `topic:dooh` has 35 repos and four of this plane's genuinely relevant
   transaction repos have **0 stars**. Permissive plus pushed-today plus zero stars means *read it*,
   never *depend on it*.

## The avails, windowing & distribution-rights plane — patterns from pass 16 (2026-11-26)

These three recipes are the first in this KB for a plane with **no vertical platform to extend**. They
are built from a licensed anchor (`MovieLabs/mddf`, MIT) plus horizontal engines, and each one names the
step where open source runs out.

### P16.1 — The avails ingest gate: stop bad availability data at the door

**Problem.** A distributor receives EMA Avails sheets from dozens of licensors in inconsistent shape.
Bad avails cause the two most expensive errors in distribution: a title published where it has no rights
(legal exposure) and a title withheld where it does (lost revenue, and nobody notices for months).

**Wiring.**
1. **Validate** the incoming Avails file with `MovieLabs/mddf` (MIT, 38*). It is Java; run `mddf-lib` as
   a service behind a thin HTTP wrapper. This is a *conformance* check against the published MDDF
   schemas — use it before any parsing of your own.
2. **Normalise** validated records into OMC entities using `MovieLabs/OMC` (Apache-2.0, 35*) as the
   ontology, and `survos/omc` (MIT) for ready-made 2.8 DTOs and schema validation if it proves alive.
   Join each avail to a title identity; note from pass 5 that EIDR has **no open client**, so title
   identity resolution stays a manual or vendor step — do not promise automation here.
3. **Decide** with `open-policy-agent/opa` (Apache-2.0, 12529*). One Rego package per question:
   `avails.permitted(title, territory, date, deal)`. Keep the window arithmetic in Rego, not in
   application code, so a rights analyst can read and a test suite can cover it.
4. **Report** exposure in `apache/superset` (Apache-2.0): titles live outside a window, windows expiring
   in 30 days, territories with no avail on a licensed title.

**Where it runs out.** Step 3's *engine* is free; the *policy model* does not exist in open source and is
the actual deliverable. Budget it as modelling work with a rights analyst, not as configuration.
Validate the estimate against `MovieLabs/mddf`'s own limit: it checks conformance, never commercial
sense — a perfectly valid Avails file can assert a window your deal does not grant.

**Licence note.** Anchor is MIT, engines Apache-2.0. This pattern is clean for a client deliverable.

### P16.2 — The AVMSD Article 13 catalogue-composition reporter (the EMEA asset)

**Problem.** Every VOD service in the EU must secure **≥30% European works in its catalogue and give
them prominence**. The Commission's 2020 guidelines count by **total number of titles**, and require the
30% to hold **in each national catalogue** of a multi-country provider — not as a group average. Most
providers answer this question with a spreadsheet and an annual scramble.

**Wiring.**
1. Take the catalogue from the ingest gate of P16.1 — avails already carry territory, so national
   catalogues are derivable rather than guessed.
2. Classify each title as a European work. **This is the judgment step**: the qualifying test is about
   production origin and is not a lookup. Use `MovieLabs/OMC` participant and organisation entities to
   hold the provenance you will need to defend, and keep the classification auditable per title.
3. Compute share per national catalogue by **title count**, matching the Commission's method. Publish in
   `apache/superset` with the per-country breakdown and a documented trail for each classification.
4. Add the prominence half, which most implementations skip: evidence of *placement*, not just presence.
5. Extend the same report to LATAM if Brazil's PL 8.889 passes — a ~10% Brazilian-title quota with half
   from independent producers is the identical computation with different constants.

**Why this is sellable.** The obligation is in force in 17 Member States (COM(2024)261, 2020–21 reference
period), it is measurable, and there is a **published measured gap**: European works are ~30% of
catalogues but only ~25% of *consumption* (EU works 28%, UK adding 9%). A provider meeting the catalogue
duty while missing on consumption has a prominence problem it can be shown on a chart. Nothing open
source computes this today.

**Honest limit.** The classification test drives the whole number and is contestable. Ship it as
*auditable*, never as *authoritative*, and keep the per-title trail — the defensibility is the product.

### P16.3 — The clearance-agent gate, with the human signature made structural

**Problem.** Music and rights clearance on a locked edit is slow, and six open agents now attack it.
All six are at zero stars and none should be trusted with a clearance decision.

**Wiring.**
1. Take the **EDL/XML** from the edit as input — the artefact `buildwithtolu/cueclear` (MIT) already
   expects, and the reason it is the most credibly shaped of the six.
2. Run extraction to a **draft** cue sheet. Treat every row as a *candidate*, with a confidence and a
   source for each cue.
3. Cross-check against rights registries. Pass 5's finding binds here: ISRC/ISWC/CWR have no usable open
   implementation, so this step is a vendor or manual lookup. Do not design it as automated.
4. **Require a named human signature** on the cue sheet before it leaves the system, stored as part of
   the record. Not a review queue that can be bulk-approved — a per-sheet attestation.
5. Settlement is out of scope by measurement, not by choice: there is **no** open residuals or royalty
   engine (`residuals calculation film` = 0 repositories). Hand off to the client's existing system.

**Why the signature is structural rather than procedural.** Clearance is a liability transfer. An agent
that reduces research time by 70% and introduces one unsignalled miss per hundred cues is *negative
value*, because the miss surfaces as an infringement claim after distribution. The signature is what
makes the speed-up safe to sell, and it is also what keeps the pattern honest about the gradient: this
recipe automates discovery and leaves judgment exactly where the open source leaves it.

## Pattern 34 — Script-to-breakdown on a permissive spine (the plane's only safe architecture)

**The problem.** A production wants AI-assisted script breakdown: scan the screenplay, tag cast, props,
locations, wardrobe, VFX and stunts, and emit something the production office can schedule from.
Commercial tools (Filmustage, Studiovity, RivetAI, Celtx, Blooper) do this; their accuracy claims are
self-published and unverified. The client wants it in-house, on their own infrastructure, and reusable.

**Why the obvious approach fails.** The temptation is to fork the one repository with the right scope.
Every candidate blocks you: `waooAI/waoowaoo` (14,989★) is **Elastic License 2.0** — delivering it as a
client service is the prohibited use; `koosoli/OpenShotDesigner` (47★) is **GPL-3.0**;
`jpcastel88/Script-Breakdown-Skills` (6★) and `machina-exm/film-studio-skills` (186★) carry **no licence
at all**; `ifrost/afterwriting-labs` (280★), which everything reaches for to render PDFs, is **also
unlicensed.**

**The architecture that survives a licence review.**

```
Screenplay (.fountain / .fdx / .pdf)
   │
   ├─ PARSE ─────────────► wildwinter/screenplay-tools (MIT, 29★, C++/JS/Python/C#)
   │                       └─ or vilcans/screenplain (MIT, 187★, Python) for render
   │                       └─ or rsdoiel/scripttool (AGPL-3.0, 46★) ONLY as a
   │                          separate process for .fdx/.fadein/.osf import —
   │                          AGPL: keep it behind a boundary, never linked in
   │
   ├─ STRUCTURE ────────► XucroYuri/how-to-make-script (MIT, 21★)
   │                       screenplay rules/structure as agent-readable knowledge
   │
   ├─ BREAKDOWN (build) ─► your tagging layer: scene → cast/props/locations/VFX
   │                       LLM extraction + a deterministic rule checker.
   │                       THIS IS THE BUILD. Nothing permissive exists for it.
   │
   ├─ SHOT PLANNING ────► neopen/story-shot-agent (Apache-2.0, 248★)
   │                       script → shot segments; the only permissive, maintained
   │                       agent in the plane. LangGraph + LlamaIndex
   │
   └─ SCHEDULE ─────────► constraint solve (CP-SAT) over the breakdown.
                           Reference only: mrrishit909/film-production-planner
                           (0★, NO LICENCE) proves the approach — READ, DO NOT COPY.
                           Export to Movie Magic / Excel; the client's office lives there.
```

**Licence boundaries, explicitly.** MIT/Apache/ISC components may be linked and shipped. `scripttool`
(AGPL-3.0) runs as a **separate executable invoked over a CLI or socket** or is dropped entirely — .fdx
import can be written against the published format instead. **Nothing unlicensed enters the tree**, which
rules out afterwriting; use `screenplain` (MIT) for PDF output.

**What to tell the client.** The parse and the shot planning are integration. **The breakdown tagging and
the scheduler are a build**, because the open ecosystem stops at the script. Budget for that honestly —
pass 17 measured the entire open production-management layer at **73 combined stars**.

**Falsifiable check for the next media pass.** If a permissive, multi-contributor breakdown-to-schedule
repository appears above ~25★, this pattern collapses into an integration and should be rewritten.

---

## Pattern 35 — Consent capture at the call sheet (the Mexican statute's missing system of record)

**The trigger, with a date.** Mexico's reformed **Federal Copyright Law Art. 87** and **Federal Labour
Law** amendments — published in the DOF **2026-05-14**, **in force 2026-05-15** — require **express,
purpose-specific, revocable consent** to use a performer's voice, image or AI-generated likeness; the
rights **survive the end of the contract**; explicit consent is required to use a worker's image or voice
**to train AI models or generate synthetic performances**; and AI-modified **advertising** featuring a
performer needs **separate consent and remuneration**. **Dubbing actors, voice-over artists and locutors
are named explicitly** — which puts the Mexican dubbing industry, serving all of Spanish-speaking LATAM,
directly in scope. In North America the 2026 WGA/SAG-AFTRA/DGA agreements impose a parallel
consent-and-compensation duty. **One build, two markets.**

**The insight that makes this a pattern rather than a policy memo.** Consent is **created at booking, not
at delivery.** Every existing provenance tool in this KB attaches claims to an *asset* after it exists —
C2PA at export, watermarking at encode. But the statutory artefact is a *permission*, granted before any
asset exists, scoped to a purpose, and revocable afterwards. The place it is actually created is the
**deal memo, the call sheet and the day-out-of-days** — and pass 17 measured that layer as having no
permissive maintained base (eight repositories, 73 stars, the only broad-scope one GPL-3.0).

**The build.**

```
BOOKING (the consent event — build this)
  performer + role + purpose scope (dubbing? synthetic performance?
  model training? advertising variant?) + territory + duration
  + post-termination scope + revocation hook
        │
        │ consent record keyed to performer AND purpose, versioned,
        │ revocation as a first-class state change (not a delete)
        ▼
CALL SHEET / DOOD  ── generated from the same model, so the consent
  (schedule layer)    trail and the production record cannot diverge
        │             Scope reference: method-production-suite/
        │             method-scheduling (Apache-2.0, 1★) — breakdown,
        │             stripboard, day-out-of-days, open file format.
        │             Permissive and the right shape; 1 star, so treat
        │             as a reference model, not a dependency.
        ▼
PRODUCTION ─► any synthetic voice/likeness step must present a valid,
              unrevoked consent token for THAT purpose, or it fails closed
        │     (gate it the way Pattern 15's rights-reservation gate works)
        ▼
PROVENANCE ─► C2PA manifest per asset carries the consent reference
              (Pattern 4 + Pattern 8 — already built in this KB)
        ▼
EVIDENCE ───► per-performer trail: what was granted, for what purpose,
              when, revoked or not. This is the deliverable a guild audit
              or an Art. 87 claim actually asks for.
```

**Why it fails closed rather than logging.** A revocable right means a pipeline that merely *records*
consent is non-compliant the moment consent is withdrawn. The gate must read current state at generation
time. This is the same shape as Pattern 15's rights-reservation gate, and the same lesson applies:
declaring is easy, honouring is the engineering.

**⚠️ Do not cite penalties.** Economic sanctions were **removed from the enacted Mexican text**. The
MX$586,000 and 1,000–5,000 UMA figures in circulation come from the **2025 draft**. Sell this on the
in-force duty, the dubbing-sector exposure and the guild agreements — not on a fine that does not exist.

**Why Globant wins this.** It needs production-office domain knowledge, LATAM statutory reading, and the
C2PA stack this KB already has — and there is **no incumbent to displace**, because the open layer where
the obligation lands is empty.

---

## Book, ebook & scholarly-publishing patterns — pass 18, 2026-11-26

Every repo named below appears with its **licence read from its own licence file** and its verified
last-commit date in `repos/foundations.md`, `verticals/solutions.md` or `agents/top.md`.

**The licence rule for this whole plane, applied in every recipe:** the *validators and renderers*
are permissive (BSD-3/MIT) and embeddable; the *platforms* are GPL-3.0/AGPL-3.0 and must be
deployed as separate services, not linked. Where a recipe crosses that line, the boundary is called
out explicitly.

---

### P33 — EAA backlist remediation, with compliance evidence as the deliverable (EMEA)

**Why:** the EAA has applied to ebooks since 28 June 2025, backlist transition to June 2030, and the
real penalty is **removal from EU storefronts**. Fewer than 4 in 10 European publishers are reported
to be producing accessible ebooks. The validators are permissive; **the generator does not exist.**

**Wire-up:**

1. **Ingest & triage.** `w3c/epubcheck` (**BSD-3-Clause**) for structural validity →
   `daisy/ace` (**MIT**) for EPUB Accessibility 1.1 conformance. Both run as CI steps. Ace's JSON
   report is the triage queue; sort the backlist by defect class, not by title.
2. **Metadata first — this is the cheapest win and a hard EAA requirement.** Accessibility features
   must be **discoverable in metadata**. Assert `schema:accessibilityFeature`,
   `accessibilityHazard`, `accessMode` and `accessibilitySummary` in the OPF. Many titles fail
   discoverability while being substantially accessible — fix the metadata before touching content.
3. **Alt text — the part Globant builds.** No open EPUB alt-text generator exists (the only
   EPUB-specific result is the *AltGen* paper, no code). Build it against the Ace report, and copy
   the honest-failure design from `CUNY-AI-Lab/pdf-accessibility-app`: when the model service
   fails, **flag the figure for re-upload rather than emitting empty alt that passes a checker**.
4. **Human fix-up.** `Sigil-Ebook/Sigil` (GPL-3.0) as the remediator's desktop tool — a separate
   application, so no copyleft touches client code.
5. **DRM check.** If the client applies LCP, verify via `readium/readium-lcp-server`
   (BSD-3-Clause) that protection does **not** disable accessibility features — an explicit EAA
   requirement and a frequently missed one.
6. **Re-validate and retain.** Re-run `epubcheck` + `ace`, and **store the reports as the
   compliance artefact.** The stored evidence is what a retailer or auditor asks for.

**Licence boundary:** steps 1, 2, 5 and 6 are **BSD-3/MIT — fully embeddable**. Step 4 is a
separately installed GPL-3.0 desktop tool. **Do not use `aerkalov/ebooklib` (AGPL-3.0) for the
server-side EPUB writing in step 2 or 3** — it would place network copyleft on the hosted service.
Write the OPF with a permissive XML library or a purpose-built writer.

---

### P34 — AI-disclosure and editorial-integrity plugin for OJS (LATAM first, globally reusable)

**Why:** **815 of 1,119 (72.8%) Scopus-indexed Latin American journals have no explicit AI
guidelines** (*Publications*, 2026), and `pkp/ojs` is the dominant platform in the region with
25,000+ journals worldwide. One plugin, many deployments.

**Wire-up:**

1. **Integrate at `pkp/pkp-lib`** (GPL-3.0), not in `pkp/ojs` directly — it is the stable seam
   shared by **both** OJS (journals) and `pkp/omp` (monographs), so the same plugin serves both.
2. **Submission-time disclosure.** Add a required AI-use declaration to the submission form:
   which tools, at which stage, for which sections.
3. **Editorial sign-off capture.** Record **who** approved AI-assisted content and **when**. This is
   not bureaucracy — under **EU AI Act Article 50** (in force August 2026), documented human
   editorial responsibility is reported to remove the labelling obligation, so the record is the
   compliance artefact for any journal with EU readership or authors.
4. **Policy publication.** Render the journal's AI policy as a public page from the same
   configuration, so the policy and the enforcement cannot drift apart.
5. **Reviewer-side screening.** Surface the declaration to reviewers; do **not** auto-reject on an
   AI-detection score — accuracy of detection is exactly what 86% of NA publishers said they
   distrust, and a false accusation is a worse failure than a missed disclosure.

**Licence position:** the deliverable **is** a GPL-3.0 plugin. No contamination question arises —
publish it as GPL-3.0 and the client's obligation is satisfied by distributing the plugin.
**The margin is in deployment, configuration and the policy design, not in withholding code.**

---

### P35 — Permissive-end-to-end book metadata and ONIX distribution (any region)

**Why:** this is **the cleanest fully permissive path in the plane** — no copyleft anywhere — and
ONIX code lists are freely available, so there is no content toll (unlike MedDRA in healthcare or
CPT in US coding).

**Wire-up:**

1. **`thoth-pub/thoth`** (**Apache-2.0**) as the metadata system of record — books, works,
   contributors, with ONIX and MARC export.
2. **`titusz/onixcheck`** (**Apache-2.0**) to validate ONIX 2.1/3.0/3.1 against the official XML
   Schema in CI before anything reaches a trading partner.
3. **`chrisribal/onix-parser`** (**MIT**) for read **and write** of ONIX 3.0/3.1 with official code
   list resolution — the only verified permissive ONIX *writer*.
4. **`zach-m/jonix`** (**Apache-2.0**) if the client is a JVM shop ingesting partner feeds.
5. **Agent layer — Globant builds it; there is none.** No open-source agent for ONIX generation or
   correction exists. The highest-value target is **error explanation and repair suggestion**:
   `onixcheck` says *what* is invalid; an agent that says *why* and proposes the corrected element
   is the differentiator.
6. **Subject-scheme mapping is also a build.** No verified repo handles **Thema** or **BISAC** as a
   first-class feature. A client selling a backlist into both NA (BISAC) and EMEA (Thema) needs that
   mapping, and it does not exist openly.

**Licence position:** **Apache-2.0 / MIT throughout.** This recipe can be embedded in a proprietary
product with no copyleft obligation — the only recipe in this plane of which that is true.

---

### P36 — Japanese accessible-production pipeline (APAC)

**Why:** Japan's Reading Barrier-Free Act (2019) targets libraries, not publishers, so there is **no
product conformance duty** — but Kadokawa itself states accessibility "has not advanced
sufficiently", and the **7 April 2026** cabinet decision recognising digital textbooks as official
textbooks creates an obligation through **education procurement**. The differentiator here is
**script and language competence, not compliance pressure.**

**Wire-up:**

1. **Layout and typesetting:** `vivliostyle/vivliostyle.js` (**AGPL-3.0**) — the best open engine
   for **CJK vertical writing, ruby/furigana and complex layout**.
   **⛔ Deploy it as a standalone rendering service behind an API.** AGPL §13 attaches to a hosted
   service's users; keeping it in its own service with published source satisfies the licence
   without touching the client's product code.
2. **Furigana and read-aloud:** `daisy/pipeline-modules` (**LGPL-2.1/3.0**) for TTS and DAISY output
   — weak copyleft, linkable with care, and the module set is the licensed artefact.
   **Do not cite `daisy/pipeline` itself: it has no licence file** (it is a `git-subrepo` umbrella).
3. **Validation:** `w3c/epubcheck` (BSD-3) + `daisy/ace` (MIT), as in P33.
4. **Audio output:** `DrewThomasson/ebook2audiobook` (**Apache-2.0**) for multi-language audiobook
   generation.
5. **Evaluation corpus:** **Aozora Bunko** (17,700+ public-domain Japanese works as of January
   2026) — a licence-safe corpus for building and benchmarking the pipeline before touching
   client content. Note Japan's **70-year** term when selecting titles.

**Licence boundary:** one AGPL component (isolated as a service), one LGPL component (linkable),
two permissive validators. Workable, but the architecture is **dictated by the licence**, not by
engineering preference — say so in the proposal rather than discovering it in delivery.

---

### P37 — Marrakesh accessible-format production for authorized entities (LATAM)

**Why:** no EAA equivalent exists in LATAM; access flows through the **Marrakesh Treaty** and
authorized entities. Argentina's **Article 36 bis** explicitly permits accessible-format
reproduction including **audio and digital**. The supply gap is measured: **~25,000** accessible
books in Argentina against **~100,000** in Spain, and a ULAC congress of **19 countries** called
specifically for greater digital accessibility and cross-border exchange.

**Wire-up:**

1. **Confirm the legal basis first, per country.** The exception is what makes the work lawful
   without per-title clearance. Argentina's Art. 36 bis is verified; **other countries must be
   checked individually against the IFLA Marrakesh Monitoring Report** — do not assume regional
   uniformity.
2. **Conversion:** `daisy/pipeline-modules` (LGPL) for DAISY and braille output — the formats
   authorized entities actually distribute, which EPUB alone does not cover.
3. **Spanish-language audio:** `DrewThomasson/ebook2audiobook` (Apache-2.0) or
   `p0n1/epub_to_audiobook` (MIT).
4. **Validation:** `epubcheck` (BSD-3) + `ace` (MIT).
5. **Delivery:** `gotson/komga` (**MIT**) as the catalogue and OPDS server — chosen over Kavita and
   Calibre-Web (both GPL-3.0) specifically because it is the **only permissive reading server
   verified**, so a public-sector client can wrap it in a proprietary portal.
6. **Interoperate, don't duplicate:** enrich against `internetarchive/openlibrary` (AGPL-3.0) **via
   its public API** — reading an AGPL service's data creates no obligation; bundling its code would.

**Pitch note:** the buyer is public-sector (libraries, authorized entities, ministries of education)
and the proposition is **capacity**, not compliance. This is the inverse of P33's EMEA framing, and
reusing the compliance pitch here would land badly.

---

### P38 — Ebook → audiobook at catalogue scale (any region)

**Why:** the one genuinely hot open-source category in this plane, and the licences are permissive.
Open TTS became good enough during 2026.

**Wire-up:** `aerkalov/ebooklib` **avoided** — use `futurepress/epub.js` (BSD-2) or a permissive
parser for chapter extraction → `DrewThomasson/ebook2audiobook` (Apache-2.0, voice cloning,
many languages) or `santinic/audiblez` (MIT, Kokoro-82M) → `advplyr/audiobookshelf` (GPL-3.0,
deployed separately) for delivery.

**The quality gate is the whole engagement.** These tools produce audio cheaply; what they do not
produce is a **pronunciation policy** — names, place names, numerals, acronyms, and in CJK the
correct reading of ambiguous kanji. A lexicon plus a QC sampling step is the deliverable with
margin, exactly as the rules library was in the healthcare pharmacovigilance pattern.

---

### What not to promise in this plane

| Temptation | Why it fails |
|---|---|
| "We'll use `ebooklib` for the EPUB service" | **AGPL-3.0.** Network copyleft on a hosted service. The most likely accidental obligation in publishing |
| "`daisy/pipeline` is LGPL" | The umbrella repo has **no licence file**. Cite `pipeline-modules` (LGPL) or `pipeline-ui` (MIT) |
| "This PDF accessibility repo is MIT, the badge says so" | `AIScientists-Dev/AI-Powered-PDF-Accessibility` has **no licence file at ten probed paths**. A badge is not a grant |
| "We'll build on the EPUB 3 spec repo" | `w3c/publ-epub-revision` is under the **W3C Software and Document License** — spec text, not a software grant |
| "There's an open alt-text generator for EPUB we can adopt" | There is not. Measured. Everything generative targets **PDF**; the one EPUB paper has no located code. **It is a build** |
| "Thema/BISAC mapping is a solved problem" | No verified open repo treats it as a first-class feature. Also a build |
| Reusing the NA 63% AI-adoption figure for other regions | It is a **BookNet Canada/BISG North American** survey. No comparable APAC or LATAM figure was located |
| Quoting EAA enforcement as established fact | Every enforcement claim located traces to a **vendor page**, and two of them contradict each other |

---

## Pattern 36 — The licence-clean sports vision spine (replace the AGPL default before it reaches a client)

**Problem.** Every sports-CV tutorial, demo and Stack Overflow answer builds on
**`ultralytics/ultralytics` (AGPL-3.0, 63,769★)**, often with
**`mikel-brostrom/boxmot` (AGPL-3.0, 8,330★)** for tracking. A team that follows the obvious path
ships AGPL into a hosted service, where **§13 obliges Globant to offer the service's source to its
users**. This is discovered in legal review, after the demo has been approved — the worst possible
moment. The capability is not the problem; the default is.

**The swap, component for component.** Each replacement is permissive, actively maintained, and does
the same job:

| Job | AGPL default | **Permissive replacement** | License | Stars | Last push |
|---|---|---|---|---|---|
| CV utilities, annotation, zones | `ultralytics` helpers | **`roboflow/supervision`** | **MIT** | 51,730 | 2026-11-26 |
| Multi-object tracking | `boxmot` | **`roboflow/trackers`** | **Apache-2.0** | 4,022 | 2026-11-25 |
| Lightweight MOT alternative | `boxmot` | **`tryolabs/norfair`** | **BSD-3-Clause** | 2,708 | 2025-04-30 |
| Tracking algorithm reference | — | **`FoundationVision/ByteTrack`** | **MIT** | 6,833 | 2024-06-19 (vendor it) |
| Sport-aware detection, pitch keypoints, radar view | — | **`roboflow/sports`** | **MIT** | 5,517 | 2026-11-25 |
| Pose and joint angles | — | **`davidpagnon/Sports2D`** (BSD-3) or **`open-mmlab/mmpose`** (Apache-2.0) | **BSD-3 / Apache-2.0** | 354 / 8,083 | 2026-11-25 / 2025-08-04 |
| Highlight / moment retrieval | — | **`line/lighthouse`** | **Apache-2.0** | 274 | 2026-11-01 |
| Provider-agnostic data model | — | **`PySport/kloppy`** | **BSD-3-Clause** | 573 | 2026-11-06 |
| Cross-provider identity resolution | — | **`withqwerty/reep`** | **CC0-1.0** | 245 | 2026-08-20 |

**Wiring.**

```
[broadcast feed / fixed camera]
      ↓
[detector]  ──► supervision (MIT): annotate, zones, line counters
      ↓
[roboflow/trackers (Apache-2.0) or norfair (BSD-3)]  ──► stable track IDs
      ↓
[roboflow/sports (MIT)]  ──► pitch keypoints → homography → real-world coordinates
      ↓
[kloppy (BSD-3)]  ──► normalize into a provider-agnostic tracking/event model
      ↓
[reep (CC0)]  ──► resolve players/teams to stable cross-provider identities
      ↓
[line/lighthouse (Apache-2.0)]  ──► retrieve highlight moments
      ↓
[clip + overlay render]  ──► deliverable
```

**The detector is the one open decision**, and it must be made deliberately: choose a permissively
licensed detector, or train your own weights, or buy Ultralytics' commercial licence. Do not let the
choice be inherited from a notebook.

**Two licence rules this pattern exists to enforce.**
1. **Resolve the licences of what you link, not of the repo.** `boxmot`'s own licence file states
   third-party components retain their own notices — the compilation-licence trap cycle 8 found on
   `chromaprint`. Native and model dependencies need their linked licences resolved in CI.
2. **Never record a licence from an API field alone.** Five R packages in this plane report
   `NOASSERTION` and are all **MIT**; `hudl/open-data` reports `NOASSERTION` and ships its licence as
   a **PDF**; `HiEventsDev/Hi.Events` reports "Other" and is **AGPL-3.0 + §7(b) attribution** in a
   file named `LICENCE`. See `repos/foundations.md` for the full probe list.

---

## Pattern 37 — The creator-broadcaster match-day pipeline (built for the LATAM buyer, runs on one GPU)

**Problem.** A digital-native rights-holder — the CazéTV archetype, and there are at least 21
World-Cup-linked rights-holders across LATAM's six biggest markets, 76% of them streaming-committed
— has an audience and advertising revenue but **no broadcast operation**. They need per-match
highlights, vertical clips and a scoreboard overlay, at a marginal cost that works for a league
nobody else is covering. They cannot absorb an AGPL obligation and cannot pay per-minute inference.

**Why the open stack fits this buyer better than it fits an incumbent.** Every component runs
locally, so there is no per-minute cost and no footage leaving the building — which also satisfies
the EMEA sovereignty requirement, making the same deployment sellable in two regions.

**Recipe.**

| Stage | Component | License | Note |
|---|---|---|---|
| 1. Detect & track | `roboflow/sports` + `roboflow/supervision` | **MIT** | Players, ball, pitch keypoints |
| 2. Spot moments | `line/lighthouse` | **Apache-2.0** | Moment retrieval; reproducible research baselines |
| 3. Cut verticals | `Anil-matcha/AI-Youtube-Shorts-Generator` (6,577★) or `jipraks/yt-short-clipper` (1,113★) | **MIT** | Both pushed within two days of this pass |
| 4. Scene boundaries | `Breakthrough/PySceneDetect` | **BSD-3-Clause** | Already in `repos/foundations.md` |
| 5. Subtitle & dub | `VideoLingo` (Apache-2.0), `KrillinAI` (MIT) | **Permissive** | Already recorded; pt-BR ↔ es-419 is the regional requirement |
| 6. Overlay | `JimThatcher/sport-streamer` (MIT, 31★) or a custom browser source | **MIT** | ⚠️ 31★ and dormant — expect to own this code |
| 7. Publish | `yt-dlp` / platform APIs | Unlicense | Already recorded |

**Honest sizing.** Stage 6 is the weak link and the pattern says so: the entire open scoreboard and
overlay category tops out at **31 stars** with two of three projects dormant. Budget for building
the overlay renderer; everything upstream of it is mature and permissive.

**Stage 0 — the stage most proposals skip.** Confirm in writing which rights the client holds for
clip distribution per platform and territory. LATAM rights are split per-territory and per-window
(Champions League runs Disney/Paramount 50/50 in Spanish-speaking markets, WBD in Brazil; the
Mexican deal expires end of 2026/27), and an automated pipeline will happily publish a clip into a
territory the client does not hold. Pass 16's avails plane is the reference for modelling that.

---

## Pattern 38 — Entering a sport the open stack has never served (the APAC cricket build)

**Problem.** The open sports stack is **football-first and essentially football-only**: `SoccerNet/*`,
`kloppy`, `mplsoccer`, `penaltyblog` and `UnravelSports` were all built for association football,
with American sports served by the R cluster. **Cricket, kabaddi, sumo, Australian rules and the
Asian baseball leagues have no equivalent at any star level** — against an IPL rights cycle worth
about **US$5.23bn**. A client in that market cannot adopt; they have to build.

**What transfers for free, and what must be built.** This split is the whole value of the pattern,
because it turns "no tooling exists" into a bounded piece of work:

| Layer | Status for a new sport | Component |
|---|---|---|
| Detection, tracking, pose | **Transfers unchanged** — sport-agnostic | `supervision` (MIT), `trackers` (Apache-2.0), `mmpose` (Apache-2.0), `Sports2D` (BSD-3) |
| Camera calibration / homography | **Transfers as method**, must be re-fit to the playing surface | ⚠️ `SoccerNet/sn-calibration` (113★) is the reference and ships **no licence** — read it for method, write your own |
| Playing-surface geometry | **Must be built** | Crease, pitch, boundary rope — not a football pitch |
| Event taxonomy & state machine | **Must be built** | Overs, innings, dismissal types, powerplays, DRS |
| Data model | **Extend, don't replace** | `kloppy` (BSD-3) is a provider-agnostic model worth extending upstream |
| Identity resolution | **Must be built** | `withqwerty/reep` (CC0) is football-only; the pattern is reusable |

**Why this is defensible rather than merely absent.** The permissive foundations mean the build is
sport-specific logic on top of solved vision — and because `kloppy` is BSD-3 and actively maintained
(2026-11-06), a cricket extension can be contributed upstream while the event taxonomy, calibration
fits and trained weights stay with the client. That is a clean IP boundary: contribute the model,
keep the domain.

**Regulatory wiring for APAC, carried from cycle 8.** Latham & Watkins (September 2026) places APAC
jurisdictions in divergent regulatory categories — binding risk-based (South Korea, Vietnam),
targeted (China), others — so the compliance component is a **policy engine keyed by jurisdiction**,
not one compliance mode. Content labelling and disclosure is the recurring concrete obligation, which
matters the moment synthetic commentary or a synthetic presenter enters the pipeline.

---

## Pattern 39 — The substrate test: a 30-minute gate before any sports-data proposal

**Problem.** The sports-data layer contains repos with **3,847**, **2,870** and **757** stars that
ship **no usable licence grant**, and five more reporting `NOASSERTION` that are actually **MIT**. A
proposal built on star counts will be wrong in both directions: it will adopt something unshippable
and reject something perfectly usable.

**The gate.** Before any sports-data dependency enters a proposal, answer one question: **who holds
the substrate?** The answer predicts licence health better than any other signal measured in this KB.

| Substrate | Expect | Action |
|---|---|---|
| **Pixels you already license** (your own feed) | Permissive, abundant, active | **Proceed.** Pattern 36 |
| **Client-side artifacts** (esports replays — the file is on the player's disk) | Permissive and active: three independent MIT CS2 parsers, all pushed within four days of this pass | **Proceed.** `demoinfocs-golang`, `demoparser`, `awpy` |
| **Vendor optical/event feeds** (Opta, Sportradar, Second Spectrum, StatsBomb) | High stars, no usable grant | **Stop.** Price the commercial feed; assume nothing is free |

**Then run the licence probe — the API field is not an answer.**

```
# 1. existence (the only true oracle)
git ls-remote --exit-code -h https://github.com/<slug> >/dev/null && echo OK

# 2. stars/forks/spdx/pushed_at — works for ANY repo, several at once
gh api -X GET search/repositories -f q='repo:<slug> repo:<slug2>' \
  --jq '.items[] | "\(.stargazers_count)\t\(.license.spdx_id // "NONE")\t\(.pushed_at[0:10])\t\(.full_name)"'

# 3. if NOASSERTION or nothing: read the file. 12 names x 2 branches.
#    LICENSE LICENSE.md LICENSE.txt license.txt LICENCE LICENCE.md
#    COPYING COPYING.md LICENSE-MIT DESCRIPTION LICENSE.pdf
# 4. CONTROL: if all 404, fetch README.md. If README 404 too, your branch name is wrong -
#    a 404 is NEVER by itself proof a licence is missing.
```

**Four failure modes this gate catches, every one of them measured in this plane:**

1. **Licence as a PDF.** `hudl/open-data` (3,847★) ships `LICENSE.pdf` **at the repo root** — HTTP
   200, `application/octet-stream`. **No SPDX field, badge or SBOM scan can read it.** Flag as
   "read manually"; never treat as absent, never auto-approve.
2. **No licence at all behind a registration wall.** `hudl/statsbombpy` (758★) has no licence file;
   its README defers *data* terms to that PDF and requires registering personal details. The
   **code** carries no grant → default all-rights-reserved.
3. **Garbage in the licence field.** `hudl/StatsBombR` (314★) declares `License: 3.5.0` in
   `DESCRIPTION` — a version number. Read the *value*, not just the field's presence.
4. **The R/CRAN false negative — the one that saves work.** A 46–57 byte `LICENSE` holding only
   `YEAR:`/`COPYRIGHT HOLDER:`, the real grant in `LICENSE.md`, and `License: MIT + file LICENSE` in
   `DESCRIPTION`. `nflfastR`, `hoopR`, `cfbfastR` and `nflreadr` all report `NOASSERTION` and are all
   **MIT**. Four usable dependencies that a careless pass would have discarded.

**The rule, stated for reuse across all twelve industries:** *existence comes from `ls-remote`;
metadata comes from `search/repositories`; the licence comes from reading the file — and a missing
file is only proven by a control request that succeeds.*

---

## Pattern 40 — The secure intake chain (leak to searchable corpus, nothing leaving the newsroom)

**The buyer:** any newsroom or NGO that accepts documents from sources and has written an AI policy
it now has to evidence. Named buyers from pass 20 research: El Comercio (Lima), Listín Diario
(Dominican Republic), SiPreBA member newsrooms (Argentina), any GIJN member.

**Why it is wired this way:** the GIJN technology agenda records the requirement verbatim — triage
leaks **without exposing sensitive data to third-party platforms**. Every component below is
self-hostable, and no document crosses a vendor boundary.

| Step | Component | Licence | Why this one |
|---|---|---|---|
| 1. Intake | `freedomofpress/securedrop` (3,897★) | AGPL-3.0 | Tor-based submission; the standard a source has heard of |
| 2. Disarm | `freedomofpress/dangerzone` (5,858★) | AGPL-3.0 | Converts the untrusted file to a safe PDF **before** anyone opens it |
| 3. Extract | `ICIJ/extract` (257★) | **MIT** | Distributed OCR/text extraction at collection scale |
| 4. Index + NER | `ICIJ/datashare` (784★) | AGPL-3.0 | Self-hosted search with named-entity extraction; pushed 2026-11-26 |
| 5. Validate | `ICIJ/prophecies` (31★) | AGPL-3.0 | Routes the labour-intensive checks to humans and records who checked what |
| 6. Publish | `MuckRock/documentcloud` (54★) | AGPL-3.0 | Annotate and embed the documents in the story |

**Wiring:** SecureDrop's journalist workstation (`securedrop-client`, AGPL) exports to a watched
directory; Dangerzone runs as the conversion step; `extract` feeds Datashare's index; Datashare's
REST API is the only surface an agent touches. **Do not fork the AGPL components** — operate them
unmodified and build beside them (see the licence posture in `verticals/solutions.md`).

**Where Globant's value sits:** steps 3→5. The agent reads Datashare's API, proposes the entity
graph and the check queue, and writes back to Prophecies — so every machine judgement lands in a
human validation record. That record is the evidence the AI policy demands, and it is the
deliverable.

**Do not substitute Aleph for Datashare without saying so.** Aleph (MIT, 2,516★) is the platform
every guide recommends; its default branch last moved **2025-12-19** (`repos/foundations.md`). If a
client wants MIT in this slot, the honest options are **Uwazi** (MIT, pushed 2026-11-26) or
operating Datashare unmodified.

---

## Pattern 41 — The records-access desk (FOIA/FOI at scale, with the agent on the drafting side)

**The gap this fills, measured:** the query `FOIA freedom of information request` returns 19
repositories; the top six hold **35 stars between them**, five of the six carry **no licence file**,
and the most-starred was last pushed **2017-12-11**. The only FOIA MCP bridge found,
`morisy/muckrock-mcp` (3★), has **no licence file** and is described *by its own author* as "highly
experimental, insecure, and unstable". Meanwhile the real platforms are healthy. **This is the
clearest build-vs-adopt hole in the plane.**

| Step | Component | Licence | Role |
|---|---|---|---|
| Portal | `okfde/froide` (413★, 2026-11-09) | **MIT** | The permissive FOI platform — use this when the portal must sit inside a product |
| Portal (alt) | `mysociety/alaveteli` (421★, 2026-11-25) | AGPL-3.0 | Use when the deployment is a public FOI site in its own right |
| US requests | `MuckRock/muckrock` (124★, 2026-11-24) | AGPL-3.0 | Federal + state request routing with a public archive |
| Drafting agent | `jamditis/claude-skills-journalism` (462★) | **MIT** | Its `foia-requests` skill carries federal and state templates |
| Response triage | `ICIJ/datashare` + `ICIJ/prophecies` | AGPL-3.0 | Released records arrive as scanned PDFs — Pattern 40 steps 3→5 |

**Wiring:** Froide exposes the request lifecycle; the drafting agent proposes the request text and
the appeal text against Froide's jurisdiction metadata; responses enter the Pattern 40 chain. The
agent never files unreviewed — a records request is a legal act in the newsroom's name.

**The honest build note:** a licensed, tested MCP bridge for records-request platforms **does not
exist**. Building one against Froide (MIT) is a small, self-contained, publishable piece of work,
and it is the piece a client cannot buy today. Do not wire `muckrock-mcp` into a deliverable; read
it for the tool surface and write your own.

---

## Pattern 42 — Field capture to structured evidence (the offline-first chain, built for LATAM and APAC)

**The buyer:** investigations where the reporter is in the field, the network is hostile or absent,
and the device may be inspected. Horizontal's own user stories record a custom Tella build for
**forest defenders in Brazil** with a simplified UI and a default connection to the monitoring
organisation's servers, and Belarusian/Russian translations for other deployments.

| Step | Component | Licence | Role |
|---|---|---|---|
| 1. Capture | `Horizontal-org/Tella-Android` (118★, 2026-11-17) | **MIT** | Encrypts and hides photos, video and forms on-device; works offline |
| 2. Receive | `huridocs/uwazi` (330★, 2026-11-26) | **MIT** | Tella's documented upload target; structured documentation database |
| 3. Verify time/place | `bellingcat/ShadowFinder` (631★) | **MIT** | Chronolocation from shadow length — narrows when/where a photo was taken |
| 4. Verify file | `exiftool/exiftool` (5,320★) | GPL-3.0 | EXIF/GPS/device metadata; run as a separate process, not linked |
| 5. Clean records | `OpenRefine/OpenRefine` (12,120★) | BSD-3-Clause | Reconcile names, places and dates across the corpus |

**Why this one is unusual in this KB: the whole chain is permissive.** Steps 1, 2, 3 and 5 are MIT or
BSD, and step 4's GPL-3.0 is reached by **invoking a binary, not linking a library** — so it does not
reach the surrounding code. This is the one pattern in the plane that can be embedded in a
proprietary product without an AGPL conversation, which makes it the right opening offer when the
client's general counsel is the blocker.

**Agent role:** summarise an incoming batch, propose the Uwazi entity and template, and flag items
whose metadata contradicts the submitted account (step 3 against step 4) — surfaced to a human, never
auto-resolved.

---

## Pattern 43 — The verification desk, with the fact-check left to the human

**Read the licence findings before building this one.** The temptation is to reach for an automated
fact-checker. The measurement says there is nothing to reach for: one non-trivial open system
(`DEFAME`, 64★, Apache-2.0) dormant since **2025-09-30**, and below it four zero-star repositories.
Build the **evidence assembly**, not the verdict.

| Step | Component | Licence | Role |
|---|---|---|---|
| 1. Transcribe | `ggml-org/whisper.cpp` (55,542★) or `m-bain/whisperX` (25,695★) | MIT / BSD-2-Clause | Interview and broadcast transcription; WhisperX adds diarization |
| 2. Archive the source | `jamditis/claude-skills-journalism` web-archiving skill | **MIT** | Capture before it changes or disappears |
| 3. Provenance | C2PA tooling already catalogued in pass 9 (`agents/trending.md`) | — | Content Credentials on anything inbound |
| 4. Image forensics | `exiftool/exiftool` | GPL-3.0 | Metadata first; it answers more questions than any detector |
| 5. Collaborative check | `meedan/check-api` (21★, MIT, 2026-11-24) | **MIT** | The annotation/tipline backend — **not** the 131★ dev-environment wrapper |
| 6. Adjudicate | **a human editor** | — | Per finding 4 in `agents/top.md`, this step has no open implementation and the KB does not pretend otherwise |

**Regional note:** Meedan's Check is the component with real deployment history in **APAC and
LATAM** — tipline programmes run with AFP, BOOM, India Today and Africa Check across India, Brazil,
South Africa, Kenya and Nigeria, including roughly 335,000 questions across four WhatsApp tiplines
during India's 2021 election cycle. If the engagement is a tipline, this is the proven starting
point, not a greenfield build.

**Two licence gates before you ship any of this.**

1. **`buriedsignals/spotlight` (67★) is MIT in its header and its own LICENSE file then states the
   skills "adapt or synthesize" GIJN methodology published under `CC BY-ND 4.0` — NoDerivatives.**
   Resolve the GIJN terms before reusing that skill text. The code licence and the knowledge licence
   are two separate questions, and only one of them is answered.
2. **`ehurrn/newsroom-extension` (11★) is not under the Unlicense**, though the file says so for two
   paragraphs. Its modified dedication reaches **"any work produced by the software"** — i.e. the
   newsroom's own journalism — unless the work explicitly indicates otherwise. Do not place it in a
   client's newsroom. Read it for the skill inventory; write your own under terms the client's
   counsel has seen.

## Pattern 44 — The licence-clean splat pipeline (capture to headset, nothing gated)

**Problem.** A client wants photoreal 3D capture of a real location or object, delivered to a browser
and a headset. The obvious stack — the Inria reference implementation everyone cites — cannot be
shipped, and the mistake is usually discovered after the pilot.

**The gate, first.** Do not start from `graphdeco-inria/gaussian-splatting` (24,564★,
**Gaussian-Splatting License, research only**) or `NVlabs/instant-ngp` (17,604★, **NVIDIA Source
Code License, non-commercial**). Both are reference reading. Neither goes into a deliverable.

**Wiring.**

1. **Pose the cameras** — `colmap/colmap` (new BSD, 13,302★, pushed 2026-11-26) for
   structure-from-motion. Read its `LICENSE`: it warns that *building COLMAP with its dependencies may
   affect the resulting licence*, so pin the build and record the linked libraries, exactly as cycle 8
   required for Chromaprint. For an aerial or large-site capture, `OpenDroneMap/ODM` is capable but
   **AGPL-3.0** — if the output is delivered as a hosted service, use COLMAP instead.
2. **Train the splats** — `nerfstudio-project/gsplat` (**Apache-2.0**, 5,961★). This is the
   substitution that makes the engagement legal. If the client's infrastructure has no NVIDIA GPUs, use
   `ArthurBrussee/brush` (**Apache-2.0**, 5,392★, pushed 2026-11-23) instead: Rust + WebGPU, no CUDA,
   and it trains in a browser. If you want ray-traced quality and have NVIDIA hardware,
   `nv-tlabs/3dgrut` (**Apache-2.0**, 2,515★) — note it is Apache while its own stablemate instant-ngp
   is not.
3. **Clean and compress** — `playcanvas/supersplat` (MIT, 10,731★) to crop, denoise and cut the splat
   count. This is the step that decides whether the asset loads on a headset at all.
4. **Convert and optimise for delivery** — `donmccurdy/glTF-Transform` (MIT) as the scriptable build
   step, with `zeux/meshoptimizer` (MIT) and `google/draco` (Apache-2.0) for geometry and
   `KhronosGroup/KTX-Software` (Apache-2.0) for textures. Take the glTF **terms from the published
   Khronos specification, not from `KhronosGroup/glTF`** — that repo has no licence file (verified).
5. **Deliver** — `google/model-viewer` (Apache-2.0) for the one-tag web/AR embed;
   `playcanvas/engine` (MIT) or `BabylonJS/Babylon.js` (Apache-2.0) for an interactive scene;
   `mkkellogg/GaussianSplats3D` (MIT) or `antimatter15/splat` (MIT) if you want a splat renderer
   inside an existing three.js app.
6. **On-headset** — `KhronosGroup/OpenXR-SDK` (Apache-2.0) as the device API so the build is not
   locked to one vendor, `godotengine/godot` + `GodotVR/godot-xr-tools` (both MIT) for a native app,
   or `splatxr/splatxr` (MIT, 39★) for on-device splat rendering with physics and portals — small, but
   the only permissive option of its kind.

**Licence table for the proposal.** Every component above is MIT, Apache-2.0 or new BSD. **No
copyleft, no research licence, no registration gate.** That sentence is the pattern's whole value in a
procurement review, and it is the thing a competitor arriving with the Inria stack cannot say.

## Pattern 45 — The volumetric-video build (and the honest conversation that precedes it)

**Problem.** The client says "volumetric video" and means a moving subject, not a static scene. The
market narrative says this is a solved product category. It is not.

**What to say first.** Static capture is a healthy permissive ecosystem. The **temporal** layer is
not: `hustvl/4DGaussians` is Apache-2.0 with 4,047★ and **has not been pushed since 2024-10-27**, and
the only permissive, actively maintained production 4D pipeline found is
`ASU-NEM-Labs/open4dgs-core` (**MIT, 161★, pushed 2026-11-21**). The strongest 4D research codebase,
`zju3dv/EasyVolcap`, is usable commercially but **only after registering the project** under PRL v1.0.
This is a build with a research dependency, priced accordingly — not an integration.

**Wiring.**

1. **Multi-camera rig and sync** — the hard, unglamorous part, and no open project solves it. Budget
   it as hardware plus bespoke integration.
2. **Per-frame pose** — `colmap/colmap` (new BSD).
3. **Temporal reconstruction** — `ASU-NEM-Labs/open4dgs-core` (**MIT**) as the spine, since it is both
   permissive and alive. Its web editor derives from PlayCanvas SuperSplat, so step 5 of Pattern 44
   carries over unchanged.
4. **If quality forces it** — `zju3dv/EasyVolcap` (**PRL v1.0**). Then, *before any engineer clones
   it*: register the project by name with the lab. One registration per distinct project, free, no
   approval needed, and it must precede use. **Put this in the SOW, not the sprint board.**
5. **Performance capture of the subject** — `google-ai-edge/mediapipe` (Apache-2.0, 37,873★) for
   landmarks. Avoid `freemocap/freemocap` (AGPL-3.0) and `zju3dv/EasyMocap` (PRL v1.0) in a
   proprietary deliverable unless the respective obligation has been accepted deliberately.
6. **Compression and carriage — stop here and be explicit.** `MPEGGroup/mpeg-pcc-tmc2` is the ISO/IEC
   V-PCC reference implementation under a **BSD licence that grants no patent rights**, at 177★. The
   spatial-video consumer path (MV-HEVC) runs through x265 multiview over a patent pool. **Do not
   promise an end-to-end open volumetric pipeline** — the capture is open and the carriage is not.
   Deliver as splats over HTTP to a controlled client, or price the codec licensing explicitly.

**Falsifiable prediction attached to this pattern.** If `4DGaussians` revives or `open4dgs-core`
crosses ~1,000★ within two quarters, step 3 becomes an integration rather than a build and this
pattern should be rewritten. Re-measure both before reusing it.

## Pattern 46 — The 20-minute licence gate for any spatial or 3D proposal

Run this before writing a line of a spatial proposal. It is four commands and it has caught a
shippability error in every repo class in this plane.

1. **Existence** — `git ls-remote --exit-code -h https://github.com/<slug>`. This is the only oracle.
   `search/repositories` returned **HTTP 422 "resources do not exist"** this pass for three repos that
   do exist (`nerfstudio-project/viser`, `pierotofy/OpenSplat`, `mozilla/hubs`); its silence proves
   nothing.
2. **Metadata** — `gh api -X GET search/repositories -f q='repo:<slug>'` for stars, forks, `pushed_at`
   and the SPDX field in one call. **Treat `pushed_at` as the primary signal, not stars** — this plane's
   most important defect is a 4,047★ Apache-2.0 repo that has been dormant 25 months.
3. **Terms — read the file, never the field.** Probe `LICENSE`, `LICENSE.md`, `LICENSE.txt`, `COPYING`,
   `COPYING.md`, `NOTICE` **and the lowercase `license` and `license.txt`** across both `main` and
   `master`. The lowercase variants are not optional: `zju3dv/EasyVolcap` keeps its licence in
   lowercase `license`, and cycle 8 lost two repos to exactly this. If every name 404s, **fetch
   `README.md` as a control**: 200 on the README with 404s on all licence names means the licence is
   genuinely absent (four spec repos this pass), while 404s on both mean your names or branch are
   wrong.
4. **Classify into four buckets, not three.** This plane forced a fourth:
   - **Shippable** — MIT / Apache-2.0 / BSD / MPL-2.0.
   - **Copyleft** — GPL-3.0 / AGPL-3.0 (`LichtFeld-Studio`, `OpenSplat`, `manyfold`, `xeokit-sdk`,
     `freemocap`): usable, but the obligation reaches a hosted service. Decide deliberately.
   - **Research-only** — Gaussian-Splatting License, NVIDIA Source Code License. **Reference reading,
     never a deliverable.**
   - **Permissive-with-a-gate** — PRL v1.0: free for commercial use, but **registration precedes
     use**. Belongs in engagement setup, and no SBOM scan can see it.

**Two things this gate catches that nothing else does.** A *dual* grant that reads as ambiguous and
is not (`o3de/o3de`: Apache-2.0 **or** MIT, licensee elects — stated in `LICENSE.txt`). And a name
that is wrong in a client-facing licence table: **`PixarAnimationStudios/OpenUSD` is not Apache-2.0**,
it is the **Tomorrow Open Source Technology License 1.0**, Apache-2.0 with §6 "Trademarks" replaced.
Permissive in substance — but cite it correctly, because the one thing that loses a procurement review
is a licence table that is confidently wrong.

## Pattern 47 — The podcast ad-and-measurement spine (building the one layer that does not exist)

**When to propose it.** A network, broadcaster or large publisher monetises podcasts with ads and
cannot reconcile what it sold with what was delivered. Strongest in **North America** ($2.9 bn US ad
revenue, IAB/PwC 2025) where the revenue justifies the build.

**Why it is a build and not an integration.** Measured 2026-11-26:
`audio ad insertion server stars:>=20` → **0 repos**. `dynamic ad insertion` → 37 repos, top hit
`leandromoreira/scte-35-scte-104-scte-67` (BSD-3, 35★) which is **documentation about broadcast
markers, last pushed 2021-04-13**. There is no open podcast ad server to adopt, fork or displace.
Every commercial system in the slot is proprietary (Megaphone, Acast, Triton, ART19, Spreaker).
**All the inputs, however, are permissive.**

**The wiring.**

1. **Catalogue + feed truth** — `Podcastindex-org/podcast-namespace` (**CC0-1.0**) as the schema;
   validate emitted feeds with `atelier-socle/podcast-feed-maker` (Apache-2.0) or
   `vpetersson/podcast-rss-generator` (MIT).
2. **Ingest signal, not polling** — subscribe to `Podcastindex-org/podping.cloud` (MIT) so new
   episodes arrive as a push rather than a crawl of the whole catalogue.
3. **Request identification (the part everyone gets wrong)** — classify every media request with
   `opawg/user-agents-v2` (MIT); exclude feed-fetchers and crawlers using
   `opawg/podcast-rss-useragents` (MIT); attribute the serving host via `opawg/podcast-hosts` (MIT).
   Without step 3 the download count is inflated by bots and the number is not defensible.
4. **Counting of record** — self-host `skymethod/op3` (MIT) as the prefix, so the client owns the
   log. Audit the incumbent prefix provider's terms against `opawg/podcast-prefixes` (MIT).
5. **Conform to the written standard** — compute downloads, audience and ad delivery per **IAB Tech
   Lab Podcast Technical Measurement Guidelines v2.3** (server-side log basis; comment closed
   2026-08-19). This is the deliverable the buyer can certify.
6. **Insertion** — the only proprietary component, and therefore where Globant's IP belongs:
   stitching or manifest-level insertion keyed to the identification in step 3, with per-impression
   logs feeding step 5.

**What to say.** "Your measurement and ad logic will be built on a permissive, auditable base you
own — the index, the identification corpus and the prefix are MIT and CC0 — and the only closed part
is the part that is your competitive advantage." **Licence surface: zero copyleft.**

## Pattern 48 — The Article 50 disclosure chain for AI-voiced audio (EMEA first, and it contributes a tag upstream)

**When to propose it.** Any client distributing podcasts into the EU with AI-generated voice,
synthetic reads, cloned presenters or AI-produced ad spots. The duty applies **since 2026-08-02**;
audio counsel reads it as covering cloned voices, synthetic dialogue, podcast ads and AI jingles even
in partly-synthetic productions. Verify the penalty figures against the regulation before quoting
them.

**The gap that makes it a project.** `podcast-namespace` is **CC0-1.0** and has tags for transcripts,
chapters, funding, credits and `alternateEnclosure` — and **no tag for AI-generated or synthetic
content**. The law wants a machine-readable mark; the open distribution format has no field for one.

**The wiring.**

1. **Mark the asset** — C2PA provenance at render time using the permissive chain this KB already
   holds (`contentauth/c2pa-rs`, pass 5). The mark lives in the audio file, so it survives
   re-hosting.
2. **Declare it in the feed** — implement a `podcast:aiDisclosure`-shaped element (per-item: what
   was synthetic — voice, script, music; which segments; whether a licensed voice was used) and
   **take the proposal to the namespace repo in the open**. Public-domain standard, visible
   first-mover position, and the compliance artefact and the contribution are the same work.
3. **Speak it where required** — generate the spoken first-use disclosure with the same TTS path
   that produced the episode, placed per the IAB's 2026 guidance (adjacent to AI segments).
   Guidance, not law — label it as such in the deliverable.
4. **Hold the consent** — a per-voice licence register: consenting performer, scope, territory,
   expiry, revocation. Required in its own right by **Mexico's performer-voice law (effective
   2026-05-15)**; see Pattern 49.
5. **Evidence** — per-episode record (asset hash, disclosure text, voice licence ID, publish
   timestamp) in a form a DPO can file.
6. **Publish through a permissive path** — `podlove/podlove-publisher` (MIT), **not** Castopod or
   microfeed (both AGPL-3.0), if the client is running it as a service.

**What to say.** "Whoever has written the disclosure policy has committed to being able to evidence
it — and we will put the field you need into the open standard so your pipeline stops being bespoke."

## Pattern 49 — The newsroom-to-podcast pipeline (built for LATAM, permissive end to end)

**When to propose it.** A news organisation in Latin America — **news is 32 % of podcast
listening/downloads and 42 % of new episodes** in the region (Triton Digital, 2026 LATAM Audio
Insights), the highest news concentration in this KB — or any publisher with a large text archive
and no audio operation. Audience scale: **135.2 m regional listeners (2023)**, Brazil 51.8 m, Mexico
27.5 m.

**The wiring, and every component is MIT / Apache-2.0 / CC0.**

1. **Source** — the day's published articles from the newsroom platform (pass 20's rows).
2. **Script** — `souzatharsis/podcastfy` (Apache-2.0) for multi-speaker conversational scripting; or
   `MODSetter/SurfSense` (Apache-2.0) when the corpus is confidential and must stay air-gapped.
3. **Voice** — the permissive TTS already in `agents/top.md` Tier 1 (`F5-TTS` MIT, `Kokoro` Apache-2.0,
   `chatterbox` MIT). **If a real presenter's cloned voice is used, Pattern 48 step 4 is mandatory,
   not optional** — Mexico's amended Federal Copyright and Federal Labour Laws (effective
   2026-05-15) govern AI use of a performer's voice, and a cloned presenter is exactly that.
4. **Enrich** — chapters, show notes and pull-quotes with `navotvolkgroundup/sofit` (MIT); social
   cutdowns with `zhouxiaoka/autoclip` (MIT); video cutdowns with `HKUDS/VideoAgent` (MIT).
5. **Chapters into the file** — `dskrad/mp3chaps` (MIT) for ID3 marks; emit Chapters JSON per the
   namespace. (`Mtillmann/chaptertool` is the better tool and is **unlicensed** — use it by hand,
   do not vendor it.)
6. **Publish** — `podlove/podlove-publisher` (MIT), emitting `podcast:transcript` and
   `podcast:chapters` (both now honoured by Apple and Spotify).
7. **Measure** — self-hosted `skymethod/op3` (MIT) + the OPAWG corpora, per Pattern 47 steps 3–5.
8. **Disclose** — Pattern 48 if any voice is synthetic.

**Why it closes.** Budgets here favour self-hosting, which is where AGPL bites hardest (Castopod,
microfeed, Funkwhale, Podverse all AGPL-3.0). This chain is **MIT/Apache/CC0 end to end**: the
client owns the deployment and inherits no network copyleft. That is the sentence that wins the
meeting.

## Pattern 50 — The 20-minute licence gate for any podcast or spoken-audio proposal

Run this **before** any estimate. It has four questions and each one has a measured answer, so it is
a checklist, not a discussion.

1. **Does the client need an app that owns the listener?**
   If yes, stop and choose deliberately. Every **living** open podcast app is GPL-3.0 or AGPL-3.0
   (`AntennaPod` 8,357★, `PodAura` 1,278★, `gpodder`, `PinePods`, `musicpod`, `podverse/*`). The only
   large permissive one, `GetStream/Winds` (BSD-3, 9,078★), **has not been pushed since 2021-10-11**.
   The one living permissive base is **`amugofjava/anytime_podcast_player` (BSD-3-Clause, 627★,
   Flutter)** — smaller and slower-moving, and the alternative is the client publishing their source.
   **Never quote "fork AntennaPod".**

2. **Will it be offered as a hosted, multi-tenant service?**
   Then Castopod, microfeed, Funkwhale and the whole Podverse stack are **out** — AGPL-3.0 reaches
   users over the network. Publishing path becomes `podlove-publisher` (MIT).

3. **Does the engagement touch ad insertion, ad serving or ad measurement?**
   There is **no open implementation** (`audio ad insertion server stars:>=20` → 0). Price it as a
   greenfield build on permissive inputs (Pattern 47), not as an integration. If the proposal assumes
   an open DAI component exists, it is wrong.

4. **Will any voice be synthetic, or any presenter cloned?**
   Then **two separate duties** may apply and they need different artefacts:
   **EU** — Article 50 transparency since 2026-08-02: machine-readable marking + first-use
   disclosure, *per episode*. **Mexico** — performer-voice consent since 2026-05-15: a consent and
   licensing record, *per voice*. A show distributed in both needs both. **APAC: treat labeling as
   probable and unconfirmed** — this pass found no podcast-specific rule for India, Japan or China,
   and pass 21's four regional labeling regimes would plausibly reach an AI host but no source says
   so. Check the national rule before designing the disclosure.

**Deliverable of the gate:** one page naming, for this client, the publishing platform, the app base,
the measurement path and the disclosure obligations — with licences attached. If the answer to Q1 is
"yes, permissive, and alive", there is exactly one row in this KB that satisfies it; make sure the
client knows that before they discover it in a legal review.

## Pass 23 (2026-11-26) — still-image, photo-desk & print-production patterns (51–55)

Every repo named below was verified on 2026-11-26: existence via `git ls-remote`, licence by reading
the actual LICENSE file, stars and last-push via `search/repositories`. Licence notes are not
decoration — in this plane they decide whether the result can be a product.

### Pattern 51 — The ownable archive: natural-language image search with zero copyleft

**Problem.** A publisher, broadcaster or heritage client has 10k–10M images with thin metadata and
wants "find me the shot of the minister in the red coat". The attractive platforms (Immich 120,170★,
PhotoPrism 40,481★) are **AGPL-3.0**, so the archive could never be offered as a product or a
multi-tenant service without disclosing the source.

**Stack — permissive end to end.**

| Role | Component | License |
|---|---|---|
| Image serving / tiling | [cantaloupe-project/cantaloupe](https://github.com/cantaloupe-project/cantaloupe) | **MIT** |
| Deep-zoom viewer | [openseadragon/openseadragon](https://github.com/openseadragon/openseadragon) | BSD-3-Clause |
| Multi-image compare workspace | [ProjectMirador/mirador](https://github.com/ProjectMirador/mirador) | Apache-2.0 |
| Embeddings (text↔image) | [mlfoundations/open_clip](https://github.com/mlfoundations/open_clip) | **MIT** |
| Vector index | [qdrant/qdrant](https://github.com/qdrant/qdrant) or [facebookresearch/faiss](https://github.com/facebookresearch/faiss) | Apache-2.0 / MIT |
| Derivative generation | [lovell/sharp](https://github.com/lovell/sharp) or [imgproxy/imgproxy](https://github.com/imgproxy/imgproxy) | Apache-2.0 |
| Metadata read/write | [exiftool/exiftool](https://github.com/exiftool/exiftool) | Artistic-1.0-Perl **OR** GPL-1.0+ |
| Near-duplicate detection | [idealo/imagededup](https://github.com/idealo/imagededup) | Apache-2.0 |

**Wiring.** Masters stay on object storage. Cantaloupe serves IIIF Image API URLs from the masters,
so no derivative pyramid is pre-baked and OpenSeadragon gets tiles on demand. On ingest: `exiftool`
extracts IPTC/EXIF/XMP into the catalogue row; `imagededup` PHash flags near-duplicates against the
existing index before anything is stored; `open_clip` embeds the image; the vector goes to Qdrant
with the catalogue id as payload. A query embeds the text with the **same** `open_clip` checkpoint
and does an ANN search. `sharp` or `imgproxy` handles web derivatives at the edge.

**Why it holds together.** The licence column has no copyleft in it — and for `exiftool`, **take the
Artistic option** (its README grants "the same terms as Perl itself", so the GPL-3.0 text in the
repo is one of two choices, not the only one; see the method notes in `agents/top.md` pass 23).

**The two traps.** (1) **Pin the `open_clip` checkpoint and store its identifier on every vector.**
Changing checkpoints silently invalidates the whole index, and a mixed index degrades without
erroring. (2) **`openai/CLIP` is reference-only and 8 months idle** — build on `open_clip`.

### Pattern 52 — The alt-text review loop (the sellable gap, not the model)

**Problem.** Accessibility obligations exist in every region; a client has 400,000 images with no
alt text and a photo desk that cannot write 400,000 captions. The model is free; the accountability
is not. The entire open GitHub field for this workflow is **one repo with one star**.

**Stack.**

| Role | Component | License |
|---|---|---|
| Caption drafting (self-hosted) | [haotian-liu/LLaVA](https://github.com/haotian-liu/LLaVA) (Apache-2.0, **pin it — dormant since 2024-08-12**) or any hosted VLM | Apache-2.0 |
| CMS-side plugin precedent | Drupal `ai_image_alt_text` / `aidmi` (drupal.org), [soderlind/ai-alt-text](https://github.com/soderlind/ai-alt-text) | GPL-2.0-or-later |
| Local inference for embargoed images | Ollama path in `soderlind/ai-alt-text` | GPL-2.0-or-later |
| Metadata persistence | [exiftool/exiftool](https://github.com/exiftool/exiftool) → IPTC `AltTextAccessibility` | Artistic **OR** GPL |
| Bulk back-catalogue pass | [lovell/sharp](https://github.com/lovell/sharp) for thumbnails + queue | Apache-2.0 |

**Wiring, and the whole value is in steps 2–4.**

1. **Classify first, draft second.** Route each image to *decorative* / *informative* /
   *complex*. The ~600-image study cited in `intel/trends.md` pass 23 found AI drafts fine as a
   first draft for the photo column and **actively risky for decorative images** — a decorative
   image needs `alt=""`, and a model will cheerfully describe it instead. **This classification step
   is the difference between a compliance improvement and a compliance regression.**
2. **Draft into a queue, never into the live field.** The draft lands in a review state with the
   model id and prompt template recorded.
3. **One-keystroke editor acceptance**, with edit-distance between draft and accepted text logged.
   That metric is the client's evidence the loop is working, and the input to deciding which image
   classes can later be auto-accepted.
4. **Write the accepted text to IPTC with `exiftool`**, so the caption travels with the file into
   every downstream system rather than living only in the CMS database.

**Why this is the proposal.** Steps 1, 3 and 4 are where every open implementation stops. Drupal's
module gets closest — it ships a customisable prompt template, multilingual output, bulk
back-processing and explicit human-in-the-loop verification — and it is a module, not a workflow.
**Sell the loop and the audit trail; the model is a commodity line item.**

### Pattern 53 — Ingest-time provenance gate (and the one honest caveat)

**Problem.** A newsroom must satisfy, depending on market: China's implicit-metadata label (binding
since 2025-09-01), the EU's Article 50 transparency duty, AP/dpa-style editorial prohibitions on
synthetic news imagery, and Mexico's consent duty. Nothing open does this.

**Stack.**

| Role | Component | License |
|---|---|---|
| Sign / verify Content Credentials | [contentauth/c2patool](https://github.com/contentauth/c2patool) | Apache-2.0 **OR** MIT |
| Embed in a service | [contentauth/c2pa-rs](https://github.com/contentauth/c2pa-rs) | MIT **OR** Apache-2.0 |
| EXIF/IPTC/XMP read-write | [exiftool/exiftool](https://github.com/exiftool/exiftool) | Artistic **OR** GPL |
| Perceptual hash for re-use detection | [JohannesBuchner/imagehash](https://github.com/JohannesBuchner/imagehash) | BSD-2-Clause |
| Pixel normalisation | [libvips/libvips](https://github.com/libvips/libvips) via [lovell/sharp](https://github.com/lovell/sharp) | LGPL-2.1 / Apache-2.0 |

**Wiring.** Every image entering the DAM passes one gate: `c2patool` reads any existing manifest and
records signer, capture claims and edit assertions; `exiftool` extracts IPTC credit, source and
usage terms; `imagehash` computes a pHash and checks it against the archive to catch re-submission
of a known asset under a new credit. The gate writes a **single provenance row per asset** —
signer, hash, declared AI involvement, consent reference, market-policy verdict — and **re-signs**
with the organisation's own certificate on publish, so downstream consumers can verify the
publisher's assertion even when the camera made none.

**Make the regime a policy object, not a branch.** One writer, four configurations: China (explicit
visible label **and** implicit metadata label, verification on ingest); EU (Article 50 label, with
the effective date as configuration — the sources disagree between 2026-08-02 and 2026-12-02);
US (materiality determination + editorial sign-off; no statute); Mexico (consent record keyed to the
person depicted, not a label on the file).

**The caveat to put in the proposal in writing.** `wiltodelta/remove-ai-watermarks` is
**Apache-2.0 with 6,530 stars** — roughly ten times the entire open C2PA implementation (629 stars).
**Metadata does not survive a determined adversary, and claiming otherwise will not survive the
first hostile question.** Anchor the argument in capture-side hardware signatures (Leica's secure
chip, Nikon Authenticity Service, Sony firmware) plus **verification at ingest and at publish**,
and present the gate as chain-of-custody for assets the organisation controls — which is a real and
defensible claim — rather than as tamper-proofing of the open internet.

### Pattern 54 — Self-hosted image CDN that replaces a SaaS line item

**Problem.** The client pays per-transform to an image SaaS and wants the spend and the data back,
without rewriting every `<img>` URL in a 15-year-old CMS.

**Stack.**

| Role | Component | License | Note |
|---|---|---|---|
| Migration-compatible server | [cshum/imagor](https://github.com/cshum/imagor) | Apache-2.0 | **Thumbor-compatible URL API** |
| Or: signed-URL server | [imgproxy/imgproxy](https://github.com/imgproxy/imgproxy) | Apache-2.0 | OSS core; a paid Pro tier exists |
| Or: Python-extensible | [thumbor/thumbor](https://github.com/thumbor/thumbor) | MIT | Widest transformation set, custom detectors |
| Engine | [libvips/libvips](https://github.com/libvips/libvips) | LGPL-2.1 | Shared by all three |
| Modern formats | [libjxl/libjxl](https://github.com/libjxl/libjxl), [AOMediaCodec/libavif](https://github.com/AOMediaCodec/libavif), [webmproject/libwebp](https://github.com/webmproject/libwebp) | BSD | Negotiate on `Accept` |
| Baseline JPEG quality | [mozilla/mozjpeg](https://github.com/mozilla/mozjpeg) | IJG + BSD-3-Clause | **Dormant ~17 months**; still best-in-class |

**Wiring.** Put the server behind the existing CDN with a long `Cache-Control` and an origin pull
from object storage; derivatives are computed once per URL and then served from cache, so steady-state
CPU is near zero. Content-negotiate AVIF → WebP → JPEG on `Accept`.

**Choose by the migration cost, not the benchmark.** If the client is already on thumbor, **imagor
is a routing change** because the URL contract matches. If starting fresh, imgproxy's signed URLs
prevent the open-proxy resize-bomb problem by construction. Treat **all** published benchmarks here
as vendor-run: imgproxy's own benchmark reports it more than twice as fast as thumbor and imagor on
Intel Xeon, while imagor's own benchmark (updated May 2026) reports imagor consistently faster than
thumbor and competitive with imgproxy. **Both projects have a stake in their own numbers.** All
three run the same libvips engine, so measure on the client's own image mix before choosing.

**Licence note that actually matters here.** `imazen/imageflow` is the fast tempting alternative and
is **AGPL-3.0** — a hosted image service built on it is disclosable. It sells a commercial licence;
if it is in scope, that is a procurement conversation, not a technical one.

### Pattern 55 — Print production with the licence boundary drawn explicitly

**Problem.** A publisher still prints — a magazine, a catalogue, a newspaper section — and wants
AI-assisted page production. This is the half of the plane that **cannot** become a product, and
the engagement has to be shaped accordingly.

**Stack.**

| Role | Component | License | Productisable? |
|---|---|---|---|
| Page layout | [scribusproject/scribus](https://github.com/scribusproject/scribus) | GPL-2.0-or-later | **No** — deploy and script only |
| RIP / PS+PDF interpretation | [ArtifexSoftware/ghostpdl](https://github.com/ArtifexSoftware/ghostpdl) | **AGPL-3.0** (composite, per-directory) | **No** — commercial licence sold |
| ICC colour management | [mm2/Little-CMS](https://github.com/mm2/Little-CMS) | **MIT** | **Yes** |
| PDF/A–PDF/X validation | [veraPDF/veraPDF-library](https://github.com/veraPDF/veraPDF-library) | GPL-3.0+ **OR MPL-2.0+** | **Yes, via MPL** |
| PDF structural repair | [qpdf/qpdf](https://github.com/qpdf/qpdf) | Apache-2.0 | **Yes** |
| Imposition / page ops | [pdfcpu/pdfcpu](https://github.com/pdfcpu/pdfcpu) | Apache-2.0 | **Yes** |
| Preflight in-browser | [mozilla/pdf.js](https://github.com/mozilla/pdf.js) | Apache-2.0 | **Yes** |
| Font QA / subsetting | [fonttools/fonttools](https://github.com/fonttools/fonttools), [googlefonts/fontbakery](https://github.com/googlefonts/fontbakery) | MIT / Apache-2.0 | **Yes** |
| Retouch automation | [GNOME/gimp](https://github.com/GNOME/gimp) | GPL **+ plug-in exemption** | **Yes, as a plug-in** |
| RAW developing | [darktable-org/darktable](https://github.com/darktable-org/darktable) | GPL-3.0 | **No** — deploy, script via Lua |

**Wiring.** Scribus runs on the design desk and is driven by its Python scripting API for templated
pages (catalogue, listings, programme). The AI-assisted parts sit **outside** Scribus, in the
permissive column: `fonttools` subsets fonts to what each page actually uses; `Little-CMS` applies
the press ICC profile; Scribus exports **PDF/X-3 or PDF/X-4 with the press condition embedded**;
`veraPDF` validates against the standard **under its MPL-2.0 option** so the preflight service can
ship alongside proprietary code; `qpdf` and `pdfcpu` repair and impose; `pdf.js` renders the proof
for in-browser sign-off.

**The two decisions to make in week one, not at delivery.**

1. **Ghostscript.** It is how a page becomes ink, Scribus needs it for EPS/PS import and print
   preview, it is **AGPL-3.0 with a commercial licence sold alongside**, and it has **310 stars.**
   A 310-star AGPL project is a single point of failure with a procurement question attached. Decide
   explicitly: deploy under AGPL (internal use, no disclosure trigger for staff tooling), or buy the
   Artifex licence.
2. **GIMP's plug-in exemption is a genuine opening.** Its LICENSE explicitly states that
   arbitrarily-licensed programs such as GIMP plug-ins do **not** automatically assume the GPL merely
   by invoking (or being invoked by) GIMP procedures. **So "automate the retouching desk with a
   proprietary plug-in" is contemplated and permitted by the project** — one of very few ways to
   build closed value on a GPL application in this plane. An SPDX field reading `GPL-3.0` tells you
   the opposite; read the file.

**And one dependency to read before promising colour fidelity:** `Little-CMS` is MIT, maintained,
load-bearing for Scribus, GIMP and Krita — and has **764 stars.** If the engagement's value
proposition is "the printed piece matches the screen", that promise rests on it.

## Owned-channel & audience-relationship recipes — added 2026-11-26 (pass 24)

Every repo named below appears with its verified licence, star count and last-push date in
`repos/foundations.md` or `verticals/solutions.md` (pass 24). The plane's agent layer is a measured
near-zero, so **four of these five patterns are integrations of healthy permissive infrastructure, not
adoptions of an agent.**

**The licence rule for this whole plane, stated once:** the list manager is copyleft (listmonk AGPL,
Mautic GPLv3+), so it runs **behind a service boundary** the client's proprietary code calls over
HTTP. Everything the client should own and differentiate — Postal, Novu, Unomi, Coral, c15t,
react-email/MJML, parsedmarc — is MIT, Apache-2.0 or MPL-2.0.

---

### Pattern 24.1 — The reachable-audience spine (run this before anything else in the plane)

**Why:** Piano's diagnostic question — *what percentage of your audience can you reach without a
referral source?* — is the business case for this entire plane, and most clients cannot answer it.
Google Discover referrals fell **21% YoY**, and exposed publishers report **50–90%** revenue declines.
This pattern produces the number and then fixes it.

```
[Web / app / player events]
        |
        v
[snowplow/snowplow (Apache-2.0)]  or  [jitsucom/jitsu (MIT)]   <- first-party event collection
        |
        v
[apache/unomi (Apache-2.0, 382*)]        <- THE PROFILE STORE: identity stitching + segments
        |                                    + consent state as a first-class field
        |
        +--> [ory/kratos (Apache-2.0)]    <- registration / login wall: anonymous -> known
        |
        +--> [novuhq/novu (MIT, 40,432*)] <- ONE orchestration API for every owned channel
        |         |
        |         +--> email  -> [knadh/listmonk (AGPL, service boundary)] or [mettle/sendportal (MIT)]
        |         |                    |
        |         |                    v
        |         |            [postalserver/postal (MIT)] <- owned MTA, per-domain DKIM, webhooks
        |         |
        |         +--> web push -> [web-push-libs/web-push (MPL-2.0)] + [mozilla-services/autopush-rs]
        |         |
        |         +--> in-app / breaking -> [binwiederhier/ntfy (Apache-2.0)]
        |
        +--> [apache/druid | apache/pinot (Apache-2.0)]  <- the Pattern 10 reporting path
```

**What makes this different from Pattern 10 (first-party audience *graph*):** Pattern 10 observes.
This one **activates** — and the join between them is Unomi's profile, where the consent record and
the reachable-channel list live on the same object. Run Pattern 10 first if it is not already in place.

**The deliverable that justifies the engagement:** a single number per client —
*reachable audience / total audience* — broken down by channel and by consent basis, refreshed daily.
No client currently has it.

**Licence posture:** Unomi, Kratos, Novu, Postal, ntfy, web-push, Snowplow, Druid = all permissive and
in the client's build. Only the list manager is copyleft, and only if listmonk is chosen over
SendPortal. **Do not use `rudderlabs/rudder-server`** (Elastic License 2.0) however many listicles
recommend it.

---

### Pattern 24.2 — The newsroom comment desk with an open moderation assistant (the smallest unbuilt product in this plane)

**Why:** Coral is the only commenting platform ever built for newsrooms, it is **Apache-2.0**, it was
pushed today, and it ships AI-assisted moderation inside the product. `detoxify` is the open toxicity
model. **Nothing wires an agent between them** — and comment moderation is a liability the publisher
carries per published comment, which is exactly why the generic alternative (Discourse, 48,117★) is
24× better resourced and 24× less fit.

```
[coralproject/talk (Apache-2.0, 2,005*)]      <- per-stream pre/post moderation, queues,
        |                                        banned + suspect word lists, publisher owns the data
        |  webhook / queue
        v
[moderation agent  <-- THE BUILD]
        |   +-- [unitaryai/detoxify (Apache-2.0, 1,320*)]  <- toxicity scores, self-hosted
        |   +-- LLM pass for context the classifier misses (sarcasm, local slurs, dogwhistles)
        |   +-- policy-as-code: the client's community standards, versioned
        v
[decision + REASON + model version]  ---> back to Coral's queue (approve / reject / escalate)
        |
        v
[append-only moderation log]  <- the evidence trail, per decision
```

**Why the log is the product, not the classifier:** a moderation decision a publisher cannot explain
is a liability in every region this KB covers. Record input, score, model version, policy version,
decision and the human who confirmed it. This is the same "we removed it → we told the regulator we
removed it" structure as Pattern 26, applied to comments instead of content.

**Both components are Apache-2.0**, so the agent, the policy and the log are all client-owned IP.
LATAM note: Brazil's Decrees 12,975 and 12,976 added content-moderation, reporting and transparency
duties for intermediaries **effective 20 July 2026** — the log is how that duty is discharged.

---

### Pattern 24.3 — Deliverability as an evidence loop (the agent nobody has built, on a substrate that is ready)

**Why:** the owned channel is only owned if it arrives. Gmail retired its High/Medium/Low reputation
scores in Postmaster Tools v2 for a compliance checklist and a deliverability verdict; Apple MPP and
now Gmail's auto-opening Gemini summaries have made the **open rate unusable** (opens inflate, clicks
fall). The metrics that survive are **DMARC evidence, clicks and conversions** — and there is no open
agent for any of it, over a permissive substrate that is pushed weekly.

```
[DMARC aggregate + forensic reports from every receiver]
        |
        v
[domainaware/parsedmarc (Apache-2.0, 1,321*)] --> OpenSearch / Elasticsearch
        |
[postalserver/postal (MIT)] bounce + click webhooks -----+
        |                                                |
        v                                                v
[deliverability ops agent  <-- THE BUILD]
        |   reads: SPF/DKIM/DMARC pass rates by receiver and sending domain,
        |          bounce classes, complaint rates, click/conversion by segment
        |   does:  flags a receiver whose alignment dropped; proposes list-hygiene
        |          actions; quarantines a bad segment BEFORE the 2M-recipient send;
        |          never sends - it files a recommendation
        v
[axllent/mailpit (MIT)] <- the template + headers proved in CI before any real send
```

**Measure what still exists, and say so to the client in these words:** stop reporting opens, report
**inbox placement evidence (DMARC alignment), clicks, conversions and replies**. A client still
running on open rate is measuring Gmail's summariser.

**Caveat to carry into the room:** the AI-summary findings above are vendor-blog sourced. No
independent 2026 dataset on publisher engagement under AI inbox summaries was found — the direction is
well attested, the magnitudes are not.

---

### Pattern 24.4 — Re-configurable consent, because the rules are mid-change (the EMEA-first build)

**Why:** every date in this layer is **already past** — TCF v2.3 mandatory since **1 March 2026**,
TCF v2.4 specs published **23 July 2026** with a website deadline of **23 October 2026** — while the
EU is simultaneously relitigating consent itself through the Digital Omnibus (EMMA, ENPA, EPC and NME
objected to Articles 88a/88b; browser-level cookie preferences were dropped in October 2026; adoption
of the wider package is **not expected before 2028**). A consent layer built to be *correct today* is
guaranteed to be wrong.

```
[c15t/c15t (Apache-2.0, 2,045*)]            <- headless consent UI, client-owned and themeable
        |  +-- [@c15t/iab]                      <- TC-string generation
        |  +-- [InteractiveAdvertisingBureau/iabtcf-es (Apache-2.0, 156*)]  <- official encode/decode
        v
[CONSENT RECORD as a typed object in apache/unomi (Apache-2.0)]
        |   fields: purpose, legal basis (consent | legitimate interest), jurisdiction,
        |           TCF version + TC string, GPP section, timestamp, UI version shown
        v
+-- activation gate: NO channel send and NO ad call without a matching basis
+-- [Prebid.js] (already in this KB, pass 2) reads the string
+-- audit export: what was asked, when, in which words, under which spec version
```

**The two things to say in week one, before anyone builds:**

1. **No open-source CMP is IAB-registered.** `c15t` and `iabtcf-es` give you a valid TC string and a
   consent UI — **not standing in the framework.** If the client needs TCF registration, that is a
   procurement line item, not a build.
2. **The IAB GPP repo is a specification under CC-BY-3.0, not software** — and the IAB Tech Lab IPR
   policy can override that licence for members. Read it as a document, implement it yourself.

**Store the legal basis, not just the boolean.** The European Publishers Council is pushing for
low-risk first-party processing to run on **legitimate interest** instead of consent. A record that
only says `true`/`false` cannot survive that change; one with a `legal_basis` field can.

**Do not use `ConsentOS/consentos`** (Elastic License 2.0) despite its feature list.

---

### Pattern 24.5 — The editorial digest with the agent kept on the draft side of the line

**Why:** the agent layer in this plane is 915★ and **16 months dead**, with a tail of 0–17★ hobby
repos, four of which have no licence. So do not adopt one — compose the two or three usable pieces and
keep the LLM strictly upstream of the send decision.

```
[CMS / wire output for the day]  (Superdesk, Ghost, ninjs — all already in this KB)
        |
        v
[curation step: rank + cluster + section]
        |   reference implementations worth reading, NOT depending on:
        |     - [elbruno/weekly-ai-news-digest] (MIT, 11*) - runs as a GitHub Agentic Workflow, no server
        |     - [p55d2k/thegist] (MIT, 0*)                 - RSS -> themed sections -> digest
        |   DO NOT depend on [finaldie/auto-news] (MIT, 915*, dead since 2025-07-19)
        v
[DRAFT in the newsroom's own tooling]  <-- HUMAN EDITOR APPROVES HERE. Hard gate.
        |
        v
[resend/react-email (MIT) | mjmlio/mjml (MIT) | maizzle/framework (MIT)]  <- render
        |
        v
[axllent/mailpit (MIT)]   <- prove it in CI: headers, alt text, dark mode, Outlook
        |
        v
[knadh/listmonk (AGPL, behind an API) | mettle/sendportal (MIT)]  --> [postalserver/postal (MIT)]
        |
        v
[Pattern 24.3's evidence loop]
```

**The gate is the pattern.** Everything above the human approval step is a draft; nothing below it is
generated. That boundary is what makes this shippable under the EU AI Act Art. 50 labelling regime,
Brazil's TSE Resolution 23,755/2026 on synthetic electoral content, and the APAC labelling duties in
`intel/market.md` — because **no generated text reaches a reader unapproved**, so the question of
labelling a generated newsletter never arises.

**Note the inversion worth pricing:** the agent is the cheap, replaceable part (reference
implementations have 11 and 0 stars and you will write your own in days). The expensive, durable parts
are the **render → CI-proof → owned-MTA → evidence** chain, and all of it is MIT.

**One thing not to automate:** send-time and frequency decisions on a list that is the client's last
unintermediated relationship with its audience. Pattern 24.3's agent *files recommendations*; a human
presses send.

---

## Traffic, sales-order-to-air & billing recipes — added 2026-11-26 (pass 25)

Every repo named below appears with its verified licence, stars and last-push date in
`repos/foundations.md` or `verticals/solutions.md` (pass 25). **Four of these five patterns build
something that does not exist in open source at all** — two of the defining searches
(`broadcast as-run reconciliation`, `spot booking advertising`) return a **literal empty set** — so
they are specifications for client-owned work on top of healthy copyleft platforms, not adoptions.

**The licence rule for this whole plane, stated once.** Every platform worth starting from is
copyleft: **Nebula GPL-3.0**, **9eye AGPL-3.0**, **AzuraCast / LibreTime AGPL-3.0**, **Rivendell
GPL-2.0**. So they run **unmodified, as separate processes, behind a service boundary** that the
client's code calls over HTTP or exchanges files with. Keep client modifications in **separate
services, never patches**, or the distribution question arrives at go-live. Everything the client
should own and differentiate is permissive: **Kill Bill (Apache-2.0)**, **OpenMeter (Apache-2.0)**,
**Aureus ERP (MIT)**, **folderplayout (MIT)**, and the reconciliation and policy services you write.

---

### Pattern 25.1 — The as-run reconciliation service (the empty set, and therefore the product)

**Why:** `broadcast as-run reconciliation` returns **zero GitHub repositories**. 9eye lists *"as-run
and reconciliation"* as a roadmap item. The only as-run artefact in existence —
[alochbaum/CheckAsRun](https://github.com/alochbaum/CheckAsRun) — is **0★, unlicensed, has no README
and has been dead since 2016-04-21**. Meanwhile this is the function that decides whether the
broadcaster gets paid.

**What it is:** a service that ingests two things and emits three.

- **In (a):** the **intended** log — the approved playlist for the broadcast day, exported from
  [nebulabroadcast/nebula](https://github.com/nebulabroadcast/nebula) (GPL-3.0) or
  [9eye9/9eye](https://github.com/9eye9/9eye) (AGPL-3.0), or from the incumbent (WideOrbit, Marketron,
  LandmarkOSI).
- **In (b):** the **as-run** log the playout system actually produced — CasparCG via
  [mint-dewit/folderplayout](https://github.com/mint-dewit/folderplayout) (**MIT**), or the station's
  proprietary automation.
- **Out:** every spot classified **AIRED AS BOOKED** / **AIRED WRONG** (late, short, wrong break,
  wrong rotation position, back-to-back with a competitor) / **NOT AIRED** (pre-empted), each with the
  frame-accurate evidence attached.

**Wire it:**

```
Nebula or 9eye (copyleft, unmodified)        incumbent traffic (WO / Marketron / LandmarkOSI)
        │ intended log (export)                      │ intended log (file/API)
        └──────────────┬──────────────────────────────┘
                       ▼
        reconciliation service  ← CLIENT-OWNED, any licence
         (frame-accurate matching + tolerance policy)
                       ▲
        as-run log ────┘  (CasparCG via folderplayout MIT, or proprietary automation)
                       │
        ┌──────────────┴───────────────┐
        ▼                              ▼
  Kill Bill (Apache-2.0)        OpenMeter (Apache-2.0)
  invoice lines + credits       delivered impressions
                                (addressable / CTV breaks)
```

**Why it is defensible work rather than a commodity:** the matching rules *are* commercial policy —
how late is still "aired", what counts as an equivalent position, which discrepancies are billable.
That judgment is the client's, which is exactly why no open-source project has it and why it should be
the client's IP. **Frame accuracy is not optional**: 9eye stores every length and time as an integer
number of frames across 23.976–59.94 fps with drop-frame timecode and broadcast days that cross
midnight — copy that model, because a reconciliation service that stores seconds will disagree with
the log it is auditing.

**Start here in every region.** In EMEA, point the same service at a compliance question instead of an
invoice (what was transmitted, in which territory and language, with which disclosures) and the
billing half is not needed at all.

---

### Pattern 25.2 — The makegood engine, with 9eye's permission model copied verbatim

**Why:** `makegood` has **zero hits** in this entire KB and **zero inside 9eye's own working tree**;
`pre-empt`, `affidavit` and `post-log` are also zero. Yet every broadcaster that pre-empts a spot
(breaking news, a sports overrun) **owes a replacement of equivalent value**, and the incumbents'
agentic launches (Fox AdStudio, NBCU/FreeWheel, Magnite/ITN) are all **proprietary**.

**What it is:** an obligation ledger plus a constrained search.

1. Pattern 25.1 emits **NOT AIRED** → create an **obligation** (what was owed: audience, daypart,
   value).
2. Search candidate future breaks with room, honouring the same placement rules a traffic system
   enforces (position order, separation, "never back to back", airing limits — 9eye implements these
   and reports unfittable spots **with the reason**, which is the behaviour to copy).
3. Propose a **makegood**; hold it for advertiser approval; on approval, write the credit in
   **[killbill/killbill](https://github.com/killbill/killbill)** (Apache-2.0) and the placement back
   into Nebula or 9eye.

**This is the one genuinely agent-shaped job in the plane** — constrained search over inventory with a
commercial objective — **and the approval must be human.** Copy 9eye's design rather than inventing
one: a permission table of **part × action** (Read · Change · Create and delete · Approve · Export)
with each cell *Allowed* / *Ask first* / *Off*; **agents and tokens can only ever be narrower than the
person who issued them**; every change carries a **preview and an undo**, lands in an **audit log**,
and waits in a **"Waiting for you"** queue. An agent may **propose** a makegood; it must never
**book** one.

---

### Pattern 25.3 — BXF without redistributing the schema (the licence gate — run it before estimating)

**Why:** BXF (SMPTE ST 2021) is the XML interchange between traffic, playout and automation, so it is
the integration a traffic engagement must build. And it is a **licence event disguised as a
download**:

- [SMPTE/st2021-4](https://github.com/SMPTE/st2021-4) — the official schema documentation — carries a
  269-byte `LICENSE.md` reading **"All rights reserved. No part of this material may be reproduced, by
  any means whatsoever, without the prior written permission of the Society of Motion Picture and
  Television Engineers."** The GitHub API reports `NOASSERTION`.
- [JoeldelPilar/bxf-manager](https://github.com/JoeldelPilar/bxf-manager) — the only BXF tool on
  GitHub — has **no licence file at all** (11 filenames × 2 branches probed; control `README.md`
  returns 200, so the absence is real). No grant ⇒ all rights reserved.

**The gate, in order:**

1. **Before estimating**, confirm the client holds a **SMPTE entitlement** for ST 2021-4. If not, that
   is a procurement task with a lead time, not a development task.
2. **Do not vendor the `.xsd`** into the client repository, a Docker image, or a public artefact.
3. Fetch it at build time from the member channel into a **gitignored** path under the client's own
   entitlement; generate bindings; **ship only generated code**, with the client's counsel signing off
   on whether generated bindings are a derivative of the schema.
4. Write the entitlement and the counsel sign-off into the proposal as **assumptions**.

**Falsifiable prediction, recorded for a later pass to check:** any proposal that estimates "BXF
export" as a two-week task without naming the schema entitlement will discover the licence at
integration time, and the schedule slip will be procurement, not engineering.

**Note the new licence category this establishes** (see `intel/trends.md` pass 25): after CPT and
MedDRA, which are *taxed*, BXF is the first artefact in this KB that is **free of charge, published
openly on GitHub, and still not redistributable** — which is easier to get wrong, because nothing
about fetching a public file feels like a licence decision. No SPDX field, badge or source-tree SBOM
scan detects it.

---

### Pattern 25.4 — The political-spot compliance gate on the booking screen (LATAM-first, and it has a hard date)

**Why:** the obligation attaches to an object the **traffic system** owns — a spot that is booked,
logged, aired and invoiced — and the broadcaster **does not control the creative**. Brazil's electoral
court approved rules for the **October 2026 elections**: AI-altered content changing a candidate's
image, voice or statements is **banned in the 72 hours before a vote and 24 hours after**, and any
campaign ad using AI must carry a **clear and visible notice**; free electoral advertising on radio and
TV runs **until 1 October**. A broadcaster carrying mandatory free electoral advertising can control
only **when a spot may be placed** and **what it can prove afterwards**.

**What it is:** a **policy object per jurisdiction**, attached to the campaign/spot, holding

- the **prohibited windows** (Brazil: −72 h / +24 h around a vote),
- the **notice requirement** (present? wording? placement?),
- the **evidence to retain**, and for how long,
- the **provenance rule** — *preserve, never strip*, C2PA metadata and signatures through editing and
  publishing (explicit broadcast-counsel advice in the US).

…enforced at **two points only**: it **blocks placement** inside a prohibited window at booking time,
and it **emits the evidence record** from the log afterwards.

**Build it on:** the campaign/spot model in [9eye9/9eye](https://github.com/9eye9/9eye) (AGPL — behind
a service boundary) or [nebulabroadcast/nebula](https://github.com/nebulabroadcast/nebula) (GPL-3.0),
with the policy object and evidence store as the **client-owned permissive** part, and Pattern 25.1's
reconciliation service supplying the proof.

**It must be configurable, not correct** — the whole point is that the rule differs by jurisdiction:

| Region | Why one compliance mode fails |
|---|---|
| **LATAM** | Brazil −72 h/+24 h + visible notice (**October 2026, fixed date**); Mexico's proposed labelling + INE takedown powers; Chile, Colombia, Brazil's AI bill all at different speeds. |
| **North America** | **31 states** regulate AI in political ads and **only ~half** require disclosure, while federal **reasonable-access** rules mean a station cannot censor a federal candidate's ad — so the policy varies **per station and per state** and can contradict itself on one spot. |
| **APAC** | A patchwork of three approaches: Korea's "clearly recognise" labelling (2026 effectively a pilot year), India's February 2026 IT-rules amendment, China's layered rules, Vietnam's decree. |
| **EMEA** | EU AI Act **Article 50** machine-readable marking, pre-August cohort due **2 December**, disclosure no later than first exposure. |

**This is the second plane in which APAC's sellable asset turns out to be a policy engine rather than
a compliance setting** (pass 5 found the same for rights reservation) — which makes it a regional
pattern worth naming, not a coincidence.

---

### Pattern 25.5 — Resurrect the plane's anchor, correctly: Nebula, not the dead slug

**Why:** this KB told a prior reader that Nebula was **archived and dead**. It recorded
`immstudios/nebula` (20★, last push 2023-04-26). The project moved org and is alive:
**[nebulabroadcast/nebula](https://github.com/nebulabroadcast/nebula)**, **GPL-3.0, 332★, 38 forks,
pushed 2026-11-23**, *"since 2012 … used by TV and production companies worldwide"*. It is the **only**
open system that does linear **planning + scheduling + playout + MAM** together, which makes it the
starting point for this entire plane.

**The stack:**

| Piece | Repo | Licence | Take it? |
|---|---|---|---|
| Server (core) | [nebulabroadcast/nebula](https://github.com/nebulabroadcast/nebula) | GPL-3.0 | **Yes** — unmodified, behind a service boundary, integrate over its API. |
| Worker | [nebulabroadcast/nebula-worker](https://github.com/nebulabroadcast/nebula-worker) | GPL-3.0 | **Yes** — required for real media processing, not optional. |
| Web UI | in the server repo | GPL-3.0 | **Yes** — the README states it now has full feature parity with the desktop client. |
| Desktop client | [nebulabroadcast/firefly](https://github.com/nebulabroadcast/firefly) | GPL-3.0 | **Only** against a hard desktop requirement — **it is being phased out** per its own README. |
| Tutorial / starter files | [nebulabroadcast/nebula-tutorial](https://github.com/nebulabroadcast/nebula-tutorial) | **NONE** | **Read, do not copy.** No licence file (11 names × 2 branches; control README = 200 ⇒ real absence). Do not lift its compose file or settings into a client repo. |

**Then add the permissive layer beside it, over the API:** Pattern 25.1's reconciliation service,
Pattern 25.2's makegood engine with 9eye's permission table, Pattern 25.4's policy object, and
**[killbill/killbill](https://github.com/killbill/killbill)** (Apache-2.0) or
**[aureuserp/aureuserp](https://github.com/aureuserp/aureuserp)** (MIT) for invoicing.

**And the sentence to say out loud in the first meeting:** *"the open-source platform will schedule
your channel; it will not sell your inventory, prove the spot aired, or raise the invoice — that part
we build, and you own it."* The measured basis for that sentence is in `verticals/solutions.md`
pass 25. **Never promise a broadcaster an all-open-source order-to-cash stack.**

---

### Pattern 25.6 — The 20-minute gate for any broadcast traffic proposal

Run these six checks before writing an estimate. Each one has cost somebody a schedule slip.

1. **Is "traffic" the media meaning?** In this plane the word is the most contaminated term in the KB:
   `broadcast traffic` → 163 GitHub results, **zero relevant**; `radio traffic` → 246, **zero**;
   `rate card` → **2,013**, **zero**. Searching it naively returns satellite ship detection and ADS-B
   decoders. **Read the results, never the total.**
2. **Which step of the gradient is actually in scope?** Plan what airs (**healthy** — Nebula, 14 years
   in production) / book inventory (**2★, 7 days old** — 9eye) / prove-and-bill (**empty set**). The
   third is a build, and pricing it as an integration is the classic error here.
3. **Does the client hold a SMPTE entitlement for ST 2021-4?** If BXF is in scope and the answer is
   no, see Pattern 25.3 — procurement lead time, not engineering.
4. **Is the incumbent staying?** If WideOrbit, Marketron or LandmarkOSI is staying (usually the right
   answer — an independent build-vs-buy analysis recommends keeping the core), the deliverable is the
   **cross-platform order and reconciliation layer**, and the integration contract with the incumbent
   is the project's main risk.
5. **Is copyleft acceptable at all?** Every startable platform is GPL/AGPL. If the client cannot
   tolerate a copyleft process anywhere in the estimate, there is **no open starting point** in this
   plane, and that must be said before the proposal, not during delivery.
6. **Is there a political or regulated-advertising window in the engagement's calendar?** If yes
   (Brazil **October 2026**, any US election cycle), Pattern 25.4 is not an enhancement — it is the
   deadline that sets the delivery date.

---

## Energy, carbon & environmental-footprint recipes — added 2026-11-26 (pass 26)

Every repo named below appears with its verified licence and last-push date in `agents/top.md`,
`repos/foundations.md` or `repos/trending.md` (pass 26 sections). **Read Pattern 26.6 first if the
engagement involves European delivery** — it is a licence and mandate gate, and it is cheap.

### P39 — The attestation condition: why a hard mandate plus free data still yields zero open source

**This is the pass's law, and it corrects P12/P31 rather than replacing them.**

Pass 6 established: *regulator declares → body publishes an implementation guide → permissive
implementations appear.* Pass 11 (healthcare) added the second condition: that sequence describes the
**format layer**; for the **judgment layer** the body of knowledge used to judge must also be freely
licensed. This plane satisfies **both** conditions and still returns zero, so a third condition exists.

**The measurement:**

| | Production carbon (albert) | Software/corporate carbon (SCI, CSRD, cloud) |
|---|---|---|
| Mandate | **Maximum enforcement** — BBC, ITV, Channel 4 require it by contract; non-compliance blocks delivery | Weaker and mostly indirect (CSRD reaches AV indirectly; SCI is voluntary) |
| Input data licence | **Free** — Ember CC-BY-SA, Green Web Foundation CC-BY-SA, Electricity Maps ODbL, USEEIO public | **Identical inputs**, same licences |
| **Form of the deliverable** | **A certificate issued by one private body** | **A number, a report, a filing** |
| Open implementations | **0** (`film production carbon footprint`, `albert carbon calculator`) | **16 adoptable repos; 6 above 1,000 stars** |

**The third condition: open source appears where the obligation is discharged by producing a computable
artefact, and does not appear where it is discharged by attestation to a gatekeeper** — no matter how
hard the mandate or how free the inputs. You cannot implement a certification; you can only submit to
it. There is no artefact to compete on, no output to validate against, and no way for a second
implementation to be *better* — so nobody writes the first one.

**Ask in this order on any plane:**
1. Is the deliverable a **document/number** or a **certificate from a named body**? If a certificate,
   expect zero open source and **sell the feed, not the replacement** (Pattern 26.3).
2. Is the knowledge content free or taxed? (P31, healthcare pass 11.)
3. Is it a format problem or a judgment problem? (P12, pass 6.)
4. Is there a figure for harm avoided, from a primary public source?

**Falsifiable prediction, with today's baseline recorded.** `film production carbon footprint` = **0**
and `albert carbon calculator` = **0** on 2026-11-26. albert's current toolkit closes **16 December
2026** (albert's figure; one guide says 17 December) and is replaced by the Next Generation Toolkit. **If
that toolkit ships a public API, data schema or export format, the first permissive implementations
should appear within two cycles of its release. If it remains a closed web form, both queries stay at
zero even as CSRD and green-claims pressure increase** — and increased mandate pressure alone will not
move them. Either outcome tests the condition directly.

### P40 — The licence enters through the dataset, not the framework

In every earlier plane of this KB, licence risk arrived through a *framework* (AGPL platforms, GPL
tooling, the BXF schema's All-Rights-Reserved trap). Here the code is permissive —
Apache-2.0/MIT/BSD-3 across the whole measurement toolchain — and **the obligations live in the bundled
facts**: Electricity Maps **ODbL** (attribution + share-alike + "provide unrestricted versions if using
DRM"), Ember and Green Web Foundation data **CC-BY-SA**.

**Operational rule, reusable across all twelve industries:** for any dependency that **ships reference
data**, resolve the licence of the *data* separately from the licence of the *code*, and do it by reading
the licence file rather than the SPDX field. `co2.js` reports Apache-2.0 at repo level and carries four
licences at file level (12,678 B vs canonical Apache-2.0's 11,357 B — **the byte count is the tell**);
`green-metrics-tool` ships a 35,429 B "License Index" stacking three. This is the companion to pass 8's
rule for **linked native libraries**: same defect, different vector, and neither is visible to an SBOM
scan of the source tree.

### Pattern 26.1 — Per-title streaming carbon, with the ODbL/DRM boundary drawn before the first commit

**For:** a streamer, broadcaster or FAST operator that needs a defensible per-title or per-stream
emissions figure — for an ESG report, a green-claims substantiation, or a carbon-aware product feature.

**Stack:**
1. [thegreenwebfoundation/co2.js](https://github.com/thegreenwebfoundation/co2.js) (Apache-2.0 code) —
   bytes → gCO2e via the Sustainable Web Design and 1-byte models.
2. [thegreenwebfoundation/grid-intensity-go](https://github.com/thegreenwebfoundation/grid-intensity-go)
   (Apache-2.0) — grid intensity at the edge/CDN node, as a Prometheus exporter.
3. [Green-Software-Foundation/if](https://github.com/Green-Software-Foundation/if) (MIT) — encode the
   delivery chain (origin → packager → CDN → device mix) as an Impact Framework manifest, so the model
   is reviewable rather than buried in code.
4. [Green-Software-Foundation/sci-otel](https://github.com/Green-Software-Foundation/sci-otel)
   (Apache-2.0) — emit the result as an OpenTelemetry metric beside bitrate and rebuffer ratio, on the
   dashboards the operations team already watches.
5. Device and embodied half: [Boavizta/boaviztapi](https://github.com/Boavizta/boaviztapi) — **AGPL-3.0,
   so call it as a service, do not embed it.**

**🔴 The licence gate, and it is the whole point of this pattern.** The grid data bundled in co2.js comes
from Electricity Maps under **ODbL**, which obliges you to attribute, to keep derivative databases
share-alike, and to **"provide unrestricted versions if using DRM."** A commercial streaming service is
DRM-protected by default (`DRM` appears 53 times in this KB). Decide **before** building, in writing:

- **Option A — keep the database at arm's length.** Query grid intensity at runtime from an external
  service; store only the computed gCO2e against your own titles. Your output is then an ordinary
  derived figure, not a redistributed derivative database.
- **Option B — publish the intensity table.** Accept the share-alike and keep-open duties and publish the
  derived database openly, attributed. Often perfectly acceptable, because grid-intensity data is not
  the client's competitive asset — **their per-title figures are**, and those stay private under A or B.
- **Option C — licence the data commercially** from Electricity Maps and drop the ODbL path entirely.

**What never to do:** vendor co2.js's bundled data into a DRM-protected product and report
"Apache-2.0" from the SPDX field. That is the finding of this pass, and it is invisible to SBOM scanning.

**Why it sells:** the EU **green-claims** rules effective **September 2026** bar generic environmental
claims without recognised proof. A "green tier" or "carbon-neutral streaming" claim needs this figure and
its audit trail; this pattern produces both, and no open competitor exists.

### Pattern 26.2 — Carbon-aware render and transcode scheduling (the one place a complete permissive stack exists)

**For:** a VFX house, animation studio, post facility or any operator of a large render/transcode farm.
**This is the shortest path to a shipped, measurable result in the plane** — and it saves money, so it
does not depend on a sustainability budget.

**Stack, MIT/Apache end to end:**
1. [GreenScheduler/cats](https://github.com/GreenScheduler/cats) (**MIT**, pushed 2026-11-26) — decide
   *when* to run: defer a job to a low-carbon window.
2. [Green-Software-Foundation/carbon-aware-sdk](https://github.com/Green-Software-Foundation/carbon-aware-sdk)
   (**MIT**) — decide *where*: shift between regions by forecast intensity.
3. [BreakTools/deadline-energy-cost-calculator](https://github.com/BreakTools/deadline-energy-cost-calculator)
   (**MIT**, 3★) — the media-native connector: a Deadline event plugin computing energy and cost per
   render job. **The only media-specific repo in this plane; treat it as a reference implementation to
   extend, not a maintained dependency** (last push 2025-09-17, 3 stars).
4. [sustainable-computing-io/kepler](https://github.com/sustainable-computing-io/kepler) (**Apache-2.0**,
   pushed today) for per-pod energy on a containerised farm, or
   [hubblo-org/scaphandre](https://github.com/hubblo-org/scaphandre) (**Apache-2.0**) on bare metal.
5. [cloud-carbon-footprint/cloud-carbon-footprint](https://github.com/cloud-carbon-footprint/cloud-carbon-footprint)
   (**Apache-2.0**) to reconcile against the cloud bill — the number finance already trusts.

**The wiring that makes it real:** Deadline's event plugin emits per-job energy; CATS gates job
submission on forecast intensity; kepler/scaphandre provide the measured ground truth that validates the
estimate; CCF reconciles monthly against billing. Deadlines that cannot move (a delivery date) opt out
per-queue — **this is a scheduling policy, not a hard constraint, and saying so protects the pipeline.**

**Why it sells:** deferred rendering cuts cost and emissions together, the measurement is defensible, and
North America — where the render capacity concentrates — has **no mandate** to satisfy, so the economic
argument has to carry the engagement. Here it does.

### Pattern 26.3 — The certification evidence pack (sell the feed, because you cannot replace the calculator)

**For:** any production company or broadcaster delivering into the UK or EU. **This is the direct
commercial consequence of P39.**

**The premise, stated to the client up front:** albert, the MEDIA Carbon Calculator, PEAR, Carbon'Clap
and Green Film **cannot and must not be replaced.** Two are commissioning conditions, one is an EU
instrument behind EU Login. A bespoke tool that disagrees with albert does not help the client — it
fails their certification. `film production carbon footprint` = **0 open repositories** is not a gap in
the market to fill with a competing calculator; it is a reason to build the **feed**.

**Build:**
1. **Extraction** from the systems that already hold the data: the production-management platform
   (**Yamdu** — which presented the MEDIA Carbon Calculator at the EFM and is already in
   `verticals/solutions.md` — plus Croogloo, SetHero, StudioBinder), the accounting/payroll system
   (travel, fuel, freight lines), facilities and generator logs, and the render farm (Pattern 26.2).
2. **Mapping** spend lines to emission factors with
   [salesforce-misc/NZC-USEEIOMatchingAgent](https://github.com/salesforce-misc/NZC-USEEIOMatchingAgent)
   (**Apache-2.0**) — the agent layer's one genuinely apt tool, and it has 0 stars.
3. **Calculation** against the GHG Protocol with
   [agirgol/carbon-accounting-dotnet](https://github.com/agirgol/carbon-accounting-dotnet) (**MIT**,
   GHG Protocol + **ISO 14064-1**, versioned source-cited factors) or, for a French engagement,
   [ABC-TransitionBasCarbone/bilan-carbone](https://github.com/ABC-TransitionBasCarbone/bilan-carbone)
   (**MIT**, pushed 2026-11-26) — the official French methodology body's own code, at 5 stars.
4. **Submission pack** shaped to each destination: albert (Scope 1/2/3 as its toolkit asks), MEDIA
   Carbon Calculator (**GHG Protocol Scope 2 + 3**: transport, waste, business travel, purchased goods),
   PEAR for US productions.
5. **Retain the per-asset detail the client owns and the certifier never sees.** This is the durable
   asset: it compounds across productions into a benchmark the client can bid with, and no calculator
   gives it back to them.

**📅 Timing, and it is the buying trigger.** The current albert toolkit closes **16 December 2026**
(albert's own figure; one industry guide says 17 December — **verify with albert before committing a
date**), replaced by the Next Generation Toolkit with a redesigned calculator. **Build the extraction and
mapping layers to be calculator-agnostic**, with the destination format as a thin adapter — because the
destination is changing within weeks and will change again.

**The multi-calculator problem is the premium.** The MEDIA Carbon Calculator explicitly does *not*
replace national calculators, so a European co-production can face albert **and** the MEDIA calculator
**and** Carbon'Clap or Green Film, each with its own factors and boundaries. One extraction, several
adapters, reconciled — that is the engagement.

### Pattern 26.4 — The AI-workload footprint annex (the plane's clearest unbuilt product)

**For:** any studio or broadcaster using GenAI in production and delivering to a European commissioner.

**Why now, with evidence rather than speculation:** the 2025 **Green Animation Guide** (EcoProd) already
documents a German studio appending an **AI traceability annex** to production reports for broadcasters,
and recommends smaller fine-tuned models. **Greening of Streaming's OWL** bench explicitly measures
streaming **and AI workloads**. The disclosure is starting to be asked for, and **nothing open maps a
measurement to a broadcaster-shaped deliverable.**

**Stack:**
1. [mlco2/codecarbon](https://github.com/mlco2/codecarbon) (**MIT**, 1,955★) — per-job emissions for
   every inference, fine-tune and generation batch.
2. [gwittebolle/claude-carbon](https://github.com/gwittebolle/claude-carbon) (**MIT**, 256★) or
   [Thomaszhou22/agent-carbon-tracker](https://github.com/Thomaszhou22/agent-carbon-tracker) (**MIT**) —
   the assistant and agent side, where scripted and iterative work accumulates invisibly.
3. [ChanelYJ19/agent-carbon](https://github.com/ChanelYJ19/agent-carbon) (**MIT**) if the pipeline is
   LangChain/LangGraph — a callback is cheaper than instrumenting by hand.
4. [Green-Software-Foundation/sci-otel](https://github.com/Green-Software-Foundation/sci-otel)
   (**Apache-2.0**) to report it as **SCI** — implement **ISO/IEC 21031**, and **do not vendor
   `Green-Software-Foundation/sci`**, which is not OSI-licensed (JDF "AS IS", W3C patent mode).
5. Attribute per shot/sequence/asset so the annex matches the production's own breakdown structure.

**The honest framing to give the client:** a per-prompt figure is an estimate with wide error bars, and
the credible claim is **relative** — this sequence against that one, this model against a smaller
fine-tune. Industry commentary on AI video production's energy and water use is largely opinion without
measured data; **this pattern's value is that it replaces that argument with the client's own numbers.**

### Pattern 26.5 — ESRS/CSRD evidence for an audiovisual group

**For:** a broadcaster or media group large enough to report under CSRD, or inside the value chain of one
that is.

**Stack:** [aimabel-ai/esrs-xbrl-parser](https://github.com/aimabel-ai/esrs-xbrl-parser) (**ISC**, 12★,
dormant since 2024-12-17) for the ESRS XBRL taxonomy; the Pattern 26.3 inventory as the data source;
[cloud-carbon-footprint](https://github.com/cloud-carbon-footprint/cloud-carbon-footprint)
(**Apache-2.0**) for the IT estate; [Boavizta/boaviztapi](https://github.com/Boavizta/boaviztapi)
(**AGPL-3.0**, as a service) for embodied hardware carbon — the half operational tools omit, and
material for a broadcaster running transmission and device estates.

**⛔ Do not use [climateandtech/report-analyst](https://github.com/climateandtech/report-analyst)** — 42
stars, pushed today, the best-starred CSRD tool found, and it has **no licence file**: 9 filenames × 2
branches all 404 while `README.md` returns 200, so the channel works and the file is genuinely absent.
All rights reserved by default.

**⚠️ State the scope honestly.** CSRD reaches the AV sector **indirectly**, via obligations on
undertakings large enough to be in scope, and **the thresholds and timing have been amended (Omnibus)
and were not verified in this pass.** Confirm the client's filing obligation with their auditors before
scoping. Promise the **evidence layer**, never the legal conclusion.

### Pattern 26.6 — The 20-minute gate for any media carbon proposal

Run this before writing an estimate. Each question has a cheap answer and each one has sunk a proposal
somewhere in this plane.

1. **Is the deliverable a certificate or a number?** If the client must be *certified* (UK commission →
   albert; EU-backed project → MEDIA Carbon Calculator), you are building a **feed**, not a calculator
   (P39, Pattern 26.3). Proposing a replacement calculator loses the engagement and would fail their
   certification if it won.
2. **Which calculators does this production actually face?** Possibly several at once — albert, MEDIA
   Carbon Calculator, Carbon'Clap, Green Film, PEAR — because the MEDIA calculator explicitly does not
   replace national tools. **Count them before estimating; each is an adapter.**
3. **Does the build touch DRM-protected delivery?** If yes and the stack includes `co2.js`, choose
   Option A, B or C of Pattern 26.1 **in writing, before the first commit**. ODbL's share-alike and
   "unrestricted versions if using DRM" duties are real and invisible to SBOM scanning.
4. **Does any dependency ship reference data?** Resolve the **data** licence separately from the **code**
   licence, by reading the licence file and checking its byte count (P40). co2.js: 12,678 B, four
   licences. green-metrics-tool: 35,429 B, three.
5. **Is copyleft acceptable anywhere in the estimate?** The data layer is where it concentrates:
   Electricity Maps **AGPL-3.0**, Boavizta **AGPL-3.0**, green-metrics-tool **AGPL-3.0**. Call them as
   services or accept the terms — decide before delivery, not during.
6. **Is there a marketing claim attached?** If the client will say "carbon-neutral" or "green" into an EU
   market, the EU **green-claims** rules from **September 2026** require recognised proof, and offsetting
   seals are not proof. The evidence trail becomes the deliverable.
7. **Is a hard date already in the calendar?** albert's current toolkit closes **16 December 2026**
   (albert's figure; one guide says 17 December — confirm with albert), and Korea's **ISSB IFRS S1/S2**
   alignment starts **FY27**. If either applies, the timeline sets the delivery date rather than the
   scope.
8. **Where are the client's emissions actually concentrated?** Usually the render farm or the delivery
   chain — and both have mature permissive tooling (Patterns 26.1, 26.2) while the mandated production
   footprint has **zero**. **Measure where the energy is, report where the mandate is**, and do not let
   the mandate decide the engineering.

---

# Pass 27 — the production-finance, soft-money & cost-accounting plane (2026-11-26)

Every repo named below appears with its verified licence, stars and last-push date in
`repos/foundations.md`, `verticals/solutions.md` or `agents/top.md` under pass 27. **45/45 slugs
resolve via `git ls-remote`.** The plane's own agent layer is one proprietary repo at one star, so
every recipe here composes **permissive general-purpose engines plus domain modelling** — which is the
whole opportunity, not a workaround.

## Pattern 27.1 — The incentive-eligibility engine: statute as versioned code, not a spreadsheet

**The problem.** "Does this budget qualify in Georgia, BC, Spain, NSW or Antioquia, and for how much?"
`production incentive eligibility` returns **0 repositories**. The free lookup tables that Wrapbook,
EP and GreenSlate publish already answer *what the rate is* — **never compete there**. What nobody
sells is a **machine-checkable answer for this specific budget, with a citation and a commencement
date attached to every rule**.

**The wiring.**
1. **Rules layer — [CatalaLang/catala](https://github.com/CatalaLang/catala) (Apache-2.0, 2,456★).**
   One Catala module per jurisdiction. Catala is literate: the statute text and the executable rule sit
   side by side in the same file, so the artefact *is* its own audit trail. Published work already
   expresses parts of the US Internal Revenue Code, so the ambition is proven on harder statutes.
   Model, per jurisdiction: qualifying-spend definition, minimum-spend floor, caps (per-work **and**
   per-company — Italy now has both), uplifts (UK VFX, French VFX > €2M), residency tests,
   above/below-the-line split, and **commencement dates** (Colombia's Decreto 876 de 2026 changed
   eligibility mid-year; Japan's JLOX+ closed to applications 2026-01-31).
2. **If the client's finance team must own the rules** —
   [apache/incubator-kie](https://github.com/apache/incubator-kie) (Apache-2.0, 6,344★) DMN decision
   tables, or [gorules/zen](https://github.com/gorules/zen) (MIT) for JDM models editable without a
   compiler. Catala for correctness, DMN for client ownership; the choice is governance, not tech.
3. **Prior art to copy, not rebuild** —
   [PolicyEngine/policyengine-us](https://github.com/PolicyEngine/policyengine-us) (AGPL-3.0) already
   models US federal **and state** tax law as code, with 224 forks against 178 stars. **Read its
   per-jurisdiction parameter layout before designing yours.** ⚠️ AGPL: study the pattern, or deploy
   client-owned and single-tenant — do not vendor it into a multi-tenant SaaS.
4. **Front door — [jhpyle/docassemble](https://github.com/jhpyle/docassemble) (MIT, 1,019★).** Turn
   the rule set into a guided interview that emits the filing pack. This is a solved problem in legal
   aid and completely unused in screen finance.
5. **Budget input.** No open parser for EP Budgeting exists, and its format is a de facto standard with
   no open specification. Accept **CSV/XLSX exports** and map to a canonical schema;
   [ChrisTempel/CineSpend](https://github.com/ChrisTempel/CineSpend) (MIT, 8★) is a usable reference
   for budget *data shape*. That CreditScout reads EP Budgeting directly confirms the integration seam
   is the export, not the database.

**Licence posture:** Catala Apache-2.0 + Zen MIT + docassemble MIT ⇒ **fully permissive, client owns
the rule sets.** Do not touch akaunting (BSL) anywhere near this.

**Deliberately out of scope:** telling the client what rate applies. That is free, from several
vendors, and more current than you will keep it.

## Pattern 27.2 — Cost report as a diffable ledger: the auditor-facing artefact nobody has built

**The problem.** `cost report film production` = **5 results, 0 relevant**. Production accounting is
double-entry bookkeeping with an industry chart of accounts and a specific weekly report
(actuals vs. budget vs. estimate-to-complete) on top. The engines are excellent and free; **the chart
of accounts is what is missing**, and it is domain modelling, not engineering.

**The wiring.**
1. **Ledger — [ledger/ledger](https://github.com/ledger/ledger) (**BSD-3-Clause**, 6,081★)** when the
   deliverable must stay permissive, or
   [beancount/beancount](https://github.com/beancount/beancount) (GPL-2.0, 6,210★) when the richer
   ecosystem matters more than the licence. Both keep the ledger as **plain text in git**, which makes
   a production's books diffable, reviewable and blame-able with the same tooling as code — an
   unusually strong fit for an artefact an incentive auditor will later contest line by line.
2. **Reporting — [beancount/fava](https://github.com/beancount/fava) (MIT, 2,615★)** for the web
   surface. Note the licence split: the UI is permissive even where the engine is GPL.
3. **Chart of accounts.** The missing asset. Build it from the standard budget topsheet structure
   (above-the-line / below-the-line / post / other), per-episode and per-department cost centres.
   [Gnucash/gnucash](https://github.com/Gnucash/gnucash) is the best open **reference** for
   chart-of-accounts semantics; it is not a deployment target here.
4. **Reconcile against production reality —
   [cgwire/kitsu](https://github.com/cgwire/kitsu) + [cgwire/zou](https://github.com/cgwire/zou)
   (AGPL-3.0).** Kitsu holds man-days and bids; the cost report must agree with it or the variance is
   fiction. ⚠️ AGPL: integrate over its **API**, do not fork it into the deliverable.
5. **Agent layer — the AP clerks, used honestly.**
   [tahasiddiquii/invoice-ap-agent](https://github.com/tahasiddiquii/invoice-ap-agent) (MIT, 5★),
   [sujalmallick/probity-ai](https://github.com/sujalmallick/probity-ai) (MIT, 5★) and
   [Devanshjoshi2804/ap-verify](https://github.com/Devanshjoshi2804/ap-verify) (MIT, 2★) are
   **5-star-and-below prior art, not dependencies.** Read them, then write the coding agent against
   your own chart of accounts. At these star counts, adopting is riskier than rebuilding.

**The hard constraint, and it is commercial.** Where a payroll incumbent (EP, Cast & Crew, Wrapbook,
GreenSlate) is in place, **the cost report shapes auditors expect are theirs.** Never propose replacing
the system of record. Build the report *alongside* it and reconcile; a client who cannot produce an
auditor-recognised cost report because a bespoke ledger disagreed with payroll can lose the credit.

## Pattern 27.3 — Recoupment waterfalls on a programmable ledger

**The problem.** Who recoups, in what order, at what corridor — across financiers, gap lenders,
pre-sales, sales agents and profit participants. `recoupment waterfall` returns **2 repositories on
all of GitHub**; the better one (6★) is an unlicensed 2023 Solidity contract for crypto splits.

**The wiring.**
1. **[formancehq/ledger](https://github.com/formancehq/ledger) (MIT, 1,489★)** — a *programmable*
   financial ledger with a DSL for modelling money movement between many parties. The closest thing in
   open source to a waterfall engine: express each tier as a transaction script, so the waterfall is
   executable and replayable rather than a spreadsheet nobody can re-derive.
2. **High volume → [tigerbeetle/tigerbeetle](https://github.com/tigerbeetle/tigerbeetle)
   (Apache-2.0, 17,467★)** when postings run to millions/day (residual and royalty splits). Purpose-built
   double-entry with strict serialisability.
3. **Embedded → [flash-oss/medici](https://github.com/flash-oss/medici) (MIT, 364★)** for a Node
   product that needs double-entry inside it.
4. **Validate against the KB's own prior finding.** Pass 5 measured `music royalty accounting` at
   **six top results summing to 0 stars**; this pass measured `royalty accounting` at **47 results, 0
   relevant**. Two independent measurements, same answer: **nothing open computes what is owed.** Do
   not promise an off-the-shelf royalty or waterfall engine in any pitch.

⚠️ **Never state a waterfall as "verified" output.** It is a contractual interpretation. The ledger
proves arithmetic and replay; a lawyer owns the tiers.

## Pattern 27.4 — The soft-money optimiser: the plane's most valuable unbuilt product

**The problem.** "Split this production across territories to maximise net benefit." Nobody sells it
and no repo in any licence does it. It is a **constraint-optimisation** problem, and both halves are
mature and permissive.

**The wiring.**
1. **[TimefoldAI/timefold-solver](https://github.com/TimefoldAI/timefold-solver) (Apache-2.0,
   1,882★)** — or [apache/incubator-kie-optaplanner](https://github.com/apache/incubator-kie-optaplanner)
   (Apache-2.0, 3,512★) for a Java/KIE-native client. Decision variables: which scenes/units/post
   stages in which jurisdiction. Hard constraints: minimum-spend floors (Japan IP360 **¥800M**
   domestic), caps (Spain €20M/film, France €30M/project, Italy per-work **and** per-company),
   residency and local-hire quotas, **window availability** (Germany's 2026 pot exhausted
   **2026-08-20**), and creative immovables. Soft constraints: crew depth, travel cost, carbon
   (links to Pattern 26.1), schedule risk.
2. **Scoring function = Pattern 27.1's Catala rules**, called per candidate allocation. The optimiser
   must not re-implement eligibility; it must *invoke* it, or the two will drift.
3. **Output.** A ranked allocation with, per territory, the rule that bound it and the citation behind
   that rule. The explanation is the product; the number alone is a guess the client cannot defend.

**Why now.** Pass 27's trend finding: incentives moved from **pricing to rationing** — exhaustion,
caps, clawback, pre-certification, minimum-spend floors. Rationing is a scheduling-under-constraints
problem. Rate comparison was consulting; **availability optimisation is software.**

## Pattern 27.5 — The claim-evidence pack: the shortest path to delivery in this plane

**Build this first.** The client already owns every input, the deliverable is a document rather than a
system, and the risk it removes is measured in millions.

**The wiring.**
1. **Inputs, all already in the client's hands:** the budget/cost report (Pattern 27.2), the payroll
   export (incumbent system, read-only), the production tracker (Kitsu API), vendor invoices and POs
   (ERP — [frappe/erpnext](https://github.com/frappe/erpnext) GPL-3.0, with
   [frappe/frappe](https://github.com/frappe/frappe) **MIT** underneath, so a custom app stays
   permissive), and contracts/chain-of-title documents.
2. **Qualification** — run Pattern 27.1's rule set over every cost line; emit **qualified /
   non-qualified / needs-review** with the governing rule cited per line.
3. **Evidence binding** — each qualified line links to its source document and the system it came from.
   This is the entire product: **traceability, not arithmetic.**
4. **Assembly** — [jhpyle/docassemble](https://github.com/jhpyle/docassemble) (MIT) builds the
   submission pack in the administrator's required shape.
5. **Agreement check** — where the administrator publishes an official calculator (**Ontario Creates**
   does), the engine must **agree with it**. Disagreement is a defect in your rules, not theirs.

**Why it is the strongest opening offer.** Italy **revoked €66M of credits in 2025** and then capped
the scheme; Manitoba now requires **pre-certification**. The question shifted from *"will we qualify"*
to *"can we still prove it eighteen months later"*. A claim pack where every number traces to a source
document is the artefact that answers the second question, and **no incumbent sells it** — the payroll
companies have no commercial reason to make a claim portable between them.

---

### P41 — When the vertical layer is empty but the horizontal layer is strong, the gap is a vocabulary, not a platform

Twenty-six passes found the same shape: a mature **generic** layer and a thin **vertical** layer, with
the advice to own the pipeline. Production finance inverts it. The vertical layer is a desert
(`completion bond film` **0**, `production incentive eligibility` **0**, `ERPNext media production`
**0**, `film tax credit` **7 repos / best 1★ / all unusable**) while the horizontal layer is among the
strongest in this KB: Catala 2,456★ Apache-2.0, TigerBeetle 17,467★ Apache-2.0, Drools 6,344★
Apache-2.0, Frappe 11,164★ **MIT**, Timefold 1,882★ Apache-2.0, ledger 6,081★ **BSD-3**.

**The rule.** When a plane's generic engines are mature *and* permissive while its vertical repos are
0-star and unlicensed, **the missing artefact is a domain vocabulary — a chart of accounts, a rule set,
a report shape — not a platform.** That reframes the estimate from a build to weeks of modelling on
proven engines, and it is the cheapest high-value position found in twenty-seven passes.

**How to test it on another industry before trusting it.** Run the plane's terms twice: once in
industry language, once in computation language. If the industry query returns 0-star unlicensed repos
and the computation query returns multi-thousand-star permissive ones, P41 applies. **It is the direct
inverse of the KB's content law** (pass 5: scarcity is the registry, not the parser) — here scarcity is
the *mapping*, and unlike a registry allocation, a mapping is something Globant can simply build.

### P42 — `NOASSERTION` is directionless, and in finance the star count predicts the risk

One pass, one API value, three incompatible truths: **akaunting** (10,349★) `NOASSERTION` ⇒ **BSL, not
open source**; **odoo/odoo** (56,124★) `NOASSERTION` ⇒ **LGPL-3.0, Community edition only**;
**ledger/ledger** (6,081★) `NOASSERTION` ⇒ **BSD-3-Clause, fully permissive**. Also read this pass:
**OpenShotDesigner** (47★) `NOASSERTION` ⇒ **GPL-3.0**; **GnuCash** ⇒ GPL-2.0-**or**-3.0;
**film-tax-credit-agent** `NOASSERTION` ⇒ **"all rights reserved … proprietary and confidential"**.

**The rule.** `NOASSERTION` carries **no** directional information — it conceals permissive grants and
commercial traps equally, and treating it as "probably fine" or "probably bad" is wrong half the time.
Read the file. **And the finance-specific corollary: in the accounting/ERP category, star count
correlates with licence risk** — the most-starred result is the one most likely to be
source-available-but-not-open, because that is the business model that funds the marketing that earns
the stars. The 10,349★ result was the only unusable one in its tier.

## Age-rating, classification & child-audience recipes — added 2026-11-26 (pass 28)

All four recipes assume the central finding of this plane: **a rating is a `(system, value)` pair and
nothing in the open estate models it as one.** That single schema decision is what makes these
patterns work and its absence is what breaks every open implementation surveyed.

## Pattern 28.1 — The territory-correct rating resolver: the small fix that makes everything else safe

**The problem, measured not assumed.** `jellyfin/jellyfin` (GPL-2.0, 59,787★) ships 45 per-territory
rating tables and **none carries a `system` field**. When the viewer's country table misses, the
source falls back — verbatim — to *"check all ratings systems, starting with US"*, then walks every
other country. The token `16` is a valid rung on the PEGI, USK, DJCTQ, GRAC and Russian ladders and
means different things on each. **A German `16` can be scored by the US table.**

**The recipe.**

1. **Model the pair.** One table: `(territory, medium, system, value, min_age, min_age_supervised,
   deprecated, valid_as_of, source_uri)`. `medium` is not optional — Germany runs `USK` (games),
   `FSK` (film) and `FSF` (broadcast), and the UK runs `BBFC` for film where the open mapping sends
   `GB → PEGI`.
2. **Seed the ladders** from [MovieLabs/cmr-ratings](https://github.com/MovieLabs/cmr-ratings) —
   110 systems, 77 territories — **as a worklist, never as a vendored dependency.** It has no licence
   file and no README: default copyright applies. Use it to know which boards exist and what their
   rungs look like, then **re-derive each ladder you actually ship from that board's own publication**
   and record the URI in `source_uri`.
3. **Port the mapping logic** from [ximion/appstream](https://github.com/ximion/appstream)
   (LGPL-2.1) — `as-content-rating.c`, with `as_content_rating_system_from_locale()` as the reference
   for territory selection. Port the *structure*; re-source the *data*, because AppStream's own
   comment names Wikipedia as its authority.
4. **Resolve strictly, and fail loudly.** An unqualified rating string must raise, never guess. Delete
   the US fallback. If a title arrives with `16` and no system, that is a **data-quality incident at
   ingest**, not a runtime decision.
5. **Add the control nobody has:** a test that fails when any ladder's `valid_as_of` ages past a
   threshold. The reason is in the data — the dataset's newest `LastChecked` anywhere is
   **2023-07-11**, and its US/MPAA entry has not been validated since **2013-09-28**.

**Deliverable:** a resolver library plus a seeded ladder table with provenance. Days of work, and it
is the precondition for 28.2, 28.3 and 28.4.

## Pattern 28.2 — The published-methodology rating engine (the EMEA play, and the strongest in this plane)

**Why it sells.** The proposed EU KIDS Act (COM(2026) 681, 2026/0286 (COD)) would require an app-store
provider to operate an age-rating system **and publish, in clear and accessible terms, the
methodology, criteria and sources used.** A board certificate cannot discharge that duty — it yields a
rung and no reasoning. A classifier is worse — unreproducible reasoning. **Declared criteria can,
because the criteria are the data.**

**The wiring.**

1. **Criteria vocabulary:** [hughsie/oars](https://github.com/hughsie/oars) (LGPL-2.1, 28★) as the
   shape — per-criterion severity for violence, sex, drugs, language, gambling, social features.
   Extend it for film/TV criteria the games vocabulary lacks; keep the OARS identifiers for the
   overlap so the AppStream mapping still applies.
2. **Ladder projection:** the 28.1 resolver, with **the projection loss recorded explicitly per
   territory.** Measured examples to encode as known limits: AppStream emits 3 Argentine rungs where
   INCAA has 5 (no `mayores de 16`, no `condicionada`) and 3 Australian rungs where the NCS has 8
   (no `G`, `M`, `CTC`, `X 18+`, **no `RC`**). **Never emit an OARS-derived rating as a board
   rating** — label it `self-declared`, and keep `board-issued` as a separate, provenanced field.
3. **Decision record per title:** criteria values, the evidence behind each, the resolved rung per
   territory, the ruleset version, the human who signed it. This is the artefact — see 28.4.
4. **Generate the public methodology page from the ruleset**, so duty (2) is discharged by a build
   step rather than by a document that drifts from the code.
5. **Carry the assurance integration:** the KIDS Act also requires stores to carry the certified EU
   age-verification solution. Pass 9's EMEA estate (the Commission's Age Verification Blueprint,
   EUPL-1.2 / Apache-2.0) is the component — **this plane does not rebuild it, it consumes it.**

**The timing argument to make to the buyer:** Article 17 routes harmonisation through voluntary codes
of conduct that have not been drafted. **An early implementer helps write the criteria everyone else
will later adopt.** That is worth more than the compliance saving.

## Pattern 28.3 — The ClassInd conformance pipeline (the LATAM play, with a fixed date)

**The deadline is real and public:** Portaria 1.048/2025, **articles 48–57 in force 2026-03-17**,
requiring ratings to be **available in catalogue descriptions, trailers and promotional materials**
for streaming and VOD. That is a metadata-propagation requirement, not a badge.

**The wiring.**

1. **Ladder:** `L, 10, 12, 14, 16, 18` via the 28.1 resolver, keyed `(BR, film|tv, ClassInd)`. Note
   two traps already measured: AppStream still names the system **`DJCTQ`** (the retired board name),
   and Jellyfin's `br.json` carries a **`9`** rung that is not on the current ladder — inherited from
   an upstream `Deprecated=true` entry whose flag did not travel. **Reject `9` at ingest.**
2. **Descriptors are the hard part, and they are closed.** MovieLabs' Brazilian entry records that
   **"only 10 reasons are currently accepted in Brazil. All other reasons are considered invalid,"**
   citing the gov.br ClassInd 2021 practical guide. Build an explicit map from detector output to
   those ten permitted descriptors, and **make anything unmapped a human-review queue item**, never a
   silent drop.
3. **Evidence, not inference.** Use [infinitered/nsfwjs](https://github.com/infinitered/nsfwjs) (MIT,
   9,038★) — the only permissive, maintained, widely-adopted detector in the plane — to flag
   candidate scenes with timecodes. **Avoid [notAI-tech/NudeNet](https://github.com/notAI-tech/NudeNet)
   in a hosted request path: AGPL-3.0 reaches the service.** The detector proposes; a human
   classifier decides and signs.
4. **Propagate to every surface the Portaria names:** catalogue feed, trailer assets, promo
   cut-downs, partner deliveries. One rating source, many renderings — and a conformance report that
   asserts each surface carries the current value.
5. **Enforce** with [seerr-team/seerr](https://github.com/seerr-team/seerr) (MIT, 13,359★) for
   per-profile ceilings and the unrated-titles toggle, on Jellyfin with the 28.1 resolver patched in.

**Why this engagement is attractive:** no open implementation of Brazilian classification exists —
`classificacao indicativa` returns 8 repositories, **all at 0 stars** — the deadline is fixed, Brazil
is LATAM's largest streaming market at 40M+ VOD households, and the same engine re-points at
Argentina for the cost of a ruleset.

## Pattern 28.4 — The classification evidence pack: what to build when the decision must stay human

**The principle this plane taught the KB:** where judgment is **legally attributed to a named party**,
the product is never the decision. `content classification agent MCP` returns literally nothing, and
that is not a market gap to fill with an agent — it is a constraint. An agent that *issues* a
statutory rating is unsellable; an agent that *prepares the evidence for the person who signs it* is
the whole job.

**What the agent does.**

- **Assembles candidate evidence:** scene timecodes and classes from `nsfwjs`, language flags from the
  transcript (the subtitle and transcript estate from passes 3 and 14), and the per-criterion OARS
  draft declaration.
- **Drafts the declaration** against the territory's descriptor list, with a citation for each
  criterion — the timecode, the line, the frame.
- **Checks consistency**, which is where it earns its keep: the same title rated across 20
  territories should not be `12` in one and `18` in a neighbour on identical criteria without a
  recorded reason. **Flag the divergence; do not resolve it.**
- **Detects drift:** when a ladder's `valid_as_of` ages or a board republishes, re-open the affected
  titles for review.

**What the human does:** signs. The record keeps who, when, on which ruleset version, with which
evidence.

**What this is worth.** It is the same artefact shape as pass 20's source-protection evidence pack and
pass 27's claim-evidence pack, and the same reason applies: **the deliverable is admissibility.** For
an EU app-store operator it discharges the published-methodology duty; for a Brazilian VOD operator it
is the audit trail behind every rating in the catalogue; for a US children's tier it is the "Made for
Kids" determination record the amended COPPA rule expects from **2026-04-22**. One artefact, three
regions, three different regulators — which is exactly the portability this KB keeps saying is the
scarce property.

## Interactive, branching & playable-story recipes — added 2026-11-26 (pass 29)

Every repo named below was verified on 2026-11-26 (`git ls-remote` + licence read). The licence note
on each line is load-bearing: this plane's authoring tools are copyleft and its runtimes are
permissive, which is the reverse of the rest of this file.

### P43 — When the open source is healthier than the channel, the gap is a *buyer*, not a component

Twenty-eight passes recorded the same law: a healthy horizontal layer above an empty vertical one, and
the gap was always something unbuilt. Pass 29 is the first inversion in this KB. The vertical layer
here is excellent — ink (MIT, 5,067★), Yarn Spinner (MIT, 2,883★), Ren'Py (MIT, 7,065★), dialogic
(MIT, 6,194★), all pushed within days — and the thing that disappeared is the **customer**: Netflix
removed its interactive catalogue in stages ending **2025-05-12**, calling the technology "limiting".

**The operational rule:** before proposing anything in a plane whose open source looks unusually
healthy, check whether the commercial channel is still there. A mature, permissive, actively-pushed
substrate with no commercial deployments is **evidence of a failed market, not of an easy win**. The
correct response is not to avoid the plane — it is to **re-point the same components at the channels
that still pay**, which is what every pattern below does.

### P44 — In a split-licence plane, adopt the copyleft half as a *tool* and ship only the permissive half

This plane's authoring tier is GPL-3.0 (Twine, the H5P hosts, BBC StoryPlayer) and its runtime tier is
permissive (ink, Yarn, Godot, Ren'Py, Lightning, OpenFMV). The naive reading — "GPL in the stack,
walk away" — loses the best writer-facing tools in the industry. The correct reading: **nobody ships
an authoring GUI to a customer.** Use Twine and H5P as internal production tools, keep the GPL host
behind a service boundary or on a GPL platform (Moodle is GPL anyway), and build the artefact the
client embeds on the MIT content types and MIT runtimes. State which side of the boundary each
component is on *in the proposal*, before the first commit.

### Pattern 29.1 — Narrative QA as a release gate (the plane's clearest unbuilt product)

**Problem.** A branching story is a graph and nobody tests it like one. Writers ship dead ends,
unreachable nodes and contradictory state, and the defect is found by a viewer.

**Wire it together.**
1. Author in [`inkle/ink`](https://github.com/inkle/ink) (MIT) — `inklecate` compiles from CI; or
   [`YarnSpinnerTool/YarnSpinner`](https://github.com/YarnSpinnerTool/YarnSpinner) (MIT) for
   screenplay-shaped dialogue.
2. Gate every commit with [`chaoz23/inkcheck`](https://github.com/chaoz23/inkcheck) (MIT, 2★) — it
   compiles the story, **exhaustively playtests every branch** and reports dead content. It is also
   an MCP server, so an agent can run it.
3. Add the coverage artefact nobody ships: for each release, the node/edge inventory, the unreachable
   set, the dead-end set, state-contradiction findings, and a **sign-off line a showrunner can read**.
4. Compile to the target with [`y-lohse/inkjs`](https://github.com/y-lohse/inkjs) (MIT) for web/CTV or
   [`paulloz/godot-ink`](https://github.com/paulloz/godot-ink) (MIT) for a shipped app.

**Why it sells.** The North American blocker is the writers room (54% of M&E leaders in Grant
Thornton's 2026 survey say the frontline needs adoption support most) under a board that has already
approved the money (87%). This pattern gives a writers room a safety net instead of a replacement —
and the whole chain is MIT.

### Pattern 29.2 — The per-path disclosure ledger (the EMEA play, and it has a live deadline)

**Problem.** AI Act Article 50 transparency applied from **2026-08-02** (guidance 2026-07-21; systems
already on the market have until **2026-12-02** under the amendment the Council approved 2026-06-29),
and it reaches production companies and rights holders *deploying* AI to generate or manipulate
content, including non-EU businesses distributing into the EU. But the duty assumes **a fixed work
that can carry a label**, and a branching experience produces a path per viewer while an AI character
produces lines that existed nowhere at publication.

**Wire it together.**
1. Enumerate the graph from the compiled story (ink/Yarn/Twee via
   [`videlais/extwee`](https://github.com/videlais/extwee), MIT) — every node, every edge, every
   reachable path class.
2. Tag each node with its generation provenance, reusing the C2PA/provenance work already in this KB
   (pass 5): human-authored, AI-assisted, AI-generated, and for performance assets the consent
   reference.
3. For AI characters, log **per-utterance** records at runtime from the agent layer
   ([`elizaOS/eliza`](https://github.com/elizaOS/eliza) MIT, or
   [`pipecat-ai/pipecat`](https://github.com/pipecat-ai/pipecat) BSD-2 /
   [`livekit/agents`](https://github.com/livekit/agents) Apache-2.0 for voice).
4. Emit the Article 50 artefact as a **queryable record per transmission**, not a badge on a frame,
   and keep it joinable to the per-path inventory from step 1.
5. If delivery is object-based, [`bbc/storyplayer`](https://github.com/bbc/storyplayer) (**GPL-3.0**)
   plus the Object Based Media Schema is the only open broadcaster-grade runtime — scope it as a
   deployed service, per P44.

**Why it sells.** The duty is in force, the EU's own Apply AI approach names "interactive and
immersive media storytelling" as a funding priority, and **nobody has modelled disclosure over a
graph**. The buyer is a public broadcaster or its production supplier.

### Pattern 29.3 — Branching scenarios inside a closed product, without the GPL host (the H5P escape route)

**Problem.** The client wants branching decision-trees over video inside their own closed product.
Every H5P host implementation is **GPL-3.0** ([`h5p-php-library`](https://github.com/h5p/h5p-php-library)
156★, [`H5P-Nodejs-library`](https://github.com/Lumieducation/H5P-Nodejs-library) 207★ with the full
35,146 B GPLv3 text), while the **content types are MIT**
([`h5p-branching-scenario`](https://github.com/h5p/h5p-branching-scenario) 36★,
[`h5p-interactive-video`](https://github.com/h5p/h5p-interactive-video) 267★). Secondary sources
flatten this to "H5P is MIT", which is how a licence breach reaches a sprint.

**Three routes, in order of preference.**
1. **Build on the MIT content type, skip the host.** Render `h5p-branching-scenario`'s MIT package
   inside your own player ([`videojs/video.js`](https://github.com/videojs/video.js), Apache-2.0,
   file-read) and keep authoring in the client's existing CMS. No copyleft enters the product.
2. **Service boundary.** Run the GPL host as a standalone service behind an API, consumed over HTTP —
   the product does not link it.
3. **Platform-native.** If the client is on Moodle or WordPress, use
   [`moodle-mod_hvp`](https://github.com/h5p/moodle-mod_hvp) (GPL-3.0) — the platform is already GPL,
   so the licence costs nothing.

**Why it sells.** Learning, onboarding, compliance training, museum and brand experiences are where
branching narrative kept its budget after streaming left. This is the pattern with the shortest path
to delivery in the plane.

### Pattern 29.4 — Interactive on the operator's box (the CTV play nobody lists)

**Problem.** A participatory format has to run on a set-top box or smart TV, and there is no
interactive primitive in HLS or DASH to lean on.

**Wire it together.**
1. App shell in [`rdkcentral/Lightning`](https://github.com/rdkcentral/Lightning) +
   [`Lightning-SDK`](https://github.com/rdkcentral/Lightning-SDK) (both Apache-2.0, 342★ combined) —
   the only open route onto RDK/WPE devices without a native SDK per vendor.
2. Story logic as a compiled ink JSON bundle via `inkjs` (MIT) — small, no engine required.
3. Video playback through the operator's existing player; treat each branch as a separate rendition
   and pre-buffer the candidate next segments, which is the mechanic
   [`mohetios/BandersnatchInteractive`](https://github.com/mohetios/BandersnatchInteractive) (MIT,
   255★) demonstrates and [`Comedian1926/OpenFMV`](https://github.com/Comedian1926/OpenFMV) (MIT,
   241★) authors.
4. Measurement through the Apache-2.0 analytics stack already recorded in pass 7 — per-branch
   completion is the only metric that justifies the format.

**Scope honestly.** State in the proposal that the player is **yours**, because no standard provides
one, and that the second-screen layer is bespoke: `second screen companion tv` returns **2
repositories in all of open source, both at 0 stars**. The nearest real artefact,
[`bbc/audio-orchestrator`](https://github.com/bbc/audio-orchestrator), is a **GPL-3.0 prototype with
11 stars**.

### Pattern 29.5 — The interactive character with a consent and disclosure trail (APAC-first)

**Problem.** Korea's **AI Basic Act** (live **2026-01-22**) requires disclosure of AI-generated **and
AI-assisted** content, reaching platforms counting Korea as a market (Webtoon, Tapas, Tappytoon), with
watermark disclosure under a **one-year grace period**; for partial AI use the standard is still
self-regulation and contract. Brazil's CONAR 2026 guidance covers **avatars and virtual profiles**.
Nothing open records *partial* assistance.

**Wire it together.**
1. Character runtime: [`lipku/LiveTalking`](https://github.com/lipku/LiveTalking) (Apache-2.0,
   11,338★ — interruptible mid-sentence) or
   [`HumanAIGC-Engineering/OpenAvatarChat`](https://github.com/HumanAIGC-Engineering/OpenAvatarChat)
   (Apache-2.0) / [`datascale-ai/opentalking`](https://github.com/datascale-ai/opentalking)
   (Apache-2.0).
2. Avatar container: [`vrm-c/UniVRM`](https://github.com/vrm-c/UniVRM) (MIT) for Unity or
   [`pixiv/three-vrm`](https://github.com/pixiv/three-vrm) (MIT) in a browser — VRM is the
   interoperable format APAC standardised on.
3. Dialogue spine: authored ink/Yarn for the parts that must be deterministic (legal lines, product
   claims, age-sensitive content), the model only inside those bounds.
4. The artefact: a **graduated assistance record** — per panel, per line, per frame — with the
   consent reference for any likeness or voice, watermark emission under the grace period, and a
   disclosure record that survives localisation into Japan (**49.5% of K-webtoon exports**).
5. ⛔ **Keep these out of delivery:** [`tegnike/aituber-kit`](https://github.com/tegnike/aituber-kit)
   (custom, **non-commercial by default**), [`duixcom/Duix-Mobile`](https://github.com/duixcom/Duix-Mobile)
   (**DUIX.COM Community Licence**), [`Tencent-Hunyuan/HunyuanVideo-Avatar`](https://github.com/Tencent-Hunyuan/HunyuanVideo-Avatar)
   (Tencent community terms), [`NVIDIA/Audio2Face-3D`](https://github.com/NVIDIA/Audio2Face-3D)
   (NVIDIA product terms, **no LICENSE file**), [`pixiv/ChatVRM`](https://github.com/pixiv/ChatVRM)
   (MIT but **archived**).

**Why it sells.** The duty is in force, the platforms in scope are named in the law, and the
graduated record is the part no vendor ships. Adoption data says the creators are not the buyers here
(**18.3%** of 800 webtoon artists had used genAI; **36.1%** intended to) — sell to the platform, whose
exposure is statutory.

### Pattern 29.6 — Zero-licence-exposure narrative delivery for a funded games sector (LATAM-first)

**Problem.** A Brazilian or Mexican studio with public funding (Brazil's 2024 games reclassification
opened cultural-funding access; grants are now reaching studios) needs a narrative pipeline, and
cannot take on licence risk it has no counsel to assess.

**Wire it together — and note that every component is MIT.**
1. Engine: [`godotengine/godot`](https://github.com/godotengine/godot) (MIT, 120,887★).
2. Narrative: [`dialogic`](https://github.com/dialogic-godot/dialogic) (MIT, 6,194★) or
   [`godot_dialogue_manager`](https://github.com/nathanhoad/godot_dialogue_manager) (MIT, 4,005★), or
   [`godot-ink`](https://github.com/paulloz/godot-ink) (MIT) if the writers prefer ink.
3. Design: [`mhgolkar/Arrow`](https://github.com/mhgolkar/Arrow) (MIT, 1,378★) for the node graph —
   with the caveat that it has not been pushed since **2025-09-05**; treat it as a stable tool, not a
   dependency.
4. Localisation: the pass 14 stack, unchanged.
5. Web build for a publisher's page: [`pixijs/pixijs`](https://github.com/pixijs/pixijs) (MIT) or
   [`phaserjs/phaser`](https://github.com/phaserjs/phaser) (MIT).

**The sentence to put in the proposal:** *"This stack is MIT end to end — authoring, runtime,
localisation and web delivery — so there is no copyleft obligation and no commercial-use
restriction."* It is rare in this KB and it is true here. Secondary play for the same region: the
**virtual-influencer compliance kit** in `intel/market.md` pass 29, built on UniVRM/three-vrm (MIT)
and LiveTalking (Apache-2.0), aimed at CONAR's avatar and child-participation duties.

### Pattern 29.7 — The 20-minute gate for any interactive-narrative proposal

Run this before estimating. Each line is a measured fact from pass 29, and each one has killed a bad
proposal shape:

1. **Is the client asking for interactive video on a streaming service?** If yes, say out loud that
   Netflix exited the category (final removals **2025-05-12**, technology called "limiting") and
   re-point to games, learning, brand experience, CTV or AI characters. Do not open with a revival
   narrative.
2. **Is a market-size number in the deck?** Interactive *video* has **no published figure**. The
   adjacent segments disagree by **1.9×** and **2.1×** on the same base year. Quote the spread or
   quote the substrate counts instead.
3. **Which side of the licence seam is each component on?** ink/Yarn/Godot/Ren'Py/Lightning/OpenFMV =
   permissive, ship it. Twine/H5P hosts/StoryPlayer = GPL-3.0, tool-only or service boundary.
   ChoiceScript and aituber-kit = **non-commercial, never ship**.
4. **Does the scope assume a standard?** There is **no branching primitive in HLS or DASH**. The
   player is yours; price it.
5. **Does the scope assume a second screen?** `second screen companion tv` = **2 repositories, both
   0★**. Every line of that is bespoke.
6. **Does a disclosure duty apply?** EU Article 50 (in force; **2026-12-02** for existing systems),
   Korea AI Basic Act (**2026-01-22**, AI-*assisted* included), Brazil CONAR (avatars). If yes, the
   per-path or per-utterance record is in scope — and it is the part nobody has built.
7. **Does a branch change the title's age rating?** Pass 28's ladders apply per path. No open tool
   knows this. Either exclude it explicitly or sell it as the junction product.

---

## Pass 30 (2026-11-26) — the AI-answer-engine discovery, citation & referral-measurement plane

### P45 — When the dominant surface emits no event, stop designing a dashboard and start designing a *refusal*

Twenty-nine passes have recorded planes where the terminal step had **no code**. This is the first
with **no measurable event**. Google's AI Overviews and AI Mode serve from `google.com`: they emit
**no referrer** (so no referrer taxonomy can ever classify them, however many entries it gains) and
Google's own Search Console gen-AI reports give **impressions without clicks**. No amount of tooling
closes that.

**The reusable rule:** before composing a measurement stack, determine for each question *which
channel could physically answer it*, and write the unanswerable ones into the deliverable as explicit
refusals. A four-row table beats a dashboard, because a dashboard that silently reports zero where
the event is unobservable **will be read as "no AI impact"** — the single most expensive
misunderstanding available in this plane.

| Question | Only channel that can answer | Open tooling | Verdict |
|---|---|---|---|
| Did an AI crawler fetch my content? | server / CDN logs | `goaccess` + `crawler-user-agents` (MIT) | ✅ answerable today |
| Did a human arrive *from* a chatbot? | referrer / UTM | `referer-parser` `chatbot:` (⚠️ GPL-3.0 data) | ⚠️ answerable, 9 engines only |
| Did I appear inside an AI Overview? | Search Console gen-AI reports | none | ⚠️ impressions only, from 2026-05-18, **no backfill** |
| How many clicks did that appearance earn? | — | — | ⛔ **not emitted** |
| What was the appearance worth? | — | — | ⛔ **nothing exists** |

### P46 — The tooling for a brand-new standard is disproportionately likely to be unlicensed (second instance → now a rule)

Pass 5 found `rslstandard/rsl` — the official repo of the RSL 1.0 licensing standard, whose entire
purpose is machine-readable terms — **with no licence file**. Pass 30 finds the same shape:
[firecrawl/llmstxt-generator](https://github.com/firecrawl/llmstxt-generator), **the most-starred
dedicated `llms.txt` generator (540★), has no licence file** (10 names × 2 branches; `README.md`
returns 200 on both, so the channel works; shallow-cloned and confirmed — nothing licence-like at
root). **Check the tool, not just the spec**, and treat an unlicensed tool for a standard as the
expected case rather than the surprise.

### P47 — Extending P40: the licence can be inherited from the data's *ancestor*, declared only in prose

P40 established that licence risk enters through **bundled facts** that carry their own licence files.
[snowplow-referer-parser/referer-parser](https://github.com/snowplow-referer-parser/referer-parser)
is a third vector and the worst yet: **the repo declares nothing** (API: `NONE`, no licence file at
root), while its README's *"Copyright and license"* section states that **`referers.yml` derives from
Matomo's `SearchEngines.php`/`Socials.php`, copyright 2012 Matthieu Aubry, under GPL-3.0.** The 85 KB
dataset — *the exact file you would extend with AI referrers* — is **copyleft by inheritance**, and
the only record of that is a sentence of prose.

**Operational rule:** when a repo reports no licence **but ships a substantial dataset**, read the
README's copyright section before concluding the data is unencumbered. Absence of a licence file is
not absence of an obligation; it may mean the obligation was inherited and never restated. Mitigation
here: **read the nine-entry list and re-implement it; do not vendor the YAML.** A list of nine domain
names is not itself the copyrightable asset — the 424-entry compilation is.

### Pattern 30.1 — The answer-engine ledger (the product that does not exist in open source)

**For:** any publisher, broadcaster or brand newsroom that has been asked "what is AI search doing to
us?" and cannot answer with evidence.

**Stack — every component MIT, self-hostable, no data leaves the client:**
1. [allinurl/goaccess](https://github.com/allinurl/goaccess) (MIT, 21,158★) — parse origin and CDN
   logs. **This is the load-bearing component:** an AI crawler never executes JavaScript, so it is
   invisible to every tag-based analytics tool the client already owns.
2. [monperrus/crawler-user-agents](https://github.com/monperrus/crawler-user-agents) (MIT, 1,416★,
   pushed 2026-11-26) — classify those hits by crawler identity. Verify forward/reverse DNS for the
   bots that publish IP ranges; record spoofable user agents as *claimed*, not *confirmed*.
3. [snowplow-referer-parser/referer-parser](https://github.com/snowplow-referer-parser/referer-parser)
   — the `chatbot:` taxonomy (9 engines). ⚠️ **Per P47: read it, re-implement the list, do not vendor
   `referers.yml`.** Add the measured absences yourself: **Grok/xAI, DeepSeek, You.com, Phind.**
4. [umami-software/umami](https://github.com/umami-software/umami) (MIT, 40,403★) — the human-session
   half, and the only permissive general analytics base (`plausible` is AGPL-3.0, `matomo` GPL-3.0).
5. **Google Search Console gen-AI impressions** — manual export. ⚠️ Whether this is reachable via the
   **Search Console API is UNVERIFIED**: `developers.google.com` does not resolve from this session
   (outside allowed network domains). **Scope iteration one around a manual export** and say so.

**The deliverable is four columns and one paragraph of refusals:** crawl events · chatbot referrals ·
AI impressions · human sessions — plus P45's explicit statement that AI Overview **clicks cannot be
measured**. Ship the refusal paragraph; it is what makes the ledger trustworthy rather than another
dashboard.

**Do first, before anything else:** extend log retention. Google's instrument has **no backfill**
before 2026-05-18, so the client's own logs are the only route to a pre-AI baseline, and every week
of un-retained logs is a week that cannot be reconstructed. This is a one-sprint fix that protects an
asset the client does not know is expiring.

### Pattern 30.2 — The machine-readability audit (and what *not* to sell)

**For:** a client asking to "optimise for AI search".

**Stack:**
1. [Auriti-Labs/geo-optimizer-skill](https://github.com/Auriti-Labs/geo-optimizer-skill) (MIT,
   1,398★, pushed 2026-11-26) — the audit of schema, meta tags and content structure. It **ships an
   MCP server**, so it drops into an agent workflow rather than staying a one-off CLI run.
2. [jina-ai/reader](https://github.com/jina-ai/reader) (Apache-2.0) or
   [unclecode/crawl4ai](https://github.com/unclecode/crawl4ai) (Apache-2.0, 87,986★) — fetch the
   client's **own** pages as an engine would read them.
3. [adbar/trafilatura](https://github.com/adbar/trafilatura) (Apache-2.0, 7,182★) — show what
   survives boilerplate stripping, i.e. which part of the page is even eligible to be quoted.
4. [microsoft/markitdown](https://github.com/microsoft/markitdown) (MIT, 198,609★) +
   [docling-project/docling](https://github.com/docling-project/docling) (MIT, 71,109★) — the
   back-catalogue and PDF conversion.
5. `schemaorg/schemaorg` (Apache-2.0, already in this KB — `NewsArticle`, `VideoObject`,
   `ClaimReview`) + [ekalinin/sitemap.js](https://github.com/ekalinin/sitemap.js) (MIT) for sitemaps
   and **news sitemaps**.

**Deliverable:** a side-by-side *"what you publish vs what the engine retains"* per template — which
is persuasive in a way no score is, because the client sees its own article reduced to what survives.

⛔ **Do not headline `llms.txt`.** It is the artefact clients name, and the evidence is against it:
Google states in writing that Search does not use such files; **Ahrefs found 97% of `llms.txt` files
across 137,210 domains received zero traffic in May 2026, with 96% of arriving requests being bots**;
SE Ranking measured **10.13% adoption**; the spec repo's last push was **2026-09-24** and the leading
generator is unlicensed and dormant since **2025-06-17**. Ship it only for **developer
documentation**, where coding agents genuinely do read it — and bill it as a 30-minute task, not a
strategy. Being able to say this with numbers is worth more to the client relationship than the work
it declines.

### Pattern 30.3 — The reservation/arrival reconciliation gate (joins pass 5 to pass 30)

**For:** an EMEA publisher that has declared a machine-readable reservation under **DSM Article 4**.

**Stack:** `ai-robots-txt/ai.robots.txt` (MIT, 4,272★, already in this KB) declares the refusal →
`goaccess` (MIT) proves what actually fetched → `crawler-user-agents` (MIT) attributes it → the
**compliance delta** is the deliverable: *crawlers you blocked that crawled anyway*, with timestamps,
verified identity where the operator publishes IP ranges, and claimed-only identity where it does not.

**Why this is EMEA-first and genuinely unbuilt:** pass 5 established that EMEA is the only region
where **reserving** rights is a legal instrument. Pass 30 adds that the same crawler's **arrival** is
measurable with MIT tooling. So EMEA is **the only region where the gap between a declared refusal and
an observed crawl is a legal fact** rather than a curiosity — and nobody ships the reconciliation. All
components are permissive; the integration is the product. Keep it **self-hosted**: the DPP's
digital-sovereignty finding means a stack shipping logs to a non-European AI service can fail the
client's own procurement.

**Sequencing across the three patterns:** 30.3 is the sharpest EMEA opener, 30.1 is the universal
one, 30.2 is the cheapest to deliver and the best qualifier. All three share the same two MIT
components (`goaccess`, `crawler-user-agents`), so the second engagement is largely the first one's
infrastructure pointed at a new question.

## Live-event, show-control & stagecraft recipes — added 2026-11-27 (pass 31)

Every repo named below appears with its verified licence, star count and last-push date in
`agents/top.md`, `repos/foundations.md` or `verticals/solutions.md`, measured 2026-11-27. The
distinguishing feature of this plane: **the agent never touches a fixture.** It writes to a console or
a daemon that already knows how. That makes these the lowest-risk recipes in the KB — and it is why
the licence gate (31.3) matters more here than the architecture.

---

## Pattern 31.1 — The licence-clean show-control spine (the one build that ships in every region)

**Why:** this is the only plane in the KB where a complete, production-grade platform is permissive.
Every component below is Apache-2.0 or MIT, so there is no copyleft conversation and no AGPL surprise.

```
[Show intent: script, cue sheet, setlist, or prose brief]
      ↓
[Agent layer — MCP server you build]                    ← see 31.2; nothing off-the-shelf is shippable
      ↓  writes a show file, does NOT drive the rig
[QLC+ (Apache-2.0, 1,593★)]                             ← authoritative show file: patch, cues, effects
      ↓  fixture definitions
[pygdtf (MIT) + pymvr (MIT)]                            ← GDTF device descriptions, MVR scene exchange
      ↓  ⛔ LICENCE GATE: where do the fixture files come from?  → 31.3
[BlenderDMX (GPL-3.0) — run as a tool, do not embed]    ← human pre-visualisation and sign-off
      ↓  approved show
[ETCLabs/sACN (Apache-2.0) or OLA (LGPL-2.1, link only)] ← E1.31 onto the venue network
      ↓
[Rig]   + [x42/libltc (LGPL-3.0)] for SMPTE/LTC sync with audio and video
```

**Wiring:** QLC+ holds the authoritative show file and exposes a web API — the agent proposes, QLC+
stores, a human approves in BlenderDMX pre-vis, and only then does sACN carry it to the rig. Use
`ETCLabs/sACN` (Apache-2.0) when you are embedding transport in your own binary; use OLA when you need
protocol conversion across many interface types and can **link** LGPL-2.1 rather than fork it. Add
`python-psn` (MIT) only if followspots or projection must track a moving performer.

**Licence posture:** QLC+ Apache-2.0, pygdtf/pymvr/sACN MIT-or-Apache, libltc LGPL-3.0 (link). The one
GPL component, BlenderDMX, is a **desktop tool a human opens** — not a library you ship — so it never
enters your distribution. **This stack can be embedded in a proprietary product.** Keep it that way:
do not reach for `xLights` (GPL-3.0) or `FPP` (see 31.3) inside a shipped binary.

**Why it ships in all four regions:** it is on-premise by nature. A rig runs on a venue LAN, often
air-gapped. That satisfies EMEA's digital-sovereignty procurement test **by construction** rather than
by concession — the easiest sovereignty story in this KB.

---

## Pattern 31.2 — The rig-aware agent: build what the eight existing projects did not

**Why:** the plane's entire agent layer is eight repos born in 2026 holding ~38 stars, and all eight
are **control bridges** — prose in, DMX out. None of them produces a **reviewable show file**, and
none of them touches **device discovery**. Both gaps have Apache-2.0 substrates and no competition.

**Build A — the agent that writes a reviewable artefact (the product a designer would buy):**

```
[Script / setlist / audio stem]
      ↓
[Your MCP server]
   ├── reads: QLC+ workspace (.qxw), MVR scene via pymvr (MIT)
   ├── reasons: cue structure, timing against LTC, colour per fixture capability from GDTF
   └── writes: a QLC+ show file + an MVR scene — NOT live DMX
      ↓
[Human programmer opens it in QLC+ / BlenderDMX, edits, owns it]
```

The precedent is measured, not hypothetical: **`JohnBreault/xlights-mcp-server` (MIT, 32★, 10 forks)
is the only project in the plane with adoption, and it is the only one that writes sequences instead
of driving a rig.** On a sample of one, the market has already stated its preference. Treat MVR exactly
as this KB treats `.otio` in the editorial handoff: **the artefact is the deliverable, not the
execution.**

**Build B — the rig inventory agent (no competition at all):**

```
[ETCLabs/RDMnet (Apache-2.0, 56★) + ETCLabs/RDM (Apache-2.0)]   ← ANSI E1.33 / E1.20 discovery
      ↓  enumerated devices: model, address, personality, firmware, errors
[GDTF definitions via pygdtf (MIT)]                              ← what each device can actually do
      ↓
[Agent: reconcile discovered rig vs. the paper patch; flag drift, firmware skew, address conflicts]
      ↓
[Report + a corrected patch proposal]  → ETCDmxTool (Apache-2.0) to sniff and confirm
```

**Why B is the better first engagement:** it is a **diagnostic and documentation** product, not a
creative one. It does not touch a designer's craft, it does not touch crew scheduling (which in North
America is a collective-bargaining question — see `intel/market.md`), it is Apache-2.0 end to end from
the incumbent manufacturer, and nothing in the existing agent layer does it. Sell the pre-show rig
check: *"here is what is actually plugged in, here is where it disagrees with your paperwork."*

---

## Pattern 31.3 — The 20-minute licence gate for any live-event or show-control proposal

**Run this before the stack is named in a client document.** It is four questions, and in this plane
each one has already produced a wrong answer somewhere.

**1. Where do the fixture definitions come from, and under whose terms?**
The format is open (**GDTF = DIN SPEC 15800:2022**) and the parsers are MIT. **The library is not:**
GDTF Share requires a free account with **no anonymous download path**, and each manufacturer
publishes its files **under its own terms**. Open Fixture Library (MIT code, 274★) is the only ungated
channel, and the licence of its fixture **data** is unstated in the repo. ⛔ **Never promise an
end-to-end open fixture pipeline until this is answered in writing.** This is the seventh plane in
which the content, not the code, is the constraint.

**2. For every `NOASSERTION` dependency, read the licence file — looking for the word "components".**
- `FalconChristmas/fpp` (747★): a licence **manifest** declaring GPL-2 + LGPL-2.1 **+ CC-BY-ND
  components that may not be modified and redistributed.** ⛔ **Disqualifying for most client work**,
  and invisible to SBOM scanning.
- `bitfocus/companion` (2,376★): **MIT + a CLA** that gives the vendor a sublicensable licence over
  contributions. Fine to ship; raise it before your team commits upstream on a client's time.
- `OpenLightingProject/ola` (773★): the grant is in **`COPYING`**, not `LICENSE` (404), and reads
  LGPL-2.1 — a 404 from the raw channel is **never** by itself proof a licence is missing.

**3. Check the governing law, not just the copyleft class.**
`wled/WLED` (19,132★) is **EUPL-1.2** — copyleft **governed by EU law**. Unremarkable for an EU
client; a question to raise before a US or APAC build.

**4. Match on `owner/name`, never on name; and verify the write path.**
`TheCraftedTech/opencue` (1★ DMX console) is not `AcademySoftwareFoundation/OpenCue` (1,010★ render
farm). `raydeoliveira/luxdmx` (0★) is not `tombueng/LuxDMX` (104★ Apache-2.0). And if an MCP server is
in the stack, **call a write tool**: this plane produced the KB's first MCP server whose dry-run tools
are free and whose live-apply tools are paid.

**Falsifiable prediction, for the next pass to check:** the fixture-definition gate will not open. By
the next time this plane is measured, GDTF Share will still require an account, and OFL's data licence
will still be unstated in-repo. If either changes, the content law has its first counter-example in
seven planes and this KB should say so loudly.

---

## Pattern 31.4 — The EN 17206-3 drone-show conformance pack (EMEA, and it has a date on it)

**Why now:** **EN 17206-3 — safety for UAS/drones in entertainment — was published by NEN on
1 October 2026**, tied to the EU Machinery Directive and Regulation 2019/945, as Part 3 of the stage
machinery family (Part 1 2020, Part 2 stage stands and truss lifts 2024). Drone shows went mainstream
with no standard; now there is one, in the single region that regulates this plane, and **nothing open
addresses it.** Dated obligations are rare in this KB and they are the easiest thing to sell.

```
[Flight plan + rig/stage plan]
      ↓
[MVR scene via pymvr (MIT)]            ← the venue, the structures, the exclusion zones, as data
      ↓
[Conformance rules as versioned code]  ← EN 17206-3 clauses, one rule per clause, each citing the clause
      ↓
[Agent: check the plan against the rules; produce a reviewed exception list, never an approval]
      ↓
[Evidence pack: plan + rule version + clause citations + named human sign-off + timestamp]
      ↓
[x42/libltc (LGPL-3.0)]                ← timecode-locked show log: what actually ran, when
```

**Hard constraints.** The human signs off; the agent assembles evidence. Encode the standard's
**clause numbers and version** in the rules so an auditor can follow a finding back to the text — this
KB's pass-27 lesson that statute belongs in versioned code applies identically to a published standard.
And state the limit honestly in the proposal: **EN 17206 adoption and legal enforceability vary by
member state, and conformance does not automatically satisfy national requirements.** The deliverable
is an evidence pack for a national authority, not a certificate.

**Sourcing caveat to resolve first:** Part 3's publication status was reported inconsistently across
sources this pass. **Verify against the CEN/NEN listing before this appears in a client document.**

---

## Pattern 31.5 — The LATAM greenfield venue stack (specify at construction, do not retrofit)

**Why LATAM specifically, and why now:** everywhere else this plane means **retrofitting** a rig and a
patch that have existed for twenty years. In LATAM the venues are being **built and bought right
now**, by a consolidating owner, at disclosed prices: Live Nation took **OCESA to 75% for $646M
(2025)** after **$400M+** for control in 2021, plus a majority of **Movistar Arena Buenos Aires**, a
stake in a major **Santiago** arena, and entry into **Peru**. **Brazil is the #9 music market
worldwide** and **Mexico entered the global top ten for the first time**, with concert attendance
**more than tripling since 2019**.

**The play:** specify the control and operations stack **at construction time**, when the network, the
patch and the documentation are being created rather than archaeologically recovered.

```
[Venue build / fit-out]
      ↓
[Network: sACN/E1.31 (ETCLabs, Apache-2.0) + RDMnet/E1.33 discovery from day one]
      ↓
[As-built rig captured as MVR (pymvr, MIT) — the documentation is born digital, not drawn later]
      ↓
[QLC+ (Apache-2.0) as the house console tier; Companion (MIT+CLA) as the operator surface]
      ↓
[Rig inventory agent of 31.2-B runs nightly: drift, firmware skew, address conflicts]
      ↓
[Touring productions arrive and import MVR instead of re-patching by hand]
```

**The commercial argument in one line:** a venue whose rig is *documented as data* turns every
incoming tour's load-in from a re-patch into an import. That is a measurable turnaround saving in the
region where touring volume is growing fastest, and it can only be built cheaply **before** the walls
close.

**One thing not to do.** Two of the plane's eight AI agents are LATAM-authored —
`Gamartinhos/lumina-ai-controller` (Portuguese) and `guillegar/show_designer` (Spanish), the only
regional concentration in any agent layer this KB has measured. **Both are unlicensed**: one has no
licence file, the other reports `NOASSERTION`. The appetite is local and already demonstrated, which
is a reason to engage the authors — **contribute a licence upstream, or rebuild the idea on QLC+. Do
not fork unlicensed code silently**; with no grant, default copyright applies and all rights are
reserved.

## Pattern 32.1 — The licence-clean CTV certification harness (and the one component you must replace)

**The problem.** A client ships a streaming app to Samsung Tizen, LG webOS, Roku, Google TV, Apple
TV, Fire TV, Vidaa and an operator STB. Each app store runs its own certification. Failures are
device-specific, intermittent and reported as "it buffers on the 2021 models". They want this
automated and they want Globant to run it as a service.

**Why the obvious build is illegal.** The complete open stack exists —
[`cta-wave/dpctf-tests`](https://github.com/cta-wave/dpctf-tests),
[`dpctf-test-runner`](https://github.com/cta-wave/dpctf-test-runner),
[`dpctf-deploy`](https://github.com/cta-wave/dpctf-deploy),
[`Test-Content-Generation`](https://github.com/cta-wave/Test-Content-Generation),
[`Test-Content`](https://github.com/cta-wave/Test-Content),
[`mezzanine`](https://github.com/cta-wave/mezzanine) (all **BSD-3-Clause**, verified by reading
`LICENSE.md` on 2026-11-27) — **except the component that produces the verdict.**
[`cta-wave/device-observation-framework`](https://github.com/cta-wave/device-observation-framework)
is **Apache-2.0 + Commons Clause**, and the clause names *"fees for hosting or consulting/ support
services"* as prohibited "Sell"ing. **A paid Globant certification service built on it breaches its
licence.** This is not a theoretical reading — it is the clause's own example list.

**Wire it together.**
1. **Harness:** `dpctf-deploy` + `dpctf-test-runner` + `dpctf-tests` (BSD-3). Serves conformance
   pages to the device under test; BSD-3 permits commercial service use without condition.
2. **Content:** `Test-Content-Generation` → `Test-Content`, from `mezzanine` sources (BSD-3). Gives
   frame-accurate, annotated vectors — the only way a stall can be attributed rather than guessed.
3. **Capability baseline:** [`cta-wave/WMAS`](https://github.com/cta-wave/WMAS) (20★, pushed
   2026-11-25) for the Web Media API surface a TV must expose, plus
   [`ott_device_matrix`](https://github.com/streaming-video-technology-alliance/ott_device_matrix)
   (8★) as the per-device capability map. ⚠️ **`ott_device_matrix` has no licence file** — read it,
   do not redistribute it; rebuild the matrix as client-owned data.
4. **⛔ Observation / verdict — DO NOT USE `device-observation-framework` in a paid engagement.**
   Build this layer yourself: it is the billable differentiator *and* the licence-blocked one, which
   is not a coincidence. Implementation: capture playback with the client's own harness, derive
   observations from the `mezzanine` annotations, and express pass/fail against
   `R4WG20-QoE-Metrics`' definitions (28★, dormant since 2019 — **the vocabulary is free, the
   judgment is yours**).
5. **Drive the device:** [`mozarkai/optics-framework`](https://github.com/mozarkai/optics-framework)
   (Apache-2.0, 104★) for Android TV / Tizen / webOS, with OCR + image-match locators because TV
   UIs expose no accessibility tree. Add
   [`takahirom/arbigent`](https://github.com/takahirom/arbigent) (Apache-2.0, 657★) for scenario
   decomposition of D-pad flows.
6. **Deploy/debug loop:** [`Braggiouy/ctv-bridge`](https://github.com/Braggiouy/ctv-bridge) (MIT,
   12★) or [`skdonthi/tv-mcp`](https://github.com/skdonthi/tv-mcp) (MIT, 6★) to put the coding agent
   in front of real Tizen/webOS hardware. Absorb as reference code — 18 stars combined.
7. **Roku, separately:** [`rokucommunity/brighterscript`](https://github.com/rokucommunity/brighterscript)
   + [`roku-deploy`](https://github.com/rokucommunity/roku-deploy) + [`roku-debug`](https://github.com/rokucommunity/roku-debug)
   (all MIT, all pushed within a week of this pass). Roku OS is closed; this volunteer toolchain is
   the entire open surface for a top-two US platform.

**Licence gate before quoting.** `grep -ri "commons clause" */LICENSE*` across every dependency.
Keep `tvdoctor` (**AGPL-3.0**) internal-only — it is an MCP server, so hosting it for a client
triggers source provision; its deterministic D-pad exploration is worth having in-house.

**What to sell.** Not "we automate certification" — the verdict logic is the asset. Sell
**client-owned pass/fail criteria** plus the harness that feeds them, and the per-store submission
evidence pack. The BSD-3 layers make the harness cheap; the Commons Clause is the reason the
judgment layer is worth money.

## Pattern 32.2 — The CMCD steering agent: the unbuilt product this plane is waiting for

**The gap, measured.** There is **no public open-source multi-CDN steering implementation** (four
slugs probed 2026-11-27, four 404s). But the entire input vocabulary is standardised and permissive,
and the players already emit it.

**Wire it together.**
1. **Telemetry in:** enable **CMCD** in the player. `dash.js` v5 emits CMCD v2 keys (`ltc`, `msd`);
   `shaka-player` has an open PR for the CMCD parameters of **ISO/IEC 23009-1:2026 Annex K**
   (manifest-signalled configuration). Spec: [`cta-wave/common-media-client-data`](https://github.com/cta-wave/common-media-client-data)
   (⚠️ no licence file — it is a spec to implement, not code to copy).
2. **Parse and normalise:** [`streaming-video-technology-alliance/common-media-library`](https://github.com/streaming-video-technology-alliance/common-media-library)
   (**Apache-2.0**, 86★, pushed 2026-11-23) — the cross-player CMCD/CMSD helpers. Custom keys via
   [`common-media-client-data-custom-keys`](https://github.com/streaming-video-technology-alliance/common-media-client-data-custom-keys)
   (MIT, 2★).
3. **Server side:** CMSD ([`common-media-server-data`](https://github.com/cta-wave/common-media-server-data), 25★)
   for origin/CDN hints, and [`OC-API`](https://github.com/streaming-video-technology-alliance/OC-API)
   (**MIT**, 4★) if Open Caching is in play (CDNI: RFC 8006/8007/8008/8804 + SVTA extensions).
4. **The agent — this is the product.** Consume per-session CMCD, score each CDN against QoE
   definitions from [`R4WG20-QoE-Metrics`](https://github.com/cta-wave/R4WG20-QoE-Metrics) (28★,
   **dormant 7.7 years**), and emit **HLS/DASH content-steering** responses. Steering *consumption*
   is already supported in `hls.js`, `dash.js`, `shaka-player` and Media3 — **so the client side is
   free and only the decision server is missing.**
5. **Cost lever:** add [`Novage/p2p-media-loader`](https://github.com/Novage/p2p-media-loader)
   (Apache-2.0, 1,738★) for peer-assisted delivery — the only open lever on egress in this plane.

**Why it is defensible.** The standards are published, the players implement the client half, and
the metrics spec has been unmaintained since 2019. Nobody has shipped the brain openly. ⚠️ Do not
promise a bandwidth-saving number: the "35–45% from AV1 + per-title + AI preprocessing" figure in
circulation is a vendor claim this KB could not verify. Measure on the client's own traffic first.

## Pattern 32.3 — The four-region CTV app build (quote it as four builds, because it is)

**The premise.** There is **no global TV application target.** A pan-regional launch means four
interactive stacks, and the KB's own prior claim that `rdkcentral/Lightning` is "the only open
answer" to on-device execution is wrong — Lightning 2 is in maintenance and **Lightning 3 is
[`lightning-js/blits`](https://github.com/lightning-js/blits)** (Apache-2.0, 117★, pushed
2026-11-26).

| Region | Stack to target | Start from | Licence |
|---|---|---|---|
| **EMEA** | HbbTV 2.0.5 (ETSI TS 102 796 V1.8.1) + DVB-I service lists; **Operator Apps** | [`OpenRedButtonProject/orb`](https://github.com/OpenRedButtonProject/orb) (24★, pushed 2026-11-19) · [`DVBProject/DVB-I-Reference-Client`](https://github.com/DVBProject/DVB-I-Reference-Client) (74★) · [`HbbTV-Association/ReferenceApplication`](https://github.com/HbbTV-Association/ReferenceApplication) (90★) | **Apache-2.0 / MIT / MIT** |
| **North America** | ATSC 3.0 / NextGen TV + the app-store platforms (Roku, Tizen, Fire TV, Google TV) | [`openBA-NextGenTV/OpenBA-NextGenTV`](https://github.com/openBA-NextGenTV/OpenBA-NextGenTV) (MIT, 15★, ⚠️ **dormant since 2022-09-21**) + the RokuCommunity MIT toolchain | **MIT** |
| **APAC (Japan)** | Hybridcast (IPTVFJ STD-0010/0011) | [`nhkrd/hyconet4j`](https://github.com/nhkrd/hyconet4j) (15★) + [`nhkrd/antwapp4hc`](https://github.com/nhkrd/antwapp4hc) TV emulator (21★) ⚠️ **both dormant since 2021** | **MIT** |
| **LATAM (Brazil)** | TV 3.0 / DTV+ — ATSC 3.0 physical layer, **Ginga** application layer, MPEG-H audio mandatory | [`TeleMidia/ginga`](https://github.com/TeleMidia/ginga) (53★, 2024-11-25) + [`clappr/clappr`](https://github.com/clappr/clappr) (BSD-3, 7,543★, Globo) | **GPL-2.0** ⚠️ + BSD-3 |

**The shared layer (build once).** Player: `shaka-player` (Apache-2.0) or `hls.js` (Apache-2.0) on
web/HbbTV targets, `androidx/media` (Apache-2.0 — **not ExoPlayer**) on Android TV / Fire TV.
Controls: [`muxinc/media-chrome`](https://github.com/muxinc/media-chrome) (MIT, 2,776★).
App shell: `blits` (Apache-2.0) for RDK/operator boxes, [`enactjs/enact`](https://github.com/enactjs/enact)
(Apache-2.0, 347★) for webOS, [`react-native-tvos`](https://github.com/react-native-tvos/react-native-tvos)
(MIT, 1,432★) for Apple TV + Android TV from one codebase.

**⚠️ Two scoping warnings that decide whether this project is profitable.**
1. **The Brazilian branch is GPL-2.0.** Ginga is the application layer of DTV+; a proprietary
   deliverable that links it inherits GPL obligations. Keep Ginga-facing code in a separate process
   and talk to it over IPC, or scope the Brazilian app as a distinct, differently-licensed artefact.
2. **The regional reference implementations are specifications with code attached, not SDKs.** Six
   of the twelve regional repos are over a year stale; the NA and APAC ones are 4–5 years cold.
   Budget to **adopt and maintain** them. Do not put them on a dependency list and assume upstream
   fixes will arrive.

## Pattern 32.4 — The 20-minute licence gate for any CTV, player or device proposal

Run this before a single estimate goes into a deck. It catches every trap this pass recorded.

1. **`grep -ri "commons clause" **/LICENSE*`** on every dependency. One hit kills a paid-service
   model. Known hit: `cta-wave/device-observation-framework`. (Known clean: all `dpctf-*`,
   `Test-Content*`, `mezzanine`, SVTA `common-media-library`.)
2. **Treat `NOASSERTION` / `NONE` as "unread", never as "unlicensed".** Eight cases this pass; all
   eight resolved by reading the file. Probe `LICENSE`, `LICENSE.md`, `LICENSE.txt`, **`license.txt`
   (lowercase)**, `COPYING`, **`COPYING.md`**, on `main` *and* `master`.
3. **If no licence file resolves, read the README before concluding anything.** `webosose/build-webos`
   carries its full Apache-2.0 grant and `SPDX-License-Identifier` in the README with no licence
   file at all. Control the probe with `README.md`: a 200 there plus 404s on licence names means
   **your filenames are wrong or the grant is elsewhere**, not that the project is unlicensed.
4. **If the README points off-site, stop.** `axiomatic-systems/Bento4` (2,530★) says only
   *"dual-license model… see the About Page"*. The terms are not in the repository. **Resolve them
   against the vendor before shipping, and never let "it's open source" clear procurement.**
5. **Check the `description` field and `pushed_at`, not the stars.** `plyr` (29,977★) is deprecated
   into Video.js 10; `ExoPlayer` (21,935★) is "deprecated and stale"; `react-tv` (2,033★) is
   archived; `mautilus/sdk` (102★) is 9.5 years dead. ~54,000 stars of tombstones in one plane.
6. **Check whether the *list* you are citing is licensed.** `vitalets/awesome-smart-tv` (1,480★) has
   no licence and no README statement — research input only. `tugkanboz/awesome-ai-testing` is
   CC0-1.0 and reusable.
7. **Confirm the conformance suite is obtainable at all.** The **HbbTV test suite is members-only**
   (licensed to member companies, tracked in a members-only SVN). If the client needs certified
   HbbTV output, membership or a registered test centre is a line item, not an assumption.

---

## Pattern 51 — AMEC-conformant earned-media intelligence, self-hosted and permissively licensed

**Why this pattern exists.** Gartner's first PR & Media Monitoring Magic Quadrant (2026-10-20) names
**outcome-based earned-media measurement** a reshaping force; AMEC's Integrated Evaluation Framework
is the free, settled standard for it; and **no open-source implementation of that framework exists**
(verified 2026-11-27). Meanwhile the collection substrate beneath it is Apache-2.0/MIT and receiving
commits daily. So: the budget is agreed, the method is public, the plumbing is free, and the thing in
the middle is missing. That gap is the deliverable.

**Licence posture: every shipped component below is MIT, Apache-2.0, BSD or public domain.** The
AGPL-3.0 options are listed only as separately-deployed services, and the one non-commercial
component is excluded by name.

```
 COLLECT                 EXTRACT              RESOLVE           INDEX              MEASURE
 feedparser   (BSD-2)    trafilatura (Ap-2)   stanza  (Ap-2)    story-indexer      AMEC:
 rss-bridge   (Unlic)    fundus      (MIT)    NER →              (Apache-2.0)      outputs →
 miniflux     (Ap-2)     newspaper4k (MIT)    brand/title/      meilisearch        out-takes →
 changedetection.io      tika        (Ap-2)   person            (MIT)              outcomes →
              (Ap-2)                                                               impact
 faster-whisper (MIT)    ── audio → text ──→                   ▲                   + PESO tags
 auto-archiver  (MIT)    ── evidence capture ─────────────────→ │
                                                    ┌──────────┴──────────┐
                                                    │ DEDUPE & CLUSTER    │ ← do this BEFORE
                                                    │ (story-level)       │   any metric
                                                    └─────────────────────┘
```

### Wiring, step by step

1. **Collect.** `miniflux` (Apache-2.0) or `feedparser` (BSD-2) for feeds; `rss-bridge` (Unlicense)
   to manufacture feeds for outlets that publish none; **`changedetection.io` (Apache-2.0)** to watch
   pages that are not feeds at all — competitor press rooms, regulator notices, rival newsrooms.
   `GNews` (MIT) for Google News queries, with the warning in step 3.
2. **Bring broadcast in.** **`faster-whisper` (MIT)** transcribes radio, TV and podcast audio so
   spoken mentions land in the same index as print. **This is the step that makes it *media*
   monitoring rather than *web* monitoring**, and it is the cheapest differentiator in the pattern —
   the commercial vendors charge separately for broadcast.
3. **⚠️ Deduplicate and cluster into stories BEFORE computing anything.** This is the pattern's
   load-bearing warning and it is measured, not theoretical: `pr-radar`'s README documents that
   without deduplication **one article appears in up to 14 Google News market editions**, inflating
   share of voice by an order of magnitude. Any metric computed on raw collected items is wrong.
   Cluster to the *story*, then count stories, not rows.
4. **Extract.** `trafilatura` (Apache-2.0) as the general extractor; **`fundus` (MIT)** where the
   outlet list is known and finite — which in client monitoring it almost always is — because
   publisher-specific parsers beat generic heuristics. `tika` (Apache-2.0) for the PDF/DOCX/scanned
   material that arrives in every real engagement.
5. **Resolve entities.** **`stanza` (Apache-2.0, 70+ languages)** for NER → brands, titles, people,
   competitors. A "mention" only becomes a *mention of the client* here. Permissive **and**
   multilingual, which on this plane is rare.
6. **Index.** **`story-indexer` (Apache-2.0)** as the corpus backbone — Media Cloud's live pipeline,
   proven past a billion stories. ⚠️ Use `story-indexer`, **not** `web-tools`: same org, same licence,
   but the UI layer has been dormant since 2023-12-14. Build your own surface over `meilisearch`
   (MIT) or OpenSearch. **Verify the licence yourself**: Media Cloud is widely mis-reported as
   AGPL-3.0 from a stale fork; both live repos read Apache-2.0.
7. **Score sentiment — and here you must build.** `NewsMTSC` (MIT *for new files only*) is the right
   *primitive*: target-dependent sentiment, i.e. polarity **toward the named brand**, not
   whole-document polarity. It is 16 months dormant. **⛔ Do NOT use `pysentimiento` in any paid
   engagement** — its licence is non-commercial/research-only, and its models additionally carry TASS
   and SemEval dataset terms. For Spanish/Portuguese (and for Indic/SEA, where nothing permissive
   exists), fine-tune **XLM-R on DimABSA (SemEval-2026)** — the published route `pr-radar` used,
   reporting 6–53% lower error than baseline on all 10 official test sets. The output is yours and
   permissively licensed.
8. **Measure to the standard, not to AVE.** Map to AMEC's **outputs → out-takes → outcomes → impact**
   with **PESO** tags. Share of voice is an *output* and belongs at the bottom of the hierarchy, with
   outlet tier and message penetration attached — never volume alone. **Do not ship AVE**; the
   Barcelona Principles reject it and a first-edition Gartner MQ now names outcome-based measurement
   as the market direction.
9. **Capture evidence where it must survive deletion.** `auto-archiver` (MIT) for hashed, timestamped
   captures — crisis monitoring, regulatory complaints, litigation. `ArchiveBox` (MIT) if the archive
   ships **inside** the product; `browsertrix-crawler` (AGPL-3.0) only as a separate internal service
   when capture fidelity matters more than licence freedom.
10. **Brief generation, with the check that makes it usable.** `pr-radar`'s design decision is the one
    to copy: a small local model drafts the weekly brief, and **every number, outlet and
    recommendation is rule-checked against the underlying data before publication**. Its measured
    effect — first drafts passing all checks went from 1 of 21 to 11 of 21, level with a model more
    than twice the size. **The rule-check layer, not the model size, is what makes an LLM brief
    shippable to a comms director.**

### Licence ledger for this pattern

| Keep inside the deliverable | Deploy as a separate service only | Never ship |
|---|---|---|
| feedparser (BSD-2), rss-bridge (Unlicense), miniflux (Ap-2), changedetection.io (Ap-2), trafilatura (Ap-2), fundus (MIT), newspaper4k (MIT), tika (Ap-2), scrapy (BSD-3), stanza (Ap-2), story-indexer (Ap-2), meilisearch (MIT), faster-whisper (MIT), auto-archiver (MIT), ArchiveBox (MIT), huginn (MIT), NewsMTSC (MIT, new files only) | FreshRSS (AGPL-3.0), RSSHub (AGPL-3.0), searxng (AGPL-3.0), browsertrix-crawler (AGPL-3.0), radar-intelligence (AGPL-3.0) | ⛔ **pysentimiento** — non-commercial/research only, plus TASS + SemEval dataset terms on the models |

### Regional variants

- **EMEA:** deploy entirely EU-resident. The sovereignty requirement (DPP European Media Trends 2026)
  is satisfiable by construction here, and **Europe Media Monitor is not forkable** — so this is a
  build, not a procurement. Public broadcasters (EBU members) are the first buyers.
- **LATAM:** step 7 is the engagement. An MIT/Apache es/pt **news** sentiment model does not exist;
  the only good library is non-commercial. Build it, and the asset is reusable across every
  Spanish- and Portuguese-language client.
- **APAC:** self-hosting answers India's DPDP residency pressure directly. Vernacular sentiment
  (Hindi, Bahasa, Thai, Vietnamese, Japanese) has **no permissive option found this pass** — same
  build as LATAM, same XLM-R route, different corpora. Lead with enablement: over half of APAC PR
  professionals report using AI without strategic adoption or structured training.
- **North America:** lead with **"own the corpus, rent the analysis."** Cision holding wire +
  clipping + listening leaves clients with no leverage and no portable history; a permissive
  collection tier restores both without forcing them to drop their analysis vendor on day one.

---

## Pattern 34.1 — The self-hosted GIVT gate in front of Prebid Server (the one build with no licence cost and a measurable return)

**Why.** Invalid traffic runs **18–21% of programmatic impressions globally**, 32–41% on Mexican and
Brazilian mobile/CTV inventory, and up to 40% on Southeast Asian open exchange. The accredited remedy
costs money and the accredited scope only *requires* GIVT anyway. **GIVT is the part you can build, and
it is the part the accreditation actually mandates.**

```
                       ┌─────────────────────────────────────────┐
  inbound request ───► │ CrowdSec (MIT, 15,814★)                  │  crowdsourced malicious-IP
                       │  + X4BNet/lists_vpn  (datacenter/VPN)    │  + datacenter ranges
                       └───────────────┬─────────────────────────┘
                                       ▼
                       ┌─────────────────────────────────────────┐
                       │ Coraza (Apache-2.0, 4,061★) embedded     │  OWASP CRS rules
                       │  + coreruleset (Apache-2.0, 3,376★)      │  INSIDE the ad server
                       └───────────────┬─────────────────────────┘
                                       ▼
                       ┌─────────────────────────────────────────┐
                       │ crawler-user-agents (MIT, 1,416★)        │  declared-bot classification
                       │  + isbot (Unlicense) + uap-core (Ap-2.0) │  ⚠ NOT ua-parser-js (AGPL-3.0)
                       └───────────────┬─────────────────────────┘
                                       ▼
                       ┌─────────────────────────────────────────┐
                       │ ALTCHA (MIT, 2,923★) — only on suspicion │  PoW human check, in-region
                       └───────────────┬─────────────────────────┘
                                       ▼
                       ┌─────────────────────────────────────────┐
                       │ prebid-server (Apache-2.0, 595★)         │  auction + schain enforcement
                       └───────────────┬─────────────────────────┘
                                       ▼
                       ┌─────────────────────────────────────────┐
                       │ Jitsu (MIT) or Matomo (GPL-3.0)          │  first-party counting you own
                       └─────────────────────────────────────────┘
```

**Wiring notes that decide whether this works.**
- Use **Coraza**, not ModSecurity, when the filter must live *inside* a Go ad server — Coraza is a
  library, ModSecurity is a proxy module. Same CRS rules either way.
- **`uap-core` (Apache-2.0, 827★), never `faisalman/ua-parser-js` (AGPL-3.0, 10,217★).** Same lineage,
  and the AGPL network clause fires on a hosted service. This is the single most likely licence
  mistake on this plane.
- `lists_vpn` and `blocklist-ipsets` have **no licence file**. Treat them as third-party data of
  unclear provenance: consume at runtime, do not redistribute, document the dependency.
- **Matomo is GPL-3.0** — deploy it as a service, do not link it into a product. **Jitsu is MIT** and
  is the choice if the collector ships inside something you sell.

**What to promise.** GIVT removal you control and can explain, at zero licence cost, with the
methodology documented. **What not to promise:** an MRC-accredited number (see 34.4), SIVT coverage
(see 34.2), or parity with a verification vendor.

---

## Pattern 34.2 — The honest SIVT conversation, with the evasion table attached

**Why.** This is a sales-integrity pattern, and it exists because the alternative is a deliverable that
fails in production. Sophisticated invalid traffic is now generated by **MIT-licensed, actively
maintained, AI-agent-oriented stealth browsers**, and the open-source defence is client-signal matching
— precisely what those tools are built to defeat.

| Side | Query | Repos | Top-8 stars |
|---|---|---|---|
| **Attack** | `bypass bot detection` | 245 | **18,425** — and **51,518** counting [CloakHQ/CloakBrowser](https://github.com/CloakHQ/CloakBrowser) (MIT, 33,093★) |
| **Defence** | `bot detection library` | 91 | **2,461** |

**The recipe is a decision procedure, not a stack:**

1. **Separate the ask.** GIVT → Pattern 34.1, build it, it works. SIVT → you are buying, not building.
2. **If the client must buy**, qualify the vendor against the **MRC accreditation letters** (free,
   public, primary): does the contract cover SIVT, or only the GIVT the accreditation requires?
   HUMAN holds GIVT **and** SIVT under the IVT 2.0 addendum (letter 2026-04-14). Many do not.
3. **If the client wants to build anyway**, the only defensible open starting point is the **Nameles
   method** ([Nameles-Org/Nameles](https://github.com/Nameles-Org/Nameles), Apache-2.0, 72★) — entropy-based
   IVT detection and pre-bid filtering, published and permissive. ⚠️ **Last pushed 2019-09-06.** Port
   the method, do not deploy the code.
4. **Do not reach for the Kaggle corpus and call it a model.** The two highest-starred open ad-fraud ML
   artifacts ([flowlight0](https://github.com/flowlight0/talkingdata-adtracking-fraud-detection) 226★,
   [ShawnyXiao](https://github.com/ShawnyXiao/2018-Kaggle-AdTrackingFraud) 72★) are solutions to the
   **2018 TalkingData contest.** There is no open labelled IVT dataset; the labels are the product.
5. **Put the table above in the proposal.** A client who understands that the attack side is
   7–21× better resourced will fund the right thing. One who does not will blame the detector.

---

## Pattern 34.3 — The supply-path audit: the declaration graph, walked end to end

**Why.** `ads.txt` / `sellers.json` declare who may sell inventory and who those sellers are. Almost
nobody walks the whole graph, and supply-path optimisation has **zero open-source tooling**
(53 repositories searched; all logistics and crypto). This is a greenfield deliverable buildable in days.

```
publisher domain
   │
   ├─► ads.txt  /  app-ads.txt
   │     └─ parse ──────────────► InteractiveAdvertisingBureau/ads.txt-parser  (Apache-2.0, 37★)
   │                              apti-jp/adstxt-validator               (MIT, 0★, TS)
   │
   ├─► each declared ad system's sellers.json
   │     └─ crawl + recurse ────► adops-tool/SPO-sellers-json-crawler    (Apache-2.0, 0★, async Py)
   │                              ↳ traverses ads.txt → app-ads.txt → sellers[].domain
   │
   ├─► mobile inventory
   │     └─ store + SDK graph ──► appgoblin-dev/adscrawler               (MIT, 36★)
   │
   ├─► anomaly rules ──────────► Yash-Vekaria/ad-inventory-fraud-measurement (MIT, 7★)
   │                              ↳ the published METHODOLOGY for ads.txt/sellers.json fraud
   │
   └─► spot-check in-browser ──► Chrome-Extensions-labs/Sellers.json-Inspector (GPL-3.0, 6★)
                                  ↳ soft-404s, commented-out lines, OWNERDOMAIN mismatches
```

**The checks that find real money:** DIRECT declared as RESELLER and vice versa; a `seller_type` in
`sellers.json` that contradicts the `ads.txt` relationship; a first hop that is not DIRECT; seller IDs
present in `ads.txt` and absent from the corresponding `sellers.json`; `OWNERDOMAIN` mismatches;
soft-404 `ads.txt` endpoints returning HTML 200 (the most common silent failure).

**Then enforce it where it can be enforced:** `schain` in **self-hosted Prebid Server** (Apache-2.0,
595★). ⚠️ `schain`, `sellers.json` and `supply path` were at **0 mentions** in this KB before this
pass, and SPO has no tooling — so this pattern competes with spreadsheets, not with products.

⚠️ **Licence gate before you ship any of it:**
`InteractiveAdvertisingBureau/adstxtcrawler` (202★) has **no licence file** and declares BSD-2-Clause
**in README prose only**; the Chrome extensions are **GPL-3.0 and AGPL-3.0** (use them, do not vendor
them); `KONTRUSTMEDIA/adsdb` ships data with **no grant at all**.

---

## Pattern 34.4 — The 20-minute accreditation gate for any ad-integrity, verification or consent proposal

Run this **before** writing a statement of work. Every question separates something buildable from
something that requires a third party's acceptance — the distinction this plane is built on.

| # | Question | If the answer is… | Then |
|---|---|---|---|
| 1 | Does the IVT number have to be **accredited**, or just correct? | Accredited | You are integrating a vendor. Scope diligence (34.5), not detection. |
| | | Correct | Pattern 34.1. Build it. |
| 2 | **GIVT or SIVT?** | GIVT | Buildable; it is also all the MRC *requires*. |
| | | SIVT | Buy. Attach the evasion table (34.2). |
| 3 | Viewability on **web**, or **in-app / CTV**? | Web | [OM-JSClients](https://github.com/InteractiveAdvertisingBureau/Open-Measurement-JSClients), Apache-2.0, self-host. |
| | | In-app / CTV | **Tools Portal download + Tech Lab compliance programme.** No open implementation exists. Integrate a certified ad SDK. |
| 4 | Does the consent string have to be a **valid TCF string** EU SSPs honour? | Yes | A **CMP ID registered with IAB Europe** is required. `iabtcf-es` (Apache-2.0) is the codec, not the registration. |
| | | No, we need lawful consent capture | `cookieconsent` (MIT, 5,786★) + `iabtcf-es`. Fully buildable. |
| 5 | Is **brand safety** conformance to a standard, or to the client's policy? | "GARM conformance" | ⚠️ **Impossible to certify.** GARM was discontinued Aug 2024 and the WFA reportedly agreed never to revive it. No maintaining body, no certifier. |
| | | The client's own policy | Buildable, and the better engagement: classify against the **IAB Content Taxonomy (CC BY 3.0, free)**, deliver the client's documented policy + the classifier. |
| 6 | Does an **accredited bot list** have to be the source of truth? | Yes | **$5,000 / $7,500 / $15,000 a year**, signed Data Subscription Agreement, revocable grant. Budget it; use [snowplow/iab-spiders-and-robots-java-client](https://github.com/snowplow/iab-spiders-and-robots-java-client) (Apache-2.0) as the client. |
| | | No | `crawler-user-agents` (MIT) + `isbot` (Unlicense) + `device-detector` (LGPL-3.0) + CrowdSec (MIT). Free. |
| 7 | Will this be hosted **for** the client? | Yes | ⚠️ Remove **rudder-server** (Elastic License 2.0 — managed service is the prohibited use) and **ua-parser-js** (AGPL-3.0). Check `ee/` if PostHog is in scope. **Resolve licences per component, not per organisation: `snowplow/snowplow` is Apache-2.0 and `snowplow/enrich` is the Snowplow Limited Use License.** |
| 8 | Which **region** is the data in? | APAC / LATAM | A US vendor SDK is a **PIPL cross-border** problem in China and a **DPDPA localisation** problem in India. Self-hosting is frequently the only lawful option, not a cost choice. |

---

## Pattern 34.5 — The vendor-accreditation diligence service (no model, no data licence, no competitor)

**Why.** Large advertisers pay for verification without knowing what the accreditation covers. Every
input is **free, public and primary**, and this pass found nobody selling it.

**Inputs (all free):** MRC accreditation letters and quarterly status updates (e.g. HUMAN's
2026-04-14 letter; the Q2 2026 update, 2026-07-14) · TAG Certified Against Fraud registry · the
client's verification contracts and vendor-reported dashboards · Pixalate's quarterly regional
benchmarks (NA / EMEA / APAC / LATAM) as an external comparator.

**The deliverable, four tables:**
1. **Scope map.** For each contracted vendor: accredited for GIVT only, or GIVT **and** SIVT? Under
   which addendum, as of which letter date? *(Most buyers have never seen this distinction.)*
2. **Gap statement.** The invalid traffic the client is paying to remove that falls **outside** the
   accredited scope — stated as a share of spend.
3. **Methodology reconciliation.** Why the client's vendor dashboard disagrees with the public
   benchmarks. The disagreement is structural, not error: loss estimates on this plane span
   **$63B–$165B** for overlapping periods, and **DoubleVerify reports IVT down 41%/45% YoY in NA/EMEA
   while Anura reports global IVT rising 26%→40% during 2026.** Two vendors, opposite directions.
4. **Buy / build line.** Mapped straight off Pattern 34.4.

**Regional variants that change the lead:**
- **North America** — lead with table 1. The accreditation exists, the client has not read it, and
  ⚠️ GroupM reportedly now mandates TAG CAF for programmatic partners (single secondary source —
  verify) which turns certification into a condition of trading.
- **EMEA** — lead with the **DSA Article 39** repository obligation instead: a peer-reviewed study
  found **only 17 of 24 obliged services (70.8%) had a public ad repository by April 2026**, and the
  Commission's **call for evidence on technical guidelines closes 2026-12-02**. Add the Belgian Market
  Court ruling of **2026-01-07** (IAB Europe not necessarily a joint controller for TCF processing) —
  which concentrates controllership on the party running the CMP, i.e. the client.
- **APAC** — lead with **a measurement baseline the client owns**, because the vendor benchmarks
  contradict each other (Lunio puts India *lowest* at 5.50%, Pixalate puts India *highest* at 19% web /
  42% app). Then the lawfulness argument: PIPL and DPDPA make self-hosting the compliant path.
- **LATAM** — lead with the **free GIVT gate** (34.1), because there is **no accreditation body in the
  region to accredit against** — searched 2026-11-27: nothing from CONAR, IAB Brasil or Mexican
  regulators on ad fraud or verification. Then position ANPD readiness: Brazil's **2026–2027 priority
  map includes five enforcement activities on secondary use of personal data for targeted advertising,
  especially profiling, scheduled for H1 2027** — an 18-month runway to sell into.

---

## Pattern 34.6 — Build on AAMP, not ARTF: the agentic-advertising window

**Why.** The agentic-advertising layer is **nine repositories, 91 stars, four pushed in November 2026**,
and for the first time in 34 planes the standards body shipped the agent framework before the market
shipped a product. That window closes.

| Component | Repo | License | Verdict |
|---|---|---|---|
| Messaging protocol | [IABTechLab/AAMP](https://github.com/IABTechLab/AAMP) | **Apache-2.0**, 28★, 2026-11-02 | ✅ **Build here.** |
| Real-time framework | [IABTechLab/agentic-real-time-framework](https://github.com/IABTechLab/agentic-real-time-framework) | spec CC BY 3.0 / impl **AGPL-3.0**, 35★, 2026-11-04 | ⚠️ Implement the **spec** (CC BY 3.0); do not deploy the AGPL Go reference as a service. |
| Proposal exchange | [IABTechLab/OpenProposal](https://github.com/IABTechLab/OpenProposal) | Apache-2.0 **scoped to `scripts/` + `workflow/`**, 11★ | ⚠️ Read the scope; the repo is not uniformly licensed. |
| Orientation map | [franks33/agentic-advertising-stack](https://github.com/franks33/agentic-advertising-stack) | **CC0-1.0**, 4★ | ✅ Read first — public domain, one sitting. |
| Buy-side reference agent | [scumunna/adcp-trader](https://github.com/scumunna/adcp-trader) | MIT, 1★ | Study: trader judgment plus hard guardrails. |
| Agent skills | [scumunna/programmatic-skills](https://github.com/scumunna/programmatic-skills) · [adops-tool/AdTech-LeadGen-agent-skills](https://github.com/adops-tool/AdTech-LeadGen-agent-skills) | MIT · Apache-2.0 | DV360 operations; publisher-compliance skills. |
| ⛔ Avoid as dependencies | [IABTechLab/CoMP](https://github.com/IABTechLab/CoMP) (NONE, 6★) · [10div10/adtech-multi-agent](https://github.com/10div10/adtech-multi-agent) (NONE, 2★) | no licence | Study only. |

**The product nobody has built, and this plane makes it obvious.** The same industry is standardising
**agent-to-agent ad buying** while its **agent-driven invalid traffic** goes undetected — the best
evasion tools being 33,000-star MIT stealth browsers built explicitly for AI agents. **Wire AAMP
(Apache-2.0) to the Pattern 34.1 gate and you have the first agentic transaction layer that can
attest what it filtered**: a signed, machine-readable integrity claim travelling with the agentic bid.
`ads.cert` (Apache-2.0, 8★) is the dormant cryptographic primitive for exactly this attestation — the
one step of the chain the industry standardised and never deployed. **Combining a three-week-old
protocol with a three-year-dormant primitive is the highest-leverage composition in this KB**, and
today it has no competitor.

---

# Pass 35 patterns (2026-11-27) — the graphics desk

**Numbering note:** patterns 1–51 are taken, so this pass uses **52.x**. (Pass 33 shipped as "33",
collided, and had to be renumbered to 51 in a follow-up commit. Check the highest number before
writing, not after.)

## Pattern 52.1 — The fully permissive graphics desk: every layer named, every licence verified

**For:** a publisher or broadcaster that wants to produce daily charts and maps in-house with no
per-seat or per-view licence, and own the output.

**The stack, bottom to top — all verified 2026-11-27:**

| Layer | Repo | Licence | Why this one |
|---|---|---|---|
| Data contract | [frictionlessdata/frictionless-py](https://github.com/frictionlessdata/frictionless-py) | MIT | Declare the schema; a renamed column fails CI instead of publishing a wrong chart. **Start here — this is the step every desk skips.** |
| Clean | [OpenRefine/OpenRefine](https://github.com/OpenRefine/OpenRefine) | BSD-3-Clause | Reporters can use it without a developer. |
| Script | [wireservice/csvkit](https://github.com/wireservice/csvkit) + [agate](https://github.com/wireservice/agate) | MIT | Deadline-shaped CLI and library. |
| Serve/explore | [simonw/datasette](https://github.com/simonw/datasette) | Apache-2.0 | Publishes the data behind the story as a queryable API. |
| Chart spec | [vega/vega-lite](https://github.com/vega/vega-lite) | BSD-3-Clause | Declarative JSON — the only mainstream permissive target you can **validate before rendering**. |
| Chart render (alt) | [apache/echarts](https://github.com/apache/echarts) | Apache-2.0 | When you want batteries included and a patent grant. |
| Simplify geography | [mbloch/mapshaper](https://github.com/mbloch/mapshaper) | MPL-2.0 | 60 MB shapefile → 200 KB web map, topology intact. Invoke it; don't paste its source into proprietary files. |
| Basemap | [protomaps/basemaps](https://github.com/protomaps/basemaps) | BSD-3-Clause | **Single-file PMTiles on static hosting — no tile server, no per-view billing.** |
| Map render | [maplibre/maplibre-gl-js](https://github.com/maplibre/maplibre-gl-js) | BSD-3-Clause | Vector rendering with no vendor key in the page. |
| Scroll narrative | [russellsamora/scrollama](https://github.com/russellsamora/scrollama) or [ZeitOnline/scrolleo](https://github.com/ZeitOnline/scrolleo) | MIT | Scrollama for 6k★ of battle-testing; scrolleo for ESM-only + real TS types. |
| Editor copy | [nprapps/copytext](https://github.com/nprapps/copytext) or ArchieML ([newsdev/archieml-js](https://github.com/newsdev/archieml-js)) | MIT / Apache-2.0 | **An editor changes story text without a deploy.** The cheapest goodwill in the build. |
| Annotation for print/mobile | [newsdev/ai2html](https://github.com/newsdev/ai2html) | Apache-2.0 | Illustrator → responsive HTML with **live text, not a flattened image** (accessibility, not just fidelity). |
| Embed | [nprapps/pym.js](https://github.com/nprapps/pym.js) | MIT | Resizes correctly inside someone else's CMS. |
| Build/publish | [the-pudding/svelte-starter](https://github.com/the-pudding/svelte-starter) + [observablehq/framework](https://github.com/observablehq/framework) | MIT / ISC | Static output; no live backend to fall over when the story lands. |

**Wire-up, in order:** schema (`frictionless describe` → commit the descriptor) → clean (OpenRefine,
export the operation history as the audit trail) → `frictionless validate` in CI → chart as a
Vega-Lite **spec file in the repo**, never inline config → geography through mapshaper into PMTiles →
page from `svelte-starter` with scroll steps → copy from a sheet via `copytext` → `pym.js` embed.

**The licence sentence for the SOW:** every component above is ISC, MIT, BSD-2/3-Clause or
Apache-2.0, except mapshaper (**MPL-2.0**, per-file weak copyleft — invoked as a CLI, so it never
touches client source). **Zero licence cost, zero copyleft exposure in the deliverable.**

## Pattern 52.2 — Replace the hosted-embed subscription, honestly (the only build in this plane with a hard-dollar number)

**For:** a client who pays for Datawrapper/Flourish seats and asks whether it can be self-hosted.

**Say this first, because it is the whole scoping decision:** **no.** Datawrapper's self-hostable core
was **archived in September 2021** (`api`, `frontend`, `chart-core`, `orm`, all within three days) and
the 1,465★ repo still carrying the name has **no licence file** and is described as "utility
functions." Flourish and Highcharts are proprietary. **There is nothing to fork.** Anyone who says
otherwise is reading a 2026 guide that is repeating a 2021 fact — several do.

**The honest comparison to put in front of the client:**

| | Keep the subscription | Build the embed service |
|---|---|---|
| Cost | ~$33–$564/month, newsroom tier | Build + maintenance, forever |
| Chart quality | Excellent, immediately | Yours to achieve |
| Non-developer editing | Solved | **The hard part — this is the product, not the chart** |
| Sovereignty / third-party JS on your page | Vendor's servers, vendor's script | Fully yours (**the EMEA-decisive column**) |
| Reader-data exposure | Vendor-dependent | None |

**Build only when the sovereignty or reader-data column decides it** — which in EMEA public-service
media it increasingly does (see `intel/market.md` pass 35, EMEA). Then the shape is:
Vega-Lite spec store + a thin editor UI + server-side render to static SVG/PNG +
[pym.js](https://github.com/nprapps/pym.js) for the responsive iframe. **Scope the editor UI as 70%
of the effort**, because for the people who use it, it is the entire product.

**The precedent that proves the gap, and the single best slide in this deck:** ABC Australia
open-sources its whole desk under MIT and *still* maintains
[abcnews/interactive-datawrapper-scrollyteller](https://github.com/abcnews/interactive-datawrapper-scrollyteller)
— an MIT wrapper whose only job is to put a **closed SaaS chart** inside their open scrollyteller. The
most open desk in the world rents the embed.

## Pattern 52.3 — The NL→chart agent that cannot hallucinate a renderer

**For:** "can an LLM make our charts?" — asked by every media client in 2026.

**The architecture, and the one rule:** the model emits a **spec**, a deterministic compiler emits the
**config**. The model never writes renderer code.
[yuqisun/chartwright](https://github.com/yuqisun/chartwright) (MIT, **0★**) is the clearest
implementation of exactly this; read it for the pattern, not as a dependency, and note its compile
target is **proprietary Highcharts**.

**The build:**
1. **Governed question → data.** [Canner/WrenAI](https://github.com/Canner/WrenAI) (Apache-2.0,
   18,413★): natural language resolves against a **semantic layer** before any SQL is emitted, so the
   agent cannot invent a column.
2. **Spec, not config.** Agent emits **Vega-Lite** (BSD-3-Clause). Validate the JSON against the
   schema and **reject it before render** — the step that makes this safe and the reason Vega-Lite
   matters more than its 5,566 stars suggest.
3. **House style as a locked layer.** Merge the validated spec with a design-token theme the agent
   cannot write to (fonts, palette, axis rules). **Author your own tokens** — `abcnews/palette` and
   `abcnews/components-dataviz` are published but **carry no licence**.
4. **Explore, don't publish.** [Kanaries/pygwalker](https://github.com/Kanaries/pygwalker)
   (Apache-2.0) in the notebook for reporters; nothing it produces goes to air unreviewed.
5. **Human gate, logged.** Spec diff + data lineage + who approved, as the publish record.
6. **Disclosure.** If a model wrote the caption or annotation, that is **synthetic text published as
   fact** — EU AI Act Article 50 plumbing applies to the chart, not just to video.

**Do not use:** [microsoft/lida](https://github.com/microsoft/lida) (MIT, 3,299★) as a dependency —
**last pushed 2024-08-08**; and keep [CJWorkbench/cjworkbench](https://github.com/CJWorkbench/cjworkbench)
out of any hosted deliverable (**AGPL-3.0**, and dormant since 2024-12-03).

## Pattern 52.4 — Election night, with the licence reality on the table

**For:** a broadcaster or publisher scoping 2026/2028 US election graphics — or any licensed-feed
results product.

**The split that governs the whole build: the data is the moat; the chart never was.**

- **Paid and unavoidable:** the tabulation feed. ABC, CBS, NBC and CNN all moved to **AP data for
  2026 and 2028**. Its only open-source client,
  [newsdev/elex](https://github.com/newsdev/elex) (Apache-2.0, 169★), has been **archived since
  2022-09-07**. civicAPI and Open America's JSON feed are **hosted services, not repositories** — no
  licence, no self-host, no SLA — so they are a fallback or a test fixture, never the spine.
  [openelections/openelections-data-us](https://github.com/openelections/openelections-data-us) is a
  historical archive for backtesting.
- **Free and complete:** the display. [d3/d3](https://github.com/d3/d3) (ISC),
  [topojson](https://github.com/topojson/topojson) (BSD) for compact boundaries,
  [mapshaper](https://github.com/mbloch/mapshaper) (MPL-2.0) to simplify them,
  [MapLibre](https://github.com/maplibre/maplibre-gl-js) + [protomaps](https://github.com/protomaps/basemaps)
  (both BSD-3) for a basemap with **no per-view cost on the one night traffic peaks**.

**The build:** licensed-feed ingestion client (schema-validated with
[frictionless-py](https://github.com/frictionlessdata/frictionless-py), **replay-tested against 2024
and 2026 results**) → immutable append-only results store → static regeneration on an interval, not
live queries → `pym.js` embeds into the CMS → race-call audit trail (who called it, on what
numbers, when).

**Sell the ingestion client, not the map.** Every US broadcaster and large regional publisher needs
exactly one, every two years, and since 2022 nobody has maintained an open one.

## Pattern 52.5 — The 15-minute licence gate for any graphics-desk proposal

Run this before the stack slide. It has caught something real in every org scanned this pass.

1. **`LICENSE` file, or nothing?** Fetch `raw.githubusercontent.com/{owner}/{repo}/{main,master}/LICENSE`
   (and `.md`, `.txt`, `COPYING`). **Two of this plane's most-recommended artifacts have no licence
   file on any branch:** `datawrapper/datawrapper` (1,465★) and `bbc/bbplot` (1,645★). **~3,000 stars
   of apparently-open tooling with no grant.**
2. **Never trust `NOASSERTION`.** Resolve it from the file. This pass: MapLibre → **BSD-3-Clause**,
   Quarto → **MIT**, ai2html/archieml-js/elex → **Apache-2.0**, guardian/frontend → **Apache-2.0**,
   mapshaper → **MPL-2.0** — and cjworkbench → **AGPL-3.0**, the one where resolving it *removes* the
   option.
3. **Never trust the launch blog either.** [tryopendata/openchart](https://github.com/tryopendata/openchart)
   was announced as MIT; the repo is **Apache-2.0**.
4. **A public repo is not a permissive repo.** [highcharts/highcharts](https://github.com/highcharts/highcharts)
   is 12,502★ with a `license.txt` pointing at a shop.
5. **Check the design system separately from the libraries.** In `abcnews`, the libraries are MIT and
   `palette` / `components-dataviz` / `svelte-scrollyteller` have **no licence**. The pieces you most
   want to reuse are the ungranted ones.
6. **Sort by `pushed_at`, never by stars.** Stars here return a museum: Chartbuilder 2,095★/**2017**,
   Idyll 2,044★/2023, bbplot 1,645★/2021, elex **archived**. Then ask the one question that separates
   abandonment from completion: **does the artifact still do its whole job?** (ArchieML and TopoJSON:
   yes — finished formats. Chartbuilder and Idyll: no — dead products.)
7. **If the metadata will not resolve, say "unknown", not "0".** `nprapps/pym.js` exists
   (`ls-remote` OK, raw MIT `LICENSE`, `package.json` v1.3.2) but returns `total_count: 0` from the
   search API — a channel limit, not an abandoned repo.

## Pattern 53 — The inbetween gate: what to promise, and what to refuse, before an AI animation statement of work is signed

**The failure this prevents.** A client asks for "AI inbetweening" because that is where the labour hours
are. The obvious repos look like an answer. They are not: the two most on-target models carry **no licence
grant at all**, the third grants MIT **only in its README**, and the one properly-licensed cartoon
interpolator has not been pushed since **2025-03-19**.

**The gate, in order.**

1. **Separate the two interpolations.** *Camera, background and held-cel motion* is a video-interpolation
   problem and is solved permissively: [Practical-RIFE](https://github.com/hzwer/Practical-RIFE) (MIT,
   1,053★, pushed 2026-08-27) or [ECCV2022-RIFE](https://github.com/hzwer/ECCV2022-RIFE) (MIT, 5,740★).
   *Line inbetweening* — new drawings between two keys — is not. **Promise the first, scope the second as
   R&D.**
2. **Licence-quarantine the line models.** [AnimeInbet](https://github.com/lisiyao21/AnimeInbet) (373★)
   and [FCVG](https://github.com/Tian-one/FCVG) (120★) have no licence file and no README grant: they may
   be *evaluated* and must not enter a deliverable.
   [AnimeInterp](https://github.com/lisiyao21/AnimeInterp) (465★) grants MIT in README prose only —
   usable only with the client's counsel accepting a prose grant, in writing, with the README commit hash
   recorded.
3. **Make ToonCrafter the baseline, and say that it is dormant.**
   [ToonCrafter](https://github.com/Doubiiu/ToonCrafter) (**Apache-2.0**, 6,071★, SIGGRAPH Asia 2024) is
   the only >1k★ cartoon interpolator with a real OSI licence. Twenty months without a push is a
   maintenance risk to state in the proposal, not to discover in month three.
4. **Wire the pipeline so the AI step is replaceable.** Keys and timing live in
   [OpenToonz](https://github.com/opentoonz/opentoonz) (BSD-3) with the exposure sheet exported via
   Pattern 55; the interpolation step is a worker behind a queue, so swapping the model is a config change.
5. **Price the clean-up, not the generation.** Every model in this plane outputs raster frames that need
   re-inking: [Anime2Sketch](https://github.com/Mukosame/Anime2Sketch) (MIT, 2,146★) for line extraction,
   [diffvg](https://github.com/BachiLi/diffvg) (Apache-2.0) to get back to vectors.
   **Do not** reach for `sketch_simplification` (755★): its licence is **academic/non-commercial only**.

**What to write in the SOW.** "Automated interpolation for camera and background motion (MIT), with
line-inbetweening as a time-boxed evaluation against ToonCrafter (Apache-2.0); no unlicensed model enters
the delivered pipeline." That sentence is defensible in procurement. "AI inbetweening" is not.

## Pattern 54 — The manga / webtoon / 漫剧 localisation line, built only from permissive parts

**Why this one is worth building first.** It is the healthiest permissive sub-plane found in this pass:
comic translation has **four stacks above 3,000★**, two of them Apache-2.0, one pushed the day of this
pass. The volume is APAC→global, and the labelling duties are already in force.

**The build.**

1. **Engine — [koharu](https://github.com/koharu-rs/koharu) (Apache-2.0, 6,853★, pushed 2026-11-27)**,
   Rust: detection → OCR → inpainting → typesetting. Alternative:
   [comic-translate](https://github.com/ogkalu2/comic-translate) (Apache-2.0, 3,024★) when a browser
   extension or desktop app is wanted.
2. **Do not link the GPL stacks.** [manga-image-translator](https://github.com/zyddnys/manga-image-translator)
   (GPL-3.0, 10,662★) and [BallonsTranslator](https://github.com/dmMaze/BallonsTranslator) (GPL-3.0,
   5,321★) are the most-starred options and the wrong ones for a closed client product. Run them as a
   separate process behind an API if the client wants their quality, and record the boundary.
3. **Production state — [Kitsu](https://github.com/cgwire/kitsu) (AGPL-3.0, 779★) operated as a service**
   by the client, never linked. Agent reads via
   [kitsu-mcp](https://github.com/EstienneG/kitsu-mcp) (MIT, 2★) — five weeks old, so vendor it.
4. **Human-in-the-loop in the artist's own tool** — [Krita](https://github.com/KDE/krita) (GPL-3.0)
   for retouch and lettering fixes; the AI assist arrives as a plugin
   ([krita-ai-diffusion](https://github.com/Acly/krita-ai-diffusion), GPL-3.0, 10,960★), which keeps the
   copyleft on the plugin side of the boundary.
5. **The disclosure layer is not optional.** Korea's AI Basic Act (in force **2026-01-22**) requires
   labelling of AI-generated content; China's labelling rules (September 2025) carry penalties to **¥50M**;
   EU **Article 50** applies from **2026-08-02**; Peru's rule covers AI-generated *or edited* content.
   Emit a per-page provenance record from the pipeline and render the market-specific label at publish
   time — one record, four renderings.

**Deliverable boundary that keeps it clean:** permissive engine in-process; GPL engines out-of-process;
AGPL platform operated, not embedded; copyleft UI extended by plugin. Four different licence strategies
in one line, which is why writing them down is the pattern.

## Pattern 55 — The exposure-sheet bridge: the one place in this KB where the open stack can shape an interchange instead of implementing one

**The opening.** **XDTS** (eXchange Digital Time Sheet) was released in 2018 by **Celsys** with **Toei
Animation**; **TDTS** is Toei's native variant; both are JSON with a text header, carrying cells,
dialogue and camerawork. The **public spec is still the November 2018 version** although Clip Studio
Paint 1.13.0 added 2D camera folders. Total world tooling: **six repositories, 32 stars**.

**The build, entirely from verified parts.**

1. **Authoring** — [Krita](https://github.com/KDE/krita) (GPL-3.0) with
   [KritaToXDTS](https://github.com/konero/KritaToXDTS) (GPL-3.0, 6★): animated paint layers out as image
   sequences **plus timing as XDTS**. For a full suite, [OpenToonz](https://github.com/opentoonz/opentoonz)
   (BSD-3) is the permissive base.
2. **Parse / emit** — [SehataKuro/xdts](https://github.com/SehataKuro/xdts) (**Apache-2.0**, 2★, pushed
   **2026-11-11**) is the only permissively-licensed XDTS/TDTS reader-writer in existence, and it is being
   worked on this month. Vendor it and pin the commit; at 2★ there is no upstream to rely on.
   [clip2xdts-rs](https://github.com/SehataKuro/clip2xdts-rs) (0★, **no licence**) shows the Clip Studio
   path but cannot be shipped.
3. **Review** — [xdts_viewer](https://github.com/opentoonz/xdts_viewer) (**BSD-3**, 22★) renders a sheet
   like paper, which is what a supervisor will actually accept.
   [vdts-editor](https://github.com/lunafuse/vdts-editor) (MIT, 0★) is a single HTML file that reads and
   writes XDTS/TDTS with revision history — a working reference for the revisioned editor nobody has built.
4. **Mind the spec delta.** The camera-folder fields added after the 2018 spec are documented only in
   [XDTS-uext](https://github.com/shun-iwasawa/XDTS-uext) — "unofficial extension", 2★, **no licence**.
   Read it for understanding; implement from observed files; **do not copy its code**.
5. **Join to production** — XDTS rows → Kitsu tasks (AGPL service) → editorial via
   [OpenTimelineIO](https://github.com/AcademySoftwareFoundation/OpenTimelineIO) (Apache-2.0, 2,122★),
   which is the only standards-backed way to hand 2D timing to an edit.

**Why it is strategically different from every other pattern in this file.** Everywhere else the open
stack implements someone else's finished standard. Here the incumbent spec is **eight years stale**, its
only extension is one individual's unlicensed repo, and the entire ecosystem is 32 stars — so a studio
that publishes a clean, permissively-licensed XDTS/TDTS library and a revisioned sheet editor becomes the
reference implementation of a format used across Japanese animation production. State the risk honestly
too: the **authority** to define the sheet belongs to Celsys and Toei, and no amount of code transfers it.

## Pattern 56 — Lip sync that survives a licence review

**The trap.** The most-starred lip-sync repo is
[Wav2Lip](https://github.com/Rudrabha/Wav2Lip) (13,291★) and its README says **"Non Commercial
Open-source Version"** beside a paid API upsell. It cannot go in a client deliverable.

**The build.**

1. **Drawn / 2D mouth charts → [Rhubarb Lip Sync](https://github.com/DanielSWolf/rhubarb-lip-sync)
   (MIT, 2,816★, pushed 2026-06-16).** Audio in, phoneme timing out, which is exactly what a 2D mouth set
   consumes. Two licence details worth quoting to a client: GitHub reports NOASSERTION only because
   `LICENSE.md` is 27,808 B of bundled third-party texts, and the licence states explicitly that **the
   lip-sync data it produces belongs to you alone**.
2. **Photoreal / live-action → [LatentSync](https://github.com/bytedance/LatentSync)
   (Apache-2.0, 6,334★).** Correct licence, wrong tool for drawn mouths; do not mix the two cases in one
   proposal.
3. **Do not propose [papagayo-ng](https://github.com/morevnaproject-org/papagayo-ng)** (294★): the
   traditional phoneme-mapping tool has **no licence file** (12 names × both branches) and was last
   pushed 2023-04-25.
4. **Wire the output into the sheet, not into a render.** Rhubarb's timing belongs in the exposure sheet
   (Pattern 55) so the mouth cells are held like every other cel, which is how a 2D unit reviews it.

## Pattern 57 — Shipping a 2D tool as a product: the copyleft wall, and the two doors through it

**The constraint, stated as a number.** Of the nine authoring repos in this plane, **seven are GPL and
two are BSD-3-Clause** — and the two permissive ones have the lowest star counts.

| Goal | Legal route | Concrete base |
|---|---|---|
| Fork a 2D tool, add proprietary AI, **ship the binary** to a client | **Only via BSD-3** | [OpenToonz](https://github.com/opentoonz/opentoonz) (8,386★) or [Tahoma2D](https://github.com/tahoma2d/tahoma2d) (699★, adds stop-motion capture) |
| Put AI in front of the artists who are already productive | **Plugin against GPL, plugin licensed separately** | [Krita](https://github.com/KDE/krita) + the proven precedent of [krita-ai-diffusion](https://github.com/Acly/krita-ai-diffusion) (10,960★) and [comfyui-tooling-nodes](https://github.com/Acly/comfyui-tooling-nodes) (683★) |
| Hybrid 2D/3D series with agent control | GPL tool, **MCP bridge is MIT** | [Blender](https://github.com/blender/blender) Grease Pencil + [mcp-for-blender](https://github.com/ahujasid/mcp-for-blender) (MIT, 35,944★) |
| Deliver playback inside a client app | **Fully permissive** | [ThorVG](https://github.com/thorvg/thorvg) (MIT) or [dotlottie-web](https://github.com/LottieFiles/dotlottie-web) (MIT) — **not** `lottie-web`, unpushed since 2025-09-01 |
| 2D skeletal animation in a shipped product | **Permissive only here** | [DragonBonesJS](https://github.com/DragonBones/DragonBonesJS) (MIT, 864★) — because [spine-runtimes](https://github.com/EsotericSoftware/spine-runtimes) requires a **paid Spine editor licence** |

**The OpenToonz footnote that belongs in the contract:** its `LICENSE.txt` grants BSD-3 for project code
but carves out `thirdparty/`, the bundled MyPaint brushes and Tahoma2D-derived portions. Resolve those
three before any redistribution — the base is permissive, the tarball is not automatically so.

## Pattern 58 — The 20-minute licence gate for any 2D animation proposal

Run this before the first estimate. It is six commands and it has caught eleven traps in this plane alone.

1. **Resolve existence, not reputation.** `git ls-remote https://github.com/<slug> HEAD`. Reputation
   lists in this plane contained repositories that do not exist, and `blender-mcp` has been **renamed** to
   `ahujasid/mcp-for-blender` (the old slug 404s).
2. **Resolve the licence from the repo, with 13 names.** `LICENSE`, `LICENSE.txt`, `LICENSE.md`,
   `license.txt`, `license`, `LICENCE`, `LICENSE.TXT`, `COPYING`, `COPYING.txt`, `COPYING.md`,
   `LICENSE-MIT`, `NOTICE`, **`EULA.txt`** — across `master` **and** `main`.
   `EULA.txt` is the name that matters most: it is how a 41,192★ repo (`aseprite`) looks unlicensed when
   it is in fact commercially forbidden.
3. **If no file resolves, read the README before recording a zero.** `AnimeInterp` grants MIT in prose;
   `ebsynth` dedicates itself to the public domain in prose. Fetch `README.md` at the same path first — a
   200 there proves the channel works and your *names* failed, not the repository.
4. **Treat `NOASSERTION` as "parser gave up", then read the file.** In this plane it flagged four
   permissive projects (`opentoonz`, `tahoma2d`, `xdts_viewer` → BSD-3; `rhubarb-lip-sync` → MIT) whose
   licence files simply open with third-party notices.
5. **Check liveness and quarantine the dead.** `enve` (GPL-3.0) is **archived**;
   `SVGAPlayer-Android` (Apache-2.0) is **archived**; `lottie-web` is MIT and **14 months stale**. A valid
   licence on a dead project is not a dependency.
6. **Read the terms of what you *link*, not what you clone** (the Chromaprint rule, pass 5): for every
   native dependency resolve the linked libraries' licences, and for every model resolve the weights'
   terms separately from the code's.

**The eleven findings this gate produces in this plane, as a checklist to hand a reviewer:** `aseprite`
(EULA), `spine-runtimes` (paid editor licence), `remotion` (fee-bearing above a headcount),
`sketch_simplification` (non-commercial academic), `Wav2Lip` (non-commercial), `bilibili/ailab` (no
grant), `AnimeGANv2`/`v3` (no grant), `storyboarder` (no grant — a blog post instead),
`XDTS-uext` (no grant), `enve` + `SVGAPlayer-Android` (archived), `lottie/lottie-spec` (spec text's
licence unresolved).

## Pattern 59 — Licensed-merchandise royalty assurance: reconcile the statement against the marketplace

**The problem.** A licensor is paid a royalty on reported net sales. The report comes from the licensee.
Nothing independently verifies it, and the licensor's audit right is exercised rarely because exercising
it is manual. Meanwhile the same artwork appears on marketplaces under listings nobody has matched to a
licence.

**Why this is the pattern to lead with.** It attacks the plane's step 5 — where the measured open-source
supply is **one GitHub result** — using the plane's step 1, where the supply is **Apache-2.0 and
5,689 stars**. The scarce half is Globant IP by necessity; the expensive half is free.

**The wiring.**

1. **Asset registry.** Stand up [`resourcespace`](https://github.com/resourcespace/resourcespace)
   (BSD-3 + trademark clause) as the DAM holding every approved licensed asset and style guide. Register
   each approved artwork at ingest.
2. **Fingerprint every approved asset.** [`idealo/imagededup`](https://github.com/idealo/imagededup)
   (Apache-2.0, 5,689★) — PHash for exact/near-exact reuse, its CNN encoder for transformed reuse. Store
   the hash beside the asset record.
3. **Add semantic reach.** [`bentoml/CLIP-API-service`](https://github.com/bentoml/CLIP-API-service)
   (Apache-2.0, alive 2026-11-09) for embeddings that survive redraws and style copies, which perceptual
   hashes miss. Two indexes, queried together: hash catches copies, embeddings catch knock-offs.
4. **Resolve the listing to a SKU.** [`jodal/biip`](https://github.com/jodal/biip) (Apache-2.0) parses
   GS1/GTIN off listing data and packshots, giving a product identity to join on. **Note the content law:**
   parsing is free, GTIN *allocation* requires paid GS1 membership — the client already has it, you do not provision it.
5. **Join to the money.** Royalty statement lines (licensee, SKU, territory, period, units, net sales)
   land in the commerce/ERP base — [`medusajs/medusa`](https://github.com/medusajs/medusa) (**MIT**) or
   [`frappe/erpnext`](https://github.com/frappe/erpnext) (GPL-3.0, client-hosted only).
6. **The agent, scoped to judgment only.** For each unmatched or under-reported listing cluster, an agent
   drafts the exception: which asset, which licensee's territory it falls in, whether a licence covers it,
   the units implied, and the citation trail. It **drafts; a licensing manager decides.**
   [`PAST2212/brand-protection-analyst-agent`](https://github.com/PAST2212/brand-protection-analyst-agent)
   (MIT, 5★) is the only MIT prior art for the agent shape — read it for structure, not as a dependency.

**What Globant owns:** the reconciliation ledger, the exception taxonomy, the royalty engine and the audit
trail. That is the deliverable, and it is the part no repository implements.

**The claim to sell:** not "AI finds counterfeits" (crowded: MarqVision, Roboflow, Counterfake) but
**"your royalty statements and your marketplace reality are reconciled, with an audit trail"**.

---

## Pattern 60 — The Article 50 labelling gate for licensed character art (EMEA, deadline 2026-12-02)

**The problem.** EU AI Act Article 50 transparency obligations took effect 2026-08-02; providers already
operating have until **2026-12-02**. Deepfakes must be visibly labelled; AI-generated output must be
marked **machine-readably**. Exposure is extraterritorial and penalties reach **€15M or 3% of global
turnover**. The exemption covers *artistic, satirical, fictional or creative* works — **which is what
licensed character art is**. So the exemption does not dispose of the duty; it relocates it into a
per-asset determination.

**The wiring.**

1. **Make the determination a field, not an opinion.** At approval time every asset gets: AI involvement
   (none / assisted / generated), whether it depicts a real person, place, entity or event, the channel
   class it is approved for, and the resulting Article 50 determination with its reason.
2. **Hold it where rights already live.** [`pwnera/artbucket`](https://github.com/pwnera/artbucket)
   (**AGPL-3.0**, 34★, pushed 2026-11-24) is the only repository that already models licence terms,
   allowed channels, **territories**, embargo dates and last-day-of-use, and it exposes an **MCP server**
   — so an agent can query "is this use permitted" directly. **Licence reality:** AGPL-3.0 means a hosted
   service built on it owes source to its users. Use it for a client-hosted deployment, negotiate the
   commercial licence with Pwnera SAS, or model the same fields in your own schema. Do not quietly embed it.
3. **Mark machine-readably, and reuse what pass 5 already found.** The marking requirement is a format
   problem, which is the half open source does well — apply the content-credential/provenance tooling
   already recorded in this KB rather than inventing a marking scheme.
4. **Allocate the duty by contract.** The licensor marks what it supplies; the licensee marks what it
   generates downstream. Encode that split per agreement, because legal analysis of the regime points
   straight at warranties, indemnities, audit rights and termination clauses.
5. **Retain evidence.** Keep the determination, its reason, who approved it and when. The deliverable is
   not compliance; it is **provable** compliance.

**Falsifiable prediction, recorded for a later pass to check:** no permissively licensed Article 50
determination/allocation engine will exist by 2027-06-30. Today the count is zero and `artbucket`
(AGPL-3.0, 34★) is the only project with the right fields.

---

## Pattern 61 — The licensee portal: build it, because there is one search result

**The problem.** Licensee administration is four flows: onboard the licensee and its agreements; distribute
style guides and approved assets; run product/art approval rounds; collect royalty statements and pay.
Every licensor runs these, and **`licensee portal` returns one result in all of GitHub** — 0 stars,
unlicensed, unrelated.

**Why now, and for whom.** The dated trigger is **Netflix taking licensee relationships in-house in
Brazil from 2027**, having done Mexico ~18 months earlier. The better *first* customer is a LATAM licensor
of its own local IP: rising local IP, no incumbent subscription to defend, and a trade agenda where
financial concerns lead — so the framing is "replace the spreadsheet and the approval email thread", not
"add AI".

**The wiring.**

1. **Multi-tenant storefront/B2B base, permissive.** [`bagisto`](https://github.com/bagisto/bagisto) (MIT,
   28,422★) ships multi-vendor marketplace natively — the closest existing shape to many licensees under
   one licensor. [`spree`](https://github.com/spree/spree) (BSD-3, 15,855★) if the client is a Rails shop
   and B2B wholesale is the dominant flow. [`saleor`](https://github.com/saleor/saleor) (BSD-3) or
   [`medusa`](https://github.com/medusajs/medusa) (MIT) for an API-first build.
2. **Asset distribution.** [`resourcespace`](https://github.com/resourcespace/resourcespace) for style
   guides and approved artwork, scoped per licensee. **Trademark clause:** the product may not be named
   "ResourceSpace"; "Powered by ResourceSpace" is the permitted phrasing. Put that in the SOW.
3. **Approval workflow — Globant IP.** Submission → art approval → pre-production sample → final. There is
   no open-source implementation; `product approval workflow` surfaces generic workflow builders
   ([`synergycodes/workflowbuilder`](https://github.com/synergycodes/workflowbuilder), Apache-2.0, 451★)
   which give you a canvas, not the domain. Model the rounds, the rejection reasons and the SLA yourself.
4. **Royalty statements — Globant IP.** Minimum guarantees, advances, tiered rates, territory splits,
   sell-through reporting. `royalty accounting`'s top six results total **9 stars**. Build it.
5. **Agent layer, where it genuinely helps.** Triage inbound approval submissions against the style guide
   (an image+text comparison, which is the substrate from Pattern 59) and draft the rejection reason with
   the specific rule cited. The approval decision stays human; the **drafting** of a consistent, citable
   rejection is the time saved.

**Scope honestly.** Do not promise an "all open source" licensing and royalty stack — Mymediabox,
Flowhaven, Dependable Solutions, BrandComply and FADEL each sell exactly the layer the open world lacks,
and this pass measured the vacuum rather than assuming it. The deliverable claim is a **permissive base
plus Globant-owned licensing logic**, which is both true and better margin.

---

## Pattern 62 — The 15-minute licence gate for any consumer-products or brand-licensing proposal

Run before the first estimate. Four checks, each of which caught a real trap in this plane.

1. **Resolve the default branch before concluding anything about a licence.**
   `gh api -X GET search/repositories -f q='repo:<slug>' --jq '.items[]|"\(.default_branch) \(.license.spdx_id)"'`
   returns branch, licence, stars and forks in one call. **Pimcore's licence file 404s on `master` and
   `main`; its default branch is `2026.x`** — and the licence there is the finding, not the absence.
2. **Treat `NOASSERTION` as "parser gave up", then read the file.** It was wrong twice here, both times in
   the permissive direction: `medusajs/medusa` and `leboncoin/trademark-monitor` are **MIT**. Reading the
   file *gains* you dependencies.
3. **If the root licence file is tiny, it is a pointer — follow it, and check the manifest.**
   ResourceSpace's is 76 bytes and points at a folder of third-party licences; the real grant is named by
   **path** in `composer.json`/`package.json` (`"license": "documentation/licenses/resourcespace.txt"`) and
   is **BSD-3 plus a trademark clause**. Any file under ~200 bytes is a redirect, not a grant.
4. **Verify existence before relevance, especially in an empty tier.** `git ls-remote` every slug, and
   search the name itself: **"UnRoyalty"**, described by an aggregator as open-source royalty software on
   GitHub, returns **TOTAL=0**. In a tier with no real code, plausible descriptions of non-existent code
   are the most likely thing you will find.

**And one non-licence check:** read the search *results*, never the total. `counterfeit detection` returns
**865** results and not one usable project (all six top hits unlicensed; five last touched 2017–2024);
`logo detection` returns **1,202** with every usable repo years dead. Conversely `licensee portal` returns
**1**, and that single digit is the most valuable number in this plane.

---

## Pattern 63 — The multi-script caption burn-in that provably renders

**Problem.** A streamer or broadcaster burns subtitles into video for Arabic, Hindi, Thai or Japanese
audiences. The pipeline reports success, the file passes QC, and the text is wrong in a way **nobody on
the delivery team can see** — letters unjoined, words reversed, conjuncts broken, tofu boxes. The failure
is invisible to a reviewer who does not read the script, so it ships.

**Stack (every component verified 2026-11-27).**

| Step | Component | License | Why this one |
|---|---|---|---|
| 1. Transcribe / translate | `openai/whisper` (MIT) + the localisation stack from pass 14 | MIT | Already in this KB |
| 2. Choose the face | [rosettatype/hyperglot](https://github.com/rosettatype/hyperglot) **208★** then [googlefonts/shaperglot](https://github.com/googlefonts/shaperglot) **58★** | **Apache-2.0** both | `hyperglot` says the font *supports* the language; `shaperglot` says it *shapes* it. Run both — coverage without features renders wrongly |
| 3. Fall back | [notofonts/notofonts.github.io](https://github.com/notofonts/notofonts.github.io) (fonts **OFL-1.1**) | Apache-2.0 tooling | Noto covers **162 of 168 Unicode 16.0 scripts**; it is the only sane fallback |
| 4. Shape + render | [libass/libass](https://github.com/libass/libass) **1,209★** over HarfBuzz | **ISC** + "old MIT" | `libass` delegates shaping to HarfBuzz, so correct RTL/Indic output is *configuration*. **This path has no copyleft in it** |
| 4b. If and only if you are in Python/Pillow | [HOST-Oman/libraqm](https://github.com/HOST-Oman/libraqm) **341★** | MIT | **Pillow built without Raqm draws Arabic isolated and left-to-right.** Check the build, not the code |
| 4c. Last resort | [mpcabd/python-arabic-reshaper](https://github.com/mpcabd/python-arabic-reshaper) **452★** + [MeirKriheli/python-bidi](https://github.com/MeirKriheli/python-bidi) **127★** | MIT + **LGPL-3.0** | Pre-shape and pre-order the string yourself. **`python-bidi` is LGPL-3.0 — the only copyleft link in the chain.** Prefer 4; use 4c only where no shaper is reachable, and never shape twice |
| 5. Prove it | [unicode-org/text-rendering-tests](https://github.com/unicode-org/text-rendering-tests) **188★** | **Unicode-3.0** | A conformance suite. Renders a known corpus and compares — the artefact that replaces eyeballing |
| 6. Arabic-specific face | [aliftype/amiri](https://github.com/aliftype/amiri) **485★** | **OFL-1.1, no RFN** | Full **Presentation Forms** coverage, which modern-shaping-only fonts often omit. No RFN, so subset and ship under the same name |

**Wiring.** `shaperglot` runs in CI against the shortlist of faces and fails the build on a missing
feature, *before* any video is encoded. At encode time `libass` renders against the chosen face; step 5
renders the conformance corpus through the same configuration and diffs it against expected output. The
delivery artefact is **the diff, not an assurance** — which is what makes it sellable to a public
broadcaster under accessibility duties.

**Anti-pattern this replaces:** applying `arabic-reshaper` *and* letting the renderer shape, which shapes
twice and produces subtly wrong output; and testing by asking one native speaker to look at three frames.

**Regional lead:** EMEA — sell it as an AVMSD/EMFA-legible delivery gate. APAC — lead with Indic
conjuncts and the Microsoft-documented reorder step. NA/LATAM — lead with indigenous orthographies
(Skeena, Andada-Pro).

---

## Pattern 64 — The font-licence CI gate (because the repo licence is not the font licence)

**Problem.** Every other plane in this KB asks *"may I use this code?"*. Type stacks **two** licences on
every deliverable: the **engine** licence (permissive, messy) and the **font** licence (a content licence,
usually OFL-1.1). A build can be 100% permissive in code and still be undistributable because of one
clause in a text file next to a `.ttf`.

**The gate, in the order the checks must run.**

1. **Locate the licence — root is not enough, at two depths.** `google/fonts` holds licences **per family**
   (`ofl/<family>/OFL.txt`); `notofonts/noto-cjk` holds them **per subtree** (`Sans/LICENSE`,
   `Serif/LICENSE`, 4,301 B, **nothing at the root**, API reports `NONE`). Probe **14 names** —
   `LICENSE`, `LICENSE.txt`, `LICENSE.md`, `LICENSE.TXT`, `LICENCE`, `COPYING`, `COPYING.txt`,
   `COPYING.md`, `license.txt`, **`OFL.txt`**, `OFL.md`, `NOTICE` — on `main` **and** `master`, **and then
   the subdirectories**. `OFL.txt` is where `EkType/Mukta` keeps its OFL-1.1, and the API reports
   `NOASSERTION` for it.
2. **Run the cycle-8 control before concluding anything is unlicensed.** Fetch `README.md` from the same
   path. `noto-cjk`: README **200**, all 12 root licence names **404** → **your names are wrong, the
   licence is not missing.** A 404 on the raw channel is *never*, by itself, evidence of a missing licence.
3. **Grep the licence for `with Reserved Font Name`.** This single grep decides whether your subset may
   keep its name. Measured this pass: **Andada-Pro, Amiri, Mukta — no RFN. Skeena — "Skeena". Charis —
   "Charis" and "SIL".** Three of five free, two not, and the split tracks nothing you could have guessed.
4. **If an RFN is declared and you subset, rename the font's internal names.** OFL-1.1 defines a Modified
   Version as *"any derivative made by adding to, deleting, or substituting — in part or in whole — any of
   the components of the Original Version"*; **subsetting deletes components**, and SIL's FAQ (per LWN's
   summary) treats format conversion and non-byte-identical rebuilds as modification too. *State this as a
   reading of the licence text:* `openfontlicense.org` does not resolve from this session, so the FAQ's
   own wording on subsetting is **unverified** — see `intel/trends.md`.
5. **Validate the binary.** [fonttools/fontspector](https://github.com/fonttools/fontspector)
   (**Apache-2.0, 123★, pushed 2026-11-27**) — CLI, Python module **and WASM**, with Google Fonts,
   OpenType, Universal, Microsoft and Adobe profiles, plus a `fontbakery-bridge` crate that runs the
   legacy Python checks. **Do not pin [fonttools/fontbakery](https://github.com/fonttools/fontbakery)**
   (713★, Apache-2.0): last push **2025-11-04**, 12.8 months stale, **not archived**, and **moved org** —
   it was recorded in this KB's pass 23 as "invisible to the search index" because the pass looked under
   `googlefonts/`.
6. **Diff the build.** [googlefonts/diffenator2](https://github.com/googlefonts/diffenator2)
   (Apache-2.0, 71★) for visual regression between two font builds.
7. **For native dependencies, resolve the licence of what you LINK, not what you clone.** The pass-5 rule,
   and this plane is full of it: **FreeType is dual FTL / GPL-2.0** — a choice you must make and record;
   **ICU is Unicode-3.0**; **HarfBuzz is "old MIT"** with per-subdirectory `COPYING` files; **FontForge is
   GPL-3.0 as a whole**, so it is a tool you run, never a component you link.

**Falsifiable prediction, recorded for the next pass of this plane:** `fonttools/fontbakery` will still
show a 2025 last-push date and still not be archived, and `fontspector` will have outgrown every other
Rust component here in percentage star growth. If fontbakery moves, the migration stalled and step 5 is
wrong.

---

## Pattern 65 — Script coverage as a go/no-go market decision (not a design opinion)

**Problem.** A client wants to launch a service, a channel or an app in a new market and has a brand
typeface they are contractually attached to. "Can our font serve India / MENA / Japan?" is answered today
by a designer's opinion, a PDF specimen, or a rendered screenshot — and the answer arrives after the
launch date is fixed.

**Make it a number, in one CI step.**

| Step | Tool | License | Output |
|---|---|---|---|
| 1. Which languages does the brand face support? | [rosettatype/hyperglot](https://github.com/rosettatype/hyperglot) **208★, 28f, 2026-10-26** | **Apache-2.0** | A per-language pass/fail list from the font file itself |
| 2. Does it *shape* them? | [googlefonts/shaperglot](https://github.com/googlefonts/shaperglot) **58★, 11f, 2026-11-17** | **Apache-2.0** | Which required OpenType features are missing |
| 3. If it fails, what covers the gap? | `notofonts/notofonts.github.io` (**OFL-1.1** fonts) | Apache-2.0 tooling | **162 of 168** Unicode 16.0 scripts, **77,000+** characters (≈ half of Unicode 18.0's 172,808) |
| 4. What does the gap cost to close? | [googlefonts/fontc](https://github.com/googlefonts/fontc) **196★** / [googlefonts/fontmake](https://github.com/googlefonts/fontmake) **900★** + [adobe-type-tools/afdko](https://github.com/adobe-type-tools/afdko) **1,191★** | Apache-2.0 | A build path for an extended family, priced as work |
| 5. What does serving it weigh? | [KonghaYao/cn-font-split](https://github.com/KonghaYao/cn-font-split) **1,269★, pushed 2026-11-27** / `fonttools` `pyftsubset` **5,338★** | Apache-2.0 / MIT | Bytes per page or per app build, against a budget |

**The decision this produces.** Three outcomes, each with a different commercial answer: **(a) the brand
face covers the market** — proceed, and keep the `shaperglot` report as the acceptance artefact; **(b) it
covers codepoints but not shaping** — a scoped font-engineering engagement, priced from step 4, which is
the best of the three for Globant because it is small, verifiable and nobody else is bidding it;
**(c) it cannot serve the market** — a Noto-based fallback plus a brand-adjacent pairing, decided before
the launch date rather than after.

**Why nobody does this.** The measurement at steps 1–2 costs minutes and exists under Apache-2.0, and the
two tools that perform it have **208 and 58 stars** between them. This is the same shape as `Little-CMS`
(pass 23) and `datadiligence` (pass 5): **load-bearing, permissive, maintained, and nearly unknown.**

**Regional lead:**
- **APAC** — lead with step 5. The weight is the objection: a full CJK font measured at **16.4 MB** against
  a **3.6 MB** subset, and India's own measured gap (no centralized public repository of high-quality
  open-licensed Indic fonts) plus **Kruti Dev** legacy encoding still in government and print workflows.
- **EMEA** — lead with step 2. Arabic and Hebrew fail at *shaping*, not coverage, and `fontsource` (MIT)
  gives the self-hosted serving story procurement will ask for.
- **LATAM** — lead with step 1 and name the language. `Andada-Pro` (**OFL-1.1, no RFN**) was built for
  Spanish and **Guaraní**, which is co-official in Paraguay; the only maintained Guaraní keyboard is
  `giellalt/keyboard-grn` (**MIT, 0★, pushed 2026-10-28**), from a **Nordic** language-technology org.
- **NA** — lead with the licence, not the glyphs. The blocker is the foundry EULA's **broadcast** and
  **app** tiers; `Skeena` (**OFL-1.1, RFN "Skeena"**) covers North American indigenous orthographies and
  **requires the rename step** from Pattern 64.

**The one-line version for a client conversation:** *coverage is not support, support is not shaping, and
all three are measurable before you commit a launch date.*

---

# The print, periodical & manuscript digitisation plane — patterns from pass 39 (2026-11-27)

Patterns 1–65 above assume, in several places, that an archive has a usable text layer. Patterns 3
(archive mining), 14 (archive→revenue) and 31 (description backfill) all begin after OCR. These five
patterns supply what comes before, and the licence gate that governs all of them.

## Pattern 66 — The text-layer retrofit: make an online archive searchable without re-scanning anything

**The build with the clearest stated demand in this KB.** Argentina's Biblioteca Nacional Mariano Moreno
publishes **415 titles / 150,000+ fascicles** online as **PDFs without OCR**; Uruguay's National Library
has a published 2026 plan to "universalizar" OCR and handwriting recognition across its digital archives.
Nothing needs scanning, negotiating or training. The pages are already digitised and largely rights-cleared.

**Wiring, step by step — every component permissive and self-hosted:**

1. **Ingest and triage.** [apache/tika](https://github.com/apache/tika) (Apache-2.0) walks the existing
   PDF corpus and separates image-only pages from pages that already carry text, so you never pay to
   OCR a page twice. Record the split — it is the first number the client has never had.
2. **Layout analysis before recognition.** [qurator-spk/eynollah](https://github.com/qurator-spk/eynollah)
   (Apache-2.0, 417★, pushed 2026-11-13) segments broadsheet pages into regions and reading order.
   **Do not skip this on newspapers**: column bleed is the single largest source of unusable OCR, and a
   recognition engine pointed at a whole broadsheet page produces text no search can use.
3. **Recognition.** [tesseract-ocr/tesseract](https://github.com/tesseract-ocr/tesseract) (Apache-2.0,
   77,680★) for Spanish/Portuguese print — it is what the national programmes run, and Latin-script
   historical print is its strongest case. Where quality is insufficient, escalate *selected* pages to
   [allenai/olmocr](https://github.com/allenai/olmocr) (Apache-2.0) — **the VLM with no weights trap**.
4. **Write the text back into the artefact the institution already serves.**
   [ocrmypdf/OCRmyPDF](https://github.com/ocrmypdf/OCRmyPDF) (MPL-2.0, 35,414★) adds an invisible text
   layer to the existing PDF. The URLs, the citations and the public-facing catalogue do not change —
   which is what makes this politically approvable inside a library.
5. **Emit ALTO XML alongside.** [cneud/alto-tools](https://github.com/cneud/alto-tools) (Apache-2.0) and
   [UB-Mannheim/ocr-fileformat](https://github.com/UB-Mannheim/ocr-fileformat) (MIT) convert hOCR→ALTO.
   The ALTO is the migratable asset; the searchable PDF is the deliverable the public sees.
6. **Prove it.** [qurator-spk/dinglehopper](https://github.com/qurator-spk/dinglehopper) (Apache-2.0) on a
   stratified sample the client hand-transcribes with you (300–600 lines is enough). This is step 6 and
   it is the one that gets the second phase funded.

**Licence ledger:** Apache-2.0 ×4, MIT ×1, MPL-2.0 ×1. **No copyleft reaching client code, no model
weights with thresholds, no data leaving the institution.** Reference implementation to cite:
[LibraryOfCongress/ndnp-open-ocr](https://github.com/LibraryOfCongress/ndnp-open-ocr) (**CC0 1.0**).

**What to quote:** page count × compute per page × a measured CER delta. Never an enterprise
document-capture market figure (see `intel/market.md` pass 39 refusal).

## Pattern 67 — The weights gate: the 15-minute check that belongs before every document-AI estimate

This plane produced **six verified cases** where the code licence and the weights licence differ. Run
this before any proposal; it has caught a wrong answer every time.

| Check | Command / action | Why |
|---|---|---|
| 1. Weights, separately from code | Read the model card **and** the README §Commercial/License | `marker`/`surya`: Apache-2.0 code, **OpenRAIL-M weights free only under $5M** funding/revenue. `Churro`: Apache-2.0 code, **Qwen research licence** weights — unshippable. |
| 2. Additional terms on an Apache repo | Read `LICENSE.md` **in full**, not the badge | `MinerU`: Apache-2.0 **+** separate commercial licence above **100M MAU / $20M monthly revenue**, **+ mandatory "uses MinerU" UI notice at any size**, + automatic termination. API says `NOASSERTION`. |
| 3. British spelling | Probe `LICENCE`, `LICENCE.md`, `LICENCE.txt` too | `ndl-lab/ndlocr-lite` 404s on all eight American names on both branches while `README.md` = 200. Licence is `LICENCE` (18,653 B). |
| 4. The distillation ancestor | Trace the model backbone | `ndlocr-lite`'s layout model is distilled from **DINOv3**: the Meta agreement travels with derivatives (§1.b.i), bars reverse engineering (§1.b.iv), compels acknowledgement (§1.b.ii), adds indemnity and patent-retaliation (§5.b). CC BY 4.0 on the wrapper cannot override it. |
| 5. Standards repos | Use the published spec, never the GitHub XSD | `altoxml/schema` (57★) and `mets/METS-schema` (27★): **no licence file**. Default copyright = all rights reserved. |
| 6. Existence | `git ls-remote`, every URL | `PaddlePaddle/PaddleOCR-VL` is cited by 2026 roundups and **does not exist**; `rednote-hilab/dots.ocr` is **absent from the search index** and does. |

**The one-line version for a client conversation:** *in document AI the code is free and the weights are
where the lawyer lives* — and an SBOM scan of the source tree reports clean for all six cases above.

## Pattern 68 — Re-OCR with an evidence trail (and the refusal that makes it credible)

**The 2026 budget in this plane is reprocessing, not scanning.** The Library of Congress shipped new OCR
reprocessing software and a Chronicling America datasets portal in **August 2026**; Luxembourg built
`nautilusocr` to turn METS/ALTO into *better* METS/ALTO; Uruguay wants OCR retrofitted across archives
already online. Engine quality has moved far enough that a decade of scans is worth running again.

**The pattern:** (1) take the client's existing ALTO/hOCR as the **baseline** — not a competitor's claim;
(2) hand-transcribe a stratified sample as ground truth, with the client's staff, and register it in
[htr-united/htr-united](https://github.com/htr-united/htr-united) (**CC0-1.0**) if they agree; (3) run
the candidate chain; (4) report **CER/WER delta per title and per decade** with
[dinglehopper](https://github.com/qurator-spk/dinglehopper) or
[ocrevalUAtion](https://github.com/impactcentre/ocrevalUAtion) (both Apache-2.0); (5) **ship only the
titles that improved.** Some will not, and saying so is the credential.

**⛔ The refusal that comes with it — and it is the sellable half.** Do not promise LLM post-correction
will clean an archive. Kanerva et al., *No Free Lunches* (RESOURCEFUL 2025,
[arXiv 2502.01205](https://arxiv.org/abs/2502.01205)) found open-weight LLMs **decreased** quality in many
cases on historical English and Finnish; **ICDAR 2026** ran the HIPE-OCRepair competition because the
problem is unsolved. The correct offer is a **bounded, measured** correction step with a gate: it ships
only where CER improves on the client's own pages. This is the P45 shape — when the dominant approach
cannot be shown to work, the deliverable is a refusal with a measurement attached. Benchmark to cite:
**BLN600** (600 newspaper excerpts with source image, OCR and manual gold transcription).

## Pattern 69 — The end-to-end permissive national newspaper pipeline (a licence fix that is a whole engagement)

**The finding:** `LibraryOfCongress/ndnp-open-ocr` is **CC0 1.0** — a US Government work, public domain,
worldwide waiver — and its **layout step uses models from American Stories** (Harvard), whose repo
[dell-research-harvard/AmericanStories](https://github.com/dell-research-harvard/AmericanStories) has
**142★, no licence file at all, last push 2024-03-07**, with **models shipped by Dropbox link** (the
dataset is CC-BY-4.0 on Hugging Face; the code and weights are not licensed). Every institution adopting
the national pipeline inherits an unlicensed, dormant dependency at the step that matters most.

**The build:** fork the CC0 pipeline, **replace the layout stage with
[eynollah](https://github.com/qurator-spk/eynollah)** (Apache-2.0, pushed 2026-11-13), keep Tesseract +
Leptonica (both already used unmodified under their own licences), add `dinglehopper` as a CI gate so the
substitution is *proven not to regress* on the client's pages, and emit the same ALTO XML + PDF the NDNP
programme expects. Deliverable: an **end-to-end permissive, CC0-rooted newspaper OCR pipeline with a
licence provenance document and a measured no-regression report.**

**Who buys it:** US library systems, university presses and newspaper groups on the NDNP stack; any
EMEA institution that wants the LoC method without the dependency. The diligence finding *is* the pitch —
you are not selling OCR, you are selling the removal of a licence defect from national infrastructure,
with the performance proof attached.

## Pattern 70 — Ground truth as the regional asset (the LATAM build that compounds)

**The measured gap:** generic engines already read Spanish and Portuguese print well, so **the scarce
asset in LATAM is not a model — it is ground truth and regional layout profiles.** Verified: no maintained
LATAM-origin OCR/HTR repository with traction exists (searched in Spanish for Brazil/Argentina/Chile
hemeroteca tooling); **Historical Ink** ([arXiv 2407.12838](https://arxiv.org/abs/2407.12838)) is a corpus
and a paper, not a tool; `FoNDUE-HTR/FONDUE-ES-PRINT-19` is **0★, dormant since 2024-01-15, with CC-BY
declared only in the HTR-United catalogue and no licence in the repo**.

**The build:** with the first client, hand-transcribe a few thousand lines spanning their decades,
typefaces and column grids; version it as a dataset with an **explicit licence file in the repository**
(do not repeat the FONDUE defect); fine-tune [kraken](https://github.com/mittagessen/kraken) (Apache-2.0)
or evaluate against it; publish the *catalogue entry* in `htr-united` (CC0) while the client keeps the
corpus if they prefer. **Each subsequent regional engagement starts from a better baseline than any
incumbent can offer**, because the asset is local, legal and cumulative — and unlike a model, it does not
depreciate when the next VLM ships.

**Commercial frame:** Chile's **Latam-GPT** (launched February 2026) makes recovered Spanish-language
newspaper text directly valuable as training data, which gives the archive owner a second reason to fund
the work — and brings pass 15's rights-reservation gate (P15) into the same conversation: *decide who may
train on the text you just created, at the moment you create it.*

## What not to promise in this plane

- **Not** "AI will clean up your archive" — measured evidence says post-correction often makes it worse.
- **Not** a pipeline built on `Churro`, however well it fits: **research-licensed weights**.
- **Not** `MinerU` inside a client product without surfacing the **mandatory attribution notice** and the
  **$20M/100M** thresholds, nor `marker`/`surya` without the **$5M** weights ceiling.
- **Not** `PyMuPDF` (AGPL-3.0) or `nautilusocr` (GPL-3.0, dormant) in anything the client ships.
- **Not** an ALTO or METS XSD vendored from GitHub — **those repos carry no licence**.
- **Not** an enterprise document-capture market figure quoted to a library as "your market".
- **Not** a quality claim without a CER/WER number on **the client's own pages**.

---

# Pass 40 (2026-11-27) — patterns for the puzzles & games-desk plane

Every repo named below appears with its verified licence and last-push date in `agents/top.md`,
`repos/foundations.md` or `verticals/solutions.md`, all probed 2026-11-27.

## Pattern 71 — The metering-free games desk (replacing the rented layer)

**When:** a publisher pays AmuseLabs PuzzleMe from $99/month, metered on **page loads** — charged
when the page opens even if the reader never starts the game — and wants the cost off the growth
path, or wants the games layer to be a differentiator it actually owns.

**Why it works:** every component of the *delivery* path is MIT and was pushed within days of this
pass. The rented part is the assembly, not the technology.

**Wiring:**
1. **Player:** [`viresh-ratnakar/exolve`](https://github.com/viresh-ratnakar/exolve) (MIT,
   2026-11-22) — single-file JS, handles grid interaction and cryptic conventions. Embed directly;
   no per-load meter exists to pay.
2. **Format spine:** [`alexdej/puzpy`](https://github.com/alexdej/puzpy) (MIT, 2026-11-22) for
   `.puz` in and out — this is what syndicators and constructors actually send — with
   [`jpd236/kotwords`](https://github.com/jpd236/kotwords) (Apache-2.0, 2026-11-26) for everything
   else and [`svisser/ipuz`](https://github.com/svisser/ipuz) (MIT) for the open JSON format.
   Normalise on ingest to one internal representation; never let a vendor format reach the player.
3. **Validation gate:** `xdlint.py` from [`century-arcade/xd`](https://github.com/century-arcade/xd)
   (MIT, 2026-11-25) — stdlib-only, no dependencies, with a published rule catalogue. Run it in CI
   on every puzzle before it is scheduled. This is the piece that stops a malformed daily reaching
   the front page at 06:00.
4. **Construction (if the desk commissions its own):**
   [`pmaher86/blacksquare`](https://github.com/pmaher86/blacksquare) (MIT, 2026-09-01) for
   programmatic grids and autofill. **Supply your own word list — see Pattern 72, and do not point
   it at a personal-use-only list.**
5. **Reference architecture, read but not forked:**
   [`crosshare`](https://github.com/crosshare-org/crosshare) (AGPL-3.0) for the publishing model and
   [`lichess-org/lila`](https://github.com/lichess-org/lila) (AGPL-3.0) for daily-item delivery,
   rating and streaks at scale. **Read them; assembling from the MIT parts avoids network copyleft
   on the differentiator.**

**The AI layer that justifies the project** (not the player, which is commodity): clue suggestion
for constructors, and **difficulty calibration from solve telemetry** — open nowhere for crosswords,
and the one product problem in the plane that neither a repo nor a vendor currently solves.

**Cost honesty:** the build replaces a $99+/month line item plus separately priced puzzle content.
Say that plainly — the saving alone does not fund a bespoke platform, so the case has to rest on
retention and ownership, which is exactly how the NYT frames it.

## Pattern 72 — The Spanish-language word list as the regional asset (the LATAM build that compounds)

**When:** any LATAM publisher engagement in this plane. It is a prerequisite, not an upsell.

**The measured gap** (`repos/foundations.md`): **zero** permissively licensed Spanish or Portuguese
word data — three of five located assets carry **no licence at all**, one is AGPL-3.0, one is an
MPL-2.0 spell-checker list whose own docs warn it is polluted with city and proper names — and **no
Spanish or Portuguese clue corpus exists at all**. English, by contrast, has
[`dwyl/english-words`](https://github.com/dwyl/english-words) in the **public domain**.

**Wiring:**
1. **Start from licensed material only.** [`pythonprobr/palavras`](https://github.com/pythonprobr/palavras)
   (MPL-2.0) for pt-BR; for Spanish, treat [`vocably/es`](https://github.com/vocably/es) (AGPL-3.0)
   as a *reference to check against*, not as input to a proprietary list. **Do not ingest the three
   unlicensed lists** — unlicensed means all rights reserved, and this is precisely the trap this
   pattern exists to avoid.
2. **Curate to crossword grade.** Strip proper nouns and place names that the speller lists carry,
   score entries for fill-friendliness (letter distribution, vowel pattern), and tag register and
   country variance — `mexicanismos` vs `rioplatense` matters editorially, and no existing asset
   encodes it.
3. **Generate the grids** with [`blacksquare`](https://github.com/pmaher86/blacksquare) (MIT) or
   [`caravaca-labs/puzzletide-cli`](https://github.com/caravaca-labs/puzzletide-cli) (MIT,
   2026-11-14) when a **print-ready PDF** is the deliverable — still the real requirement at most
   LATAM dailies.
4. **Build the clue corpus as the commercial layer.** Clues written in-house, versioned, with
   provenance per clue (human-written / AI-assisted / AI-generated, model, date) so the Article 50
   and APAC labelling obligations and Mexico's May 2026 rules are answerable by query.
5. **Licence deliberately:** CC0 or CC-BY on the **word list** buys standard-setting and goodwill
   across the region; keep the **curation layer and the clue corpus** commercial. That split is the
   whole strategy.

**Why it compounds:** the engines are MIT commodities available this afternoon; the language data is
the scarce part, it is reusable across every publisher in the region, and it gets more valuable with
each clue written. Same shape as pass 39's ground-truth finding and pass 38's multi-script finding.

## Pattern 73 — The licensed archive revival (and the renewal check that gates it)

**When:** a publisher with a long-running puzzle wants to monetise its own back catalogue — the
cheapest "new" content a games desk can ship.

**Wiring:**
1. **Run the copyright-renewal check first, as a release gate.** US works published 1931–1963 kept
   copyright only if renewed in the 28th year. The xd corpus's `docs/` shows both outcomes: *Judge*
   1931–39 **cleared** (no issue renewed, 227 puzzles freed) and NYT 1942–63 **blocked** (every
   issue renewed, **5,267 puzzles under copyright until 2037–2058**) — and an earlier release had
   already published the latter in error. **The check is the gate, and getting it wrong is a
   publication incident, not a footnote.**
2. **Digitise** with the pass-39 OCR stack, then validate every output with `xdlint.py`.
3. **Adopt the three-tier access model** verbatim from
   [`century-arcade/xd`](https://github.com/century-arcade/xd)'s `docs/ACCESS.md` and
   `docs/DATASETS.md`: **(a)** out-of-copyright puzzles published in full; **(b)** derived,
   non-reconstitutive data published openly under the governing principle "nothing we publish lets a
   copyrighted puzzle be rebuilt"; **(c)** full modern puzzles gated, approved by name. This is a
   publishable product architecture that happens to also be the rights position.
4. **Contribute upstream, and lead with the licence.** The
   [Every Puzzle Project](https://github.com/EveryPuzzleProject)'s **12 repositories are all active
   and all unlicensed**. A pull request adding CC0 or CC-BY converts a dozen archives — including
   early Black-press crosswords — from unusable to usable. Highest leverage per hour available in
   this plane, and it costs nothing but the asking.

**What not to do:** train a clue generator on the public xd clue file for a publishing product. The
corpus's `docs/AI.md` asks specifically that the data **not** be used "to build systems that generate
crosswords or clues for publication". The terms are, in their own words, "not locks" — honour them
anyway, because the alternative is a client-facing rights argument you will lose on reputation even
where you win on law.

## Pattern 74 — The cryptic co-pilot (EMEA, and the one place human expertise is the product)

**When:** a UK or Irish publisher with a cryptic tradition, where replacing the setter is both
impossible and commercially wrong.

**Why it is defensible:** published results put LLMs **significantly below human** on cryptic clues
([arXiv 2412.09012](https://arxiv.org/abs/2412.09012)) while they reach **93%** on American-style
grids ([arXiv 2406.09043](https://arxiv.org/abs/2406.09043)). The moat is wordplay.

**Wiring:** [`viresh-ratnakar/exet`](https://github.com/viresh-ratnakar/exet) (MIT, 2026-11-25) as
the setter's workbench and [`exolve`](https://github.com/viresh-ratnakar/exolve) (MIT) as the player
— one maintainer, one toolchain, both current. Add
[`rjkat/anagrind`](https://github.com/rjkat/anagrind) (MIT, 2026-10-11) to **parse and check** the
setter's own clues: detect the wordplay device, verify the definition and the subsidiary indication
agree, flag an unsound clue before an editor sees it. The AI validates; it does not compose.
Calibrate difficulty against solve telemetry.

**Compliance built in:** under EU AI Act Article 50, anything AI-generated carries disclosure. A
co-pilot that only *checks* human clues keeps the output human-authored — a simpler compliance story
than generation, and the better editorial product. Record the distinction per clue anyway.

## Pattern 75 — The daily-item engine, learned from chess, applied to number puzzles (APAC)

**When:** an APAC engagement, or any daily-puzzle product being designed from scratch.

**Why this pairing:** number and logic puzzles need **no word list and no clue corpus** — they are
generated, not authored, so steps 3 and 4 of this plane's gradient vanish, and they are the puzzle
family culturally native to the region. Meanwhile Lichess has solved daily-item delivery in the open
at a scale no publisher will reach.

**Wiring:**
1. **Engine:** [`t-dillon/tdoku`](https://github.com/t-dillon/tdoku) (BSD, with a benchmark suite
   against the fastest known solvers) for generation and solving;
   [`dawsonbooth/sudoku-tools`](https://github.com/dawsonbooth/sudoku-tools) (MIT) for **grading**,
   which is the part that matters editorially; [`gitctrlx/sodo`](https://github.com/gitctrlx/sodo)
   (dual MIT + Apache-2.0) where a WASM build is wanted in-browser.
2. **Delivery architecture:** read [`lichess-org/lila`](https://github.com/lichess-org/lila)
   (AGPL-3.0, pushed 2026-11-27) for rating, streak and daily-item mechanics, and
   [`ornicar/lichess-puzzler`](https://github.com/ornicar/lichess-puzzler) (AGPL-3.0) for the
   **generate → review → classify** pipeline shape — the only open puzzle-generation pipeline in
   existence, and the model for how classification feeds difficulty.
3. **Calibrate** generated difficulty against real solve-time distributions, not against the
   generator's own rating. This is where the product earns its keep.
4. **Print path:** [`puzzletide-cli`](https://github.com/caravaca-labs/puzzletide-cli) (MIT) for
   page-ready PDFs.

**Two regional constraints to raise in the first week:** **Nikoli holds the "sudoku" trademark in
Japan** — name the feature carefully for a Japanese launch ("number place" is the generic) — and
generative-AI **labelling duties** apply across several APAC frameworks (South Korea; Vietnam's Law
No. 134/2025/QH15, in force 1 March 2026; China's targeted rules), so a generated puzzle is
label-bearing content. Both are cheap to handle at design time and expensive later.

## What not to promise in this plane (pass 40)

- **Do not promise a market size.** The genre figures span **$4.9B to $27.1B** on scope differences,
  and **none of them sizes a publisher games desk**. The only defensible numbers are price lists —
  $99/month for the vendor layer, $50 for the standard word list, ~$50/year for a consumer
  subscription (`intel/market.md`).
- **Do not promise retention uplift with a number.** Every public retention claim is qualitative and
  from the seller. No publisher has disclosed audited games-attributable retention or revenue.
- **Do not promise AI-generated cryptic clues.** The published evidence says the models are not
  there, and a client's crossword editor will know within one clue.
- **Do not build on the standard word list.** XWord Info's terms are personal-use-only with no
  derivative lists; a publisher product built on it is outside them.
- **Do not treat an unlicensed repo as open** because it is active and well made. Twelve Every Puzzle
  Project repositories, `m0nt4ld0/crucigrama`, `javierarce/palabras` and `sofyc/ConQuer` are all
  readable and all legally unusable. Ask for a licence instead — it is the cheapest win here.

## Pattern 76 — The manifest-recovery service: build the lookup half of soft binding

**The measurement that justifies it.** The C2PA soft-binding registry holds **80 approved
algorithms**; **13** declare a Soft Binding Resolution API endpoint (measured from
`softbinding-algorithm-list.json`, 2026-11-27). The other 67 can *name* a mark and resolve nothing.
Meanwhile 19 new entries landed in November 2026 alone. The naming layer is outrunning the lookup
layer about five to one, and **the spec for the missing half is public** (C2PA Soft Binding
Resolution API, Decoupled, spec 2.5).

**What to wire together.**

```
INGEST   ─► c2patool (Apache-2.0) ............. sign manifest at creation
           contentauth/c2pa-rs (MIT+Apache-2.0)  core signing/validation
MARK     ─► facebookresearch/videoseal (MIT) ... video/image soft binding
           facebookresearch/audioseal (MIT, weights included) .. audio
           adobe/trustmark (MIT) ............... arbitrary-resolution images
STORE    ─► iscc/iscc-c2pa-store (Apache-2.0) .. Manifest Repository
RESOLVE  ─► deepmark/c2pa-soft-binding-stack (MIT) .. Resolution API reference
           iscc/iscc-c2pa-resolver (Apache-2.0)
TEST     ─► Original-Pictures/soft-bindings-benchmark (Apache-2.0)
           beomjin-ahn/provsurvive (MIT) ....... survival under edits
VERIFY   ─► contentauth/c2pa-mcp (Apache-2.0) ... agent-side read path
```

**The three decisions that make it real.**

1. **Pick the algorithm by registry position, not by stars.** If the asset must be resolvable by
   anyone else's tooling, the `alg` must be a registered identifier. Unregistered beats registered on
   benchmark scores and loses on interoperability every time.
2. **Run the benchmark before the contract, not after.** `soft-bindings-benchmark` and `provsurvive`
   exist and are permissive; a client's acceptance criterion ("the mark survives our delivery chain")
   becomes a test run, not an argument.
3. **Treat the resolution endpoint as the product.** Marking is a library call. The durable asset is
   the repository plus the API plus the uptime commitment, because that is what 67 of 80 registrants
   do not have.

**What never to promise:** that recovery works for assets marked before the service existed. Soft
binding is prospective.

## Pattern 77 — Register the algorithm: the standards position a permissive licence makes available

**The finding this is built on, and it is causal.** Eleven of the 80 registry entries wrap Meta
FAIR's MIT-licensed models (`videoseal`, `pixelseal`, `audioseal`, `silentcipher`), filed by **five
distinct third parties** — `aiwatermark`, `reconize`, `immostory`, `originalpictures`, `aidr.studio`.
Entries registered by Meta or FAIR: **zero**. `com.originalpictures.*` alone holds **12** entries,
wrapping the open fingerprinting toolkit (`chromaprint`, `audfprint`, `pdq`, `vpdq`, `tmk-pdqf`,
`dinov2`). The registry's submission rule permits exactly this: a PR may come from *"an individual
affiliated with the company owning the submitted proprietary algorithm **or a maintainer of the
submitted open source algorithm or its fork**."*

**The play, in order.**

1. Fork or maintain a permissive marking/fingerprinting implementation (MIT or Apache-2.0 — the
   licence is the eligibility condition).
2. Stand up a Soft Binding Resolution API that implements **at least the mandatory endpoints** — the
   registry's selection rules check that `softBindingResolutionApis` resolves.
3. Publish algorithm documentation at a stable URL; `informationalUrl` must resolve and must describe
   *that* algorithm's operation.
4. File the PR against `softbinding-algorithm-list.json` conforming to
   `softbinding-algorithm-list-schema.json`, with all mandatory fields.
5. Note the immutability rule before choosing names: **`identifier`, `alg` and `type` can never be
   changed** on an existing entry.

**Why a studio or broadcaster client would pay for this.** A registered identifier under their own
reverse-DNS namespace is a durable, citable interoperability asset that their competitors must
resolve against — and it is obtainable for engineering effort rather than licence fees, *because* the
underlying model is MIT.

**The honest caveat:** registration is recognition of an identifier, not a conformance certification.
Read [c2pa-org/conformance-public](https://github.com/c2pa-org/conformance-public) before any
deliverable claims the client "is C2PA conformant."

## Pattern 78 — Leak tracing where the mark is the vendor's and the evidence trail is yours

**The constraint, measured.** Session-based forensic watermarking — the per-subscriber mark that makes
leak attribution possible — **has no open implementation**. `forensic watermarking video` returns 21
repos and every one holds 0 or 1 star, most with no licence, five sharing a single repo name (a
coursework cohort). The capability sits with castLabs (registry entry
`castLabs.watermark.1.session-v1`), Nagra NexGuard, Verimatrix, MarkAny, DoveRunner. **So do not bid
the mark. Bid everything around it.**

**The division of labour to put in the statement of work.**

| Layer | Who | Why |
| --- | --- | --- |
| Session mark embed/extract | **Vendor, under contract** | No open option exists; this is Pattern 24's boundary applied to forensics. |
| Per-session identity binding | **Globant** | Mapping mark payload → entitlement → account, with retention rules. |
| Detection intake & triage | **Globant** | Screenshot/stream in, candidate mark out, confidence scored. |
| Evidence package | **Globant** | Timestamped chain of custody: what was marked, when, by which key, extracted by which build. |
| Filing & jurisdiction routing | **Globant** (see Pattern 79) | The output of tracing is a legal action, not a dashboard. |

**Build the extractor's test bench from permissive parts** — `soft-bindings-benchmark` (Apache-2.0)
and `provsurvive` (MIT) — so that "the mark survived the pirate's re-encode" is a measured claim
rather than a vendor assurance.

**The refusal that makes the proposal credible.** State in writing that invisible marking is
**evidence, not prevention**, and cite why: the best-maintained remover is MIT-licensed with
**28,928★** and was pushed this month, against 456★ for the standard's own SDK, and removability of
invisible image watermarks is a **published NeurIPS 2024 result**
([XuandongZhao/WatermarkAttacker](https://github.com/XuandongZhao/WatermarkAttacker)). A client who
hears this first will trust the rest of the estimate.

## Pattern 79 — The 30-minute blocking pipeline, built as a per-jurisdiction policy engine

**Why a single global feature cannot work.** The four regions do not merely differ in strictness,
they differ in *who holds the authority and what it reaches*:

| Region | Mechanism in force | What it reaches | Deadline |
| --- | --- | --- | --- |
| EMEA (Italy) | **Administrative** — AGCOM Piracy Shield since 2024-02 | ISPs; **VPNs and public DNS resolvers** added by AGCOM rules 2025-02; scope widened 2025-08 from live sport to film/TV premieres and live music | **30 minutes** |
| LATAM (Brazil) | **Administrative** — Anatel | ISPs and regional broadband providers | Operational, not statutory; public dashboard since 2026-05 |
| APAC (India) | **Judicial** — Delhi High Court dynamic / "Dynamic+" injunctions | Rogue sites and apps, DNRs, ISPs; plaintiff files continuing affidavits naming new targets | Real-time by order |
| North America | **None in force** | Three competing bills disagree on whether VPNs are in scope at all | — |

**The engine, concretely.** One detection pipeline; one evidence schema; **four policy packs**:

```
DETECT ──► candidate infringing endpoint + evidence bundle
             │
POLICY ──►  jurisdiction resolver
             ├─ IT  : AGCOM ticket, 30-min clock, VPN/DNS targets permitted
             ├─ BR  : Anatel administrative route, dashboard reconciliation
             ├─ IN  : affidavit generator for a live dynamic injunction
             └─ US  : notice-and-takedown only; NO blocking route — flag and stop
FILE   ──► per-route submission + immutable audit record
```

**The guardrail that belongs in the code, not the policy document:** the US pack must **refuse** to
emit a blocking request. There is no US site-blocking law in force — FADPA (H.R. 791, introduced
2025-01-28) remains in House Judiciary; the DEFEND IP Act (Senate S. 5529) merges it with Block BEARD
and **excludes VPNs**; Rep. Issa's American Copyright Protection Act of 2026 **includes** VPNs and its
text was unpublished as of this pass. A pipeline that files the wrong instrument in the wrong country
is a liability, so encode the jurisdiction's limits as a hard gate.

**Over-blocking is a design requirement, not a critique to deflect.** The EP study arguing for binding
30-minute blocking acknowledges over-blocking risk, and Italy's scheme drew a **€14.2M** AGCOM fine
against a resolver operator in January 2026, now under appeal with the legality of the orders
challenged. Every automated target must therefore carry a human approver, a reversal path and a
retained record of who authorised it.

## Pattern 80 — The 15-minute gate for any content-protection or anti-piracy proposal

Run before estimating. Each answer changes the shape of the engagement.

1. **Is the ask prevention or evidence?** If the client says "stop piracy", reset the conversation
   with the 28,928★-vs-456★ measurement before writing a line of scope. Marks are evidence.
2. **Prospective or retrospective?** Soft binding and session marking only work on assets marked from
   now on. If the library is already out, the plane that applies is detection and takedown, not
   marking.
3. **Does the deliverable need to interoperate?** If yes, the algorithm **must** be a registered
   identifier, and only **13 of 80** registered algorithms are actually resolvable today — check the
   target's endpoint before designing around it.
4. **Which jurisdictions, and which authority in each?** Administrative (IT, BR), judicial (IN) or
   none in force (US). This decides whether you are building a filing pipeline, an affidavit
   generator, or neither.
5. **Read the licence bytes, never the badge.** In this plane the API mislabels the two most important
   repos: `c2pa-rs` is **dual MIT + Apache-2.0** and `adobe/trustmark` is **MIT**, both reported as
   `NOASSERTION`. A gate that auto-rejects `NOASSERTION` discards the standard's own SDK.
6. **Separate code licence from weights licence.** `audioseal` is MIT **including weights** (README,
   2024-04-02); `content-seal` licenses *"the code"* and states the deployed system is a custom
   proprietary implementation. Ask which one the estimate assumes.
7. **Is a vendor contract already in place?** Session forensic marking and DRM key issuance cannot be
   delivered from open source. If no contract exists, that procurement is on the critical path and
   belongs in the plan on day one, not month four.
8. **Never offer to maintain the blocklist.** Detection, evidence and filing are buildable; the list
   itself is an instrument of state authority. Offering it misrepresents what Globant can lawfully do.

## Pattern 81 — The archive-to-catalogue pipeline: everything up to the price tag is free

**Why this pattern exists.** NewscastStudio (2026-03-30) makes archive work the clearest link between
AI spend and return in media, and states archives only become useful **after** metadata, taxonomy and
cleanup. imec-SMIT (May 2026) names archive search and retrieval a top-three European application
area. Meanwhile this pass measured the commercial step at **4 repos holding 1 star between them**.
So the pipeline splits at a precise point: **steps 1–5 are free and permissive, step 6 is a bespoke
build every time.** Price the engagement that way and the margin sits where the code does not exist.

**Licence posture: every shipped component is MIT, Apache-2.0, BSD or CC0.** The one GPL-3.0 option
(Phraseanet) is listed as a separately-deployed service, never embedded.

```
 1 CUT              2 PREVIEW          3 EMBED           4 RETRIEVE        5 DESCRIBE       6 SELL
 TransNetV2 (MIT)   hecate (Ap-2)      open_clip (MIT)   vespa (Ap-2)      croissant        ███████
 shot boundaries →  keyframes, GIFs,   frame/shot  →     embeddings  +     (Ap-2)           NOTHING
 the sellable unit  thumbnails,        vectors           structured        licence +        EXISTS
 PySceneDetect      summaries          ▲                 rights metadata   provenance       ███████
 (BSD-3) as the     ▲                  │                 in ONE query      per corpus       rate card
 cheap fallback     │                  │                 ▲                 ▲                quote eng.
                    └──────────────────┴─────────────────┘                 │                sale ledger
                                                          │                │                = BUILD IT
 CATALOGUE OF RECORD ─────────────────────────────────────┘                │
 resourcespace (BSD-3+TM, License Manager plugin: multi-licence per asset) ┘
 or phraseanet (GPL-3.0, separate service) — per-asset rights state lives here
```

### Wiring, step by step

1. **Cut the tape into shots.** [soCzech/TransNetV2](https://github.com/soCzech/TransNetV2) (MIT,
   1,083★) for quality, PySceneDetect (BSD-3, already in this KB) as the cheap fallback. The shot is
   the unit a clip is actually licensed in — get this wrong and every downstream price is wrong.
   **Vendor it: last push 2023-12-04.**
2. **Make something a buyer can browse.** [yahoo/hecate](https://github.com/yahoo/hecate) (Apache-2.0,
   497★) emits keyframes, thumbnails, animated GIFs and summaries. **Also vendor it: 2023-05-20.**
3. **Embed shots, not whole assets.** `open_clip` (MIT, already in this KB) over keyframes. Store
   per-shot vectors so a hit returns a **timecode**, which is what gets sold.
4. **Retrieve with the rights in the same query.** [vespa-engine/vespa](https://github.com/vespa-engine/vespa)
   (Apache-2.0, 7,202★, pushed today) holds embeddings **and** structured fields together, so
   "waterfront at dusk" and "cleared for broadcast in EMEA, non-exclusive, to 2029" resolve in one
   call. This is the single most important design decision in the pattern: **a search layer that
   cannot filter on rights will return shots you may not sell.**
5. **Keep the catalogue of record where the rights live.**
   [resourcespace/resourcespace](https://github.com/resourcespace/resourcespace) + its **License
   Manager** plugin (multiple licences per resource) is the only open DAM found with native sell-side
   data. **Read the licence trap in `verticals/solutions.md` (pass 42) before committing: the grant is
   BSD-3 + a trademark clause, and you cannot put "ResourceSpace" in the product name.**
6. **Build the commercial step.** Rate card by term/territory/exclusivity, quote engine, licence
   issuance, sale ledger. Measured non-existent this pass. This is the deliverable.

### Licence ledger for this pattern

| Component | Licence | Posture |
|---|---|---|
| TransNetV2, open_clip, PySceneDetect, hecate, vespa | MIT / MIT / BSD-3 / Apache-2.0 / Apache-2.0 | Ship embedded; vendor the two dormant ones |
| croissant / mlcroissant | Apache-2.0 | Ship embedded |
| resourcespace | **BSD-3 + trademark clause** | Ship, but **rename the product** and plan "Powered by ResourceSpace"; audit the bundled GPL-2.0 component |
| phraseanet | GPL-3.0 | Separately-deployed service only |
| Stax | **no licence** | **Excluded by name** — 8★, no grant, all rights reserved |

### Regional variants

- **EMEA** — lead with ITN–Reuters (70+ years, archive turned into a searchable dataset) as the
  precedent, and make step 4's rights filter also serve the DSM Art. 4 reservation record: same
  metadata, "no" and "yes, for a price" as two states of one field.
- **North America** — step 6 is the whole sale, because no industry-wide AV licensing framework exists
  (ABA, mid-2026); every buyer is bilateral and the seller needs its own instrumentation.
- **APAC** — step 4's rights fields must be **per-jurisdiction configuration**, since India has
  proposed compulsory blanket licensing and Japan a voluntary disclosure mechanism in the same year.
- **LATAM** — step 0 is Pattern 83: in Mexico the AI right may not be in the contract at all.

## Pattern 82 — Selling the archive as a corpus: the gate, the manifest and the meter

**Why this pattern exists.** A second buyer appeared for the same asset, and in 2026 it changed what
it wants. Trackers surveyed this pass report new publisher deals shifting from **training** rights to
**display/grounding** rights (one counts 47 display-only against 61 including training; another puts
display rights in 58.7% of news-publisher deals), and Microsoft's Publisher Content Marketplace makes
that a platform. A bulk corpus export and a metered grounding API are **different products**, and the
same archive has to be able to sell both without the rights state diverging.

```
  ARCHIVE (Pattern 81 output: shots, embeddings, per-asset rights state)
      │
      ├─► GATE ───────► CorpusCustody (MIT, 30★) — resolve SPDX obligations,
      │                 check compatibility, refuse the corpus that cannot ship
      │                      │  fails → back to clearance (Pattern 83)
      │                      ▼  passes
      ├─► MANIFEST ────► croissant (Apache-2.0, 923★) — schema.org-based,
      │                 dataset `license` field + RAI provenance extension.
      │                 Consumed natively by Kaggle / Hugging Face / OpenML.
      │                      │
      │          ┌───────────┴────────────┐
      ▼          ▼                        ▼
  RESERVATION   (a) TRAINING SALE      (b) DISPLAY / GROUNDING
  LEDGER        bulk export, one       metered API, per-call,
  ai.robots.txt price, one audit       WITH ATTRIBUTION — the
  + TDM reserv. trail                  2026 deal shape
  (pass 5)           │                        │
      └──────────────┴────────► SALE LEDGER ◄─┘   ← still does not exist
                                 (build it)
```

### Wiring, step by step

1. **Gate before you package.** [rishin-sharma/CorpusCustody](https://github.com/rishin-sharma/CorpusCustody)
   (MIT, 30★, pushed 2026-09-04) resolves SPDX obligations and compatibility across a corpus. It is
   the *only* open-source artefact found in this plane that stands between an archive and a buyer. At
   30 stars, treat it as a **reference implementation to extend**, not a dependency to trust blindly.
2. **Emit a manifest the buyer already reads.** [mlcommons/croissant](https://github.com/mlcommons/croissant)
   (Apache-2.0, 923★, pushed 2026-11-16) with the dataset-level `license` property populated from the
   catalogue of record — never hand-written — plus the Responsible-AI extension for provenance.
3. **Wire the reservation ledger to the same field.** Pass 5's `ai.robots.txt` and the W3C TDM
   reservation protocol express "no". This pattern expresses "yes, for this price". **They must read
   the same per-asset rights state**, or you will reserve an asset you have just sold, which is the
   failure mode that ends a licensing programme.
4. **Build two meters, not one.** Bulk training export: one price, one audit trail. Display/grounding:
   per-call metering **with attribution**, because that is what the 2026 deals and Microsoft's
   marketplace assume.
5. **Record the sale.** Measured non-existent. Yours.

### What this pattern will not do

It will not **price** anything. Croissant describes, CorpusCustody gates, the reservation protocols
refuse — and none of the three has a field for money. Pass 8 found the identical three-step gradient
in royalties: *declare* a reserve = solved; *honour* it = dormant; *liquidate* the obligation = zero
literal. **Pass 42 confirms the law a sixth time, now on the sell side: describe = alive, gate = 30
stars, transact = nothing.**

### Falsifiable prediction, logged

**By 2027-06-30, no Croissant-described commercial media archive corpus will be publicly listed with
a price.** If this is falsified, the sell-side zero has begun to close and this pattern needs rewriting.

## Pattern 83 — The Mexican re-clearance workflow: a statutory trigger with no tooling (LATAM)

**Why this pattern exists.** Mexico's May 2026 reforms to the Federal Copyright Law and Federal Labour
Law — the country's first sector-specific AI rules — **remove AI uses from the rights automatically
granted in audiovisual production contracts; a separate written agreement is now required** (Chambers,
*Media & Entertainment 2026*, Mexico). A new Federal Law on Cinema and Audiovisual followed on
22 May 2026, extending oversight to VOD. **Consequence: a Mexican back catalogue does not come with AI
rights attached.** Before one hour can be licensed for training or grounding, the AI right must be
re-acquired contract by contract. Open-source support for that work, measured this pass:
`rights clearance` = **40 repos whose top six hold 2,2,1,1,1,1 stars**.

```
 CONTRACT INVENTORY        PER-ASSET RIGHTS STATE        RE-ACQUISITION          LICENSABLE SUBSET
 (the hard part)           (the catalogue)               (the legal work)        (the product)
 scanned agreements  ──►   resourcespace License    ──►  outreach workflow  ──►  "cleared for AI,
 OCR + layout (pass 39     Manager: multi-licence        per counterparty,       MX, training+display"
 stack: tesseract,         per asset — model the         dated, evidenced        = the ONLY subset
 ocrmypdf, docling)        AI right as its OWN                │                  Pattern 82 may export
       │                   licence row, absent by            │                          ▲
       │                   default, NEVER inferred           │                          │
       └──────────────────────────► CorpusCustody gate ◄──────┴──────────────────────────┘
                                   refuses anything whose AI row is empty
```

### Wiring, step by step

1. **Inventory the contracts, not the footage.** Reuse this KB's pass-39 digitisation stack (OCR,
   layout, text layer) against the agreement archive. The binding constraint is paper, not video.
2. **Model the AI right as a first-class, absent-by-default licence row.** ResourceSpace's License
   Manager supports multiple licences per resource — use one row per right type and leave the AI row
   **empty** until a signed agreement fills it. *Never* infer it from the production contract: the
   reform's entire effect is that the inference is no longer valid.
3. **Gate on it.** CorpusCustody (MIT) refuses any corpus containing an asset whose AI row is empty.
   This is what makes the clearance programme auditable rather than aspirational.
4. **Sell only the cleared subset** via Pattern 82.

### Why this is the best-qualified LATAM engagement in the KB

The trigger is **statutory, dated and public** — not a trend, a survey or a vendor claim. Compare the
rest of the region, where this pass found the demand side articulated (BVS Media Connect 2026: *the
video library stops being a passive archive and becomes a searchable, exploitable asset*; LA NACIÓN's
*Flashback* animating its own photo archive) but **no public archive-for-AI licensing deal by any
LATAM broadcaster** — searched in Spanish and Portuguese, recorded as an informed gap in
`intel/market.md`. In Mexico the law tells you the work is required. Everywhere else in the region you
are still selling the idea.

### Regional variants

- **Brazil** — holdings are *espalhado por inúmeras instituições* with a national mapping effort live;
  the equivalent step 1 is a **federated inventory** across custodians, fundable as heritage and
  commercial work at once. Openverse (MIT) is the closest working model for licence-aware federated search.
- **Colombia** — CISAC/DASC are asking for AV AI rules that do not exist yet; build the rights rows so
  a future rule can be applied retroactively rather than re-surveyed.
- **APAC/EMEA reuse** — steps 2–3 are jurisdiction-agnostic; only the "is the AI right conveyed by
  default?" answer changes. That answer is the per-jurisdiction policy table from Pattern 81's APAC variant.

## What not to promise in this plane (pass 42)

1. **Never promise an open-source clip-licensing platform.** Measured: `stock footage licensing` = 4
   repos, top stars 1,0,0,0; `footage marketplace` = 18 with 7 stars across the top six;
   `media licensing marketplace` = 6 whose top three are junk repos. If a vendor claims one, ask for
   the repository URL.
2. **Never quote `clip licensing` or `media licensing marketplace` result counts as evidence of a
   field.** 47 and 6 results respectively, **zero relevant** — FTC robotics, smartwatch firmware,
   Windows software policy. Read the results, never the total.
3. **Never put ResourceSpace in a white-labelled product without reading its licence file.** The grant
   is BSD-3 **plus a trademark clause**; the product cannot be named "ResourceSpace", and a GPL-2.0
   component ships in the licence folder.
4. **Never build on Stax** (8★, **no licence file** → all rights reserved), however well it fits.
5. **Never present TransNetV2 or hecate as maintained.** Both are ~3 years cold. The MIT/Apache grant
   survives abandonment; the bug fixes do not. Budget for vendoring.
6. **Never assume a back catalogue conveys AI rights.** In Mexico it does not, by statute, since May
   2026 — and the same question is unsettled in most other jurisdictions.
7. **Never promise collective licensing as the EMEA route.** The commercial broadcasters' own
   association (ACT, June 2026) argued collective licensing **cannot** accommodate the complexity of
   AV rights and that licensing must be voluntary, direct and rightsholder-controlled.
8. **Never cite this pass's market figures as audited.** They come from secondary trackers that
   disagree, and the session's network policy blocked primary retrieval (see the channel note in
   `intel/trends.md`). Repo facts: verified by `ls-remote` + API. Press figures: cited, unfetched.

## Composition-side recipes — added 2026-11-27 (pass 43)

Concrete wiring for the lyrics / chords / score-capture / publishing-rights plane. Every repo named
below is measured in `repos/foundations.md` and `agents/top.md` for the same date, with licences read
from files and existence confirmed by `git ls-remote` (29/29).

## Pattern 84 — The per-element authorship ledger: build the field the regulator prices and no format has

**The opening.** JASRAC (June 2026) sets its management rate by **which element** a human made —
**100%** when AI wrote only one element, **50%** when both lyrics and melody involve AI. ASCAP/BMI/SOCAN
make eligibility turn on an AI-assisted-versus-wholly-AI declaration. Mexico's LFDA/LFT amendments
(14 May 2026) attach a labour entitlement to the same share. **And no open format in this plane has a
field for it** — MusicXML and MEI describe notes, LRC describes timings, ChordPro describes chords,
OpenLyrics describes words; the only homes are free-text escape hatches.

**The wiring.**
1. **Model the song as elements, not as a file.** One record per element — lyrics, melody, arrangement,
   production — each with: author identity, human/AI/hybrid flag, the tool and version if AI was
   involved, timestamp, and the evidence pointer. This is the whole product; everything else is I/O.
2. **Carry it alongside the score, not inside it.** Emit MusicXML via **`verovio`** (LGPL-3.0, p12) or
   **`music21`** (BSD-3) for the notes, and keep the ledger as a **sidecar** document keyed to element
   IDs. Writing provenance into `<miscellaneous>` makes it unqueryable and non-portable — do not.
3. **Compute the share as a function, not a stored number.** JASRAC's 100%/50% is one jurisdiction's
   arithmetic over the ledger. Korea withdrew its rules after 22 days; the EU may go statutory. Follow
   pass 8's rule and build a **per-jurisdiction policy engine** over one evidence store.
4. **Sign the record at creation.** Pass 5's identification work and pass 41's soft-binding work both
   apply: a provenance claim nobody can verify is worth what an affidavit is worth.

**Why this beats AI detection, and say so in the room.** KOMCA and five other Korean bodies are
selecting an AI-detection vendor *right now*, and the published reporting says the tools **fail on
partly AI-made tracks** — exactly the category the rules exist to govern. Detection after the fact
cannot recover a per-element share; **provenance at creation records it for free.**

**Falsifiable prediction attached.** The first format to standardise a per-element provenance field
takes the registration workflow. Watch the MusicXML/MEI trackers and DDEX; a field before mid-2027
confirms this pattern's premise.

## Pattern 85 — Score capture: pick your licence before you pick your engine, because there is no third option

**The measured constraint.** Every maintained OMR engine is copyleft — **Audiveris** (AGPL-3.0,
3,019★, pushed 2026-11-25) and **homr** (AGPL-3.0, 497★, pushed 2026-11-27). Every permissive one is
dormant — **oemer** (MIT *template, unfilled*, HEAD 2025-04-18), **Mozart** (Apache-2.0, 2022-08-24),
**SMT** (MIT, 2026-09-27), **MeasureDetector** (MIT+Apache-2.0, 2026-06-14), **OMR-Datasets** (MIT,
2024-04-01). There is **no actively-maintained permissive OMR engine today.**

**Route A — accuracy, and you ship AGPL-3.0.**
`MeasureDetector` (segmentation) → **`Audiveris`** or **`homr`** (recognition) → MusicXML →
`verovio`/`alphaTab` (MPL-2.0) for display → `music21` (BSD-3) for analysis. Run the AGPL engine as a
**batch worker behind a queue**, with your own code in separate processes communicating over files or
a message bus. Be explicit that AGPL-3.0 reaches a hosted service and that this architecture is a
containment strategy, not an exemption — then price the obligation.

**Route B — permissive, and you adopt an unmaintained upstream.**
**`SMT`** (MIT, the only permissive engine touched this year) or **`oemer`**, trained or fine-tuned on
**`OMR-Datasets`** (MIT). Budget for maintenance you now own. **Before shipping `oemer`, get the
upstream `LICENSE` fixed** — it still reads `Copyright (c) [year] [fullname]`, a grant naming no
grantor, while `setup.py` claims MIT. An unresolved licence is a worse problem than an old commit.

**Route C — the honest first engagement.** Start on **public-domain catalogues**, where the content
licence is not a counterparty risk at all. It is the only sub-segment of this plane with no clearance
problem, which makes it the right place to prove the pipeline before anyone's repertoire is involved.

## Pattern 86 — Synced lyrics at scale, where the code is MIT and the words are not

**The wiring.** **`lrclib`** (MIT, 2,314★) self-hosted as the lookup service and corpus store →
**`ctc-forced-aligner`** (BSD-2, 579★) or **`WhisperX`** (BSD-2, 25,723★) to time *your* catalogue →
LRC/ASS output → **`lrcget`** (MIT, 3,392★) as the reference client behaviour to copy. Use
**`syncedlyrics`** (MIT) only as a format reference: it has been dormant since 2024-07-28.

**Prefer `WhisperX` or `ctc-forced-aligner` over `whisper-timestamped`** (2,858★) for one reason only:
`whisper-timestamped` is **AGPL-3.0** and the other two are BSD-2. All three solve the problem; only
two leave your deployment options open.

**The clearance step that is not optional.** **Displaying lyrics in time with music is a licensed
act, and the synchronisation/reprint right sits with the music publisher** — not the recording owner
your client probably has a deal with. `lrclib` is MIT and its README contains **zero** mentions of
licence, copyright, DMCA or takedown for the corpus it serves; `LyricsGenius` (MIT) is permissive code
over a third party's API and words. **Never scope this as "open source end to end."** The pipeline is
open; the words are cleared per territory, from publishers. Put the clearance line item in the first
estimate — it is the single most common way a lyrics product dies late.

## Pattern 87 — The karaoke plant: copyleft players, permissive generation

**The wiring.** Separation with **Demucs** (p12) → transcription and timing with
**`karaoke-gen`** (MIT, 193★, pushed the day of this pass) → render to the **UltraStar song format**
→ play on **`USDX`** (GPL-2.0, 1,320★), **`Performous`** (GPL-2.0+, 650★) or **`Vocaluxe`** (GPL-3.0,
343★). Pitch scoring and feedback come free from Performous; extend analysis with **`basic-pitch`**
(Apache-2.0, p12).

**Target the format, not the player.** All three maintained players are copyleft, and all three read
the **UltraStar format** — so the format, not any one binary, is the integration surface. Write to it
and you inherit the entire hobby content ecosystem without inheriting GPL into your own product.

**Depend on `karaoke-gen`, not its library sibling.** `python-lyrics-transcriber` (MIT, 93★) was
**archived 2026-01-19** while `karaoke-gen` shipped on the day of this pass — the library folded into
the end-to-end tool. If you need the transcriber standalone, **vendor it**: an archived repo takes no
patches.

## Pattern 88 — The songbook and chord-chart line, and the one licence to send to review

**The wiring.** **`ChordPro`** (549★) as the source format — chords and lyrics in plain text, rendered
to print-ready PDF/HTML → **`pychord`** (MIT, 292★) for transposition and chord-symbol logic →
**`alphaTab`** (MPL-2.0, 1,951★) for interactive web display with playback → **`tuxguitar`**
(LGPL-2.1, 1,666★) when Guitar Pro file interop is required, which in the tab market it usually is.
Extract chords from audio with **`chord-extractor`** (GPL-2.0) as a **batch step**, never linked in.

**Two licence facts to carry into the proposal.** `ChordPro` is **Artistic-2.0** — the first
appearance of that licence in this KB; OSI-approved and permissive in practice, but outside Globant's
MIT/Apache/BSD set, so send it to review rather than assuming it passes. And `tuxguitar`'s **LGPL-2.1**
(found in **`docs/LICENSE`**, which is why GitHub reports `NOASSERTION`) permits linking from a
proprietary application provided the library stays replaceable — making it the **most commercially
flexible platform in this plane**.

## What not to promise in this plane (pass 43)

- **Do not promise a royalty or mechanical-licensing system "built on open source."** Measured
  2026-11-27: `mechanical royalty` → 13 results, relevant top-six **0★**; `music royalty accounting`
  → 14 results, **4★**; `lyrics sync licensing` → **1 result, 0★**. Pass 8's 0★ measurement
  reproduces. There is nothing to build on; there is only something to build.
- **Do not promise a permissive score-capture engine.** None is maintained. Say which of Route A, B or
  C you are taking and what it costs.
- **Do not promise "open source end to end" for anything involving lyrics.** The sync/reprint right is
  the publisher's; a permissive code licence never reaches the words.
- **Do not promise ISWC-based matching.** ISWC and CWR have no usable open implementation (p5: CWR's
  only two are dead since 2015 and 2018). **And do not search for it:** `ISWC` returns **434 results,
  zero relevant** — the International Semantic Web Conference. A row sourced from that search is
  fiction.
- **Do not quote a 0.02% CAGR, and do not quote a karaoke market figure.** The first is a data
  artefact; the second **does not exist in this KB** — it was searched and nothing came back.
- **Do not quote JASRAC's 100%/50% as settled.** The gate is corroborated; the percentages are
  **single-source** (Asiae) and JASRAC's own guideline text has not been read.
- **Do not state the MLC's position on AI-assisted registrations.** Two 2026 sources **directly
  contradict** each other and no primary source was reached. Say that, and offer to confirm it.

## IP-plant recipes — added 2026-11-27 (pass 44)

Every repo named below was verified on 2026-11-27 (`git ls-remote` existence, GitHub search API stars
and last push, licence file read where the API said `NOASSERTION`). The licences are quoted in the
recipes because in this plane the licence decides the architecture, not the other way round.

**Read first — the constraint that shapes all five patterns.** In the IP plant the permissive, active
open source is all **control** (NMOS, Apache-2.0 throughout); every tool that **measures** whether the
plant is healthy is copyleft, unlicensed or abandoned (`intel/trends.md`, finding 1). So: build
permissively on the control side, and put the copyleft analyser behind a service boundary. And the
standards **text** is derivative-blocked — Apache-2.0 code, **CC BY-ND 4.0 spec text**, and SMPTE's own
documents all-rights-reserved — so no deliverable paraphrases the standard.

## Pattern 89 — Rundown-to-fabric: resolve a Sofie take to an IS-05 connection (the highest-differentiation build in this KB's broadcast territory)

**The gap.** This KB's pattern 7 put an agentic newsroom on **Sofie** (MIT) and stopped at the
automation layer. Sofie decides *what goes to air*; it does not move essence between the boxes that
make it. The IP plant decides *how the essence moves*. Nobody has joined them in open source.

**The build.**
1. **Plant inventory:** stand up [`rhastie/easy-nmos`](https://github.com/rhastie/easy-nmos)
   (Apache-2.0, 93★) — registry + virtual node + test tool in one compose file — and develop against
   it with no broadcast hardware. Promote to [`sony/nmos-cpp`](https://github.com/sony/nmos-cpp)
   (Apache-2.0, 204★) as the production registry/node.
2. **Enumerate** senders, receivers and devices over **IS-04**; model them as the resources a rundown
   can reference.
3. **Execute the take** over **IS-05** connection management. Borrow the action semantics from
   [`bbc/nmos-web-router`](https://github.com/bbc/nmos-web-router) (Apache-2.0, 16★) — a broadcaster's
   own reference for exactly this operation — rather than inventing them.
4. **Tally and events** over **IS-07**; **audio shuffles** over **IS-08**. Both are where real
   facilities spend their time, and both are Apache-2.0 specs.
5. **Gate every device** with [`AMWA-TV/nmos-testing`](https://github.com/AMWA-TV/nmos-testing)
   (Apache-2.0, 71★) in CI, and every stream description with
   [`AMWA-TV/sdpoker`](https://github.com/AMWA-TV/sdpoker) (Apache-2.0, 22★).
6. **Keep the agent on the proposing side.** It reads state, diagnoses, and *proposes* a take; a human
   or the existing controller commits it.

**Why it is safe to propose:** every component above is Apache-2.0. Nothing in the critical path is
copyleft, and the whole chain is testable on a laptop before anyone books facility time.

**Qualifying question:** *"when your rundown calls a source, what makes the route happen today?"* If
the answer is a hardware router under a proprietary protocol, this is a two-phase engagement and
phase one is the inventory, not the agent.

## Pattern 90 — The conformance gate as the deliverable (the smallest sellable unit in this plane)

**The insight.** `nmos-testing` is **Apache-2.0**, which means a compliance gate built on it can be
shipped to a client as product. That is rare: in most planes in this KB the conformance tooling is the
part you cannot redistribute.

**The build.**
1. Run [`AMWA-TV/nmos-testing`](https://github.com/AMWA-TV/nmos-testing) against every device, per
   specification (IS-04, IS-05, IS-07, IS-08, IS-09), and record **which specifications at which
   versions** each device passes.
2. Run [`AMWA-TV/sdpoker`](https://github.com/AMWA-TV/sdpoker) over the SDP files — **SDP is where
   real 2110 deployments break**, and this is a cheap, high-yield check.
3. Emit a dated, diffable conformance report per device. The diff over time is the artefact the client
   did not have.
4. **The refusal that makes it credible:** the report states what was tested and what was not. It does
   not assert "NMOS-compliant", because that phrase is at least six separate claims and **IS-06 is
   formally deprecated**.
5. Use the agent to triage: hundreds of test results a week, of which a handful matter.

**Why this is the first thing to sell:** it is days of work, it needs no production access, and it
produces the inventory every later phase depends on. It is also the honest answer to "are you on 2110
yet?" — a question this KB has been asking since pass 31 without being able to help answer it.

## Pattern 91 — The commissioning evidence trail, with the copyleft analyser behind a boundary

**The constraint, stated plainly.** If a delivery includes evidence that a 2110 plant works, that
evidence comes from [`ebu/pi-list`](https://github.com/ebu/pi-list) (**GPL-3.0**, 134★) or
[`pkeroulas/st2110-toolkit`](https://github.com/pkeroulas/st2110-toolkit) (**GPL-3.0**, 105★). The
only permissive analyser ever published,
[`ebu/smpte2110-analyzer`](https://github.com/ebu/smpte2110-analyzer) (Apache-2.0, 93★), **has not been
pushed since 2020-05-01**. Plan for copyleft from day one; do not discover this at delivery.

**The architecture.**
1. **Deploy EBU LIST unmodified, as a separate service.** Integrate over its API. Do not patch it,
   do not link it, do not vendor it into a product tree — modify it and the GPL follows your changes
   to your client's users.
2. **Generate your own test corpus** with
   [`OpenVisualCloud/Media-Transport-Library`](https://github.com/OpenVisualCloud/Media-Transport-Library)
   (BSD-3-Clause, 254★) rather than depending on
   [`ST2110_pcap_zoo`](https://github.com/NEOAdvancedTechnology/ST2110_pcap_zoo) — those reference
   captures are **unlicensed** and dead since 2022.
3. **Timing is its own evidence stream.** `linuxptp` (GPL-2.0) as the PTP reference — ship it as a
   system package, never linked. Note the profile trap: **ST 2110 requires the ST 2059-2 profile while
   AES67 wants the Default/Media profile, and they use different delay mechanisms — running both in
   one domain is a misconfiguration.**†
4. **Your permissive layer is the evidence ledger**, not the probe: timestamped runs, pass/fail per
   stream, the diff between commissioning and today. That is yours to license as you wish.
5. **Do not propose `ptpmeasure`** (65★) — it has **no licence file at all**, verified against a live
   README.

**The revival option, stated once:** `ebu/smpte2110-analyzer` is Apache-2.0, EBU-authored, and
abandoned. Reviving it is the single highest-leverage contribution available in this plane — it would
give the industry the permissive analyser it currently does not have.

## Pattern 92 — The software-defined facility on MXL (the forward-looking build, and the one with a real deadline risk)

**The opportunity.** [`dmf-mxl/mxl`](https://github.com/dmf-mxl/mxl) (**Apache-2.0**, 192★, pushed
2026-11-27) is the first permissively-licensed, vendor-neutral **data plane** for a broadcast
facility — Linux Foundation hosted, EBU + NABA + AMWA, with BBC, CBC/Radio-Canada, France
Télévisions, SVT, RTÉ and VRT contributing.†

**The build.**
1. **MXL as the essence bus** between software media functions on a host; v1.1 reportedly extends
   this across clustered hosts over **RDMA**.†
2. **NMOS as the control plane over it** — AMWA has published a specification for managing MXL
   connections over NMOS,† and [`AMWA-TV/jt-dmf-crm`](https://github.com/AMWA-TV/jt-dmf-crm)
   (Apache-2.0, 9★) carries the reference model. **This is the convergence to build toward.**
3. **Processing** with [`Eyevinn/strom`](https://github.com/Eyevinn/strom) (Apache-2.0, 81★,
   GStreamer) or [`infantilo/pipeline-controller`](https://github.com/infantilo/pipeline-controller)
   (MIT, 6★).
4. **Mezzanine compression where a link cannot carry uncompressed:**
   [`OpenVisualCloud/SVT-JPEG-XS`](https://github.com/OpenVisualCloud/SVT-JPEG-XS) —
   **BSD-2-Clause-Patent**, which carries an express patent grant and is the right licence posture for
   a codec.
5. **Study, don't vendor:** [`bob-integration/bobistudio`](https://github.com/bob-integration/bobistudio)
   (GPL-3.0, 18★, **beta**) is the first orchestrator built on MXL and the best worked example — read
   it, run it as a separate process, do not link it.
6. **For an FFmpeg path**, [`cbcrc/guidance-for-building-ffmpeg-with-mxl`](https://github.com/cbcrc/guidance-for-building-ffmpeg-with-mxl)
   (12★) documents the build — but it has **no licence file**, so treat it as reading material and
   write your own.

**⚠️ The honest risk, stated to the client before they fund it.** MXL is roughly a year old; its v1.1
details come from trade and vendor reporting that this KB has not verified against primary release
notes;† its satellite ecosystem is six projects with 0–12★ each. **This is a bet on a forming
standard, not a mature platform.** It is the right bet for a broadcaster with an EBU affiliation and
an engineering team, and the wrong one for a client who needs air-date certainty this year. Say which
of the two they are before writing the proposal.

## Pattern 93 — The 20-minute licence gate for any IP-plant or 2110 proposal

Run this before estimating. It has caught something in every plane this KB has gated.

1. **Which specifications, at which versions?** "NMOS-compliant" is six claims minimum. **IS-06 is
   deprecated** — if a vendor or an RFP cites it, that is a dated document and the rest of it needs
   checking too.
2. **Is any deliverable a derivative of the standards text?** If the scope includes annotated,
   abridged, restructured or **translated** documentation of NMOS or ST 2110, stop. The AMWA spec text
   is **CC BY-ND 4.0** (no derivatives) and the SMPTE documents are **all rights reserved**. *No fee
   unblocks this* — unlike CPT and MedDRA in this KB's other planes, it cannot be bought. Documenting
   the **client's own facility, SDP files and conformance results** is clear; paraphrasing the
   standard is not.
3. **Does the scope include commissioning or monitoring evidence?** Then a **GPL-3.0** analyser is in
   your architecture (pattern 91). Decide the service boundary now.
4. **Does anything link `linuxptp`?** GPL-2.0 — system package, separate process, never linked.
5. **Check every candidate repo for a licence file, not a licence badge.** This plane is full of
   starred code with no licence at all: `ptpmeasure` 65★, `NVIDIA/Rivermax` 72★,
   `voc/aes67-recorder` 108★, all the `NEOAdvancedTechnology` dissectors and the pcap fixtures.
   **Verify absence with a control request** — a 404 on the raw channel proves nothing on its own if
   the README 404s too (the naming-convention trap recorded in pass 8).
6. **Is the facility hybrid?** Assume yes: two 2026 surveys put SDI at **70%** and **82%** of
   facilities (`intel/trends.md`, finding 4). Most 2110 exists as **"IP islands"**, so scope the seams
   between islands, not a greenfield fabric.
7. **Who will run it after you leave?** APAC reporting makes the **IT/networking skills shortage** the
   binding constraint on IP migration,† not the technology. If there is no answer, enablement belongs
   in the proposal and it is not a discount item.

## ⛔ What not to promise in this plane (pass 44)

- **An autonomous agent that makes live routes.** A wrong IS-05 take puts a channel to black. Agents
  read, diagnose and propose; humans and existing controllers commit.
- **AI-generated documentation of the standards.** Derivative-blocked, and no payment changes that.
- **A permissive end-to-end stack including monitoring.** It does not exist. The control plane is
  permissive; the analyser is GPL-3.0; saying otherwise will be found out at delivery.
- **A configuration-only delivery.** There is no turnkey platform at *any* licence in this plane
  (`verticals/solutions.md`). Every honest proposal here is an integration proposal.
- **A market-sized business case.** The NMOS/IP-control software segment is **not sized anywhere**
  (`intel/market.md`, pass 44 addendum). Price from the obligation and the integration, never from a
  borrowed TAM.


## Pattern 94 — The EAS cyber-compliance evidence trail (the one deliverable in this plane with a deadline already behind it)

**Why:** The FCC's EAS cybersecurity rules are in force — Federal Register **2026-07-31**, effective
60 days later, implementation date **2026-09-29** — and they cover **every FCC-licensed station**,
across EAS units *plus* automation systems, audio processors, STLs, RDS encoders and transmitters.
The nationwide test of **2026-11-17** is usable by the Commission to assess compliance, and a station
that fails to receive an alert because its equipment was not updated **can be found in violation**.†
The client is late, the scope is their whole program chain, and the regulator has an observable
trigger. Nothing else in this plane sells itself this directly.

**Wiring:**

1. **Inventory the program chain as a graph, not a list.** Every internet-reachable device between
   automation and transmitter: EAS unit, playout/automation, audio processor, STL, RDS encoder,
   transmitter. The three regulated properties per device are **authentication** (no default
   passwords, strong or qualifying alternative auth), **patch state** (manufacturer updates tested
   and installed promptly), **reachability** (firewall or comparable segmentation restricting remote
   management).
2. **Instrument the receive path independently of the EAS box.** Put a software monitor beside the
   appliance so "did the alert arrive?" has an answer that does not come from the device under test:
   `cbs228/sameold` + `samedec` (**Apache-2.0** — the only permissive demodulator in the plane) on
   an SDR feed, decoding SAME headers to a timestamped log. For the station-side console,
   `KR8MER/eas-station` (**AGPL-3.0**, monitoring/broadcasting/verifying NOAA + IPAWS) **behind a
   process boundary with its source offer honoured** — never linked into client code.
3. **Reconcile against the national test calendar.** Each nationwide and required weekly/monthly
   test becomes a row: expected at T, decoded at T+n, by which device, logged where. That table *is*
   the compliance artefact.
4. **Produce the segmentation proof as configuration-as-code**, so the evidence regenerates instead
   of being re-screenshotted at each renewal.
5. **Hand the life-safety path back.** The monitor observes; it never gates or forwards an alert.
   `cuppa-joe/dsame` disclaims life-safety use in its own README and `multimon-ng` calls its EAS
   decoder alpha — quote both lines in the SOW so the boundary is contractual.

**Sell it as:** a recurring compliance-evidence service per station group, priced from device count.
**Do not** sell it as EAS equipment replacement; the appliances are certified and you are not.

## Pattern 95 — The TV 3.0 advanced-alert integration, against a guideline that is already published (LATAM)

**Why:** Brazil is the only market where advanced broadcast alerting is **mandated, specified and
dated**. TV 3.0 / **DTV+** was adopted by decree in **August 2025** on ATSC 3.0 technology including
emergency alerting; the **SBTVD Forum's "TV 3.0 Operational Guidelines — Emergency Warning System"
(June 2026)** defines broadcaster behaviour, references **ABNT NBR 25607:2025**, and specifies
**monitoring IDAP**, Brazil's Public Alert Notification Interface.† In North America the equivalent
capability is still **awaiting FCC action on AWARN's late-September-2026 petition**.† So the
reference implementation is buildable in Brazil now and nowhere else.

**Wiring:**

1. **IDAP ingest, treated as untrusted input.** Poll/subscribe per the June 2026 guideline, validate
   the CAP payload against **CAP 1.2** before anything renders. Parse with `cB-Sigma/cap`
   (**Apache-2.0**, pure Go, the only permissive library that handles **XML signatures**, GeoJSON
   areas and feeds — 0★, so read it first and own the fork) or `kelvinn/capparselib` (**MPL**,
   actively maintained; file-level copyleft, so modified parser files must be published — flag at
   review).
2. **Geo-filter before rendering.** The guideline's model is area-scoped alerting; resolve the CAP
   `<area>` polygon/geocode against the station's service contour so a regional alert does not go
   national. The peer-reviewed SET/IJBE work on **geolocated TV 3.0 alerts for public health
   services** is the local prior art to cite.†
3. **Render the rich payload for the capability that actually exists:** maps, short video, and
   **multiple audio presentations and languages** — the multilingual and accessibility leg is the
   part of ATSC 3.0 alerting that differentiates it from a text crawl, and it connects directly to
   this KB's accessibility plane (pass 3).
4. **Verify off-air, independently.** `adswill/OnAir` (GPL-3.0, 1,129★, active) receives ATSC 3.0
   among 330+ modes — use it to confirm what the transmitter actually emitted, as a separate process.
   `drmpeg/gr-atsc3` (GPL-3.0) is the transmit-side reference if a lab signal is needed;
   `nekohkr/danttoUHD` (**MIT**) converts 3.0 to MPEG-2 TS for legacy tooling.
5. **Log every alert end-to-end**: received from IDAP, validated, geo-matched, rendered, emitted,
   confirmed off-air. In a plane with a national false-alert incident on record, the log is the
   deliverable the client's regulator will ask for.

**⚠️ Verify before proposing:** full commercial TV 3.0 rollout status was **not confirmed** in this
pass. Ask the broadcaster where they are between experimental and commercial transmission.

## Pattern 96 — The alert authentication and verification boundary (build, because the open version died in 2015)

**Why:** **ETSI TS 102 900** states that cell broadcast gives the device **no way to authenticate**
that an alert is genuine.† In **June 2026** attackers breached Brazil's emergency alert system and
sent **millions of false "extreme" alerts**.† The only open project that authenticated and signed CAP
alerts — `CAPTools/CAPCollector`, **BSD-3-Clause** — **died 2015-06-02**. One library in the entire
plane mentions XML signatures and it has **0★**. This is a build, and the justification is primary.

**Wiring:**

1. **Make provenance a first-class field, not a log line.** Every ingested alert gets: source feed,
   transport, signature present/absent, signature valid/invalid/unverifiable, signer identity,
   receipt time, and the originator's claimed authority. **"Unverifiable" must be a distinct state
   from "invalid"** — in this plane most real alerts arrive unsigned, and conflating the two either
   blocks genuine warnings or waves through forged ones.
2. **Validate what can be validated.** XML-DSig on CAP where present (`cB-Sigma/cap`, Apache-2.0);
   CAP profile conformance (`google/cap-library` is **archived** — vendor the validation logic, do
   not depend on the repo); cross-source corroboration where the same hazard appears on an
   independent feed (`seevee/cap_alerts`, **MIT**, already normalises NWS/ECCC/MeteoAlarm/BoM/DWD).
3. **Corroborate against detection, not just against another feed.** `xspanger3770/GlobalQuake`
   (**MIT**, 408★) and `openeew/openeew` (**Apache-2.0**, Linux Foundation/Grillo/IBM) give an
   independent physical signal for seismic events: an alert with no corresponding detection is a
   question worth raising before air.
4. **Two separate policies, written down.** *Display* policy (what reaches air, and with what
   provenance badge) and *escalation* policy (what wakes a human). A low-confidence alert is a
   newsroom decision, not an automation decision.
5. **Never originate.** This component authenticates, corroborates and evidences. The send stays with
   the authorised originator. Say so in the architecture document, because the failure mode here is
   regulatory, not technical.

**Revival option worth proposing explicitly:** `CAPTools/CAPCollector` is **BSD-3-Clause**, which
means the eleven-year-old implementation of exactly this problem can be lawfully revived and
contributed back. That is a credible open-source-citizenship story attached to a real client need —
rare in this KB, where most dead code is unlicensed.

## Pattern 97 — The three-question qualifier for any alerting engagement (ask before scoping anything)

**Why:** This plane punishes an architecture chosen before the client's legal position is known. All
three questions are cheap, and each one eliminates a whole class of proposal.

1. **"Are you an authorised originator, or a disseminator?"** Origination requires a state-issued
   credential and mandate — an IPAWS COG in the US, IDAP authorisation in Brazil, the national
   competent authority under **EECC Art.110** in the EU. **No licence or platform choice changes
   this.** If they are a disseminator, every "issue an alert" feature is out of scope, permanently.
2. **"Which obligation are you actually under, and what evidence does it require?"** In the US it is
   now largely a **cybersecurity** obligation on the program chain (deadline **2026-09-29**, already
   passed → pattern 94). In the EU, Art.110 is **technology-neutral** and **BEREC** publishes
   guidelines on assessing *effectiveness* — so the deliverable is a reach measurement, and a World
   Bank assessment records **Malta** as not yet meeting its obligations, which is the proof that
   non-compliance is real.† In Brazil it is carriage conformance to a **published June 2026
   guideline** (→ pattern 95). **The same plane, three different deliverables.**
3. **"What do you do with an alert you cannot authenticate?"** If there is no answer, pattern 96 is
   the engagement. If there is an answer, ask to see the log — and if the log does not distinguish
   *unverifiable* from *invalid*, pattern 96 is still the engagement.

**Then the licence gate, which in this plane is unusually tight.** Of everything measured: the one
permissive demodulator is `cbs228/sameold` (**Apache-2.0**); the one permissive platform is
`sahana/eden` (**MIT**, 37★); the one permissive signature-capable library is `cB-Sigma/cap`
(**Apache-2.0**, 0★). Everything else operational is **AGPL-3.0, GPL-3.0, MPL, unlicensed or
archived**. Design the service boundary in the proposal, not at delivery.

**⛔ And the sentence to delete from any deck in this plane:** *"an open-source alerting stack."*
There isn't one. There is a free format, a healthy sensor layer, a hobbyist receive layer, a dead
signing server, and an obligation the client cannot delegate.

## Radio delivery recipes — added 2026-11-27 (pass 46)

Every repo named below was verified on 2026-11-27: existence via `git ls-remote`, stars/push via GitHub
`search/repositories`, licences read from the actual files. The licence of each component is stated
because in this plane it is the thing that decides whether a build is sellable.

## Pattern 98 — The dashboard metadata feed (**the highest-value build in this plane, and the one with a published benchmark**)

**Problem.** A station group's logo, now-playing text and artwork are wrong, stale or absent on car
dashboards. Measured consequence: Townsquare's stations held a **0.5 share** in DTS AutoStage *before*
they began supplying now-playing metadata. Radio World: *"Visual Display Is a Cost of Doing Business."*

**Why it is a build and not an integration.** The entire open RadioDNS toolchain is **8 repos / 96
stars**; the standards body's own Java library has **10★**; the EBU's full-featured manager
(`ebu/radiodns-manager`, GPL-3.0, 15★) has been **dormant since 2023-05-01 with 89 open issues**; two
client libraries last moved in **2011** and **2008**. There is nothing to simply deploy.

**The wiring.**

1. **Source of truth** — the automation system's now-playing output. Read it with
   [`ghaiklor/icecast-parser`](https://github.com/ghaiklor/icecast-parser) (**MIT**, 72★) straight off the
   Icecast/SHOUTcast stream if the automation has no clean API; otherwise take LibreTime's or AzuraCast's
   own API. The MIT licence here matters — this component ends up inside the client's product.
2. **Normalise once, emit three ways.** One internal canonical record (track, artist, artwork URI,
   programme, segment type) → three emitters. This is the actual deliverable.
3. **Emitter A — RadioVIS** (the slideshow/visual channel): fork
   [`bbc/node-radiovis-stomp-server`](https://github.com/bbc/node-radiovis-stomp-server)
   (**Apache-2.0**, 13★, **pushed 2026-11-04 — the only live repo in the layer**). Reference behaviour from
   [`bbc/RadioVisDemo`](https://github.com/bbc/RadioVisDemo) (**Apache-2.0**, 28★).
4. **Emitter B — SPI / RadioEPG XML** (**ETSI TS 102 818**, free): there is **no maintained library** —
   `spi radiodns xml` returns **0 repositories**. Generate from the ETSI schema directly. Use
   [`magicbadger/python-dabepg`](https://github.com/magicbadger/python-dabepg) (GPL-2.0, 3★, **2017**) as a
   **reference for the schema only, behind a process boundary** — do not link GPL-2.0 into a product.
5. **Emitter C — DTS AutoStage feed** (proprietary): Xperi's onboarding. **Free to the station** —
   carmakers pay. No code to write beyond the feed format; the value is that steps 1–2 make it consistent
   across every station in the group.
6. **Resolution plumbing** — [`radiodns/java-radiodns`](https://github.com/radiodns/java-radiodns)
   (**Apache-2.0**, 10★) or [`bbc/node-radiodns`](https://github.com/bbc/node-radiodns) (**Apache-2.0**,
   7★) for the DNS lookup that maps a broadcast parameter set to a hostname.

**Licence shape: clean.** Steps 1, 3, 6 are MIT/Apache-2.0. The only copyleft (step 4's reference) stays
behind a boundary and ships nothing.

**The deliverable to quote.** Not "RadioDNS integration" — **a before/after share delta in AutoStage**,
of exactly the kind Townsquare published. That is measurable within one ratings period and it is the
client's own number, not a vendor's.

## Pattern 99 — The Icecast end-of-support migration (**a dated trigger; the date does the selling**)

**The trigger.** Icecast **2.4.4 support ends 2026-12-31**. **2.5.0** has been the stable line since
**2025-12-31**, and **Debian's tracker shows the 2.5.0 migration BLOCKED**. So a client on a
distro-packaged Icecast has an unsupported streaming server within the month and no clean apt upgrade
path. *(Both dates secondary-source; `icecast.org` is outside this session's network policy.)*

**Three exits, and the choice is a licence decision not a technical one.**

| Exit | Component | Licence | When it is right |
|---|---|---|---|
| Upgrade in place | [`xiph/Icecast-Server`](https://github.com/xiph/Icecast-Server) 2.5.0 | GPL-2.0 | Station runs it as internal infrastructure. **Build from source — do not wait for Debian.** Note the GitHub repo is a **`(Mirror)`**; canonical is `gitlab.xiph.org`. |
| Collapse the daemon | [`savonet/liquidsoap`](https://github.com/savonet/liquidsoap) 2.5.x built-in Icecast-compatible server | GPL-2.0 | The client **already** runs Liquidsoap (anyone on Airtime/AzuraCast/LibreTime does). Removes a moving part entirely. **Experimental/beta — stage it.** |
| Go permissive | [`DatanoiseTV/tinyice`](https://github.com/DatanoiseTV/tinyice) | **Apache-2.0** | The client needs to **embed or redistribute** the server in a product. The only permissive Icecast-compatible server that exists. 373★, pushed 2026-11-27, **3 open issues — early**. Pilot it, do not promise it. |

**Run the test with DJ clients, not curl.** Liquidsoap's built-in server is documented as accepting
ordinary Icecast source clients (Butt, Mixxx — and `mixxxdj/mixxx` is already in this KB at 7,445★). The
migration's real acceptance criterion is that the station's existing source clients and listener URLs
keep working untouched.

## Pattern 100 — AI presenter on an MIT base, with a jurisdiction gate in front of it

**The stack, and all three layers are permissive — which is unusual enough to say out loud.**

1. **Agent**: [`perminder-klair/subwave`](https://github.com/perminder-klair/subwave) (**MIT**, 1,687★,
   pushed 2026-11-27) for an agentic DJ, or
   [`robert-dean/deadair`](https://github.com/robert-dean/deadair) (**MIT**, 145★, **0 open issues**) if
   the music library is Navidrome, or [`johncrash64/radio-dj`](https://github.com/johncrash64/radio-dj)
   (**MIT**, 63★) whose **ffmpeg→Icecast with live ducking** is the cleanest reference wiring of agent
   onto delivery.
2. **Voice**: `resemble-ai/chatterbox` (**MIT**, 28,008★) or `SWivid/F5-TTS` (**MIT**, 15,633★) — both
   already catalogued in `agents/top.md`. `keltokhy/writ-fm` (384★) demonstrates exactly this pairing, but
   **it has no licence** — read it, do not fork it.
3. **Delivery**: Pattern 99's choice.
4. **Metadata**: Pattern 98's emitters, so the synthetic segment is labelled *on the dashboard too*.

**The gate, and it goes in front — not after.** Putting a synthetic voice on a licensed transmitter is a
regulated act with **dates already in force**: China's synthetic-content labelling (2025-09-01, fines to
**¥50m**); Korea's AI Basic Act (**2026-01-22**); India's intermediary obligations for synthetically
generated content (**2026-02-20**); Vietnam's AI law (**2026-03-01**); California's AI Transparency Act
provenance duties (**2026-08-02**); most EU AI Act requirements (**August 2026**); Canada's "AI for All"
watermarking (**2026-06-04**). Radio-specific: **Australia's media regulator published sector papers in
April 2026 mapping AI use across television, radio and news**; **Radio France added an annex in April 2026**
restricting synthetic voice; **Chile's bill** covers AI imitations of a person's **voice**; **Brazil's
electoral court prohibits synthetic audio** favouring or harming a candidacy.

**So the sellable artefact is the policy engine, not the DJ.** A per-jurisdiction rule set that decides,
per segment: may this run / must it be labelled / must the label reach the dashboard and the stream
metadata / is this an election period. The agents are free and MIT; **the compliance evidence is the
deliverable**, and it is the same per-jurisdiction conclusion this KB reached for APAC in pass 8 — now
with an actual radio regulator document behind it.

## Pattern 101 — The 20-minute licence gate for any DAB+ or RDS proposal (**run this before writing the SOW**)

Five questions. Any one of them can change the shape of the engagement, and all five are answerable from
material already in this KB.

1. **Is this "our station" or "our product for other stations"?** Every maintained radio platform —
   AzuraCast, LibreTime, OpenBroadcaster, DABcast — is **AGPL-3.0**. Internal infrastructure: harmless.
   Radio-as-a-service to third parties: the **network clause triggers** and modified source must be
   offered to users. **This question selects the entire stack and it is the most common way a radio
   engagement goes wrong at contract stage.**
2. **Does the deliverable transmit DAB+?** Then `ODR-AudioEnc` is in scope, and it is **five licences
   statically linked into one binary** (`src/` Apache-2.0, `libtoolame-dab` LGPL-2.1+, `src/edi`
   GPL-3.0+, `fdk-aac` **Fraunhofer** — not OSI-approved, `contrib/fec` LGPL-2.1), **plus AAC patent
   licensing via Via Licensing**, and **the maintainer's own README says**: *"Whether it is legal or not
   to distribute compiled binaries from these sources is unclear to me. Please seek legal advice."*
   **Put that sentence in the risk register verbatim.** No SBOM scan of the source tree will surface it.
3. **Does it generate RDS?** **7 of 7 transmit encoders are GPL-3.0** (the 8th is unlicensed). Only the
   decoder (`windytan/redsea`, **MIT**, 445★) is permissive. Reading the data channel is free; **writing
   it inside a proprietary product is a build or a commercial encoder.**
4. **Does a receiver ship in the product?** Use [`KejPi/AbracaDABra`](https://github.com/KejPi/AbracaDABra)
   (**MIT**, 188★, 2026-11-15) — **the best-licensed maintained DAB receiver that exists**. `welle.io`
   (764★) is the better-known one and it is **GPL-2.0**; picking it by star count is the mistake here.
5. **Is HD Radio or DRM in scope?** **HD Radio: receive only, permanently** — Xperi-controlled and
   patent-licensed; `theori-io/nrsc5` (GPL-3.0+, 974★) decodes and nothing encodes. **DRM30**: one live
   repo on earth, `CasualArclamp/DecDRM` (GPL-2.0, 14★) — greenfield, so durable differentiation, but
   budget for a build.

## Pattern 102 — The DAB+ small-scale multiplex, assembled (EMEA only, and only after Pattern 101)

**Where this is real:** EMEA, where ETSI publishes the standards free, DAB+ is ~100% factory-fit in Italy
and 98% in France, and **166.6M receivers** have shipped across 11 core markets. **Not** North America
(HD Radio is closed) and **not** LATAM (no standard decided).

**The chain, all of it GPL-3.0 unless noted:**

```
audio → ODR-AudioEnc  (FIVE licences — Pattern 101 Q2)
      → ODR-DabMux    (GPL-3.0, 49★)   services → ETI
      → ODR-DabMod    (GPL-3.0, 60★)   ETI → I/Q
      → USRP / LimeSDR   —or—   Raspberry Pi + EasyDAB v2 (board replaces the software modulator)
PAD:    ODR-PadEnc    (GPL-3.0, 9★)    DLS text + MOT Slideshow
EPG:    magicbadger/odr-radioepg-bridge (Apache-2.0, 2★) — EPG bitstream straight from the mux config
ops UI: ODR-EncoderManager (GPL-3.0+, 10★, DORMANT since 2023-05-22)
   or   DABodr/DABcast-diffusion-software (AGPL-3.0, 0★, pushed 2026-11-25)
QA:     Opendigitalradio/etisnoop (GPL-3.0, 14★) — analyse the ETI you just produced
monitor: KejPi/AbracaDABra (MIT, 188★) — independent off-air receive check
```

**The two places this build actually earns its fee**, because the chain itself is a documented install:

- **The ops layer is the gap.** The official web UI has been **dormant 3.5 years**; the live alternative
  has **0 stars**. A multiplex operator needs service management, scheduling, failover and audit, and
  that is where the custom work belongs — not in the transmission chain.
- **PAD and EPG are what the listener sees**, and they connect this pattern to Pattern 98: the same
  canonical now-playing record should drive `ODR-PadEnc` (DLS+/MOT on the DAB carrier) **and** the
  RadioVIS/SPI emitters (hybrid metadata to the dashboard). **Build it once.** Reference for the PAD
  side: [`radiorabe/nowplaypadgen`](https://github.com/radiorabe/nowplaypadgen) (AGPL-3.0, 3★, pushed
  2026-11-23) — read it, keep AGPL behind a boundary.

**Close the loop with measurement**, which this plane supports unusually well: `etisnoop` validates the
ETI you generated, and an independent MIT receiver confirms what actually went out. A commissioning
evidence trail of that shape is the pass-44 pattern applied here, and it is the deliverable a regulator
or a mux landlord will ask for.

## ⛔ What not to promise in this plane (pass 46)

- **Never promise the in-car audience data.** DTS AutoStage's measurement — **6M vehicles daily, 300+ US
  markets** — is Xperi's asset, and the carmaker pays for the integration. A client can **supply** the
  platform and **read its portal**. It cannot replace it. Scope the feed; never the panel.
- **Never promise redistributable open-source DAB+ transmission** without Pattern 101 Q2 answered in
  writing. The upstream maintainer will not assert it; neither should a proposal.
- **Never promise RDS generation inside a proprietary product.** 7 of 7 GPL-3.0.
- **Never promise an open HD Radio transmitter.** It does not exist and cannot.
- **Never present "RadioDNS support" as one capability.** It is three ETSI documents — RadioVIS, SPI/EPG,
  Service Following — with three different maintenance states, and the only live open implementation
  covers **RadioVIS alone**. Ask a vendor which of the three they mean, and ask for an **SPI XML sample**
  during evaluation. Watch what happens.
- **Do not pick components by star count in this plane.** `welle.io` (764★, GPL-2.0) loses to
  `AbracaDABra` (188★, **MIT**) for anything shipped. `rAudio` (441★) has **no licence**. `writ-fm`
  (384★) has **no licence**. The popular answer and the usable answer diverge in three separate places.
- **Do not grep `DRM` to check whether this plane is covered.** This KB's 89 `DRM` hits are **Digital
  Rights Management**. **Digital Radio Mondiale** returns **11 repositories worldwide**, one alive.

---

## Weather-desk recipes — added 2026-11-27 (pass 47)

Every repo named below was verified on 2026-11-27 (`git ls-remote` + raw licence file). Licences are
stated as read at source, not as reported by catalogues.

### P47.1 — The permissive forecast desk (the baseline build, all steps 1–2 permissive)

**Chain:** [blaylockbk/Herbie](https://github.com/blaylockbk/Herbie) (**MIT**) pulls GRIB2 for GFS, HRRR,
ECMWF IFS and **AIFS** → [ecmwf/cfgrib](https://github.com/ecmwf/cfgrib) (**Apache-2.0**) decodes via
[ecmwf/eccodes](https://github.com/ecmwf/eccodes) (**Apache-2.0**) → [pydata/xarray](https://github.com/pydata/xarray)
(**Apache-2.0**) holds the fields → [Unidata/MetPy](https://github.com/Unidata/MetPy) (**BSD-3**) computes
derived quantities (Skew-T, thermodynamics, cross-sections) → [ecmwf/earthkit-plots](https://github.com/ecmwf/earthkit-plots)
(**Apache-2.0**) or [SciTools/cartopy](https://github.com/SciTools/cartopy) (**BSD-3**) renders the map →
scene handed to [CasparCG/server](https://github.com/CasparCG/server) (**GPL-3.0**) for SDI/NDI output.

**Licence wiring that makes this shippable:** steps 1–2 are Apache-2.0/MIT/BSD-3 throughout — no copyleft
anywhere in your own process. **CasparCG's GPL-3.0 is the only copyleft, and it is a separate process
driven over AMCP/OSC**, so it is *invoked and distributed alongside* your code, not linked into it —
the same pattern this KB established for playout in pass 8. Attribution obligation: ECMWF data is
**CC-BY-4.0 and attribution is a legal requirement**, so the attribution string belongs in the graphic
template, not in a licence file nobody renders.

### P47.2 — The model bench, with the weights gate built in

**Chain:** [microsoft/aurora](https://github.com/microsoft/aurora) (**MIT**, code *and* weights) as the
default; [ecmwf/anemoi-core](https://github.com/ecmwf/anemoi-core) + [anemoi-models](https://github.com/ecmwf/anemoi-models)
+ [anemoi-training](https://github.com/ecmwf/anemoi-training) (**all Apache-2.0**) to fine-tune on a
regional domain; [google-deepmind/weathernext](https://github.com/google-deepmind/weathernext)
(**Apache-2.0** code, **CC BY 4.0** materials) for the WeatherNext 2 / Cyclones line;
[neuralgcm/neuralgcm](https://github.com/neuralgcm/neuralgcm) (**Apache-2.0**) when physical consistency
matters; [NVIDIA/physicsnemo](https://github.com/NVIDIA/physicsnemo) (**Apache-2.0**) +
[NVlabs/FourCastNet](https://github.com/NVlabs/FourCastNet) (**BSD-3**) for the GPU training path.

**⛔ Excluded by licence, deliberately:** [198808xc/Pangu-Weather](https://github.com/198808xc/Pangu-Weather)
— **no licence file at all**, README states trained parameters are **CC BY-NC-SA 4.0** and *"the
commercial use of these models is forbidden."* It will pass every automated licence scan because there
is nothing for a scanner to read.

**The gate to add to CI (extends the pass-8 licence gate to v8):**
1. Resolve the **weights** licence from the primary artefact (model card, README §License, bucket
   terms), **separately** from the repository licence. Record both, with the date read.
2. Probe licence filenames including `LICENSE`, `LICENSE.txt`, `LICENSE.md`, `license.txt`, `LICENCE`,
   `COPYING`, `COPYING.md`, **`COPYRIGHT`** (netcdf-c) and **`LICENSE.TXT`** (gdal).
3. Resolve the default branch with `git ls-remote --symref <url> HEAD` before concluding anything —
   `dpaulat/supercell-wx` is **MIT on `develop`** and 404s everywhere on `main`/`master`.
4. A README that returns 200 while every licence name 404s means the licence is genuinely absent; a
   README that *also* 404s means your branch or names are wrong. (Pass-8 rule, reconfirmed twice here.)
5. For native dependencies, resolve the licences of the **linked** libraries, not the repo (pass-8
   chromaprint rule) — and treat a multi-licence inventory file like gdal's 21 841-byte `LICENSE.TXT`
   as a compilation grant to read, not an SPDX value to copy.
6. **Record the acquisition route with the licence.** Identical fields are **CC BY-4.0 from BoM/JMA
   directly and CC BY-NC-4.0 via ECMWF TIGGE.**

### P47.3 — Severe-weather nowcast cut-in (the highest-value, most defensible build)

**Chain:** [ARM-DOE/pyart](https://github.com/ARM-DOE/pyart) (**BSD-3**) or
[wradlib/wradlib](https://github.com/wradlib/wradlib) (**MIT**) ingest and clean the radar volume →
[pySTEPS/pysteps](https://github.com/pySTEPS/pysteps) (**BSD-3**) produces the probabilistic 0–6 h
precipitation nowcast → [dpaulat/supercell-wx](https://github.com/dpaulat/supercell-wx) (**MIT**, on
`develop`) for the meteorologist's desk view → [maplibre/maplibre-gl-js](https://github.com/maplibre/maplibre-gl-js)
(**BSD-3**) + [visgl/deck.gl](https://github.com/visgl/deck.gl) (**MIT**) for the web/app renderer →
CAP alerting via pass 45's [CAPTools/CAPCreator](https://github.com/CAPTools/CAPCreator) (**BSD-3**) →
air via CasparCG.

**Why this one wins a bid:** the nowcast is where a station's forecast visibly beats a phone's default
weather app, the whole chain is permissive, and it joins directly onto the alerting plane this KB
already catalogued in pass 45. Avoid [JoshuaKimsey/LibreWXR](https://github.com/JoshuaKimsey/LibreWXR)
in a closed product — it is **AGPL-3.0** despite being the most broadcast-adjacent web radar renderer.

### P47.4 — The LATAM station with no national API

**Chain:** SMN Argentina's **4 km WRF** on AWS Open Data (**CC-BY-2.5-AR**, 00/12 UTC, 72 h lead) +
INMET via **`climateBR` v0.2.0** / **`rmet`** (CRAN) + a [wmo-im/wis2box](https://github.com/wmo-im/wis2box)
(**Apache-2.0**) node to publish and subscribe → the P47.1 chain above for compute and render.

**The two things to say out loud in the proposal:** (1) the attribution string must satisfy
**CC-BY-2.5-AR**, a *jurisdiction-ported* licence that an allow-list matching only `CC-BY-4.0` will
reject wrongly; (2) Brazil's path depends on **volunteer-maintained CRAN packages** because no official
INMET REST API was located — that is the integration risk, and naming it is the consulting value.

### P47.5 — The Japan-compliant build (architecture driven by a permit, not a licence)

**Do not generate a forecast.** Under the amended Meteorological Service Act (full effect end of May
2026) a **JMA permit is required to provide forecasting services to users in Japan regardless of where
the operator sits**, and JMA may publicly name unlicensed operators. Build the product to **ingest a
permitted provider's forecast** and own the *presentation, personalisation and alerting* layers —
P47.1's render chain and P47.3's display chain, with step 2 deliberately omitted. The open models are
all still usable for **internal verification and research**; the regulated act is *issuing the forecast
to users*.

### P47.6 — Reaching air without an open on-air product

There is **no open-source on-air weather graphics package**. The two viable shapes:
- **(a) Data hand-off:** compute everything on the permissive stack, then hand fields or rendered
  frames to the station's existing Chyron / Vizrt / Max / Ross system. Lowest risk, fastest, and what
  most broadcasters will actually buy.
- **(b) Custom render:** MapLibre (**BSD-3**) / deck.gl (**MIT**) / [CesiumGS/cesium](https://github.com/CesiumGS/cesium)
  (**Apache-2.0**) for the visuals, fronting CasparCG (**GPL-3.0**) for playout, with
  [Unidata/awips2](https://github.com/Unidata/awips2) (**MIT**) as the operational display reference.
  Real work, genuinely ownable, and the only route to a differentiated look.

## 🔮 Falsifiable prediction recorded this pass (test it in a later plane)

This plane's gradient is **inverted** relative to pass 5's rights gradient. Pass 5: *declare* a right =
healthy, *honour* it = dormant, *settle* it = literal zero. Pass 47: *access* the data = healthy and
permissive, *model* it = healthy and permissive, *present it on air* = zero.

**Prediction:** wherever the deliverable is a **branded, on-air or customer-facing artefact**, open
source approaches zero, while the data layer beneath it stays rich — because the product being sold is
brand, not capability. **Named test targets for future passes:** on-air **election-night** graphics,
**sports scoreboard/telestration** graphics, and **financial-ticker** on-air systems. Predict: rich open
data and computation beneath each (election results feeds, sports data APIs, market data libraries),
**no open on-air presentation layer for any of the three.** If a future pass finds a maintained,
permissively licensed on-air graphics package in any of those three, this prediction is **wrong** and
the "brand, not capability" explanation needs replacing.

## ⛔ What not to promise in this plane (pass 47)

- **Never promise "replace Chyron/Vizrt/Max with open source."** Eleven-plus proprietary vendors ship
  actively (Chyron Weather 2.3 Feb 2026, 2.4 Jun 2026) and there are **zero open peers**. The open
  alternative is a custom build, priced as one.
- **Never ship Pangu-Weather in a client deliverable.** No licence file; README forbids commercial use.
  It will pass your scanners.
- **Never quote a repo's SPDX licence as the model's licence.** Resolve weights separately, always.
- **Never trust a third-party model catalogue on licensing.** `rebase-energy/awesome-weather-models`
  (itself unlicensed) still lists GraphCast's weights as non-commercial; the repo's 2026 README says
  CC BY 4.0. Read the primary artefact.
- **Never assume a feed's licence survives the aggregator.** BoM/JMA/CMA/IMD data is **CC BY-NC-4.0 via
  TIGGE** and openly licensed direct from source.
- **Never promise a Japanese weather product that issues its own forecast** without a JMA permit in the
  risk register by name, at proposal time.
- **Never wrap Open-Meteo's code in a hosted service** — **AGPL-3.0** reaches networked use. Self-host
  internally, buy the commercial subscription, or use the CC-BY-4.0 *data* with your own server. The
  free hosted tier is **non-commercial only** (<10 000 calls/day).
- **Never put LibreWXR in a closed product** (AGPL-3.0), and **never assume `open-meteo/*` shares one
  licence** — the core is AGPL-3.0, `weather-map-layer` is **GPL-2.0**.
- **Do not promise an allow-list compliance check that only accepts `CC-BY-4.0`.** Argentina's SMN feed
  is **CC-BY-2.5-AR**, and ported CC licences are real and in production use.

## Pattern 103 — The refusal file: making a *declined* removal request defensible

**The plane's commercial inversion.** Every vendor in this space sells deletion. In Brazil deletion is
unconstitutional (STF, RE 1.010.606), in the US there is no duty to delete an archive, and the IACHR
Special Rapporteur warns that private de-indexing with vague limits is itself the hazard. For roughly half
the world's publishers the valuable artefact is **the documented refusal** — and nobody sells it.

**Wire it from verified, permissive parts:**

1. **Intake with the statutory clock.** Take the request-shape and deadline logic from
   [`jeffersongoncalves/laravel-gdpr-dsar`](https://github.com/jeffersongoncalves/laravel-gdpr-dsar)
   (**MIT**, ★2) — it encodes Arts. 15–22, identity check, and the one-month deadline with the Art. 12(3)
   extension. Two stars, so read it and reimplement; the value is the clock, not the code.
2. **Bundle validation.** [`MrLouisWright/dsar-warden`](https://github.com/MrLouisWright/dsar-warden)
   (**MIT**, ★2) for the checks worth copying: subject matching, secret-field removal, **third-party data
   flagging**, identity verification. Zero deps, SARIF output — drops into CI as a gate.
3. **Locate the personal data in the archived article.**
   [`data-privacy-stack/presidio`](https://github.com/data-privacy-stack/presidio) (**MIT**, ★12,086) as
   the detector, with [`deepanwadhwa/zink`](https://github.com/deepanwadhwa/zink) (**Apache-2.0**, ★112)
   where zero-shot NER beats a trained pipeline — which is the normal case for an unlabelled archive.
   Use the canonical `data-privacy-stack` slug, **not** `microsoft/presidio`.
4. **Offer the proportionate middle remedy, not a binary.**
   [`arx-deidentifier/arx`](https://github.com/arx-deidentifier/arx) (**Apache-2.0**, ★741) to anonymise
   or mask the party rather than remove the article. This is what EMEA practice usually wants and what the
   Delhi High Court actually ordered (masking of judicial records).
5. **Record the decision.** Extend the ticket model in
   [`Yaogui415/newsflow-oss`](https://github.com/Yaogui415/newsflow-oss) (**MIT**, ★104) — its
   `correction_tickets` API (213 lines) and `post_publish_monitor` agent (455 lines) are the only
   newsroom-shaped prior art. Add what it lacks entirely: the public-interest test applied, the decider,
   the outcome, the effective date.
6. **Publish only what should be public.** `schema.org` `correction` / `CorrectionComment` /
   `correctionsPolicy` ([`schemaorg/schemaorg`](https://github.com/schemaorg/schemaorg), **Apache-2.0**)
   for the correction notice; ninjs `pubstatus` for syndication partners.

**Licence warning for the whole recipe:** avoid
[`audrasjb/gdpr-data-request-form`](https://github.com/audrasjb/gdpr-data-request-form) (GPL-2.0) in a
proprietary product, and note that `OpenDSR` (★387) and `open-retractions` (★46) carry **no licence file
at all** — read them for design, copy nothing.

**Sell it as:** NA (US) and LATAM — the refusal file is the primary product. EMEA and APAC — it is the
audit layer underneath Pattern 104.

---

## Pattern 104 — The de-indexing executor: keep the URL alive, kill the search footprint, prove the date

**The job no open-source project performs.** `noindex takedown` returns **zero repositories**; `deindex`
returns an Illumina DNA-barcode tool. Meanwhile Italian practice reportedly requires the **publisher** to
insert metatags that hide the article from general search engines while keeping it in the historical
archive, and a 2026 ruling attached **damages to delay**. The requirement is therefore not "delete" but
"suppress, retain, and timestamp".

**The four obligations, and what to build each from:**

1. **Keep the article resolving.** No deletion, no 404, no URL change — the archive copy is the publisher's
   right to retain (Italian practice) and its defence (STF/ABRAJI position in Brazil). Do not reuse
   [`pluginpal/strapi-plugin-publisher`](https://github.com/pluginpal/strapi-plugin-publisher)
   (**MIT**, ★83) as the mechanism — it *unpublishes*, which is the wrong remedy — but do read it as the
   only mainstream CMS prior art for scheduled state change.
2. **Suppress the search footprint.** `noindex` meta plus `X-Robots-Tag`, removal from the sitemap, and
   canonical hygiene. Regenerate the sitemap deterministically in CI with
   [`cicirello/generate-sitemap`](https://github.com/cicirello/generate-sitemap) (**MIT**, ★113, pushed
   2026-11-18) so the suppressed URL cannot silently return on the next deploy.
3. **Detect silent regressions — the damages risk.** Because liability attaches to *delay* and to
   *reappearance*, monitor the directive rather than trusting it:
   [`dancolta/seo-drift-monitor`](https://github.com/dancolta/seo-drift-monitor) (★22, **no licence
   declared — read only, do not vendor**) is the shape of the check: it detects when a deploy silently
   ships or drops a `noindex` or rewrites a canonical. Build this one in-house; the open artefact is
   unlicensed.
4. **Prove when suppression took effect.** An append-only decision log keyed to the article URL, carrying
   the order reference, the effective timestamp, and re-verification results over time. This is the
   deliverable that answers the Italian damages question and the Canadian global-de-indexing order, and
   **nothing in open source produces it.**

**Then reconcile with syndication.** An article suppressed on the publisher's own domain is still live at
every partner that ingested it. ninjs gives exactly three values —
`usable` / `withheld` / `canceled` — identical across v1.2, v1.4 and v2-rc, with no reason code and no
effective date. So the partner notification must carry an out-of-band payload, and that mismatch is worth
raising with the client before it is discovered in production. **Do not promise a standards-native
de-indexing propagation: the standard cannot express it.**

**Sell it as:** EMEA first (Italy, and the measured liability is latency), then Canada within NA (global
de-indexing of judicial records), then India (court-ordered masking). In Brazil, pair it with Pattern 103
and lead with the refusal.

---

## Pattern 105 — The council-meeting desk: agenda to publishable story, with the verification gate as the product

**For:** a local publisher, a chain, or a public broadcaster that needs coverage of municipal meetings
nobody currently attends. This is the plane's flagship build.

**Why the gate and not the transcript:** Hearst's Assembly already does transcription, keyword
detection and summarisation of council and school-board meetings on a **self-hosted Whisper** — the
model layer is commodity. What makes output *publishable* is the step that proves every attributed
statement exists in the source. One published newsroom pipeline **kills the post** when the summary
attributes a statement to an official that is not in the transcript; that behaviour is the deliverable.

```
[Discovery]  City-Bureau/city-scrapers (MIT, 381*)  ── meetings, standardised
             biglocalnews/civic-scraper (Apache-2.0, 82*) ── agendas/minutes documents
             opencivicdata/python-legistar-scraper (BSD-3, 53*) ── for Legistar municipalities
                     │
                     ▼
[Join key]   opencivicdata/ocd-division-ids (CC0-1.0, 186*) ── canonical jurisdiction ID
             openstates/people (CC0-1.0, 162*) ── officials, for attribution checking
                     │
                     ▼
[Audio/ASR]  whisper / whisper.cpp + pyannote (already in this KB: agents/top.md)
                     │                             speaker turns → named officials
                     ▼
[GATE]       claim-by-claim check: every quoted statement must match a transcript span,
             every named official must match an openstates/people record.
             No match → the item does not publish. Log the refusal with the span offsets.
                     │
                     ▼
[Publish]    CMS over REST ONLY — Newspack (GPL-2.0) / Largo (GPL-2.0) stay behind an API boundary
             Alert path: themarshallproject/klaxon (MIT, 685*) for page-change watching
```

**Licence boundary, and it is the whole architecture:** everything left of `[Publish]` is
MIT/Apache/BSD/CC0 and stays yours. The CMS is GPL-2.0 by WordPress inheritance, so integrate over its
REST API and **never as a plugin compiled into the tree**. The REST boundary is the licence boundary.

**What to bill:** per-jurisdiction onboarding, and the gate. Not the ASR.

**Qualifying question:** *"when a council meeting happens in your smallest market tomorrow, who is in
the room?"* If the answer is nobody, the build has a measurable before/after. If the answer is a
reporter, price against them — in the UK that price is published (£40,790/year; see Pattern 108).

---

## Pattern 106 — The per-jurisdiction scraper factory: industrialise the fork

**For:** any engagement covering more than three jurisdictions — a chain, a state/provincial
broadcaster, a regional coalition.

**The evidence this is the right shape:** `City-Bureau/city-scrapers-template` has **42 stars and 94
forks** — forks outnumber stars 2.2×. The fork-per-jurisdiction pattern is already how this ecosystem
works; City Bureau runs its own instances that way (`city-scrapers-cle` 17★ pushed 2026-11-24,
`city-scrapers-det` 4★ 2026-11-24, `city-scrapers-atl` 3★ 2026-10-20). Nobody has industrialised it.

```
[Template]   City-Bureau/city-scrapers-template (MIT, 42*/94f) ── fork per jurisdiction
[Core lib]   City-Bureau/city-scrapers-core (MIT) ── shared behaviour, upgraded centrally
[Framework]  opencivicdata/pupa (BSD-3, 91*) ── scheduling + data model
[Vendor]     opencivicdata/python-legistar-scraper (BSD-3, 53*) ── Legistar municipalities
             (`legistar` = 70 repos, exactly ONE maintained client: this is the leverage point)
[Identity]   opencivicdata/ocd-division-ids (CC0-1.0) ── every jurisdiction gets a canonical ID
[Runner]     GitHub Actions (the template already ships this) or openaustralia/morph (AGPL-3.0 —
             fine to run internally; hosting it as a service for a client triggers the network clause)
```

**The engineering work that is actually billable:** a jurisdiction-onboarding harness — given a council
URL, identify the platform (Legistar, BoardDocs, Granicus, bespoke), generate the scraper, validate
against a known meeting, and register the OCD division ID. Onboarding in hours instead of weeks is the
product; the scrapers themselves are commodity and permissive.

**Do not rank candidate repos by stars in this plane.** A 3★ repo pushed yesterday is a live newsroom
deployment (see `intel/trends.md` Trend 5).

---

## Pattern 107 — Gazette-to-alert: the LATAM build that has a corpus waiting for a judgment layer

**For:** a Brazilian or Spanish-speaking LATAM publisher, a civic organisation, or a regional coalition.

**Why this one is unusually ready:** `okfn-brasil/querido-diario` (**MIT**, 1,429★/492f, pushed
2026-10-12) has already solved acquisition and normalisation of municipal official gazettes at roughly
350 cities, with an MIT API (66★) and frontend (59★). Globally, `official gazette scraper` returns only
**10 repos** and every other one is a single-country one-off. The corpus exists, the licence permits
everything, and **the classification-and-alerting layer on top does not exist.**

```
[Corpus]     okfn-brasil/querido-diario (MIT) ── gazettes, normalised
[Access]     okfn-brasil/querido-diario-api (MIT) ── FastAPI over the corpus
                     │
                     ▼
[Classify]   act type (contract award, tender, appointment, budget change, land decision)
             + the municipality's own thresholds (value, department, named entities)
                     │
                     ▼
[GATE]       every alert cites the gazette, the date, the page and the verbatim span.
             A gazette is a legal record: no paraphrase without the citation attached.
                     │
                     ▼
[Deliver]    reporter alert (newsroom) / citizen subscription (civic) / dataset (coalition)
             Monitoring companion: themarshallproject/klaxon (MIT) for the pages that are not gazetted
```

**Demand to size it against:** Atlas da Notícia's 7th edition counts **2,504 news deserts among 5,570
municipalities (~45%)** and **20.6M people (10.2%)** in them. Those municipalities still publish
gazettes even when no journalist reads them — **the public record outlives the newsroom**, and that is
the premise of this pattern.

**Two cautions.** Do not build on `serenata-de-amor` (4,627★ but **no push since 2024-01-31**;
`rosie` and `jarbas` ARCHIVED) — it is the name clients reach for and it is not maintained. And do not
mix the Atlas figure (2,504) with NexOS's April 2026 figure (1,974): different methodologies, neither
reconciled.

**Portability is the upside:** any country with municipal official-journal publication can run this
pattern, and the MIT licence means porting needs no negotiation.

---

## Pattern 108 — The funding-evidence pack: making public money for local news auditable

**For:** a public broadcaster, a media regulator, a ministry or a foundation that distributes money for
local coverage — and for the publishers that have to account for it.

**Why it sells:** EMFA requires public funding of media to be allocated on **public, proportionate and
non-discriminatory criteria** and to be **adequate, sustainable and predictable, preferably
multi-year**. The EBU reports national implementation is **slow and uneven** (2026 EU Rule of Law
Report), and the Liberties Media Freedom Report (April 2026) flags over-dependence of local media on
public funds as itself an EMFA sustainability concern. Meanwhile the UK already runs the model
transaction: **165 reporters, 118 contract areas, £40,790 per reporter-year**, contracts to **end-2027**.
Both sides need the same artefact and neither has tooling for it.

```
[Allocation record]  criteria, weights, applicants, scores, decisions — published, versioned,
                     diffable. "Non-discriminatory" is only demonstrable if the rule predates
                     the decision, so VERSION the criteria and timestamp them.
[Output record]      what the money produced: meetings covered, jurisdictions reached, stories
                     published, per contract area. Sourced from Pattern 105/106 telemetry,
                     not self-reported.
[Coverage baseline]  the gap being closed, measured — Medill-style county/area counts (NA),
                     contract areas (UK), Atlas da Notícia municipalities (BR)
[Join key]           opencivicdata/ocd-division-ids (CC0-1.0) / openstates/people (CC0-1.0)
                     so allocation, output and baseline all reconcile to the same jurisdiction
```

**The deliverable is the evidence trail, not a dashboard.** It must answer, for one contract area and
one year: what was the rule, who applied, who got the money, what coverage appeared, and what the gap
was before. Every element is derivable from permissive components plus the client's own records.

**Where it lands by region:** EMEA on EMFA conformance and the Charter window; North America for the
philanthropic and chain-level funders (the 75 new outlets must report to funders); LATAM as the shared
accountability layer Aspen Digital's January 2026 report explicitly calls for.

**Qualifying question:** *"if a regulator asked you to show why this outlet received funding and that
one did not, what would you send?"*

---

## ⛔ What not to promise in this plane (pass 49)

- **Do not promise a permissively-licensed turnkey platform.** The deployable local-news platforms are
  WordPress derivatives and therefore **GPL-2.0** (Newspack, Largo); the civic-service platforms are
  **AGPL-3.0** (Alaveteli, morph, MuckRock). The only permissive platform here is
  `datamade/django-councilmatic` (MIT, 26★) and it is a council tracker, not a publishing system.
- **Do not start from `Automattic/newspack-plugin`** — **ARCHIVED 2026-08-18**, and still the URL most
  funder and CMS-directory pages cite. Live code: `Automattic/newspack-workspace`,
  `OpenProducer/newspack-platform`.
- **Do not build on `okfn-brasil/serenata-de-amor`** (no push since 2024-01-31; `rosie`/`jarbas`
  archived) however impressive its 4,627 stars look.
- **Do not claim an AI moat.** The incumbent (Hearst Assembly) runs on self-hosted Whisper. The moat is
  per-jurisdiction ingest and the verification gate.
- **Do not read licences from SPDX fields in this plane.** Six repos report `NOASSERTION` and all six
  have licence files; `INN/largo`'s is at `trunk/license.txt` on a `trunk` default branch, and its
  `repo:` search query returns HTTP 422 outright. Read the files.
- **Do not quote Medill year-on-year deltas.** The 2026 levels are consistent across secondary sources;
  the prior-year baselines are not (212 vs 148 vs 136), and the primary report is unreachable from this
  environment.
- **Do not mix the two Brazilian news-desert counts** (Atlas 2,504 vs NexOS 1,974) — unreconciled
  methodologies.
- **Do not size this plane.** No market figure exists. Use the published £40,790 reporter-year instead.

---

## Pattern 109 — The consent-of-record pipeline: bind consent to the asset at booking, prove it at delivery

**The problem.** Every instrument in this plane — SAG-AFTRA 2026 (written, specific, separately paid
consent), Mexico's in-force reforms (explicit pre-training consent surviving the contract), Denmark's
§65a, China's labelling standard — demands the same artefact: **proof that this performer consented to
this use of their voice or likeness**. Consent is created at **booking**, not in post, and the booking
layer has nine repositories at 0 stars.

**The recipe, all permissive, every licence read from the file.**

1. **Declare** — [batuhanbulbul/grantmark](https://github.com/batuhanbulbul/grantmark) (**Apache-2.0**).
   Serve the performer's declaration at `/.well-known/hcs.xml` + `/registry/…` and parse it with
   `@grantmark/hcs`. Use its **consent-authority record profile** (JSON Schema **with test vectors**)
   as the record shape for a living adult's name, image, likeness and voice.
2. **Gate** — [vishwatejaaverager/consentor](https://github.com/vishwatejaaverager/consentor)
   (**MIT**). Call it *before* synthesis: no consent record, no generation. This is the enforcement
   point, and it is the one the whole chain is worthless without.
3. **Generate** — [svayatta/pratidhvani](https://github.com/svayatta/pratidhvani) (**Apache-2.0**,
   26★) for voice, which already carries consent and an **inaudible watermark**; or
   [dassjaylabs/filmwright](https://github.com/dassjaylabs/filmwright) (**MIT**) where "consented
   cloned voice" is an explicit mode.
4. **Stamp** — `@grantmark/stamp` writes a **C2PA manifest with a `cawg.consent` assertion**. This is
   the join to work this KB already banked: the C2PA/provenance substrate of passes 4 and 8, and
   Patterns 4 and 8 built on it. **You are not adding a stack, you are adding an assertion.**
5. **Verify** — `/v1/verify` reads the manifest back and checks the consent reference against the
   registry. Ledger the result in
   [mahmoudabdelnaby1/customer-ugc-rights-consent-ledger](https://github.com/mahmoudabdelnaby1/customer-ugc-rights-consent-ledger)
   (**MIT**) for the audit trail.

**What to say out loud.** `grantmark`'s own README states it is an **experimental prototype on devnet
with fictional demo data**, tracking a **draft** standard, and is **not affiliated with or endorsed by**
the Human Consent Foundation, the RSL Collective or CAWG/C2PA. Steps 1, 4 and 5 are therefore a
reference design to harden, not a dependency to install. The HCS 1.0 spec text itself could **not be
read from this session** (`humanconsent.org` returns 403 through the proxy) — treat its exact terms as
unverified. Say all of this in the proposal; it is still the best starting point that exists.

## Pattern 110 — Casting on OpenCATS: bend the only adopted platform rather than forking a 0★ repo

**The problem.** A client wants a casting or talent-roster system. The nine purpose-built casting
repositories measured this pass are **all at 0 stars and eight carry no licence**, which eliminates
them as bases regardless of code quality.

**The recipe.**

1. **Base** — [opencats/OpenCATS](https://github.com/opencats/OpenCATS) (**dual MPL-2.0 + "CATS
   Project" 2007**, 789★/332f, pushed 2026-11-26, in development since 2009). Candidates become talent;
   job orders become roles; submissions become auditions; its search becomes the breakdown response.
   **Adopt the compilation licence knowingly** — MPL-2.0 is weak, per-file copyleft, and the 2007
   component is bespoke; read the 43 KB LICENSE.md before committing.
2. **Data model reference, not code** — [jacobgwilliams/casting-site](https://github.com/jacobgwilliams/casting-site)
   models **casting offices, agencies and management companies**, the relationship OpenCATS lacks.
   It has **no licence**: read it for schema, write your own.
3. **Agent layer** — [cranberrymuffin/auditionwithme](https://github.com/cranberrymuffin/auditionwithme)
   shows the mechanism worth rebuilding (parse PDF sides → cast and voice other characters → record the
   self-tape). **No licence file — reimplement, do not vendor.**
4. **Consent at intake** — wire Pattern 109 step 1 into the talent record *at booking*, so consent is
   captured where the law says it is created.
5. **Schedule and budget** — [method-production-suite/method-scheduling](https://github.com/method-production-suite/method-scheduling)
   (**dual MIT/Apache-2.0**) for the open schedule format, and
   [gravy42/profitshare](https://github.com/gravy42/profitshare) (**MIT**) for the **SAG-AFTRA tier
   check at rates effective 7/1/2026** plus California fringes.

**What not to promise.** Not a casting product. This is an ATS customisation with a media data model
bolted on, and the honest estimate says so.

## Pattern 111 — The residuals gate: build the record that makes settlement possible, not the settlement

**The problem.** `residuals calculation film` returns **zero** GitHub results and has done across three
independent passes. There is no open-source residuals engine, no union timecard payroll, no performer
royalty settlement. Clients will still ask.

**The recipe — and it deliberately stops short of computing a residual.**

1. **Payroll substrate** — [frappe/hrms](https://github.com/frappe/hrms) (**GPL-3.0**, 9,123★). Deploy
   it for the client; do not embed it in a proprietary deliverable. It knows nothing about guild
   agreements, and that is the gap you are being paid for.
2. **Guild rate tiers as code** — [gravy42/profitshare](https://github.com/gravy42/profitshare)
   (**MIT**) is the **only permissively licensed artefact in this KB that encodes guild economics**:
   SAG-AFTRA low-budget tiers at rates effective 7/1/2026, California payroll fringes, the Diversity in
   Casting cap uplift, every line typed as cash, deferred or points. Its README is explicit that it
   **does not replace a payroll company, a signatory rep or an attorney** — carry that caveat forward.
3. **The deliverable: the liability record.** For each performer, each engagement: the tier, the pay
   type, the consent reference from Pattern 109, the use actually made, and the dated obligation. This
   is the artefact a residual is computed *from*, and it is what nobody has.
4. **Do not build the engine.** Residual terms are negotiated, versioned by agreement and
   jurisdiction, and change with each cycle. The pass-8 finding applies unchanged: **settlement is pure
   judgment, and judgment is where open source stops.**

**Why this is sellable anyway.** The commercial anchors are published: a replica-generated commercial
performance is reported at **1.5× the session fee**, and SAG-AFTRA's voice-replica dubbing consent bites
for pictures commencing principal photography **on or after 2027-07-01**. A buyer with a dated
obligation and no record system has a procurement problem, not a research problem.

## Pattern 112 — The per-jurisdiction consent policy engine

**The problem.** The five instruments in this plane disagree on nearly everything: Mexico's statute is
in force and survives contract termination; SAG-AFTRA binds signatories by contract with a 2027 dubbing
trigger; Denmark's §65a is a bill and is **collectively manageable**; China requires visible **and**
metadata labels under GB 45438-2025; India's courts refuse blanket relief and want evidence per
defendant, per item. One compliance mode cannot satisfy these.

**The recipe.**

1. **One record shape** — `grantmark`'s consent-authority record profile (**Apache-2.0**, JSON Schema +
   test vectors) as the canonical internal representation.
2. **Policy per jurisdiction, data once** — encode each instrument as rules over that record: *does
   consent survive contract end?* (Mexico: yes), *is separate payment required?* (SAG-AFTRA: yes), *can
   the right be collectively managed?* (Denmark §65a: yes), *is a metadata label mandatory?* (China:
   yes), *must evidence be per-item?* (India: yes).
3. **Label and watermark at generation** — `pratidhvani` (**Apache-2.0**) already emits an inaudible
   watermark, which is what China's implicit-metadata requirement and India's per-item evidentiary
   posture both reward.
4. **Cite the regime** — [socialgravity/state-of-ai-identity-licensing-2026](https://github.com/socialgravity/state-of-ai-identity-licensing-2026)
   (**CC BY 4.0** — a *content* licence, not an OSI grant: attribute it, do not treat it as code) is a
   versioned primary-source dataset for the policy table, and
   [AgileWoW/ai-likeness-rights-compliance-guide](https://github.com/AgileWoW/ai-likeness-rights-compliance-guide)
   (**MIT**) is permissively licensed prose you may quote in a deliverable.

**The reusable judgment.** Pass 5 reached the per-jurisdiction policy-engine conclusion for rights
reservation; pass 50 reaches it independently for identity, from both the strictest regime (Mexico) and
the most fragmented (APAC). **Two planes, same answer: the portable asset is the policy engine, not the
compliance mode.**

## Over-the-air transmission recipes — added 2026-11-27 (pass 51)

Every repo named below was verified this pass: existence by `git ls-remote`, metadata by the GitHub
`search/repositories` API, **licence by reading the licence file's bytes**. Run Pattern 117 before
quoting any of the others.

## Pattern 113 — The transport-stream conformance and signalling service (the permissive baseline build)

**Who buys it.** Any broadcaster mid-transition: a US station completing ATSC 3.0, a Brazilian
broadcaster standing up DTV+ beside ISDB-T, a European multiplex operator. **This is the only build in
the plane with no licence friction**, which is why it leads.

**Wiring, step by step.**
1. **`tsduck` (BSD-2-Clause, 1,103★, pushed 2026-11-24)** as the engine. Use `tsp` as a plugin pipeline,
   not as a CLI you shell out to.
2. **Ingest** from the plant: `tsp -I ip` for multicast, or `-I dvb` from a tuner for off-air
   confidence monitoring of your own signal.
3. **Analyse in-stream**: chain `-P analyze`, `-P continuity`, `-P pcrverify`, `-P tables` to emit
   structured PSI/SI, continuity-error and PCR-jitter records.
4. **Add the decision stage as your own `tsp` plugin** — this is where Globant IP lives. Classify
   PCR-jitter and continuity patterns into *transport fault* versus *encoder fault* versus
   *mux-overcommit*, which is the triage call an operator makes manually at 03:00 today.
5. **Validate SCTE-35** splice points against the as-run log before they reach air.
6. **Ship as a service, not as an appliance** — see the licence ledger.

**Why it holds.** BSD-2 permits proprietary derivative work, TSDuck is packaged for Debian/FreeBSD and
has a vendor-independent 21-year maintenance record (copyright 2005–2026), and `tsp`'s plugin boundary
is a genuine extension point rather than a fork.

### Licence ledger for this pattern
- `tsduck` **BSD-2-Clause** — your plugin stays yours. **One hard condition:** `OTHERS.txt` states the
  build downloads **Dektec DTAPI (proprietary, binary-only)** and the installers bundle it, with libsrt
  (MPL-2.0) and librist (BSD-2) binaries on Windows. **Using `tsp` is clean; redistributing a
  TSDuck-derived binary appliance is a licence review.** Build from source with DTAPI disabled if you
  must ship binaries.
- Do **not** pull `dvblast` (GPL-2.0) or `opencaster` (GPL-2.0) into the same process to "fill gaps" —
  that is how a proprietary plugin becomes a distribution problem.

## Pattern 114 — The dual-stack simulcast desk (**the highest-value build in this plane; LATAM first**)

**Who buys it, and why it is ranked first.** Brazilian broadcasters face a **10–15 year** obligation to
run **ISDB-T and DTV+ in parallel** (deployment deadline extended to **end-2027**, Decree **12,595** of
2025-08-27, full coverage estimated at up to 15 years). That is not a migration project, it is a
**permanent two-standard operating model**, and **no vendor sizes it and no open platform addresses it**.

**Wiring, step by step.**
1. **One editorial schedule, two emission chains.** Model the schedule once; render two signalling sets.
2. **ISDB-T leg**: PSI/SI and EIT generation with **`tsduck`**; where a carousel or DSM-CC payload is
   needed, **`opencaster` (GPL-2.0)** is the only open option — run it **as a separate process behind a
   pipe**, never linked in.
3. **DTV+ leg**: ATSC 3.0 signalling. **Stop here and read Pattern 115** — there is no open path to a
   retail ATSC 3.0 receiver, so this leg integrates a **commercial** exciter/gateway. Your deliverable
   is the signalling and conformance layer in front of it, not the modulator.
4. **Reconciliation gate**: assert that the two legs carry the same service at the same time — the
   regulator-facing artefact, and the one thing a broadcaster cannot currently prove automatically.
5. **Per-site sequencing** from coverage studies (Pattern 116) to decide the order in which sites get
   DTV+.
6. **As-run evidence** for both legs, retained — this is what makes the parallel period auditable.

**What this pattern will not do.** It will not transmit ATSC 3.0 from open source, it will not resolve
the VVC/LCEVC patent position (Pattern 115), and it will not shorten the parallel period — **the
parallel period is the revenue.**

### Why this is the best-qualified LATAM engagement in this plane
A **legal deadline**, **zero open implementation** of the target stack, a **decade-long** dual-stack
obligation, and **proven local capacity** — `git-artes/gr-isdbt` (GPL-3.0-or-later, **195★**, UdelaR
Montevideo) is the most-starred modulation repo in the plane and it is Latin American. The capability is
local and documented; what is missing is an industrial programme aimed at the incoming standard.
**Standing recommendation: partner with UdelaR rather than compete with it.**

## Pattern 115 — The TV 3.0 patent-and-licence gate (**run this before anyone budgets a codec**)

**A 20-minute gate, in the shape of Pattern 101, and it has teeth.** Brazil's decree mandates **VVC with
an MPEG-5 LCEVC enhancement layer**. Pass 8 established, by reading the licences, that the open
reference implementations of exactly those codecs — **`vvenc`, `vvdec`, `LCEVCdec`, all
`BSD-3-Clause-Clear`** — **expressly grant no patent rights**; the *Clear* in the licence name **is**
the carve-out. **Brazil has therefore mandated a codec pair whose open implementations decline to
license the patents.**

**The four questions, in order.**
1. **Will you ship an encoder/decoder binary, or only operate a service?** Operating is not
   distributing; the exposure differs.
2. **Have you priced the VVC pool licences?** There is more than one pool. "We'll use the open
   implementation" is **not** an answer to a patent question.
3. **Does LCEVC's licensing position cover your deployment shape** (broadcast emission versus
   client-side enhancement)?
4. **Who indemnifies?** If nobody, the answer is a commercial encoder with indemnity, and the open
   implementation is a **bench tool only**.

**Deliverable.** A two-page position stating what may be shipped, what must be licensed, and what stays
on the bench — produced **before** the architecture, because it changes it. This is a short, high-trust
first engagement and nothing in the market sells it.

## Pattern 116 — The coverage-prediction service, with the model/licence trap wired in

**The trap, stated first.** The **only permissively-licensed** propagation engine in this plane —
**`edwardoughton/itmlogic`, MIT (verified, 1,143 B), 73★** — implements **Longley–Rice/ITM**, the model
**North American** filings use. **Every other region's filings require ITU-R P.1546 or P.1812**, whose
only implementations are a **personal account under a bespoke non-OSI notice**, topping out at **15★**,
with **P.1546 untouched since 2024-08-16**. **A coverage service is therefore a different build in North
America than anywhere else**, and anyone who ships one build has shipped the wrong model somewhere.

**Build A — North America (clean, permissive, recommended).**
1. **`itmlogic` (MIT)** for the propagation core, or **`NTIA/itm`** (17 U.S.C. §105 + express worldwide
   royalty-free grant, 88★, pushed 2026-11-24) when you need the agency's own C++ reference.
2. Terrain from public DEM; the NTIA library ships **separate test-data repositories** — use them as
   regression fixtures, which is the whole reason this base is trustworthy.
3. Wrap as a hosted service. **No copyleft obligation**, so the service layer is proprietary.
4. **ATSC 1.0 → 3.0 service-contour replication** as the headline output: prove the new contour covers
   the old one, which is the station's regulatory burden.

**Build B — EMEA / APAC / LATAM (constrained; price the constraint).**
1. The required models are **P.1546 / P.1812**. Available implementations: `eeveetza/p1546` (12★),
   `Py1812` (15★), `p452` (12★) — **bespoke non-OSI notice**; `cpp452` (6★) is the account's one
   GPL-3.0 repo.
2. **Do the licence review before the engineering.** The notice is the NTIA text **with the
   rights-granting paragraph deleted**; a personal account has no §105 to rely on. Treat the grant as
   **unsettled**, and get written permission or reimplement from the published Recommendation.
3. **Reimplementation from the ITU-R Recommendation text is the defensible path** and is a real,
   scopeable deliverable: the Recommendations are published, the maths is specified, and the result can
   be **MIT and yours**. Validate against the existing code as a reference oracle, not as a dependency.
4. **`hoche/splat` (GPL, `COPYING` 17,990 B)** is the free terrain tool, with two caveats: it outputs
   **path loss, not dBµV/m** — the unit coverage is specified in — and **GPL** makes a hosted service a
   licence decision.
5. **Do not use `Cloud-RF/Signal-Server`** (4★, **no licence file detected**).

**The sellable insight.** Three-quarters of the world's broadcast regulators depend, for a regulatory
input, on a **twelve-star personal repository under a notice that is not an OSI licence**. Naming that
in a first meeting establishes more credibility than any capability slide — and **the MIT
reimplementation of P.1546/P.1812 is the single most defensible piece of IP available in this plane.**

## Pattern 117 — The transmission-stack due-diligence audit (**the cheapest credible first engagement**)

**Why it exists.** European and APAC broadcasters are, today, planning work on an **archived**
transmitter and a **12-star** propagation model without knowing it. A two-week audit that says so is
worth more than a capability deck, and it qualifies the client for Patterns 113–116.

**The checklist, all verifiable in an afternoon.**
1. **Is the open component you are relying on archived?** `drmpeg/gr-dvbt2`: **archived, read-only,
   last pushed 2018-10-31**, 73★. Its live successor `gr-dvbt2ll` has **19★**.
2. **Does your "open ATSC 3.0" path reach a real receiver?** `gr-atsc3` (51★) has **no ROUTE/DASH**;
   `libatsc3` has **no canonical repository**. If the plan involves a retail set, the answer is no.
3. **Does an open implementation of your target standard exist at all?** For **Advanced ISDB-T**:
   **none, at any star count, under any licence.**
4. **Read the licence file's bytes, every time.** Three of this plane's most important components report
   `NOASSERTION` and are **not** unlicensed: `gr-isdbt` is **GPL-3.0-or-later**, `itmlogic` is **MIT**,
   `NTIA/itm` is **effectively public domain with an express worldwide grant**. A `NOASSERTION` is a
   prompt to read, never a conclusion.
5. **Audit what the build downloads, not just what the repo contains** — the TSDuck/DTAPI case.
6. **Count the maintainers.** One individual holds **DVB-T2, DVB-S2 and ATSC 3.0**; one university lab
   holds **ISDB-T**; one association holds **5G Broadcast**. Then ask the client who they call at 03:00.
7. **If forks exceed stars, the tool is load-bearing and unmaintained** — `opencaster`, 79f/74★.

## Pattern 118 — The EMEA per-country spectrum roadmap engine

**The spec comes from a regulator.** The **RSPG concluded that a common post-2030 UHF spectrum policy
across Europe is impracticable**, recorded in the **EBU's September 2026 WRC-27 opinion**; EU law
protects **470–694 MHz** for DTT and PMSE **until at least 2030**; and the decisive conference is
**WRC-31, not WRC-27** — WRC-27 only decides what WRC-31 will consider. **Correct that misreading in the
first meeting.**

**Wiring.**
1. **A per-country state model**, not a compliance mode: current standard (DVB-T/T2), switch-off status,
   national post-2030 position, PMSE dependency, 5G Broadcast trial activity.
2. **Scenario branches** keyed to WRC-31 outcomes, with the 2030 legal floor as the invariant.
3. **Coverage impact per scenario** via Pattern 116 **Build B** — ITU-R models, so read the licence gate.
4. **5G Broadcast option appraisal**: the **5G-MAG** reference stack (`rt-mbms-modem`, `rt-mbms-tx`,
   both **AGPL-3.0**, pushed 2026-11-24; `rt-mbs-examples` pushed 2026-11-27) with **Rai/EBU
   Milano-Cortina 2026** trials in Rome and Turin as the evidence base.
5. **The AGPL gate, explicitly:** AGPL-3.0 on a transmit path obliges source release to the users of a
   network service. **Decide this before architecture, not after.**

**The reusable judgment, now confirmed a third time.** Pass 5 reached the per-jurisdiction policy-engine
conclusion for rights reservation; pass 50 reached it for performer consent; **pass 51 reaches it for
spectrum — and this time a regulator wrote the conclusion down.** With one critical limit recorded in
`intel/trends.md`: **a policy engine cannot abstract a modulation scheme.** Patterns 113–117 are
per-standard builds, and this is the one plane in the KB where "build once, configure per region" is
**false**.

## 🔮 Falsifiable prediction recorded this pass (test it in a later plane)

**If a corporate contributor ever enters the open modulation layer, it will arrive permissively licensed
and on the *receiver* side, not the transmitter** — because receivers ship in silicon and transmitters
ship in licences. Baselines recorded 2026-11-27: `tsduck` 1,103★ (BSD-2, the lone permissive asset),
`gr-isdbt` 195★, `NTIA/itm` 88★, `itmlogic` 73★, `gr-atsc3` 51★, `rt-mbms-modem` 26★, `SpectrumAlert`
22★, `Py1812` 15★, `p1546` 12★ (unpushed since 2024-08-16). **Secondary test:** whether `gr-dvbt2ll`
(19★) ever crosses its archived predecessor's 73★ — if it never does, this plane's problem is
discoverability, not maintenance.

## ⛔ What not to promise in this plane (pass 51)

- **An open ATSC 3.0 service path** — `gr-atsc3` cannot reach a retail receiver; `libatsc3` has no
  canonical repo.
- **An open DVB-T2 transmitter from the obvious repo** — archived since 2018.
- **Anything for Advanced ISDB-T** — no open implementation exists.
- **An open TV 3.0 stack** — none exists, and its mandated codecs' open implementations grant **no
  patent rights**.
- **A single coverage service for all regions** — the permissive engine implements the **North American**
  model only.
- **A supported, permissive P.1546/P.1812 implementation** — it does not exist. Offer to **build** it.
- **Brazil's mid-2026 World Cup timeline** — superseded; cite the decree and the **end-2027** extension.
- **An agent ecosystem** — the entire ML layer of this plane is **one repo at 22★**.

## Pattern 119 — The licence-clean archive remaster pipeline (**the GPL boundary, solved by process isolation**)

**The problem this solves.** The client wants a restoration pipeline they can ship inside a proprietary
product. The only mature motion-compensated repair filters in open source are **GPL-2.0**
(`pinterf/RemoveDirt`, `dubhater/vapoursynth-mvtools`). Linking them into proprietary code is not available
to you. Doing the repair with permissive code alone means accepting a 20★ plugin as your only tool.

**The wiring — and the boundary is the point.**

1. **Ingest / IO** — [`AcademySoftwareFoundation/OpenImageIO`](https://github.com/AcademySoftwareFoundation/OpenImageIO)
   (**Apache-2.0**, 2,409★) reads the scanner's DPX/Cineon and writes the EXR intermediate via
   [`openexr`](https://github.com/AcademySoftwareFoundation/openexr) (**BSD-3-Clause**, 1,893★).
2. **Colour** — [`OpenColorIO`](https://github.com/AcademySoftwareFoundation/OpenColorIO)
   (**BSD-3-Clause**, 2,152★) carries the log→linear transform. Set this up before any repair: a dust
   detector tuned on mis-linearised frames will chase grain.
3. **Repair — ACROSS A PROCESS BOUNDARY.** Drive
   [`vapoursynth`](https://github.com/vapoursynth/vapoursynth) (**LGPL-2.1**, 2,138★) as a **separate
   executable invoked over a CLI/pipe**, running a Python script that loads the GPL filters
   (`RemoveDirt` → `RestoreMotionBlocks`/`SCSelect`, plus MVTools for motion vectors). Your proprietary
   orchestrator passes file paths and a script; it does **not** link GPL code into its own address space.
   VapourSynth itself being **LGPL rather than GPL** is what makes the frameserver safe to depend on.
4. **Permissive repair where it suffices** — for single-frame dust on material that does not need temporal
   motion compensation, [`fabiocolor/Advanced-Dirt-Removal`](https://github.com/fabiocolor/Advanced-Dirt-Removal)
   (**MIT**, 20★, pushed 2026-11-20) runs as an **OFX plugin** inside
   [`Natron`](https://github.com/NatronGitHub/Natron) (**GPL-2.0**, 5,778★) or inside DaVinci Resolve's free
   tier. Its documented limit is real: **it fills from neighbouring frames, so it cannot fix damage that
   persists across several frames** — a long scratch or a hair in the gate still needs the GPL temporal path
   or a commercial suite.
5. **Enhance (optional, and label it)** — [`ByteDance-Seed/SeedVR`](https://github.com/ByteDance-Seed/SeedVR)
   (**Apache-2.0**, 1,469★) for restoration/upscale and
   [`hzwer/Practical-RIFE`](https://github.com/hzwer/Practical-RIFE) (**MIT**, 1,054★) for frame rate.
   **Do not reach for Real-ESRGAN/GFPGAN/DeOldify here** — all dormant since 2024, DeOldify archived.
6. **Review and QC** — [`grizzlypeak3d/DJV`](https://github.com/grizzlypeak3d/DJV) (**BSD-3-Clause**,
   1,180★) for full-bit-depth playback; [`jhove`](https://github.com/openpreserve/jhove) and
   [`jpylyzer`](https://github.com/openpreserve/jpylyzer) to validate the delivered masters and access
   copies.

**Get the legal review on step 3 in writing before you build it.** Process isolation versus linking is a
well-trodden distinction, but it is the client's counsel who has to be comfortable, not you — and the
answer changes if you ever ship the VapourSynth binary *inside* your installer.

**What to tell the client up front:** the scanner itself is **not** in scope for open source — there is no
open scanner-control stack at any usable maturity (see `repos/foundations.md`, step 1).

## Pattern 120 — The restoration triage agent (**decide what to restore before restoring anything**)

**The problem this solves.** An archive has tens of thousands of cans and a budget for dozens. The
expensive decision is *which* material to restore, and it is currently made by an operator spot-checking
reels. The NFPF's 2026 round funded **54 films** — that is the scale of the funnel, against collections
orders of magnitude larger.

**The wiring.**

1. **Cheap proxy scan** of everything (not a preservation scan) — any capture that produces viewable frames.
2. **Damage detection per shot**, as a scoring pass, not a fixing pass: run the **detectors** from the
   permissive/unlicensed micro-tools as measurement only —
   [`Abel1629/Image-restoration-with-OpenCL`](https://github.com/Abel1629/Image-restoration-with-OpenCL)
   (deflicker + motion-protected dust/scratch detection) and
   [`Sandesh-Chougala0/Scratched-to-Screen`](https://github.com/Sandesh-Chougala0/Scratched-to-Screen)
   (vertical-scratch detection by morphological filtering). **Both carry NO licence** — so use them as
   *algorithm references you reimplement*, not as dependencies. Reimplementing a morphological scratch
   detector is a day's work; clearing an unlicensed dependency is impossible.
3. **Shot segmentation** with `PySceneDetect` (**BSD-3-Clause**, already in `repos/foundations.md` from
   pass 6) so the damage score is per shot, not per reel.
4. **Rank** by `damage × catalogue value`, where catalogue value comes from the **archive-monetisation
   plane (pass 42)** — shot-level discovery and clip-licensing demand. This is the join that makes the
   pattern commercial rather than curatorial: **restore what sells or what is decaying fastest, and show
   the arithmetic.**
5. **Output** a ranked work order with per-title cost estimates, in the shape a grant application needs
   (NFPF's unit of funding is a preservation master plus two access copies — match that unit).

**Why this is the right first engagement.** It needs no restoration licence, no scanner, and no commercial
suite. It is pure orchestration over permissive code, it produces a defensible number, and it is the
artefact the archive's funder actually asks for.

## Pattern 121 — Provenance-documented restoration (**the deliverable the 2026 draft guidance is pointing at**)

**The problem this solves.** Once a restoration includes a learned upscale, an interpolated frame or a
colourisation, the archive has created material that is partly synthetic. FADGI's draft on **content
authenticity and provenance for AI-impacted audiovisual collections** (public comment closed
**2026-10-15**) signals that documenting this becomes expected practice. An archive that cannot say which
frames were invented has a catalogue problem that compounds every year.

**The wiring.**

1. **Record the chain, per shot, as data** — source element and gauge, scanner settings, the OCIO transform
   applied, each repair filter with its parameters, and **every learned model by name, version and licence**
   (`SeedVR` Apache-2.0, `Practical-RIFE` MIT, and so on).
2. **Attach it to the asset** using the identification substrate from **pass 5** — the fingerprinting and
   rights-reservation plane — so the provenance travels with the file rather than living in a spreadsheet
   that is lost at the next migration.
3. **Mark the synthetic frames explicitly.** An interpolated frame from RIFE is not a photographic record of
   anything. Flag it at frame level; this is the single most defensible thing an archive can do and almost
   nobody does it.
4. **Validate and seal** with [`jhove`](https://github.com/openpreserve/jhove) /
   [`jpylyzer`](https://github.com/openpreserve/jpylyzer), and wrap the whole package with
   **Archivematica** (pass 4).
5. **Re-verify the guidance against the primary source.** Everything above about FADGI in this KB is
   **search-attested only** — `digitizationguidelines.gov` is outside this session's network policy. Read
   the actual draft before you write it into a statement of work.

**The commercial angle.** This is the layer the commercial suites do not provide, because they are
single-operator desktop tools. It is also what makes a restored catalogue licensable for AI training on
defensible terms (pass 42): a buyer paying for archive footage increasingly wants to know what in it is
photographic and what is generated.

## ⛔ What not to promise in this plane (pass 52)

- **An open-source replacement for DIAMANT-Film, PFClean, VIVA or MTI.** It does not exist. The whole open
  film-damage-repair layer is ten repositories and the largest with a usable licence has **20★**.
- **"State-of-the-art AI restoration" built on Real-ESRGAN, GFPGAN, DeOldify or BasicSR.** All dormant since
  mid-2024; **DeOldify is archived**. They work, they are not maintained.
- **GPL filters inside a proprietary binary.** `RemoveDirt` and the MVTools ports are **GPL-2.0**. Pattern
  119's process boundary exists for this reason and needs counsel's sign-off.
- **Anything resting on `pinterf/mvtools`'s licence.** 192★, pushed 2026-11-14, **no licence file at all** —
  verified by a control request that passed plus a complete 404 sweep of every licence filename.
- **`avisalmon/MOV8mm` as cleared MIT code.** Its licence says `Copyright (c) 2025 [Your Name]`.
- **An open scanner-control stack.** `telecine scanner film capture` returns **zero** repositories; the
  best-known project (`kinograph`, GPL-3.0) has been dormant since **2016**.
- **A single film-restoration market size.** Three firms disagree by **2.9×** on nominally the same market.
- **A FADGI-conformant film scan to a current specification.** The motion picture film scanning guideline is
  **still the 2015/2016 document** and the two ISO standards that define scanner resolution and dynamic
  range are **paid**.
- **`darbyjohnston/DJV` as a URL.** It is a redirect; the canonical repo is `grizzlypeak3d/DJV`.

---

## Pattern 122 — The TPN / R143 readiness evidence pack, assembled from permissive parts

**Why:** studios push content-security controls down their supply chain, and **no open-source
implementation of either framework exists** — verified this pass for both the **MPA Content Security Best
Practices v5.3.1** (gated: assessed through the member-only TPN+ platform; **TPN no longer issues
certificates**; each content owner still makes its own call) and **EBU R 143 v3.0** (March 2025; **free
public PDF** plus a **free official "Security Controls Assertion" spreadsheet**, 8 sections: operational
security, secure development, incident management, physical security, cloud security, business continuity,
supply chain). The deliverable is therefore **not a tool and not a certificate — it is an evidence pack**,
and every component below is something the client keeps.

```
  CONTROL CATALOGUE (not code)                 EVIDENCE PRODUCERS (all self-hosted)
  MPA CSBP v5.3.1 domains  ----+               +--> wazuh/wazuh        GPL-2.0 (+AGPL engine) 17.9k*
  (physical, logical,          |               |     log + file-integrity + config evidence
   network, personnel,         +---- map ----->+--> Velocidex/velociraptor  AGPL-3.0  4.5k*
   asset management)           |               |     endpoint forensics: "what was touched"
  EBU R 143 v3.0 xlsx  --------+               +--> aquasecurity/trivy + anchore/syft  Apache-2.0
  (8 sections, free)                           |     SBOM + vulnerability evidence
                                               +--> mitre/caldera      Apache-2.0  7.6k*
                                               |     PROOF the control works, not an assertion
                                               +--> restic BSD-2 37.5k* / kopia Apache-2.0
                                                     the restore test, with a dated result
```

**Steps**

1. **Pick the catalogue by region, not by preference.** Selling into a US studio's vendor list → **MPA
   CSBP v5.3.1** (mapped by TPN to AICPA TSC 2017, CSA CCM v4.03, ISO/IEC 27001:2022, 27002:2022 and
   NIST 800-53, so an existing ISO 27001 estate is mostly reusable evidence). Selling into an **EBU-member
   tender** → **R 143 v3.0** and its assertion spreadsheet, which is written for exactly that procurement
   moment.
2. **Produce evidence, not prose.** Each control gets a generated artefact with a date: a Wazuh
   file-integrity report, a Velociraptor collection, a Trivy SBOM, a Caldera run showing the detection
   fired.
3. **Test the restore and put the number in the pack.** Business continuity is a section in both
   frameworks and the only honest evidence is a timed restore.
4. **Keep the licence boundary visible.** Wazuh's `src/engine/` is **AGPL-3.0-or-later** and Velociraptor
   is **AGPL-3.0**: operating them for the client is fine; **exposing them as a multi-tenant service is a
   counsel question.** Never put **Graylog (SSPL)** under a managed offering.

**Do not promise:** "TPN certification" (the programme does not certify), a Gold Shield as a universal pass
(it is not), or an open-source tool that fills either questionnaire (none exists in either framework, and
the free one is as empty as the gated one).

---

## Pattern 123 — IS-10 authorization on an ST 2110 plant, without a media-specific product

**Why:** the IP broadcast plant (pass 44: ST 2110, NMOS, PTP) is a flat, highly regular network where an
unauthenticated device can drive a router or a playout node. **AMWA IS-10** (NMOS Authorization,
**Apache-2.0** spec, v1.0.1) is the standard for that, and the **only broadcast-specific implementation
ever published is archived**: `bbc/nmos-auth-server`, **11★/4f, read-only since 2025-03-25**, targeting the
earlier BCP-003-02 draft. `MovieLabs/CSAP` **does not exist as a repo**. The answer is a horizontal identity
server wearing a media claims profile.

```
  [keycloak/keycloak  Apache-2.0  38,060*]   <- the authorization server; AMWA's own IS-10
        |   issues JWT with IS-10 claims         guidance uses Keycloak. NOT a bespoke build.
        v
  [sony/nmos-cpp  Apache-2.0  204*]  <---- registry + node (pass 44)
        ^   validates Bearer token against JWKS from the AS
        |   claim semantics reference: alabou/NMOS-Reference  Apache-2.0
  [openziti/ziti  Apache-2.0  4.5k*]  <- control plane is DIALLED, not routable
        |
  [zeek/zeek BSD-3] + [OISF/suricata GPL-2.0] --> [idaholab/Malcolm Apache-2.0 497*]
        PTP/NMOS traffic is extremely regular => anomalies are unusually detectable here
```

**Steps**

1. **Configure, don't build.** Stand up Keycloak as the IS-10 authorization server and model the IS-10
   claims; use `alabou/NMOS-Reference` (Apache-2.0) as the reference for JWKS fetch and claim enforcement
   on the node side. Add **BCP-003-01** (Apache-2.0) for TLS on the NMOS APIs.
2. **Take the control plane off the routable network** with OpenZiti, so an unauthenticated device cannot
   even reach the control API to be rejected by it.
3. **Watch the plant with Malcolm**, because ST 2110/PTP traffic is periodic and well-formed: baseline
   drift is a far stronger signal here than in an office network. This is the one place a media-specific
   detection set is worth writing — and **no vendor's default ruleset contains it**.
4. **Cross-check the alerting chain** against the FCC EAS cybersecurity obligations already recorded in
   this KB (pass 45, in force, deadline **2026-09-29** passed) when the plant carries EAS.

**Do not promise:** a build on `bbc/nmos-auth-server` (archived), anything resting on
`OfferPk/nmosis10forge-pro` (**no licence file at 6 names** — all rights reserved), or "the NMOS security
product", which does not exist.

---

## Pattern 124 — An LLM triage agent for a studio SOC that breaches neither the licence nor the perimeter

**Why:** this is the one plane in media where the agentic layer is already permissive and maintained — and
it carries two constraints that are specific to media and specific to 2026, both of which this pass
measured rather than assumed.

```
  detection content: SigmaHQ/sigma  <-- rules are DRL-1.1, NOT the repo's licence
        |                                 attribution must survive INTO the alert text
        v
  [wazuh/wazuh GPL-2.0/AGPL engine]  or  [zeek/zeek BSD-3 -> idaholab/Malcolm Apache-2.0]
        |
        v   MCP bridge -- START READ-ONLY
  [Letos01/Mcp-wazuh  MIT]  (prompt-injection defence; treats every log byte as hostile)
        |   or gensecaihq/Wazuh-MCP-Server  MIT  282*  (55 tools, read+write)
        v
  [beenuar/AiSOC  MIT  8.3k*]  or  [Vigil-SOC/vigil  Apache-2.0  481*]
        |   LOCAL model, human-approved response, every prompt and tool call logged
        v
  analyst  --- approves --->  action        (autonomous response OFF by default)
```

**The two hard requirements**

1. **Propagate the rule author into the summary.** Sigma's rules are **DRL 1.1**, which requires that
   *messages based on matches* retain the rule's `author` field. **An LLM summary of a Sigma-matched alert
   is such a message.** Carry `author` through the summarisation prompt into the rendered alert. This is
   the only licence in this KB that a paraphrase can breach, and no SBOM scan will catch it.
2. **The prompt itself is the crown jewel.** A studio's alerts name **unreleased titles, cuts and key
   art** — the Inception leak-site claim of 2026-11-26 advertised ~5 TB of exactly that (unverified claim,
   see `intel/trends.md` §52). So **the triage transcript becomes pre-release content** and must stay
   inside the assessed perimeter. Both AiSOC and Vigil are **local-first and run against your own
   model**; that property is not a nice-to-have here, it is **the reason these two are the correct choices
   over any hosted SOC copilot**. Note the generalisation: **an AI SOC for a studio is one of the few AI
   deployments where the input, not the output, is the asset being protected.**

**Steps**

1. Start with the **read-only** bridge (`Letos01/Mcp-wazuh`) and autonomous response **off** — the default
   in Vigil and Argus alike. Earn write access later.
2. Keep the **agent's own runtime** sandboxed: `nolabs-ai/nono` (**Apache-2.0, 5.1k★**) exists for exactly
   this, and the moment the agent holds credentials it is itself an asset in the TPN-assessed estate.
3. Log every prompt and tool call (AiSOC does this by default) — that log is also your evidence artefact
   for Pattern 122's incident-management section.
4. **Pin versions and re-read licences each pass.** `beenuar/AiSOC` went from a reported ~6,353★ on
   2026-11-25 to **8.3k★ on 2026-11-27**: that is **velocity, not installed base**, and a project moving
   that fast can relicence or change posture between engagements.

**Do not promise:** `birhantprkc/AiSOC` or `saledream/wazuh-mcp-server` (**both 404 — surfaced by search,
do not exist**; AiSOC's real origin is `beenuar/AiSOC`, and three live *forks* of the dead name resolve
perfectly), `MISP/misp-mcp` as cleared AGPL code (**no licence file**; the grant is README prose only),
`FiligranHQ/xtm-mcp` (**archived 2026-07-05**), or `SecurityClaw/SecurityClaw` as actively maintained
(**last commit 2026-07-20**).

---

## Pattern 125 — The compliant AI-anchor stack, built only from permissive parts (**and the one component you must build, because it does not exist**)

**The situation.** A client wants a synthetic host presenting products on a live stream. The generation layer
is permissive, large and actively maintained; the **disclosure** layer that China's Order No. 117 already
requires and the EU's DFA draft would require **has no open implementation anywhere**.

**Wiring.**

1. **The host.** [`lipku/LiveTalking`](https://github.com/lipku/LiveTalking) — **Apache-2.0** (`LICENSE`,
   11,344 B), 11,373★, pushed 2026-11-27. Real-time interactive streaming digital human.
2. **The assembled reference.** [`l11223/digital-human-livestream`](https://github.com/l11223/digital-human-livestream)
   — **Apache-2.0** (11,344 B), 169★ — a LiveTalking derivative that already wires in LLM dialogue, **danmaku
   interaction, a content-safety filter and a web admin console**. Read this before building; it is the
   closest thing to a deployable product and it is permissively licensed. Last push 2026-02-14, so treat it as
   a blueprint, not a dependency.
3. **Fully-local variant where data cannot leave the country** (EMEA sovereignty, China hosting):
   [`HeiXia2077/live-avatar`](https://github.com/HeiXia2077/live-avatar) — **MIT** (`master/LICENSE`, 1,081 B),
   136★: Qwen + `llama.cpp` + `wav2lip`, no external inference call.
4. **The room and the overlay.** [`Tencent-RTC/TUILiveKit`](https://github.com/Tencent-RTC/TUILiveKit) —
   **MIT** (1,078 B), pushed 2026-11-27 — for the interactive room;
   [`DIYgod/DPlayer`](https://github.com/DIYgod/DPlayer) — **MIT** (`master/LICENSE`, 1,121 B), 16,551★ — for
   the web danmaku layer; [`CarGuo/GSYVideoPlayer`](https://github.com/CarGuo/GSYVideoPlayer) —
   **Apache-2.0** (11,359 B), 21,536★ — for Android.
   ⚠️ **Do not reach for [`bilibili/DanmakuFlameMaster`](https://github.com/bilibili/DanmakuFlameMaster)**
   (Apache-2.0, 9,605★): it is the reference implementation and it has been **dormant since 2020-02-27**.
5. **Transport.** `SRS` (MIT) or `OvenMediaEngine` (Apache-2.0) — already recorded in pass 8. Nothing in this
   plane changes the transport problem.
6. 🔨 **The component you build: the persistent AI-host disclosure overlay.** Order No. 117 requires labelling
   of AI-generated content and brings digital-human hosts under oversight; the DFA draft would require the
   disclosure to appear **from the outset, in the same medium and language, and to remain in place throughout**.
   Specify it as: a disclosure layer **bound to the stream's own lifecycle** (not a chat message, not a
   pre-roll), per-language, rendered into the video path so it survives clipping and re-upload, with a signed
   log of what was displayed when.

**Why this is the right shape.** Every generative component is Apache-2.0 or MIT and verified; the obligation
is real, dated and enforced (**¥26.7 m Kuaishou fine, January 2026**); and the compliance component is
**greenfield**. Price it as compliance engineering, not as a streaming build.

**⚠️ Two repositories to exclude explicitly, because they are what a search engine returns.**
[`WWBN/AVideo`](https://github.com/WWBN/AVideo) (2,115★, pushed 2026-11-27) is **the JSON licence** — *"used
for Good, not Evil"* — **not OSI, Debian-non-free (`license-problem-json-evil`), undeployable**, and a web
search called it MIT. [`lipku/LiveStream`](https://github.com/lipku/LiveStream) (98★) has **no licence file at
all** across eleven filename probes on two branches, with `README.md` returning 200 — same author as
LiveTalking, opposite licence position. **All rights reserved by default.**

---

## Pattern 126 — The join layer: stream moment → pinned product → checkout → attributed sale (**the assembly nobody ships**)

**The measurement that justifies building rather than buying.** `livestream ecommerce` returns **36 results in
total**; the only repository self-describing as a *"headless shoppable video platform"*
([`james-a-rob/KodaStream`](https://github.com/james-a-rob/KodaStream), 41★) is **proprietary,
non-commercial-only, all rights reserved** (`LICENSE`, 2,173 B, read in full, UK governing law); **Google's
own** [`google-marketing-solutions/shoppable-video`](https://github.com/google-marketing-solutions/shoppable-video)
is **Apache-2.0 with 5 stars** and needs a billed GCP project; and
[`kukuhtw/livestreamshop_rust`](https://github.com/kukuhtw/livestreamshop_rust) (**Apache-2.0**, 11,357 B) is
the honest permissive attempt at **6★**, last pushed 2025-09-06.

**Wiring — all MIT or BSD, all verified by file read.**

1. **Catalogue and checkout:** [`medusajs/medusa`](https://github.com/medusajs/medusa) — **MIT**
   (file-verified; the API says `NOASSERTION`), 37,463★ — or [`saleor/saleor`](https://github.com/saleor/saleor)
   (BSD-3-Clause) where B2B/multi-region is dominant. Both recorded in pass 37.
2. **The pin event.** Define one primitive: `(stream_id, media_timestamp, product_sku, locale)` emitted when
   the host pins an item. **This is the whole missing standard** — there is no open interchange format for it,
   which is why `product feed` and `product tag` both returned **0 hits** in this KB before today.
3. **Overlay rendering:** `DPlayer` (MIT) web-side, `GSYVideoPlayer` (Apache-2.0) Android-side, consuming the
   pin event over the same channel that carries danmaku.
4. **Attribution and payout:** [`getcoherence/openpartner`](https://github.com/getcoherence/openpartner) —
   **MIT** (`LICENSE`, 1,081 B), **18★/11f**, pushed 2026-11-25 — Stripe Connect payouts with a full
   attribution chain. **Be explicit with the client that this is an 18-star dependency**: read it before
   adopting, and budget to maintain a fork.
   ⚠️ **`dubinc/dub` is the alternative and it is directory-scoped**: the `(ee)` directories fall under the
   **Dub.co Commercial Licence**, which requires a paid Enterprise subscription **for production use** —
   exactly this use. Same shape as `PostHog`'s `ee/` and `tolgee`'s `ee/` already recorded in this KB. Resolve
   per directory before vendoring.
5. **Retrieval when the catalogue metadata is poor:** `mlfoundations/open_clip` (MIT) for shot-level product
   retrieval, `Grounded-SAM` (Apache-2.0) for region proposals — both already in this KB. Use these instead of
   searching for a "product recognition" product: `product recognition video` returns **25 results**, top hit
   13★ and unrelated.
6. **Clip the stream into the asset you actually monetise afterwards:**
   [`avisii1680769-cell/livestream-clip-editor`](https://github.com/avisii1680769-cell/livestream-clip-editor)
   — **MIT** (1,065 B), 10★, pushed 2026-11-14. **Low star count, correct idea**: the KB's own EMEA evidence
   says shoppable *video* outperforms the live room in Europe, so the clip is the deliverable, not a byproduct.

**Why it sells.** The channel's size is disputed **3.4×** in the US and **8.3×** globally *because nobody
instruments it*. A client who can answer *"what did this stream sell, by moment, by creator, by locale"* owns
the number the entire channel is bought and sold on. **Lead with that, not with the platform.**

---

## Pattern 127 — The disclosure-and-consent evidence pack for synthetic hosts (**two jurisdictions, both already in force, one deliverable**)

**The trigger is published and dated in both regions**, which makes this the rare compliance build that does
not depend on a forecast.

| Jurisdiction | Instrument | Status | What it demands of a stream |
|---|---|---|---|
| **China** | SAMR **Order No. 117**, *Supervision and Management Measures for Live Streaming E-commerce* | **In force 2026-02-01**; ¥26.7 m fine already issued (Jan 2026) | Digital-human hosts under oversight; **labelling of AI-generated content**; no false/misleading promotion (Art. 34); Advertising Law applies (Art. 35) |
| **EU** | **Digital Fairness Act**, draft | **Published 2026-11-11** — start of the legislative process; **article numbers from leaked-draft commentary, re-verify** | **"advertisement"** or **"commercial collaboration"**, from the outset, same medium and language, **remaining in place throughout** (Art. 11(1)); brand must secure creator compliance **by contract** (Art. 11(6)) |
| **Mexico** | Decree amending the **Federal Copyright Law** and **Federal Labour Law** | **Published 2026-05-14** — the region's first sector-specific AI rules for M&E | Consent for image and voice **extends to AI-generated output**; contract terms and pay for AI use of a performer's likeness; **increased severance where AI replaces a human** |

**The deliverable — one artefact, three audiences.**

1. **The persistent disclosure layer** from Pattern 125, step 6, with its signed display log. The log is the
   evidence; the overlay alone proves nothing after the stream ends.
2. **The consent record for the likeness.** Where the host is synthetic and modelled on a real performer,
   Mexico now makes this a copyright **and** employment matter. **Do not rebuild this here** — the KB's
   talent, casting and performer-consent plane (pass 50) is the file that answers it, and this pattern should
   import its consent-record format rather than invent a second one.
3. **The contractual clause pack** satisfying DFA Art. 11(6): the brand must be able to show it *required*
   creator compliance, not merely hoped for it. Pair each clause with the field in the display log that
   evidences it.
4. **The audit view.** [`lengzhanbao/taobao_scraper`](https://github.com/lengzhanbao/taobao_scraper) — **MIT**
   (`LICENSE`, 1,089 B), **8★**, pushed 2026-11-26 — captures Taobao Live streams with danmaku and performs
   **digital-human detection**. It is tiny, and it is the **only** code located anywhere that engages the
   AI-host disclosure rule. Note what it tells you about the market: **the only implementation detects
   somebody else's non-compliance from the outside; nothing declares its own from the inside.** Use it to test
   your own overlay adversarially — if an open 8-star scraper can tell your host is synthetic while your
   disclosure layer is silent, you have the finding before the regulator does.

**Falsifiable prediction, recorded for a later pass.** If the DFA's Art. 11 survives to adoption in
substantially its drafted form, a permissive persistent-disclosure component will appear in this plane within
twelve months of adoption — because the duty falls on brands, who buy rather than build. **If none appears,
the disclosure layer is structurally proprietary**, like royalty accounting in music (cycle 8) and settlement
in rights reservation. `openpartner` at **18★** is the control variable: watch whether it crosses **100★ by
2027-06**.

---

## Compositing-floor recipes — added 2026-11-28 (pass 55)

Five patterns for roto, keying, matchmove and paint-out. Every repository named below was verified this pass
by `git ls-remote` (**51/51**) with its licence **read from the file**.

## Pattern 128 — The licence-clean roto bay (**the plane's only commercially shippable matte pipeline**)

**The problem.** A client wants AI-assisted rotoscoping. The obvious picks — MatAnyone (1,648★), MatAnyone 2
(959★) — are **S-Lab License 1.0, non-commercial**. RobustVideoMatting (9,649★, the most-starred matting
model) is **GPL-3.0**. Choose by stars and the engagement is undeliverable.

**The build, permissive end to end:**

1. **Prompt / select** — [`facebookresearch/sam2`](https://github.com/facebookresearch/sam2) **Apache-2.0**,
   20,248★. **Pin SAM 2, not SAM 3.** SAM 3 (12,419★) is the better model and ships under Meta's bespoke
   **"SAM License"** — non-OSI, with an Acceptable Use Policy, a litigation-termination clause, ITAR
   restrictions and a no-reverse-engineering covenant. If the client's counsel will sign off on SAM 3, use
   it; **the default must be SAM 2, because it is the only Apache-2.0 option at this quality.**
2. **Propagate through time** — [`hkchengrex/Cutie`](https://github.com/hkchengrex/Cutie) **MIT**, 1,135★,
   or [`hkchengrex/XMem`](https://github.com/hkchengrex/XMem) **MIT**, 1,997★. ⚠️ **Both dormant since
   November 2024** — budget maintenance, they are not abandoned-but-broken, they are frozen-and-working.
3. **Refine the edge** — [`hustvl/ViTMatte`](https://github.com/hustvl/ViTMatte) **MIT**, 574★ for
   trimap-based alpha, plus [`ZhengPeng7/BiRefNet`](https://github.com/ZhengPeng7/BiRefNet) **MIT**, 4,466★
   (pushed 2026-10-25) for high-resolution boundaries. These two carry the quality that MatAnyone would have
   given you, under licences you can actually ship.
4. **Stabilise with flow** — [`princeton-vl/RAFT`](https://github.com/princeton-vl/RAFT) **BSD-3-Clause**,
   4,131★ to damp inter-frame matte chatter.
5. **Deliver into the compositor** — wrap as an
   [`AcademySoftwareFoundation/openfx`](https://github.com/AcademySoftwareFoundation/openfx)
   **BSD-3-Clause** plugin emitting **alpha + Cryptomatte AOVs**. The OFX ABI is the boundary that lets your
   permissive node load into **Natron (GPL-2.0)** or **DaVinci Resolve (proprietary)** without either
   licence reaching your code.

**The design reference to copy and not depend on:**
[`lettidude/LiveActionAOV`](https://github.com/lettidude/LiveActionAOV) (**BSL 1.1**, 70★, pushed
**2026-11-27**) already draws the correct output boundary — plates in, **Nuke-ready AOVs and Cryptomatte
out**. BSL 1.1 grants free production use only to **individuals and organisations under 10 people**, so it
is free for a freelancer and **chargeable for a studio**. Study the interface; build your own.

**What you must tell the client:** this bay produces **mattes**, which is roto and keying. It does **not**
do paint-out — see Pattern 129, which is a different licence problem *and* a different regulatory problem.

## Pattern 129 — The paint-out decision gate (**one decision that answers both the licence and the regulator**)

**The insight this pass contributes.** Two independent boundaries — the commercial-licence boundary and the
EU AI Act Article 50 marking boundary — **fall in the same place** on the compositing floor. So classify the
operation **once**, and both answers follow.

| | **Roto / key / matte** | **Paint-out / clean plate / removal** |
|---|---|---|
| What it does to the plate | Isolates what was photographed | **Synthesises pixels never photographed** |
| Art. 50(2) "assistive function for standard editing"? | **Very likely yes → exempt** | **Very likely no → in scope** |
| Best open model | SAM 2 + ViTMatte + BiRefNet | ProPainter (7,106★) |
| Licence of that model | ✅ Apache-2.0 / MIT | ⛔ **S-Lab 1.0 — non-commercial** |
| Permissive fallback | — (none needed) | LaMa **Apache-2.0** 10,419★ / MMagic **Apache-2.0** 7,483★ — ⚠️ **still-image only, no temporal coherence, dormant since 2024/2025** |

**The gate, as a pipeline step:**

1. **Tag every shot operation** at task creation as `assistive` or `generative`, carried on the
   [`OpenTimelineIO`](https://github.com/AcademySoftwareFoundation/OpenTimelineIO) **Apache-2.0** clip
   metadata that already moves through the facility.
2. **Route `assistive` to Pattern 128.** No marking obligation, fully permissive stack, ship it.
3. **Route `generative` to a hard stop with three exits**, and make the client choose explicitly:
   - **Licence ProPainter commercially** — S-Lab clause 4 requires contacting the authors; the licence text
     names the contacts at NTU. A real, available path, and the honest recommendation when paint-out is
     central.
   - **Accept still-image quality** — LaMa/MMagic per-frame with manual temporal cleanup. Permissive, and
     worse; quantify the artist hours before proposing it.
   - **Keep paint-out human** — and sell the triage that decides which shots need it (Pattern 120's logic,
     applied here).
4. **For any `generative` shot that ships, emit the Article 50 marking** through the existing dual-mark
   provenance chain (**Pattern 8**) and the Article 50 disclosure chain (**Pattern 48**). Two machine-readable
   layers, per the Code of Practice of **2026-06-10**.
5. **Keep the classification as evidence.** The deliverable is not just marked frames — it is a per-shot
   record of *why* each operation was or was not marked. That record is what makes an over-marking dispute
   survivable.

⚠️ **State this caveat in writing to the client.** The Article 50(2) carve-out wording is corroborated
across multiple independent secondary sources, but **primary text was not read in this session**
(`artificialintelligenceact.eu` does not resolve under this session's network policy), and commentators
describe the **"substantially alter" threshold as deliberately fuzzy** pending Guidelines and case law.
**This gate is a defensible engineering default requiring legal sign-off, not a compliance guarantee.**

## Pattern 130 — The permissive matchmove spine (**swap the famous tracker for the shippable one**)

**The trap.** Matchmove's best-known learned components are all unusable commercially: **CoTracker**
(5,216★) is **CC BY-NC 4.0**; **DUSt3R** (7,396★) and **MASt3R** (3,182★) are **CC BY-NC-SA 4.0**; **VGGT**
(14,689★) ships under a bespoke **"VGGT License v1."** That is **~30,500★ of non-commercial code** sitting
exactly where a matchmove engineer would reach first.

**The spine that ships:**

| Step | Component | Licence | Stars |
|---|---|---|---|
| Feature match | [`cvg/Hierarchical-Localization`](https://github.com/cvg/Hierarchical-Localization) | **Apache-2.0** | 4,272 |
| Point tracking | [`google-deepmind/tapnet`](https://github.com/google-deepmind/tapnet) | **Apache-2.0** | 2,277 |
| Camera solve | [`colmap/colmap`](https://github.com/colmap/colmap) | **BSD-3-Clause** | 13,316 |
| Bundle adjustment | [`ceres-solver/ceres-solver`](https://github.com/ceres-solver/ceres-solver) | **BSD-3-Clause** | 4,616 |
| Alternative solve | [`openMVG/openMVG`](https://github.com/openMVG/openMVG) · [`mapillary/OpenSfM`](https://github.com/mapillary/OpenSfM) | **MPL-2.0** · **BSD-2-Clause** | 6,609 · 3,826 |
| Lens undistort | [`opencv/opencv`](https://github.com/opencv/opencv) `calib3d` + [`lensfun/lensfun`](https://github.com/lensfun/lensfun) profiles | **Apache-2.0** + **LGPL-3.0** | 91,749 · 898 |
| Set geometry | [`alicevision/Meshroom`](https://github.com/alicevision/Meshroom) | **MPL-2.0** (`COPYING.md`) | 13,118 |
| Depth prior | [`DepthAnything/Depth-Anything-V2`](https://github.com/DepthAnything/Depth-Anything-V2) | **Apache-2.0** | 9,244 |

**`tapnet` replaces CoTracker and that is the whole pattern.** Same job, **Apache-2.0**, pushed
**2026-11-02**, and **less than half the stars** — which is precisely why it gets passed over.

**Two licence rules that are not optional:**
- **`lensfun` is LGPL-3.0.** Link it dynamically as an external library; do not vendor or statically link it
  into a distributed binary. This is cycle 8's Chromaprint rule: **resolve the licence of what you link, not
  of the repo you cloned.**
- **`glomap`** (**BSD-3-Clause**, 2,346★) is faster global SfM than incremental COLMAP and is
  🗄️ **ARCHIVED (2026-01-30)**. Permissive and unmaintained. Use it only with a plan to own it.

**Hand off** the solved camera to **Blender's Motion Tracking workspace** (GPL — call it as a service from
an add-on, do not build your product inside it) or to the client's PFTrack/3DEqualizer seats via standard
camera export.

## Pattern 131 — The APAC up-stack offer (**sell what the disruptor's licence will not let them buy**)

**The situation, from `intel/market.md` pass 55.** >90% of Hollywood roto is attributed to India;† crews run
20–50 artists per feature;† FICCI-EY puts AI savings in roto/clean-up at **up to 40%** — a saving on the
exact hours an APAC vendor invoices. A services business cannot be sold 40% fewer billable hours.

**The asymmetry that makes this sellable, and it is this pass's own measurement.** A well-capitalised buyer
licenses or acquires the models (Netflix/InterPositive, announced **2026-03-05**). A mid-size APAC vendor
**cannot lawfully deploy the public state of the art at all** — S-Lab non-commercial on matting and
inpainting, CC BY-NC on CoTracker, bespoke licences on VGGT and SAM 3. **Open source does not level this
plane; it tilts it toward whoever can pay for a commercial grant.**

**So sell per-seat and per-system, never per-frame:**

1. **The licence-clean bay** (Pattern 128) as owned infrastructure — the vendor's own Apache/MIT stack,
   commercially shippable, not rented from a research lab.
2. **The paint-out gate** (Pattern 129) as a client-facing compliance artefact — it makes the vendor the
   party who can answer an EMEA client's Article 50 question about a VFX slate.
3. **The review-and-approval agent that still does not exist.** Pass 6 found no agent bridge for notes,
   versions and approvals; pass 55 re-measured the best candidate — [`dughogan/nuke_mcp`](https://github.com/dughogan/nuke_mcp),
   **40★, no licence file, last pushed 2025-11-03** — **unchanged in a year**. `OpenRV` (797★) and
   `xstudio` (782★) are both permissive and both still unbridged. This is the **most agent-shaped workflow
   in post and it is empty.**
4. **The margin story, explicitly.** Per-hour roto revenue is the thing under attack. Per-seat pipeline
   licensing, per-system integration and per-engagement compliance evidence are not. Lead with **margin
   architecture**, not tooling — pass 6's conclusion, now with a licence proof underneath it.

**Say the risk honestly:** no rotoscoping layoff or contract change tied to InterPositive has been reported,
and InterPositive's described product is **colour grading, relighting and continuity fixes** — **not roto**.
The threat is projected. Overstating it loses the room.

## Pattern 132 — The 20-minute licence gate for any roto, paint or matchmove proposal

Run before anyone scopes hours. Four commands, four questions.

1. **Does it exist?** `git ls-remote --exit-code -h https://github.com/<slug>`. The only existence oracle.
   `stuffmatic/fSpy` **resolves here while `search/repositories` returns 422** — a search 422 is **not**
   evidence of absence.
2. **What is the licence, read from the file?**
   `curl -s https://raw.githubusercontent.com/<slug>/{main,master}/{LICENSE,LICENSE.md,LICENSE.txt,license.txt,COPYING,COPYING.md}`
   — all six names, both branches. **`Meshroom`'s MPL-2.0 is in `COPYING.md`; `MatAnyone2`'s S-Lab is in
   `LICENSE.txt`.** Both read as "no licence" under a shorter probe. Then grep the text for
   **`non-commercial`** — that one word is the gate in this plane.
3. **Is it archived?** `gh api -X GET search/repositories -f q="repo:<slug>" --jq '.items[].archived'`.
   **In this plane the permissive options are disproportionately the archived ones** — `Sammie-Roto`
   (Apache-2.0), `Cutie-Roto` (MIT), `glomap` (BSD-3-Clause) are all archived. **Licence filter without
   archive check selects for abandonment here.**
4. **Does the search total hide a zero?** `planar tracking` = **131 results**, top hits academic SLAM from
   **2017** and a benchmark from **2022** — a **relevant zero** behind a plausible total. Read the results,
   never the count.

**The 20-minute output** is one line per component: *exists / licence as read / archived / commercially
usable yes-no*. Any `non-commercial`, `NC`, `BSL`, bespoke vendor licence or missing licence file is a
**hard stop requiring a named alternative** before the proposal goes out.

## ⛔ What not to promise in this plane (pass 55)

Carried in full in `intel/trends.md` pass 55. The six-line version:

1. **No** "open source AI paint-out" — the two leading video inpainters are non-commercial; the permissive
   fallbacks are still-image and dormant.
2. **No** open planar tracker. Mocha Pro has no open equivalent.
3. **No** despill — absent from this KB and from open source.
4. **No** California AB 2319 VFX rate — unstated in available analyses.
5. **No** claim that Netflix/InterPositive automates roto — it is described as grading, relighting and
   continuity.
6. **No** shortlisting by the GitHub SPDX field — it returns `NOASSERTION` for fourteen repositories in this
   plane, mixing safe BSD/MPL with explicitly non-commercial. **Read the file.**

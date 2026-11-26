---
industry: media
region: Global
updated: 2026-11-26
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

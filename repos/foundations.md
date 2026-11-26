---
industry: media
region: Global
updated: 2026-11-26
---

# 🏗️ Foundational Repos — Media & Entertainment

> The layer under the agents: codecs, timelines, colour, quality metrics, ASR, streaming.
> All rows verified 2026-11-21 (existence, stars, last push, license-file read where needed).
>
> **The finding that shapes this file:** in M&E the *permissive* open source is the **pipeline and
> standards layer** (Academy Software Foundation, Netflix, Apache-licensed players), while the
> *turnkey platform* layer is overwhelmingly copyleft. Build proprietary value here, and keep the
> copyleft platforms at arm's length (see `verticals/solutions.md`).

## Media industry standards — permissive, and the real differentiator

These are the repos that make a pipeline *broadcast-credible* rather than a demo. They have modest
star counts and are almost never on "top AI repo" lists, which is exactly why they are an advantage.

| Repo | License | Stars | Last push | Why it matters |
|---|---|---|---|---|
| [AcademySoftwareFoundation/OpenTimelineIO](https://github.com/AcademySoftwareFoundation/OpenTimelineIO) | Apache-2.0 | 2,105 | 2026-11-20 | The interchange format for editorial timelines (`.otio`). The clean handoff between an AI agent and a human editor in Premiere/Resolve/Avid. |
| [AcademySoftwareFoundation/OpenImageIO](https://github.com/AcademySoftwareFoundation/OpenImageIO) | Apache-2.0 | 2,405 | 2026-11-20 | Image I/O and processing used across VFX; `oiiotool` is the workhorse for frame pipelines. |
| [AcademySoftwareFoundation/OpenColorIO](https://github.com/AcademySoftwareFoundation/OpenColorIO) | BSD-3-Clause | 2,143 | 2026-10-01 | Colour management. Without it, generated frames will not match a show's look. |
| [AcademySoftwareFoundation/openexr](https://github.com/AcademySoftwareFoundation/openexr) | BSD-3-Clause | 1,888 | 2026-11-21 | HDR frame format for VFX//film finishing. |
| [Netflix/vmaf](https://github.com/Netflix/vmaf) | BSD-2-Clause-Patent | 5,609 | 2026-11-16 | Netflix's perceptual video quality metric. The objective gate for "is this AI-generated/re-encoded output good enough to ship." Licence read: BSD+Patent, with an express patent grant. |
| [Netflix/photon](https://github.com/Netflix/photon) | Apache-2.0 | 258 | 2026-11-20 | IMF (Interoperable Master Format) validation — the package format studios actually deliver in. 258 stars, and the only open implementation. |

## Core engines — generation, ASR, frames

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [yt-dlp/yt-dlp](https://github.com/yt-dlp/yt-dlp) | Unlicense | 209,447 | 2026-11-21 | Media acquisition for corpus building and monitoring. (Earlier cycles recorded ~96k stars; it is 209k.) |
| [Comfy-Org/ComfyUI](https://github.com/Comfy-Org/ComfyUI) | GPL-3.0 | 147,860 | 2026-11-21 | **Renamed from `comfyanonymous/ComfyUI`.** The node graph the whole generative-media ecosystem targets. GPL-3.0 → run as a service, don't embed. |
| [openai/whisper](https://github.com/openai/whisper) | MIT | 113,184 | 2026-08-31 | Reference ASR. Underpins every subtitling, dubbing and search workflow here. |
| [FFmpeg/FFmpeg](https://github.com/FFmpeg/FFmpeg) | LGPL-2.1+ (GPL parts) | 67,746 | 2026-11-21 | The substrate. License read: most files LGPL-2.1+, some components GPL — build flags decide your obligations, so pin them deliberately. |
| [ggml-org/whisper.cpp](https://github.com/ggml-org/whisper.cpp) | MIT | 55,377 | 2026-11-20 | Whisper in C/C++: on-prem and edge ASR with no cloud egress — the version that passes a broadcaster's security review. |
| [huggingface/diffusers](https://github.com/huggingface/diffusers) | Apache-2.0 | 34,961 | 2026-11-21 | Standard inference/training library for the image and video models in `agents/top.md`. |
| [invoke-ai/InvokeAI](https://github.com/invoke-ai/InvokeAI) | Apache-2.0 | 29,131 | 2026-11-21 | Apache-licensed creative engine with a real asset/workflow model — the permissive alternative to ComfyUI's GPL. |
| [m-bain/whisperX](https://github.com/m-bain/whisperX) | BSD-2-Clause | 25,547 | 2026-11-12 | Word-level timestamps + diarization. This, not raw Whisper, is what makes frame-accurate subtitles. |
| [pyannote/pyannote-audio](https://github.com/pyannote/pyannote-audio) | MIT | 10,831 | 2026-11-19 | Speaker diarization — **the dependency `whisperX` is built on, and missing from this KB until 2026-11-22.** "Who speaks when" is what makes multi-speaker dubbing and per-character subtitles possible. |
| [mltframework/mlt](https://github.com/mltframework/mlt) | **LGPL-2.1** | 1,883 | 2026-11-22 | The NLE engine under Shotcut and Kdenlive. **LGPL, not GPL** — alone among the open editing engines it can be *linked* from proprietary code, making it the permissive-enough backend for a custom editor. |
| [facebookresearch/demucs](https://github.com/facebookresearch/demucs) | MIT | 10,423 | 2024-04-24 | **ARCHIVED** but still the standard for **stem separation** (dialogue / music / effects). This is the step that lets a title be re-dubbed when the original M&E stems are lost — a very common archive problem. Vendor it. |
| [sigsep/open-unmix-pytorch](https://github.com/sigsep/open-unmix-pytorch) | MIT | 1,523 | 2024-06-17 | Reference academic stem separator. Dormant, MIT, reproducible — the citable baseline. |
| [apple-aiml-research/ml-stable-diffusion](https://github.com/apple-aiml-research/ml-stable-diffusion) | MIT | 17,962 | 2026-09-11 | **Renamed from `apple/ml-stable-diffusion`.** Core ML inference on Apple silicon — on-device generation. |
| [Zulko/moviepy](https://github.com/Zulko/moviepy) | MIT | 15,181 | 2026-08-26 | Programmatic editing in Python; the glue in most agent render steps. |
| [Breakthrough/PySceneDetect](https://github.com/Breakthrough/PySceneDetect) | BSD-3-Clause | 5,605 | 2026-11-21 | Shot-boundary detection — the first step of nearly every archive/clipping pipeline. |
| [jdepoix/youtube-transcript-api](https://github.com/jdepoix/youtube-transcript-api) | MIT | 8,643 | 2026-11-09 | Transcript ingestion without burning ASR compute. |

## Delivery & playback — permissive

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [ossrs/srs](https://github.com/ossrs/srs) | MIT | 29,445 | 2026-11-18 | Simple Realtime Server: RTMP/WebRTC/HLS/SRT. License file read — **MIT**, correcting web sources that list it as Apache-2.0. |
| [video-dev/hls.js](https://github.com/video-dev/hls.js) | Apache-2.0 | 17,062 | 2026-11-17 | HLS playback in the browser. License file read (the API reports `NOASSERTION`). |
| [shaka-project/shaka-player](https://github.com/shaka-project/shaka-player) | Apache-2.0 | 8,286 | 2026-11-20 | DASH/HLS player with DRM support — the permissive choice when content protection is in scope. |

## Provenance & watermarking — the gap this KB recorded is now closed

Until this pass, `intel/trends.md` called the absence of a permissive open watermarking library
"the clearest open-source gap in media today" and stated that SynthID was Google-internal. **Both
claims were wrong.** The family below is real, mostly MIT, and mostly active. All rows measured
2026-11-22; existence by `git ls-remote`.

| Repo | License | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| [facebookresearch/videoseal](https://github.com/facebookresearch/videoseal) | MIT | 828 | 111 | 2026-11-10 | **Video** watermarking — the embedder to standardize on. Models, training and eval code all MIT. Robust to re-encode and edits; strength is tunable against visibility. |
| [facebookresearch/audioseal](https://github.com/facebookresearch/audioseal) | MIT | 804 | 109 | 2026-11-03 | **Audio** watermarking with sample-level localized detection — identifies *which segments* are synthetic. Pairs with every TTS/dubbing step in Pattern 2. |
| [adobe/trustmark](https://github.com/adobe/trustmark) | **MIT** | 189 | 41 | 2026-11-11 | **Image** watermarking from Adobe Research; the soft-binding counterpart to C2PA's manifests. License file read — the 1,218-byte LICENSE begins "Copyright 2023 Adobe All Rights Reserved" and then grants MIT. |
| [google-deepmind/synthid-text](https://github.com/google-deepmind/synthid-text) | Apache-2.0 | 1,258 | 117 | 2026-11-18 | **Text** watermarking, genuinely open. Scope matters: SynthID for image/video/audio is *not* released, so the accurate line is "SynthID-Text is open, SynthID for AV is not." |
| [ShieldMnt/invisible-watermark](https://github.com/ShieldMnt/invisible-watermark) | MIT | 1,993 | 177 | 2023-09-23 | DWT-DCT embedder that Stable Diffusion ships by default — the most *deployed* of these, and dormant since 2023. Vendor it; expect no fixes. |
| [contentauth/c2pa-rs](https://github.com/contentauth/c2pa-rs) | **MIT OR Apache-2.0** | 453 | 208 | 2026-11-21 | Reference C2PA implementation. Dual license re-confirmed this pass by reading both `LICENSE-MIT` (1,083 B) and `LICENSE-APACHE` (11,335 B). 208 forks — real adoption. |
| [contentauth/c2patool](https://github.com/contentauth/c2patool) | Apache-2.0 | 174 | 47 | 2026-11-20 | CLI for signing and inspecting manifests. Adds provenance to an existing pipeline without writing Rust. |
| [contentauth/c2pa-python](https://github.com/contentauth/c2pa-python) | Apache-2.0 | 110 | 41 | 2026-11-18 | Python binding — the practical entry point from an ML pipeline. |
| [c2pa-org/specifications](https://github.com/c2pa-org/specifications) | CC-BY-4.0 | 215 | 35 | 2026-11-16 | The normative spec. Cite this, not a vendor blog, when a client asks what C2PA requires. |
| [facebookresearch/watermark-anything](https://github.com/facebookresearch/watermark-anything) | MIT | 1,133 | 56 | 2025-06-20 | **ARCHIVED.** Localized multi-mark image watermarking; superseded by VideoSeal for new work. |
| [DAI-Lab/RivaGAN](https://github.com/DAI-Lab/RivaGAN) | MIT | 324 | 44 | 2021-10-12 | Early robust video watermarking. Dormant 5 years; lineage only. |

### The constraint that must travel with every provenance pitch

Measured this pass: **watermark-*removal* repos total 42,896 stars across six projects against 4,138
across the five embedders — a 10.4× asymmetry**, and three of the six removers were pushed within
three weeks of measurement. `guillaumemeyer/watermarks-remover` alone (MIT, 28,124★, 3,162 forks) is
34× VideoSeal, and `froggeric/gemini-watermark-and-synthid-remover` (MIT, 132★) names a specific
scheme in its title. Full table and slugs in `repos/trending.md` under 2026-11-22.

So the correct engineering position is **dual marking plus detection-side verification**, never "the
asset is watermarked, therefore it is safe": a C2PA manifest (strippable by re-encode), a
VideoSeal/AudioSeal payload (attackable, by better-resourced open tooling), and a verification
service the client runs at ingest. Provenance is a probabilistic chain of custody. Pattern 8 in
`compose/patterns.md` wires this up.

## Broadcast device control & newsroom integration — the Sofie libraries

The other gap this KB recorded as absolute ("no open MOS-protocol implementation exists at all") is
closed by the same project. **Sofie** was commissioned by **NRK**, the Norwegian public broadcaster,
as an open replacement for Vizrt Mosart, presented at EBU's open-source conference, and has run
daily live news at NRK, the BBC and TV 2 Norway since 2018. The platform itself is in
`verticals/solutions.md`; these are the libraries worth reusing on their own. The org renamed
`nrkno/*` → `Sofie-Automation/*`.

| Repo | License | Stars | Forks | ★/fork | Last push | Role |
|---|---|---|---|---|---|---|
| [Sofie-Automation/sofie-mos-connection](https://github.com/Sofie-Automation/sofie-mos-connection) | MIT | 29 | 18 | **1.6** | 2026-10-07 | **MOS Protocol v2.8.4** client/server in Node — talks to Newsroom Computer Systems (iNEWS, ENPS, Octopus) and MOS devices. The repo whose non-existence this KB previously asserted. |
| [Sofie-Automation/sofie-timeline-state-resolver](https://github.com/Sofie-Automation/sofie-timeline-state-resolver) | MIT | 25 | 25 | **1.0** | 2026-11-12 | Typed device abstraction: declare desired state on a timeline, it diffs and drives the hardware. Covers ATEM, CasparCG, Lawo, HyperDeck, Quantel, Kairos, OBS, vMix and more behind one interface. |
| [Sofie-Automation/sofie-atem-connection](https://github.com/Sofie-Automation/sofie-atem-connection) | MIT | 158 | 50 | 3.2 | 2026-11-20 | Blackmagic ATEM vision-mixer protocol — the most independently reused of these. |
| [Sofie-Automation/sisyfos-audio-controller](https://github.com/Sofie-Automation/sisyfos-audio-controller) | **MIT** | 45 | 21 | 2.1 | 2026-11-14 | Audio-mixer control. API reports `NOASSERTION`; the 1,297-byte LICENSE is MIT, copyright **TV 2 Denmark** with NRK contributions — two national broadcasters co-maintaining one library. |
| [Sofie-Automation/sofie-package-manager](https://github.com/Sofie-Automation/sofie-package-manager) | MIT | 6 | 8 | **0.75** | 2026-11-16 | Media ingest, transfer and transcode orchestration with progress reporting. |
| [Sofie-Automation/sofie-hyperdeck-connection](https://github.com/Sofie-Automation/sofie-hyperdeck-connection) | MIT | 6 | 8 | **0.75** | 2026-07-20 | HyperDeck record/playback control. |
| [Sofie-Automation/sofie-input-gateway](https://github.com/Sofie-Automation/sofie-input-gateway) | MIT | 0 | 5 | **0.0** | 2026-10-08 | Physical control surfaces: Stream Deck, X-keys, MIDI. |
| [Sofie-Automation/sofie-atem-state](https://github.com/Sofie-Automation/sofie-atem-state) | MIT | 12 | 5 | 2.4 | 2026-11-20 | ATEM state diffing, used by the resolver. |
| [Sofie-Automation/sofie-casparcg-launcher](https://github.com/Sofie-Automation/sofie-casparcg-launcher) | MIT | 28 | 10 | 2.8 | 2026-08-06 | Supervises/restarts CasparCG graphics servers. |
| [Sofie-Automation/sofie-quantel-gateway](https://github.com/Sofie-Automation/sofie-quantel-gateway) | GPL-2.0 | 3 | 3 | 1.0 | 2026-03-20 | Quantel bridge — **the single copyleft component** in an otherwise MIT stack. Separate process. |
| [CasparCG/server](https://github.com/CasparCG/server) | GPL-3.0 | 1,112 | 329 | 3.4 | 2026-11-11 | The graphics/playout server Sofie drives, from SVT (Swedish public broadcaster). GPL-3.0, used over its own protocol — which is how Sofie uses it. |
| [ebu/awesome-broadcasting](https://github.com/ebu/awesome-broadcasting) | CC0-1.0 | 1,803 | 238 | 7.6 | 2026-09-30 | **The EBU's own public-domain index of open broadcast tooling.** Institutional rather than a listicle, and the place Sofie and ffplayout are catalogued. Start discovery here, not on GitHub search. |

**Read the ★/fork column before judging these by stars.** `sofie-timeline-state-resolver` sits at
25★/25f, `sofie-package-manager` and `sofie-hyperdeck-connection` have *more forks than stars*, and
`sofie-input-gateway` is 0★/5f. Deployed broadcast infrastructure gets forked and configured, not
starred. Zero stars with five forks is not abandonment — it is a library whose entire audience is
broadcast engineers who run it in a gallery.

## The monetization plane — ad signalling, auction and measurement

New on 2026-11-22 (second pass of the day). Until this section the KB described how to **make**,
**deliver** and **prove** media, and said nothing about how to **sell against it** — while
`intel/market.md` carried $9.1B of AI video advertising and named advertising as *the* primary driver
of LATAM media growth. Measured across all eight files before this pass: `prebid` 0 hits, `scte` 0,
`ssai` 0, `openrtb` 0, `ad server` 0. The gap was total, and it sat directly under the KB's own
revenue numbers.

Stars/forks/`pushed_at` come from one `search/repositories` call; existence from `git ls-remote`;
licenses were read from the LICENSE file directly. That last step is not ceremony here: GitHub's
detector returns `NOASSERTION` for **both** Video.js repos and `NONE` for four others that do carry
terms, so an API-only pass would have mislabelled six of the rows below.

### Auction — the only layer of this plane that is permissive, canonical and active

| Repo | License | Stars | Forks | ★/fork | Last push | Role |
|---|---|---|---|---|---|---|
| [prebid/Prebid.js](https://github.com/prebid/Prebid.js) | Apache-2.0 | 1,619 | 2,437 | **0.66** | 2026-11-22 | The de-facto client-side header-bidding library. Publisher runs one auction across many demand partners before the ad call. Pushed the day this was written. |
| [prebid/prebid-server](https://github.com/prebid/prebid-server) | Apache-2.0 | 595 | 983 | **0.61** | 2026-11-22 | Server-side auction in Go. This is the component that makes **server-side ad insertion** possible without handing the auction to a vendor. |
| [prebid/prebid-server-java](https://github.com/prebid/prebid-server-java) | Apache-2.0 | 110 | 264 | **0.42** | 2026-11-20 | The JVM implementation of the same spec — the realistic choice inside a broadcaster whose stack is already Java. |

**Read the ★/fork column before judging these by stars.** All three Prebid repos have **more forks
than stars** — the same signature this file already documented for the Sofie libraries. It means the
same thing: nobody stars their ad stack, they fork it and add their own bidder adapters. 1,619 stars
on Prebid.js understates it by an order of magnitude; 2,437 forks is the real number, and it is the
largest fork count of any repo in this KB outside the core engines.

### Ad signalling (SCTE-35) — permissive, tiny, and the weakest link in the chain

SCTE-35 is the cue standard that marks where an ad break starts and stops inside a transport stream.
It is the exact hinge between a broadcaster's playout and an ad auction, and it is the most
poorly-maintained layer in this KB.

| Repo | License | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| [Comcast/scte35-js](https://github.com/Comcast/scte35-js) | Apache-2.0 | 51 | 23 | 2026-05-21 | SCTE-35 cue parser in TypeScript, from Comcast. **The only maintained option** — start here, not at `threefive`. |
| [futzu/threefive](https://github.com/futzu/threefive) | MIT | 164 | 30 | 2024-11-27 | The best-known Python SCTE-35 parser and the one every tutorial points to. **Dormant for two years.** Licence caveat: the LICENSE file is the full MIT grant, but its copyright line still reads "The Python Packaging Authority" — a packaging-template leftover, not a second licensor. MIT holds; the attribution line is wrong. |
| [futzu/x9k3](https://github.com/futzu/x9k3) | MIT *(declared, not licensed)* | — | — | 2024-07-10 | HLS segmenter that cuts segments on SCTE-35 cues. **Has no LICENSE file at all**: MIT appears only as a `setup.py` classifier. It is also absent from GitHub's search index, so `git ls-remote` is the only proof it is live. Do not put this in a client deliverable without getting the licence in writing. |

**This is the finding, and it is a build opportunity rather than a warning.** The three repos that
stand between a broadcaster's ad cues and a Prebid auction are 51★, 164★ and one with no licence
file, and two of the three have been untouched since 2024. The auction layer above them was pushed
today; the measurement layer below them is maintained by the Apache Software Foundation. The hinge is
the only dormant part, and the hinge is also the smallest codebase — a few thousand lines of cue
parsing. Cheap to adopt, cheap to maintain, and whoever maintains it owns the integration point.

### Playback — where the ad is actually rendered

| Repo | License | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| [videojs/video.js](https://github.com/videojs/video.js) | Apache-2.0 *(LICENSE read; API says `NOASSERTION`)* | 40,233 | 7,504 | 2026-11-22 | The most-deployed open web player. Already in `verticals/solutions.md` as a player; listed here for its ad surface. |
| [shaka-project/shaka-player](https://github.com/shaka-project/shaka-player) | Apache-2.0 | 8,285 | 1,629 | 2026-11-22 | Google's DASH/HLS player. The DRM-and-ads path most CTV work ends up on. |
| [openplayerjs/openplayerjs](https://github.com/openplayerjs/openplayerjs) | MIT | 650 | 92 | 2026-11-16 | The one **MIT** player here, and the only one whose ads plugin handles **SSAI with SCTE-35 boundaries surfaced as TextTrack cues** — i.e. it can detect a stitched ad break client-side. Small but precisely on target. |
| [videojs/videojs-contrib-ads](https://github.com/videojs/videojs-contrib-ads) | Apache-2.0 *(LICENSE read; API says `NOASSERTION`)* | 396 | 252 | 2024-05-17 | The ad-plugin toolkit for Video.js. **Dormant since mid-2024** — note the 396★/252f ratio: heavily forked relative to stars, so the forks are where any current work lives. |

### FAST channel assembly — EMEA-origin, and the layer LATAM is buying

FAST (free ad-supported streaming TV) is where the ad-supported money actually is in LATAM, where
Brazil is the world's #3 FAST market by revenue. Both maintained open components come from **Eyevinn
(Sweden)** — a genuinely EMEA-origin entry in a KB whose repos are otherwise US- and China-origin.

| Repo | License | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| [Eyevinn/channel-engine](https://github.com/Eyevinn/channel-engine) | Apache-2.0 | 134 | 34 | 2026-11-06 | Assembles a **linear FAST channel from VOD assets**, with ad-break signalling. This is the core of a FAST build and it is Apache-2.0. |
| [Eyevinn/hls-vodtolive](https://github.com/Eyevinn/hls-vodtolive) | MIT *(package.json; **no LICENSE file**, API reports `NONE`)* | 46 | 12 | 2026-10-26 | The library `channel-engine` is built on: converts HLS VOD into a live window. Get the licence confirmed in writing before shipping — the declaration exists only in `package.json`. |

### Consent and the wire formats

| Repo | License | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| [orestbida/cookieconsent](https://github.com/orestbida/cookieconsent) | MIT | 5,779 | 505 | 2026-11-22 | Lightweight, dependency-free consent UI. The practical MIT starting point for the GDPR/LGPD banner layer. |
| [InteractiveAdvertisingBureau/openrtb](https://github.com/InteractiveAdvertisingBureau/openrtb) | **CC BY 3.0** (per README) | 530 | 218 | 2026-11-11 | The OpenRTB bid-request spec. **Specification, not code.** |
| [InteractiveAdvertisingBureau/AdCOM](https://github.com/InteractiveAdvertisingBureau/AdCOM) | **CC BY 3.0** (per README) | 142 | 85 | 2026-10-29 | The ad-object model OpenRTB 3.0 carries. Spec, not code. |
| [InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework) | **CC BY 3.0** (per README) | 954 | 370 | 2026-08-07 | The TCF consent-string spec — the EMEA-specific obligation in this plane. Spec, not code. |

**All three IAB repos report `NONE` to GitHub's licence detector and carry CC BY 3.0 in the README
instead.** CC BY is a *documentation* licence: it lets you implement the spec, it does not give you
code, and it is not interchangeable with Apache-2.0 in a bid response. Four of the "repos" in this
plane are documents.

### Measurement — Apache-2.0, boring, and the strongest part of the stack

| Repo | License | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| [apache/superset](https://github.com/apache/superset) | Apache-2.0 | 75,621 | 18,632 | 2026-11-22 | The reporting surface an ad-sales team actually logs into. |
| [apache/druid](https://github.com/apache/druid) | Apache-2.0 | 14,099 | 3,821 | 2026-11-21 | Real-time OLAP built for exactly this shape of data: high-cardinality impression and bid events, sub-second slice-and-dice. |
| [apache/pinot](https://github.com/apache/pinot) | Apache-2.0 | 6,178 | 1,536 | 2026-11-22 | The same job as Druid with lower query latency; the two are genuine alternatives, not a stack. |
| [snowplow/snowplow](https://github.com/snowplow/snowplow) | Apache-2.0 | 7,051 | 1,170 | 2026-10-19 | Event collection and enrichment you own end-to-end — the permissive answer to "we need first-party audience data" that `intel/market.md` identifies as the fragmented capability. |

Deloitte's 2026 outlook says media firms **lack a unified view of their audiences, and that this is
what hampers monetization.** That is a data-engineering problem with four Apache-2.0 answers already
in the list above, which makes it the lowest-risk, highest-certainty engagement in this entire plane.

## The accessibility & caption plane — the typed layer under a statutory duty

Added 2026-11-22 (pass 3). This plane behaves like the ad plane this KB mapped in pass 2 — permissive
at the edges, hollow in the middle — but with one difference that matters commercially: **the
deadlines are set by law, not by a client's roadmap.** Existence verified with `git ls-remote`;
licences read from the LICENSE file; `last push` from a blobless shallow clone.

### Interchange & rendering — permissive and active

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [sandflow/ttconv](https://github.com/sandflow/ttconv) | BSD-2-Clause | 242 | 2026-11-21 | Format spine of the plane: STL ↔ SRT ↔ TTML ↔ SCC ↔ WebVTT. EBU-STL (broadcast) in, IMSC/WebVTT (web) out — the conversion every hybrid broadcaster needs and few do correctly. |
| [sandflow/imscJS](https://github.com/sandflow/imscJS) | BSD-2-Clause | 92 | 2026-11-20 | Reference renderer for IMSC Text and Image Profile → HTML5. Use it to prove what a caption file will *look* like before it ships. |
| [w3c/imsc-tests](https://github.com/w3c/imsc-tests) | W3C Test Suite License **or** W3C BSD-3-Clause (dual; take BSD-3 to adapt) | 18 | 2026-10-22 | The IMSC conformance corpus. A caption QC gate that cites this suite is defensible to a regulator; one built on in-house samples is not. |
| [ableplayer/ableplayer](https://github.com/ableplayer/ableplayer) | MIT | 837 | 2026-11-20 | Accessible HTML5 player carrying audio description and sign-language tracks natively. The player-UI half of the EAA duty. |
| [Dash-Industry-Forum/dash.js](https://github.com/Dash-Industry-Forum/dash.js) | BSD-3-Clause | — | 2026-11-22 | DASH reference player; accessibility track selection and rendering. |

### Caption carriage out of broadcast — active, and copyleft

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [CCExtractor/ccextractor](https://github.com/CCExtractor/ccextractor) | **GPL-2.0** | 919 | 2026-11-11 | Extracts CEA-608/708 from transport streams, MP4 and more. There is **no permissive equivalent** — so the GPL boundary is architectural, not a preference: wrap it as a CLI/sidecar process. Consumer AI captioning tools do not produce CEA-608/708 at all, which is exactly why this repo still matters. |

### Conformance — BSD-licensed, and the weakest link in the chain

| Repo | License | Stars | Last push | Status |
|---|---|---|---|---|
| [sandflow/imscHRM](https://github.com/sandflow/imscHRM) | BSD-2-Clause | 10 | 2024-05-16 | **Dormant ~920 days.** Validates the IMSC Hypothetical Render Model — the constraint that decides whether a subtitle document can actually be rendered in real time on constrained hardware. |
| [ebu/ebu-tt-live-toolkit](https://github.com/ebu/ebu-tt-live-toolkit) | BSD-3-Clause | 27 | 2021-12-21 | **Abandoned ~5 years.** Reference implementation of EBU-TT Live, the European live-subtitle contribution spec. The EAA made live subtitling a legal duty in June 2025; its reference toolkit stopped in December 2021. |

This is the same failure mode this KB recorded for SCTE-35 in the ad plane: the spec is public and
permissive, the production tooling is one dormant repo. The difference is that here a regulator, not
an ad buyer, asks for the evidence.

### Alignment & timing — the quality layer

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [jianfch/stable-ts](https://github.com/jianfch/stable-ts) | MIT | 2,300 | 2026-05-30 | Whisper plus reliable word-level timestamps and forced alignment. Caption *timing* compliance, not just text. |
| [baxtree/subaligner](https://github.com/baxtree/subaligner) | MIT | 509 | 2026-11-02 | Re-synchronizes drifted subtitle files against audio. The single most common real-world caption defect. |
| [SubtitleEdit/subtitleedit](https://github.com/SubtitleEdit/subtitleedit) | MIT | 15,100 | 2026-11-22 | 300+ formats, Whisper built in, the human review step every compliance workflow needs. MIT — verified, against the widespread claim that it is GPL. |

> Already catalogued elsewhere in this KB and part of this plane: `openai/whisper` and
> `ggml-org/whisper.cpp` (ASR), `m-bain/whisperX` (diarized alignment), `pyannote/pyannote-audio`
> (speaker turns, which is what distinguishes a *good* caption from a correct one),
> `Netflix/photon` (IMF, which carries caption/AD assets), `shaka-project/shaka-player` and
> `videojs/video.js` (playback). Not re-listed here.

## The conformance & preservation plane — measured 2026-11-22 (pass 4)

Pass 4 of the same day. Before writing a line, this plane was **measured at zero across all eight
files at `HEAD`**: `mediainfo`, `mediaconch`, `ebur128`, `R128`, `BS.1770`, `CALM`, `archivematica`,
`bagit`, `qctools`, `FFV1`, `Matroska`, `OAIS` and `preservation` each returned **no match in any
file in this KB**. This is not a refresh of existing rows — it is a layer the KB did not have.

Three facts govern everything below, and all three were established by reading bytes, not metadata:

1. **GitHub's license field is wrong on six repos in this plane.** Not "imprecise" — wrong.
2. **A license can hide in three different places.** A plain `LICENSE` file is only the first.
3. **This plane has a mature permissive tool layer and no agent layer at all.** Measured, in
   `agents/top.md`, not assumed.

### Where a license actually lives — three channels, and GitHub only reads one

This is the generalizable channel finding of the pass, and it applies to all twelve industries.

| Channel | Example | What GitHub's API reports | What the bytes say |
|---|---|---|---|
| Plain `LICENSE` / `COPYING` file | `openpreserve/fido` → `LICENSE.txt` (615 B) | `NOASSERTION` | Apache-2.0 |
| **An HTML file** — `License.html` | `bavc/qctools`, `MediaArea/MediaConch` | `NOASSERTION` / `NONE` | GPL-3.0 / GPLv3+ **and** MPLv2+ |
| **Packaging metadata only** — no license file exists | `LibraryOfCongress/bagit-python` → `pyproject.toml` classifier | `NONE` | `License :: Public Domain` |

Practical rule, added to this KB's channel notes: when the license field reads `NOASSERTION` or
`NONE`, probing plain filenames is **not sufficient**. Search the repo for `filename:LICENSE` (which
finds `License.html`), and if that is empty, read the packaging manifest. Three of the rows below
would have been recorded with the wrong license by a plain-name probe alone.

### Conformance & technical QC — permissive at the metadata layer, copyleft at the checker

| Repo | License | Stars / forks | Last push | What it is |
|---|---|---|---|---|
| [MediaArea/MediaInfo](https://github.com/MediaArea/MediaInfo) | BSD-2-Clause | 2075★ / 203f | 2026-11-19 | The de-facto standard technical-metadata reader for audiovisual files. Permissive, active, embeddable. |
| [MediaArea/MediaInfoLib](https://github.com/MediaArea/MediaInfoLib) | BSD-2-Clause | 806★ / 229f | 2026-11-22 | The library under MediaInfo. This is the one you link against; 229 forks against 806 stars (ratio 3.5) says it is deployed, not admired. |
| [MediaArea/RAWcooked](https://github.com/MediaArea/RAWcooked) | BSD-2-Clause | 50★ / 13f | 2026-11-22 | Lossless RAW image sequence → FFV1 in Matroska, reversibly. The film-scan preservation workhorse. |
| [MediaArea/MediaConch](https://github.com/MediaArea/MediaConch) | **GPLv3+ *or* MPLv2+ (dual)** — in `SourceCode/License.html` | 35★ / 10f | **2021-09-29** | Conformance checker for Matroska / FFV1 / LPCM. See the two warnings below — both matter commercially. |
| [bavc/qctools](https://github.com/bavc/qctools) | **GPL-3.0**, in `License.html`; the GUI part and the FFmpeg statistics filter are additionally BSD | 389★ / 44f | 2026-11-15 | Visual QC analysis for video — the tool archivists actually use to find tape and transfer defects. |
| [amiaopensource/vrecord](https://github.com/amiaopensource/vrecord) | **CC-BY-4.0** — a *content* license on software | 206★ / 55f | 2026-11-01 | Analog/VHS capture to preservation-grade targets. Widely used; see the licensing caveat below. |

**Two warnings on MediaConch, and they point in opposite directions.**

- *The good news nobody states:* it is **dual-licensed GPLv3+ / MPLv2+**. Every listicle records it as
  "GPL" and stops. The MPL-2.0 option is file-level copyleft, which means **MediaConch can be linked
  into a proprietary or client-owned product** — you keep modifications to MediaConch's own files
  open and nothing else. For a deliverable that must ship inside a client's closed system, this is
  the difference between usable and unusable, and it is invisible in GitHub's UI.
- *The bad news:* the repository **has not been pushed since 2021-09-29**, and carries 35 stars
  against 72 refs. The canonical open conformance checker is effectively dormant. Its own license
  file also records that several bundled libraries and `libcurl`/`zlib` support are **disabled
  pending consent of the PREFORMA Consortium** — a licensing condition written into the project by
  the EU programme that funded it. Budget for carrying it yourself if a client build depends on it.

**The `vrecord` licensing trap.** `vrecord` is published under **CC-BY-4.0**, a Creative Commons
*content* license applied to executable code. Creative Commons itself advises against using CC
licenses for software: CC-BY grants copyright permission but says nothing about patents and has no
source-disclosure or warranty-disclaimer structure built for code. It is permissive in spirit and
ambiguous in practice. Use it as a *documented procedure* to reimplement; do not vendor it into a
client deliverable and call the licensing settled. Same shape as the `NOASSERTION` traps earlier
cycles found, one level further out: here the license is real, correctly stated, and **the wrong
instrument for the artefact**.

### Loudness — the regulated measurement, and the permissive implementation is tiny

Loudness is the cleanest example in media of this KB's standing rule that regulators **mandate the
artefact and are silent on the method** (see `intel/trends.md` T18). Every region sets a target in
LUFS/LKFS; not one specifies the code that measures it.

| Repo | License | Stars / forks | Last push | What it is |
|---|---|---|---|---|
| [csteinmetz1/pyloudnorm](https://github.com/csteinmetz1/pyloudnorm) | MIT | 796★ / 71f | 2026-01-04 | ITU-R BS.1770 loudness meter and normalization in Python. The fastest path to a measured number in a pipeline. |
| [jiixyj/libebur128](https://github.com/jiixyj/libebur128) | MIT | 498★ / 94f | 2026-11-20 | The canonical C implementation of EBU R128 / ITU-R BS.1770. 94 forks on 498 stars (ratio 5.3) — this is the one that ships inside other products. |
| [librosa/librosa](https://github.com/librosa/librosa) | ISC | 9106★ / 1149f | 2026-11-22 | General audio analysis. ISC is a permissive BSD-equivalent — safe, and often misrecorded as MIT. |
| [MTG/essentia](https://github.com/MTG/essentia) | **AGPL-3.0** | 3814★ / 646f | 2026-11-18 | Audio feature extraction at scale. AGPL reaches across a network boundary — if it sits behind a client's API, the obligation follows. A commercial license exists; it is not open source. |
| [bbc/peaks.js](https://github.com/bbc/peaks.js) | **LGPL-3.0** | 3413★ / 292f | 2026-10-21 | BBC waveform visualization UI. LGPL is workable for a linked front-end component; it is not MIT, and vendor roundups routinely say it is. |

**The asymmetry worth pricing.** The entire permissive loudness layer is two small MIT repos —
`libebur128` (498★) and `pyloudnorm` (796★) — sitting under a duty that applies to effectively every
broadcaster and, as of July 2026 in the US, to streaming distribution as well. The measurement is
solved and free; the **compliance workflow around it is not open source anywhere**. That is the
build, and it is a small build on a large obligation.

### Preservation & repository — OAIS, and the one Apache-2.0 platform

| Repo | License | Stars / forks | Last push | What it is |
|---|---|---|---|---|
| [fcrepo/fcrepo](https://github.com/fcrepo/fcrepo) | **Apache-2.0** | 255★ / 138f | 2026-11-20 | Fedora repository core. **The only permissively-licensed platform in this tier** — 138 forks on 255 stars (ratio 1.8) is an infrastructure signature, not a promotion signature. |
| [artefactual/archivematica](https://github.com/artefactual/archivematica) | **AGPL-3.0** | 527★ / 136f | 2026-11-21 | The reference OAIS-conformant preservation system. AGPL, so it is a system you deploy and integrate, not code you absorb. |
| [archivesspace/archivesspace](https://github.com/archivesspace/archivesspace) | **ECL-2.0**, in `COPYING` (747 B) | 449★ / 255f | 2026-11-20 | Archival description and access. ECL-2.0 is Apache-2.0 with a narrowed patent grant for academic contributors — OSI-approved and permissive; almost no tool recognizes the identifier. |
| [openpreserve/jhove](https://github.com/openpreserve/jhove) | **LGPL-2.1-or-later**, in `LICENSE` (879 B) | 204★ / 86f | 2026-09-16 | Format validation (JSTOR/Harvard, now Open Preservation Foundation). Its own license file misspells "Lesser" as "Lessor" — a reminder that these strings are written by humans and should be read, not matched. |
| [openpreserve/fido](https://github.com/openpreserve/fido) | **Apache-2.0**, in `LICENSE.txt` (615 B) | 160★ / 49f | 2026-11-18 | Format identification against the PRONOM registry. Permissive, active, and reported as `NOASSERTION` by GitHub. |
| [Islandora/islandora](https://github.com/Islandora/islandora) | **GPL-2.0** (`LICENSE`, 18091 B) | *stars unavailable* — refs=1659 | — | Drupal + Fedora repository front end. **`search/repositories` returns nothing for this slug while `ls-remote` returns 1659 refs** — the false-negative pattern this KB has now measured five times. Existence is `ls-remote`. |
| [LibraryOfCongress/bagit-python](https://github.com/LibraryOfCongress/bagit-python) | **Public Domain** — declared *only* in the `pyproject.toml` classifier; **there is no license file** | 276★ / 101f | 2026-06-18 | Reference implementation of BagIt, the packaging format for archival transfer. Public domain is the least encumbered status available; it is also the easiest to miss. |

### The AI layer over the archive — already permissive, already proven

Nothing in this subsection is new to the world; what is new is that this KB had no row connecting it
to the preservation tier. These two are what turn a preserved archive into a searchable one.

| Repo | License | Stars / forks | Last push | Role in this plane |
|---|---|---|---|---|
| [facebookresearch/faiss](https://github.com/facebookresearch/faiss) | MIT | 41857★ / 4661f | 2026-11-22 | Vector index for archive retrieval at collection scale. |
| [mlfoundations/open_clip](https://github.com/mlfoundations/open_clip) | MIT (`LICENSE`, 1228 B) | 14281★ / 1345f | 2026-11-21 | Open visual-text embeddings — the shot-level search layer over footage with no usable metadata. Reported `NOASSERTION`; the bytes say MIT. |

### Documents, not code — demoted on sight

This KB's T13 rule (four "repos" in the ad plane were documents) applies again. Both of these are
real, useful and **not software**; carrying them as tooling rows would be the padding this KB refuses.

| Repo | License | Stars | What it actually is |
|---|---|---|---|
| [usnationalarchives/digital-preservation](https://github.com/usnationalarchives/digital-preservation) | Public Domain (`LICENSE.md`, 1335 B) | 245★ / 22f, **refs=2** | NARA's preservation *policy and strategy documents*. A federal-agency primary source — cite it, do not `pip install` it. |
| [digipres/awesome-digital-preservation](https://github.com/digipres/awesome-digital-preservation) | CC0-1.0 | 151★ / 15f | An awesome-list. Excellent starting index, zero executable content. |

## The identification & rights-reservation plane — measured 2026-11-22 (pass 5)

This is the plane that answers *"which asset is this, and who may train on it?"* Before this pass the
word **`fingerprint` did not appear anywhere in this KB** — a structural hole, because content
identification is the substrate under royalty attribution, ad verification, takedown, archive
dedupe and every AI-training-rights claim a client will make this year.

All rows below: existence by `git ls-remote`, licence by fetching the licence file and counting its
bytes. **30/30 URLs resolved.** Star/fork counts measured 2026-11-22 via one `search/repositories`
call each — not inherited from any listicle.

### Audio fingerprinting — permissive at the edges, copyleft in the active middle

| Repo | License (verified) | Stars / forks | Last push | Notes |
|---|---|---|---|---|
| [acoustid/chromaprint](https://github.com/acoustid/chromaprint) | ⚠️ **LGPL-2.1 as a whole** (`LICENSE.md`, 1800 B) | 1,432★ / 180f | 2026-10-15 | The industry-standard audio fingerprinter; generates the codes behind AcoustID/MusicBrainz. **Read the licence note below — this is not an MIT repo.** |
| [beetbox/pyacoustid](https://github.com/beetbox/pyacoustid) | MIT (`LICENSE`, 1080 B) | 413★ / 71f | 2026-05-19 | Python bindings to Chromaprint + the AcoustID web service. The clean way in. |
| [worldveil/dejavu](https://github.com/worldveil/dejavu) | MIT (`LICENSE.md`, 1070 B) | 6,789★ / 1,463f | 2024-04-22 | The most-starred permissive fingerprinter. Ratio 4.6 — genuinely deployed. **Dormant ~2.5 years**; vendor it. |
| [dpwe/audfprint](https://github.com/dpwe/audfprint) | MIT (`LICENSE`, 1112 B) | 622★ / 136f | 2019-09-24 | Landmark-based matching from Dan Ellis (Columbia/Google). Reference-grade algorithm, **unmaintained since 2019**. |
| [adblockradio/stream-audio-fingerprint](https://github.com/adblockradio/stream-audio-fingerprint) | MPL-2.0 (`LICENSE`, 16722 B) | 781★ / 65f | 2021-11-05 | **Real-time** matching against a live stream — built to detect ad breaks on radio. The only repo here designed for broadcast ingest. Weak copyleft: file-level, linkable. |
| [JorenSix/Olaf](https://github.com/JorenSix/Olaf) | AGPL-3.0 (`LICENSE`, 32386 B) | 426★ / 48f | 2026-10-16 | Embedded/C fingerprinter, runs on microcontrollers and in-browser. **Actively maintained — and AGPL.** |
| [JorenSix/Panako](https://github.com/JorenSix/Panako) | AGPL-3.0 (`license.txt`, 32385 B) | 276★ / 53f | 2026-09-17 | Pitch/time-scale **invariant** matching — survives the speed-ups broadcasters apply. Academic pedigree (`paper.md` in-tree). **AGPL.** |

**The pattern this table shows, and it is the commercially important one:** the two *actively
maintained* fingerprinters are **AGPL-3.0**, and the three *permissive* ones have not been touched
since 2019–2024. A client who wants permissive audio fingerprinting is choosing between vendoring
dead MIT code and accepting AGPL obligations on a service. There is **no actively maintained
permissive audio fingerprinter.** That is a precise, buildable gap.

### ⚠️ Chromaprint's licence is decided by your build flags — a category this KB had not met

`chromaprint`'s `LICENSE.md` states it plainly, and the GitHub API reports `NOASSERTION` *because*
of it:

> *"Chromaprint's own source code is licensed under the MIT license, but we include some parts of the
> FFmpeg library, which is licensed under the LGPL 2.1 license. As a whole, Chromaprint should be
> therefore considered to be licensed under the LGPL 2.1 license."*

And then a **third** layer: *"when distributing Chromaprint in binary form, you should also take into
consideration the license of the external FFT library that you compile Chromaprint with."*

So the licence of the shipped artefact is a function of **which FFT library the build links** —
FFmpeg (LGPL-2.1), FFTW3 (**GPL-2.0+**, and the commercial-licence route exists precisely because of
this), or KissFFT (BSD-3). Build with FFTW3 and a redistributed binary is arguably **GPL**.

This is a new category for this KB. T22 recorded that a licence can live in an HTML file or a
packaging classifier; this is worse — **the licence is not a property of the repository at all, it is
a property of the compile.** No SPDX field, SBOM scan of the source tree, or GitHub licence badge can
capture it. CI rule, generalisable to all twelve industries: *for any native dependency, resolve the
licence of the **linked** libraries, not the repository.*

### Standards-based content codes — the ISO identifier with an Apache-2.0 implementation

| Repo | License (verified) | Stars / forks | Last push | Notes |
|---|---|---|---|---|
| [iscc/iscc-core](https://github.com/iscc/iscc-core) | Apache-2.0 (`LICENSE`, 11345 B) | 26★ / 6f | 2026-10-17 | Reference implementation of **ISO 24138:2024** — the International Standard Content Code. Similarity-preserving, content-derived codes for text, image, audio, video, mixed. |
| [iscc/iscc-sdk](https://github.com/iscc/iscc-sdk) | Apache-2.0 (`LICENSE`, 11339 B) | 24★ / 8f | 2026-10-26 | The batteries-included layer (media extraction + code generation). The practical entry point. |
| [iscc/iscc-lib](https://github.com/iscc/iscc-lib) | Apache-2.0 | 2★ / 1f | 2026-11-22 | Pushed the day of this pass — the Rust/multi-language rewrite. Early. |
| [iscc/iscc-web](https://github.com/iscc/iscc-web) | Apache-2.0 | 9★ / 4f | 2026-11-09 | HTTP service wrapper. Useful as a deployment template. |
| [iscc/iscc-codes](https://github.com/iscc/iscc-codes) | **CC-BY-4.0** | 53★ / 8f | 2026-11-11 | ⚠️ **Documents, not code** — the specification text. T13 rule: cite it, do not depend on it. |

**Why this matters more than 26 stars suggests.** ISCC is a *published ISO standard* (ISO 24138:2024,
first edition, 2024-05 — **no 2026 revision exists**; checked, because an invented version number is
exactly the error this KB has been punished for). It is designed to complement, not replace, DOI,
ISBN, **ISAN, ISRC, ISSN and ISWC**. And unlike all of those, **its reference implementation is
Apache-2.0 and free to use.**

The honest reading is a two-sided one, and a proposal must carry both sides: ISCC is the only
content identifier in media whose implementation Globant can build on without a licence negotiation
— *and* a 26-star reference implementation is evidence that the industry has not adopted it. It is a
**standards-backed bet, not an installed base.** Pitch it as the internal join key, never as the
identifier a client's partners will already recognise.

### The incumbent identifiers have no open implementation at all — measured, not assumed

Queries run and shortened per this KB's rule (*a plausible query returning 0 is a query that is too
long, until proven otherwise*):

- **EIDR** (the audiovisual registry — the ID that actually moves between studios and distributors):
  `eidr` → **160 results, not one of them an EIDR implementation.** Every hit is a false friend
  (national eID card readers, an unrelated `eidra-agent`, an epidemiology tagger). There is **no
  open-source EIDR client.**
- **ISAN** (ISO 15706, audiovisual works): `isan` → **1,942 results, zero relevant** — all NLP
  libraries (`isanlp`) and unrelated projects. **No open ISAN tooling.**
- **ISRC / ISWC**: no implementation repo; these are registry allocations, not computable artefacts.

These are **informed gaps, not silence.** The reason is structural and is the same law this KB found
in healthcare for CPT codes: *an identifier issued by a registry under membership terms cannot have a
useful open implementation, because the scarce thing is the allocation, not the parser.*

### Rights-format carriers — DDEX lives, CWR died

| Repo | License (verified) | Stars / forks | Last push | Notes |
|---|---|---|---|---|
| [miqwit/dedex](https://github.com/miqwit/dedex) | MIT (`LICENSE`, 1063 B) | 30★ / 15f | 2026-11-02 | **DDEX ERN** (Electronic Release Notification) parser. Ratio 2.0 — forked by people who deploy it. Small but the only live permissive DDEX code found. |
| [wavbee/ddex-ern-validate](https://github.com/wavbee/ddex-ern-validate) | MIT | 0★ / 0f | 2026-08-03 | Listed for completeness and **not recommended**: zero stars, zero forks. Read it, don't depend on it. |
| [weso/CWR-Validator](https://github.com/weso/CWR-Validator) | MIT (`LICENSE`, 1070 B) | 16★ / 7f | **2015-07-31** | **CWR** (Common Works Registration — how publishers register songs with societies). Untouched for **11 years**. |
| [aporia-records/APORIA-Works-Registration](https://github.com/aporia-records/APORIA-Works-Registration) | GPL-3.0 (`LICENSE`, 35140 B) | 16★ / 6f | 2018-09-06 | The only other CWR implementation. Also dead. |

**The contrast is the finding.** DDEX ERN — the *delivery* format, implemented by anyone shipping
audio to a store — has live permissive code. **CWR — the *rights registration* format — has two
implementations and both have been dead for 7–11 years.** Delivery is a format problem and attracts
open source; rights registration sits behind CISAC society membership, so the open layer starved.
Same law, visible inside a single industry.

⚠️ **Channel limitation, recorded rather than glossed:** `new.ddex.net` **does not resolve from this
session** (outside the allowed network domains), so **DDEX's membership fees and implementer-licence
terms are UNVERIFIED in this pass.** What search results did indicate — and what must be confirmed
against the primary source before it reaches a client: DDEX is a not-for-profit standards body
(20th anniversary in 2026) whose standards require a licence to implement, and it is **developing a
rights-reservation message for AI training opt-outs**. Treat the commercial terms as *unresearched,
not free*. Never assume a standards body's spec is royalty-free because its parser is MIT.

### AI rights reservation — the declaration layer is real, the honouring layer is abandoned

| Repo | License (verified) | Stars / forks | Last push | Notes |
|---|---|---|---|---|
| [ai-robots-txt/ai.robots.txt](https://github.com/ai-robots-txt/ai.robots.txt) | MIT (`LICENSE`, 1069 B) | 4,265★ / 206f | **2026-11-22** | The de-facto AI-crawler blocklist, with generated `robots.txt`/nginx/Caddy artefacts. Pushed the day of this pass — this list is maintained *daily*. |
| [w3c-cg/tdm-reservation-protocol](https://github.com/w3c-cg/tdm-reservation-protocol) | ⚠️ **W3C Software and Document License** (`LICENSE.md`, 432 B) | 17★ / 14f | 2026-09-03 | **TDMRep** — the machine-readable opt-out the EU DSM Directive's Art. 4 reservation depends on. Ratio **1.2** — forks ≈ stars, this KB's signature of real infrastructure. Not an OSI-style permissive licence; read it before vendoring. |
| [rslstandard/rsl](https://github.com/rslstandard/rsl) | ⛔ **NO LICENCE FILE** (checked `master`+`main`, 11 filenames) | 47★ / 1f | 2026-03-31 | The official repo of **RSL 1.0** — the licensing standard Reddit, Yahoo, Medium, Quora and Ziff Davis have endorsed. See the warning below. |
| [jeffpaul/rsl-wp](https://github.com/jeffpaul/rsl-wp) | ⛔ **NO LICENCE FILE** | 35★ / 1f | 2026-11-03 | WordPress plugin emitting RSL terms. Active, unlicensed. |
| [onurkanbakirci/rsl-editor](https://github.com/onurkanbakirci/rsl-editor) | MIT (`LICENSE.md`, 1070 B) | 22★ / 1f | 2026-02-16 | An RSL term editor, and **the only properly licensed RSL tool found.** |
| [Spawning-Inc/datadiligence](https://github.com/Spawning-Inc/datadiligence) | MIT (`LICENSE.txt`, 1079 B) | 41★ / 5f | **2024-10-09** | The library for *honouring* opt-outs on the training side. **Dormant 2+ years.** |

**⛔ The sharpest licence trap in this KB: the rights-reservation standard is itself unlicensed.**
`rslstandard/rsl` — the repository of the standard whose entire purpose is to let publishers state
machine-readable terms for reuse — **ships no licence file at all.** Neither does the WordPress
plugin that implements it. Without a licence grant, default copyright applies: *all rights
reserved*. A client cannot safely vendor the schema, and an agent that generated RSL documents from
that repo's code would be building a compliance product on an unlicensed dependency. Use the spec as
published at `rslstandard.org`, use `rsl-editor` (MIT) for code, and raise this in any
rights-reservation engagement. **This is a defect in the standard's packaging, not a reason to ignore
RSL** — the backers are real and the direction of travel is clear.

**The asymmetry is the opportunity.** The tooling to *declare* a reservation was updated the day of
this pass (`ai.robots.txt`, 2026-11-22). The tooling to *honour* one has been untouched since
October 2024 (`datadiligence`). Publishers are tooled to say no; nobody maintains the code that
listens. And the settlement layer below it is empty — `pay-per-crawl` returns 33 results whose top
six hold **5, 2, 2, 0, 0 and 0 stars.** Declaration is a format problem (solved, permissive);
honouring and settlement are judgment problems (empty). **Fifth consecutive confirmation** of this
KB's structural law.

### Catalogue & metadata — copyleft at the platform, with one MIT exception

| Repo | License (verified) | Stars / forks | Last push | Notes |
|---|---|---|---|---|
| [beetbox/beets](https://github.com/beetbox/beets) | **MIT** (`LICENSE`, 1079 B) | 15,972★ / 2,207f | 2026-11-22 | Music catalogue manager with a real plugin API, MusicBrainz lookup and `chromaprint` fingerprinting built in. **The MIT exception at the platform tier** (cf. T10). The single best starting point in this plane. |
| [metabrainz/musicbrainz-server](https://github.com/metabrainz/musicbrainz-server) | **GPL-2.0-or-later** (`COPYING.md`, with `leaflet` under BSD-2) | 1,114★ / 347f | 2026-11-19 | The open music metadata encyclopedia. The *database* is the asset; the server is copyleft. |
| [metabrainz/picard](https://github.com/metabrainz/picard) | GPL-2.0 (`COPYING.txt`, 17983 B) | 5,398★ / 479f | 2026-11-19 | The reference tagger — AcoustID fingerprint → MusicBrainz identity. The working proof of the ID→metadata join. |
| [metabrainz/listenbrainz-server](https://github.com/metabrainz/listenbrainz-server) | GPL-2.0 (`LICENSE`, 18205 B) | 1,077★ / 402f | 2026-11-22 | Open listening-history and recommendation data. Ratio 2.7 — deployed. |
| [MTG/essentia](https://github.com/MTG/essentia) | AGPL-3.0 (`COPYING.txt`, 31772 B) | 3,814★ / 646f | 2026-11-18 | Already in this file. Restated here because it is also the audio-ID feature extractor. |
| [librosa/librosa](https://github.com/librosa/librosa) | ISC (`LICENSE.md`, 765 B) | 9,106★ / 1,149f | 2026-11-22 | Already in this file. The permissive feature-extraction floor under any custom fingerprinter. |

**`beets` is the row to act on.** MIT, 15,972★, ratio 7.2, pushed the day of this pass, and it
already wires fingerprint → identity → tagged catalogue. For an archive or catalogue engagement it
removes months of plumbing, and unlike the MetaBrainz servers it carries **no copyleft obligation on
a derived product.**

### Visual / generic hashing

| Repo | License (verified) | Stars / forks | Last push | Notes |
|---|---|---|---|---|
| [akamhy/videohash](https://github.com/akamhy/videohash) | MIT (`LICENSE`, 1075 B) | 388★ / 65f | 2024-07-12 | Perceptual video hashing — near-duplicate detection across re-encodes. **Dormant since 2024**; small enough to vendor and own. |

For scene-level work this pairs with `PySceneDetect` (BSD-3) already listed above: segment, then hash
per segment, rather than hashing whole files.

### Rights *enforcement* — one Apache-2.0 reference server

| Repo | License (verified) | Stars / forks | Last push | Notes |
|---|---|---|---|---|
| [awslabs/speke-reference-server](https://github.com/awslabs/speke-reference-server) | Apache-2.0 (`LICENSE`, 11357 B) | 123★ / 50f | 2026-09-08 | **SPEKE** (Secure Packager and Encoder Key Exchange) reference server — the standard interface between a packager and a DRM key provider. Ratio **2.5** = real deployment. |

Note what it is and is not: SPEKE standardises *key exchange*. The DRM systems it feeds (Widevine,
PlayReady, FairPlay) are **proprietary and licensed per-device** — no open implementation exists or
can. Same shape as the identifier registries: the **interface** is open, the **entitlement** is not.

### Audio watermarking — the identification sibling, permissive and crowded

| Repo | License (verified) | Stars / forks | Last push | Notes |
|---|---|---|---|---|
| [facebookresearch/audioseal](https://github.com/facebookresearch/audioseal) | MIT | 804★ / 109f | 2026-11-03 | Already in this KB. Localised detection — finds *which seconds* were AI-generated. |
| [resemble-ai/Perth](https://github.com/resemble-ai/Perth) | MIT (`LICENSE`, 1067 B) | 546★ / 51f | 2026-09-02 | **New to this KB.** Perceptual-threshold watermarker, built for robustness across re-encoding. |
| [wavmark/wavmark](https://github.com/wavmark/wavmark) | ⚠️ MIT **template, unfilled** (`LICENSE`, 1068 B — reads `Copyright (c) [year] [fullname]`) | 323★ / 44f | 2024-01-07 | **New to this KB.** AI-based watermarking with ~1s payload resolution. The licence is an **unexecuted MIT template** — the grant is almost certainly intended but the copyright holder is not named. Minor, real, and worth a one-line note in a legal review. |
| [swesterfeld/audiowmark](https://github.com/swesterfeld/audiowmark) | GPL-3.0 (`COPYING`, 35148 B) | 604★ / 119f | 2026-09-23 | **New to this KB.** The broadcast-grade option (robust to MP3/AAC, used by radio); **copyleft**, so service-side only. |

**And the counter-signal, measured again:** `wiltodelta/remove-ai-watermarks` (Apache-2.0,
**6,483★ / 600f**, pushed **2026-11-22**) has more stars than every watermarking repo in this table
*combined*. T8 recorded this asymmetry; it has **widened**, and it was re-measured today rather than
re-asserted. Any provenance pitch must assume the removal tool is better maintained and more popular
than the marking tool.

### Method correction from this pass — the licence probe was wrong, and it mattered

`JorenSix/Panako` initially returned **404 from `raw.githubusercontent.com` for every path tried,
including a commit-pinned one** — which looked like a repo whose licence could not be read. It was
not. The licence is at **`license.txt`, all lower-case**, and the readme is `README.textile`, not
`README.md`. The probe list used by earlier cycles (`LICENSE`, `LICENSE.md`, `LICENSE.txt`, `COPYING`,
`LICENCE`, `License`, `license.md`, …) **omits the all-lower-case `license.txt`**, and the earlier
`COPYING.md` omission is what made `musicbrainz-server` look unlicensed too.

Two durable rules for all twelve industries:

1. **Add `license.txt`, `license`, `COPYING.md` and `Licence.txt` to the probe list.** Paths are
   case-sensitive and older projects favour lower-case.
2. **If `README.md` also 404s, the repo is not missing files — your filename guesses are wrong.**
   A failing control request proves throttling; a *passing* control plus a 404 proves a naming
   convention. In that case **shallow-clone and look**, which is cheap and conclusive. A 404 from
   the raw channel is never by itself evidence that a licence is absent.

## The production & post-production plane — measured 2026-11-25 (pass 6)

The layer *above* the codecs and *below* the delivery stack: scene description, colour, timelines,
asset resolution, render management and camera metadata. Before this pass none of
`usd`, `materialx`, `opencue`, `openvdb`, `render farm`, `animation` or `color grading` appeared
anywhere in this KB.

**This is the healthiest substrate in this entire knowledge base, and it is the one honest
counterexample to this file's "permissive at the pipeline, copyleft at the platform" summary — the
pipeline half is not merely permissive, it is permissive, canonical, vendor-neutral, foundation-
governed and pushed daily.** Twenty-two repos over 100★ in one organisation, of which **20 are
Apache-2.0 or BSD-3-Clause** — the only two exceptions being `openexr-images` (`NOASSERTION`, an
image corpus) and `tac` (CC-BY-4.0, governance documents), i.e. **every code project in the
foundation above 100★ is permissive.** Fifteen were pushed within nine days of this pass.

### The Academy Software Foundation core — Apache-2.0 / BSD-3, and active this week

Verified 2026-11-25: existence by `git ls-remote` (**35/35 resolved** across this pass), stars /
forks / `pushed_at` / SPDX from `search/repositories`.

| Repo | Licence | Stars / forks | Last push | What it is |
|---|---|---|---|---|
| [openvdb](https://github.com/AcademySoftwareFoundation/openvdb) | Apache-2.0 | 3,556★ / 807f | 2026-11-25 | Sparse volume data structure and tools — the standard for volumetrics |
| [OpenImageIO](https://github.com/AcademySoftwareFoundation/OpenImageIO) | Apache-2.0 | 2,407★ / 727f | 2026-11-25 | Format-agnostic image read/write/process API aimed at VFX |
| [OpenShadingLanguage](https://github.com/AcademySoftwareFoundation/OpenShadingLanguage) | BSD-3-Clause | 2,351★ / 422f | 2026-11-25 | Shading language for production GI renderers |
| [MaterialX](https://github.com/AcademySoftwareFoundation/MaterialX) | Apache-2.0 | 2,315★ / 472f | 2026-11-23 | Open standard for exchanging material and look-dev content |
| [OpenColorIO](https://github.com/AcademySoftwareFoundation/OpenColorIO) | BSD-3-Clause | 2,145★ / 513f | 2026-10-01 | Colour management framework for VFX and animation |
| [OpenTimelineIO](https://github.com/AcademySoftwareFoundation/OpenTimelineIO) | Apache-2.0 | 2,117★ / 366f | 2026-11-25 | **API and interchange format for editorial timeline information** — the spine of Patterns 17–19 |
| [openexr](https://github.com/AcademySoftwareFoundation/openexr) | BSD-3-Clause | 1,890★ / 721f | 2026-11-25 | The EXR spec and reference implementation — the industry's image storage format |
| [rez](https://github.com/AcademySoftwareFoundation/rez) | Apache-2.0 | 1,101★ / 369f | 2026-11-25 | Package configuration, build and deployment — how studios pin an environment |
| [OpenCue](https://github.com/AcademySoftwareFoundation/OpenCue) | Apache-2.0 | 1,010★ / 273f | 2026-11-23 | **Render management system** for VFX and animation (Sony Imageworks / Google origin) |
| [OpenPBR](https://github.com/AcademySoftwareFoundation/OpenPBR) | Apache-2.0 | 845★ / 48f | 2026-11-16 | Spec + reference implementation of the OpenPBR Surface shading model |
| [OpenRV](https://github.com/AcademySoftwareFoundation/OpenRV) | ⚠️ Apache-2.0 **except** components in `Notice.txt` | 797★ / 258f | 2026-11-25 | Sci-Tech-award media review and playback (the open RV) |
| [xstudio](https://github.com/AcademySoftwareFoundation/xstudio) | Apache-2.0 | 782★ / 135f | 2026-11-20 | Playback and review application for post, VFX and animation |
| [openfx](https://github.com/AcademySoftwareFoundation/openfx) | BSD-3-Clause | 592★ / 160f | 2026-11-11 | The OpenFX plug-in effects API |
| [Imath](https://github.com/AcademySoftwareFoundation/Imath) | BSD-3-Clause | 495★ / 166f | 2026-11-13 | 2D/3D vector and matrix maths for graphics |
| [OpenColorIO-Config-ACES](https://github.com/AcademySoftwareFoundation/OpenColorIO-Config-ACES) | BSD-3-Clause | 440★ / 53f | 2026-10-27 | The ACES configuration generator for OCIO |
| [openapv](https://github.com/AcademySoftwareFoundation/openapv) | BSD-3-Clause | 273★ / 50f | 2026-11-10 | OpenAPV — professional-grade intra-frame codec implementation |
| [rawtoaces](https://github.com/AcademySoftwareFoundation/rawtoaces) | Apache-2.0 | 197★ / 66f | 2026-11-24 | Camera RAW → ACES conversion utility |
| [aswf-landscape](https://github.com/AcademySoftwareFoundation/aswf-landscape) | Apache-2.0 | 153★ / 31f | 2026-11-23 | CNCF-style interactive landscape of motion-picture open source — **use it as a map, it is data not code** |
| [openqmc](https://github.com/AcademySoftwareFoundation/openqmc) | Apache-2.0 | 107★ / 8f | 2026-11-23 | Quasi-Monte-Carlo sampling library for renderers |

### ⚠️ OpenUSD is not Apache-2.0 — a fourth way a licence hides

| Repo | Licence (read this pass) | Stars / forks | Last push |
|---|---|---|---|
| [PixarAnimationStudios/OpenUSD](https://github.com/PixarAnimationStudios/OpenUSD) | ⚠️ **Tomorrow Open Source Technology License 1.0** (`LICENSE.txt`, master, 49,827 B) | 7,675★ / 1,486f | 2026-11-23 |

Its own preamble states the delta: *"the Tomorrow Open Source Technology License 1.0 differs from the
original Apache License 2.0 in the following manner. Section 6 ('Trademarks') is different."*

**So: functionally Apache-2.0 with a modified trademark clause, but a separate, renamed licence.** The
GitHub API reports `NOASSERTION`; no SPDX field, badge or SBOM scan of the source tree will tell a
client what it actually is. Four distinct hiding places are now recorded in this file: a non-standard
filename, a licence owned by the *compile* (Chromaprint), an HTML file or packaging classifier, and
now **a renamed fork of a standard licence whose only delta is trademarks.** Also note **OpenRV**
above: Apache-2.0 *except as otherwise required by the specific licences of components*, enumerated
in `Notice.txt` — the Chromaprint lesson again, in a repo a client will absolutely want.

### Asset resolution — the layer that makes a pipeline addressable, and it is all permissive

| Repo | Licence | Stars / forks | Last push | Role |
|---|---|---|---|---|
| [OpenAssetIO/OpenAssetIO](https://github.com/OpenAssetIO/OpenAssetIO) | Apache-2.0 | 353★ / 50f | 2026-11-25 | **Interoperability standard between tools and content-management systems in media production** |
| [LucaScheller/VFX-UsdAssetResolver](https://github.com/LucaScheller/VFX-UsdAssetResolver) | Apache-2.0 | 141★ / 28f | 2026-05-24 | USD asset-resolver reference implementations — the practical entry point |
| [OpenAssetIO/usdOpenAssetIOResolver](https://github.com/OpenAssetIO/usdOpenAssetIOResolver) | Apache-2.0 | 28★ / 5f | 2026-11-02 | AR2 plug-in hosting OpenAssetIO — joins USD resolution to the asset standard |
| [OpenAssetIO/OpenAssetIO-MediaCreation](https://github.com/OpenAssetIO/OpenAssetIO-MediaCreation) | Apache-2.0 | 16★ / 12f | 2026-11-23 | The media-creation trait set |
| [OpenAssetIO/OpenAssetIO-Manager-BAL](https://github.com/OpenAssetIO/OpenAssetIO-Manager-BAL) | Apache-2.0 | 9★ / 9f | 2026-11-23 | Basic Asset Library — the reference manager to develop against |
| [OpenAssetIO/OpenAssetIO-TraitGen](https://github.com/OpenAssetIO/OpenAssetIO-TraitGen) | Apache-2.0 | 7★ / 7f | 2026-11-23 | Trait code generation |
| [OpenAssetIO/otio-openassetio](https://github.com/OpenAssetIO/otio-openassetio) | Apache-2.0 | 10★ / 2f | 2024-07-26 | **OTIO ↔ OpenAssetIO bridge. Dormant since 2024-07** — and it is precisely the join Pattern 17 needs. |

**The gap in one sentence a proposal can use:** the asset-resolution layer is Apache-2.0 end to end,
maintained this week at the core, and the *two* repos that connect it to anything else — `otio-openassetio`
(10★, dormant 16 months) and `OpenAssetIO-ComfyUI` (2★, dormant 14 months) — are the smallest and
stalest in the set. The standard is healthy; the connectors are orphaned.

### Render management — permissive at the incumbent, copyleft at both challengers

| Repo | Licence | Stars / forks | Last push | Note |
|---|---|---|---|---|
| [AcademySoftwareFoundation/OpenCue](https://github.com/AcademySoftwareFoundation/OpenCue) | **Apache-2.0** | 1,010★ / 273f | 2026-11-23 | The incumbent, foundation-governed, and the only permissive option at this tier |
| [CGRU/cgru](https://github.com/CGRU/cgru) | LGPL-3.0 | 302★ / 117f | 2026-10-18 | CGRU / AFANASY — long-lived independent render manager |
| [uberware/sqi](https://github.com/uberware/sqi) | **AGPL-3.0** | 44★ / 1f | **2026-11-25** | New distributed task/render manager "built for modern production pipelines". Pushed the day of this pass. |

**Worth noting as a trend, not an anecdote:** the 2026 entrant at this tier chose **AGPL-3.0**, and
the other independent is LGPL-3.0. The orchestration tier is behaving like this KB's *platform* tier,
not its *pipeline* tier — and OpenCue's Apache-2.0 is a foundation artefact, not a market norm. Build
on OpenCue and the licence position is clean; build on `sqi` and a hosted render service is a network
-copyleft question.

### Virtual production & camera metadata — tiny, permissive, and standards-backed

| Repo | Licence | Stars / forks | Last push | Note |
|---|---|---|---|---|
| [SMPTE/ris-osvp-metadata-camdkit](https://github.com/SMPTE/ris-osvp-metadata-camdkit) | BSD-3-Clause | 55★ / 17f | 2026-07-31 | **Reference implementation of the SMPTE RIS OSVP camera metadata model** — the OpenTrackIO substrate |
| [mosys/opentrackio-cpp](https://github.com/mosys/opentrackio-cpp) | MIT | 15★ / 12f | 2026-07-23 | C++ OpenTrackIO implementation from a tracking vendor. Fork ratio 1.25 = being integrated, not starred |
| [unitycoder/Unity.OpenTrackIO](https://github.com/unitycoder/Unity.OpenTrackIO) | MIT | 1★ | 2026-05-04 | Unity receiver — minimal, but it exists |

`opentrackio` returns **8 results total** and four are real and permissively licensed. Compare
`virtual production` (1,291 results, near-total contamination — see `agents/top.md`). **The standard
name is the query; the marketing phrase is noise.** Per vendor documentation, Unreal Engine has
supported OpenTrackIO officially since **5.6**, and a camera vendor states support across its
cine line as of February 2026 — both carried at **vendor-documentation confidence**, not verified
against SMPTE primary text (`www.gov.uk` and `www.linuxfoundation.org` do not resolve from this
session; SMPTE's own repos do, and are the rows above).

### Node graphs and DCCs — context rows, not recommendations

| Repo | Licence | Stars / forks | Last push | Note |
|---|---|---|---|---|
| [GafferHQ/gaffer](https://github.com/GafferHQ/gaffer) | BSD-3-Clause | 1,116★ / 227f | 2026-11-25 | Node-based look-dev, lighting **and automation** — the permissive place to put pipeline logic |
| [blender/blender](https://github.com/blender/blender) | ⚠️ `NOASSERTION` (GPL family; this is the GitHub mirror) | 22,543★ / 3,679f | 2026-11-25 | Context for the 35,788★ MCP bridge above. Canonical development is **not** on GitHub |

### Documents, not code — demoted on sight (the rule from pass 4 holds)

- [cgwire/awesome-cg-vfx-pipeline](https://github.com/cgwire/awesome-cg-vfx-pipeline) — 1,286★ /
  185f, pushed 2026-11-16, licence **CC-BY-SA-3.0** (`LICENSE`, master, 21,581 B, read this pass). It
  is the best *map* of this plane that exists and it is a **link list**. High stars, zero code. Use it
  for discovery; never cite it as tooling.
- [AcademySoftwareFoundation/aswf-landscape](https://github.com/AcademySoftwareFoundation/aswf-landscape)
  — 153★, Apache-2.0, is likewise a landscape/data project, not a library.

*Still genuinely missing in this plane: an agent bridge for review-and-approval (`OpenRV` and
`xstudio` are both permissive, active and unexposed), a licensed Nuke bridge, and a maintained
`otio-openassetio`. See `agents/top.md` pass 6 and `compose/patterns.md` Pattern 17.*

## The audience & measurement plane — measured 2026-11-25 (pass 7)

The demand side: **recommend the next item, model what media did, resolve who the viewer is, and count
the audience as a tradeable currency.** Pass 2 covered the supply side of monetization (auction,
SCTE-35, SSAI, Druid/Pinot). This section is what the KB was missing on the other side, and it supplies
the recommender layer that `compose/patterns.md` Pattern 10 had been pointing at since 2026-11-22
without it existing.

**The headline, and it is the most precisely measured statement of this KB's structural law so far.**
Three steps inside one plane, each one a strictly harder *observation* problem, and the open-source
health collapses monotonically along it:

| Step | What it needs to observe | Open-source health (measured 2026-11-25) |
|---|---|---|
| **Recommend the next item** | only your own first-party log | **Strong** — 22,012★ MIT, pushed this month |
| **Model what the media did** | your spend + outcomes, no panel | **Strong** — 1,616★ and 1,540★, both pushed within 15 days |
| **Count the audience as currency** | a nationally representative panel you cannot own | **Zero** — see the measured void below |

The scarce thing is **not the algorithm and not the data licence — it is the right to observe.** A
currency is a legally constituted observation right (JIC certification, MRC accreditation) plus a
~$110M/year operating cost, not a library. Sixth confirmation of this KB's law, and the first time the
law has a **price** attached from a named primary source. See `intel/market.md` North America.

### Recommenders — the healthiest permissive layer in this KB, and it was entirely absent until now

| Repo | Licence | Stars | Forks | Last push | Notes |
|---|---|---|---|---|---|
| [recommenders-team/recommenders](https://github.com/recommenders-team/recommenders) | **MIT** | 22,012 | 3,336 | 2026-11-05 | Linux Foundation project (ex-Microsoft). Best-practice implementations end to end: data prep, 30+ algorithms, evaluation, operationalization. **The default starting point.** |
| [gorse-io/gorse](https://github.com/gorse-io/gorse) | **Apache-2.0** | 9,928 | 931 | 2026-11-25 | Go recommender *service* — REST/gRPC, not a notebook library. Pushed on measurement day. The one component in this plane that is deployable as-is. |
| [NicolasHug/Surprise](https://github.com/NicolasHug/Surprise) | **BSD-3-Clause** | 6,828 | 1,054 | 2026-05-30 | Classic explicit-rating toolkit. Good for baselines and teaching; not a serving path. |
| [RUCAIBox/RecBole](https://github.com/RUCAIBox/RecBole) | **MIT** | 4,623 | 755 | 2026-11-23 | 90+ algorithms on a unified benchmark. **The right tool for "prove model B beats model A"** before committing a client to one. |
| [benfred/implicit](https://github.com/benfred/implicit) | **MIT** | 3,842 | 640 | 2026-05-08 | Fast ALS/BPR for implicit feedback — the realistic case for a streamer (plays, not ratings). GPU-capable. |
| [meta-pytorch/torchrec](https://github.com/meta-pytorch/torchrec) | **BSD-3-Clause** | 2,630 | 751 | 2026-11-25 | Production-scale sharded embeddings for very large catalogues. Pushed on measurement day. |
| [NVIDIA-Merlin/Transformers4Rec](https://github.com/NVIDIA-Merlin/Transformers4Rec) | **Apache-2.0** | 1,283 | 168 | 2026-08-23 | Sequential/session-based recommendation — **the shape that matches a viewing session**, which matters more in media than in retail. |
| [NVIDIA-Merlin/Merlin](https://github.com/NVIDIA-Merlin/Merlin) | **Apache-2.0** | 913 | 132 | 2026-07-22 | The umbrella for NVIDIA's recommender stack (NVTabular, Systems). Useful as an integration reference. |
| [massquantity/LibRecommender](https://github.com/massquantity/LibRecommender) | **MIT** | 490 | 72 | 2025-07-17 | End-to-end train-and-serve. **16 months without a push** — read before adopting. |
| [NVIDIA/recsys-examples](https://github.com/NVIDIA/recsys-examples) | **BSD-3-Clause** (`LICENSE`, 2,124 B; API says `NOASSERTION`) | 369 | 97 | 2026-11-23 | Accelerated training/deployment examples. Licence resolved by reading the file. |
| [alibaba/RecIS](https://github.com/alibaba/RecIS) | **Apache-2.0** | 366 | 26 | 2026-09-23 | Large-scale sparse training framework. APAC-origin; useful signal for APAC engagements. |
| [keras-team/keras-rs](https://github.com/keras-team/keras-rs) | **Apache-2.0** | 173 | 23 | 2026-11-18 | Multi-backend (JAX/TF/PyTorch) recommender layers on Keras 3. New and small, but actively pushed and from a credible maintainer. |

**Two exclusions made after reading, not before:**

- [twitter/the-algorithm](https://github.com/twitter/the-algorithm) — **AGPL-3.0**, 74,125★, 13,228
  forks, **last push 2025-09-08**. The most-starred recommender code on GitHub and **unusable for
  client work twice over**: network copyleft, and over a year stale. It is a published artefact, not a
  maintained library. Named here so no later pass is tempted by the star count.
- [bytedance/monolith](https://github.com/bytedance/monolith) — **Apache-2.0** (`LICENSE`, 12,621 B;
  API says `NOASSERTION` because a copyright preamble precedes the Apache text), 9,283★, but
  **ARCHIVED, last push 2025-10-13**. Permissive and dead — the licence check passes and the project is
  still unusable. See this section's own archived list below.
- [lyst/lightfm](https://github.com/lyst/lightfm) — **Apache-2.0**, 5,119★, 723 forks, **last push
  2024-07-24**. Still the most-cited hybrid recommender in blog posts; **28 months stale.** Do not
  start new work here.

### Media-mix and incrementality — the open substitute for a currency, and it is thriving

This is the commercially important finding of the plane. Advertisers cannot buy an open currency, so
the open-source energy went into **measuring media effect without a panel** — and that layer is
permissive, well-maintained and backed by Google and Meta:

| Repo | Licence | Stars | Forks | Last push | Notes |
|---|---|---|---|---|---|
| [google/meridian](https://github.com/google/meridian) | **Apache-2.0** | 1,616 | 317 | 2026-11-25 | Google's current Bayesian MMM, with geo-level hierarchical modelling and reach/frequency support. Pushed on measurement day. **The successor to `lightweight_mmm`.** |
| [facebookexperimental/Robyn](https://github.com/facebookexperimental/Robyn) | **MIT** | 1,540 | 442 | 2026-11-10 | Meta's semi-automated MMM (R, with a Python port). Ridge regression + evolutionary hyperparameter search. The most permissive of the three. |
| [pymc-labs/pymc-marketing](https://github.com/pymc-labs/pymc-marketing) | **Apache-2.0** | 1,314 | 451 | 2026-11-25 | Bayesian MMM **and** CLV in one toolbox, on PyMC. Vendor-neutral maintainer; the best choice when the client wants the model inspectable rather than a black box. |

**Deprecated, and do not start here:** [google/lightweight_mmm](https://github.com/google/lightweight_mmm)
— Apache-2.0, 1,055★, 237 forks, **ARCHIVED, last push 2025-06-17**. Still the top search result for
"open source MMM" and still cited in vendor decks. Google's replacement is Meridian, above.

### Identity resolution — the generic technique is healthy, the advertising-specific graph is a zero

| Repo | Licence | Stars | Forks | Last push | Notes |
|---|---|---|---|---|---|
| [dedupeio/dedupe](https://github.com/dedupeio/dedupe) | **MIT** | 4,531 | 578 | 2025-07-29 | Active-learning record linkage. 16 months stale but the library is mature and widely embedded. |
| [moj-analytical-services/splink](https://github.com/moj-analytical-services/splink) | **MIT** | 2,604 | 291 | 2026-11-25 | Probabilistic linkage at scale (Fellegi–Sunter) on DuckDB/Spark/Athena. **UK Ministry of Justice**, pushed on measurement day. The strongest choice here, and a public-sector provenance that survives procurement review. |
| [zinggAI/zingg](https://github.com/zinggAI/zingg) | **AGPL-3.0** | 1,277 | 177 | 2026-11-03 | ML entity resolution on Spark. **AGPL — run it unmodified as a separate service behind its interface**, per this file's standing rule. |

**The measured gap:** `identity resolution advertising` returns **4 repos on all of GitHub**, and the
only on-topic one has **0 stars** and has not been touched since 2021. The *technique* is open and
excellent; the **advertising identity graph** — the thing a media client actually needs — has no open
implementation at all. Build it on Splink; do not go looking for a ready-made one.

### Privacy-preserving joins — what exists instead of an open clean room

`data clean room` is a dead query (870 results, zero relevant — see `agents/top.md`). The real
primitives are published under their cryptographic names:

| Repo | Licence | Stars | Forks | Last push | Notes |
|---|---|---|---|---|---|
| [google/private-join-and-compute](https://github.com/google/private-join-and-compute) | **Apache-2.0** | 860 | 162 | 2026-03-09 | Private set intersection **sum** — compute an aggregate over the overlap without revealing the overlap. The exact primitive under "how many of my viewers saw your campaign". |
| [OpenMined/PSI](https://github.com/OpenMined/PSI) | **Apache-2.0** | 153 | 40 | 2026-09-22 | PSI with multi-language bindings (C++, Go, Rust, JS, Python). Smaller, but the easiest to integrate. |

**Archived — do not build on, named so they are not re-adopted:**
[tiktok-privacy-innovation/PrivacyGo-DataCleanRoom](https://github.com/tiktok-privacy-innovation/PrivacyGo-DataCleanRoom)
(Apache-2.0, 37★, archived 2024-10-31; TEE-based and one-way collaboration only) and
[facebookresearch/fbpcs](https://github.com/facebookresearch/fbpcs) (MIT, 151★, archived 2024-11-22).
**Both of the industry-backed open clean rooms are dead.** The pattern is the one this KB keeps
finding: the primitives survive, the products built on them do not.

### Experimentation and feature flags — the layer that makes a recommender provable

| Repo | Licence | Stars | Forks | Last push | Notes |
|---|---|---|---|---|---|
| [Unleash/unleash](https://github.com/Unleash/unleash) | **AGPL-3.0** (`LICENSE`, 34,523 B — verified) | 14,342 | 933 | 2026-11-25 | Feature flags and gradual rollout. **See the licence correction below — this is not Apache-2.0.** |
| [Flagsmith/flagsmith](https://github.com/Flagsmith/flagsmith) | **BSD-3-Clause** | 9,879 | 659 | 2026-11-25 | Flags + remote config, self-hostable. **The most permissive real platform in this tier** and the right default for client work. |
| [growthbook/growthbook](https://github.com/growthbook/growthbook) | **MIT with an enterprise carve-out** (3 named dirs) | 8,659 | 919 | 2026-11-25 | The only one here with real statistics: CUPED variance reduction and sequential testing. Carve-out is `packages/{back-end/src,front-end,shared/src}/enterprise`. |
| [open-feature/spec](https://github.com/open-feature/spec) | **Apache-2.0** | 1,301 | 65 | 2026-11-25 | CNCF vendor-neutral flagging **specification** — a document, not an engine. Use it to keep the client un-locked-in, per this KB's standing warning that specs are not code. |

**⛔ Licence correction, and it contradicts the published comparisons.** Third-party roundups — including
one dated 2026 — state that Unleash's open-source core is **Apache-2.0**. It is **AGPL-3.0**: verified
by reading `LICENSE` on both `main` and `master` (34,523 bytes, GNU AFFERO GENERAL PUBLIC LICENSE
Version 3), and the GitHub API agrees. For a media client embedding flag evaluation in a streaming
service, that is the difference between a permissive dependency and a network-copyleft one. **Flagsmith
(BSD-3) or GrowthBook's MIT core are the safe picks.**

### The event and query substrate — the new rows, and one licence that is not open source at all

Pass 2 already recorded Snowplow, Druid, Pinot and Superset. The demand side adds:

| Repo | Licence | Stars | Forks | Last push | Notes |
|---|---|---|---|---|---|
| [ClickHouse/ClickHouse](https://github.com/ClickHouse/ClickHouse) | **Apache-2.0** | 51,139 | 9,326 | 2026-11-25 | The column store most audience platforms are actually built on. Apache-2.0 and enormous. |
| [duckdb/duckdb](https://github.com/duckdb/duckdb) | **MIT** | 43,358 | 4,203 | 2026-11-25 | In-process analytics; the engine Splink runs linkage on. MIT, no server to operate. |
| [umami-software/umami](https://github.com/umami-software/umami) | **MIT** | 40,358 | 8,656 | 2026-11-25 | **The only large self-hosted web analytics platform that is actually MIT** — Matomo is GPL-3.0, Plausible AGPL-3.0, PostHog MIT-with-carve-out. For a publisher that wants to *modify* its analytics, this is the one. |
| [getredash/redash](https://github.com/getredash/redash) | **BSD-2-Clause** | 28,902 | 4,647 | 2026-11-25 | Query-and-dashboard layer; lighter alternative to Superset. |
| [cube-js/cube](https://github.com/cube-js/cube) | **Apache-2.0** by default (dual Apache-2.0 / MIT per `LICENSE`, 254 B) | 21,294 | 2,210 | 2026-11-25 | Semantic layer — defines "a view", "a unique viewer" **once** so the recommender, the dashboard and the ad stack cannot disagree. The highest-leverage small component in this plane. |
| [jitsucom/jitsu](https://github.com/jitsucom/jitsu) | **MIT** | 5,139 | 403 | 2026-11-25 | Event collection / Segment replacement. MIT and pushed on measurement day. |

**⛔ Excluded after reading the licence:**
[rudderlabs/rudder-server](https://github.com/rudderlabs/rudder-server) — 4,520★, pushed on measurement
day, universally described as open-source CDP infrastructure. Its `LICENSE` is the **Elastic License
2.0** (3,793 B), which forbids providing the software to third parties as a managed service. **It is
source-available, not open source**, and it cannot be the basis of a Globant-operated platform for a
client. Use Jitsu (MIT) or Snowplow (Apache-2.0) instead. This is the **fourth** licence category this
KB has had to add at the platform tier, after copyleft, delayed-open (FSL) and MIT-with-carve-out.

### Catalogue, EPG and podcast measurement — the small permissive corner that actually works

| Repo | Licence | Stars | Forks | Last push | Notes |
|---|---|---|---|---|---|
| [iptv-org/iptv](https://github.com/iptv-org/iptv) | **Unlicense** | 144,722 | 8,635 | 2026-11-25 | The largest public channel index. Public-domain dedication; **treat the channel *streams* as a legal question separate from the data.** |
| [iptv-org/epg](https://github.com/iptv-org/epg) | **Unlicense** | 3,560 | 561 | 2026-11-21 | EPG grabbers for hundreds of sources, emitting XMLTV. The practical way to get programme metadata without a vendor feed. |
| [XMLTV/xmltv](https://github.com/XMLTV/xmltv) | **GPL-2.0** | 425 | 108 | 2026-10-13 | The 25-year-old EPG interchange format and grabber suite. The *format* is the asset; the Perl tooling is copyleft. |
| [skymethod/op3](https://github.com/skymethod/op3) | **MIT** | 144 | 10 | 2026-11-25 | **The Open Podcast Prefix Project** — an open, privacy-respecting download-analytics prefix service. MIT, pushed on measurement day, and the only credible open audience-measurement *service* found anywhere in this plane. |
| [opawg/user-agents-v2](https://github.com/opawg/user-agents-v2) | **MIT** | 69 | 76 | 2026-11-24 | The Open Podcast Analytics Working Group's user-agent list — the shared reference data that makes two podcast counts comparable. **More forks than stars (1.1)**, the signature of real infrastructure. |

**Podcasting is the exception that proves the rule, and it is worth understanding.** OP3 is an open
measurement service that exists *because podcast delivery is an open RSS/HTTP download* — the
observation point is the publisher's own redirect, so no panel is needed and no gatekeeper can withhold
it. Where the observation is structurally available, open measurement appears immediately. Where it is
not — television — it does not exist at any star count.

**One informed caveat:** OP3 states IAB v2 *compliance as a goal* contingent on sponsorship, **not
certification**. Do not tell a client OP3 is IAB-certified. [growlfm/odl](https://github.com/growlfm/odl)
("Open Downloads", an alternative counting spec) **exists** — 11 refs via `git ls-remote` — but returns
nothing from `search/repositories` (**sixth measurement of that false negative**) and has **no LICENSE
file** at any of six probed names while `README.md` returns 200, so the missing licence is real, not a
naming convention. Use the spec, not the code.

### Automatic content recognition — the only open sensing method, and it is legally contested

ACR is how cross-platform viewing gets measured without a panel: fingerprint what the TV is playing,
match it to a reference database. This KB covered fingerprinting as *identification* in pass 5; here it
is the **measurement sensor**.

| Repo | Licence | Stars | Forks | Last push | Notes |
|---|---|---|---|---|---|
| [a-gram/audioneex](https://github.com/a-gram/audioneex) | **MPL-2.0** | 61 | 10 | 2026-06-17 | Content-agnostic real-time audio recognition; small fingerprints. **MPL-2.0 is weak per-file copyleft — it can be linked from proprietary code**, which is why it is the usable one. |
| [SafeNetIoT/ACR](https://github.com/SafeNetIoT/ACR) | **AGPL-3.0** | 24 | 0 | 2024-09-09 | The measurement tool from the 2024 smart-TV ACR tracking study. A research instrument, **not** a library; 0 forks, 14 months stale. |

**And the finding that makes this section matter:** in EMEA the ACR method itself was stopped by legal
action, not by a technical limit — see `intel/market.md` EMEA. **There is no open-source reference
fingerprint database for broadcast or streaming content, and that — not the matcher — is the asset.**
The matcher is 61 stars of MPL-2.0 you can have today.

### ⚠️ Archived or dormant in this plane — verified 2026-11-25, do not start new work here

Five repos that are top search results for their category and should not be adopted:

| Repo | Licence | Stars | Last push | Status |
|---|---|---|---|---|
| [twitter/the-algorithm](https://github.com/twitter/the-algorithm) | AGPL-3.0 | 74,125 | 2025-09-08 | Not archived but 14 months stale, **and AGPL** — unusable twice over. A published artefact, not a library. |
| [bytedance/monolith](https://github.com/bytedance/monolith) | Apache-2.0 (file read) | 9,283 | 2025-10-13 | **ARCHIVED.** Permissive and dead. |
| [lyst/lightfm](https://github.com/lyst/lightfm) | Apache-2.0 | 5,119 | 2024-07-24 | **28 months stale** and still the most-cited hybrid recommender in blog posts. |
| [google/lightweight_mmm](https://github.com/google/lightweight_mmm) | Apache-2.0 | 1,055 | 2025-06-17 | **ARCHIVED.** Still the top result for "open source MMM". Replaced by `google/meridian`. |
| [facebookresearch/fbpcs](https://github.com/facebookresearch/fbpcs) | MIT | 151 | 2024-11-22 | **ARCHIVED.** One of the two dead industry open clean rooms. |

Also dormant rather than dead: [dedupeio/dedupe](https://github.com/dedupeio/dedupe) (MIT, 4,531★,
2025-07-29) and [massquantity/LibRecommender](https://github.com/massquantity/LibRecommender) (MIT, 490★,
2025-07-17) — both mature and still embeddable, but check before proposing them as actively maintained.
[devflowinc/trieve](https://github.com/devflowinc/trieve) (MIT, 2,727★) has not been pushed since
**2026-01-25**.


## The live & delivery plane — measured 2026-11-26 (pass 8)

> Contribution → transcode → package/encrypt → origin → edge → player. 45 repos verified
> 2026-11-26, 45/45 resolved by `git ls-remote`. **9 of 45 required reading the LICENSE file**
> because the API returned `NOASSERTION` or `NONE` — the worst ratio in this KB, and the reason this
> section leads with licensing rather than ending with it.

### ⛔ The finding of this pass: this plane is permissive in copyright and gated by *two* non-copyright instruments

Every earlier plane in this KB had one gate, and it was always a **copyright** licence — on the code
(copyleft at the platform) or on the *content* (CPT, MedDRA, MDRA, a measurement currency). This
plane is the first where copyright is **not** the binding constraint. The code is permissive almost
everywhere. What gates it is:

1. **Patent pools.** The codecs are patent-encumbered, and their own reference implementations
   *affirmatively refuse* to license the patents.
2. **DRM key agreements.** Packaging and encryption are fully open; the key and licence server are
   not obtainable as open source at all, by design.

Neither gate is visible in a licence badge, a GitHub "Apache-2.0" label, or any listicle. Both are
absolute. This is the most commercially important structural finding in eight passes.

#### Gate 1 — the codecs refuse to grant patents, in writing

`BSD-3-Clause-Clear` and "The Clear BSD License" are not cosmetic variants of BSD. The *Clear* in the
name **is** the patent carve-out. Read from the licence files on 2026-11-26:

| Codec | Reference implementation | Licence | Stars | Last push | The patent clause, verbatim |
|---|---|---|---|---|---|
| VVC (H.266) encoder | https://github.com/fraunhoferhhi/vvenc | BSD-3-Clause-Clear | 1,228 | 2026-11-25 | "NO EXPRESS OR IMPLIED LICENSES TO ANY PARTY'S PATENT RIGHTS ARE GRANTED BY THIS LICENSE" |
| VVC (H.266) decoder | https://github.com/fraunhoferhhi/vvdec | BSD-3-Clause-Clear | 573 | 2026-11-24 | same |
| MPEG-5 LCEVC decoder | https://github.com/v-novaltd/LCEVCdec | The Clear BSD License | 35 | 2026-10-27 | same |
| MPEG-H 3D Audio decoder | https://github.com/Fraunhofer-IIS/mpeghdec | Fraunhofer FDK MPEG-H Software Licence | 100 | 2026-07-24 | §3 is titled **"No PATENT LICENSE"**; patent licences "may be obtained from the respective patent owners individually and/or under FRAND conditions" |
| AV1 encoder (production) | https://github.com/AOMediaCodec/SVT-AV1 | BSD-3-Clause-Clear | 131 | 2026-11-23 | no patent grant |
| AV1 encoder (Rust) | https://github.com/xiph/rav1e | BSD-2-Clause | 4,167 | 2026-11-25 | no patent clause either way |
| Quality metric | https://github.com/Netflix/vmaf | **BSD-2-Clause-Patent** | 5,660 | 2026-11-16 | the **opposite**: "an express patent grant" |
| AVIF | https://github.com/AOMediaCodec/libavif | BSD-2-Clause | 2,236 | 2026-11-25 | no patent clause |

**`Netflix/vmaf` is the control case that proves this is deliberate.** It is BSD-2-Clause-**Patent**,
a licence chosen specifically *to* grant patents. The same engineering culture, the same era, the
opposite choice — because VMAF is a metric nobody pooled, and VVC/LCEVC/MPEG-H are pooled. The
licence tracks the patent pool, not the generosity of the author.

**What this means operationally:** you may compile, ship and run `vvenc` under its copyright licence
and still owe royalties to the VVC pools (Access Advance / MPEG-LA administer them; the licence text
itself points you to "the respective patent owners"). The open source is not a route around the pool
and was never intended as one. Budget codec royalties as a line item, separately from engineering.

#### Gate 2 — the key is the gate: open source packages and encrypts, and stops at the licence server

Verified from the tooling and the vendor programmes:

| Step | Open source? | Verified detail |
|---|---|---|
| CMAF/DASH/HLS packaging | **Yes, permissive** | `shaka-project/shaka-packager`, BSD-3-Clause (read from `main/LICENSE`, API said `NOASSERTION`), 2,673★, 2026-11-04 |
| Common Encryption (CENC, ISO/IEC 23001-7) | **Yes** | one encrypted asset serves all three DRMs; `cenc` (AES-CTR) vs `cbcs` (AES-CBC) is the split, and **FairPlay requires `cbcs`** |
| Key/licence **server** for Widevine, PlayReady, FairPlay | **No — and not by neglect** | each requires a separate licence request, endpoint and key-delivery protocol, under a signed agreement: Widevine via Google's partner programme and a Master Licence Agreement plus a security questionnaire; PlayReady via an agreement with Microsoft for any service provider deploying it; FairPlay via Apple's developer agreement |
| ClearKey | Yes, in every open player | **and no studio accepts it for premium content** — it is a test mechanism, not a DRM |

So the only DRM you can run entirely on open source is the one the rights holder will not allow. For
premium content, three private companies hold the cryptographic root of trust and issue it by
contract. **There is no open-source path to a Widevine L1 / HDCP-compliant premium service, and no
amount of engineering changes that.** Plan the commercial agreement (or a multi-DRM vendor) into
week one of any premium-video engagement; it is a procurement dependency, not a build task.

#### ⚠️ The sixth distinct way a licence hides — and it is on the tool every multi-DRM guide names

| Repo | What GitHub's API reports | What is actually true |
|---|---|---|
| https://github.com/axiomatic-systems/Bento4 | **`NONE`** — "no licence" | **GPL-2.0 with a paid commercial alternative.** The text sits at **`Documents/LICENSE.txt`** (18,693 B): "Bento4 is available under two different licenses… a non-GPL commercial license is available from Axiomatic Systems LLC." |

Bento4 is one of the two tools every multi-DRM packaging guide recommends (a commercial DRM vendor
even publishes a Bento4 configuration guide for it). A client that links Bento4 into a proprietary
packaging service has either shipped GPL-2.0 obligations into their product or owes Axiomatic a
commercial fee. **GitHub reporting "no licence" caused this**, because the file is one directory
below root and no scanner reads it there.

This KB's licence-hiding taxonomy is now **six** shapes: an HTML file; a packaging classifier only;
decided by compile flags (Chromaprint); a modified Apache that keeps the name (OpenUSD); a PDF; and
now **a path outside the repository root.** Six independent mechanisms, one conclusion: the licence
*field* is not evidence. Only the file is.

#### A seventh shape, found in the same pass: a standards body minted its own licence

| Repo | Licence | Stars | Last push |
|---|---|---|---|
| https://github.com/5G-MAG/rt-libflute | **5G-MAG Public License v1.0** | 25 | 2026-11-24 |
| https://github.com/5G-MAG/rt-mbms-modem | AGPL-3.0 | 26 | 2026-11-24 |

The 5G-MAG Public License is **Apache-2.0 in structure and wording** — same definitions, same
numbering — with the patent grant rewritten. Read verbatim from `LICENSE`:

- **§3.1** grants Essential Patents "to make, have made, use, and otherwise transfer **(excluding
  selling)** the Work, **solely for study, testing and research purposes**".
- **§3.2**, for any other purpose, grants **nothing**. Instead: "**You commit to be prepared to
  negotiate**" a licence "with each Contributor and/or the Licensor on **Fair, Reasonable and
  NonDiscriminatory ('FRAND')** terms".

So production use of 5G-MAG code carries **no patent licence and an affirmative obligation to
negotiate one with every contributor**. A field-of-use restriction on selling means this is **not
open source** under the OSI definition, whatever the file name says. It reads as permissive to any
scanner and to any engineer who recognises the Apache shape. This matters because 5G-MAG is the
reference implementation ecosystem for 5G Broadcast/MBMS — the exact technology an EMEA public
broadcaster would pilot (see `intel/market.md` → EMEA).

### Contribution — the first mile, permissive, and the healthiest corner of this KB

| Name | Repo | Licence | Stars | Last push | Note |
|---|---|---|---|---|---|
| SRS | https://github.com/ossrs/srs | MIT | 29,457 | 2026-11-25 | **APAC-origin (China).** The most-starred self-hosted streaming server in the world, and MIT. |
| MediaMTX | https://github.com/bluenviron/mediamtx | MIT | 20,772 | 2026-11-25 | SRT/RTSP/WebRTC/HLS in one Go binary; the default modern choice. |
| ZLMediaKit | https://github.com/ZLMediaKit/ZLMediaKit | MIT *(read; API said `NOASSERTION`)* | 17,729 | 2026-11-25 | **APAC-origin (China).** C++11 media server. |
| Pion WebRTC | https://github.com/pion/webrtc | MIT | 16,926 | 2026-11-25 | The Go WebRTC stack under much of the above; first-party WHIP/WHEP examples. |
| SRT | https://github.com/Haivision/srt | MPL-2.0 | 3,640 | 2026-11-25 | `libsrt` is the de-facto reference; SRT is **not** an IETF standard. MPL-2.0 is weak per-file copyleft — safe beside proprietary code. |
| OBS Studio | https://github.com/obsproject/obs-studio | GPL-2.0 | 80,138 | **2026-11-26** | Pushes RTMP, SRT and WebRTC/WHIP. GPL-2.0: a tool you *run*, not a library you link. |
| Eyevinn WHIP | https://github.com/Eyevinn/whip | Apache-2.0 | 150 | 2026-06-09 | **EMEA-origin (Sweden).** WHIP (RFC 9725) client/server. |
| Eyevinn srt-whep | https://github.com/Eyevinn/srt-whep | Apache-2.0 | 145 | 2026-10-31 | SRT→WHEP bridge: the missing adapter between broadcast contribution and browser playout. |
| LiveKit | https://github.com/livekit/livekit | Apache-2.0 | 22,396 | 2026-11-25 | Self-hostable WebRTC SFU; the permissive option at the interactive end. |

**The APAC reading is the one to carry into an engagement:** the two most-starred self-hosted
streaming servers on earth (`ossrs/srs`, `ZLMediaKit`) are **both China-origin and both MIT**. This
is the inverse of the pattern in every other plane of this KB, where the permissive layer is
Western-origin and the Asian contribution is downstream. Here APAC *owns* the permissive substrate.

### Platform-tier servers — and this plane breaks the "copyleft at the platform" law twice

| Name | Repo | Licence | Stars | Last push | Verdict |
|---|---|---|---|---|---|
| OvenMediaEngine | https://github.com/OvenMediaLabs/OvenMediaEngine | AGPL-3.0 | 3,309 | 2026-11-25 | Obeys the law. **Note the rename** — every guide still says `AirenSoft/…`. Sub-second LL-HLS/WebRTC. |
| MistServer | https://github.com/DDVTECH/mistserver | **Unlicense (public domain)** | 521 | 2026-11-23 | **Breaks the law completely.** `COPYING.md`: "dedicated to the public domain… anyone can use MistServer for any purpose - including commercial purposes - without any restrictions." |
| Ant Media Server | https://github.com/ant-media/Ant-Media-Server | **no LICENSE file at root** | 4,747 | 2026-11-23 | Open-core. README sells an Enterprise Edition against a Community Edition; six filename probes returned 404. **Treat as source-available and verify in writing before client use.** |

MistServer is the second platform-tier exception this KB has recorded (the first was noted in
`intel/trends.md` §10) — and it goes further than MIT: **public domain.** A platform-tier streaming
server with zero obligations is a genuinely unusual asset, and at 521★ almost nobody has noticed.

### Packaging, origin and the player tier

| Name | Repo | Licence | Stars | Last push | Note |
|---|---|---|---|---|---|
| Shaka Packager | https://github.com/shaka-project/shaka-packager | BSD-3-Clause *(read)* | 2,673 | 2026-11-04 | CMAF + `cbcs` natively; the reference open packager. |
| Bento4 | https://github.com/axiomatic-systems/Bento4 | **GPL-2.0 + paid commercial** *(read at `Documents/LICENSE.txt`)* | 2,530 | 2026-11-22 | See the warning above. Do not link into proprietary code. |
| GPAC | https://github.com/gpac/gpac | LGPL-2.1 | 3,331 | 2026-11-24 | Packager/filter engine. LGPL: dynamic linking keeps proprietary code clean. |
| mp4ff | https://github.com/Eyevinn/mp4ff | MIT | 669 | 2026-11-24 | **EMEA-origin.** Go ISOBMFF/CMAF library — the MIT way to manipulate segments. |
| video.js | https://github.com/videojs/video.js | Apache-2.0 *(read)* | 40,253 | 2026-11-25 | The most-starred player in the plane. |
| hls.js | https://github.com/video-dev/hls.js | Apache-2.0 *(read)* | 17,066 | 2026-11-23 | Originally Dailymotion. |
| Shaka Player | https://github.com/shaka-project/shaka-player | Apache-2.0 | 8,289 | 2026-11-25 | DASH+HLS, EME/DRM integration. |
| dash.js | https://github.com/Dash-Industry-Forum/dash.js | **BSD-3 with an explicit patent non-grant** *(read)* | 5,555 | 2026-11-24 | `LICENSE.md`: "This software may be subject to other third party and contributor rights, **including patent rights, and no such rights are granted** under this license." Gate 1 again, in the reference *player*. |
| Eyevinn webrtc-player | https://github.com/Eyevinn/webrtc-player | MIT | 169 | 2026-10-30 | WHEP playback. |
| FFmpeg | https://github.com/FFmpeg/FFmpeg | **LGPL-2.1+, or GPL by build flag** *(read)* | 68,197 | 2026-11-25 | `LICENSE.md`: LGPL-2.1+ in combination, but `--enable-gpl` makes the binary GPL. **The compile-flag licence category, second instance** after Chromaprint (pass 5) — so it is a pattern, not an anecdote. Audit your build flags, not just your dependency list. |

### Media over QUIC — the one genuinely new thing in this plane, and it is Apache-2.0

MoQ is the first new media transport since this KB began. Status verified 2026-11-26:

- **Not yet an RFC.** `draft-ietf-moq-transport` is an Internet-Draft on the Standards Track; the
  IETF datatracker milestone to request IESG publication is **2026-12-31**. Draft revision was -22
  (1 October 2026) per trade reporting.
- **Eleven vendors demonstrated interoperable implementations at NAB 2026**; the MoQ Alliance
  includes Akamai, AWS, Cisco, Cloudflare and Fastly.
- Companion drafts are earlier: CMAF/streaming-format drafts are early WG items, the LOC container
  has a **March 2027** milestone, and common access tokens were at -02 on 2026-11-02.

| Name | Repo | Licence | Stars | Last push | Origin |
|---|---|---|---|---|---|
| moq (Rust, reference) | https://github.com/moq-dev/moq | Apache-2.0 | 1,642 | **2026-11-26** | formerly `kixelated/moq-rs` |
| moxygen (C++) | https://github.com/facebookexperimental/moxygen | Apache-2.0 | 127 | 2026-11-25 | Meta — North America |
| libquicr | https://github.com/Quicr/libquicr | BSD-2-Clause | 21 | 2026-11-25 | Cisco — North America |
| moqtransport (Go) | https://github.com/mengelbart/moqtransport | MIT | 91 | 2026-09-16 | academic — EMEA |
| moq-wasm | https://github.com/nttcom/moq-wasm | MIT | 57 | 2026-11-25 | **NTT Communications — APAC** |
| moq-js | https://github.com/kixelated/moq-js | `NONE` | 154 | **ARCHIVED 2025-06-20** | do not start here |

**Why this matters now:** MoQ is the rare case where the open implementations are permissive
(Apache-2.0/MIT/BSD), the standard is still open for influence, **and** all four regions are already
represented in the implementer set. Pilot-stage in 2026, wider production expected 2027 — which
means an engagement starting now is early rather than late. Caveat recorded honestly: ad insertion is
only partially supported and VOD is still being worked out, so MoQ does not replace HLS/DASH yet.

### Edge, CDN and broadcast delivery

| Name | Repo | Licence | Stars | Last push | Note |
|---|---|---|---|---|---|
| Apache Traffic Server | https://github.com/apache/trafficserver | Apache-2.0 | 2,001 | 2026-11-25 | The only actively-developed, permissively-licensed caching proxy/CDN core left in this table. |
| Varnish Cache | https://github.com/varnishcache/varnish-cache | BSD-2-Clause | 4,040 | **ARCHIVED 2026-02-16** | See the warning below — **do not record this as "dead" without reading it.** |
| RDK Thunder | https://github.com/rdkcentral/Thunder | Apache-2.0 | 61 | 2026-11-25 | Set-top/STB framework plumbing; the device end of the chain. |
| Tvheadend | https://github.com/tvheadend/tvheadend | GPL-3.0 | 3,587 | 2026-11-25 | DVB/IPTV backend. |
| Jellyfin | https://github.com/jellyfin/jellyfin | GPL-2.0 | 59,765 | 2026-11-25 | Media server; copyleft at the platform, as the law predicts. |
| Eyevinn Channel Engine | https://github.com/Eyevinn/channel-engine | Apache-2.0 | 135 | 2026-11-06 | FAST channel assembly (already in the monetization plane; it belongs to both). |

#### ⚠️ Varnish Cache: archived on GitHub, with a relocation this pass could not confirm

Stated precisely, because the difference matters to an engagement:

- The GitHub repo **is archived** (2026-02-16) and its own `README.rst` carries a banner: "IMPORTANT
  - THIS REPOSITORY HAS MOVED", naming `code.vinyl-cache.org/vinyl-cache/vinyl-cache`, a branch
  rename `master`→`main`, and a `last` tag for the final usable GitHub version.
- **Neither `code.vinyl-cache.org` nor `vinyl-cache.org` resolved from this environment**
  (`curl` returned `000` for both), so the destination is **unverified**. That may be this
  environment's egress policy rather than the host being absent.
- **Therefore:** do not start new work from the GitHub repo, and do not tell a client the project is
  dead. Confirm the project's current home directly before relying on either statement. Apache
  Traffic Server is the verified-active permissive alternative today.

### Informed gaps in this plane — searched, not assumed

- **librist is not on GitHub.** RIST — the standards-based (VSF) multi-vendor contribution protocol —
  has its reference implementation on `code.videolan.org` (GitLab), so it is invisible to every
  GitHub-based discovery method including this KB's own oracle. An informed gap, not an absence.
- **No open MPEG-H Audio encoder** (decoder only), while Brazil's DTV+ mandates MPEG-H support.
- **No maintained open ATSC 3.0 implementation** — `libatsc3` has no canonical repo; only stale forks.
- **No open-source premium DRM licence server**, structurally (Gate 2).

## ⚠️ Archived or dormant — do not start new work here

Four repos that earlier cycles of this KB listed as live foundations:

| Repo | License | Stars | Last push | Status |
|---|---|---|---|---|
| [Sanster/IOPaint](https://github.com/Sanster/IOPaint) | Apache-2.0 | 23,286 | 2025-04-29 | **ARCHIVED** by its owner. Was listed here as a current foundation. Vendor the code or move on. |
| [salesforce/LAVIS](https://github.com/salesforce/LAVIS) | BSD-3-Clause | 11,256 | 2026-09-18 | **ARCHIVED.** Use `huggingface/transformers` for BLIP-class models instead. |
| [IDEA-Research/Grounded-Segment-Anything](https://github.com/IDEA-Research/Grounded-Segment-Anything) | Apache-2.0 | 17,795 | 2024-09-05 | Not archived but untouched for ~2 years. |
| [coqui-ai/TTS](https://github.com/coqui-ai/TTS) | MPL-2.0 | 46,261 | 2024-08-16 | Company wound down; repo dormant since 2024. Superseded for new work by Chatterbox / F5-TTS / GPT-SoVITS. |

Also still live but worth knowing the terms: [mifi/lossless-cut](https://github.com/mifi/lossless-cut)
(GPL-2.0, 46,264★), [bbc/audiowaveform](https://github.com/bbc/audiowaveform) (GPL-3.0, 2,172★ — BBC R&D's
waveform generator), [camenduru/stable-diffusion-webui-colab](https://github.com/camenduru/stable-diffusion-webui-colab)
(Unlicense, 15,882★, last push 2025-12-16).

*Gap **retracted 2026-11-22**: this file previously recorded that no permissively-licensed open
implementation of the **MOS protocol** (newsroom computer system ↔ playout) existed, and that newsroom
automation therefore had to be built against a vendor NRCS. That was wrong.
[`Sofie-Automation/sofie-mos-connection`](https://github.com/Sofie-Automation/sofie-mos-connection)
implements **MOS Protocol v2.8.4** under MIT, and the surrounding Sofie stack (above) is a complete
MIT newsroom automation system in daily production at NRK, the BBC and TV 2 Norway. Newsroom
automation is an **integration** job, not a from-scratch build — which is better news commercially,
because the risky part was never the protocol.*

*The gap that is actually open, and it is narrower and more buildable: **there is no MCP bridge to
`sofie-timeline-state-resolver`.** The typed, safe device-abstraction layer for broadcast hardware
already exists and is MIT; nothing exposes it to an agent. See `compose/patterns.md` Pattern 7.*

*Still genuinely missing: a permissive **MAM** (see `verticals/solutions.md`) and maintained **stem
separation** — `demucs` and `open-unmix` are both MIT and both dormant, with nothing active replacing
them.*

---

## The trust & safety plane — measured 2026-11-26 (pass 9)

The enforcement substrate under every age-verification, illegal-content, minor-protection and
platform-transparency duty this KB has recorded in `intel/market.md` for three passes. **62 repos
verified, 62/62 resolve by `git ls-remote`.** Unlike the agent layer above it, this substrate is
healthy, permissive and actively pushed — several of the repos below were pushed the day this pass
ran.

### The organisation that changed this plane: ROOST

[ROOST](https://github.com/roostorg) (Robust Open Online Safety Tools) is a non-profit that builds
and maintains open safety infrastructure, and it is the reason this plane is now buildable. Fifteen
repos, Apache-2.0 on the code, and the two flagship projects were pushed this week.

| Repo | Licence | ★ / forks | Last push | What it is |
|---|---|---|---|---|
| [roostorg/osprey](https://github.com/roostorg/osprey) | Apache-2.0 | 511★ / 73f | 2026-11-23 | **Discord's production safety rules engine, donated.** "Automate the obvious and investigate the ambiguous." High-performance rule evaluation over event streams. This is the piece nobody could build before. |
| [roostorg/coop](https://github.com/roostorg/coop) | Apache-2.0 | 150★ / 55f | **2026-11-26 (the day of this pass)** | Review console: moderation dashboard, queues, routing, automatic enforcement rules, integrations. Self-hosted, so the content never leaves the client's infrastructure — which is the whole argument in a GDPR or ECA Digital engagement. |
| [roostorg/coop-integration-example](https://github.com/roostorg/coop-integration-example) | Apache-2.0 | 4★ / 1f | 2026-08-24 | Reference integration package. The thing to copy on day one. |
| [roostorg/pigeon](https://github.com/roostorg/pigeon) | **none in repo** | 2★ / 1f | 2026-11-21 | The model→signal bridge. See `agents/top.md`: this is the entire agent layer of the plane. |
| [roostorg/awesome-safety-tools](https://github.com/roostorg/awesome-safety-tools) | CC-BY-4.0 | 274★ / 44f | 2026-11-18 | **A directory, not code** — demoted on sight per this file's standing rule. But it is the highest-yield *discovery* asset in the plane: it names the real tools that generic GitHub search cannot surface. |
| [roostorg/model-community](https://github.com/roostorg/model-community) | CC-BY-4.0 | 139★ / 31f | 2026-11-18 | Documents, not code. Same demotion, same usefulness. |

### Hash matching — the identification layer, and it is permissive

| Repo | Licence | ★ / forks | Last push | Notes |
|---|---|---|---|---|
| [meta/ThreatExchange](https://github.com/meta/ThreatExchange) | **BSD** — file-verified, 1,522 B `LICENSE`: *"BSD License For ThreatExchange software"* | 1,417★ / 368f | 2026-11-19 | The reference implementations of **PDQ** (256-bit perceptual image hash), **TMK+PDQF** and **vPDQ** (video), plus **HMA** (Hasher-Matcher-Actioner) and `python-threatexchange`. The canonical substrate of this plane. ⚠️ **The repo moved from `facebook/ThreatExchange`** — see the method note below. |
| [matrix-org/hma-matrix](https://github.com/matrix-org/hma-matrix) | Apache-2.0 | 8★ / 2f | 2026-11-24 | Matrix-specific extensions to HMA. Tiny, but pushed this week and a working example of binding HMA into a real platform. |
| [c4osl/rocketchatcsam](https://github.com/c4osl/rocketchatcsam) | MIT | 13★ / 1f | 2026-11-05 | A safety app for Rocket.Chat that validates uploads against **Microsoft PhotoDNA**. The clearest artifact of the content law in this plane: the client is MIT and 13 stars, the service it calls is gated. |
| [jenssegers/imagehash](https://github.com/jenssegers/imagehash) | MIT | 2,060★ / 173f | 2025-09-17 | Perceptual image hashing for PHP. |
| [coenm/ImageHash](https://github.com/coenm/ImageHash) | MIT | 242★ / 27f | 2025-01-08 | Perceptual hash algorithms on ImageSharp (.NET). |
| [AsuharietYgvar/AppleNeuralHash2ONNX](https://github.com/AsuharietYgvar/AppleNeuralHash2ONNX) | Apache-2.0 | 1,532★ / 124f | 2021-08-21 | Historical. The reverse-engineering that ended Apple's on-device scanning programme. Cite it as evidence of how fast client-side hashing becomes a political problem, not as a tool. |

### ⛔ The content law, ninth confirmation — and now a three-step obligation gradient

The algorithms are BSD. **The hash lists are not available at all.** NCMEC, the IWF and GIFCT
distribute their hash sets under membership and vetting, not under a licence; PhotoDNA is reached
through a gated Microsoft service. So the gradient across a single statutory duty runs:

| Step in the duty | Nature of the problem | Best open artifact | State |
|---|---|---|---|
| **1. Detect** — hash and match | A format and performance problem | [meta/ThreatExchange](https://github.com/meta/ThreatExchange) — BSD, 1,417★ | **Healthy**, pushed 2026-11-19 |
| **2. Obtain the list** to match against | **Membership and vetting**, not code | none — no licence exists to obtain | **Closed by design** |
| **3. Report** to the authority, as federal law requires | Pure judgment plus a wire format | [ello/ncmec_reporting](https://github.com/ello/ncmec_reporting) — 7★, **no licence file** | **Abandoned 2022-03-29** |

This is the same declare → honour → settle shape pass 5 measured for rights reservation, and the
same CPT/MedDRA shape healthcare measured twice. **Ninth confirmation, and the most legally loaded
instance of it**: a provider can build the detector, cannot lawfully obtain the list, and the only
open code that files the mandated report is unlicensed and four years dead.

### Rules engines and review consoles — the platform tier, and it breaks this KB's copyleft law

| Repo | Licence | ★ / forks | Last push | Notes |
|---|---|---|---|---|
| [roostorg/osprey](https://github.com/roostorg/osprey) | Apache-2.0 | 511★ / 73f | 2026-11-23 | Rules engine. |
| [roostorg/coop](https://github.com/roostorg/coop) | Apache-2.0 | 150★ / 55f | 2026-11-26 | Review console. |
| [conversationai/conversationai-moderator](https://github.com/conversationai/conversationai-moderator) | Apache-2.0 | 208★ / 31f | 2026-06-22 | Google Jigsaw's machine-assisted human-moderation toolkit. The original of the category, still maintained. |
| [Jigsaw-Code/altitude](https://github.com/Jigsaw-Code/altitude) | Apache-2.0 | 44★ / 11f | 2026-06-21 | Jigsaw again: a single elevated view of potential terrorist and violent extremist content, aimed explicitly at **small platforms** that cannot build a T&S org. The right starting point for a mid-size broadcaster or UGC client. |
| [meta/content-review-filters](https://github.com/meta/content-review-filters) | Apache-2.0 | 8★ / 6f | 2026-10-24 | Filters and preferences for a content-review tool. 8 stars, from Meta, pushed last month — the kind of repo only the ROOST directory surfaces. |
| [policykit/policykit](https://github.com/policykit/policykit) | MIT | 159★ / 26f | 2025-12-17 | Builds *governance* — the policy-authoring layer above moderation. Academic in origin, MIT, and the only open artifact that treats a moderation policy as a first-class object. |

**This breaks the "copyleft at the platform tier" law** that `verticals/solutions.md` has recorded
since pass 2, and it breaks it decisively: every platform-tier artifact in this plane is Apache-2.0
or MIT. The reason is visible in who published them — Discord, Google Jigsaw and Meta donated
infrastructure they run themselves, and a donor who wants adoption does not pick AGPL. **Where the
platform tier was built by a vendor it is copyleft; where it was donated by an operator it is
permissive.** That is the sharpest statement this KB has of the law, and it predicts the licence from
the publisher rather than from the layer.

### Age verification — the EMEA estate, and the regulator shipped the code

The European Commission published the Age Verification Blueprint as working software, not as a
specification to implement. Nine repos under one organisation, verified this pass:

| Repo | Licence | ★ / forks | Last push | Role |
|---|---|---|---|---|
| [av-app-android-wallet-ui](https://github.com/eu-digital-identity-wallet/av-app-android-wallet-ui) | **EUPL-1.2** | 309★ / 52f | 2026-11-07 | The white-label Android age-verification app. The flagship. |
| [av-app-ios-wallet-ui](https://github.com/eu-digital-identity-wallet/av-app-ios-wallet-ui) | **EUPL-1.2** | 20★ / 3f | 2026-10-15 | iOS counterpart. |
| [av-doc-technical-specification](https://github.com/eu-digital-identity-wallet/av-doc-technical-specification) | **CC-BY-4.0** — file-verified, 227 B: *"© 2025 by European Commission … Attribution 4.0 International"* | 99★ / 8f | 2026-09-02 | The specification. Documents, not code. |
| [av-lib-android-zkp-age-icao](https://github.com/eu-digital-identity-wallet/av-lib-android-zkp-age-icao) | Apache-2.0 | 20★ / 6f | 2026-05-21 | Zero-knowledge age proof against ICAO travel-document chips. |
| [av-lib-ios-longfellow-zkp](https://github.com/eu-digital-identity-wallet/av-lib-ios-longfellow-zkp) | Apache-2.0 | 4★ / 2f | 2026-10-30 | Swift ZKP generation/verification for mdoc credentials. |
| [av-srv-web-issuing-avw-py](https://github.com/eu-digital-identity-wallet/av-srv-web-issuing-avw-py) | Apache-2.0 | 5★ / 6f | 2026-05-15 | Provider backend issuer, OID4VCI. |
| [av-web-verifier-ui](https://github.com/eu-digital-identity-wallet/av-web-verifier-ui) | Apache-2.0 | 15★ / 5f | 2026-06-22 | Relying-party verifier UI. |
| [av-verifier-frontend-cinema](https://github.com/eu-digital-identity-wallet/av-verifier-frontend-cinema) | Apache-2.0 | 1★ / 3f | 2026-06-22 | **A cinema age-gate reference frontend.** One star, and it is a media use case written by the regulator. |
| [av-srv-trust-validator](https://github.com/eu-digital-identity-wallet/av-srv-trust-validator) | Apache-2.0 | 0★ | 2026-10-12 | Trust-list validation. |

**Two licence shapes, split by artifact type, and the split matters.** The two *apps* are **EUPL-1.2**
— OSI-approved, but a **copyleft** licence with an unusual compatibility clause and legal force in 23
languages. The *libraries and servers* are Apache-2.0. So a client can embed the ZKP libraries freely
and must think carefully before shipping a modified fork of the app itself. This is the first
EUPL-1.2 artifact recorded anywhere in this KB.

⚠️ **Channel gap, stated as a gap:** `ageverification.dev`, the dedicated technical portal, **does not
resolve from this session** (outside the allowed network domains), so the blueprint's current version
number, conformance programme and the exact status of the 31 December 2026 rollout date are **not
verified here**. Secondary sources place the Commission's Recommendation on a common EU age
verification approach at **29 April 2026** and pilots in Denmark, France, Greece, Italy and Spain.
Treat the rollout date as reported, not confirmed, and check the portal from an unrestricted network.

### Platform transparency — the DSA reporting layer

| Repo | Licence | ★ / forks | Last push | Notes |
|---|---|---|---|---|
| [digital-services-act/transparency-database](https://github.com/digital-services-act/transparency-database) | **GPL-2.0** | 55★ / 10f | 2026-11-25 | The DSA Transparency Database itself. **The regulator's own code is copyleft** — the one place in this plane where the platform tier is GPL, and it is GPL because the publisher is a public body, not an operator courting adoption. Consistent with the refined law above. |
| [afkzonagroup/rationale](https://github.com/afkzonagroup/rationale) | Apache-2.0 | 0★ | 2026-11-22 | SDK for submitting statements of reasons to the Commission's database. **Zero stars, pushed four days before this pass.** The submission side of a live legal obligation has one Apache-2.0 SDK and nobody is watching it. |
| [eu-dsa-transparency-db-sor-data-downloader](https://github.com/transparency-in-content-moderation/eu-dsa-transparency-db-sor-data-downloader) | Apache-2.0 | 1★ | 2026-09-14 | Downloads and converts statement-of-reasons data. The research/benchmarking direction. |

### Decentralised moderation — permissive, small, and the AT Protocol side is the live one

| Repo | Licence | ★ / forks | Last push | Notes |
|---|---|---|---|---|
| [bluesky-social/ozone](https://github.com/bluesky-social/ozone) | **Dual MIT/Apache-2.0** — file-verified, 307 B: *"Except as otherwise noted in individual files, this software is licensed under…"* | 548★ / 94f | 2026-11-23 | Labelling and moderation console for atproto. The reference implementation of *stackable* moderation — third parties publish labels, users subscribe. |
| [bluesky-social/indigo](https://github.com/bluesky-social/indigo) | Apache-2.0 | 1,395★ / 271f | 2026-11-25 | The Go atproto services, including the firehose consumers a labeler runs on. |
| [matrix-org/mjolnir](https://github.com/matrix-org/mjolnir) | Apache-2.0 | 449★ / 77f | 2026-10-28 | The original Matrix moderation bot. |
| [the-draupnir-project/Draupnir](https://github.com/the-draupnir-project/Draupnir) | **Apache-2.0** — see the licence finding below | 253★ / 30f | **2026-11-26 (the day of this pass)** | The maintained successor to mjolnir. A Matrix community-management platform. |
| [fedimod/fires](https://github.com/fedimod/fires) | AGPL-3.0 | 29★ / 3f | 2026-03-27 | Fediverse Intelligence Recommendations Replication Endpoint Server — shares moderation recommendations between instances. AGPL, as the law predicts for a non-operator publisher. |
| [MarcT0K/Fediverse-Spam-Filtering](https://github.com/MarcT0K/Fediverse-Spam-Filtering) | GPL-2.0 | 8★ / 2f | 2025-12-07 | Spam filtering service for the Fediverse. |
| [selfagency/mastodont](https://github.com/selfagency/mastodont) | MIT | 22★ / 2f | 2026-06-01 | CLI blocklist importer for Mastodon admins. |
| [swicg/activitypub-trust-and-safety](https://github.com/swicg/activitypub-trust-and-safety) | NOASSERTION (W3C community-group documents) | 51★ / 6f | 2026-11-05 | The W3C Social Web Incubator Community Group's T&S taskforce. Documents, not code, but it is where the ActivityPub side's interoperability is being decided. |

### ⛔ The licence finding of this pass: an eighth distinct way a licence hides — and this one is the *inverse* of hiding

[the-draupnir-project/Draupnir](https://github.com/the-draupnir-project/Draupnir) — 253★, **pushed
the day of this pass** — is reported by the GitHub API as having **no licence at all**. Probing the
eleven usual filenames on both `main` and `master` found nothing but a `NOTICE`. A careless pass
would have written "unlicensed, all rights reserved" and dropped a maintained project.

A shallow clone settles it in one call. The repo uses ****REUSE** (the FSFE/SPDX reuse-compliance standard; `reuse.software` is outside this session's allowed network domains, so the URL is deliberately not linked here — unverified, not dead)**, the
FSFE/SPDX compliance standard:

- `REUSE.toml` at the root, declaring `SPDX-PackageName`, supplier and download location, then a
  `[[annotations]]` block **per file** with its own `SPDX-License-Identifier`;
- a `LICENSES/` **directory** holding the full text of every licence actually used —
  `Apache-2.0.txt`, `MIT.txt`, `0BSD.txt`, `AFL-3.0.txt`, `CC-BY-SA-4.0.txt`, `CC0-1.0.txt`;
- `"license": "Apache-2.0"` in `package.json`;
- a `NOTICE` recording the modified mjolnir heritage and stating that *"All source files include an
  SPDX license identifier."*

**The project is more licence-compliant than the API is able to read.** GitHub's detector looks for
one licence file at the root; REUSE deliberately replaces that with per-file annotation, so maximum
compliance reads as zero compliance. New standing rule, and it generalises to all twelve industries:

> **`NONE` on an actively maintained repo is a prompt to check for `REUSE.toml` and a `LICENSES/`
> directory before concluding anything.** Check `package.json` / `pyproject.toml` / `Cargo.toml`
> too — the declared licence often lives there while the root is deliberately bare.

And a second instance in the same pass, on a far bigger repo: **[NVIDIA-NeMo/Guardrails](https://github.com/NVIDIA-NeMo/Guardrails)**
(7,581★) is reported `NOASSERTION`, yet its `LICENSE.md` literally contains the line
`SPDX-License-Identifier: Apache-2.0`. The detector failed on a file that states its own SPDX
identifier in machine-readable form. **Two of the largest repos in this plane are mislabelled by the
API in the same direction**, so the probe is not optional here.

### ⚙️ Method confirmation: the `repo:` 422 is a rename detector, and it fired three times in one pass

Pass 8 noticed that a `repo:<slug>` search failing while `git ls-remote` succeeds indicates a
**rename**, not an absence. This pass fired it three times, which makes it a rule rather than an
observation:

| Slug as every blog and doc still writes it | `ls-remote` | `repo:` search | Canonical name today | ★ |
|---|---|---|---|---|
| `facebook/ThreatExchange` | EXISTS | **422** | **[meta/ThreatExchange](https://github.com/meta/ThreatExchange)** | 1,417★ |
| `NVIDIA/NeMo-Guardrails` | EXISTS | **422** | **[NVIDIA-NeMo/Guardrails](https://github.com/NVIDIA-NeMo/Guardrails)** | 7,581★ |
| `microsoft/presidio` | EXISTS | **422** | **[data-privacy-stack/presidio](https://github.com/data-privacy-stack/presidio)** | 12,065★ |

All three old paths still redirect in a browser, so a human never notices and every secondary source
keeps citing the dead slug. The control case proves the mechanism is the rename and not case
sensitivity: `jigsaw-code/altitude` resolves correctly to `Jigsaw-Code/altitude` despite the wrong
case. **Write the canonical path in a KB, because the old one is what a client's SBOM will fail on.**

### Adjacent substrate worth knowing — red-teaming and PII

| Repo | Licence | ★ / forks | Last push | Notes |
|---|---|---|---|---|
| [data-privacy-stack/presidio](https://github.com/data-privacy-stack/presidio) | MIT | 12,065★ / 1,472f | 2026-11-24 | PII detection, redaction, masking and anonymisation. **The largest permissive repo in this plane**, and the one most media clients actually need first — subtitle files, transcripts and UGC are full of personal data. Moved from `microsoft/presidio`. |
| [NVIDIA/garak](https://github.com/NVIDIA/garak) | Apache-2.0 | 10,186★ / 1,523f | 2026-11-25 | LLM vulnerability scanner. The pre-launch test harness for any generative feature shipped to the public. |
| [microsoft/PyRIT](https://github.com/microsoft/PyRIT) | MIT | 5,088★ / 1,128f | 2026-11-25 | AI red-teaming toolkit with automated scanning. |

## The theatrical & digital-cinema plane — measured 2026-11-26 (pass 10)

The channel this KB had no row for. 25 repos verified this pass, **25/25 URLs resolve**
(`git ls-remote`, the only existence oracle that works from this session — see the measurement note).

### ⛔ The finding of this pass: this is the first plane in this KB that is **copyleft end to end**

Every other plane in this file obeys some version of "permissive at the pipeline, copyleft at the
platform" (trend 4). **The theatrical chain inverts it completely: the authoring tools, the
validators and the key managers are GPL-2.0, GPL-3.0 or AGPL-3.0 without exception, and the only
permissive licences in the plane sit in the *substrate* — the codec, the container and one
validator.** For Globant this is the single most important commercial fact in the plane:

> **You cannot ship a proprietary client deliverable built on the DCP authoring chain.** `dcpomatic`,
> `libdcp`, `libsub`, `opendcp`, `backports`/`dcp_inspect`, `dcpdoctor` and `kdmcourier` are all
> copyleft. A client engagement that touches DCP authoring is either an open-source contribution, a
> hosted-service play where the copyleft boundary is the process boundary, or a rewrite on top of
> `asdcplib` + `openjpeg` (both permissive). Decide which in week one, not at delivery.

The one escape hatch is real and worth naming: **ClairMeta is BSD-3-Clause**, so *validation* — the
step a client is most likely to want embedded in their own pipeline — can be built permissively even
though authoring cannot.

### DCP authoring and packaging — GPL, and the canonical tool is active this week

| Repo | Licence | ★ / forks | Last push | Notes |
|---|---|---|---|---|
| [cth103/dcpomatic](https://github.com/cth103/dcpomatic) | GPL-2.0 | 175★ / 38f | 2026-11-24 | **DCP-o-matic** — the canonical open-source DCP authoring application, and the tool every film-school and festival guide points at. Pushed **two days before this pass**: the most active project in the plane. |
| [cth103/libdcp](https://github.com/cth103/libdcp) | GPL-2.0 | 29★ / 18f | 2026-11-03 | The read/write library underneath DCP-o-matic. This is the layer to call if you are building your own tool and can accept GPL. |
| [cth103/libsub](https://github.com/cth103/libsub) | **GPL-2.0-or-later, in the file headers only** | 9★ / 3f | 2026-10-14 | Subtitle read/write. **No licence file of any kind** — see the licence finding below. |
| [tmeiczin/opendcp](https://github.com/tmeiczin/opendcp) | GPL-3.0 | 134★ / 51f | **2020-04-28** | **OpenDCP.** Still the second-most-starred DCP tool and still recommended by QC guides, but **dormant for six and a half years.** Do not start new work here. |
| [cth103/dcpomatic1](https://github.com/cth103/dcpomatic1) | GPL-2.0 | 8★ / 4f | 2020-06-27 | Legacy v1 line. Context row, not a recommendation. |
| [brightfish-be/DcpToolkit](https://github.com/brightfish-be/DcpToolkit) | **MIT** | 3★ / 1f | 2026-06-22 | PHP library to read and write DCPs, from a Belgian (EMEA) cinema-tech company. **The only permissive authoring-side code in the plane** — and at 3★ it is a seed, not a base. Worth watching precisely because of its licence. |
| [ruhrmann/dcp-renamer](https://github.com/ruhrmann/dcp-renamer) | GPL-3.0 | 3★ / 1f | 2021-03-11 | Renames DCPs to the ISDCF naming convention. Tiny, dormant, and solves a real daily annoyance. |
| [adrievx/DCPInfo](https://github.com/adrievx/DCPInfo) | **none** | 0★ / 0f | 2025-04-25 | C# DCP parser. No licence — all rights reserved. Listed so nobody rediscovers it and assumes otherwise. |

### Validation and QC — the one permissive layer, and the one with a user base

| Repo | Licence | ★ / forks | Last push | Notes |
|---|---|---|---|---|
| [ClairMeta/ClairMeta](https://github.com/ClairMeta/ClairMeta) | **BSD-3-Clause** | 106★ / 30f | 2026-10-10 | **The only permissive DCP validator, and the most important row in this plane.** Python; checks asset integrity (MIME, size, hash), XSD schema validation of every XML, and digital-signature/certificate validation. Depends on `asdcplib`. **Moved org**: was `Ymagis/ClairMeta` — licence confirmed in its own `LICENSE` (1,470B, "Copyright © 2017 YMAGIS S.A."). |
| [wolfgangw/backports](https://github.com/wolfgangw/backports) | **GPL-3.0** | 40★ / 2f | 2026-10-03 | **`dcp_inspect`** — deep inspection and validation of DCPs, the tool the BAVC QC guide pairs with DCP-o-matic. Active. Licence is real but **named `gpl.txt`** — see the finding below. |
| [wolfgangw/digital_cinema_tools](https://github.com/wolfgangw/digital_cinema_tools) | **no licence file** | 100★ / 41f | 2024-01-15 | The predecessor distribution, and still the higher-starred of the two. Superseded by `backports`; **unlicensed and dormant two years.** Cite the successor, not this. |
| [PostPerfection/dcpdoctor](https://github.com/PostPerfection/dcpdoctor) | AGPL-3.0 | 1★ / 0f | 2026-11-13 | A brand-new validator whose own site claims "135+ validation checks, KDM and IMF support". **1 star, 0 forks.** The claim is self-reported marketing; the adoption is measured. Watch it, do not stake a programme on it. |

### ⛔ Two new ways a licence hides, both found in this plane, and one of them reverses a verdict

This KB has catalogued eight ways a licence hides. This pass adds two, and the first one **nearly
produced a wrong row in this file**:

1. **The licence file is named after the licence.** `wolfgangw/backports` has no `LICENSE`, no
   `LICENCE`, no `COPYING` — it has **`gpl.txt`** (32,473B, GNU GPL **version 3**, verified by
   reading it). A fourteen-name probe across both `master` and `main` missed it, the GitHub API
   reports `NONE`, and the README says nothing about licensing. The tool is GPL-3.0. **A shallow
   clone and `ls` resolved in one call what eleven HTTP requests could not.**
2. **The licence can live only in the source headers.** `cth103/libsub` has **no licence file at
   all** — the shallow clone shows nothing licence-shaped at root — yet **73 of its source files
   carry a full GPL-2.0-or-later header** (`Copyright (C) 2014 Carl Hetherington … either version 2
   of the License, or (at your option) any later version`). It is unambiguously GPL-2.0+.

   **This is the inverse of the `rslstandard/rsl` trap from pass 5, and the pair is now the rule:**
   a repo with no licence file is *not* automatically all-rights-reserved, and a repo with no licence
   file is *not* automatically licensed either. `rsl` had no file and no headers → default copyright
   applies. `libsub` has no file and 73 headers → GPL-2.0+. **The distinguishing step is reading the
   source, and it costs one shallow clone.** Pass 8 established that a 404 is never by itself proof a
   licence is missing; this pass establishes the positive half: *absence of a licence file is not
   evidence of either answer.*

### The substrate — permissive, and the only place in this plane that is

| Repo | Licence | ★ / forks | Last push | Notes |
|---|---|---|---|---|
| [uclouvain/openjpeg](https://github.com/uclouvain/openjpeg) | **BSD-2-Clause** (reported `NOASSERTION`) | 1,123★ / 543f | 2026-09-05 | **The DCI-mandated codec.** Digital cinema is JPEG 2000 by specification, and this is the reference open implementation. Licence hides in a **ninth** way: `LICENSE` exists but opens with `/*` — the text is **wrapped in a C comment block**, so every scanner reads it as source and reports `NOASSERTION`. Verified by reading: "the 2-clauses BSD License, included below". |
| [cinecert/asdcplib](https://github.com/cinecert/asdcplib) | **BSD-3-Clause** (reported `NOASSERTION`) | 99★ / 65f | 2026-11-19 | **AS-DCP and AS-02 file access library — the industry's actual DCP/MXF implementation**, maintained by CineCert with support from D-Cinema manufacturers, and `ClairMeta`'s dependency. Licence is in `COPYING` (3,047B, "Copyright (c) 2003-2012, John Hurst", clause 3 = no-endorsement). **Permissive, active this month, and the correct foundation for a permissive theatrical build.** |
| [GrokImageCompression/grok](https://github.com/GrokImageCompression/grok) | **AGPL-3.0** (reported `NOASSERTION`) | 300★ / 63f | 2026-11-23 | Self-describes as "World's Leading Open Source JPEG 2000 Codec", and it is the fastest. **It is AGPL-3.0** (37,281B licence file, verified). Faster than OpenJPEG and unusable in a proprietary deliverable: the performance/licence trade-off in this plane is explicit and unavoidable. |
| [Netflix/photon](https://github.com/Netflix/photon) | Apache-2.0 | 259★ / 82f | 2026-11-20 | IMF validator — **already in this file**, and the bridge into this plane: IMF is the mastering format a DCP is made *from*. Apache-2.0, so the IMF side of the chain is permissive while the DCP side is not. |
| [IMFTool/IMFTool](https://github.com/IMFTool/IMFTool) | GPL-3.0 | 145★ / 16f | 2026-11-19 | Editing IMF CPLs and creating new versions of an existing IMF package. Active, and the copyleft counterpart to Photon. |

### ⚠️ The MXF container layer has been retired by its maintainers — measured, not assumed

The broadcast-grade MXF toolchain this plane depends on has been **archived or relocated across the
board**, and the most recently touched copy is a vendor fork:

| Repo | Licence | ★ / forks | Last push | State |
|---|---|---|---|---|
| [bbc/bmx](https://github.com/bbc/bmx) | BSD-3-Clause | 88★ / 41f | 2025-09-29 | **ARCHIVED** — the BBC's MXF read/write utilities, the highest-starred of the set |
| [Limecraft/ebu-libmxf](https://github.com/Limecraft/ebu-libmxf) | BSD-3-Clause | 17★ / 6f | 2024-11-15 | Active-ish; **EMEA vendor fork (Limecraft, Belgium) and the most recently touched copy in the family** |
| [BBC-archive/libMXF](https://github.com/BBC-archive/libMXF) | BSD-3-Clause | 15★ / 7f | 2023-11-22 | **Relocated to the BBC's `-archive` org** — the relocation is itself the finding |
| [sandflow/regxmllib](https://github.com/sandflow/regxmllib) | BSD-2-Clause | 39★ / 15f | 2026-11-22 | **ARCHIVED** — MXF→XML (RegXML, SMPTE ST 2001-1). Archived *four days before this pass* |

**The pattern**: the container format every DCP and every broadcast master is wrapped in is
permissively licensed and **no longer maintained by anyone with a public mandate.** The BBC retired
its stack into an archive org; the EBU's library last moved in 2013 and lives on only through a
Belgian vendor's fork; `regxmllib` was archived this month. This is the clearest case in the KB of
**permissive and abandoned beating copyleft and alive** — and it is the opposite risk from the
authoring layer above, where everything is alive and nothing is permissive.

### Key delivery (KDM) — the crudest measured zero in this entire KB

A KDM (Key Delivery Message) is the dated, per-screen cryptographic key **without which a film
does not play.** It gates every commercial screening on earth. The open-source estate for managing
them, in full:

| Repo | Licence | ★ | Last push | Notes |
|---|---|---|---|---|
| [PostPerfection/kdmcourier](https://github.com/PostPerfection/kdmcourier) | AGPL-3.0 | 1★ | 2026-11-13 | KDM manager for distributors; cinemas from FLM files, bookings. The most serious attempt, two weeks old |
| [theantiz/dcpkdm](https://github.com/theantiz/dcpkdm) | **none** | 1★ | 2026-03-06 | Automates KDM generation. Unlicensed |
| [tobiasmiosczka/KdmManager](https://github.com/tobiasmiosczka/KdmManager) | GPL-3.0 | 0★ | 2026-04-16 | For projectionists, auto-downloads KDMs |

`KDM cinema` returns **8 results whose star counts are 1, 1, 1, 0, 0, 0, 0, 0 — a top-eight sum of
three stars.** That ties healthcare's `medical necessity` (3) as the crudest number ever recorded in
this knowledge base, and it is attached to a harder object: medical necessity is a judgement, a KDM
is **a file with a published SMPTE schema**. The capability exists in exactly one place —
`asdcplib` can write KDMs, permissively — and **nothing open manages their lifecycle.** For a
circuit running 400 screens against 30 distributors, key-window expiry is a daily operational risk
with no open tooling and no commercial open alternative.

### Measurement note — the oracle, and a correction to this KB's 422 rule

- **`curl -sI https://github.com/<slug>` is useless from this session**: the agent proxy answers
  `HTTP/1.1 200 Connection Established` and then GitHub's HTML returns **403**, for repos that
  plainly exist. `git ls-remote https://github.com/<slug> HEAD` is the existence oracle (25/25 this
  pass), and `raw.githubusercontent.com` serves licence files normally (control request: 200).
- **The 422 rule from passes 8 and 9 holds but needed sharpening.** A `repo:<slug>` search returning
  422 while `git ls-remote` succeeds does mean the slug no longer serves under that name — it caught
  `Ymagis/ClairMeta` → `ClairMeta/ClairMeta` and `bbc/libMXF` → `BBC-archive/libMXF` this pass. **But
  `gh api repos/<slug>` does not disambiguate it:** both returned an identical
  `403 "GitHub access to this repository is not enabled for this session"`, which reads like a
  permissions problem and is not one. **The resolver is an unqualified keyword search** (`q='libMXF'`),
  which surfaced the new location and its forks in one call. And a new consequence worth watching
  for: when the new owner is an `*-archive` org, **the relocation is the finding** — it means the
  maintainer has formally retired the project.

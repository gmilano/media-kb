---
industry: media
region: Global
updated: 2026-11-22
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

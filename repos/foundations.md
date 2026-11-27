---
industry: media
region: Global
updated: 2026-11-27
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

## The description & semantic-interchange plane — foundations, measured 2026-11-26 (pass 11)

Everything below was verified in this session: existence by `git ls-remote`, stars/forks/push date by
`search/repositories`, and **licence by fetching the actual file over the raw channel**. Where the
GitHub API reported `NOASSERTION`, the real licence is given with the filename and byte count that
proves it.

### Tier 1 — The interchange schemas, and they are permissively licensed

| Project | Repo | License | Stars / forks | Last push | Role |
|---|---|---|---|---|---|
| schema.org | https://github.com/schemaorg/schemaorg | Apache-2.0 | 6320★ / 975f | 2026-11-25 | `NewsArticle`, `VideoObject`, `ClaimReview`. The vocabulary AI answer engines actually consume |
| ninjs (News in JSON) | https://github.com/iptc/newsinjson | MIT | 47★ / 10f | 2026-11-24 | IPTC's JSON news format; schema + examples + generator. Versions 1.7, 2.3, 3.2 |
| NewsML-G2 | https://github.com/iptc/newsml-g2 | **CC-BY-4.0** (`LICENSE`, 901 B) | 20★ / 5f | 2026-11-20 | The XML news interchange standard, v2.34, with unit tests |
| python-newsmlg2 | https://github.com/iptc/python-newsmlg2 | MIT | 6★ / 4f | 2026-11-11 | IPTC's own Python library for NewsML-G2, v1.0 |
| Video Metadata Hub | https://github.com/iptc/video-metadata-hub | MIT (`LICENSE`, 1066 B) | 2★ / 0f | **2026-11-25** | IPTC's video metadata mapping — pushed the day before this pass |
| IPTC catalog | https://github.com/iptc/catalog | MIT (`LICENSE`, 1061 B) | 3★ / 0f | 2026-11-17 | Catalog files resolving IPTC scheme URIs |
| Sports NewsCodes | https://github.com/iptc/sports-newscodes | **CC-BY-4.0** (`LICENSE`, 444 B) | 1★ / 0f | 2023-09-29 | **Primary evidence for the whole vocabulary licence — see below** |
| EBUCorePlus | https://github.com/ebu/ebucoreplus | **MIT** | 30★ / 8f | 2026-10-02 | EBU's current flagship media-enterprise ontology, v2.0/v2.1 |
| awesome-broadcasting | https://github.com/ebu/awesome-broadcasting | CC0-1.0 | 1805★ / 237f | 2026-09-30 | EBU's own curated index; the highest-starred thing in the EBU org |

### Tier 1 — Vocabulary servers and description tooling

| Project | Repo | License | Stars / forks | Last push | Role |
|---|---|---|---|---|---|
| OpenRefine | https://github.com/OpenRefine/OpenRefine | BSD-3-Clause | 12118★ / 2214f | 2026-11-24 | Messy-metadata cleanup **and Wikidata reconciliation** — the practical bridge from a spreadsheet of titles to linked entities |
| ExifTool | https://github.com/exiftool/exiftool | GPL-3.0 (`LICENSE`, 35149 B) | 5319★ / 508f | 2026-11-16 | Read/write XMP + IPTC photo metadata. Copyleft — a tool you *run*, not a library you link |
| MediaInfo | https://github.com/MediaArea/MediaInfo | BSD-2-Clause | 2079★ / 202f | 2026-11-24 | Extracts technical metadata and **exports EBUCore and PBCore 1.2/2.1 directly** |
| Apache Jena | https://github.com/apache/jena | Apache-2.0 | 1511★ / 745f | 2026-11-25 | RDF/SPARQL store; the triple store Skosmos runs on (Fuseki) |
| Exiv2 | https://github.com/Exiv2/exiv2 | GPL-2.0 (`COPYING`, 18092 B) | 1174★ / 350f | 2026-11-23 | C++ XMP/IPTC/Exif library |
| **Skosmos** | https://github.com/NatLibFi/Skosmos | **MIT** (`LICENSE`, 1376 B) | 269★ / 105f | 2026-11-18 | SKOS thesaurus browser/publisher over a SPARQL endpoint; the software behind Finto |
| **TemaTres** | https://github.com/tematres/TemaTres-Vocabulary-Server | **GPL-2.0-or-later** — declared in `readme.md` and in every source header; **there is no `LICENSE` file** | 142★ / 11f | **2026-11-25** | Vocabulary/thesaurus server. **Argentine-built** (© Diego Ferreyra, `tematres@r020.com.ar`). See LATAM in `intel/market.md` |
| Finto-data | https://github.com/NatLibFi/Finto-data | **MIXED** (`LICENSE`, 1765 B: code under `tools/` generally MIT, data varies) | 21★ / 6f | 2026-11-26 | The vocabulary data behind Finto; read the licence per-directory |

### Tier 3 — Verified traps. These exist, are starred, and grant you nothing

| Project | Repo | Stars | Last push | The trap |
|---|---|---|---|---|
| **EBUCore** | https://github.com/ebu/ebucore | 27★ / 7f | 2026-08-18 | **CC BY-NC-SA 3.0 — NonCommercial** (`LICENSE.md`, 386 B). EBU's long-standing descriptive/technical metadata spec (Tech 3293), still in active use, **cannot be used in commercial client work**. Its successor EBUCorePlus is MIT. *The predecessor is the one most broadcasters have deployed.* |
| IPTC Sport Schema | https://github.com/iptc/sport-schema | 38★ / 3f | 2026-10-01 | **No licence file** on `master` or `main`; control `README.md` on `master` = 200, so the filenames are not at fault |
| IPTC RightsML dev | https://github.com/iptc/rightsml-dev | 5★ / 2f | 2026-07-06 | **No licence file**; control passes on `master` |
| JSON for Concepts & Vocabularies | https://github.com/iptc/json-for-concepts-vocabularies | 4★ / 0f | 2017-10-20 | **No licence file**; control passes on `master` |
| jebu-core | https://github.com/mikrosimage/jebu-core | 3★ / 2f | **2018-06-13** | Java port of EBUCore Tech 3293 incl. Audio Definition Model. GPL-2.0 and **dead for 8 years** |

The IPTC repos with no licence are the `rslstandard/rsl` trap of pass 5, repeated inside an
organisation that licenses its flagship standards CC BY 4.0. **Openness at the org level does not
propagate to the repo level.** Three of twenty IPTC repos grant nothing; use the published spec, not
the repo contents.

### Primary evidence for the vocabulary licence — and why it mattered

`iptc.org` and `cv.iptc.org` **do not resolve from this session** (outside the allowed network
domains), so IPTC's own NewsCodes server could not be read — the same channel limit as `new.ddex.net`
in pass 8. The licence was established from a *harder* source instead: IPTC's own repository files.

`iptc/sports-newscodes/master/LICENSE` (444 B) states verbatim:

> Copyright (c) 2016 IPTC — **The Creative Commons Attribution (CC BY) 4.0 license applies to all
> NewsCodes**

and `iptc/newsml-g2/master/LICENSE` (901 B) grants:

> Adapt — remix, transform, and build upon the material **for any purpose, even commercially**.

That is the sentence that makes this plane commercially buildable, from IPTC's own repository, not
from a vendor summary. **IPTC Media Topics (~1,100 terms after retirements) being CC BY 4.0 is
therefore primary-sourced as to the licence family, and secondary-sourced as to the term count and
the 2-3 month update cadence**, which came from search snippets of the unreachable iptc.org and
disagree with each other (one IPTC page says "at least once a year"). Treat the cadence as unverified.

### Three method corrections, reusable across all twelve industries

**(1) `curl` is not a valid existence oracle in this session, and a 403 is not a 404.** The task
instructions say to verify every URL with `curl -sI`. Run against the 52 GitHub URLs in this pass,
curl returned **403 for all 52 and `000` for every non-GitHub domain — one single 200 in 60 URLs.**
Every one of those 52 repos exists. The 403 is the agent proxy refusing github.com HTML; the `000` is
a blocked domain. `git ls-remote --exit-code` then confirmed **52/52 exist, 0 dead.** A pass that
believed curl would have deleted its entire findings list as "404s".

**(2) `search/repositories` is *not* a complete existence oracle either — and this is the converse of
the rule above.** `Islandora/islandora` is absent from the search index entirely (`islandora in:name`
returns 1317 results without it), yet `git ls-remote` confirms it exists and the raw channel returns
its `LICENSE` (GPL-2.0, 18092 B). Use search for *metrics*, `ls-remote` for *existence*. Neither
substitutes for the other.

**(3) The licence probe needed a new filename, and the control request is what revealed it.**
TemaTres returned 404 for every licence name **and** for `README.md` on both branches, which by pass
8's rule means the filenames were wrong rather than the licence missing. A shallow clone showed why:
the file is **`readme.md`, lowercase**, and there is no licence file at all — the grant lives in
`readme.md` and in every source header. Add lowercase `readme.md` to the control set. Running total
of conventions this KB has had to learn: `LICENSE`, `LICENSE.md`, `LICENSE.txt`, `license.txt`,
`COPYING`, `COPYING.md`, and now `readme.md` for the control.

## The sound, music & immersive-audio plane — measured 2026-11-26 (pass 12)

Everything between the microphone and the loudness meter. Loudness *measurement* is pass 4 and is not
repeated here; `pyannote` and `librosa` arrived in passes 7 and 5 and are cross-referenced, not
re-listed. All 65 URLs in this pass resolve by `git ls-remote`; every licence below was read from the
repository's own licence file, not from a directory or an API field.

### ⛔ Read this before choosing anything in this plane

The licence outcome is predicted by **where the code runs**, not by who wrote it:

- Runs **beside** the proprietary host (library, renderer, converter, reference implementation) →
  **permissive**, 7/7 measured.
- Runs **inside** the proprietary host (VST/AU/AAX plugin, plugin framework, DAW engine) → **dual or
  copyleft**, 6/6 measured, no counterexample.

Design the deliverable accordingly. A rendering or analysis service is clean; a plugin in the client's
DAW drags AGPL or a commercial fee underneath it.

### Immersive / next-generation audio — the standards layer, permissive and institutional

This is the healthiest permissive corner found in any audio layer, and it is **EMEA-built**: the EBU,
the BBC and the (now closed) IRT wrote most of it.

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| https://github.com/ebu/ebu_adm_renderer | BSD-3-Clause-Clear | 105 | 2026-02-11 | **The reference ITU ADM Renderer (ITU-R BS.2127) in Python.** The normative implementation — what "correct" means for object-based audio |
| https://github.com/ebu/bear | Apache-2.0 | 32 | 2026-08-14 | **Binaural EBU ADM Renderer**, BBC copyright. The permissive path to headphone rendering of ADM |
| https://github.com/ebu/libadm | Apache-2.0 | 51 | 2026-08-07 | C++ library for the ADM metadata model (ITU-R BS.2076) |
| https://github.com/ebu/libbw64 | Apache-2.0 | 43 | 2024-04-13 | BW64 (Broadcast Wave 64-bit) container I/O. **Dormant two years — stable format, low churn; verify before depending** |
| https://github.com/immersive-audio-live/ADM-OSC | MIT | 91 | 2026-10-16 | Object positions over OSC — the live/show-control bridge for immersive audio |
| https://github.com/GoogleChrome/omnitone | Apache-2.0 | 919 | 2026-10-22 | Browser ambisonic renderer; the highest-starred permissive spatial renderer |
| https://github.com/polarch/JSAmbisonics | BSD-3-Clause | 182 | 2026-09-17 | Higher-order ambisonic processing in Web Audio |
| https://github.com/hoene/libmysofa | BSD-3-Clause (API reports `NOASSERTION`) | 180 | 2026-10-25 | Reads SOFA HRTF files — the input any binaural renderer needs |

**Constrained, and each for a different reason:**

| Repo | License | Stars | Last push | Constraint |
|---|---|---|---|---|
| https://github.com/ebu/ear-production-suite | **GPL-3.0-or-later** | 126 | 2026-11-18 | The actual ADM **production** toolset (VST plugins, Reaper-optimised). Active, 62 open issues. Licence file is at **`packaging/LICENSE.md`, not the root** |
| https://github.com/leomccormack/Spatial_Audio_Framework | **ISC core, GPL-2.0 with optional modules** | 771 | 2026-05-30 | The licence **is decided by your build configuration** — second instance of this category after Chromaprint (p5) |
| https://github.com/videolan/libspatialaudio | **LGPL-2.1+ or commercial** | 325 | 2026-07-14 | Ambisonic encode/decode/binauralise. Note the owner is `videolan`, **not** `videolabs` |
| https://github.com/resonance-audio/resonance-audio | Apache-2.0 | 543 | 2022-09-08 | **ARCHIVED.** Google's spatial engine — permissive and dead; read it, do not depend on it |
| https://github.com/spatialaudio/python-sofa | MIT | 28 | 2021-03-08 | Dormant five years |
| https://github.com/tu-studio/IEMPluginSuite | GPL-3.0 | 12 | 2026-10-13 | **A fork.** The canonical IEM Plugin Suite lives on `git.iem.at`, unreachable through this proxy — recorded as unverifiable, not absent |

### Speech & dialogue restoration — the permissive layer that actually does post-production work

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| https://github.com/xiph/rnnoise | BSD-3-Clause | 5,982 | 2025-02-22 | The classic recurrent denoiser; embedded everywhere, low churn |
| https://github.com/Rikorose/DeepFilterNet | MIT **or** Apache-2.0 | 5,107 | 2026-11-06 | Real-time full-band suppression — current best permissive dialogue cleanup |
| https://github.com/k2-fsa/sherpa-onnx | Apache-2.0 | 16,241 | 2026-11-24 | On-device runtime for ASR/TTS/enhancement; the deployment layer |
| https://github.com/speechbrain/speechbrain | Apache-2.0 | 11,951 | 2026-11-25 | Separation, enhancement, diarisation in one toolkit |
| https://github.com/asteroid-team/asteroid | MIT | 2,605 | 2026-11-03 | Source separation, maintained |
| https://github.com/deezer/spleeter | MIT | 28,539 | 2026-10-28 | Stem separation; **the maintained alternative to archived Demucs** |

Cross-reference: `pyannote/pyannote-audio` (MIT, 10,842★, 2026-11-24) for diarisation — already in
this KB from pass 7; it is the speaker-attribution step of every dialogue workflow below.

### Audio I/O, codecs and DSP substrate

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| https://github.com/xiph/opus | BSD-3-Clause (read from `COPYING`) | 3,395 | 2026-11-26 | The codec; IETF-standard, pushed the day of this pass |
| https://github.com/libsndfile/libsndfile | LGPL-2.1 | 1,736 | 2026-10-28 | The file-I/O layer under most audio tooling |
| https://github.com/pure-data/pure-data | "Standard Improved BSD" | 2,130 | 2026-11-19 | Dataflow audio environment — **permissive, unusually for this tier** |
| https://github.com/csound/csound | LGPL-2.1 | 1,533 | 2026-11-25 | Synthesis engine, embeddable under LGPL |
| https://github.com/grame-cncm/faust | GPL-2.0 + exception | 3,222 | 2026-11-25 | DSP language that **compiles to plugins** — the exception is what makes that usable |
| https://github.com/Tonejs/Tone.js | MIT | 14,959 | 2026-11-20 | Web Audio framework; the permissive choice for browser-delivered audio |
| https://github.com/jackaudio/jack2 | GPL-2.0 / LGPL | 2,461 | 2026-01-07 | Low-latency audio server for studio routing |

### The host tier — and it is copyleft or dual, without exception

Listed as **context rows**, not recommendations. Each is a real system a client may already run.

| Repo | License | Stars | Last push | Note |
|---|---|---|---|---|
| https://github.com/juce-framework/JUCE | **AGPL-3.0 or commercial** | 9,180 | 2026-11-24 | The industry's default plugin framework. **Price the commercial licence before promising a plugin** |
| https://github.com/Tracktion/tracktion_engine | **GPL-3.0 or commercial** | 1,471 | 2026-11-25 | Embeddable DAW engine, same model |
| https://github.com/audacity/audacity | GPL-3.0 | 19,185 | 2026-11-25 | The most-installed audio editor on earth |
| https://github.com/LMMS/lmms | GPL-2.0 | 10,736 | 2026-11-25 | Pattern-based DAW |
| https://github.com/sonic-pi-net/sonic-pi | **MIT source, GPLv3 by linkage** | 12,293 | 2026-11-25 | The headline licence is not the distribution obligation |
| https://github.com/supercollider/supercollider | GPL-3.0 | 6,858 | 2026-11-26 | Synthesis server + language |
| https://github.com/mixxxdj/mixxx | GPL-2.0-or-later | 7,445 | 2026-11-25 | DJ/playout system |
| https://github.com/Ardour/ardour | GPL-2.0 (read from `COPYING`) | 5,459 | 2026-11-25 | Full DAW with surround and Dolby-capable busses |
| https://github.com/zrythm/zrythm | **AGPL-3.0 + §7 additional terms** (REUSE pointer) | 3,223 | 2026-11-26 | Licence declared by reference, not inline |
| https://github.com/spotify/pedalboard | GPL-3.0 | 6,513 | 2026-11-09 | Python audio effects — **GPL, despite the permissive habits of its publisher** |

### Music, notation and MIR — permissive at the library, copyleft at the application

The same gradient, one tier down: the *formats and libraries* are permissive; the *applications
musicians install* are GPL.

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| https://github.com/librosa/librosa | ISC | 9,166 | 2026-11-25 | The audio-analysis baseline (already cited in p5) |
| https://github.com/cuthbertLab/music21 | BSD-3-Clause | 2,635 | 2026-11-18 | Computational musicology toolkit, MIT-origin |
| https://github.com/spotify/basic-pitch | Apache-2.0 | 6,127 | 2025-11-13 | Audio-to-MIDI transcription — permissive, unlike its sibling `pedalboard` |
| https://github.com/mido/mido | MIT | 1,662 | 2026-11-09 | MIDI objects/IO in Python |
| https://github.com/craffel/pretty-midi | MIT | 1,052 | 2026-11-08 | MIDI manipulation and analysis |
| https://github.com/Natooz/MidiTok | MIT | 909 | 2026-11-25 | MIDI tokenisation for sequence models — the bridge from music to an LLM |
| https://github.com/0xfe/vexflow | MIT (read from `LICENSE`) | 4,409 | 2025-03-05 | Music notation rendering in the browser |
| https://github.com/paulrosen/abcjs | MIT (read from `LICENSE.md`) | 2,378 | 2026-11-18 | ABC-notation rendering and playback |
| https://github.com/rism-digital/verovio | LGPL-3.0 | 984 | 2026-11-25 | MEI/MusicXML engraving library — the bridge to the description plane (p11) |
| https://github.com/beetbox/beets | MIT | 15,983 | 2026-11-26 | Music library management and metadata — permissive, and pushed the day of this pass |
| https://github.com/metabrainz/picard | GPL-2.0 | 5,408 | 2026-11-25 | MusicBrainz tagger; pairs with the fingerprinting layer in p5 |
| https://github.com/musescore/MuseScore | **GPL-3.0 with a font exception** | 15,489 | 2026-11-25 | Notation application. The added exception is why GitHub reports `NOASSERTION` |
| https://github.com/lilypond/lilypond | GPL-3.0 | 711 | 2026-11-26 | Engraving system; the GitHub repo is a mirror of a GitLab-hosted project |
| https://github.com/aubio/aubio | GPL-3.0 | 3,792 | 2026-04-10 | Onset, pitch and beat detection |
| https://github.com/MTG/essentia | **AGPL-3.0** | 3,819 | 2026-11-18 | Large MIR feature library; AGPL reaches a hosted service |
| https://github.com/CPJKU/madmom | **BSD code / CC BY-NC-SA 4.0 models** | 1,745 | 2026-03-20 | **Do not ship.** The pretrained models — which is the whole product — are non-commercial |

### Standards bodies and documents, not code — demoted on sight (the rule from pass 4 holds)

- **ITU-R BS.2076** (Audio Definition Model), **BS.2127** (ADM Renderer), **BS.2051** (loudspeaker
  configurations) — the normative specifications the EBU repos implement. Specifications, not
  dependencies.
- **ATSC A/342 Part 3** (MPEG-H system) and the **ATSC 3.0 suite approved 2026-04-14** — the North
  American carriage standard. The encoder implementations are Fraunhofer's and are **not open**; the
  open stack reaches ADM and stops.
- **`w3c/musicxml`** exists (confirmed by `ls-remote`) but is not resolvable through this session's
  search index; it is a specification repository in any case.

## The subscription, entitlement & reader-revenue plane — measured 2026-11-26 (pass 13)

Everything below was measured on 2026-11-26 via `search/repositories`, with existence confirmed by
`git ls-remote` (33/33) and every `NOASSERTION` resolved by reading the actual licence file. This
plane is the subscriber half of media revenue; pass 2 covered the advertising half.

### ⛔ Read this before choosing anything in this plane

The licence shape is **positional**, and the position that matters is distance from the recurring
charge. Identity and entitlement are Apache-2.0 and healthy. Billing is AGPL-dominant with exactly
one permissive anchor. The publisher-facing funnel is one MIT repo at 138 stars. Choose the layer
you need before you choose a project, because the licence answer changes completely between layers —
the full gradient table is in `agents/top.md`.

### Entitlement & authorization — the healthiest permissive layer in this plane

The Zanzibar-style engines are the right abstraction for subscriber rights: territory, concurrency,
device count, windowing and offline rights are all *relationships*, not roles.

| Repo | License | Stars | Last push | Why it matters here |
|---|---|---|---|---|
| [authzed/spicedb](https://github.com/authzed/spicedb) | Apache-2.0 | 7,243 | 2026-11-24 | Zanzibar-style relationship database. Best fit for entitlement graphs with territory and device limits. |
| [openfga/openfga](https://github.com/openfga/openfga) | Apache-2.0 | 6,197 | 2026-11-25 | CNCF-hosted; lighter operationally, same modelling idea. |
| [ory/keto](https://github.com/ory/keto) | Apache-2.0 | 5,424 | 2026-09-04 | Permission server. Permissive, real, slower cadence (~3 months). |
| [cerbos/cerbos](https://github.com/cerbos/cerbos) | Apache-2.0 | 4,669 | 2026-11-25 | Policy-as-code decisions, externalised to policy files. Open-core; engine is Apache-2.0. |
| [casbin/casbin](https://github.com/casbin/casbin) | Apache-2.0 | n/m | n/m | Embeddable authz library, many languages. Licence read from the LICENSE file; stars/push **not measurable** (absent from the search index — see `agents/top.md` method correction). |
| [Permify/permify](https://github.com/Permify/permify) | **AGPL-3.0** | 5,975 | 2026-11-26 | The one non-permissive engine of the group. Prefer SpiceDB/OpenFGA. |
| [warrant-dev/warrant](https://github.com/warrant-dev/warrant) | Apache-2.0 | 1,339 | 2025-12-05 | Centralized authorization service. **~12 months without a push** — do not start new work here. |

### Identity — the gate in front of entitlement

| Repo | License | Stars | Last push | Note |
|---|---|---|---|---|
| [keycloak/keycloak](https://github.com/keycloak/keycloak) | Apache-2.0 | 38,060 | 2026-11-26 | The permissive default for a subscriber estate. |
| [ory/kratos](https://github.com/ory/kratos) | Apache-2.0 | 13,977 | 2026-07-29 | Headless identity. Apache-2.0, ~4 months quiet. |
| [zitadel/zitadel](https://github.com/zitadel/zitadel) | **AGPL-3.0** | 15,654 | 2026-11-25 | Capable, but AGPL at the identity tier. |
| [supertokens/supertokens-core](https://github.com/supertokens/supertokens-core) | **Open core + proprietary `ee/`** | 15,347 | 2026-11-25 | GitHub says `NOASSERTION`; LICENSE.md says everything outside `ee/` is open and `ee/` has separate terms. |

### Billing, metering & payments — AGPL-dominant, with one Apache-2.0 anchor

| Repo | License | Stars | Last push | Note |
|---|---|---|---|---|
| [killbill/killbill](https://github.com/killbill/killbill) | **Apache-2.0** | 5,869 | 2026-11-26 | **The anchor.** Plans, trials, proration, dunning, invoicing. The only mature permissive billing engine found in this plane. |
| [juspay/hyperswitch](https://github.com/juspay/hyperswitch) | **Apache-2.0** | 45,917 | 2026-11-26 | Payments orchestration across PSPs. Largest permissive project in the plane. APAC-origin (Juspay, India). |
| [openmeterio/openmeter](https://github.com/openmeterio/openmeter) | **Apache-2.0** | 2,471 | 2026-11-26 | Usage metering/aggregation — meter consumption without adopting an AGPL platform. |
| [getlago/lago](https://github.com/getlago/lago) | AGPL-3.0 | 10,922 | 2026-11-25 | Most-starred billing platform here. Network copyleft. |
| [flexprice/flexprice](https://github.com/flexprice/flexprice) | AGPL-3.0 | 6,874 | 2026-11-26 | Usage-based pricing/billing, very active. |
| [meteroid-oss/meteroid](https://github.com/meteroid-oss/meteroid) | AGPL-3.0 | 1,370 | 2026-11-26 | Pricing and billing infrastructure. |
| [tabloy/keygate](https://github.com/tabloy/keygate) | AGPL-3.0 | 279 | 2026-11-23 | Licence/subscription key management. |
| [laravel/cashier-stripe](https://github.com/laravel/cashier-stripe) | MIT | 2,550 | 2026-11-17 | MIT, but a Stripe binding — a single PSP as a hard dependency, not a billing engine. |
| [billabear/billabear](https://github.com/billabear/billabear) | **Undetermined** | 760 | 2026-09-13 | `NOASSERTION` and **no retrievable LICENSE file** at the default branch. Unresolved, not merely unlabelled. |
| [service-bot/servicebot](https://github.com/service-bot/servicebot) | GPL-3.0 | 956 | 2021-01-12 | **Dormant ~5 years.** Recorded so it is not re-adopted. |

### Reader revenue — the whole layer, and it is one repository

| Repo | License | Stars | Last push | What it contains |
|---|---|---|---|---|
| [remp2020/remp](https://github.com/remp2020/remp) | **MIT** | 138 | 2026-11-25 | README read in full. A monorepo of four services: **SSO** (auth across the tools), **Beam** (pageview/conversion event tracking, aggregation, user segments), **Campaign** (banner and offer targeting, driven by Beam segments), **Mailer** (newsletter templates, batch send, A/B testing, subscription APIs). Docker-compose install. Built and run by **Denník N (Slovakia)** — EMEA-origin. |
| [remp2020/crm-skeleton](https://github.com/remp2020/crm-skeleton) | MIT | 8 | 2026-11-06 | CRM skeleton with core modules — the subscriber-record side of REMP. |
| [remp2020/pythia-tools](https://github.com/remp2020/pythia-tools) | **NONE** | 4 | 2023-03-20 | Churn-propensity aggregation over Beam data. **No licence and dormant since 2023** — the one piece that would have been the churn layer is the one piece that is unusable. |

That last row is the sharpest single fact in this pass: the only open reader-revenue platform in
existence *did* build a churn-propensity component, and it is unlicensed and three years dead.

### Churn & lifetime-value — permissive substrate, no media wiring

| Repo | License | Stars | Last push | Note |
|---|---|---|---|---|
| [CamDavidsonPilon/lifelines](https://github.com/CamDavidsonPilon/lifelines) | MIT | 2,623 | 2026-03-07 | Survival analysis. The statistically honest way to model subscriber tenure — censoring is the whole problem in churn, and this handles it. |
| [CamDavidsonPilon/lifetimes](https://github.com/CamDavidsonPilon/lifetimes) | MIT | 1,476 | 2024-06-28 | **ARCHIVED.** BG/NBD and Gamma-Gamma CLV models. Vendor it; expect no fixes. |

### ⛔ The licence finding of this pass: Directus's MSCL-1.0-GPL, read in full — and it has a professional-services clause

`verticals/solutions.md` already carries the correction that Directus is **not** BSL and **not**
OSI-approved. This pass read the 4,481-byte licence file itself, and three clauses matter to a
services firm:

1. **Competing Use is the only prohibition.** A "Permitted Purpose is any purpose other than a
   Competing Use", where a Competing Use means making the Software available to a party "that
   competes with the Licensor's commercial offerings of the Software itself, where Licensor imposes
   a license fee". It is a non-compete, not a general commercial restriction.
2. **Professional services are explicitly permitted.** The Permitted Purposes list names, verbatim,
   use "in connection with professional services that you provide to a licensee using the Software
   in accordance with these Terms and Conditions". **This is the clause that decides whether Globant
   may build on Directus for a client, and it says yes** — provided the client's own use is itself a
   Permitted Purpose. Internal use by the client is explicitly listed as one.
3. **There is a dated escape hatch.** A "Grant of Future License" irrevocably licenses each version
   under **GPL-3.0 on the fourth anniversary** of the date that version was made available. So
   Directus is delayed-open on a four-year clock, and the destination is GPL-3.0 — copyleft, not
   permissive. A version adopted today becomes GPL-3.0 in 2030; it never becomes MIT or Apache.

This is the KB's **delayed-open** category (trend 34) with its terms finally pinned down, and the
professional-services carve-out is a genuinely useful fact that no licence scanner will surface,
because scanners report the SPDX id — and here there isn't one.

### Split licences confirmed by directory boundary — three projects, one pattern

GitHub reports `NOASSERTION` for all three. In each case the LICENSE file says the same thing: the
project is MIT **except** for named directories, which carry separate commercial terms. The licence
is a *path*, not an identifier.

| Repo | Open part | Carved-out path |
|---|---|---|
| [PostHog/posthog](https://github.com/PostHog/posthog) | MIT Expat | `ee/` |
| [growthbook/growthbook](https://github.com/growthbook/growthbook) | MIT Expat | `packages/back-end/src/enterprise`, `packages/front-end/enterprise`, `packages/shared/src/enterprise` |
| [supertokens/supertokens-core](https://github.com/supertokens/supertokens-core) | open | `ee/` |

The practical rule: **for these projects, "is it MIT?" is the wrong question. "Does my build import
anything under that path?" is the right one** — and it is answerable with a dependency graph, not a
licence scan.

## The localization substrate — measured 2026-11-26 (pass 14)

**49 distinct repository slugs were checked with `git ls-remote` on 2026-11-26: 47 resolve, 2 do
not** — and both failures are recorded as informed gaps below rather than dropped silently.
Metadata (stars, forks, licence, push date) was read from the GitHub `search/repositories` API the
same day. **None of the 47 appeared anywhere in this KB before this pass.**

⚠️ **Method warning for every future pass of every industry in this rotation:**
`gh api repos/<owner>/<name>` returned **`Not Found` for all eleven well-known repos tested through
it**, including `WeblateOrg/weblate` — which the `search/repositories` endpoint simultaneously
reported at 6,185★. In this environment the GitHub *repos* endpoint is scoped to the session's own
repositories, so **its 404 is an access artefact and carries no information about existence.** A pass
that trusted it would have deleted Weblate, Pontoon, LibreTranslate and COMET from this KB as dead
links. `git ls-remote` is the existence oracle; `search/repositories` with `q=repo:<slug>` is the
metadata oracle. Nothing else.

### Tier 1 — the job formats: XLIFF and friends (maintained, permissive, boring, reliable)

XLIFF is the format that carries **this week's work** out to translators and back. It is well served.

| Repo | Licence | Stars | Pushed | Role |
|---|---|---|---|---|
| [vslavik/poedit](https://github.com/vslavik/poedit) | MIT | 2,061 | 2026-11-09 | The desktop editor for PO, XLIFF and JSON. The single most-starred permissive tool in this plane, and the one a human linguist actually sits in front of. |
| [locize/xliff](https://github.com/locize/xliff) | MIT | 91 | 2026-10-31 | `xliff2js` / `js2xliff` converters. Small, current, MIT — the right pick for a pipeline step. |
| [maxprograms-com/OpenXLIFF](https://github.com/maxprograms-com/OpenXLIFF) | EPL-1.0 | 86 | 2026-11-03 | Java filters to **create, merge and validate** XLIFF 1.2, 2.0, 2.1 **and 2.2**. The most standards-complete converter found, and the practical substitute for Okapi (below). |
| [daniel-sc/ng-extract-i18n-merge](https://github.com/daniel-sc/ng-extract-i18n-merge) | MIT | 224 | 2026-10-20 | Extract/merge XLIFF for Angular. Framework-specific, but proof the format has live tooling. |
| [microsoft/XLIFF2-Object-Model](https://github.com/microsoft/XLIFF2-Object-Model) | ⚠️ NOASSERTION | 92 | 2023-06-06 | Microsoft's XLIFF 2.0 object model. **Dormant since 2023** and licence unresolved — reference only. |

### Tier 2 — the asset format: TMX, and the emptiest table in this file

TMX is the format that carries the **accumulated translation memory** — the client's decade of paid
translation, and the only artefact that makes them portable between vendors. It is abandoned.

| Repo | Licence | Stars | Pushed | State |
|---|---|---|---|---|
| [bitextor/bitextor](https://github.com/bitextor/bitextor) | GPL-3.0 | 302 | 2024-11-11 | Generates translation memories from multilingual websites. **The #1 result for both "translation memory" and "tmx translation memory" — and dormant two years.** Strong GPL: keep it a separate process. |
| [maxprograms-com/HybridTM](https://github.com/maxprograms-com/HybridTM) | EPL-1.0 | 7 | 2026-07-26 | A hybrid translation-memory **engine**. Alive, permissive-ish (weak file-level copyleft) — and seven stars. |
| [yasslab/konjak](https://github.com/yasslab/konjak) | MIT | 12 | 2021-08-21 | TMX tools for Ruby. MIT and readable; dormant since 2021. |
| [GregoryVigoTorres/sdltm2tmx](https://github.com/GregoryVigoTorres/sdltm2tmx) | GPL-3.0 | 8 | 2023-10-13 | Converts proprietary SDL `.sdltm` memories to TMX 1.4 — i.e. the **vendor-exit tool**. 8 stars. |
| [camertron/tmx-parser](https://github.com/camertron/tmx-parser) | ⚠️ none per API (unprobed) | 6 | 2015-07-24 | TMX parser. Last touched 2015. |

**The measurement:** the entire TMX estate is `302★ (dead) → 17 → 12 → 8 → 7 → 6 → 6 → 4`.
**Nothing above 17 stars is alive.** Compare Tier 1, where the job format alone carries 2,061★ of
maintained MIT tooling. Same discipline, same decade, same standards body — opposite outcome.

### Tier 3 — the MT engines (where the licence decides the business model)

| Repo | Licence | Stars | Pushed | Note |
|---|---|---|---|---|
| [LibreTranslate/LibreTranslate](https://github.com/LibreTranslate/LibreTranslate) | AGPL-3.0 | 17,851 | 2026-11-25 | The self-hosted MT API everyone names. Network copyleft. |
| [argosopentech/argos-translate](https://github.com/argosopentech/argos-translate) | **MIT** | 6,696 | 2026-11-17 | The engine underneath it. **Pinned by LibreTranslate's own `pyproject.toml` as `argos-translate-lt==1.12.1`.** |
| [argosopentech/argos-train](https://github.com/argosopentech/argos-train) | MIT | 158 | 2026-06-26 | Training scripts — the route to a client-specific, domain-tuned engine. |
| [LibreTranslate/LTEngine](https://github.com/LibreTranslate/LTEngine) | AGPL-3.0 | 215 | 2026-11-20 | LLM-backed local MT, API-compatible with LibreTranslate. |
| [NiuTrans/NiuTrans.SMT](https://github.com/NiuTrans/NiuTrans.SMT) | GPL-2.0 | 163 | 2024-07-17 | Statistical MT. Historical interest; superseded by neural. Dormant. |

### Tier 4 — terminology: small, permissive, and alive at the margin

Terminology (which word the brand uses in es-MX versus es-AR) is a *judgment* asset, and the pattern
holds — but less brutally than elsewhere, because termbases have an ISO interchange format (TBX).

| Repo | Licence | Stars | Pushed | State |
|---|---|---|---|---|
| [gaois/terminologue](https://github.com/gaois/terminologue) | MIT | 76 | 2026-11-24 | Open terminology-management tool. **MIT and actively pushed** — the single best permissive pick in this tier. |
| [translate/terminator](https://github.com/translate/terminator) | GPL-3.0 | 49 | 2022-04-22 | Terminology-management web platform. Dormant since 2022. |
| [diegoberaldin/MetaTerm](https://github.com/diegoberaldin/MetaTerm) | GPL-3.0 | 19 | 2023-06-11 | Terminology-management desktop solution. Dormant since 2023. |

### Tier 5 — quality, and the sharpest measurement of the law in this KB

Split the single word "quality" by **who has to agree on the number**, and the estate splits with it.

| Repo | Licence | Stars | Pushed | What kind of quality |
|---|---|---|---|---|
| [mjpost/sacrebleu](https://github.com/mjpost/sacrebleu) | Apache-2.0 | 1,266 | 2026-08-20 | **Computable.** Reference BLEU with versioned, reproducible test sets. |
| [Unbabel/COMET](https://github.com/Unbabel/COMET) | Apache-2.0 | 792 | 2026-04-21 | **Computable.** Neural MT evaluation — the current state of the art metric. |
| [Unbabel/OpenKiwi](https://github.com/Unbabel/OpenKiwi) | AGPL-3.0 | 236 | 2022-06-23 | **Predictive** (quality estimation without a reference). **Dead since 2022.** |
| [NJUNLP/njuqe](https://github.com/NJUNLP/njuqe) | MIT | 12 | 2025-09-10 | **Predictive.** MIT, 12 stars. |
| [BYU-TRG-Team/mqm-scorecard](https://github.com/BYU-TRG-Team/mqm-scorecard) | Apache-2.0 | **1** | 2025-06-11 | **Contractual.** The MQM error-typology scorecard that real localization contracts are written against. |
| [BYU-TRG-Team/mqm-scorecard-api](https://github.com/BYU-TRG-Team/mqm-scorecard-api) | Apache-2.0 | **1** | 2025-06-11 | **Contractual.** Its API sibling. |

**Quality a machine can compute on its own: 2,058★, alive, Apache-2.0.
Quality a buyer and a vendor must sign: 2★, from one university team, untouched since mid-2025.**
A ratio of roughly **1,000:1 inside a single discipline** — the most precise confirmation yet of the
law this KB has now recorded across six industries.

### Informed gaps — searched, and genuinely not on GitHub

- **The Okapi Framework is not on GitHub.** `okapiframework/okapi` was the *only* failure in 35
  `ls-remote` checks. Okapi is the industry-standard open filter/segmentation toolkit — the thing
  that turns ~50 proprietary file formats into XLIFF — and it is hosted on Bitbucket. GitHub holds
  only satellites: [spartansw/okapi-worldserver-components](https://github.com/spartansw/okapi-worldserver-components)
  (MIT, 7★, 2024-07-17), [dameikle/okapi-maven-plugin](https://github.com/dameikle/okapi-maven-plugin)
  (Apache-2.0, 7★, 2024-10-23), and [sheep-works/Suffolk](https://github.com/sheep-works/Suffolk)
  (0★, 2026-11-20), an early Rust port of Okapi's Tikal filter.
- **OmegaT is not on GitHub either.** The most widely used open-source CAT tool returns only
  plugins ([yoyicue/omegat-tencent-plugin](https://github.com/yoyicue/omegat-tencent-plugin) GPL-3.0
  41★; [inertia42/omegat-openaitrans-plugin](https://github.com/inertia42/omegat-openaitrans-plugin)
  GPL-3.0 30★) and unrelated name collisions. It is a SourceForge project.
- **This is a method defect, not a market fact, and it affects all twelve industries in this
  rotation.** GitHub-only discovery has a blind spot shaped precisely like *mature, pre-2010,
  standards-implementing open source* — which is disproportionately where industrial standards
  tooling lives. Every prior pass of this KB, and of the other eleven, inherits that blind spot.
  **Rule: when a plane has an obvious incumbent and the search does not return it, the next check is
  a different forge, not a conclusion of absence.**

## The out-of-home, signage & retail-media plane — foundations measured 2026-11-26 (pass 15)

Scope of the measurement: `topic:digital-signage` = **576 repos**; `topic:dooh` = **35 repos**;
`SMIL signage` = **5 repos**; `org:openooh` = **6 repos**. 37 slugs checked with `git ls-remote`, **36
resolve, 1 does not** (`screenrig/screenrig` — see the gap note in `agents/top.md`). Every
`NOASSERTION` licence was opened by hand rather than inferred.

### Permissive foundations you can build a client deliverable on

| Repo | Stars / forks | Licence | Last push | Why it is foundational |
|---|---|---|---|---|
| [ardera/flutter-pi](https://github.com/ardera/flutter-pi) | 2,012\* / 210f | **MIT** | 2026-11-15 | Flutter on bare KMS/DRM — no X11, no desktop. The efficient player runtime, and the answer to EMEA energy scoring |
| [RushB-fr/freekiosk](https://github.com/RushB-fr/freekiosk) | 765\* / 145f | **MIT** | 2026-11-24 | Android kiosk player for web creative |
| [concerto/concerto](https://github.com/concerto/concerto) | 485\* / — | **Apache-2.0** | 2026-11-26 | Rails CMS, Docker, 2008 origin, pushed today — the platform anchor of this plane |
| [screenlite/screenlite](https://github.com/screenlite/screenlite) | 368\* / 18f | **MIT** | 2026-05-08 | Self-hosted CMS; permissive, currently quiet |
| [screentinker/screentinker](https://github.com/screentinker/screentinker) | 281\* / 76f | **MIT** | 2026-11-26 | Multi-tenant CMS — fastest path to a managed offering |
| [prebid/prebid-server](https://github.com/prebid/prebid-server) | 595\* / 986f | **Apache-2.0** | 2026-11-25 | Server-side bidding with DOOH support — the auction half of pDOOH |
| [openooh/venue-taxonomy](https://github.com/openooh/venue-taxonomy) | 56\* / 40f | **Apache-2.0** | 2026-11-16 | The venue vocabulary the whole buy side assumes; spec 1.2 targets OpenRTB 2.6 |
| [home-screens/home-screens](https://github.com/home-screens/home-screens) | 114\* / 21f | **MIT** | 2026-11-26 | Lightweight screen/dashboard renderer |
| [NVIDIA-AI-IOT/deepstream-occupancy-analytics](https://github.com/NVIDIA-AI-IOT/deepstream-occupancy-analytics) | 240\* | **MIT** | 2023-10-19 | Occupancy counting reference for measurement work — **stale, port the approach** |
| [saimj7/People-Counting-in-Real-Time](https://github.com/saimj7/People-Counting-in-Real-Time) | 613\* | **MIT** | 2023-08-15 | Counting reference — **stale, port the approach** |

Ten permissive foundations, all verified. **Nine exceed the five-repo bar; the two counting
references are included with their staleness stated rather than hidden.**

### Copyleft and constrained foundations — real, useful, and not shippable closed

| Repo | Stars | Licence | Last push | Constraint |
|---|---|---|---|---|
| [xibosignage/xibo-cms](https://github.com/xibosignage/xibo-cms) | 520\* | AGPL-3.0 | 2026-11-24 | AGPL; certain players need a commercial player licence |
| [xibosignage/xibo](https://github.com/xibosignage/xibo) | 745\* | AGPL-3.0 | 2026-11-25 | AGPL umbrella repo |
| [garlic-signage/garlic-player](https://github.com/garlic-signage/garlic-player) | 150\* / 34f | AGPL-3.0 | 2026-11-24 | The only maintained open SMIL player |
| [garlic-signage/garlic-hub](https://github.com/garlic-signage/garlic-hub) | 151\* | AGPL-3.0 | 2026-11-22 | SMIL CMS, active development |
| [garlic-signage/garlic-proxy](https://github.com/garlic-signage/garlic-proxy) | 5\* | AGPL-3.0 | 2025-09-17 | Caching proxy for SMIL fleets |
| [garlic-signage/garlic-creator](https://github.com/garlic-signage/garlic-creator) | 4\* | AGPL-3.0 | 2025-09-17 | SMIL authoring |
| [nktnet1/webview-kiosk](https://github.com/nktnet1/webview-kiosk) | 319\* / 67f | AGPL-3.0 | 2026-11-25 | Maintained kiosk web view |
| [debloper/xiosk](https://github.com/debloper/xiosk) | 349\* / 42f | MPL-2.0 | 2026-02-17 | Weak copyleft — file-level, usually acceptable |
| [Screenly/Anthias](https://github.com/Screenly/Anthias) | 3,745\* / 735f | GPLv2 + Commercial | 2026-11-26 | The plane's most popular repo; commercial licence required for closed work |

### Archived — read, cite, never depend

| Repo | Stars | Licence | Archived / last push | Note |
|---|---|---|---|---|
| [dividuum/info-beamer](https://github.com/dividuum/info-beamer) | 230\* / 49f | **BSD-2-Clause** | archived, 2020-05-01 | Permissive after all — GitHub said NOASSERTION, the file says BSD-2-Clause |
| [eerotal/LibreSignage](https://github.com/eerotal/LibreSignage) | 695\* / 132f | BSD-3-Clause | archived 2021-08-26 | The former permissive favourite, gone |

## The avails, windowing & distribution-rights plane — foundations measured 2026-11-26 (pass 16)

**The anchor exists and this KB had never named it.** `MovieLabs` appeared exactly **once** across 1.1 MB
of KB before this pass. The MovieLabs Digital Distribution Framework is the reference implementation of
the Avails interchange the entire title-licensing industry sends to retailers, and it is **MIT**.

### Verified foundations

Every row below: existence confirmed by `git ls-remote` (HEAD resolves), licence confirmed by fetching
the licence file and counting bytes — not by trusting an SPDX badge.

| Repo | Stars/Forks | Licence | Last push | Role in this plane |
|---|---|---|---|---|
| https://github.com/MovieLabs/mddf | 38*/11f | MIT (`LICENSE`, 1144 B) | 2025-12-19 | **The anchor.** Java library + tools for Avails, Common Media Manifest (CMM), Media Manifest Core (MMC), Media Entertainment Core (MEC) and Asset Order & Delivery (AOD). Validates and generates the actual interchange files |
| https://github.com/MovieLabs/OMC | 35*/6f | Apache-2.0 (`LICENSE`, 11357 B) | 2026-02-07 | Ontology for Media Creation — the production-side entity model (assets, participants, tasks) that an avails record must join back to |
| https://github.com/pivotshare/avails | 1*/1f | MIT (`LICENSE`, 1081 B) | 2016-10-31 | Parser/generator for EMA Avails. Dormant ten years; valuable as a readable, small reference for the sheet format |
| https://github.com/thomas-shirley/ema-avails-generator | 0*/0f | Apache-2.0 (`LICENSE`, 11357 B) | 2023-03-21 | Shell automation for producing EMA avails documents for digital video retail |
| https://github.com/survos/omc | 0*/0f | MIT | 2026-11-25 | OMC 2.8 DTOs, schema validation and production catalogue JSON. **Created 2026-11-24** — the freshest thing in this plane, and one day old at time of writing |
| https://github.com/MovieLabs/cmr-ratings | 1*/0f | **NONE** | 2026-06-17 | Common Metadata Ratings: the ratings specifications and data. Ratings gate what may be exploited where, so this is in-plane — but see the licence warning below |
| https://github.com/MovieLabs/omc-util | 1*/0f | **NONE** | 2026-11-03 | OMC utilities, actively pushed. No licence file |
| https://github.com/MovieLabs/DCNC-to-CPL | 3*/0f | MIT | 2016-05-09 | Digital Cinema Naming Convention string to SMPTE 429-7 CPL. Bridges this plane to the theatrical plane of pass 10 |
| https://github.com/playmoviespartner/emavalidator | 3*/2f | **NONE** | 2017-04-20 | Google Play Movies' own EMA Avails validator. Historically the de-facto conformance check for anyone delivering to Play — and it has **no licence file** |
| https://github.com/omi/RAIDAR | 21*/4f | MIT | 2021-01-12 | Music licensing platform out of Berklee. Dormant since 2021; the highest-starred permissively-licensed music-licensing codebase found |

Ten verified rows. `MichaelBrandonFalk/UltimateAvailMaker` (0*/0f, **no licence**, pushed 2026-11-12) also
resolves and is the only *currently maintained* avails authoring tool found — a browser app for Standard
EMA and YouTube avails — but with no licence it cannot be built on, so it is listed here as intelligence
rather than as a foundation.

### ⚠️ Licence warnings specific to this plane

- **Three of the four MovieLabs satellite repos carry no licence file at all** (`cmr-ratings`,
  `omc-util`, `comfyui-movielabs-util`), while the two flagship repos are cleanly licensed (`mddf` MIT,
  `OMC` Apache-2.0). Do not infer the org's licence from its best repo. Checked across `master` and
  `main` with the full six-name probe (`LICENSE`, `LICENSE.md`, `LICENSE.txt`, `license.txt`, `COPYING`,
  `COPYING.md`) that pass 8 corrected into this KB.
- **`playmoviespartner/emavalidator` has no licence and is the one a delivery engineer is most likely to
  reach for**, because it is the validator a major retailer published. No grant means default copyright:
  all rights reserved. Read it for behaviour, do not vendor it.
- **`MovieLabs/mddf` is maintained at the repo but stalled at the release.** `pushed_at` is 2025-12-19,
  which looks healthy; its own README's "What's New" section tops out at **"2023-Jul-2: v2.0.8
  released"**. Freshness of the default branch is not freshness of a shipped artefact — check the
  release notes, not the push date. This is a new instance of a trap this KB keeps re-finding.

### The three-step gradient — sixth confirmation of this KB's structural law, and the cleanest yet

The law: within a single plane, the further a task moves from **format** toward **judgment**, the thinner
the open source gets. This plane splits into three steps that are unusually clean, because each one is a
different verb applied to the same avail.

1. **DECLARE the avail — a format problem.** Solved and permissively licensed: `MovieLabs/mddf` MIT
   38*/11f, plus three smaller MIT/Apache parsers. You can read, write and validate the interchange today.
2. **EVALUATE the window — a judgment problem.** **Nothing avails-specific exists.** There is no open
   source that takes a title, a territory, a date and a deal and answers "may I exploit this?". The only
   route is to borrow a general-purpose policy engine — `open-policy-agent/opa` (Apache-2.0, 12529*) or
   `cerbos/cerbos` (Apache-2.0, 4669*) — and encode the windows yourself. The engine is free; the
   *policy model* is the work, and nobody has published one for avails.
3. **SETTLE the money — pure judgment.** **Zero, literally.** `residuals calculation film` returns **0
   repositories**. `film royalty statement` returns **1**, and it is a scripture-governance project.
   `royalty accounting` returns 47 whose top hits are crypto NFT royalty splitters
   (`mdcryptonfts/royalty_contract`, `sdoddler/XRPSiphon`) and whose only on-topic entries are three
   0-star music-royalty apps pushed in 2026 by one author (`Nasglobal/premier-royalty-accounting-*`).

So: the industry can **state** an availability, cannot **evaluate** one without building the model
itself, and cannot **settle** one at all. Pass 5 found the identical shape for rights reservation
(declare → honour → liquidate). That is now two planes in this KB with the same three-step collapse, and
in both the collapse bottoms out at **the money**.

### New record for false abundance — and a new rule

`rights windowing` returns **681 repositories and not one is relevant**. Every result is Microsoft
Windows privilege tooling: `gtworek/Priv2Admin` (2534*), `jborean93/PSPrivilege`, `lkarlslund/hashmuncher`,
portable-runtime installers that avoid needing "administrator rights on Windows".

This beats pass 8's `isan` (1942 results, zero relevant) on **plausibility**, which is what makes it
dangerous: "rights windowing" is the industry's own term of art, so a careless pass would not even
suspect the query. The collision is total — both words are overloaded by one operating system.

**New rule for all twelve industries:** when any term in a query is also the name of an operating
system, platform or language (`windows`, `rust`, `go`, `swift`, `kotlin`, `android`), the result total is
noise by construction. Add a disambiguating industry noun (`avails`, `EMA`, `distribution`) or the search
has told you nothing. Pass 8's rule was "read the results, not the total"; this pass adds **"and predict
which of your nouns the platform already owns."**

### Adjacent and deliberately not promoted: the CLM cluster

Deal terms live in contracts, so contract-lifecycle management is the nearest adjacent layer. It has
real 2026 activity but is **licence-hostile for Globant's purposes**: `AniketTati/draft-legal` (23*,
NOASSERTION), `aaked-app/aakd` (12*, **AGPL-3.0**), `bytecrunch-io/openclm` (4*, **AGPL-3.0**),
`0xyz-exe/contractflow` (1*, MIT). The only permissive entry has one star. AGPL on a service that
would hold a studio's deal terms is a conversation with a client's counsel, not a default. Recorded so a
later pass does not re-discover it as an opportunity.

## The development & pre-production plane — measured 2026-11-26 (pass 17)

**42 slugs probed. 38 resolve to a canonical repository, 4 do not exist, and 4 of the 38 were reachable
only through a rename redirect** (recorded below under their canonical names — see the new oracle rule at
the end of this section).

### Tier 1 — the format substrate: permissive, and the one healthy layer in the plane

Fountain is the open screenplay markup format, and it is the reason this plane has any permissive
foundation at all. It is plain text, so every tool in this tier is a parser or a renderer.

| Repo | License | Stars / Forks | Last push | Role |
|---|---|---|---|---|
| [nyousefi/Fountain](https://github.com/nyousefi/Fountain) | **MIT** | 690★ / 71f | 2023-06-10 | The **reference implementation** of the Fountain format. Dormant three years, but it is the spec made executable — read it, do not depend on it |
| [piersdeseilligny/betterfountain](https://github.com/piersdeseilligny/betterfountain) | **MIT** | 454★ / 75f | 2026-09-11 | Screenwriting inside VS Code. The most-starred *maintained* MIT artefact in the plane, and the practical authoring front end |
| [vilcans/screenplain](https://github.com/vilcans/screenplain) | **MIT** | 187★ / 35f | 2026-11-21 | Fountain → PDF / HTML / FDX in Python. Pushed five days before measurement; the dependable conversion workhorse |
| [overvale/Textplay](https://github.com/overvale/Textplay) | **BSD-3-Clause** (verified by reading; see below) | 107★ / 16f | 2019-11-28 | Fountain → HTML/FDX command-line converter. Dormant since 2019; **licence is permissive despite the API saying `NOASSERTION`** |
| [wildwinter/screenplay-tools](https://github.com/wildwinter/screenplay-tools) | **MIT** | 29★ / 8f | 2026-11-18 | Format-agnostic screenplay representation with parse **and write** in C++, JavaScript, Python and C#. The only multi-language option, and the right pick for a polyglot pipeline |
| [rsdoiel/scripttool](https://github.com/rsdoiel/scripttool) | AGPL-3.0 | 46★ / 7f | 2026-11-19 | Converts between **fdx, fadein, osf and fountain** (Go). The widest format coverage found — but AGPL, so deploy unmodified behind an interface |
| [rsdoiel/fountain](https://github.com/rsdoiel/fountain) | AGPL-3.0 | 8★ / 1f | 2026-11-19 | Go package for Fountain; the library under `scripttool` |
| [xiota/ftn2xml](https://github.com/xiota/ftn2xml) | GPL-3.0 | 5★ / 2f | 2026-01-21 | C++ converter to XML/HTML/PDF/FDX, written for speed because the author observed that nearly all open Fountain parsers are scripting-language implementations |
| [mgmarlow/ftnbuild](https://github.com/mgmarlow/ftnbuild) | **MIT** | 2★ / 1f | 2021-12-25 | JS processor. Dormant five years; listed for completeness |
| [Joeboy/scenewriter](https://github.com/Joeboy/scenewriter) | **MIT** | 1★ / 0f | 2023-10-22 | Fountain parser in Rust/Nom |
| [jtoy/fountainrb](https://github.com/jtoy/fountainrb) | **MIT** | 0★ / 0f | 2026-10-27 | Dependency-free pure-Ruby parser with line-level validation. Active, unnoticed |

⚠️ **The licence trap in this tier, and it sits on the critical path.**
[ifrost/afterwriting-labs](https://github.com/ifrost/afterwriting-labs) — **280★ / 53f, last push
2026-01-28 — has no license file at all.** Seventeen license filenames were probed on both `master` and
`main` (including the lowercase `license.txt` and `COPYING.md` names added by pass 5) and every one
returned 404, while the control request for `README.md` returned 200. The names are not the problem:
**there is no grant.** Afterwriting is the de-facto Fountain post-processor and PDF generator that the
rest of this tier leans on for output. **Unlicensed means all rights reserved.** Use `screenplain` (MIT)
for the render path instead.

### Tier 2 — the editors: all copyleft, one archived

| Repo | License | Stars / Forks | Last push | Note |
|---|---|---|---|---|
| [lmparppei/Beat](https://github.com/lmparppei/Beat) | **GPL-3.0-or-later** (LICENSE.md, 507 B — a notice, not the full text) | 368★ / 60f | 2026-11-02 | macOS screenwriting app, actively maintained. API said `NOASSERTION` |
| [trelby/trelby](https://github.com/trelby/trelby) | GPL-2.0 | 354★ / 107f | 2025-10-21 | Multiplatform, feature-rich. Thirteen months since last push |
| [dimkanovikov/KITScenarist](https://github.com/dimkanovikov/KITScenarist) | GPL-3.0 | 352★ / 51f | 2023-08-01 | 🚫 **ARCHIVED.** Do not propose it |

### Tier 3 — the management layer: this is the desert

Breakdown, stripboard, schedule, call sheet, budget. Everything a production office runs on.

| Repo | License | Stars / Forks | Last push | Scope |
|---|---|---|---|---|
| [koosoli/OpenShotDesigner](https://github.com/koosoli/OpenShotDesigner) | **GPL-3.0** (LICENSE, 35,809 B behind a custom header) | 47★ / 9f | 2026-11-16 | The broadest scope found: lined script, shot list, storyboard, floor plan, scheduling, call sheets, crew/cast, budget, locations, continuity log. Browser-based. **The high-water mark of this tier is 47 stars** |
| [ChrisTempel/CineSched](https://github.com/ChrisTempel/CineSched) | **GPL-3.0-or-later** (LICENSE, 817 B notice) | 15★ / 6f | 2026-10-11 | macOS shoot scheduling, Final Draft (.fdx) import, PDF schedule export |
| [ChrisTempel/CineSpend](https://github.com/ChrisTempel/CineSpend) | **MIT** | 8★ / 1f | 2026-10-06 | macOS budgeting, ten currencies. **The only budgeting repository found in the plane, and the only permissive one** |
| [nachobust/FilmOrganizer](https://github.com/nachobust/FilmOrganizer) | **MIT** | 1★ / 0f | 2026-11-17 | Breakdown + shooting schedule, offline, Windows/macOS/Linux. Imports PDF, Word, Final Draft and Fountain |
| [method-production-suite/method-scheduling](https://github.com/method-production-suite/method-scheduling) | **Apache-2.0** | 1★ / 1f | 2026-11-21 | Breakdown, stripboard with day breaks and banners, calendar, **day out of days**, reports. Imports Fountain and .fdx. Claims an open file format. The most permissive licence in the tier at one star |
| [opengateapp/opengate](https://github.com/opengateapp/opengate) | GPL-3.0 | 1★ / 1f | 2026-11-03 | Screenplay → breakdown → stripboard → calendar → call sheets → storyboards, one synced project |
| [Govind-vaghasiya/CALLSHEETPRO](https://github.com/Govind-vaghasiya/CALLSHEETPRO) | ⚠️ **No license** | 0★ / 0f | 2026-10-13 | Next.js/Supabase scene-breakdown-to-call-sheet app with conflict checks |
| [mrrishit909/film-production-planner](https://github.com/mrrishit909/film-production-planner) | ⚠️ **No license** | 0★ / 0f | 2026-10-05 | Breakdown parser + **CP-SAT** shoot scheduling with a rule checker and producer approval gate. The only constraint-solver approach found |

**Nothing in Tier 3 is a base.** The combined star count of all eight repositories is **73** — fewer than
`betterfountain` alone, and barely a tenth of `nyousefi/Fountain`. Five of the eight were first pushed
within the last ten weeks, which is the signature of freshly generated single-author projects rather than
an emerging ecosystem. The permissive ones are at 1 and 8 stars; the one with real scope is GPL-3.0.

### Tier 4 — the money: effectively nothing

`production accounting`, `payroll`, `budgeting` and `greenlight` returned **zero** across all eight KB
files before this pass, and the web is barely better. Besides `CineSpend` (MIT, 8★) the only adjacent
artefact located is [jtsage/TDTracX](https://github.com/jtsage/TDTracX) — **0★, no license, ARCHIVED
2024-06-25**, and built for *theatre* technical directors, not film. `residuals calculation film` remains
**0 repositories**, now confirmed in two separate passes. Incumbents here (Movie Magic Budgeting,
Showbiz, Wrapbook, Cast & Crew) are entirely proprietary.

### 🔧 New oracle rule — reusable across all twelve industries

**`git ls-remote` says EXISTS + `search/repositories` with `repo:<slug>` returns HTTP 422 "cannot be
searched" ⇒ the slug is a rename/transfer redirect, and `ls-remote` followed it silently.**

Four cases in this pass alone:

| Slug as published by search engines and blogs | Canonical repository | Licence difference it hides |
|---|---|---|
| `wildwinter/fountain-tools` | [wildwinter/screenplay-tools](https://github.com/wildwinter/screenplay-tools) | — (MIT either way) |
| `rsdoiel/scripttools` | [rsdoiel/scripttool](https://github.com/rsdoiel/scripttool) | — (AGPL-3.0 either way) |
| `afterwriting-labs/afterwriting` | [ifrost/afterwriting-labs](https://github.com/ifrost/afterwriting-labs) | Owner changes entirely; **no licence** |
| `olivertaylor/textplay` | [overvale/Textplay](https://github.com/overvale/Textplay) | Owner changes entirely; BSD-3-Clause |

And one case where **both oracles agree the repo is simply gone**: `Falconwing/CineSched` (also
`nguernse/screenplay-js`, `sunsetsystems/fountain`, `ifrost/afterwriting`).

**Why this matters more than it sounds.** The stale slug *resolves in a browser today* — GitHub serves
the redirect — so a `curl`/URL check **passes** and the KB still records a non-canonical slug that breaks
the day the owner drops the redirect or someone else claims the old name. **`ls-remote` is an oracle of
reachability, not of identity.** Pass 5's rule stands ("a 404 is never by itself proof a licence is
missing"); this adds its mirror: **a 200 is never by itself proof a slug is canonical.** Two oracles, and
the disagreement between them is the signal. Note also that in this session `curl -sI https://github.com/…`
is answered **403 by the egress proxy**, so the redirect cannot be read from response headers — a
`WebFetch` of the repository page was the third oracle that produced the canonical names above.

### 🔧 Correction to the licence probe — `NOASSERTION` cuts both ways

Pass 5 established that a custom LICENSE filename can hide a real licence. This pass found the stronger
version: **a custom licence *title* can hide either a standard permissive grant or an affirmative refusal
of one, and the API reports `NOASSERTION` for both.**

- [overvale/Textplay](https://github.com/overvale/Textplay) — file titled `TEXTPLAY LICENSE`, body is
  **verbatim BSD-3-Clause**. Permissive. Safe.
- [imMamdouhaboammar/motion-graphics-skills](https://github.com/imMamdouhaboammar/motion-graphics-skills)
  — file titled `PROPRIETARY AND CONFIDENTIAL LICENSE (ALL RIGHTS RESERVED)`. **No grant at all.**

Same API value, opposite legal consequence. **`NOASSERTION` is an instruction to read the file, not a
verdict in either direction** — and in this plane it also concealed three GPL-3.0 projects behind short
custom notices (`Beat` 507 B, `CineSched` 817 B, `OpenShotDesigner` 35,809 B).

---

## The book, ebook & scholarly-publishing plane — measured 2026-11-26 (pass 18)

The written-word substrate of M&E, absent from this KB until this pass. All rows verified
2026-11-26: existence via `git ls-remote`, **licence by reading the licence file in the repo**,
last-commit date via `git clone --depth 1 --filter=blob:none --no-checkout` + `git log -1`.
**No star counts** — the GitHub API is unreachable for out-of-session repos from this environment,
and an unverified number is worse than an absent one.

### The finding that shapes this section

In this plane the licence tracks **who wrote the code**, not how regulated the layer is:

- **Standards bodies** (W3C, DAISY, EDRLab/Readium, Posit, Jupyter) → **BSD-3 / MIT / Apache-2.0**.
  Their product is a *format*; a copyleft reference implementation would slow its adoption.
- **The scholarly & library commons** (PKP, Pressbooks, Manifold, Internet Archive, Fidus Writer) →
  **GPL-3.0 / AGPL-3.0**. Their product is a *commons*; permissiveness would let a host enclose it.

Practical consequence for a bid: **the conformance and rendering layers are embeddable; the platform
layer must be deployed and extended, not linked into proprietary code.** This is the reverse of the
AV side of the same industry, where pass 4 found the checker (`MediaConch`) copyleft and the
metadata layer permissive.

### Conformance & accessibility validation — permissive, and this is the strongest part of the stack

This is the layer under a statutory duty in the EU (see `intel/market.md`), and it is the layer
Globant can embed without obligation. That combination does not occur anywhere else in this KB.

| Repo | Licence (file) | Last commit | Role |
|---|---|---|---|
| https://github.com/w3c/epubcheck | BSD-3-Clause (`LICENSE.md`) | 2026-11-02 | The canonical EPUB validator; what retailers and aggregators gate on |
| https://github.com/daisy/ace | MIT (`LICENSE.txt`) | 2026-05-01 | Ace by DAISY — EPUB accessibility conformance against EPUB Accessibility 1.1 |
| https://github.com/daisy/pipeline-modules | LGPL-2.1/3.0 (`LICENSE.txt`) | 2026-10-08 | Conversion modules: braille, TTS, DAISY ↔ EPUB. Weak copyleft — linkable with care |
| https://github.com/daisy/pipeline-ui | MIT (`LICENSE`) | 2026-09-05 | Desktop front end to the Pipeline |

> **⚠️ `daisy/pipeline` itself has no licence file.** It is a `git-subrepo` umbrella pointing at ~25
> sub-repositories; the licensed artefacts are the modules above. Citing `daisy/pipeline` as
> "LGPL" in a client deck would be citing a repository that grants nothing. Verified 2026-11-26.

### Reading systems & rendering — permissive, EMEA-anchored

| Repo | Licence (file) | Last commit | Role |
|---|---|---|---|
| https://github.com/edrlab/thorium-reader | BSD-3-Clause (`LICENSE`) | 2026-11-26 | Reference desktop reader (EDRLab, France); EPUB + LCP + audiobooks |
| https://github.com/readium/readium-css | BSD-3-Clause (`LICENSE`) | 2026-11-16 | The typography and user-settings layer of a reading system |
| https://github.com/readium/r2-shared-js | BSD-3-Clause (`LICENSE`) | 2025-10-28 | Readium 2 shared models. **13 months stale** — pin it, do not expect fixes |
| https://github.com/readium/readium-lcp-server | BSD-3-Clause (`LICENSE.md`) | 2026-06-22 | LCP licence server — open DRM |
| https://github.com/futurepress/epub.js | BSD-2-Clause (bare `license`) | 2026-03-23 | Browser-side EPUB renderer. **The permissive alternative to `ebooklib`** for read paths |
| https://github.com/pagedjs/pagedjs | MIT (`LICENSE.md`) | 2026-10-20 | Paged-media CSS: HTML → print/PDF with real pagination |
| https://github.com/vivliostyle/vivliostyle.js | **AGPL-3.0** (`LICENSE`) | 2026-11-24 | CSS typesetting engine, **Japanese-origin** — the best open answer for CJK vertical writing and complex layout, and the licence is the catch |

### Authoring & toolchains

| Repo | Licence (file) | Last commit | Role |
|---|---|---|---|
| https://github.com/jgm/pandoc | **GPL-2.0** (`COPYING.md`) | 2026-11-25 | Universal document converter. Licence lives in `COPYING.md` — GitHub's own detector often misses it |
| https://github.com/quarto-dev/quarto-cli | **MIT** (`COPYING.md`) | 2026-11-25 | Scientific & technical publishing toolchain (Posit). Also `COPYING.md` |
| https://github.com/asciidoctor/asciidoctor | MIT (`LICENSE`) | 2026-11-22 | Fast text processor + publishing toolchain |
| https://github.com/jupyter-book/jupyter-book | BSD-3-Clause (`LICENSE`) | 2026-11-25 | Executable books from notebooks |
| https://github.com/rstudio/bookdown | GPL-3.0 (`LICENSE.txt`) | 2026-09-18 | R-based book authoring |
| https://github.com/Sigil-Ebook/Sigil | GPL-3.0 (`COPYING.txt`) | 2026-11-25 | WYSIWYG EPUB editor — the tool human remediators actually use |
| https://github.com/standardebooks/tools | GPL-3.0, **CC0 1.0 for `./se/data/templates`** (`LICENSE.md`) | 2026-11-25 | Production toolset with a genuinely reusable CC0 template set |
| https://github.com/aerkalov/ebooklib | **AGPL-3.0** (`LICENSE.txt`) | 2026-11-01 | Python EPUB read/write. **Read the warning below before importing it** |

> **⛔ `ebooklib` is AGPL-3.0 and it is the default choice.** It is the library a developer reaches
> for to manipulate EPUB in Python. Inside a *hosted* conversion or remediation service, AGPL §13
> obliges offering complete corresponding source to the service's users. Nothing in the package name
> signals this. **This is the most likely way a publishing engagement acquires network copyleft by
> accident.** Verified from `LICENSE.txt`, 2026-11-26.
>
> **There is no verified permissive server-side EPUB read/write library in this pass.** Searched and
> not found — stated as a gap. Permissive options exist only either side of it: `epub.js`
> (BSD-2, browser) and `pagedjs` (MIT) for rendering, `epubcheck` (BSD-3) and `ace` (MIT) for
> validation. A server-side writer is a **build**, not an adopt.

### ONIX — the book industry's metadata wire format, permissive across the board

ONIX for Books (EDItEUR) is to publishing what SCTE-35 is to ad insertion: small, boring, and the
thing that actually has to be right. Unlike MedDRA in healthcare or CPT in US coding, the **ONIX
code lists are freely available** — so this is a regulated-adjacent metadata layer with no content
toll, which is rarer in this KB than it should be.

| Repo | Licence (file) | Last commit | Language | Read |
|---|---|---|---|---|
| https://github.com/titusz/onixcheck | Apache-2.0 (`LICENSE`) | 2026-10-16 | Python | Validates 2.1/3.0/3.1 against official XML Schema. **Start here** |
| https://github.com/zach-m/jonix | Apache-2.0 (`LICENSE`) | 2026-10-17 | Java | Extraction library. Aggregators misreport it as stale; it is not |
| https://github.com/chrisribal/onix-parser | MIT (`LICENSE`) | 2026-09-29 | PHP | **Reads and writes** 3.0/3.1 and resolves code lists — the only verified writer |
| https://github.com/jaerith/ONIX-Data | Apache-2.0 (`LICENSE`) | 2025-10-14 | C# / .NET | 13 months stale, but structurally complete |
| https://github.com/xercode/metadata-onix-lib | MIT (`LICENSE`) | 2021-04-28 | PHP | **5½ years stale. Do not start here** |
| https://github.com/phantom-artist/onix-creator | **none found** | 2022-05-10 | — | No licence file, 4½ years stale. Unusable |

**Informed gap:** no verified open-source library resolves **Thema** (the international subject
scheme) or **BISAC** codes as a first-class feature. Searched; the repositories above handle ONIX
structure and EDItEUR code lists, and subject-scheme mapping was not found in any of them. For a
client moving a backlist between NA (BISAC) and EMEA (Thema) markets, **that mapping is a build.**

### Catalogue, library & bibliographic layer

| Repo | Licence (file) | Last commit | Role |
|---|---|---|---|
| https://github.com/internetarchive/openlibrary | AGPL-3.0 (`LICENSE`) | 2026-11-26 | Open bibliographic catalogue + identifiers |
| https://github.com/thoth-pub/thoth | **Apache-2.0** (`LICENSE`) | 2026-11-25 | OA book metadata management and ONIX/MARC export (COPIM, UK). **The permissive metadata platform in this plane** |
| https://github.com/omeka/Omeka-S | GPL-3.0 (`LICENSE`) | 2026-11-24 | Digital collections publishing |
| https://github.com/gotson/komga | MIT (`LICENSE`) | 2026-11-24 | Ebook/comic server — **the permissive one** of the four reading servers |
| https://github.com/Kareadita/Kavita | GPL-3.0 (`LICENSE`) | 2026-11-22 | Self-hosted reading server |
| https://github.com/janeczku/calibre-web | GPL-3.0 (`LICENSE`) | 2026-11-22 | Web front end over a Calibre library |
| https://github.com/koreader/koreader | AGPL-3.0 (`COPYING`) | 2026-11-25 | E-ink reader application |
| https://github.com/kovidgoyal/calibre | GPL-3.0 (`LICENSE`) | 2026-11-26 | Library management + format conversion; the de facto desktop standard |

### Standards documents — not code, demoted on sight

| Artefact | Licence | Read |
|---|---|---|
| https://github.com/w3c/publ-epub-revision | **W3C Software and Document License** | EPUB 3 spec revision text. A document licence, not a software grant |
| https://github.com/daisy/epub-revision-a11y | none | Last commit 2015-10-02. Historical |

### ⚙️ Method additions from this pass — reusable in all twelve industries

1. **`COPYING.md` joins the licence probe** (extension #4). Two independent hits in one pass:
   `jgm/pandoc` = GPL-2.0, `quarto-dev/quarto-cli` = MIT. Both read "unlicensed" without it.
2. **A bare lowercase `license` with no extension joins the probe** (extension #5).
   `futurepress/epub.js` = BSD-2-Clause, found nowhere else.
3. **Report the licence *set*, not the first match.** `standardebooks/tools` auto-classified as
   `CC-*` on first match; it is GPL-3.0 with a CC0 carve-out. The first licence named in a file is
   not the licence of the code.
4. **Last-commit dates without an API:** `git clone --depth 1 --filter=blob:none --no-checkout`
   then `git log -1 --format=%cs`. Sub-second, no blob transfer, works where the GitHub API is
   blocked. This replaced the API for all 40 repos in this pass.
5. **Always include a negative control in an existence probe.** A deliberate fake slug was probed
   alongside the 39 real ones; without it, "all resolved" is not evidence that the probe works.

## The sports-media & live-event plane — measured 2026-11-26 (pass 19)

**A substrate this KB was missing entirely, not just for sports.** A probe of all eight files
returned **0 lines** for `YOLO`, `pose estimation`, `mmpose`, `ultralytics`, `DeepSORT`,
`ByteTrack`, `object tracking` and `multi-object` — and 7 lines for `supervision`. Nineteen passes
into an M&E knowledge base, **the object-detection and multi-object-tracking layer had never been
recorded**. It underpins sports analytics, but also virtual production, ad verification, trust &
safety and audience measurement — all planes this KB already covers. The rows below are therefore
foundations for far more than sport.

All rows verified 2026-11-26: existence via `git ls-remote`, stars/forks/push via
`search/repositories`, licence by reading the file where the API was unhelpful.

### Detection, tracking & pose — and the licence gradient is commercially decisive

| Repo | License | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| https://github.com/roboflow/supervision | **MIT** | 51,730 | 4,963 | 2026-11-26 | The permissive workhorse: annotation, zones, line counters, tracker glue. **Start here** |
| https://github.com/FoundationVision/ByteTrack | **MIT** | 6,833 | 1,156 | 2024-06-19 | The reference MOT algorithm. Permissive but dormant — vendor it, don't depend on upstream |
| https://github.com/open-mmlab/mmpose | **Apache-2.0** | 8,083 | 1,547 | 2025-08-04 | Pose estimation toolbox/benchmark. Permissive; last push 2025-08 |
| https://github.com/roboflow/trackers | **Apache-2.0** | 4,022 | 437 | 2026-11-25 | Clean modular re-implementations of leading MOT algorithms — the maintained permissive path to ByteTrack-class tracking |
| https://github.com/tryolabs/norfair | **BSD-3-Clause** | 2,708 | 280 | 2025-04-30 | Lightweight real-time MOT, attaches to any detector |
| https://github.com/ultralytics/ultralytics | ⚠️ **AGPL-3.0** | 63,769 | 12,045 | 2026-11-26 | YOLO26/YOLO27 — the de-facto default detector, and **the single most consequential licence trap in this plane** |
| https://github.com/mikel-brostrom/boxmot | ⚠️ **AGPL-3.0** (`LICENSE`, 34,715 B) | 8,330 | 1,912 | 2026-11-20 | Leading pluggable MOT collection. API reports `NOASSERTION`; the file is plainly AGPL-3.0 |

**Read this before any sports or vision proposal.** The two most-starred libraries in the layer —
`ultralytics` (63,769★) and `boxmot` (8,330★) — are **both AGPL-3.0**. For a hosted service, AGPL
§13 reaches the client's deployment: Globant would owe source for the service, or buy Ultralytics'
commercial licence. The permissive stack is a full alternative and is not a downgrade:
`supervision` (MIT, 51,730★) + `trackers` or `norfair` (Apache-2.0 / BSD-3) + a permissive detector.
`boxmot`'s own licence file additionally warns that *"third-party components retain their own
licensing notices"* — the **compilation-licence** category cycle 8 identified on `chromaprint`,
reappearing here. Resolve the licences of what you link, not of the repo.

### Sports-specific vision

| Repo | License | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| https://github.com/davidpagnon/Sports2D | **BSD-3-Clause** | 354 | 52 | 2026-11-25 | 2D pose **and joint angles** from video or webcam; active. The most permissive sports-pose option |
| https://github.com/SilvioGiancola/SoccerNetv2-DevKit | **MIT** | 231 | 46 | 2024-07-08 | SoccerNet challenge dev kit; dormant but the canonical benchmark entry point |
| https://github.com/lRomul/ball-action-spotting | **MIT** | 141 | 25 | 2023-07-02 | 1st-place SoccerNet ball-action-spotting solution; dormant, valuable as a reference implementation |
| https://github.com/SoccerNet/sn-gamestate | GPL-3.0 | 472 | 102 | 2026-05-02 | Game-state reconstruction: tracking + athlete identification |
| https://github.com/AtomScott/SportsLabKit | GPL-3.0 | 329 | 31 | 2023-12-19 | Sports video → CSV; dormant |
| https://github.com/SoccerNet/sn-calibration | ⚠️ **no licence** | 113 | 17 | 2024-06-18 | Camera calibration — the step everything geometric depends on, and it ships **no grant** (verified: READMEs resolve on both branches, 10 filenames + `LICENSE.pdf` + `LICENCE` all absent) |

### The data-standardization layer — thin, alive, and the real keystone

| Repo | License | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| https://github.com/PySport/kloppy | **BSD-3-Clause** | 573 | 113 | 2026-11-06 | **The keystone.** Normalizes tracking *and* event data across providers into one model. Without it every integration is bespoke |
| https://github.com/andrewRowlinson/mplsoccer | **MIT** | 555 | 92 | 2026-10-27 | Pitch plotting for matplotlib — the default visual vocabulary of the field |
| https://github.com/dcaribou/transfermarkt-datasets | **CC0-1.0** | 532 | 102 | 2026-09-05 | Extract/prepare/publish Transfermarkt datasets |
| https://github.com/martineastwood/penaltyblog | **MIT** | 250 | 40 | 2026-11-24 | Football data pipelines, scraping and match models; active |
| https://github.com/withqwerty/reep | **CC0-1.0** | 245 | 12 | 2026-08-20 | **The football entity register** — maps player, team and coach identity across providers. The identity-resolution layer pass 5's identification plane needed and did not have for sport |
| https://github.com/UnravelSports/unravelsports | MPL-2.0 | 250 | 34 | 2026-01-16 | Graph/spatial modelling helpers; weak copyleft (file-level) |
| https://github.com/floodlight-sports/floodlight | **MIT** | 135 | 25 | 2026-05-04 | Provider-agnostic sports data analysis |
| https://github.com/droher/boxball | **Apache-2.0** | 135 | 22 | 2026-05-20 | Retrosheet's complete baseball history prebuilt into Docker images for several analytic engines |
| https://github.com/shufinskiy/sport_analytics_tools | **Apache-2.0** | 90 | 5 | 2026-06-16 | Index of sports data tools |
| https://github.com/USSoccerFederation/ussf_ssac_23_soccer_gnn | **MIT** | 122 | 13 | 2024-08-29 | US Soccer Federation's MIT Sloan GNN paper code — a federation publishing permissively |
| https://github.com/devinpleuler/analytics-handbook | **MIT** | 1,720 | 214 | 2024-05-26 | The field's teaching text; dormant, still the best onboarding reference |

### The R cluster — rescued from a systematic false negative

All five below report `NOASSERTION` on the GitHub API and **all are MIT**. See the method correction
after the table; this is reusable across all twelve industries.

| Repo | Real license (verified) | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| https://github.com/nflverse/nflfastR | **MIT** (`LICENSE.md` 1,086 B; `DESCRIPTION`: `License: MIT + file LICENSE`) | 558 | 73 | 2026-11-25 | NFL play-by-play |
| https://github.com/sportsdataverse/hoopR | **MIT** (`LICENSE.md` 1,418 B) | 157 | 28 | 2026-11-25 | Men's basketball play-by-play |
| https://github.com/sportsdataverse/cfbfastR | **MIT** (`LICENSE.md` 1,080 B) | 114 | 17 | 2026-11-25 | College football play-by-play |
| https://github.com/nflverse/nflreadr | **MIT** (`LICENSE.md` 1,075 B) | 117 | 20 | 2026-09-17 | nflverse data loader |
| https://github.com/lbenz730/ncaahoopR | **MIT** (API-reported, standard file) | 232 | 59 | 2026-02-08 | NCAA basketball play-by-play |

Permissive and API-clean in the same ecosystem: `sportsdataverse/sportsdataverse-py` (**MIT**, 133★,
2026-11-26), `sportsdataverse/sportsdataverse-js` (**MIT**, 89★, 2026-11-25). Copyleft siblings:
`sportsdataverse/sportyR` (GPL-3.0, 120★) and `sportypy` (GPL-3.0, 52★) for drawing regulation
playing surfaces.

### Esports — the healthiest corner of the plane

| Repo | License | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| https://github.com/markus-wa/demoinfocs-golang | **MIT** | 1,078 | 156 | 2026-11-23 | CS2 demo parser (Go) |
| https://github.com/LaihoE/demoparser | **MIT** | 746 | 110 | 2026-11-24 | CS2 replay parser for Python and JavaScript |
| https://github.com/pnxenopoulos/awpy | **MIT** | 640 | 89 | 2026-11-22 | Parse, analyze and visualize CS2 data |
| https://github.com/teijo/jquery-bracket | **MIT** | 500 | 243 | 2023-07-30 | Single/double-elimination tournament brackets; dormant but still the common answer |

Three independent MIT parsers, all pushed within four days of this pass. Compare the vendor-feed
column in `agents/top.md`: same analytical problem, opposite licence health.

### ⚠️ Known-broken: high stars, no usable grant — do not ship these

Verified 2026-11-26 by the full probe (10 filenames × `master`/`main`, plus `LICENSE.pdf` and
`LICENCE`), with a README control request confirming the branch name resolves in every case. A 404
alone is never proof; these are proof.

| Repo | Stars | What it actually is | Status |
|---|---|---|---|
| https://github.com/hudl/open-data | 3,847 | StatsBomb Open Data (events, lineups, 360 frames) | **Licence is `LICENSE.pdf` at the repo root** — HTTP 200, `application/octet-stream`. GitHub reports `NOASSERTION` because SPDX detectors read text, not PDFs. README additionally requires crediting StatsBomb **and using their logo** |
| https://github.com/hudl/statsbombpy | 758 | Official Python client | **No licence file of any kind.** README points to `doc/LICENSE.pdf` (verified present) for *data* terms and requires registration. The **code** carries no grant → default all-rights-reserved |
| https://github.com/hudl/StatsBombR | 314 | Official R client | **`DESCRIPTION` declares `License: 3.5.0`** — a version number in the licence field. Not a missing licence, not a custom one: a field filled from the wrong field |
| https://github.com/eddwebster/football_analytics | 2,870 | The best-known football analytics collection | No licence |
| https://github.com/linouk23/NBA-Player-Movements | 757 | SportVU movement visualization | No licence |
| https://github.com/metrica-sports/sample-data | 515 | Metrica tracking + event sample data | No licence |
| https://github.com/iptc/sport-schema | 38 | **IPTC's next-generation sports data model** (SportsML successor, semantic-web based), pushed 2026-10-01 | No licence on either branch. Note the contrast: IPTC's *vocabulary* `iptc/sports-newscodes` **is** CC-BY-4.0 (recorded in this file at pass 11); the **schema repo is not licensed** |
| https://github.com/iptc/sportsml-python | 2 | SportsML/SportsJS Python library | MIT, but **dead since 2019-01-25** |

### Method corrections — reusable across all twelve industries

**1. The R/CRAN `MIT + file LICENSE` convention produces a systematic `NOASSERTION` false negative.**
Measured on four repos this pass, not inferred: CRAN requires the copyright holder in a separate
file, so an R package ships a **46–57 byte `LICENSE`** containing only `YEAR:` and
`COPYRIGHT HOLDER:` lines, puts the real grant in **`LICENSE.md`**, and declares
`License: MIT + file LICENSE` in `DESCRIPTION`. GitHub's detector sees a licence file it cannot match
and returns `NOASSERTION`. **All four were MIT.** Rule: *for any R package, read `DESCRIPTION`'s
`License:` field and `LICENSE.md` before recording `NOASSERTION` or "none".* This likely rescues R
packages across the health, finance, energy and education KBs too — and note the inverse exists:
`hudl/StatsBombR` has the same `DESCRIPTION` structure and its field reads `3.5.0`, so **read the
value, don't just confirm the field is present.**

**2. A licence delivered as a PDF is invisible to every SPDX field, badge and SBOM scan.**
`hudl/open-data` carries `LICENSE.pdf` at the repository root and GitHub still reports
`NOASSERTION`. Cycle 8 extended the probe list with lowercase `license.txt` and `COPYING.md`; two
more entries are now required: **`LICENSE.pdf`** and **`LICENCE`** (British spelling — which is
exactly how `HiEventsDev/Hi.Events` ships AGPL-3.0, 35,725 B, and why its API licence reads
"Other"). A PDF licence should be flagged *"read manually, do not auto-classify"* — never treated as
absent and never auto-approved.

**3. This corrects pass 18's own stated conclusion.** Pass 18 recorded that "the GitHub API is
unreachable for out-of-session repositories (`403: sessions are bound to their configured
repositories`)" and consequently **dropped every star count from its tables**. That is true only of
the `repos/{owner}/{repo}/...` endpoints. **`search/repositories` with `repo:<slug>` qualifiers works
for arbitrary repositories** and returns stars, forks, SPDX id and `pushed_at` in a single call —
which is how every figure in this pass was obtained, and it accepts several `repo:` qualifiers at
once. Pass 18's star data was lost unnecessarily; later passes should not repeat that.

## The investigative-journalism & source-protection plane — measured 2026-11-26 (pass 20)

> The substrate under the newsroom's craft: secure intake, document mining, records access,
> verification. Verified 2026-11-26 — existence by `git ls-remote`, stars/licence by the
> `search/repositories` channel, **default-branch HEAD by shallow clone**, licence files read
> wherever the API returned `NOASSERTION`.
>
> **The finding that shapes this file:** this plane's live layer is **copyleft and self-hosted**, and
> that is a demand signal, not an accident. The GIJN technology agenda from the GIJC25 pre-conference
> records practitioners asking for ways to analyse large document troves, connect datasets and
> **triage leaks without exposing sensitive data to third-party platforms**. A buyer whose stated
> requirement is "nothing leaves my infrastructure" selects self-hosted AGPL tools, and a SaaS-first
> proposal loses this plane on the first question.

### Secure intake and source protection

| Repo | Stars | Licence (verified) | HEAD | Role |
|---|---|---|---|---|
| https://github.com/onionshare/onionshare | 7,247★ | GPL-3.0 (`LICENSE.txt`, 35,285 B) | 2026-11-26 | Anonymous file transfer / drop over Tor |
| https://github.com/freedomofpress/dangerzone | 5,858★ | AGPL-3.0 | 2026-11-23 | Converts untrusted documents to safe PDFs — the step between a leak and opening it |
| https://github.com/freedomofpress/securedrop | 3,897★ | AGPL-3.0 (`LICENSE`, 34,629 B) | 2026-11-24 | The whistleblower submission system; Tor-based, 22 languages |
| https://github.com/globaleaks/globaleaks-whistleblowing-software | 1,529★ | AGPL-3.0 (`LICENSE`, 41,172 B) | 2026-11-20 (branch `stable`) | Multi-tenant whistleblowing platform, Hermes Center (Italy) |
| https://github.com/scidsg/hushline | 140★ | AGPL-3.0 | 2026-11-14 | Encrypted tip line for an individual or small desk |
| https://github.com/Horizontal-org/Tella-Android | 118★ | MIT | 2026-11-17 | Offline-first encrypted field capture; hides files on-device |
| https://github.com/freedomofpress/securedrop-client | 59★ | AGPL-3.0 | 2026-11-25 | Journalist workstation client (Qubes) |

**Licence note, and a correction to this KB's own probe.** Three of these report `NOASSERTION` on the
GitHub API for three *different* reasons, none of which is a missing licence: OnionShare prepends a
third-party-licences note above the GPL text; SecureDrop prepends a multi-party copyright header
above the AGPL text; Alaveteli (below) ships a multi-licence explainer. **A `NOASSERTION` is a
signal to read the file, never a finding in itself** — the same conclusion cycle 8 reached from the
opposite direction (a 404 on the raw channel is not proof a licence is missing).

### Document mining and entity investigation

| Repo | Stars | Licence | HEAD | Role |
|---|---|---|---|---|
| https://github.com/OpenRefine/OpenRefine | 12,120★ | BSD-3-Clause | 2026-11-24 | The data-cleaning standard for messy records |
| https://github.com/simonw/datasette | 11,670★ | Apache-2.0 | 2026-11-26 | Publish and explore a dataset as a queryable site |
| https://github.com/alephdata/aleph | 2,516★ | MIT | **2025-12-19** (develop) | Entity-centric investigation platform — **see the dormancy finding** |
| https://github.com/ICIJ/datashare | 784★ | AGPL-3.0 | **2026-11-26** | Self-hosted document search, OCR + named-entity extraction (ICIJ) |
| https://github.com/huridocs/uwazi | 330★ | MIT (`LICENSE`, 1,073 B) | 2026-11-26 | Structured documentation database (HURIDOCS); Tella's upload target |
| https://github.com/alephdata/followthemoney | 311★ | MIT | **2025-06-27** | The Aleph entity ontology; last commit reverts "begin project re-homing" |
| https://github.com/ICIJ/extract | 257★ | MIT | 2026-11-23 | Distributed OCR/text extraction at collection scale |
| https://github.com/MuckRock/documentcloud | 54★ | AGPL-3.0 | 2026-11-24 | Document hosting, annotation and publication for newsrooms |
| https://github.com/ICIJ/prophecies | 31★ | AGPL-3.0 | 2026-10-15 | Collaborative data-validation workflow for labour-intensive checking |

### Records access (FOIA / FOI)

| Repo | Stars | Licence | HEAD | Jurisdiction it was built for |
|---|---|---|---|---|
| https://github.com/mysociety/alaveteli | 421★ | AGPL-3.0 (`LICENSE.txt`, 36,128 B) | 2026-11-25 | UK (mySociety); deployed in many countries |
| https://github.com/okfde/froide | 413★ | MIT | 2026-11-09 | Germany (Open Knowledge Foundation DE) |
| https://github.com/MuckRock/muckrock | 124★ | AGPL-3.0 | 2026-11-24 | US federal + state records requests |

### Verification and OSINT

| Repo | Stars | Licence | HEAD | Role |
|---|---|---|---|---|
| https://github.com/sherlock-project/sherlock | 117,843★ | MIT | 2026-11-26 | Username search across ~400 networks — the plane's control group |
| https://github.com/exiftool/exiftool | 5,320★ | GPL-3.0 | 2026-11-16 | Metadata extraction (EXIF/GPS/device) — the first step of image verification |
| https://github.com/bellingcat/telegram-phone-number-checker | 1,934★ | MIT | 2026-08-17 | Telegram account checks from phone numbers |
| https://github.com/bellingcat/ShadowFinder | 631★ | MIT | 2026-09-03 | Chronolocation: narrows where/when a photo was taken from shadow length |
| https://github.com/bellingcat/EDGAR | 219★ | GPL-3.0 | 2025-05-15 | SEC EDGAR filings retrieval for corporate investigation |

### Finding — the Aleph-family dormancy, stated narrowly because the wide version is false

The two **Aleph-family** permissive repos are stale while every AGPL peer in the same sub-layer is
current: `aleph` (MIT, 2,516★) last moved on its default branch `develop` on **2025-12-19**, and
`followthemoney` (MIT, 311★) on **2025-06-27**, its final commit a revert of "begin project
re-homing". Against that: `datashare` (AGPL) pushed **today**, `documentcloud` (AGPL) 2026-11-24,
`prophecies` (AGPL) 2026-10-15.

**The tempting generalisation — "in this plane MIT is the dead licence" — is wrong, and the
measurement says so.** `uwazi` (MIT) pushed today, `extract` (MIT) 2026-11-23, `Tella-Android` (MIT)
2026-11-17, `froide` (MIT) 2026-11-09, `sherlock` (MIT) today. The true claim is confined to the
**Aleph family specifically**, and it matters only because Aleph is the platform every guide
recommends first. **Recommend Datashare or Uwazi for new work and say why; propose Aleph only with
the maintenance position stated to the client.**

### Method correction — `pushed_at` is not liveness, and `ls-remote` is not canonicality

Two corrections to this KB's own verification oracle, both found by contradiction this pass:

1. **`pushed_at` counts any ref, including stale release branches and bot branches.** The search
   channel reported `alephdata/aleph` at `pushed_at=2026-02-20`. Its default branch `develop` last
   moved **2025-12-19**, and `main` is older still — **2025-08-07** (release 4.1.6). A 6-month
   overstatement of liveness on the single most-recommended repo in the plane. `DEFAME` showed the
   same gap (`pushed_at` 2026-05-21, HEAD 2025-09-30). **Rule: resolve the default branch and read
   its last commit — `git clone --depth 1 --single-branch` answers both in one call.**
2. **`git ls-remote` proves reachability, not canonical naming.** `github.com/globaleaks/globaleaks`
   resolves on both the `ls-remote` and raw channels (default branch `stable`) — and it is a
   **rename redirect**. The canonical repository is
   `globaleaks/globaleaks-whistleblowing-software` (1,529★); both HEADs are the identical SHA
   `efa0161c`, which is the proof. GitHub honours renames forever, so `ls-remote` cannot detect one,
   and the search index knows only the new name — which is also why a `repo:globaleaks/globaleaks`
   query fails while the repository plainly exists. **Rule: write the name the search index returns,
   and treat an `ls-remote` success on a name the index rejects as a rename to be resolved.**

### Channel gaps, stated as gaps

- **`api.github.com` is scoped to this session's own repositories** (every third-party call returns
  "GitHub access to this repository is not enabled for this session"), and `github.com` HTML returns
  **403**. All stars, licences and `pushed_at` values in this file therefore come from the sanctioned
  **`gh api search/repositories`** channel, which does serve them. Recording this because it is the
  only metadata oracle currently available, and a future pass that finds the direct API blocked
  should not conclude that star counts are unobtainable.
- **No non-GitHub host resolves from this session.** Verified by probe: `cnti.org`, `unlicense.org`,
  `reutersinstitute.politics.ox.ac.uk`, `latamjournalismreview.org`, `acma.gov.au`, `securedrop.org`,
  `globaleaks.org`, `icij.org`, `opensource.org` and `spdx.org` all return curl `000` / DNS
  `ENOTFOUND`. Consequence: the regional policy figures in `intel/market.md` are attributed to
  **search-result snippets, not primary sources**, and are flagged there as such.
- **Reusable workaround found:** canonical licence texts are reachable through the raw channel at
  `raw.githubusercontent.com/spdx/license-list-data/main/text/<SPDX-ID>.txt` when the licence's own
  site is blocked. That is how the modified Unlicense in `agents/top.md` was proven to be modified.

---

## Pass 21 (2026-11-26) — foundations of the spatial, immersive & volumetric plane

Every row below was verified this pass: existence by `git ls-remote`, stars/forks/HEAD by
`search/repositories`, and **licence by reading the file**, not by trusting the SPDX field. Where
GitHub reported `NOASSERTION` the real terms are given with the file they came from.

### Photogrammetry and structure-from-motion — the capture substrate

| Repo | Stars | Licence (verified) | HEAD | Note |
|---|---|---|---|---|
| https://github.com/colmap/colmap | 13,302★ / 2,241f | new BSD (`LICENSE`, self-declared; GitHub says NOASSERTION) | 2026-11-26 | The SfM/MVS reference everything else poses cameras with. **Its own licence text warns that building with its dependencies may affect the resulting licence** — the linked-library problem cycle 8 recorded for Chromaprint, stated here by the project itself |
| https://github.com/alicevision/Meshroom | 13,116★ / 1,243f | MPL-2.0 (`COPYING.md`) | 2026-11-26 | Node-graph photogrammetry GUI over AliceVision; weak copyleft, file-level |
| https://github.com/openMVG/openMVG | 6,609★ / 1,723f | MPL-2.0 | 2026-11-07 | Multiple-view geometry library |
| https://github.com/OpenDroneMap/ODM | 6,645★ / 1,332f | AGPL-3.0 | 2026-11-24 | Aerial/drone photogrammetry; copyleft reaches a hosted service |

### Radiance fields and splatting — see `agents/top.md` for the licence split

| Repo | Stars | Licence (verified) | HEAD | Note |
|---|---|---|---|---|
| https://github.com/nerfstudio-project/gsplat | 5,961★ / 1,026f | Apache-2.0 | 2026-09-19 | The permissive rasteriser the whole commercial stack rests on |
| https://github.com/nerfstudio-project/nerfstudio | 12,264★ / 1,698f | Apache-2.0 | 2025-07-29 | Framework around it; **13 months without a push — slowing while gsplat continues** |
| https://github.com/ArthurBrussee/brush | 5,392★ / 359f | Apache-2.0 | 2026-11-23 | Rust/WebGPU, CUDA-free |
| https://github.com/MrNeRF/LichtFeld-Studio | 4,040★ / 529f | GPL-3.0 | 2026-11-26 | Native train/inspect/edit/export; pushed the day of measurement, but GPL |
| https://github.com/harry7557558/spirula-studio | 2,624★ / 257f | GPL-3.0 | 2026-11-26 | Cross-vendor trainer, video→splat→mesh, Vulkan or CUDA |
| https://github.com/hustvl/4DGaussians | 4,047★ / 393f | Apache-2.0 | **2024-10-27** | The permissive 4D/temporal implementation — **dormant 25 months**, and the plane's central defect |
| https://github.com/ASU-NEM-Labs/open4dgs-core | 161★ / 17f | MIT | 2026-11-21 | The only permissive, *active* production 4D pipeline found |

### 3D interchange, compression and delivery — permissive and healthy

| Repo | Stars | Licence (verified) | HEAD | Note |
|---|---|---|---|---|
| https://github.com/mrdoob/three.js | 119,448★ / 37,033f | MIT | 2026-11-26 | The web 3D runtime; the single largest permissive asset in this plane |
| https://github.com/godotengine/godot | 120,865★ / 27,647f | MIT | 2026-11-25 | The only MIT engine with a credible XR path; see `GodotVR/godot-xr-tools` |
| https://github.com/pmndrs/react-three-fiber | 33,957★ / 2,140f | MIT | 2026-10-21 | React renderer for three.js |
| https://github.com/BabylonJS/Babylon.js | 26,457★ / 3,748f | Apache-2.0 | 2026-11-26 | Engine with first-class WebXR |
| https://github.com/playcanvas/engine | 17,382★ / 2,075f | MIT | 2026-11-26 | Engine behind SuperSplat; strong glTF extension coverage |
| https://github.com/aframevr/aframe | 17,721★ / 4,407f | MIT | 2026-07-13 | Declarative WebXR; slowing but not dormant |
| https://github.com/CesiumGS/cesium | 15,990★ / 3,906f | Apache-2.0 | 2026-11-26 | Geospatial 3D Tiles streaming at planet scale |
| https://github.com/o3de/o3de | 9,929★ / 2,601f | **Apache-2.0 OR MIT, licensee elects** (`LICENSE.txt`) | 2026-11-26 | Linux Foundation engine; the dual grant is explicit and unusually clean |
| https://github.com/zeux/meshoptimizer | 8,948★ / 770f | MIT | 2026-11-25 | Mesh optimisation + the `EXT_meshopt_compression` path |
| https://github.com/google/model-viewer | 8,360★ / 965f | Apache-2.0 | 2026-11-18 | `<model-viewer>` web component with AR handoff |
| https://github.com/google/draco | 7,569★ / 1,092f | Apache-2.0 | 2026-11-16 | Geometry compression |
| https://github.com/PixarAnimationStudios/OpenUSD | 7,676★ / 1,486f | **Tomorrow Open Source Technology License 1.0** (`LICENSE.txt`, 49,827 B) | 2026-11-25 | **Correction to earlier passes: this is not plain Apache-2.0.** It is Apache-2.0 with §6 "Trademarks" replaced. Permissive in substance; cite it by its real name in any client licence table |
| https://github.com/AcademySoftwareFoundation/MaterialX | 2,316★ / 472f | Apache-2.0 | 2026-11-23 | Material interchange |
| https://github.com/AcademySoftwareFoundation/OpenPBR | 845★ / 47f | Apache-2.0 | 2026-11-16 | The shading model MaterialX now targets |
| https://github.com/CesiumGS/gltf-pipeline | 2,138★ / 261f | Apache-2.0 | 2026-06-23 | glTF conversion/optimisation CLI |
| https://github.com/donmccurdy/glTF-Transform | 2,104★ / 230f | MIT | 2026-10-20 | The scriptable glTF pipeline; the practical choice for a build step |
| https://github.com/KhronosGroup/KTX-Software | 1,413★ / 328f | Apache-2.0 (`LICENSE.md`, mixed copyright holders) | 2026-11-17 | GPU texture containers — the difference between a 40 MB and a 4 MB asset |
| https://github.com/AcademySoftwareFoundation/OpenImageIO | 2,409★ / 727f | Apache-2.0 | 2026-11-26 | Image I/O across the pipeline |
| https://github.com/AcademySoftwareFoundation/openvdb | 3,556★ / 808f | Apache-2.0 | 2026-11-25 | Sparse volumes; already in this KB, re-verified |

### Headset runtimes, streaming and performance capture

| Repo | Stars | Licence (verified) | HEAD | Note |
|---|---|---|---|---|
| https://github.com/google-ai-edge/mediapipe | 37,873★ / 6,253f | Apache-2.0 | 2026-11-25 | Pose/face/hand landmarks; the permissive markerless capture front end |
| https://github.com/freemocap/freemocap | 10,912★ / 1,056f | AGPL-3.0 | 2026-11-14 | Full markerless mocap system — capable, but copyleft |
| https://github.com/alvr-org/ALVR | 8,134★ / 778f | MIT | 2026-11-23 | Streams PC VR to standalone headsets; the cheapest way to demo without a tethered rig |
| https://github.com/vrm-c/UniVRM | 3,432★ / 493f | MIT | 2026-10-19 | VRM avatar interchange runtime |
| https://github.com/WiVRn/WiVRn | 1,882★ / 258f | GPL-3.0 | 2026-11-25 | OpenXR streaming server |
| https://github.com/KhronosGroup/OpenXR-SDK | 1,175★ / 204f | Apache-2.0 | 2026-10-16 | The vendor-neutral device API; the anti-lock-in layer |
| https://github.com/StereoKit/StereoKit | 1,095★ / 138f | MIT | 2026-11-04 | C# XR app framework on OpenXR |
| https://github.com/GodotVR/godot-xr-tools | 749★ / 113f | MIT | 2026-10-10 | Locomotion/interaction toolkit; completes the all-MIT Godot XR chain |
| https://github.com/MPEGGroup/mpeg-pcc-tmc2 | 177★ / 54f | **BSD text that grants no patent rights** (`COPYING`) | 2026-11-17 | V-PCC point-cloud compression reference software. See the note below — this is the plane's patent trap |

### The patent trap, stated precisely

`MPEGGroup/mpeg-pcc-tmc2` is the ISO/IEC reference implementation of V-PCC, the standard for
compressing volumetric point clouds. Its `COPYING` file is a BSD licence whose second sentence reads:
*"This software may be subject to other third party and contributor rights, including patent rights,
and no such rights are granted under this licence."* So the **code** is open and the **codec** is
not. At 177★ it also has no meaningful installed base.

This is the same shape as the HEVC/MV-HEVC path for spatial video: the open encoder route runs through
x265, whose GitHub mirror is **GPL-2.0 and last pushed 2023-09-11** (canonical development is at
VideoLAN, outside GitHub — verify there, not here), over a patent pool. Combined with cycle 8's
Chromaprint finding — where the licence belonged to the *compilation*, not the repository — the rule
for this industry is now general: **for any codec or native dependency, resolve the terms of the
linked libraries and the patent pool, never the SPDX field of the source tree.** No badge, scanner or
SBOM of the source tree can see either.

## The podcast & spoken-audio substrate — measured 2026-11-26 (pass 22)

Podcasting's open substrate is **unusually clean**: the specification, the notification bus, the
analytics prefix and the entire user-agent identification corpus are **CC0 or MIT**, every one of
them, with no copyleft and no registration gate anywhere. This is the most permissive substrate
measured in any plane of this KB. The constraint in this plane is not the substrate — it is layer 3
(the listener-facing app, uniformly copyleft) and layer 4 (ad insertion, which does not exist). See
`agents/top.md` pass 22.

### The specification and its reference infrastructure — all CC0 / MIT

| Repo | License | Stars | Last push | Why it is foundational |
|---|---|---|---|---|
| [Podcastindex-org/podcast-namespace](https://github.com/Podcastindex-org/podcast-namespace) | **CC0-1.0** | 496 | 2026-10-10 | **The Podcasting 2.0 RSS namespace.** Public-domain dedication — no attribution, no licence compatibility question, nothing to clear. The tags behind transcripts, chapters, funding, soundbites, person credits and `alternateEnclosure`. Apple adopted `podcast:transcript` (Mar 2024) and now `podcast:chapters`; Spotify supports the transcript tag. |
| [skymethod/op3](https://github.com/skymethod/op3) | MIT | 144 | 2026-11-26 | **The Open Podcast Prefix Project** — an open, auditable download-analytics prefix. The only open implementation of podcast measurement-of-record. Pushed the day of this pass. |
| [Podcastindex-org/podping.cloud](https://github.com/Podcastindex-org/podping.cloud) | MIT | 50 | 2026-11-25 | Publish-notification bus: replaces polling 4 M feeds with a push signal. The piece that makes near-real-time podcast ingest affordable. |
| [Podcastindex-org/docs-api](https://github.com/Podcastindex-org/docs-api) | MIT | 78 | 2026-07-08 | Developer docs for the podcastindex.org API — the open alternative to Apple's and Spotify's closed catalogues. |
| [Podcastindex-org/web-ui](https://github.com/Podcastindex-org/web-ui) | MIT | 73 | 2026-11-26 | Reference front end over that index. |
| [Podcastindex-org/helipad](https://github.com/Podcastindex-org/helipad) | MIT | 37 | 2026-11-26 | Boost/boostagram receiver — the value4value payment rail, MIT. |
| [podlove/podlove-publisher](https://github.com/podlove/podlove-publisher) | MIT | 310 | 2026-11-17 | **The one MIT publishing platform in the plane.** WordPress-based; emits standards-compliant feeds. Where Castopod is AGPL and microfeed AGPL, this is the permissive publishing base. |

### The measurement corpus — OPAWG, and all of it is MIT

Podcast measurement is server-side by necessity: most apps never confirm playback client-side, so a
download log plus a user-agent corpus **is** the audience number. That corpus is open and permissive.

| Repo | License | Stars | Last push | Why it is foundational |
|---|---|---|---|---|
| [opawg/user-agents](https://github.com/opawg/user-agents) | MIT | 123 | 2025-01-07 | The original Open Podcast Analytics Working Group regex corpus: maps a request's user-agent to an app/bot. Frozen — use v2. |
| [opawg/user-agents-v2](https://github.com/opawg/user-agents-v2) | MIT | 69 | 2026-11-24 | **The current corpus** and the one to build on. Actively maintained. |
| [opawg/podcast-rss-useragents](https://github.com/opawg/podcast-rss-useragents) | MIT | 65 | 2026-11-17 | Agents that fetch *feeds* (as opposed to media) — needed to avoid counting crawlers as listeners. |
| [opawg/podcast-hosts](https://github.com/opawg/podcast-hosts) | MIT | 52 | 2026-09-22 | JSON list of hosting providers + URL patterns: identifies which host serves a show from its audio URL. |
| [opawg/podcast-prefixes](https://github.com/opawg/podcast-prefixes) | MIT | 14 | 2026-11-10 | Prefix-analytics providers and their privacy policies — the input to a GDPR review of a client's existing measurement. |

### Feed, chapter and client libraries — permissive, small, and that is the honest framing

Nothing here is big. They are listed because they are the **only licensed implementations** of steps
a podcast build needs, and because a 5★ MIT client beats writing an API wrapper from scratch.

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [vpetersson/podcast-rss-generator](https://github.com/vpetersson/podcast-rss-generator) | MIT | 54 | 2026-11-23 | Generates a compliant feed for self-hosted audio/video. Active. |
| [dskrad/mp3chaps](https://github.com/dskrad/mp3chaps) | MIT | 82 | 2022-03-12 | Writes ID3 chapter marks. Dormant but the format has not changed. |
| [Mtillmann/chaptertool](https://github.com/Mtillmann/chaptertool) | **NONE** | 45 | 2026-01-24 | Chapter conversion CLI + web, incl. Chapters JSON. Active, useful, **no licence file** → do not vendor. |
| [fnayou/podcastify](https://github.com/fnayou/podcastify) | MIT | 9 | 2026-11-13 | Private/self-hosted feed generator from a directory of audio. |
| [atelier-socle/podcast-feed-maker](https://github.com/atelier-socle/podcast-feed-maker) | Apache-2.0 | 3 | 2026-05-14 | Swift library: generate, parse **and validate** podcast RSS. The only validator-grade library found. |
| [jasonyork/podcast-index](https://github.com/jasonyork/podcast-index) | MIT | 5 | 2026-11-16 | Ruby client for the podcastindex.org API. |
| [brb3/PodcastIndexSharp](https://github.com/brb3/PodcastIndexSharp) | MIT | 5 | 2025-09-06 | .NET client for the same API. |
| [aws-samples/amazon-transcribe-comprehend-podcast](https://github.com/aws-samples/amazon-transcribe-comprehend-podcast) | MIT-0 | 137 | 2023-07-25 | Transcribe → index → search reference architecture. MIT-0 (no attribution). Dormant; useful as a shape, not a dependency. |

### The transcript and clipping layer

Covered elsewhere in this KB and **not duplicated here**: Whisper-family ASR and diarisation
(`pyannote`) are in pass 7's rows; `Demucs`/`Essentia`/`librosa` in pass 12's. For podcasting
specifically, the pieces that matter are `podcast:transcript` (CC0 spec, above) plus the clipping
agents in `agents/top.md` pass 22 (`autoclip` MIT, `VideoAgent` MIT).

### What is NOT here, stated explicitly

- **No open podcast ad server, ad-insertion service or ad-measurement system exists.**
  `audio ad insertion server stars:>=20` → **0 results**. `dynamic ad insertion` → 37, top hit a
  BSD-3 *documentation* repo on broadcast SCTE markers, last pushed **2021-04-13**.
- **No permissive, living, listener-facing app exists.** The permissive one (`GetStream/Winds`,
  BSD-3, 9,078★) died in **2021**; the living ones are GPL/AGPL. The single exception is
  `amugofjava/anytime_podcast_player` (BSD-3, 627★, 2026-04-22) — small, Flutter, and the only
  clean white-label base in the plane.
- **Two major platforms are not on GitHub and were not measured:** Castopod (AGPL-3.0,
  `code.castopod.org`) and Funkwhale (AGPL-3.0, `dev.funkwhale.audio`). Both hosts are blocked by
  this session's egress proxy; figures for them are **not** restated as measured here.

## Pass 23 (2026-11-26) — the still-image, photo-desk & print-production substrate

Licences read from the actual LICENSE file over the raw channel; stars and last-push from
`gh api -X GET search/repositories` (the REST `/repos/*` endpoint is blocked in this session).
`n/a` = exists and serves git, but invisible to the search index — never guessed.

### The central structural finding of this pass

**Licensing in this plane tracks the *lineage* of the layer, not its position in the stack.**

Every previous pass of this KB confirmed a law of the form "the substrate is permissive, the
judgment layer is empty". This plane splits that law in a way no earlier pass could see, because it
is the first plane holding two substrates with different ancestries:

- **The pixel substrate descends from web infrastructure** → Apache-2.0, MIT, BSD, almost
  without exception, and all of it pushed within the last week.
- **The page-and-print substrate descends from desktop applications** → GPL-2.0, GPL-3.0 and
  **AGPL-3.0**, almost without exception.

Both are "substrate". Both are mature. Both are actively maintained. **One is free to build a
product on and the other is not** — and the predictor is not how fundamental the layer is, it is
whether the code grew up in a browser/CDN world or in a desktop-publishing world. Written down
because it is directly actionable: it tells you which half of an imaging engagement can be
productised and which half can only be deployed.

### Layer 1 — image codecs (permissive; the floor of the plane)

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [libjxl/libjxl](https://github.com/libjxl/libjxl) | BSD-3-Clause | 3,871 | 2026-11-26 | JPEG XL reference codec. The successor format; permissive and pushed daily. |
| [webmproject/libwebp](https://github.com/webmproject/libwebp) | BSD-3-Clause | 2,435 | 2026-11-25 | WebP encode/decode. The format with real browser ubiquity today. |
| [strukturag/libheif](https://github.com/strukturag/libheif) | LGPL-3.0 | 2,427 | 2026-11-24 | HEIF/HEIC — the format every iPhone shoots. API reports `NOASSERTION`; `COPYING` (44,366 B) read and it is LGPL-3.0. **Link, do not statically fold in.** |
| [AOMediaCodec/libavif](https://github.com/AOMediaCodec/libavif) | BSD-2-Clause | 2,237 | 2026-11-26 | AVIF container/codec. API reports `NOASSERTION`; LICENSE (20,415 B) read and it is BSD-2-Clause. |
| [mozilla/mozjpeg](https://github.com/mozilla/mozjpeg) | IJG + BSD-3-Clause (+ zlib for SIMD) | 5,748 | 2025-06-23 | Still the best-in-class baseline-JPEG encoder. **Dormant ~17 months.** A *three-licence composite in one repo* — see the warning below. |

### Layer 2 — processing engines and servers (permissive; four competitors, one engine)

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [lovell/sharp](https://github.com/lovell/sharp) | Apache-2.0 | 32,872 | 2026-11-26 | The Node binding to libvips. The most-deployed resize layer in JS. |
| [ImageMagick/ImageMagick](https://github.com/ImageMagick/ImageMagick) | ImageMagick License (own, permissive) | 17,946 | 2026-11-26 | Universal conversion/composition. Its own licence explicitly permits commercial use, linking across licences, and merging into differently-licensed works. |
| [libvips/libvips](https://github.com/libvips/libvips) | LGPL-2.1 | 11,841 | 2026-11-25 | The streaming, low-memory engine under sharp, imgproxy, imagor and imaginary. |
| [imgproxy/imgproxy](https://github.com/imgproxy/imgproxy) | Apache-2.0 | 11,220 | 2026-11-24 | Signed-URL image server in Go. OSS core Apache-2.0; a paid Pro tier exists. |
| [thumbor/thumbor](https://github.com/thumbor/thumbor) | MIT | 10,533 | 2026-11-21 | Python smart-crop server; the widest transformation set and a plugin model. |
| [image-rs/image](https://github.com/image-rs/image) | MIT OR Apache-2.0 | 5,920 | 2026-11-11 | Pure-Rust imaging; dual-licensed, no native linking question at all. |
| [cshum/imagor](https://github.com/cshum/imagor) | Apache-2.0 | 4,065 | 2026-11-21 | Thumbor-compatible URLs on a Go/libvips core — the migration target off thumbor. |
| [weserv/images](https://github.com/weserv/images) | BSD-3-Clause | 2,865 | 2026-11-01 | Production nginx+libvips image CDN, open-sourced. |

### Layer 3 — image metadata (where the editorial facts live)

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [exiftool/exiftool](https://github.com/exiftool/exiftool) | **Artistic-1.0-Perl OR GPL-1.0-or-later** | 5,321 | 2026-11-16 | The universal read/write tool for EXIF, IPTC and XMP — the de facto standard for photo metadata. **The GitHub API reports `GPL-3.0` and that is wrong**: the repo ships a GPL-3.0 text, but the README states the terms are "the same terms as Perl itself (either the Perl Artistic License or GPL)". The permissive option is available to you. |
| [Exiv2/exiv2](https://github.com/Exiv2/exiv2) | GPL-2.0 | 1,174 | 2026-11-23 | C++ metadata library behind many desktop photo tools. API reports `NOASSERTION`; `COPYING` (18,092 B) read and it is GPL-2.0, **not** LGPL. |
| [ianare/exif-py](https://github.com/ianare/exif-py) | BSD-3-Clause | 978 | 2026-06-10 | Pure-Python EXIF reader; the permissive choice when you only need to read. |

IPTC Photo Metadata is the schema a picture desk actually fills in, and `exiftool` is how it gets
written. This KB already covers IPTC *NewsML* for story interchange (pass 11); the **photo**
side of IPTC enters the KB here.

### Layer 4 — colour, type and shaping (the permissive half of print)

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [google/fonts](https://github.com/google/fonts) | **per-family OFL-1.1 / Apache-2.0 / UFL** — no root licence | 20,807 | 2026-11-26 | The font library itself. **There is no repository-level LICENSE file**: licences live per family under `ofl/`, `apache/` and `ufl/` (e.g. `ofl/roboto/OFL.txt`). A scanner that looks only at the root concludes "unlicensed" and is wrong. |
| [harfbuzz/harfbuzz](https://github.com/harfbuzz/harfbuzz) | "Old MIT" | 6,259 | 2026-11-26 | The text-shaping engine behind essentially every modern renderer. API reports `NOASSERTION`; `COPYING` read — MIT-variant, **with per-subdirectory COPYING files and Unicode data under its own notice.** |
| [fonttools/fonttools](https://github.com/fonttools/fonttools) | MIT | 5,338 | 2026-11-25 | Python font manipulation: subsetting (`pyftsubset`), TTX round-tripping, and `varLib` for building variable fonts from a designspace. Latest release reported as 4.64.0 (2026-08-31). |
| [mm2/Little-CMS](https://github.com/mm2/Little-CMS) | MIT | 764 | 2026-11-26 | **The single most strategically important repo in the print half of this plane.** ICC colour management — the thing that makes a CMYK proof match the press. MIT, pushed the day of this pass, and **764 stars**. Scribus, GIMP and Krita all depend on it. |
| [googlefonts/fontbakery](https://github.com/googlefonts/fontbakery) | Apache-2.0 | n/a | — | Font QA: validates a font family against Google Fonts / OpenType spec checks. Exists; invisible to the search index. |

`Little-CMS` at 764 stars, under MIT, maintained, and load-bearing for every open-source
publishing application is the clearest instance in this KB of **critical infrastructure with no
constituency.** If a print engagement depends on colour fidelity, this is the dependency to read.

### Layer 5 — page, PDF and print (the copyleft half, with four permissive exceptions)

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [mozilla/pdf.js](https://github.com/mozilla/pdf.js) | Apache-2.0 | 54,196 | 2026-11-26 | Browser PDF rendering. **Permissive exception #1** — and by far the most-starred repo in this layer. |
| [py-pdf/pypdf](https://github.com/py-pdf/pypdf) | BSD-3-Clause | 10,319 | 2026-11-26 | Python PDF read/write/split/merge. API reports `NOASSERTION`; LICENSE (1,605 B) read — BSD-3-Clause. **Permissive exception #2.** |
| [pdfcpu/pdfcpu](https://github.com/pdfcpu/pdfcpu) | Apache-2.0 | 8,922 | 2026-11-02 | Go PDF processor with imposition, validation and page manipulation. **Permissive exception #3.** |
| [qpdf/qpdf](https://github.com/qpdf/qpdf) | Apache-2.0 | 5,618 | 2026-09-26 | Structural PDF transformation and linearisation — the tool for repairing a broken print PDF. **Permissive exception #4.** |
| [pdfarranger/pdfarranger](https://github.com/pdfarranger/pdfarranger) | GPL-3.0 | 6,085 | 2026-11-13 | Page-level reordering, rotation and imposition GUI. |
| [ArtifexSoftware/mupdf](https://github.com/ArtifexSoftware/mupdf) | AGPL-3.0 | 3,073 | 2026-11-25 | Lightweight, fast PDF/XPS renderer. **AGPL.** Commercial licence sold by Artifex. |
| [OpenPrinting/cups](https://github.com/OpenPrinting/cups) | Apache-2.0 | 1,803 | 2026-11-25 | The printing system itself — queues, drivers, IPP. Relicensed to Apache-2.0 years ago; the one piece of the physical-output path that is permissive. |
| [scribusproject/scribus](https://github.com/scribusproject/scribus) | GPL-2.0-or-later | 659 | 2026-11-26 | **The only open-source professional page-layout application** — the InDesign substitute. PDF/X-1a, PDF/X-3 and PDF/X-4 export with embedded ICC press profiles. Reported stable 1.6.6 and preview 1.7.3, both 2026-04-13. Pushed the day of this pass, with 659 stars. |
| [veraPDF/veraPDF-library](https://github.com/veraPDF/veraPDF-library) | **GPL-3.0+ OR MPL-2.0+** (dual) | 352 | 2026-11-22 | The industry-reference PDF/A validator, built for archives and regulated print. **Its default branch is `integration`, and its licences are `LICENSE.GPL` and `LICENSE.MPL`** — a conventional probe finds neither. The MPL-2.0 option makes this *usable alongside proprietary code*, which the GPL option alone would not. |
| [ArtifexSoftware/ghostpdl](https://github.com/ArtifexSoftware/ghostpdl) | AGPL-3.0 (composite, per-directory) | 310 | 2026-11-24 | Ghostscript — PostScript/PDF interpretation and rasterisation; the RIP. Required by Scribus for EPS/PS import and print preview. **See the composite-licence warning below.** |

**The print path has a 310-star, AGPL-licensed single point of failure.** Ghostscript is how a
PDF becomes ink, Scribus depends on it, and it is AGPL with a commercial licence sold alongside.
Any print-production engagement must answer the Ghostscript licensing question explicitly and
early; it is not a detail.

### Layer 6 — RAW decoding and the darkroom (uniformly copyleft)

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [darktable-org/darktable](https://github.com/darktable-org/darktable) | GPL-3.0 | 13,508 | 2026-11-26 | The leading open RAW developer. **5.6 (June 2026) added an opt-in AI subsystem** — `neural restore` for RAW denoise, denoise and upscale, plus an AI object-mask tool and HEIF export; disabled by default and gated behind a build flag. See `repos/trending.md` pass 23. |
| [LibRaw/LibRaw](https://github.com/LibRaw/LibRaw) | **LGPL-2.1 OR CDDL-1.0** (dual) | 1,640 | 2026-11-26 | The library that decodes every camera's RAW format — the dependency under darktable, RawTherapee and ART. **Licence files are `COPYRIGHT`, `LICENSE.LGPL` and `LICENSE.CDDL`**; a probe for `LICENSE`/`COPYING` finds nothing and a careless reading calls it unlicensed. |
| [Beep6581/RawTherapee](https://github.com/Beep6581/RawTherapee) | GPL-3.0 | n/a | — | The other major open RAW developer. **Default branch is `dev`.** Invisible to the search index. |
| [artpixls/ART](https://github.com/artpixls/ART) | GPL-3.0 | n/a | — | A RawTherapee derivative focused on a simpler pipeline and local editing. Licence in `LICENSE.txt` (33,345 B). |

### Composite-licence warnings — the pattern cycle 8 found with Chromaprint, now confirmed twice more

Cycle 8 recorded that **a licence can belong to the compilation rather than the repository**
(`acoustid/chromaprint`: own code MIT, but LGPL-2.1 as a whole because it links FFmpeg). This pass
found two more instances, which makes it a structural property of native media code rather than an
anecdote:

- **`ArtifexSoftware/ghostpdl` — licence varies by directory.** Its LICENSE states that `base`,
  `psi`, `lib`, `toolbin`, `examples`, `doc`, `man`, `iccprofiles`, `pcl`, `xps` and `gpdl` are GPL
  Ghostscript; that `Resource` is too **except** the Adobe-copyrighted `CMap` files, which are under
  a separate AGPL-compatible licence; and that the fonts in `Resource/Font` are AGPL **with a
  written exemption**. One repository, four licensing regimes, none visible from a root-level scan.
- **`GNOME/gimp` — GPL with an explicit plug-in exemption.** Its LICENSE carries a deliberate
  carve-out stating that *"arbitrarily-licensed programs such as GIMP plug-ins do not automatically
  assume the GPL themselves simply because of their invocation of (or by) procedures"*. This is
  materially useful: **a proprietary GIMP plug-in is contemplated and permitted by the project.**
  An SPDX field reading `GPL-3.0` tells you the opposite of what the licence actually says.
- **`mozilla/mozjpeg` — three licences in one tree.** The IJG licence covers the libjpeg API, the
  3-clause BSD covers the TurboJPEG API and build system, and the SIMD code is zlib-licensed
  (subsumed by IJG in context).

**Reusable rule, now with three independent confirmations: for any native media dependency, resolve
the licence of the *linked libraries and the specific directories you ship*, not of the repository.
No SPDX field, badge or source-tree SBOM scan can see this.**

## The owned-channel & audience-relationship plane — measured 2026-11-26 (pass 24)

The substrate under the owned channel: sending, rendering, delivering, pushing, hosting the
conversation, taking consent, and resolving identity without a third-party cookie. Until this pass
**no file in this KB contained the string `email`** — see `agents/top.md` pass 24 for how the gap was
found. All rows verified 2026-11-26 via the GitHub API, with licence files **read** wherever the API
returned `NONE` or `NOASSERTION`.

**The shape of this plane, stated before the tables:** it is permissive and healthy at the
**transport** layer, copyleft at the **list-management** layer, and a near-zero at the **consent and
identity** layer. That is the KB's structural law ordered by liability — the full gradient is in
`agents/top.md`.

### Sending & list management — the layer the industry is retreating to, and it is mostly copyleft

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [knadh/listmonk](https://github.com/knadh/listmonk) | **AGPL-3.0** | 24,473 | 2,836 | 2026-11-26 | The default self-hosted newsletter and mailing-list manager: single Go binary, Postgres, template engine, bounce processing, per-subscriber attributes. **AGPL — keep at arm's length from client-proprietary code** (see the licence note below). |
| [mautic/mautic](https://github.com/mautic/mautic) | **GPL-3.0-or-later** (LICENSE.txt read) | 11,123 | 3,572 | 2026-11-26 | Full marketing automation: segments, campaigns, drip, landing pages, CRM hooks. The API reports `NOASSERTION`; the file is unambiguous GPLv3-or-later. Heaviest option here, and the only one with real campaign logic. |
| [Mailtrain-org/mailtrain](https://github.com/Mailtrain-org/mailtrain) | GPL-3.0 | 5,748 | 707 | 2026-11-25 | Self-hosted newsletter app; older lineage, still maintained. |
| [pentacent/keila](https://github.com/pentacent/keila) | **AGPL-3.0** | 2,269 | 180 | 2026-11-24 | Elixir newsletter tool, **EU-built and EU-hosted** — the one to name first in an EMEA engagement where data residency is the objection. |
| [mettle/sendportal](https://github.com/mettle/sendportal) | **MIT** | 2,193 | 475 | 2026-10-22 | **The only permissively-licensed newsletter manager in this plane.** Laravel, self-hosted, bring-your-own SMTP relay. 2,193 stars against listmonk's 24,473 — i.e. **the permissive option has 9% of the copyleft option's adoption**, which is the choice a client actually has to make. |
| [TryGhost/Ghost](https://github.com/TryGhost/Ghost) | MIT | 55,925 | 12,088 | 2026-11-26 | Already in `verticals/solutions.md`; re-verified here because **publishing + memberships + newsletters in one MIT codebase** makes it the shortest path to an owned channel with a paywall attached. |

**The licence trap in this row set, stated plainly:** the newsletter layer is the first layer in this
KB where the **most-adopted option is AGPL and the permissive option is 9% of its size**. AGPL's
network clause bites when the client's subscribers interact with a modified copy over a network —
which is the whole point of a newsletter platform. Either (a) run listmonk unmodified as a service
boundary behind an API, (b) take `sendportal` (MIT) and accept the smaller community, or (c) take
Ghost (MIT) if memberships are in scope anyway. **Do not fork listmonk into a client's codebase.**

### Rendering the message — permissive, boring, and genuinely solved

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [resend/react-email](https://github.com/resend/react-email) | MIT | 20,008 | 1,122 | 2026-11-26 | Compose emails as React components. The current default for a team that already has a React front end. |
| [mjmlio/mjml](https://github.com/mjmlio/mjml) | MIT | 18,305 | 1,007 | 2026-11-26 | The markup language that makes responsive email survive Outlook. Still the most portable choice — output is plain HTML, no runtime. |
| [maizzle/framework](https://github.com/maizzle/framework) | MIT (LICENSE read) | 1,624 | 69 | 2026-11-25 | Tailwind-based email framework. **Note the repo name**: `maizzle/maizzle` (2,864★) is the *starter template* and carries **no licence file** — see the star-count decoy finding in `agents/top.md`. |

This is the one layer of the plane with no gap: three MIT projects, all pushed this week, all with
real licence files. **Charge nothing for solving it and spend the budget on the consent layer.**

### Delivery & deliverability — permissive transport, and the measurement layer nobody installs

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [postalserver/postal](https://github.com/postalserver/postal) | MIT | 16,982 | 1,325 | 2026-11-20 | Full open mail-delivery platform (in and out): queues, per-domain DKIM, bounce and click webhooks, message-level tracing. **The permissive answer to "we don't want to depend on SES."** |
| [axllent/mailpit](https://github.com/axllent/mailpit) | MIT | 11,044 | 381 | 2026-11-25 | SMTP capture + API for testing. Belongs in every newsletter CI pipeline; it is how you prove a template before a 2-million send. |
| [Mailu/Mailu](https://github.com/Mailu/Mailu) | **MIT** (LICENSE.md read) | 7,642 | 1,037 | 2026-11-25 | Docker-image mail server. API reports `NOASSERTION`; the file is plain MIT. |
| [foxcpp/maddy](https://github.com/foxcpp/maddy) | GPL-3.0 | 6,142 | 346 | 2026-11-21 | Composable all-in-one mail server in Go. Copyleft — infrastructure, so usually fine at a service boundary. |
| [haraka/Haraka](https://github.com/haraka/Haraka) | MIT | 5,646 | 720 | 2026-11-23 | Event-driven, highly extensible SMTP server. The one to pick when the *plugin* surface is the requirement. |
| [domainaware/parsedmarc](https://github.com/domainaware/parsedmarc) | Apache-2.0 | 1,321 | 277 | 2026-11-23 | Parses aggregate + forensic **DMARC** reports into Elasticsearch/Splunk/OpenSearch. **The quietest high-value row in this file.** |

**Why `parsedmarc` deserves more attention than its 1,321 stars:** deliverability is now the binding
constraint on the owned channel, and it has become *measurable* in exactly one place. Gmail retired
its High/Medium/Low domain and IP reputation scores, replacing them in Postmaster Tools v2 with a
compliance checklist and a deliverability verdict; Apple Mail Privacy Protection already made the
open rate unusable (vendor estimates put the inflation at **4–8 percentage points**, unverified); and
Gmail's Gemini summaries appear to **auto-open** messages, inflating opens while clicks fall. When
the open rate dies as a metric, **DMARC aggregate reports and click/conversion are what remain** —
and `parsedmarc` is the Apache-2.0 way to own that evidence rather than rent it.

### Web push — the second owned channel, permissive and unglamorous

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [novuhq/novu](https://github.com/novuhq/novu) | **MIT** (LICENSE read) | 40,432 | 4,571 | 2026-11-26 | Notification infrastructure: one API, multi-channel (email/SMS/push/in-app), templates, subscriber preferences, digest batching. API reports `NOASSERTION`; the file is plain MIT. **The highest-starred permissive repo in this entire plane** — and it is the orchestration layer, not a channel. |
| [binwiederhier/ntfy](https://github.com/binwiederhier/ntfy) | Apache-2.0 | 35,771 | 1,753 | 2026-11-25 | Pub/sub push over HTTP PUT/POST, self-hostable. Operationally trivial; built for alerts, usable for breaking-news fan-out. |
| [web-push-libs/web-push](https://github.com/web-push-libs/web-push) | **MPL-2.0** (LICENSE read) | 3,580 | 331 | 2026-11-23 | The Node Web Push (RFC 8030/8291/8292, VAPID) library. File-level copyleft only — safe to depend on. |
| [mozilla-services/autopush-rs](https://github.com/mozilla-services/autopush-rs) | MPL-2.0 | 363 | 32 | 2026-11-25 | Mozilla's production push server in Rust — the reference for *operating* a push endpoint at scale. |
| [web-push-libs/pywebpush](https://github.com/web-push-libs/pywebpush) | MPL-2.0 | 381 | 61 | 2026-09-01 | Python payload-encryption counterpart. |

**The subscription-storage caveat that breaks push projects:** the Web Push libraries encrypt and
deliver; they do **not** store subscriptions. That is the publisher's database, which means push
subscriptions are first-party data governed by the same consent record as everything else in this
plane. On iOS the site must ship a web-app manifest and the user must add it to the Home Screen —
plan for a materially smaller addressable push audience there than on Android.

### Hosting the conversation — and the 24× liability discount

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [discourse/discourse](https://github.com/discourse/discourse) | GPL-2.0 | 48,117 | 9,057 | 2026-11-26 | The general-purpose community platform. Enormous, active, copyleft. |
| [NodeBB/NodeBB](https://github.com/NodeBB/NodeBB) | GPL-3.0 | 15,254 | 2,999 | 2026-11-26 | Node.js forum, real-time first. |
| [umputun/remark42](https://github.com/umputun/remark42) | **MIT** | 5,654 | 463 | 2026-11-25 | Lightweight embeddable comment engine, Go, privacy-friendly. **The permissive pick for bolting comments onto an existing site.** |
| [isso-comments/isso](https://github.com/isso-comments/isso) | MIT | 5,316 | 464 | 2026-10-25 | Self-hosted Disqus alternative, Python. Note the org rename — `posativ/isso` no longer resolves in search. |
| [coralproject/talk](https://github.com/coralproject/talk) | **Apache-2.0** (LICENSE read, © 2025 Vox Media) | **2,005** | 374 | 2026-11-26 | **The only comment platform in existence built for newsrooms.** Pre/post-moderation per stream, moderation queues, banned/suspect word lists, Slack integration, AI-assisted moderation, publisher owns the audience data, ad-free, GDPR-conscious. Born at Mozilla + the Washington Post; maintained by Vox Media; pushed **today**. |
| [unitaryai/detoxify](https://github.com/unitaryai/detoxify) | Apache-2.0 | 1,320 | 149 | 2026-11-11 | The open toxicity model (Jigsaw challenges). The classifier an open moderation agent would call — nothing currently wires it to a comment platform. |
| ⛔ [djyde/cusdis](https://github.com/djyde/cusdis) | GPL-3.0 | 2,773 | 294 | 2026-07-17 | **ARCHIVED.** Do not start new work here. Recorded so a directory listing does not resell it. |

**The control case.** Hosting comments *generically* is a 48,117-star problem. Hosting comments *in a
newsroom*, where every published comment is the publisher's legal and editorial exposure, is a
**2,005-star** problem — and that repo exists only because two news organisations funded it. One
function, two liability regimes, **24× the code**. This is the tightest evidence for this KB's
structural law found in twenty-four passes, and it is quotable to a client in one sentence.

### Consent, CDP and identity — the near-zero at the end of the gradient

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [orestbida/cookieconsent](https://github.com/orestbida/cookieconsent) | MIT | 5,785 | 505 | 2026-11-22 | Already in this file (pass 2). The practical consent **banner** — UI, not compliance. |
| [jitsucom/jitsu](https://github.com/jitsucom/jitsu) | MIT | 5,140 | 403 | 2026-11-26 | MIT, scriptable event ingestion — the permissive CDP ingest layer. **No identity resolution**; you build that. |
| [c15t/c15t](https://github.com/c15t/c15t) | **Apache-2.0** | 2,045 | 287 | 2026-11-26 | Headless, developer-first consent manager for React/Next/Vue/JS, with an optional `@c15t/iab` add-on for **TC-string generation**. The best-licensed CMP in the open set, and the only one that is both Apache-2.0 and active. |
| [apache/unomi](https://github.com/apache/unomi) | Apache-2.0 | **382** | 148 | 2026-11-26 | **The only genuinely Apache-licensed customer data platform that exists.** ASF-governed, profile and segment store, consent-aware by design. 382 stars, pushed today. |
| [InteractiveAdvertisingBureau/iabtcf-es](https://github.com/InteractiveAdvertisingBureau/iabtcf-es) | Apache-2.0 | **156** | 101 | 2026-11-03 | The **official** TCF v2 encode/decode suite. 156 stars for the library that makes EMEA ad consent lawful. |
| [InteractiveAdvertisingBureau/Global-Privacy-Platform](https://github.com/InteractiveAdvertisingBureau/Global-Privacy-Platform) | **CC-BY-3.0 — documents, not code** (README read) | 128 | 54 | 2026-11-04 | The GPP spec: one consent string spanning GDPR + US state regimes. **No licence file; the README licenses the *specification* under Creative Commons, and the IAB Tech Lab IPR policy overrides it for members.** Demoted on sight, per pass 4's rule. |
| [IABTechLab/uid2-operator](https://github.com/IABTechLab/uid2-operator) | Apache-2.0 | **18** | 19 | 2026-11-26 | **The cookie replacement for the open web, with eighteen stars.** Apache-2.0, pushed today, not abandoned — simply not self-served, because operating it means holding other parties' hashed emails under GDPR/LGPD. |
| [ory/kratos](https://github.com/ory/kratos) | Apache-2.0 | 13,983 | 1,223 | 2026-07-29 | Identity capture — the registration/login wall that converts an anonymous reader into a known one. Already referenced in this KB; re-verified. **Four months without a push.** |
| ⛔ [rudderlabs/rudder-server](https://github.com/rudderlabs/rudder-server) | **Elastic License 2.0** (LICENSE read) | 4,521 | 85 | 2026-11-26 | **Not open source.** The CDP every 2026 listicle calls open source. ELv2 forbids managed-service provision to third parties — i.e. exactly an integrator engagement. |
| ⛔ [ConsentOS/consentos](https://github.com/ConsentOS/consentos) | **Elastic License 2.0** (LICENSE read) | 25 | 11 | 2026-10-24 | Same restriction. TCF v2.3 + GPP v1 + Consent Mode v2 + GPC, but source-available only. |

**Read the star counts in that table as one sentence:** the banner that *asks* for consent has 5,785
stars; the library that *encodes* consent lawfully has 156; the spec that *carries* it across
jurisdictions is not software; and the operator that *acts* on it has 18. **The further a component
sits from the user interface and the closer it sits to the liability, the less code exists.**

### The regulatory clock on the consent layer — why this is an EMEA-first build

Dates matter here more than in any other plane in this KB, because they are already past:

- **TCF v2.3 became mandatory** for TC strings generated on or after **1 March 2026** (Google's
  publisher guidance; iubenda gives 28 February 2026 — the discrepancy is one day and does not
  change the posture).
- **TCF v2.4 specifications and the updated Global Vendor List published 23 July 2026**, with the
  **website deadline 23 October 2026** and a later date for apps and CTV.
- **No open-source CMP is IAB-registered.** A publisher integrating TCF needs a *registered* CMP;
  `c15t` and `iabtcf-es` give you the string and the UI, not the registration. **Say this before a
  client assumes the open stack discharges the obligation — it does not.**

---

## The traffic, sales-order-to-air & billing substrate — measured 2026-11-26 (pass 25)

The substrate under the commercial administration of linear and FAST inventory. All rows verified
2026-11-26: `git ls-remote` for existence, `search/repositories -f q='repo:<slug>'` for canonical slug
+ stars + forks + last push + SPDX, and **licence files read** wherever the API returned `NONE` or
`NOASSERTION`. 20/20 slugs resolved; 20/20 indexed at the slug written here.

### The scheduling and playout substrate (step 1 of the gradient — healthy)

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [nebulabroadcast/nebula](https://github.com/nebulabroadcast/nebula) | **GPL-3.0** (35,141 B) | 332 | 38 | 2026-11-23 | **The anchor of this plane, and a correction to this KB**, which recorded the old `immstudios/nebula` slug as "dead". Broadcast automation + MAM for TV, radio and VOD; *"since 2012 … used by TV and production companies worldwide"*; Python 3.14 + React. Does linear **planning, scheduling, playout and asset management together** — no other open system does. |
| [nebulabroadcast/nebula-worker](https://github.com/nebulabroadcast/nebula-worker) | **GPL-3.0** | 6 | 3 | 2026-11-15 | The media-processing worker. Required for a real deployment, not optional. |
| [nebulabroadcast/firefly](https://github.com/nebulabroadcast/firefly) | **GPL-3.0** | 29 | 6 | 2026-10-30 | Desktop client for linear planning/scheduling/playout. **Being phased out** per its own README (web UI has feature parity). Choose it only against a hard desktop requirement. |
| [nebulabroadcast/nebula-tutorial](https://github.com/nebulabroadcast/nebula-tutorial) | **NONE** | 13 | 9 | 2025-12-20 | The official starting point (compose file, default settings, plugins) — **with no licence file** (11 names × 2 branches; control README = 200). Read it, do not copy it into a client repo. |
| [ElvishArtisan/rivendell](https://github.com/ElvishArtisan/rivendell) | **GPL-2.0** — API says `NONE`; verified by reading `COPYING` (17,992 B) | 250 | 76 | 2026-08-26 | Full-featured radio automation for professional broadcast. **Its README is the architectural evidence of this pass:** it *"supports importation of schedule information from a wide variety of third-party traffic and music scheduling systems"* — i.e. the most mature open radio automation system **delegates traffic to proprietary vendors by design.** |
| [AzuraCast/AzuraCast](https://github.com/AzuraCast/AzuraCast) | **AGPL-3.0** | **4,118** | 764 | 2026-11-25 | **New to this KB.** Self-hosted web radio management suite with turnkey installers for the whole stack. The highest-starred broadcast-operations platform in the plane. Operations and scheduling, **not** traffic: no rate cards, no invoicing. |
| [libretime/libretime](https://github.com/libretime/libretime) | AGPL-3.0 | 941 | 251 | 2026-11-22 | Already catalogued (pass 5). Listed to complete the tier. |
| [mint-dewit/folderplayout](https://github.com/mint-dewit/folderplayout) | **MIT** | 64 | 7 | 2023-12-31 | CasparCG client for scheduled recurring playlist playback — **the one permissive link between a schedule and a playout engine.** Dormant since 2023, small enough to read and fork. |
| [itsoumya-d/rcs-music-scheduler](https://github.com/itsoumya-d/rcs-music-scheduler) | **MIT** | **0** | — | 2026-11-06 | C# .NET 10 radio music scheduler: rotation, separation, **dayparts**, conflict explanations. **The only repo in this KB that contains the word *daypart*** — and it has zero stars. Recorded as a measured zero, not a recommendation. |
| [mickaelmonsieur/openstudio](https://github.com/mickaelmonsieur/openstudio) | **GPL-3.0** | **0** | — | 2026-06-14 | Rust desktop radio-automation **prototype** with a PostgreSQL-backed library. Zero stars; listed for the record. |

### The billing substrate the plane has to borrow (step 3 — empty, so compose it)

None of these is media-specific, and that is precisely the finding: the broadcaster's revenue step has
to be assembled from general-purpose permissive engines because no broadcast-specific open one exists.

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [killbill/killbill](https://github.com/killbill/killbill) | **Apache-2.0** | **5,870** | — | 2026-11-26 | Subscription billing and payments. The invoice/credit engine for reconciled spots and makegood obligations. |
| [killbill/killbill-admin-ui](https://github.com/killbill/killbill-admin-ui) | **MIT** | 70 | — | 2026-11-26 | Admin UI engine for Kill Bill. |
| [killbill/killbill-commons](https://github.com/killbill/killbill-commons) | **Apache-2.0** | 145 | — | 2026-10-06 | Reusable Java components. |
| [killbill/killbill-cloud](https://github.com/killbill/killbill-cloud) | **Apache-2.0** | 68 | — | 2026-11-19 | Deployment utilities. |
| [aureuserp/aureuserp](https://github.com/aureuserp/aureuserp) | **MIT** | **12,301** | — | 2026-11-24 | **New to this KB.** Laravel ERP with invoicing and accounting — the most-starred MIT ERP found in 25 passes. Relevant because the missing step in this plane is an accounting step. |
| [openmeterio/openmeter](https://github.com/openmeterio/openmeter) | **Apache-2.0** | 2,471 | 247 | 2026-11-26 | Already catalogued. Usage metering — the delivered-impressions side of addressable and CTV breaks. |

### The interchange substrate — and why it is a licence gate, not a library choice

| Repo | License | Stars | Forks | Last push | Finding |
|---|---|---|---|---|---|
| [SMPTE/st2021-4](https://github.com/SMPTE/st2021-4) | **All Rights Reserved** (API: `NOASSERTION`; `LICENSE.md`, 269 B, read in full) | 2 | 1 | 2026-11-11 | Official BXF (SMPTE ST 2021-4) schema documentation. *"All rights reserved. No part of this material may be reproduced, by any means whatsoever, without the prior written permission of the Society of Motion Picture and Television Engineers."* **Public on GitHub, not redistributable.** |
| [JoeldelPilar/bxf-manager](https://github.com/JoeldelPilar/bxf-manager) | **NONE** (11 names × 2 branches; control README = 200 → real absence) | 4 | 1 | 2025-10-09 | The only BXF tool on GitHub. No grant ⇒ all rights reserved by default. |

**There is no usable open BXF implementation and the schema cannot be vendored.** BXF support is built
from the specification under the client's own SMPTE entitlement — see Pattern 25.3, which states the
gate before anyone estimates the work.

### Measured absences in the substrate

`broadcast as-run reconciliation` → **0 results.** `spot booking advertising` → **0 results.**
The sole as-run artefact on GitHub is [alochbaum/CheckAsRun](https://github.com/alochbaum/CheckAsRun)
(**0★, no licence, no README, 2016-04-21**), confirmed by cloning rather than by inferring from a 404.
`broadcast erp` → [stukenov/broadcast-erp](https://github.com/stukenov/broadcast-erp) (**MIT, 0★**,
2026-11-16), one of six same-author playout repos all pushed the same day with 0–3 stars: unproven,
recorded for completeness only. Contaminated totals that look like coverage and are not:
`broadcast traffic` 163/**0 relevant**, `radio traffic` 246/**0**, `rate card` **2,013**/**0**,
`traffic billing` 136/**0**, `advertising sales management` 51/**0**.

---

## Energy, carbon & environmental-footprint foundations — added 2026-11-26 (pass 26)

All rows verified 2026-11-26: **21 slugs probed by `git ls-remote`, 21/21 resolve, 0 absent.** Stars,
forks and last-push via `search/repositories`; every `NOASSERTION` resolved by reading the licence file
and counting its bytes.

**The shape of this layer, stated before the table.** This plane inverts the usual finding of this KB.
Here the *substrate is healthy, institutional and largely permissive* — the Green Software Foundation,
the Green Web Foundation, Hubblo, Boavizta, PowerAPI and Electricity Maps between them ship a complete
measurement toolchain, much of it pushed this week. What is missing is not infrastructure. It is
**everything media-specific above it**: one 3-star plugin, and nothing else.

### Measurement and metrology

| Repo | Stars | Forks | Licence | Last push | Role |
|---|---|---|---|---|---|
| [hubblo-org/scaphandre](https://github.com/hubblo-org/scaphandre) | 2,018★ | 133f | **Apache-2.0** | 2026-07-19 | Host-level power metrology via RAPL. The most-starred permissive measurement tool here; 4 months quiet |
| [mlco2/codecarbon](https://github.com/mlco2/codecarbon) | 1,955★ | 360f | **MIT** | 2026-11-22 | Per-job compute emissions. The standard way to attach a number to a GenAI render, fine-tune or inference batch |
| [sustainable-computing-io/kepler](https://github.com/sustainable-computing-io/kepler) | 1,605★ | 294f | **Apache-2.0** | **2026-11-26** | Per-pod energy attribution in Kubernetes via eBPF. The right instrument for a containerised transcode or render farm |
| [powerapi-ng/powerapi](https://github.com/powerapi-ng/powerapi) | 255★ | 45f | **BSD-3-Clause** | 2026-11-24 | Software power-meter toolkit for building your own middleware. The most permissive band in the plane |
| [green-coding-solutions/green-metrics-tool](https://github.com/green-coding-solutions/green-metrics-tool) | 260★ | 50f | **AGPL-3.0 source + bundled ODbL data + Apache (co2.js)** — 35,429 B "License Index" read | **2026-11-26** | Repeatable measurement lab for a whole pipeline. Three licences in one dependency; see the licence note below |

### Emission factors, grid intensity and embodied carbon

| Repo | Stars | Forks | Licence | Last push | Role |
|---|---|---|---|---|---|
| [electricitymaps/electricitymaps-contrib](https://github.com/electricitymaps/electricitymaps-contrib) | 4,057★ | 1,073f | **AGPL-3.0** | 2026-11-26 | The grid-intensity source the rest of the ecosystem re-publishes. Consume the data under its own terms; **do not vendor the application** |
| [thegreenwebfoundation/co2.js](https://github.com/thegreenwebfoundation/co2.js) | 499★ | 73f | **Apache-2.0 code + CC-BY-SA + ODbL data** — 12,678 B read | 2026-11-17 | Bytes → gCO2e via the Sustainable Web Design and 1-byte models. **The single most useful repo in this plane for a streaming business, and the one with the sharpest licence gate** |
| [thegreenwebfoundation/grid-intensity-go](https://github.com/thegreenwebfoundation/grid-intensity-go) | 84★ | 10f | **Apache-2.0** | 2026-05-11 | Grid intensity as a Go library and Prometheus exporter — the shape you want on a CDN or edge node |
| [Boavizta/boaviztapi](https://github.com/Boavizta/boaviztapi) | 102★ | 45f | **AGPL-3.0** | 2026-11-24 | **Embodied** (manufacturing) carbon of hardware — devices, servers, the half that operational tools silently omit. Copyleft |
| [agirgol/carbon-accounting-dotnet](https://github.com/agirgol/carbon-accounting-dotnet) | 0★ | — | **MIT** | 2026-08-17 | GHG Protocol + **ISO 14064-1** Scope 1/2/3 in .NET with a versioned, source-cited factor catalogue. Zero adoption, correct standards |

### Modelling, reporting and reduction

| Repo | Stars | Forks | Licence | Last push | Role |
|---|---|---|---|---|---|
| [cloud-carbon-footprint/cloud-carbon-footprint](https://github.com/cloud-carbon-footprint/cloud-carbon-footprint) | 1,054★ | 310f | **Apache-2.0** | 2026-04-23 | Cloud billing exports → emissions estimates across AWS/Azure/GCP. 7 months quiet; still the only credible open multi-cloud estimator |
| [Green-Software-Foundation/carbon-aware-sdk](https://github.com/Green-Software-Foundation/carbon-aware-sdk) | 600★ | 113f | **MIT** | 2026-11-04 | Move a workload to a cleaner time or region. The *reduce* layer, and the only part of it with real adoption |
| [Green-Software-Foundation/if](https://github.com/Green-Software-Foundation/if) | 184★ | 54f | **MIT** | 2026-10-24 | Impact Framework — a manifest describing a pipeline becomes a calculable footprint. The natural place to encode a media delivery chain |
| [GreenScheduler/cats](https://github.com/GreenScheduler/cats) | 82★ | 23f | **MIT** (1,076 B) | **2026-11-26** | Climate-Aware Task Scheduler: a CLI that defers a job to a low-carbon window. Pushed today |
| [Green-Software-Foundation/sci-otel](https://github.com/Green-Software-Foundation/sci-otel) | 10★ | — | **Apache-2.0** | 2026-11-18 | SCI as an OpenTelemetry vocabulary — how a carbon figure becomes an ordinary metric beside bitrate and rebuffer ratio |
| [ABC-TransitionBasCarbone/bilan-carbone](https://github.com/ABC-TransitionBasCarbone/bilan-carbone) | 5★ | — | **MIT** (1,081 B, `master`) | **2026-11-26** | The **Association Bilan Carbone** — owner of France's official corporate carbon methodology — shipping MIT code, pushed today, at 5 stars |
| [aimabel-ai/esrs-xbrl-parser](https://github.com/aimabel-ai/esrs-xbrl-parser) | 12★ | — | **ISC** (746 B) | 2024-12-17 | Parses **ESRS** XBRL taxonomies. A permissive licence band not previously recorded in this KB; dormant ~23 months |

### The media-native layer, in full

| Repo | Stars | Licence | Last push | Note |
|---|---|---|---|---|
| [BreakTools/deadline-energy-cost-calculator](https://github.com/BreakTools/deadline-energy-cost-calculator) | **3★** | **MIT** (1,067 B) | 2025-09-17 | An AWS/Thinkbox **Deadline** event plugin that computes the energy and cost of a render job. **This is the entire media-native intersection of this plane.** Deadline is standard across VFX and animation facilities, so the installed base under this 3-star plugin is large and nobody has built on it |

That table is not an excerpt. **One repo, three stars, fifteen months since its last push** — against a
substrate of six repos with over a thousand stars each.

### ⚠️ Licence notes that no SBOM scan will produce

1. **co2.js is a four-licence compilation.** `LICENSE` is **12,678 B** where canonical Apache-2.0 is
   11,357 B; the surplus is data licensing. Code **Apache-2.0**; Ember average grid-intensity data
   **CC-BY-SA**; Green Web Foundation marginal-intensity data **CC-BY-SA** (derived from the UNFCCC
   **IFI TWG** harmonised dataset); Electricity Maps annual grid data **ODbL**, which obliges you to
   **attribute**, to **share-alike derivative databases**, and to **"provide unrestricted versions if
   using DRM."** The GitHub API reports `NOASSERTION`; a repo-level reading reports "Apache-2.0"; both
   miss the obligation. **In a plane where `DRM` appears 53 times in this KB, that clause is the gate**
   — Pattern 26.1 draws it explicitly.
2. **green-metrics-tool is a three-licence compilation**: AGPL-3.0 source (licence text at line 652 of
   the index), bundled co2.js Apache terms (line 7), bundled Electricity Maps **ODbL** (line 673).
3. **`Green-Software-Foundation/sci` is not open source.** `LICENCE.md` — **British spelling**, which is
   why a `LICENSE*`-only probe reports "no licence" — is a 2,347 B Joint Development Foundation "AS IS"
   materials grant with **W3C patent mode**: warranty disclaimers and a patent pledge, and **no
   copyright grant to reproduce or modify**. The specification is **ISO/IEC 21031**; implement the
   standard, cite it, and do not vendor the repo. This is the second body in this KB to publish a
   standard without an OSI licence (after `w3c-cg/tdm-reservation-protocol`, pass 5) and the **third
   confirmation that `LICENCE` with a C belongs in every licence probe.**
4. **Copyleft is concentrated in the data layer**: Electricity Maps (AGPL-3.0), Boavizta (AGPL-3.0),
   green-metrics-tool (AGPL-3.0). The *code* layer is permissive and the *facts* layer is share-alike —
   the exact inverse of the pass-1 finding for M&E platforms, and it means the licence risk here enters
   through a dataset, not through a framework.

### Measured gaps — searched and absent, stated so silence is not read as coverage

| Query (GitHub `search/repositories`, 2026-11-26) | Total | Relevant | Reading |
|---|---|---|---|
| `film production carbon footprint` | **0** | 0 | The task three UK broadcasters require by contract has **no open implementation anywhere** |
| `albert carbon calculator` | **0** | 0 | No open client, exporter or schema for the mandated toolkit |
| `sustainable film production` | 3 | **0** | Two production-company portfolio sites and a 2019 coursework report |
| `video encoding energy efficiency` | 1 | **0** | A 2022 bibliography repo. **The single largest energy line in streaming has no open measurement tool** |
| `broadcast energy consumption` | 1 | **0** | An Arduino mains monitor, last push 2014-11-25 |
| `render farm energy` | 2 | **1** | The one real hit is the 3-star MIT Deadline plugin above |
| `emission factor database api` | 1 | **0** | An API-profile stub. Factor data arrives bundled in libraries or from commercial APIs, not from an open database repo |
| **False abundance** — `huella de carbono` / `pegada de carbono` | **467 / 177** | **0** | Every first-page result is a student or personal project at 0–4 stars, mostly unlicensed, **none audiovisual**. Pass 8's rule earns its keep: read the results, not the total |

## The production-finance & cost-accounting substrate — measured 2026-11-26 (pass 27)

**The finding that shapes this section, and it inverts the plane's apparent emptiness.** Pass 17 wrote
*"Tier 4 — the money: effectively nothing"* after searching for **film** budgeting and accounting
repos. That conclusion is correct and incomplete. Searched as a *media* problem the plane is a desert;
searched as a **computation** problem it has some of the most mature, most permissive code in this
entire knowledge base. Money is the one plane where the generic layer is **stronger** than the
vertical layer, not weaker — and the whole engineering opportunity is the thin mapping between them.

### Tier 1 — rules-as-code: the correct substrate for an incentive engine, and nobody has pointed it at film

An incentive is a **statute**, not a spreadsheet: eligibility tests, qualifying-spend definitions,
caps, uplifts, carve-outs and commencement dates. There is a mature open-source discipline for
exactly this, and it has never been applied to screen incentives.

| Repo | Licence | Stars / Forks | Last push | Why it belongs under this plane |
|---|---|---|---|---|
| [CatalaLang/catala](https://github.com/CatalaLang/catala) | **Apache-2.0** | 2,456★ / 126f | 2026-11-26 | A DSL for **deriving correct-by-construction implementations from legislative text**, literate-programming style: the statute and the code sit side by side. Published work expresses sections of the **US Internal Revenue Code** and the whole of French family benefits. Pushed on measurement day. **The single best-licensed, best-maintained foundation in the plane** |
| [apache/incubator-kie](https://github.com/apache/incubator-kie) | **Apache-2.0** | 6,344★ / 2,608f | 2026-11-26 | The **Drools** rule engine and DMN runtime, now consolidated into the Apache KIE monorepo. The pragmatic choice when the client's finance team needs decision tables they can read and edit themselves |
| [CacheControl/json-rules-engine](https://github.com/CacheControl/json-rules-engine) | **ISC** | 3,151★ / 511f | 2026-02-16 | Rules as JSON. The lightest way to ship a per-jurisdiction eligibility check inside an existing app; dormant nine months but complete and stable |
| [gorules/zen](https://github.com/gorules/zen) | **MIT** | 2,154★ / 237f | 2026-11-26 | Rust business-rules engine with JDM decision models and bindings for Node/Python/Go. Permissive **and** fast enough to evaluate a rule set per budget line |
| [openfisca/openfisca-core](https://github.com/openfisca/openfisca-core) | **AGPL-3.0** | 252★ / 100f | 2026-11-24 | The reference rules-as-code engine for tax and benefit legislation; a recognised **Digital Public Good**. ⚠️ **AGPL** — fine for an internal or client-owned deployment, a licensing problem for a hosted multi-tenant product |
| [PolicyEngine/policyengine-us](https://github.com/PolicyEngine/policyengine-us) | **AGPL-3.0** | 178★ / 224f | 2026-11-26 | The largest live OpenFisca-family model: US federal **and state** tax law as executable code. **The closest existing prior art to a 39-state incentive engine** — the per-jurisdiction modelling pattern is already solved here, for a different statute |
| [PolicyEngine/policyengine-core](https://github.com/PolicyEngine/policyengine-core) | **AGPL-3.0** | 22★ / 31f | 2026-11-25 | The engine underneath it. **Forks (31) exceed stars (22)** — the signature of a component used as a base rather than admired |
| [jhpyle/docassemble](https://github.com/jhpyle/docassemble) | **MIT** | 1,019★ / 324f | 2026-11-25 | Guided-interview and document-assembly platform used widely in legal aid. The permissive way to turn an incentive application into an interview that emits the filing pack — the **front door** to Pattern 27.1 |

### Tier 2 — double-entry ledgers: seven real engines, and the licence spread is the whole decision

Production cost accounting is double-entry bookkeeping with an industry chart of accounts and a
different report on top. The engines are excellent; **what does not exist is the chart of accounts.**

| Repo | Licence — read where the API was unclear | Stars / Forks | Last push | Shape |
|---|---|---|---|---|
| [tigerbeetle/tigerbeetle](https://github.com/tigerbeetle/tigerbeetle) | **Apache-2.0** | 17,467★ / 945f | 2026-11-25 | A purpose-built **financial accounting database**: double-entry primitives, strict serialisability, very high throughput. Permissive and the most serious engineering in the tier. Right choice when postings are millions/day (residuals, royalties, per-stream splits) |
| [beancount/beancount](https://github.com/beancount/beancount) | GPL-2.0 | 6,210★ / 491f | 2026-08-23 | Plain-text double-entry language. The ledger is a **file in git** — which makes a production's books diffable, reviewable and auditable by the same tooling as its code. The deepest ecosystem in plain-text accounting |
| [ledger/ledger](https://github.com/ledger/ledger) | **BSD-3-Clause** — API said `NOASSERTION`; `LICENSE.md` (1,492 B) read in full: BSD-3-Clause, © 2003-2025 John Wiegley | 6,081★ / 554f | 2026-11-24 | The original CLI double-entry tool. **The only permissively licensed plain-text ledger of the three**, and the API hides that |
| [hledgerorg/hledger](https://github.com/hledgerorg/hledger) | GPL-3.0 | 4,837★ / 427f | 2026-11-26 | Haskell reimplementation, strong reporting and a stable file format. ⚠️ **Slug correction below** |
| [formancehq/ledger](https://github.com/formancehq/ledger) | **MIT** | 1,489★ / 230f | 2026-11-26 | A **programmable** financial ledger with a transaction DSL for modelling money movement between many parties. The closest thing in open source to a recoupment-waterfall engine — see Pattern 27.3 |
| [beancount/fava](https://github.com/beancount/fava) | **MIT** | 2,615★ / 429f | 2026-11-23 | Web UI and reporting over a Beancount ledger. **Permissive even though the engine it reads is GPL** — the usual split in this tier |
| [flash-oss/medici](https://github.com/flash-oss/medici) | **MIT** | 364★ / 101f | 2026-07-29 | Embeddable double-entry for Node/MongoDB. The library to reach for when the ledger lives *inside* a product rather than beside it |

### Tier 3 — allocation and optimisation: where the soft-money question is actually answered

| Repo | Licence | Stars / Forks | Last push | Use in this plane |
|---|---|---|---|---|
| [TimefoldAI/timefold-solver](https://github.com/TimefoldAI/timefold-solver) | **Apache-2.0** — `LICENSE.txt`, 11,358 B, read | 1,882★ / 245f | 2026-11-24 | Constraint solver, the maintained successor to OptaPlanner. Jurisdiction/spend allocation under caps, minimum-spend floors and local-hire quotas is a textbook constraint problem: **Pattern 27.4** |
| [apache/incubator-kie-optaplanner](https://github.com/apache/incubator-kie-optaplanner) | **Apache-2.0** | 3,512★ / 972f | 2026-07-14 | The Apache-held predecessor. Still the better citation when a client's stack is already Java/KIE; four months since last push |

### 🔧 Two oracle corrections this pass, both fresh instances of pass 17's rule

Pass 17's rule — *`ls-remote` says EXISTS **+** `search/repositories` with `repo:<slug>` returns no
item ⇒ the slug is a rename/transfer redirect that `ls-remote` followed silently* — fired twice here,
and in one case the canonical target is a **different organisation**:

| Slug as published by package registries, docs and blogs | Canonical repository | What the stale slug hides |
|---|---|---|
| `simonmichael/hledger` | [hledgerorg/hledger](https://github.com/hledgerorg/hledger) | Owner changes from a person to an org. 4,837★ GPL-3.0 — the stale slug reports **nothing at all** through the search API |
| `kiegroup/drools` and `apache/incubator-kie-drools` | [apache/incubator-kie](https://github.com/apache/incubator-kie) | **Both** legacy slugs still answer `ls-remote`. Drools was consolidated into the Apache KIE monorepo; a KB that recorded either would publish a slug with no searchable metadata and an outdated governance story |

**A 200 is never by itself proof a slug is canonical.** Two oracles; the disagreement is the signal.

### ⚠️ Licence trap of this pass, and it is the highest-starred trap found in twenty-seven passes

[akaunting/akaunting](https://github.com/akaunting/akaunting) — **10,349★**, the second-most-starred
result for open-source accounting — **is not open source.** `LICENSE.txt` (3,654 B, read in full) is
the **Business Source License**: *"License text copyright (c) 2020 MariaDB Corporation Ab … Licensor:
Akaunting, Inc. Licensed Work: Akaunting"*, with an Additional Use Grant limiting production use.
GitHub's API reports `NOASSERTION`. At ten thousand stars it will surface in any search a client or a
junior engineer runs, and a BSL dependency in a delivered platform is a commercial problem discovered
at the worst possible moment. **Do not build on it.** `firefly-iii` (AGPL) and `LedgerSMB` (GPL-2.0)
are genuinely open; `ledger`, `tigerbeetle`, `formance`, `medici` and `fava` are genuinely permissive.

### Measured gaps — searched and absent, written down so silence is not read as coverage

| Query (GitHub `search/repositories`, 2026-11-26) | Total | Relevant | Reading |
|---|---|---|---|
| `completion bond film` | **0** | 0 | The instrument that unlocks most independent film financing has **no open-source presence whatsoever** |
| `production incentive eligibility` | **0** | 0 | The highest-value agent in the plane has no prior art in any licence |
| `ERPNext media production` | **0** | 0 | **No media vertical exists for the world's most-starred open ERP** (41,661★). The gap is the chart of accounts, and it is unclaimed |
| `film tax credit` | **7** | 4 | Seven repos on all of GitHub; best is 1★; all four relevant are proprietary or unlicensed |
| `recoupment waterfall` | **2** | 1 | The one hit is an unlicensed 2023 Solidity contract for crypto splits |
| `film finance` | 51 | ~3 | All at 0-1★; the best-starred result (78★) is a 2022 LGPL **DCP** tool that merely matched on "film" |
| `cost report film production` | 5 | **0** | Three market-research spam repos, one 2023 C++ student project (GPL-3.0, 0★), one API stub |
| `errors and omissions insurance` | 6 | **0** | Five `api-evangelist` API-profile stubs, one 2018 university assignment |
| `film production ERP` | 5 | **0** | All five at **0★ and with no licence file** — the signature of freshly generated single-author projects |
| `royalty accounting` | 47 | **0** | Confirms pass 5's identical finding in the rights plane, now in the cost plane too |
| **False abundance** — `production accounting` | **1,946** | **0** | Every first-page result is unrelated: a 2,909★ MIT coding-assistant repo, CS coursework, an Instagram MCP server, an AWS break-glass role. **"Production" means *software* production to GitHub** |
| **False abundance** — `residuals` | **11,617** | **0** | Entirely **ResNet and super-resolution machine learning**. The single worst false friend recorded in this KB — worse than pass 5's `isan` (1,942/0) — and it sits on the exact term a media-finance client uses for performer payments |

**The two false-abundance rows are the method lesson of this pass.** `production accounting` and
`residuals` return **13,563 repositories between them and zero relevant results.** A pass that read
totals instead of results would have reported the plane as well served and written filler rows from
coursework. Pass 8's rule — *read the results, not the total* — and pass 5's corollary that shortening
a query can manufacture false abundance both earn their keep here, on terms a domain expert would
consider unambiguous.

## The age-rating, classification & child-audience plane — foundations, measured 2026-11-26 (pass 28)

**The finding of this pass, stated first: the only open, machine-readable, multi-territory age-rating
vocabulary in existence ships in the Linux desktop app-store stack, not in the media industry.** The
media industry's own dataset is broader, is published, and carries no licence at all.

### The four-step gradient — the sharpest statement this KB's structural law has had

Earlier passes found two- and three-step gradients (pass 5: declare / honour / liquidate). This plane
has four steps, and each one degrades predictably:

| Step | Problem type | State of the open estate |
|---|---|---|
| **1. DECLARE** the criteria | Format | **Solved and permissive** — `hughsie/oars` + `ximion/appstream`, LGPL-2.1, pushed within the last five weeks |
| **2. MAP** criteria → territory ladder | Table lookup | **Open and maintained, but sourced from Wikipedia** — 16 systems in AppStream (see the caveat below) |
| **3. ENFORCE** in the player | Engineering | **Open, huge, and structurally unsound** — Jellyfin at 59,787★ resolves ratings by bare string and falls back to the US ladder |
| **4. ALLOCATE** the certificate | Authority | **Closed. Zero.** `IARC age rating` → 2 repos, both 0★. No open client for ESRB, PEGI, USK, GRAC, CERO or ClassInd submission |

The pattern is the one this KB has now confirmed eight times: **the closer a layer sits to an act of
authority, the emptier the open estate gets.** Writing the criteria down is free; being the party
whose signature the rating carries is not.

### Step 1–2 — the vocabulary and the mapping (the find of the pass)

| Repo | Licence | Stars / forks | Pushed | What it actually contains |
|---|---|---|---|---|
| [hughsie/oars](https://github.com/hughsie/oars) | **LGPL-2.1** (`LICENSE`, 26,526 B) | 28★ / 12f | 2026-10-20 | **The Open Age Ratings Service.** The OARS vocabulary itself — the per-criterion scheme (violence, sex, drugs, language, gambling, social features) that an author self-declares. 28 stars for the only open age-rating vocabulary on earth. |
| [ximion/appstream](https://github.com/ximion/appstream) | **LGPL-2.1** (`COPYING`, 26,419 B) | 283★ / 147f | 2026-11-24 | **The mapping layer, and the reason this plane is tractable at all.** `as-content-rating.c` (67,649 B) converts an OARS declaration into a **territory-specific ladder for 16 national systems**, and `as_content_rating_system_from_locale()` picks the system from the locale. Pushed two days before this pass. |

**The 16 systems AppStream maps, with the ladders verified by reading the source table:**

| System | Territory | Ladder exactly as the source table implements it |
|---|---|---|
| INCAA | Argentina | `ATP, +13, +18` → ages `0, 13, 18` |
| DJCTQ | Brazil | `L, 10, 12, 14, 16, 18` → ages `0, 10, 12, 14, 16, 18` |
| ACB | Australia | `PG, MA15+, R18+` → ages `0, 15, 18` |
| GSRR | Taiwan | `普通, 保護, 輔12, 輔15, 限制` → `0, 6, 12, 15, 18` |
| PEGI | Europe (not DE/FI) | `3, 7, 12, 16, 18` |
| KAVI | Finland | `3+, 7+, 12+, 16+, 18+` |
| USK | Germany | `0, 6, 12, 16, 18` |
| ESRA | Iran | `+3, +7, +12, +15, +18` |
| CERO | Japan | `A, B, C, D, Z` |
| OFLCNZ | New Zealand | `G, R13, R15, R16, R18` |
| Russia | Russia | `0+, 6+, 12+, 16+, 18+` |
| MDA | Singapore | `General, ADV, M18` |
| GRAC | South Korea | `ALL, 12, 15, 18` |
| ESRB | United States | `Early Childhood, Everyone, Everyone 10+, Teen, Mature, Adults Only` — the source notes these are *"just the locale-independent parts"* and that ESRB needs further locale-specific handling |
| IARC | **fallback** | `3+, 7+, 12+, 16+, 18+` — returned for any locale that cannot be parsed |

**Why this matters to Globant specifically: the mapping covers all four regions.** INCAA and DJCTQ
are LATAM; PEGI, USK, KAVI and Russia are EMEA; ACB, CERO, GRAC, GSRR and MDA are APAC; ESRB is
North America. A rating component built on OARS + AppStream is **regionally portable by
construction** — which is exactly what passes 24 and 27 identified as the scarce property in a
multi-market engagement.

#### ⚠️ The mapping is a *projection*, not a translation — measured against the industry dataset

This is the caveat that matters most, and it is measurable because both open sources were read side
by side. **AppStream emits only the rungs an OARS declaration can reach, not the rungs a board can
issue** — and the rungs it drops are disproportionately the ones with legal consequence.

| Territory | AppStream emits | The board's actual ladder (from `MovieLabs/cmr-ratings`) | What is unreachable |
|---|---|---|---|
| **Argentina** | 3 rungs — `ATP, +13, +18` | **5 rungs** — `Todo público, mayores de 13, mayores de 16, mayores de 18, condicionada` | `mayores de 16` and **`condicionada`** (conditional exhibition) |
| **Australia** | 3 rungs — `PG, MA15+, R18+` | **8 rungs** — `G, PG, M, MA 15+, R 18+, CTC, X 18+, RC` | `G`, `M`, `CTC`, `X 18+` and **`RC` (Refused Classification)** |

**`Refused Classification` and `condicionada` are the two outcomes a distribution system absolutely
must act on** — one forbids distribution outright, the other constrains it — and neither is
expressible in the open mapping. **Never present an OARS-derived rating to a client as a board
rating.** It is a self-declaration projected onto a board's scale, and the projection is lossy at
exactly the rungs that carry consequence.

#### Three further caveats, in descending order of seriousness

1. **AppStream's own source comment names its authority — twice: `/* data obtained from
   https://en.wikipedia.org/wiki/Video_game_rating_system */`** appears at both line 298 and line 693
   of `as-content-rating.c`, covering the ladder table *and* the locale→system mapping. The only open
   multi-territory age-rating mapping in existence is sourced from Wikipedia. It is well-maintained
   and actively pushed — but **it is not a primary source, and a client who must publish "the
   methodology, criteria and sources" under the proposed EU KIDS Act cannot cite it as the source.**
   Use the code; re-derive each ladder from the board's own publication before shipping.
   *(Verification note: the quoted comment was read directly from the source file. The Wikipedia URL
   itself is **not reachable from this session**, so the article's current content is unverified —
   which is immaterial to the finding, since the finding is what the code cites, not what the article
   says.)*
2. **It is a *games and apps* vocabulary, and the territory data proves the divergence.** The
   industry dataset carries **three separate German systems** — `DE_USK` (games), `DE_FSK` (film,
   6 rungs) and `DE_FSF` (broadcast) — and for the UK it carries `GB_BBFC` (7 rungs) where AppStream
   maps `GB → PEGI`. **One country is not one ladder; it is one ladder per medium.** A film catalogue
   rated through the games mapping is wrong in Germany and wrong in the UK.
3. **The unparseable-locale default is IARC**, a membership body with no open client. A silent
   default to a closed system is the kind of thing that ships to production unnoticed.

### Step 3 — enforcement: the biggest repos in this plane, and the defect they share

| Repo | Licence | Stars / forks | Pushed | Finding |
|---|---|---|---|---|
| [jellyfin/jellyfin](https://github.com/jellyfin/jellyfin) | **GPL-2.0** (`LICENSE`, 18,014 B) | 59,787★ / 5,879f | 2026-11-26 | **Ships 45 per-territory rating files** in `Emby.Server.Implementations/Localization/Ratings/` (44 country codes plus `0-prefer.json`) — a wider territory set than AppStream's 16. Enumerated by shallow sparse clone, not inferred. **But see the defect below.** |
| [seerr-team/seerr](https://github.com/seerr-team/seerr) | **MIT** (`LICENSE`, 1,060 B) | 13,359★ / 1,169f | 2026-11-26 | The live request/discovery manager for Jellyfin, Plex and Emby. Carries per-user maximum movie and TV rating ceilings with an unrated-titles toggle. **MIT and pushed the day of this pass — the best-licensed enforcement surface in the plane.** |
| [sct/overseerr](https://github.com/sct/overseerr) | **MIT** | 4,952★ / 557f | 2026-02-15 | **ARCHIVED.** The predecessor Seerr forked from. Its long-running rating-restriction feature request is the origin of the Seerr implementation. Do not start here; it is read-only history. |
| [xbmc/xbmc](https://github.com/xbmc/xbmc) (Kodi) | **NOASSERTION** (GPL-2.0 in practice) | 21,551★ / 6,692f | 2026-11-26 | The other large open player. **The GitHub API reports NOASSERTION** — resolve the licence from the tree, not the badge. Pass 8's native-linking rule applies: Kodi links a large set of third-party libraries. |
| [varthe/Redirecterr](https://github.com/varthe/Redirecterr) | **NONE** | 146★ / 9f | 2026-10-14 | Routes media requests by requester, keyword **and age rating**. **No licence file at 8 probed names across `master` and `main`, while `README.md` returns 200** — so the names are right and the grant is genuinely absent. 146 stars of code nobody may legally redistribute. **Do not ship it.** |

#### The defect, quoted from the source, and it is the most citable engineering finding of this pass

Jellyfin resolves a rating string against the viewer's country, then:

```
// If we don't find anything, check all ratings systems, starting with US
if (_allParentalRatings.TryGetValue("us", out var usRatings) && usRatings.TryGetValue(rating, out var usValue))
    return usValue;

foreach (var dictionary in _allParentalRatings.Values)
    if (dictionary.TryGetValue(rating, out var value))
        return value;
```
*(`Emby.Server.Implementations/Localization/LocalizationManager.cs`, read 2026-11-26)*

**None of the 45 rating files carries a `system` field** — they are keyed by country code only, and
a rating is matched as a **bare string**. The consequence is concrete and testable: the token `16`
is a valid rung on the PEGI, USK, DJCTQ, GRAC and Russian ladders, and it does **not** mean the same
thing on all of them. A title tagged `16` with no territory qualifier resolves against whichever
dictionary matches first — **US first, then an unordered walk of every other country.** A German
`16` can be scored by the US table, and a parental control can silently pass a title it should block.

Two further details found in the same tree, both worth knowing before you build on it:

- **`gb.json` and `uk.json` both exist**, so the United Kingdom is represented twice under two keys.
- **`br.json` contains a `9` band**, which is not on the current ClassInd ladder
  (`L / 10 / 12 / 14 / 16 / 18`). It is not a bug: the MovieLabs dataset's Brazilian entry carries
  entries flagged `Deprecated=true`, one of which has `MinRecAge 9`. **The open implementations have
  inherited deprecated rungs without inheriting the deprecation flag** — a general hazard when a
  ladder is modelled as a flat string list.

**The reusable rule for all twelve industries:** a rating, a code or a classification is never a
string. It is a **pair** — `(system, value)` — and any schema that stores only the value will resolve
correctly in testing and incorrectly in a second territory.

### Step 4 — the authoritative dataset: 110 systems, 77 territories, and no licence

Pass 16 added `MovieLabs/cmr-ratings` as a one-line row with a licence warning. **Nobody had opened
it.** It was cloned and measured for this pass:

| Measurement | Value |
|---|---|
| Rating systems (`xml/*.xml`) | **110** |
| Distinct territories (ISO prefixes) | **77** — `AE AR AT AU BE BG BH BN BO BR BY CA CH CL CO CR CZ DE DK EC EE EG ES FI FR GB GR HK HN HR HU ID IE IL IN IS IT JO JP KE KH KR KW KZ LB LT LU LV MT MV MX MY NG NL NO NZ PE PH PL PT RO RU SA SE SG SK SV TH TR TW UA US UY VE VN ZA ZZ` |
| Total files | **506** (plus an `imageCache/` of board logos and a `toBeReviewed/` of 12 more systems) |
| Newest `LastChecked` anywhere in the dataset | **2023-07-11** |
| Systems with **no** `LastChecked` at all | **25 of 110** |
| Systems whose `lastValidated` is **2013** | **54** |
| Licence file | **NONE** — 8 names (`LICENSE`, `LICENSE.md`, `LICENSE.txt`, `license.txt`, `LICENCE`, `COPYING`, `COPYING.md`, `COPYING.txt`) × 2 branches. `README.md` also 404s: **the repo has no README either** |
| Stars / forks | **1★ / 0f** |

The data itself is good. Brazil's entry (`xml/BR_DJCTQ_Ratings.xml`, version 6) models
`Region`, `System`, `Usage` (Film/Game/TV × Home/Theater/Broadcast/App), per-rung `MinAge`,
`MinRecAge`, `MinAgeSupervised`, `Deprecated`, board logos, and a `Notes` block that links the
**gov.br ClassInd 2021 practical guide** and records that *"Only 10 reasons are currently accepted in
Brazil. All other reasons are considered invalid."* This is better modelling than anything else in
the plane — `LastChecked 2023-06-01`, `lastValidated 2013-10-12`.

**Three conclusions, and they are the ones to take to a client:**

1. **It is the broadest ratings dataset in the world and it cannot be used.** 110 systems against
   AppStream's 16 and Jellyfin's 44 — and with no licence grant, default copyright applies: all
   rights reserved. **Do not vendor it into a client deliverable.** Use it to know what to go and
   verify from each board directly.
2. **It is stale exactly where 2026 moved.** Nothing has been re-checked since **2023-07-11**. Since
   then: Brazil's Portaria 1.048/2025 took effect (with articles 48–57 landing **17 March 2026**),
   Korea's GCRB gained 19+ rating authority in **January 2026**, Australia's under-16 regime went
   live in **December 2025**, and the EU proposed the KIDS Act in **September 2026**. The dataset
   predates all four.
3. **Its own ChangeLog is admirably honest, and quoting it is the fastest way to end an argument
   about whether to trust it.** It records systems taken *"from paramount database"* that *"could not
   be confirmed"*, ratings that *"differ slightly from both news articles"*, and boards that have
   *"internal documents, but [do] not have a public present or post papers."* A vendor would never
   write that down. Treat `toBeReviewed/` as what it says it is.

### Step 1 alternative — a normative bet worth watching, not adopting

| Repo | Licence | Stars / forks | Pushed | Read |
|---|---|---|---|---|
| [R8rly/show](https://github.com/R8rly/show) | **CC-BY-SA-4.0** (20,139 B) | 22★ / 6f | 2026-11-05 | "The SHOW Standard" — an open content-rating vocabulary for books, audiobooks, film and stories (spice level, heat, content warnings). **Same shape as ISCC in pass 5: a normative bet, not an installed base.** And note the licence class: **CC-BY-SA on a *vocabulary* means share-alike reaches the derived metadata**, which is a real constraint on a client catalogue. Flagged, not recommended. |

### Supporting infrastructure already in this KB, now placed in this plane

- **[XMLTV/xmltv](https://github.com/XMLTV/xmltv)** — GPL-2.0 (`COPYING`, 18,092 B), 425★ / 108f,
  2026-10-13. Already in the KB from the EPG work. Relevant here because the XMLTV DTD carries a
  `<rating system="...">` element — **it is the one widely-deployed interchange format in this plane
  that models the `(system, value)` pair correctly.** Use its shape as the schema reference.
- **[endlessm/malcontent](https://github.com/endlessm/malcontent)** — LGPL-2.1, 5★ / 0f,
  **2022-03-21 (stale)**. A parental-controls library that filters apps by OARS rating.
  **Channel note: the canonical malcontent is hosted on GNOME's GitLab, not GitHub**, so a
  GitHub-only survey of this plane will conclude, wrongly, that enforcement-by-rating has no library.
  The GitHub copy is a four-year-old Endless fork. Do not judge the project by it.

### Verified ladder reference — six territories, read directly from the dataset 2026-11-26

Useful on day one of an engagement, and recorded here so the next pass does not have to re-read the
XML. Every row was extracted from `MovieLabs/cmr-ratings`; `lastChecked` is the dataset's own field,
and it is why each row needs re-verification against the board before it is shipped.

| Territory / system | Rungs | Ladder | Dataset `lastChecked` |
|---|---|---|---|
| **AU / NCS** | 8 | `General (G)`, `Parental Guidance (PG)`, `Mature (M)`, `Mature Accompanied (MA 15+)`, `Restricted (R 18+)`, `Check the Classification (CTC)`, `Restricted (X 18+)`, `Refused Classification (RC)` | 2023-05-31 |
| **GB / BBFC** | 7 | `Universal`, `Parental Guidance`, `12 and Older`, `Accompanied under 12`, `15 and Older`, `18 and Older`, `RESTRICTED 18 and Older` | 2023-07-10 |
| **DE / FSK** | 6 | `ab 0 freigegeben / ohne Altersbeschränkung`, `ab 6`, `ab 12`, `ab 16`, `ab 18 / Keine Jugendfreigabe`, `Keine Kennzeichnung` | 2023-05-31 |
| **JP / EIRIN** | 8 (4 pairs) | `General (G)`, `Parental guidance – 12 and Above (PG12)`, `15 and above only (R15+)`, `18 and above only (R18+)` | 2023-07-10 |
| **KR / KMRB** | 12 | `전체 관람가 (All)`, `12세 이상 관람가 (12)`, `15세 이상 관람가 (15)`, `19`, `관람등급`, `청소년 관람불가` | 2023-07-10 |
| **US / MPAA** | 8 | `General Audiences`, `Parental Guidance Suggested`, `Parents Strongly Cautioned`, `Restricted`, `No One 17 and Under Admitted`, plus `Mature Audiences` | **2013-09-28** |

**Two things to notice in that last column.** The US entry — the home market of most of this
industry's buyers — **has not been validated since 2013**. And the ladders are stored as
*label pairs* (long name plus short code), which is why the rung counts look inflated: `JP/EIRIN`'s
"8" is four ratings with two labels each. **Count ratings, not labels**, or a conformance test will
report twice the rungs that exist.

## The interactive, branching & playable-story plane — measured 2026-11-26 (pass 29)

78 repository slugs were probed this pass; **78/78 resolve** (`git ls-remote` on each, plus a licence
read for every row whose SPDX field came back `None` or `NOASSERTION`). This is the healthiest
substrate in the KB and also the one with the most licence surprises, so the tables below are ordered
by **what the licence lets Globant do**, not by stars.

### Narrative scripting & dialogue runtimes — permissive, active, and the strongest layer in this plane

| Repo | Licence | Stars | Last push | Why it matters |
|---|---|---|---|---|
| [inkle/ink](https://github.com/inkle/ink) | MIT | 5,067★ | 2026-11-16 | The industry-standard narrative scripting language (*80 Days*, *Heaven's Vault*). **Middleware, not an engine** — it slots into your runtime and leaves the UI to you, which is exactly what a client integration needs. |
| [y-lohse/inkjs](https://github.com/y-lohse/inkjs) | MIT | 673★ | 2026-11-20 | The JavaScript port. This is how an ink story reaches a browser, a CTV app or a web player without C#. |
| [inkle/inky](https://github.com/inkle/inky) | MIT (stated in README; **no LICENSE file at the repo root**) | 2,758★ | 2026-05-05 | The writer-facing editor. Hand this to the client's writers room; it is the reason ink gets adopted. |
| [inkle/ink-unity-integration](https://github.com/inkle/ink-unity-integration) | MIT — in **`LICENCE.md`**, British spelling, which is why GitHub reports `NOASSERTION` | 733★ | 2026-07-08 | Unity binding. See the method note below: the licence is real, the probe was wrong. |
| [paulloz/godot-ink](https://github.com/paulloz/godot-ink) | MIT | 793★ | 2026-07-04 | ink inside Godot. With Godot itself MIT, this is the only fully-MIT authoring-to-runtime path in the plane. |
| [YarnSpinnerTool/YarnSpinner](https://github.com/YarnSpinnerTool/YarnSpinner) | MIT | 2,883★ | 2026-11-26 | Screenplay-shaped dialogue language (*Night in the Woods*, *A Short Hike*). Engine-agnostic compiler + runtime; **pushed the day of this pass**. |
| [YarnSpinnerTool/YarnSpinner-Unity](https://github.com/YarnSpinnerTool/YarnSpinner-Unity) | MIT | 856★ | 2026-11-25 | The official Unity integration, equally alive. |
| [dialogic-godot/dialogic](https://github.com/dialogic-godot/dialogic) | MIT | 6,194★ | 2026-11-19 | Dialogue, characters and visual-novel flow as a Godot addon — the highest-starred *authoring* tool in the plane after the engines. |
| [nathanhoad/godot_dialogue_manager](https://github.com/nathanhoad/godot_dialogue_manager) | MIT | 4,005★ | 2026-11-25 | The leaner Godot alternative: nonlinear dialogue as plain text files, diffable in git. |
| [mhgolkar/Arrow](https://github.com/mhgolkar/Arrow) | MIT | 1,378★ | 2025-09-05 | Node-graph narrative design tool — the only open answer to Articy draft. **14 months without a push**: usable, not maintained. |
| [radiatoryang/merino](https://github.com/radiatoryang/merino) | MIT (confirmed in `LICENSE`, 1,307 B) | 298★ | **2021-12-21, archived** | In-editor Yarn authoring for Unity. Archived — listed so a later pass does not rediscover it as live. |

### The Twine family — the authoring tool actual writers already know, and a GPL seam

| Repo | Licence | Stars | Last push | Note |
|---|---|---|---|---|
| [klembot/twinejs](https://github.com/klembot/twinejs) | **GPL-3.0** | 2,964★ | 2026-10-07 | Twine itself. The most widely taught interactive-narrative tool in the world, and **copyleft** — fine as a tool you *use*, a licence problem if you embed or fork it into a client product. |
| [tmedwards/sugarcube-2](https://github.com/tmedwards/sugarcube-2) | BSD-2-Clause | 272★ | 2026-03-02 | The story format that actually ships Twine games. Permissive, unlike the editor above. |
| [tmedwards/tweego](https://github.com/tmedwards/tweego) | BSD-2-Clause | 169★ | 2024-06-15 | CLI compiler — the piece that lets Twine stories live in CI instead of a GUI. 17 months stale but a stable format. |
| [klembot/chapbook](https://github.com/klembot/chapbook) | MIT | 103★ | 2026-11-10 | The readable, MIT-licensed story format. The right default when the output must be embeddable. |
| [videlais/extwee](https://github.com/videlais/extwee) | MIT | 44★ | 2026-11-20 | Parsing/compilation toolchain for Twee. Small, alive, and the programmatic entry point for an agent. |
| [iftechfoundation/twine-specs](https://github.com/iftechfoundation/twine-specs) | **no licence statement found** | 104★ | 2024-07-04 | The Twee 3 / story-format specs. Documents, not code — demoted on sight, per this file's standing rule. |

### Visual-novel & interactive-fiction engines — where APAC's open source is strongest

| Repo | Licence | Stars | Last push | Note |
|---|---|---|---|---|
| [renpy/renpy](https://github.com/renpy/renpy) | **MIT for most of it** — stated in `sphinx/source/license.rst`; **no root LICENSE file**, portions under other licences | 7,065★ | 2026-11-26 | The Ren'Py visual-novel engine: two decades old, pushed the day of this pass, and the default for commercial VN production. |
| [OpenWebGAL/WebGAL](https://github.com/OpenWebGAL/WebGAL) | MPL-2.0 | 4,054★ | 2026-11-21 | Browser-native VN engine, CN-origin, bilingual docs. MPL-2.0 = file-level copyleft: you may embed it, you must publish changes to *its* files. |
| [VoidmatrixHeathcliff/VoidNovelEngine](https://github.com/VoidmatrixHeathcliff/VoidNovelEngine) | MIT | 1,715★ | 2026-11-26 | Modern MIT VN engine, also CN-origin, also pushed today. |
| [Monogatari/Monogatari](https://github.com/Monogatari/Monogatari) | MIT | 897★ | 2026-11-15 | Web VN engine in plain JS — the lightest path to a branching story inside an existing web product. |
| [ganelson/inform](https://github.com/ganelson/inform) | Artistic-2.0 | 1,671★ | 2026-06-24 | Inform 7, the literate IF compiler. Artistic-2.0 is permissive but unusual — flag it in legal review rather than assuming MIT. |
| [garglk/garglk](https://github.com/garglk/garglk) | **aggregate**: `License.txt` states the package combines components under several licences | 439★ | 2026-11-25 | The cross-platform IF interpreter. "Several components, several licences" is a per-component review, not a single answer. |
| [erkyrath/glkote](https://github.com/erkyrath/glkote) | MIT | 29★ | 2025-06-25 | The JS display layer for IF interfaces. Tiny, and the only permissive piece of the web-IF stack. |
| [le-doux/bitsy](https://github.com/le-doux/bitsy) | MIT | 1,065★ | **2026-07-22, archived** | The little engine that taught a generation to ship a tiny world. Archived — history, not a dependency. |
| [dfabulich/choicescript](https://github.com/dfabulich/choicescript) | ⛔ **ChoiceScript Licence (CSL) v1.0 — non-commercial use only** | 464★ | 2026-05-29 | The language behind Choice of Games. **Explicitly forbids commercial use.** It is the single clearest "do not ship" in this plane, and it is also the most likely to be suggested by a search. |
| [pistacchio/Dedalus](https://github.com/pistacchio/Dedalus) | **no licence detected** | 185★ | 2024-04-02 | JS/HTML CYOA system. No licence = all rights reserved. Listed so nobody re-finds it hopefully. |

### Interactive video — the thinnest layer, and the one the market retreated from

| Repo | Licence | Stars | Last push | Note |
|---|---|---|---|---|
| [Comedian1926/OpenFMV](https://github.com/Comedian1926/OpenFMV) | MIT | 241★ | 2026-06-26 | Local-first visual editor for interactive video and branching scenes. **Copyright line reads 2026** — this is a new project, and the best open starting point for branching video that exists. |
| [mohetios/BandersnatchInteractive](https://github.com/mohetios/BandersnatchInteractive) | MIT | 255★ | 2026-10-18 | An HTML5 interactive player modelled on the format Netflix retired. Useful as a reference implementation of the *mechanics*. |
| [bbc/storyplayer](https://github.com/bbc/storyplayer) | **GPL-3.0** | 19★ | 2026-11-03 | BBC R&D's object-based media player — the only broadcaster-grade interactive runtime that is open at all. 19 stars, GPL-3.0, still pushed this month. |
| [bbc/audio-orchestrator](https://github.com/bbc/audio-orchestrator) | **GPL-3.0** | 11★ | 2026-11-12 | BBC R&D production tool for orchestrated/companion-device audio. The closest thing to a second-screen toolchain in open source, and it is a prototype. |
| [hyperaudio/hyperaudio-lite](https://github.com/hyperaudio/hyperaudio-lite) | MIT | 183★ | 2026-10-30 | Interactive transcript player — the navigable-media primitive that *did* survive, because it serves accessibility and search as well as interactivity. |
| [NUKnightLab/StoryMapJS](https://github.com/NUKnightLab/StoryMapJS) | MPL-2.0 | 254★ | 2026-09-13 | Knight Lab's map-driven story tool. Still the default for a non-linear editorial story. |
| [mozilla/popcorn-js](https://github.com/mozilla/popcorn-js) | MIT | 2,126★ | **2017-09-21, archived** | The ancestor of all web interactive video, dead for nine years. Quoted here as **history**: this plane has buried a generation of tooling already, and a client deserves to know that before funding the next one. |
| [videojs/video.js](https://github.com/videojs/video.js) | **Apache-2.0** (read from `LICENSE`; GitHub reports `NOASSERTION`) | 40,260★ | 2026-11-26 | The player you will actually extend to get branching behaviour, because no standard provides it. |

### Runtimes that deliver a playable story — the CTV and web tier

| Repo | Licence | Stars | Last push | Note |
|---|---|---|---|---|
| [godotengine/godot](https://github.com/godotengine/godot) | MIT | 120,887★ | 2026-11-26 | The MIT engine. With dialogic/Dialogue Manager/godot-ink above it, the whole authoring-to-runtime chain is permissive. |
| [pixijs/pixijs](https://github.com/pixijs/pixijs) | MIT | 48,914★ | 2026-11-26 | 2D web renderer — the right substrate for a playable story inside a publisher's own page. |
| [phaserjs/phaser](https://github.com/phaserjs/phaser) | MIT | 40,791★ | 2026-08-21 | HTML5 game framework; the fastest route from a narrative script to something that runs on a phone browser. |
| [cocos/cocos-engine](https://github.com/cocos/cocos-engine) | **MIT** (read from `LICENSE.md`; GitHub reports `NOASSERTION`) | 9,949★ | 2026-11-25 | Strong in APAC and in mini-game channels, which is where interactive stories actually monetise there. |
| [defold/defold](https://github.com/defold/defold) | ⚠️ **Defold Licence v1.0** (bespoke, 9,976 B) — *not* an OSI licence | 6,491★ | 2026-11-26 | Free to use, and **not** Apache-2.0 as it is often listed. Legal review before it enters a client estimate. |
| [rdkcentral/Lightning](https://github.com/rdkcentral/Lightning) | Apache-2.0 | 204★ | 2026-10-12 | The WPE/RDK UI framework for TV apps. **This is how an interactive experience reaches a set-top box or smart TV** without a native SDK per vendor. |
| [rdkcentral/Lightning-SDK](https://github.com/rdkcentral/Lightning-SDK) | Apache-2.0 | 138★ | 2026-10-06 | The SDK layer above it. Two repos, 342 stars between them, and they carry the CTV side of this plane. |
| [rive-app/rive-runtime](https://github.com/rive-app/rive-runtime) | MIT | 1,270★ | 2026-11-26 | State-machine-driven interactive animation. The permissive way to make a character *react* without a game engine. |
| [vrm-c/UniVRM](https://github.com/vrm-c/UniVRM) | MIT | 3,432★ | 2026-10-19 | VRM avatar format for Unity — the interoperable character container APAC standardised on. |
| [pixiv/three-vrm](https://github.com/pixiv/three-vrm) | MIT | 2,309★ | 2026-11-24 | The same format on three.js, i.e. in a browser. |
| [jarikomppa/soloud](https://github.com/jarikomppa/soloud) | **zlib/libpng** (stated in `LICENSE`; GitHub reports `NOASSERTION`) | 2,200★ | 2024-08-13 | Easy embeddable audio engine. The permissive stand-in for Wwise/FMOD when the story needs adaptive sound. |
| [libpd/libpd](https://github.com/libpd/libpd) | **"Standard Improved BSD"** (stated in `LICENSE.txt`) | 1,257★ | 2026-09-20 | Pure Data as an embeddable synthesis library — procedural, state-reactive audio for a branching scene. |

### ⚠️ The licence findings of this pass — four new ways a licence hides, all measured byte by byte

1. **`LICENCE.md`, with a C.** `inkle/ink-unity-integration` is MIT and GitHub reports
   `NOASSERTION`, purely because the file uses British spelling. **Add `LICENCE`, `LICENCE.md` and
   `LICENCE.txt` to every licence probe in all twelve industries** — pass 4's probe, pass 8's
   extension and pass 27's byte-reader all missed this spelling.
2. **The licence lives in the documentation tree.** `renpy/renpy` has *no* root LICENSE file; its MIT
   grant is in `sphinx/source/license.rst`, with explicit carve-outs for derived components. A
   root-only probe reports "no licence" for a 7,065-star engine that is in fact MIT.
3. **The non-commercial OSS trap, twice in one plane.** `dfabulich/choicescript` (CSL v1.0) and
   `tegnike/aituber-kit` (custom dual licence) both read as open source on GitHub and both **forbid
   commercial use by default**. Neither is flagged by the SPDX field.
4. **The bespoke "community licence" tier.** `duixcom/Duix-Mobile` (8,362★) and
   `Tencent-Hunyuan/HunyuanVideo-Avatar` (2,226★) ship 6 KB bespoke agreements. The stars say
   "safe", the file says "read me". In this plane the two highest-starred avatar runtimes are both in
   this tier.

### The H5P seam — the single most useful licence fact in this plane

H5P is how branching narrative is *actually* shipped at scale today (learning, training, museum and
brand experiences), and its licence changes depending on which half you take:

| Repo | Licence | Stars | Last push | Role |
|---|---|---|---|---|
| [h5p/h5p-branching-scenario](https://github.com/h5p/h5p-branching-scenario) | **MIT** (stated in README) | 36★ | 2026-10-30 | The branching content type itself — decision trees over video and text. |
| [h5p/h5p-interactive-video](https://github.com/h5p/h5p-interactive-video) | MIT | 267★ | 2026-11-26 | Interactive video content type; pushed the day of this pass. |
| [h5p/h5p-php-library](https://github.com/h5p/h5p-php-library) | **GPL-3.0** | 156★ | 2026-11-26 | ⚠️ The **core host library**. The content types are MIT; the thing that runs them is copyleft. |
| [h5p/h5p-editor-php-library](https://github.com/h5p/h5p-editor-php-library) | no SPDX; same GPL family as the core | 83★ | 2026-11-26 | The authoring half of the host. |
| [Lumieducation/H5P-Nodejs-library](https://github.com/Lumieducation/H5P-Nodejs-library) | **GPL-3.0** (35,146 B, full GPLv3 text) | 207★ | 2026-11-26 | The Node/TypeScript host — the one a web team would reach for, and also GPL-3.0. |
| [h5p/moodle-mod_hvp](https://github.com/h5p/moodle-mod_hvp) | GPL-3.0 | 160★ | 2026-11-18 | The Moodle plugin (Moodle is GPL anyway, so no new constraint there). |
| [h5p/h5p-wordpress-plugin](https://github.com/h5p/h5p-wordpress-plugin) | no LICENSE file at probed names (WordPress plugins are GPL by platform convention) | 77★ | 2026-10-27 | The WordPress route. |

**Read it once and remember it: in H5P the *content types* are MIT and every *host implementation* is
GPL-3.0.** Secondary sources say "H5P is MIT" — that is true of the pieces that do not run anything.
If a client wants branching scenarios inside a closed product, the authoring/runtime host is the
licence decision, and the options are (a) accept GPL-3.0 for that service, (b) run H5P as a separate
service behind an API boundary, or (c) build the player on `h5p-branching-scenario`'s MIT content
type and skip the GPL host entirely. Option (c) is the one no vendor will tell you about.

### Measured absences — searched, and genuinely missing

| Searched | GitHub result | Reading |
|---|---|---|
| `second screen companion tv` | **2 repositories total**, both 0★ | No companion-device layer exists. The nearest real artefact is BBC's GPL-3.0 `audio-orchestrator` (11★). |
| `interactive fiction MCP` | **7 repositories total** | The entire agent bridge; see `agents/top.md` pass 29. |
| `branching scenario authoring` | **8 repositories**, none in-plane (top hits are unrelated student projects) | The capability is real and the vocabulary is not indexed — H5P does not describe itself with these words. |
| `object based media` | 187 repositories, none in-plane in the top results | BBC's own player ranks far below noise. Search by repo, not by concept. |
| interactive-video standard in HLS/DASH | nothing found | **There is no branching primitive in either standard.** Any proposal implies a player you own. |

---

## Pass 30 (2026-11-26) — foundations of the answer-engine discovery & measurement plane

Nine foundational repos, each verified twice (search-API metadata + `git ls-remote`). The split that
matters is the **licence** column: only two of the four analytics bases are permissive.

| Repo | URL | Licence | Stars / forks | Last push | Role in this plane |
|---|---|---|---|---|---|
| **GoAccess** | https://github.com/allinurl/goaccess | **MIT** | 21,158★ / 1,213f | 2026-11-26 | Real-time log analyser. **The only channel that sees an AI crawler at all** — a bot that never executes JavaScript is invisible to every tag-based analytics tool. This is the load-bearing repo of the plane. |
| **crawler-user-agents** | https://github.com/monperrus/crawler-user-agents | **MIT** | 1,416★ / 299f | 2026-11-26 | The crawler user-agent database. Pushed today. The identification substrate: without it, a log line is just a hit. |
| **Umami** | https://github.com/umami-software/umami | **MIT** | 40,403★ / 8,664f | 2026-11-26 | Self-hosted analytics, MIT, pushed today. **The only permissively-licensed general analytics base** — already referenced elsewhere in this KB; recorded here for its role as the human-session half of the ledger. |
| **referer-parser** | https://github.com/snowplow-referer-parser/referer-parser | ⚠️ **no licence file; `referers.yml` is GPL-3.0 by provenance** | 383★ / 148f | 2026-07-30 | Holds the **`chatbot:` referrer taxonomy** — see the measured asymmetry below. Read it, re-implement the list; do not vendor the YAML. |
| **llms-txt (spec)** | https://github.com/AnswerDotAI/llms-txt | Apache-2.0 | 2,702★ / 189f | 2026-09-24 | The standard itself. Recorded as a **foundation that measurably failed** — see `agents/top.md` pass 30. Kept in the KB so the refusal is citable. |
| **Crawler-Detect** | https://github.com/JayBizzle/Crawler-Detect | **MIT** | 2,413★ / 283f | 2026-11-26 | PHP crawler detection. Relevant because a very large share of the world's publishing runs on PHP/WordPress. |
| **isbot** | https://github.com/omrilotan/isbot | **Unlicense** (public domain) | 1,169★ / 86f | 2026-11-24 | JS-side bot detection. Unlicense is *more* permissive than MIT — no attribution duty at all. |
| **web-check** | https://github.com/lissy93/web-check | **MIT** | 35,661★ / 2,961f | 2026-11-23 | Site inspection — headers, robots, security, crawlability — in one pass. The fastest way to open a client conversation with evidence. |
| **sitemap.js** | https://github.com/ekalinin/sitemap.js | **MIT** | 1,710★ / 157f | 2026-11-01 | Sitemap and **news sitemap** generation. The boring artefact that still works when the fashionable one (`llms.txt`) does not. |

### The measured headline: the taxonomy of the channel replacing search is 3.9% the size of search

`referers.yml` was cloned and counted directly — not inferred. It has **six top-level categories**:

| Category | Entries |
|---|---|
| `unknown` | 3 |
| `email` | 45 |
| `social` | 90 |
| **`search`** | **232** |
| `paid` | 45 |
| **`chatbot`** | **9** |

**232 versus 9.** And `chatbot:` is new: the commit that created it is dated **2026-07-30**, *"Add
utm_sources for chatbot providers"*. The nine, in full: **Character.AI, ChatGPT, Claude.ai, Google
Gemini, META.ai, Microsoft Copilot, Mistral.ai, Perplexity.ai, Poe.** Measured absences in the same
file: **Grok/xAI 0, DeepSeek 0, You.com 0, Phind 0** (and `anthropic` as a token: **0** — only
`claude.ai` is listed).

The good news is real and should be said: **the vocabulary now models AI answer engines as a distinct
channel rather than filing them under `search:`.** That is the correct shape, it arrived in July 2026,
and it is the substrate any honest AI-referral dashboard rests on.

### ⛔ The structural blind spot — and why "add the AI engines to your referrer list" is not a fix

**Google AI Overviews and AI Mode are served from `google.com`, the same host as organic search.**
They therefore **cannot be represented in a referrer taxonomy at all**, however many entries it
gains. A zero-click answer emits **no referrer and no click**. So the single largest AI-answer surface
in the world is *structurally* invisible to referrer analytics — not under-counted, but unobservable
in principle through that channel.

This is the finding that dictates the plane's architecture, and it is why the two load-bearing repos
above are a **log analyser** and a **user-agent database** rather than a JavaScript tag:

| What you want to know | Only channel that can answer it | Open tooling |
|---|---|---|
| Did an AI crawler fetch my content? | Server / CDN logs | `goaccess` + `crawler-user-agents` (both MIT) ✅ |
| Did a user arrive *from* a chatbot? | Referrer / UTM | `referer-parser` `chatbot:` ⚠️ GPL-3.0 data |
| Did I appear inside an AI Overview? | **Google Search Console gen-AI reports only** | **none** — impressions, and *no clicks* |
| What was that appearance worth? | — | **nothing exists** |

### Measured search zeros and non-zeros for this plane

| Query | Result | Reading |
|---|---|---|
| open-source "AI visibility platform" comparable to Odoo/Moodle | **does not exist** | The commercial tier is proprietary (Ahrefs Bot Analytics, Cloudflare Attribution Business Insights, Semrush AI Visibility Toolkit, AthenaHQ, Rankscale). The open tier is a handful of WordPress plugins plus `loamly` (21★). |
| `cloudflare/ai.txt`, `usewebsights/llms-txt`, `nalgeon/llms-txt` | **all three do not exist** | Checked precisely because plausible-looking slugs appear in listicles. Three rows that a careless pass would have invented. |
| permissive self-hosted analytics | **two only**: `umami` MIT, `goaccess` MIT | `plausible` is **AGPL-3.0**, `matomo` **GPL-3.0**, `matomo-org/device-detector` **LGPL-3.0** (3,562★). The default choices are all copyleft. |

## The live-event, show-control & stagecraft substrate — measured 2026-11-27 (pass 31)

The finding that shapes this section: **this is one of the healthiest open substrates in the KB and
the hardest to find.** Twenty-eight repos verified below; the oldest predate every generative-media
project in this file; nine were pushed in the week of this pass. And the web-search layer surfaced
**none of them** (see `repos/trending.md` for that measurement). The permissive tier is unusually
strong — QLC+ is the only fully Apache-2.0 production console in any plane of this KB — while the
*fixture data* that makes a console able to drive a real light is registration-gated.

### Tier 1 — the network and standards layer: permissive, official, and almost unstarred

ANSI/ESTA standards implementations, published by **Electronic Theatre Controls** — the incumbent
console manufacturer. This is exactly Netflix's posture in the generative tier (publish the
measurement and delivery standards, keep the product) at **one-hundredth of the star count**.

| Repo | Licence | Stars | Last push | Why it matters |
|---|---|---|---|---|
| [ETCLabs/sACN](https://github.com/ETCLabs/sACN) | Apache-2.0 | 44★ | 2026-11-16 | Implementation of **ANSI E1.31 (sACN)** — lighting control over IP. The network protocol essentially every modern rig runs on, maintained by the market-leading manufacturer, at 44 stars. |
| [ETCLabs/RDMnet](https://github.com/ETCLabs/RDMnet) | Apache-2.0 | 56★ | 2026-09-25 | **ANSI E1.33** — device discovery, configuration and management over IP. The layer that makes a rig inventoriable, which is the precondition for any agent that reasons about it. |
| [ETCLabs/RDM](https://github.com/ETCLabs/RDM) | Apache-2.0 | 11★ | 2026-09-25 | Helper library for the **ANSI E1.20 (RDM)** message format — bidirectional DMX. |
| [ETCLabs/EtcPal](https://github.com/ETCLabs/EtcPal) | Apache-2.0 | 21★ | 2026-09-25 | Platform abstraction layer the three libraries above share. Pin it deliberately; it is the common dependency. |
| [OpenLightingProject/libartnet](https://github.com/OpenLightingProject/libartnet) | LGPL-2.1 | 151★ | 2025-12-16 | Reference implementation of **Art-Net**, the UDP transport that carries DMX512-A. LGPL — link, do not fork into a proprietary binary. |
| [ETCLabs/OSCRouter](https://github.com/ETCLabs/OSCRouter) | MIT | 197★ | 2026-07-08 | UDP/TCP packet router with OSC awareness. The most-starred thing ETC publishes, and marked **UNOFFICIAL**. |
| [x42/libltc](https://github.com/x42/libltc) | LGPL-3.0 | 255★ | 2022-09-04 | **SMPTE/LTC linear timecode** encode/decode. Dormant since 2022 and that is fine: timecode has not changed. This is the clock that makes lights, audio and video agree. |
| [Hundemeier/sacn](https://github.com/Hundemeier/sacn) | MIT | 56★ | 2025-02-18 | sACN/E1.31 in pure Python — the fastest permissive path from a Python agent to a real fixture. |
| [bondagit/aes67-linux-daemon](https://github.com/bondagit/aes67-linux-daemon) | GPL-3.0 | 572★ | 2026-10-26 | **AES67** audio-over-IP with a config web UI. The open counterpart to Dante, which is proprietary (Audinate) and has no open implementation. |

**Governance note worth carrying to other industries:** every ETCLabs repo that is a *tool* rather
than a *standard* has its description prefixed **"UNOFFICIAL"** — `OSCRouter`, `Sound2Light`,
`lighthack`, `ETCDmxTool`, `EosSyncLib`. The manufacturer open-sources the standards it is obliged to
interoperate on, and explicitly disclaims support for everything else. Read that prefix as a support
statement, not modesty: it is the licence's warranty disclaimer restated in the shop window.

### Tier 2 — consoles, cue players and control hubs: real, old, and mostly copyleft

| Repo | Licence | Stars | Last push | Role |
|---|---|---|---|---|
| [bitfocus/companion](https://github.com/bitfocus/companion) | **MIT + CLA** | 2,376★ | 2026-11-22 | Turns Stream Deck-class controllers into a control surface for hundreds of devices. The most-starred control project in the plane. **Licence read: `LICENSE.md` Part 1 is plain MIT; Part 2 is a Contributor Licence Agreement** granting Bitfocus a perpetual, transferable, sublicensable copyright licence over contributions. Free to use and ship; material if your team contributes upstream. This is why the API reports `NOASSERTION`. |
| [benkuper/Chataigne](https://github.com/benkuper/Chataigne) | GPL-3.0 | 1,718★ | 2026-11-26 | The show-control hub: any protocol in (OSC, MIDI, DMX, Art-Net, HTTP), any protocol out, with state machines between. The open answer to QLab-class cueing for installations. Pushed the day before this pass. |
| [mcallegari/qlcplus](https://github.com/mcallegari/qlcplus) | **Apache-2.0** | 1,593★ | 2026-11-26 | **QLC+ — the single most important row in this section.** A full DMX/analogue lighting console: patching, cue lists, effects, virtual console, GDTF import. **Apache-2.0 and pushed the day before this pass.** The only production-grade console in any plane of this KB that a client can embed, rebrand and ship without a copyleft conversation. |
| [OpenLightingProject/ola](https://github.com/OpenLightingProject/ola) | **LGPL-2.1** (COPYING) | 773★ | 2026-10-14 | Open Lighting Architecture — the protocol-conversion daemon between every DMX transport and interface. **Licence read: the API says `NOASSERTION` because the grant is in `COPYING`, not `LICENSE` (404), and reads LGPL-2.1; the bundled tools are GPL-2.** Third confirmation of the pass-8 naming rule: *a 404 from the raw channel is never by itself proof a licence is missing.* |
| [xLightsSequencer/xLights](https://github.com/xLightsSequencer/xLights) | GPL-3.0 | 768★ | 2026-11-26 | Sequencer for large pixel/LED shows with E1.31 and USB output. **Repo renamed: `smeighan/xLights` no longer resolves as the project home** — the sixth rename this KB has had to correct, after ComfyUI, KrillinAI, Mochi, firecrawl and OFL's own moves. |
| [FalconChristmas/fpp](https://github.com/FalconChristmas/fpp) | ⚠️ **compilation: GPL-2 + LGPL-2.1 + CC-BY-ND** | 747★ | 2026-11-26 | Falcon Player — the playback engine for large synchronised light shows. **See the licence warning below. Do not ship this without reading it.** |
| [FrancescoCeruti/linux-show-player](https://github.com/FrancescoCeruti/linux-show-player) | GPL-3.0 | 314★ | 2026-10-24 | Cue player for stage productions — the open, Linux-side answer to QLab for sound playback. |
| [OpenLightingProject/rp2040-dmxsun](https://github.com/OpenLightingProject/rp2040-dmxsun) | Apache-2.0 | 128★ | 2025-03-31 | RP2040-based USB-DMX dongle with an onboard web server. Permissive **hardware** interface, which is rarer than permissive software here. |
| [tombueng/LuxDMX](https://github.com/tombueng/LuxDMX) | Apache-2.0 | 104★ | 2026-11-22 | ESP32 Art-Net/sACN→DMX512 gateway firmware, browser-flashable, with a live 512-channel view and console-conflict detection. Permissive, active, 7 forks. |
| [wled/WLED](https://github.com/wled/WLED) | **EUPL-1.2** | 19,132★ | 2026-11-26 | Addressable-LED control firmware over WiFi, with E1.31/DDP input. **By far the most-starred repo in this plane — 11× the next one — and under the European Union Public Licence, the first EUPL repo in this KB.** EUPL-1.2 is copyleft, governed by EU law, and on the Commission's compatibility list with GPL-family licences. Treat it as copyleft, and note that its governing-law clause is a live question for a non-EU client. |

### Tier 3 — device description, visualisation and projection

| Repo | Licence | Stars | Last push | Role |
|---|---|---|---|---|
| [OpenLightingProject/open-fixture-library](https://github.com/OpenLightingProject/open-fixture-library) | MIT (code) | 274★ | 2026-11-26 | OFL — library and website of DMX fixture definitions, exporting to many console formats. **The only ungated fixture-data channel found.** Licence read: `LICENSE` is the MIT text (2017, Florian & Felix Edelmann) covering the **code**; the licence of the **fixture definitions themselves is not stated in the repo**, and `open-fixture-library.org` is outside this session's network policy, so it could not be verified. **Recorded as an unresolved gap, not as CC-BY-SA** — see the warning below. |
| [open-stage/python-gdtf](https://github.com/open-stage/python-gdtf) | MIT | 16★ | 2026-08-23 | pygdtf — parses **GDTF** (General Device Type Format), the device-description standard recognised as **DIN SPEC 15800:2022**. MIT, and the dependency under BlenderDMX. |
| [open-stage/python-mvr](https://github.com/open-stage/python-mvr) | MIT | 19★ | 2026-08-23 | pymvr — parses **MVR** ("My Virtual Rig"), the scene-exchange half of GDTF: the whole rig, its positions and its patch as one file. **This is the `OpenTimelineIO` of live events** — the clean handoff between a tool and a human designer. |
| [open-stage/python-psn](https://github.com/open-stage/python-psn) | MIT | 5★ | 2026-08-23 | **PosiStageNet** — live position tracking of performers and moving scenery. 5 stars, and it is the entire open implementation of the protocol that makes followspots and projection track a moving body. |
| [open-stage/blender-dmx](https://github.com/open-stage/blender-dmx) | GPL-3.0 | 291★ | 2026-11-15 | BlenderDMX — design, visualise and pre-programme a rig inside Blender, importing GDTF fixtures and MVR scenes. The pre-visualisation tier, and the most-starred thing in the GDTF ecosystem. |
| [cpdt/gdtf-rs](https://github.com/cpdt/gdtf-rs) | MIT | 1★ | 2026-08-11 | GDTF in Rust. **One star — listed for completeness and explicitly not recommended**; use pygdtf. |
| [kpfaulkner/mvr](https://github.com/kpfaulkner/mvr) | Apache-2.0 | — | — | MVR/GDTF in Go. Resolves and is Apache-2.0; its own docs state several optional GDTF sections (Wheels, Models) are not modelled. Partial by the author's admission. |
| [mapmapteam/mapmap](https://github.com/mapmapteam/mapmap) | GPL-3.0 | 731★ | 2026-11-26 | Projection mapping — the established open tool, pushed the day before this pass, 202 open issues. |
| [paperManu/splash](https://github.com/paperManu/splash) | GPL-3.0 | 530★ | 2025-09-26 | Modular video-mapping for multi-projector installations with calibration. **GitHub repo is a declared mirror** — development is on GitLab, so watch upstream there, not here. |
| [ETCLabs/ETCDmxTool](https://github.com/ETCLabs/ETCDmxTool) | Apache-2.0 | 30★ | 2023-11-22 | DMX/RDM controller and **sniffer**. The diagnostic tool for the "is my agent actually sending what I think" question. UNOFFICIAL, dormant since 2023. |

### ⚠️ The licence warning of this pass: a no-derivatives clause inside a 747-star "open source" player

[FalconChristmas/fpp](https://github.com/FalconChristmas/fpp) reports `NOASSERTION`. Its `LICENSE`
file is not a licence — it is a **manifest of several licences**, and it states plainly that the core
is LGPL-2.1-or-later, other components are GPL-2, and **"Other parts of FPP such as those covered
under the CC-BY-ND license are redistributable in their original form, but may not be modified and
redistributed."**

This is the **second confirmation, and the more severe instance, of the pass-8 law that a licence can
be a property of the compilation rather than of the repository.** Chromaprint was MIT code that became
LGPL-2.1 as a whole; this is worse, because **CC-BY-ND forbids modification outright** — and
modification is precisely what a client engagement is. No SPDX field, no badge and no source-tree SBOM
scan surfaces this; only reading the file does. The operational rule, now proven twice in this
industry: **for any repo reporting `NOASSERTION`, read the licence file before it reaches a proposal,
and read it looking for the word "components".**

### The gated layer, and the seventh confirmation of the content law

The console code is free. The **device definition** is not — and without it a console cannot control a
real light, only a channel number.

- **GDTF is a genuinely open standard**: recognised as **DIN SPEC 15800:2022**, with MIT libraries
  (`pygdtf`, `pymvr`) and a GPL-3.0 visualiser (`blender-dmx`). The *format* is unencumbered.
- **GDTF Share, the fixture library, requires a free account and has no anonymous download path**, and
  the files are published **by each manufacturer under its own terms**. Third-party build scripts that
  need fixtures authenticate with a personal GDTF Share account. (`gdtf-share.com` is outside this
  session's network policy; this is sourced from the consuming projects' own documentation and from
  secondary documentation, and the account requirement should be re-verified directly when the host is
  reachable.)
- **Open Fixture Library is the only ungated channel**, MIT for its code — and its **data licence is
  unstated in the repo and could not be verified** this pass.

So: **the spec is open, the parsers are MIT, and the content is registration-gated with per-vendor
terms.** Identical in shape to CPT in healthcare, MedDRA in pharmacovigilance, and ISRC/ISWC/EIDR in
the identification plane (pass 5). Seventh plane, seventh identical result. **Never promise a client
an end-to-end open fixture pipeline without resolving where the fixture definitions come from and
under whose terms** — that is the one question in this plane that cannot be answered with code.

### Informed gaps — searched, and genuinely not there

- **Ride and attraction show control is closed, and will stay closed.** The only open library surfaced
  was ShowControl4J, roughly 2.3 years dormant. Ride control is safety-rated PLC engineering carrying
  personal-injury liability; it is not a candidate for open substitution. Disney filed two AI patent
  applications in **August 2026** — ML monitoring performers to adjust animatronic responses, and ML
  for attraction maintenance — which are **filings, not shipped products**. Europa-Park has described
  working on a comprehensive "AI Suite" rather than a single AI attraction.
- **OpenLP, the main open worship-presentation platform, is not meaningfully on GitHub** — its
  canonical home is GitLab, and a GitHub-only sweep returns only sub-2-star derivatives
  (`Gamusi/OpenLPxx`, `tbc-productions/opal-presenter`, `BlazingAsher/OpenLP-WCAC`). A reminder that
  **this KB's GitHub-centred method has a systematic blind spot for GitLab-hosted projects**, which in
  this plane and in pass-5's Panako case has now cost two real findings.
- **Open Stage Control's GitHub repo is archived** (`jean-emmanuel/open-stage-control`, 7★,
  read-only). The project is referenced widely in the field; its live home is not GitHub. Do not cite
  the archived repo as a live dependency.
- **Dante has no open implementation.** AES67 (`aes67-linux-daemon`, GPL-3.0) is the open path for
  audio-over-IP; Dante remains proprietary to Audinate. State this before promising audio transport.

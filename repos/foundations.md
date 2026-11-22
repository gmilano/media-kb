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
| [CasparCG/server](https://github.com/CasparCG/server) | GPL-3.0 | 1,112 | 329 | 2026-11-11 | The graphics/playout server Sofie drives, from SVT (Swedish public broadcaster). GPL-3.0, used over its own protocol — which is how Sofie uses it. |
| [ebu/awesome-broadcasting](https://github.com/ebu/awesome-broadcasting) | CC0-1.0 | 1,803 | 238 | 2026-09-30 | **The EBU's own public-domain index of open broadcast tooling.** Institutional rather than a listicle, and the place Sofie and ffplayout are catalogued. Start discovery here, not on GitHub search. |

**Read the ★/fork column before judging these by stars.** `sofie-timeline-state-resolver` sits at
25★/25f, `sofie-package-manager` and `sofie-hyperdeck-connection` have *more forks than stars*, and
`sofie-input-gateway` is 0★/5f. Deployed broadcast infrastructure gets forked and configured, not
starred. Zero stars with five forks is not abandonment — it is a library whose entire audience is
broadcast engineers who run it in a gallery.

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

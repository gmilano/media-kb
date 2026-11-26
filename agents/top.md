---
industry: media
region: Global
updated: 2026-11-26
---

# 🎯 AI Agents & Generative Media Models — Media & Entertainment

> Open source agents and generative models for M&E. Focus: MIT / Apache 2.0 / BSD — what Globant can build on.
> **Every row below was verified on 2026-11-21**: existence via `git ls-remote`, stars + last-push via
> GitHub `search/repositories`, and license by reading the actual LICENSE file where the API returned
> `NOASSERTION`. Star counts are point-in-time, not carried forward from earlier cycles.

## Tier 1 — Permissive, actively maintained (safe to build on)

| Agent / Model | Repo | License | Stars | Last push | What it does |
|---|---|---|---|---|---|
| MoneyPrinterTurbo | [harry0703/MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | MIT | 144,854 | 2026-11-20 | One-click short-video generation from a topic/script: picks footage, TTS voiceover, subtitles, renders. The most-starred media agent on GitHub. |
| Hyperframes | [heygen-com/hyperframes](https://github.com/heygen-com/hyperframes) | Apache-2.0 | 87,525 | 2026-11-21 | HeyGen's open framework for agentic video generation. License file read and confirmed genuine Apache-2.0. |
| GPT-SoVITS | [RVC-Boss/GPT-SoVITS](https://github.com/RVC-Boss/GPT-SoVITS) | MIT | 64,146 | 2026-11-11 | Few-shot voice cloning + TTS; ~1 min of reference audio. Strong for localization and dubbing. |
| Voicebox | [jamiepine/voicebox](https://github.com/jamiepine/voicebox) | MIT | 61,009 | 2026-10-07 | Open-source AI voice studio: clone, dictate, create. |
| Open-Sora | [hpcaitech/Open-Sora](https://github.com/hpcaitech/Open-Sora) | Apache-2.0 | 29,943 | 2026-04-09 | Full text-to-video training + inference stack. Fully Apache, but **7 months without a push** — treat as a frozen baseline, not a live dependency. |
| Chatterbox | [resemble-ai/chatterbox](https://github.com/resemble-ai/chatterbox) | MIT | 28,008 | 2026-11-04 | Production TTS from Resemble AI, with emotion-exaggeration control. |
| AudioCraft | [facebookresearch/audiocraft](https://github.com/facebookresearch/audiocraft) | MIT | 23,935 | 2026-03-03 | MusicGen + AudioGen + EnCodec: music and sound-effect generation, MIT end to end. |
| VideoLingo | [Huanshere/VideoLingo](https://github.com/Huanshere/VideoLingo) | Apache-2.0 | 19,339 | 2026-11-13 | Subtitling + dubbing pipeline: Whisper align → translate → TTS → burn-in. Localization workhorse. |
| Wan 2.2 | [Wan-Video/Wan2.2](https://github.com/Wan-Video/Wan2.2) | Apache-2.0 | 18,802 | 2026-09-21 | MoE text-to-video; the strongest open model that runs on a single consumer GPU. |
| Wan 2.1 | [Wan-Video/Wan2.1](https://github.com/Wan-Video/Wan2.1) | Apache-2.0 | 17,469 | 2026-03-05 | Previous Wan generation; lighter VRAM, still widely deployed. |
| F5-TTS | [SWivid/F5-TTS](https://github.com/SWivid/F5-TTS) | MIT | 15,633 | 2026-11-03 | Flow-matching TTS, fast and high-fidelity zero-shot cloning. |
| OpenCreator | [krillinai/OpenCreator](https://github.com/krillinai/OpenCreator) | Apache-2.0 | 14,449 | 2026-11-20 | **Renamed from `krillinai/KrillinAI`.** Multi-language video repurposing and dubbing agent. |
| rea-video | [JuneYaooo/rea-video](https://github.com/JuneYaooo/rea-video) | Apache-2.0 | 11,476 | 2026-11-21 | Agentic video creation workbench; currently top of GitHub's AI-video star-velocity lists. License file read and confirmed. |
| LTX-Video | [Lightricks/LTX-Video](https://github.com/Lightricks/LTX-Video) | Apache-2.0 | 11,445 | 2026-11-02 | Lightricks' real-time-class DiT video model; the most practical latency/quality trade-off. |
| Kokoro-82M | [hexgrad/kokoro](https://github.com/hexgrad/kokoro) | Apache-2.0 | 10,273 | 2025-08-06 | 82M-param TTS that runs on CPU. **Correction: 10.3k stars, not the ~35–38k earlier cycles recorded** (that figure was the Hugging Face model page, not this repo), and no push since Aug 2025. |
| MuseTalk | [TMElyralab/MuseTalk](https://github.com/TMElyralab/MuseTalk) | MIT | 6,999 | 2026-11-19 | Real-time high-quality lip-sync / talking-head dubbing. |
| Mochi 1 | [genmoai/mochi](https://github.com/genmoai/mochi) | Apache-2.0 | 3,766 | 2026-10-22 | **Renamed from `genmoai/models`.** Genmo's 10B diffusion video model. |
| mediago-drama | [mediago-dev/mediago-drama](https://github.com/mediago-dev/mediago-drama) | Apache-2.0 | 110 | 2026-10-21 | Novel→short-drama agent workbench (text to episodic video). Small but the only vertical short-drama agent found. |

## Tier 2 — Real and useful, but the license or staleness constrains client work

| Agent / Model | Repo | License | Stars | Last push | Constraint |
|---|---|---|---|---|---|
| OpenMontage | [OpenMontageInc/OpenMontage](https://github.com/OpenMontageInc/OpenMontage) | **AGPL-3.0** | 81,978 | 2026-11-16 | Agentic video production suite, and the biggest M&E agent after MoneyPrinterTurbo — but AGPL-3.0 (34,522-byte license file read to confirm). Network copyleft: deploy unmodified and integrate over its API, or the client's own code becomes disclosable. Listicles describing it as MIT-ish at "63k stars" are wrong on both counts. |
| ChatTTS | [2noise/ChatTTS](https://github.com/2noise/ChatTTS) | AGPL-3.0 | 40,033 | 2026-04-10 | Excellent conversational TTS; AGPL makes it unsuitable as an embedded library in proprietary work. |
| fish-speech | [fishaudio/fish-speech](https://github.com/fishaudio/fish-speech) | Fish Audio Community License v1.0 | 33,814 | 2026-11-14 | **Not** a permissive license (19,684-byte custom agreement, last updated 2026-10-13). Review before any commercial use. |
| OpenVoice | [myshell-ai/OpenVoice](https://github.com/myshell-ai/OpenVoice) | MIT | 38,295 | 2025-04-19 | MIT and genuinely good, but dormant ~19 months. Fine to vendor; do not expect upstream fixes. |
| pyvideotrans | [jianchang512/pyvideotrans](https://github.com/jianchang512/pyvideotrans) | GPL-3.0 | 19,786 | 2026-11-21 | Very active video translation/dubbing tool. GPL-3.0 → ship as a separate process/CLI, not linked in. |
| SadTalker | [OpenTalker/SadTalker](https://github.com/OpenTalker/SadTalker) | Apache-2.0 | 14,213 | 2024-06-26 | Audio-driven talking head. Its LICENSE opens "Tencent … All rights reserved." but **is** Apache-2.0 with third-party carve-outs — read past line 1. Dormant since mid-2024. |
| CogVideo / CogVideoX | [zai-org/CogVideo](https://github.com/zai-org/CogVideo) | Apache-2.0 | 13,217 | 2025-11-04 | **Renamed from `THUDM/CogVideo`.** Apache-2.0, but no push in ~12 months. |
| HunyuanVideo | [Tencent-Hunyuan/HunyuanVideo](https://github.com/Tencent-Hunyuan/HunyuanVideo) | Tencent Hunyuan Community | 12,815 | 2026-10-08 | ⚠️ **Territorially restricted.** The license text states it "DOES NOT APPLY IN THE EUROPEAN UNION, UNITED KINGDOM AND SOUTH KOREA." Unusable for EMEA and South Korean engagements — a constraint no listicle surfaces. Also needs 60–80 GB VRAM at full size. |

## Re-verified 2026-11-22 — what moved, and what was added elsewhere

Spot-checked the rows above against fresh `search/repositories` measurements. **Every figure the
2026-11-21 pass *measured* reproduced within a day's drift** — `mediago-drama` 110★ exactly,
`KyaniteLabs/kinocut` 272→278★, `Netflix/photon` 258★ exactly, `OpenTimelineIO` 2,105→2,109★,
`c2pa-rs` 452→453★. The figures that were wrong in earlier cycles were the ones *inherited from
listicles*, never the ones measured. **Measuring is cheap; inheriting is expensive.** No row above
needed correction this pass.

**Two agent/model families were added to other files rather than duplicated here:**

- **Provenance & watermarking models** — `facebookresearch/videoseal` (MIT, 828★),
  `facebookresearch/audioseal` (MIT, 804★), `adobe/trustmark` (MIT, 189★),
  `google-deepmind/synthid-text` (Apache-2.0, 1,258★). These retract this KB's previous claim that no
  permissive watermarking library existed. Full table in `repos/foundations.md`; the adversarial
  counter-measurement is in `intel/trends.md` trend 8; the recipe is `compose/patterns.md` Pattern 8.
- **Broadcast automation (Sofie, MIT)** — a 23-repo MIT ecosystem from NRK that retracts the "no open
  MOS implementation exists" claim. Platform in `verticals/solutions.md`, libraries in
  `repos/foundations.md`, the agent recipe in `compose/patterns.md` Pattern 7.

**Also added to `repos/foundations.md` this pass, and load-bearing for Pattern 2:**
[`pyannote/pyannote-audio`](https://github.com/pyannote/pyannote-audio) (MIT, 10,831★, pushed
2026-11-19) — the speaker-diarization toolkit `whisperX` is built on, absent from this KB until now;
and [`facebookresearch/demucs`](https://github.com/facebookresearch/demucs) (MIT, 10,423★,
**archived**) for stem separation, which is how a title gets re-dubbed when the original M&E stems are
lost.

### Short-form drama (the APAC category clients ask about): informed gap, not silence

Searched the `short-drama`, `micro-drama` and `ai-short-drama` topics. The category is commercially
real; the open code is mostly unusable, and the reason is worth recording so no future pass re-adopts
these:

| Candidate | Measured | Verdict |
|---|---|---|
| [mediago-dev/mediago-drama](https://github.com/mediago-dev/mediago-drama) | Apache-2.0, 110★/29f, 2026-10-21 | **The only usable one.** Re-measured at exactly the 110★ the last pass recorded. Novel→short-drama agent workbench. Already in Tier 1 above. |
| [Anil-matcha/Open-AI-Micro-Drama-Generator](https://github.com/Anil-matcha/Open-AI-Micro-Drama-Generator) | **no LICENSE file**, 587★/123f, 2026-08-02 | **Reject.** Unlicensed, and a wrapper around *paid closed* APIs (Seedance, Kling, Veo, Sora) — neither open nor self-hostable. |
| `chatfire-AI/drama-skills` | slug does not resolve | **Reject.** Promoted by a directory site as "~4.4k★, MIT". It does not exist. |
| `huobao-drama` | unconfirmed at any slug; reported CC-BY-NC-SA-4.0 | **Reject.** Non-commercial licensing would bar client work even if the claimed ~18k★ are real. |

**The honest line for a client:** for short-form drama, the open ecosystem gives you one Apache-2.0
workbench and otherwise expects you to rent closed video models. Build this pattern on the
Apache-2.0 generators already in Tier 1 (Wan 2.2, LTX-Video) rather than on a short-drama-branded
wrapper, and you keep both the license position and the model choice.

## The monetization plane has no agent layer — measured on 2026-11-22, not assumed

`repos/foundations.md` gained a whole new section this pass: the ad signalling, auction and
measurement layer. The obvious follow-up question is which **agents** compose onto it. The measured
answer is **none that can be listed here**, and that is the commercially useful finding, so it is
written down rather than padded.

**What was searched:** `open source AI agent advertising creative generation media buying github 2026
MIT Apache`, plus the ad-tech cuts of the four prescribed global queries.

**What came back:** commercial products, almost exclusively — Creatify's *AI Media Buyer*, Omneky
(which released an API and MCP server but not the agent), AdsGency, and Taboola's agent tooling. The
only named open-source candidate, `Nuraveda_lab/ai-ads-agent`, is hosted on **Codeberg, not GitHub**,
and `git ls-remote` could not reach it — so it fails this KB's existence test and gets no row. Two
further leads ("MiniAgent", an unnamed `ad-ops` topic repo) had no verifiable licence and no
resolvable slug.

**So the row count for this section is zero, and the table is omitted rather than filled.** Compare
the generation side of this same file: ten permissive, actively-maintained models. The asymmetry is
real and it is the opportunity — the ad plane has excellent permissive *infrastructure* (Prebid pushed
today, Druid and Pinot under the ASF) and **no open agent on top of any of it.**

**What to compose instead, using only rows that already exist in this KB:**

- **Creative variation** is already solved here. The TVBEurope signal for 2026 is AI-native content
  packaging — platforms generating multiple versions of promos and previews per user context. That is
  Tier 1 of this file (Wan, CogVideoX) plus `compose/patterns.md` Pattern 5, pointed at ad creative
  instead of social clips. No new agent needed.
- **Localized ad creative** is Pattern 2 (the localization factory) with a 15-second input. For LATAM
  this matters more than it sounds: one Spanish-language campaign, re-voiced per market, is the same
  pipeline the Mexican dubbing industry already buys.
- **The decisioning agent is the unbuilt product**, and it is the direct sibling of Pattern 4's
  consent ledger: both are cases where this KB found strong permissive primitives, a hard regulatory
  driver, and nobody selling the thing in between.

**One caution carried over from this file's own corrections.** An "ad agent" is the kind of target
where keyword-collision ingest produces confident, plausible, wrong rows — the sister `retail-kb`
carried a *Minecraft hopper-optimization mod* as inventory intelligence for months. Anything proposed
for this section needs the proper name of a real ad-tech artefact in it (openrtb, scte-35, vast,
prebid, tcf) before it earns a row.

## The accessibility plane — measured 2026-11-22 (pass 3)

Three passes of this file covered generation, provenance and the ad plane. The plane that was missing
is the one with a **statutory deadline attached**: captions, audio description and the player UI that
exposes them. It is the only plane in this KB where a client's legal exposure, not their ambition,
sets the delivery date — the EAA has applied since 2025-06-28, and the FCC's caption-display-settings
rule reached its compliance date on 2026-08-17.

The shape of the plane, measured rather than assumed: **the format layer is permissive and alive, and
the conformance layer — the part that proves compliance — is dormant or abandoned.**

### Tier 1 — permissive, active, safe to build on

| Agent / Tool | Repo | License | Stars | Last push | What it does |
|---|---|---|---|---|---|
| Subtitle Edit | [SubtitleEdit/subtitleedit](https://github.com/SubtitleEdit/subtitleedit) | MIT | 15,100 | 2026-11-22 | The reference open subtitle editor, 300+ formats, with Whisper integration built in. **Correction to the common assumption: it is MIT, not GPL** — LICENSE file read. The single most useful artefact in this plane. |
| stable-ts | [jianfch/stable-ts](https://github.com/jianfch/stable-ts) | MIT | 2,300 | 2026-05-30 | Whisper with usable word-level timestamps and forced alignment. The piece plain Whisper lacks for caption timing. 6 months without a push — vendor it. |
| Able Player | [ableplayer/ableplayer](https://github.com/ableplayer/ableplayer) | MIT | 837 | 2026-11-20 | Fully accessible HTML5 player, and the only one here that natively carries **audio description** (described `<source>` or a WebVTT `descriptions` track) **and sign language** (a second synchronized player). This is the EAA player-UI duty, already solved. |
| subaligner | [baxtree/subaligner](https://github.com/baxtree/subaligner) | MIT | 509 | 2026-11-02 | Re-syncs drifted subtitles via DNN forced alignment; also transcribes and translates. Fixes the defect most caption QC actually finds. |
| ttconv | [sandflow/ttconv](https://github.com/sandflow/ttconv) | BSD-2-Clause | 242 | 2026-11-21 | Converts between STL, SRT, TTML, SCC and WebVTT. The broadcast-to-web bridge: EBU-STL in, IMSC/WebVTT out. |
| imscJS | [sandflow/imscJS](https://github.com/sandflow/imscJS) | BSD-2-Clause | 92 | 2026-11-20 | Renders IMSC Text and Image Profile documents to HTML5. The reference IMSC renderer. |
| dash.js | [Dash-Industry-Forum/dash.js](https://github.com/Dash-Industry-Forum/dash.js) | BSD-3-Clause | — | 2026-11-22 | DASH reference player; renders caption and description tracks. Already in `foundations.md` for delivery — it earns a row here for the accessibility track handling. |
| IMSC test suites | [w3c/imsc-tests](https://github.com/w3c/imsc-tests) | W3C Test Suite License **or** W3C BSD-3-Clause (dual) | 18 | 2026-10-22 | The conformance corpus for IMSC. ⚠️ Licence subtlety read from LICENSE.md: under the Test Suite option "no right to create modifications or derivatives" is granted — **take the BSD-3 option** if you need to adapt the tests. |

### Tier 2 — real, but the licence or the staleness constrains client work

| Agent / Tool | Repo | License | Stars | Last push | Constraint |
|---|---|---|---|---|---|
| CCExtractor | [CCExtractor/ccextractor](https://github.com/CCExtractor/ccextractor) | **GPL-2.0** | 919 | 2026-11-11 | The canonical extractor for CEA-608/708 captions out of broadcast streams, and genuinely active. GPL-2.0 → run it as a separate process/CLI, never linked in. There is no permissive equivalent, so this constraint is structural. |
| axe-core | [dequelabs/axe-core](https://github.com/dequelabs/axe-core) | **MPL-2.0** | — | 2026-11-16 | The accessibility conformance engine for the *player UI* half of the EAA duty. MPL-2.0 is file-level copyleft: usable in a proprietary product, but modifications to its own files must be published. |
| VideoCaptioner | [WEIFENG2333/VideoCaptioner](https://github.com/WEIFENG2333/VideoCaptioner) | **GPL-3.0** | — | 2026-05-24 | LLM-assisted subtitle pipeline that trended through late 2025. GPL-3.0 and 6 months quiet. |
| whisper-subs | [GeiserX/whisper-subs](https://github.com/GeiserX/whisper-subs) | **GPL-3.0** | — | 2026-11-16 | Active LLM transcribe/translate to SRT, ASS/SSA, VTT. GPL-3.0 → separate process only. |
| Rylo Translate (ex `sign.mt`) | [sign/translate](https://github.com/sign/translate) | ⚠️ **Source-available, dual-tier (Nagish Inc.)** | — | 2026-08-11 | Sign-language translation, and the most visible project in that space. **Not open source for Globant's purposes:** LICENSE.md grants free use to individuals, non-profits and education only, and *"a separate license is required for for-profit commercial organizations."* Any client engagement needs a commercial licence first. |

### The conformance layer is the gap — and it is a measured one

| Repo | License | Stars | Last push | Status |
|---|---|---|---|---|
| [sandflow/imscHRM](https://github.com/sandflow/imscHRM) | BSD-2-Clause | 10 | 2024-05-16 | **Dormant ~920 days.** Validates the IMSC Hypothetical Render Model, i.e. whether a subtitle document is too complex to render in real time. The one tool that answers "will this caption file actually play on a set-top box". |
| [ebu/ebu-tt-live-toolkit](https://github.com/ebu/ebu-tt-live-toolkit) | BSD-3-Clause | 27 | 2021-12-21 | **Abandoned ~1,797 days (≈5 years).** EBU-TT Live is *the* European live-subtitle contribution spec, and its reference toolkit has not been touched since 2021 — while the EAA made live subtitling a legal duty in 2025. |

Both are BSD-licensed and small. Reviving or reimplementing either is a credible, cheap, highly
visible open-source contribution for Globant, and it sits directly under a compliance budget.

### Audio description: the legal duty with almost no open tooling

The EAA requires audio description where the picture carries information the sound does not; the FCC
requires 50 hours per calendar quarter in prime time or children's programming. Against that duty,
the entire open AD layer is **prototypes** — every repo below is a single-maintainer or research
project, and the largest has 56 stars, against Subtitle Edit's 15,100 in the caption layer.

| Repo | License | Stars | Last push | Honest status |
|---|---|---|---|---|
| [microsoft/ai-audio-descriptions](https://github.com/microsoft/ai-audio-descriptions) | MIT | 56 | 2026-08-31 | AI draft → human editor → TTS render to MP4. README states it is "intended to support audio-description research and practical experimentation", ships **no authentication**, and advises binding to localhost. The most credible starting point, and still not a product. |
| [asadullah48/accessai](https://github.com/asadullah48/accessai) | Apache-2.0 | — | 2026-09-06 | The only one aimed at **live** AD: multi-agent, fits description into dialogue gaps, scores against WCAG 2.2 AAA / Section 508 / ADA Title III. Apache-2.0 confirmed from the LICENSE file, not the README. |
| [jdmiller/audio-description-generator](https://github.com/jdmiller/audio-description-generator) | MIT | — | 2026-10-19 | Drafts WebVTT AD with a **local** vision model (no cloud dependency) targeting WCAG SC 1.2.5. Explicitly does not do extended AD. |
| [fhswf/descraibe](https://github.com/fhswf/descraibe) | MIT | 0 | 2026-10-27 | VAD → Whisper → scene extraction → LLM description, as a Flask app. German university (FH Südwestfalen) — EMEA-origin research. Requires an external LLM API key. |
| [arnabdotorg/open-vtt](https://github.com/arnabdotorg/open-vtt) | **AGPL-3.0** | — | 2026-10-16 | Extended AD (WCAG 1.2.7) via ffmpeg + Whisper + a hosted LLM. Authors call it a feasibility path, not gold-standard output. AGPL-3.0 → network copyleft. |
| [Double-FW/Audio-Descriptions](https://github.com/Double-FW/Audio-Descriptions) | MIT | — | 2026-11-20 | Editorial rules and review frameworks for AD, aimed at both human editors and AI agents. **This is a documents repo, not code** — valuable as the style guide an AD agent is prompted with. |

**This is the clearest build opportunity in the media KB.** The duty is statutory, the deadlines are
public, the caption half is solved by MIT tooling, and the AD half has no incumbent — open or
commercial — with any real adoption.

## The conformance & preservation plane has no agent layer — measured 2026-11-22 (pass 4)

Pass 4 went looking for agents over broadcast QC, loudness compliance and archive preservation.
**There are none.** Not "few", not "immature" — two of the four primary queries return literal zero.
This is written down as a measurement because an informed gap is information and silence is not.

| GitHub search query | Total results | Verdict |
|---|---|---|
| `broadcast QC agent` | **0** | Nothing exists, under any license. |
| `file-based quality control video stars:>=20` | **0** | Nothing exists above the noise floor. |
| `media preservation agent` | 1 | A single repo with **1 star**. Not a finding. |
| `archive metadata agent stars:>=20` | 2 | **Both are keyword collisions** — `jettbrains/-L-` (GPL-3.0, 174★) and `CNTRUN/Termux-command` (120★) have nothing to do with archives. |
| `loudness normalization stars:>=50` | 2 | Both are TTS/voice audio tools, not broadcast loudness compliance. |
| `mediainfo mcp` | 2 | Top results have **0 and 2 stars**. The MCP layer over technical metadata does not exist yet. |
| `loudness agent` | 287 | **Contaminated, not populated** — top hits are `kajisho5/ffmpeg-skill` (MIT, 9637★) and generic assistants. See the contamination note below. |

### The fourth consecutive confirmation of this KB's structural law

This is now measured in four separate planes of this KB — provenance, monetization, accessibility and
conformance — and the law holds every time:

> **Permissive open source follows the file format, not the judgment.**

The conformance plane is the sharpest case yet, because the two halves sit side by side:

- **The format layer is mature, permissive and actively maintained.** `MediaInfo` (BSD-2-Clause,
  2075★), `MediaInfoLib` (BSD-2-Clause, 806★, pushed the day of this pass), `libebur128` (MIT, 498★),
  `pyloudnorm` (MIT, 796★), `fido` (Apache-2.0), `bagit-python` (public domain). Six permissive
  implementations of *measurement and identification*.
- **The judgment layer is empty.** "Is this file fit to air?" and "does this archive transfer meet
  the preservation target?" are decisions, and **zero** permissive agents make them.

The commercial reading is the same one healthcare's prior-authorization finding produced, and it is
the reason this plane is worth a proposal: the expensive, regulated, auditable *decision* has no open
floor, while every input it needs is free and permissively licensed. That is where proprietary IP
belongs.

### Contamination warning — `loudness agent` returns 287 results and none of them qualify

`kajisho5/ffmpeg-skill` (MIT, 9637★ / 859f) is real, popular and genuinely useful — and it is an
**agent skill pack for driving FFmpeg**, not loudness or QC tooling. Retail's pass recorded the same
hazard with Claude-Code marketing skill packs dominating `ecommerce mcp`, and noted that media
shipped eight of them as headline agents before catching it. Not repeating that here: `ffmpeg-skill`
is **excluded from this KB's agent tables deliberately**, and recorded here so a later pass does not
"discover" it.

### What stands in for an agent layer today

Nothing in this KB's agent tiers covers this plane. The honest answer for a client engagement is that
the agent is **the thing Globant builds**, assembled from the permissive parts catalogued in
`repos/foundations.md` and wired per `compose/patterns.md` P13 (delivery QC gate) and P14
(archive-to-revenue). There is no base to adopt and no incumbent to displace.

## The identification & rights-reservation plane has no agent layer — measured 2026-11-22 (pass 5)

Pass 5 went looking for agents over content identification, royalty attribution and AI-training
rights. **There are none** — and this plane produced the starkest zero yet recorded in this KB:
a query whose entire first page holds **no stars at all**.

| GitHub search query | Total results | Verdict |
|---|---|---|
| `music royalty accounting` | 14 | ⛔ **The top six results hold 0, 0, 0, 0, 0 and 0 stars**, and four of the six carry **no licence**. An empty field — starker than healthcare's `medical necessity` (six repos, 3 stars between them). |
| `pay-per-crawl` | 33 | Top six hold **5, 2, 2, 0, 0, 0** stars. The AI-content *settlement* layer does not exist. |
| `rights management media stars:>=50` | 5 | **Four of the five are keyword collisions** (a DRM-bypass toolkit, a reference list, an unrelated repo). The one real hit is `awslabs/speke-reference-server` — a *key-exchange* server, not rights management. |
| `eidr` | 160 | ⛔ **Zero relevant** — all false friends (national eID readers, an epidemiology tagger). No open EIDR client exists. |
| `isan` | 1,942 | ⛔ **Zero relevant** — all NLP libraries. No open ISAN tooling exists. |
| `cwr common works registration` | 8 | Two real implementations, last pushed **2015** and **2018**. The rights-registration format's open layer is dead. |
| `rslstandard` | 0 | The org is findable only as `org:rslstandard`. The standard has **one** repo, and it is unlicensed. |

### The fifth consecutive confirmation of this KB's structural law — and a sharper statement of it

Five planes now — provenance, monetization, accessibility, conformance/preservation, and
identification/rights — and the law has not broken once:

> **Permissive open source follows the file format, not the judgment.**

This plane lets the law be stated more precisely, because here the two halves are *the same subject
matter* split by function:

- **Declaring** a rights reservation is a format problem. It is solved, permissive and maintained
  **daily**: `ai.robots.txt` (MIT, 4,265★) was pushed on the day of this pass; `tdm-reservation-protocol`
  carries a fork-to-star ratio of 1.2.
- **Honouring** a reservation is a judgment problem. `Spawning-Inc/datadiligence` (MIT, 41★) is the
  only library for it and has been **dormant since October 2024**.
- **Settling** the resulting obligation — who owes whom, for which use — is pure judgment, and it is
  a **measured zero** in both `pay-per-crawl` and `music royalty accounting`.

So: **publishers are tooled to say no; nobody maintains the code that listens; and nothing at all
computes what is owed.** That is a three-step gradient from permissive-and-active to literally empty,
inside one plane, measured in a single pass. The commercial reading is this KB's standing one — the
expensive, auditable *decision* has no open floor while every input it needs is free — and the
prediction it licenses is in `compose/patterns.md` P15.

### The content-licence law reappears, and it is the real constraint in this plane

Healthcare's pass found that *the licence of the code is not the licence of the content* (an open
format can carry a proprietary code set, and the obligation travels with the content). **Media's
identifier layer is the same trap in a different costume**, and it explains every zero above:

| Identifier | What it identifies | Who controls it | Open implementation? |
|---|---|---|---|
| **ISRC** | A sound recording | IFPI via **decentralised national agencies** | None — allocation, not computation |
| **ISWC** | A musical work (composition) | **CISAC** | None |
| **ISAN** | An audiovisual work | ISAN-IA (ISO 15706) | ⛔ None — measured, 1,942 false hits |
| **EIDR** | An audiovisual asset, commercially | EIDR Association (membership) | ⛔ None — measured, 160 false hits |
| **CWR** | A works *registration* message | CISAC societies | Two, both dead since 2015/2018 |
| **DDEX ERN** | A release *delivery* message | DDEX (licence to implement; **terms unverified, see below**) | ✅ `miqwit/dedex`, MIT, live |
| **ISCC** | Any digital asset, by content | **ISO 24138:2024 — open** | ✅ `iscc-core`, Apache-2.0 |

Read the last two rows against the first five. **The only identifiers with usable open
implementations are the two that are not gated by a membership registry** — and of those, the only
one that is genuinely open end to end (ISCC) has a 26-star reference implementation, i.e. no installed
base. That is not a market oversight. It is the licence structure of the industry showing through the
code.

**What this means for a proposal, stated so it cannot be over-promised:** an identification build for
a music or audiovisual client is **an integration with registries the client already pays for**, plus
an internal content-derived join key (ISCC, or a fingerprint) that Globant builds and the client
owns. What must never be promised is a "fully open" identification stack — the same prohibition
healthcare's pass wrote down for CPT.

⚠️ **Unverified in this pass:** `new.ddex.net` does not resolve from this session, so **DDEX's
implementer-licence terms and fees were not confirmed.** Treat them as *unresearched, not free*.

### Contamination warning — three queries in this plane are traps

- **`eidr` and `isan` are the worst false-friend queries met so far in this KB**: 160 and 1,942
  results respectively, **none relevant**. A careless pass would have written an "EIDR client" row
  from `vigorlee/eidra-agent` (MIT, 89★ — an unrelated agent) or an "ISAN" row from `isanlp`. Both
  would have compiled into this KB as fictional entities.
- **`rights management media` returns a DRM-circumvention toolkit** in its top five. Do not carry it;
  do not cite it.
- **The generic query `top open source AI agents media 2026 github MIT` returned no media-specific
  agent at all** — only general-purpose harnesses (OpenHands, MetaGPT, browser-use, CrewAI and the
  like). Recorded because it is now the **sixth** such measurement across this KB's industries: there
  is still **no boom in permissively licensed vertical media agents.**

### What stands in for an agent layer today

Nothing in this KB's agent tiers covers this plane, and no base exists to adopt. The assembly is
Globant's: `chromaprint`/`pyacoustid` or `dejavu` for audio identity, `iscc-sdk` for a standards-backed
content code, `beets` (MIT) as the catalogue spine that already joins the two, `dedex` for DDEX
ingest, and `ai.robots.txt` + TDMRep + RSL for the reservation surface. Wiring in
`compose/patterns.md` **P15** (rights-reservation gate) and **P16** (identification → attribution).

## The production & post-production plane — measured 2026-11-25 (pass 6), and it is the first plane with a real agent layer

> **Read this section before the five above it.** Passes 2–5 each ended in the same sentence: the
> plane has no agent layer. This one does — and the result is *more* useful than another zero,
> because the agent layer here is not missing, it is **misallocated**, and the misallocation is
> measurable to the star.

The plane: *how a shot is built, versioned, reviewed and rendered* — the upstream of everything else
in this KB. Before this pass, `usd`, `materialx`, `opencue`, `openvdb`, `virtual production`,
`render farm`, `animation`, `color grading`, `motion capture` and `opentrackio` appeared **nowhere in
this KB** (grep, 2026-11-25, all 8 files). That is the second-largest vocabulary hole found in any
pass, after `fingerprint`.

### The gradient — the finding of this pass, and the most actionable one in the file

Every row verified 2026-11-25 by `git ls-remote` (existence) plus one `search/repositories` call
(stars / forks / `pushed_at` / SPDX), so the two can always be cross-checked.

| Layer the bridge targets | Best open agent bridge | Licence | Stars | Last push |
|---|---|---|---|---|
| **Blender** — free DCC, mass individual user base | [ahujasid/mcp-for-blender](https://github.com/ahujasid/mcp-for-blender) | MIT | **35,788★** / 3,298f | 2026-11-18 |
| **Houdini** — paid licence, studio tool | [healkeiser/fxhoudinimcp](https://github.com/healkeiser/fxhoudinimcp) | MIT | 437★ / 55f | 2026-11-20 |
| **Maya** — paid licence, studio tool | [PatrickPalmer/MayaMCP](https://github.com/PatrickPalmer/MayaMCP) | MIT | 124★ / 36f | 2025-05-12 (dormant) |
| **OpenUSD** — studio *interchange* | [dcc-mcp/dcc-mcp-openusd](https://github.com/dcc-mcp/dcc-mcp-openusd) | MIT | **2★** / 1f | 2026-11-24 |
| **OpenAssetIO** — studio *asset resolution* | [OpenAssetIO/openassetio-mcp](https://github.com/OpenAssetIO/openassetio-mcp) | Apache-2.0 | **1★** / 1f | 2026-05-18 |

Read the column of stars downward: **35,788 → 437 → 124 → 2 → 1.** Five orders of magnitude, and the
ordering is not by substrate health, not by obligation, and not by market size. It is by **how many
individual practitioners can install the thing on a laptop tonight.**

**The law this KB has been writing, restated for six planes:** the open agent layer tracks the size
of the *individual practitioner population*, not the regulatory obligation (planes 3–5) and not the
substrate's health (this plane). Where the user is a person, the bridge is enormous. Where the user
is a pipeline, the bridge is a rounding error — **even when the pipeline underneath it is the
healthiest, most permissive, best-funded substrate in this entire knowledge base.**

**Why that is a sell, not a lament.** The 35,788★ bridge is a solved, crowded, undifferentiated
problem and it carries an explicit disclaimer in its own description: *"Community plugin to control
Blender 3D with any LLM of your choice. **Not affiliated with the official Blender Foundation.**"*
The 1★ and 2★ bridges sit on Apache-2.0 / BSD-3 foundations that every major studio already runs, and
have **no commercial alternative a client could buy instead**. That is the whole opportunity of this
plane in two sentences.

### Tier 1 — permissive, active, safe to build on

| Agent / bridge | Licence (verified) | Stars / forks | Last push | Why it is here |
|---|---|---|---|---|
| [ahujasid/mcp-for-blender](https://github.com/ahujasid/mcp-for-blender) | MIT | 35,788★ / 3,298f | 2026-11-18 | The reference implementation of DCC-over-MCP, and the proof the pattern works. Community project, **not** Blender Foundation. |
| [healkeiser/fxhoudinimcp](https://github.com/healkeiser/fxhoudinimcp) | MIT | 437★ / 55f | 2026-11-20 | The most complete Houdini MCP server. The highest-value *studio* bridge that is actually maintained. |
| [binary-core-llc/bowerbot](https://github.com/binary-core-llc/bowerbot) | Apache-2.0 | 39★ / 3f | **2026-11-25** | Agent that assembles production-correct OpenUSD scenes from natural language — assets, materials, lighting, validation. Pushed the day of this pass. Small company, early, but the right shape. |
| [dcc-mcp/dcc-mcp-core](https://github.com/dcc-mcp/dcc-mcp-core) | MIT | 76★ / 9f | 2026-11-25 | The multi-DCC abstraction the one-off bridges lack. Siblings: `dcc-mcp-maya` (79★), `dcc-mcp-openusd` (2★). |
| [sideshowroberto/vfx-agent-toolkit](https://github.com/sideshowroberto/vfx-agent-toolkit) | MIT | 21★ / 4f | 2026-11-09 | Small, honest, VFX-specific agent tooling. Owner-sized. |

### Tier 2 — real, but staleness or scope constrains client work

| Agent / bridge | Licence | Stars / forks | Last push | Constraint |
|---|---|---|---|---|
| [capoomgit/houdini-mcp](https://github.com/capoomgit/houdini-mcp) | MIT | 312★ / 41f | 2026-06-11 | Second Houdini bridge; ~5 months quiet. Prefer `fxhoudinimcp`. |
| [PatrickPalmer/MayaMCP](https://github.com/PatrickPalmer/MayaMCP) | MIT | 124★ / 36f | 2025-05-12 | **Dormant 18 months.** Maya is the most-installed studio DCC and its best-known bridge is stale. |
| [damionrashford/media-os](https://github.com/damionrashford/media-os) | MIT | 26★ / 6f | 2026-05-31 | One of very few projects joining agents to OpenTimelineIO. Dormant 6 months. |
| [OpenAssetIO/openassetio-mcp](https://github.com/OpenAssetIO/openassetio-mcp) | Apache-2.0 | **1★** / 1f | 2026-05-18 | **The highest-leverage repo in this section and the least-starred.** See Pattern 17. |
| [OpenAssetIO/OpenAssetIO-ComfyUI](https://github.com/OpenAssetIO/OpenAssetIO-ComfyUI) | Apache-2.0 | 2★ / 2f | 2025-09-30 | The bridge from generative tooling to studio asset resolution. **Two stars, dormant 14 months** — the exact seam between this KB's generative plane and its production plane, and nobody is holding it. |

### ⚠️ Contamination warnings — two of the worst queries in this KB

Both measured 2026-11-25. A careless pass would have written fictional rows from either.

| Query | Total | What the top of the page actually is |
|---|---|---|
| `virtual production` | **1,291** | **Near-total false friend.** Top hits include `knadh/stuffbin` (205★, a *Go static-asset embedder* — matches "production"), `jettbrains/-L-` (176★, a dumped W3C report), `rbowler/spinhawk` (113★, a mainframe emulator describing itself as "production-quality"), and a 121★ `motionbuilder-setup-guide` with no licence. The one defensible hit is `otdavies/UnityChromakey` (260★, MIT, 2025-02-28). |
| `color grading open source` | 42 | **The most absurd contamination found in any industry.** Four of the top six results are the **Bee Movie script** meme repos (228★, 98★, 53★, 40★ — all opening *"According to all known laws of aviation…"*). The only genuine hit is `hety0211/lumen-raw` (304★, MIT, RAW photo editor, 2026-11-21) and it is photography, not grading. |

**Rule, repeated because it keeps paying:** read the results, never the total. `virtual production`
returning 1,291 hits looks like abundance and is a vocabulary that GitHub's index simply does not
carry — the real vocabulary is the vendor and standard names (`opentrackio`, `camdkit`), which return
8 and 1 results respectively and are both real.

### Informed gaps from this pass — searched, and genuinely not found

- **Blender's own render-farm manager, Flamenco, is not on GitHub.** `flamenco blender render`
  returns 16 results, all third-party and ≤5★. Flamenco is developed at `projects.blender.org`, which
  **does not resolve from this session** (egress policy). Treat Flamenco as *real but unverified
  here* — not as absent, and not as GitHub-hosted.
- **No open agent layer for review-and-approval.** `OpenRV` (797★) and `xstudio` (782★) are both
  permissive, both active, and neither has any agent bridge found. Notes, versions and approvals are
  the most agent-shaped workflow in post, and the hook does not exist.
- **No open agent bridge for Nuke** worth a row: best found is `dughogan/nuke_mcp` (40★, **no licence
  file**, 2025-11-03). Compositing is the largest seat count in VFX.

*Verification method for this pass: `git ls-remote` for existence (**35/35 resolved**); stars, forks
and `pushed_at` from `search/repositories`; licences read from the actual file where the API returned
`NOASSERTION`. `gh api repos/{owner}/{repo}` is **not** available in this session (repo-scoped token,
returns "GitHub access to this repository is not enabled") — use the search endpoint, which is.*

## The audience & measurement plane — measured 2026-11-25 (pass 7), and the agent layer is *inverted*

The seventh plane: **who is watching, what to show them next, and how reach is counted and sold.**
Found the same way as pass 6 — ~95 candidate terms grepped against all eight files before any web
search. `panel`, `Nielsen`, `ratings`, `clean room`, `identity resolution`, `collaborative filtering`,
`EPG`, `podcast`, `esports`, `A/B`, `audience measurement` and `recommender` all scored **zero files**,
while pass 2 had already covered *ad* measurement — auction, SSAI, Druid/Pinot — which is the **supply**
side. This plane is the **demand** side, and it was the largest remaining vocabulary gap in this KB.

**It also closes a defect in this KB, not just a gap.** `compose/patterns.md` Pattern 10 has pointed at
`[agents/top.md recommender work]` since 2026-11-22. No recommender repo has ever existed anywhere in
these eight files — the reference was **dangling for three days across four passes**. The stack it was
pointing at is now in `repos/foundations.md`, and Pattern 10's arrow is corrected to point there.

### The agent-layer gradient — and it runs *against* the substrate's openness

Pass 6 found that the open agent layer tracks **practitioner population** — not regulatory pressure
(passes 3–5) and not the substrate's health. This plane is the first test where openness and
population point in **opposite** directions, and population wins decisively:

| Analytics substrate | Agent bridge | Licence | Stars | Forks | Last push | Substrate is |
|---|---|---|---|---|---|---|
| Google Analytics 4 | [googleanalytics/google-analytics-mcp](https://github.com/googleanalytics/google-analytics-mcp) | Apache-2.0 | **3,866** | 802 | 2026-11-24 | **proprietary, hosted** |
| PostHog (41,121★) | [PostHog/mcp](https://github.com/PostHog/mcp) | MIT | 152 | 27 | 2026-01-19 (**archived**) | open source |
| Matomo (22,056★) | [FGRibreau/mcp-matomo](https://github.com/FGRibreau/mcp-matomo) | MIT | 12 | 2 | 2026-07-27 | open source |
| Generic multi-tool | [embeddedlayers/mcp-analytics](https://github.com/embeddedlayers/mcp-analytics) | MIT | 9 | 1 | 2026-10-26 | mixed |
| Matomo (22,056★) | [kitconcept/matomo-mcp](https://github.com/kitconcept/matomo-mcp) | MIT | 1 | 0 | 2025-12-15 | open source |

The open substrate is **~63,000 stars of analytics software served by 22 stars of agent bridge**, one
of which is archived. The closed, hosted substrate has 3,866 stars and 802 forks. The mechanism is the
one pass 6 named: a bridge is written by whoever has the most users to serve, and GA4's practitioner
population is orders of magnitude larger than Matomo's. **Licence and openness do not enter into it.**

**Procurement consequence, and it is immediate:** the GA4 bridge is Apache-2.0, 802 forks and was
pushed the day before this measurement — a real dependency Globant can take. The open-source analytics
agents are not: PostHog's own MCP repo is **archived** (the code moved into the monorepo at
`services/mcp`, confirmed by a 200 on its README) and the Matomo bridges are 12 and 1 star. If a client
runs Matomo or PostHog and wants an agentic analyst, **that bridge is a build, not an adoption** — and
it is a small, well-specified build, which makes it one of the better-shaped openings in this KB.

### The recommender layer has no agent bridge at all — measured, not assumed

`recommender MCP` and `personalization MCP` return no project with meaningful adoption. The closest
artefact is [JoshuaOliphant/vault-recommender](https://github.com/JoshuaOliphant/vault-recommender)
(**2 stars, no LICENSE file at any probed name, 2026-11-16**) — a personal Obsidian note recommender,
not media infrastructure. **Do not cite it to a client.** Meanwhile the recommender *libraries* below
it are among the healthiest in this KB (22,012★ MIT, pushed this month). Sixth consecutive plane in
which the substrate is strong and the agent layer is absent — but for a new and more tractable reason:
not regulatory risk and not a closed content licence, simply that **a recommender is called by a
service, not by a person**, so nobody has needed a conversational bridge to one yet.

### ⛔ The licence finding of this pass — a fifth distinct way a licence hides, and the worst for tooling

The only code published under an *audience-measurement* banner by an actual currency vendor is
Comscore's own client SDK set. Its `LICENSE` file is **145 bytes of prose that points at a PDF**:

> `Please refer to the license agreement document on the following URL`
> `https://github.com/comScore/ComScore-Android/blob/master/LicenseAgreement.pdf`

The real terms are `LicenseAgreement.pdf`, **58,057 bytes**, verified present and readable. No SPDX
field, no SBOM scan, no GitHub API call and no text-based licence probe — including this KB's own,
which pass 5 already had to extend twice — can read it. GitHub reports `NOASSERTION` for all three
repos. **Fifth category, after a non-standard filename, a licence owned by the compile, an HTML file /
packaging classifier, and a modified Apache (OpenUSD).**

And the content is worse than the format. Read, the PDF is **not a software licence in the OSI sense at
all** — it is a *data-collection agreement*, granting Comscore the right to collect viewing data
through the SDK "for inclusion in syndicated and/or custom products and services … as well as use in
its work with certain industry associations and market currency initiatives or joint industry
committees." The code is public; what you accept by using it is that **your audience flows into
someone else's currency.** That is this plane's law in a single artefact, and it is the exact inverse
of pass 5's rights-reservation plane, whose entire purpose was machine-readable terms.

| Repo | Licence as published | Stars | Forks | Last push |
|---|---|---|---|---|
| [comScore/ComScore-Android](https://github.com/comScore/ComScore-Android) | `NOASSERTION` — stub → `LicenseAgreement.pdf` (58,057 B), a data-collection agreement | 16 | 3 | 2026-11-25 |
| [comScore/ComScore-iOS-watchOS-tvOS](https://github.com/comScore/ComScore-iOS-watchOS-tvOS) | `NOASSERTION` — same stub → PDF pattern | 15 | 18 | 2026-11-25 |
| [comScore/Comscore-Swift-Package-Manager](https://github.com/comScore/Comscore-Swift-Package-Manager) | `NOASSERTION` — SPM distribution of the above | 6 | 0 | 2026-11-25 |

**Rule for CI, and it generalises past media:** a `LICENSE` file under ~300 bytes is not a licence, it
is a *pointer*. Treat short LICENSE files as unresolved and open what they point at, including binary
documents. All three of these were pushed on measurement day, so this is live, maintained code.

### ⚠️ Contamination — the worst false-friend query measured in any industry

Pass 5 recorded `eidr` (160 results, zero relevant) and `isan` (1,942, zero relevant). This plane beats
both:

- **`data clean room` = 870 results and ZERO relevant.** Every top result is Android **"clean
  architecture"** or a timetable app with a **"clean room overview"** — `CoinTrend/CoinTrend` (274★,
  GPL-3.0), `ibrajix/NewsFly` (124★), `ahmedmolawale/Star-Wars-Characters` (108★). A careless pass
  would have written three plausible-looking rows from this and every one would be a mobile app. The
  only genuine match found anywhere is
  [tiktok-privacy-innovation/PrivacyGo-DataCleanRoom](https://github.com/tiktok-privacy-innovation/PrivacyGo-DataCleanRoom)
  (Apache-2.0, 37★, **archived 2024-10-31**).
- **`audience measurement` = 91 results**, top result by stars is a machine-learning *tutorial*
  (`sayantann11/all-classification-templetes-for-ML`, 304★, no licence, 2024). The only relevant hits
  are Comscore's three SDKs above.
- **`identity resolution advertising` = 4 results**, and the only on-topic one has **0 stars**
  (`htpeter/Identity-Resolution-Using-Neo4J`, no licence, last touched 2021).

Confirms pass 5's two-sided rule again: **read the results, never the total.** 870 is not abundance.

### What stands in for an agent layer today

1. **The GA4 MCP bridge (Apache-2.0, 3,866★)** for clients on Google's stack — adopt, do not build.
2. **A built bridge over PostHog's monorepo `services/mcp` or Matomo's HTTP API** for clients who
   self-host. Small, well-specified, and nobody has done it credibly yet.
3. **No agent for the currency itself.** There is no open client for Nielsen, Comscore or VideoAmp
   data, and `currency measurement TV` returns **one repo with 0 stars** — an API-surface description
   ([api-evangelist/videoamp](https://github.com/api-evangelist/videoamp), no licence, 2026-11-01), not
   an implementation.

### Informed gaps from this pass — stated as gaps

- **No open-source panel-based measurement exists, and this is now a priced fact rather than an
  impression.** See `intel/market.md` North America: the CIMM January 2026 report puts the floor at
  **~$110M/year of operating cost**. The reason is not licensing and not neglect.
- **DDEX-style commercial terms for currency data were not obtainable.** `videoweek.com`,
  `www.barb.co.uk` and `www.fifty5blue.com` **do not resolve from this session** (outside the allowed
  network domains), so the Barb/YouTube ACR dispute and the Kantar Media → Fifty5Blue rebrand are
  recorded from trade-press summaries, **not primary sources**. Treat both as reported, not verified.
- **No measured figure was found for how many media companies self-host a recommender** versus buying
  one. Unresearched, not absent.


## The live & delivery plane — measured 2026-11-26 (pass 8), and the agent layer is a measured near-zero

> The plane: contribution (first mile) → transcode → package/encrypt → origin → CDN/edge → player.
> This is where M&E spends the most money per engineer and where this KB had **eight lines of
> content** before today. All rows verified 2026-11-26: existence by `git ls-remote` (45/45 resolved),
> stars and `pushed_at` from `search/repositories`, licence by reading the LICENSE file wherever the
> API returned `NOASSERTION` or `NONE` — which in this plane was **9 of 45 repos**, the highest
> proportion of any plane in this KB.

### The eighth consecutive confirmation of the structural law — with the gradient now fully inverted

Seven planes have now produced the same result: **the substrate is permissive and healthy, and the
agent layer above it is missing.** This plane confirms it an eighth time, and it is the most extreme
case measured so far, because the substrate here is the *strongest* in the entire KB:

| Layer | Health (verified 2026-11-26) | Agent layer |
|---|---|---|
| Contribution / ingest servers | `ossrs/srs` 29,457★ MIT, `bluenviron/mediamtx` 20,772★ MIT, `pion/webrtc` 16,926★ MIT — all pushed within 24h | none |
| Transcode | `FFmpeg/FFmpeg` 68,197★, pushed 2026-11-25 | none |
| Packaging / origin | `shaka-project/shaka-packager` 2,673★ BSD-3 | none |
| Players | `videojs/video.js` 40,253★, `video-dev/hls.js` 17,066★ — both Apache-2.0 | none |
| **Delivery operations agent** | **the only real-time one is 26★ and last pushed 2024-11-04** | — |

Five queries were run against `search/repositories`, stars-sorted (`ffmpeg agent llm`,
`streaming agent llm video ops`, `video encoding agent ai`, `broadcast ai agent`,
`transcoding llm agent`). `streaming agent llm video ops` returned **literally zero results**. The
others returned general-purpose video *editing* agents, not delivery or operations agents. Nothing
that watches an encoder ladder, reacts to a QoE collapse, re-packs a failing rendition or drives an
origin exists as open source at any star count.

### The four agents that are real in or adjacent to this plane

| Name | Repo | Licence | Stars | Last push | What it actually does |
|---|---|---|---|---|---|
| OpenMontage | https://github.com/OpenMontageInc/OpenMontage | **AGPL-3.0** | 83,342 | 2026-11-16 | Agentic video production/assembly. The largest media agent repo found in any pass of this KB. |
| Hypit | https://github.com/hypit-ai/hypit | **modified Apache-2.0** (source-available) | 31,513 | 2026-11-25 | Agentic render/generation backend driving FFmpeg-class tooling; produces run reports and manifests. |
| vox-director | https://github.com/Alisa0808/vox-director | MIT | 3,187 | 2026-10-05 | Multi-step voice/narration direction agent. |
| ai-rtc-agent | https://github.com/yondonfu/ai-rtc-agent | MIT | 26 | **2024-11-04** | Real-time AI over a WebRTC transport. **The only genuine real-time agent in this plane, and it is dormant — two years stale.** |

### ⛔ The licence finding of this pass, part 1: a 32,000-star agent is not the licence the directories report

An AI-tooling aggregator promoted OpenMontage as **"32.3K stars, MIT License"**. Both halves are
wrong, and verification took one call:

- Stars: **83,342**, not 32.3K.
- Licence: **AGPL-3.0**, not MIT.

MIT and AGPL-3.0 are the two ends of this KB's risk axis. AGPL-3.0 on a video-production agent means
that if a client reaches it over a network, the client's own modifications are in scope. This is the
third time in this KB that an aggregator or directory has misreported a licence in the **permissive**
direction, and the direction of the error is never random: it always makes the repo look more usable
than it is. **Never take a licence from a listicle. Read the file.**

`hypit-ai/hypit` is the same shape in a subtler form: GitHub reports `NOASSERTION` because it is a
*modified* Apache-2.0. Read in full, the modification is commercially precise, and for a consultancy
it is unusually favourable — so the detail is worth stating rather than avoiding:

- **Permitted without a paid licence:** running it on your own infrastructure, for your own
  organisation's commercial work, **and explicitly "work performed for your clients"**, plus
  single-tenant deployments operated by and for one organisation.
- **Requires a paid licence:** operating a **multi-tenant** environment (two or more outside parties
  holding separate workspaces, *fee or no fee*), and commercial redistribution — selling or bundling
  it into a product supplied to third parties.
- Also: the name, logo and copyright in the CLI and in **generated run reports and manifests** may
  not be removed where a user sees them.
- Output is yours: the producer claims no rights in generated artefacts.

So Hypit is usable in Globant client delivery, and **not** usable as the engine of a Globant-hosted
multi-tenant product. That distinction decides which of the two it can be, and it is invisible from
the repo badge.

### ⚠️ Contamination — and a method correction that turns a known flaw into a diagnostic

Earlier cycles of this file recorded that `search/repositories` "returns false 422s on live repos"
and treated it as oracle flakiness. **That diagnosis was incomplete. Both 422s in this pass had a
single cause: the repository had been renamed**, so the old path still resolves over git (GitHub
serves a redirect) while search only indexes the canonical name.

| Path every guide still cites | `ls-remote` | `search/repositories` | Canonical name today |
|---|---|---|---|
| `AirenSoft/OvenMediaEngine` | OK | **422** | **`OvenMediaLabs/OvenMediaEngine`** (AGPL-3.0, 3,309★) |
| `kixelated/moq-rs` | OK | **422** | **`moq-dev/moq`** (Apache-2.0, 1,642★, pushed 2026-11-26) |

**The rule, stated for the next pass:** `ls-remote` OK + search 422 does not mean the oracle is
broken. It means *rename* — go find the new owner with a name search before writing either path.
A dead-looking project may simply have moved, and a KB that records the old path sends an engagement
to a repo nobody is updating.

### Informed gaps from this pass — searched, and genuinely not found

- **No open-source delivery-operations agent**, at any star count, under any of five query shapes.
- **No agent anywhere near the DRM step** — and §"the key is the gate" in `repos/foundations.md`
  explains why that one is structural rather than neglect.
- **No MPEG-H Audio encoder**, open or otherwise: `Fraunhofer-IIS/mpeghdec` is a **decoder**, and
  Brazil's DTV+ mandates MPEG-H support in every receiver (see `intel/market.md` → LATAM).
- **`libatsc3` has no canonical home.** `libatsc3/libatsc3` and `Sony/libatsc3` both fail
  `ls-remote`; what exists are forks (`junhuac/libatsc3` 13★ 2019, `kansonkong/libatsc3` 12★ 2023),
  all MIT, all stale. The US transition standard has no maintained open implementation.

## Corrections to earlier cycles of this file

The eight rows this file carried until today were **generic Claude-Code marketing/SEO skill packs, not
media-industry agents**: `coreyhaines31/marketingskills` (61,759★ MIT), `AgriciDaniel/claude-seo`
(31,209★ MIT), `yaojingang/GEOFlow`, `aaron-he-zhu/aaron-marketing-skills` (3,181★ Apache-2.0),
`AgriciDaniel/claude-blog` (2,829★ MIT), `ReScienceLab/opc-skills` (1,920★ Apache-2.0),
`kostja94/marketing-skills` (1,125★ MIT), `Bhanunamikaze/Agentic-SEO-Skill` (1,075★ MIT). All eight
exist and are popular — they are simply content-marketing tooling, which belongs to a marketing KB,
not to Media & Entertainment production. They are kept here only as this correction record.

- **`yaojingang/GEOFlow` is AGPL-3.0, not Apache-2.0** as this file previously stated (4,171★,
  pushed 2026-11-13). That misread would have put a client's codebase under network copyleft.
- Renames caught this cycle, where the old slug still redirects and so looks alive:
  `THUDM/CogVideo`→`zai-org/CogVideo`, `genmoai/models`→`genmoai/mochi`,
  `krillinai/KrillinAI`→`krillinai/OpenCreator`, `calesthio/OpenMontage`→`OpenMontageInc/OpenMontage`.
  Each confirmed by matching HEAD SHAs, not by assumption.
- Earlier cycles recorded KrillinAI as **MIT**; it is **Apache-2.0**.

*Verification method: `git ls-remote` for existence (the only reliable oracle — `search/repositories`
returns false 422s on live repos, and `curl -sI github.com` is blind through this proxy); stars and
`pushed_at` from the same `search/repositories` call so the two can always be cross-checked.*

---

## The trust & safety plane — measured 2026-11-26 (pass 9), and the first plane whose licence breaks in the **model** layer

Scope: the pipeline that decides whether a piece of user or licensed content may be published, shown
to a minor, monetised or reported to an authority. Hash matching → classification → rules →
review queue → enforcement → statutory report. **62 repos verified this pass, 62/62 resolve by
`git ls-remote`.**

This plane did not exist in this KB before today. The vocabulary probe that found it is recorded in
`agents/trending.md`: `trust and safety`, `age verification`, `age assurance`, `perceptual hash`,
`hash matching`, `DSA`, `Online Safety`, `brand safety`, `CSAM`, `content classification` and
`parental` returned **zero occurrences across all eight files**, while the regulatory prose in
`intel/market.md` had been describing the obligations for three passes without naming a single tool
that discharges them.

### The agent layer, measured — and it is the ninth consecutive near-zero

| Agent | Repo | Licence | ★ / forks | Last push | What it actually is |
|---|---|---|---|---|---|
| **ROOST Pigeon** | [roostorg/pigeon](https://github.com/roostorg/pigeon) | **none in repo** | 2★ / 1f | 2026-11-21 | "Prototyping open-weight safety models as Coop signals and Osprey rule functions." **This is the entire agent layer of the plane** — the bridge from a safety model to a rules engine — and it is a 2-star prototype with no licence file, from the one organisation with the most credibility in the field. |

That is not a thin agent layer. That is **the** agent layer. The substrate underneath it is healthy,
permissive and pushed this week (see `repos/foundations.md`), and the thing that would turn a model
into an enforcement decision is a prototype two people have starred.

### The finding of this pass: the licence constraint has moved from the code to the weights

Every earlier pass in this KB found the restrictive instrument in a **content** licence (CPT codes in
healthcare, MedDRA, ISRC/ISWC registry membership, MDN/Nielsen panels) or in a **code** licence
(AGPL at the platform tier, GPL at the checker). This plane is the first where the code is almost
uniformly permissive and **the restriction sits on the model weights** — and it sits there in
proportion to how valuable the model is.

The cleanest proof is a single company publishing a single toolkit under two licences:

| Artifact | Repo | Licence | ★ | What it is | Usable in client work? |
|---|---|---|---|---|---|
| Roblox **Sentinel** | [Roblox/Sentinel](https://github.com/Roblox/Sentinel) | **Apache-2.0** | 120★ | Python library for real-time safety inference — the *plumbing* | **Yes** |
| Roblox **RoGuard 1.0** | [Roblox/RobloxGuard-1.0](https://github.com/Roblox/RobloxGuard-1.0) | **RAIL Research-Only** (17,642 B licence file: "ROGUARD RESEARCH-ONLY RAIL-MS LICENSE", licensed artifacts = "RoGuard Model Weights and related inference code") | 68★ | The state-of-the-art safety LLM trained on the abuse that actually happens on Roblox — the *judgment* | **No** |
| Roblox **voice safety classifier** | [Roblox/voice-safety-classifier](https://github.com/Roblox/voice-safety-classifier) | **CC-BY-SA-3.0** (22,240 B) — a *content* licence, with share-alike, applied to model weights | 105★ | Real-time voice abuse detection | Only with share-alike accepted |

Same company. Same toolkit. Same month. The library is Apache-2.0; the model that makes the library
worth running is research-only. **Ask for the weights' licence separately from the repo's licence, on
every safety model, every time** — and expect the answer to get worse the better the model is.

The same split holds across the field: Meta's **Llama Guard** ships under the
[Llama 3.2 Community Licence](https://github.com/meta-llama/PurpleLlama) (4,495★, 7,669 B licence
file — acceptable-use restrictions plus an MAU threshold, **not** OSI-approved), and the leading
deepfake-detection benchmark, [SCLBD/DeepfakeBench](https://github.com/SCLBD/DeepfakeBench)
(1,145★), is **CC-BY-NC-4.0** — explicitly *"NonCommercial means not primarily intended for or
directed towards commercial advantage or monetary compensation"*, verified in the 43,107 B licence
file. A client engagement is commercial advantage. That benchmark cannot ship.

### Tier 1 — permissive, active, and safe to build on

| Agent / model | Repo | Licence | ★ / forks | Last push | Why it qualifies |
|---|---|---|---|---|---|
| **IBM Granite Guardian** | [ibm-granite/granite-guardian](https://github.com/ibm-granite/granite-guardian) | Apache-2.0 | 192★ / 20f | 2026-10-16 | Risk detection in prompts *and* responses, Apache-2.0 on the weights as well as the code. The cleanest licence in the judgment layer. |
| **OpenAI gpt-oss-safeguard** | [openai/gpt-oss-safeguard](https://github.com/openai/gpt-oss-safeguard) | Apache-2.0 | 67★ / 14f | 2026-01-14 | Open-weight safety *reasoning* model: you supply the policy, it reasons against it. The only artifact in this plane that takes a client's own policy document as input. Low stars, high strategic value. |
| **Detoxify** | [unitaryai/detoxify](https://github.com/unitaryai/detoxify) | Apache-2.0 | 1,320★ / 149f | 2026-11-11 | Toxicity across all three Jigsaw challenges. The most-installed permissive text classifier here, and still maintained after five years. |
| **OpenGuardrails** | [openguardrails/openguardrails](https://github.com/openguardrails/openguardrails) | Apache-2.0 | 373★ / 63f | 2026-11-18 | Local rules + sandbox + firewall for agents. Active, and the newest credible entrant. |
| **Guardrails AI** | [guardrails-ai/guardrails](https://github.com/guardrails-ai/guardrails) | Apache-2.0 | 7,641★ / 751f | 2026-11-24 | The validator-framework incumbent. |
| **NeMo Guardrails** | [NVIDIA-NeMo/Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) | **Apache-2.0** — file-verified, see the licence finding below | 7,581★ / 912f | 2026-11-25 | Programmable safety rails. **Note the repo path**: it moved from `NVIDIA/NeMo-Guardrails`. |
| **Roblox Sentinel** | [Roblox/Sentinel](https://github.com/Roblox/Sentinel) | Apache-2.0 | 120★ / 27f | 2026-08-18 | Real-time safety inference library from a platform that runs it at scale. |

### Tier 2 — real, but the licence or the staleness constrains client work

| Agent / model | Repo | Licence | ★ | Last push | The constraint |
|---|---|---|---|---|---|
| Llama Guard / Purple Llama | [meta-llama/PurpleLlama](https://github.com/meta-llama/PurpleLlama) | Llama 3.2 Community | 4,495★ | 2026-11-20 | Not OSI-approved; acceptable-use terms + MAU threshold. Legal review before any client deployment. |
| NudeNet | [notAI-tech/NudeNet](https://github.com/notAI-tech/NudeNet) | **AGPL-3.0** | 2,510★ | 2026-06-09 | Active and good, but AGPL over a network service is the one copyleft shape that reaches a SaaS deployment. |
| nsfw-filter | [nsfw-filter/nsfw-filter](https://github.com/nsfw-filter/nsfw-filter) | GPL-3.0 | 1,800★ | 2026-10-18 | Browser extension; GPL-3.0. |
| nsfw_model | [GantMan/nsfw_model](https://github.com/GantMan/nsfw_model) | **MIT with a third-party carve-out** — the 1,243 B `LICENSE.md` opens *"This project contains third-party copyrighted material under different licenses. Except where otherwise explicitly stated, this project is licensed as follows: MIT"* | 2,112★ | 2024-02-26 | Stale by two and a half years, and the carve-out means the SPDX field (`NOASSERTION`) is right to hesitate. |
| Bumble Private Detector | [bumble-tech/private-detector](https://github.com/bumble-tech/private-detector) | Apache-2.0 | 1,366★ | 2023-11-05 | Clean licence, three years stale. |
| Yahoo open_nsfw | [yahoo/open_nsfw](https://github.com/yahoo/open_nsfw) | BSD-2-Clause | 6,018★ | 2018-11-21 | **Archived.** Caffe-era. The most-starred artifact in this plane is also the deadest — read the stars as history, not as a recommendation. |
| LLM Guard | [protectai/llm-guard](https://github.com/protectai/llm-guard) | MIT | 3,223★ | 2026-07-08 | **Archived in 2026.** A 3.2k-star LLM security toolkit went read-only this year; do not start on it. |
| Marble | [checkmarble/marble](https://github.com/checkmarble/marble) | **Elastic-2.0 — source-available, not open source** | 629★ | 2026-11-16 | Real-time fraud/AML decision engine. Good software, wrong licence class for a resold build. |
| localmod | [KOKOSde/localmod](https://github.com/KOKOSde/localmod) | MIT | 116★ | 2026-10-31 | Self-hosted moderation API, fully offline. Young, but MIT and active — worth watching. |
| FaceForensics | [ondyari/FaceForensics](https://github.com/ondyari/FaceForensics) | **code: verbatim MIT text** (1,142 B, unnamed) / **dataset: separate EULA** | 2,807★ | 2022-12-08 | The content law again: the code is permissive, the data that makes it work needs a signed agreement. |
| DFDC winning solution | [selimsef/dfdc_deepfake_challenge](https://github.com/selimsef/dfdc_deepfake_challenge) | MIT | 867★ | 2023-02-11 | Genuinely MIT, genuinely stale, and trained against 2020-era generators. |
| CLIP-based NSFW detector | [LAION-AI/CLIP-based-NSFW-Detector](https://github.com/LAION-AI/CLIP-based-NSFW-Detector) | **NO LICENCE FILE** — probed 11 names on `main` and `master`; `README.md` returns 200 on both, so the names are not the problem | 473★ | 2023-05-30 | No grant means all rights reserved. 473 stars of unusable code. |

### ⚠️ Contamination — two of the worst false-friend queries measured in this KB

- **`age assurance` → 478 results, zero relevant.** Every hit is quality *assurance*, an *agent*
  framework, or French-language insurance (`gestion-assurance`). The real artifact estate for age
  verification — nine repos, see `repos/foundations.md` — is **only** reachable through the
  organisation name `eu-digital-identity-wallet`, never through the plane's own vocabulary. A pass
  that searched the obvious term and wrote "no open age-verification tooling found" would have been
  confidently wrong about a 309-star regulator-published Android app.
- **`csam` → 722 results, one relevant.** The top hits are a Bioconductor genomics summer school
  (`CSAMA`, 92★) and Azure B2C samples (`b2csamples`, 136★). The single relevant result is
  [AsuharietYgvar/AppleNeuralHash2ONNX](https://github.com/AsuharietYgvar/AppleNeuralHash2ONNX)
  (1,532★, Apache-2.0, 2021) — which is a *reverse-engineering* of Apple's abandoned NeuralHash, not
  a detection tool. **The acronym is not the vocabulary.** The working tools are found under "hash
  matching" and are listed in `repos/foundations.md`.

### Informed gaps from this pass — searched, and genuinely not found

- **No open agent that files a statutory report.** US federal law (18 U.S.C. §2258A) obliges
  providers to report to the NCMEC CyberTipline. Exactly one open client exists —
  [ello/ncmec_reporting](https://github.com/ello/ncmec_reporting), 7★, **no licence file**, last
  pushed **2022-03-29** — and it is abandoned and unlicensed. Searched; nothing has replaced it.
- **No open brand-safety classifier.** `brand safety` as a tooling query returns no permissive
  implementation; the GARM taxonomy is a document, and the IAB floor is a PDF. Stated as a gap.
- **No agent layer for age assurance.** The EU estate is apps, libraries and verifiers — there is no
  agent that reads a platform's own age policy and decides a case.
- **No open deepfake detector trained on 2026-era generators.** The three detection repos that exist
  are from 2020–2025 and the usable ones are non-commercial or stale. Measured, not assumed.

## The theatrical & digital-cinema plane — measured 2026-11-26 (pass 10), and it is the emptiest plane in this KB

This KB had, until today, no row for the distribution channel every studio release still starts in.
Nine passes covered streaming, broadcast, live, podcast, archive, production, measurement, delivery
and trust & safety. **The theatrical chain — the DCP that is shipped to a cinema, the key that
unlocks it, and the validator that says it will play — was a literal zero.** The vocabulary probe
that found it is recorded in `agents/trending.md`; the short version is that `digital cinema`,
`asdcplib`, `dcp-o-matic`, `KDM`, `box office`, `theatrical`, `SMPTE ST 429`, `projector` and `TMS`
all returned **zero hits across all eight files**, while the four apparent `DCP` hits were every one
of them **HDCP** (copy protection, from pass 8) and the twenty `cinema` hits were OpenEXR and
Brazilian and Mexican statute prose.

### The agent layer, measured — and this is the tenth consecutive near-zero, by a distance

| Query | Results | Top-6 star sum | What is actually there |
|---|---|---|---|
| `DCP automation agent` | **0** | 0 | Literal zero |
| `theatrical distribution automation` | **0** | 0 | Literal zero |
| `digital cinema LLM` | **0** | 0 | Literal zero |
| `subtitle cinema DCP agent` | **0** | 0 | Literal zero |
| `projection automation cinema` | 1 | 0 | A **Minecraft** cinema mod, 0★ |
| `SMPTE DCP interop` | **0** | 0 | Literal zero |
| `preshow advertising cinema` | **0** | 0 | Literal zero |
| `cinema exhibitor data` | **0** | 0 | Literal zero |
| `movie theater point of sale open source` | **0** | 0 | Literal zero |

**Six literal zeros and three near-zeros in one plane.** Pass 4 reported "two literal zeros" as the
record; pass 8's `pay-per-crawl` top-6 summed 9 stars; pass 9's thinnest query still returned
something. This plane returns *nothing at all* for the automation of a chain that gates roughly
**$34.6bn of 2025 box office** (Futuresource) across every commercial screen on earth. It is not a
thin agent layer. It is an absent one.

### ⚠️ Contamination — `cinema AI agent` is the sharpest false friend measured in this KB

`cinema AI agent` returns **205 results and 526 stars in the top 6, and not one of them is about
cinema.** Every hit is generative-video *prompt styling*:

| Repo | Licence | ★ | What it actually is |
|---|---|---|---|
| [workingprototype/Fuobe](https://github.com/workingprototype/Fuobe) | MIT | 262★ | A ComfyUI creative studio |
| [akseolabs-seo/cinematic-ui](https://github.com/akseolabs-seo/cinematic-ui) | MIT | 119★ | An agent skill for **website** design |
| [Leo414x/AI_Cinematic_Prompt](https://github.com/Leo414x/AI_Cinematic_Prompt) | NOASSERTION | 87★ | HBO-look prompt skill |
| [aedev-tools/kling-3-prompting-skill](https://github.com/aedev-tools/kling-3-prompting-skill) | MIT | 30★ | Kling 3 prompt skill |
| [DenisHumen/cinema-skills](https://github.com/DenisHumen/cinema-skills) | MIT | 19★ | Claude skills for AI video |

**In open source, "cinema" means "cinematic look" and never "movie theatre".** This is worse than
pass 7's false friend, because the results are numerous, well-starred, permissively licensed and
actively maintained — a careless pass would have written five plausible rows and all five would have
been about video generation. The query that finds the real plane is the **artifact name**: `DCP`,
`KDM`, `asdcplib`, `digital cinema package`. The pass-6 rule holds exactly: *the standard's name is
the query.*

A second abundance trap in the same plane: `cinema ticketing platform` returns **350 results** whose
top five are 12★, 6★, 6★, 4★, 4★ — all student and portfolio CRUD apps. Read the results, not the
total.

### What stands in for an agent layer today

Nothing, and the reason is worth stating because it is commercially useful rather than
discouraging. The theatrical chain is **deterministic and already automated** — `dcp-o-matic` builds
a package, `ClairMeta` validates it, a KDM unlocks it on a dated window. What is missing is not
intelligence inside those steps but **judgement across them**: which of 400 incoming DCPs failed and
why, which keys expire before which booking, which accessibility track is absent for which mandated
screening. That is an orchestration problem over typed artifacts, which is the one shape agents are
actually good at. See Patterns 28–30 in `compose/patterns.md`.

### Informed gaps from this pass — searched, and genuinely not found

- **No open theatre management system (TMS) or playout automation for cinema.** 350+ results across
  two queries, ceiling 12★, every one a booking-form exercise. The single real candidate is
  [1105821037/CineTMS](https://github.com/1105821037/CineTMS) (Apache-2.0, 5★, 2026-07-30), an APAC
  cinema automation project — verified Apache-2.0 in its own `LICENSE` (11,357B), but at 5 stars it
  is a bet, not a base.
- **No open cinema accessibility tooling, under a US federal mandate.** `cinema accessibility app
  captioning` returns **one repo with zero stars**. The DOJ's ADA Title III rule has required
  captioning and audio-description equipment at the patron's seat in every digital auditorium since
  December 2016. **A 0-star ceiling under a nine-year-old federal mandate** — sharper than pass 3's
  56-star audio-description ceiling.
- **No open box-office forecasting of any currency.** 103 results, top-6 sum **29 stars**, every one
  student coursework from 2017–2020, none with a licence.
- **No open KDM lifecycle manager with a user base.** See `repos/foundations.md`: the entire key
  layer is 3 stars across its top eight repos.
- **No open preshow/cinema-advertising stack.** Zero results. Cinema advertising is a real market
  (Statista tracks it as its own APAC category) with no open substrate at all.

## The description & semantic-interchange plane — measured 2026-11-26 (pass 11), and the **first plane in this KB whose agent layer is permitted but still unbuilt**

Ten passes have found the same shape: a plane with no agent layer, because the knowledge content the
agents would need was licensed shut (CPT, MedDRA, ISRC/ISWC/ISAN/EIDR/CWR, MovieLabs). This plane is
the **control case** the law needed. Here the knowledge content is *openly licensed* — and the result
is neither the usual zero nor a healthy field. It is a **three-step gradient inside one plane**, and
it is the most precise statement the structural law has had.

### How the gap was found — the vocabulary probe again, two Bash calls, before any web search

| Term | Files | Hits | Verdict |
|---|---|---|---|
| `IPTC`, `NewsML`, `ninjs`, `NITF`, `EBUCore`, `PBCore`, `Dublin Core`, `schema.org` | 0 | **0** | The interchange schemas are absent |
| `XMP`, `exiftool`, `syndication`, `wire service`, `cataloguing`, `metadata schema` | 0 | **0** | The description substrate is absent |
| `SKOS`, `thesaurus`, `controlled vocabulary`, `authority control` | 0 | **0** | The vocabulary layer is absent |
| `Wikidata`, `named entity`, `entity linking`, `knowledge graph`, `semantic search`, `ontolog*` | 0 | **0** | The linking layer is absent |
| `OAI-PMH`, `IIIF`, `Omeka`, `DSpace`, `CollectiveAccess`, `Dataverse` | 0 | **0** | The exposure protocols are absent |
| `Sofie` | 7 | **165** | **Already covered** — pass 8 took newsroom *playout*, not description |
| `AtoM`, `ArchivesSpace`, `Islandora`, `fedora`, `MARC` | 4–6 | 15–28 | **Already covered** — pass 4 took archival *repositories*, not cataloguing |
| `C2PA`, `provenance` | 7–8 | 51–64 | **Already covered** — pass 9 took *provenance*, not description |

The KB could already **identify** an asset (pass 5), **prove** it (pass 9), **preserve** it (pass 4)
and **play it out** (pass 8). It could not **describe, catalogue or syndicate** it. That is the
bottleneck under every "AI over the client's archive" engagement: retrieval is impossible over
assets that carry no description.

### Tier 1 — Permissive, actively maintained, safe to build on

| Agent | Repo | License | Stars / forks | Last push | What it actually does |
|---|---|---|---|---|---|
| spaCy | https://github.com/explosion/spaCy | MIT | 34094★ / 4753f | 2026-11-21 | The pipeline substrate the rest of this table plugs into |
| flair | https://github.com/flairNLP/flair | MIT (`LICENSE`, 1166 B, Zalando SE) | 14400★ / 2095f | 2026-10-19 | NER + entity linking framework; sequence labelling over news text |
| GLiNER | https://github.com/urchade/GLiNER | Apache-2.0 | 4296★ / 327f | 2026-11-11 | **Zero-shot NER** — arbitrary entity types with no retraining, which is what an archive with a bespoke subject list actually needs |
| inaSpeechSegmenter | https://github.com/ina-foss/inaSpeechSegmenter | MIT | 919★ / 149f | 2026-03-12 | Speech/music/noise segmentation for AV archive indexing, from **INA**, the French national audiovisual institute — the most-starred purpose-built archive-indexing tool found in this plane |
| **Annif** | https://github.com/NatLibFi/Annif | **Apache-2.0** (`LICENSE.txt`, 606 B, University of Helsinki) | 280★ / 50f | 2026-11-24 | **Automated subject indexing against a controlled vocabulary.** Trains on a SKOS thesaurus + existing catalogue records and assigns subject headings to new documents. Powers Finto AI, a national service, since May 2020 |
| OpenTapioca | https://github.com/opentapioca/opentapioca | Apache-2.0 | 263★ / 30f | 2026-08-26 | Lightweight **Wikidata** entity linking, kept in sync with Wikidata in real time |
| spacyopentapioca | https://github.com/UB-Mannheim/spacyopentapioca | MIT | 96★ / 8f | 2026-02-05 | spaCy wrapper for OpenTapioca — the one-line way to put Wikidata linking in an existing pipeline |
| Annif-client | https://github.com/NatLibFi/Annif-client | Apache-2.0 (`LICENSE.txt`, 601 B) | 3★ / 3f | 2025-09-25 | Thin REST client for a hosted Annif; use when you do not want to train |

Note the shape: **one** tool does the actual judgment (Annif), and it comes from a *national library*,
not a media company. Everything above it in the star ranking is general-purpose NLP that knows
nothing about media vocabularies.

### Tier 2 — Real, but the licence or the staleness constrains client work

| Agent | Repo | License | Stars / forks | Last push | Constraint |
|---|---|---|---|---|---|
| amalia.js | https://github.com/ina-foss/amalia.js | MIT | 191★ / 36f | 2023-08-28 | INA's metadata-overlay player. Permissive but **dormant >3 years** |
| twembeddings | https://github.com/ina-foss/twembeddings | MIT | 33★ / 5f | 2026-06-30 | INA event detection/clustering over social text; research-grade |
| afp-api-client | https://github.com/ina-foss/afp-api-client | LGPL-3.0 | 3★ / 0f | 2023-12-05 | Agence France-Presse wire client — the only open wire-service client found. Dormant, and LGPL |
| Annif-corpora | https://github.com/NatLibFi/Annif-corpora | **NO LICENSE FILE** | 8★ / 6f | 2026-10-09 | See below — this is the finding of the pass |
| metadata-extraction | https://github.com/icaew-digital-archive/metadata-extraction | **NO LICENSE FILE** | 3★ / 0f | 2026-11-24 | LLM → Dublin Core JSON cataloguing with archivist review. Live two days before this pass, and **unlicensed** |

### The finding: Annif is Apache-2.0 and **Annif-corpora is not licensed at all**

`NatLibFi/Annif` carries a clean Apache-2.0 grant. `NatLibFi/Annif-corpora` — the labelled training
corpora **without which Annif assigns nothing** — has no licence file on either branch, with the
control request passing (`README.md` on `master` = 200, so the probe's filenames are not at fault).
`NatLibFi/Finto-data` (21★, pushed 2026-11-26, the day of this pass) is explicitly **mixed**: its
`LICENSE` opens "This repository contains code and data under various open source licenses. Code
under `tools/` is generally licensed under the MIT License, unless explicitly stated otherwise".

So the law survives its control case, in a sharper form than before:

> **The code was never the bottleneck. In every plane, the thing that is not granted is the
> knowledge content — and when the *schema* is finally granted (IPTC, CC BY 4.0), the withheld
> layer moves down to the *labelled corpus* that teaches a machine to apply it.**

An open schema buys you the format. It does not buy you the judgment, because judgment is trained on
annotated records, and those are the asset an institution does not give away. This is why the plane
is permitted but unbuilt.

### Measured: the judgment layer is one repo deep, and the searches that should find rivals return other industries

Per pass 8's rule — read the results, not the total:

| Query | Results | Top-6 star sum | What is actually in the top 6 |
|---|---|---|---|
| `subject indexing` | 257 | 437 | **Annif (280★) and then nothing** — ranks 2-6 are `OK-`, `sahabatfb`, `Aim`, `Theme`, `DAWD`, all 2014-2022, all unlicensed, all unrelated |
| `automated cataloguing` | 203 | 753 | **Top hit is a security recon tool** — `chrismaddalena/ODIN`, BSD-3, 670★, archived 2022. Zero relevance |
| `metadata enrichment` | 1043 | 1392 | **False abundance** — top hit is a *Kubernetes fluentd plugin* (355★). Only one media item: INA's `amalia.js` |
| `automatic cataloging library` | 61 | 141 | One real: `fabiodalez-dev/Pinakes` (GPL-3.0, 95★, 2026-11-25) |
| `controlled vocabulary` | 531 | 1141 | Real: Skosmos 269★, TemaTres 142★. The rest is climate (`CMIP6_CVs`) and privacy (`w3c-cg/dpv`) |
| `archival metadata LLM agent` | 8 | 3 | **Empty.** Top results 0-2★, none relevant |
| `vidya archival metadata` | **0** | — | arXiv 2605.16338 describes an LLM+FOSS archival pipeline. **No code under that name on GitHub** |

`automated cataloguing` returning a penetration-testing tool is this pass's `eidr`/`isan`: a query
that looks productive and is answering a different industry. Four of the seven queries above are
false friends or false abundance.

### The agentic layer is papers, not code — stated precisely

Two 2026 arXiv papers describe exactly the agent this plane needs: **2504.05711** (a multi-agent
archival-metadata framework with several LLMs, a validator and a federator) and **2605.16338**
("Vidya", an LLM + FOSS pipeline for semantic enrichment and archival ingestion, reported compliant
with **NOBRADE** and **ISAD(G)** and designed for low-cost deployment on modest hardware in memory
institutions). Neither has locatable released code from this session. The only live LLM-cataloguing
repo found anywhere is ICAEW's, at 3★ and unlicensed.

**Do not promise a client an off-the-shelf agentic cataloguing stack.** The format layer is ready,
the judgment layer is one national-library tool, and the agentic layer is two preprints.

## The sound, music & immersive-audio plane — measured 2026-11-26 (pass 12), and the licence hardens by *where the code runs*

`media-kb` arrived with the remote already carrying **passes 8, 9, 10 and 11**, four of them dated
today, while `rotation.json` still read `next=4, last_industry=healthcare` — the **seventh
consecutive failure of step 5** on this one industry. Pass 8's corollary applied again: same-day
passes mean the right move is neither a rewrite nor a re-verification but **finding the missing
vocabulary plane.**

### How the gap was found — the vocabulary probe, two Bash calls, 95 terms, before any web search

| Term group | Files | Hits | Verdict |
|---|---|---|---|
| `spatial audio`, `Atmos`, `binaural`, `ambisonic`, `object-based audio`, `next-generation audio` | 0 | **0** | Immersive audio absent |
| `Ardour`, `Audacity`, `LMMS`, `Zrythm`, `JUCE`, `SuperCollider`, `Csound`, `Faust`, `Pure Data`, `DAW` | 0 | **0** | The authoring/host layer absent |
| `MuseScore`, `LilyPond`, `music21`, `Verovio`, `VexFlow`, `abcjs`, `MusicXML`, `music notation`, `MIDI` | 0-2 | **≤2** | The music layer absent |
| `Spleeter`, `Magenta`, `Basic Pitch`, `aubio`, `RNNoise`, `DeepFilterNet`, `noise suppression`, `foley`, `dialogue edit`, `audio post` | 0 | **0** | Restoration & MIR absent |
| `loudness` 39 · `ebur128` 14 · `Essentia` 11 · `librosa` 10 · `pyannote` 19 · `Demucs` 7 | 3-8 | present | **Already covered** — loudness as *regulated measurement* (p4), fingerprinting (p5), diarisation (p7) |

The KB could **measure** audio (p4), **identify** it (p5) and **generate** it (base pass). It could
not **author** it. Everything between the microphone and the loudness meter — mixing, dialogue
editing, restoration, music, and the entire immersive/next-generation-audio stack that ATSC 3.0 and
every 2026 sports deliverable now depend on — was a blank.

### The finding: a four-step gradient, and it is ordered by *whose process the code runs inside*

This is the most complete gradient measured in this KB, and the first that explains itself with a
mechanism rather than a correlation.

| Layer | What it is | State | Evidence |
|---|---|---|---|
| **1. STANDARD / REFERENCE** (format) | ITU/EBU reference implementations, run *beside* the host | **PERMISSIVE, 7/7** | `ebu/bear` Apache-2.0 · `ebu/libadm` Apache-2.0 · `ebu/libbw64` Apache-2.0 · `ebu/ebu_adm_renderer` BSD-3-Clause-Clear · `ADM-OSC` MIT · `omnitone` Apache-2.0 · `JSAmbisonics` BSD-3 |
| **2. PLUGIN / HOST** (code that must load *inside* a proprietary DAW) | VSTs, plugin frameworks, engines | **DUAL OR COPYLEFT, 6/6 — no exception** | `JUCE` **AGPL-3.0 or commercial** · `tracktion_engine` **GPL-3.0 or commercial** · `libspatialaudio` **LGPL-2.1+ or commercial** · `Spatial_Audio_Framework` **ISC core / GPL-2.0 once optional modules are enabled** · `ear-production-suite` GPL-3.0 · `zrythm` AGPL-3.0 + §7 additional terms |
| **3. MODEL / DATA** (judgment) | Pretrained weights and annotated corpora | **RESTRICTED** | `madmom` code BSD, **models CC BY-NC-SA 4.0** · `fish-speech` bespoke licence with a **USD 500,000 revenue threshold** |
| **4. AGENT** (judgment at scale) | — | **MEASURED NEAR-ZERO, twelfth consecutive** | `audio post production agent` = **6 results in all of GitHub**, top-6 star sum **7** (3,2,1,1,0,0) |

> **The refinement, and it is the sharpest mechanical statement the structural law has had.**
> Across eleven previous planes this KB recorded *that* the licence hardens at the platform tier. This
> plane says *why*: **the licence hardens exactly where the code must enter someone else's proprietary
> process space.** Code that runs *beside* a proprietary host stays permissive — all seven reference
> implementations. Code that must be *loaded into* one is dual-licensed or copyleft — all six, without
> a single counterexample. Dual licensing here is not an ideological choice; it is the business model
> of selling an exception to people shipping closed plugins.

**What that means for an engagement, concretely.** A renderer, an analysis service or a conversion
tool built on layer 1 is clean. The moment the deliverable is *a plugin inside the client's Pro Tools
or Nuendo rig*, the stack underneath it is AGPL or a paid commercial licence, and that is a
procurement line item, not a technical detail. Price JUCE before promising a plugin.

### ⛔ The licence finding of this pass: a 1,745-star library whose *models* are non-commercial

`CPJKU/madmom` is the standard beat-, downbeat- and tempo-tracking library in music information
retrieval. Its single `LICENSE` file splits in two:

- **Source code files** (`.py`, `.pyx`, `.pxd`, `.c`) — BSD-style, 3-clause, fully permissive.
- **Data and model files** (`.npy`, `.npz`, `.h5`, `.hdf5`, `.pkl`, `.mat`) — **Creative Commons
  Attribution-NonCommercial-ShareAlike 4.0**, with the file stating in terms:
  *"If you want to include any of these files ... in a commercial product, please contact Gerhard
  Widmer at [JKU]. Please note that **pickled Processors (i.e. saved models) fall into this
  category**."*

madmom without its pretrained models tracks nothing. **The permissive badge on the repository is
therefore true and useless**: every GitHub listing, every awesome-list and every licence scanner that
reads the repo-level field will call this safe for client work, and it is not. This is the third
independent confirmation of pass 9's refinement — the licence has moved into the weights — and the
first time it has been found *inside a single licence file*, where no repo-level scanner can see it.

`fishaudio/fish-speech` (**33,872★**, the largest repo in this plane) does the same thing with a
different instrument: a bespoke **Fish Audio Community License Agreement v1.0**, dated 2026-10-13,
which GitHub reports as `NOASSERTION`. It permits commercial use only while annual revenue is under
**USD 500,000**, and — this clause matters more to Globant than any other sentence measured this pass
— it extends to work done *"as a contractor, integrator, consultant, or on-premises vendor"* **only if
the client's revenue is also under the threshold.** Delivering a fish-speech deployment into an
enterprise is unlicensed. Delivering *only the output* — "voiceovers, dubbing, or audiobooks for a
client" — is explicitly carved out and permitted. **Same software, same studio; the licence turns on
the delivery model.** Read Section III before any voice engagement.

### Tier 1 — permissive, active, safe to build on

| Agent / model | Repo | License | Stars | Last push | What it does |
|---|---|---|---|---|---|
| sherpa-onnx | https://github.com/k2-fsa/sherpa-onnx | Apache-2.0 | 16,241 | 2026-11-24 | On-device ASR, TTS, speaker ID and enhancement; the deployment runtime for the whole speech layer |
| speechbrain | https://github.com/speechbrain/speechbrain | Apache-2.0 | 11,951 | 2026-11-25 | All-in-one speech toolkit — separation, enhancement, diarisation, recognition |
| YuE | https://github.com/multimodal-art-projection/YuE | Apache-2.0 | 13,742 | 2026-11-01 | Full-song music generation with vocals; the most permissive serious music model |
| DeepFilterNet | https://github.com/Rikorose/DeepFilterNet | MIT **or** Apache-2.0 (dual-permissive; API says `NOASSERTION`) | 5,107 | 2026-11-06 | Real-time full-band speech noise suppression — the dialogue-cleanup workhorse |
| ACE-Step | https://github.com/ace-step/ACE-Step | Apache-2.0 | 5,113 | 2026-02-15 | Music generation foundation model |
| ClearerVoice-Studio | https://github.com/modelscope/ClearerVoice-Studio | Apache-2.0 | 4,659 | 2025-08-14 | Speech enhancement, separation and target-speaker extraction |
| stable-audio-tools | https://github.com/Stability-AI/stable-audio-tools | MIT | 3,920 | 2026-11-01 | Training and inference for audio generation (code MIT; check weights separately) |
| spleeter | https://github.com/deezer/spleeter | MIT | 28,539 | 2026-10-28 | Stem separation — still the most-deployed, and unlike Demucs it is **not archived** |
| asteroid | https://github.com/asteroid-team/asteroid | MIT | 2,605 | 2026-11-03 | Source-separation research framework |
| resemble-enhance | https://github.com/resemble-ai/resemble-enhance | MIT | 2,510 | 2024-12-03 | Speech restoration and denoising — permissive, but **two years without a push** |
| versatile_audio_super_resolution | https://github.com/haoheliu/versatile_audio_super_resolution | MIT | 2,004 | 2025-08-27 | Bandwidth extension for archive and telephone-grade audio |

### Tier 2 — real, but the licence or the staleness constrains client work

| Agent / model | Repo | License | Stars | Last push | Constraint |
|---|---|---|---|---|---|
| fish-speech | https://github.com/fishaudio/fish-speech | Fish Audio Community License v1.0 | 33,872 | 2026-11-14 | **USD 500k revenue threshold**; hosted TTS service needs a separate agreement; agency *output* delivery carved out |
| magenta | https://github.com/magenta/magenta | Apache-2.0 | 19,781 | 2026-01-06 | **ARCHIVED** — permissive and dead; cite as provenance, never as a dependency |
| demucs | https://github.com/facebookresearch/demucs | MIT | 10,425 | 2024-04-24 | **ARCHIVED.** Still the quality leader for stems; use Spleeter or asteroid where maintenance matters |
| essentia | https://github.com/MTG/essentia | **AGPL-3.0** | 3,819 | 2026-11-18 | Healthy and active, but AGPL reaches a hosted service |
| aubio | https://github.com/aubio/aubio | GPL-3.0 | 3,792 | 2026-04-10 | Onset/pitch/beat detection; copyleft |
| matchering | https://github.com/sergree/matchering | GPL-3.0 | 2,741 | 2026-10-07 | Reference-based automated mastering — the closest thing to an "AI mastering agent" that is real |
| DiffRhythm | https://github.com/ASLP-lab/DiffRhythm | Apache-2.0 | 2,372 | 2025-11-27 | Full-length song generation; a year without a push |
| madmom | https://github.com/CPJKU/madmom | BSD code / **CC BY-NC-SA 4.0 models** | 1,745 | 2026-03-20 | **The models are non-commercial.** See above |

### ⚠️ Contamination — the word "supervision" collides, and one query returns pirated software

Four of six agent-layer queries in this plane are false friends, and one is a safety hazard:

| Query | Top result | Why it is not what you asked for |
|---|---|---|
| `music supervision AI` | `ANI-IN/Multi-Agent-Customer-Support`, **27★** | In media, *music supervision* is clearing and placing music. In agent frameworks, a *supervisor* routes sub-agents. Rank 5, `music-agent-supervisor`, is the **LangGraph supervisor pattern** — the same word colliding twice in one result set |
| `dialogue editing AI` | `koronto11/ludo-npc-ai`, **104★** | In post-production, *dialogue editing* is cleaning production sound. In AI, *dialogue* is conversation. Every high-star hit is NPC chat |
| `sound design agent LLM` | `matinsizen/ai-3d-animator-skill`, **83★** | Returns 3D animation skills, not audio |
| `spatial audio agent` | game and streamer **config skills** | Returns per-app audio *configuration* helpers, not production tooling |
| `dialogue editing AI`, rank 3 | `...SpectraLayers-Pro-13-Free-AI-Audio-Editing`, 9★, **no licence** | **A pirated-commercial-software lure.** This plane's queries surface warez repos dressed as tooling. Do not clone results in this family without reading the repo first |

**Rule for this plane: never take a star count from a query containing `audio`, `dialogue`, `sound`
or `supervision` without opening the repo.** The vocabulary of audio post-production is almost
entirely homonymous with the vocabulary of AI agents.

### What stands in for an agent layer today

There is no agentic audio-post tooling worth recommending. What exists and works is a **pipeline of
permissive single-purpose models** with the judgment supplied by a human supervisor or a thin
orchestrator you write: separate (Spleeter/asteroid) → clean (DeepFilterNet/ClearerVoice) → restore
(versatile_audio_super_resolution) → identify speakers (pyannote, MIT, already in this KB) →
transcribe (Whisper, MIT, already in this KB) → render to the target layout (BEAR/EAR). Pass 12's
compose patterns wire exactly that.

### Informed gaps from this pass — searched, and genuinely not found

- **No open loudness-compliant *mixing* agent.** Loudness *measurement* is solved (p4, ebur128); the
  decision of what to do about a failing measurement has no open implementation.
- **No open music-clearance or cue-sheet tooling.** `music cue`, `cue sheet`, `rights clearance` and
  `sync licensing` return nothing usable — consistent with pass 5's finding that music royalty
  accounting is the crudest zero in this KB.
- **No open MPEG-H authoring tool.** The ATSC 3.0 2026 suite standardises MPEG-H audio; the open
  stack here is ADM/EAR-based. The encoder side is Fraunhofer's and is not open. **This is the single
  largest supply gap in the plane**, and it sits directly under a live North American deadline.
- **IEM Plugin Suite** — the reference ambisonic plugin set — is **not canonically on GitHub**; it
  lives on `git.iem.at`, which this environment's proxy cannot reach (uniform `000`). GitHub carries
  only forks, the largest `tu-studio/IEMPluginSuite` at 12★, GPL-3.0. Recorded as *unverifiable from
  here*, not as absent.

## The subscription, entitlement & reader-revenue plane — measured 2026-11-26 (pass 13), and the licence hardens as the code approaches the money

The first twelve passes measured how media is **made, described, delivered and policed**. None of them
measured how it is **paid for on a recurring basis**. The monetization plane (pass 2) covered the
*advertising* half of media revenue and stopped there: ad signalling, auction, measurement. The
subscriber half — identity, entitlement, billing, dunning, churn, and the publisher's own conversion
funnel — had no row anywhere in this KB. This pass measures it.

### How the gap was found — the vocabulary probe again, before any web search

Two Bash calls against `search/repositories`, the same method as passes 11 and 12. Agent-layer
vocabulary first:

| Query | Total repos | Top result above 200★ |
|---|---|---|
| `billing agent` | 2,869 | `Fosowl/agenticSeek` (27,701★) — a general-purpose assistant |
| `subscription agent` | 2,687 | `ParadevAI/Paradev` (16,696★) — a coding agent |
| `revenue agent` | 3,230 | `Lifecycle-Innovations-Limited/claude-ops` (563★) — devops |
| `churn agent` | 764 | `danderfer/Comp_Sci_Sem_2` (228★) — a university coursework repo |
| `paywall agent` | 222 | `actionbook/actionbook` (1,633★) — an agent that gets *past* paywalls |
| `entitlement agent` | 148 | `MoritzPindorek/Five-Laws-of-AI-Agents` (305★) — an essay |
| **`dunning agent`** | **57** | **none** |
| `subscriber retention AI` | 28 | none |

**This is the thirteenth consecutive plane with a near-zero agent layer, and the vocabulary collapse
here is the worst measured in this KB.** The pattern is now explicit enough to state as a rule: in
this plane, *generic* terms return tens of thousands of stars of general-purpose agents that have
nothing to do with media revenue, and the *precise* term — `dunning`, the industry's own word for
failed-payment recovery, which cannot mean anything else — returns 57 repos and not one above 200
stars. The generic query is contaminated; the precise query is empty. Both describe the same absence.

### The finding of this pass: a four-step gradient, ordered by distance from the recurring charge

Pass 12 found a licence gradient ordered by *whose process the code runs inside*. This plane's
gradient is ordered by **how close the code sits to the money**, and it is the cleanest one measured
so far. All figures measured 2026-11-26.

| Step | Layer | What it decides | Licence shape | Evidence |
|---|---|---|---|---|
| 1 | **Identity** | Who are you | **Apache-2.0, large, healthy** | Keycloak 38,060★, Ory Kratos 13,977★ |
| 2 | **Entitlement** | What may you watch | **Apache-2.0, crowded, healthy** | SpiceDB 7,243★, OpenFGA 6,197★, Cerbos 4,669★, Ory Keto 5,424★, Casbin |
| 3 | **Billing / subscription** | The recurring charge itself | **AGPL-dominant**, one permissive anchor | Lago 10,922★ AGPL, flexprice 6,874★ AGPL, Meteroid 1,370★ AGPL, keygate 279★ AGPL — vs **Kill Bill 5,869★ Apache-2.0** |
| 4 | **Reader revenue / paywall** | The publisher's own conversion funnel | **One MIT repo, 138★** | REMP (138★) and nothing else |

The gradient is monotone and it has a plain commercial reading: **authorization is infrastructure and
gets given away; the recurring charge is the business and gets protected.** For Globant this is
actionable in one line — steps 1 and 2 are free to build on and embed, step 3 is a deployment-shape
decision before it is a technical one, and step 4 is not a build-vs-buy choice because there is
almost nothing to buy.

### Tier 1 — permissive, active, safe to build on

| Agent / Component | Repo | License | Stars | Last push | What it does |
|---|---|---|---|---|---|
| Keycloak | [keycloak/keycloak](https://github.com/keycloak/keycloak) | Apache-2.0 | 38,060 | 2026-11-26 | Identity and access management. The default front door for a subscriber estate; OIDC/SAML, and the layer entitlement hangs off. |
| SpiceDB | [authzed/spicedb](https://github.com/authzed/spicedb) | Apache-2.0 | 7,243 | 2026-11-24 | Google Zanzibar-style relationship database for permissions. The strongest fit for "which titles may this subscriber stream, in which territory, on how many devices". |
| OpenFGA | [openfga/openfga](https://github.com/openfga/openfga) | Apache-2.0 | 6,197 | 2026-11-25 | CNCF-hosted Zanzibar-style authorization engine. Lighter to operate than SpiceDB; same modelling idea. |
| Kill Bill | [killbill/killbill](https://github.com/killbill/killbill) | Apache-2.0 | 5,869 | 2026-11-26 | **The permissive anchor of this plane.** Subscription billing and payments platform: plans, trials, proration, dunning, invoicing. The only mature billing engine in this plane that is not copyleft. |
| Ory Keto | [ory/keto](https://github.com/ory/keto) | Apache-2.0 | 5,424 | 2026-09-04 | Zanzibar-style permission server. Permissive and real, but ~3 months without a push — slower than its rivals above. |
| Cerbos | [cerbos/cerbos](https://github.com/cerbos/cerbos) | Apache-2.0 | 4,669 | 2026-11-25 | Policy-as-code authorization: decisions are externalised to a policy file rather than a relationship graph. Open-core — the engine is Apache-2.0. |
| Ory Kratos | [ory/kratos](https://github.com/ory/kratos) | Apache-2.0 | 13,977 | 2026-07-29 | Headless identity and user management. Apache-2.0, but ~4 months without a push. |
| Casbin | [casbin/casbin](https://github.com/casbin/casbin) | Apache-2.0 | n/m | n/m | Embeddable authorization library across many languages. **Stars and push date are not measurable** — see the method correction below; licence confirmed by reading the LICENSE file directly. |
| OpenMeter | [openmeterio/openmeter](https://github.com/openmeterio/openmeter) | Apache-2.0 | 2,471 | 2026-11-26 | Usage metering and aggregation. The permissive way to meter consumption without adopting an AGPL billing platform. |
| Hyperswitch | [juspay/hyperswitch](https://github.com/juspay/hyperswitch) | Apache-2.0 | 45,917 | 2026-11-26 | Payments orchestration across PSPs, self-hostable. The largest permissive project anywhere in this plane. |
| REMP | [remp2020/remp](https://github.com/remp2020/remp) | MIT | 138 | 2026-11-25 | **The only open reader-revenue platform found.** Monorepo from Denník N (Slovakia): SSO, Beam (event tracking + segments), Campaign (banner/offer targeting), Mailer (newsletters, A/B). EMEA-origin. See `verticals/solutions.md`. |
| lifelines | [CamDavidsonPilon/lifelines](https://github.com/CamDavidsonPilon/lifelines) | MIT | 2,623 | 2026-03-07 | Survival analysis in Python. The honest statistical basis for subscriber-churn and tenure modelling. |

### Tier 2 — real, but the licence or the staleness constrains client work

| Agent / Component | Repo | License | Stars | Last push | Constraint |
|---|---|---|---|---|---|
| Lago | [getlago/lago](https://github.com/getlago/lago) | **AGPL-3.0** | 10,922 | 2026-11-25 | The most-starred billing platform in this plane, and network copyleft. Run it unmodified behind its API, or the client's surrounding revenue code becomes disclosable. |
| flexprice | [flexprice/flexprice](https://github.com/flexprice/flexprice) | **AGPL-3.0** | 6,874 | 2026-11-26 | Usage-based pricing and billing. Same constraint as Lago; very active. |
| Permify | [Permify/permify](https://github.com/Permify/permify) | **AGPL-3.0** | 5,975 | 2026-11-26 | Zanzibar-style authorization — the one entitlement engine that is *not* permissive. Pick SpiceDB or OpenFGA instead unless a Permify feature is decisive. |
| ZITADEL | [zitadel/zitadel](https://github.com/zitadel/zitadel) | **AGPL-3.0** | 15,654 | 2026-11-25 | Identity infrastructure. Capable, but AGPL at the identity tier — Keycloak is the Apache-2.0 equivalent. |
| Meteroid | [meteroid-oss/meteroid](https://github.com/meteroid-oss/meteroid) | **AGPL-3.0** | 1,370 | 2026-11-26 | Pricing and billing infrastructure, actively developed. AGPL. |
| SuperTokens | [supertokens/supertokens-core](https://github.com/supertokens/supertokens-core) | **Split: core + proprietary `ee/`** | 15,347 | 2026-11-25 | GitHub reports `NOASSERTION`. LICENSE.md read: everything outside `ee/` is open; `ee/` carries its own separate terms. The directory boundary *is* the licence. |
| keygate | [tabloy/keygate](https://github.com/tabloy/keygate) | **AGPL-3.0** | 279 | 2026-11-23 | Licence/subscription management (perpetual + subscription keys). Small, active, AGPL. |
| Laravel Cashier | [laravel/cashier-stripe](https://github.com/laravel/cashier-stripe) | MIT | 2,550 | 2026-11-17 | MIT and healthy, but it is a Stripe binding, not a billing engine — it inherits a single PSP as a hard dependency. |
| billabear | [billabear/billabear](https://github.com/billabear/billabear) | **Unresolved** | 760 | 2026-09-13 | Subscription management and billing. GitHub reports `NOASSERTION` and **no LICENSE file was retrievable at the default branch** — licence genuinely undetermined, not merely unlabelled. Do not adopt before resolving it with the maintainer. |
| lifetimes | [CamDavidsonPilon/lifetimes](https://github.com/CamDavidsonPilon/lifetimes) | MIT | 1,476 | 2024-06-28 | **ARCHIVED.** Customer-lifetime-value (BG/NBD, Gamma-Gamma) modelling. Still the clearest reference implementation of CLV; vendor it, expect no fixes. Its author's `lifelines` is the live project. |
| servicebot | [service-bot/servicebot](https://github.com/service-bot/servicebot) | GPL-3.0 | 956 | 2021-01-12 | Subscription management automation. **Dormant ~5 years.** Listed so no future pass re-adopts it as live. |

### ⚠️ Contamination — `paywall` is the most adversarial query measured in this KB

Pass 7 recorded the worst *false-friend* query; this is something different and worse. The open-source
`paywall` ecosystem is not empty and it is not mislabelled — **it is aimed at the opposite outcome**.
`topic:paywall`, sorted by stars, top ten, measured 2026-11-26:

| Repo | License | Stars | What it does |
|---|---|---|---|
| [everywall/ladder](https://github.com/everywall/ladder) | GPL-3.0 | 9,457 | Self-hosted proxy that strips paywalls |
| [manualdousuario/marreta](https://github.com/manualdousuario/marreta) | GPL-3.0 | 1,229 | Breaks access barriers — Brazilian, aimed at the Brazilian press |
| [burlesco/burlesco](https://github.com/burlesco/burlesco) | MIT | 948 | "Read news without subscribing" — Brazilian |
| [stefanw/bibbot](https://github.com/stefanw/bibbot) | GPL-3.0 | 656 | Removes paywalls on German news sites via library credentials |

Ten of the top ten are circumvention tools; **the sum of their stars is 21,592**. The single
publisher-side implementation in the same measurement, REMP, has **138**. That is a ratio of about
**156 : 1 against the business model this plane exists to serve.**

Two further measurements make the point unarguable:

- **`topic:reader-revenue` returns zero repositories.** Not a few, not stale ones — the topic does not
  exist on GitHub.
- `metered paywall` returns 18 repos; `subscription paywall publisher` returns 6.

This is the same shape as trend 28's watermark-removal finding (`intel/trends.md`), but far more
extreme — and it carries a regional edge worth naming in a pitch: the two largest non-English
circumvention projects target the **Brazilian** press, and the third targets the **German** press.
A LATAM or EMEA publisher asking "what does open source give us for subscriptions" is asking about an
ecosystem whose most popular artefacts are built to defeat them.

### Informed gaps from this pass — searched, and genuinely not found

- **No open dunning or failed-payment-recovery agent.** `dunning agent` = 57 repos, none above 200★.
  Dunning is unambiguous vocabulary, so this is a clean zero, and it is the single most obviously
  automatable task in the plane.
- **No open churn-prediction system built for media.** The statistical substrate is permissive and
  excellent (`lifelines` MIT, `lifetimes` MIT-archived); nothing wires it to a subscriber estate.
- **No open entitlement model expressed in media terms.** SpiceDB/OpenFGA/Cerbos are generic; none
  ships a schema for territory, concurrency, device limits, windowing or offline rights. That schema
  is the reusable asset, and it does not exist.
- **No open reader-revenue platform outside REMP.** One repo, 138 stars, one publisher's house tooling.

### ⚙️ Two method corrections from this pass — both reusable across all twelve industries

**1. The `repo:` 422 is *not* only a rename detector.** `repos/foundations.md` (pass 9) records that
a 422 from `search/repositories` with a `repo:` qualifier means the repo was renamed or deleted. This
pass found a counter-example and it is unambiguous:

- `git ls-remote https://github.com/casbin/casbin HEAD` → returns a commit SHA. The repo **exists**
  and is public.
- `curl` of its LICENSE → Apache License 2.0, full text.
- `org:casbin` searches → return sibling repos (`casbin-caddy-authz`, etc.) normally.
- `repo:casbin/casbin` → **HTTP 422**, "resources do not exist or you do not have permission".

A live, public, 400-star-class repository can be **absent from GitHub's search index while present on
GitHub**. The corrected rule: *a 422 means the search index cannot see it, which is evidence about
the index, not about the repository.* Confirm with `git ls-remote` before recording a repo as gone —
and note the cost: stars and push dates for such a repo are simply **not measurable** by this method,
which is why Casbin's row above says `n/m` rather than carrying an inherited figure.

**2. `curl -sI https://github.com/...` is a broken existence oracle in this environment.** All 33
URLs in this pass returned a uniform **403** to HTTP HEAD through the egress proxy — including repos
that demonstrably exist. A pass that trusted HEAD would have discarded every finding as a dead link.
`git ls-remote` returned **33/33 OK** on the same list. **Verify with `git ls-remote`, not with HEAD.**

## The localization & translation-management plane — measured 2026-11-26 (pass 14), and the first plane this KB had **half** of

This KB already knew, in detail, how to *generate* a dub or a subtitle: Whisper for ASR, GPT-SoVITS
and the TTS layer for voice, MuseTalk for lip-sync, VideoLingo and pyvideotrans for orchestration.
What it had **nothing** of was the industrial substrate underneath that output — the formats,
memories, termbases, routing systems and quality contracts that turn one translated asset into a
repeatable localization *programme*.

The gap was measured before it was filled. Across all eight KB files, before this pass:
`xliff` 0 hits, `tmx` 0, `translation memory` 0, `termbase` 0, `terminology` 0, `glossary` 0,
`MQM` 0, `post-editing` 0, `quality estimation` 0, `Weblate` 0, `Okapi` 0, `OmegaT` 0.
Against `dubbing` 46, `subtitle` 61, `caption` 126. **34 repos were verified this pass and 0 of
the 34 already appeared anywhere in this KB** — the cleanest true-gap result of any pass.

### The agent layer, and why this plane breaks the streak

Thirteen consecutive passes found a near-zero agent layer. This one does not. There are real,
maintained, high-star tools that do translation work — because translation is the one media task
with a forty-year commercial tooling industry behind it. The scarcity has moved somewhere else
(see the quality table below, and §Trends).

| Agent / tool | Repo | Licence | Stars | Pushed | What it actually does |
|---|---|---|---|---|---|
| LibreTranslate | [LibreTranslate/LibreTranslate](https://github.com/LibreTranslate/LibreTranslate) | AGPL-3.0 | 17,851 | 2026-11-25 | Self-hosted, offline-capable MT API. ⚠️ Network copyleft — see the engine/wrapper note below. |
| argos-translate | [argosopentech/argos-translate](https://github.com/argosopentech/argos-translate) | MIT | 6,696 | 2026-11-17 | Offline translation **library**. The permissive engine the AGPL server above is built on. |
| BallonsTranslator | [dmMaze/BallonsTranslator](https://github.com/dmMaze/BallonsTranslator) | GPL-3.0 | 5,321 | 2026-11-21 | Comic/manga CAT: OCR → text detection → inpaint → MT → typeset. The highest-star *applied* CAT tool found. |
| Transub | [dlsandy/Transub](https://github.com/dlsandy/Transub) | ⚠️ "MIT (Core)" | 222 | 2026-11-25 | Batch subtitle generation, automated QC, editor and burn-in. Licence carve-out — see below. |
| DeepTrans Studio | [hint-lab/deeptrans-studio](https://github.com/hint-lab/deeptrans-studio) | MIT | 173 | 2026-07-26 | Multi-agent translation platform aimed at professional localization. |
| BasicCAT | [xulihang/BasicCAT](https://github.com/xulihang/BasicCAT) | GPL-2.0 | 141 | 2026-04-14 | Open computer-aided-translation tool. |
| Swordfish | [maxprograms-com/Swordfish](https://github.com/maxprograms-com/Swordfish) | EPL-1.0 | 101 | 2026-11-07 | CAT tool built on open standards (XLIFF/TMX/TBX). |
| argos-train | [argosopentech/argos-train](https://github.com/argosopentech/argos-train) | MIT | 158 | 2026-06-26 | Training scripts for Argos models — the path to a client-specific engine. |
| LTEngine | [LibreTranslate/LTEngine](https://github.com/LibreTranslate/LTEngine) | AGPL-3.0 | 215 | 2026-11-20 | Local LLM-backed MT, LibreTranslate-API-compatible. |
| Lokalize | [KDE/lokalize](https://github.com/KDE/lokalize) | GPL-2.0-or-later | 32 | 2026-11-26 | KDE's computer-aided translation tool. Pushed the day of this pass. GitHub reports *no* licence — it is wrong; see the REUSE note below. |
| Silhouette | [xulihang/Silhouette](https://github.com/xulihang/Silhouette) | GPL-3.0 | 23 | 2026-08-30 | CAT tool specifically for **audio and video** — the only one found. |
| Game Localization QA | [memolyviza2012-max/game-localization-qa](https://github.com/memolyviza2012-max/game-localization-qa) | MIT | 9 | 2026-10-16 | A written QA protocol ("7 QA pillars") for AI game translation, not a library. |

**All twelve URLs above were verified with `git ls-remote` on 2026-11-26.**

### The engine/wrapper licence inversion — the most actionable finding in this plane

`LibreTranslate`'s own `pyproject.toml` pins **`argos-translate-lt ==1.12.1`** and
`argos-translate-files ==1.4.4`. The AGPL-3.0 licence is therefore in the **API wrapper**, while the
**translation engine is MIT** (`argosopentech/argos-translate`, verified MIT in its LICENSE file).

This is the exact inverse of the Chromaprint finding in pass 12, where a permissively-licensed repo
was hardened by its LGPL/GPL *dependencies*. Here the permissive core is *wrapped* in network
copyleft. The consequence for Globant is concrete and favourable:

- Deploying **LibreTranslate itself** as a client-facing hosted service triggers AGPL-3.0 §13 —
  users interacting over the network must be offered the corresponding source.
- Building a service **directly on `argos-translate` (MIT)** carries no such duty. It is the same
  engine, one layer down.

⚠️ **Informed gap:** the pinned `argos-translate-lt` is a fork distributed as a **PyPI package**; no
GitHub repository resolves at `LibreTranslate/argos-translate-lt` (checked 2026-11-26, `ls-remote`
FAIL). Confirm that fork's own licence on the PyPI artefact before shipping it — do not assume it
inherited upstream MIT.

### A third extension to the licence probe: the `LICENSES/` directory (REUSE)

Pass 12 established that a GitHub licence 404 is never, by itself, proof that a licence is missing,
and added `license.txt` (lowercase) and `COPYING.md` to the probe list. This pass adds a fourth
location, and it is the one that defeats every probe built so far:

**`KDE/lokalize` carries `LICENSES/GPL-2.0-or-later.txt` (17,277 bytes) — an entire `LICENSES/`
directory of SPDX-named files.** This is the **REUSE specification**, published by the Free Software
Foundation Europe. The GitHub API reports the repository as unlicensed because it does not look
inside `LICENSES/`; the control request (`README.md` on `master` = 200, `main` = 404) proves the
branch and channel were correct and the file names were the only thing wrong.

**Rule, now in its final form — probe all four shapes before recording "no licence":**
1. `LICENSE` / `LICENSE.md` / `LICENCE` (and **`license.txt`**, lowercase),
2. `COPYING` / **`COPYING.md`**,
3. **`LICENSES/<SPDX-ID>.txt`** (REUSE — new this pass),
4. and if all 404 *while `README.md` returns 200*, clone shallow and look.

This matters most in **EMEA**: REUSE is an FSFE standard and is disproportionately adopted by
European and EU-funded projects, which is exactly the estate a sovereignty-driven engagement draws
from. A licence sweep tuned only to American repo conventions will under-report European compliance.

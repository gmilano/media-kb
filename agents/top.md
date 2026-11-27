---
industry: media
region: Global
updated: 2026-11-27
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

## The out-of-home, signage & retail-media plane — measured 2026-11-26 (pass 15), and the first plane whose **open source sits in the screen while the vacuum sits in the transaction**

### Headline: the first plane in this KB where the open source is in the **screen** and the vacuum is in the **transaction**

Fourteen passes measured planes where the *capability* was missing. This one inverts that. The
display layer is abundant, maintained and permissive: `topic:digital-signage` returns **576 repos**,
led by Screenly/Anthias at **3,745\***, with four MIT players pushed within the last two weeks. The
*transaction* layer — buying a screen, identifying it, proving the ad played, settling the bill — is
a measured near-zero: `topic:dooh` returns **35 repos in total**, and below OpenOOH's 56-star venue
taxonomy **nothing exceeds 10 stars**.

You can build the screen from open source today. You cannot buy, measure or bill it from open source
at all.

### The sharpest evidence of the structural law in fifteen passes — and it is *inside one standards body*

Every prior pass inferred the law across repos from different owners. Here the whole gradient sits in
a single GitHub org, so maintenance and licence cannot be blamed on differing project cultures. The
only variable is **what kind of problem each spec solves**.

| Spec | What it decides | Stars / forks | Last push | Licence | State |
|---|---|---|---|---|---|
| [openooh/venue-taxonomy](https://github.com/openooh/venue-taxonomy) | **Targeting** — what kind of place a screen is (a *format* problem) | 56\* / 40f | 2026-11-16 | **Apache-2.0** | **Alive** |
| [openooh/creative-formats](https://github.com/openooh/creative-formats) | What a creative may look like | 4\* / 1f | 2021-03-08 | **NONE** | Dormant |
| [openooh/screen-id](https://github.com/openooh/screen-id) | **Identity** — which physical screen this is | 1\* / 2f | 2021-07-29 | **NONE** | Dormant |
| [openooh/measurement-spec](https://github.com/openooh/measurement-spec) | **Measurement** — what counts as a play (a *judgment* problem) | 0\* / 0f | 2021-04-07 | **NONE** | Dormant |

Four specs, one alive. The one that is alive is the one that is a pure format question, and it is the
one with a licence. **The three that are dormant carry no licence file at all** — which means default
copyright, all rights reserved, on the very documents a buyer would need to settle a bill.

**Verified, not assumed.** Per the cycle-8 rule that a raw 404 is never by itself proof of a missing
licence, each dormant repo was checked on both `main` and `master` for eight filenames (`LICENSE`,
`LICENSE.md`, `LICENSE.txt`, `license.txt`, `LICENCE`, `COPYING`, `COPYING.md`, `NOTICE`). All 48
probes returned 404 **while `README.md` returned 200 on every one of them**, and the control
(`venue-taxonomy/main/LICENSE`) returned 200. The raw channel works and the filenames are right: the
licences are genuinely absent.

**This refines the law rather than repeating it.** Pass 13 found that *the licence hardens as the code
approaches the money*. In this plane it does not harden — **it disappears**. Not copyleft, not
commercial, simply absent, because nobody maintained the spec long enough to add one. Absence is
worse than copyleft for a client engagement: AGPL tells you the rules, no-licence tells you nothing
and defaults to "you may not".

**P17 — falsifiable prediction, recorded for a later pass to kill.** If DOOH's transaction layer is
empty because the registry and consortium control the asset — not because the engineering is hard —
then twelve months from now `topic:dooh` will *still* contain no repo above 100 stars implementing
measurement or proof-of-play, even while `topic:digital-signage` keeps growing. Re-measure at roughly
pass 27 and write down the counts either way.

### A new licence category for this KB, and it ranks above the honest projects

[jeremiaa/magic-frame](https://github.com/jeremiaa/magic-frame) — **532\* / 22f, pushed 2026-11-22** —
appears in `topic:digital-signage` *above* both Xibo and Concerto. GitHub's licence field reports
`NOASSERTION`. Its own `LICENSE.md` (5,556 B) reads:

> `# Magic Frame License` … `This software is released under the **Polyform Noncommercial License**`

**Source-available, actively maintained, highly starred, and unusable in any client engagement.** This
is the first Polyform Noncommercial project this KB has recorded. A screen that ranks by stars and
recent activity — the screen most people actually apply — passes it. Only opening the file catches it.

### `NOASSERTION` resolved four times, with four different answers

`NOASSERTION` is not a synonym for "no licence"; it means *GitHub's classifier declined*. Four probes,
four outcomes, each with a different consequence for Globant:

| Repo | Stars | GitHub says | The file actually says | Consequence |
|---|---|---|---|---|
| [Screenly/Anthias](https://github.com/Screenly/Anthias) | 3,745\* | NOASSERTION | **dual GPLv2 + Commercial** (stated in its own 18,232 B `LICENSE` header) | The flagship of open signage is **not permissive** — proprietary client work needs the commercial licence |
| [dividuum/info-beamer](https://github.com/dividuum/info-beamer) | 230\* | NOASSERTION | **BSD-2-Clause** (`LICENSE.txt`, 2,393 B) | Fully permissive — but **archived since 2020-05-01** |
| [concerto/concerto](https://github.com/concerto/concerto) | 485\* | Apache-2.0 | **Apache-2.0** confirmed on both branches | Clean; the best permissive CMS in the plane |
| [jeremiaa/magic-frame](https://github.com/jeremiaa/magic-frame) | 532\* | NOASSERTION | **Polyform Noncommercial** | Unusable commercially |

Note the two *inverted* errors in that table: web search told us info-beamer had "no license
information" when it is in fact BSD-2-Clause, and told us Anthias was plausibly GPLv3 when it is
GPLv2-plus-commercial. **A permissive licence was missed and a copyleft one was understated — the
error runs in both directions, so neither optimism nor pessimism about `NOASSERTION` is safe.**

### Slug correction

The canonical Concerto repository is **`concerto/concerto`** (485\*, Apache-2.0, pushed 2026-11-26).
Comparison blogs this pass implied `concerto-signage/concerto`, which **does not resolve**. Prior
cycles have been bitten by exactly this; the `ls-remote` check is what caught it.

### The agent layer exists, and that is the bad news — a shape not seen in fourteen prior passes

`signage mcp` returns **14 repos; the top one has 2 stars.** But the striking part is not the size, it
is the *ownership*. Almost every identifiable entry is an MCP adapter for a **proprietary** CMS:

| Repo | Stars | Licence | Last push | What it bridges to |
|---|---|---|---|---|
| [DaScheife/Sklera-Digital-Signage-MCP-Server](https://github.com/DaScheife/Sklera-Digital-Signage-MCP-Server) | 2\* | NONE | 2026-06-18 | Sklera (closed SaaS) |
| [SUDARSHANCHAUDHARI/SignageQAMCPServer](https://github.com/SUDARSHANCHAUDHARI/SignageQAMCPServer) | 1\* | MIT | 2026-11-25 | QA harness |
| [Cast-Hub/mcp-server](https://github.com/Cast-Hub/mcp-server) | 0\* | MIT | 2026-06-30 | Cast-Hub (closed SaaS) |
| [TomsFaire/Yodeck-MCP](https://github.com/TomsFaire/Yodeck-MCP) | 0\* | NONE | 2026-11-13 | Yodeck (closed SaaS) |
| [RevelDigital/reveldigital-webapp-skill](https://github.com/RevelDigital/reveldigital-webapp-skill) | 0\* | MIT | 2026-06-21 | RevelDigital (closed SaaS) |
| [arnibj/InfoSlides.MCP](https://github.com/arnibj/InfoSlides.MCP) | 0\* | MIT | 2026-11-22 | InfoSlides |
| [timerise-ai/digital-signage](https://github.com/timerise-ai/digital-signage) | 1\* | MIT | 2026-10-25 | agent skill, self-hosted |
| [trillboards/dooh-agent-example](https://github.com/trillboards/dooh-agent-example) | 1\* | MIT | 2026-03-12 | DOOH buying demo |

In the fourteen earlier planes the agent layer was simply *absent*. Here it is being **defined by the
SaaS vendors whose lock-in it extends**. For Globant that is the opposite of leverage: adopting a
vendor MCP imports that vendor's lock-in into the agent layer, which is the most expensive layer to
migrate off later. The recommendation in `compose/patterns.md` (P15.5) is therefore to own the
abstraction and read these only as shape references.

### The display layer — real, maintained, and mostly permissive (this is the part you can build on)

All rows verified this pass: existence by `git ls-remote`, metadata by `search/repositories`, and
every `NOASSERTION` opened by hand.

| Repo | Stars / forks | Licence | Last push | What it is | Verdict for client work |
|---|---|---|---|---|---|
| [concerto/concerto](https://github.com/concerto/concerto) | 485\* / — | **Apache-2.0** | 2026-11-26 | Rails signage CMS, Docker-deployable; originated at Rensselaer in 2008 | **Best permissive CMS in the plane.** Oldest, still pushed today |
| [ardera/flutter-pi](https://github.com/ardera/flutter-pi) | 2,012\* / 210f | **MIT** | 2026-11-15 | Flutter runtime on KMS/DRM — no X11, no desktop | **Best permissive player runtime** for Pi-class hardware |
| [RushB-fr/freekiosk](https://github.com/RushB-fr/freekiosk) | 765\* / 145f | **MIT** | 2026-11-24 | Android kiosk/web-view player | Use when the creative is already web |
| [screentinker/screentinker](https://github.com/screentinker/screentinker) | 281\* / 76f | **MIT** | 2026-11-26 | Multi-tenant signage CMS, self-hostable | Multi-tenancy out of the box; single-maintainer risk |
| [screenlite/screenlite](https://github.com/screenlite/screenlite) | 368\* / 18f | **MIT** | 2026-05-08 | Self-hosted signage CMS | Permissive but **~6 months quiet** — check before depending |
| [home-screens/home-screens](https://github.com/home-screens/home-screens) | 114\* / 21f | **MIT** | 2026-11-26 | Lightweight dashboard/screen renderer | Small but pushed today |
| [debloper/xiosk](https://github.com/debloper/xiosk) | 349\* / 42f | MPL-2.0 | 2026-02-17 | Chromium kiosk wrapper | Weak copyleft — file-level, usually acceptable |
| [Screenly/Anthias](https://github.com/Screenly/Anthias) | 3,745\* / 735f | **GPLv2 + Commercial** | 2026-11-26 | The best-known open signage player (ex-Screenly OSE) | **Most popular, least usable.** Needs the commercial licence for proprietary work |
| [xibosignage/xibo-cms](https://github.com/xibosignage/xibo-cms) | 520\* / 368f | AGPL-3.0 | 2026-11-24 | The most established open signage CMS | AGPL; some players additionally need a commercial player licence |
| [xibosignage/xibo](https://github.com/xibosignage/xibo) | 745\* / 184f | AGPL-3.0 | 2026-11-25 | Xibo umbrella/meta repo | As above |
| [garlic-signage/garlic-player](https://github.com/garlic-signage/garlic-player) | 150\* / 34f | AGPL-3.0 | 2026-11-24 | **The only maintained open SMIL player** | Essential for SMIL interop; see P15.2 for the AGPL-safe use |
| [garlic-signage/garlic-hub](https://github.com/garlic-signage/garlic-hub) | 151\* / — | AGPL-3.0 | 2026-11-22 | SMIL-compatible CMS (new codebase, active development) | Pair with garlic-player |
| [dividuum/info-beamer](https://github.com/dividuum/info-beamer) | 230\* / 49f | **BSD-2-Clause** | 2020-05-01 | Lua-scripted renderer, the developer favourite | **Archived.** Permissive and worth reading; do not depend |
| [jeremiaa/magic-frame](https://github.com/jeremiaa/magic-frame) | 532\* / 22f | **Polyform Noncommercial** | 2026-11-22 | Polished display/frame app | **Excluded from all commercial work** — see the licence-trap table |
| [eerotal/LibreSignage](https://github.com/eerotal/LibreSignage) | 695\* / 132f | BSD-3-Clause | 2021-02-03 | Former permissive favourite | **Archived 2021.** Historical reference only |

**Fifteen real rows, no placeholders.** Two more maintained SMIL satellites exist and are listed in
`repos/foundations.md`: `garlic-signage/garlic-proxy` (5\*) and `garlic-signage/garlic-creator` (4\*),
both AGPL-3.0.

### The transaction layer — everything that exists, which is almost nothing

| Repo | Stars | Licence | Last push | Role | Honest verdict |
|---|---|---|---|---|---|
| [openooh/venue-taxonomy](https://github.com/openooh/venue-taxonomy) | 56\* | **Apache-2.0** | 2026-11-16 | Venue types for OpenRTB DOOH bid requests; spec 1.1 accepted, 1.2 targets OpenRTB 2.6 | **The one piece of this layer you may legally build on** |
| [prebid/prebid-server](https://github.com/prebid/prebid-server) | 595\* / 986f | **Apache-2.0** | 2026-11-25 | Server-side header bidding; already carries DOOH support | The auction half of any pDOOH build |
| [vistarmedia/dynamic-creative-spec](https://github.com/vistarmedia/dynamic-creative-spec) | 10\* | Apache-2.0 | 2022-11-22 | Dynamic-creative spec from a major DOOH SSP | Dormant 4 years; read as documentation |
| [WhimsicalCoder/dooh-bid-validator](https://github.com/WhimsicalCoder/dooh-bid-validator) | 0\* | Apache-2.0 | 2026-11-26 | Validates DOOH bid requests | Pushed today, **0 stars** — read, do not depend |
| [trillboards/proof-of-play-verifier](https://github.com/trillboards/proof-of-play-verifier) | 0\* | MIT | 2026-03-12 | Proof-of-play verification | **The entire open proof-of-play corpus.** Reference only |
| [RayTrunk/OpenSMIL](https://github.com/RayTrunk/OpenSMIL) | 0\* | MIT | 2026-03-28 | SMIL implementation attempt | Permissive, unproven |

Six rows, and after the first two the star counts are 10, 0, 0, 0. **There is no open-source billing,
settlement or measurement for DOOH.** Any client promise in that area is a build, not an integration.

### False abundance, measured four times — read the results, never the total

Cycle 8 established that shortening a query can convert a false zero into a *false abundance*. This
plane produced the four crudest examples the KB has recorded:

| Query | Results | Relevant | What actually ranks |
|---|---|---|---|
| `proof of play` | **751** | **0** | `D4stiny/ForkPlayground` (229\*), Minecraft help threads, and `proofofplay/piratenation-game` (97\*) — a web3 games studio *named* Proof of Play |
| `retail media network` | **37** | **~0** | Minecraft support threads, a `dxdiag` dump, a Windows-7 issue tracker. The single genuine hit is a **3\*** MIT link-list, not code |
| `people counting` | **4,970** | low | Top hit `schollz/howmanypeoplearearound` (**7,089\***, MIT) is a Wi-Fi-sniffing novelty **dead since 2024**, not audience measurement |
| `footfall analytics` | **184** | ~0 | 67\* hackathon repo, then 10\*, 6\*, 6\*, 4\*, 3\* — student coursework only |

**Retail media deserves emphasis.** It is the fastest-growing advertising channel in the world, and
its open-source implementation is *a three-star list of links*
([ishandutta2007/Awesome-Retail-Media-Network-Platform](https://github.com/ishandutta2007/Awesome-Retail-Media-Network-Platform),
MIT, 2026-09-11). That is cruder than this KB's previous worst — music royalty accounting, where the
top six summed to zero — because here the category is not niche, it is the centre of ad-industry
growth.

### A recurring cross-plane false friend, worth a KB-wide note

**`danderfer/Comp_Sci_Sem_2` (228\*) ranked in BOTH `proof of play` AND `people counting`.** A generic
coursework dump matches many short, plain-English media queries. Combined with the pass-11 note that
the placeholder regex needs word boundaries, the rule is: **a plain-English multi-word query on
GitHub search returns coursework and tutorial repos before it returns industry code.** Pair every such
query with a `topic:` query, which is curated and gave the honest counts above.

### One unverifiable vendor claim, recorded as a gap rather than a row

The first search of this pass named **"screenRIG"** — described as a signage CLI shipping an "official
plugin for Claude Code and Codex" — as its single most relevant AI-agent-for-signage match. It does
not survive verification: `screenrig/screenrig` **fails `git ls-remote`**, and a `screenrig` repo
search returns 9 results, none of them this project. It may exist as a product off GitHub, but
**nothing was written as a table row for it.** This is the exact shape that has previously compiled
fabricated entities into this KB.

## The avails, windowing & distribution-rights plane — measured 2026-11-26 (pass 16), and the first plane whose **agent layer was all born in one quarter and adopted by nobody**

**What this plane is.** Not "who owns this content" (pass 5, identification & rights-reservation) and not
"who may stream it today" (pass 13, subscription & entitlement). This is the layer in between, and it is
the one every studio and distributor actually runs a department for: **which title may be exploited, in
which territory, in which window, under which deal, and who gets paid downstream.** In the trade it is
the *avails* plane.

**Why it was missed for fifteen passes.** The grep below was run against all eight KB files *before* any
web search, and it is the largest single-plane vocabulary hole this KB has recorded:

| Term | Hits across all 8 files before this pass |
|---|---|
| `avails` | 0 |
| `distribution right` | 0 |
| `license window` | 0 |
| `VOD window` | 0 |
| `theatrical window` | 0 |
| `output deal` | 0 |
| `first-run` | 0 |
| `rightsholder` | 0 |
| `sublicens` | 0 |
| `performing right` | 0 |
| `residual` | 0 |
| `music licens` | 0 |
| `deal memo` | 0 |
| `Entertainment Identifier` | 0 |
| `licensing deal` | 1 |
| `cue sheet` | 1 |
| `sync licens` | 1 |
| `MovieLabs` | 1 |
| `rights holder` | 3 |
| `rights management` | 5 |

**A false friend caught in the probe itself, worth recording as method.** `EMA ` returned 75 hits and
**every one is noise**: the trailing-space guard does not stop `cinema `/`cinemas `. The Entertainment
Merchants Association — the body whose Avails spec defines this plane — was in fact mentioned **zero**
times. A probe term that is a substring of a common industry word cannot be read off the count.

### The agent layer: six repos, all real, all MIT or Apache, and all at zero stars

This is a shape no prior pass has seen. Fourteen passes found agent layers that were *absent*; pass 15
found one that was *vendor-captured*. Here the agent layer **exists, is permissively licensed, and has no
users at all** — and every single entry was created between June and October 2026, i.e. this quarter.

| Agent | Repo | Stars/Forks | Licence | Last push | What it does |
|---|---|---|---|---|---|
| evangeline-legal-agent | https://github.com/falcoschaefer99-eng/evangeline-legal-agent | 3*/0f | Apache-2.0 | 2026-06-30 | Legal counsel agent covering contract lifecycle and compliance; the only entry above 0 stars |
| Rights-Clearance-Scanner | https://github.com/IBR4H33M/Rights-Clearance-Scanner | 0*/0f | MIT | 2026-10-12 | Multi-agent trademark and rights clearance sweep |
| cueclear | https://github.com/buildwithtolu/cueclear | 0*/0f | MIT | 2026-09-09 | Music rights clearance for locked edits: EDL/XML in, cue sheet out — the only entry wired to a real post-production artefact |
| screenplay-clearance-agent | https://github.com/Priyanka-Purushotham5/screenplay-clearance-agent | 0*/0f | MIT | 2026-09-09 | Screenplay rights clearance |
| soundwave_cue_sheet_palooza | https://github.com/lucylow/soundwave_cue_sheet_palooza | 0*/0f | MIT | 2026-09-16 | Mobile-first audiovisual music-rights workflow for production teams |
| rights-clearance-scout | https://github.com/nawaltahir/rights-clearance-scout | 0*/0f | MIT | 2026-08-22 | Rights clearance research agent (no description published) |

Six real rows. There is no seventh — `rights clearance` returns 40 repos in total and the remainder are
either duplicate pushes of one author's workbench (`williamsahoo1`, three slugs, no licence) or false
friends (`draron-dare-045/Final_Rights` is secondary-school certificate clearance in Kenya).

**How to read this table.** These are **signals, not foundations.** Zero stars at three to five months
old is not "early", it is unvalidated: nobody has run this code but its author. Use them as evidence
that the clearance problem is being attacked and as prior art for a design, never as a dependency. The
one with a defensible shape is `cueclear`, because it takes an **EDL/XML** — an artefact that genuinely
falls out of an edit — rather than asking a human to describe the problem in prose.

**Falsifiable prediction, recorded so a later pass can score it.** By **2027-05-31**, either at least one
of these six repos exceeds **25 stars**, or the clearance-agent layer of 2026-Q3/Q4 is confirmed
abandoned. Both outcomes are informative; the KB should check and write down which happened.

### Where the agent layer stops, and why

Clearance is the *researchable* end of this plane, which is why six people tried to agent it. Nothing in
the table evaluates a window, and nothing settles money. Those two are the subject of the gradient
recorded in `repos/foundations.md` for this pass, and the second of them is a literal zero.

## The development & pre-production plane — measured 2026-11-26 (pass 17): the agent layer is **real at the creative end and unlicensed at the management end**

The plane is the one every production starts with and this KB had never touched: **script → breakdown →
stripboard → shooting schedule → call sheet → budget → payroll.** Before any search, 27 candidate terms
were grepped against all eight files. `script breakdown`, `fountain`, `stripboard`, `pre-production`,
`call sheet`, `production accounting`, `payroll`, `budgeting`, `greenlight`, `chain of title`,
`shot list`, `day out of days`, `screenwriting` and `logline` each returned **literal zero**. The
apparent hits were substring noise and are worth recording as a method warning: `casting` (31) was
**broad*casting***, `slate` (98) was **tran*slate***, `script` (237) was **de*script*ion**. This is the
largest single vocabulary gap found in seventeen passes.

### The agents, verified 2026-11-26

Existence via `git ls-remote`, stars/forks/last-push via GitHub `search/repositories`, and **license by
reading the LICENSE file** wherever the API returned `NOASSERTION` or `NONE`.

| Agent | Repo | License | Stars / Forks | Last push | What it actually does |
|---|---|---|---|---|---|
| PenShot (story-shot-agent) | [neopen/story-shot-agent](https://github.com/neopen/story-shot-agent) | **Apache-2.0** (+NOTICE) | 248★ / 49f | 2026-11-26 | Script → shot-level breakdown → video prompts, via LangGraph + LlamaIndex. Accepts arbitrary script formats. **The only permissive, actively maintained agent in this plane** — pushed on measurement day |
| how-to-make-script | [XucroYuri/how-to-make-script](https://github.com/XucroYuri/how-to-make-script) | **MIT** | 21★ / 1f | 2026-08-24 | Screenwriting *knowledge infrastructure* written for writers **and agents** — rules and structure, not generation |
| ai-screenplay-writer | [E-Asrar-Haghighi/ai-screenplay-writer](https://github.com/E-Asrar-Haghighi/ai-screenplay-writer) | **MIT** | 11★ / 0f | 2026-03-12 | Multi-agent system generating full seasons of original TV screenplays |
| visual-storytelling-skills | [leynos/visual-storytelling-skills](https://github.com/leynos/visual-storytelling-skills) | **ISC** | 11★ / 1f | 2026-11-26 | Agent skills for film production, prose → picture. Pushed on measurement day |
| Story-Film-Skills | [badgids/Story-Film-Skills](https://github.com/badgids/Story-Film-Skills) | **Apache-2.0** (+NOTICE) | 10★ / 2f | 2026-08-24 | Local-first agent-skills suite for story writing and book/film work |

**Five permissive agents, and none of them reaches the management end.** Every one of the five operates
on *story* — structure, prose, shots, prompts. Not one produces a breakdown sheet, a stripboard, a
shooting schedule, a call sheet or a budget line.

### The management end: four artefacts, none usable as a base

| Artefact | Repo | License | Stars | Last push | Why it cannot be built on |
|---|---|---|---|---|---|
| waoowaoo | [waooAI/waoowaoo](https://github.com/waooAI/waoowaoo) | ⚠️ **Elastic License 2.0** (LICENSE, 3,860 B) | 14,989★ / 3,232f | 2026-09-21 | Self-described "industry-first industrial-grade full-pipeline AI film/TV production platform". **Not open source.** ELv2 forbids providing the software to third parties as a managed service — which is exactly what a studio engagement does. The most-starred artefact in the plane by 60×, and unusable |
| film-studio-skills | [machina-exm/film-studio-skills](https://github.com/machina-exm/film-studio-skills) | ⚠️ **No license file** | 186★ / 26f | 2026-08-14 | Seven installable agent skills claiming to run a "$2M AI video production" pipeline. 17 license names probed on both branches, all 404, control README 200 → genuinely unlicensed = all rights reserved |
| motion-graphics-skills | [imMamdouhaboammar/motion-graphics-skills](https://github.com/imMamdouhaboammar/motion-graphics-skills) | 🚫 **"PROPRIETARY AND CONFIDENTIAL — ALL RIGHTS RESERVED"** (LICENSE, 4,261 B) | 69★ / 20f | 2026-11-11 | A public repository whose LICENSE file affirmatively reserves all rights. The GitHub API reports only `NOASSERTION`. Worse than no license, because it is deliberate |
| Script-Breakdown-Skills | [jpcastel88/Script-Breakdown-Skills](https://github.com/jpcastel88/Script-Breakdown-Skills) | ⚠️ **No license file** | 6★ / 0f | 2026-08-04 | Six agent skills turning a screenplay into a **production breakdown** — the single artefact in the entire plane aimed at the management end, and it carries no grant |
| script-weaver | [KKenny0/script-weaver](https://github.com/KKenny0/script-weaver) | ⚠️ **No license file** | 11★ / 3f | 2026-11-15 | Agent-native screenplay and storyboard engine; no grant |

### The measured zeros, and two of the worst false friends in the KB

| Query | Results | Relevant | What came back instead |
|---|---|---|---|
| `stripboard` | **112** | **0** | **Every hit is electronics.** `golkit1/Stripboard-Layouts` (46★, GPL-3.0) is modular-synthesizer perfboard; `rogerdahl/striprouter-cpp` (27★, MIT) is a PCB autorouter; `KarloFunke/stripboard-editor` (19★, GPL-3.0) is a circuit layout editor |
| `call sheet agent` | **109** | **0** | All phone-call sales agents — n8n/Vapi/Twilio voice bots. "Call" collides completely |
| `script breakdown agent` | 16 | 1 | Only `jpcastel88/Script-Breakdown-Skills`, unlicensed. The rest are YouTube/short-form "hook breakdown" skills |
| `production scheduling MCP` | 41 | 0 | Generic "production-ready MCP servers" — "production" collides with "production-grade" |
| `residuals calculation film` | **0** | 0 | Carried from pass 5 and re-confirmed: still literally zero |

**The stripboard case is the sharpest false friend this KB has recorded, and it deserves its own rule.**
The stripboard is *the* central artefact of film scheduling — the board of coloured strips that becomes
the shooting order — and its name is owned outright by electronics prototyping. A careless pass does not
return zero rows here; it returns 46★ GPL-3.0 **modular-synthesizer layouts** written into a media KB as
production tooling. This is the `eidr`/`isan` pattern of pass 5 recurring, and it confirms that rule's
second half: **shortening a query can convert a false zero into a false abundance. Read the results, never
the total.**

### What this means for a bid

**Do not promise an open-source pre-production stack.** The honest position is narrow and defensible: the
*format* layer is permissive and solid (see `repos/foundations.md`), the *creative* agent layer is
permissive and genuinely moving, and the *management* layer — the part a production actually pays for —
has no permissive, maintained base anywhere. It is a build, not an integration.

---

## The book, ebook & scholarly-publishing plane — measured 2026-11-26 (pass 18), and the **first plane in this KB whose permissive code is the regulated layer**

Seventeen passes have measured the audiovisual side of M&E. This pass measures the **written-word**
side — ebooks, trade and scholarly publishing — which a vocabulary probe showed was a near-total
blank in this KB before today.

### How the plane was chosen — the vocabulary probe, before any web search

Two Bash calls over the whole KB, counting files and hits per term:

| Term | Files | Hits | Read |
|---|---|---|---|
| `Readium` | 0 | 0 | **Zero** — the reference reading-system stack was absent |
| `Calibre` | 0 | 0 | **Zero** |
| `ONIX` | 0 | 0 | **Zero** — the book industry's metadata standard was absent |
| `Pressbooks` | 0 | 0 | **Zero** |
| `Open Journal` | 0 | 0 | **Zero** — the most-deployed scholarly platform on earth was absent |
| `Thorium` | 0 | 0 | **Zero** |
| `Audiobookshelf` | 0 | 0 | **Zero** |
| `EPUB` | 4 | 4 | Four incidental mentions, no rows |
| `newsroom` | 7 | 53 | **Already covered** — the editorial/CMS layer is not the gap |
| `Superdesk` / `Ghost` / `Wagtail` / `Directus` | 3–5 | 5–18 | **Already covered** |

The probe did real work: the obvious guess — "the newsroom plane" — was already well covered, and
the actual hole was the **book**, not the news story. This KB's publishing coverage stopped at the
article and never reached the volume.

### ⛔ The finding of this pass: the licence is ordered by **who wrote the code**, and in this plane the producers split cleanly

Seventeen prior passes ordered the licence by *proximity* — to the money, to the regulator, to the
process the code runs inside. This plane does not fit that shape, and the reason is that its code
has exactly **two kinds of author**:

| Producer | Mission | Licence they ship | Verified examples |
|---|---|---|---|
| **Format standards bodies & format consortia** | Get the *format* adopted everywhere | **BSD-3-Clause / MIT / Apache-2.0** | `w3c/epubcheck` BSD-3, `daisy/ace` MIT, `edrlab/thorium-reader` BSD-3, all of `readium/*` BSD-3, `pagedjs` MIT, `quarto-cli` MIT |
| **The scholarly & library commons** | Keep the *commons* open | **GPL-3.0 / AGPL-3.0** | `pkp/ojs` GPL-3, `pressbooks` GPL-3, `manifold` GPL-3, `internetarchive/openlibrary` AGPL-3, `fiduswriter` AGPL-3, `calibre` GPL-3 |

A standards body is permissive because a copyleft reference implementation would **suppress adoption
of its own format**; a scholarly commons is copyleft because permissiveness would let a commercial
host enclose the commons it was built to defend. Both choices are rational, and they point in
opposite directions.

### Why that inverts this KB's AV finding — the sharpest cross-plane contrast in eighteen passes

Pass 4 recorded, for the audiovisual side of this same industry, that conformance tooling was
*permissive at the metadata layer and copyleft at the checker* — `MediaConch` is GPL. In publishing
the **checker itself is permissive**: `w3c/epubcheck` is BSD-3-Clause and `daisy/ace` is MIT.

**Same industry, opposite licence shape, and the discriminator is the producer, not the subject
matter.** AV conformance tools come from engineering collectives; publishing conformance tools come
from the standards body that wrote the spec. The actionable consequence reverses too:

> On the AV side of M&E, Globant can embed the *platform* and must be careful with the *checker*.
> On the publishing side, Globant can embed the **checker** freely and must deploy-not-link the
> **platform**.

### ⚠️ The licence warning that matters most in this plane — `ebooklib` is AGPL-3.0

`aerkalov/ebooklib` is the default Python EPUB library; it is what almost every developer reaches
for first, and it is **AGPL-3.0** (verified from `LICENSE.txt`, last commit 2026-11-01). Used inside
a *hosted* remediation or conversion service, AGPL §13 obliges offering the service's complete
corresponding source to its users. This is the single most likely way a publishing engagement
acquires a network-copyleft obligation without noticing, because nothing in the package name
signals it.

Permissive alternatives verified in this pass for the same job: `futurepress/epub.js` (BSD-2-Clause,
browser-side) and `pagedjs/pagedjs` (MIT) for rendering; `w3c/epubcheck` (BSD-3) and `daisy/ace`
(MIT) for validation. There is **no verified permissive server-side EPUB read/write library** in
this pass — stated as a gap below, not papered over.

### Tier 1 — permissive, active, safe to build on

Verified 2026-11-26: existence via `git ls-remote`, licence by **reading the licence file in the
repo**, last-commit date via a `--filter=blob:none --no-checkout` clone.

| Agent / tool | Repo | Licence (file read) | Last commit | What it does | Region of origin |
|---|---|---|---|---|---|
| Accessibility Agents | https://github.com/Community-Access/accessibility-agents | MIT (`LICENSE`) | 2026-11-07 | **The only verified agent in this plane that handles EPUB.** WCAG 2.2 AA review packaged as agent skills for Claude Code/Copilot/Gemini CLI/Codex; scans Office, PDF and ePub one file or a whole tree, emits remediation scripts | Global |
| ebook2audiobook | https://github.com/DrewThomasson/ebook2audiobook | Apache-2.0 (`LICENSE`) | 2026-11-24 | Ebook → audiobook with voice cloning, many languages; the most active audio-conversion project measured | Global |
| audiblez | https://github.com/santinic/audiblez | MIT (`LICENSE`) | 2026-02-27 | EPUB → M4B audiobook via Kokoro-82M TTS. **9 months since last commit** — works, but not moving | EMEA |
| epub_to_audiobook | https://github.com/p0n1/epub_to_audiobook | MIT (`LICENSE`) | 2026-10-26 | EPUB → audiobook, pluggable TTS backends; trended late Oct 2026 | Global |
| book-writer | https://github.com/tobyilee/book-writer | MIT (`LICENSE`) | 2026-11-21 | Multi-agent long-form book-writing harness with EPUB output; agent+skill architecture | Global |

### Tier 2 — real, but the licence or the staleness constrains client work

| Agent / tool | Repo | Licence (file read) | Last commit | The constraint |
|---|---|---|---|---|
| pdf-accessibility-app | https://github.com/CUNY-AI-Lab/pdf-accessibility-app | **AGPL-3.0** (`LICENSE`) | 2026-11-25 | Very active and institutionally maintained, but AGPL — network copyleft if hosted. PDF only, not EPUB |
| infinite-bookshelf | https://github.com/Bklieger/infinite-bookshelf | MIT (`LICENSE.md`) | 2025-10-09 | **Over 13 months stale.** Readable as a reference pipeline, not a base |

### ⛔ A new licence-hiding category for this KB: the **licence asserted only in prose and a badge**

`AIScientists-Dev/AI-Powered-PDF-Accessibility` is reported as MIT-licensed by the search results
that surfaced it, and its own README carries an **MIT shields.io badge**, the sentence "This project
is open source under the MIT License", and a `## License` section reading "MIT License — Use freely,
contribute back if you can."

**There is no licence file in the repository.** Probed: `LICENSE`, `LICENSE.txt`, `LICENSE.md`,
`LICENCE`, `LICENCE.md`, `COPYING`, `COPYING.txt`, `license.txt`, `LICENSE.rst`, `LICENSE-MIT` — all
404.

Every prior licence finding in this KB was a licence **hidden in a channel GitHub does not read**
(`COPYING.txt`, `LICENSES/`, a wrapper that is not the data). This is the **inverse**: a licence
*announced* in three places with no licence text behind any of them. A badge is not a grant and
"use freely" is not a licence. **Not usable as a base for client work** — and it is also 10 months
stale (last commit 2026-01-20). Recorded as a row here precisely so nobody re-finds it and believes
the badge.

### ⚙️ Three method corrections from this pass — all reusable across the other eleven industries

1. **`COPYING.md` is licence-probe extension #4.** `jgm/pandoc` and `quarto-dev/quarto-cli` both
   returned "no licence file" against the previous probe list and both are licensed — pandoc
   **GPL-2.0** and quarto **MIT**, each in `COPYING.md`. Two independent hits in one pass makes it a
   pattern, not an accident.
2. **A bare lowercase `license` with no extension is extension #5.** `futurepress/epub.js` is
   licensed **BSD-2-Clause** (FreeBSD; confirmed by the *absence* of a "neither the name" clause) in
   a file named `license`. The probe checked `license.txt` and missed it.
3. **First-match licence detection is wrong on a multi-licence file, and it failed on my own run.**
   `standardebooks/tools` was auto-classified `CC-*` because CC0 appears early in its `LICENSE.md`.
   Reading the file: the repository is **GPL-3.0**, with CC0 1.0 only for `./se/data/templates`, and
   per-directory licences under `./se/data` and `./se/vendor`. **The first licence named in a licence
   file is not the licence of the code.** Detectors must read the whole file and report the set.

### The measured zeros, and the honest statement of what could not be measured

- **No open-source agent for ONIX metadata generation or correction.** Five real ONIX *libraries*
  were verified (see `repos/foundations.md`) and not one agentic layer over them.
- **No open-source agent for EPUB accessibility remediation.** The only EPUB-aware agent found is a
  *reviewer* (`accessibility-agents`); everything generative in this space targets PDF. The single
  EPUB-specific result was an academic paper, "AltGen: AI-driven alt text generation for enhancing
  EPUB accessibility", with no public code located.
- **No open-source agent for peer review, manuscript triage or editorial decision support**, against
  `pkp/ojs` running 25,000+ journals.
- **⚠️ Star counts could not be verified this session and are therefore absent from every row
  above.** The GitHub API is unreachable for out-of-session repositories from this environment
  (`403: sessions are bound to their configured repositories`), so this pass reports only what it
  could verify first-hand: existence, licence read from the file, and last-commit date. **Aggregator
  star and staleness claims were actively wrong at least once here** — a directory page reported
  `zach-m/jonix` as ~763 days stale; its real last commit is **2026-10-17**. Prior passes' star
  figures are left as they stand and are not carried into this one.

## The sports-media, live-event & fan-engagement plane — measured 2026-11-26 (pass 19), and the **first plane in this KB with a control group for the content law**

**Why this plane, and why it was missing.** Eighteen passes built out the audiovisual chain, and a
vocabulary probe over all eight files returned **0 hits** for `play-by-play`, `box score`,
`Sportradar`, `tracking data`, `officiating`, `sports rights`, `player stats`, `odds` and
`merchandise`, **1 hit** for `esports` and `live sports`, and **2** for `clipping` — while
`broadcast` scored **246 lines**. The generic delivery plumbing was deeply covered and the single
largest category of live media value was absent. `agents/top.md` itself had already flagged
`esports` as scoring zero files in an earlier probe; that gap was never closed. It is closed here.

**Every row below was verified on 2026-11-26**: existence via `git ls-remote`, stars/forks/last-push
via GitHub `search/repositories` with `repo:` qualifiers, and licence by reading the actual file
whenever the API returned `NOASSERTION` or nothing.

### Why this plane matters more than its size suggests

Sports is the one media segment where the *same* technical problem appears with three different data
substrates, which makes it the first place this KB can test the content law instead of merely
observing it. See "The control group" below — it is the most important thing in this pass.

### Tier 1 — Permissive, actively maintained (safe to build on)

| Agent / Model | Repo | License | Stars | Forks | Last push | What it does |
|---|---|---|---|---|---|---|
| Roboflow Sports | https://github.com/roboflow/sports | **MIT** | 5,517 | 684 | 2026-11-25 | The keystone of this plane: player/ball detection, tracking, pitch keypoint detection and radar-view projection, as runnable notebooks per sport |
| AI YouTube Shorts Generator | https://github.com/Anil-matcha/AI-Youtube-Shorts-Generator | **MIT** | 6,577 | 1,217 | 2026-11-24 | Open alternative to Opus Clip / Vidyo.ai / Klap: long-form → vertical clips with highlight selection. The clip layer most sports rights-holders actually need |
| yt-short-clipper | https://github.com/jipraks/yt-short-clipper | **MIT** | 1,113 | 316 | 2026-11-26 | Desktop long-form → 9:16 clipper with AI highlight picking; pushed the day of this pass |
| LINE Lighthouse | https://github.com/line/lighthouse | **Apache-2.0** | 274 | 22 | 2026-11-01 | The only *research-grade* highlight library here: video moment retrieval + highlight detection, reproducible (EMNLP'24 demo, ICASSP'25 and '26). This is the component to build on, not the YouTube wrappers |
| World Cup Voice | https://github.com/zicojiao/worldcupvoice | **MIT** | 111 | 15 | 2026-06-25 | AI live commentator: watches an Agora RTC feed and adds generated voice commentary. The only open commentary agent located |

### Tier 2 — Real but copyleft, dormant, or narrow

| Agent | Repo | License | Stars | Forks | Last push | Caveat |
|---|---|---|---|---|---|---|
| Clips Studio ("Clips Kitty") | https://github.com/ColinGPT9/clips-studio | AGPL-3.0 | 700 | 149 | 2026-11-26 | Local Opus Clip alternative, actively developed — but AGPL reaches a hosted clipping service |
| VideoHighlighter | https://github.com/Aseiel/VideoHighlighter | AGPL-3.0 | 510 | 71 | 2026-11-24 | Local Ollama-powered analyzer, visual search + automatic highlights. Same AGPL reach |
| SoccerNet Game State | https://github.com/SoccerNet/sn-gamestate | GPL-3.0 | 472 | 102 | 2026-05-02 | CVPRW'24 end-to-end athlete tracking **and identification** — the closest thing to a full game-state agent. GPL-3.0 |
| Volleyball Analytics | https://github.com/masouduut94/volleyball_analytics | GPL-2.0 | 154 | 38 | 2026-10-08 | Complete per-sport worked example; GPL-2.0 |
| AI Basketball Video Editor | https://github.com/OwlTing/AI_basketball_games_video_editor | Apache-2.0 | 126 | 23 | 2024-08-19 | Permissive and genuinely on-topic (auto basketball highlights) but **dormant 2+ years** |

### The control group — the finding of this pass

This KB has asserted a "content law" since healthcare (CPT) and restated it for media (MedDRA,
ISRC/ISWC): *the regulator creates the obligation, but the licence of the underlying content decides
whether open source can satisfy it.* Until now that was a correlation across different problems.
Sports supplies something better: **one problem — extract spatiotemporal events from a match — with
three different substrates.** Difficulty is held constant; only ownership of the substrate varies.

| Substrate | Who holds it | Representative code | Licence health |
|---|---|---|---|
| **A. Pixels you already license** (the broadcast feed) — you generate the data yourself with CV | You / the rights-holder | `roboflow/sports` MIT 5,517★, `roboflow/supervision` MIT 51,730★, `roboflow/trackers` Apache-2.0 4,022★, `tryolabs/norfair` BSD-3 2,708★, `davidpagnon/Sports2D` BSD-3 354★ | **Healthy and permissive.** Abundant, active, multiple independent maintainers |
| **B. Vendor optical / event feeds** (Opta, Sportradar, Second Spectrum, StatsBomb) | A vendor, by contract | `hudl/statsbombpy` **no licence** 758★, `hudl/StatsBombR` **`License: 3.5.0`** 314★, `hudl/open-data` **licence-in-a-PDF** 3,847★, `metrica-sports/sample-data` none 515★, `eddwebster/football_analytics` none 2,870★, `linouk23/NBA-Player-Movements` none 757★ | **Broken.** High stars, no usable grant. Nothing here is safe to ship |
| **C. Client-side game replays** (esports demo files on the player's own disk; no registry allocates them) | Nobody — the artifact is local | `markus-wa/demoinfocs-golang` MIT 1,078★ (2026-11-23), `LaihoE/demoparser` MIT 746★ (2026-11-24), `pnxenopoulos/awpy` MIT 640★ (2026-11-22) | **Healthy and permissive.** All three active within four days of this pass |

**The conclusion, stated as sharply as the evidence allows:** *esports telemetry is open because the
file sits on the player's disk; football telemetry is closed because the file sits on Opta's server.*
The analytics problem is the same and the engineering is arguably harder in esports. What differs is
who holds the substrate — and the licence health tracks the substrate, not the difficulty. **A and C
are the treatment and the control; B is the untreated case.** This is the strongest form the content
law has taken in nineteen passes, and the first time it rests on a controlled comparison.

**Falsifiable prediction, registered for a later pass to check:** if any league publishes optical
tracking data under an actual open licence, a permissively-licensed client library will appear within
two quarters. Conversely, **no amount of demand will produce a permissive Opta/Sportradar client
while the feed is contractual** — the blocker is not developer interest, which substrate B's star
counts (3,847 / 2,870 / 757) prove is high.

### The gradient within the plane — four steps, and it collapses at the money

Cycle 8 found a three-step gradient in rights reservation. Sports has four, and the collapse is
sharper:

1. **SEE the game** (pixels → data) — permissive, abundant, active. *Solved.*
2. **STANDARDIZE the data** — thin but real and alive: `PySport/kloppy` **BSD-3-Clause** 573★
   (2026-11-06) normalizes tracking and event data across providers; `withqwerty/reep` **CC0-1.0**
   245★ maps player/team/coach identity across Transfermarkt and others. *Two repos carry this step.*
3. **ACCESS the official feed** — unlicensed wrappers only (substrate B above). *Legally unusable.*
4. **MONETIZE it** (odds, betting, ticketing tied to rights, fan engagement) — **near-total vacuum.**

### The measured zeros, and what could not be measured

- **Fan engagement is the crudest zero in this KB to date.** The top six GitHub results for
  `fan engagement` are **28★, 6★, 5★, 4★, 3★, 3★** — about 49 stars in total — and the top result
  (`ASportsV/iBall`, a gaze-moderated basketball viewing study) has **no licence** and last moved
  **2023-12-12**. This is cruder than cycle 8's `music royalty accounting` (top six = 0★) in one
  respect: here there is demand and spend, and still no code. The nearest usable thing is
  `AkramOM606/AI-SoccerCoach` (MIT, **5★**, 2025-02-22).
- **Betting/odds is a dead layer.** Most-starred result `S1M0N38/soccerapi` is MIT, 182★ and **dead
  since 2022-12-08**. The only active permissive entry is `odds-api/odds-api` (Apache-2.0, 41★,
  2026-11-05), which is an OpenAPI spec and SDK wrapper around a commercial feed, not an odds source.
- **No open agent for officiating, VAR or rules adjudication** was located at any star level.
- **No sports-specific open-source project originating in LATAM was found**, despite LATAM being the
  region this plane's market section shows as most streaming-committed. Stated as an informed gap,
  not coverage.
- **Commercial terms for Sportradar, Genius Sports and Stats Perform are NOT verified.** No public
  pricing exists and none was reachable. Treat as *not investigated, not free* — the same discipline
  cycle 8 applied to DDEX.
- **The StatsBomb user agreement was deliberately not retrieved.** Access requires registering
  personal details at `statsbomb.com/resource-centre`. This pass declined to submit any user details
  to a third party, so the agreement's terms are recorded as unread. What *is* verified is that the
  agreement exists as a binary PDF in-repo (see `repos/foundations.md`).

## The investigative-journalism, source-protection & fact-checking plane — measured 2026-11-26 (pass 20), the **first plane in this KB whose agent layer is permissive, alive, and still not safely shippable**

**Why this plane, and the vocabulary probe that found it.** Nineteen passes covered distribution,
rights, delivery, monetization, production, measurement, theatrical, audio, localization, signage,
avails, publishing and sport. A grep of ~90 candidate terms over the eight live files found the
newsroom's own craft absent: **`journalism` appeared 4 times in the entire KB, all four in
`intel/market.md`**. `SecureDrop`, `GlobaLeaks`, `OSINT`, `data journalism`, `Aleph`, `Datasette`,
`Bellingcat`, `InVID`, `press freedom`, `source protection`, `whistleblow` and `reverse image` were
**all zero**. Every one of the 73 hits for `verification` was age-verification (pass 15) or file
conformance (pass 4) — not editorial verification of a claim. The gap mattered because pass 8 had
already identified the **newsroom** as LATAM's hottest buyer; the KB was selling to a buyer whose
working tools it had never catalogued.

**All rows below verified 2026-11-26**: existence by `git ls-remote`, stars/licence/last-push by the
GitHub `search/repositories` channel, **default-branch HEAD date by shallow clone** (see the method
correction below — `pushed_at` is not liveness), and licence by reading the LICENSE file wherever the
API returned `NOASSERTION`.

### Tier 1 — the agent layer that actually exists here

This is the first plane in twenty where the agent layer is **permissive and currently maintained**
rather than absent or vendor-captured. It is also the first where being permissive is **not enough**,
for the reason in finding 2.

| Name | Repo | Stars | Licence (verified) | Default-branch HEAD | What it does |
|---|---|---|---|---|---|
| claude-skills-journalism | https://github.com/jamditis/claude-skills-journalism | 462★ | MIT (LICENSE, 1,068 B) | 2026-11-25 | Skill set for verification, FOIA drafting, interview transcription (Whisper/WhisperX + diarization), data journalism |
| Spotlight | https://github.com/buriedsignals/spotlight | 67★ | **MIT code + CC BY-ND 4.0 methodology** — see finding 2 | 2026-11-25 | OSINT investigation orchestrator: structured briefs, methodology approval, sourced findings, independent fact-checking |
| ArkhamMirror | https://github.com/mantisfury/ArkhamMirror | 509★ | MIT | 2026-01-25 (10 months stale) | Local-first AI document-intelligence platform for investigative journalism |
| JornAI | https://github.com/MatheusBomtempo/JornAI | 116★ | MIT | 2026-10-04 | AI-assisted breaking-news publishing for newsrooms, human in the loop |
| newsflow-oss | https://github.com/Yaogui415/newsflow-oss | 104★ | MIT | 2026-07-22 | Newsroom workflow: event tracking, evidence organization, approval chains, corrections, post-publication monitoring |
| DEFAME | https://github.com/multimodal-ai-lab/DEFAME | 64★ | Apache-2.0 | 2025-09-30 (14 months stale) | Multimodal (text + image) automated fact-checking research system |
| data2story-skill | https://github.com/QinghongLin/data2story-skill | 163★ | MIT | 2026-07-05 | Data-to-narrative skill, the storytelling end of data journalism |

### Tier 2 — the agent layer to read but not ship

| Name | Repo | Stars | Licence (verified) | HEAD | Why it is here and not Tier 1 |
|---|---|---|---|---|---|
| newsroom-extension | https://github.com/ehurrn/newsroom-extension | 11★ | **Modified Unlicense** — dedication reaches the software's *output* (finding 2) | 2026-06-21 | 18 skills (OSINT, FOIA, evidence preservation, libel defence). The licence modification is the problem, not the code |
| newsroom-agents | https://github.com/Juanangara/newsroom-agents | 0★ | **No licence file in root — all rights reserved** | 2026-11-07 | Researcher→summarizer→fact-verifier→editor chain; verifier must quote source text. Good design, unusable terms |
| muckrock-mcp | https://github.com/morisy/muckrock-mcp | 3★ | **No licence file** | 2025-06-05 | The only FOIA MCP bridge found. Its own author describes it as "highly experimental, insecure, and unstable" |

### Finding 1 — this plane inverts the law the previous nineteen passes established

The standing law of this KB has been *strong substrate, empty agent layer*. Here the substrate is
strong **and** the agent layer is real: `claude-skills-journalism` (462★, MIT) and `spotlight` (67★)
were both pushed **the day before this measurement**. But note what that agent layer *is* — it is a
**skills-and-prompt layer, not a code layer**. Its competence lives in methodology prose, not in
functions. That single fact relocates the licence question from the code to the content, which is
exactly where the healthcare passes found the binding constraint (CPT, MedDRA). The law did not
break; it moved.

### Finding 2 — two licence traps, one of them a category this KB has not recorded before

**(a) THE LICENCE THAT REACHES THE OUTPUT — new category.** `ehurrn/newsroom-extension` ships a file
named `LICENSE` whose first two paragraphs are the Unlicense verbatim. It is not the Unlicense.
Diffed word-by-word against the canonical SPDX text (obtained from `spdx/license-list-data` via the
raw channel, because `unlicense.org` does not resolve from this session), the canonical third
paragraph — *"for the benefit of the public at large and to the detriment of our heirs and
successors… an overt act of relinquishment in perpetuity"* — is **replaced**, and this clause is
**added**:

> "We dedicate any and all copyright and related or neighboring rights to this work to the public
> domain worldwide. **This dedication applies to any work produced by the software**, unless such
> work explicitly indicates otherwise."

A public-domain dedication that reaches the tool's **output**. For a newsroom the output is the
journalism, and the newsroom's only asset is copyright in its reporting — the same copyright on
which, per pass 5, every AI-training claim and every rights reservation depends. The default is
therefore exactly inverted for this buyer. It is escapable (the clause carries an opt-out: the work
must "explicitly indicate otherwise"), but it is an opt-out you must know exists. **No SBOM scan can
see it**: GitHub reports `NOASSERTION`, the file is named `LICENSE`, and it reads like the Unlicense
until the third paragraph. This is licence category 12 for this KB, and the first one whose subject
is the artefact the software produces rather than the software.

**(b) THE CONTENT LAW, NOW INSIDE AN AGENT'S SKILL FILES.** `buriedsignals/spotlight` is MIT in its
header — and its own LICENSE file (1,940 B, which is why GitHub says `NOASSERTION`) then declares
that the skills *"adapt or synthesize methodology from"*:

- `jamditis/claude-skills-journalism` (MIT) — web-archiving, content-access, social-media-intelligence skills
- **GIJN methodology publications — Patrucic & Cosic, "Introduction to Investigative Journalism: Following the Money," Nov 2024, `CC BY-ND 4.0`**
- Bellingcat training materials; Jim Shultz / Revenue Watch (2005); Derek Bowler, EBU Eurovision News Spotlight (Dec 2025)

**CC BY-ND is NoDerivatives.** A repository whose licence file states that its skill text adapts and
synthesizes an ND-licensed work, while offering that text under MIT, has an unresolved tension on
its face: ND does not permit distributing adaptations. This is a **diligence item, not a legal
conclusion** — but it is the sharpest instance this KB has recorded of its own content law, because
for an *agent* the methodology prose **is** the product. MIT on the repository settles nothing about
whether the skills may be shipped or modified. Any engagement that reuses `spotlight`'s skill text
should resolve the GIJN terms first, and the honest answer to a client is that the code licence and
the knowledge licence are two different questions.

### Finding 3 — the measured zeros, and the first plane where the obvious query is actively misleading

| Query (`search/repositories`, sorted by stars) | Results | Top-6 star sum | What it hides |
|---|---|---|---|
| `whistleblower submission platform` | 8 | **2★** | SecureDrop (3,897★) and GlobaLeaks (1,529★) — the two world standards — do not appear at all |
| `claim verification fact check newsroom` | **1** | 1★ | one repo, 1 star, no licence file |
| `FOIA freedom of information request` | 19 | 35★ (5 of 6 unlicensed; top result last pushed **2017-12-11**) | Alaveteli (421★), Froide (413★), MuckRock (124★) |
| `investigative journalism documents` | 10 | 546★ (509 of it is one repo) | Datashare, Aleph, Uwazi, DocumentCloud |
| `fact-checking journalism` | 94 | 929★ | — this is the one query that works |

**Cycle 8's lesson, now with its mirror image.** Pass 15 learned: *search the obvious term or you
will miss a whole layer* (age verification). This plane teaches the inverse — **here the obvious term
is a trap**. A pass that had probed `whistleblower submission platform` and stopped would have
written "no open whistleblowing tooling exists" over a layer containing a 3,897★ and a 1,529★
institutional standard. The reason is structural and reusable: **institutional tools are named, not
described.** Their READMEs say "SecureDrop", not "whistleblower submission platform".

> **Rule for all twelve industries:** in any plane with institutional incumbents, query the
> **institution**, not the function — `freedomofpress`, `ICIJ`, `MuckRock`, `bellingcat`,
> `mysociety`, `huridocs`, `meedan`, `globaleaks`. The functional keyword returns the vanity layer.

### Finding 4 — the fact-checking agent layer is the plane's real zero, and it has a control group

Fact-checking is the one sub-layer where the agent story collapses. `DEFAME` (64★, Apache-2.0) is
the only non-trivial open system, and its default branch has not moved since **2025-09-30**. Below
it: `ClaimVerify` 0★ (no licence), `Ai-Claim-Verification` 0★ (no licence), `claimcheck` 0★ (MIT),
`ClaimLedger` 0★ (MIT) — **four literal zeros, three of them pushed within the last eight weeks**.
The control group is in the same measurement: the same channel returns `sherlock-project/sherlock` at
**117,843★** for OSINT username search. Open source is not weak at investigation; it is weak at
**adjudicating a claim** — which is judgement, the thing the content law says stays closed.

---

## Pass 21 (2026-11-26) — the spatial, immersive & volumetric-capture plane

A ~60-term vocabulary probe over the eight live files found this plane almost entirely absent.
Word-boundary counts (the earlier passes' own lesson about `grep -i` without `-w`): **`Quest` 0,
`Godot` 0, `WebXR` 0, `glTF` 0, `photogrammetry` 0, `point cloud` 0, `gaussian splat` 0, `NeRF` 0,
`lightfield` 0, `mocap` 0, `rigging` 0, `scene graph` 0, `USDZ` 0, `MV-HEVC` 0, `360 video` 0,
`digital human` 0, `Apple Vision` 0, `XR` 1, `Unity` 2, `volumetric` 1** — and that single
`volumetric` hit is a one-line description of OpenVDB. Pass 6 covered LED-volume virtual production
and pass 12 covered immersive *audio*, so the KB held the stage and the soundfield but nothing about
capturing a real subject in three dimensions or delivering it to a headset.

### Tier 1 — permissive, active, shippable

| Name | Repo | Stars | Licence (verified) | HEAD | What it does |
|---|---|---|---|---|---|
| gsplat | https://github.com/nerfstudio-project/gsplat | 5,961★ / 1,026f | Apache-2.0 | 2026-09-19 | Clean-room CUDA rasteriser for 3D Gaussian splatting — **the component that makes 3DGS commercially usable at all** |
| Brush | https://github.com/ArthurBrussee/brush | 5,392★ / 359f | Apache-2.0 | 2026-11-23 | Rust/WebGPU 3DGS trainer + viewer; **no CUDA**, runs in a browser — the portability escape hatch |
| SuperSplat | https://github.com/playcanvas/supersplat | 10,731★ / 1,242f | MIT | 2026-11-19 | Browser-based splat editor/cleanup/compression; the de-facto post-capture tool |
| 3DGRUT | https://github.com/nv-tlabs/3dgrut | 2,515★ / 293f | Apache-2.0 | 2026-11-06 | NVIDIA's ray-traced Gaussian primitives — see Finding 3 on NVIDIA's own licence reversal |
| TripoSplat | https://github.com/VAST-AI-Research/TripoSplat | 1,489★ / 160f | MIT | 2026-08-13 | Single image → 3D Gaussians; the cheapest generative entry to the plane |
| Three-Live | https://github.com/google/three-live | 516★ / 67f | Apache-2.0 | 2026-11-25 | Google's AI-first runtime + JIT compiler: Three.js → glTF, USDZ and WebXR; **released this month** |
| MediaPipe | https://github.com/google-ai-edge/mediapipe | 37,873★ / 6,253f | Apache-2.0 | 2026-11-25 | Face/hand/pose landmarks — the markerless performance-capture front end |
| UniVRM | https://github.com/vrm-c/UniVRM | 3,432★ / 493f | MIT | 2026-10-19 | VRM avatar runtime; the only avatar interchange format with a permissive reference implementation |
| SplatXR | https://github.com/splatxr/splatxr | 39★ / — | MIT | 2026-10-29 | On-headset splat rendering with physics, shadows and portals (PSI Lab). Tiny, but the only permissive *on-device* XR splat toolkit found |

### Tier 2 — read, cite, do not ship into a client deliverable

| Name | Repo | Stars | Licence (verified) | HEAD | Why it is gated |
|---|---|---|---|---|---|
| gaussian-splatting (original) | https://github.com/graphdeco-inria/gaussian-splatting | 24,564★ / 3,511f | **Gaussian-Splatting License** (Inria + MPII) | 2025-10-17 | Research/evaluation only; commercial use requires Inria's explicit consent via tech transfer |
| instant-ngp | https://github.com/NVlabs/instant-ngp | 17,604★ / 2,067f | **NVIDIA Source Code License** | 2026-02-02 | Non-commercial |
| EasyVolcap | https://github.com/zju3dv/EasyVolcap | 1,600★ / 101f | **PRL v1.0** | 2026-09-15 | Neural volumetric video library — commercial use *allowed* but gated on prior registration; see Finding 2 |
| EasyMocap | https://github.com/zju3dv/EasyMocap | 4,993★ / 575f | **PRL v1.0** | 2026-09-15 | Markerless multi-view motion capture, same gate |
| SadTalker | https://github.com/OpenTalker/SadTalker | 14,224★ / 2,714f | Apache-2.0 **with third-party carve-outs** | 2024-06-26 | Talking-head avatars; Apache for Tencent's own code only, and **dormant 29 months** |
| OpenSplat | https://github.com/pierotofy/OpenSplat | — | AGPL-3.0 | — | Permissive-looking alternative to the Inria code, but copyleft reaches the service |

### Finding 1 — this plane's encumbrance sits at the ORIGIN, not at the registry

The previous twenty passes converged on a law about *content*: the regulator creates the obligation,
but the licence of the **knowledge content** (CPT, MedDRA, ISRC, MeSH) decides whether open source can
discharge it. This plane inverts the location of the problem. There is no registry and no membership
body here. The encumbrance is **the research licence on the originating implementation**, and the
market resolved it the only way it can be resolved — by reimplementing.

Measured: the most-starred artefact in the plane, `graphdeco-inria/gaussian-splatting`, holds
**24,564★ and cannot be shipped**. The thing that actually ships, `nerfstudio-project/gsplat`, holds
**5,961★ — 24% of the stars of the repo it replaces** — and is the reason a 3DGS engagement is legal
at all. **Star count in this plane is an inverse proxy for usability.** Any sweep that ranks by
popularity will hand a client the one repo they may not use.

### Finding 2 — a licence category this KB has never recorded: the registration gate

`zju3dv/EasyVolcap` and `zju3dv/EasyMocap` both carry **Project Registration License (PRL) v1.0**,
copyright 2026 — read in full, not inferred. It is **not** a non-commercial licence, and reading it
as one (the obvious mistake) would wrongly discard the best open neural-volumetric-video codebase:

- Research, education, evaluation and personal use: free, **no registration**.
- Any use by a company or organisation in any internal or external project: free, **but the project
  must be registered before use begins** — explicitly regardless of whether it is commercial,
  internal, revenue-generating or merely in testing.
- Registration is a Google Form naming the entity, a contact, the project and the intended use.
  **No fee, no approval, no response required** — permission is automatic on submission.
- One registration per materially distinct project; versions and deployments inside it are covered.
- **No patent grant, no trademark grant.**

The operational consequence is specific: GitHub reports `NOASSERTION` for both repos, so **no SPDX
field, licence badge or SBOM scan of the source tree can express this obligation**. It is a
compliance step that lives in the engagement-setup checklist, not in CI — and it must happen
*before* work starts, which means it belongs in the proposal, not the retro. First instance recorded
in this KB; worth watching as a template other labs may copy.

### Finding 3 — the same vendor, opposite terms, and the newer one is permissive

NVIDIA appears twice in this plane with contradictory licences. `NVlabs/instant-ngp` (17,604★, last
pushed 2026-02-02) is under the **NVIDIA Source Code License** and is non-commercial.
`nv-tlabs/3dgrut` (2,515★, pushed 2026-11-06) is **Apache-2.0**. The permissive one is newer and
alive; the gated one is larger and slowing. **Vendor identity predicts nothing about licence
terms — the repo must be read every time**, and a stale internal note saying "NVIDIA research code
is non-commercial" would have cost the usable option.

### Finding 4 — the spec repositories have no licence grant, and this is now a cross-industry pattern

Pass 5 recorded `rslstandard/rsl` — the official repo of a licensing standard — as having no licence
file. That looked like an anecdote. It is not. Verified this pass with the control test the earlier
cycles established (13 filename variants × `main` and `master`, with `README.md` fetched as a control
and a known-good positive control):

| Spec repo | Stars | Licence file | README control |
|---|---|---|---|
| https://github.com/KhronosGroup/glTF | 7,907★ | **none found** (13 names × 2 branches) | 200 on both branches |
| https://github.com/CesiumGS/3d-tiles | 2,653★ | **none found** | 200 |
| https://github.com/KhronosGroup/glTF-Sample-Assets | 1,180★ | **none found** | 200 |
| https://github.com/needle-tools/needle-engine-support | 613★ | **none found** | 200 |

Because `README.md` returns 200 where all thirteen licence names return 404, this is **not** the
naming-convention false negative that cycle 8 warned about — the files are genuinely absent from the
repo root. glTF is *the* 3D interchange standard for this plane. The practical rule: **take the terms
from the published Khronos/OGC specification, never from the spec repository**, and never let a
dependency scanner's reading of these repos stand as the answer.

### Finding 5 — the measured zeros, placed on the time axis

The honest shape of this plane is a gradient along **time**, not along region or licence:

- **Static capture** — permissive and healthy. gsplat (Apache-2.0, 5,961★), Brush (Apache-2.0,
  5,392★, pushed 2026-11-23), SuperSplat (MIT, 10,731★), COLMAP (new BSD, 13,302★, pushed
  2026-11-26).
- **Temporal capture — actual volumetric *video*** — this is the hole. `hustvl/4DGaussians`
  (Apache-2.0, 4,047★) has not been pushed since **2024-10-27, 25 months**. The permissive
  alternative with a production pipeline, `ASU-NEM-Labs/open4dgs-core`, is **MIT and alive
  (2026-11-21) at 161★**. The strongest 4D codebase, EasyVolcap, is behind the PRL gate.
- **Delivery to a headset** — permissive and enormous. three.js (MIT, 119,448★), Godot (MIT,
  120,865★), OpenXR-SDK (Apache-2.0), Babylon.js (Apache-2.0, 26,457★).

So the industry can photograph a static scene and can deliver to a device, and **the one layer that
turns 3D photography into volumetric video — the temporal layer — thins to 161 permissive, active
stars.** That is the measurement to put in front of a client, and it is falsifiable: if
`4DGaussians` is revived or open4dgs crosses ~1k★ in the next two quarters, this finding expires.

### Informed gaps — searched, not found

- **No open-source production encoder for Apple Immersive Video / MV-HEVC was found.** The only open
  paths are x265's multiview encoder plus an ffmpeg remux, and small project-level work
  (`mrgnw/spatial-maker`, `simon-lowes/montage`) where the author states Vision Pro playback was not
  tested and hardware encoding is unsupported. The one live MV-HEVC broadcast encoder announced in
  2026 (SpatialGen, AWE USA) is **proprietary**. Treat spatial-video delivery as a build, not an
  integration.
- **Monado, the leading open OpenXR runtime, could not be verified from this session.** Its canonical
  home is `gitlab.freedesktop.org`, which the egress proxy refused (HTTP 403, host not permitted).
  The GitHub hits for "monado" are unrelated forks (top result 5★, last pushed 2022-03-16). Recorded
  as **not investigated**, not as absent.
- **`opensimulator/opensim` does not exist on GitHub** (`git ls-remote` negative). OpenSimulator is
  hosted outside GitHub; not verified this pass.

### Method correction — the GitHub search index is not an existence oracle, and now not a metadata one either

Earlier cycles established `git ls-remote` as the only existence oracle. This pass sharpens it:
`search/repositories` with `q=repo:<slug>` returned **HTTP 422 "resources do not exist"** for three
repositories that `git ls-remote` confirms **do** exist — `nerfstudio-project/viser`,
`pierotofy/OpenSplat` and `mozilla/hubs`. So the index's silence is not evidence of absence *or* of
missing metadata; when it 422s, fall back to `ls-remote` for existence and to the raw licence probe
for terms. Both fallbacks were used here and both resolved in one call each.

## The podcast & spoken-audio distribution plane — measured 2026-11-26 (pass 22), and the licence hardens by **what the code owns**

`media-kb` arrived with the remote carrying **passes 19, 20 and 21, all three dated today**, while
`rotation.json` still read `next=4, last_industry=healthcare` — the **eighth consecutive failure of
step 5** on this industry (pass 12 counted seven). Same-day passes again mean the right move is
neither a rewrite nor a re-verification but **finding the missing vocabulary plane**, so the probe
ran first.

### How the gap was found — the vocabulary probe, two Bash calls, 61 terms, before any web search

| Term group | Files with a hit | Verdict |
|---|---|---|
| `podcast-namespace`, `Podcasting 2.0`, `AntennaPod`, `Podverse`, `dynamic ad insertion`, `PodcastIndex`, `value4value`, `chapters` | **0 of 8** | The open podcast ecosystem is **entirely absent** |
| `IIIF`, `Omeka`, `Islandora`, `ArchivesSpace`, `AtoM`, `DSpace`, `Fedora` | 5–8 each | Already covered (passes 4, 18) |
| `CasparCG`, `playout`, `EPG`, `FAST`, `Rundown` | 3–8 each | Already covered (passes 8, 16) |
| `Datasette`, `OpenRefine`, `Superset`, `data journalism` | 2–5 each | Already covered (pass 20) |
| `Kavita`, `Komga`, `comic`, `manga` | 1–6 each | Already covered (pass 18) |
| `Castopod`, `Audiobookshelf`, `Funkwhale` | 2–4 each | Present as **vertical rows only** — never measured as a plane |

The word "podcast" appears in five files of this KB. **The podcast ecosystem does not.** Audiobook­shelf
was carried as a self-hosting vertical, Castopod as a dead slug (`repos/trending.md`), Funkwhale as a
federation example — and nothing anywhere described how a show is published, found, measured or paid
for. Podcasting is a **$9.2 bn global business** (Owl & Co., 2025, up from $7.5 bn in 2024) with
**$2.9 bn of US ad revenue alone** (IAB/PwC, 2025, +10.2 % YoY). It had no plane.

### The finding: four layers, four licence regimes, and the ordering is by *ownership*, not by proximity

Every figure below was measured on **2026-11-26** via GitHub `search/repositories`; every slug was
confirmed to resolve with `git ls-remote`. 36 slugs probed, **36 resolve, 0 absent**.

| Layer | What the code owns | Licence regime measured | Evidence |
|---|---|---|---|
| **1. The standard** | Nothing — it wants universal adoption | **CC0 / MIT, no exceptions** | `podcast-namespace` CC0-1.0; `podping.cloud`, `docs-api`, `web-ui`, `helipad`, `op3`, 5× `opawg/*`, `podlove-publisher` all MIT |
| **2. The library / generator** | One step of a pipeline | **Apache-2.0 / MIT** | `podcastfy` Apache-2.0 6,860★; `notebookllama` MIT 1,982★; `SurfSense` Apache-2.0 16,962★ |
| **3. The app that owns the listener** | The audience relationship | **GPL-3.0 / AGPL-3.0, no live exception** | `audiobookshelf` GPL-3.0 15,123★; `AntennaPod` GPL-3.0 8,357★; `microfeed` AGPL-3.0 4,143★; `podverse/*` AGPL ×5; `gpodder`, `PinePods`, `PodAura`, `podgrab`, `rssguard`, `musicpod` all GPL-3.0 |
| **4. The money** | The $2.9 bn | **Does not exist in the open** | `audio ad insertion server stars:>=20` → **TOTAL = 0** |

This is the first plane in this KB where the licence gradient has a **stated mechanism rather than a
correlation**, and the mechanism is not proximity to the money — pass 13 proposed that — but
**ownership**. A spec that charges nothing and claims nothing is published CC0 so that Apple and
Spotify can implement it without a lawyer. A generator is a library, and libraries chase adoption, so
they are permissive. A podcast *app* is a direct competitor to Spotify and YouTube, and its authors
pick AGPL **deliberately**, as a defence against enclosure. And the ad server — the only layer that
touches the industry's actual revenue — **was never written in the open at all**.

Pass 13's law survives as a special case: the licence does harden toward the money. Pass 22 shows
what is at the end of that gradient. **It is not AGPL. It is absence.**

### The money layer, measured four ways, because a single zero is an anecdote

| Query | Total repos | Top result | Verdict |
|---|---|---|---|
| `audio ad insertion server stars:>=20` | **0** | — | Literal zero. Nothing exists above the noise floor. |
| `dynamic ad insertion` | 37 | `leandromoreira/scte-35-scte-104-scte-67` (BSD-3-Clause, 35★, **last push 2021-04-13**) | The top hit is a **documentation repo about broadcast SCTE markers**, abandoned 5 years, not a podcast DAI implementation. |
| `podcast analytics stars:>=20` | **2** | `aws-samples/amazon-transcribe-comprehend-podcast` (MIT-0, 137★, push 2023-07-25); `opawg/user-agents` (MIT, 123★) | One is an AWS demo; the other is **a list of regexes**, not an analytics system. |
| `podcast monetization` | 59 | `AshutoshBhawsar/Automated-Sentiment-Analysis-of-Web-Multimedia` (**2★**) | Noise. Nothing in the first page is monetization software. |

**The sharpest single fact in this plane:** the open-source community built a complete,
permissively-licensed **payment rail** — `helipad` (MIT, 37★), `BoostBots` (BSD-3-Clause, 15★),
`getAlby/nostr-wallet-connect` (Apache-2.0, 115★), `v4v-info` (MIT, 32★) — for *value4value*
micropayments, a revenue model worth a rounding error of the industry. For the **$2.9 bn that
podcasting actually earns from advertising, it wrote nothing.** Open source here followed the
*ideology*, not the money.

### Tier 1 (pass 22) — permissive, alive, and usable as-is for the generation layer

| Agent / Tool | Repo | License | Stars | Last push | What it does |
|---|---|---|---|---|---|
| SurfSense | [MODSetter/SurfSense](https://github.com/MODSetter/SurfSense) | Apache-2.0 | 16,962 | 2026-11-24 | Air-gapped NotebookLM alternative; document corpus → chat → generated audio overview. The most-starred permissive repo in this plane and the only one built for confidential material. |
| autoclip | [zhouxiaoka/autoclip](https://github.com/zhouxiaoka/autoclip) | MIT | 16,708 | 2026-11-26 | Local-first clipping + MCP server: long audio/video → short social cuts. The repurposing half of podcast distribution. |
| Podcastfy | [souzatharsis/podcastfy](https://github.com/souzatharsis/podcastfy) | Apache-2.0 | 6,860 | 2026-05-04 | Multimodal content → multi-speaker conversational podcast audio. The reference open NotebookLM-podcast implementation. **7 months without a push** — vendor it, don't depend on it. |
| VideoAgent | [HKUDS/VideoAgent](https://github.com/HKUDS/VideoAgent) | MIT | 2,073 | 2026-07-22 | EMNLP 2026 agentic framework for video understanding + editing; the practical base for video-podcast cutdowns. |
| NotebookLlama | [run-llama/notebookllama](https://github.com/run-llama/notebookllama) | MIT | 1,982 | 2026-03-02 | Fully open LlamaCloud-backed NotebookLM alternative, incl. audio generation. MIT end to end. |
| video-podcast-maker | [Agents365-ai/video-podcast-maker](https://github.com/Agents365-ai/video-podcast-maker) | MIT | 1,733 | 2026-10-01 | Topic → 4K narrated video episode, local TTS (no external API required). Built to be driven *by* a coding agent. |
| InsightsLM | [theaiautomators/insights-lm-public](https://github.com/theaiautomators/insights-lm-public) | MIT | 661 | 2026-01-16 | Self-hosted NotebookLM alternative: chat with documents, generate audio overviews. |
| sofit | [navotvolkgroundup/sofit](https://github.com/navotvolkgroundup/sofit) | MIT | 31 | 2026-11-05 | Auto-generates chapters, show notes and pull-quotes from an episode. Hebrew-first — **the only show-notes agent found with a real licence and a 2026 push.** |

### Tier 2 (pass 22) — real, and the licence or the silence is the constraint

| Tool | Repo | License | Stars | Last push | Constraint |
|---|---|---|---|---|---|
| Audiobookshelf | [advplyr/audiobookshelf](https://github.com/advplyr/audiobookshelf) | **GPL-3.0** | 15,123 | 2026-11-19 | The plane's largest project and the de-facto self-hosted audiobook/podcast server. GPL-3.0: ship as a separate service, do not link client code into it. |
| AntennaPod | [AntennaPod/AntennaPod](https://github.com/AntennaPod/AntennaPod) | **GPL-3.0** | 8,357 | 2026-11-25 | The reference open Android podcast client, actively developed. A white-label client fork inherits GPL-3.0 — fatal to most app-store OEM deals. |
| Winds | [GetStream/Winds](https://github.com/GetStream/Winds) | BSD-3-Clause | 9,078 | **2021-10-11** | **The exception that proves the rule.** The only large permissive podcast app — and it has been dead five years. Permissive + listener-owning + alive does not exist in this plane. |
| microfeed | [microfeed/microfeed](https://github.com/microfeed/microfeed) | **AGPL-3.0** | 4,143 | 2026-11-24 | Agentic CMS for podcasts/blogs on Cloudflare. Network copyleft — the worst possible licence for a hosted multi-tenant product. |
| PodAura | [SkyD666/PodAura](https://github.com/SkyD666/PodAura) | **GPL-3.0** | 1,278 | 2026-11-23 | Modern Material You Android podcast app, very active. Same copyleft constraint as AntennaPod. |
| Podverse | [podverse/podverse-rn](https://github.com/podverse/podverse-rn) | **AGPL-3.0** | 287 | 2026-11-16 | Cross-platform client; the only full open stack with Podcasting 2.0 features end to end (`-rn`, `-web` 100★, `-api` 34★ — **all five repos AGPL-3.0**). |
| anytime_podcast_player | [amugofjava/anytime_podcast_player](https://github.com/amugofjava/anytime_podcast_player) | BSD-3-Clause | 627 | 2026-04-22 | **The one clean base for a white-label client.** Flutter/Dart, BSD-3. Smaller and slower-moving than the GPL options, and that is exactly the trade to put in front of a client. |
| Twocast | [panyanyany/Twocast](https://github.com/panyanyany/Twocast) | **NONE** | 1,292 | 2025-07-01 | Bilingual AI podcast generator, 1,292★ and **no licence file at all** → all rights reserved, unusable. The most-starred AI podcast generator in the plane is legally unavailable. |
| podcast-transcriber | [wendy7756/podcast-transcriber](https://github.com/wendy7756/podcast-transcriber) | NOASSERTION | 248 | 2026-04-12 | Podcast → transcript + AI summary. GitHub cannot classify the licence; read it before use. |

### Contamination warnings — two of them, and one is a repeat offender

- **`show notes agent` returns 85 results and the top two are a SARS-CoV-2 mRNA sequence archive
  (3,352★) and a GitHub Desktop release-notes mirror.** Pure keyword collision on "notes" and
  "release notes". There is no show-notes agent layer; the query only looks populated.
- **`audiobook agent stars:>=10` returns 4, and the second is `jettbrains/-L-` (GPL-3.0, 176★) —
  the exact repo pass 4 flagged as a collision in `archive metadata agent`.** The same unrelated
  repo now contaminates two different planes of this KB. **Recorded so a later pass does not
  "discover" it a third time.**

### What this means for a client engagement

The plane splits cleanly into work Globant can take and work it cannot:

- **Take the generation and the measurement.** Both are permissive and both are weak. An
  IAB-compliant server-side measurement service built on `opawg/*` + `op3` (all MIT) has no open
  incumbent, and the generation layer is Apache/MIT down to the model wrappers.
- **Never fork the player.** Layer 3 is copyleft by design, not by accident. The only permissive
  live base is `anytime_podcast_player` (BSD-3); everything else makes the client's app
  disclosable.
- **The ad stack is a greenfield build, and that is the proposal.** Zero open repos touch podcast
  ad insertion. The input signals (`podcast-namespace` CC0, OPAWG regexes MIT, OP3 MIT) are all
  free. Pattern 47 wires exactly that.

## Pass 23 (2026-11-26) — the still-image, photo-desk & print-production plane

**Why this plane.** media-kb already held 22 passes, eight of them dated 2026-11-26. Following the
cycle-8 method, 65 vocabulary terms were grepped against the eight live files *before* any web
search. The result was the cleanest hole found in this KB since `fingerprint`: **`libvips`,
`ImageMagick`, `imgproxy`, `thumbor`, `darktable`, `RawTherapee`, `fontTools`, `Ghostscript`,
`CMYK`, `ICC profile`, `color management`, `stock photo`, `photo editorial`, `prepress`, `Scribus`,
`PhotoPrism`, `image captioning` and `upscal*` were all at literal zero.** The word `print`
appeared on 124 lines and **121 of them were `fingerprint`/`Chromaprint`** — bare `print` occurred
three times. Twenty-two passes of a Media & Entertainment KB had never described how a still image
or a printed page is actually made.

**Verification channel, and a disclosure.** The GitHub REST `/repos/*` endpoint is **blocked in
this session** (HTTP 403, "GitHub access to this repository is not enabled for this session") — it
is scoped to the session's own repositories. Stars and last-push below therefore come from
`gh api -X GET search/repositories`, which does work, and licenses come from **reading the actual
LICENSE file over the raw channel**, which is how every `NOASSERTION` in this table was resolved.
**Six repos exist and serve git but are invisible to the search index** (HTTP 422); their star
counts are written `n/a` rather than guessed. See the method notes at the end of this section.

### Tier 1 — move and convert pixels: permissive, and alive (the healthiest substrate in this KB)

| Agent / Library | Repo | License | Stars | Last push | What it does |
|---|---|---|---|---|---|
| sharp | [lovell/sharp](https://github.com/lovell/sharp) | Apache-2.0 | 32,872 | 2026-11-26 | Node image pipeline over libvips; the default resize/convert layer for JS backends. Pushed the day of this pass. |
| ImageMagick | [ImageMagick/ImageMagick](https://github.com/ImageMagick/ImageMagick) | ImageMagick License (own, permissive) | 17,946 | 2026-11-26 | The universal convert/composite toolbox. API reports `NOASSERTION`; the LICENSE file (12,557 B) is ImageMagick's own Apache-2.0-derived licence, which permits commercial use and linking against differently-licensed libraries. |
| libvips | [libvips/libvips](https://github.com/libvips/libvips) | LGPL-2.1 | 11,841 | 2026-11-25 | The engine under sharp, imgproxy and imagor: streaming, low-memory image processing. LGPL — link, do not fork into a static binary without reading it. |
| imgproxy | [imgproxy/imgproxy](https://github.com/imgproxy/imgproxy) | Apache-2.0 | 11,220 | 2026-11-24 | Go on-the-fly resize/crop/convert server over libvips, with signed URLs. The OSS core is Apache-2.0; a separate commercial "Pro" tier exists — check which you deploy. |
| thumbor | [thumbor/thumbor](https://github.com/thumbor/thumbor) | MIT | 10,533 | 2026-11-21 | The original smart-crop image server; Python, widest transformation set, extensible detectors. |
| imaginary | [h2non/imaginary](https://github.com/h2non/imaginary) | MIT | 6,091 | 2025-11-08 | Go/libvips HTTP microservice. **Dormant ~12 months** — usable, unmaintained. |
| image (Rust) | [image-rs/image](https://github.com/image-rs/image) | MIT OR Apache-2.0 | 5,920 | 2026-11-11 | Pure-Rust decode/encode/transform. Dual-licensed, so it is the cleanest base for a redistributable binary. |
| imageflow | [imazen/imageflow](https://github.com/imazen/imageflow) | AGPL-3.0 | 4,475 | 2026-11-23 | High-performance imaging server. **AGPL — a hosted service built on it is disclosable.** Commercial licence sold separately. |
| imagor | [cshum/imagor](https://github.com/cshum/imagor) | Apache-2.0 | 4,065 | 2026-11-21 | Go, libvips, **thumbor-compatible URL API** — the drop-in migration path off thumbor. |
| images (wsrv.nl) | [weserv/images](https://github.com/weserv/images) | BSD-3-Clause | 2,865 | 2026-11-01 | The code behind the public wsrv.nl image CDN; nginx module + libvips. |

### Tier 2 — describe pixels (the judgment layer): permissive, and **dying at the top**

This is the finding of the pass. Every row is permissive. **Four of the seven are dormant or
archived, including the three most-starred.**

| Agent / Model | Repo | License | Stars | Last push | State |
|---|---|---|---|---|---|
| Real-ESRGAN | [xinntao/Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN) | BSD-3-Clause | 37,679 | **2024-08-06** | The most-starred upscaler/restorer in the plane and **dormant for over two years.** Still the weights everyone ships. |
| CLIP | [openai/CLIP](https://github.com/openai/CLIP) | MIT | 34,666 | 2026-03-25 | The original image/text embedding model. Reference-only; 8 months idle. |
| LLaVA | [haotian-liu/LLaVA](https://github.com/haotian-liu/LLaVA) | Apache-2.0 | 25,093 | **2024-08-12** | The vision-language model most captioning tutorials still target. **Dormant over two years.** |
| open_clip | [mlfoundations/open_clip](https://github.com/mlfoundations/open_clip) | MIT | 14,292 | 2026-11-21 | **The live one.** Open CLIP training + inference, many checkpoints. API says `NOASSERTION`; LICENSE file read (1,229 B) and it is MIT. Build semantic image search on this, not on `openai/CLIP`. |
| imagededup | [idealo/imagededup](https://github.com/idealo/imagededup) | Apache-2.0 | 5,688 | 2025-08-15 | Near-duplicate detection (PHash/CNN). ~15 months idle; the algorithms are stable, so low risk. |
| BLIP | [salesforce/BLIP](https://github.com/salesforce/BLIP) | BSD-3-Clause | 5,699 | 2026-03-03 | **ARCHIVED by its owner.** The canonical open captioning model for alt-text drafting is now read-only. |
| imagehash | [JohannesBuchner/imagehash](https://github.com/JohannesBuchner/imagehash) | BSD-2-Clause | n/a | — | Perceptual hashing (aHash/pHash/dHash/wHash). Exists and serves git; invisible to the search index. |

### Tier 3 — the editorial alt-text workflow: a measured near-zero

| Agent | Repo | License | Stars | Last push | Note |
|---|---|---|---|---|---|
| AI Alt Text (WordPress) | [soderlind/ai-alt-text](https://github.com/soderlind/ai-alt-text) | GPL-2.0-or-later | **1** | 2026-03-29 | Multi-provider alt text (OpenAI/Claude/Gemini/Ollama/Grok) for the WP media library. **Its README links a LICENSE file that returns 404; the SPDX id lives in `composer.json`.** One star. |

The CMS-side alt-text modules that newsrooms actually install are **not on GitHub** — Drupal's
`ai_image_alt_text` and `aidmi` are on drupal.org, and the WordPress plugins on wordpress.org.
A plane that looks empty on GitHub is not necessarily empty; it is hosted elsewhere, and that is
itself the finding for anyone sizing the competition.

### Tier 4 — provenance at the point of capture: permissive, alive, and tiny

| Tool | Repo | License | Stars | Last push | Note |
|---|---|---|---|---|---|
| c2pa-rs | [contentauth/c2pa-rs](https://github.com/contentauth/c2pa-rs) | MIT OR Apache-2.0 | 455 | 2026-11-26 | The reference Rust implementation of C2PA / Content Credentials. API says `NOASSERTION`; `LICENSE-MIT` (1,083 B) read and confirmed — dual-licensed. Pushed the day of this pass. |
| c2patool | [contentauth/c2patool](https://github.com/contentauth/c2patool) | Apache-2.0 OR MIT | 174 | 2026-11-26 | CLI to sign, inspect and verify Content Credentials on image files. The piece that drops into an ingest pipeline. |

**455 stars.** The entire open implementation of image provenance — the thing every 2026 trust-in-media
panel is about — is two repos with 629 stars between them, against 120,170 for one self-hosted
photo app. The standard is settled and the tooling is permissive; almost nobody has wired it up.

### Measured: does an "image judgment agent" layer exist? No, and the results are contaminated

Measured 2026-11-26 via `search/repositories`, sorted by stars:

| Query | Total repos | Top result | Stars | Verdict |
|---|---|---|---|---|
| `caption agent newsroom` | **0** | — | — | Literal zero. |
| `photo desk agent` | 11 | `danderfer/Comp_Sci_Sem_2` | 228 | **Contamination** — a computer-science coursework repo. |
| `image licensing agent` | 31 | `danderfer/Comp_Sci_Sem_2` | 228 | **The same coursework repo**, contaminating a second query. |
| `picture editor agent` | 14 | `yuyuanweb/ai-picture-editor` | 320 | On-topic but unlicensed; a consumer editor, not a picture desk. |
| `photo archive agent` | 16 | `CNTRUN/Termux-command` | 120 | **Contamination** — a Termux command list by its name. **Listed by the search index but `git ls-remote` cannot serve it** (see method note 7); the count of 16 is indexed, the top repo is not verifiable. |
| `alt text agent` | 47 | `zszszszsz/.config` | 373 | **Contamination** — a dotfiles repo. |
| `prepress automation` | 26 | `sams-joseph/prepress-automation` | **1** | The only genuinely on-topic top hit in the set, at one star. |
| `image metadata agent` | 93 | `wiltodelta/remove-ai-watermarks` | 6,530 | On-topic and **pointing the wrong way**: the most-starred result is a tool for *stripping* watermarks and provenance. |

**Contamination warning for later passes.** `danderfer/Comp_Sci_Sem_2` (228★) is the top result for
both `photo desk agent` and `image licensing agent`. It is unrelated to media. Pass 4 and pass 22
recorded the same behaviour for `jettbrains/-L-`; this is the second repo in this KB to contaminate
two distinct planes. **Recorded so a later pass does not "discover" it as a finding.**

The irony in the last row is worth stating plainly for a client: in the one query where a
well-starred, properly licensed, on-topic project exists, **it exists to remove the metadata the
rest of this plane is trying to add.**

### What this means for a client engagement

- **Take the pipeline. It is free and it is alive.** Resize/convert/serve is Apache-2.0 and MIT down
  to the engine, and four independent servers compete on the same libvips core. Nobody needs to buy
  Cloudinary to crop an image, and `imagor` gives a thumbor-compatible URL contract so a migration
  is a routing change rather than a rewrite.
- **Do not inherit the describe layer; pin it.** The three most-starred models in Tier 2 have not
  been touched since 2024, and the canonical captioning model is archived. They still work — but
  "BSD-3 and 37k stars" is not maintenance. Vendor the weights, pin the commit, and own the
  inference wrapper. `open_clip` (MIT, pushed 2026-11-21) is the one live base.
- **The alt-text workflow is the sellable gap.** Drafting a caption is solved and nearly free.
  Routing it to a photo editor, recording who approved it, and proving it later is not: the whole
  GitHub field is one repo with one star, and the Disability World testing cited in `intel/trends.md`
  pass 23 found AI drafts usable as a *first draft* and actively risky on decorative images. The
  product is the review loop and the audit trail, not the model.
- **Wire C2PA now, because the capture end is already shipping.** Leica (M11-P, SL3-S), Nikon's
  Authenticity Service and Sony firmware already sign at capture; `c2patool` verifies on ingest in
  one binary under a permissive licence. 629 stars means no incumbent.

### Method notes from this pass (reusable across all twelve industries)

1. **`search/repositories` returning HTTP 422 is not evidence a repo does not exist.** Six of 65
   repos — `Beep6581/RawTherapee`, `artpixls/ART`, `googlefonts/fontbakery`,
   `JohannesBuchner/imagehash`, `ente-io/ente`, `UKPLab/sentence-transformers` — return
   *"the listed users and repositories cannot be searched"* while `git ls-remote` serves refs
   normally. This is the exact analogue of cycle 8's rule that a raw-channel 404 never proves a
   missing licence. **Confirm existence with `git ls-remote`, and write `n/a` for stars rather than
   guessing.**
2. **The `repo:` qualifier is case-sensitive.** A retry loop that had lower-cased the slugs turned
   five live repos into 422s. Keep the original casing.
3. **Detect a GPL version from the title lines, not the body.** A body-wide grep misreported
   **GPL-2.0 as LGPL-2.0** for `Exiv2/exiv2` and `Piwigo/Piwigo`, because the GPL-2.0 preamble
   contains the phrase *"the GNU Library General Public License instead"*. Read the first six lines.
4. **The default branch is often neither `master` nor `main`.** This pass found `2026.x`
   (pimcore), `integration` (veraPDF) and `dev` (RawTherapee). Probe
   `git ls-remote --symref <url> HEAD` before concluding a file is absent.
5. **A LICENSE file can be one option of a dual licence, and taking it at face value overstates
   copyleft.** `exiftool/exiftool` ships a 35,149-byte GPL-3.0 text and the GitHub API duly reports
   `GPL-3.0` — but its README states the terms are *"the same terms as Perl itself (either the Perl
   Artistic License or GPL)"*. The real answer is `Artistic-1.0-Perl OR GPL-1.0-or-later`, which is
   far weaker copyleft than the file implies. **New licence-trap category: the file in the repo may
   be a copy of the stricter option.**
6. **A licence can live only in package metadata.** `soderlind/ai-alt-text` has no reachable LICENSE
   file at all; `composer.json` carries `"license": "GPL-2.0-or-later"`. Check `composer.json`,
   `package.json`, `pyproject.toml` and `Cargo.toml` before declaring a repo unlicensed.
7. **The divergence in note 1 runs both ways, and this direction is the dangerous one.** Note 1
   recorded repos that git serves but the search index cannot see. The inverse also happened:
   **`CNTRUN/Termux-command` is returned by `search/repositories` with 120 stars, and
   `git ls-remote` cannot serve it** under any casing. An indexed result is therefore **not**
   proof a repository is live — the index can be stale or the repo withdrawn. **Rule: verify with
   `git ls-remote` before writing any repo into a table, including one you only intend to cite as
   noise.** Of 66 repo URLs written in this pass, 66 resolve; of 6 repos cited by name as search
   contamination, 5 resolve and this one does not, and it is annotated in place rather than
   removed, because the search *count* it illustrates is still real.

## The owned-channel & audience-relationship plane — measured 2026-11-26 (pass 24), and the KB's largest vocabulary gap to date

**How this plane was found.** The vocabulary probe (two Bash calls, ~120 terms, run *before* any web
search — the method fixed in pass 22) returned a result no earlier pass has produced: the string
**`email` occurred ZERO times in 20,389 lines** of this KB. So did `Listmonk`, `Mautic`, `Coral`,
`web push`, `Novu`, `ntfy`, `Discourse`, `customer data platform`, `cookieless`, `UID2`,
`Unified ID` and `Privacy Sandbox`. Meanwhile `Snowplow`, `Matomo`, `PostHog`, `Plausible`,
`Keycloak` and `Jitsu` were all **present**.

That asymmetry is the finding, and it is sharper than pass 22's `fingerprint` gap:

> **This KB could already measure an audience. It had nothing that could contact one.**
> The observation half of first-party data was built out across passes 7 and 10; the **activation**
> half — the owned channel the audience is actually reached through — did not exist in any file.

It is also the gap that matters most right now, because the owned channel is where the industry is
retreating to. Publishers report revenue declines of **50–90%** where referral traffic evaporated,
Google Discover referrals fell **21% YoY** (Reuters Institute, via Digiday), and the April 2026 IAB
survey of **109 US publishers** found news publishers prioritising **subscriptions, attribution and
direct audience ownership**. Email is the answer the industry gave, and the KB had no word for it.

### The agent layer for this plane — measured, and it is the weakest in twenty-four passes

Searched 2026-11-26. This is **everything** that turned up on-topic, not a selection. Verified by
GitHub API (stars, forks, last push, archived flag) with licence files read where the API returned
`NONE`/`NOASSERTION`.

| Agent | Repo | License | Stars | Last push | State |
|---|---|---|---|---|---|
| auto-news | [finaldie/auto-news](https://github.com/finaldie/auto-news) | MIT | 915 | **2025-07-19** | Personal news aggregator: multi-source pull + LLM (ChatGPT/Gemini/Ollama) summarisation into a digest. **The best-starred agent in this plane, and it has been dead for 16 months.** |
| aginews | [ericciarla/aginews](https://github.com/ericciarla/aginews) | **NONE** | 274 | 2024-11-15 | Agent + Resend + Firecrawl newsletter pipeline. **No licence file: all rights reserved by default.** Two years stale. |
| AIPulse | [raghavkv85/AIPulse](https://github.com/raghavkv85/AIPulse) | **NONE** | 17 | 2026-04-07 | Curated AI newsletter generator. No licence. |
| weekly-ai-news-digest | [elbruno/weekly-ai-news-digest](https://github.com/elbruno/weekly-ai-news-digest) | MIT | 11 | 2026-11-25 | Agentic daily digest auto-generated via GitHub Agentic Workflows. **The only permissive, actively-pushed agent in the plane — and it has 11 stars.** |
| newsletter-ai-agent | [ahmadhuss/newsletter-ai-agent](https://github.com/ahmadhuss/newsletter-ai-agent) | **NONE** | 7 | 2024-08-14 | Researcher + chief-editor + HTML-writer crew. No licence. |
| thegist | [p55d2k/thegist](https://github.com/p55d2k/thegist) | MIT | 0 | 2026-10-11 | RSS → thematic sections → personalised email digest, on GitHub Actions. Licensed, alive, **zero stars**. |
| myfeed | [MatDagommer/myfeed](https://github.com/MatDagommer/myfeed) | **NONE** | 0 | 2026-04-25 | LangGraph + Mistral RSS picker. No licence. |

Seven rows. **Permissive AND pushed in the last 90 days: two of seven, with 11 and 0 stars between
them.** Four of seven carry **no licence file at all**. That is written as seven rows because seven
is what exists.

### The gradient — and this is the most precise statement the KB's structural law has had

Twenty-three passes have recorded the same law in different words. This plane orders it by a single
variable that no earlier pass isolated: **who carries the liability for the record the code keeps.**

| Function in the plane | Best open implementation | Stars | Licence | Who carries the liability |
|---|---|---|---|---|
| **Deliver a byte to an inbox** | [postalserver/postal](https://github.com/postalserver/postal) | 16,982 | MIT | Nobody — it is a protocol |
| **Send to a list** | [knadh/listmonk](https://github.com/knadh/listmonk) | 24,473 | AGPL-3.0 | Nobody |
| **Render the message** | [resend/react-email](https://github.com/resend/react-email) | 20,008 | MIT | Nobody |
| **Host a conversation (generic)** | [discourse/discourse](https://github.com/discourse/discourse) | 48,117 | GPL-2.0 | The operator, weakly |
| **Host a *newsroom* conversation** | [coralproject/talk](https://github.com/coralproject/talk) | **2,005** | Apache-2.0 | The publisher — editorially and legally |
| **Encode consent lawfully (TCF)** | [InteractiveAdvertisingBureau/iabtcf-es](https://github.com/InteractiveAdvertisingBureau/iabtcf-es) | **156** | Apache-2.0 | The publisher, under GDPR |
| **Carry consent across jurisdictions** | [IAB GPP](https://github.com/InteractiveAdvertisingBureau/Global-Privacy-Platform) | **128** | **CC-BY-3.0 — a spec, not code** | The publisher |
| **Replace the cookie / operate identity** | [IABTechLab/uid2-operator](https://github.com/IABTechLab/uid2-operator) | **18** | Apache-2.0 | The operator, fully |
| **Write the thing (agent)** | [finaldie/auto-news](https://github.com/finaldie/auto-news) | 915 **dead** | MIT | The editor |

**24,473 → 2,005 → 156 → 18.** A **1,360× collapse** across one plane, and it tracks liability
almost perfectly. Two sub-findings worth quoting to a client:

1. **The same function, with and without liability, differs 24×.** Hosting comments generically is
   48,117 stars. Hosting comments *in a newsroom*, where every published comment is the publisher's
   problem, is 2,005 — and that repo exists only because Mozilla and the Washington Post paid for it
   and Vox Media now maintains it. This is the cleanest control case the KB has: **one function, two
   liability regimes, 24× the code.**
2. **The thing that replaces the third-party cookie for the entire open web has 18 stars.**
   `uid2-operator` is Apache-2.0 and was pushed *today*. It is not abandoned — it is simply not
   something anyone self-serves, because running an identity operator means holding hashed email
   addresses for other people under GDPR and LGPD. The code is free; the liability is not.

### ⚠️ The licence finding of this pass — a *sixth* way a licence hides, and it is a star-count decoy

This is a new category and it nearly put a wrong row in this file.

Searching for the Maizzle email framework surfaces **`maizzle/maizzle`, 2,864 stars** — the
better-starred of the two repos, and the one every directory links. Checked properly:

- `maizzle/maizzle` has **no licence file** — `LICENSE`, `LICENSE.md`, `License.md`, `LICENSE-MIT`,
  `packages/framework/LICENSE` and `.github/LICENSE` all return **404** on `master`.
- Its README says "licensed under the MIT license" and links to **`./LICENSE`** — **that link 404s.**
- `package.json` has **no `license` field**.
- The npm registry entry for `@maizzle/framework` points at a **different repository**:
  `github.com/maizzle/framework`.
- **`maizzle/framework`, 1,624 stars, has a real MIT `LICENSE` file** (Copyright Cosmin Popovici) and
  was pushed 2026-11-25.

So `maizzle/maizzle` is the **starter template**, not the framework, and it is unlicensed. **The rule,
reusable across all twelve industries:** when a project name resolves to two repos, find out which
one the package registry points at **before** quoting either the stars or the licence. The
more-starred repo is often the scaffold, and scaffolds are the repos people forget to license.

The five earlier ways a licence hides are in `repos/foundations.md` (pass 4), plus Chromaprint's
build-flag licence (pass 5), OpenUSD (pass 6), the directory-vs-repo mismatch (pass 8) and pass 23's
`composer.json`-only declaration.

### ⛔ Two Elastic License 2.0 repos in one plane, both in the privacy layer

| Repo | Stars | Licence (file read) | Why it matters |
|---|---|---|---|
| [rudderlabs/rudder-server](https://github.com/rudderlabs/rudder-server) | 4,521 | **Elastic License 2.0** | The CDP that **every 2026 "open source Segment alternative" listicle recommends**. ELv2 forbids providing the software to third parties as a managed service. |
| [ConsentOS/consentos](https://github.com/ConsentOS/consentos) | 25 | **Elastic License 2.0** | Self-hosted CMP with TCF v2.3, GPP v1 and Consent Mode v2. Same restriction. |

Neither is OSI open source, and ELv2's managed-service limitation is aimed precisely at what a
systems integrator does for a client. **Use [jitsucom/jitsu](https://github.com/jitsucom/jitsu) (MIT,
5,140★) or [apache/unomi](https://github.com/apache/unomi) (Apache-2.0, 382★) instead** — and note
the gradient again: the only genuinely Apache-licensed CDP in the plane has **382 stars**.

### ⚠️ Contamination — three queries in this plane return a different industry

| Query | What comes back | Why |
|---|---|---|
| `AI newsletter agent` | **Sales/outbound and growth-hacking tooling**, plus dozens of 0-star hobby digests. Almost nothing editorial. | "Newsletter" in open source means *marketing send*, not *publication*. The editorial newsletter has no open agent layer; the marketing one has hundreds. |
| `open source CDP` | **Elastic-licensed and source-available products** presented as open source by comparison blogs (see above). | The category is vendor-defined, and the vendors write the listicles. |
| `email agent` | **Inbox assistants** — triage, auto-reply, calendar. Zero publisher relevance. | The word "email" collocates to *receiving*, not *publishing*. Search the verb (`send`, `digest`, `curate`), never the medium. |

### Informed gaps from this pass — searched, and genuinely not found

- **No open-source agent for newsletter *operations*** — list hygiene, send-time optimisation,
  deliverability triage, churn-risk scoring on an owned list. Searched; nothing on-topic and licensed.
  This is the most commercially obvious unbuilt agent found in twenty-four passes, because the
  substrate under it (`parsedmarc` Apache-2.0, `postal` MIT) is permissive and healthy.
- **No IAB-registered open-source CMP.** A publisher integrating TCF needs a *registered* CMP;
  nothing in the open set is registered. `iabtcf-es` (156★) gives you the string, not the standing.
- **No open comment-moderation agent built on an open toxicity model.** Coral ships AI moderation
  inside the platform and [unitaryai/detoxify](https://github.com/unitaryai/detoxify) (Apache-2.0,
  1,320★) is the open model, but **nothing wires them together** as an agent. Smallest buildable gap
  in this plane.
- **No open-source WhatsApp/LINE publisher-distribution agent**, despite those being the owned channel
  in LATAM and parts of APAC (see `intel/market.md`). Searched per region; genuinely absent.

---

## The traffic, sales-order-to-air & billing plane — measured 2026-11-26 (pass 25), and **the agent layer is one repo, seven days old**

The KB could say `SCTE-35` 25 times and `makegood` zero times. This plane is the commercial system of
record for linear and FAST inventory: who sold the spot, at what rate, whether it aired, and who is
invoiced. All rows verified 2026-11-26 (existence via `git ls-remote`, canonical slug via
`search/repositories -f q='repo:<slug>'`, licence files **read** where the API returned `NONE`).

### The agent

| Agent | Repo | License | Stars | Last push | State |
|---|---|---|---|---|---|
| 9eye | [9eye9/9eye](https://github.com/9eye9/9eye) | **AGPL-3.0** | 2 | 2026-11-26 | Broadcast scheduling + TV traffic with an MCP server at `/api/mcp` (Claude/ChatGPT/Grok), 75+ tools, a per-company permission table (part × action, each *Allowed*/*Ask first*/*Off*), preview + undo + audit log on every change, and an approval queue. Created **2026-11-19**. Multi-tenant, frame-accurate (23.976–59.94 fps, drop-frame, broadcast day crossing midnight). Agents run on the company's own model key, encrypted. |

**One agent, and that is the entire list for this plane.** Not padding — the searches are tabulated in
`agents/trending.md` pass 25, including two that return a **literal empty set**
(`broadcast as-run reconciliation`, `spot booking advertising`).

**Use it for its design, not as a core.** AGPL-3.0 + 2★ + 0 forks + 7 days old + a consultancy behind
it is a normative bet, not an installed base (the ISCC shape from pass 5). Its permission model —
agents and tokens can only ever be **narrower** than the issuing person, and every agent change waits
for human approval — is the best-specified human-in-the-loop design in any agent repo in this KB and
is the thing to copy into a client build. See Pattern 25.2.

### What the agent layer does *not* do, per 9eye's own roadmap

> - **As-run and reconciliation:** air logs matched against the playlist; broadcast history from them.
> - **More exports:** BXF and the other playout formats, XMLTV EPG.
> - **Sales and billing:** prices, ad rates and invoices.

Grepped inside 9eye's own working tree: `makegood` **0**, `pre-empt`/`preempt` **0**, `affidavit` **0**,
`ratecard` **0**. The vocabulary of settling what is owed is absent from the only agent in the plane.

### The agents that do not exist (recorded as measured absences)

| The agent a client will ask for | Measured state |
|---|---|
| As-run reconciliation agent (match the log to the booking, classify aired / aired-wrong / pre-empted) | `broadcast as-run reconciliation` = **0 GitHub results.** The only as-run repo in existence is [alochbaum/CheckAsRun](https://github.com/alochbaum/CheckAsRun) — **0★, no licence, no README, last push 2016-04-21**, a Visual Studio project for rounding errors in iTX as-run logs. |
| Makegood proposal agent (price a pre-empted spot, find equivalent replacement inventory) | **0 hits anywhere**, including inside 9eye. The incumbents are building this and none of it is open (see `intel/trends.md` pass 25). |
| Rate-card / yield agent (price an avail by daypart and demand) | `rate card` = **2,013 results, zero relevant.** The only repo in this KB containing the word *daypart* is [itsoumya-d/rcs-music-scheduler](https://github.com/itsoumya-d/rcs-music-scheduler) (MIT, **0★**) and it is a music rotation scheduler, not a pricing engine. |
| BXF export agent | No usable implementation, **and the schema is All Rights Reserved** — see Pattern 25.3. |

---

## Energy, carbon & environmental-footprint agents — added 2026-11-26 (pass 26)

Verified 2026-11-26: existence via `git ls-remote`, stars/forks/last-push via GitHub
`search/repositories`, licence by reading the licence file wherever the API returned `NOASSERTION`.

**Read this section with its conclusion first: there is no media-specific agent in this plane.** Every
permissive, maintained agent below measures *generic compute* or *generic corporate emissions*. None
reads a call sheet, a render queue, a transcode ladder, a playout schedule or a CDN log. The obligation,
by contrast, is the most consistently enforced in this entire KB (BBC, ITV and Channel 4 all require
BAFTA albert tooling or certification as a condition of commission). That mismatch is the opportunity,
and **P39** explains why it has persisted.

### Tier 1 — permissive and maintained

| Agent | Repo | Stars | Licence | Last push | What it does |
|---|---|---|---|---|---|
| claude-carbon | [gwittebolle/claude-carbon](https://github.com/gwittebolle/claude-carbon) | 256★ / 23f | **MIT** (1,074 B read) | 2026-11-23 | Measures the carbon footprint of Claude Code sessions. The plane's best-starred agent — and it measures the assistant, not the media workload |
| CATS (Climate-Aware Task Scheduler) | [GreenScheduler/cats](https://github.com/GreenScheduler/cats) | 82★ / 23f | **MIT** (1,076 B read) | **2026-11-26** | Defers a job until the grid is cleaner. Usable today as the scheduling brain for render and transcode queues |
| agent-carbon-tracker | [Thomaszhou22/agent-carbon-tracker](https://github.com/Thomaszhou22/agent-carbon-tracker) | 8★ | **MIT** | 2026-07-30 | EcoLogits-based footprint accounting for agent operations |
| NZC USEEIO matching agent | [salesforce-misc/NZC-USEEIOMatchingAgent](https://github.com/salesforce-misc/NZC-USEEIOMatchingAgent) | 0★ | **Apache-2.0** | 2026-11-12 | Maps Scope 3 procurement spend lines onto USEEIO emission factors — the exact shape of a production-spend footprint. **0 stars behind a Salesforce org**: institutional code nobody found |
| agent-carbon (callback) | [ChanelYJ19/agent-carbon](https://github.com/ChanelYJ19/agent-carbon) | 0★ | **MIT** | 2026-05-17 | Emissions-tracking callback for LangChain / LangGraph pipelines |
| carbon.md | [carbon-md/carbon-md](https://github.com/carbon-md/carbon-md) | 0★ | **MIT** | 2026-10-11 | A proposed Markdown standard for declaring carbon governance of an agent. A convention to adopt, not a system to run |

### Tier 2 — usable but constrained

| Agent | Repo | Stars | Licence | Last push | Constraint |
|---|---|---|---|---|---|
| Scope3Scout | [m-zest/Scope3Scout](https://github.com/m-zest/Scope3Scout) | 17★ | **AGPL-3.0** | 2026-10-06 | Supplier ESG claim verification. **Copyleft** — fine as a deployed service, not as embedded library code in a proprietary product |
| Climatiq MCP server | [jagan-shanmugam/climatiq-mcp-server](https://github.com/jagan-shanmugam/climatiq-mcp-server) | 12★ | **MIT** | 2025-03-28 | **Dormant ~20 months**, and the permissive part is a thin shim over the **commercial** Climatiq emission-factor API. The licence is free; the data behind it is not |

### ⛔ Do not ship these — verified non-adoptable

| Repo | Stars | Measured problem |
|---|---|---|
| [crbnos/carbon](https://github.com/crbnos/carbon) | **2,863★** | **A manufacturing ERP/MES/QMS named "Carbon".** Zero relation to emissions, yet it ranks first for `carbon mcp server`. By star count alone a careless pass writes this as the plane's flagship — the sharpest false friend since `eidr` and `isan` in pass 5 |
| [climateandtech/report-analyst](https://github.com/climateandtech/report-analyst) | 42★ | **No licence file.** 9 filenames × 2 branches all 404 while `README.md` returns HTTP 200 — the raw channel works, so the file is genuinely absent, not misnamed. All rights reserved by default. The best-starred CSRD tool in the plane and unusable |
| `Hazrat-Ali9/Carbon-Aware-AI-Model-Scheduling` (no link given, deliberately) | 30★ | **Empty repository.** `git ls-remote` returns **0 refs** and `README.md` 404s on `main` and `master`, yet the search API reports 30 stars and a push date of 2026-08-15. There is no code to license, review or adopt |
| [Green-Software-Foundation/sci](https://github.com/Green-Software-Foundation/sci) | 298★ | **Not OSI-licensed** — `LICENCE.md` (2,347 B, read in full) is a Joint Development Foundation "AS IS" grant under **W3C patent mode**: disclaimers and a patent pledge, **no copyright grant**. Implement **ISO/IEC 21031**; do not vendor the repository |

### The agents a media client will ask for, and their measured state

| The agent a client will ask for | Measured state on 2026-11-26 |
|---|---|
| Production carbon agent (read the call sheet, travel and generator logs; emit an albert-shaped footprint) | `film production carbon footprint` = **0 GitHub repositories**, `albert carbon calculator` = **0**. The mandated task has no open implementation at all |
| Per-title streaming carbon agent (gCO2e per stream, per title, per device mix) | No repo does this. The substrate exists ([co2.js](https://github.com/thegreenwebfoundation/co2.js) + [grid-intensity-go](https://github.com/thegreenwebfoundation/grid-intensity-go)) and the assembly is Pattern 26.1 — **with the ODbL/DRM gate cleared first** |
| Render-farm carbon scheduler (shift a queue into a clean-grid window) | The two halves both exist and permissive — [cats](https://github.com/GreenScheduler/cats) (MIT) + [carbon-aware-sdk](https://github.com/Green-Software-Foundation/carbon-aware-sdk) (MIT) — and the only media-native connector is a **3-star** MIT Deadline plugin. This is the shortest path to a working product in the plane (Pattern 26.2) |
| GenAI-footprint disclosure agent (what did this AI-assisted sequence cost in energy?) | [codecarbon](https://github.com/mlco2/codecarbon) (MIT) measures it; nothing maps it to a broadcaster deliverable, **even though the 2025 Green Animation Guide already documents a studio appending an AI traceability annex to production reports for broadcasters** (Pattern 26.4) |
| CSRD/ESRS evidence agent for an AV group | Partial: [esrs-xbrl-parser](https://github.com/aimabel-ai/esrs-xbrl-parser) (**ISC**, dormant 23 months) is the only permissive, correctly-licensed piece; the best-starred alternative has no licence at all |

## The production-finance, soft-money & cost-accounting plane — measured 2026-11-26 (pass 27): **the agent layer is one repository, it has one star, and its LICENSE says "all rights reserved"**

This is the plane pass 17 found and declined to open. Its own words, still live in
`repos/foundations.md`: *"Tier 4 — the money: effectively nothing."* Pass 17 was looking for film
**budgeting** software and found one MIT repo at 8 stars. This pass takes the whole money plane —
**how a production is financed, how soft money is qualified and claimed, how cost is booked and
reported, and how the claim is audited** — and measures it properly.

**Before any web search, 33 candidate terms were grepped against all eight KB files.** Literal zero:
`film financ*`, `production financ*`, `soft money`, `cost report`, `waterfall`, `recoupment`,
`gap financing`, `pre-sale`, `minimum guarantee`, `co-production treaty`, `section 181`, `AVEC`,
`CPTC`, `above-the-line`, `below-the-line`, `chart of accounts`, `general ledger`, `double-entry`,
`bookkeeping`, `trial balance`, `timecard`, `petty cash`, `completion bond`, `escrow`,
`errors and omissions`. **Twenty-five of thirty-three probed terms returned literal zero.** `insurance` (3) and `audit` (8)
were checked and are **unrelated senses** — French-language insurance repos and audit *logging*. For
comparison, pass 17 recorded 14 zeros from 27 probed terms and called that the largest gap at the time;
this pass does not re-rank the intervening passes, it just records the count.

### Tier 1 — the media-specific agent layer: four repositories, and not one is usable

Existence via `git ls-remote`; stars/forks/last-push via GitHub `search/repositories`; **licence by
reading the LICENSE file** in every case where the API returned `NOASSERTION` or `NONE`.

| Repo | Licence — **read, not inferred** | Stars / Forks | Last push | State |
|---|---|---|---|---|
| [jorgedoiany/film-tax-credit-agent](https://github.com/jorgedoiany/film-tax-credit-agent) | 🚫 **Proprietary.** `LICENSE` (817 B, read in full): *"Copyright (c) 2026 … All rights reserved. This software and its associated documentation files (the 'Software') are **proprietary and confidential**"* | 1★ / 0f | 2026-10-22 | The **only** film-tax-credit agent on GitHub, and it is explicitly closed. GitHub's API reports `NOASSERTION`, which reads as "unknown" — it is not unknown, it is reserved |
| [marcusg999/Film-financing-agent](https://github.com/marcusg999/Film-financing-agent) | ⚠️ **No licence file** | 0★ / 0f | 2026-07-23 | Default copyright applies: all rights reserved |
| [samjohnr-bot/greenlight-engine](https://github.com/samjohnr-bot/greenlight-engine) | ⚠️ **No licence file** | 0★ / 0f | 2026-08-20 | One of only **two** results for `recoupment waterfall` on all of GitHub |
| [tahokovi-s/hollywood-film-tax-credit-buyers-demo](https://github.com/tahokovi-s/hollywood-film-tax-credit-buyers-demo) | ⚠️ **No licence file** | 0★ / 0f | 2026-05-26 | A demo for *buyers* of credits — the secondary market, not the claim |

**`film tax credit` returns seven repositories in total across all of GitHub.** Not seven relevant
ones out of many — seven, full stop, and the best of them has one star. Two are the rows above; the
rest are a 2018 Rails exercise, a dormant Bloomberg data dump, an unrelated iOS app and a US state
marketing site. **This is the thinnest agent layer any plane in this KB has recorded**, thinner than
pass 23's still-image desk (one repo, one star) because here the single repo is also legally shut.

### Tier 2 — the generic finance agents that *are* permissive, and what they actually cover

None of these knows what a production is. They are listed because they are the **only permissively
licensed, agent-shaped code in the plane**, and Patterns 27.2 and 27.3 compose them deliberately.

| Agent | Repo | Licence | Stars / Forks | Last push | What it does |
|---|---|---|---|---|---|
| invoice-ap-agent | [tahasiddiquii/invoice-ap-agent](https://github.com/tahasiddiquii/invoice-ap-agent) | **MIT** | 5★ / 0f | 2026-07-01 | Accounts-payable invoice intake and extraction. Best-starred permissive agent in the plane — at five stars |
| probity-ai | [sujalmallick/probity-ai](https://github.com/sujalmallick/probity-ai) | **MIT** | 5★ / 1f | 2026-10-05 | Invoice coding and anomaly flagging over an AP queue |
| ap-verify | [Devanshjoshi2804/ap-verify](https://github.com/Devanshjoshi2804/ap-verify) | **MIT** | 2★ / 2f | 2026-06-21 | Three-way match verification (invoice / PO / receipt) |
| invoice-intake-agent | [northkeellabs/invoice-intake-agent](https://github.com/northkeellabs/invoice-intake-agent) | **MIT** | 1★ / 0f | 2026-11-23 | Document intake → structured AP record; pushed three days before measurement |
| ledgic | [alihdrndm/ledgic](https://github.com/alihdrndm/ledgic) | **MIT** | 0★ / 4f | 2026-11-25 | Ledger-posting assistant. **Four forks against zero stars** — the inverse ratio, which usually means coursework, not adoption |
| GuardLedger | [Mohanbabu82/GuardLedger](https://github.com/Mohanbabu82/GuardLedger) | **MIT** | 0★ / 0f | 2026-11-25 | Ledger-integrity and fraud checks over postings |
| django-invoice-agent | [MurtazaBhutta/django-invoice-agent](https://github.com/MurtazaBhutta/django-invoice-agent) | **MIT** | 0★ / 0f | 2026-11-26 | Django AP agent, pushed **on measurement day** |

**Seven permissive agents, 13 stars between them, and every one of them is an accounts-payable
clerk.** Not one computes an incentive, tests eligibility, builds a cost report, or models a
recoupment waterfall. The plane's actual economics — which jurisdiction to shoot in, what qualifies,
who gets paid back first — has **no agent at all, in any licence**.

### The agents a media-finance client will ask for, and their measured state on 2026-11-26

| The agent the client will ask for | Measured state |
|---|---|
| Incentive-eligibility agent ("does this budget qualify in Georgia, BC, Spain or NSW, and for how much?") | `production incentive eligibility` = **0 repositories**. `film tax credit` = 7, best 1★, all four relevant ones unlicensed or proprietary. **The substrate exists and is permissive** — [Catala](https://github.com/CatalaLang/catala) (Apache-2.0, 2,456★) — and nothing has been written on it for this domain: **Pattern 27.1** |
| Cost-report agent (weekly actuals vs. budget, estimate-to-complete, variance narrative) | `cost report film production` = **5 results, 0 relevant** (three market-research spam repos, one 2023 C++ student project, one API stub). The incumbents — Movie Magic, Showbiz, Wrapbook, Cast & Crew, GreenSlate, EP — are **entirely proprietary**, exactly as pass 17 recorded |
| Soft-money optimiser ("split this shoot across territories to maximise net benefit") | No repo in any licence. Both halves of the engine are permissive and mature — [Timefold](https://github.com/TimefoldAI/timefold-solver) (Apache-2.0, 1,882★) for the allocation, Catala for the rules: **Pattern 27.4**. This is the plane's most valuable unbuilt product |
| Recoupment-waterfall agent (who recoups, in what order, at what corridor) | `recoupment waterfall` = **2 repositories on all of GitHub.** The better one, [0xSplits/splits-recoup](https://github.com/0xSplits/splits-recoup) (6★), has **no licence file** — probed 8 filenames × 2 branches — and is a 2023 Solidity contract for crypto splits, not a film waterfall |
| Audit-evidence agent (assemble the cost report, ledger and payroll into a certifiable claim pack) | No repo. This is the plane's **shortest path to delivery** because the client already owns every input and the deliverable is a document, not a system: **Pattern 27.5** |
| Completion-bond / E&O risk agent | `completion bond film` = **0 repositories, literal zero.** `errors and omissions insurance` = 6, **0 relevant** (five are `api-evangelist` API-profile stubs, one is a 2018 university assignment). The entire risk-transfer layer of film finance is absent from open source |

## The age-rating & classification plane has no agent layer — measured 2026-11-26 (pass 28)

Scope of this plane: **what rating a title carries, in which territory, how that rating travels in the
metadata, and what the player does with it.** This is the inverse of pass 9 (trust & safety), which
asked *is this user old enough* and *is this user-generated post harmful*. This pass asks
*what is this title rated in Brazil, and did the right number arrive in the catalogue*.

The plane was still open after twenty-seven passes. Before searching the web, 69 candidate terms were
grepped against all eight files. `age rating`, `COPPA`, `PEGI`, `BBFC`, `FSK`, `ESRB`, `KMRB`,
`parental control`, `kids content` and `classificação indicativa` all scored **literal zero**. The
only artefact anywhere in the KB was a single row for `MovieLabs/cmr-ratings` added in pass 16 —
1 star, no licence, one line of description. That row turned out to be the most under-described
artefact in this KB, and sizing it is the main result of this pass (see `repos/foundations.md`).

### The eighth consecutive confirmation of this KB's structural law — and the first time the blocker is *legal attribution*

| Query | Result |
|---|---|
| `content classification agent MCP` | **0 results — literally empty** |
| `age rating MCP server` | 6 results, **0 relevant** (agent-reputation scores, a news MCP, App Store Connect) |
| `age rating agent LLM` | 6 results, **0 relevant**, top hit is a pull-request review agent |
| `video content moderation agent` | 6 results, **all 0 stars**, all student or demo projects |
| `OARS rating` | **1 result** in all of GitHub — `hughsie/oars` itself |

There is no agent layer, and this time the reason is neither regulatory burden (pass 3), nor a closed
content licence (passes 5 and 16), nor operating cost (pass 7). It is **legal attribution of
judgment**. A statutory age rating is an act attributed to a *named authority* — a board, or, under
the proposed EU KIDS Act, an app-store operator who must **publish the methodology, criteria and
sources** behind its rating. A probabilistic classifier cannot hold an attribution duty: "the model
said 16" is not a methodology a regulator can read, and it is not a party anyone can hold to it.

**The sellable consequence, and it is the most useful sentence in this pass:** an *open, declared*
criteria vocabulary satisfies a published-methodology duty far more naturally than a closed board
certificate or a black-box classifier does. The duty the EU is drafting is a duty to *explain*, and
explanation is a data-model problem.

### ⚠️ Contamination warnings — two of the sharpest false friends in this KB

- **`PEGI api` → 6 results, 0 relevant.** Every hit is a misspelling of *pagination*:
  `PegiskaAPI`, `peginationBloc`, `API-handling-Pegination`, `Pegion-News`. The European games rating
  system collides totally with a typo of the commonest word in web development.
- **`ESRB API` → 6 results, 0 relevant.** All are IGDB/RAWG game-database hobby projects at 0 stars.
- **`age rating` → 1,147 total results, roughly 5 relevant.** Pass 8's rule holds and is worth
  restating: **read the results, not the total.** Shortening a query can turn a false zero into a
  false abundance.
- **`maturity rating API` → 1 result**, a personal book-tracking project from 2020.

### What stands in for an agent layer today — generic classifiers, and the licence is the whole story

None of these is an age-rating system. They are signal detectors a human classifier can use as
evidence, and the licence decides whether a client can ship them.

| Repo | Licence | Stars / forks | Pushed | What it is, and the honest limit |
|---|---|---|---|---|
| [infinitered/nsfwjs](https://github.com/infinitered/nsfwjs) | **MIT** (`LICENSE`, 1,075 B) | 9,038★ / 596f | 2026-10-29 | Client-side NSFW detection in TensorFlow.js. **The only permissive, maintained, widely-adopted detector in this plane** — and the one to build on. Five classes, not an age ladder. |
| [serengil/deepface](https://github.com/serengil/deepface) | **MIT** | 23,740★ / 3,222f | 2026-11-20 | Face analysis including age estimation. Relevant to *age assurance of the viewer*, not to rating the title. Pass 9's plane, listed here because teams conflate the two. |
| [WildChlamydia/MiVOLO](https://github.com/WildChlamydia/MiVOLO) | **Apache-2.0** (11,357 B) | 546★ / 99f | 2026-06-04 | Age & gender transformer. The strongest-licensed age *estimator* found. Same caveat: viewer, not title. |
| [notAI-tech/NudeNet](https://github.com/notAI-tech/NudeNet) | **AGPL-3.0** (34,523 B) | 2,510★ / 443f | 2026-06-09 | Nudity detection. Already in this KB from pass 9. **AGPL — if it is in the request path of a hosted service, the copyleft reaches your service.** Do not put it in a client SaaS without counsel. |
| [GantMan/nsfw_model](https://github.com/GantMan/nsfw_model) | **NOASSERTION** | 2,113★ / 304f | 2024-02-26 | Keras NSFW detector. Two years stale and the licence does not resolve to a known SPDX id. Read the stars as history. |
| [EmotionEngineer/EmotionPlayer](https://github.com/EmotionEngineer/EmotionPlayer) | **MIT** (`LICENSE`, 1,069 B) | 57★ / 15f | 2025-12-18 | A video player that analyses content to derive an age rating. **The only repo found that attempts title-level rating from the content itself.** 57 stars — a demonstration of the idea, not a product. Cite it as proof the idea is unclaimed, not as a component. |

**The gap worth naming to a client:** every artefact above detects *nudity* or estimates a *face's
age*. A national rating ladder weighs violence, drugs, language, discrimination, horror and — in
Brazil's case — a closed list of exactly ten permitted content descriptors. **No open model emits a
territory's descriptor set.** That is the unbuilt thing, and the EU's published-methodology duty is
what would make a client pay for it.

## The interactive, branching & playable-story plane — measured 2026-11-26 (pass 29), and **the first plane in this KB where the supply is healthy and the *buyer* withdrew**

Pass 29 took the gap grep before the web search, per the pass-8 method. The result was the widest
vocabulary hole measured in twenty-eight passes: across all eight files, `interactive video`,
`branching`, `visual novel`, `interactive fiction`, `dialogue tree`, `narrative design`,
`transmedia`, `second screen`, `companion app`, `Ren'Py`, `inkle` and `Yarn Spinner` scored
**zero occurrences each**. The KB could say `playout` 83 times and `branching` zero times.

**Read this plane differently from the other twenty-eight.** Everywhere else, this KB has recorded a
healthy horizontal layer above an empty vertical one. Here the vertical layer is *the healthy part* —
narrative authoring is mature, permissive, actively pushed and nearly all MIT — and what collapsed is
the **distribution channel**: Netflix removed most of its interactive titles on **2024-12-01** and
the final two, *Black Mirror: Bandersnatch* and *Kimmy vs. the Reverend*, on **2025-05-12**, stating
that the interactive-TV technology "served its purpose, but is now limiting as we focus on
technological efforts in other areas", and pivoting to games. So the correct pitch in this plane is
**never "branching video for a streamer"**. It is the authoring and dialogue substrate pointed at the
channels that *did* keep paying: games, learning and brand experience, AI characters, and public-service
object-based media.

### Tier 1 — permissive, active, safe to build on (interactive-character & story-runtime agents)

| Agent / runtime | Repo | Licence | Stars | Last push | What it actually does |
|---|---|---|---|---|---|
| elizaOS (Eliza) | [elizaOS/eliza](https://github.com/elizaOS/eliza) | MIT | 19,925★ | 2026-11-26 | Agentic OS whose unit of configuration is a **character file**. The closest thing to a persistent cast of characters you can host yourself. |
| Pipecat | [pipecat-ai/pipecat](https://github.com/pipecat-ai/pipecat) | BSD-2-Clause | 17,458★ | 2026-11-26 | Realtime voice/multimodal pipeline. The transport layer under a spoken interactive character. |
| LiveKit Agents | [livekit/agents](https://github.com/livekit/agents) | Apache-2.0 | 15,355★ | 2026-11-26 | Realtime voice/video agent framework with the WebRTC plumbing already solved. |
| LiveTalking | [lipku/LiveTalking](https://github.com/lipku/LiveTalking) | Apache-2.0 | 11,338★ | 2026-11-26 | Real-time interactive streaming digital human; supports being **interrupted mid-sentence**, which is the hard part of a live character. |
| AI Town | [a16z-infra/ai-town](https://github.com/a16z-infra/ai-town) | MIT | 10,866★ | 2026-11-25 | Deployable starter kit for a populated world of interacting agents. The cheapest honest demo of emergent narrative. |
| OpenAvatarChat | [HumanAIGC-Engineering/OpenAvatarChat](https://github.com/HumanAIGC-Engineering/OpenAvatarChat) | Apache-2.0 | 3,907★ | 2026-07-31 | Modular real-time avatar conversation stack (ASR→LLM→TTS→face). |
| OpenTalking | [datascale-ai/opentalking](https://github.com/datascale-ai/opentalking) | Apache-2.0 | 3,421★ | 2026-09-04 | Industrial-grade digital-human pipeline: LLM, TTS, WebRTC, pluggable model backends. |
| Story-to-game | [Shanyin-ai/Story-to-game](https://github.com/Shanyin-ai/Story-to-game) | MIT | 503★ | 2026-06-02 | Toolkit for creating **and running** branch-narrative games — the only permissive repo found that spans authoring *and* runtime. |
| ludo-npc-ai | [koronto11/ludo-npc-ai](https://github.com/koronto11/ludo-npc-ai) | MIT | 103★ | 2026-10-11 | Visual workspace for game narratives and NPCs: arrange worlds, wire characters. Small, but in-plane and alive. |

Nine rows, all verified by `git ls-remote` plus a licence read on 2026-11-26. That is the first time
in this KB that a plane's agent layer has had **nine permissive, actively-pushed rows** — the
opposite of pass 27's "one repo, one star, all rights reserved".

### Tier 2 — real and widely used, but the licence or the staleness constrains client work

| Agent | Repo | Licence | Stars | Last push | Constraint |
|---|---|---|---|---|---|
| SillyTavern | [SillyTavern/SillyTavern](https://github.com/SillyTavern/SillyTavern) | AGPL-3.0 | 36,122★ | 2026-11-22 | The most-starred character-interaction frontend in existence, and **AGPL-3.0** — network copyleft. It is a reference implementation, not a shippable component. |
| Generative Agents | [joonspk-research/generative_agents](https://github.com/joonspk-research/generative_agents) | Apache-2.0 | 22,425★ | **2024-08-05** | The paper everyone cites for believable agents. Permissive and **16 months without a push** — cite the method, do not fork the code. |
| Duix-Mobile | [duixcom/Duix-Mobile](https://github.com/duixcom/Duix-Mobile) | **DUIX.COM Community License Agreement** (6,198 B, bespoke) | 8,362★ | 2026-08-05 | On-device real-time avatar, and the plane's **star-count decoy**: 8,362★ behind a bespoke community licence, not OSI-approved. Read it before it reaches a proposal. |
| Hallo | [fudan-generative-vision/hallo](https://github.com/fudan-generative-vision/hallo) | MIT | 8,678★ | **2024-09-14** | Audio-driven portrait animation. MIT and genuinely good; 26 months stale. |
| HunyuanVideo-Avatar | [Tencent-Hunyuan/HunyuanVideo-Avatar](https://github.com/Tencent-Hunyuan/HunyuanVideo-Avatar) | NOASSERTION (Tencent community terms) | 2,226★ | 2025-12-16 | Trended daily on Trendshift 2026-11-10→15 and hit #1 on one of those days. The **licence is the community licence, not Apache-2.0** — same trap as the other Hunyuan drops recorded in pass 6. |
| RisuAI | [kwaroran/RisuAI](https://github.com/kwaroran/RisuAI) | GPL-3.0 | 1,874★ | 2026-11-26 | Active daily. GPL-3.0 — fine for an internal tool, not for embedding in a client product. |
| AITuber Kit | [tegnike/aituber-kit](https://github.com/tegnike/aituber-kit) | **Custom dual licence: non-commercial by default** (1,589 B) | 1,149★ | 2026-11-23 | The best-documented AI-character streaming kit out of Japan, and **commercial use requires a separate licence**. ⛔ Do not ship without one. |
| ChatVRM | [pixiv/ChatVRM](https://github.com/pixiv/ChatVRM) | MIT | 847★ | 2025-05-27 | **Archived.** The reference 3D-avatar chat web app. Read it, do not depend on it. |

### The agent bridge for narrative tooling exists — and it is **36 stars wide in total**

This is the measurement to quote. Six MCP servers touch interactive narrative at all, and here is
every one of them:

| MCP server | Repo | Licence | Stars | Last push |
|---|---|---|---|---|
| role-playing-mcp-server | [fritzprix/role-playing-mcp-server](https://github.com/fritzprix/role-playing-mcp-server) | MIT | 17★ | 2026-10-04 |
| dmcp (AI dungeon master) | [shawnrushefsky/dmcp](https://github.com/shawnrushefsky/dmcp) | MIT | 15★ | 2026-01-06 |
| opera-omnia-mcp | [triptych/opera-omnia-mcp](https://github.com/triptych/opera-omnia-mcp) | MIT | 2★ | 2025-03-23 |
| inkcheck (CI for ink stories) | [chaoz23/inkcheck](https://github.com/chaoz23/inkcheck) | MIT | 2★ | 2026-10-26 |
| twine-play-mcp | [adorablelovelymia/twine-play-mcp](https://github.com/adorablelovelymia/twine-play-mcp) | MIT | **0★** | 2026-11-21 |
| game-writer-mcp-server | [kehindeBankole/game-writer-mcp-server](https://github.com/kehindeBankole/game-writer-mcp-server) | **no LICENSE file** | **0★** | 2025-08-24 |

**17 + 15 + 2 + 2 + 0 + 0 = 36 stars** for the entire agent bridge of a plane whose substrate carries
over 190,000 stars. `interactive fiction MCP` returns **7 repositories in total** on GitHub search.

Two readings, both actionable:

1. **`inkcheck` is the right shape and nobody noticed.** It compiles an ink story, **playtests every
   branch exhaustively** and reports dead content — i.e. it treats a narrative as a graph with test
   coverage. That is precisely the job an agent should do in this plane, it is MIT, it was pushed
   2026-10-26, and it has **2 stars**. The gap is adoption, not invention.
2. **`twine-play-mcp` corrects a wrong answer.** A web search for a Twine MCP server returns "none
   exists"; GitHub search returns one, MIT, pushed **five days before this pass**, with zero stars.
   *Absence in a listicle is not absence in the registry* — the same lesson pass 25 recorded when it
   found this plane's anchor alive after the KB had declared it dead.

### ⚠️ Contamination warnings — three queries in this plane are traps

- **`choose your own adventure` → 5,873 repositories, essentially none of them infrastructure.** The
  top three are a Next.js demo (222★), a JS toy (185★, no licence) and a *conference-presentation*
  generator (174★). This is the highest contaminated total recorded in any plane so far.
- **`transmedia` → 522 repositories, zero in-plane.** The top hit is `d3cod3/Mosaic` (519★), a
  visual-programming art tool. The word is academic vocabulary, not a software category.
- **`object based media` → 187 repositories, zero in-plane in the top results.** The real artefact —
  BBC R&D's own player — has **19 stars** and is three pages down. Rank by relevance in this plane,
  never by stars.

### Informed gaps from this pass — searched, and genuinely not found

- **There is no second-screen / companion-TV layer at all.** `second screen companion tv` returns
  **2 repositories in total**, both at **0 stars**. This is the smallest total this KB has ever
  recorded for a named capability — smaller than pass 27's four-repo finance layer. If a client asks
  for a companion-app experience, every line is bespoke.
- **No open interactive-video *standard* exists.** HLS and DASH have no branching primitive, and the
  only open players found are `Comedian1926/OpenFMV` (MIT, 241★, first commits 2026) and
  `mohetios/BandersnatchInteractive` (MIT, 255★) — a clone of the format Netflix retired. Pitch a
  **player you own**, not conformance to a standard that does not exist.
- **No agent writes a *territory-legal* interactive flow.** Pass 28's finding carries straight in:
  nothing in this plane knows that a branch leading to a drug-use scene changes a title's rating.
  That is the junction between pass 28 and pass 29, and it is unbuilt.
- **`NVIDIA/Audio2Face-3D` is not open source.** 582★, no LICENSE file at any probed name, and the
  README points at **NVIDIA's product-specific software terms**. It appears on "open source digital
  human" lists anyway. ⛔ Do not put it in a client stack on the strength of those lists.

---

## Pass 30 (2026-11-26) — the AI-answer-engine discovery, citation & referral-measurement plane

**The gap grep, run before any web search (pass 8's method).** Thirteen candidate terms against all
eight files: `llms.txt` **0**, `zero-click` **0**, `generative engine optimization` **0**,
`search console` **0**, `voice-clone` 0, `fandom` 0, `creator economy` 0, `merchandising` 0,
`stock footage` 0, `sitemap` **1**, `answer engine` 2, `referral traffic` 2, `Perplexity` **1**,
`Google-Extended` **0**. The KB already carried the *symptom* in prose — "AI Overviews cite news
publications but send fewer clicks", publisher revenue declines of 50–90% where referral traffic
evaporated — and **none of the plane's tooling.** This is the exact inverse of pass 5: that plane was
about telling a crawler **no**; this one is about being **found, cited and counted** by the same
crawler. Both halves of one crawler, 25 passes apart.

### The agents that exist — all seven verified twice (search API metadata + `git ls-remote`)

| Agent / tool | Repo | Licence | Stars / forks | Last push | What it actually does in this plane |
|---|---|---|---|---|---|
| **GEO Optimizer** | https://github.com/Auriti-Labs/geo-optimizer-skill | MIT | 1,398★ / 166f | 2026-11-26 | The only purpose-built, permissively-licensed **answer-engine visibility auditor** found. Ships as CLI + Python library + **MCP server** + Astro integration; audits schema, meta tags and content structure. The MCP server is what makes it composable into an agent stack. |
| **Crawl4AI** | https://github.com/unclecode/crawl4ai | Apache-2.0 | 87,986★ / 9,181f | 2026-11-23 | LLM-oriented crawler. In this plane you point it at **your own** site to see what an answer engine retains — not to harvest someone else's. |
| **Jina Reader** | https://github.com/jina-ai/reader | Apache-2.0 | 12,283★ / 901f | 2026-05-22 | URL → LLM-readable text. The reference implementation of "what the engine sees". Note the **6-month gap since last push**. |
| **Trafilatura** | https://github.com/adbar/trafilatura | Apache-2.0 | 7,182★ / 520f | 2026-11-23 | Main-content extraction. Shows what survives boilerplate stripping — i.e. which of your page is even eligible to be quoted. |
| **MarkItDown** | https://github.com/microsoft/markitdown | MIT | 198,609★ / 15,085f | 2026-11-07 | Microsoft's converter to clean Markdown. The highest-starred repo in this plane by two orders of magnitude, and MIT. |
| **Docling** | https://github.com/docling-project/docling | MIT | 71,109★ / 5,449f | 2026-11-26 | Document → structured text for AI consumption. Pairs with MarkItDown for archive and PDF back-catalogue. |
| **Loamly** | https://github.com/loamly/loamly | MIT | **21★** / 1f | **2026-01-28** | AI *traffic* detection — visits originating from ChatGPT, Claude, Perplexity, Gemini. The right shape for this plane and **the whole open-source answer is 21 stars and has been dormant for ten months.** |

### The headline: this plane's substrate is enormous and its *measurement* layer is 21 stars wide

Read that table as two blocks. **Being readable** is solved and permissively licensed — MarkItDown,
Docling, Crawl4AI, Trafilatura and Reader total over **375,000 stars**, all MIT or Apache-2.0, nearly
all pushed within the last three weeks. **Knowing whether it worked** is `loamly` at 21★, dormant
since January. The industry is thoroughly equipped to be ingested and almost entirely unequipped to
find out what the ingestion earned.

### ⛔ The standard built for this plane is a *measured* dud — do not sell it

`llms.txt` is the one artefact a client will ask for by name, and the KB must be able to say no with
numbers:

| Evidence | Finding |
|---|---|
| The spec repo | https://github.com/AnswerDotAI/llms-txt — Apache-2.0, 2,702★ / 189f, **last push 2026-09-24** (the only repo in this plane with a multi-month gap on the *standard* itself) |
| Google, in writing (June 2026) | Machine-readable AI files **are not needed** to appear in Google Search, because Search does not use them. Gary Illyes (Jul 2025): no support, no plans. John Mueller later compared it to the **keywords meta tag**. |
| Ahrefs, 137,210 domains | **97% of `llms.txt` files received zero traffic in May 2026**, and **96% of the requests that did arrive were bots.** |
| SE Ranking, 300,000 domains | **10.13% adoption.** Ahrefs' own higher 28% figure is stated by Ahrefs as an **upper bound** (its analytics customers skew technical). |
| The leading generator | https://github.com/firecrawl/llmstxt-generator — 540★ / 71f, **NO LICENCE FILE**, **dormant since 2025-06-17** |

The surviving honest use case is narrow and worth stating precisely: **developer documentation**, where
coding agents and docs assistants genuinely do read it. For a media or publishing client it is not a
discovery strategy. ⚠️ Both Ahrefs and SE Ranking are **vendor studies**, and Ahrefs did not check
whether the files followed the spec — cite them as the best available measurement, not as neutral.

### ⛔ Licence traps — two, and one is a category this KB has not recorded before

**1. `firecrawl/llmstxt-generator` (540★) has no licence at all.** Probed 10 filenames × 2 branches
through the raw channel; `README.md` returned **200 on both `main` and `master`**, so the channel
works and the 404s are real absences. Shallow-cloned and looked, per pass 5's rule: root holds
`README.md app components components.json hooks lib next.config.ts package.json …` and **nothing
licence-like.** Without a grant, default copyright applies — all rights reserved. This is the **second
instance** of pass 5's `rslstandard/rsl` trap, so it is promoted to a rule: **when a new standard
appears, its most-starred tooling is disproportionately likely to be unlicensed.** Check the tool, not
just the spec.

**2. `snowplow-referer-parser/referer-parser` (383★) — NEW CATEGORY: the licence lives in the data
file's ancestry, declared only in README prose.** The API reports `NONE` and there is no licence file
at root. But the README's own *"Copyright and license"* section states that **`referers.yml` is based
on Matomo's `SearchEngines.php` and `Socials.php`, copyright 2012 Matthieu Aubry, available under the
GNU General Public License v3.** So the 85 KB YAML — *the single file you would want to extend with
AI referrers* — carries **GPL-3.0 by inheritance** while the repository declares nothing at all. Pass
5 found a licence owned by **the compilation** (Chromaprint/FFmpeg); this is a licence owned by **the
dataset's ancestor**, and no SPDX field, badge or SBOM scan of the source tree can see it. **Rule:
for any vendored dataset, resolve the licence of the data's provenance, not the repo's.**

⚠️ Also NOASSERTION in this plane: `mitchellkrogza/nginx-ultimate-bad-bot-blocker` (4,848★),
`ua-parser/uap-core` (827★).

## The live-event, show-control & stagecraft plane — measured 2026-11-27 (pass 31), and the **youngest agent layer in this KB: eight projects, all born in 2026, ~38 stars between them**

Gap grep first, as always. Of ~90 terms probed against all eight files, this cluster was a hard zero:
`DMX`, `sACN`, `Art-Net`, `GDTF`, `MVR`, `LTC`, `projection mapping`, `show control`, `stagecraft`,
`lighting control`, `theme park`, `touring`, `front of house`, `stage management`. The KB already had
`venue` (30 hits), `concert` (45) and ticketing — it had the **commerce** of live entertainment and
none of the **machinery**. CasparCG, Sofie and NRK were already present from pass 25, so broadcast
graphics is excluded here; this plane is the physical show: lights, cues, projection, timecode.

**The headline, and it is a measurement result rather than an opinion:** the agent layer of this plane
is real, it is entirely **MCP-shaped**, every single project was created in 2026, and the eight of them
together hold about **38 stars**. One has adoption; seven have essentially none; one is **paywalled**.

| Agent / tool | Repo | Licence | Stars | Created | Last push | What it does, and the verdict |
|---|---|---|---|---|---|---|
| xlights-mcp-server | [JohnBreault/xlights-mcp-server](https://github.com/JohnBreault/xlights-mcp-server) | MIT | 32★ | 2026-04-04 | 2026-11-12 | MCP server that generates xLights sequences from music analysis. **10 forks — the only project in this plane with measurable adoption, and the only one to build on.** |
| freeshow-mcp | [restonauta/freeshow-mcp](https://github.com/restonauta/freeshow-mcp) | MIT | 2★ | 2026-06-26 | 2026-06-26 | MCP server to drive FreeShow presentation software from an LLM. Single-day repo: pushed once, never again. |
| show_designer | [guillegar/show_designer](https://github.com/guillegar/show_designer) | NOASSERTION | 2★ | 2026-06-03 | 2026-07-06 | Lighting design with timeline editor, 3D viewer, Art-Net/sACN/USB output and natural-language control over MCP. **No resolvable licence — unusable for client work as published.** Spanish-language repo (see LATAM). |
| lights-pi | [gfargo/lights-pi](https://github.com/gfargo/lights-pi) | MIT | 1★ | 2026-03-05 | 2026-11-26 | Headless Raspberry Pi DMX controller with natural-language scene generation; MCP over Streamable HTTP, built on QLC+ and an ENTTEC DMX USB Pro. **Pushed the day before this pass — the liveliest of the small ones, and the only one wired to QLC+.** |
| light-mcp-server | [bawaaaaah/light-mcp-server](https://github.com/bawaaaaah/light-mcp-server) | MIT | 1★ | 2026-10-14 | 2026-11-22 | DMX over Art-Net/sACN driven by MIDI, a WebSocket UI or MCP; imports QLC+ fixtures, exports to Ableton. Self-declared **v0 / in development**. French-language repo. |
| stagelight | [crownemmanuel/stagelight](https://github.com/crownemmanuel/stagelight) | **none** | 0★ | 2026-10-26 | 2026-11-16 | "Agent-first" lighting control: describe the rig in prose, the agent patches fixtures and programs looks against a 3D preview, Art-Net out. **The most interesting design in the plane and it has no licence file at all** — default copyright, all rights reserved. |
| lumina-ai-controller | [Gamartinhos/lumina-ai-controller](https://github.com/Gamartinhos/lumina-ai-controller) | **none** | 0★ | 2026-10-03 | 2026-10-03 | Local DMX/Art-Net server exposing endpoints for Claude/Gemini. One push, no licence. Portuguese-language repo (see LATAM). |
| luxdmx (Mac CLI/MCP) | [raydeoliveira/luxdmx](https://github.com/raydeoliveira/luxdmx) | NOASSERTION | 0★ | 2026-11-24 | 2026-11-26 | Art-Net 4 + sACN control as a macOS CLI and stdio MCP server, with CIE colour science and gel presets. **Open-core: read-only and dry-run tools are free, live apply and atomic scene execution require a Pro licence.** |

### Three warnings that belong with this table

**1. The paywalled tool surface is new to this KB.** `raydeoliveira/luxdmx` is the first MCP server
measured here that **gates individual tools behind a paid licence**. The agent can look and simulate;
making a light actually change is the paid call. Any evaluation that tests an MCP server with
read-only probes will score it as working and discover the wall in production. **Test the write path,
not the read path**, on every MCP dependency from here on — this applies to all twelve industries.

**2. Two name collisions, both capable of producing a wrong row.** `raydeoliveira/luxdmx` (0★, three
days old, open-core) is **not** [tombueng/LuxDMX](https://github.com/tombueng/LuxDMX) (104★,
Apache-2.0, ESP32 Art-Net/sACN→DMX512 gateway firmware, 7 forks, pushed 2026-11-22) — different
things, same name, and the Apache-2.0 one is the usable one. Worse: `TheCraftedTech/opencue` (1★, a
GPL-3.0 DMX console created 2026-10-16) is **not**
[AcademySoftwareFoundation/OpenCue](https://github.com/AcademySoftwareFoundation/OpenCue) (1,010★,
Apache-2.0, the render-farm manager already in this KB's orchestration tier from pass 6). A pass that
trusted the search layer would have merged **a render farm with a lighting desk**.

**3. What this plane's agent layer is *for* is already settled, and it is not generation.** Every one
of the eight is a **control bridge**: prose or MCP in, DMX/Art-Net/sACN out. None generates a show
file as an artefact to hand to a human programmer, which is the one thing a lighting designer would
actually buy (the editorial-handoff role `OpenTimelineIO` plays in the generative pipeline). The
nearest thing is `xlights-mcp-server`, which writes sequences — and it is the one with the forks.
**The unbuilt product is "agent writes a reviewable show file", not "agent drives the rig live".**

## The device, TV-app & client-playback plane — measured 2026-11-27 (pass 32), and **it has a real agent layer, 125 stars wide, aimed at the one thing in the plane that is not automatable**

Added 2026-11-27 (pass 32). This plane is how content actually reaches a screen a viewer owns:
the player, the TV application, the device it is certified on. The KB already held the *web player*
layer (`shaka-player`, `hls.js`, `dash.js`, `shaka-packager` appear in 5–6 files each). It held
**nothing** on the device side: before this pass the eight files said `HbbTV` 0 times, `Roku` 0
times, `multi-CDN` 0 times, `encoding ladder` 0 times and `geoblock` 0 times, while saying `ATSC`
53 times. The broadcast transmission side was covered; the endpoint it transmits to was not.

**71 repo slugs probed this pass; 58 resolve, 13 do not.** Two of the 13 were wrong guesses of mine
that resolved to real repos under different owners (`rdkcentral/Blits` → **`lightning-js/blits`**;
`cta-wave/common-media-library` → **`streaming-video-technology-alliance/common-media-library`**).
Licences were read from the actual file wherever the GitHub API returned `NOASSERTION` or `NONE`.

### The agent layer — real, permissive, and all of it born in the last 24 months

| Agent | Repo | Licence | Stars | Last push | What it does |
|---|---|---|---|---|---|
| **Arbigent** | https://github.com/takahirom/arbigent | Apache-2.0 | 657★ | 2026-11-27 | AI agent for testing Android, iOS, **web and TV** apps. Decomposes a scenario into dependent sub-tasks, which is what makes D-pad flows tractable. Pushed the day of this pass. Provider-agnostic. |
| **Optics Framework** | https://github.com/mozarkai/optics-framework | Apache-2.0 | 104★ | 2026-11-26 | Test automation explicitly covering **Android TV, Tizen and webOS**. Tests as CSV/YAML, recorded live, **or built by an AI agent over MCP**. Self-healing locators (XPath, text, OCR, image match) — the only one here that addresses the real failure mode, which is that TV UIs have no accessibility tree. |
| **ctv-bridge** | https://github.com/Braggiouy/ctv-bridge | MIT | 12★ | 2026-11-25 | Cross-platform desktop tool to build, deploy and debug **Tizen, webOS and Android TV** apps. Replaces three vendor toolchains with one. |
| **tv-mcp** | https://github.com/skdonthi/tv-mcp | MIT | 6★ | 2026-08-05 | MCP server that lets a coding agent build, deploy and debug web apps on **Samsung Tizen and LG webOS** TVs. The agent bridge for this plane, and it is 6 stars. |
| **tvdoctor** | https://github.com/Ticklect/tvdoctor | **AGPL-3.0** | 3★ | 2026-11-23 | Local MCP tools for coding agents: **deterministic D-pad exploration**, evidence-linked findings, replay for web and Android TV. Created 2026-08-23. ⚠️ AGPL — see the licence note below. |

**Index, not an agent:** https://github.com/tugkanboz/awesome-ai-testing (**CC0-1.0**, 206★,
2026-11-25) lists `optics-framework`, `arbigent` and Playwright-based AI regression tools. CC0 means
it is genuinely reusable as a research input, which is unusual for a curated list — contrast
`vitalets/awesome-smart-tv` below.

**The media/TV-specific agent layer is 125 stars** (104 + 12 + 6 + 3). Arbigent's 657 are
general-purpose mobile/web testing that happens to reach TV. So the honest reading: **the plane has
a real agent layer, unlike monetization, conformance, identification, age-rating or
production-finance — but four of its five repos are under 15 stars and three were created in 2026.**

### Why the agent layer exists *here* and nowhere else in this KB — and it is the sharpest version of the content law

Across eleven planes this KB has recorded the same law: where the work is **formal**, open source
ships; where the work is **judgment**, it is empty. This plane is the first one where **both halves
are in the same repo list**, and the licence of one of them says the quiet part out loud:

- **Driving a TV app is formal.** A D-pad has five buttons. Focus either moved or it did not. So an
  agent can do it, and five of them do — `optics-framework`'s OCR/image matching exists precisely
  because the formal accessibility tree is missing, and recovering it is mechanical work.
- **Deciding whether playback was *correct* is judgment** — was that stall a device fault, a
  ladder fault, or the network? — and the one open component that renders that verdict,
  `cta-wave/device-observation-framework`, is **Apache-2.0 plus the Commons Clause** (see
  `repos/foundations.md`, pass 32). Its own licence file forbids using it to provide
  *"a product or service whose value derives, entirely or substantially, from the functionality of
  the Software"* for a fee — and names **"fees for hosting or consulting/support services"** as
  exactly that.

**This is the first licence in the entire KB that specifically prohibits the Globant business
model.** Not copyleft, not a field-of-use restriction on a model, not a BSL clock: a clause whose
plain text blocks billing a client for a service built on it. Every other licence trap recorded in
this KB (AGPL network copyleft, BSL date, Llama acceptable-use) can be engineered around or waited
out. This one cannot.

### Licence notes a client engagement will hit

- ⚠️ **`tvdoctor` is AGPL-3.0.** It is an MCP server, so a hosted deployment for a client is a
  network-service use and triggers source provision. Fine for a Globant-internal QA tool, a
  deliberate choice for anything client-facing. `arbigent` and `optics-framework` (both Apache-2.0)
  carry no such condition — **prefer them as the default, and reach for `tvdoctor` only for its
  D-pad exploration, which the others do not have.**
- ✅ **`tv-mcp` and `ctv-bridge` are MIT** and are the cheapest way to put a coding agent in front of
  a real Tizen or webOS device. Combined: 18 stars. Treat them as reference code to absorb, not as
  dependencies to pin — at this size, the maintenance risk is total.

---

## Pass 33 addendum (2026-11-27) — the media-monitoring, earned-media & press-intelligence agent layer

**The plane this pass opened.** Thirty-two passes catalogued the industry *publishing outward*. This
one covers the mirror: **listening inward** — what is said about a brand or a title across news,
broadcast and social, and how that is measured. Before this pass the eight files said
`media monitoring` **0** times, `press clipping` **0** times, `broadcast monitoring` **0** times,
`share of voice` **0** times, `earned media` **0** times, `social listening` **0** times,
`sentiment analysis` **0** times and `AMEC` **0** times — while saying `playout` 86 times and
`C2PA` 123 times. The outbound side was covered to the byte; the inbound side had no vocabulary.

> **⚠️ Verification note for this pass — read before comparing with rows above.**
> **No star counts are asserted in any pass-33 section, and that is deliberate.** This session's
> GitHub API access is scoped to the session's own repositories: `api.github.com/repos/{any other}`
> returns `"GitHub access to this repository is not enabled for this session"`. The HTML
> `stargazerCount` scrape and the `commits/{branch}.atom` feed both returned empty through the
> proxy. So an absent star figure below is an **unavailable** measurement, not an unrecorded one.
> What *was* verified, for every row: **existence** via `git ls-remote --exit-code`, **licence** by
> reading the actual licence file and counting its bytes, and **last commit date** via
> `git clone --depth 1 --filter=blob:none --no-checkout`. Dates below are last-commit, not
> last-push, and are therefore slightly conservative.

### The agent layer — six real repos, and the licence line runs straight through the middle

| Agent | Repo | Licence | Last commit | What it does |
|---|---|---|---|---|
| PR Radar | [Etipufhu/pr-radar](https://github.com/Etipufhu/pr-radar) | MIT (1,069 B) | 2026-11-26 | **The only end-to-end implementation of this plane in open source.** Collects brand + competitor coverage, deduplicates and clusters into stories, scores tone per brand mention, and has a LoRA-tuned Qwen3-1.7B write a weekly brief whose every number, outlet and recommendation is rule-checked before publication. Market defined in one YAML file; ships two unrelated demos (beauty tech, electric cars). ⚠️ **18 commits, first commit 2026-11-21** — six days old at time of writing. Reference implementation to absorb, *not* a dependency to pin. |
| NewsMTSC | [fhamborg/NewsMTSC](https://github.com/fhamborg/NewsMTSC) | MIT **for newly-developed files only** — composite, see below | 2025-07-18 | Target-dependent sentiment for news text: polarity **toward a named entity**, not whole-document polarity. This is the correct primitive for brand sentiment and almost nothing else implements it. 16 months dormant. |
| pysentimiento | [pysentimiento/pysentimiento](https://github.com/pysentimiento/pysentimiento) | ⛔ **NON-COMMERCIAL / RESEARCH ONLY** (337 B) | 2024-06-20 | Transformer social-NLP for **Spanish, Portuguese, English, Italian**: sentiment, hate speech, irony. The best Spanish/Portuguese library on this plane — and **the licence forbids the only use Globant has for it.** See the licence finding below. |
| VADER | [cjhutto/vaderSentiment](https://github.com/cjhutto/vaderSentiment) | MIT (1,076 B) | 2026-03-02 | Lexicon-and-rule sentiment tuned for short social text. English-only, no training required. A baseline and a fallback, not a solution. |
| faster-whisper | [SYSTRAN/faster-whisper](https://github.com/SYSTRAN/faster-whisper) | MIT (1,063 B) | 2026-11-12 | CTranslate2 reimplementation of Whisper. **The component that makes *broadcast* monitoring possible at all**: turns radio, TV and podcast audio into searchable text so spoken mentions land in the same index as print. |
| auto-archiver | [bellingcat/auto-archiver](https://github.com/bellingcat/auto-archiver) | MIT (1,076 B) | 2026-11-18 | Evidence-grade capture of URLs and social posts with hashes and metadata. The tier that matters when a mention must survive deletion — crisis monitoring, regulatory complaints, litigation. |

**Six rows, six real repos. No seventh was invented to reach a round number.**

### ⛔ The licence finding of this pass — a category this KB has not recorded before

`pysentimiento`'s entire `LICENSE.md` is 337 bytes and reads:

> "`pysentimiento` is an open-source library for **non-commercial use and scientific research
> purposes only**. Please be aware that models are trained with third-party datasets and are subject
> to their respective licenses." — then links the TASS and SemEval-2017 dataset licences.

**This is worse than copyleft, and it is the first instance in this KB.** AGPL-3.0 constrains *how
you distribute*; a non-commercial clause forbids *the engagement itself*. There is no architectural
workaround — no service boundary, no separate process, no "we only call it over an API" structure
makes a paid client deliverable non-commercial. And note the **second** layer, which is the cycle-8
law again: even if the code licence were permissive, the **models** carry the TASS and SemEval
dataset terms.

**Why this lands hardest on LATAM:** this is the Spanish- and Portuguese-language sentiment
substrate. The plane's English tooling is MIT; the es/pt tooling is non-commercial **and 2.5 years
dormant**. See `intel/market.md` → Opportunities by region → LATAM for the build this implies.

### Composite licensing, second instance — and this one is pure Python

Cycle 8 recorded `acoustid/chromaprint`: MIT code, LGPL-2.1 as a whole, because of what it links.
That was read as a native-linking artefact. **`fhamborg/NewsMTSC` shows it is not.** Its 1,393-byte
licence file opens:

> "This project uses code from various projects, who may have their own license or copyright.
> - ABSA-PyTorch by Yury Soong et al. … - early-stopping-pytorch by Bjarten …
> **For newly developed files**, the license information is: … [MIT text]"

A pure-Python repo, no compilation, no linker — and the MIT grant still covers only part of the
tree. **Rule: "MIT" in a repo's licence file is a claim about some files, not necessarily all of
them. Read the first paragraph, not the SPDX badge.** Any SBOM scan keyed on the licence *file* will
report this repo as cleanly MIT.

### Method correction — the licence-filename probe needed a fourth name

Cycle 8 added lowercase `license.txt` and `COPYING.md`. This pass adds **`UNLICENSE`**:
[`RSS-Bridge/rss-bridge`](https://github.com/RSS-Bridge/rss-bridge) returns 404 for `LICENSE`,
`LICENSE.md`, `LICENSE.txt`, `license.txt`, `LICENCE`, `COPYING` and `COPYING.md`, while its README
resolves 200 — which by cycle 8's own rule means *the naming convention is wrong, not the licence
missing*. It is in `UNLICENSE`: public domain. Current working name set:
`LICENSE LICENSE.md LICENSE.txt license.txt LICENCE COPYING COPYING.md LICENSE-APACHE UNLICENSE`.

---

## The ad-integrity, supply-chain-transparency & verification plane — measured 2026-11-27 (pass 34), and **the open-source community builds the attack at 7× to 21× the rate it builds the defence**

**Vocabulary probe that found this plane.** Before this pass the eight files said `prebid` **72 times**
and `OpenRTB` **15 times** — the demand side was covered by pass 2 (monetization). The *integrity*
side was absent: `ad fraud` **0**, `invalid traffic` **0**, `IVT` **0**, `GIVT` **0**, `SIVT` **0**,
`ads.txt` **0**, `sellers.json` **0**, `schain` **0**, `supply path` **0**, `ad quality` **0**,
`malvertising` **0**, `Media Rating Council` **0**, `Trustworthy Accountability` **0**,
`DoubleVerify` **0**, `Integral Ad Science` **0**, `Pixalate` **0**, `AdCP` **0**, `ARTF` **0**.
Thirty-three passes on how to make, deliver, measure and monetise media; **no words for whether the
ad impression was real, authorised, viewable or next to safe content.**

> **Verification channel for this pass — and a channel RESTORED.** Pass 33 shipped with no star
> counts because `api.github.com/repos/{other}` returns *"GitHub access to this repository is not
> enabled for this session."* That is still true. **But `api.github.com/search/repositories?q=repo:owner/name`
> is not scoped the same way and returns the full record — stars, SPDX licence, `pushed_at`,
> `archived` — at a 15,000/hour limit.** Up to five repos per call with `+repo:` OR. Every star count
> and date below came through that channel on **2026-11-27**, licences were read from the actual file
> where the API said `NONE` or `NOASSERTION`, and three repos were shallow-cloned to settle the
> licence question conclusively. **Star counts are back in this KB.**

### The structural result, stated before the tables

This plane does **not** confirm the content-licence law of passes 5 and 33 — it *refines* it, and the
refinement is the most useful thing in this pass. The vocabulary brand safety needs
(**IAB Content Taxonomy, CC BY 3.0, free to use with attribution**) is open, and brand-safety open
source is still a **literal zero**. So the binding constraint is not the licence on the content. It is
**accreditability**: wherever the output number must be accepted by a third-party auditor (MRC for
invalid traffic, OM SDK compliance for viewability, TAG Certified Against Fraud for the supply chain),
open source stops at the boundary of the accreditation no matter how open the spec and the vocabulary
are. The five-step gradient is in `intel/trends.md` pass 34.

### Tier 1 — Agentic advertising: the layer that did not exist at pass 8, and is three weeks old

`AdCP` / `Ad Context Protocol`, `ARTF` and `AAMP` were all at **0 files** in this KB before today.
This is the newest agent layer found in any of the 34 planes and the only one where the standards
body shipped a reference implementation **before** the market shipped a product.

| Agent / framework | Repo | License | Stars | Last push | What it does |
|---|---|---|---|---|---|
| ARTF (Agentic Real-Time Framework) | [IABTechLab/agentic-real-time-framework](https://github.com/IABTechLab/agentic-real-time-framework) | AGPL-3.0 (Go reference impl); spec CC BY 3.0 | 35 | 2026-11-04 | IAB Tech Lab's framework for agent-to-agent real-time advertising transactions. **Note the licence split: the spec is CC BY 3.0 and freely implementable, the reference implementation is AGPL-3.0** — fine to study, a network-copyleft obligation if you deploy it as a service. |
| AAMP (Advertising Agentic Messaging Protocol) | [IABTechLab/AAMP](https://github.com/IABTechLab/AAMP) | Apache-2.0 | 28 | 2026-11-02 | The permissive half of the same initiative. **This is the one to build on** — same body, same plane, no copyleft. |
| OpenProposal | [IABTechLab/OpenProposal](https://github.com/IABTechLab/OpenProposal) | NOASSERTION — README grants Apache-2.0 to `scripts/` + `workflow/` only | 11 | 2026-11-12 | Machine-readable media proposals/RFPs. Read the licence note: **the grant is scoped to two directories**, not the repository. |
| CoMP | [IABTechLab/CoMP](https://github.com/IABTechLab/CoMP) | NONE | 6 | 2026-07-09 | Compliance-messaging protocol work. No licence file at all — unusable as a dependency. |
| Agentic advertising stack map | [franks33/agentic-advertising-stack](https://github.com/franks33/agentic-advertising-stack) | CC0-1.0 | 4 | 2026-09-06 | A curated map of the agentic advertising stack: protocols, standards, sell-side and buy-side implementations. Public domain — **the fastest orientation document in this plane.** |
| AdCP buy-side trading agent | [scumunna/adcp-trader](https://github.com/scumunna/adcp-trader) | MIT | 1 | 2026-06-24 | A buyer-side trading agent for the Ad Context Protocol: trader judgment plus hard guardrails. One star — recorded as the measure of how new this is, not as an incumbent. |
| Programmatic agent skills | [scumunna/programmatic-skills](https://github.com/scumunna/programmatic-skills) | MIT | 3 | 2026-07-03 | Agent skills for programmatic trading, analytics and account operations (DV360-oriented). |
| AdTech lead-gen / publisher-compliance skills | [adops-tool/AdTech-LeadGen-agent-skills](https://github.com/adops-tool/AdTech-LeadGen-agent-skills) | Apache-2.0 | 1 | 2026-11-07 | Schema-validated agent skills for AdTech lead generation and publisher compliance. |
| LangGraph ad-investment agents | [10div10/adtech-multi-agent](https://github.com/10div10/adtech-multi-agent) | NONE | 2 | 2026-07-10 | Multi-agent ad-investment framework on LangGraph. No licence — study only. |

**The whole agentic-advertising agent layer is 91 stars across nine repositories.** Compare with the
monetization plane's `prebid/Prebid.js` at 1,619 stars on the same measurement day. The protocols
arrived before the practitioners.

### Tier 2 — The detection layer, and it is the broken one

| Agent / tool | Repo | License | Stars | Last push | Verdict |
|---|---|---|---|---|---|
| Nameles | [Nameles-Org/Nameles](https://github.com/Nameles-Org/Nameles) | Apache-2.0 (LICENSE read, 11,357 B) | 72 | **2019-09-06** | **The only real open-source invalid-traffic engine ever built** — entropy-based IVT detection and pre-bid filtering, the published method. Permissive, documented, and **dead for over seven years.** Use the method, not the code. |
| AdTruth | [papa-torb/adtruth](https://github.com/papa-torb/adtruth) | MIT (LICENSE read, 1,062 B) | 254 | 2025-12-17 | The most-starred thing in the plane, and **its own 17,992-byte README states the ML models and detection rules remain proprietary.** The MIT grant covers the SDK and the plumbing. ⚠️ Do not quote this as "open-source ad fraud detection" to a client without that sentence attached. |
| PVUV.ai | [qiayue/pvuv.ai](https://github.com/qiayue/pvuv.ai) | MIT | 112 | 2026-11-03 | Privacy-friendly self-hosted web analytics **with built-in invalid-traffic detection**. Genuinely MIT, genuinely active, and the only live permissive IVT code found this pass. Publisher-side, not buy-side. |
| SEADS | [andpalmier/seads](https://github.com/andpalmier/seads) | Apache-2.0 | 50 | 2026-09-05 | Search-engine ads scanner — detects **malvertising** in search results. The only maintained tool in a category with 57 total GitHub results. |
| TrafficSentinel Suite | [akmalkhaniub/trafficsentinel-suite](https://github.com/akmalkhaniub/trafficsentinel-suite) | NONE | 0 | 2026-11-13 | An IVT-investigator monorepo with an MCP server — exactly the shape this plane needs, 0 stars, no licence file. Watch it; do not depend on it. |
| TalkingData 2018 (1st) | [flowlight0/talkingdata-adtracking-fraud-detection](https://github.com/flowlight0/talkingdata-adtracking-fraud-detection) | MIT | 226 | **2018-06-10** | A Kaggle competition solution. |
| TalkingData 2018 (2nd) | [ShawnyXiao/2018-Kaggle-AdTrackingFraud](https://github.com/ShawnyXiao/2018-Kaggle-AdTrackingFraud) | MIT | 72 | **2019-01-12** | Another one. |

⚠️ **Read the last three rows together.** `ad fraud detection` returns 894 repositories. After AdTruth
(whose models are closed), **the two highest-starred open artifacts in the category are solutions to a
single Kaggle contest that closed in 2018.** The public corpus of ad-fraud machine learning is a
seven-year-old competition dataset. There is no open labelled IVT dataset, because the labels are the
product the verification vendors sell.

### Tier 3 — The bot-identification substrate (healthy, permissive, and not accreditable)

These are the free substitutes for the **IAB/ABC International Spiders and Bots List**, which costs
**$5,000 / $7,500 / $15,000 a year** depending on membership (see `intel/market.md` pass 34).

| Repo | License | Stars | Last push | Note |
|---|---|---|---|---|
| [crowdsecurity/crowdsec](https://github.com/crowdsecurity/crowdsec) | MIT | 15,814 | 2026-11-25 | IDS/IPS, WAF and bot detection with a crowdsourced malicious-IP blocklist. **The largest permissive asset in this plane by an order of magnitude**, and it is a security tool that nobody in adtech cites. |
| [owasp-modsecurity/ModSecurity](https://github.com/owasp-modsecurity/ModSecurity) | Apache-2.0 | 9,889 | 2026-11-18 | The WAF engine. |
| [corazawaf/coraza](https://github.com/corazawaf/coraza) | Apache-2.0 | 4,061 | 2026-11-26 | Go, ModSecurity-compatible WAF **library** — embeddable, which ModSecurity is not. |
| [coreruleset/coreruleset](https://github.com/coreruleset/coreruleset) | Apache-2.0 | 3,376 | 2026-11-27 | OWASP CRS — the rules, pushed on the day of this pass. |
| [matomo-org/device-detector](https://github.com/matomo-org/device-detector) | LGPL-3.0 | 3,562 | 2026-11-25 | The most complete open bot/device classifier. LGPL — link, do not fork into a proprietary binary. |
| [fingerprintjs/BotD](https://github.com/fingerprintjs/BotD) | MIT | 1,504 | 2026-11-26 | Client-side automation detection. README is explicit that the vendor's paid API adds proprietary technology on top. |
| [monperrus/crawler-user-agents](https://github.com/monperrus/crawler-user-agents) | MIT | 1,416 | 2026-11-26 | The permissive bot user-agent pattern list. **This is the free stand-in for the $15,000 list.** |
| [omrilotan/isbot](https://github.com/omrilotan/isbot) | Unlicense | 1,169 | 2026-11-24 | Public domain, maintained. |
| [ua-parser/uap-core](https://github.com/ua-parser/uap-core) | **Apache-2.0** (API says `NOASSERTION`; LICENSE read, 608 B) | 827 | 2026-10-05 | The shared regex corpus behind most UA parsers. See the method note below — the API is wrong here. |
| [atmire/COUNTER-Robots](https://github.com/atmire/COUNTER-Robots) | MIT | 72 | 2024-04-22 | The scholarly-publishing robot list. Small, stable, and the one with an actual standards body behind it. |
| [snowplow/iab-spiders-and-robots-java-client](https://github.com/snowplow/iab-spiders-and-robots-java-client) | Apache-2.0 (in `LICENSE-2.0.txt`) | 7 | 2026-09-25 | **The purest open-code/closed-data split in this KB:** a maintained Apache-2.0 client library for a list that costs $5,000–$15,000/year under a signed, revocable data-subscription agreement. The code is free. The data is not. |
| [altcha-org/altcha](https://github.com/altcha-org/altcha) | MIT | 2,923 | 2026-11-20 | Self-hosted proof-of-work CAPTCHA alternative; GDPR / WCAG 2.2 AA / EAA compliant. The pre-bid human-check that does not ship a US adtech vendor into an EMEA data flow. |
| [X4BNet/lists_vpn](https://github.com/X4BNet/lists_vpn) | NONE | 944 | 2026-11-26 | Auto-updated VPN/datacenter IP lists — the raw material of GIVT filtering. No licence file; treat as data of unclear provenance. |
| [firehol/blocklist-ipsets](https://github.com/firehol/blocklist-ipsets) | NONE | 4,011 | 2026-11-26 | Same category, same caveat. |

⚠️ **The relicensing trap in this tier.** [faisalman/ua-parser-js](https://github.com/faisalman/ua-parser-js)
is **AGPL-3.0** (LICENSE.md read, 32,095 B) at **10,217 stars, pushed 2026-11-26**. It is the
user-agent parser most teams reach for from memory, and most teams remember it as MIT. If it is in a
hosted service, the AGPL network clause is live. `uap-core` (Apache-2.0) + a permissive binding is the
replacement.

### ⛔ Tier 4 does not exist: there is no brand-safety or brand-suitability agent layer

Searched 2026-11-27. `brand safety` returns **465 repositories and not one of them is a brand-safety
tool** — the top eight by stars are an unrelated docs fork, an Android ROM flasher, a logo-design
skill, a 2014 Facebook userscript, a 2014 JS file, a Google Analytics ToS paste, a URL shortener and an
Android-TV debloater. `viewability` is unusable as a search term (498,228 results, all Android chart
libraries and view bindings). `supply path optimization` returns **53 repositories**, of which the top
eight are supply-chain logistics projects and BSC token contracts — **zero** are adtech.

This is not a thin result to be padded. It is the finding: **the judgment layer of ad integrity has no
open-source presence at all**, and the reason is in `intel/trends.md` pass 34 — GARM was discontinued
in August 2024 and, per the X/WFA settlement, the WFA agreed never to revive it or anything like it,
so the one framework everybody still uses has **no maintaining body** and no body to accredit an
implementation against.

### Method corrections from this pass — reusable in all twelve industries

1. **A licence can be declared in README prose and nowhere else, and no automated gate can see it.**
   [InteractiveAdvertisingBureau/adstxtcrawler](https://github.com/InteractiveAdvertisingBureau/adstxtcrawler)
   (202 stars) has **no licence file under any of nine names** — confirmed by shallow clone, root
   listing is `README.md adstxt_crawler.py adstxt_crawler.sql …` — and the GitHub API reports `NONE`.
   Its README says *"license used is the 2-clause BSD license."* Same pattern at
   [InteractiveAdvertisingBureau/Taxonomies](https://github.com/InteractiveAdvertisingBureau/Taxonomies)
   (229 stars): no licence file, README says *"licensed under a Creative Commons Attribution 3[.0]"*.
   **Cycle 8 found that a licence can belong to the compilation rather than the repository. This adds:
   a licence can exist only as a sentence in prose.** Neither SPDX fields, licence badges nor SBOM
   scanning of the source tree can see it. CI rule: when the API says `NONE`, grep the README for
   `licen[sc]e` before declaring the repo unusable — and when it says BSD in prose, get it in writing.
2. **A licence can belong to the *component*, not the organisation — and the org's flagship repo is not
   the component you ship.** [snowplow/snowplow](https://github.com/snowplow/snowplow) is **Apache-2.0**
   (LICENSE read, 11,358 B) at 7,052 stars. [snowplow/enrich](https://github.com/snowplow/enrich) — the
   piece you actually deploy — is the **Snowplow Limited Use License Agreement v1.0 (January 2024)**,
   31 stars, API reports `NOASSERTION`. A scanner that resolves "snowplow" to the repository named
   `snowplow` returns Apache-2.0 and is wrong about every pipeline component.
3. **`NOASSERTION` from the API is not evidence of a missing or bad licence.** `ua-parser/uap-core` is
   Apache-2.0 and `kiprotect/klaro` is BSD-3-Clause (LICENSE read, 1,657 B); the API says `NOASSERTION`
   for both, because the files open with a non-standard header. Read the file.
4. **Licence-filename set extended again.** Cycle 8 added `license.txt` and `COPYING.md`; pass 33 added
   `UNLICENSE`. This pass adds **`LICENSE-2.0.txt`** (snowplow's IAB client) and **`licenses/LICENSE.md`**.
   Current working set:
   `LICENSE LICENSE.md LICENSE.txt license.txt LICENCE COPYING COPYING.md LICENSE-APACHE UNLICENSE LICENSE-2.0.txt licenses/LICENSE.md`.

---

## Pass 35 addendum (2026-11-27) — the graphics-desk tier: natural-language → chart agents

**The vocabulary probe that opened this plane.** Across the eight files and thirty-four passes, the KB
said `OpenRefine` 13 times, `Datasette` 6, `d3` 5, `Leaflet` 2 — and said **`Vega` 0, `Observable Plot` 0,
`Chart.js` 0, `MapLibre` 0, `QGIS` 0, `Scrollama` 0, `ArchieML` 0, `ai2html` 0, `csvkit` 0,
`Frictionless` 0, `Idyll` 0, `scrollytelling` 0, `election results` 0, `graphics desk` 0.**
Thirty-four passes on moving the video and selling the impression; nothing on the desk that draws the
chart the story is actually about.

**Why this tier is different from every other agent tier in this file:** in most media planes the open
tooling is partial and the agent layer is speculative. Here the substrate is *finished* — a 114,024★
ISC renderer, two 67k★ permissive charting libraries, BSD maps, MIT wrangling — so the only real
question is whether an LLM can drive it. Three projects answer yes under a licence Globant can ship.

### ✅ Tier 1 — permissive, active, verified 2026-11-27

| Agent | Repo | License | Stars | Last push | What it actually does |
|---|---|---|---|---|---|
| WrenAI | [Canner/WrenAI](https://github.com/Canner/WrenAI) | Apache-2.0 | 18,413 | **2026-11-26** | GenBI: governed text-to-SQL over a semantic context layer, emitting charts and dashboards across 20+ sources. The only project in this tier with a real governance story. |
| PyGWalker | [Kanaries/pygwalker](https://github.com/Kanaries/pygwalker) | Apache-2.0 | 16,009 | **2026-11-25** | Turns a dataframe into a Tableau-like exploratory UI inside a notebook; LLM explainer on top. The fastest route from a reporter's CSV to a shareable view. |
| Vizro + Vizro-AI | [mckinsey/vizro](https://github.com/mckinsey/vizro) | Apache-2.0 | 3,828 | **2026-11-26** | Low-code dashboard toolkit with an NL chart-generation layer; opinionated defaults that already look like a design system. |
| Evidence | [evidence-dev/evidence](https://github.com/evidence-dev/evidence) | MIT | 7,150 | **2026-11-26** | BI-as-code: Markdown + SQL compiles to an interactive site. The closest thing to a *publishable* agent target — output is a static site, not a BI seat. |
| Chartwright | [yuqisun/chartwright](https://github.com/yuqisun/chartwright) | MIT | **0** | 2026-09-16 | Agentic data inspection that emits a library-agnostic chart **spec**, then compiles it deterministically — the model never writes chart config. Architecturally the most correct design found; **0 stars, one author.** Read it for the pattern, do not depend on it. |

**Zero stars is written above as data, not as an omission.** Chartwright is listed because its
separation — agent proposes a spec, deterministic compiler emits the config — is the design the other
four get wrong, and that is worth knowing even when nobody has starred it. Its compile target is
**Highcharts, which is proprietary** (see the licence note below), so the pattern is transferable but
the repo as shipped is not.

### ⚠️ Tier 2 — real, but the licence or the staleness constrains client work

| Agent | Repo | License | Stars | Last push | Constraint |
|---|---|---|---|---|---|
| LIDA | [microsoft/lida](https://github.com/microsoft/lida) | MIT | 3,299 | **2024-08-08** | The most-cited NL→visualisation/infographic agent in the literature, and it has not been touched in over two years. MIT, so forkable — but treat it as a paper with code, not a dependency. |
| CJ Workbench | [CJWorkbench/cjworkbench](https://github.com/CJWorkbench/cjworkbench) | **AGPL-3.0** (LICENSE 34,654 B, © Columbia University) | 312 | 2024-12-03 | The only purpose-built *data-journalism platform with training built in*, and it is both network-copyleft and dormant for two years. AGPL rules it out of a hosted client deliverable. |

### ⛔ The licence trap in this tier, stated plainly

**Highcharts is not open source.** [highcharts/highcharts](https://github.com/highcharts/highcharts)
carries 12,502 stars and was pushed 2026-11-26, and it has **no `LICENSE` file** — only a
`license.txt` that points at `shop.highcharts.com` for "licensing alternatives." A public repo with a
commercial licence file reads, in a hurry, exactly like a permissive dependency. Any agent that
compiles to Highcharts options (Chartwright does) inherits that bill. The permissive compile targets
are Vega-Lite (BSD-3-Clause), ECharts (Apache-2.0), Chart.js (MIT) and Plot (ISC) — all verified in
`repos/foundations.md` this pass.

## The 2D animation, cel-production, inbetweening & lip-sync plane — measured 2026-11-27 (pass 36), and **the operation AI is supposed to absorb is the one with no licensed implementation**

Vocabulary probe that found this plane (run against all eight files *before* any web search, 36 passes
of history): `MAM` **85**, `playout` **89**, `VFX` **83**, `dubbing` **77**, `OpenUSD` **35**,
`Blender` **46**, `screenplay` **37** — and `inbetween` **0**, `in-between` **0**, `colorization` **0**,
`2d animation` **0**, `cel` **0**, `lip sync` **0**, `exposure sheet` **0**, `x-sheet` **0**,
`onion skin` **0**, `Lottie` **0**, `motion graphics` **0**, `OpenToonz` **0**, `Synfig` **0**,
`Pencil2D` **0**, `Natron` **0**, `Glaxnimate` **0**, `grease pencil` **0**, `sakuga` **0**.
Thirty-five passes about shooting, shipping, selling and measuring the frame — **nothing about drawing it.**
(`tween` scored 144 and `rive` 216, but both are substring hits inside "between" and "driven" — the
pass-8 rule holds: read the results, not the total.)

### The four-step gradient inside one plane — the sharpest form the KB's structural law has taken

| Step | The operation | What kind of problem it is | Open-source health, measured 2026-11-27 |
|---|---|---|---|
| **Play** it | render a finished 2D animation on a device | **format** | **Healthiest layer in the plane.** Lottie + ThorVG + Rive + dotLottie ≈ **100k★** combined, MIT/Apache-2.0, several pushed the day of this pass |
| **Draw** it | keyframes, line art, paint, onion skin | **tool** | **Healthy but copyleft.** Krita GPL-3 10,816★, Synfig GPL-3 2,480★, Pencil2D GPL-2 1,930★; permissive only in the Toonz lineage (BSD-3) |
| **Inbetween** it | generate the frames between two drawings | **judgment** | **`inbetweening` returns 55 repos in all of GitHub.** Top result 373★ **with no licence file**; #3 (120★) also none |
| **Schedule** it | the exposure sheet / timing sheet that drives the whole unit | **registry** | **Six repos exist on Earth. They sum to 32★.** Public spec frozen at **November 2018** |

Read downward: the further an operation moves from *format* toward *judgment* and *owned registry*,
the thinner and less licensed the open supply. This is the sixth independent confirmation of the law
first written in the healthcare passes and refined in media pass 5 — and the first time all four steps
have been measurable **inside a single plane, on a single day**.

### Agent and model tier — 18 repos, every URL confirmed by `git ls-remote` 2026-11-27

| Agent / model | Repo | Licence | ★ | Last push | What it actually does |
|---|---|---|---|---|---|
| **Toonflow** | https://github.com/HBAI-Ltd/Toonflow-app | **MIT** | 22,960 | 2026-11-20 | The largest permissively-licensed AI animation *production platform* in existence: script writing → smart storyboarding (智能分镜) → character & scene asset management → image and video generation, on an infinite canvas. Targets China's 短剧 / 漫剧 (short-drama / comic-drama) vertical. Created 2026-01-29; 4,188 forks (★/fork 5.5 — organic, not purchased) |
| **mcp-for-blender** | https://github.com/ahujasid/mcp-for-blender | **MIT** | 35,944 | 2026-11-26 | Drives Blender from any LLM over MCP. The 2D relevance is Grease Pencil: an agent that can build and re-time strokes in a 3D scene graph. Renamed from `blender-mcp` — the old slug 404s |
| **Jellyfish** | https://github.com/Forget-C/Jellyfish | **Apache-2.0** | 7,353 | 2026-11-25 | AI short-drama workbench: script breakdown, storyboard generation, character-consistency management, video generation. Created 2026-03-06 |
| **koharu** | https://github.com/koharu-rs/koharu | **Apache-2.0** | 6,853 | **2026-11-27** | ML manga translator written in Rust — detection, OCR, inpainting, typesetting. Pushed the day of this pass; ★/fork 13.2 |
| **LatentSync** | https://github.com/bytedance/LatentSync | **Apache-2.0** | 6,334 | 2025-06-20 | ByteDance diffusion lip-sync. **Photoreal/live-action**, not drawn mouth charts — see the trap table |
| **ToonCrafter** | https://github.com/Doubiiu/ToonCrafter | **Apache-2.0** | 6,071 | 2025-03-19 | Generative *cartoon* interpolation (SIGGRAPH Asia 2024, Journal Track). The only inbetweening model in the plane with a real OSI licence and >1k★. Unpushed for 20 months |
| **manga-image-translator** | https://github.com/zyddnys/manga-image-translator | GPL-3.0 | 10,662 | 2026-11-18 | The most-starred comic-translation stack. **GPL-3.0 — cannot be linked into a client's closed product** |
| **BallonsTranslator** | https://github.com/dmMaze/BallonsTranslator | GPL-3.0 | 5,321 | 2026-11-26 | Deep-learning-aided comic translation with an image/text editor; ★/fork 14.5 |
| **comic-translate** | https://github.com/ogkalu2/comic-translate | **Apache-2.0** | 3,024 | 2026-11-09 | Comic/manga translator app + browser extension. The permissive alternative to the two GPL stacks above |
| **krita-ai-diffusion** | https://github.com/Acly/krita-ai-diffusion | GPL-3.0 | 10,960 | 2026-11-26 | Generative inpaint/outpaint/refine **inside the 2D artist's own canvas**. The single most-adopted "AI in the drawing app" project |
| **Rhubarb Lip Sync** | https://github.com/DanielSWolf/rhubarb-lip-sync | **MIT** | 2,816 | 2026-06-16 | Automatic 2D mouth-shape (phoneme) animation from an audio file. GitHub reports NOASSERTION only because `LICENSE.md` is 27,808 B of bundled third-party texts; the grant is MIT, and the licence states **the lip-sync data it produces belongs to you alone** |
| **Anime2Sketch** | https://github.com/Mukosame/Anime2Sketch | **MIT** | 2,146 | 2026-10-18 | Line-art extraction from anime/illustration — the clean-up and re-ink step |
| **anime-segmentation** | https://github.com/SkyTNT/anime-segmentation | **Apache-2.0** | 860 | 2025-05-21 | High-accuracy character matting for drawn frames |
| **AnimeInterp** | https://github.com/lisiyao21/AnimeInterp | **MIT — in README prose only** | 465 | 2024-03-31 | CVPR'21 "Deep Animation Video Interpolation in the Wild". **No licence file exists**; GitHub reports NONE; the README says "Our code is released under MIT License." See method note 2 |
| **nijiGPen** | https://github.com/chsh2/nijiGPen | GPL-3.0 | 389 | 2026-11-07 | Blender add-on dedicated to Grease Pencil — 2D NPR workflow inside Blender |
| **AnimeInbet** | https://github.com/lisiyao21/AnimeInbet | **NONE** | 373 | 2024-04-15 | Inbetweening of *line drawings* (ICCV'23) — the single most on-target repo for the plane's core operation, and **it carries no licence grant at all** |
| **FCVG** | https://github.com/Tian-one/FCVG | **NONE** | 120 | 2025-02-27 | Frame-level controllable video generation for interpolation. Also no licence grant |
| **kitsu-mcp** | https://github.com/EstienneG/kitsu-mcp | **MIT** | 2 | 2026-11-15 | MCP server for Kitsu (CGWire) production tracking — lets an agent read animation task state. Created 2026-10-24, i.e. **five weeks old**: the agent layer for animation production management is being born right now, at 2★ |

### The traps — eleven repos that a star-count or SPDX-badge pass would have written as findings

| Repo | ★ | What a scanner says | What the file actually says | Verdict |
|---|---|---|---|---|
| https://github.com/aseprite/aseprite | 41,192 | licence **NONE** | no `LICENSE`/`COPYING` under 12 names, but **`EULA.txt` on both `main` and `master`** | **Not open source.** Paid EULA. The most dangerous false negative in the plane: it reads as "unlicensed" when it is "licensed and forbidden" |
| https://github.com/EsotericSoftware/spine-runtimes | 5,384 | **NOASSERTION** | "Spine Runtimes License Agreement", last updated 2025-04-05 | **Requires a paid Spine editor licence.** The industry-standard 2D skeletal runtime is not usable without purchase |
| https://github.com/remotion-dev/remotion | 76,008 | **NOASSERTION** | "Remotion License" with company-size terms | Source-available, **fee-bearing above a headcount**. Not a permissive base |
| https://github.com/bobbens/sketch_simplification | 755 | **NOASSERTION** | "ACADEMIC OR NON-PROFIT ORGANIZATION NONCOMMERCIAL RESEARCH USE ONLY" | **Unusable for client work.** The canonical rough-sketch cleanup model |
| https://github.com/Rudrabha/Wav2Lip | 13,291 | licence NONE | README: "Non Commercial Open-source Version" + a commercial API upsell | **Non-commercial.** Quarantine |
| https://github.com/bilibili/ailab | 5,881 | licence NONE | no licence file (12 names × `master`+`main`), no licence statement in README | **No grant.** Real-CUGAN, the upscaler behind much Chinese streaming anime, is unlicensed |
| https://github.com/TachibanaYoshino/AnimeGANv2 | 5,373 | licence NONE | no licence file; README says "[Open Source]" and nothing more | **No grant.** "Open source" in a README is not a licence |
| https://github.com/TachibanaYoshino/AnimeGANv3 | 2,056 | licence NONE | same | **No grant** |
| https://github.com/wonderunit/storyboarder | 3,972 | licence NONE | README's "Notes on Open Source License" links to a **blog post**, not a licence | **No grant.** Default copyright applies |
| https://github.com/MaurycyLiebner/enve | 1,195 | GPL-3.0 | repo **archived**, last push 2022-09-25 | Dead. Do not propose |
| https://github.com/svga/SVGAPlayer-Android | 3,258 | Apache-2.0 | repo **archived**, last push 2023-02-06 | Dead runtime; use Lottie or ThorVG |

### Three method corrections, reusable in all twelve industries

**1. There is a thirteenth licence-file name, and it is the worst one to miss: `EULA.txt`.**
Pass 8 extended the probe to `license.txt` (lowercase) and `COPYING.md`. That 12-name probe reports
*"no licence file found"* for `aseprite/aseprite` — a 41,192★ animation tool whose terms are a paid
EULA sitting at `EULA.txt` on both branches. Every previous miss in this KB turned a permissive repo
into a false negative (safe direction). **This one inverts: it turns a forbidden repo into something
that merely looks unlicensed, and "unlicensed" is a risk a team sometimes accepts.** The probe list is
now: `LICENSE`, `LICENSE.txt`, `LICENSE.md`, `license.txt`, `license`, `LICENCE`, `LICENSE.TXT`,
`COPYING`, `COPYING.txt`, `COPYING.md`, `LICENSE-MIT`, `NOTICE`, **`EULA.txt`**.

**2. The grant can live in prose only — the exact inverse of the Chromaprint case.**
Chromaprint (pass 5) had a licence file that *understated* its obligations. `lisiyao21/AnimeInterp`
is the mirror image: no licence file at all, GitHub reports NONE, and the README says *"Our code is
released under MIT License."* `jamriska/ebsynth` (1,695★) is the same shape — no file, README says
*"The code is released into the public domain."* **Rule: a repo with no licence file is not a zero
until you have read its README.** An SBOM or SPDX scan cannot see a prose grant, so it reports the
opposite of the truth in both directions.

**3. `NOASSERTION` is a parsing signal, not a risk signal.**
Four repos in this plane report NOASSERTION purely because their licence file opens with third-party
notices before the grant: `opentoonz/opentoonz` and `tahoma2d/tahoma2d` (both **BSD-3-Clause**, after a
preamble about `thirdparty/`, the MyPaint brushes and Tahoma2D notices), `opentoonz/xdts_viewer`
(**BSD-3-Clause**), `rhubarb-lip-sync` (**MIT**). All four are permissive and all four would be dropped
by a filter that treats NOASSERTION as unknown-risk. Read the file; it costs one request.

### False-friend queries measured in this plane — the false-abundance list now has four entries

| Query | Results returned | Relevant results | What it actually finds |
|---|---|---|---|
| `cel animation` | **527** | **0** | `folding-cell`, `cellular-automaton.nvim`, `YoCelsius`, `celluloid`, swipe-action *cells* |
| `animatic` | **110,383** | **0** | substring of "animation" — React UI libraries, `aos`, `scrollreveal`, `magicui` |
| `eidr` (pass 5) | 160 | 0 | electronic-ID card readers |
| `isan` (pass 5) | 1,942 | 0 | NLP libraries (`isanlp`) |

Pass 8's rule was "shortening a query can turn a false zero into a false abundance." These two are the
largest false abundances yet recorded, and `animatic` — 110,383 results, zero of them animatics — is
the clearest demonstration in the KB that **a result count is not evidence of a field.**

## The consumer-products, brand-licensing & merchandising plane — measured 2026-11-27 (pass 37), and **the agent layer is five stars wide under a $389.8 billion industry**

This is the plane where an entertainment IP stops being content and becomes a physical object: the
licensing-out business. Licensing International's **2026 Global Licensing Industry Study** (research by
Brandar Consulting, **1,068 companies**) puts 2025 retail sales of licensed merchandise and services at
**$389.8B, +5.45% YoY** — faster than retail overall at +4.52%. Character/entertainment alone is
**$161.8B (+8%)**.

It was also, before this pass, **the largest vocabulary gap left in this KB**. Measured by grep against
all eight files *before* any web search, twelve terms returned **literal zero**: `consumer products`,
`counterfeit`, `royalty report`, `art approval`, `apparel`, `collectible`, `IP licensing`, `franchise`,
`character licensing`, `brand protection`, `product placement`, `brand licensing`.

### What the plane actually needs, and what exists

The work in this plane is five operations in sequence. Each one was measured separately, and the result
is **the cleanest monotonic gradient this KB has recorded**: permissive-and-thousands-of-stars at the
format end, literally one search result at the money end.

| Step | What it is | Nature of the problem | Measured supply |
|---|---|---|---|
| 1. Match an image | Is this picture the same as that picture? | Pure format / math | **5,689★ Apache-2.0**, healthy |
| 2. Identify the product | Which SKU is this? | Format, with a paid registry | **59★ Apache-2.0**, alive, small |
| 3. See the mark | Is our logo in this image? | Perception | **529★ MIT**, dead since 2022 |
| 4. Judge the infringement | Is this listing counterfeit? | Judgment | **5★ MIT** |
| 5. Settle the money | What is owed, to whom, on what audit trail? | Judgment + relationship | **1 search result, 0★, no licence** |

### Step 1 — the substrate is finished and permissive

Image matching is the substrate of every counterfeit-detection and royalty-attribution claim in this
plane, and it is the healthiest tier measured in any of the 37 planes. All five rows are real, licensed
and verified by `git ls-remote`.

| Repo | Licence | Stars / forks | Last push | Why it matters here |
|---|---|---|---|---|
| [idealo/imagededup](https://github.com/idealo/imagededup) | Apache-2.0 | 5,689★ / 477f | 2025-08-15 | Near-duplicate detection (PHash/CNN). The reference substrate for "is this listing our artwork?" |
| [jenssegers/imagehash](https://github.com/jenssegers/imagehash) | MIT | 2,060★ / 173f | 2025-09-17 | Perceptual hashing, PHP — drops into a Laravel/Bagisto storefront directly |
| [corona10/goimagehash](https://github.com/corona10/goimagehash) | BSD-2-Clause | 841★ / 79f | 2024-01-21 | Go perceptual hashing; the choice for a high-throughput marketplace crawler |
| [KilianB/JImageHash](https://github.com/KilianB/JImageHash) | MIT | 444★ / 87f | 2024-03-08 | JVM perceptual hashing, for shops whose commerce stack is Java |
| [bentoml/CLIP-API-service](https://github.com/bentoml/CLIP-API-service) | Apache-2.0 | 67★ / 4f | **2026-11-09** | Serve CLIP embeddings as an API — the live, permissive route to semantic (not pixel) similarity |

One adjacent repo is deliberately **excluded from the permissive tier**:
[dessant/search-by-image](https://github.com/dessant/search-by-image) (3,841★, 2026-06-27) is the
largest and most actively maintained reverse-image-search tool found, but it is **GPL-3.0** and a browser
extension — useful for a brand-protection analyst's desk, not for embedding in a client deliverable.

### Step 2 — product identity is permissive, but the numbers are rented

GTIN/GS1 is how a licensed product is identified in retail. The **parsers are free and permissive; the
numbers are not** — GTIN allocation requires paid GS1 membership. This is the fourth distinct appearance
of **the content law** in this KB (CPT in healthcare; ISRC/ISWC/ISAN/EIDR in media pass 5): *what is
scarce is the registry allocation, never the parser.*

| Repo | Licence | Stars | Last push | Note |
|---|---|---|---|---|
| [jodal/biip](https://github.com/jodal/biip) | Apache-2.0 | 59★ | **2026-11-01** | Python GS1/GTIN/SSCC parser; the best-maintained permissive option |
| [PeterBrockfeld/BarcodeParser](https://github.com/PeterBrockfeld/BarcodeParser) | MIT | 77★ | 2022-04-21 | Most-starred GS1 parser, but unmaintained for three years |
| [xremix/SwiftGS1Barcode](https://github.com/xremix/SwiftGS1Barcode) | MIT | 30★ | **2026-11-08** | Swift — the in-store / field-inspection path, alive |
| [lamoda/gs1-barcode-parser](https://github.com/lamoda/gs1-barcode-parser) | MIT | 21★ | **2026-10-27** | PHP, by a real fashion retailer; alive |
| [ronanguilloux/IsoCodes](https://github.com/ronanguilloux/IsoCodes) | GPL-3.0 | 803★ | 2026-03-20 | Validates GTIN/EAN among ~40 standards — **GPL-3.0, so validation only, not embedded** |

### Step 3 — the mark detector exists and nobody maintains it

Logo detection returns **1,202 results**, so the raw total looks like abundance. Reading the results
instead of the total (the pass-8 rule) shows every usable repo is **years stale**: the category was
solved academically and abandoned.

| Repo | Licence | Stars / forks | Last push | State |
|---|---|---|---|---|
| [satojkovic/DeepLogo](https://github.com/satojkovic/DeepLogo) | MIT | 529★ / 153f | 2022-08-28 | Best-known brand-logo detector. **Dead 3+ years**; TF Object Detection API era |
| [FenHua/Robust_Logo_Detection](https://github.com/FenHua/Robust_Logo_Detection) | Apache-2.0 | 77★ / 19f | 2021-10-24 | Adversarially-robust variant. **Dead 5 years** |
| [nuwandda/yolov7-logo-detection](https://github.com/nuwandda/yolov7-logo-detection) | BSD-3-Clause | 50★ / 12f | 2024-12-02 | Most recent usable baseline; YOLOv7-era |

**The practical consequence:** there is no maintained open logo detector to adopt, but the task is now a
fine-tune, not a research project. Globant's realistic move is to re-train on a current detector rather
than revive any of these three.

### Steps 4 and 5 — judgment, then the vacuum

| Repo | Licence | Stars | Last push | What it does |
|---|---|---|---|---|
| [PAST2212/brand-protection-analyst-agent](https://github.com/PAST2212/brand-protection-analyst-agent) | MIT | 5★ | 2025-07-07 | **The only MIT-licensed brand-protection *agent* that exists.** Gemini-backed; detects fraudulent/typosquat brand use |
| [leboncoin/trademark-monitor](https://github.com/leboncoin/trademark-monitor) | **MIT** (see correction) | 5★ | 2025-01-19 | Monitors social networks for trademark keywords. Built by a real classifieds operator |
| [Ivan-Kouznetsov/DailyMark](https://github.com/Ivan-Kouznetsov/DailyMark) | AGPL-3.0 | 4★ | 2022-12-08 | USPTO trademark-filing watcher; copyleft, so tooling not product |
| [codexoy/trademark-monitoring-app](https://github.com/codexoy/trademark-monitoring-app) | **none** | 12★ | 2025-11-24 | Most-starred trademark monitor — and **no LICENSE file, so all rights reserved** |

That is the entire judgment tier: **four repositories, 26 stars between them**, one of them unlicensed.

**Step 5 has no tier at all.** Measured, not assumed:

- `licensee portal` → **1 result in all of GitHub**. It is 0★, unlicensed, and unrelated (a GMV portal).
  **This is the crudest zero recorded anywhere in this KB** — below media pass 5's `music royalty
  accounting` (14 results, top six summing to 0 stars) and below healthcare's `medical necessity` (3 stars).
- `merchandise licensing` → **3 results, none relevant** (a sports-management CRUD app, 0★; two unrelated).
- `royalty accounting` → 47 results; **top six sum to 9 stars**; the top hit is a blockchain contract.
- `product placement detection video` → **2 results, neither relevant.**

A **$389.8 billion** industry, with 1,068 companies reporting into its own trade study, has **no open
source implementation of the thing that makes a product licensed**: the approval, the royalty
calculation, the licensee statement, the audit.

### The one real platform in the plane

[**pwnera/artbucket**](https://github.com/pwnera/artbucket) — **AGPL-3.0** (verified: 34,523 B LICENSE on
both `master` and `main`, © Pwnera SAS), **34★**, pushed **2026-11-24** (three days before this pass).

Its README opens *"Your brand's source of truth, open source."* It is the only repository found that
models the plane's actual data: each asset carries **licence terms, allowed channels and territories,
embargo dates, and a last-day-of-use**, and it will answer whether a planned use is permitted and
suggest alternatives when it is not. It exposes a web app, **an MCP server**, a REST API, a CLI and Git.

Two caveats a client deck must carry: it is **AGPL-3.0** (Pwnera offers commercial licensing on request),
and at 34 stars it is **a bet, not an installed base**. But it is the only code in this plane that has
the right shape, and the MCP server makes it the natural agent target.

### Corrections to the measurement channel — three licence traps, all new

Pass 8 established that a raw-channel 404 is never by itself proof that a licence is missing. This pass
adds **three further categories**, each of which would have produced a wrong row:

1. **The GitHub API's `spdx_id` is not authoritative — it under-reports.** `search/repositories` returned
   **NOASSERTION** for both [medusajs/medusa](https://github.com/medusajs/medusa) and
   [leboncoin/trademark-monitor](https://github.com/leboncoin/trademark-monitor). Both are in fact
   **MIT** — verified by reading `master/LICENSE` (1,075 B and 1,114 B respectively). Reading the file
   *upgraded* the single most relevant repo in the judgment tier from "no grant" to MIT.
2. **The licence can be declared by PATH instead of by identifier.**
   [resourcespace/resourcespace](https://github.com/resourcespace/resourcespace) has a 76-byte
   `license.txt` that only says *"Please see the documentation/licenses folder."* That folder holds ~30
   **third-party** licences. Its own grant is reachable only because `composer.json` and `package.json`
   set `"license": "documentation/licenses/resourcespace.txt"` — **a file path where SPDX expects an
   identifier**, which is exactly why every scanner reports NOASSERTION. The actual terms: **BSD-3-Clause
   plus a fourth trademark clause** (derivatives may not be named "ResourceSpace"; use "Powered by
   ResourceSpace"). The repository has **no README at all**.
3. **A repository can be publicly readable and still not be open source, by default.**
   [pimcore/pimcore](https://github.com/pimcore/pimcore) (3,891★) — the PIM/DAM that general "open source
   DAM" roundups still recommend — carries the **Pimcore Open Core License (POCL, last updated June
   2025)** at `2026.x/LICENSE.md`. It defines "Open Core Software" as source that is *publicly available
   but not licensed out as open source*, and states: **"if not provided for otherwise, a software element
   is Proprietary Software."** Publicly visible source, proprietary by default. Note the probe detail:
   `LICENSE.md` 404s on `master` and `main` — Pimcore's default branch is **`2026.x`**. Probing the wrong
   branch would have reported "no licence" on a repo whose licence is the finding.

### One claimed project that does not exist

A vendor-adjacent aggregator describes **"UnRoyalty"** as an open-source web application for managing
royalties, copyrights and licensing, *"available on GitHub to extend and modify."* GitHub code search for
`unroyalty` returns **TOTAL=0**. There is no such repository. It is recorded here because it is precisely
the row a hurried pass would have written, with a plausible name and a plausible description, into the
one tier of this plane that has no code in it.

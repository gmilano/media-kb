---
industry: media
region: Global
updated: 2026-11-25
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

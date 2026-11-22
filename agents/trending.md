---
industry: media
region: Global
updated: 2026-11-22
---

# 📈 Trending Media AI Agents — append-only log

> Newest section first. **Nothing below is ever rewritten** — that history is the only way to see
> which projects actually sustained momentum and which spiked and died.

## 2026-11-22 — pass 2: the monetization plane (a measured zero)

Second pass of the same day. The morning pass had already shipped this KB's eight files, so rather
than re-measure generation agents three hours later, this pass researched the one plane the KB had
never touched: **ad signalling, auction, decisioning and measurement.** `repos/trending.md` carries
the infrastructure findings; this file records the agent result.

**The agent result is zero, and it is reported as zero.** Searched `open source AI agent advertising
creative generation media buying github 2026 MIT Apache` plus the ad-tech cuts of the four prescribed
global queries. Everything returned was commercial — Creatify's *AI Media Buyer*, Omneky (API and MCP
server released, agent not open-sourced), AdsGency, Taboola's agent tooling. The one named
open-source candidate, `Nuraveda_lab/ai-ads-agent`, is on **Codeberg rather than GitHub** and
`git ls-remote` could not reach it, so it fails the existence test and gets **no row**.

| What was looked for | Result |
|---|---|
| Permissive GitHub-hosted ad-decisioning agent | **None found** |
| Permissive ad-creative generation agent (ad-specific) | **None found** — generation is covered by Tier 1 of `agents/top.md` already |
| Open ad-ops / campaign-orchestration agent | One unlicensed GitHub topic repo, no resolvable slug — **not carried** |

**Why a zero is worth a dated entry.** The infrastructure under this absent layer is in excellent
health — `prebid/Prebid.js` was pushed on the day of this measurement, and `apache/druid`/`pinot` are
ASF-maintained. So this is not "an immature field with nothing in it"; it is a mature permissive
infrastructure stack with **no open agent layer above it.** That asymmetry is the finding, and the
next pass should re-run the same query and see whether the zero moves. If it does, that is a real
trend signal. If a future pass fills this table without the proper name of an ad-tech artefact
(openrtb, scte-35, vast, prebid, tcf) in each row, that is keyword-collision ingest, not progress —
the sister `retail-kb` carried a Minecraft mod as inventory intelligence for exactly that reason.

**No corrections to the morning pass.** Its ten Tier-1 rows, the VideoSeal/AudioSeal watermarking
correction and the short-form-drama gap note were spot-checked and stand as written.

## 2026-11-22

Measured on 2026-11-22 via GitHub `search/repositories` (stars, forks, `pushed_at` and SPDX in one
call, so the figures can always be cross-checked); existence confirmed by `git ls-remote`; licenses
read from the LICENSE file wherever the API returned `NOASSERTION`.

**The headline: this KB's "clearest open-source gap in media" was never a gap.** The previous pass
recorded that *no permissive open watermarking library exists* and that *SynthID is Google-internal*.
Both are wrong. There is a whole MIT-licensed family, most of it actively maintained:

| Agent / Model | Repo | License | Stars | Forks | Last push | What it does |
|---|---|---|---|---|---|---|
| VideoSeal | [facebookresearch/videoseal](https://github.com/facebookresearch/videoseal) | MIT | 828 | 111 | 2026-11-10 | Meta's neural **video** watermarking — models, training and evaluation code all MIT. Survives re-encoding and editing; strength setting trades robustness against visibility. The direct answer to the gap this KB recorded. |
| AudioSeal | [facebookresearch/audioseal](https://github.com/facebookresearch/audioseal) | MIT | 804 | 109 | 2026-11-03 | Localized **audio** watermarking with sample-level detection — marks which *segments* of a track are synthetic. The missing piece for dubbed/cloned-voice deliverables. |
| TrustMark | [adobe/trustmark](https://github.com/adobe/trustmark) | **MIT** | 189 | 41 | 2026-11-11 | Adobe Research's invisible image watermarking, and the watermarking arm of C2PA's own soft-binding story. API reports `NOASSERTION`; the 1,218-byte LICENSE opens "Copyright 2023 Adobe All Rights Reserved" and **then grants MIT** — the same read-past-line-1 trap as SadTalker. |
| SynthID-Text | [google-deepmind/synthid-text](https://github.com/google-deepmind/synthid-text) | Apache-2.0 | 1,258 | 117 | 2026-11-18 | **Correction: SynthID is not entirely Google-internal.** The *text* watermarking is open and Apache-2.0. The image/video/audio SynthID remains closed — so the correct statement is "SynthID-Text is open, SynthID for AV is not." |
| invisible-watermark | [ShieldMnt/invisible-watermark](https://github.com/ShieldMnt/invisible-watermark) | MIT | 1,993 | 177 | 2023-09-23 | The DWT-DCT library Stable Diffusion ships by default — the most-deployed embedder here, and dormant since 2023. Fine to vendor, do not expect fixes. |
| Watermark Anything | [facebookresearch/watermark-anything](https://github.com/facebookresearch/watermark-anything) | MIT | 1,133 | 56 | 2025-06-20 | **ARCHIVED.** Localized image watermarking (multiple marks per image). Superseded by VideoSeal for new work. |
| RivaGAN | [DAI-Lab/RivaGAN](https://github.com/DAI-Lab/RivaGAN) | MIT | 324 | 44 | 2021-10-12 | Attention-based robust video watermarking. Research-grade, five years dormant; cited for lineage only. |

**Counter-signal, and it is the most important number in this pass: the removal ecosystem is
10.4× the size of the embedding ecosystem, and it is better maintained.**

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [guillaumemeyer/watermarks-remover](https://github.com/guillaumemeyer/watermarks-remover) | MIT | 28,124 | 3,162 | 2026-11-16 | Single most-starred repo in this whole subject area — 34× VideoSeal. |
| [wiltodelta/remove-ai-watermarks](https://github.com/wiltodelta/remove-ai-watermarks) | Apache-2.0 | 6,482 | 599 | 2026-11-22 | Pushed on measurement day. Named for removing *AI* watermarks specifically. |
| [GargantuaX/gemini-watermark-remover](https://github.com/GargantuaX/gemini-watermark-remover) | MIT | 5,781 | 835 | 2026-11-19 | Targets a specific vendor's marks. |
| [YaoFANGUK/video-subtitle-remover](https://github.com/YaoFANGUK/video-subtitle-remover) | Apache-2.0 | 13,865 | 1,721 | 2026-06-30 | Burned-in subtitle/overlay removal — also strips visible provenance badges. |
| [D-Ogi/WatermarkRemover-AI](https://github.com/D-Ogi/WatermarkRemover-AI) | MIT | 2,150 | 404 | 2026-11-02 | Diffusion-based inpainting removal. |
| [froggeric/gemini-watermark-and-synthid-remover](https://github.com/froggeric/gemini-watermark-and-synthid-remover) | MIT | 132 | 24 | 2026-09-25 | **Names SynthID in the repo title.** Small, but proof that the specific defeat of a named scheme is a published, MIT-licensed project. |

Measured totals: six removers = **42,896 stars**; five embedders = **4,138 stars**. Ratio **10.4×**.
Three of the six removers were pushed inside the last three weeks.

**What to tell a client, precisely:** watermarking is buildable today on MIT code — that part of the
gap is closed and Pattern 8 in `compose/patterns.md` now exists. But never sell a watermark as
tamper-proof. The honest architecture is **dual marking plus detection-side verification**: C2PA
manifest (strippable by re-encode) + VideoSeal/AudioSeal payload (attackable by a better-resourced
open ecosystem) + a verification service *you* run at ingest. Provenance is a *probabilistic chain of
custody*, not a seal, and the measured star counts are the argument for saying so out loud.

**Short-form drama, the APAC category everyone asks about — informed gap, not silence.** Searched
`short-drama`, `micro-drama` and `ai-short-drama`. The category is commercially real, the open code
is not usable:

- `Anil-matcha/Open-AI-Micro-Drama-Generator` — 587★/123f, pushed 2026-08-02, and **no LICENSE file
  at all**. Also a wrapper around *paid closed* APIs (Seedance, Kling, Veo, Sora), so it is neither
  open nor self-hostable.
- `chatfire-AI/drama-skills` — promoted by a directory site as "~4.4k stars, MIT". **The slug does not
  resolve.** Do not re-adopt it.
- `huobao-drama` — promoted as "~18k stars", reported **CC-BY-NC-SA-4.0**. Non-commercial: unusable
  in client work even if the stars are real. Not confirmed at any slug.
- [mediago-dev/mediago-drama](https://github.com/mediago-dev/mediago-drama) — Apache-2.0, **110★/29f**,
  2026-10-21. Re-measured at exactly the 110 the last pass recorded. Still the **only** permissively
  licensed, self-hostable short-drama agent found in two consecutive passes.

## 2026-11-21

Measured this pass, not carried forward. Stars and last-push read from GitHub `search/repositories`
on 2026-11-21; licenses read from the LICENSE file wherever the API said `NOASSERTION`.

| Agent | Repo | License | Stars | Last push | Signal |
|---|---|---|---|---|---|
| rea-video | [JuneYaooo/rea-video](https://github.com/JuneYaooo/rea-video) | Apache-2.0 | 11,476 | 2026-11-21 | Top of the AI-video star-velocity boards this month; pushed the day of measurement. The genuine new entrant. |
| OpenMontage | [OpenMontageInc/OpenMontage](https://github.com/OpenMontageInc/OpenMontage) | AGPL-3.0 | 81,978 | 2026-11-16 | Fastest-growing agentic video production suite — but **AGPL-3.0**, which the coverage calling it "63k stars, MIT-ish" gets wrong. |
| Hyperframes | [heygen-com/hyperframes](https://github.com/heygen-com/hyperframes) | Apache-2.0 | 87,525 | 2026-11-21 | Vendor-backed (HeyGen) and genuinely Apache-2.0. Now the largest permissive agentic-video framework. |
| OpenCreator | [krillinai/OpenCreator](https://github.com/krillinai/OpenCreator) | Apache-2.0 | 14,449 | 2026-11-20 | **Renamed from `krillinai/KrillinAI`** since the last pass. Still shipping weekly. |
| Kinocut | [KyaniteLabs/kinocut](https://github.com/KyaniteLabs/kinocut) | Apache-2.0 | 272 | 2026-11-19 | **Renamed from `KyaniteLabs/mcp-video`.** Guardrailed video-editing MCP server; v2.0.1 exposes 206 tools with loudness/quality gates. Small but the most mature media MCP server found. |
| MuseTalk | [TMElyralab/MuseTalk](https://github.com/TMElyralab/MuseTalk) | MIT | 6,999 | 2026-11-19 | Real-time lip-sync; steady activity, MIT, good localization fit. |
| pyvideotrans | [jianchang512/pyvideotrans](https://github.com/jianchang512/pyvideotrans) | GPL-3.0 | 19,786 | 2026-11-21 | Very active dubbing/translation tool. GPL-3.0 — separate process only. |

**Movements worth recording**

- **Deflation, not growth, is the story.** `hexgrad/kokoro` was logged by three earlier cycles at
  "~35k → 38k stars". It is **10,273** and has not been pushed since **2025-08-06**. The inflated
  number appears to have come from the Hugging Face model page. Likewise `Tencent-Hunyuan/HunyuanVideo`
  was logged at "~22k"; it is **12,815**.
- **The video-generation models are cooling while the agents heat up.** Open-Sora (29,943★) last
  pushed 2026-04-09; Wan2.1 2026-03-05; CogVideo 2025-11-04; AudioCraft 2026-03-03. Every repo pushed
  *this week* is an orchestration layer, not a model. Composition is where the movement is.
- **Nothing in last pass's trending list survived as media tooling.** The ten rows carried below were
  mostly 0-star, non-media utilities (a text randomizer, a JSON formatter) picked up by keyword match.
  All still exist; none became relevant.

## History — 2026-07-02 (preserved verbatim; rows unverified at the time of writing)

> ⚠️ Audited 2026-11-21: these repos do all exist, but most are not media tooling and most had 0–1
> stars. `veyracast` is still 0★ (pushed 2026-09-24); `random.airat.top` 0★; `json.airat.top` 0★ and
> unlicensed; `media_monitor` 1★ and unlicensed; `mediago-drama` has grown 14★ → 110★ and is the one
> row that held up.


> Última actualización: 2026-07-02

| Nombre | Licencia | Descripción | Stars |
|--------|----------|-------------|-------|
| [veyracast](https://github.com/veyralabsgroup/veyracast) | MIT | API-first AI social content agent — generate on-brand posts and comments with Cl | 0 |
| [random.airat.top](https://github.com/Adrielc7958/random.airat.top) | MIT | Generate unique, privacy-first text randomizations fully in-browser with support | 0 |
| [json.airat.top](https://github.com/rodiproactive998/json.airat.top) | ? | Provide local JSON formatting, validation, conversion, and sorting with a static | 0 |
| [mediago-drama](https://github.com/mediago-dev/mediago-drama) | Apache-2.0 | 小说改短剧，从文本到视频的一站式 Agent 工作台。 | 14 |
| [flyweel-agentic-seo-aeo-engine](https://github.com/Yashvaghela2003/flyweel-agentic-seo-aeo-engine) | MIT | Generate SEO-optimized blog posts using an open-source AI engine with multi-mode | 1 |
| [media_monitor](https://github.com/matuteiglesias/media_monitor) | ? | Live news intelligence and publishing pipeline for economic, political, and civi | 1 |
| [devflow-ai](https://github.com/monaty1/devflow-ai) | ? | 🤖 Build and streamline developer workflows with 15 AI-powered, local-first tool | 1 |
| [devflow-ai](https://github.com/haseeb-321/devflow-ai) | MIT | 🚀 Generate SEO-optimized technical articles from GitHub repositories effortless | 0 |
| [trans-epub](https://github.com/fonger900/trans-epub) | MIT | Translate EPUB books from English to Vietnamese using AI translation engines. | 0 |
| [aegitox](https://github.com/aegitox/aegitox) | NOASSERTION | Intercept. Classify. Replace. Dual MiniLM-L6-v2 AI moderation for Discord. Targe | 0 |

---
*Pipeline automático — se actualiza cada hora.*

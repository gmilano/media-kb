---
industry: media
region: Global
updated: 2026-11-21
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

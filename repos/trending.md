---
industry: media
region: Global
updated: 2026-11-22
---

# 📈 Trending Media Repos — append-only log

> Newest section first; history below is never rewritten.
> Distinct from `agents/trending.md`: this file tracks **infrastructure and platform** repos.
> (Until this pass the two files were byte-identical — that defect is fixed here.)

## 2026-11-22

**The headline: this KB's second recorded hard gap — "no open MOS-protocol implementation exists at
all, so newsroom playout integration remains unautomatable off-the-shelf" — is also false.** It
exists, it is MIT, and it has been running daily news at NRK, the BBC and TV 2 Norway since 2018.

The project is **Sofie**, commissioned by NRK (Norwegian public broadcaster) as an open replacement
for Vizrt Mosart and presented at EBU's open-source conference. It is not one repo but a 23-repo
MIT ecosystem, and the org was **renamed `nrkno/*` → `Sofie-Automation/*`** — the exact rename trap
this KB already documents, which is part of why earlier passes missed it.

| Repo | License | Stars | Forks | ★/fork | Last push | Role |
|---|---|---|---|---|---|---|
| [Sofie-Automation/sofie-core](https://github.com/Sofie-Automation/sofie-core) | MIT | 349 | 63 | 5.5 | 2026-11-19 | The automation server itself: rundowns, show styles, live control. MOS Gateway development now lives in here. |
| [Sofie-Automation/Sofie-TV-automation](https://github.com/Sofie-Automation/Sofie-TV-automation) | MIT | 440 | 38 | 11.6 | 2025-12-16 | Umbrella/docs repo — the most-starred and the least useful to build against. Start at `sofie-core`. |
| [Sofie-Automation/sofie-mos-connection](https://github.com/Sofie-Automation/sofie-mos-connection) | MIT | 29 | 18 | **1.6** | 2026-10-07 | **The MOS answer.** Node library speaking **MOS Protocol v2.8.4** to Newsroom Computer Systems (iNEWS, ENPS, Octopus) and MOS devices. 29 stars, 18 forks. |
| [Sofie-Automation/sofie-timeline-state-resolver](https://github.com/Sofie-Automation/sofie-timeline-state-resolver) | MIT | 25 | 25 | **1.0** | 2026-11-12 | The typed device-abstraction layer: declare a timeline, it drives the hardware. **This is the repo that changes the architecture** — see trend 3. |
| [Sofie-Automation/sofie-atem-connection](https://github.com/Sofie-Automation/sofie-atem-connection) | MIT | 158 | 50 | 3.2 | 2026-11-20 | Blackmagic ATEM vision-mixer control. The most reused single device library. |
| [Sofie-Automation/sofie-package-manager](https://github.com/Sofie-Automation/sofie-package-manager) | MIT | 6 | 8 | **0.75** | 2026-11-16 | Media ingest/transfer/transcode orchestration. **More forks than stars.** |
| [Sofie-Automation/sofie-hyperdeck-connection](https://github.com/Sofie-Automation/sofie-hyperdeck-connection) | MIT | 6 | 8 | **0.75** | 2026-07-20 | HyperDeck record/playback control. More forks than stars. |
| [Sofie-Automation/sofie-input-gateway](https://github.com/Sofie-Automation/sofie-input-gateway) | MIT | 0 | 5 | **0.0** | 2026-10-08 | Physical control surfaces (Stream Deck, X-keys, MIDI). **Zero stars, five forks.** |
| [Sofie-Automation/sisyfos-audio-controller](https://github.com/Sofie-Automation/sisyfos-audio-controller) | **MIT** | 45 | 21 | 2.1 | 2026-11-14 | Audio-mixer control. API says `NOASSERTION`; LICENSE (1,297 B) is MIT — copyright **TV 2 Denmark** with NRK contributions, i.e. two national broadcasters co-maintaining it. |
| [Sofie-Automation/sofie-atem-state](https://github.com/Sofie-Automation/sofie-atem-state) | MIT | 12 | 5 | 2.4 | 2026-11-20 | ATEM state diffing. |
| [Sofie-Automation/sofie-casparcg-launcher](https://github.com/Sofie-Automation/sofie-casparcg-launcher) | MIT | 28 | 10 | 2.8 | 2026-08-06 | Supervises CasparCG graphics servers. |
| [Sofie-Automation/sofie-quantel-gateway](https://github.com/Sofie-Automation/sofie-quantel-gateway) | GPL-2.0 | 3 | 3 | 1.0 | 2026-03-20 | Quantel server bridge — **the one copyleft component**; run it as its own process. |
| [nrkno/sofie-mos-gateway](https://github.com/nrkno/sofie-mos-gateway) | MIT | 7 | 4 | 1.8 | 2022-03-03 | **ARCHIVED** — folded into `sofie-core`. Listed so no future pass adopts the dead slug. |

**Why this stack is invisible to every "top AI repo" list, stated as a rule.** Run the obvious query
and you find nothing: measured this pass, `mos protocol broadcast` returns **total=1**, and that one
result is a dead 2★ student project from 2018. Sofie is undiscoverable by capability because its
repos are named after *itself*, not after what they do. **The methodological lesson, which
generalizes to all twelve industries: when a plausible capability query returns nothing, the gap may
be in the vocabulary, not the market — search for the proper noun (the project, the vendor, the
standards body, the broadcaster) before concluding the category is empty.** The previous healthcare
pass learned to *shorten* a zero-result query; this pass adds: also try the *name*.

**And the fork ratios are the cleanest confirmation of the ★/fork law this rotation has produced.**
`sofie-timeline-state-resolver` at 25★/25f, `sofie-package-manager` and `sofie-hyperdeck-connection`
with **more forks than stars**, `sofie-input-gateway` at **0★/5f**. Infrastructure people actually
deploy gets forked and not starred. A repo with 0 stars and 5 forks is not a dead project — it is a
project whose only audience is the handful of broadcast engineers who run it.

### Other infrastructure measured this pass

| Repo | License | Stars | Forks | Last push | Signal |
|---|---|---|---|---|---|
| [pyannote/pyannote-audio](https://github.com/pyannote/pyannote-audio) | MIT | 10,831 | 1,145 | 2026-11-19 | **Missing from this KB until now, and it is load-bearing** — the speaker-diarization toolkit `whisperX` depends on. "Who speaks when" is the step that makes multi-speaker dubbing and subtitle attribution work. MIT and actively maintained. |
| [mltframework/mlt](https://github.com/mltframework/mlt) | **LGPL-2.1** | 1,883 | 407 | 2026-11-22 | The engine under Shotcut and Kdenlive: non-linear editing, filters, rendering. **LGPL, not GPL** — so unlike every other editing engine here it can be *linked* from proprietary code. The most permissive real NLE backend available, and pushed on measurement day. |
| [CasparCG/server](https://github.com/CasparCG/server) | GPL-3.0 | 1,112 | 329 | 2026-11-11 | The broadcast graphics/playout server Sofie drives, from SVT (Swedish public broadcaster). GPL-3.0 → separate process, which is how Sofie uses it anyway. |
| [contentauth/c2patool](https://github.com/contentauth/c2patool) | Apache-2.0 | 174 | 47 | 2026-11-20 | CLI for signing/inspecting C2PA manifests — the fastest way to add provenance to an existing pipeline without writing Rust. |
| [contentauth/c2pa-python](https://github.com/contentauth/c2pa-python) | Apache-2.0 | 110 | 41 | 2026-11-18 | Python binding; the practical entry point for ML pipelines. |
| [c2pa-org/specifications](https://github.com/c2pa-org/specifications) | CC-BY-4.0 | 215 | 35 | 2026-11-16 | The spec itself. Cite this, not a vendor blog, when a client asks what C2PA actually mandates. |
| [ebu/awesome-broadcasting](https://github.com/ebu/awesome-broadcasting) | **CC0-1.0** | 1,803 | 238 | 2026-09-30 | **The source that should have been the KB's starting point.** The European Broadcasting Union's own curated index of open broadcast tooling, public domain. Institutional, not a listicle — this is where Sofie and ffplayout are listed. |
| [libretime/libretime](https://github.com/libretime/libretime) | AGPL-3.0 | 940 | 250 | 2026-11-22 | Radio automation/scheduling (the maintained Airtime fork). Pushed on measurement day. AGPL. |
| [ffplayout/ffplayout](https://github.com/ffplayout/ffplayout) | GPL-3.0 | 607 | 146 | 2026-11-20 | Rust/FFmpeg 24-7 channel playout from playlists — the practical way to run a FAST channel. GPL-3.0. |
| [openbroadcaster/observer](https://github.com/openbroadcaster/observer) | AGPL-3.0 | 187 | 55 | 2026-11-13 | MAM + scheduling + automation web app. The closest thing to an open broadcast MAM, and AGPL. |
| [openbroadcaster/obplayer](https://github.com/openbroadcaster/obplayer) | AGPL-3.0 | 144 | 54 | 2026-09-23 | Its playout client, with CAP/emergency-alerting support — a genuine regulatory feature. |
| [OpenShot/openshot-qt](https://github.com/OpenShot/openshot-qt) | **GPL-3.0** | 6,826 | 856 | 2026-11-22 | Desktop NLE. API says `NOASSERTION`; COPYING (33,310 B) is GPL-3.0. Not embeddable. |
| [facebookresearch/demucs](https://github.com/facebookresearch/demucs) | MIT | 10,423 | 1,685 | 2024-04-24 | **ARCHIVED**, and still the standard for music/dialogue **stem separation** — the step that lets you re-dub a mix without the original M&E stems. Vendor it; nothing maintained has replaced it. |
| [sigsep/open-unmix-pytorch](https://github.com/sigsep/open-unmix-pytorch) | MIT | 1,523 | 206 | 2024-06-17 | The reference/academic stem separator. Dormant but MIT and reproducible. |
| [jaskie/PlayoutAutomation](https://github.com/jaskie/PlayoutAutomation) | GPL-2.0 | 224 | 43 | 2026-04-28 | TVPlay channel-playout automation (.NET). The only other real open playout system found. |
| [olive-editor/olive](https://github.com/olive-editor/olive) | GPL-3.0 | 9,164 | 622 | 2024-12-05 | Promising NLE, **~2 years dormant**. Do not start here. |
| [immstudios/nebula](https://github.com/immstudios/nebula) | GPL-3.0 | 20 | 2 | 2023-04-26 | **ARCHIVED.** Recommended by current search results as an open MAM + broadcast automation system; it is dead at this slug. |
| [JuneYaooo/awesome-ai-media-cn](https://github.com/JuneYaooo/awesome-ai-media-cn) | **none** | 416 | 58 | 2026-11-21 | Trendshift-flagged index of Chinese AI-media tooling — useful *reading* for APAC discovery, but it ships **no license file**, so treat it as a bibliography, never a dependency. |

**Figures that reproduced exactly, confirming the last pass measured rather than inherited.**
`Netflix/photon` 258★ (unchanged), `mediago-drama` 110★ (unchanged), `OpenTimelineIO` 2,105→2,109★,
`KyaniteLabs/kinocut` 272→278★, `c2pa-rs` 452→453★. Every number the previous pass *measured*
reproduced within a day's drift; the numbers earlier cycles *inherited from listicles* were the ones
that were wrong by 3–4×. **Measuring is cheap; inheriting is expensive.**

**License re-reads this pass (API `NOASSERTION` → actual):** `adobe/trustmark` → MIT;
`Sofie-Automation/sisyfos-audio-controller` → MIT; `OpenShot/openshot-qt` → GPL-3.0;
`ebu/awesome-broadcasting` → CC0-1.0; `contentauth/c2pa-rs` → **dual MIT *or* Apache-2.0 confirmed**
(both `LICENSE-MIT`, 1,083 B, and `LICENSE-APACHE`, 11,335 B, present — the previous pass's claim
holds). That is five more cases where GitHub's metadata was a poor witness and the file was decisive.

## 2026-11-21

| Repo | License | Stars | Last push | Signal |
|---|---|---|---|---|
| [contentauth/c2pa-rs](https://github.com/contentauth/c2pa-rs) | MIT OR Apache-2.0 | 452 | 2026-11-21 | Pushed the day of measurement. The reference C2PA implementation, dual-licensed — see `compose/patterns.md`; this is the compliance layer the 2026 labeling laws now require. |
| [Comfy-Org/ComfyUI](https://github.com/Comfy-Org/ComfyUI) | GPL-3.0 | 147,860 | 2026-11-21 | **Org renamed from `comfyanonymous`.** 147,860★ — earlier cycles logged "~75k", so this one genuinely doubled. |
| [yt-dlp/yt-dlp](https://github.com/yt-dlp/yt-dlp) | Unlicense | 209,447 | 2026-11-21 | Still the most-starred media repo anywhere; earlier cycles under-recorded it at ~96k. |
| [huggingface/diffusers](https://github.com/huggingface/diffusers) | Apache-2.0 | 34,961 | 2026-11-21 | Daily pushes; absorbing the new video models as they land. |
| [invoke-ai/InvokeAI](https://github.com/invoke-ai/InvokeAI) | Apache-2.0 | 29,131 | 2026-11-21 | The permissive counterweight to ComfyUI's GPL, still shipping daily. |
| [AcademySoftwareFoundation/openexr](https://github.com/AcademySoftwareFoundation/openexr) | BSD-3-Clause | 1,888 | 2026-11-21 | ASWF cadence is steady — the standards layer is quietly active while models stall. |
| [Breakthrough/PySceneDetect](https://github.com/Breakthrough/PySceneDetect) | BSD-3-Clause | 5,605 | 2026-11-21 | Pushed on measurement day; still the default shot-detection step. |
| [ggml-org/whisper.cpp](https://github.com/ggml-org/whisper.cpp) | MIT | 55,377 | 2026-11-20 | On-prem ASR momentum continues (55,377★, up from the ~52k logged earlier). |
| [owncast/owncast](https://github.com/owncast/owncast) | MIT | 11,683 | 2026-11-21 | The only MIT self-hosted live-streaming platform still under active development. |

**Two listicle recommendations that are 404s.** Recorded so no future pass re-adopts them:

- `MUKE-coder/mediakit` — pitched by current search results as "MediaKit (MIT), self-hosted
  Mux/Cloudinary alternative". `git ls-remote` returns nothing. **The repo does not exist.**
- `google/credentio` — widely reported as "Google open-sourced a C2PA validator (Aug 2026)". There is
  **no `google/credentio` repo**; only third-party accounts (`ghchinoy/credentio-validator-web`, 1★)
  carry the name. The claim is unverifiable at the slug everyone cites.
- `Castopod/castopod` — carried as a vertical by an earlier cycle. **Dead at that slug**; Castopod
  develops on its own GitLab, not GitHub.

**Archived, and previously listed here as live:** `Sanster/IOPaint` (23,286★, archived),
`salesforce/LAVIS` (11,256★, archived).

## History — 2026-07-02 (preserved verbatim; was byte-identical to agents/trending.md)


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

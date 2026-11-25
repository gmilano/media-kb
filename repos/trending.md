---
industry: media
region: Global
updated: 2026-11-25
---

# 📈 Trending Media Repos — append-only log

> Newest section first; history below is never rewritten.
> Distinct from `agents/trending.md`: this file tracks **infrastructure and platform** repos.
> (Until this pass the two files were byte-identical — that defect is fixed here.)

## 2026-11-25 — pass 7: the audience & measurement infrastructure (37 verified repos, 37/37 resolved)

The demand-side substrate: recommenders, media-mix models, identity resolution, privacy-preserving
joins, experimentation, the event/query layer, EPG and podcast measurement, and ACR. New section in
`repos/foundations.md`. Every row verified by `search/repositories` for stars/forks/`pushed_at`/SPDX,
with the licence **file read** wherever the API returned `NOASSERTION`.

### Headline: the first plane where open-source health collapses along a measured gradient inside itself

| Step | What it must observe | Health |
|---|---|---|
| Recommend the next item | your own first-party log | **22,012★ MIT**, pushed this month |
| Model what the media did | your spend + outcomes | **1,616★ / 1,540★ / 1,314★**, all pushed ≤15 days |
| Count the audience as currency | a national panel you cannot own | **a literal zero** (below) |

The scarce thing is **the right to observe**, not the algorithm and not a data licence. Sixth
confirmation of this KB's structural law, and the first with a **price**: ~$110M/year (CIMM, Jan 2026).

### The void, measured rather than asserted

| Query | Results | What is actually there |
|---|---|---|
| `reach frequency curve media` | **1** | An unrelated ML tutorial. The core deliverable of every TV currency has **no open implementation**. |
| `currency measurement TV` | **1** | `api-evangelist/videoamp`, **0★**, no licence — a description of an API surface. |
| `panel weighting survey` | **4** | Top three have **0 stars**. Panel weighting is the statistical method under every TV rating. |
| `identity resolution advertising` | **4** | Only on-topic repo has **0★**, untouched since 2021. |
| `audience measurement` | **91** | Only relevant hits are **Comscore's own SDKs** (16★/15★/6★), licence = a PDF. |
| `data clean room` | **870** | **Zero relevant** — all Android "clean architecture". |
| `media mix modeling` | **247** | **Healthy**: Meridian, Robyn, pymc-marketing, all pushed within 15 days. |

Crueller than pass 5's `music royalty accounting` (14 results, top six summing 0 stars) and pass 4's
`medical necessity` comparison, because here **two separate queries return exactly one result each and
neither is an implementation.**

### Recommenders — absent from this KB until today, and the healthiest permissive layer in it

| Repo | Licence | Stars | Forks | Last push |
|---|---|---|---|---|
| [recommenders-team/recommenders](https://github.com/recommenders-team/recommenders) | MIT | 22,012 | 3,336 | 2026-11-05 |
| [gorse-io/gorse](https://github.com/gorse-io/gorse) | Apache-2.0 | 9,928 | 931 | **2026-11-25** |
| [NicolasHug/Surprise](https://github.com/NicolasHug/Surprise) | BSD-3-Clause | 6,828 | 1,054 | 2026-05-30 |
| [RUCAIBox/RecBole](https://github.com/RUCAIBox/RecBole) | MIT | 4,623 | 755 | 2026-11-23 |
| [benfred/implicit](https://github.com/benfred/implicit) | MIT | 3,842 | 640 | 2026-05-08 |
| [meta-pytorch/torchrec](https://github.com/meta-pytorch/torchrec) | BSD-3-Clause | 2,630 | 751 | **2026-11-25** |
| [NVIDIA-Merlin/Transformers4Rec](https://github.com/NVIDIA-Merlin/Transformers4Rec) | Apache-2.0 | 1,283 | 168 | 2026-08-23 |
| [NVIDIA-Merlin/Merlin](https://github.com/NVIDIA-Merlin/Merlin) | Apache-2.0 | 913 | 132 | 2026-07-22 |
| [massquantity/LibRecommender](https://github.com/massquantity/LibRecommender) | MIT | 490 | 72 | 2025-07-17 |
| [NVIDIA/recsys-examples](https://github.com/NVIDIA/recsys-examples) | BSD-3-Clause (file read) | 369 | 97 | 2026-11-23 |
| [alibaba/RecIS](https://github.com/alibaba/RecIS) | Apache-2.0 | 366 | 26 | 2026-09-23 |
| [keras-team/keras-rs](https://github.com/keras-team/keras-rs) | Apache-2.0 | 173 | 23 | 2026-11-18 |

**Star count is a trap in this tier, twice over.** The two most-starred recommenders on GitHub are both
unusable: [twitter/the-algorithm](https://github.com/twitter/the-algorithm) (**AGPL-3.0**, 74,125★,
13,228 forks, **2025-09-08** — network copyleft *and* 14 months stale; a published artefact, not a
library) and [bytedance/monolith](https://github.com/bytedance/monolith) (**Apache-2.0** per its
`LICENSE`, 12,621 B, though the API says `NOASSERTION`; 9,283★ but **ARCHIVED 2025-10-13** — permissive
and dead). [lyst/lightfm](https://github.com/lyst/lightfm) is Apache-2.0 with 5,119★ and **28 months
stale** while remaining the most-cited hybrid recommender in blog posts.

### Media-mix modelling — the open substitute for a currency, and it is thriving

| Repo | Licence | Stars | Forks | Last push |
|---|---|---|---|---|
| [google/meridian](https://github.com/google/meridian) | Apache-2.0 | 1,616 | 317 | **2026-11-25** |
| [facebookexperimental/Robyn](https://github.com/facebookexperimental/Robyn) | MIT | 1,540 | 442 | 2026-11-10 |
| [pymc-labs/pymc-marketing](https://github.com/pymc-labs/pymc-marketing) | Apache-2.0 | 1,314 | 451 | **2026-11-25** |

**A trend, not an anecdote:** all three are permissive, all three were pushed within 15 days, and two of
them are maintained by Google and Meta — the companies with the most to gain from advertisers *not*
transacting on a panel. The open layer grew precisely where the closed currency could not reach.
**Deprecated and still the top search result:** [google/lightweight_mmm](https://github.com/google/lightweight_mmm)
(Apache-2.0, 1,055★, 237 forks, **ARCHIVED 2025-06-17**) — Meridian replaces it.

### Identity resolution and privacy-preserving joins

| Repo | Licence | Stars | Forks | Last push |
|---|---|---|---|---|
| [dedupeio/dedupe](https://github.com/dedupeio/dedupe) | MIT | 4,531 | 578 | 2025-07-29 |
| [moj-analytical-services/splink](https://github.com/moj-analytical-services/splink) | MIT | 2,604 | 291 | **2026-11-25** |
| [zinggAI/zingg](https://github.com/zinggAI/zingg) | AGPL-3.0 | 1,277 | 177 | 2026-11-03 |
| [google/private-join-and-compute](https://github.com/google/private-join-and-compute) | Apache-2.0 | 860 | 162 | 2026-03-09 |
| [OpenMined/PSI](https://github.com/OpenMined/PSI) | Apache-2.0 | 153 | 40 | 2026-09-22 |

**Both industry-backed open clean rooms are dead:**
[tiktok-privacy-innovation/PrivacyGo-DataCleanRoom](https://github.com/tiktok-privacy-innovation/PrivacyGo-DataCleanRoom)
(Apache-2.0, 37★, **archived 2024-10-31**) and
[facebookresearch/fbpcs](https://github.com/facebookresearch/fbpcs) (MIT, 151★, **archived 2024-11-22**).
The cryptographic primitives survive; the products built on them do not. Same shape this KB found in the
rights plane — **declare/compute is maintained, the product that settles the obligation is not.**

### Experimentation, event collection and query

| Repo | Licence | Stars | Forks | Last push |
|---|---|---|---|---|
| [ClickHouse/ClickHouse](https://github.com/ClickHouse/ClickHouse) | Apache-2.0 | 51,139 | 9,326 | **2026-11-25** |
| [duckdb/duckdb](https://github.com/duckdb/duckdb) | MIT | 43,358 | 4,203 | **2026-11-25** |
| [umami-software/umami](https://github.com/umami-software/umami) | MIT | 40,358 | 8,656 | **2026-11-25** |
| [getredash/redash](https://github.com/getredash/redash) | BSD-2-Clause | 28,902 | 4,647 | **2026-11-25** |
| [cube-js/cube](https://github.com/cube-js/cube) | Apache-2.0 default (dual, file read) | 21,294 | 2,210 | **2026-11-25** |
| [Unleash/unleash](https://github.com/Unleash/unleash) | **AGPL-3.0** (file read — *not* Apache-2.0) | 14,342 | 933 | **2026-11-25** |
| [Flagsmith/flagsmith](https://github.com/Flagsmith/flagsmith) | BSD-3-Clause | 9,879 | 659 | **2026-11-25** |
| [growthbook/growthbook](https://github.com/growthbook/growthbook) | MIT + enterprise carve-out (file read) | 8,659 | 919 | **2026-11-25** |
| [jitsucom/jitsu](https://github.com/jitsucom/jitsu) | MIT | 5,139 | 403 | **2026-11-25** |
| [open-feature/spec](https://github.com/open-feature/spec) | Apache-2.0 | 1,301 | 65 | **2026-11-25** |

**⛔ Excluded after reading, and it is the kind of exclusion that saves an engagement:**
[rudderlabs/rudder-server](https://github.com/rudderlabs/rudder-server) (4,520★, pushed on measurement
day) is described everywhere as open-source CDP infrastructure. Its `LICENSE` is the **Elastic License
2.0** (3,793 B) — **source-available, not open source**, and it forbids offering the software to third
parties as a managed service, which is exactly what an SI does. Use Jitsu (MIT) or Snowplow
(Apache-2.0). **Fourth licence category at the platform tier in this KB**, after copyleft, delayed-open
(FSL, pass 6) and MIT-with-carve-out.

### EPG, catalogue and podcast — and the exception that proves the rule

| Repo | Licence | Stars | Forks | Last push |
|---|---|---|---|---|
| [iptv-org/iptv](https://github.com/iptv-org/iptv) | Unlicense | 144,722 | 8,635 | **2026-11-25** |
| [iptv-org/epg](https://github.com/iptv-org/epg) | Unlicense | 3,560 | 561 | 2026-11-21 |
| [XMLTV/xmltv](https://github.com/XMLTV/xmltv) | GPL-2.0 | 425 | 108 | 2026-10-13 |
| [skymethod/op3](https://github.com/skymethod/op3) | MIT | 144 | 10 | **2026-11-25** |
| [opawg/user-agents-v2](https://github.com/opawg/user-agents-v2) | MIT | 69 | 76 | 2026-11-24 |

**OP3 is the only credible open audience-measurement *service* in this entire plane, and the reason is
structural:** podcast delivery is an open RSS/HTTP download, so the observation point is the publisher's
own redirect — no panel, no gatekeeper who can withhold it. `opawg/user-agents-v2` has **more forks than
stars (ratio 1.1)**, this KB's signature of real shared infrastructure. Where the observation is
structurally available, open measurement appears immediately; where it is not, it does not exist at any
star count.

**Caveat to carry:** OP3 states IAB v2 compliance as a **goal contingent on sponsorship, not
certification** — do not claim it is certified. And **sixth measurement of the `search/repositories`
false negative**: [growlfm/odl](https://github.com/growlfm/odl) returns nothing from the API but has
**11 refs** via `git ls-remote`. Unlike the pass-5 cases this one has **no licence file** at six probed
names while `README.md` returns 200 — so here the absence is real, not a naming convention. Use its
spec, not its code.

### ACR — the open sensor, and the database is the asset

| Repo | Licence | Stars | Forks | Last push |
|---|---|---|---|---|
| [a-gram/audioneex](https://github.com/a-gram/audioneex) | MPL-2.0 | 61 | 10 | 2026-06-17 |
| [SafeNetIoT/ACR](https://github.com/SafeNetIoT/ACR) | AGPL-3.0 | 24 | 0 | 2024-09-09 |

MPL-2.0 is weak per-file copyleft, so Audioneex **can be linked from proprietary code** — it is the
usable one. There is **no open reference fingerprint database** for broadcast or streaming content, and
that, not the matcher, is the asset. In EMEA the method itself was stopped by legal action rather than a
technical limit (`intel/market.md` EMEA).

### Measurement note — the probe needed extending for the fifth time

Pass 5 added `license.txt` (lowercase) and `COPYING.md`. This pass adds: **a licence can be a binary
document referenced by a text stub.** `comScore/ComScore-Android`'s `LICENSE` is 145 bytes of prose
pointing at `LicenseAgreement.pdf` (58,057 B). The probe now treats **any LICENSE under ~300 bytes as
unresolved** and follows what it points at. Also reconfirmed: `git ls-remote` is the only reliable
oracle of existence, and reading the file is the only reliable oracle of licence.

## 2026-11-25 — pass 6: the production & post-production infrastructure (35 verified repos, 35/35 resolved)

New section in `repos/foundations.md`: **the production & post-production plane** — scene
description, colour, timelines, asset resolution, render management, camera metadata. Found by
grepping ~45 candidate terms against the 8 files before any web search (~1 call); `usd`, `materialx`,
`opencue`, `openvdb`, `render farm`, `animation`, `color grading`, `motion capture` and `opentrackio`
all scored **zero files, zero hits** — the second-largest vocabulary hole after `fingerprint`.

**Verification:** existence by `git ls-remote` (**35/35 resolved**); stars / forks / `pushed_at` /
SPDX from `search/repositories`; licences read from the actual file wherever the API said
`NOASSERTION`. Note for future passes: **`gh api repos/{owner}/{repo}` is unavailable in this
session** (repo-scoped token → *"GitHub access to this repository is not enabled"*, 18/18 candidates).
The search endpoint works and `org:<name>` returns a whole foundation's inventory in **one call** —
that is how the table below was built.

### The ASWF core — one org, one call, and the healthiest substrate in this KB

| Repo | Licence | Stars / forks | Ratio | Last push |
|---|---|---|---|---|
| [openvdb](https://github.com/AcademySoftwareFoundation/openvdb) | Apache-2.0 | 3,556★ / 807f | 4.4 | 2026-11-25 |
| [OpenImageIO](https://github.com/AcademySoftwareFoundation/OpenImageIO) | Apache-2.0 | 2,407★ / 727f | 3.3 | 2026-11-25 |
| [OpenShadingLanguage](https://github.com/AcademySoftwareFoundation/OpenShadingLanguage) | BSD-3-Clause | 2,351★ / 422f | 5.6 | 2026-11-25 |
| [MaterialX](https://github.com/AcademySoftwareFoundation/MaterialX) | Apache-2.0 | 2,315★ / 472f | 4.9 | 2026-11-23 |
| [OpenColorIO](https://github.com/AcademySoftwareFoundation/OpenColorIO) | BSD-3-Clause | 2,145★ / 513f | 4.2 | 2026-10-01 |
| [OpenTimelineIO](https://github.com/AcademySoftwareFoundation/OpenTimelineIO) | Apache-2.0 | 2,117★ / 366f | 5.8 | 2026-11-25 |
| [openexr](https://github.com/AcademySoftwareFoundation/openexr) | BSD-3-Clause | 1,890★ / 721f | 2.6 | 2026-11-25 |
| [rez](https://github.com/AcademySoftwareFoundation/rez) | Apache-2.0 | 1,101★ / 369f | 3.0 | 2026-11-25 |
| [OpenCue](https://github.com/AcademySoftwareFoundation/OpenCue) | Apache-2.0 | 1,010★ / 273f | 3.7 | 2026-11-23 |
| [OpenPBR](https://github.com/AcademySoftwareFoundation/OpenPBR) | Apache-2.0 | 845★ / 48f | 17.6 | 2026-11-16 |
| [OpenRV](https://github.com/AcademySoftwareFoundation/OpenRV) | ⚠️ Apache-2.0 except `Notice.txt` components | 797★ / 258f | 3.1 | 2026-11-25 |
| [xstudio](https://github.com/AcademySoftwareFoundation/xstudio) | Apache-2.0 | 782★ / 135f | 5.8 | 2026-11-20 |
| [openfx](https://github.com/AcademySoftwareFoundation/openfx) | BSD-3-Clause | 592★ / 160f | 3.7 | 2026-11-11 |
| [Imath](https://github.com/AcademySoftwareFoundation/Imath) | BSD-3-Clause | 495★ / 166f | 3.0 | 2026-11-13 |
| [OpenColorIO-Config-ACES](https://github.com/AcademySoftwareFoundation/OpenColorIO-Config-ACES) | BSD-3-Clause | 440★ / 53f | 8.3 | 2026-10-27 |
| [openapv](https://github.com/AcademySoftwareFoundation/openapv) | BSD-3-Clause | 273★ / 50f | 5.5 | 2026-11-10 |
| [rawtoaces](https://github.com/AcademySoftwareFoundation/rawtoaces) | Apache-2.0 | 197★ / 66f | 3.0 | 2026-11-24 |
| [openqmc](https://github.com/AcademySoftwareFoundation/openqmc) | Apache-2.0 | 107★ / 8f | 13.4 | 2026-11-23 |

**Twenty-two repos over 100★ in one organisation, of which 20 are Apache-2.0 or BSD-3-Clause — the
two exceptions, `openexr-images` (`NOASSERTION`) and `tac` (CC-BY-4.0), are an image corpus and
governance documents. Every code project in the foundation above 100★ is permissive, and fifteen of
them were pushed within nine days of this pass.** (The 19 rows above are the code projects relevant
to a build; the full org listing is one `search/repositories` call with `org:AcademySoftwareFoundation`.) No other plane in this KB looks like this. The low
star:fork ratios (2.6–5.8 across the core) say the same thing the dates do: these are *integrated*,
not admired.

### Asset resolution — Apache-2.0 end to end, with both connectors orphaned

| Repo | Licence | Stars / forks | Ratio | Last push |
|---|---|---|---|---|
| [OpenAssetIO/OpenAssetIO](https://github.com/OpenAssetIO/OpenAssetIO) | Apache-2.0 | 353★ / 50f | 7.1 | 2026-11-25 |
| [LucaScheller/VFX-UsdAssetResolver](https://github.com/LucaScheller/VFX-UsdAssetResolver) | Apache-2.0 | 141★ / 28f | 5.0 | 2026-05-24 |
| [OpenAssetIO/usdOpenAssetIOResolver](https://github.com/OpenAssetIO/usdOpenAssetIOResolver) | Apache-2.0 | 28★ / 5f | 5.6 | 2026-11-02 |
| [OpenAssetIO/OpenAssetIO-MediaCreation](https://github.com/OpenAssetIO/OpenAssetIO-MediaCreation) | Apache-2.0 | 16★ / 12f | 1.3 | 2026-11-23 |
| [OpenAssetIO/otio-openassetio](https://github.com/OpenAssetIO/otio-openassetio) | Apache-2.0 | 10★ / 2f | 5.0 | **2024-07-26** |
| [OpenAssetIO/OpenAssetIO-Manager-BAL](https://github.com/OpenAssetIO/OpenAssetIO-Manager-BAL) | Apache-2.0 | 9★ / 9f | 1.0 | 2026-11-23 |
| [OpenAssetIO/OpenAssetIO-TraitGen](https://github.com/OpenAssetIO/OpenAssetIO-TraitGen) | Apache-2.0 | 7★ / 7f | 1.0 | 2026-11-23 |
| [OpenAssetIO/OpenAssetIO-ComfyUI](https://github.com/OpenAssetIO/OpenAssetIO-ComfyUI) | Apache-2.0 | 2★ / 2f | 1.0 | **2025-09-30** |
| [OpenAssetIO/openassetio-mcp](https://github.com/OpenAssetIO/openassetio-mcp) | Apache-2.0 | **1★** / 1f | 1.0 | 2026-05-18 |

**The shape of this table is the finding.** The standard (353★) and its trait/manager machinery are
maintained this week. The *connectors* — `otio-openassetio` (dormant since **2024-07**),
`OpenAssetIO-ComfyUI` (dormant since **2025-09**) and `openassetio-mcp` (**1★**) — are the three
repos a client actually needs and all three are orphaned or newborn. A healthy standard with
orphaned connectors is a different, better opportunity than an empty field: the hard part is done.

### Render management — and a trend, not an anecdote

| Repo | Licence | Stars / forks | Last push | Note |
|---|---|---|---|---|
| [AcademySoftwareFoundation/OpenCue](https://github.com/AcademySoftwareFoundation/OpenCue) | **Apache-2.0** | 1,010★ / 273f | 2026-11-23 | Incumbent; the only permissive option at this tier |
| [CGRU/cgru](https://github.com/CGRU/cgru) | LGPL-3.0 | 302★ / 117f | 2026-10-18 | CGRU/AFANASY, independent, long-lived |
| [uberware/sqi](https://github.com/uberware/sqi) | **AGPL-3.0** | 44★ / 1f | **2026-11-25** | The 2026 entrant — and it chose network copyleft |

`render farm manager` returns **32 results in total**: this tier is genuinely tiny. The notable
pattern is that the orchestration layer licenses like this KB's *platform* tier (AGPL/LGPL), and
OpenCue's Apache-2.0 is a **foundation artefact, not a market norm**.

### Virtual production & camera metadata — the standard name is the query

| Repo | Licence | Stars / forks | Ratio | Last push |
|---|---|---|---|---|
| [SMPTE/ris-osvp-metadata-camdkit](https://github.com/SMPTE/ris-osvp-metadata-camdkit) | BSD-3-Clause | 55★ / 17f | 3.2 | 2026-07-31 |
| [mosys/opentrackio-cpp](https://github.com/mosys/opentrackio-cpp) | MIT | 15★ / 12f | **1.25** | 2026-07-23 |
| [unitycoder/Unity.OpenTrackIO](https://github.com/unitycoder/Unity.OpenTrackIO) | MIT | 1★ | — | 2026-05-04 |

`opentrackio` = **8 results, 4 real and permissive**. `virtual production` = **1,291 results and
near-total contamination** (a Go asset embedder at 205★, a dumped W3C report at 176★, a mainframe
emulator at 113★). The fork ratio of 1.25 on `opentrackio-cpp` is the tell that it is being
*integrated* by vendors rather than starred by onlookers.

### Query-shortening rule — the inverse case, and the sharpest example yet

Pass 5 recorded that shortening a query can turn a false zero into a false *abundance*. This pass
produced the cleanest illustration in the KB: **`color grading open source` returns 42 results and
four of the top six are the Bee Movie script** (228★, 98★, 53★, 40★, each opening *"According to all
known laws of aviation…"*). Meme repos outrank every real colour tool in this plane, while the actual
colour infrastructure — `OpenColorIO` (2,145★) and `OpenColorIO-Config-ACES` (440★) — is found only
by its project name. **In this plane, generic English is worthless and the standard's name is
everything.**

### Licence findings carried into `foundations.md`

- **OpenUSD** (7,675★): **Tomorrow Open Source Technology License 1.0** — Apache-2.0 with Section 6
  (Trademarks) changed, `LICENSE.txt` 49,827 B. API says `NOASSERTION`.
- **OpenRV** (797★): Apache-2.0 *except components enumerated in `Notice.txt`*.
- **ynput/ayon-backend + ayon-frontend**: **FSL-1.1-ALv2** (3,744 B) — source-available with delayed
  Apache conversion, while every AYON *client* repo is plain Apache-2.0.
- **cgwire/awesome-cg-vfx-pipeline** (1,286★): **CC-BY-SA-3.0** — a link list. Documents, not code.
- **ynput/OpenPype** (301★, MIT): **archived 2024-09-18**, superseded by AYON. A live URL is still
  not a live project.

## 2026-11-22 — pass 5: the identification & rights infrastructure (30 verified repos, 30/30 resolved)

Fifth pass of the same day. New section in `repos/foundations.md`: **the identification &
rights-reservation plane**. Before this pass, `fingerprint` appeared **nowhere** in this KB — the
largest single vocabulary hole found in any pass, because content identification is the substrate
under royalty attribution, ad verification, takedown, archive dedupe and every AI-training-rights
claim a client will make this year.

**Verification:** existence by `git ls-remote` (**30/30 resolved**); licence by fetching the licence
file and counting bytes; stars/forks/`pushed_at` from one `search/repositories` call each, so the two
can always be cross-checked. No number below is inherited from a listicle.

### The audio-fingerprinting layer — and the gap that defines it

| Repo | Licence | Stars / forks | Ratio | Last push |
|---|---|---|---|---|
| [worldveil/dejavu](https://github.com/worldveil/dejavu) | MIT, 1070 B | 6,789★ / 1,463f | 4.6 | 2024-04-22 |
| [acoustid/chromaprint](https://github.com/acoustid/chromaprint) | ⚠️ LGPL-2.1 as a whole, 1800 B | 1,432★ / 180f | 8.0 | 2026-10-15 |
| [adblockradio/stream-audio-fingerprint](https://github.com/adblockradio/stream-audio-fingerprint) | MPL-2.0, 16722 B | 781★ / 65f | 12.0 | 2021-11-05 |
| [dpwe/audfprint](https://github.com/dpwe/audfprint) | MIT, 1112 B | 622★ / 136f | 4.6 | 2019-09-24 |
| [JorenSix/Olaf](https://github.com/JorenSix/Olaf) | AGPL-3.0, 32386 B | 426★ / 48f | 8.9 | 2026-10-16 |
| [beetbox/pyacoustid](https://github.com/beetbox/pyacoustid) | MIT, 1080 B | 413★ / 71f | 5.8 | 2026-05-19 |
| [JorenSix/Panako](https://github.com/JorenSix/Panako) | AGPL-3.0, 32385 B | 276★ / 53f | 5.2 | 2026-09-17 |

**The gap, stated as a sentence a proposal can use:** the two *actively maintained* audio
fingerprinters are **AGPL-3.0**; the three *permissive* ones were last touched in 2019, 2021 and
2024. **There is no actively maintained permissive audio fingerprinter.** A client wanting one is
choosing between vendoring dead MIT code and accepting network copyleft on a service. Narrow,
measured, and buildable.

### Standards-based codes, catalogue, enforcement, watermarking

| Repo | Licence | Stars / forks | Last push | Layer |
|---|---|---|---|---|
| [beetbox/beets](https://github.com/beetbox/beets) | **MIT**, 1079 B | 15,972★ / 2,207f | 2026-11-22 | Catalogue platform — the MIT exception at the platform tier |
| [metabrainz/picard](https://github.com/metabrainz/picard) | GPL-2.0, 17983 B | 5,398★ / 479f | 2026-11-19 | Tagger / ID→metadata join |
| [metabrainz/musicbrainz-server](https://github.com/metabrainz/musicbrainz-server) | GPL-2.0-or-later, `COPYING.md` | 1,114★ / 347f | 2026-11-19 | Metadata encyclopedia |
| [metabrainz/listenbrainz-server](https://github.com/metabrainz/listenbrainz-server) | GPL-2.0, 18205 B | 1,077★ / 402f | 2026-11-22 | Listening data |
| [awslabs/speke-reference-server](https://github.com/awslabs/speke-reference-server) | Apache-2.0, 11357 B | 123★ / 50f | 2026-09-08 | DRM key exchange |
| [iscc/iscc-core](https://github.com/iscc/iscc-core) | Apache-2.0, 11345 B | 26★ / 6f | 2026-10-17 | **ISO 24138:2024** reference |
| [iscc/iscc-sdk](https://github.com/iscc/iscc-sdk) | Apache-2.0, 11339 B | 24★ / 8f | 2026-10-26 | ISCC, batteries included |
| [iscc/iscc-web](https://github.com/iscc/iscc-web) | Apache-2.0 | 9★ / 4f | 2026-11-09 | ISCC HTTP service |
| [iscc/iscc-lib](https://github.com/iscc/iscc-lib) | Apache-2.0 | 2★ / 1f | 2026-11-22 | ISCC multi-language rewrite, early |
| [akamhy/videohash](https://github.com/akamhy/videohash) | MIT, 1075 B | 388★ / 65f | 2024-07-12 | Perceptual video hashing |
| [resemble-ai/Perth](https://github.com/resemble-ai/Perth) | MIT, 1067 B | 546★ / 51f | 2026-09-02 | **New** — perceptual audio watermarking |
| [swesterfeld/audiowmark](https://github.com/swesterfeld/audiowmark) | GPL-3.0, 35148 B | 604★ / 119f | 2026-09-23 | **New** — broadcast-grade, copyleft |
| [wavmark/wavmark](https://github.com/wavmark/wavmark) | ⚠️ MIT **template, unfilled** | 323★ / 44f | 2024-01-07 | **New** — `Copyright (c) [year] [fullname]` |

**Documents, not code — demoted on sight (T13 again):** [iscc/iscc-codes](https://github.com/iscc/iscc-codes)
(**CC-BY-4.0**, 53★) is the ISCC specification text. Cite it; do not depend on it.

### T8 re-measured, not re-asserted: watermark removal has widened its lead

[wiltodelta/remove-ai-watermarks](https://github.com/wiltodelta/remove-ai-watermarks) — Apache-2.0,
**6,483★ / 600f**, pushed **2026-11-22** — has more stars than every watermarking repo in this KB
*combined* (`audioseal` 804 + `audiowmark` 604 + `Perth` 546 + `wavmark` 323 = 2,277). Measured
today. Any provenance pitch must assume the removal tool is better maintained and more popular than
the marking tool.

### Measurement note — the licence probe used by earlier passes was incomplete

`JorenSix/Panako` returned **404 from `raw.githubusercontent.com` for every path tried, including a
commit-pinned one.** That looked like an unreadable licence. It was not: the file is
**`license.txt`, all lower-case**, and the readme is `README.textile`, not `README.md`. A control
request (`beetbox/beets/master/LICENSE` → 200) proved the channel was healthy, so the 404s were
**naming convention, not absence**. A shallow clone settled it in one call: AGPL-3.0, 32,385 B.

The same omission had already bitten this pass once — `musicbrainz-server` looked unlicensed because
the probe list lacked **`COPYING.md`**.

**Two durable rules, for all twelve industries:**

1. **Probe list must include** `license.txt`, `license`, `COPYING.md`, `Licence.txt` alongside the
   upper-case names. Paths are case-sensitive; older projects favour lower-case.
2. **If `README.md` also 404s, your filenames are wrong — the repo is not empty.** Failing control =
   throttled; *passing* control + 404 = naming convention. Then **shallow-clone and look**: cheap and
   conclusive. A raw-channel 404 is never by itself evidence that a licence is absent.

This supersedes nothing in the channel guidance; it extends it. `git ls-remote` remains the only
reliable existence oracle, and `search/repositories` with `-f q='repo:<slug>'` still returns
stars + forks + `pushed_at` + SPDX in a single call.

### Query-shortening rule confirmed again, and it saved this pass

Four plausible queries returned 0 or 1 and were wrong: `tdm reservation protocol`, `eidr identifier`,
`ai.txt crawler opt-out`, `spawning ai datadiligence`. Shortened to `tdmrep`/`tdm reservation
protocol`, `eidr`, `ai.txt`, `datadiligence` they returned the real repos — including
`ai-robots-txt/ai.robots.txt` (4,265★), which the long query missed entirely. **A plausible query
returning zero is a query that is too long, until proven otherwise.**

But the converse also held, and that is the new half: `eidr` → 160 results and `isan` → 1,942
results, with **zero relevant hits in either**. Shortening a query can turn a false zero into a false
*abundance*. Both require reading the results, not the total.

## 2026-11-22 — pass 4: the conformance & preservation infrastructure (20 verified repos)

Fourth pass of the same day, on a plane that returned **no match in any of the eight files** at
`HEAD` before this pass. Every row below was measured this pass: stars/forks/push date via
`search/repositories`, existence via `git ls-remote`, **license by reading bytes**.

**Conformance & technical QC**

| Repo | License | Stars/forks | Push | Note |
|---|---|---|---|---|
| MediaArea/MediaInfo | BSD-2-Clause | 2075★/203f | 2026-11-19 | De-facto technical-metadata reader. |
| MediaArea/MediaInfoLib | BSD-2-Clause | 806★/229f | 2026-11-22 | The library to link; ratio 3.5 = deployed. |
| MediaArea/RAWcooked | BSD-2-Clause | 50★/13f | 2026-11-22 | RAW → FFV1/Matroska, reversible. |
| bavc/qctools | **GPL-3.0** (in `License.html`; GUI + ffmpeg stats filter additionally BSD) | 389★/44f | 2026-11-15 | GitHub says `NOASSERTION`. |
| MediaArea/MediaConch | **GPLv3+ *or* MPLv2+** (in `SourceCode/License.html`) | 35★/10f | **2021-09-29** | Dual-licensed — MPL route is embeddable. Dormant. PREFORMA Consortium condition on bundled libs. |
| amiaopensource/vrecord | **CC-BY-4.0** | 206★/55f | 2026-11-01 | A *content* license on software — reimplement, do not vendor. |

**Loudness**

| Repo | License | Stars/forks | Push | Note |
|---|---|---|---|---|
| csteinmetz1/pyloudnorm | MIT | 796★/71f | 2026-01-04 | ITU-R BS.1770 meter in Python. |
| jiixyj/libebur128 | MIT | 498★/94f | 2026-11-20 | Canonical EBU R128 implementation; ratio 5.3 = ships inside other products. |
| librosa/librosa | **ISC** | 9106★/1149f | 2026-11-22 | Permissive BSD-equivalent, often misrecorded as MIT. |
| MTG/essentia | **AGPL-3.0** | 3814★/646f | 2026-11-18 | Reaches across a network boundary. |
| bbc/peaks.js | **LGPL-3.0** | 3413★/292f | 2026-10-21 | Routinely misreported as MIT. |

**Preservation & repository**

| Repo | License | Stars/forks | Push | Note |
|---|---|---|---|---|
| fcrepo/fcrepo | **Apache-2.0** | 255★/138f | 2026-11-20 | **The only permissive platform in the tier.** Ratio 1.8. |
| artefactual/archivematica | AGPL-3.0 | 527★/136f | 2026-11-21 | Reference OAIS pipeline. |
| archivesspace/archivesspace | **ECL-2.0** (in `COPYING`, 747 B) | 449★/255f | 2026-11-20 | Apache-shaped, OSI-approved, almost no tool recognizes the id. |
| openpreserve/jhove | **LGPL-2.1+** (in `LICENSE`, 879 B) | 204★/86f | 2026-09-16 | Its own license file misspells "Lesser" as "Lessor". |
| openpreserve/fido | **Apache-2.0** (in `LICENSE.txt`, 615 B) | 160★/49f | 2026-11-18 | PRONOM format identification; GitHub says `NOASSERTION`. |
| Islandora/islandora | **GPL-2.0** (`LICENSE`, 18091 B) | **refs=1659, stars unavailable** | — | `search/repositories` returns nothing; `ls-remote` returns 1659 refs. **Fifth measurement of that false negative.** |
| LibraryOfCongress/bagit-python | **Public Domain** (only in `pyproject.toml`; **no license file**) | 276★/101f | 2026-06-18 | Reference BagIt implementation. |

**AI layer over the archive** (not new to the world; new as a row connecting it to the tier above)

| Repo | License | Stars/forks | Push | Note |
|---|---|---|---|---|
| facebookresearch/faiss | MIT | 41857★/4661f | 2026-11-22 | Collection-scale retrieval. |
| mlfoundations/open_clip | MIT (`LICENSE`, 1228 B) | 14281★/1345f | 2026-11-21 | Shot-level search over unlabelled footage; GitHub says `NOASSERTION`. |

**Demoted — documents, not code** (T13 applied again): `usnationalarchives/digital-preservation`
(Public Domain, 245★, **refs=2**) is NARA's preservation *policy*; `digipres/awesome-digital-preservation`
(CC0-1.0, 151★) is an awesome-list. Both are worth citing and neither is software.

**Channel notes added this pass.** (1) A license may ship as **HTML** — searching the repo for
`filename:LICENSE` is what surfaces `License.html`; plain-name raw probes miss it. (2) A license may
exist **only in packaging metadata**. (3) `search/repositories` false negatives measured again
(Islandora). (4) `MediaArea/MediaInfoOnline` returned **refs=0 — the slug does not exist**; dropped
rather than carried.

## 2026-11-22 — pass 3: the accessibility & conformance infrastructure

Third pass of the same day, on the plane measured at **zero** across all eight files at `HEAD`
(`imsc`, `ttml`, `cea-608`, `cea-708`, `ebu-tt`, `wcag`, `accessib*`, `closed caption` — 0 hits each).
This file records the **infrastructure and standards** half; `agents/trending.md` carries the tools
and the AD finding.

### Verified this pass — standards, rendering, conformance

| Repo | License | Stars | Last push | Layer |
|---|---|---|---|---|
| [Dash-Industry-Forum/dash.js](https://github.com/Dash-Industry-Forum/dash.js) | BSD-3-Clause | — | 2026-11-22 | Delivery / accessibility track rendering. Pushed today. |
| [sandflow/ttconv](https://github.com/sandflow/ttconv) | BSD-2-Clause | 242 | 2026-11-21 | Subtitle format interchange (STL/SRT/TTML/SCC/WebVTT). |
| [ableplayer/ableplayer](https://github.com/ableplayer/ableplayer) | MIT | 837 | 2026-11-20 | Accessible player; AD + sign-language tracks. |
| [sandflow/imscJS](https://github.com/sandflow/imscJS) | BSD-2-Clause | 92 | 2026-11-20 | IMSC → HTML5 rendering. |
| [dequelabs/axe-core](https://github.com/dequelabs/axe-core) | **MPL-2.0** | — | 2026-11-16 | Accessibility conformance engine for the player UI. File-level copyleft. |
| [CCExtractor/ccextractor](https://github.com/CCExtractor/ccextractor) | **GPL-2.0** | 919 | 2026-11-11 | CEA-608/708 caption extraction from transport streams. |
| [w3c/imsc-tests](https://github.com/w3c/imsc-tests) | W3C Test Suite **or** W3C BSD-3 | 18 | 2026-10-22 | IMSC conformance corpus. |
| [sandflow/imscHRM](https://github.com/sandflow/imscHRM) | BSD-2-Clause | 10 | 2024-05-16 | ⚠️ HRM validator — dormant ~920 days. |
| [ebu/ebu-tt-live-toolkit](https://github.com/ebu/ebu-tt-live-toolkit) | BSD-3-Clause | 27 | 2021-12-21 | ⚠️ EBU-TT Live reference toolkit — abandoned ~1,797 days. |

### What the dates say

Ranked by last push, this plane splits cleanly in two. Everything that **moves bytes** — conversion,
rendering, playback, extraction — was pushed within the last 11 days. Everything that **proves
correctness** — `imscHRM`, `ebu-tt-live-toolkit` — stopped years ago. The W3C test corpus (31 days)
is the only conformance artefact still maintained, and it is a test suite, not a validator.

That is the third time this KB has recorded the same shape in a different plane:

| Plane | Edges | Middle |
|---|---|---|
| Ad / monetization (pass 2) | Prebid active, measurement active | SCTE-35 tooling dormant |
| Provenance (pass 1) | c2pa-rs active, watermarking active | verification at ingest unbuilt |
| Accessibility (this pass) | ttconv/imscJS/dash.js active | HRM + EBU-TT Live conformance dead |

The generalization worth carrying into client conversations: **open source reliably builds the
pipeline and reliably abandons the proof.** Wherever a regulator asks for evidence rather than
output, there is a gap — and that is precisely where a services firm is paid.

### Measurement note — the verification oracle changed

`curl -sI` against a github.com repo page is now **useless in this environment**: the egress proxy returns
`403` for every github.com HTML request, real and nonexistent alike, so it cannot distinguish a live
repo from a 404. `api.github.com` is scoped to this session's own repositories and returns
"GitHub access to this repository is not enabled for this session" for everything else.

What works, and what this pass used:

- **Existence:** `git ls-remote` against the repo URL — lists refs for a real repo, fails
  with a credential prompt for a nonexistent one. Confirms the method already recorded in `agents/top.md`.
- **Licence:** `git clone --depth 1 --filter=blob:none --sparse` then
  `git sparse-checkout set LICENSE` and read the file. Catches what the GitHub sidebar hides —
  this is how `sign/translate`'s commercial tier and Subtitle Edit's real MIT licence were found.
- **Last push:** blobless shallow clone + `git log -1 --format=%ad`. Cheap and exact.
- **Stars:** WebFetch of the repo page (the only channel that still reports them here).

## 2026-11-22 — pass 2: the monetization plane (16 verified repos, a new section in `foundations.md`)

Second pass of the same day, aimed at the plane this KB had never covered. Measured before starting:
`prebid` 0 hits across all eight files, `scte` 0, `ssai` 0, `openrtb` 0, `ad server` 0 — while
`intel/market.md` already carried $9.1B of AI video advertising and named advertising as the primary
driver of LATAM media growth. The KB quantified the market and had no tooling for it.

**Headline: the plane is permissive and active at the auction and measurement ends, and dormant in
the middle.** Full tables in `repos/foundations.md` → *The monetization plane*; the new builds are
`compose/patterns.md` Patterns 9 and 10.

| Repo | License | Stars | Forks | Last push | Signal |
|---|---|---|---|---|---|
| [prebid/Prebid.js](https://github.com/prebid/Prebid.js) | Apache-2.0 | 1,619 | 2,437 | 2026-11-22 | **More forks than stars (0.66).** Pushed the day of measurement. The canonical header-bidding library. |
| [prebid/prebid-server](https://github.com/prebid/prebid-server) | Apache-2.0 | 595 | 983 | 2026-11-22 | Also fork-heavy (0.61). Server-side auction — the piece that makes SSAI possible without a vendor. |
| [prebid/prebid-server-java](https://github.com/prebid/prebid-server-java) | Apache-2.0 | 110 | 264 | 2026-11-20 | 0.42 ★/fork. The JVM option for broadcaster stacks. |
| [Comcast/scte35-js](https://github.com/Comcast/scte35-js) | Apache-2.0 | 51 | 23 | 2026-05-21 | **The only maintained SCTE-35 parser.** Start here. |
| [futzu/threefive](https://github.com/futzu/threefive) | MIT | 164 | 30 | 2024-11-27 | The one every tutorial recommends — **dormant two years.** LICENSE is a real MIT grant but the copyright line still says "The Python Packaging Authority". |
| [futzu/x9k3](https://github.com/futzu/x9k3) | MIT *declared only* | — | — | 2024-07-10 | **No LICENSE file**; MIT lives in a `setup.py` classifier. Absent from GitHub's search index — `git ls-remote` is the only proof it exists. |
| [Eyevinn/channel-engine](https://github.com/Eyevinn/channel-engine) | Apache-2.0 | 134 | 34 | 2026-11-06 | FAST linear-channel assembly with ad-break signalling. **EMEA-origin (Sweden).** |
| [Eyevinn/hls-vodtolive](https://github.com/Eyevinn/hls-vodtolive) | MIT *(package.json only)* | 46 | 12 | 2026-10-26 | No LICENSE file; API reports `NONE`. |
| [shaka-project/shaka-player](https://github.com/shaka-project/shaka-player) | Apache-2.0 | 8,285 | 1,629 | 2026-11-22 | Already in this KB as a player; logged here for its DRM-and-ads path. |
| [openplayerjs/openplayerjs](https://github.com/openplayerjs/openplayerjs) | MIT | 650 | 92 | 2026-11-16 | The only player whose ads plugin surfaces **SSAI breaks as SCTE-35 TextTrack cues** — lets a client verify a stitched break. |
| [videojs/videojs-contrib-ads](https://github.com/videojs/videojs-contrib-ads) | Apache-2.0 *(API: `NOASSERTION`)* | 396 | 252 | 2024-05-17 | **Dormant since mid-2024**, and fork-heavy — current work lives in the forks. |
| [orestbida/cookieconsent](https://github.com/orestbida/cookieconsent) | MIT | 5,779 | 505 | 2026-11-22 | The practical MIT consent-banner start for GDPR/LGPD. |
| [apache/superset](https://github.com/apache/superset) | Apache-2.0 | 75,621 | 18,632 | 2026-11-22 | Ad-sales reporting surface. |
| [apache/druid](https://github.com/apache/druid) | Apache-2.0 | 14,099 | 3,821 | 2026-11-21 | Real-time OLAP for impression/bid events. |
| [apache/pinot](https://github.com/apache/pinot) | Apache-2.0 | 6,178 | 1,536 | 2026-11-22 | Druid's genuine alternative — pick one, not both. |
| [snowplow/snowplow](https://github.com/snowplow/snowplow) | Apache-2.0 | 7,051 | 1,170 | 2026-10-19 | Own-your-own first-party event collection. |

**Specs, not code — logged so a later pass does not mistake them for dependencies.** The three IAB
Tech Lab repos report `NONE` to GitHub's licence detector and carry **CC BY 3.0** in their READMEs:
[openrtb](https://github.com/InteractiveAdvertisingBureau/openrtb) (530★, 2026-11-11),
[AdCOM](https://github.com/InteractiveAdvertisingBureau/AdCOM) (142★, 2026-10-29),
[GDPR-Transparency-and-Consent-Framework](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework)
(954★, 2026-08-07).

**Platform-layer repos went to `verticals/solutions.md`, not here:** `revive-adserver` (GPL-2.0,
1,522★, the only maintained open ad server, display-only), `matomo` (GPL-3.0), `plausible` (AGPL-3.0),
`posthog` (MIT **with a proprietary `ee/` carve-out**). The plane reproduces this KB's existing
licence law — permissive at the primitives, copyleft at the platforms — which is the strongest
independent confirmation that rule has had.

**Rejected after verification, recorded so nobody re-guesses them:** `Eyevinn/vod2live`,
`Eyevinn/node-vast-parser`, `futzu/threefive3` and
`InteractiveAdvertisingBureau/iabtechlab-ads.cert` were all plausible slugs that **`git ls-remote`
reports dead.** Also excluded: `countly/countly-server`, which presents as open source but ships the
**"Countly Lite License"** — a vendor licence, not an OSI one.

**Method note for the fleet.** `curl -sI github.com/<slug>` returns 403 for everything through this
proxy, so the brief's URL check carries no information here — this is the fifth consecutive pass to
measure that. Two channels that *do* work: `git ls-remote` for existence, and
`raw.githubusercontent.com/<slug>/HEAD/LICENSE` for licence text. New this pass:
`git init && git fetch --depth 1 --filter=blob:none <url> HEAD && git log -1 --format=%cd FETCH_HEAD`
gives a **real last-push date without the API**, which is how `x9k3` was dated despite being missing
from the search index. `gh api -X GET search/repositories` remains the only source of star/fork
counts, and it cross-confirmed every licence and date measured independently above.

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

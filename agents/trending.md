---
industry: media
region: Global
updated: 2026-11-26
---

# 📈 Trending Media AI Agents — append-only log

> Newest section first. **Nothing below is ever rewritten** — that history is the only way to see
> which projects actually sustained momentum and which spiked and died.

## 2026-11-26 — pass 9: the trust & safety plane (the licence moved into the weights)

Scope: hash matching → classification → rules → review queue → enforcement → statutory report.
**62 repos verified, 62/62 resolve by `git ls-remote`.** A plane that did not exist in this KB
before today.

### How the gap was found — the vocabulary probe, and it is now the cheapest tool in this workflow

The remote already held a pass from **this same day** (`799f1f4`, the live & delivery plane), so
rewriting or re-verifying would have added nothing. Per the pass-8 corollary, the right move was to
look for the missing vocabulary. One `grep` of ~50 candidate terms against the eight files, before a
single web search:

| Term | Occurrences across all 8 files, before this pass |
|---|---|
| `trust and safety` | **0** |
| `CSAM`, `PhotoDNA` | **0** |
| `age verification`, `age assurance` | **0** |
| `perceptual hash`, `hash matching` | **0** |
| `DSA`, `Online Safety` | **0** |
| `brand safety`, `content classification`, `parental`, `nudity` | **0** |
| `moderation` | 4 — and **all four** were regulatory prose or one 0-star Discord bot |

Three passes of this KB had been describing minor-protection, illegal-content and transparency
obligations in `intel/market.md` without naming **one tool that discharges any of them**. Cost of
finding that: one tool call.

### The headline: the ninth consecutive near-zero agent layer, and the thinnest one yet

The entire agent layer of this plane is
[roostorg/pigeon](https://github.com/roostorg/pigeon) — "prototyping open-weight safety models as
Coop signals and Osprey rule functions" — at **2★, no licence file, pushed 2026-11-21**. The
substrate beneath it is Apache-2.0, operator-donated and pushed this week. The bridge from "a model
has an opinion" to "an enforcement action happens" is a two-star prototype.

### ⛔ The finding of this pass, and the first genuine refinement of the structural law since pass 6

Every earlier pass located the restrictive instrument in a **content** licence (CPT, MedDRA,
ISRC/ISWC, Nielsen panels) or a **code** licence (AGPL at the platform, GPL at the checker). **This
plane is the first where the code is uniformly permissive and the restriction sits on the model
weights — in proportion to how good the model is.**

One company, one toolkit, one month, two licences:

| Artifact | Licence | ★ | Layer | Usable commercially |
|---|---|---|---|---|
| [Roblox/Sentinel](https://github.com/Roblox/Sentinel) | **Apache-2.0** | 120★ | the plumbing | **yes** |
| [Roblox/RobloxGuard-1.0](https://github.com/Roblox/RobloxGuard-1.0) | **RAIL Research-Only** (17,642 B) | 68★ | the judgment | **no** |
| [Roblox/voice-safety-classifier](https://github.com/Roblox/voice-safety-classifier) | **CC-BY-SA-3.0** (22,240 B) — a content licence, with share-alike, on model weights | 105★ | the judgment | only under share-alike |

Confirmed across the field: Llama Guard ([meta-llama/PurpleLlama](https://github.com/meta-llama/PurpleLlama),
4,495★) is **Llama 3.2 Community** — acceptable-use terms plus an MAU threshold, not OSI-approved;
and the leading deepfake benchmark ([SCLBD/DeepfakeBench](https://github.com/SCLBD/DeepfakeBench),
1,145★) is **CC-BY-NC-4.0**, verified in a 43,107 B licence file that defines NonCommercial as *"not
primarily intended for or directed towards commercial advantage"*. A client engagement is commercial
advantage.

**Falsifiable prediction, recorded for a later pass:** as open safety models improve, the share of
them under research-only / non-commercial / community licences will **rise, not fall**, because the
training data is the moat and the weights are the only place to defend it. If a SOTA safety model
ships Apache-2.0 on the weights in 2027, this is wrong.

### ⛔ An eighth way a licence hides — and the first that is the *inverse* of hiding

[the-draupnir-project/Draupnir](https://github.com/the-draupnir-project/Draupnir) (253★, pushed the
day of this pass) reports **no licence** via the API; eleven filename probes on `main` and `master`
found only a `NOTICE`. It is in fact **Apache-2.0**, declared through **REUSE** — `REUSE.toml` with
per-file `SPDX-License-Identifier` annotations, a `LICENSES/` directory holding `Apache-2.0.txt`,
`MIT.txt`, `0BSD.txt`, `AFL-3.0.txt`, `CC-BY-SA-4.0.txt`, `CC0-1.0.txt`, and `"license":
"Apache-2.0"` in `package.json`.

The project is **more** compliant than the API can read: GitHub looks for one root file, REUSE
deliberately replaces it with per-file annotation. Maximum compliance reads as zero compliance.

Second instance the same pass, bigger repo: **[NVIDIA-NeMo/Guardrails](https://github.com/NVIDIA-NeMo/Guardrails)**
(7,581★) reports `NOASSERTION` while its `LICENSE.md` contains the literal line
`SPDX-License-Identifier: Apache-2.0`. Two of the largest repos in the plane, mislabelled in the same
direction.

### ⚙️ Method: the `repo:` 422 is confirmed as a rename detector — three hits in one pass

| Slug as the docs still write it | `ls-remote` | `repo:` search | Canonical today | ★ |
|---|---|---|---|---|
| `facebook/ThreatExchange` | EXISTS | **422** | [meta/ThreatExchange](https://github.com/meta/ThreatExchange) | 1,417★ |
| `NVIDIA/NeMo-Guardrails` | EXISTS | **422** | [NVIDIA-NeMo/Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) | 7,581★ |
| `microsoft/presidio` | EXISTS | **422** | [data-privacy-stack/presidio](https://github.com/data-privacy-stack/presidio) | 12,065★ |

Control case proving it is rename and not case: `jigsaw-code/altitude` resolved fine to
`Jigsaw-Code/altitude`. All three old paths still redirect in a browser, so humans never notice and
secondary sources keep citing dead slugs.

### The law that *broke* this pass, and the better law that replaces it

`verticals/solutions.md` has said since pass 2 that the **platform tier is copyleft**. In this plane
every platform-tier artifact is permissive: Osprey (Apache-2.0, Discord), Coop (Apache-2.0, ROOST),
conversationai-moderator (Apache-2.0, Google Jigsaw), Altitude (Apache-2.0, Jigsaw),
content-review-filters (Apache-2.0, Meta), Ozone (dual MIT/Apache-2.0, Bluesky).

The replacement predicts better: **the publisher sets the licence, not the layer.** An *operator*
donating infrastructure it runs itself wants adoption and picks permissive. A *vendor* or a *public
body* picks copyleft — and sure enough the one GPL artifact here is the European Commission's own
[digital-services-act/transparency-database](https://github.com/digital-services-act/transparency-database)
(GPL-2.0, 55★), and the fediverse's non-operator tooling is AGPL
([fedimod/fires](https://github.com/fedimod/fires)) and GPL-2.0.

### ⚠️ Contamination — two of the worst false-friend queries measured in this KB

- **`age assurance` → 478 results, ZERO relevant.** All quality *assurance*, *agent* frameworks, or
  French insurance (`gestion-assurance`). The actual estate — nine repos, 309★ on the flagship — is
  reachable **only** through the org name `eu-digital-identity-wallet`. A pass that trusted the
  obvious query would have reported "no open age-verification tooling" while a regulator-published
  Android app sat there.
- **`csam` → 722 results, ONE relevant.** Top hits: a Bioconductor genomics summer school (`CSAMA`,
  92★) and Azure B2C samples (136★). **The acronym is not the vocabulary** — the working tools are
  under "hash matching".

This is the second half of the pass-8 query rule, confirmed again: shortening a query can turn a
false zero into a **false abundance**. Read the results, never the total.

### Informed gaps from this pass

- **No open agent files a statutory report.** US law (18 U.S.C. §2258A) mandates NCMEC CyberTipline
  reporting; the only open client, [ello/ncmec_reporting](https://github.com/ello/ncmec_reporting),
  is **7★, no licence file, dead since 2022-03-29**.
- **The hash lists cannot be obtained at all.** NCMEC / IWF / GIFCT distribute under membership and
  vetting, not licence; PhotoDNA is a gated service. [c4osl/rocketchatcsam](https://github.com/c4osl/rocketchatcsam)
  (MIT, 13★) is an open client to a closed service — the content law, ninth confirmation.
- **No open brand-safety classifier.** GARM is a taxonomy document, the IAB floor is a PDF.
- **No open deepfake detector trained on 2026-era generators.** The three that exist are 2020–2025
  and the usable ones are non-commercial or stale.
- **Channel gap:** `ageverification.dev` **does not resolve from this session** (outside allowed
  network domains), so the blueprint's version, conformance programme and the reported
  **31 December 2026** rollout deadline are **unverified here**. Treat as reported, not confirmed.

## 2026-11-26 — pass 8: the live & delivery plane (the strongest substrate, the emptiest agent layer)

Scope: contribution → transcode → package/encrypt → origin → edge → player. 45 repos verified,
45/45 resolved by `git ls-remote`. **9 of 45 needed a LICENSE-file read** — the worst API-accuracy
ratio of any plane in this KB.

### The eighth consecutive confirmation of the structural law, and the most extreme instance

The substrate here is the healthiest this KB has measured in any plane — `ossrs/srs` 29,457★ MIT,
`bluenviron/mediamtx` 20,772★ MIT, `pion/webrtc` 16,926★ MIT, `FFmpeg` 68,197★, all pushed within
24 hours of measurement. The delivery-operations agent layer above it is a **measured zero**.

Five stars-sorted `search/repositories` queries were run. `streaming agent llm video ops` returned
**zero results**. The rest returned general video-*editing* agents. The only genuine real-time agent
found at any star count is `yondonfu/ai-rtc-agent` — **26★, MIT, last pushed 2024-11-04**.

Nothing open source watches an encoder ladder, reacts to a QoE collapse, re-packs a failing
rendition, or drives an origin. That is the gap, and it sits on top of the best substrate in M&E.

### The four real agents in or adjacent to this plane

| Repo | Licence | Stars | Last push |
|---|---|---|---|
| https://github.com/OpenMontageInc/OpenMontage | **AGPL-3.0** | 83,342 | 2026-11-16 |
| https://github.com/hypit-ai/hypit | modified Apache-2.0 (source-available) | 31,513 | 2026-11-25 |
| https://github.com/Alisa0808/vox-director | MIT | 3,187 | 2026-10-05 |
| https://github.com/yondonfu/ai-rtc-agent | MIT | 26 | 2024-11-04 (dormant) |

### ⛔ Licence finding: a directory reported an 83,342★ AGPL agent as "32.3K stars, MIT"

An AI-tooling aggregator promoted OpenMontage as **"32.3K stars, MIT License"**. Verified:
**83,342 stars and AGPL-3.0.** Wrong on both counts, and wrong in the direction that always recurs —
the repo looked *more* usable than it is. Third time in this KB that a directory has shifted a
licence toward permissive. MIT and AGPL-3.0 are the two ends of the client-risk axis; this is not a
rounding error.

`hypit-ai/hypit` (31,513★) is `NOASSERTION` because it is a *modified* Apache-2.0. The modification,
read in full, is favourable to a consultancy and worth knowing exactly: **permitted** — own
infrastructure, own commercial work, and explicitly "work performed for your clients", plus
single-tenant deployments; **requires a paid licence** — operating a multi-tenant environment (two or
more outside parties with separate workspaces, fee or no fee) and commercial redistribution or
bundling. Attribution must stay visible in the CLI and in generated run reports. Output is yours.
Net: usable in Globant client delivery, **not** usable as the engine of a Globant-hosted SaaS.

### ⚙️ Method correction — a known oracle "flaw" was actually a rename detector

Earlier cycles recorded that `search/repositories` "returns false 422s on live repos" and left it as
flakiness. **Both 422s this pass had one cause: the repo was renamed.** The old path still resolves
over git (redirect); search only indexes the canonical name.

| Path still cited everywhere | ls-remote | search | Canonical today |
|---|---|---|---|
| `AirenSoft/OvenMediaEngine` | OK | 422 | **`OvenMediaLabs/OvenMediaEngine`** (AGPL-3.0, 3,309★) |
| `kixelated/moq-rs` | OK | 422 | **`moq-dev/moq`** (Apache-2.0, 1,642★, pushed 2026-11-26) |

New rule: **ls-remote OK + search 422 = rename.** Search by name, find the new owner, write that one.

### Informed gaps from this pass

- No open-source delivery-operations agent, at any star count, under five query shapes.
- No agent anywhere near the DRM step — structural, not neglect (see `repos/foundations.md`, Gate 2).
- No MPEG-H Audio **encoder** exists; `Fraunhofer-IIS/mpeghdec` is a decoder, and Brazil's DTV+
  mandates MPEG-H in every receiver.
- `libatsc3` has **no canonical repo** — `libatsc3/libatsc3` and `Sony/libatsc3` both fail
  `ls-remote`; only stale MIT forks (13★/2019, 12★/2023) exist for the US transition standard.

## 2026-11-25 — pass 7: the audience & measurement plane (the agent layer runs *against* the openness)

Seventh plane, found by grepping ~95 candidate terms against all eight files before any web search.
`panel`, `Nielsen`, `ratings`, `clean room`, `identity resolution`, `collaborative filtering`, `EPG`,
`podcast`, `A/B` and `recommender` all scored **zero files**. Pass 2 had covered *ad* measurement — the
supply side; this is the **demand** side: who is watching, what to show them next, and how reach is
counted and sold.

### The gradient — and it is the first one that contradicts what openness would predict

| Analytics substrate | Agent bridge | Licence | Stars | Forks | Last push |
|---|---|---|---|---|---|
| Google Analytics 4 — **proprietary, hosted** | [googleanalytics/google-analytics-mcp](https://github.com/googleanalytics/google-analytics-mcp) | Apache-2.0 | **3,866** | 802 | 2026-11-24 |
| PostHog — **open, 41,121★** | [PostHog/mcp](https://github.com/PostHog/mcp) | MIT | 152 | 27 | 2026-01-19 (**archived**) |
| Matomo — **open, 22,056★** | [FGRibreau/mcp-matomo](https://github.com/FGRibreau/mcp-matomo) | MIT | 12 | 2 | 2026-07-27 |
| Mixed / generic | [embeddedlayers/mcp-analytics](https://github.com/embeddedlayers/mcp-analytics) | MIT | 9 | 1 | 2026-10-26 |
| Matomo — **open, 22,056★** | [kitconcept/matomo-mcp](https://github.com/kitconcept/matomo-mcp) | MIT | 1 | 0 | 2025-12-15 |

~63,000 stars of **open** analytics software are served by **22 stars** of agent bridge, one archived.
The **closed** hosted platform has 3,866 stars and 802 forks.

### The structural law, seventh plane — second confirmation of pass 6's refinement, from the hard side

Pass 6 refined this KB's law: the open agent layer tracks **practitioner population**, not regulatory
obligation (passes 3–5) and not substrate health. Pass 6 could not separate population from openness,
because Blender is both the most-installed *and* open. **This plane separates them, and they point in
opposite directions.** GA4's population is vastly larger than Matomo's, GA4 is closed, and GA4 has
~175× the agent adoption. Population wins; **licence and openness do not enter into it.**

Practical form: *an agent bridge is written by whoever has the most users to serve.* Where a client runs
the popular closed platform, adopt the bridge. Where they self-host the open one, **the bridge is a
build** — small, well-specified, and genuinely unoccupied.

### The recommender layer has no agent bridge at all, and for a new reason

`recommender MCP` / `personalization MCP` surface nothing with adoption. Closest artefact:
[JoshuaOliphant/vault-recommender](https://github.com/JoshuaOliphant/vault-recommender) — **2 stars, no
LICENSE file, 2026-11-16**, a personal Obsidian note recommender. Do not cite it.

Yet the libraries *below* it are the healthiest permissive layer in this KB (`recommenders-team/recommenders`
MIT **22,012★** pushed 2026-11-05; `gorse-io/gorse` Apache-2.0 **9,928★** pushed on measurement day).
Sixth plane with a strong substrate and no agent layer — but the reason is new and much more tractable
than passes 3–5: not regulatory risk, not a closed content licence, simply that **a recommender is
called by a service, not by a person.** Nobody has needed to talk to one yet.

### ⛔ The licence finding of this pass: the licence is a PDF

The only code published under an audience-measurement banner by an actual currency vendor is Comscore's
SDK set. Its `LICENSE` is **145 bytes of prose pointing at `LicenseAgreement.pdf`** (58,057 B, verified
present and readable). GitHub reports `NOASSERTION` on all three repos; no SPDX field, SBOM scan or
text-based probe — **including this KB's own, already extended twice in pass 5** — can read it.

**Fifth distinct way a licence hides**, after a non-standard filename (pass 5), a licence owned by the
compile (Chromaprint, pass 5), an HTML file / packaging classifier (pass 4) and a modified Apache
(OpenUSD, pass 6).

And the content is the real finding: read, the PDF is **not a software licence** but a **data-collection
agreement** granting Comscore rights to viewing data "for inclusion in syndicated and/or custom products
… as well as use in its work with certain industry associations and market currency initiatives or joint
industry committees." The code is public; what you accept is that **your audience feeds someone else's
currency** — the exact inverse of pass 5's rights-reservation plane, whose whole purpose was
machine-readable terms. All three repos were **pushed on measurement day**, so this is live code.

**New CI rule, and it generalises past media:** a `LICENSE` under ~300 bytes is a *pointer*, not a
licence. Treat it as unresolved and open what it points at, including binary documents.

### ⛔ Licence correction that contradicts the published comparisons: Unleash is AGPL-3.0

Third-party roundups, one dated 2026, state Unleash's open-source core is **Apache-2.0**. It is
**AGPL-3.0** — `LICENSE` read on both `main` and `master`, 34,523 B, GNU Affero v3, and the API agrees.
For a client embedding flag evaluation in a streaming service that is the difference between a
permissive dependency and network copyleft. Use **Flagsmith (BSD-3-Clause, 9,879★)** or GrowthBook's
MIT core.

### Contamination — the worst false-friend query measured in any industry in this KB

- **`data clean room` = 870 results, ZERO relevant.** All Android **"clean architecture"** repos and a
  timetable app with a "clean room overview": `CoinTrend/CoinTrend` 274★, `ibrajix/NewsFly` 124★,
  `ahmedmolawale/Star-Wars-Characters` 108★. Three plausible-looking rows were available and every one
  would have been a mobile app. Worse than pass 5's `isan` (1,942 results, zero relevant).
- **`audience measurement` = 91 results**, top by stars is an ML *tutorial* (304★, no licence, 2024).
- **`identity resolution advertising` = 4 results**, only on-topic one has **0 stars**, stale since 2021.
- **`reach frequency curve media` = 1 result** and it is the same ML tutorial.
- **`panel weighting survey` = 4 results; the top three have 0 stars.**
- **`currency measurement TV` = 1 result, 0 stars** — an API-surface description, not an implementation.

Pass 5's two-sided rule confirmed again: **read the results, never the total.** 870 is not abundance.

### Informed gaps from this pass

- **No open-source panel measurement exists, and it is now a priced fact, not an impression:** the CIMM
  (Jan 2026) floor is **~$110M/year of operating cost** — see `intel/market.md` North America.
- **Three hosts do not resolve from this session** (outside allowed network domains): `videoweek.com`,
  `www.barb.co.uk`, `www.fifty5blue.com`. The Barb/YouTube ACR dispute and the Kantar Media →
  Fifty5Blue rebrand are therefore recorded **from trade-press summaries, not primary sources**.
- **Brazil's PL 2338/2023 status could not be settled**: sources disagree on whether it is law. Recorded
  as contested, not asserted.
- **No figure found for how many media companies self-host a recommender** versus buying one.

## 2026-11-25 — pass 6: the production & virtual-production plane (the first plane whose agent layer is *misallocated*, not missing)

Three days after pass 5, and the first pass in six to find an agent layer that is not a rounding
error. The plane: *how a shot is built, versioned, reviewed and rendered.* The gap was found the same
way as last pass — grep ~45 candidate terms against the 8 files before touching the web (~1 call).
`usd`, `materialx`, `opencue`, `openvdb`, `virtual production`, `render farm`, `animation`,
`color grading`, `motion capture` and `opentrackio` scored **zero files, zero hits**.

### The gradient — five orders of magnitude, ordered by who installs it

| Layer the bridge targets | Best open bridge | Licence | Stars | Last push |
|---|---|---|---|---|
| Blender — free DCC, mass individual base | [ahujasid/mcp-for-blender](https://github.com/ahujasid/mcp-for-blender) | MIT | **35,788★** | 2026-11-18 |
| Houdini — paid, studio | [healkeiser/fxhoudinimcp](https://github.com/healkeiser/fxhoudinimcp) | MIT | 437★ | 2026-11-20 |
| Maya — paid, studio | [PatrickPalmer/MayaMCP](https://github.com/PatrickPalmer/MayaMCP) | MIT | 124★ | 2025-05-12 |
| OpenUSD — studio interchange | [dcc-mcp/dcc-mcp-openusd](https://github.com/dcc-mcp/dcc-mcp-openusd) | MIT | **2★** | 2026-11-24 |
| OpenAssetIO — studio asset resolution | [OpenAssetIO/openassetio-mcp](https://github.com/OpenAssetIO/openassetio-mcp) | Apache-2.0 | **1★** | 2026-05-18 |

**35,788 → 437 → 124 → 2 → 1.** Not ordered by substrate health, obligation or market size — ordered
by how many individuals can install it on a laptop tonight.

### The structural law, sixth plane, and this is the first genuine refinement since pass 3

Passes 2–5 produced the same result four times: high obligation, absent agent layer. That could still
have been a story about regulation. This plane kills that reading, because the substrate here is the
**healthiest in the entire KB** — **22 ASWF repos over 100★, of which 20 are Apache-2.0 or BSD-3**
(the only two exceptions are an image corpus and the governance repo: data, not code), **15 of them
pushed within 9 days of this pass**, under a Linux Foundation umbrella with studio funding — and
the studio-facing agent layer is still **1 star**.

So the law is not "regulated planes lack agents". It is:

> **The open agent layer tracks the size of the individual practitioner population — not the
> regulatory obligation, and not the substrate's health.**

Where the user is a person, the bridge is enormous. Where the user is a pipeline, the bridge is a
rounding error. Pass 5's three-step gradient (declare / honour / settle) was about *judgment*; this
one is about *who holds the mouse*, and it is the more general statement.

### Verified this pass — the agent layer

`git ls-remote` existence: **35/35 resolved.** Stars / forks / `pushed_at` from `search/repositories`.

| Repo | Licence | Stars / forks | Last push | Note |
|---|---|---|---|---|
| [ahujasid/mcp-for-blender](https://github.com/ahujasid/mcp-for-blender) | MIT | 35,788★ / 3,298f | 2026-11-18 | Bigger than Blender's own repo star count (22,543★). Self-declared: *"Not affiliated with the official Blender Foundation."* |
| [healkeiser/fxhoudinimcp](https://github.com/healkeiser/fxhoudinimcp) | MIT | 437★ / 55f | 2026-11-20 | Best maintained *studio* bridge found. |
| [capoomgit/houdini-mcp](https://github.com/capoomgit/houdini-mcp) | MIT | 312★ / 41f | 2026-06-11 | Second Houdini bridge, quiet 5 months. |
| [PatrickPalmer/MayaMCP](https://github.com/PatrickPalmer/MayaMCP) | MIT | 124★ / 36f | 2025-05-12 | Dormant 18 months, for the most-installed studio DCC. |
| [dcc-mcp/dcc-mcp-maya](https://github.com/dcc-mcp/dcc-mcp-maya) | MIT | 79★ / 9f | 2026-11-24 | Active alternative to the above. |
| [dcc-mcp/dcc-mcp-core](https://github.com/dcc-mcp/dcc-mcp-core) | MIT | 76★ / 9f | 2026-11-25 | Multi-DCC abstraction. |
| [binary-core-llc/bowerbot](https://github.com/binary-core-llc/bowerbot) | Apache-2.0 | 39★ / 3f | **2026-11-25** | Natural language → production-correct OpenUSD scene. Pushed the day of this pass. |
| [damionrashford/media-os](https://github.com/damionrashford/media-os) | MIT | 26★ / 6f | 2026-05-31 | Rare agent↔OpenTimelineIO join. |
| [sideshowroberto/vfx-agent-toolkit](https://github.com/sideshowroberto/vfx-agent-toolkit) | MIT | 21★ / 4f | 2026-11-09 | Owner-sized VFX agent tooling. |
| [dcc-mcp/dcc-mcp-openusd](https://github.com/dcc-mcp/dcc-mcp-openusd) | MIT | 2★ / 1f | 2026-11-24 | The USD bridge. Two stars. |
| [OpenAssetIO/OpenAssetIO-ComfyUI](https://github.com/OpenAssetIO/OpenAssetIO-ComfyUI) | Apache-2.0 | 2★ / 2f | 2025-09-30 | **The seam between this KB's generative plane and its production plane. Two stars, dormant 14 months.** |
| [OpenAssetIO/openassetio-mcp](https://github.com/OpenAssetIO/openassetio-mcp) | Apache-2.0 | **1★** / 1f | 2026-05-18 | Highest leverage, lowest stars. Pattern 17. |

### ⛔ The licence finding of this pass: OpenUSD is not Apache-2.0

[PixarAnimationStudios/OpenUSD](https://github.com/PixarAnimationStudios/OpenUSD) — **7,675★ /
1,486f, pushed 2026-11-23**, the foundation of the modern 3D pipeline and the thing AOUSD ratified a
Core Specification 1.0 for — is licensed under the **"Tomorrow Open Source Technology License 1.0"**
(`LICENSE.txt` on `master`, **49,827 B**, read this pass). Its own preamble states the delta:

> *"Note: The Tomorrow Open Source Technology License 1.0 differs from the original Apache License
> 2.0 in the following manner. Section 6 ('Trademarks') is different."*

Practically Apache-2.0 with a modified trademark clause — but it is a **separate, renamed licence**,
the GitHub API reports `NOASSERTION`, and no SPDX field, badge or SBOM scan will tell a client what
it is. This KB has now met four distinct ways a licence hides: a non-standard filename (pass 5), a
licence owned by the *compile* (Chromaprint, pass 5), an HTML file or a packaging classifier
(trend 22), and now **a renamed fork of a standard licence whose only delta is trademarks.**

### ⚠️ A third licence category at the platform tier: delayed-open

[ynput/ayon-backend](https://github.com/ynput/ayon-backend) and
[ayon-frontend](https://github.com/ynput/ayon-frontend) are **FSL-1.1-ALv2** — Functional Source
Licence, *ALv2 Future Licence* (`LICENSE`, 3,744 B each, read this pass): source-available now,
Apache-2.0 only after a delay. Meanwhile **every** AYON client component is plain Apache-2.0
(`ayon-core` 80★, `ayon-launcher` 55★, `ayon-blender` 20★, `ayon-houdini` 18★, `ayon-kitsu` 14★).

The platform/pipeline licence law of this KB held in all five previous planes with copyleft at the
platform. Here the platform chose **neither permissive nor copyleft but delayed-open, and split the
split *inside one product*.** A client told "AYON is Apache-2.0" has been told something true about
the clients and false about the server they would actually deploy.

### Contamination — two of the worst queries measured in any industry

| Query | Total | Reality |
|---|---|---|
| `virtual production` | **1,291** | Top hits are a Go asset embedder (`knadh/stuffbin`, 205★ — matches "production"), a dumped W3C report (176★), a mainframe emulator calling itself "production-quality" (113★). One defensible hit in the top six. |
| `color grading open source` | 42 | **Four of the top six are the Bee Movie script** (228★, 98★, 53★, 40★, each opening *"According to all known laws of aviation…"*). |

`virtual production` is the inverse of pass 5's `eidr`/`isan` trap and the same lesson: 1,291 looks
like abundance and is noise, while `opentrackio` returns **8 results of which 4 are real and
permissive**. Read the results, not the total.

### Informed gaps from this pass

- **Flamenco** (Blender's own farm manager) is not on GitHub; it lives at `projects.blender.org`,
  which **does not resolve from this session** (egress policy). Real, unverified here, not absent.
- **No agent bridge for review-and-approval**, though `OpenRV` (797★, Apache-2.0) and `xstudio`
  (782★, Apache-2.0) are both permissive and active. Notes/versions/approvals is the most
  agent-shaped workflow in post and the hook does not exist.
- **No licensed agent bridge for Nuke**: best found is `dughogan/nuke_mcp`, 40★, **no licence file**,
  2025-11-03. Compositing is the largest seat count in VFX.
- `www.gov.uk` and `www.linuxfoundation.org` **do not resolve from this session**, so the UK VFX
  relief wording and the AOUSD Core Spec 1.0 ratification date are carried at **secondary-source
  confidence only** — see `intel/market.md`. Not verified against primary text.

## 2026-11-22 — pass 5: the identification & rights-reservation plane (the first page with no stars)

Fifth pass of the same day, and the first to find a query whose **entire first page of results holds
zero stars**. The plane: *which asset is this, and who may train on it?* Before this pass the word
`fingerprint` did not appear anywhere in this KB.

**The measured zeros, which are the finding:**

| Query | Total | Top-6 stars | Verdict |
|---|---|---|---|
| `music royalty accounting` | 14 | **0, 0, 0, 0, 0, 0** | ⛔ Empty field. Four of six carry no licence. Starker than healthcare's `medical necessity` (3 stars across six). |
| `pay-per-crawl` | 33 | 5, 2, 2, 0, 0, 0 | ⛔ The AI-content settlement layer does not exist. |
| `eidr` | 160 | — | ⛔ **Zero relevant.** No open EIDR client. All false friends. |
| `isan` | 1,942 | — | ⛔ **Zero relevant.** All NLP libraries. No open ISAN tooling. |
| `cwr common works registration` | 8 | 16, 16, 8, 2, 0, 0 | Both real implementations dead since **2015** and **2018**. |

### The fifth consecutive confirmation of the structural law — now with a three-step gradient

Five planes, five identical results. This pass sharpens the law because the same subject matter
splits cleanly by function:

- **Declare** a reservation → format problem → **permissive, maintained daily.** `ai.robots.txt`
  (MIT, 4,265★/206f) pushed **2026-11-22**, the day of this pass.
- **Honour** a reservation → judgment problem → **MIT, 41★, dormant since 2024-10-09**
  (`Spawning-Inc/datadiligence`).
- **Settle** the obligation → pure judgment → **literal zero.**

Publishers are tooled to say no; nobody maintains the code that listens; nothing computes what is
owed.

### Verified this pass — newly added to this KB

All 30 repos of this pass: existence by `git ls-remote` (**30/30 resolved**), licence by fetching the
file and counting bytes, stars/forks/`pushed_at` from one `search/repositories` call each.

| Repo | Licence (verified) | Stars / forks | Last push | Why it is here |
|---|---|---|---|---|
| [beetbox/beets](https://github.com/beetbox/beets) | MIT, 1079 B | 15,972★ / 2,207f | 2026-11-22 | **The row to act on.** MIT catalogue platform that already joins fingerprint → identity → tags. Ratio 7.2. |
| [worldveil/dejavu](https://github.com/worldveil/dejavu) | MIT, 1070 B | 6,789★ / 1,463f | 2024-04-22 | Most-starred permissive fingerprinter. Ratio 4.6 = deployed. Dormant 2.5y. |
| [ai-robots-txt/ai.robots.txt](https://github.com/ai-robots-txt/ai.robots.txt) | MIT, 1069 B | 4,265★ / 206f | **2026-11-22** | The de-facto AI-crawler blocklist, updated daily. |
| [acoustid/chromaprint](https://github.com/acoustid/chromaprint) | ⚠️ **LGPL-2.1 as a whole** | 1,432★ / 180f | 2026-10-15 | The industry fingerprinter. **Licence depends on build flags** — see below. |
| [metabrainz/picard](https://github.com/metabrainz/picard) | GPL-2.0, 17983 B | 5,398★ / 479f | 2026-11-19 | Working proof of the fingerprint→metadata join. |
| [metabrainz/musicbrainz-server](https://github.com/metabrainz/musicbrainz-server) | GPL-2.0-or-later (`COPYING.md`) | 1,114★ / 347f | 2026-11-19 | Copyleft at the platform — the law holds again. |
| [metabrainz/listenbrainz-server](https://github.com/metabrainz/listenbrainz-server) | GPL-2.0, 18205 B | 1,077★ / 402f | 2026-11-22 | Ratio 2.7 = deployed. |
| [adblockradio/stream-audio-fingerprint](https://github.com/adblockradio/stream-audio-fingerprint) | MPL-2.0, 16722 B | 781★ / 65f | 2021-11-05 | The only **real-time/broadcast** matcher found. Weak copyleft. |
| [dpwe/audfprint](https://github.com/dpwe/audfprint) | MIT, 1112 B | 622★ / 136f | 2019-09-24 | Reference-grade landmark matching (Columbia/Google). Unmaintained. |
| [JorenSix/Olaf](https://github.com/JorenSix/Olaf) | AGPL-3.0, 32386 B | 426★ / 48f | 2026-10-16 | Embedded fingerprinting. **Active and copyleft.** |
| [beetbox/pyacoustid](https://github.com/beetbox/pyacoustid) | MIT, 1080 B | 413★ / 71f | 2026-05-19 | The clean way into Chromaprint/AcoustID. |
| [akamhy/videohash](https://github.com/akamhy/videohash) | MIT, 1075 B | 388★ / 65f | 2024-07-12 | Perceptual video hashing. Dormant, small enough to own. |
| [JorenSix/Panako](https://github.com/JorenSix/Panako) | AGPL-3.0 (`license.txt`, 32385 B) | 276★ / 53f | 2026-09-17 | Pitch/time-scale **invariant** matching — survives broadcast speed-ups. |
| [awslabs/speke-reference-server](https://github.com/awslabs/speke-reference-server) | Apache-2.0, 11357 B | 123★ / 50f | 2026-09-08 | SPEKE key-exchange reference. Ratio 2.5 = real. |
| [rslstandard/rsl](https://github.com/rslstandard/rsl) | ⛔ **NO LICENCE FILE** | 47★ / 1f | 2026-03-31 | The RSL 1.0 standard repo. **Unlicensed.** See below. |
| [Spawning-Inc/datadiligence](https://github.com/Spawning-Inc/datadiligence) | MIT, 1079 B | 41★ / 5f | 2024-10-09 | The *honouring* side. Dormant 2+ years. |
| [jeffpaul/rsl-wp](https://github.com/jeffpaul/rsl-wp) | ⛔ **NO LICENCE FILE** | 35★ / 1f | 2026-11-03 | Active RSL WordPress plugin, unlicensed. |
| [miqwit/dedex](https://github.com/miqwit/dedex) | MIT, 1063 B | 30★ / 15f | 2026-11-02 | DDEX ERN parser. Ratio 2.0 — the only live permissive DDEX code. |
| [iscc/iscc-core](https://github.com/iscc/iscc-core) | Apache-2.0, 11345 B | 26★ / 6f | 2026-10-17 | Reference implementation of **ISO 24138:2024**. |
| [iscc/iscc-sdk](https://github.com/iscc/iscc-sdk) | Apache-2.0, 11339 B | 24★ / 8f | 2026-10-26 | The practical ISCC entry point. |
| [onurkanbakirci/rsl-editor](https://github.com/onurkanbakirci/rsl-editor) | MIT, 1070 B | 22★ / 1f | 2026-02-16 | **The only properly licensed RSL tool found.** |
| [w3c-cg/tdm-reservation-protocol](https://github.com/w3c-cg/tdm-reservation-protocol) | ⚠️ W3C Software and Document Licence, 432 B | 17★ / 14f | 2026-09-03 | **TDMRep** — the EU DSM Art. 4 machine-readable opt-out. Ratio **1.2** = real infrastructure. |
| [weso/CWR-Validator](https://github.com/weso/CWR-Validator) | MIT, 1070 B | 16★ / 7f | **2015-07-31** | Rights registration, dead 11 years. |
| [aporia-records/APORIA-Works-Registration](https://github.com/aporia-records/APORIA-Works-Registration) | GPL-3.0, 35140 B | 16★ / 6f | 2018-09-06 | The other dead CWR implementation. |

Watermarking rows added the same pass (`resemble-ai/Perth` MIT 546★, `wavmark/wavmark` 323★ with an
**unfilled MIT template**, `swesterfeld/audiowmark` GPL-3.0 604★) are logged in `repos/trending.md`.

### ⛔ The sharpest licence trap yet: the rights-reservation standard is itself unlicensed

`rslstandard/rsl` — the repository of **RSL 1.0**, the licensing standard endorsed by Reddit, Yahoo,
Medium, Quora and Ziff Davis, whose whole purpose is machine-readable terms for content reuse —
**ships no licence file** (checked `master` and `main`, 11 filenames). Neither does the WordPress
plugin implementing it. Default copyright applies: all rights reserved. Use the published spec and
`rsl-editor` (MIT) for code, and raise it explicitly in any rights engagement. A defect in the
standard's packaging, **not** a reason to ignore RSL.

### ⚠️ Chromaprint: a licence decided by the compile — a new category for this KB

Its own `LICENSE.md`: own code MIT, bundled FFmpeg parts LGPL-2.1, *"as a whole, Chromaprint should
be therefore considered to be licensed under the LGPL 2.1 license"* — plus a third layer, the
**external FFT library you compile against** (FFmpeg LGPL-2.1 / FFTW3 **GPL-2.0+** / KissFFT BSD-3).
Build with FFTW3 and a redistributed binary is arguably GPL. T22 recorded licences hiding in HTML
files and packaging classifiers; this is worse — **the licence is a property of the build, not of the
repository**, so no SPDX field or source-tree SBOM scan can see it.

### Informed gaps from this pass

- **DDEX commercial terms: UNVERIFIED.** `new.ddex.net` does not resolve from this session (outside
  allowed network domains). Membership fees and implementer-licence terms are *unresearched, not
  free*. DDEX is reportedly developing an **AI rights-reservation message** — confirm at source.
- **No open implementation of EIDR, ISAN, ISRC or ISWC exists** — measured, not assumed, and
  structural: the scarce thing is the registry allocation, not the parser.
- **No media-specific agent appeared in the generic 2026 agent search** — only general harnesses.
  Sixth such measurement in this KB. Still no boom in permissive vertical media agents.
- **ISCC has no 2026 revision.** ISO 24138:2024, first edition, published 2024-05. Checked, because
  an invented version number is exactly the error this KB has been punished for.

## 2026-11-22 — pass 4: the conformance & preservation plane (two literal zeros)

Fourth pass of the same day. The plane was **measured at zero across all eight files at `HEAD`**
before any research: `mediainfo`, `mediaconch`, `ebur128`, `R128`, `BS.1770`, `CALM`, `archivematica`,
`bagit`, `qctools`, `FFV1`, `Matroska`, `OAIS` and `preservation` returned **no match anywhere in
this KB**. Nothing here overlaps passes 1–3 (general, monetization, accessibility).

**The headline is an absence, and it is the cleanest one this KB has measured:**

| Query | Total | Note |
|---|---|---|
| `broadcast QC agent` | **0** | Nothing, under any license. |
| `file-based quality control video stars:>=20` | **0** | Nothing above the noise floor. |
| `media preservation agent` | 1 | 1 star. Not a finding. |
| `archive metadata agent stars:>=20` | 2 | Both keyword collisions (`jettbrains/-L-`, `CNTRUN/Termux-command`). |
| `loudness normalization stars:>=50` | 2 | Both TTS/voice tools, not broadcast compliance. |
| `mediainfo mcp` | 2 | Top results at 0 and 2 stars. |
| `loudness agent` | 287 | **Contaminated, not populated** — top hit `kajisho5/ffmpeg-skill` (MIT, 9637★/859f) is an FFmpeg *skill pack*. Deliberately excluded; recorded so a later pass does not "discover" it as a media agent. |

So this section adds **no agent rows**, because there are none to add. Fourth consecutive
confirmation of this KB's law: **permissive open source follows the file format, not the judgment.**
The format layer of this same plane is mature and permissive — six implementations, several pushed
the day of this pass — and is catalogued in `repos/foundations.md`, not here.

**Licensing discovery of the pass, and it is reusable in all twelve industries.** A license can live
in three places and GitHub reads only one: a plain `LICENSE` file; **an HTML file** (`License.html` —
this is how `bavc/qctools` and `MediaArea/MediaConch` ship theirs, both reported `NOASSERTION`/`NONE`);
and **packaging metadata with no license file at all** (`bagit-python` declares `License :: Public
Domain` in a `pyproject.toml` classifier). Six repos in this plane carry a GitHub license field that
is wrong rather than vague. Best single find: **MediaConch is dual GPLv3+ *or* MPLv2+**, so under MPL
it can be linked into a closed client product — a fact every secondary source misses, sitting in an
HTML file.

**Dormancy worth recording:** `MediaArea/MediaConch`, the tool the field cites for Matroska/FFV1
conformance, has **not been pushed since 2021-09-29** (35★) while its siblings `MediaInfoLib` and
`RAWcooked` were both pushed 2026-11-22. Third plane in a row where **conformance is the weakest
link** (accessibility found it in caption conformance; the ad plane in SCTE-35).

## 2026-11-22 — pass 3: the accessibility plane (the duty with a deadline)

Third pass of the same day. Before starting, the gap was **measured, not guessed**: across all eight
files at `HEAD`, `imsc` 0 hits, `ttml` 0, `audio description` 0, `cea-608` 0, `cea-708` 0, `ebu-tt` 0,
`accessib*` 0, `closed caption` 0, `accessibility act` 0, `cvaa` 0, `wcag` 0. Meanwhile `subtitl*`
had 10 hits and `dubbing` 13 — so this KB knew subtitling **as a localization revenue activity and
not once as a compliance artefact.** That is the hole this pass fills.

**New in `agents/top.md` and `repos/foundations.md` this pass — all existence-verified with
`git ls-remote`, all licences read from the LICENSE file, all dates from blobless shallow clones:**

| Agent / Tool | Repo | License | Stars | Last push | Note |
|---|---|---|---|---|---|
| Subtitle Edit | [SubtitleEdit/subtitleedit](https://github.com/SubtitleEdit/subtitleedit) | MIT | 15,100 | 2026-11-22 | Pushed *today*. **MIT, not GPL** — the widely repeated claim is wrong; LICENSE read. |
| stable-ts | [jianfch/stable-ts](https://github.com/jianfch/stable-ts) | MIT | 2,300 | 2026-05-30 | Word-level timestamps for Whisper. Slowing (176 days). |
| Able Player | [ableplayer/ableplayer](https://github.com/ableplayer/ableplayer) | MIT | 837 | 2026-11-20 | Carries AD **and** sign-language tracks natively. |
| CCExtractor | [CCExtractor/ccextractor](https://github.com/CCExtractor/ccextractor) | GPL-2.0 | 919 | 2026-11-11 | CEA-608/708 extraction. No permissive equivalent exists. |
| subaligner | [baxtree/subaligner](https://github.com/baxtree/subaligner) | MIT | 509 | 2026-11-02 | Forced-alignment re-sync. |
| ttconv | [sandflow/ttconv](https://github.com/sandflow/ttconv) | BSD-2-Clause | 242 | 2026-11-21 | STL/SRT/TTML/SCC/WebVTT conversion. |
| imscJS | [sandflow/imscJS](https://github.com/sandflow/imscJS) | BSD-2-Clause | 92 | 2026-11-20 | IMSC → HTML5 reference renderer. |
| IMSC tests | [w3c/imsc-tests](https://github.com/w3c/imsc-tests) | W3C Test Suite **or** W3C BSD-3 | 18 | 2026-10-22 | Dual-licensed; the Test Suite option forbids derivatives — take BSD-3. |
| imscHRM | [sandflow/imscHRM](https://github.com/sandflow/imscHRM) | BSD-2-Clause | 10 | 2024-05-16 | ⚠️ Dormant ~920d. |
| EBU-TT Live toolkit | [ebu/ebu-tt-live-toolkit](https://github.com/ebu/ebu-tt-live-toolkit) | BSD-3-Clause | 27 | 2021-12-21 | ⚠️ Abandoned ~1,797d. |

### The finding of this pass

**The format layer is alive; the conformance layer is dead.** `ttconv` and `imscJS` were both pushed
within 48 hours of this measurement. `imscHRM` — the validator that answers whether a caption file
can actually render in real time — has not moved in 920 days, and `ebu-tt-live-toolkit`, the
reference implementation of Europe's live-subtitle contribution spec, has not moved in ~5 years,
*while the EAA turned live subtitling into a legal duty in June 2025.*

Both dormant repos are BSD and small. That makes reviving one the cheapest high-visibility open-source
contribution available to Globant anywhere in this KB, and it sits under a compliance budget rather
than an innovation budget.

### Audio description: a 56-star ceiling under a statutory mandate

Searched for open AD tooling and found **only prototypes**: `microsoft/ai-audio-descriptions` (MIT,
**56★**, README says research/experimentation, ships no authentication),
`asadullah48/accessai` (Apache-2.0, the only live-AD attempt, scores against WCAG 2.2 AAA),
`jdmiller/audio-description-generator` (MIT, local vision model, WCAG 1.2.5),
`fhswf/descraibe` (MIT, **0★**, German university), `arnabdotorg/open-vtt` (AGPL-3.0, extended AD,
WCAG 1.2.7), `Double-FW/Audio-Descriptions` (MIT, editorial rules — documents, not code).

56 stars is the ceiling of the entire open AD layer, against Subtitle Edit's 15,100 in the caption
layer next door — while the FCC requires 50 hours of AD per calendar quarter and the EAA requires it
wherever the picture carries information the sound does not. **Recorded as the clearest unmet build
opportunity in this KB.**

### One licence trap caught

`sign/translate` — formerly `sign.mt`, now **"Rylo Translate" (Nagish Inc.)** — is the most visible
sign-language translation project and reads as open source from its GitHub page. Its LICENSE.md is a
**dual-tier source-available** licence: free for individuals, non-profits and education, and *"a
separate license is required for for-profit commercial organizations."* It cannot be used in a client
engagement without buying a licence. Added to Tier 2 with that constraint attached.

### Informed gaps from this pass

- **No open sign-language *generation*** (avatar/synthesis) with meaningful adoption was found, only
  the commercially-licensed translation project above.
- **Japan (MIC) subtitling targets:** searched, not found in accessible sources. Australia's ACMA
  quotas were found and are recorded in `intel/market.md`; Japan's are not, and that is a gap in this
  KB rather than an absence of regulation.
- **No regulation found anywhere** that governs the *use of AI* to produce accessibility assets
  (automatic AD, machine captions as legal compliance). Regulators mandate the artefact and are silent
  on the method — which is permission to automate, and the commercial opening for this plane.

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

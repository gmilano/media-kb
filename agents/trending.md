---
industry: media
region: Global
updated: 2026-11-26
---

# 📈 Trending Media AI Agents — append-only log

> Newest section first. **Nothing below is ever rewritten** — that history is the only way to see
> which projects actually sustained momentum and which spiked and died.

## 2026-11-26 — pass 21: the spatial, immersive & volumetric-capture plane (**the most-starred repo in the plane cannot be shipped**)

**What is new to this KB.** A ~60-term word-boundary probe found the plane missing almost entirely:
`Quest` 0, `Godot` 0, `WebXR` 0, `glTF` 0, `photogrammetry` 0, `point cloud` 0, `gaussian splat` 0,
`NeRF` 0, `mocap` 0, `rigging` 0, `USDZ` 0, `MV-HEVC` 0, `digital human` 0, `XR` 1, `volumetric` 1
(a single OpenVDB description). Pass 6 held LED-volume virtual production and pass 12 held immersive
audio, so the KB had the stage and the soundfield and nothing in between.

**Pushed within 72 hours of measurement:**

| Name | Repo | Stars | Licence (verified) | HEAD | Note |
|---|---|---|---|---|---|
| LichtFeld-Studio | https://github.com/MrNeRF/LichtFeld-Studio | 4,040★ | GPL-3.0 | 2026-11-26 | Native splat train/edit/export; pushed the day of measurement |
| Spirula Studio | https://github.com/harry7557558/spirula-studio | 2,624★ | GPL-3.0 | 2026-11-26 | Video→splat→mesh, Vulkan or CUDA, cross-vendor |
| Three-Live | https://github.com/google/three-live | 516★ | Apache-2.0 | 2026-11-25 | **Released this month.** Three.js → glTF/USDZ/WebXR via an on-device JIT compiler; Google's explicit bet that 3D assets get generated, not authored |
| Brush | https://github.com/ArthurBrussee/brush | 5,392★ | Apache-2.0 | 2026-11-23 | Rust/WebGPU 3DGS, CUDA-free — the portability play |
| SuperSplat | https://github.com/playcanvas/supersplat | 10,731★ | MIT | 2026-11-19 | The editor the rest of the stack post-processes with |
| open4dgs-core | https://github.com/ASU-NEM-Labs/open4dgs-core | 161★ | MIT | 2026-11-21 | The only permissive **and active** production 4D (temporal) pipeline found |
| 3DGRUT | https://github.com/nv-tlabs/3dgrut | 2,515★ | Apache-2.0 | 2026-11-06 | NVIDIA's ray-traced Gaussians — **Apache, unlike its own instant-ngp** |
| SplatXR | https://github.com/splatxr/splatxr | 39★ | MIT | 2026-10-29 | On-headset splats with physics/shadows/portals (PSI Lab) |

**The headline, and it inverts how a popularity sweep reads this plane.** The original
`graphdeco-inria/gaussian-splatting` holds **24,564★** under the **Gaussian-Splatting License**
(Inria + MPII): research and evaluation only, commercial use by explicit consent through Inria's tech
transfer office. The repo that actually makes 3DGS shippable, `nerfstudio-project/gsplat`, is
Apache-2.0 at **5,961★ — 24% of the stars of the repo it replaces.** `NVlabs/instant-ngp` repeats the
pattern at 17,604★ under the non-commercial NVIDIA Source Code License. **In this plane star count is
an inverse proxy for usability**, and any ranked-by-popularity recommendation hands a client the one
thing they may not use.

**A licence category not previously recorded in this KB: the registration gate.** `zju3dv/EasyVolcap`
(1,600★) and `zju3dv/EasyMocap` (4,993★) carry **Project Registration License (PRL) v1.0**, dated
2026 and read in full. It is *not* non-commercial — organisational use of any kind is free, but the
project must be **registered via a Google Form before use begins**, one registration per materially
distinct project, with no fee and no approval needed. There is **no patent grant**. GitHub reports
`NOASSERTION`, so no SPDX field or SBOM scan of the tree can carry the obligation: it belongs in the
engagement-setup checklist, before work starts. Reading it as "non-commercial" — the obvious
mistake — would have wrongly discarded the strongest open neural-volumetric-video codebase.

**Where the plane actually breaks, measured on the time axis.** Static capture is permissive and
healthy (gsplat Apache-2.0 5,961★; Brush Apache-2.0 pushed 2026-11-23; COLMAP new BSD pushed
2026-11-26). Delivery to a headset is permissive and enormous (three.js MIT 119,448★; Godot MIT
120,865★; OpenXR-SDK Apache-2.0). **The temporal layer in between — the thing that makes volumetric
*video* rather than 3D photography — is the hole:** `hustvl/4DGaussians` is Apache-2.0 at 4,047★ and
has not been pushed since **2024-10-27 (25 months)**; the permissive active alternative is
**161★**. Falsifiable: if 4DGaussians revives or open4dgs passes ~1k★ within two quarters, this
expires.

**Informed gaps.** No open-source production encoder for Apple Immersive Video / MV-HEVC exists — only
x265 multiview plus an ffmpeg remux, and small project-level work whose own authors note Vision Pro
playback is untested; the one live MV-HEVC broadcast encoder announced in 2026 (SpatialGen, AWE USA)
is proprietary. **Monado**, the leading open OpenXR runtime, **could not be verified from this
session**: its canonical home `gitlab.freedesktop.org` was refused by the egress proxy (HTTP 403,
host not permitted), and every GitHub "monado" hit is an unrelated fork (top result 5★, pushed
2022-03-16). Recorded as not investigated, not as absent.

**Oracle correction.** `search/repositories` with `q=repo:<slug>` returned HTTP 422 "resources do not
exist" for three repos that `git ls-remote` confirms exist (`nerfstudio-project/viser`,
`pierotofy/OpenSplat`, `mozilla/hubs`). The index's silence is evidence of nothing; `ls-remote` for
existence and the raw licence probe for terms both resolved in one call each.

---

## 2026-11-26 — pass 20: the investigative-journalism, source-protection & fact-checking plane (**the agent layer is finally permissive and alive — and still not shippable**)

**What is new this week in this plane, and what is new only to this KB.** A ~90-term vocabulary probe
over the eight live files found the newsroom's own craft missing entirely: **`journalism` occurred 4
times in the whole KB, all four in one file**, while `SecureDrop`, `GlobaLeaks`, `OSINT`,
`data journalism`, `Aleph`, `Datasette`, `Bellingcat`, `press freedom`, `source protection`,
`whistleblow` and `reverse image` were **all zero**, and all 73 occurrences of `verification` were
age-verification (pass 15) or file conformance (pass 4). Pass 8 had already named the **newsroom** as
LATAM's hottest buyer, so the KB was selling to a buyer whose tools it had never recorded.

**Genuinely new this week (pushed within 48 hours of measurement):**

| Name | Repo | Stars | Licence (verified) | HEAD | Note |
|---|---|---|---|---|---|
| claude-skills-journalism | https://github.com/jamditis/claude-skills-journalism | 462★ | MIT | 2026-11-25 | Verification, FOIA, transcription, data-journalism skills |
| Spotlight | https://github.com/buriedsignals/spotlight | 67★ | MIT code / **CC BY-ND 4.0 methodology** | 2026-11-25 | OSINT orchestrator; see the licence trap below |
| Datashare | https://github.com/ICIJ/datashare | 784★ | AGPL-3.0 | 2026-11-26 | ICIJ's self-hosted document platform, pushed the day of measurement |
| Uwazi | https://github.com/huridocs/uwazi | 330★ | MIT | 2026-11-26 | HURIDOCS documentation database, also pushed that day |
| OnionShare | https://github.com/onionshare/onionshare | 7,247★ | GPL-3.0 | 2026-11-26 | Anonymous transfer over Tor |

**THE HEADLINE: the law of the previous nineteen passes inverts here, and then reasserts itself one
level up.** The standing law has been *strong substrate, empty agent layer*. This plane has a strong
substrate **and** a live permissive agent layer — the first in twenty passes. But the agent layer is
a **skills-and-prompt layer, not a code layer**: its competence is methodology prose. So the binding
licence moves off the dependency tree and onto the text, which is exactly where the healthcare
passes found it (CPT, MedDRA). **Prediction, falsifiable: every industry in this rotation will show
the same migration as its agent layer matures — permissive code, encumbered knowledge — and an SBOM
will see none of it.**

**LICENCE CATEGORY 12, AND THE FIRST ONE WHOSE SUBJECT IS THE SOFTWARE'S OUTPUT.**
`ehurrn/newsroom-extension` (11★) ships a `LICENSE` whose first two paragraphs are the Unlicense
verbatim. Diffed word-by-word against the canonical SPDX text, the third paragraph is replaced and
this is added: *"We dedicate any and all copyright and related or neighboring rights to this work to
the public domain worldwide. **This dedication applies to any work produced by the software**, unless
such work explicitly indicates otherwise."* A public-domain dedication reaching the **output** — for
a newsroom, its journalism, the one asset it has and the basis of every rights reservation in pass 5.
Escapable via the opt-out, invisible to every scanner: GitHub says `NOASSERTION`, the file is named
`LICENSE`, and it reads like the Unlicense until you get to the clause.

**THE CONTENT LAW, NOW INSIDE AN AGENT'S SKILL FILES.** `buriedsignals/spotlight` is MIT, and its own
licence file declares the skills *"adapt or synthesize methodology from"* GIJN's Patrucic & Cosic,
"Introduction to Investigative Journalism: Following the Money" (Nov 2024), **`CC BY-ND 4.0`** —
NoDerivatives — plus Bellingcat training material and an EBU Eurovision News piece (Dec 2025). A repo
offering adapted ND-licensed text under MIT has an unresolved tension on its face. Diligence item,
not a legal conclusion — but for an agent the methodology **is** the product, so MIT on the repo
settles nothing.

**THE MEASURED ZEROS, WITH A CONTROL GROUP IN THE SAME CHANNEL ON THE SAME DAY.** Automated
fact-checking is this plane's real void: `DEFAME` (64★, Apache-2.0) dormant since **2025-09-30**, and
below it **four literal zeros** — `ClaimVerify`, `Ai-Claim-Verification`, `claimcheck`, `ClaimLedger`
— three pushed in the last eight weeks. `claim verification fact check newsroom` returns **one
repository on Earth** (1★, no licence). Control: `sherlock-project/sherlock`, **117,843★**. Open
source is not weak at investigation; it is weak at **adjudicating a claim**.

**METHOD FINDING THAT CHANGES HOW THIS KB SEARCHES — cycle 8's lesson has a mirror image.** Pass 15
learned *search the obvious term or you will miss a layer* (age verification). Here the obvious term
is **a trap**: `whistleblower submission platform` returns 8 repos whose top six hold **2 stars
between them**, while SecureDrop (3,897★) and GlobaLeaks (1,529★) — the two world standards — do not
appear at all. Same for `FOIA freedom of information request`: top-6 = 35★, five of six unlicensed,
top result last pushed **2017-12-11**, while Alaveteli (421★) and Froide (413★) are current. The
reason is structural: **institutional tools are named, not described.** New rule for all twelve
industries: in any plane with institutional incumbents, query the **institution** —
`freedomofpress`, `ICIJ`, `MuckRock`, `bellingcat`, `mysociety`, `huridocs`, `meedan` — because the
functional keyword returns only the vanity layer.

**TWO CORRECTIONS TO THIS KB'S OWN VERIFICATION ORACLE, both found by contradiction.**
(1) **`pushed_at` is not liveness.** The search channel reported `alephdata/aleph` at
`pushed_at=2026-02-20`; its default branch `develop` last moved **2025-12-19** and `main` is older
still (**2025-08-07**, release 4.1.6). A six-month overstatement on the most-recommended repo in the
plane; `DEFAME` showed the same gap. Resolve the **default branch** and read **its** last commit —
`git clone --depth 1 --single-branch` answers both at once.
(2) **`ls-remote` proves reachability, not canonical naming.** `globaleaks/globaleaks` resolves on
both the ls-remote and raw channels and is a **rename redirect**; the canonical repo is
`globaleaks/globaleaks-whistleblowing-software` (1,529★, AGPL-3.0), proven by identical HEAD SHA
`efa0161c`. GitHub honours renames forever, so ls-remote cannot detect one — which is also why
`repo:globaleaks/globaleaks` fails in the search index while the repository plainly exists.

**Also recorded:** `morisy/muckrock-mcp` (3★) is the only FOIA MCP bridge in existence and has **no
licence file**, its own author calling it "highly experimental, insecure, and unstable" — the
clearest publishable build gap found this pass. `Juanangara/newsroom-agents` (0★) has a sound
researcher→verifier→editor design whose verifier must quote source text, and **no licence file at
all**. `mantisfury/ArkhamMirror` (509★, MIT) is the best-starred journalism agent platform and has
not moved since **2026-01-25**.

**VERIFICATION: 40/40 repository URLs in this pass resolve** via `git ls-remote --exit-code`; every
star/licence/push value from the `gh api search/repositories` channel; every default-branch HEAD by
shallow clone; four licence files read in full where the API said `NOASSERTION`
(SecureDrop → AGPL-3.0, OnionShare → GPL-3.0, Alaveteli → AGPL-3.0, Spotlight → MIT + ND methodology).

## 2026-11-26 — pass 19: the sports-media, live-event & fan-engagement plane (**the first plane with a control group, and the crudest zero yet**)

**What is new this week in this plane, and what is simply new to this KB.** A vocabulary probe over
all eight files before searching the web — the cycle-8 method, ~1 call — returned **0 hits** for
`play-by-play`, `box score`, `Sportradar`, `tracking data`, `officiating`, `sports rights`,
`player stats`, `odds` and `merchandise`, and **1** for `esports`, against **246 lines** for
`broadcast`. The plumbing was covered; the largest category of live media value was not.

**Genuinely new this week (pushed within four days of this pass):**

| Repo | License | Stars | Forks | Last push |
|---|---|---|---|---|
| `jipraks/yt-short-clipper` — long-form → 9:16 AI highlight clipper | **MIT** | 1,113 | 316 | 2026-11-26 |
| `ColinGPT9/clips-studio` — local Opus Clip alternative | AGPL-3.0 | 700 | 149 | 2026-11-26 |
| `roboflow/supervision` — the permissive CV workhorse | **MIT** | 51,730 | 4,963 | 2026-11-26 |
| `ultralytics/ultralytics` — YOLO26/27 | ⚠️ AGPL-3.0 | 63,769 | 12,045 | 2026-11-26 |
| `sportsdataverse/sportsdataverse-py` | **MIT** | 133 | 22 | 2026-11-26 |
| `roboflow/sports` — the keystone sports-CV repo | **MIT** | 5,517 | 684 | 2026-11-25 |
| `davidpagnon/Sports2D` — 2D pose + joint angles | **BSD-3-Clause** | 354 | 52 | 2026-11-25 |
| `Anil-matcha/AI-Youtube-Shorts-Generator` | **MIT** | 6,577 | 1,217 | 2026-11-24 |
| `LaihoE/demoparser` — CS2 replay parser | **MIT** | 746 | 110 | 2026-11-24 |
| `markus-wa/demoinfocs-golang` — CS2 demo parser | **MIT** | 1,078 | 156 | 2026-11-23 |
| `pnxenopoulos/awpy` — CS2 analysis | **MIT** | 640 | 89 | 2026-11-22 |

**The finding — and it is a method result, not just a list.** Sports is the first plane in this KB
where the *same* problem (extract spatiotemporal events from a match) exists with **three different
data substrates**, so difficulty is held constant and only ownership varies. Pixels you already
license → permissive and abundant. Vendor optical feeds → high stars, no usable grant. Client-side
esports replays → permissive and active. **Esports telemetry is open because the file is on the
player's disk; football telemetry is closed because the file is on Opta's server.** The content law
finally has a control group instead of a correlation. Full table in `agents/top.md`.

**The crudest zero this KB has recorded.** `fan engagement`: top six results are **28★, 6★, 5★, 4★,
3★, 3★** — ~49 stars combined — and the leader (`ASportsV/iBall`) has **no licence** and last moved
**2023-12-12**. Cycle 8's `music royalty accounting` summed to 0 stars, but this one is worse in a
way that matters commercially: here the spend is enormous and documented, and still nobody has
written the code. Betting/odds is likewise dead — most-starred `S1M0N38/soccerapi` (MIT, 182★) has
not moved since **2022-12-08**.

**Three licence traps found this week, all in repos with four-figure stars:**

1. `hudl/open-data` (3,847★) — licence is **`LICENSE.pdf` at the repo root**. HTTP 200,
   `application/octet-stream`. GitHub reports `NOASSERTION` because SPDX detectors read text, not
   PDFs. **No badge, SPDX field or SBOM scan can see this.**
2. `hudl/statsbombpy` (758★) — the official Python client has **no licence file at all**; its README
   points to that PDF for *data* terms and requires registration. The code carries no grant.
3. `hudl/StatsBombR` (314★) — `DESCRIPTION` declares **`License: 3.5.0`**. A version number in the
   licence field: not missing, not custom, just filled from the wrong field.

**And one false negative corrected, worth more than the traps.** Five R packages reported
`NOASSERTION` and **all are MIT**: CRAN's convention ships a 46–57 byte `LICENSE` holding only
`YEAR:`/`COPYRIGHT HOLDER:`, puts the grant in `LICENSE.md`, and writes
`License: MIT + file LICENSE` in `DESCRIPTION`. `nflfastR` (558★), `hoopR` (157★), `cfbfastR` (114★)
and `nflreadr` (117★) were all recoverable — rescuing the whole nflverse/sportsdataverse cluster,
and probably R packages in the health, finance and energy KBs as well.

**Momentum check against earlier passes.** `roboflow/supervision` at 51,730★ and `ultralytics` at
63,769★ confirm that the detection/tracking layer — absent from this KB for eighteen passes — is one
of the largest permissive-vs-AGPL forks in open source, not a niche. The sports-specific layer is
two orders of magnitude smaller (`roboflow/sports` 5,517★, `kloppy` 573★) and that ratio is the real
shape of the opportunity: the general substrate is solved and free; the sports-specific glue is thin
and mostly maintained by two or three people.

## 2026-11-26 — pass 18: the book, ebook & scholarly-publishing plane (the **written word**, measured for the first time)

**What is new this week in this plane, and what is simply new to this KB.** Seventeen passes covered
the audiovisual side of M&E. A vocabulary probe over the whole KB returned **0 hits** for `Readium`,
`Calibre`, `ONIX`, `Pressbooks`, `Open Journal`, `Thorium` and `Audiobookshelf` — so most of what
follows is not newly built, it is newly *recorded*. The genuinely recent movement is flagged as such.

**Moving right now (verified last-commit dates, 2026-11-26):**

| Project | Repo | Licence (file read) | Last commit | Why it is moving |
|---|---|---|---|---|
| ebook2audiobook | https://github.com/DrewThomasson/ebook2audiobook | Apache-2.0 | 2026-11-24 | Voice-cloning audiobook conversion; the most active AI project in the plane |
| book-writer | https://github.com/tobyilee/book-writer | MIT | 2026-11-21 | Multi-agent book harness with EPUB output; appeared on trending lists early Nov 2026 |
| accessibility-agents | https://github.com/Community-Access/accessibility-agents | MIT | 2026-11-07 | **The only EPUB-aware agent found**; WCAG 2.2 AA skills for coding agents |
| pdf-accessibility-app | https://github.com/CUNY-AI-Lab/pdf-accessibility-app | AGPL-3.0 | 2026-11-25 | Nov 2026 PR made a model-service failure flag the figure for re-upload instead of silently passing alt text — an honest-failure design worth copying |
| epub_to_audiobook | https://github.com/p0n1/epub_to_audiobook | MIT | 2026-10-26 | Gained stars late Oct 2026 |

**The substrate is overwhelmingly alive, which is the real headline.** Of 40 repos verified in this
pass, **28 had a commit in November 2026**, including `pkp/ojs`, `calibre`, `thorium-reader`,
`openlibrary`, `pressbooks` and `sigil` all on 2026-11-23 or later. This is not a legacy plane.

**The licence shape, stated once (full argument in `agents/top.md`):** in publishing the licence is
ordered by **who wrote the code** — standards bodies ship BSD/MIT (`epubcheck`, `ace`, `readium/*`),
the scholarly commons ships GPL/AGPL (`ojs`, `pressbooks`, `manifold`, `openlibrary`). This
**inverts** pass 4's AV finding, where the checker was the copyleft component.

**⛔ Watch item: `ebooklib` is AGPL-3.0.** The default Python EPUB library carries network copyleft.
Most likely accidental obligation in a publishing engagement.

**⛔ Watch item: a badge is not a licence.**
`AIScientists-Dev/AI-Powered-PDF-Accessibility` advertises MIT in a shields.io badge, in prose, and
under a `## License` heading, and ships **no licence file at all** (ten probe filenames, all 404).
New category for this KB — the inverse of a hidden licence.

**Informed gaps, searched and genuinely not found this week:** no agentic layer over ONIX metadata;
no open EPUB alt-text generator (the one EPUB-specific result, "AltGen", is a paper with no located
code); no peer-review or manuscript-triage agent against 25,000+ OJS journals.

## 2026-11-26 — pass 17: the development & pre-production plane (the agent layer **splits down the middle of one plane**)

### A new shape, and the cleanest split measured so far

Fourteen planes produced near-zero agent layers; pass 14 broke the streak; pass 15 found a
vendor-captured layer; pass 16 found one born in a quarter and adopted by nobody. **This plane produces
something different again: a layer that is healthy on one side of a single workflow and absent on the
other.** The workflow is script → breakdown → stripboard → schedule → call sheet → budget. Everything
left of the breakdown has permissive, maintained agents. Everything right of it has none.

**Permissive and alive — all five operate on *story*:**

| Agent | Repo | Stars | License | Last push |
|---|---|---|---|---|
| PenShot | neopen/story-shot-agent | 248★ | **Apache-2.0** | **2026-11-26** (measurement day) |
| how-to-make-script | XucroYuri/how-to-make-script | 21★ | **MIT** | 2026-08-24 |
| ai-screenplay-writer | E-Asrar-Haghighi/ai-screenplay-writer | 11★ | **MIT** | 2026-03-12 |
| visual-storytelling-skills | leynos/visual-storytelling-skills | 11★ | **ISC** | **2026-11-26** (measurement day) |
| Story-Film-Skills | badgids/Story-Film-Skills | 10★ | **Apache-2.0** | 2026-08-24 |

**Unlicensed or source-available — and these are the ones that touch production management:**

| Agent | Repo | Stars | License status |
|---|---|---|---|
| waoowaoo | waooAI/waoowaoo | **14,989★** | 🚫 **Elastic License 2.0** — not open source |
| film-studio-skills | machina-exm/film-studio-skills | 186★ | ⚠️ **no license file** (17 names × 2 branches, control README 200) |
| motion-graphics-skills | imMamdouhaboammar/motion-graphics-skills | 69★ | 🚫 **"PROPRIETARY AND CONFIDENTIAL — ALL RIGHTS RESERVED"** |
| script-weaver | KKenny0/script-weaver | 11★ | ⚠️ no license file |
| Script-Breakdown-Skills | jpcastel88/Script-Breakdown-Skills | 6★ | ⚠️ no license file |

**The one-line version: every agent that generates a story is permissive, and every agent that runs a
production is not.** 15,261 stars sit on the unlicensed/source-available side; 301 sit on the permissive
side. The money follows the restriction.

### Two false friends, one of them the worst in the KB

- **`stripboard` → 112 results, ZERO relevant.** Every result is electronics: modular-synth perfboard
  layouts (`golkit1/Stripboard-Layouts`, 46★ GPL-3.0), a PCB autorouter (`rogerdahl/striprouter-cpp`,
  27★ MIT), a circuit layout editor (`KarloFunke/stripboard-editor`, 19★ GPL-3.0). The stripboard is the
  defining artefact of film scheduling and **its name belongs to electronics on GitHub.**
- **`call sheet agent` → 109 results, ZERO relevant.** All n8n/Vapi/Twilio phone-call sales bots.

Both are the `eidr`/`isan` pattern from pass 5 and they confirm its second half: a short query can
manufacture **false abundance** as easily as a long one manufactures a false zero. 112 results and 0
findings is not a thin plane — it is a collision.

### Watch item with a falsifiable prediction

`neopen/story-shot-agent` (Apache-2.0, 248★) pushed on measurement day and is the only permissive,
maintained, non-trivial agent in the plane. **Prediction, to check next media pass:** it will still be
the only one, and the breakdown-to-schedule side will still have no permissive agent above 25 stars.
If a permissive management-side agent appears above that line, the plane has started to open and the
build-vs-integrate advice in `verticals/solutions.md` needs revisiting.

## 2026-11-26 — pass 16: the avails, windowing & distribution-rights plane (an agent layer **born in one quarter, adopted by nobody**)

### A new shape: six agents, all permissive, all at zero

Fourteen passes found agent layers that were *absent*. Pass 15 found one that was *vendor-captured*. This
plane has the third shape: **the agent layer exists, is cleanly MIT/Apache licensed, and has no users.**

| Agent | Repo | Stars | Licence | Created | Last push |
|---|---|---|---|---|---|
| evangeline-legal-agent | falcoschaefer99-eng/evangeline-legal-agent | 3* | Apache-2.0 | 2026-06 | 2026-06-30 |
| Rights-Clearance-Scanner | IBR4H33M/Rights-Clearance-Scanner | 0* | MIT | 2026-09-06 | 2026-10-12 |
| soundwave_cue_sheet_palooza | lucylow/soundwave_cue_sheet_palooza | 0* | MIT | 2026-09 | 2026-09-16 |
| screenplay-clearance-agent | Priyanka-Purushotham5/screenplay-clearance-agent | 0* | MIT | 2026-09 | 2026-09-09 |
| cueclear | buildwithtolu/cueclear | 0* | MIT | 2026-08-21 | 2026-09-09 |
| rights-clearance-scout | nawaltahir/rights-clearance-scout | 0* | MIT | 2026-08 | 2026-08-22 |

**Every one was created between June and October 2026.** That is not a trend line, it is a single
quarter's worth of simultaneous attempts at the same problem, with no survivor yet. Zero stars at three
to five months is unvalidated code, not early code.

**What they all do, and what none of them does.** All six do *discovery* — scan a screenplay, sweep a
trademark register, derive a cue sheet from an edit. **None evaluates an availability window and none
computes a payment.** The agent layer stopped exactly where this KB's structural law predicts it
stops: at the judgment steps that carry liability.

**Falsifiable prediction, recorded for scoring.** By **2027-05-31**, either one of these six exceeds
**25 stars**, or the 2026-Q3/Q4 clearance-agent cohort is confirmed abandoned. A later pass should check
and write down which.

**Best-shaped of the six:** `cueclear`, because it ingests an **EDL/XML** — an artefact that genuinely
falls out of a locked edit — instead of asking a human to describe the problem in prose. Prior art for a
design, not a dependency.

**Method note carried forward.** `rights clearance` returns 40 repos in total; the remainder are one
author's duplicated workbench (`williamsahoo1`, three slugs, no licence) and a false friend
(`draron-dare-045/Final_Rights` — secondary-school certificate clearance in Kenya). The six rows above
are all that survive reading the results.


## 2026-11-26 — pass 15: the out-of-home, signage & retail-media plane (the agent layer is **present but vendor-captured** — a new shape)

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

### Why this is a different finding from the previous fourteen passes

Passes 1–13 measured agent layers that were *absent*. Pass 14 found the first real one. Pass 15 finds the first one that is **occupied by incumbents**: 14 repos, top 2 stars, and the identifiable entries are MCP bridges into closed SaaS signage platforms. Absence leaves a greenfield; occupation sets a default. The practical consequence is in `compose/patterns.md` P15.5 — own the abstraction, read the vendor MCPs as shape references, and do not take one as a dependency.

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


## 2026-11-26 — pass 14: the localization & translation-management plane (the streak of fourteen near-zero agent layers **ends**)

### Headline: the first plane in this KB with a real, maintained, permissive agent layer

Thirteen consecutive passes measured a near-zero agent layer. This one does not, and the reason is
structural rather than lucky: **translation is the only media task with a forty-year commercial
tooling industry behind it.** The scarcity has not disappeared — it has moved from the tooling to the
*agreement* (see the quality measurement below).

Measured the industrial substrate under dubbing and subtitling — formats, memories, termbases,
routing and quality contracts. **49 slugs checked with `git ls-remote`, 47 resolve, 2 do not, and
0 of the 47 already appeared anywhere in this KB.** The widest true gap found in any pass: before
today `xliff`, `tmx`, `translation memory`, `termbase`, `terminology`, `glossary`, `MQM`,
`post-editing`, `quality estimation`, `Weblate`, `Okapi` and `OmegaT` were **all at zero hits**
across all eight files, while `dubbing` sat at 46, `subtitle` at 61 and `caption` at 126. This KB
knew how to *make* a dub and nothing about how to *run a localization programme*.

| Agent / tool | Repo | Licence | Stars | Pushed | Note |
|---|---|---|---|---|---|
| LibreTranslate | [LibreTranslate/LibreTranslate](https://github.com/LibreTranslate/LibreTranslate) | AGPL-3.0 | 17,851 | 2026-11-25 | The headline MT server — and the licence is in the wrapper, not the engine |
| argos-translate | [argosopentech/argos-translate](https://github.com/argosopentech/argos-translate) | **MIT** | 6,696 | 2026-11-17 | The MIT engine LibreTranslate pins. The pick. |
| BallonsTranslator | [dmMaze/BallonsTranslator](https://github.com/dmMaze/BallonsTranslator) | GPL-3.0 | 5,321 | 2026-11-21 | CJK comic CAT: OCR → inpaint → MT → typeset. The most active *applied* localization engineering found. |
| Transub | [dlsandy/Transub](https://github.com/dlsandy/Transub) | ⚠️ "MIT (Core)" | 222 | 2026-11-25 | Subtitle generation + QC + burn-in. Prompts excluded from MIT — see below. |
| LTEngine | [LibreTranslate/LTEngine](https://github.com/LibreTranslate/LTEngine) | AGPL-3.0 | 215 | 2026-11-20 | LLM-backed local MT, LibreTranslate-compatible |
| DeepTrans Studio | [hint-lab/deeptrans-studio](https://github.com/hint-lab/deeptrans-studio) | MIT | 173 | 2026-07-26 | Multi-agent platform aimed at professional localization |
| argos-train | [argosopentech/argos-train](https://github.com/argosopentech/argos-train) | MIT | 158 | 2026-06-26 | Route to a client-owned, domain-tuned engine |
| BasicCAT | [xulihang/BasicCAT](https://github.com/xulihang/BasicCAT) | GPL-2.0 | 141 | 2026-04-14 | Open CAT tool |
| ImageTrans docs | [xulihang/ImageTrans-docs](https://github.com/xulihang/ImageTrans-docs) | ❌ **no grant** | 128 | 2026-11-21 | Docs for an image-CAT tool, same APAC ecosystem. 10 licence filenames probed on both branches with a passing control (`README.md` master=200) — **genuinely unlicensed, so default copyright: all rights reserved.** |
| Swordfish | [maxprograms-com/Swordfish](https://github.com/maxprograms-com/Swordfish) | EPL-1.0 | 101 | 2026-11-07 | Standards-based CAT (XLIFF/TMX/TBX) |
| Lokalize | [KDE/lokalize](https://github.com/KDE/lokalize) | GPL-2.0-or-later | 32 | 2026-11-26 | Pushed the day of this pass. GitHub reports *no* licence and is **wrong** — REUSE layout. |
| Silhouette | [xulihang/Silhouette](https://github.com/xulihang/Silhouette) | GPL-3.0 | 23 | 2026-08-30 | The only CAT tool found for **audio and video** |
| Game Localization QA | [memolyviza2012-max/game-localization-qa](https://github.com/memolyviza2012-max/game-localization-qa) | MIT | 9 | 2026-10-16 | A written QA protocol, not a library |

### The law, measured inside one discipline — the tightest control case in this KB

Split "translation quality" by **who has to agree on the number**. Licence is not the variable (all
four are Apache-2.0 or MIT); only the nature of the judgment is.

- **Computable from text** → `mjpost/sacrebleu` (Apache-2.0, 1,266★, 2026-08-20) + `Unbabel/COMET`
  (Apache-2.0, 792★, 2026-04-21) = **2,058★, alive.**
- **Predicted without a reference** → `Unbabel/OpenKiwi` (AGPL-3.0, 236★) **dead since 2022-06-23**;
  `NJUNLP/njuqe` (MIT, 12★).
- **Contractual — the MQM typology real localization SLAs are written against** →
  `BYU-TRG-Team/mqm-scorecard` + `-api`, both Apache-2.0, **1★ each**, both last pushed 2025-06-11.

**≈1,000:1 inside a single discipline.** The scarce thing is never the computation; it is the
agreement.

### Two licence findings, both generalisable to all twelve industries

**1. `NOASSERTION` is four different things.** Four platforms carry the identical GitHub label and
four genuinely different regimes — read on 2026-11-26: `tolgee/tolgee-platform` (4,164★) is
**Apache-2.0 by default** with only `ee/` and `/webapp/src/ee` carved out, i.e. *more* usable than
its badge; `txty-io/texterify` (203★) is **BSL 1.1 with Additional Use Grant: None** and is
effectively proprietary; `serge-community/serge` (228★) grants "the same terms as Perl 5.10.0";
`dlsandy/Transub` (222★) says "MIT License **(Core)**". **The label is an instruction to open the
file, never a verdict** — it cleared one of these and disqualified another.

**2. The prompts can be the proprietary asset while the code is MIT.** Transub's LICENSE, verbatim:
*"Transub Pro algorithms, prompts, and the closed module shipped as `_advanced/` are NOT licensed
under MIT."* Every source file scans MIT, an SBOM reports clean, and the thing that makes the tool
work is withheld. Pass 12 found a licence belonging to the *compilation*; this is a licence excluding
the *artefacts the code loads*. **Rule: grep LICENSE and NOTICE for `prompt`, `model`, `weights`,
`Pro` before trusting any AI-era repo's badge.**

### Method corrections recorded this pass

- ⚠️ **`gh api repos/<slug>` is not an existence oracle in this environment.** It returned
  `Not Found` for **all eleven** well-known repos tested, including `WeblateOrg/weblate` — which
  `search/repositories` simultaneously reported at 6,185★. The endpoint is scoped to the session's
  own repositories, so its 404 carries **no information**. A pass trusting it would have deleted
  Weblate, Pontoon, LibreTranslate and COMET as dead links. Use `git ls-remote` for existence and
  `search/repositories q=repo:<slug>` for metadata.
- **The licence probe needs a fourth location: `LICENSES/<SPDX-ID>.txt` (the REUSE spec).**
  `KDE/lokalize` carries `LICENSES/GPL-2.0-or-later.txt` (17,277 B) and the API reports it
  unlicensed. The control request confirmed the channel was fine (`README.md` on `master` = 200,
  `main` = 404) — only the filenames were wrong. REUSE is an FSFE standard, so this
  under-reports **European** projects specifically.
- **Name collisions here are high-star and plausible, which is worse than pass 8's zero-relevant
  cases:** `localization platform` → rank 1 is `cartographer-project/cartographer` (8,021★, robotics
  SLAM); `translation memory` → rank 2 is `dlbeer/dhara` (508★, a NAND **flash** translation layer);
  `omegat` → rank 1 is a piracy megathread list (392★). Read descriptions, never counts.
- **Two incumbents are not on GitHub at all**, so no GitHub-shaped sweep can see them: the **Okapi
  Framework** (Bitbucket) and **OmegaT** (SourceForge). This blind spot is shaped like *mature,
  pre-2010, standards-implementing open source* and it affects all twelve industries in this rotation.
- **The four mandated generic global searches returned nothing media-specific** — general agent
  roundups (OpenHands, browser-use, DeerFlow) and vendor outlook PDFs. Recorded so the silence is not
  read as coverage. Generic industry queries have saturated for media; value now comes from naming an
  unexamined plane and measuring it.

## 2026-11-26 — pass 13: the subscription, entitlement & reader-revenue plane (the licence hardens toward the money)

### Headline: the thirteenth consecutive near-zero agent layer, and the cleanest licence gradient yet

Measured the subscriber half of media revenue — identity, entitlement, billing, dunning, churn and the
publisher's conversion funnel. Pass 2 covered the advertising half; this had no row anywhere in the KB.

**Agent-layer probe (`search/repositories`, 2026-11-26):**

| Query | Total | Top result >200★ |
|---|---|---|
| `billing agent` | 2,869 | `Fosowl/agenticSeek` (27,701★) — general assistant |
| `subscription agent` | 2,687 | `ParadevAI/Paradev` (16,696★) — coding agent |
| `revenue agent` | 3,230 | `claude-ops` (563★) — devops |
| `churn agent` | 764 | a coursework repo (228★) |
| **`dunning agent`** | **57** | **none** |
| `subscriber retention AI` | 28 | none |

The generic terms are contaminated by general-purpose agents; `dunning` — unambiguous industry
vocabulary — is a clean zero. Thirteen planes, thirteen near-zeros.

### The gradient — new this pass, and ordered by distance from the recurring charge

| Layer | Licence shape | Evidence |
|---|---|---|
| Identity | Apache-2.0, large | Keycloak 38,060★ |
| Entitlement | Apache-2.0, crowded | SpiceDB 7,243★, OpenFGA 6,197★, Cerbos 4,669★ |
| Billing | **AGPL-dominant** | Lago 10,922★, flexprice 6,874★, Meteroid 1,370★ — vs Kill Bill 5,869★ Apache-2.0 |
| Reader revenue | **one MIT repo, 138★** | REMP, and nothing else |

Authorization is infrastructure and gets given away; the recurring charge is the business and gets
protected. Monotone, no counterexample.

### New this pass, verified 2026-11-26 (`git ls-remote` 33/33)

- **Kill Bill** [killbill/killbill](https://github.com/killbill/killbill) — Apache-2.0, 5,869★,
  pushed today. The only mature permissive billing engine in the plane.
- **SpiceDB** [authzed/spicedb](https://github.com/authzed/spicedb) — Apache-2.0, 7,243★. Best fit
  for territory/device/windowing entitlement graphs.
- **Hyperswitch** [juspay/hyperswitch](https://github.com/juspay/hyperswitch) — Apache-2.0, 45,917★.
  Largest permissive project in the plane; APAC-origin (Juspay, India).
- **REMP** [remp2020/remp](https://github.com/remp2020/remp) — MIT, 138★. The only open
  reader-revenue platform that exists. EMEA-origin (Denník N, Slovakia).
- **lifelines** [CamDavidsonPilon/lifelines](https://github.com/CamDavidsonPilon/lifelines) — MIT,
  2,623★. Survival analysis; the honest basis for tenure/churn modelling.

### ⚠️ The contamination finding: `paywall` is adversarial, not merely noisy

`topic:paywall` top ten by stars are **ten out of ten circumvention tools**, totalling **21,592
stars**. The one publisher-side implementation in the same measurement (REMP) has **138**. Ratio
≈ **156 : 1 against the business model**. `topic:reader-revenue` returns **zero repositories**.

Regional edge worth carrying into a pitch: the two largest non-English bypass projects target the
**Brazilian** press (`marreta` 1,229★, `burlesco` 948★) and the third targets the **German** press
(`bibbot` 656★).

### ⚙️ Method corrections — both reusable across all twelve industries

1. **The `repo:` 422 is not only a rename detector.** `casbin/casbin` resolves via `git ls-remote`,
   serves an Apache-2.0 LICENSE, and its org siblings are searchable — yet `repo:casbin/casbin`
   returns 422. A live public repo can be **absent from the search index while present on GitHub**.
   Its stars/push date are therefore *not measurable*, recorded as `n/m` rather than inherited.
2. **`curl -sI https://github.com/...` is a broken oracle here.** All 33 URLs returned a uniform
   **403** to HTTP HEAD through the egress proxy, including repos that plainly exist. `git ls-remote`
   returned 33/33 OK on the same list. Verify with `ls-remote`, never with HEAD.

## 2026-11-26 — pass 12: the sound, music & immersive-audio plane (the law gets a mechanism)

### How the gap was found — the vocabulary probe, two Bash calls, 95 terms

Seventh consecutive step-5 failure on this industry: the remote already held passes 8-11, four of
them dated today, while `rotation.json` still read `next=4, last_industry=healthcare`. Probe first,
web second.

| Term group | Hits across the 8 files | Verdict |
|---|---|---|
| `spatial audio`, `Atmos`, `binaural`, `ambisonic`, `object-based audio`, `next-generation audio` | **0** | Immersive audio absent |
| `Ardour`, `Audacity`, `JUCE`, `SuperCollider`, `Csound`, `Faust`, `Pure Data`, `DAW`, `Zrythm`, `LMMS` | **0** | The authoring/host layer absent |
| `MuseScore`, `LilyPond`, `music21`, `Verovio`, `VexFlow`, `MusicXML`, `music notation` | **0** | The music layer absent |
| `Spleeter`, `Magenta`, `Basic Pitch`, `RNNoise`, `DeepFilterNet`, `foley`, `dialogue edit`, `audio post` | **0** | Restoration & MIR absent |
| `loudness` 39 · `pyannote` 19 · `ebur128` 14 · `Essentia` 11 · `librosa` 10 | present | **Covered already** — measurement (p4), identification (p5), diarisation (p7) |

The KB could measure, identify and generate audio. It could not **author** it.

### The headline: the licence hardens by *where the code runs*, and this time with a mechanism

Eleven planes established *that* openness collapses at the platform tier. This one establishes *why*.
Sorted by whose process the code executes inside, with no counterexample in either direction:

| Layer | Runs… | Licence outcome | Count |
|---|---|---|---|
| Reference implementations (`ebu/bear`, `libadm`, `libbw64`, `ebu_adm_renderer`, `ADM-OSC`, `omnitone`, `JSAmbisonics`) | *beside* the host | Apache-2.0 / BSD / MIT | **7/7 permissive** |
| Plugins & plugin frameworks (`JUCE`, `tracktion_engine`, `libspatialaudio`, `Spatial_Audio_Framework`, `ear-production-suite`, `zrythm`) | *inside* a proprietary DAW | AGPL/GPL/LGPL **or paid commercial** | **6/6 dual or copyleft** |
| Models & corpora (`madmom` weights, `fish-speech`) | — | Non-commercial / revenue-capped | restricted |
| Agents | — | `audio post production agent` = **6 results on all of GitHub**, top-6 star sum **7** | **twelfth consecutive near-zero** |

> Dual licensing in this plane is not ideology, it is the business model of **selling an exception to
> people shipping closed plugins.** Consequence for delivery: a renderer or analysis service is clean;
> a plugin inside the client's Pro Tools rig puts AGPL or a commercial fee under the deliverable.

### ⛔ The licence finding of this pass: permissive repo, non-commercial weights, one file

`CPJKU/madmom` (1,745★), the standard beat/downbeat/tempo library in MIR, has **one** `LICENSE` file
that splits by file extension: source (`.py`, `.pyx`, `.c`) BSD-3; **data and models (`.npy`, `.h5`,
`.pkl`) CC BY-NC-SA 4.0**, the text naming *"pickled Processors (i.e. saved models)"* explicitly and
directing commercial users to contact JKU. madmom without its models tracks nothing, so **the
permissive repo badge is true and useless** — and no repo-level licence scanner can see the split,
because it is inside the licence file's prose. Third confirmation of pass 9's "licence in the
weights", first instance found *within a single file*.

### ⛔ The Globant-specific clause of the pass: a licence that turns on the delivery model

`fishaudio/fish-speech` (**33,872★** — the biggest repo in the plane, reported by GitHub as
`NOASSERTION`) ships the **Fish Audio Community License Agreement v1.0**, dated 2026-10-13.
Commercial use is free only under **USD 500,000 annual revenue**, and Section III(a) addresses our
exact business:

- Deploying it *"as a contractor, integrator, consultant, or on-premises vendor"* is licensed **only
  if the client's revenue is also under USD 500k** → an enterprise on-prem delivery is **unlicensed**.
- Delivering *only output* — *"as an agency, studio, or freelancer producing voiceovers, dubbing, or
  audiobooks"* — is **explicitly carved out and permitted**.
- Any **Hosted Service** (self-serve TTS/voice-cloning API) needs a separate written agreement
  **regardless of revenue**.

Same software, same studio: **the licence turns on whether you hand over the model or the mix.**

### New agents verified this pass

| Agent | Repo | License | Stars | Push |
|---|---|---|---|---|
| sherpa-onnx | k2-fsa/sherpa-onnx | Apache-2.0 | 16,241 | 2026-11-24 |
| YuE | multimodal-art-projection/YuE | Apache-2.0 | 13,742 | 2026-11-01 |
| speechbrain | speechbrain/speechbrain | Apache-2.0 | 11,951 | 2026-11-25 |
| DeepFilterNet | Rikorose/DeepFilterNet | MIT **or** Apache-2.0 | 5,107 | 2026-11-06 |
| ACE-Step | ace-step/ACE-Step | Apache-2.0 | 5,113 | 2026-02-15 |
| ClearerVoice-Studio | modelscope/ClearerVoice-Studio | Apache-2.0 | 4,659 | 2025-08-14 |
| stable-audio-tools | Stability-AI/stable-audio-tools | MIT | 3,920 | 2026-11-01 |
| spleeter | deezer/spleeter | MIT | 28,539 | 2026-10-28 |
| matchering | sergree/matchering | GPL-3.0 | 2,741 | 2026-10-07 |
| asteroid | asteroid-team/asteroid | MIT | 2,605 | 2026-11-03 |

Archived-but-cited: `magenta` (Apache-2.0, 19,781★, archived 2026-01-06) and `demucs` (MIT, 10,425★,
archived 2024-04-24). Both are quality leaders and neither is a safe dependency.

### ⚙️ Method corrections, reusable across all twelve industries

1. **A batched `repo:` search query dies whole on one bad name.** `repo:a/b repo:c/d` is an efficient
   way to probe ten repos in one call — until one name is wrong, when GitHub returns
   `422 Validation Failed` and **the valid repos in the batch return nothing.** It fails silently in
   the direction of "nothing found". Hit twice this pass. **Rule: on a 422, re-probe the batch
   one repo at a time** — never record the batch as empty.
2. **A 422 is not automatically a rename.** Earlier passes read `422` as a rename detector. In two of
   three cases this pass it was **my own wrong owner** — `videolabs/libspatialaudio` does not exist;
   the repo is **`videolan/libspatialaudio`** (325★, LGPL-2.1+ or commercial). **Rule: before calling
   a 422 a rename, search the bare repo name.**
3. **The github.com HTML channel carries no signal in this environment.** `curl -sI
   https://github.com/<owner>/<repo>` returned **403 for every repo tried, including ones that exist
   and are indexed.** The proxy, not the repo, produces that status. Only `git ls-remote` (git
   protocol) and the search API are usable oracles here. **Never read a 403 as "gone".**
4. **A NINTH way a licence hides, and the root probe is structurally blind to it: the licence file is
   not at the repository root.** `ebu/ear-production-suite` returns **404 for all ten conventional
   licence filenames at the root** while `README.md` returns 200 — the control that earlier passes
   established as proof the filenames are not at fault. The file is real and it is at
   **`packaging/LICENSE.md`**, 110,524 B, GPL-3.0-or-later, BBC/EBU/IRT. Found with **one**
   `search/code` call: `repo:<r> filename:LICENSE`. **Rule: when the root probe comes back empty on
   all names and README is 200, the next call is a code search, not a clone.**
5. **`NOASSERTION` has a diagnosable cause, and in this plane it is usually "a clause was added".**
   19 of 59 repos came back `NOASSERTION`, and every one resolved on reading the file:
   `MuseScore` = **GPL-3.0 with a font exception** (the exception defeats the classifier);
   `sonic-pi` = **MIT main source that links GPLv3 code**, so the distribution obligation is GPLv3
   despite the MIT headline; `Ardour` = GPL-2.0 in `COPYING`; `faust` = GPL-2.0 + exception in
   `COPYING.txt`; `pure-data` = "Standard Improved BSD"; `opus` = BSD-3; `zrythm` = AGPL-3.0 plus §7
   additional terms, declared by **REUSE pointer** (`LICENSES/LicenseRef-ZrythmLicense.txt`) rather
   than inline. **`NOASSERTION` is a signal to read, not a verdict of "unknown".**

### Licence traps found this pass

| Repo | Reported | Actually | Why it matters |
|---|---|---|---|
| juce-framework/JUCE | `NOASSERTION` | **AGPL-3.0 or commercial JUCE 9 EULA** | The default plugin framework for the industry. AGPL on a client plugin is usually a blocker |
| CPJKU/madmom | `NOASSERTION` | BSD code / **CC BY-NC-SA models** | Unusable commercially as shipped |
| fishaudio/fish-speech | `NOASSERTION` | Revenue-capped bespoke licence | See above |
| leomccormack/Spatial_Audio_Framework | `NOASSERTION` | **ISC by default, GPL-2.0 once optional modules are enabled** | **Second instance of pass 5's "licence decided by your build"** (Chromaprint was the first) — so it is a category, not an anecdote |
| videolan/libspatialaudio | `NOASSERTION` | **LGPL-2.1+ or commercial** | |
| Tracktion/tracktion_engine | `NOASSERTION` | **GPL-3.0 or commercial** | |
| sonic-pi-net/sonic-pi | `NOASSERTION` | MIT source, **GPLv3 by linkage** | The inverse of the usual trap: permissive file, copyleft outcome |

### ⚠️ Contamination — audio vocabulary is almost entirely homonymous with agent vocabulary

`music supervision AI` → **#1 is a customer-support multi-agent repo (27★)**, and rank 5 is the
LangGraph **supervisor** pattern: one word colliding twice in one result set. `dialogue editing AI` →
#1 is `ludo-npc-ai` (104★), NPC chat, because *dialogue* means conversation to AI and production
sound to post. `sound design agent LLM` → #1 is a 3D-animation skill (83★). `spatial audio agent` →
per-app config helpers. And rank 3 of `dialogue editing AI` is a **pirated-commercial-software lure**
(`...SpectraLayers-Pro-13-Free-AI-Audio-Editing`, 9★, no licence). **This plane's queries surface
warez dressed as tooling — open the repo before you clone it.**

### Informed gaps — searched and genuinely not found

- **No open MPEG-H authoring/encoder.** ATSC 3.0's 2026 suite (approved 2026-04-14) standardises
  MPEG-H audio; the open stack is ADM/EAR-based and the encoder side is Fraunhofer's. Largest supply
  gap in the plane, sitting under a live North American deadline.
- **No open loudness-compliant mixing agent** — measurement solved (p4), remediation unbuilt.
- **No open music clearance / cue-sheet tooling** — consistent with p5's music-royalty zero.
- **IEM Plugin Suite is not canonically on GitHub.** It lives on `git.iem.at`, unreachable through
  this proxy (uniform `000`); GitHub has only forks, largest `tu-studio/IEMPluginSuite` 12★ GPL-3.0.
  Recorded as unverifiable from here, **not** as absent.

## 2026-11-26 — pass 11: the description & semantic-interchange plane (the law's control case)

### How the gap was found — the vocabulary probe, now at two calls and 110 terms

`media-kb` arrived with the remote **already carrying pass 10 from today** and `rotation.json` still
reading `next=4, last_industry=healthcare` — **the sixth consecutive failure of step 5 on this same
industry.** Pass 8's corollary applied again: same-day passes on the remote mean the correct move is
neither a rewrite nor a re-verification but **finding the missing vocabulary plane**. Two Bash calls,
110 candidate terms, before any web search:

| Term group | Files | Hits | Verdict |
|---|---|---|---|
| `IPTC`, `NewsML`, `ninjs`, `NITF`, `EBUCore`, `PBCore`, `Dublin Core`, `schema.org`, `metadata schema` | 0 | **0** | Interchange schemas absent |
| `SKOS`, `thesaurus`, `controlled vocabulary`, `authority control`, `cataloguing` | 0 | **0** | Vocabulary layer absent |
| `Wikidata`, `named entity`, `entity linking`, `knowledge graph`, `semantic search`, `ontolog*` | 0 | **0** | Linking layer absent |
| `OAI-PMH`, `IIIF`, `Omeka`, `DSpace`, `CollectiveAccess`, `Dataverse`, `XMP`, `exiftool`, `syndication` | 0 | **0** | Exposure + description substrate absent |
| `Sofie` 165 · `C2PA` 64 · `MARC`/`AtoM`/`ArchivesSpace` 15-28 | 4-8 | high | **Already covered** — playout (p8), provenance (p9), repositories (p4). The *description* layer between them was the hole |

The KB could identify (p5), prove (p9), preserve (p4) and play out (p8) an asset. It could not
**describe, catalogue or syndicate** one — the bottleneck under every archive-AI engagement.

### The headline: the first plane where the content is openly licensed, and it is still not built

Primary evidence, from IPTC's own repository files rather than a vendor page:
`iptc/sports-newscodes/master/LICENSE` (444 B) — *"The Creative Commons Attribution (CC BY) 4.0
license applies to **all NewsCodes**"*; `iptc/newsml-g2/master/LICENSE` (901 B) — *"Adapt — remix,
transform, and build upon the material for any purpose, **even commercially**."*

Prediction: a healthy plane. Measurement: **a three-step gradient.**

| Layer | State | Evidence |
|---|---|---|
| **DESCRIBE** (format) | **HEALTHY** | schema.org 6320★ Apache-2.0 · ninjs MIT 47★ · EBUCorePlus MIT · Skosmos MIT 269★ · TemaTres 142★ · **IPTC pushed six repos in Nov 2026**, `video-metadata-hub` the day before this pass |
| **ASSIGN** (judgment) | **ONE REPO DEEP** | **Annif**, 280★, Apache-2.0, from the National Library of Finland. `subject indexing` = 257 results and ranks 2-6 are `OK-`, `sahabatfb`, `Aim`, `Theme`, `DAWD` — unlicensed 2014-2022 noise |
| **AGENTIC** (judgment at scale) | **PAPERS, NOT CODE** | arXiv 2504.05711, 2605.16338 · `archival metadata LLM agent` = 8 results, **top-6 star sum 3** · `vidya archival metadata` = **0** · only live repo is ICAEW's, **3★ and unlicensed** |

**The refinement — the sharpest the structural law has had.** Inside one organisation:
`NatLibFi/Annif` is **Apache-2.0**; `NatLibFi/Annif-corpora`, the labelled training data **without
which Annif assigns nothing**, has **no licence file** (control `README.md` on `master` = 200, so the
filenames are not at fault). `NatLibFi/Finto-data` is explicitly mixed — code under `tools/` MIT,
data varies.

> An open licence on the schema buys the **format**. It does not buy the **judgment**, because
> judgment trains on annotated records — and those are the asset an institution keeps. When the
> schema is finally granted, the withheld layer does not vanish; it **moves down to the corpus.**

### New agents verified this pass

| Agent | Repo | License | Stars | Push |
|---|---|---|---|---|
| spaCy | `explosion/spaCy` | MIT | 34094★ | 2026-11-21 |
| flair | `flairNLP/flair` | MIT (`LICENSE` 1166 B, Zalando) | 14400★ | 2026-10-19 |
| GLiNER | `urchade/GLiNER` | Apache-2.0 | 4296★ | 2026-11-11 |
| inaSpeechSegmenter | `ina-foss/inaSpeechSegmenter` | MIT | 919★ | 2026-03-12 |
| **Annif** | `NatLibFi/Annif` | Apache-2.0 (`LICENSE.txt` 606 B) | 280★ | 2026-11-24 |
| OpenTapioca | `opentapioca/opentapioca` | Apache-2.0 | 263★ | 2026-08-26 |
| spacyopentapioca | `UB-Mannheim/spacyopentapioca` | MIT | 96★ | 2026-02-05 |

**`wetneb/opentapioca` would have been a 404** — the project moved to its own org. Verify slugs, not
remembered paths.

### Method corrections, reusable across all twelve industries

**(1) `curl` is not an existence oracle in this session, and a 403 is not a 404.** The task
instructions mandate `curl -sI` verification. Run over this pass's 60 URLs, curl returned **403 for
all 52 GitHub URLs and `000` for every non-GitHub domain — exactly one 200 in 60.** All 52 repos
exist: `git ls-remote --exit-code` confirms **52/52, zero dead.** A pass that trusted curl would have
discarded its entire findings list as dead links. The 403 is the agent proxy refusing github.com
HTML; the `000` is a blocked domain.

**(2) `search/repositories` is not a complete existence oracle either — the converse.**
`Islandora/islandora` is **absent from the search index** (`islandora in:name` → 1317 results without
it) while `ls-remote` confirms it exists and raw returns its `LICENSE` (GPL-2.0, 18092 B).
**Search for metrics, `ls-remote` for existence.**

**(3) The control request needs lowercase `readme.md`.** TemaTres 404'd on every licence name *and*
on `README.md` on both branches — which by pass 8's rule means wrong filenames, not a missing
licence. A shallow clone settled it in one call: the file is **`readme.md`**, and the GPL-2.0-or-later
grant lives in it and in every source header, with **no licence file at all.**

**(4) Read the results, not the total — now with a fourth failure mode.** `automated cataloguing`
(203 results) tops out at **a penetration-testing tool** (`chrismaddalena/ODIN`, 670★, archived);
`metadata enrichment` (1043 results) tops out at a **Kubernetes fluentd plugin**. Four of seven
queries this pass were false friends or false abundance — the `eidr`/`isan` trap of pass 8, repeated.

### Licence traps found

- **`ebu/ebucore` is CC BY-NC-SA 3.0 — NonCommercial**, while successor `ebu/ebucoreplus` is **MIT**.
  The *installed* generation of the EBU's metadata standard is the commercially unusable one.
  Second predecessor/successor licence split in this KB → treat as a pattern (new Pattern 32).
- **Three of IPTC's twenty public repos have no licence file** — `sport-schema` (38★),
  `rightsml-dev`, `json-for-concepts-vocabularies` — inside an org that licenses its flagship
  standards CC BY 4.0. **Openness at org level does not propagate to repo level.**
- `icaew-digital-archive/metadata-extraction`: live LLM→Dublin Core cataloguing, pushed 2026-11-24,
  **unlicensed**. Reference, not dependency.

### Informed gaps — searched and genuinely not found

**VocBench 3** (BSD-3 per the EU SEMIC catalogue, the system that managed **EuroVoc**) has **no
canonical GitHub repo** — only third-party Dockerfiles at 1-4★. **ShowVoc**: no meaningful GitHub
presence (top hit 0★). **pymarc** is **archived** at `edsu/pymarc` (last push 2020-02-03); live at
`gitlab.com/pymarc/pymarc` — the one URL of 60 that curl could reach. **No open system does IIIF
delivery *and* OAI-PMH out of the box.** **`iptc.org` and `cv.iptc.org` do not resolve from this
session** (outside allowed network domains, as `new.ddex.net` was in pass 8), so Media Topics' ~1,100
term count and 2-3 month cadence are **secondary-sourced and internally inconsistent** across IPTC's
own pages — treat the cadence as unverified; the licence family is primary-sourced from the repos.

## 2026-11-26 — pass 10: the theatrical & digital-cinema plane (six literal zeros)

### How the gap was found — the vocabulary probe, now confirmed as the cheapest tool in this workflow

`media-kb` arrived at this pass with **four passes never recorded in `rotation.json`** (passes 6 and
7 on 2026-11-25, passes 8 and 9 on 2026-11-26) and the remote already carrying two commits from
today. Pass 8's corollary applies exactly: when the remote has same-day passes, the correct pass is
neither a rewrite nor a re-verification but **finding the missing vocabulary plane**. One grep of 51
candidate terms against the eight files, before a single web search, produced the answer:

| Term | Files | Hits | Verdict |
|---|---|---|---|
| `digital cinema`, `asdcplib`, `dcp-o-matic`, `KDM`, `box office`, `theatrical`, `SMPTE ST 429`, `projector`, `TMS` | 0 | **0** | The plane is absent |
| `DCP` | 4 | 4 | **False positive — all four are `HDCP`** (pass 8's copy protection) |
| `cinema` | 6 | 20 | **False positive — OpenEXR, plus Brazilian/Mexican statute prose** |
| `OpenJPEG`, `MXF`, `JPEG 2000`, `ST 2067`, `asdcp` | 0 | **0** | The substrate is absent too |

Cost: one Bash call. **And the probe must check its own hits** — `DCP` looked like 4 hits of
coverage and was 4 hits of `HDCP`. A term-count probe that does not read its matches manufactures
false coverage exactly as fast as it finds real gaps.

### The headline: the tenth consecutive near-zero agent layer, and the first with *six literal zeros*

`DCP automation agent`, `theatrical distribution automation`, `digital cinema LLM`,
`subtitle cinema DCP agent`, `SMPTE DCP interop`, `preshow advertising cinema`,
`cinema exhibitor data` and `movie theater point of sale open source` **all return zero results.**
`projection automation cinema` returns one: a Minecraft mod, 0★. Against a channel worth **$34.6bn
in 2025 box office** (Futuresource; Gower Street forecasts ~$34.55bn for 2026).

### ⛔ The finding of this pass: the first plane in this KB that is copyleft end to end

Every authoring tool, validator and key manager in the theatrical chain is GPL-2.0, GPL-3.0 or
AGPL-3.0. The only permissive licences sit in the substrate (`openjpeg` BSD-2, `asdcplib` BSD-3) and
in **exactly one validator** (`ClairMeta` BSD-3). This inverts trend 4 ("permissive at the pipeline,
copyleft at the platform") — here the *pipeline* is the copyleft part. Consequence, stated plainly
for engagement planning: **a proprietary client deliverable cannot be built on the DCP authoring
chain.** Validation can. Full reasoning and the escape route in `repos/foundations.md`.

### ⛔ Two new ways a licence hides — and the second one reverses this KB's own default

Ways nine and ten for this KB, both verified by reading the bytes:

- **The licence file is named after the licence.** `wolfgangw/backports` (`dcp_inspect`, 40★, active)
  carries **`gpl.txt`** — 32,473B of GNU GPL **v3** — and no `LICENSE`, `LICENCE` or `COPYING`.
  Fourteen filenames across two branches missed it; GitHub reports `NONE`. **I had this recorded as
  "unlicensed" before a shallow clone corrected it.**
- **The licence can live only in the source headers.** `cth103/libsub` (9★) has nothing licence-shaped
  at root, and **73 source files carrying a full GPL-2.0-or-later header.**

**Together these fix a rule this KB had half-right.** Pass 8 established that a 404 is never by
itself proof a licence is missing. Pass 5 established that `rslstandard/rsl`, with no licence file,
is all-rights-reserved by default. Put side by side: `rsl` = no file, no headers → default copyright;
`libsub` = no file, 73 headers → GPL-2.0+. **Absence of a licence file is evidence of *neither*
answer.** The resolving step is reading the source, and it costs one shallow clone — which also
caught `gpl.txt` in the same call. Use it before writing either "unlicensed" or "no licence found".

### ⚙️ Method correction: the 422 "rename detector" is real but does not self-diagnose

Passes 8 and 9 recorded a `repo:<slug>` 422 + successful `ls-remote` as a rename detector. It fired
twice this pass and was right twice (`Ymagis/ClairMeta` → `ClairMeta/ClairMeta`; `bbc/libMXF` →
`BBC-archive/libMXF`). **The correction is to the follow-up:** `gh api repos/<slug>` returns
`403 "GitHub access to this repository is not enabled for this session"` for *both* cases, which
reads like a session-permissions problem and is not one. Do not conclude "out of scope" from it. The
resolver is an **unqualified keyword search** (`q='libMXF'`), which returned the new location and its
forks in one call. New corollary: if the new owner is an `*-archive` org, **the move is the finding.**

### ⚠️ Contamination — the sharpest false friend measured in this KB, and an abundance trap beside it

`cinema AI agent`: **205 results, 526 stars in the top six, zero relevance.** Every hit is
generative-video prompt styling — a ComfyUI studio (262★ MIT), an agent skill for *website* design
(119★ MIT), three "cinematic look" prompt skills. **In open source "cinema" means "cinematic", never
"movie theatre".** Worse than pass 7's false friend because these results are numerous, well-starred,
permissive and actively maintained: every property a careless pass uses as a quality signal.

`cinema ticketing platform`: **350 results**, top five 12★/6★/6★/4★/4★, all student CRUD. This is
pass 8's lesson again — shortening a query can convert a false zero into a **false abundance**. Read
the results, never the total.

### The real estate, in one table

| Layer | What exists | Licence shape |
|---|---|---|
| Authoring | `dcpomatic` 175★ (pushed 2 days before this pass), `libdcp` 29★, `opendcp` 134★ **dormant since 2020-04-28** | **All GPL** |
| Validation | `ClairMeta` 106★, `backports`/`dcp_inspect` 40★, `dcpdoctor` 1★ | **BSD-3 / GPL-3 / AGPL-3** |
| Substrate | `openjpeg` 1,123★, `asdcplib` 99★ (active 2026-11-19), `grok` 300★ | **BSD-2 / BSD-3 / AGPL-3** |
| Container | `bmx` 88★ **ARCHIVED**, `regxmllib` 39★ **ARCHIVED 4 days ago**, `BBC-archive/libMXF` 15★ | BSD, and retired |
| Keys (KDM) | 3 repos, **3 stars between them** | AGPL-3 / GPL-3 / none |
| Exhibition (TMS) | `CineTMS` 5★ (APAC, Apache-2.0) and nothing else real | — |

### Informed gaps from this pass

- **No open TMS or cinema playout automation.** One 5★ APAC candidate; everything else is coursework.
- **No open cinema accessibility tooling — under a US federal mandate since December 2016.** One repo,
  **zero stars**. Sharper than pass 3's 56★ audio-description ceiling.
- **No open box-office forecasting.** 103 results, top-6 = 29★, all 2017–2020 coursework, no licences.
- **No open KDM lifecycle management.** Three stars across the whole layer.
- **No open preshow/cinema-advertising stack.** Zero results, against a tracked ad category.
- **`new.isdcf.com` and the UNIC/Omdia screen databases were not reachable or are paywalled**, so
  **2026 country-level screen counts are NOT verified** and are recorded as an informed gap in
  `intel/market.md` rather than estimated. SMPTE's own `DPROVE2` verifier is a member tool, not open
  source — noted so nobody searches for its repo.

---

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

---
industry: media
region: Global
updated: 2026-11-26
---

# 📈 Trending Media Repos — append-only log

> Newest section first; history below is never rewritten.
> Distinct from `agents/trending.md`: this file tracks **infrastructure and platform** repos.
> (Until this pass the two files were byte-identical — that defect is fixed here.)

## 2026-11-26 — pass 20: investigative-journalism & source-protection infrastructure (**40 slugs probed, 40 resolve, 0 absent; 1 rename redirect, 4 licence files read, 2 oracle corrections**)

**Infrastructure recorded this pass** (platform and substrate repos; the agent/skill layer is in
`agents/trending.md`). All values 2026-11-26: stars/licence from `gh api search/repositories`,
**default-branch HEAD by shallow clone**, licence files read where the API returned `NOASSERTION`.

| Repo | Stars | Licence (verified) | Default-branch HEAD | Layer |
|---|---|---|---|---|
| https://github.com/sherlock-project/sherlock | 117,843★ | MIT | 2026-11-26 | OSINT — the plane's control group |
| https://github.com/TryGhost/Ghost | 55,920★ | MIT | 2026-11-26 | Publishing + membership |
| https://github.com/ggml-org/whisper.cpp | 55,542★ | MIT | 2026-11-26 | Transcription substrate |
| https://github.com/m-bain/whisperX | 25,695★ | BSD-2-Clause | 2026-11-21 | Transcription + diarization |
| https://github.com/OpenRefine/OpenRefine | 12,120★ | BSD-3-Clause | 2026-11-24 | Record cleaning/reconciliation |
| https://github.com/simonw/datasette | 11,670★ | Apache-2.0 | 2026-11-26 | Dataset publishing/exploration |
| https://github.com/onionshare/onionshare | 7,247★ | GPL-3.0 (`LICENSE.txt`, 35,285 B) | 2026-11-26 | Anonymous transfer over Tor |
| https://github.com/freedomofpress/dangerzone | 5,858★ | AGPL-3.0 | 2026-11-23 | Untrusted-document disarm |
| https://github.com/exiftool/exiftool | 5,320★ | GPL-3.0 | 2026-11-16 | Metadata forensics |
| https://github.com/freedomofpress/securedrop | 3,897★ | AGPL-3.0 (`LICENSE`, 34,629 B) | 2026-11-24 | Source intake |
| https://github.com/alephdata/aleph | 2,516★ | MIT | **2025-12-19** (`develop`) | Entity investigation — dormant |
| https://github.com/bellingcat/telegram-phone-number-checker | 1,934★ | MIT | 2026-08-17 | OSINT |
| https://github.com/globaleaks/globaleaks-whistleblowing-software | 1,529★ | AGPL-3.0 (`LICENSE`, 41,172 B) | 2026-11-20 (`stable`) | Whistleblowing platform — **canonical name, see rename note** |
| https://github.com/ICIJ/datashare | 784★ | AGPL-3.0 | **2026-11-26** | Self-hosted doc search + NER |
| https://github.com/superdesk/superdesk | 760★ | AGPL-3.0 | 2026-11-26 | Newsroom CMS |
| https://github.com/bellingcat/ShadowFinder | 631★ | MIT | 2026-09-03 | Chronolocation |
| https://github.com/mysociety/alaveteli | 421★ | AGPL-3.0 (`LICENSE.txt`, 36,128 B) | 2026-11-25 | FOI platform (UK) |
| https://github.com/okfde/froide | 413★ | **MIT** | 2026-11-09 | FOI platform (Germany) |
| https://github.com/huridocs/uwazi | 330★ | MIT (`LICENSE`, 1,073 B) | **2026-11-26** | Documentation database |
| https://github.com/alephdata/followthemoney | 311★ | MIT | **2025-06-27** | Aleph ontology — dormant |
| https://github.com/ICIJ/extract | 257★ | MIT | 2026-11-23 | Distributed OCR |
| https://github.com/bellingcat/EDGAR | 219★ | GPL-3.0 | 2025-05-15 | Corporate filings |
| https://github.com/scidsg/hushline | 140★ | AGPL-3.0 | 2026-11-14 | Small-desk tip line |
| https://github.com/meedan/check | 131★ | MIT | 2026-09-23 | Tipline/annotation — **dev environment, not the backend** |
| https://github.com/MuckRock/muckrock | 124★ | AGPL-3.0 | 2026-11-24 | US records requests |
| https://github.com/Horizontal-org/Tella-Android | 118★ | MIT | 2026-11-17 | Offline encrypted field capture |
| https://github.com/freedomofpress/securedrop-client | 59★ | AGPL-3.0 | 2026-11-25 | Journalist workstation (Qubes) |
| https://github.com/MuckRock/documentcloud | 54★ | AGPL-3.0 | 2026-11-24 | Document publication |
| https://github.com/ICIJ/prophecies | 31★ | AGPL-3.0 | 2026-10-15 | Human validation workflow |
| https://github.com/meedan/check-api | 21★ | MIT | 2026-11-24 | **The actual Check backend** |

**THE RENAME, AND WHY IT CORRECTS THIS KB'S ORACLE.** `globaleaks/globaleaks` resolves perfectly on
both the `ls-remote` and raw channels (default branch `stable`) — and it is a redirect. The canonical
repository is `globaleaks/globaleaks-whistleblowing-software`; both HEADs are the identical SHA
`efa0161c40a6ab4b273caf0e19ca828ebb25e7ad`, which is the proof. GitHub honours renames
indefinitely, so **`ls-remote` success proves reachability, never canonical naming**, and the search
index knows only the new name — which is why `repo:globaleaks/globaleaks` returns "resources do not
exist" against a repository that plainly does. Pass 17 recorded 4 repos "reached only via rename
redirect"; this pass adds the detection rule: **an ls-remote success on a name the search index
rejects is a rename to be resolved, not a repo to be written.**

**`pushed_at` IS NOT LIVENESS — the second oracle correction.** `alephdata/aleph` reported
`pushed_at=2026-02-20`; its default branch `develop` last moved **2025-12-19**, and `main` — a stale
release branch — sits at **2025-08-07** (release 4.1.6). `pushed_at` counts a push to *any* ref,
including bot and release branches, so it overstated liveness by six months on the most-recommended
repository in the plane. `multimodal-ai-lab/DEFAME` showed the same gap (`pushed_at` 2026-05-21, HEAD
2025-09-30). **Resolve the default branch and read its last commit; `git clone --depth 1
--single-branch` gives both in one call.** Every HEAD column in this pass was produced that way.

**FOUR LICENCE FILES READ, THREE `NOASSERTION` CAUSES, NONE A MISSING LICENCE.** OnionShare prepends
a third-party-licences note above the GPL-3.0 text; SecureDrop prepends a multi-party copyright
header above the AGPL-3.0 text; Alaveteli ships a multi-licence explainer that resolves to AGPL-3.0;
`buriedsignals/spotlight` appends a methodology-attribution section to an MIT grant (1,940 B). Cycle
8 established that *a 404 on the raw channel is not proof a licence is missing*; this pass adds the
symmetric rule — **a `NOASSERTION` from the API is an instruction to read the file, not a finding.**

**THE DORMANCY, STATED NARROWLY BECAUSE THE WIDE VERSION IS FALSE.** The two **Aleph-family**
permissive repos are stale (`aleph` 2025-12-19; `followthemoney` 2025-06-27, its last commit a revert
of "begin project re-homing") while every AGPL peer is current (Datashare today, DocumentCloud
2026-11-24, Prophecies 2026-10-15). The tempting generalisation — *MIT is the dead licence here* — is
**contradicted by this pass's own table**: Uwazi (MIT) today, `extract` (MIT) 2026-11-23, Tella (MIT)
2026-11-17, Froide (MIT) 2026-11-09, sherlock (MIT) today. The claim holds for the **Aleph family
only**, and matters only because Aleph is what every guide recommends first.

**STAR COUNTS CAME FROM THE SEARCH CHANNEL BECAUSE THE DIRECT API IS SCOPED.** Every
`api.github.com/repos/<third-party>` call in this session returns "GitHub access to this repository
is not enabled for this session", and `github.com` HTML returns **403** — so no star count is
obtainable by the routes earlier passes may have used. `gh api -X GET search/repositories` with
`repo:` qualifiers **does** serve stars, licence and `pushed_at`, in batches. Recording it because a
future pass hitting the blocked API should not conclude the metadata is unobtainable.

**CHANNEL GAP, STATED AS A GAP.** No non-GitHub host resolves from this session — `cnti.org`,
`unlicense.org`, `reutersinstitute.politics.ox.ac.uk`, `latamjournalismreview.org`, `acma.gov.au`,
`securedrop.org`, `globaleaks.org`, `icij.org`, `opensource.org` and `spdx.org` all return curl `000`
/ DNS `ENOTFOUND` (probed, not assumed). **Reusable workaround:** canonical licence texts are
reachable at `raw.githubusercontent.com/spdx/license-list-data/main/text/<SPDX-ID>.txt` — that is how
the modified Unlicense in `agents/trending.md` was proven modified without reaching `unlicense.org`.

## 2026-11-26 — pass 19: sports-media & live-event infrastructure (**~65 slugs recorded, 0 absent; 15 licence-channel investigations, 3 traps and 5 false negatives**)

**Method this pass, and it reverses pass 18's conclusion.** Pass 18 reported the GitHub API
unreachable for out-of-session repositories (`403: sessions are bound to their configured
repositories`) and **dropped every star count as a result**. That 403 applies only to
`repos/{owner}/{repo}/...`. **`search/repositories` with `repo:<slug>` qualifiers works for
arbitrary repositories** — several at once — returning stars, forks, SPDX id and `pushed_at` in one
call. Every figure in this pass came from that endpoint; **25 slugs were additionally confirmed by
`git ls-remote`**, which remains the only true existence oracle. The rest were returned live by the
search endpoint, which only lists extant repositories. **0 absent.**

### The layer this KB had never recorded

A probe of all eight files returned **0 lines** for `YOLO`, `pose estimation`, `mmpose`,
`ultralytics`, `DeepSORT`, `ByteTrack`, `object tracking` and `multi-object`. The detection and
multi-object-tracking substrate — which sports analytics, virtual production, ad verification, trust
& safety and audience measurement all sit on — was missing after eighteen passes. It is now in
`repos/foundations.md`. The headline is a licence fork, not a capability gap:

| Repo | License | Stars | Last push |
|---|---|---|---|
| `ultralytics/ultralytics` (YOLO26/27, the default detector) | ⚠️ **AGPL-3.0** | 63,769 | 2026-11-26 |
| `mikel-brostrom/boxmot` (leading pluggable MOT) | ⚠️ **AGPL-3.0** (`LICENSE`, 34,715 B) | 8,330 | 2026-11-20 |
| `roboflow/supervision` (permissive workhorse) | **MIT** | 51,730 | 2026-11-26 |
| `open-mmlab/mmpose` | **Apache-2.0** | 8,083 | 2025-08-04 |
| `FoundationVision/ByteTrack` | **MIT** | 6,833 | 2024-06-19 |
| `roboflow/trackers` | **Apache-2.0** | 4,022 | 2026-11-25 |
| `tryolabs/norfair` | **BSD-3-Clause** | 2,708 | 2025-04-30 |

The two most-starred libraries in the layer are **both AGPL-3.0**, and a permissive stack of equal
capability exists beside them. For a hosted service this is the difference between owing source code
under §13 and not. `boxmot`'s licence file also states that third-party components keep their own
notices — the **compilation-licence** category cycle 8 found on `chromaprint`, recurring.

### Licence-channel results — 3 traps, 5 false negatives

**Traps** (high stars, nothing shippable), each verified with a README control request proving the
branch resolves, then 10 filenames × 2 branches plus `LICENSE.pdf` and `LICENCE`:

| Repo | Stars | Finding |
|---|---|---|
| `hudl/open-data` | 3,847 | Licence is **`LICENSE.pdf` at repo root** (HTTP 200, `application/octet-stream`). API says `NOASSERTION` — **SPDX detectors read text, not PDFs** |
| `hudl/statsbombpy` | 758 | **No licence file at all.** README defers *data* terms to `doc/LICENSE.pdf` (verified present) behind a registration wall |
| `hudl/StatsBombR` | 314 | `DESCRIPTION` reads **`License: 3.5.0`** — a version number in the licence field |

Also confirmed genuinely unlicensed, with controls passing: `iptc/sport-schema` (38★, IPTC's
SportsML successor, pushed 2026-10-01 — while IPTC's *vocabulary* repo `sports-newscodes` **is**
CC-BY-4.0), `SoccerNet/sn-calibration` (113★), `metrica-sports/sample-data` (515★),
`eddwebster/football_analytics` (2,870★), `linouk23/NBA-Player-Movements` (757★).

**False negatives — the more valuable half.** Five repos reported `NOASSERTION` and **all are MIT**:

| Repo | Evidence |
|---|---|
| `nflverse/nflfastR` (558★) | `LICENSE` 57 B (`YEAR:`/`COPYRIGHT HOLDER:` only) + `LICENSE.md` 1,086 B full MIT + `DESCRIPTION`: `License: MIT + file LICENSE` |
| `sportsdataverse/hoopR` (157★) | `LICENSE` 48 B stub + `LICENSE.md` 1,418 B MIT |
| `sportsdataverse/cfbfastR` (114★) | `LICENSE` 46 B stub + `LICENSE.md` 1,080 B MIT |
| `nflverse/nflreadr` (117★) | `LICENSE` 46 B stub + `LICENSE.md` 1,075 B MIT |
| `HiEventsDev/Hi.Events` (4,201★) | Licence in **`LICENCE`** (British spelling), 35,725 B: **AGPL-3.0 with an additional §7(b) attribution requirement** |

**Two additions to the probe list**, which cycle 8 last extended with lowercase `license.txt` and
`COPYING.md`: **`LICENSE.pdf`** and **`LICENCE`**. And the rule behind the R result: *for any R
package, read `DESCRIPTION`'s `License:` field and `LICENSE.md` before recording `NOASSERTION` —
but read the value, because `StatsBombR` has the same structure with garbage in it.*

### Dormancy ledger for this plane

Permissive, on-topic and **dead** — vendor the code, do not depend on upstream:
`S1M0N38/soccerapi` (MIT, 182★, **2022-12-08** — and it is the most-starred odds library),
`iptc/sportsml-python` (MIT, 2★, **2019-01-25**), `OwlTing/AI_basketball_games_video_editor`
(Apache-2.0, 126★, **2024-08-19**), `lRomul/ball-action-spotting` (MIT, 141★, **2023-07-02**),
`SilvioGiancola/SoccerNetv2-DevKit` (MIT, 231★, **2024-07-08**), `AtomScott/SportsLabKit` (GPL-3.0,
329★, **2023-12-19**), `teijo/jquery-bracket` (MIT, 500★, **2023-07-30**),
`devinpleuler/analytics-handbook` (MIT, 1,720★, **2024-05-26**), `FoundationVision/ByteTrack` (MIT,
6,833★, **2024-06-19**), `open-mmlab/mmpose` (Apache-2.0, 8,083★, **2025-08-04**),
`tryolabs/norfair` (BSD-3, 2,708★, **2025-04-30**).

### Alive and permissive — the short list that matters

`roboflow/supervision` (MIT, 2026-11-26), `roboflow/sports` (MIT, 2026-11-25), `roboflow/trackers`
(Apache-2.0, 2026-11-25), `davidpagnon/Sports2D` (BSD-3, 2026-11-25), `PySport/kloppy` (BSD-3,
2026-11-06), `martineastwood/penaltyblog` (MIT, 2026-11-24), `withqwerty/reep` (CC0-1.0,
2026-08-20), `sportsdataverse/sportsdataverse-py` (MIT, 2026-11-26), and the three MIT esports
parsers `demoinfocs-golang` / `demoparser` / `awpy` (all within four days of this pass).

## 2026-11-26 — pass 18: book & scholarly-publishing infrastructure (**40 slugs probed, 39 resolve, 1 absent; 5 licence files found only off the standard path**)

Method this pass, and it is a change worth noting: **the GitHub API was unavailable**
(`403: sessions are bound to their configured repositories`), so no field here comes from an API.
Existence is `git ls-remote`; licence is **the licence file read from `raw.githubusercontent.com`**;
last-commit date is a `git clone --depth 1 --filter=blob:none --no-checkout` followed by
`git log -1 --format=%cs`. That last trick is **instant** (sub-second per repo, no blobs fetched) and
is the method fix of this pass: *verified last-commit dates without any API access.* Reusable in all
twelve industries.

### The permissive substrate — standards bodies and format consortia

| Repo | Licence (file read) | Last commit | Role |
|---|---|---|---|
| https://github.com/w3c/epubcheck | BSD-3-Clause (`LICENSE.md`) | 2026-11-02 | **The** EPUB conformance checker; the one every retailer runs |
| https://github.com/daisy/ace | MIT (`LICENSE.txt`) | 2026-05-01 | Ace by DAISY — EPUB accessibility checker |
| https://github.com/edrlab/thorium-reader | BSD-3-Clause (`LICENSE`) | 2026-11-26 | Reference desktop EPUB/LCP reader; committed *today* |
| https://github.com/readium/readium-css | BSD-3-Clause (`LICENSE`) | 2026-11-16 | Reading-system CSS; the typography layer |
| https://github.com/readium/r2-shared-js | BSD-3-Clause (`LICENSE`) | 2025-10-28 | Readium 2 shared models. **13 months stale** |
| https://github.com/readium/readium-lcp-server | BSD-3-Clause (`LICENSE.md`) | 2026-06-22 | LCP licence server — the open DRM the EAA does not let you use to disable accessibility |
| https://github.com/futurepress/epub.js | **BSD-2-Clause** (bare `license`) | 2026-03-23 | Browser EPUB renderer. Licence found only at a lowercase extensionless path |
| https://github.com/pagedjs/pagedjs | MIT (`LICENSE.md`) | 2026-10-20 | Paged-media CSS — print/PDF from HTML |
| https://github.com/asciidoctor/asciidoctor | MIT (`LICENSE`) | 2026-11-22 | Text processor and publishing toolchain |
| https://github.com/quarto-dev/quarto-cli | **MIT** (`COPYING.md`) | 2026-11-25 | Scientific publishing toolchain. Licence found only in `COPYING.md` |
| https://github.com/jupyter-book/jupyter-book | BSD-3-Clause (`LICENSE`) | 2026-11-25 | Executable-book builder |
| https://github.com/thoth-pub/thoth | Apache-2.0 (`LICENSE`) | 2026-11-25 | Open-access book metadata management (COPIM, UK) |
| https://github.com/gotson/komga | MIT (`LICENSE`) | 2026-11-24 | Ebook/comic media server — the permissive one of the four |
| https://github.com/daisy/pipeline-ui | MIT (`LICENSE`) | 2026-09-05 | DAISY Pipeline UI |

### The copyleft commons — scholarly platforms, reader tools, libraries

| Repo | Licence (file read) | Last commit | Role |
|---|---|---|---|
| https://github.com/pkp/ojs | GPL-3.0 (`LICENSE`) | 2026-11-26 | Open Journal Systems; 25,000+ journals. Committed *today* |
| https://github.com/pkp/omp | GPL-3.0 (`LICENSE`) | 2026-11-23 | Open Monograph Press — scholarly books |
| https://github.com/pkp/pkp-lib | GPL-3.0 (`LICENSE`) | 2026-11-23 | Shared library under OJS/OMP |
| https://github.com/pressbooks/pressbooks | GPL-3.0 (`LICENSE.md`) | 2026-11-25 | Book publishing on WordPress multisite; PDF/EPUB/web |
| https://github.com/manifoldscholar/manifold | GPL-3.0 (`LICENSE.md`) | 2026-11-19 | Scholarly monograph reading platform |
| https://github.com/pubpub/pubpub | LGPL (`LICENSE`) | 2026-11-24 | Drafting, peer review, journal/book hosting. **LGPL — weak copyleft, the mildest in this group** |
| https://github.com/fiduswriter/fiduswriter | AGPL-3.0 (`LICENSE`) | 2026-11-12 | Collaborative academic writing |
| https://github.com/kovidgoyal/calibre | GPL-3.0 (`LICENSE`) | 2026-11-26 | Ebook library management and conversion. Committed *today* |
| https://github.com/Sigil-Ebook/Sigil | GPL-3.0 (`COPYING.txt`) | 2026-11-25 | WYSIWYG EPUB editor |
| https://github.com/standardebooks/tools | **GPL-3.0 + CC0 1.0 (split)** (`LICENSE.md`) | 2026-11-25 | Production toolset. GPL-3 overall; CC0 only for `./se/data/templates` |
| https://github.com/internetarchive/openlibrary | AGPL-3.0 (`LICENSE`) | 2026-11-26 | Open bibliographic catalogue. Committed *today* |
| https://github.com/aerkalov/ebooklib | **AGPL-3.0** (`LICENSE.txt`) | 2026-11-01 | Python EPUB read/write. **The accidental-copyleft trap of this plane** |
| https://github.com/vivliostyle/vivliostyle.js | AGPL-3.0 (`LICENSE`) | 2026-11-24 | CSS typesetting engine. **APAC-origin (Japan)** |
| https://github.com/koreader/koreader | AGPL-3.0 (`COPYING`) | 2026-11-25 | E-ink reader application |
| https://github.com/janeczku/calibre-web | GPL-3.0 (`LICENSE`) | 2026-11-22 | Web front end over a Calibre library |
| https://github.com/Kareadita/Kavita | GPL-3.0 (`LICENSE`) | 2026-11-22 | Self-hosted reading server |
| https://github.com/rstudio/bookdown | GPL-3.0 (`LICENSE.txt`) | 2026-09-18 | R-based book authoring |
| https://github.com/omeka/Omeka-S | GPL-3.0 (`LICENSE`) | 2026-11-24 | Digital collections publishing |
| https://github.com/daisy/pipeline-modules | LGPL-2.1/3.0 (`LICENSE.txt`) | 2026-10-08 | DAISY Pipeline conversion modules — braille, TTS, DAISY/EPUB |

### ONIX — the book industry's metadata wire format, and it is permissive across the board

| Repo | Licence (file read) | Last commit | Note |
|---|---|---|---|
| https://github.com/titusz/onixcheck | Apache-2.0 (`LICENSE`) | 2026-10-16 | Validates ONIX 2.1/3.0/3.1 against official XML Schema. **Best-maintained validator** |
| https://github.com/zach-m/jonix | Apache-2.0 (`LICENSE`) | 2026-10-17 | Java ONIX extraction. **An aggregator claimed ~763 days stale; it is 5 weeks** |
| https://github.com/chrisribal/onix-parser | MIT (`LICENSE`) | 2026-09-29 | PHP; reads **and writes** ONIX 3.0/3.1, resolves official code lists |
| https://github.com/jaerith/ONIX-Data | Apache-2.0 (`LICENSE`) | 2025-10-14 | C#/.NET ONIX structures. 13 months stale |
| https://github.com/xercode/metadata-onix-lib | MIT (`LICENSE`) | 2021-04-28 | **5½ years stale — do not start here** |

### ⛔ Four slugs that do not survive contact, and one that is not software

| Slug | What the probe returned | Read |
|---|---|---|
| `AIScientists-Dev/AI-Powered-PDF-Accessibility` | Exists; **no licence file** at ten probed paths, while README badge + prose claim MIT | Unusable. A badge is not a grant |
| `daisy/pipeline` | Exists; **no licence file at root** | A `git-subrepo` umbrella, not the licensed artefact. The code is in `pipeline-modules` (LGPL) and `pipeline-ui` (MIT) |
| `phantom-artist/onix-creator` | Exists; no licence file; last commit **2022-05-10** | Not usable |
| `daisy/epub-revision-a11y` | Exists; no licence file; last commit **2015-10-02** | Dead; historical interest only |
| `w3c/publ-epub-revision` | **W3C Software and Document License** | **Documents, not code** — spec text under a document licence. Demoted on sight, per this KB's standing rule |

**39 of 40 slugs resolve.** The one absent slug was a deliberate control (`nonexistent/nope-xyz123`)
used to prove the existence probe can actually fail — without a negative control, "everything
resolved" means nothing.

## 2026-11-26 — pass 17: development & pre-production infrastructure (42 slugs probed, 38 resolve, 4 do not, **4 reached only via rename redirect**)

### The movement is all in the format layer, and it is this week

Last-push dates, measured 2026-11-26:

| Repo | License | Stars | Last push | Note |
|---|---|---|---|---|
| [neopen/story-shot-agent](https://github.com/neopen/story-shot-agent) | **Apache-2.0** | 248★ | **2026-11-26** | Script → shots → video prompts. Pushed on measurement day |
| [leynos/visual-storytelling-skills](https://github.com/leynos/visual-storytelling-skills) | **ISC** | 11★ | **2026-11-26** | Pushed on measurement day |
| [method-production-suite/method-scheduling](https://github.com/method-production-suite/method-scheduling) | **Apache-2.0** | 1★ | 2026-11-21 | Breakdown → stripboard → day-out-of-days. Only Apache licence in the management tier |
| [vilcans/screenplain](https://github.com/vilcans/screenplain) | **MIT** | 187★ | 2026-11-21 | Fountain → PDF/HTML/FDX |
| [rsdoiel/scripttool](https://github.com/rsdoiel/scripttool) | AGPL-3.0 | 46★ | 2026-11-19 | fdx/fadein/osf/fountain conversion |
| [rsdoiel/fountain](https://github.com/rsdoiel/fountain) | AGPL-3.0 | 8★ | 2026-11-19 | Go Fountain package |
| [wildwinter/screenplay-tools](https://github.com/wildwinter/screenplay-tools) | **MIT** | 29★ | 2026-11-18 | C++/JS/Python/C# parse **and write** |
| [nachobust/FilmOrganizer](https://github.com/nachobust/FilmOrganizer) | **MIT** | 1★ | 2026-11-17 | Breakdown + schedule, offline, three platforms |
| [koosoli/OpenShotDesigner](https://github.com/koosoli/OpenShotDesigner) | GPL-3.0 | 47★ | 2026-11-16 | Widest deployable scope in the plane |
| [KKenny0/script-weaver](https://github.com/KKenny0/script-weaver) | ⚠️ none | 11★ | 2026-11-15 | Agent-native screenplay/storyboard |
| [imMamdouhaboammar/motion-graphics-skills](https://github.com/imMamdouhaboammar/motion-graphics-skills) | 🚫 proprietary | 69★ | 2026-11-11 | All rights reserved, stated in LICENSE |
| [lmparppei/Beat](https://github.com/lmparppei/Beat) | GPL-3.0+ | 368★ | 2026-11-02 | macOS screenwriting |
| [opengateapp/opengate](https://github.com/opengateapp/opengate) | GPL-3.0 | 1★ | 2026-11-03 | Full pre-production scope, one star |
| [jtoy/fountainrb](https://github.com/jtoy/fountainrb) | **MIT** | 0★ | 2026-10-27 | Pure-Ruby parser with validation. Active, unnoticed |

**Seven of the fourteen repos above were pushed in the ten days before measurement, and five of them are
permissive.** All five permissive movers are in the *format and story* layer. The management-tier movers
(`method-scheduling`, `FilmOrganizer`, `opengate`, `OpenShotDesigner`) are all at 1–47 stars.

### Dormant or gone — recorded so later passes do not re-discover them

| Repo | Status |
|---|---|
| [nyousefi/Fountain](https://github.com/nyousefi/Fountain) | MIT, 690★ — the format's reference implementation, **no push since 2023-06-10** |
| [dimkanovikov/KITScenarist](https://github.com/dimkanovikov/KITScenarist) | GPL-3.0, 352★ — **ARCHIVED** 2023-08-01 |
| [trelby/trelby](https://github.com/trelby/trelby) | GPL-2.0, 354★ — last push 2025-10-21 |
| [overvale/Textplay](https://github.com/overvale/Textplay) | BSD-3-Clause, 107★ — last push 2019-11-28 |
| [ifrost/afterwriting-labs](https://github.com/ifrost/afterwriting-labs) | 280★ — **no licence file**, last push 2026-01-28 |
| [jtsage/TDTracX](https://github.com/jtsage/TDTracX) | 0★, no licence, **ARCHIVED** 2024-06-25, and it is theatre not film — the only payroll-adjacent artefact found |
| `Falconwing/CineSched`, `nguernse/screenplay-js`, `sunsetsystems/fountain`, `ifrost/afterwriting` | **Do not exist.** Both oracles agree |

### 🔧 The oracle disagreement that produced four corrections

`git ls-remote` reported EXISTS for four slugs that `search/repositories` rejected with **HTTP 422
"the listed users and repositories cannot be searched"**. That combination means **rename/transfer
redirect**, which `ls-remote` follows silently:

- `wildwinter/fountain-tools` → **`wildwinter/screenplay-tools`**
- `rsdoiel/scripttools` → **`rsdoiel/scripttool`**
- `afterwriting-labs/afterwriting` → **`ifrost/afterwriting-labs`** (owner changes entirely)
- `olivertaylor/textplay` → **`overvale/Textplay`** (owner changes entirely)

Every one of those stale slugs is what the search engines and tool directories still publish, and every
one **still resolves in a browser**, so a URL check passes and the KB would have recorded four
non-canonical slugs. See `repos/foundations.md` for the full rule. In this session
`curl -sI https://github.com/…` returns **403 from the egress proxy**, so the redirect is not readable
from headers; `WebFetch` of the repository page is the oracle that yields the canonical name.

## 2026-11-26 — pass 16: avails & distribution-rights infrastructure (24 slugs checked, 22 resolve, 2 do not)

### The anchor this KB had never named

`MovieLabs` appeared **once** in 1.1 MB of KB before this pass. `MovieLabs/mddf` — **MIT, 38*/11f** — is
the reference implementation for **Avails, CMM, MMC, MEC and AOD**, i.e. the interchange the entire
title-licensing industry delivers to retailers. Confirmed from its own README's overview, not inferred.

### Movement, dormancy and the two that do not resolve

| Repo | Stars/Forks | Licence | Last push | Signal |
|---|---|---|---|---|
| MovieLabs/mddf | 38*/11f | MIT | 2025-12-19 | Anchor. **Push date flatters it** — own README tops out at "2023-Jul-2: v2.0.8 released" |
| MovieLabs/OMC | 35*/6f | Apache-2.0 | 2026-02-07 | Live ontology, the production-side join target |
| survos/omc | 0*/0f | MIT | 2026-11-25 | **Created 2026-11-24** — one day old when measured. OMC 2.8 DTOs. First new permissive entrant since 2023 |
| MovieLabs/omc-util | 1*/0f | **NONE** | 2026-11-03 | Active, unlicensed |
| MichaelBrandonFalk/UltimateAvailMaker | 0*/0f | **NONE** | 2026-11-12 | The **only maintained** avails authoring tool found — and unlicensed, so unusable |
| MovieLabs/cmr-ratings | 1*/0f | **NONE** | 2026-06-17 | Common Metadata Ratings, active-ish, unlicensed |
| thomas-shirley/ema-avails-generator | 0*/0f | Apache-2.0 | 2023-03-21 | Dormant 3 years |
| playmoviespartner/emavalidator | 3*/2f | **NONE** | 2017-04-20 | Google Play's own Avails validator. Dormant 9 years, no licence |
| pivotshare/avails | 1*/1f | MIT | 2016-10-31 | Dormant 10 years. Small, readable reference for the sheet format |
| omi/RAIDAR | 21*/4f | MIT | 2021-01-12 | Berklee music-licensing platform. Dormant 5 years |
| **kaltura/server** | — | — | — | ⚠️ **`git ls-remote` returns nothing.** Gone or no longer public |
| **kaltura/platform-install-packages** | — | — | — | ⚠️ **Does not resolve either** |

**The Kaltura note matters even though this KB never cited it** (checked: 0 mentions across all eight
files). For a decade "the open-source video platform" meant Kaltura; that reflex survives in memory long
after it stops being true on disk. Recorded so no future pass writes a row that 404s.

### Two measured zeros and one record for false abundance

- `residuals calculation film` → **0 repositories.**
- `film royalty statement` → **1**, and it is a scripture-governance project.
- `rights windowing` → **681 repositories, zero relevant.** Every hit is Microsoft Windows privilege
  tooling (`gtworek/Priv2Admin` 2534*, `jborean93/PSPrivilege`, portable installers that avoid needing
  "administrator rights on Windows").

**681/0 is this KB's new record for false abundance**, beating pass 8's `isan` (1942/0) on
*plausibility*: "rights windowing" is the industry's own term of art, so the query looks safe. **New
rule:** when any noun in a query is also an OS, platform or language name (`windows`, `rust`, `go`,
`swift`), the total is noise by construction — add a disambiguating industry noun or the search has told
you nothing.

### Licence-file probe, sixth confirmation that the badge is not the licence

Run across `master` and `main` with the full six-name set that pass 8 corrected into this KB:

- `Phraseanet` (276*/106f, active 2026-11-25) → `LICENSE` reads **"Licensed under GPL license"** with
  **no version**. GPL-2.0-only and GPL-3.0-or-later differ materially for a hosted deployment.
- `resourcespace` (95*/29f, active 2026-11-26) → `license.txt` says only *"Please see the
  documentation/licenses folder for all applicable licenses."* The compilation-owned-licence pattern
  pass 8 found in `acoustid/chromaprint`. Clone and read the folder.
- Both show as **NOASSERTION** on the API. The badge was right to refuse; only reading the file says why.


## 2026-11-26 — pass 15: out-of-home & signage infrastructure (37 slugs checked, 36 resolve, 1 does not)

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

### Movement worth watching

| Repo | Stars | Licence | Last push | Signal |
|---|---|---|---|---|
| [concerto/concerto](https://github.com/concerto/concerto) | 485\* | Apache-2.0 | 2026-11-26 | An 18-year-old Rails CMS pushed **today** — the permissive anchor nobody cites |
| [screentinker/screentinker](https://github.com/screentinker/screentinker) | 281\* | MIT | 2026-11-26 | Multi-tenant MIT CMS, pushed today, single maintainer |
| [home-screens/home-screens](https://github.com/home-screens/home-screens) | 114\* | MIT | 2026-11-26 | Small, new, pushed today — watch the trajectory |
| [WhimsicalCoder/dooh-bid-validator](https://github.com/WhimsicalCoder/dooh-bid-validator) | 0\* | Apache-2.0 | 2026-11-26 | Pushed today into an empty layer; zero users yet |
| [jeremiaa/magic-frame](https://github.com/jeremiaa/magic-frame) | 532\* | **Polyform Noncommercial** | 2026-11-22 | Rising fast and **commercially unusable** — the trap of this pass |
| [openooh/venue-taxonomy](https://github.com/openooh/venue-taxonomy) | 56\* | Apache-2.0 | 2026-11-16 | The alive spec; its three siblings are dormant and unlicensed |
| [screenlite/screenlite](https://github.com/screenlite/screenlite) | 368\* | MIT | 2026-05-08 | **Went quiet ~6 months ago** — was a top recommendation; re-check next pass |


## 2026-11-26 — pass 14: localization substrate infrastructure (49 slugs checked, 47 resolve, 2 do not)

### Headline: within one standards family, the format that carries the job is maintained and the format that carries the client's asset is abandoned

The plane under dubbing and subtitling: interchange formats, translation memories, termbases,
translation-management platforms, MT engines and quality tooling. **0 of the 47 resolving repos
appeared anywhere in this KB before today.**

The structural result is a *within-family* comparison, which is stronger evidence than the
cross-domain comparisons earlier passes relied on. XLIFF and TMX come from the same standards
lineage, the same decade and the same vendors. XLIFF carries **this week's job**; TMX carries **ten
years of paid translation** — the client's switching cost and only wholly-owned multilingual corpus.

| | Carries | Best maintained open tooling | State |
|---|---|---|---|
| **XLIFF** | this week's work | `vslavik/poedit` MIT **2,061★** | Healthy — pushed 2026-11-09 |
| **TMX** | a decade of paid output | `bitextor/bitextor` GPL-3.0 302★ | **Dead — pushed 2024-11-11** |

Full TMX estate by stars: `302 (dormant) → 17 → 12 → 8 → 7 → 6 → 6 → 4`. **Nothing above 17★ is alive.**

### Platforms — the tier that can actually be deployed

| Repo | Licence | Stars | Forks | Pushed |
|---|---|---|---|---|
| [WeblateOrg/weblate](https://github.com/WeblateOrg/weblate) | GPL-3.0 | 6,185 | 1,392 | 2026-11-26 |
| [lingodotdev/lingo.dev](https://github.com/lingodotdev/lingo.dev) | Apache-2.0 | 5,400 | 812 | 2026-11-20 |
| [tolgee/tolgee-platform](https://github.com/tolgee/tolgee-platform) | ⚠️ Apache-2.0 + `ee/` | 4,164 | 381 | 2026-11-25 |
| [ever-co/ever-traduora](https://github.com/ever-co/ever-traduora) | AGPL-3.0 | 2,140 | 224 | 2026-11-25 |
| [generaltranslation/inlang](https://github.com/generaltranslation/inlang) | MIT | 2,012 | 184 | 2026-11-24 |
| [mozilla/pontoon](https://github.com/mozilla/pontoon) | **BSD-3-Clause** | 1,680 | 620 | 2026-11-25 |
| [box/mojito](https://github.com/box/mojito) | Apache-2.0 | 389 | 73 | 2026-11-09 |
| [serge-community/serge](https://github.com/serge-community/serge) | ⚠️ "terms of Perl 5.10.0" | 228 | 48 | 2024-06-13 |
| [txty-io/texterify](https://github.com/txty-io/texterify) | ❌ **BSL 1.1, no use grant** | 203 | 17 | 2026-10-09 |
| [Lessify/localess](https://github.com/Lessify/localess) | MIT | 75 | 20 | 2026-11-25 |

`mozilla/pontoon` is the find of the pass: **the only mature *permissive* platform in the tier**, in
production at Mozilla, and therefore the default when the client must own and relicense the result.

### Formats, memory, terminology and quality

| Repo | Licence | Stars | Pushed | Layer |
|---|---|---|---|---|
| [vslavik/poedit](https://github.com/vslavik/poedit) | MIT | 2,061 | 2026-11-09 | XLIFF/PO/JSON editor |
| [daniel-sc/ng-extract-i18n-merge](https://github.com/daniel-sc/ng-extract-i18n-merge) | MIT | 224 | 2026-10-20 | XLIFF extract/merge |
| [locize/xliff](https://github.com/locize/xliff) | MIT | 91 | 2026-10-31 | XLIFF ↔ JS converters |
| [microsoft/XLIFF2-Object-Model](https://github.com/microsoft/XLIFF2-Object-Model) | ⚠️ NOASSERTION | 92 | 2023-06-06 | XLIFF 2.0 model; dormant |
| [maxprograms-com/OpenXLIFF](https://github.com/maxprograms-com/OpenXLIFF) | EPL-1.0 | 86 | 2026-11-03 | XLIFF 1.2–2.2 create/merge/validate — the Okapi substitute |
| [bitextor/bitextor](https://github.com/bitextor/bitextor) | GPL-3.0 | 302 | 2024-11-11 | TM mining; **dormant** |
| [yasslab/konjak](https://github.com/yasslab/konjak) | MIT | 12 | 2021-08-21 | TMX tools (Ruby) |
| [GregoryVigoTorres/sdltm2tmx](https://github.com/GregoryVigoTorres/sdltm2tmx) | GPL-3.0 | 8 | 2023-10-13 | `.sdltm` → TMX: the vendor-exit tool |
| [maxprograms-com/HybridTM](https://github.com/maxprograms-com/HybridTM) | EPL-1.0 | 7 | 2026-07-26 | TM engine; alive at 7★ |
| [camertron/tmx-parser](https://github.com/camertron/tmx-parser) | ⚠️ none per API (unprobed) | 6 | 2015-07-24 | TMX parser; last touched 2015 |
| [gaois/terminologue](https://github.com/gaois/terminologue) | MIT | 76 | 2026-11-24 | Termbase — best permissive pick in its tier |
| [translate/terminator](https://github.com/translate/terminator) | GPL-3.0 | 49 | 2022-04-22 | Termbase; dormant |
| [diegoberaldin/MetaTerm](https://github.com/diegoberaldin/MetaTerm) | GPL-3.0 | 19 | 2023-06-11 | Termbase; dormant |
| [mjpost/sacrebleu](https://github.com/mjpost/sacrebleu) | Apache-2.0 | 1,266 | 2026-08-20 | Computable quality (BLEU) |
| [Unbabel/COMET](https://github.com/Unbabel/COMET) | Apache-2.0 | 792 | 2026-04-21 | Computable quality (neural) |
| [Unbabel/OpenKiwi](https://github.com/Unbabel/OpenKiwi) | AGPL-3.0 | 236 | 2022-06-23 | Quality estimation; **dead** |
| [NJUNLP/njuqe](https://github.com/NJUNLP/njuqe) | MIT | 12 | 2025-09-10 | Quality estimation |
| [BYU-TRG-Team/mqm-scorecard](https://github.com/BYU-TRG-Team/mqm-scorecard) | Apache-2.0 | **1** | 2025-06-11 | **Contractual quality (MQM)** |
| [BYU-TRG-Team/mqm-scorecard-api](https://github.com/BYU-TRG-Team/mqm-scorecard-api) | Apache-2.0 | **1** | 2025-06-11 | **Contractual quality (MQM) API** |
| [NiuTrans/NiuTrans.SMT](https://github.com/NiuTrans/NiuTrans.SMT) | GPL-2.0 | 163 | 2024-07-17 | Statistical MT; historical |

### The two that do not resolve — recorded, not dropped

- **`okapiframework/okapi` → `ls-remote` FAIL.** The Okapi Framework, the standard open
  filter/segmentation toolkit that converts ~50 proprietary formats into XLIFF, is on **Bitbucket**.
  GitHub holds only satellites: [spartansw/okapi-worldserver-components](https://github.com/spartansw/okapi-worldserver-components)
  (MIT, 7★, 2024-07-17), [dameikle/okapi-maven-plugin](https://github.com/dameikle/okapi-maven-plugin)
  (Apache-2.0, 7★, 2024-10-23), [sheep-works/Suffolk](https://github.com/sheep-works/Suffolk)
  (0★, 2026-11-20, an early Rust port of Okapi's Tikal filter).
- **`LibreTranslate/argos-translate-lt` → `ls-remote` FAIL.** The fork LibreTranslate pins
  (`argos-translate-lt==1.12.1`) ships via **PyPI** with no resolving GitHub repo. Confirm its
  licence on the published artefact; do not assume it inherited upstream MIT.
- **OmegaT** has no primary GitHub repo either — a **SourceForge** project. Search returns only
  plugins ([yoyicue/omegat-tencent-plugin](https://github.com/yoyicue/omegat-tencent-plugin) GPL-3.0
  41★, [inertia42/omegat-openaitrans-plugin](https://github.com/inertia42/omegat-openaitrans-plugin)
  GPL-3.0 30★) and name collisions.

**The method consequence, which applies to all twelve industries:** GitHub-only discovery has a blind
spot shaped exactly like *mature, pre-2010, standards-implementing open source*, which is
disproportionately where industrial standards tooling lives. When a plane has an obvious incumbent
and the sweep does not return it, **check another forge before concluding absence.**

## 2026-11-26 — pass 13: subscription, entitlement & reader-revenue infrastructure (33 repos, 33/33 resolve)

### Headline: the licence outcome is predicted by distance from the recurring charge

Sorted by what the layer decides. No counterexample in either direction:

| Step | Layer | Licence shape | Anchor |
|---|---|---|---|
| 1 | Identity — *who are you* | Apache-2.0 | Keycloak 38,060★ |
| 2 | Entitlement — *what may you watch* | Apache-2.0 | SpiceDB 7,243★, OpenFGA 6,197★, Cerbos 4,669★ |
| 3 | Billing — *the recurring charge* | AGPL-dominant | Kill Bill 5,869★ is the lone Apache-2.0 |
| 4 | Reader revenue — *the conversion funnel* | one MIT repo | REMP 138★ |

### Infrastructure added this pass (all measured 2026-11-26)

**Entitlement / authorization** — the healthiest permissive layer here:
[authzed/spicedb](https://github.com/authzed/spicedb) Apache-2.0 7,243★ ·
[openfga/openfga](https://github.com/openfga/openfga) Apache-2.0 6,197★ ·
[cerbos/cerbos](https://github.com/cerbos/cerbos) Apache-2.0 4,669★ ·
[ory/keto](https://github.com/ory/keto) Apache-2.0 5,424★ (~3 months quiet) ·
[casbin/casbin](https://github.com/casbin/casbin) Apache-2.0, stars **n/m** ·
[Permify/permify](https://github.com/Permify/permify) **AGPL-3.0** 5,975★ ·
[warrant-dev/warrant](https://github.com/warrant-dev/warrant) Apache-2.0 1,339★ — **~12 months
dormant, do not start here**.

**Identity**: [keycloak/keycloak](https://github.com/keycloak/keycloak) Apache-2.0 38,060★ ·
[ory/kratos](https://github.com/ory/kratos) Apache-2.0 13,977★ ·
[zitadel/zitadel](https://github.com/zitadel/zitadel) **AGPL-3.0** 15,654★ ·
[supertokens/supertokens-core](https://github.com/supertokens/supertokens-core) open core +
proprietary `ee/` 15,347★.

**Billing, metering, payments**: [killbill/killbill](https://github.com/killbill/killbill)
**Apache-2.0** 5,869★ · [juspay/hyperswitch](https://github.com/juspay/hyperswitch) **Apache-2.0**
45,917★ · [openmeterio/openmeter](https://github.com/openmeterio/openmeter) **Apache-2.0** 2,471★ ·
[getlago/lago](https://github.com/getlago/lago) AGPL-3.0 10,922★ ·
[flexprice/flexprice](https://github.com/flexprice/flexprice) AGPL-3.0 6,874★ ·
[meteroid-oss/meteroid](https://github.com/meteroid-oss/meteroid) AGPL-3.0 1,370★ ·
[tabloy/keygate](https://github.com/tabloy/keygate) AGPL-3.0 279★ ·
[laravel/cashier-stripe](https://github.com/laravel/cashier-stripe) MIT 2,550★ (a Stripe binding,
not an engine) · [billabear/billabear](https://github.com/billabear/billabear) **licence
undetermined** 760★ · [service-bot/servicebot](https://github.com/service-bot/servicebot) GPL-3.0
956★ **dormant since 2021-01-12**.

**Reader revenue** — the entire layer:
[remp2020/remp](https://github.com/remp2020/remp) MIT 138★ (SSO + Beam + Campaign + Mailer) ·
[remp2020/crm-skeleton](https://github.com/remp2020/crm-skeleton) MIT 8★ ·
[remp2020/pythia-tools](https://github.com/remp2020/pythia-tools) **no licence**, 4★, dormant since
2023-03-20 — the churn-propensity component, and it is the one piece that is unusable.

**Churn / CLV substrate**: [CamDavidsonPilon/lifelines](https://github.com/CamDavidsonPilon/lifelines)
MIT 2,623★ · [CamDavidsonPilon/lifetimes](https://github.com/CamDavidsonPilon/lifetimes) MIT 1,476★
**ARCHIVED 2024-06-28**.

### ⛔ Directus MSCL-1.0-GPL read in full — and it has a professional-services clause

The 4,481-byte licence file: the only prohibition is **Competing Use** (reselling a hosted Directus
against the licensor's own paid offering). Permitted Purposes explicitly include use "in connection
with **professional services that you provide to a licensee**" — the clause that decides whether a
services firm may build on it, and it says yes. A **Grant of Future License** makes each version
**GPL-3.0 on its fourth anniversary**: delayed-open on a four-year clock, landing on copyleft, never
on permissive. No SPDX id exists for this, so no licence scanner will tell you any of it.

### Split-licence pattern: the licence is a *path*, not an identifier

Three projects report `NOASSERTION` and all three are MIT-except-a-directory:
[PostHog/posthog](https://github.com/PostHog/posthog) (`ee/`),
[growthbook/growthbook](https://github.com/growthbook/growthbook) (three `enterprise` dirs),
[supertokens/supertokens-core](https://github.com/supertokens/supertokens-core) (`ee/`).
The answerable question is not "is it MIT?" but "does my build import anything under that path?"

### Measurement note

`git ls-remote` resolved **33/33**. HTTP HEAD via `curl -sI` returned **403 for all 33** through the
egress proxy — a uniform false negative. Existence was confirmed with `ls-remote`; licences with
`NOASSERTION` were resolved by reading the licence file over `raw.githubusercontent.com`.

## 2026-11-26 — pass 12: sound, music & immersive-audio infrastructure (65 repos, 65/65 resolve)

### Headline: the first plane whose licence outcome is predicted by a *mechanism*

Sorted by whose process the code runs inside. No counterexample in either direction:

| Tier | Repos | Licence outcome |
|---|---|---|
| Runs **beside** the host — reference implementations, libraries, renderers | `ebu/bear`, `ebu/libadm`, `ebu/libbw64`, `ebu/ebu_adm_renderer`, `ADM-OSC`, `omnitone`, `JSAmbisonics` | **7/7 permissive** (Apache-2.0 / BSD / MIT) |
| Runs **inside** the host — plugins, plugin frameworks, DAW engines | `JUCE`, `tracktion_engine`, `libspatialaudio`, `Spatial_Audio_Framework`, `ear-production-suite`, `zrythm` | **6/6 dual-licensed or copyleft** |

The immersive-audio standards layer is also the most **institutionally European** corner of this KB:
the EBU, the BBC and the former IRT wrote nearly all of it, and it is permissive by policy.

### The ADM / next-generation-audio stack, verified

| Repo | License | Stars | Push |
|---|---|---|---|
| ebu/ebu_adm_renderer | BSD-3-Clause-Clear | 105 | 2026-02-11 |
| ebu/ear-production-suite | GPL-3.0-or-later | 126 | 2026-11-18 |
| ebu/libadm | Apache-2.0 | 51 | 2026-08-07 |
| ebu/libbw64 | Apache-2.0 | 43 | 2024-04-13 |
| ebu/bear | Apache-2.0 | 32 | 2026-08-14 |
| immersive-audio-live/ADM-OSC | MIT | 91 | 2026-10-16 |
| GoogleChrome/omnitone | Apache-2.0 | 919 | 2026-10-22 |
| videolan/libspatialaudio | LGPL-2.1+ **or commercial** | 325 | 2026-07-14 |
| polarch/JSAmbisonics | BSD-3-Clause | 182 | 2026-09-17 |
| hoene/libmysofa | BSD-3-Clause | 180 | 2026-10-25 |
| leomccormack/Spatial_Audio_Framework | ISC core / GPL-2.0 optional | 771 | 2026-05-30 |
| resonance-audio/resonance-audio | Apache-2.0 | 543 | **ARCHIVED 2022-09-08** |
| spatialaudio/python-sofa | MIT | 28 | dormant 2021-03-08 |
| tu-studio/IEMPluginSuite | GPL-3.0 | 12 | 2026-10-13 (**a fork**; canonical on `git.iem.at`) |

Note the star ceiling: **the normative renderer for all object-based audio has 105 stars.** The
standard that NBC's Olympics and Super Bowl Atmos deliverables and the 2026 World Cup sit on top of is
implemented, in the open, by a project the size of a weekend hobby repo. That is the supply picture,
not an insult to it.

### Speech, restoration and music — the new permissive rows

| Repo | License | Stars | Push |
|---|---|---|---|
| deezer/spleeter | MIT | 28,539 | 2026-10-28 |
| k2-fsa/sherpa-onnx | Apache-2.0 | 16,241 | 2026-11-24 |
| beetbox/beets | MIT | 15,983 | 2026-11-26 |
| Tonejs/Tone.js | MIT | 14,959 | 2026-11-20 |
| speechbrain/speechbrain | Apache-2.0 | 11,951 | 2026-11-25 |
| librosa/librosa | ISC | 9,166 | 2026-11-25 |
| spotify/basic-pitch | Apache-2.0 | 6,127 | 2025-11-13 |
| xiph/rnnoise | BSD-3-Clause | 5,982 | 2025-02-22 |
| Rikorose/DeepFilterNet | MIT **or** Apache-2.0 | 5,107 | 2026-11-06 |
| 0xfe/vexflow | MIT | 4,409 | 2025-03-05 |
| xiph/opus | BSD-3-Clause | 3,395 | 2026-11-26 |
| asteroid-team/asteroid | MIT | 2,605 | 2026-11-03 |
| cuthbertLab/music21 | BSD-3-Clause | 2,635 | 2026-11-18 |
| paulrosen/abcjs | MIT | 2,378 | 2026-11-18 |
| pure-data/pure-data | Standard Improved BSD | 2,130 | 2026-11-19 |
| libsndfile/libsndfile | LGPL-2.1 | 1,736 | 2026-10-28 |
| mido/mido | MIT | 1,662 | 2026-11-09 |
| craffel/pretty-midi | MIT | 1,052 | 2026-11-08 |
| rism-digital/verovio | LGPL-3.0 | 984 | 2026-11-25 |
| Natooz/MidiTok | MIT | 909 | 2026-11-25 |

### ⛔ Three licences that resolve differently from what the API says — and one that is not at the root

- **`ebu/ear-production-suite`**: 404 on all **ten** conventional licence filenames at the repo root,
  with `README.md` = 200 as the control. The file is real, 110,524 B, GPL-3.0-or-later (BBC/EBU/IRT),
  at **`packaging/LICENSE.md`**. Found by one `search/code` call with `filename:LICENSE`. **A ninth
  way a licence hides: it is not at the root, and the raw-root probe cannot see it.**
- **`musescore/MuseScore`**: `NOASSERTION` → **GPL-3.0 with a font exception.** The added clause is
  what defeats the classifier — which is the general cause of `NOASSERTION` in this plane.
- **`sonic-pi-net/sonic-pi`**: `NOASSERTION` → **MIT main source that links GPLv3 code**, so the
  distribution obligation is GPLv3. The inverse of the usual trap.
- **`zrythm/zrythm`**: `NOASSERTION` → AGPL-3.0 plus §7 additional terms, declared as a **REUSE
  pointer** (`LICENSES/LicenseRef-ZrythmLicense.txt`), not inline.

### ⚙️ Measurement notes — two oracles corrected

1. **Batched `repo:` queries fail whole-batch on one bad name** (`422 Validation Failed`), returning
   nothing for the valid repos alongside it. Efficient, but it fails in the direction of a false
   negative. On 422, re-probe individually.
2. **The github.com HTML channel is dead in this environment**: `curl -sI https://github.com/<o>/<r>`
   returns **403 for every repo, existing or not**. It cannot confirm, deny, or detect a rename here.
   `git ls-remote` and the search API are the only usable oracles. And a 422 is not proof of a
   rename — two of three this pass were **my own wrong owner** (`videolabs` → **`videolan`**).

### Where the repos live when they are not on GitHub

`git.iem.at` (IEM Plugin Suite) is unreachable through this proxy — a uniform `000`, which is a
network verdict and not a project verdict. LilyPond's GitHub presence is a mirror of a GitLab
project. Pass 10 retired the MXF container layer for a similar reason. **The habit of equating "not
on GitHub" with "does not exist" would have dropped the reference ambisonic plugin suite from this
KB entirely.**

## 2026-11-26 — pass 11: description, cataloguing & syndication infrastructure (52 repos, 52/52 exist)

**Verification channel for this pass, stated because it had to change.** `curl -sI` returned **403
for all 52 GitHub URLs and `000` for all 8 non-GitHub URLs — one 200 in 60**. Those are proxy policy
and blocked domains, **not 404s**. Existence was established with `git ls-remote --exit-code`:
**52/52 exist, 0 dead.** Metrics came from `search/repositories`; **every licence below was read from
the actual file over the raw channel**, with filename and byte count where the API said
`NOASSERTION`.

### Standards & schemas — the layer that is open, and actively pushed

| Repo | License | Stars / forks | Push |
|---|---|---|---|
| `schemaorg/schemaorg` | Apache-2.0 | 6320★ / 975f | 2026-11-25 |
| `iptc/newsinjson` (ninjs) | MIT | 47★ / 10f | 2026-11-24 |
| `iptc/sport-schema` | **no licence file** | 38★ / 3f | 2026-10-01 |
| `ebu/ebucoreplus` | **MIT** | 30★ / 8f | 2026-10-02 |
| `ebu/ebucore` | **CC-BY-NC-SA-3.0 ⚠ NonCommercial** (`LICENSE.md`, 386 B) | 27★ / 7f | 2026-08-18 |
| `iptc/newsml-g2` | **CC-BY-4.0** (`LICENSE`, 901 B) | 20★ / 5f | 2026-11-20 |
| `iptc/python-newsmlg2` | MIT | 6★ / 4f | 2026-11-11 |
| `iptc/rightsml-dev` | **no licence file** | 5★ / 2f | 2026-07-06 |
| `iptc/json-for-concepts-vocabularies` | **no licence file** | 4★ / 0f | 2017-10-20 |
| `iptc/catalog` | MIT (`LICENSE`, 1061 B) | 3★ / 0f | 2026-11-17 |
| `iptc/video-metadata-hub` | MIT (`LICENSE`, 1066 B) | 2★ / 0f | **2026-11-25** |
| `iptc/sports-newscodes` | **CC-BY-4.0** (`LICENSE`, 444 B — "applies to all NewsCodes") | 1★ / 0f | 2023-09-29 |

**IPTC's whole org tops out at 47★ and pushed six repos in November 2026.** That is the signature of
infrastructure maintained by the standards body itself with almost no outside adoption — the inverse
of the usual "popular but abandoned" pattern, and the reason low stars here are not a disqualifier.

### Vocabulary, description & reconciliation tooling

| Repo | License | Stars / forks | Push |
|---|---|---|---|
| `OpenRefine/OpenRefine` | BSD-3-Clause | 12118★ / 2214f | 2026-11-24 |
| `exiftool/exiftool` | GPL-3.0 (`LICENSE`, 35149 B) | 5319★ / 508f | 2026-11-16 |
| `MediaArea/MediaInfo` | BSD-2-Clause | 2079★ / 202f | 2026-11-24 |
| `ebu/awesome-broadcasting` | CC0-1.0 (`LICENSE.md`, 187 B) | 1805★ / 237f | 2026-09-30 |
| `apache/jena` | Apache-2.0 | 1511★ / 745f | 2026-11-25 |
| `Exiv2/exiv2` | GPL-2.0 (`COPYING`, 18092 B) | 1174★ / 350f | 2026-11-23 |
| `NatLibFi/Skosmos` | **MIT** (`LICENSE`, 1376 B) | 269★ / 105f | 2026-11-18 |
| `tematres/TemaTres-Vocabulary-Server` | **GPL-2.0-or-later** — `readme.md` + source headers, **no licence file** | 142★ / 11f | **2026-11-25** |
| `NatLibFi/Finto-data` | **MIXED** (`LICENSE`, 1765 B) | 21★ / 6f | **2026-11-26** |
| `mikrosimage/jebu-core` | GPL-2.0 | 3★ / 2f | **2018-06-13 — dead 8 years** |

### Platforms — newsroom, cataloguing, repository, IIIF

| Repo | License | Stars / forks | Push |
|---|---|---|---|
| `wagtail/wagtail` | BSD-3-Clause | 20779★ / 4750f | 2026-11-26 |
| `DSpace/DSpace` | BSD-3-Clause | 1116★ / 1509f | 2026-11-23 |
| `IQSS/dataverse` | Apache-2.0 (`LICENSE.md`, 10889 B) | 1080★ / 574f | 2026-11-24 |
| `projectblacklight/blacklight` | Apache-2.0 (`LICENSE`, 788 B) | 800★ / 254f | 2026-11-24 |
| `superdesk/superdesk` | **AGPL-3.0** | 760★ / 236f | 2026-11-23 |
| `ProjectMirador/mirador` | Apache-2.0 | 625★ / 280f | 2026-11-25 |
| `UniversalViewer/universalviewer` | MIT (`LICENSE.txt`, 1227 B) | 576★ / 210f | 2026-11-25 |
| `omeka/omeka-s` | GPL-3.0 | 534★ / 179f | 2026-11-24 |
| `archivesspace/archivesspace` | **ECL-2.0** (`COPYING`, 748 B) | 450★ / 255f | 2026-11-25 |
| `collectiveaccess/providence` | GPL-3.0 | 389★ / 200f | 2026-11-25 |
| `vufind-org/vufind` | GPL-2.0 | 311★ / 404f | 2026-11-25 |
| `cantaloupe-project/cantaloupe` | **NCSA** (`LICENSE.txt`, 1870 B) | 308★ / 124f | 2026-11-23 |
| `fcrepo/fcrepo` | Apache-2.0 | 255★ / 138f | **2026-11-26** |
| `Islandora/islandora` | GPL-2.0 (`LICENSE`, 18092 B) | **not in search index** | — |
| `Islandora/documentation` | MIT | 112★ / 69f | 2026-11-25 |
| `fabiodalez-dev/Pinakes` | GPL-3.0 | 95★ / 11f | 2026-11-25 |
| `islandora-interest-groups/Islandora-Metadata-Committee` | no licence file | 37★ / 42f | 2026-11-20 |
| `superdesk/superdesk-core` | AGPL-3.0 | 32★ / 89f | 2026-11-25 |
| `intranda/goobi-viewer-core` | GPL-2.0 | 27★ / 17f | 2026-11-20 |
| `superdesk/newsroom` | GPL-3.0 | 24★ / 32f | 2026-11-23 |
| `Daniel-KM/Omeka-S-module-OaiPmhRepository` | GPL-3.0 | 5★ / 7f | 2026-10-05 |

### INA — the French national audiovisual institute's org, new to this KB

| Repo | License | Stars / forks | Push |
|---|---|---|---|
| `ina-foss/inaSpeechSegmenter` | MIT | 919★ / 149f | 2026-03-12 |
| `ina-foss/amalia.js` | MIT | 191★ / 36f | 2023-08-28 (dormant) |
| `ina-foss/twembeddings` | MIT | 33★ / 5f | 2026-06-30 |
| `ina-foss/afp-api-client` | LGPL-3.0 | 3★ / 0f | 2023-12-05 (dormant) |

22 repos in the org. `inaSpeechSegmenter` is **the most-starred purpose-built archive-indexing tool
found in this plane.** `afp-api-client` is the only open wire-service client located anywhere.

### Two structural reads of this table

**The copyleft/permissive split runs along a functional line, not a random one.** Schemas and
*delivery* are permissive (CC BY 4.0, MIT, Apache-2.0, BSD, NCSA, CC0); **purpose-built newsroom and
cataloguing systems are uniformly AGPL/GPL** — Superdesk, CollectiveAccess, Omeka S, VuFind,
Islandora, TemaTres. If a client refuses copyleft for a hosted service there is **no open newsroom
CMS for them**; the honest substitute is Wagtail (BSD-3) plus custom workflow. **IIIF is the one
permissive escape hatch in the systems tier** — Mirador Apache-2.0, Universal Viewer MIT, Cantaloupe
NCSA, all pushed within six days of this pass.

**Liveness is near-universal here, which is unusual for this KB.** Of 52 repos, all but four were
pushed within ~60 days, and eleven within six days of the pass — including `fcrepo` and
`NatLibFi/Finto-data` **on the day of the pass**. The dead ones are named and dated above rather than
quietly dropped: `jebu-core` (2018), `amalia.js` (2023), `afp-api-client` (2023), `edsu/pymarc`
(archived 2020, live at `gitlab.com/pymarc/pymarc`).

## 2026-11-26 — pass 10: the theatrical & digital-cinema infrastructure (25 verified repos, 25/25 resolved)

### Headline: the first plane in this KB that is **copyleft end to end**, and the keys are a 3-star layer

The channel this KB had never recorded. Nine passes covered streaming, broadcast, live, podcast,
archive, production, measurement, delivery and trust & safety; **the DCP shipped to a cinema, the
KDM that unlocks it and the validator that clears it were a literal zero across all eight files.**

| Layer | Repos | Licence shape | State |
|---|---|---|---|
| Authoring | `dcpomatic` 175★, `libdcp` 29★, `libsub` 9★, `opendcp` 134★, `DcpToolkit` 3★ | **GPL-2.0 / GPL-3.0**, one MIT outlier | `dcpomatic` pushed **2026-11-24**; `opendcp` dormant since **2020-04-28** |
| Validation | `ClairMeta` 106★, `backports` 40★, `digital_cinema_tools` 100★, `dcpdoctor` 1★ | **BSD-3 / GPL-3 / AGPL-3 / none** | `ClairMeta` is the only permissive one |
| Substrate | `openjpeg` 1,123★, `asdcplib` 99★, `grok` 300★ | **BSD-2 / BSD-3 / AGPL-3** | all active; `asdcplib` 2026-11-19 |
| Container | `bmx` 88★, `regxmllib` 39★, `BBC-archive/libMXF` 15★, `Limecraft/ebu-libmxf` 17★ | BSD-2 / BSD-3 | **three of four archived or relocated** |
| IMF bridge | `Netflix/photon` 259★, `IMFTool` 145★ | Apache-2.0 / GPL-3.0 | both active |
| Keys (KDM) | `kdmcourier` 1★, `dcpkdm` 1★, `KdmManager` 0★ | AGPL-3 / none / GPL-3 | **3 stars in the whole layer** |
| Exhibition | `CineTMS` 5★ | Apache-2.0 | APAC-origin, and the only real candidate |

### The KDM layer — ties the crudest number ever recorded in this KB

`KDM cinema` returns **8 results with star counts 1, 1, 1, 0, 0, 0, 0, 0 — three stars in total.**
That equals healthcare's `medical necessity` (3) and beats pass 8's `pay-per-crawl` (9), and it is
attached to a *harder* object than either: a KDM is a file with a published SMPTE schema, not a
judgement call, and **no film plays in any commercial cinema on earth without one.** `asdcplib` can
write them, permissively. Nothing open manages their lifecycle — windows, expiry, per-screen
reissue, 400 screens against 30 distributors.

### ⚠️ The MXF container layer has been formally retired by its maintainers

Measured, not inferred. [`bbc/bmx`](https://github.com/bbc/bmx) (BSD-3, 88★) is **ARCHIVED**
(2025-09-29). [`sandflow/regxmllib`](https://github.com/sandflow/regxmllib) (BSD-2, 39★, MXF→XML per
SMPTE ST 2001-1) was **ARCHIVED on 2026-11-22 — four days before this pass.**
[`bbc/libMXF`](https://github.com/BBC-archive/libMXF) has been **relocated into the BBC's `-archive`
org**. The EBU's own library last moved in 2013 and survives only through
[`Limecraft/ebu-libmxf`](https://github.com/Limecraft/ebu-libmxf) (BSD-3, 17★, 2024-11-15), a
Belgian vendor's fork — **the most recently touched copy in the family is maintained by a company,
not a standards body.**

This is the clearest instance in this KB of **permissive-and-abandoned versus copyleft-and-alive**,
and the two risks sit one layer apart: the container beneath the DCP is free to use and unmaintained;
the tools that write the DCP are maintained and copyleft. Neither is the risk a licence scanner
reports.

### ⛔ Three licences that resolve differently from what the API says

| Repo | API says | Actually is | Where it hides |
|---|---|---|---|
| [`uclouvain/openjpeg`](https://github.com/uclouvain/openjpeg) | `NOASSERTION` | **BSD-2-Clause** | `LICENSE` exists but **opens with `/*`** — the text is wrapped in a C comment block, so scanners read it as source. **A ninth way a licence hides.** |
| [`cinecert/asdcplib`](https://github.com/cinecert/asdcplib) | `NOASSERTION` | **BSD-3-Clause** | `COPYING`, 3,047B, "Copyright (c) 2003-2012, John Hurst", clause 3 = no-endorsement |
| [`GrokImageCompression/grok`](https://github.com/GrokImageCompression/grok) | `NOASSERTION` | **AGPL-3.0** | 37,281B `LICENSE`. The fastest open JPEG 2000 codec is **AGPL** — the performance/licence trade-off in this plane is explicit |

Plus the two new hiding places carried into `repos/foundations.md`: `wolfgangw/backports` licensed by
**`gpl.txt`** (GPL-3.0, missed by a 14-name probe) and `cth103/libsub` licensed **only in 73 source
headers** (GPL-2.0+). The second one **reversed a verdict mid-pass** — it was written down as
unlicensed until a shallow clone showed the headers.

### Measurement note — the probe needed extending for the seventh time, and the oracle changed

- **`curl -sI` does not work against github.com from this session.** The agent proxy answers
  `200 Connection Established` and GitHub's HTML then returns **403** for repos that plainly exist.
  **`git ls-remote` is the existence oracle** — 25/25 this pass — and `raw.githubusercontent.com`
  serves licence files normally (control: 200). Recorded because the standing instruction to verify
  URLs with `curl -sI` would have failed every one of these 25 real repos.
- **Licence-name filenames join the probe** (`gpl.txt`, and by extension `agpl.txt`, `mit.txt`,
  `apache-2.0.txt`). The probe now covers 15 names across two branches and **still** needs a shallow
  clone as the fallback, because a per-file-header licence cannot be found over HTTP at all.
- **The 422 rename detector holds but does not self-diagnose**: `gh api repos/<slug>` answers
  `403 "not enabled for this session"` for a renamed repo, which reads like a scope problem. Resolve
  with an **unqualified keyword search**, not the repos endpoint.

---

## 2026-11-26 — pass 9: the trust & safety infrastructure (62 verified repos, 62/62 resolved)

The enforcement substrate under the minor-protection, illegal-content and transparency duties this
KB has described in prose since pass 2 without naming a tool. **62/62 URLs resolve by
`git ls-remote`.** Full tables in `repos/foundations.md`; this is what moved and what it means.

### Headline: the healthiest *permissive platform tier* in this KB, and it arrived by donation

Three operators gave away infrastructure they run in production, and that single fact explains the
licence distribution of the whole plane:

| Repo | Licence | ★ / forks | Last push | Donated by |
|---|---|---|---|---|
| [roostorg/osprey](https://github.com/roostorg/osprey) | Apache-2.0 | 511★ / 73f | 2026-11-23 | **Discord** — its production safety rules engine |
| [roostorg/coop](https://github.com/roostorg/coop) | Apache-2.0 | 150★ / 55f | **2026-11-26** | **ROOST** — review console, queues, routing, enforcement rules |
| [conversationai/conversationai-moderator](https://github.com/conversationai/conversationai-moderator) | Apache-2.0 | 208★ / 31f | 2026-06-22 | **Google Jigsaw** |
| [Jigsaw-Code/altitude](https://github.com/Jigsaw-Code/altitude) | Apache-2.0 | 44★ / 11f | 2026-06-21 | **Google Jigsaw** — aimed explicitly at small platforms |
| [meta/content-review-filters](https://github.com/meta/content-review-filters) | Apache-2.0 | 8★ / 6f | 2026-10-24 | **Meta** |
| [bluesky-social/ozone](https://github.com/bluesky-social/ozone) | **dual MIT/Apache-2.0** | 548★ / 94f | 2026-11-23 | **Bluesky** |

[ROOST](https://github.com/roostorg) is new to this KB and is the reason the plane is buildable:
15 repos, Apache-2.0 on code, two flagships pushed this week, and a CC-BY-4.0 directory
([awesome-safety-tools](https://github.com/roostorg/awesome-safety-tools), 274★) that is the only
reliable way to *discover* this plane — generic GitHub search cannot surface an 8-star Meta repo.

### The hash-matching layer — BSD, and the list is the asset

| Repo | Licence | ★ / forks | Last push | Notes |
|---|---|---|---|---|
| [meta/ThreatExchange](https://github.com/meta/ThreatExchange) | **BSD** (file-verified, 1,522 B) | 1,417★ / 368f | 2026-11-19 | PDQ, TMK+PDQF, vPDQ, HMA, `python-threatexchange`. **Renamed from `facebook/ThreatExchange`.** |
| [matrix-org/hma-matrix](https://github.com/matrix-org/hma-matrix) | Apache-2.0 | 8★ / 2f | 2026-11-24 | HMA bound into a real platform. Pushed this week. |
| [c4osl/rocketchatcsam](https://github.com/c4osl/rocketchatcsam) | MIT | 13★ / 1f | 2026-11-05 | Validates uploads against **Microsoft PhotoDNA** — open client, gated service. |
| [jenssegers/imagehash](https://github.com/jenssegers/imagehash) | MIT | 2,060★ / 173f | 2025-09-17 | PHP perceptual hashing. |
| [coenm/ImageHash](https://github.com/coenm/ImageHash) | MIT | 242★ / 27f | 2025-01-08 | .NET, on ImageSharp. |
| [AsuharietYgvar/AppleNeuralHash2ONNX](https://github.com/AsuharietYgvar/AppleNeuralHash2ONNX) | Apache-2.0 | 1,532★ / 124f | 2021-08-21 | Historical: the reverse-engineering that ended Apple's client-side scanning. |

**The three-step gradient across one statutory duty**, measured rather than asserted:
**detect** = BSD and healthy (1,417★, pushed last week) → **obtain the list** = no licence exists,
membership and vetting only (NCMEC / IWF / GIFCT / PhotoDNA) → **report to the authority** =
[ello/ncmec_reporting](https://github.com/ello/ncmec_reporting), **7★, no licence file, dead since
2022-03-29**. Ninth confirmation of the content law, and the most legally loaded instance of it.

### Age verification — nine repos, published by the regulator, two licence shapes

The European Commission shipped the Age Verification Blueprint **as working software**:
[av-app-android-wallet-ui](https://github.com/eu-digital-identity-wallet/av-app-android-wallet-ui)
(**EUPL-1.2**, 309★/52f, 2026-11-07),
[av-app-ios-wallet-ui](https://github.com/eu-digital-identity-wallet/av-app-ios-wallet-ui)
(**EUPL-1.2**, 20★, 2026-10-15),
[av-lib-android-zkp-age-icao](https://github.com/eu-digital-identity-wallet/av-lib-android-zkp-age-icao)
(Apache-2.0, 20★), [av-lib-ios-longfellow-zkp](https://github.com/eu-digital-identity-wallet/av-lib-ios-longfellow-zkp)
(Apache-2.0, 4★, 2026-10-30), [av-srv-web-issuing-avw-py](https://github.com/eu-digital-identity-wallet/av-srv-web-issuing-avw-py)
(Apache-2.0, 5★), [av-web-verifier-ui](https://github.com/eu-digital-identity-wallet/av-web-verifier-ui)
(Apache-2.0, 15★), [av-srv-trust-validator](https://github.com/eu-digital-identity-wallet/av-srv-trust-validator)
(Apache-2.0, 0★), the CC-BY-4.0 [technical specification](https://github.com/eu-digital-identity-wallet/av-doc-technical-specification)
(99★) — and, one star and easy to miss,
[av-verifier-frontend-cinema](https://github.com/eu-digital-identity-wallet/av-verifier-frontend-cinema):
**a cinema age-gate reference frontend written by the regulator**.

**Apps are EUPL-1.2 (copyleft, OSI-approved, legally binding in 23 languages); libraries and servers
are Apache-2.0.** First EUPL-1.2 artifact recorded anywhere in this KB. Embed the ZKP libraries
freely; think hard before shipping a modified fork of the app.

### Platform transparency — the obligation has an open substrate and nobody is watching it

| Repo | Licence | ★ | Last push | Notes |
|---|---|---|---|---|
| [digital-services-act/transparency-database](https://github.com/digital-services-act/transparency-database) | **GPL-2.0** | 55★ / 10f | 2026-11-25 | The Commission's own database code. Copyleft — because the publisher is a public body, not an operator. |
| [afkzonagroup/rationale](https://github.com/afkzonagroup/rationale) | Apache-2.0 | 0★ | 2026-11-22 | SDK for submitting statements of reasons. **Zero stars, four days old at the time of this pass.** |
| [eu-dsa-transparency-db-sor-data-downloader](https://github.com/transparency-in-content-moderation/eu-dsa-transparency-db-sor-data-downloader) | Apache-2.0 | 1★ | 2026-09-14 | Research direction: pulling the data back out. |

### Decentralised moderation — atproto is live, the fediverse side is copyleft and small

[bluesky-social/ozone](https://github.com/bluesky-social/ozone) (dual MIT/Apache-2.0, 548★,
2026-11-23) and [bluesky-social/indigo](https://github.com/bluesky-social/indigo) (Apache-2.0,
1,395★/271f, 2026-11-25) are the reference implementation of **stackable** moderation — third
parties publish labels, users subscribe — which is the only architecture in this plane that does not
assume one platform owns one truth. On Matrix,
[the-draupnir-project/Draupnir](https://github.com/the-draupnir-project/Draupnir) (253★, **pushed
2026-11-26**) has succeeded [matrix-org/mjolnir](https://github.com/matrix-org/mjolnir) (449★,
2026-10-28). The fediverse tooling is smaller and copyleft:
[fedimod/fires](https://github.com/fedimod/fires) (AGPL-3.0, 29★),
[MarcT0K/Fediverse-Spam-Filtering](https://github.com/MarcT0K/Fediverse-Spam-Filtering) (GPL-2.0,
8★), [selfagency/mastodont](https://github.com/selfagency/mastodont) (MIT, 22★), with
[swicg/activitypub-trust-and-safety](https://github.com/swicg/activitypub-trust-and-safety) (51★)
holding the W3C taskforce's documents.

### The adjacent giants — bigger than anything in the plane proper

| Repo | Licence | ★ / forks | Last push | Why it matters to a media client first |
|---|---|---|---|---|
| [data-privacy-stack/presidio](https://github.com/data-privacy-stack/presidio) | MIT | 12,065★ / 1,472f | 2026-11-24 | PII detection and redaction. Subtitles, transcripts and UGC are full of personal data. **Renamed from `microsoft/presidio`.** |
| [NVIDIA/garak](https://github.com/NVIDIA/garak) | Apache-2.0 | 10,186★ / 1,523f | 2026-11-25 | LLM vulnerability scanner — the pre-launch harness for any public generative feature. |
| [microsoft/PyRIT](https://github.com/microsoft/PyRIT) | MIT | 5,088★ / 1,128f | 2026-11-25 | AI red-teaming toolkit. |

### Measurement note — the licence probe needed extending for the sixth time, and in a new direction

Earlier passes extended the probe with lowercase `license.txt` and `COPYING.md`. This pass needed
something different: **a directory**. Draupnir's licences live in `LICENSES/` with per-file SPDX
annotation under **REUSE** (the FSFE/SPDX reuse-compliance standard; `reuse.software` is outside this session's allowed network domains, so the URL is deliberately not linked here — unverified, not dead), and `NVIDIA-NeMo/Guardrails` states
`SPDX-License-Identifier: Apache-2.0` inside a `LICENSE.md` the detector still called
`NOASSERTION`. Standing rule, all twelve industries: **`NONE` or `NOASSERTION` on an actively
pushed repo means check `REUSE.toml`, a `LICENSES/` directory, and the manifest
(`package.json` / `pyproject.toml` / `Cargo.toml`) before concluding anything.** A shallow clone
settles it in one call and is still the cheapest conclusive oracle.

## 2026-11-26 — pass 8: the live & delivery infrastructure (45 verified repos, 45/45 resolved)

### Headline: the first plane in this KB where copyright is not the binding constraint

Seven planes, one gate, always copyright — on the code or on the content. This plane is permissive
almost everywhere in copyright and gated instead by **two non-copyright instruments**: patent pools
and DRM key agreements. Neither is visible in a licence badge.

**Gate 1 — the codecs refuse to grant patents, in writing.** `BSD-3-Clause-Clear` / "The Clear BSD
License": the *Clear* **is** the patent carve-out.

| Codec | Repo | Licence | Stars | Push |
|---|---|---|---|---|
| VVC encoder | https://github.com/fraunhoferhhi/vvenc | BSD-3-Clause-Clear | 1,228 | 2026-11-25 |
| VVC decoder | https://github.com/fraunhoferhhi/vvdec | BSD-3-Clause-Clear | 573 | 2026-11-24 |
| LCEVC decoder | https://github.com/v-novaltd/LCEVCdec | The Clear BSD License | 35 | 2026-10-27 |
| MPEG-H 3D Audio decoder | https://github.com/Fraunhofer-IIS/mpeghdec | Fraunhofer FDK — §3 **"No PATENT LICENSE"** | 100 | 2026-07-24 |
| AV1 (production) | https://github.com/AOMediaCodec/SVT-AV1 | BSD-3-Clause-Clear | 131 | 2026-11-23 |
| AV1 (Rust) | https://github.com/xiph/rav1e | BSD-2-Clause | 4,167 | 2026-11-25 |
| **Quality metric (control case)** | https://github.com/Netflix/vmaf | **BSD-2-Clause-Patent — express patent grant** | 5,660 | 2026-11-16 |

VMAF proves the pattern is deliberate: same era, same culture, **opposite** licence — because VMAF is
unpooled and VVC/LCEVC/MPEG-H are pooled. The licence tracks the patent pool.

**Gate 2 — the key is the gate.** Packaging and CENC encryption are fully open
(`shaka-project/shaka-packager`, BSD-3-Clause, 2,673★). The key/licence server for Widevine,
PlayReady and FairPlay is not available as open source at all: each needs its own endpoint and
key-delivery protocol under a signed agreement (Google partner programme + Master Licence Agreement
and security questionnaire; a Microsoft agreement for any PlayReady service provider; Apple's
developer agreement for FairPlay). **ClearKey is the only fully-open DRM and no studio accepts it.**

### ⛔ Sixth distinct way a licence hides — on the most-recommended DRM packaging tool

`https://github.com/axiomatic-systems/Bento4` — API reports **`NONE`**. Reality: **GPL-2.0 with a
paid commercial alternative**, text at **`Documents/LICENSE.txt`** (18,693 B), one directory below
root where no scanner reads it. Link it into a proprietary packager and you have shipped GPL
obligations or you owe Axiomatic a fee. Taxonomy now: HTML file / packaging classifier / compile
flags / modified-Apache-same-name / PDF / **non-root path**.

### A seventh shape: a standards body minted its own licence

`https://github.com/5G-MAG/rt-libflute` — **5G-MAG Public License v1.0**, Apache-2.0 in structure and
wording with the patent grant rewritten: §3.1 licenses Essential Patents "to make, have made, use,
and otherwise transfer **(excluding selling)** … **solely for study, testing and research
purposes**"; §3.2 grants nothing for any other purpose and instead requires that "**You commit to be
prepared to negotiate**" FRAND terms with every contributor. A field-of-use restriction on selling
means **this is not open source** by the OSI definition — and it governs the reference stack for
5G Broadcast/MBMS, exactly what an EMEA public broadcaster would pilot.

### Contribution — and APAC owns the permissive substrate here

| Repo | Licence | Stars | Push | Origin |
|---|---|---|---|---|
| https://github.com/ossrs/srs | MIT | 29,457 | 2026-11-25 | **China** |
| https://github.com/bluenviron/mediamtx | MIT | 20,772 | 2026-11-25 | — |
| https://github.com/ZLMediaKit/ZLMediaKit | MIT *(read)* | 17,729 | 2026-11-25 | **China** |
| https://github.com/pion/webrtc | MIT | 16,926 | 2026-11-25 | — |
| https://github.com/Haivision/srt | MPL-2.0 | 3,640 | 2026-11-25 | — |
| https://github.com/obsproject/obs-studio | GPL-2.0 | 80,138 | 2026-11-26 | — |
| https://github.com/livekit/livekit | Apache-2.0 | 22,396 | 2026-11-25 | — |
| https://github.com/Eyevinn/whip | Apache-2.0 | 150 | 2026-06-09 | **Sweden** |
| https://github.com/Eyevinn/srt-whep | Apache-2.0 | 145 | 2026-10-31 | **Sweden** |

**The two most-starred self-hosted streaming servers on earth are both China-origin and both MIT.**
That inverts the pattern in every other plane of this KB, where the permissive layer is
Western-origin. Here APAC owns it outright.

### The platform tier breaks this KB's "copyleft at the platform" law — twice

| Repo | Licence | Stars | Push |
|---|---|---|---|
| https://github.com/OvenMediaLabs/OvenMediaEngine | AGPL-3.0 (obeys) | 3,309 | 2026-11-25 |
| https://github.com/DDVTECH/mistserver | **Unlicense — public domain** | 521 | 2026-11-23 |
| https://github.com/ant-media/Ant-Media-Server | **no root LICENSE** — open-core | 4,747 | 2026-11-23 |

MistServer's `COPYING.md`: "dedicated to the public domain… anyone can use MistServer for any
purpose - including commercial purposes - without any restrictions." A platform-tier streaming server
with **zero** obligations, and at 521★ almost nobody has noticed. Ant Media returned 404 across six
filename probes while `README.md` returns 200 and sells an Enterprise Edition — source-available;
get terms in writing.

### Packaging, players, and the compile-flag licence category confirmed twice

| Repo | Licence | Stars | Push |
|---|---|---|---|
| https://github.com/shaka-project/shaka-packager | BSD-3-Clause *(read)* | 2,673 | 2026-11-04 |
| https://github.com/gpac/gpac | LGPL-2.1 | 3,331 | 2026-11-24 |
| https://github.com/Eyevinn/mp4ff | MIT | 669 | 2026-11-24 |
| https://github.com/videojs/video.js | Apache-2.0 *(read)* | 40,253 | 2026-11-25 |
| https://github.com/video-dev/hls.js | Apache-2.0 *(read)* | 17,066 | 2026-11-23 |
| https://github.com/shaka-project/shaka-player | Apache-2.0 | 8,289 | 2026-11-25 |
| https://github.com/Dash-Industry-Forum/dash.js | **BSD-3 + explicit patent non-grant** *(read)* | 5,555 | 2026-11-24 |
| https://github.com/FFmpeg/FFmpeg | **LGPL-2.1+, GPL by build flag** *(read)* | 68,197 | 2026-11-25 |

FFmpeg joins Chromaprint (pass 5) as the **second** instance of a licence decided by the compile, so
that category is now a pattern. Audit build flags, not just the dependency list. And dash.js — the
*reference DASH player* — states that no patent rights are granted: Gate 1 reaching the last mile.

### Media over QUIC — the first new media transport since this KB began, and it is permissive

Not yet an RFC: `draft-ietf-moq-transport` is Standards-Track Internet-Draft (-22, 1 Oct 2026); the
IESG publication-request milestone is **2026-12-31**. Eleven vendors interoperated at NAB 2026; the
MoQ Alliance includes Akamai, AWS, Cisco, Cloudflare, Fastly. LOC container milestone: March 2027.

| Repo | Licence | Stars | Push | Origin |
|---|---|---|---|---|
| https://github.com/moq-dev/moq | Apache-2.0 | 1,642 | **2026-11-26** | reference (ex-`kixelated/moq-rs`) |
| https://github.com/facebookexperimental/moxygen | Apache-2.0 | 127 | 2026-11-25 | Meta — NA |
| https://github.com/Quicr/libquicr | BSD-2-Clause | 21 | 2026-11-25 | Cisco — NA |
| https://github.com/mengelbart/moqtransport | MIT | 91 | 2026-09-16 | academic — EMEA |
| https://github.com/nttcom/moq-wasm | MIT | 57 | 2026-11-25 | **NTT — APAC** |
| https://github.com/kixelated/moq-js | `NONE` | 154 | **ARCHIVED 2025-06-20** | do not start here |

All four regions are already in the implementer set, the implementations are permissive, and the
standard is still open to influence. Pilot in 2026, production expected 2027 — early, not late.
Honest caveat: ad insertion only partially supported, VOD unresolved. It does not replace HLS/DASH.

### Edge and CDN — and a relocation this pass deliberately did not over-claim

| Repo | Licence | Stars | Push |
|---|---|---|---|
| https://github.com/apache/trafficserver | Apache-2.0 | 2,001 | 2026-11-25 |
| https://github.com/varnishcache/varnish-cache | BSD-2-Clause | 4,040 | **ARCHIVED 2026-02-16** |
| https://github.com/rdkcentral/Thunder | Apache-2.0 | 61 | 2026-11-25 |
| https://github.com/tvheadend/tvheadend | GPL-3.0 | 3,587 | 2026-11-25 |
| https://github.com/jellyfin/jellyfin | GPL-2.0 | 59,765 | 2026-11-25 |

Varnish's GitHub repo is archived and its own `README.rst` says "THIS REPOSITORY HAS MOVED" to
`code.vinyl-cache.org`, with `master`→`main` and a `last` tag. **Neither `code.vinyl-cache.org` nor
`vinyl-cache.org` resolved from this environment (`curl` → `000`)**, which may be egress policy
rather than absence. So: don't start new work from the GitHub repo, and **don't tell a client the
project is dead.** Apache Traffic Server is the verified-active permissive alternative.

### Measurement note

`librist` — the standards-based (VSF) RIST contribution reference — lives on `code.videolan.org`
(GitLab), so it is invisible to GitHub-based discovery including this KB's own oracle. Recorded as an
informed gap, not an absence. Second plane in which the canonical implementation is off-GitHub.

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

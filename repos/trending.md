---
industry: media
region: Global
updated: 2026-11-27
---

# 📈 Trending Media Repos — append-only log

> Newest section first; history below is never rewritten.
> Distinct from `agents/trending.md`: this file tracks **infrastructure and platform** repos.
> (Until this pass the two files were byte-identical — that defect is fixed here.)

## 2026-11-27 — pass 43: composition-side infrastructure (**no maintained permissive OMR engine exists**)

Infrastructure and platform movement for the composition-side plane — lyrics, chords, score capture,
publishing rights. The agent/model layer, the JASRAC per-element finding and the false friends are in
`agents/trending.md` for the same date.

**The measurement, GitHub search API, 2026-11-27, existence via `git ls-remote` (29/29 resolve),
every `NOASSERTION` resolved by reading the licence file.** This is the pass's primary artefact,
because the licence distribution — not the star counts — is what decides whether any of it is usable.

| Repo | Licence | Stars | Last push | Status |
|---|---|---|---|---|
| `tranxuanthang/lrcget` | MIT | 3,392 | 2026-11-20 | Alive — most-starred in the plane |
| `Audiveris/audiveris` | AGPL-3.0 | 3,019 | 2026-11-25 | Alive — reference OMR engine |
| `tranxuanthang/lrclib` | MIT | 2,314 | 2026-11-10 | Alive — the open synced-lyrics server/corpus |
| `CoderLine/alphaTab` | MPL-2.0 (file) | 1,951 | 2026-11-26 | Alive — notation + tablature rendering |
| `helge17/tuxguitar` | LGPL-2.1 (`docs/LICENSE`) | 1,666 | 2026-11-26 | Alive — tablature editor |
| `UltraStar-Deluxe/USDX` | GPL-2.0 | 1,320 | **2026-11-27** | Alive — pushed the day of this pass |
| `johnwmillr/LyricsGenius` | MIT | 1,130 | 2026-11-22 | Alive |
| `cifkao/html-midi-player` | BSD-2-Clause | 914 | 2025-07-06 | Dormant ~1.4 yr |
| `aashrafh/Mozart` | Apache-2.0 | 716 | 2022-08-24 | **Dead 4 yr** — permissive OMR |
| `performous/performous` | GPL-2.0-or-later (file) | 650 | 2026-11-26 | Alive |
| `MahmoudAshraf97/ctc-forced-aligner` | BSD-2-Clause | 579 | 2026-11-24 | Alive |
| `ChordPro/chordpro` | **Artistic-2.0** (file) | 549 | 2026-11-21 | Alive |
| `moehmeni/syncedlyrics` | MIT | 526 | 2024-07-28 | Dormant ~2.3 yr |
| `liebharc/homr` | AGPL-3.0 | 497 | **2026-11-27** | Alive — pushed the day of this pass |
| `apacha/OMR-Datasets` | MIT | 402 | 2024-04-01 | Dormant ~2.6 yr — the training corpus |
| `Vocaluxe/Vocaluxe` | GPL-3.0 | 343 | 2026-11-20 | Alive |
| `yuma-m/pychord` | MIT | 292 | 2026-11-25 | Alive |
| `ohollo/chord-extractor` | GPL-2.0 | 248 | 2025-08-14 | Dormant ~1.3 yr |
| `jayg996/BTC-ISMIR19` | MIT | 222 | 2020-05-23 | **Dead 6 yr** |
| `quelea-projection/Quelea` | GPL-3.0 | 207 | 2026-11-24 | Alive — 161 forks on 207 stars |
| `antoniorv6/SMT` | MIT | 90 | 2026-09-27 | Slow — permissive OMR research line |
| `OMR-Research/MeasureDetector` | MIT + Apache-2.0 (split by directory) | 53 | 2026-06-14 | Slow |
| `BreezeWhite/oemer` | **MIT template, unfilled** | *not indexed* | HEAD 2025-04-18 | Dormant + licence-unresolved |

**What the table says when you sort it by licence instead of stars.** Maintained OMR: Audiveris
(AGPL-3.0, 2026-11-25) and homr (AGPL-3.0, 2026-11-27). Permissive OMR: oemer (2025-04-18, and its
licence names no holder), Mozart (2022-08-24), OMR-Datasets (2024-04-01), MeasureDetector
(2026-06-14), SMT (2026-09-27). **Every maintained engine is copyleft; every permissive one is
dormant.** Score capture is therefore an architecture decision with a licence consequence, and there
is no third option today.

The karaoke platforms repeat it: USDX (GPL-2.0), Performous (GPL-2.0+), Vocaluxe (GPL-3.0) — all
maintained, all copyleft. Projection: Quelea (GPL-3.0). The **permissive** half of this plane is the
*library* layer — lrcget/lrclib (MIT), alphaTab (MPL-2.0), pychord (MIT), the aligners (BSD-2/MIT) —
and the alignment tools are permissive mainly because they are shared with the speech plane (p7),
not because anyone built them for music.

**One licence to flag, not wave through:** `ChordPro` is **Artistic-2.0** — the first appearance of
that licence anywhere in this KB. OSI-approved and permissive in practice, but outside Globant's
MIT/Apache/BSD set; send it to review.

**Three `NOASSERTION` repos resolved to real licences by reading files** — alphaTab (MPL-2.0, stated
in a 16,907 B composite `LICENSE`), tuxguitar (**LGPL-2.1, filed in `docs/LICENSE`** — a new location
for this KB's probe list), performous (GPL-2.0-or-later in `LICENSE.md`). A root-only scanner reports
all three as unlicensed. **A `NOASSERTION` is never, by itself, evidence that a licence is missing.**

**The money layer, measured the same day:** `mechanical royalty` 13 results / relevant top-six **0★**;
`music royalty accounting` 14 results / **4★**; `music publishing rights` 16 results / 5★;
`lyrics sync licensing` **1 result / 0★**. Pass 8's 0★ measurement on the second query reproduces
five days later with a wider query set. Two of the publishing-rights hits are 0★ repos advertising
"Free AI-powered music distribution" — SEO slop occupying the surface of a real commercial function.

**Not on GitHub, so not listed:** OpenLP, the largest open lyric-projection application. Searched by
name; every result was a fork, a converter or an unrelated church-display project. Its upstream lives
elsewhere. **`openlyrics/openlyrics`** (35★) has **no licence file** under nine names on `master`
while `README.txt` returns 200 — control test passes, so the absence is real; dormant since
2022-02-20. Specification, not dependency.

## 2026-11-27 — pass 42: archive-monetisation infrastructure (**the sell-side measured at four repos holding one star**)

Infrastructure and platform movement for the archive-monetisation plane. Agent-side movement and the
186× adoption ratio are in `agents/trending.md` for the same date.

**The measurement, GitHub search API, 2026-11-27, `sort=stars`.** This is the pass's primary artefact,
because the interesting number is a zero and zeros have to be measured to count:

| Query | Repos | Top-6 stars | Relevant |
|---|---|---|---|
| `stock footage licensing` | **4** | 1, 0, 0, 0 | **none** |
| `footage marketplace` | 18 | 3, 3, 1, 0, 0, 0 | none |
| `media licensing marketplace` | 6 | 83, 79, 55, 0, 0, 0 | **none — top three are junk repos** |
| `rights clearance` | 40 | 2, 2, 1, 1, 1, 1 | none |
| `archive monetization` | 21 | 176, 7, 2, 1, 1, 1 | none |
| `clip licensing` | 47 | 327, 153, 146, 95, 77, 23 | **none — FTC robotics, smartwatch firmware, Windows policy** |
| `shot search video` | 52 | 27, 18, 8, 8, 7, 6 | **one** — shotit/shotit (Apache-2.0) |

`clip licensing` and `media licensing marketplace` are the sharpest **false friends** recorded in this
KB to date: 47 results that are entirely unrelated, and an 83-star "leader" that is a junk repo. Cycle
8's rule — *read the results, never the total* — would have been violated six times over by a pass
that trusted these counts.

**Infrastructure added to `repos/foundations.md` this pass:** TransNetV2 (MIT, shot cutting), hecate
(Apache-2.0, keyframes/previews), croissant (Apache-2.0, dataset metadata + licence + provenance),
openverse (MIT, licence-aware media search, pushed today), vespa (Apache-2.0, embeddings + metadata in
one query, pushed today), free-for-creators (CC0-1.0, licence metadata as a tested field). **Six for
six permissive.**

**New licence pathology, logged here because it is a CI rule and not a media fact.**
[resourcespace/resourcespace](https://github.com/resourcespace/resourcespace) (96★, pushed today)
reports **`NOASSERTION`**. Verified by shallow clone this pass: `LICENSE`/`LICENSE.md`/`COPYING`/
`COPYING.md`/`LICENCE` all 404; `license.txt` is **76 bytes of pointer** ("see the documentation/licenses
folder"); that folder holds **30 files of which 29 are other projects' licences** — including
`jquery-image-annotation.txt`, **29,880 B of GPL-2.0**. The real grant is the 30th file,
`documentation/licenses/resourcespace.txt`: **BSD-3-Clause plus a trademark clause** forbidding
"ResourceSpace" in a derived product's name.

**Worse than pass 8's Chromaprint case for exactly one reason:** there, no SPDX field *could* see the
truth. Here a scanner that globs the licence folder gets a **confident wrong answer** — Apache-2.0 or
MIT, depending on read order — while missing both the trademark restriction and the copyleft component.
**Rule, generalising to all twelve industries:** a 200 at the licence path is no more proof you found
the grant than a 404 is proof one is missing. If the file points at a folder, the folder answers a
different question; find the file bearing the project's own name.

## 2026-11-27 — pass 41: content-protection & soft-binding infrastructure (**an entire standards layer born this month, with 0 to 3 stars per repo**)

Infrastructure and platform layer beneath the agents logged in `agents/trending.md`. Verified
2026-11-27: `git ls-remote` for existence, raw-channel fetch of the licence file for **licence by
bytes** (13 candidate filenames × 2 branches), and `search/repositories` with `repo:<slug>` for
stars/forks/pushed in one call each.

**The headline is a date distribution, not a repo.** The C2PA soft-binding *resolution* layer — the
infrastructure that turns a registered algorithm identifier into an actual manifest lookup — is being
built right now, in public, by near-anonymous repos. Of the 13 repos matching `c2pa soft binding`,
**eleven were pushed in November 2026** and the largest holds **3 stars**:

| Repo | Licence (by bytes) | ★ | Forks | Pushed | What it is |
| --- | --- | --- | --- | --- | --- |
| [c2pa-org/softbinding-algorithm-list](https://github.com/c2pa-org/softbinding-algorithm-list) | **CC-BY-4.0** (18,650 B) | 37 | 41 | 2026-11-25 | **The registry itself** — 80 approved algorithm identifiers. Forks (41) **exceed** stars (37), ratio 0.9: this is a *contribution* repo, not a consumption repo. Every entry arrives as a PR. |
| [contentauth/c2pa-rs](https://github.com/contentauth/c2pa-rs) | **dual MIT + Apache-2.0** | 456 | 206 | 2026-11-26 | The reference Rust SDK. **The API reports `NOASSERTION`; the bytes are `LICENSE-MIT` (1,083 B) *and* `LICENSE-APACHE` (11,335 B).** The most permissive arrangement available, mislabelled. |
| [contentauth/c2patool](https://github.com/contentauth/c2patool) | Apache-2.0 | 175 | 48 | 2026-11-26 | The CLI. The practical entry point for signing and inspecting manifests. |
| [contentauth/c2pa-python](https://github.com/contentauth/c2pa-python) | Apache-2.0 | 110 | 40 | 2026-11-25 | Python binding over `c2pa-rs`. |
| [c2pa-org/specifications](https://github.com/c2pa-org/specifications) | CC-BY-4.0 | 216 | 34 | 2026-11-25 | The published spec. **CC-BY-4.0 on the document — use the spec, which is the correct move in this plane.** |
| [c2pa-org/conformance-public](https://github.com/c2pa-org/conformance-public) | CC-BY-4.0 | 52 | 25 | 2026-11-26 | The conformance programme. The gate between "implements C2PA" and "may claim C2PA". |
| [Original-Pictures/soft-bindings-benchmark](https://github.com/Original-Pictures/soft-bindings-benchmark) | **Apache-2.0** (11,358 B) | **0** | 1 | 2026-11-07 | **The most strategically interesting repo in the pass.** An open-licence benchmark of invisible watermarks and fingerprints *as C2PA soft bindings* — and it is from the registrant holding **12 of the 80 registry entries**. Zero stars. |
| [beomjin-ahn/provsurvive](https://github.com/beomjin-ahn/provsurvive) | **MIT** (1,081 B) | 2 | 0 | 2026-11-14 | Benchmark harness for provenance survival under image edits. The independent counterpart to the above. |
| [deepmark/c2pa-soft-binding-stack](https://github.com/deepmark/c2pa-soft-binding-stack) | **MIT** (1,065 B) | 3 | 1 | 2026-11-24 | An implementation of the **Soft Binding Resolution API** — one of only a handful anywhere. Registry entry `me.deepmark.audio.vigil.128` with a live endpoint. |
| [iscc/iscc-c2pa-resolver](https://github.com/iscc/iscc-c2pa-resolver) | **Apache-2.0** (11,358 B) | 0 | 0 | **2026-11-27** | Resolution API for ISCC (`io.iscc.v0`). **Pushed on measurement day.** |
| [iscc/iscc-c2pa-store](https://github.com/iscc/iscc-c2pa-store) | Apache-2.0 | 0 | 0 | 2026-11-21 | A **Manifest Repository** with a resolution API — the storage half of the lookup. |
| [writerslogic/c2pa-text-binding](https://github.com/writerslogic/c2pa-text-binding) | Apache-2.0 **+** dual MIT/Apache | 0 | 1 | 2026-11-16 | Soft binding and fingerprinting for **text**. Holds 6 of the registry's 7 text entries. |
| [Cognitive-Proof/c2pa-soft-binding-server](https://github.com/Cognitive-Proof/c2pa-soft-binding-server) | MIT | 0 | 0 | 2026-11-16 | Resolution server. Registry entry `com.cognitive-proof.vsrmark.1`. |

**The measured gap, and it is the build:** **13 of the 80 approved algorithms declare a resolution
API endpoint.** The other 67 are *names without lookups* — a soft binding that identifies an
algorithm nobody can query recovers no manifest, so the registry is filling roughly five times faster
than the infrastructure that makes it function. The spec for the missing half is public
(C2PA Soft Binding Resolution API, Decoupled, spec 2.5) and the two reference implementations above
are Apache-2.0 and MIT.

**Marking substrate, re-measured 2026-11-27 (licence by bytes in every row):**

| Repo | Licence | ★ | Forks | Pushed | Status change vs this KB |
| --- | --- | --- | --- | --- | --- |
| [facebookresearch/videoseal](https://github.com/facebookresearch/videoseal) | **MIT** (1,087 B) | 829 | 111 | 2026-11-10 | Already in KB. **Alive and separate** — see the oracle note below. |
| [facebookresearch/content-seal](https://github.com/facebookresearch/content-seal) | **MIT** (1,086 B) | 243 | 17 | 2026-11-05 | **New to this KB.** Meta's current umbrella framework (Pixel Seal, Video Seal, TextSeal). |
| [facebookresearch/audioseal](https://github.com/facebookresearch/audioseal) | **MIT, weights included** | 808 | 109 | 2026-11-03 | Already in KB — **with a licence fact the KB did not record**, below. |
| [facebookresearch/watermark-anything](https://github.com/facebookresearch/watermark-anything) | MIT | 1,133 | 56 | 2025-06-20 | Already in KB. **17 months dormant** — the most-starred marker in the family is the least maintained. |
| [adobe/trustmark](https://github.com/adobe/trustmark) | **MIT** (1,218 B) | 191 | 41 | 2026-11-11 | Already in KB, correctly as MIT. API still says `NOASSERTION`. Holds 4 registry entries (`trustmark.Q/C/P/F`). |
| [eluv-io/blind-video-watermark](https://github.com/eluv-io/blind-video-watermark) | **MIT** (1,063 B) | 109 | 18 | 2022-08-11 | **New to this KB.** Dormant 4 years. |
| [resemble-ai/Perth](https://github.com/resemble-ai/Perth) | MIT | 547 | 51 | 2026-09-02 | Already in KB. |
| [swesterfeld/audiowmark](https://github.com/swesterfeld/audiowmark) | **GPL-3.0** (35,149 B) | 605 | 119 | 2026-09-23 | Already in KB. Copyleft — the licence gate matters for a shipped product. |
| [syvaidya/openstego](https://github.com/syvaidya/openstego) | **GPL-2.0** | 1,452 | 244 | 2023-08-12 | **New to this KB.** Frequently recommended in vendor round-ups as the open option; **it is steganography, dormant since 2023, and GPL-2.0.** Do not carry it into a forensic proposal. |

**A licence fact worth recording because it is the exception that proves the pass-39 law is a
*choice*.** Pass 39 established "the code is permissive, the weights are not," six times in one
plane. Here, one lab went the other way and said so in its own README: AudioSeal, **2024-04-02** —
*"We have updated our license to full MIT license (**including the license for the model weights**)!
Now you can use AudioSeal in commercial application too!"* That is the only unambiguous
weights-included permissive grant in this plane, and it is measurably why third parties could
register it as a C2PA algorithm. **The law still holds for its sibling:** `content-seal`'s README
licenses *"The code"* under MIT, says nothing about weights, and notes the production system
("Muse Image") is **a custom proprietary implementation**. So the marker you can download is the
research version; the one Meta runs is not in the repo.

**METHOD CORRECTION — A NEW LIMIT ON THIS KB'S OWN EXISTENCE ORACLE, AND IT IS THE FIRST TIME THIS
HAS BEEN CAUGHT.** This KB's standing rule is "`git ls-remote` is the only oracle of existence."
That is still true, but it is **not an oracle of canonical identity**: `git ls-remote
https://github.com/facebookresearch/videoseal` succeeds, and so does `content-seal`, because GitHub
serves renamed and redirected slugs transparently. A success therefore cannot distinguish *live
repo* from *redirect to a renamed repo* — which would silently create duplicate KB rows for one
project. **The cheap, conclusive test is to compare `HEAD` SHAs:**

```
videoseal    f12875a9b5e711e0c6e2dc3a22aca18231ce4a1a
content-seal b93b1a44dea8b32a88e22672d96072a2e0c72bae   → DIFFERENT SHAs = two distinct live repos
```

This pass began with the hypothesis that `videoseal` had been renamed to `content-seal`; the SHA test
**falsified it in one call**, and both rows above are correct as a result. `curl -sI` on the repo page
returns **403 through this session's proxy**, so it cannot be used for the redirect check — the SHA
comparison is the method that works here. **Add to the gate: when two slugs look like the same
project, compare HEAD SHAs before writing either row.**

**EIGHTH FALSE NEGATIVE OF `search/repositories`, AND THE FIRST ONE THAT POINTS THE OTHER WAY.** The
KB's counter stood at seven. `contentauth/c2pa-rs` — the reference SDK of the entire provenance
standard — reports `NOASSERTION` because it carries **two** licence files (`LICENSE-MIT` +
`LICENSE-APACHE`). Every prior instance in this KB had `NOASSERTION` concealing something *worse*
than advertised (PacBio's proprietary EULA, R stubs). Here it conceals the **best possible** outcome:
a dual permissive grant. **The corrected rule is symmetric — `NOASSERTION` means "unmeasured in both
directions," never "non-permissive."** `adobe/trustmark` is the same shape: 1,218 B of Adobe
"All Rights Reserved" header followed by the full, unmodified MIT text. A gate that auto-rejects
`NOASSERTION` would have discarded both the standard's SDK and its best image watermarker.


## 2026-11-27 — pass 40: puzzles & games-desk infrastructure (**twelve active archive repos, zero licences — and no permissive word data in Spanish or Portuguese at all**)

Infrastructure and data layer under the engines logged in `agents/trending.md`. Verified 2026-11-27
by `git ls-remote --symref` + `--bare --depth 1 --filter=blob:none` clone for last-push + licence
file read for bytes. Org sweep via `gh api -X GET search/repositories` (the sanctioned search
channel; REST is 403 here).

**The headline defect of the plane: the digitisation effort is live and legally unusable.** The
[Every Puzzle Project](https://github.com/EveryPuzzleProject) supplies the public-domain puzzles the
corpus publishes — **12 repositories, every one pushed this month, every one at 0 stars, not one
carrying a licence file**:

| Repo | Licence | Last push | Scope |
|---|---|---|---|
| [census](https://github.com/EveryPuzzleProject/census) | **none** | 2026-11-25 | Every publication that ever printed a crossword |
| [games](https://github.com/EveryPuzzleProject/games) | **none** | 2026-11-26 | Every crossword in GAMES magazine, 1977 on |
| [blitz](https://github.com/EveryPuzzleProject/blitz) | **none** | 2026-11-26 | Restoring old crosswords from scans with donated LLM usage |
| [judge](https://github.com/EveryPuzzleProject/judge) | **none** | 2026-11-20 | *Judge* magazine 1924–1939 — the source of the corpus's public-domain tier |
| [afroamerican](https://github.com/EveryPuzzleProject/afroamerican) | **none** | 2026-11-19 | Baltimore Afro-American, Dec 1924 – Mar 1925 |
| [pittsburghcourier](https://github.com/EveryPuzzleProject/pittsburghcourier) | **none** | 2026-11-19 | Pittsburgh Courier, 1925–27 |
| [journalandguide](https://github.com/EveryPuzzleProject/journalandguide) | **none** | 2026-11-19 | Norfolk Journal and Guide, 1925 |
| [bell](https://github.com/EveryPuzzleProject/bell) | **none** | 2026-11-16 | Bell Syndicate 1924–25: which papers carried it |
| [bostonglobe](https://github.com/EveryPuzzleProject/bostonglobe) | **none** | 2026-11-07 | Boston Globe crosswords since 1917 |

Not the usual failure in this KB (a dead project with a clean licence) but its inverse: **a live,
careful, well-documented project with no licence at all**. No licence = all rights reserved. A PR
adding CC0 or CC-BY converts a dozen archives — including the concentrated record of early
**Black-press** crosswords — from unusable to usable. Cheapest high-leverage contribution in the plane.

**The word substrate, and the sharpest regional asymmetry this KB has measured:**

| Repo | Language | Licence | Last push | Note |
|---|---|---|---|---|
| [dwyl/english-words](https://github.com/dwyl/english-words) | English | **Unlicense / public domain** | 2025-01-06 | Commercial use explicit |
| [tabatkins/wordle-list](https://github.com/tabatkins/wordle-list) | English | MIT | 2022-09-06 | Guessable-word list |
| [vocably/es](https://github.com/vocably/es) | Spanish | **AGPL-3.0** | 2026-11-21 | Active; vocabulary + translations, not a crossword list |
| [pythonprobr/palavras](https://github.com/pythonprobr/palavras) | Portuguese (BR) | MPL-2.0 | 2019-07-15 | LibreOffice **speller** list; its own docs warn of proper/city names |
| [javierarce/palabras](https://github.com/javierarce/palabras) | Spanish | **none** | 2014-07-18 | Unlicensed, 12 years dormant |
| [m0nt4ld0/crucigrama](https://github.com/m0nt4ld0/crucigrama) | Spanish | **none** | 2026-04-04 | Recent generator, unlicensed |
| [dm03514/open-dictionaries](https://github.com/dm03514/open-dictionaries) | Spanish | **none** | 2013-02-09 | Exists because its author found no good open Spanish dictionaries |

**English has a public-domain word substrate. Spanish and Portuguese have none** — three of five
assets unlicensed, one AGPL, one MPL, **zero permissive**, not one of them a *crossword* list rather
than a speller or vocabulary set, and **no Spanish or Portuguese clue corpus exists at all**.
Searched in both languages on 2026-11-27: measured absence, not an unexamined one. This is the
LATAM build that compounds (`compose/patterns.md`, Pattern 72).

**The corpus layer — the most carefully documented content-rights position in this KB.**
[century-arcade/xd](https://github.com/century-arcade/xd) (MIT code, pushed 2026-11-25) publishes
**no in-copyright puzzles**; the full corpus is a **private** repo; three tiers govern release —
public full content (out of copyright: **459** pre-1931 puzzles + **227** *Judge* 1931–39 cleared by
renewal check), public **derived** data under the rule "*nothing we publish lets a copyrighted
puzzle be rebuilt*", and a **gated** 1,000-puzzle sample approved by name on Hugging Face. The
renewal check cuts both ways and is a release gate: the NYT renewed **every** issue 1942–63, so
**5,267 puzzles stay under copyright until 2037–2058**, and an earlier `puzzles-pre1965` release had
published them in error — documented, dated, with the maintainers deciding what to do.

**Rights reservation, stated by the declarer.** `docs/AI.md`: terms are attached "as signals: fields
on the Hugging Face dataset card, and machine-readable training opt-outs where the venue supports
them. **They are terms we ask people to honor, not locks**" — asking that derived data not be used
"to build systems that generate crosswords or clues for publication", conceding that the public clue
file "has already been used to train crossword-solving models", and declining to overclaim on
public-domain puzzles: "we cannot restrict them and do not pretend to." Pass 5's **declare → honour →
settle** gradient, in the rights-holder's own words. Sixth confirmation, first from their side.

**Formats:** `.puz` (legacy, binary, proprietary origin) has the maintained library —
[puzpy](https://github.com/alexdej/puzpy) MIT 2026-11-22. `.ipuz` (the open JSON standard) has the
dormant one — [svisser/ipuz](https://github.com/svisser/ipuz) MIT **2021-03-20**. Conversion across
both: [kotwords](https://github.com/jpd236/kotwords) Apache-2.0 2026-11-26. Validation: `xdlint.py`,
stdlib-only, published rule catalogue.

## 2026-11-27 — pass 39: digitisation infrastructure (**the two formats every national programme mandates are published from repos with no licence at all**)

Infrastructure half of pass 39. Figures from `search/repositories` with `repo:` qualifiers on
2026-11-27; existence from `git ls-remote`; every `NOASSERTION`/`NONE` resolved by reading the file.

### The institutional toolchain — this is where the plane's real infrastructure lives

| Repo | Licence | Stars | Forks | Last push | Role |
|---|---|---|---|---|---|
| [tesseract-ocr/tesseract](https://github.com/tesseract-ocr/tesseract) | Apache-2.0 | 77,680 | 10,917 | 2026-11-26 | The substrate. Still the engine inside the national pipelines. |
| [ocrmypdf/OCRmyPDF](https://github.com/ocrmypdf/OCRmyPDF) | MPL-2.0 | 35,414 | 2,468 | 2026-11-27 | Adds a text layer to existing PDFs — the exact shape of the LATAM problem below. |
| [mittagessen/kraken](https://github.com/mittagessen/kraken) | Apache-2.0 | 1,114 | 178 | 2026-11-21 | HTR engine for historical print and manuscript. |
| [qurator-spk/eynollah](https://github.com/qurator-spk/eynollah) | Apache-2.0 | 417 | 38 | 2026-11-13 | Newspaper/periodical layout analysis. |
| [UB-Mannheim/ocr-fileformat](https://github.com/UB-Mannheim/ocr-fileformat) | MIT | 204 | 28 | 2025-05-21 | Converts between hOCR, ALTO, PAGE. The glue nobody budgets for. |
| [OCR-D/core](https://github.com/OCR-D/core) | Apache-2.0 | 137 | 31 | 2026-11-09 | Germany's national OCR programme framework. |
| [OCR-D/ocrd_all](https://github.com/OCR-D/ocrd_all) | MIT | 73 | 17 | 2025-07-04 | The assembled OCR-D toolchain. |
| [qurator-spk/dinglehopper](https://github.com/qurator-spk/dinglehopper) | Apache-2.0 | 71 | 18 | 2025-08-22 | CER/WER evaluation against ground truth. |
| [impactcentre/ocrevalUAtion](https://github.com/impactcentre/ocrevalUAtion) | Apache-2.0 | 68 | 26 | 2026-10-13 | The other evaluation tool; still maintained. |
| [natliblux/nautilusocr](https://github.com/natliblux/nautilusocr) | ⚠️ GPL-3.0 | 56 | 5 | **2023-05-30** | National Library of Luxembourg, METS/ALTO→improved METS/ALTO. Copyleft **and** dormant. |
| [htr-united/htr-united](https://github.com/htr-united/htr-united) | **CC0-1.0** | 51 | 45 | 2026-11-08 | Ground-truth catalogue. Fork ratio **0.88** — contributed infrastructure, not a showcase. |
| [cneud/alto-tools](https://github.com/cneud/alto-tools) | Apache-2.0 | 50 | 15 | 2026-09-21 | ALTO XML manipulation. |
| [LibraryOfCongress/ndnp-open-ocr](https://github.com/LibraryOfCongress/ndnp-open-ocr) | **CC0 1.0** (read, 1,951 B) | 34 | 1 | 2026-10-24 | US national newspaper OCR reprocessing → ALTO XML + PDF at scale. |
| [open-oni/open-oni](https://github.com/open-oni/open-oni) | Apache-2.0 (read, 573 B) | 58 | 24 | 2026-09-15 | The open newspaper **front end**; API reported `NOASSERTION`. |

### ⚠️ The standards repos have no licence — now 3 for 3 in this plane

| Standard | Repo | Stars | Licence file |
|---|---|---|---|
| **ALTO** (the OCR layout format national programmes mandate) | [altoxml/schema](https://github.com/altoxml/schema) | 57 | **NONE** — `README.md` returns 200, all probed licence names 404 |
| **METS** (the packaging format beside it) | [mets/METS-schema](https://github.com/mets/METS-schema) | 27 | **NONE** |
| *(pass 8, for comparison)* RSL 1.0 | rslstandard/rsl | 47 | NONE |

**P46 is now a measured rule, not an observation:** *the repository that publishes a standard is
disproportionately likely to carry no licence grant at all.* Without a grant, default copyright applies —
all rights reserved. **Use the published specification, not the repo contents**, and never vendor an
XSD from one of these repos into a client deliverable without asking the maintaining body in writing.
Both ALTO and METS specifications are published by the Library of Congress and are usable; it is the
*GitHub copies* that lack terms.

### The supply-chain finding: the US national pipeline depends on an unlicensed, dormant repo

`LibraryOfCongress/ndnp-open-ocr` is a **work of the United States Government — public domain, with a
CC0 1.0 waiver worldwide** (read from `LICENSE.md`; the API's `NOASSERTION` is wrong in the permissive
direction, the same false negative the healthcare pass found on `FDA/openfda`). It acknowledges
incorporating **Tesseract** and **Leptonica** unmodified under their own licences — and per the Library's
own August 2026 announcement it uses newspaper **layout-detection models from American Stories**
(Harvard). That repo, [dell-research-harvard/AmericanStories](https://github.com/dell-research-harvard/AmericanStories):
**142★, no licence file** (8 names × 2 branches probed, `README.md` = 200 so the control passes),
**last push 2024-03-07**, models distributed via **Dropbox**. The dataset is CC-BY-4.0 on Hugging Face;
the code and models are not licensed at all.

So the clean, CC0, government-published pipeline has an **unlicensed dependency at its layout step.**
Anyone who adopts the LoC pipeline inherits that. The fix is small and worth quoting as work:
substitute `eynollah` (Apache-2.0, pushed 2026-11-13) at the layout step and the chain becomes
end-to-end permissive.

---


## 2026-11-27 — pass 38: type & text-rendering infrastructure (**the engine layer is being rewritten in Rust under Apache-2.0, and the QA tool's successor shipped today**)

Infrastructure half of pass 38. All figures verified 2026-11-27 via `search/repositories` with `repo:`
qualifiers, existence via `git ls-remote`, licences by reading the file wherever the API said
`NOASSERTION`/`NONE`.

### The live movement: a permissive Rust stack replacing a licence-messy C stack

| Repo | License | Stars | Forks | Last push |
|---|---|---|---|---|
| [googlefonts/fontations](https://github.com/googlefonts/fontations) | Apache-2.0 | 857 | 91 | 2026-11-25 |
| [dfrg/swash](https://github.com/dfrg/swash) | Apache-2.0 | 886 | 67 | 2026-11-13 |
| [harfbuzz/rustybuzz](https://github.com/harfbuzz/rustybuzz) | MIT | 666 | 42 | 2026-07-26 |
| [googlefonts/fontc](https://github.com/googlefonts/fontc) | Apache-2.0 | 196 | 22 | 2026-11-25 |
| [fonttools/fontspector](https://github.com/fonttools/fontspector) | Apache-2.0 | 123 | 27 | **2026-11-27** |
| [servo/font-kit](https://github.com/servo/font-kit) | Apache-2.0 | 844 | 138 | 2026-11-01 |

…replacing, component for component, a C layer whose licences each need a file read:
[harfbuzz](https://github.com/harfbuzz/harfbuzz) **"old MIT"** (`NOASSERTION`, 6,261★, 2026-11-27);
[freetype](https://github.com/freetype/freetype) **dual FTL / GPL-2.0** (`LICENSE.TXT` 2,149 B, 935★);
[unicode-org/icu](https://github.com/unicode-org/icu) **Unicode-3.0** (`LICENSE` 27,718 B, 3,654★);
[fontforge](https://github.com/fontforge/fontforge) **GPL-3.0 as a whole** (`LICENSE` 10,015 B, 8,105★).

### The rest of the plane, first appearance in this KB

| Repo | License | Stars | Last push | Why it is here |
|---|---|---|---|---|
| [typst/typst](https://github.com/typst/typst) | Apache-2.0 | **57,454** | 2026-11-26 | Largest permissive project in the plane by an order of magnitude. |
| [fontsource/fontsource](https://github.com/fontsource/fontsource) | MIT | 6,305 | 2026-11-09 | Self-hosted open fonts as npm packages — the GDPR-safe route for EMEA. |
| [fonttools/fonttools](https://github.com/fonttools/fonttools) | MIT | 5,338 | 2026-11-27 | `pyftsubset`; the most-called tool here. |
| [opentypejs/opentype.js](https://github.com/opentypejs/opentype.js) | MIT | 5,052 | 2026-08-08 | Font parsing in JS/Node. |
| [sile-typesetter/sile](https://github.com/sile-typesetter/sile) | MIT | 1,793 | 2026-11-14 | Typesetter built for complex scripts. |
| [google/woff2](https://github.com/google/woff2) | MIT | 1,830 | 2026-10-28 | The format browsers want. |
| [KonghaYao/cn-font-split](https://github.com/KonghaYao/cn-font-split) | Apache-2.0 | 1,269 | **2026-11-27** | CJK subsetting into unicode-range slices. The APAC answer, pushed the day of this pass. |
| [libass/libass](https://github.com/libass/libass) | **ISC** | 1,209 | 2026-11-21 | Burns the caption into the frame; delegates shaping to HarfBuzz. |
| [adobe-type-tools/afdko](https://github.com/adobe-type-tools/afdko) | Apache-2.0 (`LICENSE.md`) | 1,191 | 2026-11-23 | Adobe's toolkit; API said `NOASSERTION`. |
| [Jolg42/awesome-typography](https://github.com/Jolg42/awesome-typography) | **CC0-1.0** | 1,554 | 2026-11-18 | A *list*, under a content licence — correctly, since it is content. |
| [mpcabd/python-arabic-reshaper](https://github.com/mpcabd/python-arabic-reshaper) | MIT | 452 | 2026-11-02 | Arabic letter joining where no shaper is available. |
| [HOST-Oman/libraqm](https://github.com/HOST-Oman/libraqm) | MIT | 341 | 2026-07-23 | Complex-text layout; **Pillow without it draws Arabic isolated and LTR**. |
| [notofonts/notofonts.github.io](https://github.com/notofonts/notofonts.github.io) | Apache-2.0 | 324 | 2026-11-24 | The live Noto distribution. |
| [rosettatype/hyperglot](https://github.com/rosettatype/hyperglot) | Apache-2.0 | 208 | 2026-10-26 | **Which languages does this font support?** |
| [unicode-org/text-rendering-tests](https://github.com/unicode-org/text-rendering-tests) | Unicode-3.0 (`LICENSE` 2,033 B) | 188 | 2026-08-24 | Conformance suite for renderers. |
| [MeirKriheli/python-bidi](https://github.com/MeirKriheli/python-bidi) | **LGPL-3.0** | 127 | 2026-10-28 | **The one copyleft link in an otherwise permissive RTL chain.** Matters if statically linked. |
| [googlefonts/shaperglot](https://github.com/googlefonts/shaperglot) | Apache-2.0 | 58 | 2026-11-17 | **Does it *shape* that language, not merely contain the codepoints?** |
| [googlefonts/diffenator2](https://github.com/googlefonts/diffenator2) | Apache-2.0 | 71 | 2026-11-06 | Visual regression between two font builds. |
| [vp-tw/cjk-web-fonts](https://github.com/vp-tw/cjk-web-fonts) | MIT | **0** | 2026-11-15 | Prebuilt CJK web-font subsets served via jsDelivr. **Zero stars — do not cite it to a client**; recorded because a CJK search surfaces it immediately. |
| [boxesandglue/textshape](https://github.com/boxesandglue/textshape) | MIT | **2** | 2026-11-25 | Go shaper, self-described beta with unstable API. Recorded so a Go shop learns its scale before adopting it. |

### Measured subsetting effects — self-reported, and labelled as such

| Source | Before | After | Caveat |
|---|---|---|---|
| `faberline/surface` PR (WASM build) | full CJK font **16,435,884 B** | subset **3,615,900 B** | One project's own PR description, not a benchmark |
| `xingkaixin/blog` PR (page-level subsetting with fontTools) | median **393 KB** font bytes/page | **117 KB** | Same caveat; single site |
| `storytold/texturecraft` PR | web build **27.1 MB**, over its 24 MiB gate | under gate after CJK subsetting | Same caveat |

These are the only quantified figures this pass could reach. **The Web Almanac fonts chapter
(`almanac.httparchive.org`) does not resolve from this session** — see the informed-gaps note in
`intel/trends.md`. Treat the three rows above as directional evidence that CJK subsetting is a
multiple-megabyte problem, and nothing more.

## 2026-11-27 — pass 37: consumer-products & brand-licensing infrastructure (**the substrate is Apache-2.0 and 5,689 stars; the application layer is one search result**)

The licensing-out plane has no open-source application tier and a genuinely excellent substrate. Both
halves verified: existence by `git ls-remote` (22/22 resolve), licences read from the repository rather
than taken from the API's `spdx_id` — which was wrong twice, both times in the permissive direction.

**Substrate — image matching (the healthiest tier measured in any of the 37 planes).**

| Repo | Licence | Stars / forks | Last push |
|---|---|---|---|
| [idealo/imagededup](https://github.com/idealo/imagededup) | Apache-2.0 | 5,689★ / 477f | 2025-08-15 |
| [jenssegers/imagehash](https://github.com/jenssegers/imagehash) | MIT | 2,060★ / 173f | 2025-09-17 |
| [corona10/goimagehash](https://github.com/corona10/goimagehash) | BSD-2-Clause | 841★ / 79f | 2024-01-21 |
| [KilianB/JImageHash](https://github.com/KilianB/JImageHash) | MIT | 444★ / 87f | 2024-03-08 |
| [bentoml/CLIP-API-service](https://github.com/bentoml/CLIP-API-service) | Apache-2.0 | 67★ / 4f | **2026-11-09** |

**Product identity — GS1/GTIN (permissive and alive, and the content law again: parsers free, numbers rented).**

| Repo | Licence | Stars | Last push |
|---|---|---|---|
| [PeterBrockfeld/BarcodeParser](https://github.com/PeterBrockfeld/BarcodeParser) | MIT | 77★ | 2022-04-21 |
| [jodal/biip](https://github.com/jodal/biip) | Apache-2.0 | 59★ | **2026-11-01** |
| [xremix/SwiftGS1Barcode](https://github.com/xremix/SwiftGS1Barcode) | MIT | 30★ | **2026-11-08** |
| [lamoda/gs1-barcode-parser](https://github.com/lamoda/gs1-barcode-parser) | MIT | 21★ | **2026-10-27** |
| [ronanguilloux/IsoCodes](https://github.com/ronanguilloux/IsoCodes) | GPL-3.0 | 803★ | 2026-03-20 |

**Mark detection — 1,202 search results, and every usable repo is years dead.**

| Repo | Licence | Stars / forks | Last push | State |
|---|---|---|---|---|
| [satojkovic/DeepLogo](https://github.com/satojkovic/DeepLogo) | MIT | 529★ / 153f | 2022-08-28 | Dead 3+ years — a baseline to re-train, not a dependency |
| [FenHua/Robust_Logo_Detection](https://github.com/FenHua/Robust_Logo_Detection) | Apache-2.0 | 77★ / 19f | 2021-10-24 | Dead 5 years |
| [nuwandda/yolov7-logo-detection](https://github.com/nuwandda/yolov7-logo-detection) | BSD-3-Clause | 50★ / 12f | 2024-12-02 | Most recent usable baseline |

**Commerce & catalogue bases that can carry licensed-product work.**

| Repo | Licence | Stars / forks | Last push | Note |
|---|---|---|---|---|
| [frappe/erpnext](https://github.com/frappe/erpnext) | GPL-3.0 | 41,679★ / 13,652f | **2026-11-27** | No licensing module; royalty accrual is a custom DocType. Client-hosted only |
| [medusajs/medusa](https://github.com/medusajs/medusa) | **MIT** (file-verified) | 37,443★ / 5,575f | 2026-11-26 | Best permissive API-first base |
| [bagisto/bagisto](https://github.com/bagisto/bagisto) | MIT | 28,422★ / 3,399f | 2026-11-25 | Multi-vendor marketplace native — closest shape to many licensees |
| [saleor/saleor](https://github.com/saleor/saleor) | BSD-3-Clause | 23,612★ / 6,222f | 2026-11-23 | Composable headless commerce |
| [spree/spree](https://github.com/spree/spree) | BSD-3-Clause | 15,855★ / 5,319f | 2026-11-26 | DTC + **B2B** + marketplace; B2B is the licensee wholesale flow |
| [resourcespace/resourcespace](https://github.com/resourcespace/resourcespace) | **BSD-3 + trademark clause** | 96★ / 29f | **2026-11-27** | Style-guide/asset distribution. Derivatives may not be named "ResourceSpace" |
| [pwnera/artbucket](https://github.com/pwnera/artbucket) | **AGPL-3.0** | 34★ | **2026-11-24** | The only repo modelling licence terms, territories, embargo dates — **with an MCP server** |

**Quarantined, with the reason:** [pimcore/pimcore](https://github.com/pimcore/pimcore) (3,891★ / 1,511f,
2026-11-26) is still listed by generic "open source DAM/PIM" roundups. Its `2026.x/LICENSE.md` is the
**Pimcore Open Core License** (June 2025): *"if not provided for otherwise, a software element is
Proprietary Software."* Publicly readable, proprietary by default. Probe note: the licence file 404s on
`master` and `main` — the default branch is **`2026.x`**.
Also quarantined: [khammal/RealDeal](https://github.com/khammal/RealDeal), the one project the web
surfaced as open-source counterfeit detection — **0★, no LICENSE file**, so all rights reserved.

**What was searched and is missing:** `licensee portal` = **1 result** (the crudest zero in this KB);
`merchandise licensing` = 3, none relevant; `product placement detection video` = 2, neither relevant;
`royalty accounting` top six = 9 stars; `style guide brand assets` top four = 12 stars, all stale or
unlicensed. `counterfeit detection` = **865 results and a false abundance** — all six top hits unlicensed,
five last pushed 2017–2024. Read the results, not the total.

## 2026-11-27 — pass 36: 2D animation infrastructure (**six repositories and 32 stars hold the timing sheet of an entire production tradition**)

Measured 2026-11-27; **69/69 URLs confirmed by `git ls-remote`**. This file tracks the **rigs,
runtimes and formats**; the AI models and agents are in `agents/trending.md` pass 36.

### The playback tier — the healthiest layer in the plane, and its most-used entry is its stalest

| Repo | Licence | ★ | Last push | Note |
|---|---|---|---|---|
| https://github.com/airbnb/lottie-android | **Apache-2.0** | 35,782 | 2026-02-15 | — |
| https://github.com/airbnb/lottie-web | **MIT** | 32,606 | **2025-09-01** | **14 months stale.** The most-deployed 2D animation player on the web |
| https://github.com/airbnb/lottie-ios | **Apache-2.0** | 26,952 | 2026-11-24 | Actively maintained |
| https://github.com/thorvg/thorvg | **MIT** | 1,938 | **2026-11-27** | Pushed the day of this pass; SVG **and** Lottie. The live path |
| https://github.com/LottieFiles/dotlottie-web | **MIT** | 962 | **2026-11-27** | Rust+WASM player, React/Vue bindings |
| https://github.com/LottieFiles/dotlottie-rs | **MIT** | 294 | **2026-11-27** | The Rust core |
| https://github.com/rive-app/rive-runtime | **MIT** | 1,270 | 2026-11-26 | State-machine 2D/3D runtime |
| https://github.com/DragonBones/DragonBonesJS | **MIT** | 864 | 2026-01-23 | **The only permissive 2D skeletal runtime** — Spine's requires a paid editor licence |

**The asymmetry that is the story of this tier:** ~95,000★ of Airbnb-owned runtimes render a format
authored in **Adobe After Effects**, a proprietary tool. Open source owns the playback of 2D animation
completely and owns none of its authoring — and the spec repo
(https://github.com/lottie/lottie-spec, 120★) has **no licence file resolving at its root** under 13
names, while `README.md` at the same path returns 200. The runtimes are unambiguously permissive; the
**specification text's licence is unresolved** and is recorded as an informed gap.

### The authoring tier — and the licence wall in one line

| Repo | Licence | ★ | Last push |
|---|---|---|---|
| https://github.com/blender/blender | **GPL-2.0-or-later** (`COPYING`) | 22,610 | 2026-11-26 |
| https://github.com/KDE/krita | GPL-3.0 | 10,816 | **2026-11-27** |
| https://github.com/opentoonz/opentoonz | **BSD-3-Clause** (`LICENSE.txt`, after a third-party preamble) | 8,386 | 2026-11-26 |
| https://github.com/NatronGitHub/Natron | GPL-2.0 | 5,777 | **2026-11-27** |
| https://github.com/mypaint/mypaint | GPL-2.0 | 3,005 | 2026-10-20 |
| https://github.com/synfig/synfig | GPL-3.0 | 2,480 | 2026-11-22 |
| https://github.com/pencil2d/pencil | GPL-2.0 | 1,930 | 2026-11-23 |
| https://github.com/tahoma2d/tahoma2d | **BSD-3-Clause** | 699 | 2026-10-17 |
| https://github.com/mypaint/libmypaint | **ISC** (`COPYING`, 792 B) | 393 | 2026-04-14 |

**Seven GPL, two BSD-3** — and the two permissive ones are the two smallest. A studio that needs to fork,
add proprietary AI and ship a binary has exactly two legal starting points in the entire plane.

### The exposure-sheet tier — every repository that exists, worldwide

| Repo | Licence | ★ | Last push |
|---|---|---|---|
| https://github.com/opentoonz/xdts_viewer | **BSD-3-Clause** | 22 | 2026-07-29 |
| https://github.com/konero/KritaToXDTS | GPL-3.0 | 6 | 2026-05-19 |
| https://github.com/SehataKuro/xdts | **Apache-2.0** | 2 | **2026-11-11** |
| https://github.com/shun-iwasawa/XDTS-uext | **NONE** | 2 | 2024-10-17 |
| https://github.com/SehataKuro/clip2xdts-rs | **NONE** | 0 | 2026-11-18 |
| https://github.com/lunafuse/vdts-editor | **MIT** | 0 | 2026-10-04 |

**Six repositories. 32 stars combined.** XDTS was released in **2018 by Celsys with Toei Animation**;
the **public spec is still the November 2018 version** although Clip Studio Paint 1.13.0 added 2D
camera-folder data, and that delta is documented only in one person's **unlicensed** "unofficial
extension" — written by the author of the only viewer. The format that schedules the world's largest
animation tradition has less open tooling than a mid-sized colour-picker library.

### Archived or stale rigs — quarantine list added this pass

| Repo | Licence | ★ | State |
|---|---|---|---|
| https://github.com/MaurycyLiebner/enve | GPL-3.0 | 1,195 | **Archived**, last push 2022-09-25 |
| https://github.com/svga/SVGAPlayer-Android | Apache-2.0 | 3,258 | **Archived**, last push 2023-02-06 |
| https://github.com/airbnb/lottie-web | MIT | 32,606 | Live repo, **no push in 14 months** |
| https://github.com/nagadomi/waifu2x | MIT | 28,239 | No push since 2023-05-04 |
| https://github.com/bloc97/Anime4K | MIT | 21,679 | No push since 2024-08-17 |
| https://github.com/lllyasviel/style2paints | Apache-2.0 | 18,143 | No push since 2023-08-01 |

**A valid licence on a dead project is not a dependency** — and in this plane four of the six
best-known permissive names are dormant.

## 2026-11-27 — pass 35: graphics-desk infrastructure (**the newsroom rig is MIT, the shared design system is unlicensed, and the two facts live in the same org**)

Measured 2026-11-27 via `api.github.com/search/repositories?q=repo:owner/name`; 77/77 URLs confirmed
by `git ls-remote`. This file tracks the **rigs and platforms**; the libraries and NL→chart agents are
in `agents/trending.md` pass 35.

### The rig layer, by region — one table, because the asymmetry is the story

| Region | Who publishes a graphics rig | Licence pattern | Freshest push | Honest read |
|---|---|---|---|---|
| **APAC** | [abcnews](https://github.com/abcnews/odyssey) (ABC Australia, 231 repos) | **MIT** for libraries, **none** for the design system | **2026-11-27** ([chart-builder](https://github.com/abcnews/chart-builder)) | The most active open graphics desk anywhere, and nobody is watching: 3–22 stars per repo. Plus the region owns the chart libraries — ECharts (Apache-2.0, 67,808★), G2 (MIT, 12,678★), pyecharts (MIT, 15,781★). |
| **North America** | [nprapps](https://github.com/nprapps/interactive-template) (212 repos), [newsdev](https://github.com/newsdev/ai2html) (NYT, 71), [the-pudding](https://github.com/the-pudding/svelte-starter) | **MIT** (NPR, Pudding) / **Apache-2.0** (NYT) | 2026-11-25 (`interactive-template`) | Owns the *rig* lineage and the ideas everyone copied. Ageing: ai2html 2025-10-22, archieml-js 2021-11-12, copytext 2018-06-12, elex **archived**. |
| **EMEA** | [ZeitOnline/scrolleo](https://github.com/ZeitOnline/scrolleo), [guardian/dotcom-rendering](https://github.com/guardian/dotcom-rendering) | MIT / Apache-2.0 | **2026-11-26** (`scrolleo`) | **Thinnest rig layer of the four.** One new library at 9★; the most-starred EMEA artifact, [bbc/bbplot](https://github.com/bbc/bbplot) (1,645★), has **no licence file** and no push since **2021-07-02**. The Guardian open-sources its entire website but no chart tooling. |
| **LATAM** | [InfoAmazonia/jeo-plugin](https://github.com/InfoAmazonia/jeo-plugin), [chequeado](https://github.com/chequeado/chequeabot-legacy), [estadao](https://github.com/estadao/basometro) | **GPL-3.0 / AGPL-3.0**, WordPress-coupled | 2026-11-13 (`jeo-plugin`) | **No permissive reusable library found in seven orgs scanned.** What is alive is copyleft geo-tooling for WordPress; the rest is per-story GPL-3.0 code from 2018–2020. Detail and method in `intel/market.md`. |

### The licence detail that decides a client deliverable

Inside **one** organisation — `abcnews`, the most permissive desk found — the split is exact:

- **MIT:** `odyssey`, `odyssey-scrollyteller`, `scrollyteller`, `chart-builder`, `interactive-isobands`,
  `interactive-datawrapper-scrollyteller`, `d3-layout-narrative`, `dev-proxy`, `us-election-2026`
- **No licence field at all:** `palette` (the colour system), `components-dataviz` (the shared
  components), `svelte-scrollyteller` (the newest framework work)

**The reusable libraries are granted; the shared design system is not.** That is the inverse of what
an integrator hopes for, and it is a five-minute check that prevents a three-week problem.

### Infrastructure that removes a recurring cost — worth its own line

[protomaps/basemaps](https://github.com/protomaps/basemaps) (**BSD-3-Clause**, 780★, 2026-09-11)
builds a **single-file PMTiles basemap served from static hosting** — no tile server, no per-view
billing, no vendor key in the page. Paired with
[maplibre/maplibre-gl-js](https://github.com/maplibre/maplibre-gl-js) (**BSD-3-Clause**, 12,189★,
2026-11-26) it is the first fully permissive web-cartography stack with **zero marginal cost per map
view** — which matters most on exactly the stories that go viral.

### Channel notes for the next pass

- **`search/repositories?q=repo:owner/name` is still the working channel** for stars/SPDX/`pushed_at`
  /`archived`; `/repos/{owner}/{repo}` remains blocked ("GitHub access to this repository is not
  enabled for this session").
- **New limit found:** that channel returns `total_count: 0` for
  [nprapps/pym.js](https://github.com/nprapps/pym.js) although the repo exists (`git ls-remote` OK,
  raw `LICENSE` 1,047 B MIT, `package.json` v1.3.2). **The dot is not the cause** — `chartjs/Chart.js`
  resolves. Some repos are simply absent from the search index: when that happens, fall back to
  `ls-remote` + raw, and **record the metadata as unknown rather than as zero.**
- **`github.com` HTML returns 403** through this session's proxy, so star counts cannot be scraped as
  a fallback. `raw.githubusercontent.com` works.
- **The SPDX field is wrong often enough to check:** `NOASSERTION` resolved to real permissive
  licences for `maplibre-gl-js` (BSD-3-Clause), `quarto-cli` (MIT), `ai2html`/`archieml-js`/`elex`
  (Apache-2.0, NYT), `guardian/frontend` (Apache-2.0), `mapshaper` (MPL-2.0) and to **AGPL-3.0** for
  `cjworkbench`. Resolve it from the file; never report `NOASSERTION` as "no licence."

## 2026-11-27 — pass 34: ad-integrity & supply-chain-transparency infrastructure (**the industry standardised the claim and never deployed the proof: `ads.txt` has eight maintained tools, `ads.cert` has eight stars and no commits since 2023**)

Measured 2026-11-27 via `api.github.com/search/repositories?q=repo:owner/name` — see
`agents/trending.md` pass 34 for the channel note. **Star counts restored after pass 33's gap.**

### The one table that describes this plane

| Step in the chain | What kind of problem it is | Best open artifact | License | Stars | Last push |
|---|---|---|---|---|---|
| 1. **Declare** who may sell | format | [10up/ads-txt](https://github.com/10up/ads-txt) | GPL-2.0 | 61 | **2026-11-24** |
| 1b. Parse the declaration | format | [InteractiveAdvertisingBureau/ads.txt-parser](https://github.com/InteractiveAdvertisingBureau/ads.txt-parser) | Apache-2.0 | 37 | 2024-08-27 |
| 1c. Walk the whole supply graph | format | [adops-tool/SPO-sellers-json-crawler](https://github.com/adops-tool/SPO-sellers-json-crawler) | Apache-2.0 | 0 | **2026-11-07** |
| 2. **Prove** the declaration cryptographically | format + crypto | [IABTechLab/adscert](https://github.com/IABTechLab/adscert) | Apache-2.0 | **8** | **2023-07-05** |
| 3. **Detect** invalid traffic | judgment + accredited labels | [Nameles-Org/Nameles](https://github.com/Nameles-Org/Nameles) | Apache-2.0 | 72 | **2019-09-06** |
| 4. **Judge** brand suitability | pure judgment | — **nothing exists** — | — | — | — |
| 5. **Count** it so an auditor accepts it | accreditation | [InteractiveAdvertisingBureau/Open-Measurement-JSClients](https://github.com/InteractiveAdvertisingBureau/Open-Measurement-JSClients) (web only) | Apache-2.0 | 76 | 2026-11-02 |

**Read down the "Last push" column.** 2026-11-24 → 2026-11-07 → **2023-07-05** → **2019-09-06** →
nothing. The further the step is from parsing a file and the closer it is to forming a judgement a
third party must accept, the older the newest commit, until there is no commit. This is the
**five-step gradient**, and it is the most complete version of this KB's structural law yet measured —
pass 33 managed three steps, pass 5 managed three.

### Infrastructure committed in the last three weeks

| Repo | License | Stars | Last push | What it is |
|---|---|---|---|---|
| [coreruleset/coreruleset](https://github.com/coreruleset/coreruleset) | Apache-2.0 | 3,376 | **2026-11-27** | OWASP CRS — pushed on the day of this pass. |
| [corazawaf/coraza](https://github.com/corazawaf/coraza) | Apache-2.0 | 4,061 | 2026-11-26 | Embeddable Go WAF library, ModSecurity-rule compatible. **The piece that lets you put CRS inside your own ad server** rather than in front of it. |
| [crowdsecurity/crowdsec](https://github.com/crowdsecurity/crowdsec) | MIT | 15,814 | 2026-11-25 | **The largest permissive asset on this plane and nobody in adtech cites it.** Crowdsourced malicious-IP intelligence — a free, continuously-updated GIVT signal, built by the security community, sitting unused next to a $15,000/year bot list. |
| [monperrus/crawler-user-agents](https://github.com/monperrus/crawler-user-agents) | MIT | 1,416 | 2026-11-26 | The free stand-in for the paid list. |
| [matomo-org/device-detector](https://github.com/matomo-org/device-detector) | LGPL-3.0 | 3,562 | 2026-11-25 | The most complete open bot/device classifier. |
| [X4BNet/lists_vpn](https://github.com/X4BNet/lists_vpn) | NONE | 944 | 2026-11-26 | Datacenter/VPN IP lists — raw GIVT material, no licence grant. |
| [firehol/blocklist-ipsets](https://github.com/firehol/blocklist-ipsets) | NONE | 4,011 | 2026-11-26 | Same, larger, same caveat. |
| [altcha-org/altcha](https://github.com/altcha-org/altcha) | MIT | 2,923 | 2026-11-20 | Self-hosted PoW CAPTCHA alternative, GDPR/WCAG 2.2 AA/EAA compliant. |
| [prebid/openrtb](https://github.com/prebid/openrtb) | Apache-2.0 | 89 | 2026-11-12 | Go OpenRTB/AdCOM types — **the live one.** |
| [InteractiveAdvertisingBureau/openrtb](https://github.com/InteractiveAdvertisingBureau/openrtb) | spec CC BY 3.0 | 532 | 2026-11-11 | The spec, actively maintained. |
| [Chrome-Extensions-labs/Sellers.json-Inspector](https://github.com/Chrome-Extensions-labs/Sellers.json-Inspector) | GPL-3.0 | 6 | 2026-11-07 | MV3 `sellers.json` validator. |
| [Chrome-Extensions-labs/Lines-Checker-ads.txt-app-ads.txt-sellers.json](https://github.com/Chrome-Extensions-labs/Lines-Checker-ads.txt-app-ads.txt-sellers.json) | AGPL-3.0 | 4 | 2026-11-07 | Soft-404 and `OWNERDOMAIN`-mismatch detection. |

### The archived-vs-active trap, third occurrence in this KB

| Repo | License | Stars | Last push | State |
|---|---|---|---|---|
| [bsm/openrtb](https://github.com/bsm/openrtb) | NOASSERTION | **292** | 2024-08-09 | **ARCHIVED** |
| [prebid/openrtb](https://github.com/prebid/openrtb) | Apache-2.0 | **89** | 2026-11-12 | Active, permissive |

**The archived one has 3.3× the stars.** Trend #49 in `intel/trends.md` recorded that star count has
become actively misleading; this is the third plane to prove it, and here it would steer a team onto an
archived Go library for the single most load-bearing protocol in programmatic advertising.

### Two licence traps in the event-collection tier, found by reading files rather than fields

1. **The licence belongs to the component, not the organisation.**
   [snowplow/snowplow](https://github.com/snowplow/snowplow) — **Apache-2.0**, 7,052★, 2026-11-26.
   [snowplow/enrich](https://github.com/snowplow/enrich) — **Snowplow Limited Use License Agreement
   v1.0 (January 2024)**, 31★, 2026-11-24, API reports `NOASSERTION`.
   [snowplow/snowplow-javascript-tracker](https://github.com/snowplow/snowplow-javascript-tracker) —
   BSD-3-Clause, 593★. **The repo with the brand name on it is the permissive one; the repo you deploy
   is not.** A scanner that resolves the org name and stops gets the wrong answer. **New category,
   generalises to all twelve industries** — it extends cycle 8's "the licence can belong to the
   compilation" to "the licence can belong to the component."
2. **Elastic License 2.0 wearing an open-source badge.**
   [rudderlabs/rudder-server](https://github.com/rudderlabs/rudder-server) — LICENSE read, 3,792 B,
   **Elastic License 2.0**, 4,521★, 2026-11-26. Not OSI-approved; forbids offering the product as a
   managed service. For a consultancy that hosts for clients, that is the prohibited use.

And one correction in the opposite direction, which matters just as much:
[PostHog/posthog](https://github.com/PostHog/posthog) (41,180★) reports `NOASSERTION` but its LICENSE
grants **MIT Expat to everything outside `ee/`**. `NOASSERTION` is not a verdict — it is an instruction
to read the file.

### ⛔ What is not here, and the searches that establish it

- `supply path optimization` → **53 repos, zero adtech.**
- `brand safety` → **465 repos, zero brand-safety tools.**
- `invalid traffic` → **63 repos total**; the only purpose-built engine dead since 2019.
- `malvertising` → **57 repos**; one maintained ([andpalmier/seads](https://github.com/andpalmier/seads), Apache-2.0, 50★).
- `viewability` → **unusable** (498,228 results, all Android view/chart libraries).
- **The OM SDK native library is not on GitHub at all** — Tools Portal download plus a Tech Lab
  compliance programme. In-app and CTV viewability have no open implementation, and those are the two
  fastest-growing inventory types.
- **No APAC- or LATAM-specific ad-integrity repository was found**, in the two regions with the
  highest measured IVT rates on earth.

## 2026-11-27 — pass 33: media-monitoring collection infrastructure (**the most permissive and most actively maintained substrate found in any of the 33 planes — and a three-year dead zone inside one Apache-2.0 organisation**)

Measured 2026-11-27. **No star counts this pass** — API scoped to this session's own repos, HTML and
`.atom` channels empty through the proxy. Existence via `git ls-remote`, licences read from the actual
file with byte counts, dates via `git clone --depth 1 --filter=blob:none`. See `agents/trending.md`
pass 33 for the full channel note.

**Four repos on this plane were committed on the day of this pass. Eleven of thirteen in the
collection tier are MIT / Apache-2.0 / BSD / public domain.** After 32 passes in which the permissive
layer was consistently the *standards and pipeline* tier and the turnkey tier was consistently
copyleft, this plane inverts the usual warning: **here the permissive options are the good ones.**

| Repo | Licence | Last commit |
|---|---|---|
| [dgtlmoon/changedetection.io](https://github.com/dgtlmoon/changedetection.io) | **Apache-2.0** (11,381 B) | **2026-11-27** |
| [DIYgod/RSSHub](https://github.com/DIYgod/RSSHub) | AGPL-3.0 (34,522 B) | **2026-11-27** |
| [FreshRSS/FreshRSS](https://github.com/FreshRSS/FreshRSS) | AGPL-3.0 (34,522 B) | **2026-11-27** |
| [huginn/huginn](https://github.com/huginn/huginn) | MIT (1,097 B) | **2026-11-27** |
| [flairNLP/fundus](https://github.com/flairNLP/fundus) | MIT (1,101 B) | 2026-11-26 |
| [miniflux/v2](https://github.com/miniflux/v2) | **Apache-2.0** (10,173 B) | 2026-11-26 |
| [ArchiveBox/ArchiveBox](https://github.com/ArchiveBox/ArchiveBox) | MIT (1,069 B) | 2026-11-26 |
| [meilisearch/meilisearch](https://github.com/meilisearch/meilisearch) | MIT | 2026-11-26 |
| [webrecorder/browsertrix-crawler](https://github.com/webrecorder/browsertrix-crawler) | AGPL-3.0 (34,522 B) | 2026-11-26 |
| [searxng/searxng](https://github.com/searxng/searxng) | AGPL-3.0 (34,519 B) | 2026-11-26 |
| [scrapy/scrapy](https://github.com/scrapy/scrapy) | BSD-3-Clause (1,516 B) | 2026-11-25 |
| [apache/tika](https://github.com/apache/tika) | **Apache-2.0** (33,976 B) | 2026-11-25 |
| [RSS-Bridge/rss-bridge](https://github.com/RSS-Bridge/rss-bridge) | **Unlicense** (public domain) | 2026-11-25 |
| [adbar/trafilatura](https://github.com/adbar/trafilatura) | **Apache-2.0** (10,172 B) | 2026-11-23 |
| [stanfordnlp/stanza](https://github.com/stanfordnlp/stanza) | **Apache-2.0** (602 B) | 2026-11-13 |
| [AndyTheFactory/newspaper4k](https://github.com/AndyTheFactory/newspaper4k) | MIT (1,079 B) | 2026-11-01 |
| [codelucas/newspaper](https://github.com/codelucas/newspaper) | MIT (1,079 B) | 2026-10-26 |
| [ranahaani/GNews](https://github.com/ranahaani/GNews) | MIT (1,068 B) | 2026-10-25 |
| [markusmobius/go-trafilatura](https://github.com/markusmobius/go-trafilatura) | **Apache-2.0** (11,356 B) | 2026-09-29 |
| [kurtmckee/feedparser](https://github.com/kurtmckee/feedparser) | BSD-2-Clause (3,167 B) | 2026-07-30 |
| [fhamborg/news-please](https://github.com/fhamborg/news-please) | **Apache-2.0** (11,356 B, `LICENSE.txt`) | 2026-04-14 |
| [go-shiori/go-readability](https://github.com/go-shiori/go-readability) | MIT (1,071 B) | 2025-12-05 |
| [mediacloud/story-indexer](https://github.com/mediacloud/story-indexer) | **Apache-2.0** (11,357 B) | 2026-08-28 |
| [mediacloud/web-tools](https://github.com/mediacloud/web-tools) | **Apache-2.0** (10,171 B) | **2023-12-14** |

**⚠️ LICENCE CORRECTION — AND IT RUNS IN THE COMMERCIALLY FAVOURABLE DIRECTION, WHICH IS WHY IT WOULD
HAVE BEEN MISSED.** Public search results and the widely-linked 2015-era fork `nzufelt/mediacloud`
describe **Media Cloud as AGPL-3.0**. **Both live repos read Apache-2.0** — verified by reading the
files on 2026-11-27 (11,357 B and 10,171 B of Apache 2.0 text). AGPL would have disqualified the only
mature permissive news-index pipeline from any client deliverable; Apache-2.0 makes it the natural
backbone. **Rule: a licence from a fork, aggregator, listicle or model card is a rumour. Read the file
on the canonical repo's default branch.** This is the inverse of the usual failure — the KB has
repeatedly caught licences that were *worse* than advertised; this one was *better*, and a cautious
reader would have wrongly excluded it.

**THE THREE-YEAR DEAD ZONE INSIDE ONE ORGANISATION, WHICH IS THE WHOLE PLANE IN MINIATURE.** Same
org, same Apache-2.0 licence, two components: `story-indexer` (the ingest/index pipeline behind a
corpus of 1B+ stories) committed **2026-08-28**; `web-tools` (the interface humans use to interpret
that corpus) last committed **2023-12-14 — ~3 years**. Not a licence problem, not a funding problem.
The half that is a *format* problem is maintained; the half that is a *judgment* problem is not.
**Operational consequence: build on `story-indexer`, never `web-tools`, and plan to write your own
analysis surface** (`meilisearch` MIT, or OpenSearch). See `compose/patterns.md` pattern 51 step 6.

**THE SEARCH-LAYER ARTEFACT WORTH RECORDING, because it will mislead the next pass too.** Querying
for open-source *PR measurement* tooling returns almost entirely GitHub **pull-request** dashboards
(devtrack, DevPulse, github-pr-dashboard, "Engineering Pulse"). "PR" collides, and the collision
makes an empty category look populated. The genuine hits were two: `Etipufhu/pr-radar` (MIT, six days
old) and `Elmo` — and **Elmo was already catalogued in pass 30**, correctly, as answer-engine
visibility rather than press monitoring. **Method: when a plane's search results all come from an
adjacent meaning of the acronym, the category is empty, not covered.**

## 2026-11-27 — pass 32: device, TV-app & certification infrastructure (**a 30,000-star player deprecated into a rival, a 21,935-star engine declared dead by its own authors, and the plane's verdict component licensed against consultancies**)

Measured 2026-11-27. **71 slugs probed, 58 resolve, 13 do not.** Licences read from the actual file
in every `NOASSERTION`/`NONE` case — eight such cases resolved this pass.

**Two consolidation events at the top of the player layer, both visible only in repo metadata:**

1. **[`sampotts/plyr`](https://github.com/sampotts/plyr) (MIT, 29,977★) now describes itself as
   "Deprecated in favour of Video.js 10; security updates only."** Thirty thousand stars moved into
   maintenance-only, and the beneficiary is
   [`videojs/video.js`](https://github.com/videojs/video.js) (40,260★), which has restyled itself
   from "player" to **"Video.js v10 — media player framework for HTML and React"**. The open web
   player field is consolidating, not proliferating.
2. **[`google/ExoPlayer`](https://github.com/google/ExoPlayer) (Apache-2.0, 21,935★) is "deprecated
   and stale" by its own description**, last pushed 2025-12-23 (~11 months). The live code is
   [`androidx/media`](https://github.com/androidx/media) (Apache-2.0, 3,094★, pushed 2026-11-26) —
   **Jetpack Media3**. A client proposal citing ExoPlayer in 2027 is citing a dead repo with seven
   times the stars of the live one. ⚠️ **Star count is the single most misleading signal in this
   plane**: in both cases the deprecated repo massively outranks its own successor.

**A correction to this KB's own record (pass 29).** `verticals/solutions.md` calls
`rdkcentral/Lightning` *"the only open answer to 'how does it run on the operator's box?'"*. Both
halves are now false: **[`lightning-js/blits`](https://github.com/lightning-js/blits) (Apache-2.0,
117★, pushed 2026-11-26) is "The Lightning 3 App Development Framework"**, the live successor to
Lightning 2 (204★, pushed 2026-10-12) — and `enact` (LG's official framework, 347★, pushed
2026-11-26), `react-native-tvos` (1,432★) and `zombiebox` (113★) were always open alternatives. The
KB had a row for Lightning and none for any of these. **Probing `rdkcentral/Blits` 404s** — the
Lightning 3 repo moved out of the `rdkcentral` org to `lightning-js`, which is exactly the kind of
move a stale KB row hides.

**The certification layer, which is where this plane's real scarcity sits — 51 stars in total:**

| Repo | Licence | Stars | Last push |
|---|---|---|---|
| [cta-wave/WMAS](https://github.com/cta-wave/WMAS) | `NOASSERTION` | 20★ | 2026-11-25 |
| [cta-wave/dpctf-deploy](https://github.com/cta-wave/dpctf-deploy) | BSD-3 (read) | 6★ | 2026-09-07 |
| [cta-wave/Test-Content-Generation](https://github.com/cta-wave/Test-Content-Generation) | BSD-3 | 5★ | 2026-11-20 |
| [cta-wave/dpctf-tests](https://github.com/cta-wave/dpctf-tests) | BSD-3 (read) | 3★ | 2026-11-09 |
| [cta-wave/dpctf-test-runner](https://github.com/cta-wave/dpctf-test-runner) | BSD-3 (read) | **0★** | 2026-11-09 |
| [cta-wave/device-observation-framework](https://github.com/cta-wave/device-observation-framework) | ⛔ **Apache-2.0 + Commons Clause** | 1★ | 2026-10-14 |
| [streaming-video-technology-alliance/ott_device_matrix](https://github.com/streaming-video-technology-alliance/ott_device_matrix) | ⚠️ no licence file | 8★ | 2025-03-17 |

**The licence finding of this pass, and the most commercially consequential one in the KB so far.**
`device-observation-framework` — the component that converts observations into a **pass/fail
verdict** — is Apache-2.0 with a **Commons Clause** rider whose text excludes *"the right to Sell
the Software"*, defining "Sell" to include *"fees for hosting or consulting/ support services
related to the Software"*. Licensor: **Consumer Technology Association**; contributor: **Resillion
UK Limited** (a commercial test house). Every sibling repo in the org is BSD-3; a sweep of four
found **0** further Commons Clause hits. Read plainly: **the open test *content* is free, and the
open *verdict* is reserved** — and the reservation lands precisely on service businesses.
→ **CI rule for all twelve industries: grep incoming `LICENSE` files for `commons clause`.** SPDX
fields, licence badges and SBOM scans of the source tree cannot see it.

**Three more licence shapes recorded this pass** (all generalise beyond media):
- **The licence is not in the repository.** [`axiomatic-systems/Bento4`](https://github.com/axiomatic-systems/Bento4)
  (2,530★): no licence file under any of ten names on either branch; README says *"Open Source, with
  a dual-license model… find out more on the About Page"*. `bento4.com` is **unreachable under this
  session's network policy**, so the KB records the licence as **unresolved** rather than guessing.
  Worse than pass 8's `chromaprint` case — there the terms were at least in the repo.
- **The README is the licence.** [`webosose/build-webos`](https://github.com/webosose/build-webos)
  (732★) reports `NONE`, has no licence file, and its README carries the full Apache-2.0 grant plus
  `SPDX-License-Identifier: Apache-2.0`.
- **A Markdown heading defeats the detector.** All three `dpctf-*` repos report `NOASSERTION` only
  because `LICENSE.md` starts with `# The 3-Clause BSD License`.

**⛔ Stated as a measured gap: there is no public open-source multi-CDN steering implementation.**
Four slugs probed and 404: `streaming-video-technology-alliance/content-steering`,
`.../open-caching-api`, `Dash-Industry-Forum/dash.js-content-steering`,
`muxinc/mux-stats-sdk-hlsjs`. The SVTA's own pages and an IBC paper describe a client-side
multi-CDN switcher and an open content-steering framework; **neither has a locatable public
repository as of 2026-11-27.** What is public is the *vocabulary* —
[`common-media-library`](https://github.com/streaming-video-technology-alliance/common-media-library)
(Apache-2.0, 86★, pushed 2026-11-23), CMCD (35★, **no licence file**), CMSD (25★, no licence file),
[OC-API](https://github.com/streaming-video-technology-alliance/OC-API) (MIT, 4★) — plus steering
support inside the players themselves. **Nervous system standardised and permissive; brain unbuilt.**

**⚠️ The best index of this plane cannot be reused.**
[`vitalets/awesome-smart-tv`](https://github.com/vitalets/awesome-smart-tv) (1,480★, pushed
2026-11-09) has **no licence file and no licence statement in its README**. Default copyright:
research input only, never a client deliverable. (By contrast
[`tugkanboz/awesome-ai-testing`](https://github.com/tugkanboz/awesome-ai-testing) is **CC0-1.0**.)

**Two dead repos with enough stars to fool a proposal:**
[`raphamorim/react-tv`](https://github.com/raphamorim/react-tv) (MIT, 2,033★) is **archived**, dead
4.7 years; [`mautilus/sdk`](https://github.com/mautilus/sdk) (BSD-3, 102★) dead **9.5 years**.

## 2026-11-27 — pass 31: show-control infrastructure (**the search layer returned 0–6-star repos born last month and one that does not exist, while every incumbent in the plane went unmentioned**)

Infrastructure half of pass 31. **46 slugs probed by `git ls-remote`; 45 resolve, 1 does not.** But
the resolution rate is not the finding this pass — **the provenance of the candidates is.**

### The measurement: what web search returned vs. what is actually there

Every repository that the web-search layer surfaced for "open source lighting console / show control",
verified against the GitHub search API:

| Repo the search layer returned | Stars | Created | Forks | Verdict |
|---|---|---|---|---|
| [TheCraftedTech/opencue](https://github.com/TheCraftedTech/opencue) | 1★ | 2026-10-16 | 0 | 6 weeks old; **name-collides with a 1,010★ ASWF project** |
| [typoirl/Lumora](https://github.com/typoirl/Lumora) | 6★ | 2026-10-18 | 0 | 6 weeks old, no push since 2026-10-31 |
| [diego-costanzo/BlindCUE](https://github.com/diego-costanzo/BlindCUE) | 1★ | 2026-11-10 | 0 | 17 days old |
| `ciechomir/BlindCUE` | — | — | — | **DOES NOT EXIST.** Returned with a near-identical description to the row above |
| [dio99/luxcanvas](https://github.com/dio99/luxcanvas) | 1★ | 2026-10-08 | 0 | AGPL-3.0, no push since 2026-10-23 |
| [grosserd/lightstage_dmx](https://github.com/grosserd/lightstage_dmx) | 0★ | 2026-11-17 | 0 | 10 days old, NOASSERTION |

**Six candidates: zero to six stars, all created in the last seven weeks, zero forks between them, and
one of them is not a repository at all.** Meanwhile the search layer named **none** of the following,
all of which are the actual substrate of this plane:

| Repo it did not mention | Stars | Licence | Last push |
|---|---|---|---|
| [bitfocus/companion](https://github.com/bitfocus/companion) | 2,376★ | MIT + CLA | 2026-11-22 |
| [benkuper/Chataigne](https://github.com/benkuper/Chataigne) | 1,718★ | GPL-3.0 | 2026-11-26 |
| [mcallegari/qlcplus](https://github.com/mcallegari/qlcplus) | 1,593★ | **Apache-2.0** | 2026-11-26 |
| [OpenLightingProject/ola](https://github.com/OpenLightingProject/ola) | 773★ | LGPL-2.1 | 2026-10-14 |
| [xLightsSequencer/xLights](https://github.com/xLightsSequencer/xLights) | 768★ | GPL-3.0 | 2026-11-26 |
| [FalconChristmas/fpp](https://github.com/FalconChristmas/fpp) | 747★ | GPL-2/LGPL-2.1/**CC-BY-ND** | 2026-11-26 |
| [mapmapteam/mapmap](https://github.com/mapmapteam/mapmap) | 731★ | GPL-3.0 | 2026-11-26 |
| [wled/WLED](https://github.com/wled/WLED) | 19,132★ | **EUPL-1.2** | 2026-11-26 |

**This inverts the failure mode the KB has been guarding against.** Pass 30's lesson was that
listicle-driven passes write *plausible slugs that do not exist*. Pass 31's is sharper: the search
layer can return **repositories that do exist, are correctly described, and are worthless** — six
weeks old, unadopted, and in one case unlicensed — while ranking a 1,593-star Apache-2.0 console that
was pushed yesterday nowhere at all. Newborn repos are optimised for discovery; twenty-year-old
infrastructure projects are not.

**The operational rule, and it is cheap:** in any plane with real industrial tooling, **do not source
candidates from web search at all.** Query the GitHub search API by organisation
(`user:OpenLightingProject`, `user:ETCLabs`, `user:open-stage`) and gate every row on
**stars + created_at + forks_count** together. One API call per org returned the entire real substrate
of this plane; four web searches returned six near-empty repos and a phantom. Applies to all twelve
industries.

### New infrastructure this pass

| Repo | Licence | Stars | Last push | Role |
|---|---|---|---|---|
| [mcallegari/qlcplus](https://github.com/mcallegari/qlcplus) | **Apache-2.0** | 1,593★ | 2026-11-26 | The only fully permissive production lighting console in any plane of this KB |
| [ETCLabs/sACN](https://github.com/ETCLabs/sACN) | Apache-2.0 | 44★ | 2026-11-16 | ANSI E1.31 — the network protocol every modern rig runs on, at 44 stars |
| [ETCLabs/RDMnet](https://github.com/ETCLabs/RDMnet) | Apache-2.0 | 56★ | 2026-09-25 | ANSI E1.33 device discovery — the precondition for any rig-aware agent |
| [open-stage/python-mvr](https://github.com/open-stage/python-mvr) | MIT | 19★ | 2026-08-23 | MVR scene exchange — **the `OpenTimelineIO` of live events** |
| [open-stage/python-gdtf](https://github.com/open-stage/python-gdtf) | MIT | 16★ | 2026-08-23 | GDTF parser (DIN SPEC 15800:2022) |
| [open-stage/python-psn](https://github.com/open-stage/python-psn) | MIT | 5★ | 2026-08-23 | PosiStageNet performer tracking — 5★ and it is the whole open implementation |
| [wled/WLED](https://github.com/wled/WLED) | **EUPL-1.2** | 19,132★ | 2026-11-26 | **First EUPL-1.2 repo in this KB**; most-starred repo in the plane by 11× |
| [bondagit/aes67-linux-daemon](https://github.com/bondagit/aes67-linux-daemon) | GPL-3.0 | 572★ | 2026-10-26 | AES67 audio-over-IP — the open counterpart to proprietary Dante |
| [x42/libltc](https://github.com/x42/libltc) | LGPL-3.0 | 255★ | 2022-09-04 | SMPTE/LTC timecode; dormant since 2022 and correctly so |

### Two renames and an archive, recorded so the next pass does not re-derive them

- `smeighan/xLights` → **[xLightsSequencer/xLights](https://github.com/xLightsSequencer/xLights)**.
  Sixth rename this KB has had to correct.
- `jean-emmanuel/open-stage-control` is **archived at 7★** and is not the project's live home. Do not
  cite it as a dependency.
- `paperManu/splash` is a **declared mirror**; development is on GitLab.

## 2026-11-26 — pass 30: discovery & referral-measurement infrastructure (**the referrer taxonomy of the channel replacing search holds 9 entries against search's 232 — and Google's AI surfaces cannot be entered into it at all**)

Infrastructure half of pass 30. 22 slugs probed this pass; **19 resolve, 3 do not** — and the three
that don't are the finding, because they are the plausible-looking slugs a listicle-driven pass would
have written as rows: `cloudflare/ai.txt`, `usewebsights/llms-txt`, `nalgeon/llms-txt`. All three
**do not exist.** (`mendableai/firecrawl` also no longer resolves under that owner; the project moved
to the `firecrawl` org.)

### New infrastructure this pass

| Repo | Licence | Stars | Last push | Role |
|---|---|---|---|---|
| [allinurl/goaccess](https://github.com/allinurl/goaccess) | MIT | 21,158★ | 2026-11-26 | Log analyser — **the only channel that sees an AI crawler**; load-bearing repo of the plane |
| [monperrus/crawler-user-agents](https://github.com/monperrus/crawler-user-agents) | MIT | 1,416★ | 2026-11-26 | Crawler UA database; pushed today |
| [umami-software/umami](https://github.com/umami-software/umami) | MIT | 40,403★ | 2026-11-26 | The only permissive general analytics base |
| [snowplow-referer-parser/referer-parser](https://github.com/snowplow-referer-parser/referer-parser) | ⚠️ none declared; data **GPL-3.0 by provenance** | 383★ | 2026-07-30 | Holds the `chatbot:` taxonomy |
| [lissy93/web-check](https://github.com/lissy93/web-check) | MIT | 35,661★ | 2026-11-23 | One-pass site inspection — headers, robots, crawlability |
| [JayBizzle/Crawler-Detect](https://github.com/JayBizzle/Crawler-Detect) | MIT | 2,413★ | 2026-11-26 | PHP detection — matters because publishing runs on PHP |
| [omrilotan/isbot](https://github.com/omrilotan/isbot) | Unlicense | 1,169★ | 2026-11-24 | JS bot detection; public domain, no attribution duty |
| [ekalinin/sitemap.js](https://github.com/ekalinin/sitemap.js) | MIT | 1,710★ | 2026-11-01 | Sitemaps and **news sitemaps** — the boring artefact that still works |

### The measured headline, counted from the cloned file rather than inferred

`referers.yml` (85 KB, 424 entries) has six categories: `unknown` 3, `email` 45, `social` 90,
**`search` 232**, `paid` 45, **`chatbot` 9**. The `chatbot:` block was created **2026-07-30**. Its
nine: Character.AI, ChatGPT, Claude.ai, Google Gemini, META.ai, Microsoft Copilot, Mistral.ai,
Perplexity.ai, Poe. Absent and measured: **Grok/xAI, DeepSeek, You.com, Phind.**

The trend to record is genuinely two-sided. **Positive:** the industry's reference referrer taxonomy
now models AI answer engines as their **own channel**, not a sub-type of `search:` — correct shape,
shipped July 2026. **Structural:** it will never be sufficient, because **AI Overviews and AI Mode
are served from `google.com`** and so have no referrer to classify. The largest AI-answer surface is
unobservable in principle through this channel, which is why this plane's infrastructure is a **log
analyser plus a UA database**, not a JavaScript tag.

### ⛔ Licence trap of the pass — a new category

`referer-parser` reports `NONE` at repo level and has no licence file. Its README's own *"Copyright and
license"* section states that **`referers.yml` derives from Matomo's `SearchEngines.php`/`Socials.php`,
copyright 2012 Matthieu Aubry, under GPL-3.0.** The dataset you would extend is **copyleft by
inheritance** while the repo declares nothing. Pass 5 found a licence owned by *the compilation*;
this is one owned by *the dataset's ancestor*, invisible to any SPDX field or SBOM scan of the tree.
**Read the list, re-implement it, do not vendor the YAML.**

### Copyleft note for the analytics tier

Only **two** permissive bases exist here: `umami` (MIT) and `goaccess` (MIT). The obvious
alternatives are all copyleft — `plausible/analytics` **AGPL-3.0** (29,945★), `matomo-org/matomo`
**GPL-3.0** (22,064★), `matomo-org/device-detector` **LGPL-3.0** (3,562★). Also NOASSERTION:
`mitchellkrogza/nginx-ultimate-bad-bot-blocker` (4,848★), `ua-parser/uap-core` (827★).


## 2026-11-26 — pass 29: interactive, branching & playable-story infrastructure (**78 slugs probed, 78/78 resolve; a licence hidden behind British spelling, a licence hidden in a docs tree, and the MIT/GPL seam that decides every H5P proposal**)

Verification for this pass: `git ls-remote` on **78** slugs — **78/78 resolve** — plus a byte-level
licence read for every row whose SPDX field came back `None` or `NOASSERTION`. Four licence
categories were resolved by hand; all four are reusable across the twelve industries.

### 🔴 Four new ways a licence hides — the method finding of this pass

1. **`LICENCE.md`, with a C.** [inkle/ink-unity-integration](https://github.com/inkle/ink-unity-integration)
   (733★) is **MIT**, and GitHub reports `NOASSERTION` only because the file uses British spelling.
   Pass 4 built this KB's licence probe, pass 8 extended it, pass 27 read licences byte by byte —
   **all three missed this spelling.** Add `LICENCE`, `LICENCE.md`, `LICENCE.txt` to the probe list.
2. **The licence lives in the documentation tree.** [renpy/renpy](https://github.com/renpy/renpy)
   (7,065★) has **no root LICENSE file**; the MIT grant is in `sphinx/source/license.rst` with
   carve-outs for derived components. A root-only probe calls the plane's flagship engine unlicensed.
3. **Non-commercial, twice, dressed as open source.**
   [dfabulich/choicescript](https://github.com/dfabulich/choicescript) ships `LICENSE.txt` reading
   "CHOICESCRIPT LICENSE (CSL) v1.0 — Non-commercial usage and modification…" and
   [tegnike/aituber-kit](https://github.com/tegnike/aituber-kit) ships a 1,589 B custom dual licence
   that is non-commercial by default. Neither is visible in the SPDX field.
4. **The bespoke community-licence tier is now the top of the avatar category.**
   [duixcom/Duix-Mobile](https://github.com/duixcom/Duix-Mobile) (8,362★, 6,198 B "DUIX.COM COMMUNITY
   LICENSE AGREEMENT") and [Tencent-Hunyuan/HunyuanVideo-Avatar](https://github.com/Tencent-Hunyuan/HunyuanVideo-Avatar)
   (2,226★, Tencent community terms). The two highest-starred interactive-avatar runtimes in open
   source are **both** outside OSI licensing.

Three more SPDX corrections in the other direction, all read from the file:
[videojs/video.js](https://github.com/videojs/video.js) is **Apache-2.0**,
[cocos/cocos-engine](https://github.com/cocos/cocos-engine) is **MIT** (`LICENSE.md`),
[jarikomppa/soloud](https://github.com/jarikomppa/soloud) is **zlib/libpng** — and
[defold/defold](https://github.com/defold/defold) (6,491★) is **neither**: a bespoke "Defold Licence
v1.0", frequently listed as Apache-2.0 and not.

### Pushed within days of this pass — the live edge

| Repo | Licence | Stars | Last push |
|---|---|---|---|
| [godotengine/godot](https://github.com/godotengine/godot) | MIT | 120,887★ | 2026-11-26 |
| [pixijs/pixijs](https://github.com/pixijs/pixijs) | MIT | 48,914★ | 2026-11-26 |
| [videojs/video.js](https://github.com/videojs/video.js) | Apache-2.0 (file-read) | 40,260★ | 2026-11-26 |
| [renpy/renpy](https://github.com/renpy/renpy) | MIT (docs-tree) | 7,065★ | 2026-11-26 |
| [YarnSpinnerTool/YarnSpinner](https://github.com/YarnSpinnerTool/YarnSpinner) | MIT | 2,883★ | 2026-11-26 |
| [VoidmatrixHeathcliff/VoidNovelEngine](https://github.com/VoidmatrixHeathcliff/VoidNovelEngine) | MIT | 1,715★ | 2026-11-26 |
| [rive-app/rive-runtime](https://github.com/rive-app/rive-runtime) | MIT | 1,270★ | 2026-11-26 |
| [h5p/h5p-interactive-video](https://github.com/h5p/h5p-interactive-video) | MIT | 267★ | 2026-11-26 |
| [h5p/h5p-php-library](https://github.com/h5p/h5p-php-library) | **GPL-3.0** | 156★ | 2026-11-26 |
| [Lumieducation/H5P-Nodejs-library](https://github.com/Lumieducation/H5P-Nodejs-library) | **GPL-3.0** | 207★ | 2026-11-26 |
| [nathanhoad/godot_dialogue_manager](https://github.com/nathanhoad/godot_dialogue_manager) | MIT | 4,005★ | 2026-11-25 |
| [cocos/cocos-engine](https://github.com/cocos/cocos-engine) | MIT (file-read) | 9,949★ | 2026-11-25 |
| [YarnSpinnerTool/YarnSpinner-Unity](https://github.com/YarnSpinnerTool/YarnSpinner-Unity) | MIT | 856★ | 2026-11-25 |
| [pixiv/three-vrm](https://github.com/pixiv/three-vrm) | MIT | 2,309★ | 2026-11-24 |
| [OpenWebGAL/WebGAL](https://github.com/OpenWebGAL/WebGAL) | MPL-2.0 | 4,054★ | 2026-11-21 |
| [adorablelovelymia/twine-play-mcp](https://github.com/adorablelovelymia/twine-play-mcp) | MIT | 0★ | 2026-11-21 |
| [inkle/ink](https://github.com/inkle/ink) | MIT | 5,067★ | 2026-11-16 |

### The H5P seam — the decision point for every branching-scenario proposal

Branching narrative ships at scale today through H5P, and **its two halves are licensed
differently**: the content types are **MIT**
([h5p-branching-scenario](https://github.com/h5p/h5p-branching-scenario) 36★,
[h5p-interactive-video](https://github.com/h5p/h5p-interactive-video) 267★) while **every host
implementation is GPL-3.0** ([h5p-php-library](https://github.com/h5p/h5p-php-library) 156★,
[H5P-Nodejs-library](https://github.com/Lumieducation/H5P-Nodejs-library) 207★ with the full 35,146 B
GPLv3 text, [moodle-mod_hvp](https://github.com/h5p/moodle-mod_hvp) 160★). Secondary sources say
"H5P is MIT"; that is true only of the parts that do not run anything. Full analysis and the three
escape routes are in `repos/foundations.md` pass 29.

### The CTV tier nobody lists — 342 stars carrying every set-top deployment

[rdkcentral/Lightning](https://github.com/rdkcentral/Lightning) (Apache-2.0, 204★) and
[rdkcentral/Lightning-SDK](https://github.com/rdkcentral/Lightning-SDK) (Apache-2.0, 138★) are the
WPE/RDK UI framework for TV apps — the only open path from an interactive experience to a set-top box
without a native SDK per vendor. They are the thinnest-starred load-bearing repos recorded since
pass 25.

### The archaeology, stated because a client deserves it

[mozilla/popcorn-js](https://github.com/mozilla/popcorn-js) (MIT, 2,126★) — **archived 2017-09-21**.
The ancestor of web interactive video, dead nine years. [le-doux/bitsy](https://github.com/le-doux/bitsy)
(MIT, 1,065★) — archived 2026-07-22. [radiatoryang/merino](https://github.com/radiatoryang/merino)
(MIT, 298★) — archived 2021-12. This plane has buried a generation of tooling already; that history
belongs in the first conversation, not the third.

### Measured absences

| Searched | Result | Reading |
|---|---|---|
| `second screen companion tv` | **2 repos total, both 0★** | No companion-device layer. Nearest artefact: BBC's GPL-3.0 `audio-orchestrator`, 11★. |
| `branching scenario authoring` | 8 repos, none in-plane | The capability exists (H5P) and does not use these words. |
| interactive-video primitive in HLS/DASH | nothing | **No standard has one.** Every proposal implies a player you own. |
| `object based media` | 187 repos, none in-plane in top results | `bbc/storyplayer` (GPL-3.0, 19★) is the whole category. |

---

## 2026-11-26 — pass 28: age-rating vocabulary, territory mapping & enforcement (**the open vocabulary for this plane ships in the Linux desktop, and the media industry's own dataset — 110 systems, 77 territories — has no licence**)

18 slugs probed, **18/18 resolve** by `git ls-remote`. Licences read as bytes at 8 names × 2 branches.
Two datasets cloned and measured rather than described.

**The finding, stated first because it is the whole pass.** The only open, machine-readable,
multi-territory age-rating vocabulary in existence is **not** a media-industry artefact. It is
[hughsie/oars](https://github.com/hughsie/oars) (**LGPL-2.1**, `LICENSE` 26,526 B, 28★/12f,
2026-10-20) — the Open Age Ratings Service — plus
[ximion/appstream](https://github.com/ximion/appstream) (**LGPL-2.1**, `COPYING` 26,419 B, 283★/147f,
**2026-11-24**, two days before this pass), whose `as-content-rating.c` maps an OARS self-declaration
onto **16 national rating systems**. It exists to put age ratings on Linux desktop applications.
**It is the best thing available for rating a film catalogue, and that is an indictment of this
industry, not a compliment to GNOME.**

**Why it matters commercially:** the 16 systems span all four regions — INCAA (AR) and DJCTQ (BR) in
LATAM, PEGI/USK/KAVI/Russia in EMEA, ACB/CERO/GRAC/GSRR/MDA in APAC, ESRB in North America. A
component built on it is **regionally portable by construction**, the property passes 24 and 27
identified as scarce in multi-market work.

**But it is a projection, not a translation — and this was measured, not assumed.** Read side by side
with the industry dataset: AppStream emits **3 Argentine rungs** where INCAA has **5**, and **3
Australian rungs** where the National Classification Scheme has **8**. The dropped rungs are
disproportionately the consequential ones — **`condicionada`** (AR) and **`RC — Refused
Classification`** (AU), the two outcomes a distribution system must actually act on. And AppStream's
own source comment names its authority **twice** — `/* data obtained from
https://en.wikipedia.org/wiki/Video_game_rating_system */` at lines 298 and 693, covering both the
ladder table and the locale mapping. **Never present an OARS-derived rating to
a client as a board rating.**

**The enforcement layer is enormous and structurally unsound.**
[jellyfin/jellyfin](https://github.com/jellyfin/jellyfin) (**GPL-2.0**, 59,787★/5,879f, pushed the day
of this pass) ships **45 per-territory rating files** — enumerated by shallow sparse clone — a wider
territory set than AppStream's. **None of them carries a `system` field.** Ratings are matched as bare
strings, and when the viewer's country misses, the source says, verbatim: *"If we don't find
anything, check all ratings systems, starting with US"*, then walks every other country's table. The
token `16` is a valid rung on the PEGI, USK, DJCTQ, GRAC and Russian ladders and means different
things on each. **A German `16` can be scored by the US table and a parental control can silently
pass a title it should block.** `gb.json` and `uk.json` both exist. `br.json` carries a `9` band that
is not on the current ClassInd ladder — inherited from a `Deprecated=true` entry upstream, with the
deprecation flag left behind.

**The reusable rule, for all twelve industries:** a rating, code or classification is never a string.
It is a **pair — `(system, value)`** — and a schema that stores only the value resolves correctly in
testing and incorrectly in the second territory.

**The dataset nobody had opened.** Pass 16 added `MovieLabs/cmr-ratings` as a one-line row. Cloned and
measured for this pass: **110 rating systems, 77 territories, 506 files**, structured XML modelling
usage by medium and environment, per-rung `MinAge` / `MinRecAge` / `MinAgeSupervised` / `Deprecated`,
board logos, and sourcing notes. It is **the broadest ratings dataset in the world and it cannot be
used**: no licence file at 8 names × 2 branches, and **no README either** — default copyright, all
rights reserved, 1★/0f. It is also stale precisely where 2026 moved: **newest `LastChecked` anywhere
is 2023-07-11**, 25 systems have none at all, 54 were last *validated* in **2013**, and the **US/MPAA
entry has not been validated since 2013-09-28**. Its own ChangeLog is candid in a way no vendor would
be — systems taken *"from paramount database"* that *"could not be confirmed"*, ratings that *"differ
slightly from both news articles"*, boards with *"internal documents, but [no] public present or post
papers"* — plus a `toBeReviewed/` of 12 more. **Mine it to know what to verify; never vendor it.**

| Repo | Licence | Stars / forks | Pushed | Role in this plane |
|---|---|---|---|---|
| [hughsie/oars](https://github.com/hughsie/oars) | **LGPL-2.1** (26,526 B) | 28★ / 12f | 2026-10-20 | The vocabulary. The only one. |
| [ximion/appstream](https://github.com/ximion/appstream) | **LGPL-2.1** (26,419 B) | 283★ / 147f | 2026-11-24 | OARS → 16 territory ladders |
| [jellyfin/jellyfin](https://github.com/jellyfin/jellyfin) | **GPL-2.0** (18,014 B) | 59,787★ / 5,879f | 2026-11-26 | 45 territory files; the US-fallback defect |
| [seerr-team/seerr](https://github.com/seerr-team/seerr) | **MIT** (1,060 B) | 13,359★ / 1,169f | 2026-11-26 | Per-user rating ceilings + unrated toggle. **Best-licensed enforcement surface** |
| [sct/overseerr](https://github.com/sct/overseerr) | **MIT** | 4,952★ / 557f | 2026-02-15 | **ARCHIVED** — the predecessor. Read-only history; start at Seerr |
| [xbmc/xbmc](https://github.com/xbmc/xbmc) | **NOASSERTION** | 21,551★ / 6,692f | 2026-11-26 | Kodi. Resolve the licence from the tree, not the badge |
| [MovieLabs/cmr-ratings](https://github.com/MovieLabs/cmr-ratings) | **NONE** (no README either) | 1★ / 0f | 2026-06-17 | 110 systems / 77 territories / 506 files. Unusable as code; invaluable as a map |
| [R8rly/show](https://github.com/R8rly/show) | **CC-BY-SA-4.0** (20,139 B) | 22★ / 6f | 2026-11-05 | "SHOW Standard" — a normative bet. **Share-alike reaches derived catalogue metadata** |
| [varthe/Redirecterr](https://github.com/varthe/Redirecterr) | **NONE** | 146★ / 9f | 2026-10-14 | Routes requests by age rating. Licence genuinely absent (`README` 200, 8 names 404). **Do not ship** |
| [endlessm/malcontent](https://github.com/endlessm/malcontent) | **LGPL-2.1** | 5★ / 0f | **2022-03-21** | Stale fork. **Canonical malcontent is on GNOME GitLab, not GitHub** |
| [XMLTV/xmltv](https://github.com/XMLTV/xmltv) | **GPL-2.0** (18,092 B) | 425★ / 108f | 2026-10-13 | Already in the KB. Its `<rating system="...">` is **the one deployed format that models the pair correctly** |

**Channel notes for the next pass.** `gh api repos/{slug}` is **blocked** this session for
out-of-repo slugs — `gh api -X GET search/repositories -f q='repo:owner/name'` works and returns
stars, forks, SPDX id, `pushed_at` and `archived` in one call; use it as the only API channel.
**`www.movielabs.com` does not resolve from this session** (same class as `new.ddex.net` in pass 5),
so CMR's published HTML tables and any terms-of-use statement are **not verified** — but the GitHub
mirror carries the data, so the dataset itself was read directly rather than described. And pass 8's
licence-probe rule earned its keep again in reverse: six `raw` 404s for Jellyfin's rating files were
**my filename guess** (`.csv`, not `.json`); a shallow sparse clone settled it in one call.

## 2026-11-26 — pass 27: production-finance, rules-as-code & ledger infrastructure (**45 slugs probed, 45/45 resolve; a 10,349★ BSL trap, two rename redirects, and a plane whose generic layer beats its vertical layer**)

**The finding, stated first because it inverts the plane.** Searched as a *media* problem, production
finance is a desert — `completion bond film` **0**, `production incentive eligibility` **0**,
`ERPNext media production` **0**, `film production ERP` 5 results all at 0★ and unlicensed. Searched as
a *computation* problem, it holds some of the best-licensed, best-maintained code in this KB. **This is
the only plane in twenty-seven passes where the horizontal layer is stronger than the vertical layer**,
and the missing piece is a mapping, not a platform.

### Rules-as-code — the correct substrate for an incentive engine, and unclaimed for screen

| Repo | Stars / Forks | Licence | Last push |
|---|---|---|---|
| [CatalaLang/catala](https://github.com/CatalaLang/catala) | 2,456★ / 126f | **Apache-2.0** | 2026-11-26 (measurement day) |
| [apache/incubator-kie](https://github.com/apache/incubator-kie) (Drools/DMN) | 6,344★ / 2,608f | **Apache-2.0** | 2026-11-26 |
| [CacheControl/json-rules-engine](https://github.com/CacheControl/json-rules-engine) | 3,151★ / 511f | **ISC** | 2026-02-16 |
| [gorules/zen](https://github.com/gorules/zen) | 2,154★ / 237f | **MIT** | 2026-11-26 |
| [jhpyle/docassemble](https://github.com/jhpyle/docassemble) | 1,019★ / 324f | **MIT** | 2026-11-25 |
| [openfisca/openfisca-core](https://github.com/openfisca/openfisca-core) | 252★ / 100f | AGPL-3.0 | 2026-11-24 |
| [PolicyEngine/policyengine-us](https://github.com/PolicyEngine/policyengine-us) | 178★ / 224f | AGPL-3.0 | 2026-11-26 |
| [PolicyEngine/policyengine-core](https://github.com/PolicyEngine/policyengine-core) | 22★ / **31f** | AGPL-3.0 | 2026-11-25 |

`policyengine-us` carries **more forks (224) than stars (178)**, and `policyengine-core` the same
(31f/22★) — the signature of components used as a base rather than admired. It models US federal **and
state** tax law as executable code: **the closest prior art anywhere to a 39-state incentive engine**.

### Ledgers — seven engines, and the licence spread is the decision

| Repo | Stars / Forks | Licence | Last push |
|---|---|---|---|
| [tigerbeetle/tigerbeetle](https://github.com/tigerbeetle/tigerbeetle) | 17,467★ / 945f | **Apache-2.0** | 2026-11-25 |
| [beancount/beancount](https://github.com/beancount/beancount) | 6,210★ / 491f | GPL-2.0 | 2026-08-23 |
| [ledger/ledger](https://github.com/ledger/ledger) | 6,081★ / 554f | **BSD-3-Clause** (API said `NOASSERTION`; `LICENSE.md` 1,492 B read) | 2026-11-24 |
| [hledgerorg/hledger](https://github.com/hledgerorg/hledger) | 4,837★ / 427f | GPL-3.0 | 2026-11-26 |
| [beancount/fava](https://github.com/beancount/fava) | 2,615★ / 429f | **MIT** | 2026-11-23 |
| [formancehq/ledger](https://github.com/formancehq/ledger) | 1,489★ / 230f | **MIT** | 2026-11-26 |
| [flash-oss/medici](https://github.com/flash-oss/medici) | 364★ / 101f | **MIT** | 2026-07-29 |

### Solvers — where "which territory do we shoot in" is actually answered

| Repo | Stars / Forks | Licence | Last push |
|---|---|---|---|
| [apache/incubator-kie-optaplanner](https://github.com/apache/incubator-kie-optaplanner) | 3,512★ / 972f | **Apache-2.0** | 2026-07-14 |
| [TimefoldAI/timefold-solver](https://github.com/TimefoldAI/timefold-solver) | 1,882★ / 245f | **Apache-2.0** (`LICENSE.txt` 11,358 B read) | 2026-11-24 |

### ⚠️ The licence trap of this pass — the highest-starred one in twenty-seven passes

[akaunting/akaunting](https://github.com/akaunting/akaunting), **10,349★ / 3,029f**, pushed
2026-11-26, is **not open source**. `LICENSE.txt` (3,654 B, read in full) is the **Business Source
License**: MariaDB BSL text, *Licensor: Akaunting, Inc.*, with a limited Additional Use Grant. GitHub's
API says `NOASSERTION`. It ranks second for "open source accounting" and will surface in front of any
client or junior engineer searching this category.

**Same pass, same `NOASSERTION`, three different truths** — which is the real lesson:
`akaunting` → **BSL (unusable)**; `odoo/odoo` (56,124★) → **LGPL-3.0, Community only**
(`LICENSE` 43,529 B); `ledger/ledger` → **BSD-3-Clause, fully permissive**. The API's `NOASSERTION` is
**directionless**: it hid a trap, a dual-edition copyleft and a clean permissive grant in one search.
Also read this pass: `Gnucash/gnucash` → GPL-2.0-**or**-3.0 (19,423 B), `ledgersmb/LedgerSMB` →
GPL-2.0 (12,339 B), `koosoli/OpenShotDesigner` (47★) → **GPL-3.0** (35,809 B).

### 🔧 Two rename redirects, fresh instances of pass 17's oracle rule

`ls-remote` EXISTS **+** `search/repositories repo:<slug>` returns no item ⇒ stale slug:

| Stale slug (as published in docs, registries and blogs) | Canonical | What it hides |
|---|---|---|
| `simonmichael/hledger` | [hledgerorg/hledger](https://github.com/hledgerorg/hledger) | Person → org; 4,837★ GPL-3.0 invisible via the stale slug |
| `kiegroup/drools` **and** `apache/incubator-kie-drools` | [apache/incubator-kie](https://github.com/apache/incubator-kie) | **Both** legacy slugs still answer `ls-remote`; Drools is now an Apache monorepo |

**A 200 is never by itself proof a slug is canonical** — the mirror of pass 5's rule, confirmed twice.

### Platform layer (full table in `verticals/solutions.md` pass 27)

[frappe/erpnext](https://github.com/frappe/erpnext) 41,661★ GPL-3.0 · [frappe/frappe](https://github.com/frappe/frappe)
11,164★ **MIT** (the licence split that makes this tier usable) · [odoo/odoo](https://github.com/odoo/odoo)
56,124★ LGPL-3.0 · [firefly-iii/firefly-iii](https://github.com/firefly-iii/firefly-iii) 25,348★ AGPL-3.0 ·
[Dolibarr/dolibarr](https://github.com/Dolibarr/dolibarr) 7,903★ GPL-3.0 · [Gnucash/gnucash](https://github.com/Gnucash/gnucash)
4,429★ GPL-2/3 · [espocrm/espocrm](https://github.com/espocrm/espocrm) 3,674★ AGPL-3.0 ·
[apache/ofbiz-framework](https://github.com/apache/ofbiz-framework) 1,151★ **Apache-2.0** (the only fully
permissive ERP in the tier) · [ledgersmb/LedgerSMB](https://github.com/ledgersmb/LedgerSMB) 579★ GPL-2.0 ·
[cgwire/kitsu](https://github.com/cgwire/kitsu) 779★ + [cgwire/zou](https://github.com/cgwire/zou) 203★ AGPL-3.0 ·
[ChrisTempel/CineSpend](https://github.com/ChrisTempel/CineSpend) 8★ MIT (unchanged since pass 17).

### Measured absences — full gap table in `repos/foundations.md` pass 27

`completion bond film` **0** · `production incentive eligibility` **0** · `ERPNext media production`
**0** · `film tax credit` **7** (4 relevant, all proprietary or unlicensed) · `recoupment waterfall`
**2** (1 relevant, unlicensed) · `cost report film production` 5/**0** · `errors and omissions
insurance` 6/**0** · `film production ERP` 5/**0** · `royalty accounting` 47/**0**. **False
abundance:** `production accounting` **1,946/0** and `residuals` **11,617/0** — 13,563 repositories,
zero relevant, on the two terms a domain expert would call unambiguous.

## 2026-11-26 — pass 26: energy, carbon & environmental-footprint infrastructure (**21 slugs probed, 21/21 resolve; 3 compilation-licence cases read byte by byte, and one of them collides with DRM**)

Verification for every row below: existence by `git ls-remote` (21/21 OK, 0 absent), stars/forks/last-push
via `search/repositories`, and for every `NOASSERTION` the **actual licence file read and counted**. The
licence-byte read was not a formality this time — it changed the classification of three repos and
produced the single most consequential finding of the pass.

**🔧 Oracle correction, and it applies to all twelve industries.** This pass found a repository that
**exists and is empty**: `Hazrat-Ali9/Carbon-Aware-AI-Model-Scheduling` is indexed by
`search/repositories` with **30 stars and a `pushed_at` of 2026-08-15**, and `git ls-remote` against it
returns **0 refs** — no heads, no tags, nothing — with `README.md` 404 on both `main` and `master`.
Stars and a push date are therefore **not evidence that a repository contains code.**

Two consequences for the probe this KB has been recommending since pass 5:

1. `git ls-remote -h --exit-code <url>` exits non-zero on an empty-but-real repository, so it reports
   **ABSENT for something that exists**. Conversely `git ls-remote <url>` (no `-h`) exits **0** for that
   same repo because the connection succeeded. Neither form alone distinguishes "gone" from "empty".
2. **Count the refs.** `git ls-remote <url> | wc -l` is the reliable test: `0` means absent *or* empty —
   both equally unusable — and any positive count means there is something to read. Verify with a
   `README.md` fetch when the distinction matters for a write-up.

This is the first empty repository recorded in this KB, and it was caught only because the final
URL-verification sweep disagreed with the discovery query. **Run that sweep; the two channels answer
different questions.**

### 🔴 The finding: co2.js carries ODbL data into a plane built on DRM

[thegreenwebfoundation/co2.js](https://github.com/thegreenwebfoundation/co2.js) is the obvious
substrate for any per-stream or per-byte carbon metric, and the GitHub API reports it as
**`NOASSERTION`**. Reading `LICENSE` (main and master, **12,678 B** — note that canonical Apache-2.0 is
11,357 B, and *that 1.3 KB difference is the whole story*) shows it is not one licence but a **stack of
four**:

| Layer inside co2.js | Licence | What it obliges you to do |
|---|---|---|
| The library source code | **Apache-2.0** | Standard permissive terms |
| Ember average grid-intensity data | **CC-BY-SA** | Attribute; share-alike on derivatives |
| Green Web Foundation marginal-intensity data (derived from the UNFCCC **IFI TWG** harmonised dataset) | **CC-BY-SA** | Attribute; share-alike |
| **Electricity Maps** annual grid-intensity data | **ODbL** | Attribute **· Share-Alike: keep derivative works under the same licence · Keep open: "provide unrestricted versions if using DRM"** |

That last cell is the one to carry into a client conversation. **This KB says `DRM` 53 times, `Widevine`
13 and `PlayReady` 12** — DRM is the default state of commercial media delivery. The ODbL "keep open"
parallel-distribution requirement is written for exactly the situation a streaming operator creates:
compute a per-title or per-stream emissions figure from the bundled Electricity Maps data, embed it in a
technically-restricted product, and the obligation to also offer an unrestricted version of *the
database or derived database* is live. No SPDX field, no badge and **no SBOM scan of the source tree can
see this** — the repo-level answer is "Apache-2.0", and the repo-level answer is wrong.

This is the **third** instance of the pass-8 law that *the licence can belong to the compilation, not the
repository* (after `acoustid/chromaprint` and `metabrainz/musicbrainz-server`), and the first where the
compilation's obligation **conflicts with a technical norm of the industry** rather than merely adding a
copyleft duty. Mitigation is cheap and must be chosen deliberately — see Pattern 26.1.

A fourth instance sits right next to it:
[green-coding-solutions/green-metrics-tool](https://github.com/green-coding-solutions/green-metrics-tool)
also reports `NOASSERTION`, and its `LICENSE` is a **35,429 B "License Index"** whose own table of
contents reads *1. License for Green Metrics Tool Source Code · 2. License for the bundled Electricity
Maps Grid Intensity Data*, with the **AGPL-3.0** text at line 652, co2.js's Apache terms bundled at line
7, and the Electricity Maps ODbL terms at line 673. **Three licences, two of them with share-alike
duties, in one dependency.**

### The substrate — real, permissive, and maintained (this layer is healthy)

| Repo | Stars | Forks | Licence | Last push | Role in a media footprint stack |
|---|---|---|---|---|---|
| [electricitymaps/electricitymaps-contrib](https://github.com/electricitymaps/electricitymaps-contrib) | 4,057★ | 1,073f | **AGPL-3.0** | 2026-11-26 | The grid-intensity source everything else re-publishes. **Copyleft — consume the data under its own terms, do not vendor the app** |
| [hubblo-org/scaphandre](https://github.com/hubblo-org/scaphandre) | 2,018★ | 133f | **Apache-2.0** | 2026-07-19 | Host power metrology (RAPL). The most-starred *permissive* measurement tool in the plane; **4 months without a push** |
| [mlco2/codecarbon](https://github.com/mlco2/codecarbon) | 1,955★ | 360f | **MIT** | 2026-11-22 | Emissions of a compute job. The canonical way to put a number on a GenAI render or training run |
| [sustainable-computing-io/kepler](https://github.com/sustainable-computing-io/kepler) | 1,605★ | 294f | **Apache-2.0** | **2026-11-26** | Per-pod energy in Kubernetes via eBPF. Pushed today; the right instrument for a containerised transcode farm |
| [cloud-carbon-footprint/cloud-carbon-footprint](https://github.com/cloud-carbon-footprint/cloud-carbon-footprint) | 1,054★ | 310f | **Apache-2.0** | 2026-04-23 | Cloud billing exports → emissions estimates. **7 months quiet**; still the only credible open multi-cloud estimator |
| [Green-Software-Foundation/carbon-aware-sdk](https://github.com/Green-Software-Foundation/carbon-aware-sdk) | 600★ | 113f | **MIT** | 2026-11-04 | Shift a workload to a cleaner hour or region. The *reduce* layer, and the only one with a real adoption story |
| [thegreenwebfoundation/co2.js](https://github.com/thegreenwebfoundation/co2.js) | 499★ | 73f | **Apache-2.0 code + CC-BY-SA + ODbL data** (12,678 B read) | 2026-11-17 | Bytes → gCO2e (Sustainable Web Design and 1-byte models). **Read the ODbL note above before shipping** |
| [Green-Software-Foundation/sci](https://github.com/Green-Software-Foundation/sci) | 298★ | — | **Not OSI** (JDF "AS IS", W3C patent mode, 2,347 B) | 2026-01-05 | The SCI specification, **ISO/IEC 21031**. Implement the standard; do not vendor the repo |
| [green-coding-solutions/green-metrics-tool](https://github.com/green-coding-solutions/green-metrics-tool) | 260★ | 50f | **AGPL-3.0 + ODbL + Apache** (35,429 B index read) | 2026-11-26 | Repeatable measurement lab for a pipeline. Pushed today; copyleft plus two data licences |
| [powerapi-ng/powerapi](https://github.com/powerapi-ng/powerapi) | 255★ | 45f | **BSD-3-Clause** | 2026-11-24 | Software power-meter toolkit. The most permissive licence band in the plane |
| [Green-Software-Foundation/if](https://github.com/Green-Software-Foundation/if) | 184★ | 54f | **MIT** | 2026-10-24 | Impact Framework: manifest-driven impact modelling — turns a pipeline description into a calculable footprint |
| [carbonalyser/Carbonalyser](https://github.com/carbonalyser/Carbonalyser) | 166★ | 35f | **MIT** | **2023-01-02** | Browser-side traffic→emissions extension. **Dormant ~4 years** — cite as a method reference, not a dependency |
| [Boavizta/boaviztapi](https://github.com/Boavizta/boaviztapi) | 102★ | 45f | **AGPL-3.0** | 2026-11-24 | **Embodied** (manufacturing) carbon of hardware — the half that operational tools omit. Copyleft |
| [thegreenwebfoundation/grid-intensity-go](https://github.com/thegreenwebfoundation/grid-intensity-go) | 84★ | 10f | **Apache-2.0** | 2026-05-11 | Grid intensity as a Go library/exporter, for edge and CDN nodes |
| [GreenScheduler/cats](https://github.com/GreenScheduler/cats) | 82★ | 23f | **MIT** (1,076 B read) | **2026-11-26** | Climate-Aware Task Scheduler — a CLI that defers a job to a low-carbon window. Pushed today |
| [Green-Software-Foundation/sci-otel](https://github.com/Green-Software-Foundation/sci-otel) | 10★ | — | **Apache-2.0** | 2026-11-18 | SCI as an OpenTelemetry vocabulary — how a footprint becomes an ordinary metric on an existing dashboard |

### The media-native layer — one repo, three stars

| Repo | Stars | Licence | Last push | Why it matters anyway |
|---|---|---|---|---|
| [BreakTools/deadline-energy-cost-calculator](https://github.com/BreakTools/deadline-energy-cost-calculator) | **3★** | **MIT** (1,067 B read) | 2025-09-17 | **The only media-production-native energy repo found in the entire pass.** An AWS/Thinkbox **Deadline** event plugin that computes the energy and cost of a render job. Deadline is standard in VFX and animation facilities, so this 3-star plugin sits on a genuinely wide installed base — and nobody has built on it |

Twenty-five passes of this KB, and the whole intersection of *media* and *energy* in open source is one
MIT file with three stars. That is the pass's second headline.

### Regional and compliance infrastructure

| Repo | Stars | Licence | Last push | Region | Note |
|---|---|---|---|---|---|
| [ABC-TransitionBasCarbone/bilan-carbone](https://github.com/ABC-TransitionBasCarbone/bilan-carbone) | 5★ | **MIT** (1,081 B, on `master`) | **2026-11-26** | EMEA | **Association Bilan Carbone** — the body that owns France's official corporate carbon methodology, shipping MIT code and pushing today. 5 stars. The most under-recognised institutional asset in the plane |
| [aimabel-ai/esrs-xbrl-parser](https://github.com/aimabel-ai/esrs-xbrl-parser) | 12★ | **ISC** (746 B, "The Climate Action Agency AB") | 2024-12-17 | EMEA | Parses **ESRS** XBRL taxonomies. **ISC** — a permissive band this KB had not recorded before. Dormant ~23 months |
| [agirgol/carbon-accounting-dotnet](https://github.com/agirgol/carbon-accounting-dotnet) | 0★ | **MIT** | 2026-08-17 | Global | GHG Protocol + **ISO 14064-1** Scope 1/2/3 for .NET, with a versioned, source-cited emission-factor catalogue. 0 stars, clean licence, correct standards — recorded for completeness |

### The generic-ESG swarm, and why it is not supply

`ghg protocol scope 3 accounting` returns 16 repositories; **eight of the first eight have 0 stars**, and
most were created or pushed within the last six months (`openscope`, `carbon-accounting-sbti`,
`clima-carbon-accounting`, `carbonledger`, `emitly`, `esg-carbon-platform`…). `esg reporting agent`
returns 62 with the same profile. This is the **vibe-coded-compliance pattern**: a regulation creates
visible demand, dozens of single-author repos appear within weeks, none acquires users, and the totals
look like a thriving ecosystem. **Counting repositories here measures enthusiasm, not supply.** The
adoptable set in this plane is the ~16 rows above, and it is institutional almost without exception —
Green Software Foundation, Green Web Foundation, Hubblo, Boavizta, PowerAPI, Electricity Maps, the
Association Bilan Carbone.

## 2026-11-26 — pass 25: the traffic, sales-order-to-air & billing plane (**the KB had recorded this plane's anchor as dead; it has 332 stars and was pushed three days ago**)

Infrastructure and platform repos. The agent layer for this plane is in `agents/trending.md` pass 25.
All rows verified 2026-11-26 via `git ls-remote` (existence), `search/repositories -f q='repo:<slug>'`
(canonical slug, stars, forks, last push, SPDX) and **by reading the licence file** wherever the API
returned `NONE` or `NOASSERTION`. 20/20 slugs resolved and 20/20 were indexed at the slug written here.

### ⚠️ A correction to this KB's own record — the anchor of this plane is alive

`repos/trending.md` (pass 5 history, line ~2057) and `verticals/solutions.md` (~line 94) both record:

> `immstudios/nebula` | GPL-3.0 | 20★ | 2023-04-26 | **ARCHIVED.** Recommended by current search
> results as an open MAM + broadcast automation system; **it is dead at this slug.**

**That is true of the slug and wrong about the project.** Nebula moved org. It is alive, maintained
and in production:

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [nebulabroadcast/nebula](https://github.com/nebulabroadcast/nebula) | **GPL-3.0** (35,141 B) | 332 | 38 | **2026-11-23** | **The anchor of this plane.** Broadcast automation + MAM for television, radio and VOD. Its README: *"Since 2012 Nebula has proven stable and reliable software in 24/7 broadcast environment and it is now used by TV and production companies worldwide."* Python backend + React frontend, Python 3.14, maintained-2026 badge. **16× the stars of the slug this KB called dead.** |
| [nebulabroadcast/nebula-worker](https://github.com/nebulabroadcast/nebula-worker) | **GPL-3.0** | 6 | 3 | 2026-11-15 | The media-processing worker node. Required for a real deployment. |
| [nebulabroadcast/firefly](https://github.com/nebulabroadcast/firefly) | **GPL-3.0** | 29 | 6 | 2026-10-30 | Desktop client for **linear broadcast planning, scheduling and playout**. **Being phased out** — the README states the web interface now has full feature parity. Take it only if a desktop client is a hard requirement. |
| [nebulabroadcast/nebula-tutorial](https://github.com/nebulabroadcast/nebula-tutorial) | **NONE** | 13 | 9 | 2025-12-20 | Example `docker-compose.yml`, default settings and plugins — "the best starting point". **No licence file** (11 filenames × 2 branches probed; control `README.md` = 200, so this is a real absence, not a naming miss). **Do not copy its files into a client repository.** |

**Method lesson, reusable in all twelve industries:** when a repo looks archived, search the
**project name as an owner**, not just the slug. `immstudios` → `nebulabroadcast` was one call. A pass
that stops at the dead slug writes off the live anchor of an entire plane — which is what happened
here, and it stood in the KB until this pass.

### The platform tier for this plane

| Repo | License | Stars | Forks | Last push | Why it matters |
|---|---|---|---|---|---|
| [AzuraCast/AzuraCast](https://github.com/AzuraCast/AzuraCast) | **AGPL-3.0** | **4,118** | 764 | 2026-11-25 | **New to this KB** (0 prior mentions). Self-hosted web radio management suite with turnkey installers for the full stack. **The highest-starred broadcast-operations platform in the plane** — by a factor of 12 over Nebula. Station/playlist/scheduling operations, not traffic: no rate cards, no invoicing. |
| [ElvishArtisan/rivendell](https://github.com/ElvishArtisan/rivendell) | **GPL-2.0** — API says `NONE`; verified by reading `COPYING` (17,992 B, "GNU GENERAL PUBLIC LICENSE Version 2") | 250 | 76 | 2026-08-26 | **The architectural evidence of this whole pass.** The most mature open-source radio automation system in the world, and its README says it *"supports importation of schedule information from a wide variety of **third-party traffic and music scheduling systems**."* It does not implement traffic — **it delegates it to proprietary vendors, by design.** Open source' own architecture concedes the commercial layer. |
| [libretime/libretime](https://github.com/libretime/libretime) | AGPL-3.0 | 941 | 251 | 2026-11-22 | Already in this KB (pass 5). Radio automation/scheduling, the maintained Airtime fork. Shown here for completeness of the tier. |
| [mint-dewit/folderplayout](https://github.com/mint-dewit/folderplayout) | **MIT** | 64 | 7 | 2023-12-31 | CasparCG client for scheduled recurring playlist playback. **The permissive bridge between a schedule and a playout engine** — the one MIT-licensed piece in the chain. Dormant since 2023; small enough to read and fork. |
| [efeone/beams](https://github.com/efeone/beams) | **MIT** — in **lowercase `license.txt`** (1,069 B), not `LICENSE` | 21 | 15 | 2026-04-30 | A Frappe/ERPNext app, **and not what its name suggests.** See the characterisation note below — this row would have become wrong data if taken from the title. |
| [adam-rms/adam-rms](https://github.com/adam-rms/adam-rms) | **AGPL-3.0** | 64 | 47 | 2026-11-17 | Rental/asset management for theatre, AV and broadcast: crew and kit booking. Adjacent, not in-plane — **it books the kit, not the airtime.** Unusually high fork:star ratio (0.73), which means people deploy it. |

**BEAMS, characterised from its doctypes rather than its title.** "Broadcast Enterprise Administration
Management System" with `frappe`/`erpnext`/`broadcasting` topics sounds like a broadcast ERP covering
ad sales. Its README is four lines and documents nothing, so the repo was cloned and its doctypes
read. What is actually there: `job_portal`, `roster`, `manpower_transaction_log`, `substitute_booking`,
`stringer_bill` + `stringer_bill_detail`, `courier_log`, `vehicle_log_detail`, `fuel_card_log`,
`key_log`, `visitor_log`, `security_patrol_log`, plus `sales_order`/`sales_invoice` **inherited from
ERPNext**. So BEAMS is a broadcaster **back-office** system — HR, rostering, fleet, security, and
paying freelance correspondents — **not a traffic or ad-sales system.** It is nonetheless the only
**MIT-licensed broadcast-specific business application** found in 25 passes, and `stringer_bill`
(settling with freelance correspondents) is a media-specific object no other repo in this KB models.

### The permissive billing tier — because the plane's own billing step is empty

Step 3 of the gradient has no open-source implementation, so it must be **composed**. These are the
permissive engines to compose it from (none is media-specific; that is the point):

| Repo | License | Stars | Forks | Last push | Role in this plane |
|---|---|---|---|---|---|
| [killbill/killbill](https://github.com/killbill/killbill) | **Apache-2.0** | **5,870** | — | 2026-11-26 | Subscription billing and payments platform. The invoice/credit engine for reconciled spots and makegood obligations. Pushed on measurement day. |
| [killbill/killbill-admin-ui](https://github.com/killbill/killbill-admin-ui) | **MIT** | 70 | — | 2026-11-26 | Admin UI engine for the above. |
| [killbill/killbill-commons](https://github.com/killbill/killbill-commons) | **Apache-2.0** | 145 | — | 2026-10-06 | Reusable Java components. |
| [openmeterio/openmeter](https://github.com/openmeterio/openmeter) | **Apache-2.0** | 2,471 | 247 | 2026-11-26 | Already in this KB. Usage metering/aggregation — the delivered-impressions side for addressable and CTV breaks. |
| [aureuserp/aureuserp](https://github.com/aureuserp/aureuserp) | **MIT** | **12,301** | — | 2026-11-24 | **New to this KB.** Laravel ERP with invoicing/accounting. The most-starred **MIT** ERP found; relevant because this plane's missing step is an accounting step. |

### The BXF trap — a licence category this KB has not recorded before

BXF (SMPTE ST 2021) is the XML interchange format between traffic, playout and automation — exactly
the integration a traffic engagement must build. There is **no usable open implementation, and the
schema itself may not be redistributed:**

| Repo | License | Stars | Forks | Last push | Finding |
|---|---|---|---|---|---|
| [SMPTE/st2021-4](https://github.com/SMPTE/st2021-4) | **All Rights Reserved** — API says `NOASSERTION`; `LICENSE.md` (269 B) **read in full** | 2 | 1 | 2026-11-11 | The official BXF schema documentation. Its licence: *"Copyright © by the Society of Motion Picture and Television Engineers. **All rights reserved. No part of this material may be reproduced, by any means whatsoever, without the prior written permission** of the Society of Motion Picture and Television Engineers."* **Published on GitHub and not redistributable.** |
| [JoeldelPilar/bxf-manager](https://github.com/JoeldelPilar/bxf-manager) | **NONE** (11 filenames × 2 branches probed; control `README.md` = 200 → real absence) | 4 | 1 | 2025-10-09 | The only BXF *tool* on GitHub. No licence grant ⇒ default copyright, all rights reserved. |

**New licence category: free of charge, published openly, and still not redistributable.** Pass 5
recorded two *taxed* content layers (CPT in healthcare, MedDRA in healthcare). This is the first where
the artefact costs nothing to view, sits in a public GitHub repo, and **still cannot be vendored** —
which is far easier to get wrong, because nothing about the retrieval feels like a licence event. No
SPDX field, badge or SBOM scan of the source tree catches it. See Pattern 25.3 for the gate.

### Two reusable method corrections

**(1) `git ls-remote` follows GitHub's rename/transfer redirects, so it is an existence oracle and
*not* a canonicity oracle.** The web search for this plane returned `mrtero22/9eye`. `ls-remote` said
**OK**. But `search/repositories -f q='repo:mrtero22/9eye'` returns **422 — "cannot be searched
either because the resources do not exist or you do not have permission"**, while
`repo:9eye9/9eye` returns **1**. Both slugs serve the **same HEAD sha**
`bd151c528cd695131d038653ccd4476406946772`, and 9eye's own README badges still point at the old
slug. This refines pass 5's rule ("`ls-remote` is the only existence oracle"): it proves the
repository **exists**, never that the **slug is current**. Cross-check every URL with
`search/repositories -f q='repo:<slug>'` before writing it — a redirect slug is not a 404 today and
breaks the day the old name is reused. All 20 slugs in this pass were checked this way.

**(2) In this environment, use `search/repositories`, not `repos/<slug>`, for third-party metadata.**
`gh api repos/9eye9/9eye` returns **403** ("GitHub access to this repository is not enabled for this
session") for any repo outside the session's own scope, while
`gh api -X GET search/repositories -f q='repo:9eye9/9eye'` returns stars, forks, SPDX, created and
pushed dates for the **same** repo in one call. A pass that only tries `repos/` will wrongly conclude
a repo is inaccessible.

Also re-confirmed for the third time: **lowercase `license.txt`** must stay in the probe list —
`efeone/beams` has no `LICENSE`, and its MIT grant is in `license.txt` (1,069 B).

### Measured zeros for infrastructure (what was searched, what was missing)

`broadcast as-run reconciliation` → **0 results**. `spot booking advertising` → **0 results**.
`EPG schedule generator` → 3 results, top is 0★. `music scheduling rotation` → 5, and the only
on-topic repos are [itsoumya-d/rcs-music-scheduler](https://github.com/itsoumya-d/rcs-music-scheduler)
(**MIT**, **0★**, 2026-11-06 — "C# .NET 10 radio music scheduler: rotation, separation, **dayparts**
and conflict explanations"; the only repo anywhere that contains the word *daypart*, and nobody has
starred it) and [mickaelmonsieur/openstudio](https://github.com/mickaelmonsieur/openstudio)
(**GPL-3.0**, **0★**, 2026-06-14, a Rust radio-automation **prototype**). Recorded as zeros, not as
recommendations. `broadcast erp` surfaced [stukenov/broadcast-erp](https://github.com/stukenov/broadcast-erp)
(**MIT**, **0★**, 2026-11-16, Laravel, claims schedules/programs/sales/inventory) — one of a cluster of
six same-author playout repos all pushed 2026-11-16 with 0–3 stars; **unproven, listed for the record
only.**

### Contaminated-total record: `rate card` → 2,013 results, zero relevant

Pass 5's corollary was *read the results, not the total* (`eidr` 160/0, `isan` 1942/0). This plane
sets the new record and explains why: **"traffic" and "rate card" are the most contaminated terms in
this KB.** `broadcast traffic` 163/**0** (satellite ship detection, V2X signal decoders, mDNS, virtual
ATC); `radio traffic` 246/**0** (ADS-B, FLARM, SOCKS proxies); `rate card` **2,013**/**0** (virtual
displays, GPU monitors, heart-rate clients); `traffic billing` 136/**0** (ISP bandwidth billing);
`advertising sales management` 51/**0**. In media these words mean commercial inventory
administration; everywhere else in software they mean packets or vehicles. A pass that trusted totals
would have reported this plane as **richly served**. It is empty.

---

## 2026-11-26 — pass 24: the owned-channel & audience-relationship plane (**the transport layer is permissive and shipping daily; the consent and identity layer at the end of it has 18 stars**)

Infrastructure and platform repos. The agent layer for this plane is in `agents/trending.md` pass 24.
All rows verified 2026-11-26 via the GitHub API, licence files **read** where the API returned
`NONE`/`NOASSERTION` (nine corrections — the highest rate of any pass here).

**Why this plane entered the KB now:** the vocabulary probe found the string **`email` zero times in
20,389 lines**, along with `Listmonk`, `Mautic`, `Coral`, `Novu`, `ntfy`, `web push`, `Discourse`,
`cookieless` and `UID2`. The KB had the *observation* half of first-party data (Snowplow, Matomo,
PostHog, Plausible, Jitsu, Keycloak) and none of the *activation* half.

### Pushed within the last 7 days — the live edge of this plane

| Repo | License | Stars | Forks | Last push | What it is |
|---|---|---|---|---|---|
| [TryGhost/Ghost](https://github.com/TryGhost/Ghost) | MIT | 55,925 | 12,088 | 2026-11-26 | Publishing + memberships + newsletters in one MIT codebase. |
| [discourse/discourse](https://github.com/discourse/discourse) | GPL-2.0 | 48,117 | 9,057 | 2026-11-26 | General-purpose community platform. |
| [novuhq/novu](https://github.com/novuhq/novu) | **MIT** (file read) | 40,432 | 4,571 | 2026-11-26 | Multi-channel notification infrastructure (email/SMS/push/in-app), preferences, digest batching. Highest-starred permissive repo in the plane. |
| [binwiederhier/ntfy](https://github.com/binwiederhier/ntfy) | Apache-2.0 | 35,771 | 1,753 | 2026-11-25 | Self-hostable HTTP pub/sub push. |
| [knadh/listmonk](https://github.com/knadh/listmonk) | **AGPL-3.0** | 24,473 | 2,836 | 2026-11-26 | The default self-hosted newsletter manager. **v7.0.0-beta.2 released 10 Nov 2026.** |
| [resend/react-email](https://github.com/resend/react-email) | MIT | 20,008 | 1,122 | 2026-11-26 | Emails as React components. |
| [mjmlio/mjml](https://github.com/mjmlio/mjml) | MIT | 18,305 | 1,007 | 2026-11-26 | Responsive-email markup language. |
| [postalserver/postal](https://github.com/postalserver/postal) | MIT | 16,982 | 1,325 | 2026-11-20 | Full open mail-delivery platform. |
| [NodeBB/NodeBB](https://github.com/NodeBB/NodeBB) | GPL-3.0 | 15,254 | 2,999 | 2026-11-26 | Real-time Node.js forum. |
| [axllent/mailpit](https://github.com/axllent/mailpit) | MIT | 11,044 | 381 | 2026-11-25 | SMTP capture + API for testing sends. |
| [mautic/mautic](https://github.com/mautic/mautic) | **GPL-3.0-or-later** (file read) | 11,123 | 3,572 | 2026-11-26 | Marketing automation: segments, campaigns, drip. |
| [Mailu/Mailu](https://github.com/Mailu/Mailu) | **MIT** (file read) | 7,642 | 1,037 | 2026-11-25 | Docker mail server. |
| [foxcpp/maddy](https://github.com/foxcpp/maddy) | GPL-3.0 | 6,142 | 346 | 2026-11-21 | Composable Go mail server. |
| [Mailtrain-org/mailtrain](https://github.com/Mailtrain-org/mailtrain) | GPL-3.0 | 5,748 | 707 | 2026-11-25 | Self-hosted newsletter app. |
| [umputun/remark42](https://github.com/umputun/remark42) | **MIT** | 5,654 | 463 | 2026-11-25 | Embeddable privacy-friendly comment engine. |
| [haraka/Haraka](https://github.com/haraka/Haraka) | MIT | 5,646 | 720 | 2026-11-23 | Extensible event-driven SMTP server. |
| [orestbida/cookieconsent](https://github.com/orestbida/cookieconsent) | MIT | 5,785 | 505 | 2026-11-22 | Consent banner (UI, not compliance). |
| [jitsucom/jitsu](https://github.com/jitsucom/jitsu) | MIT | 5,140 | 403 | 2026-11-26 | MIT event ingestion; **no identity resolution** — you build it. |
| [web-push-libs/web-push](https://github.com/web-push-libs/web-push) | **MPL-2.0** (file read) | 3,580 | 331 | 2026-11-23 | Node Web Push (RFC 8030/8291/8292, VAPID). |
| [pentacent/keila](https://github.com/pentacent/keila) | **AGPL-3.0** | 2,269 | 180 | 2026-11-24 | EU-built, EU-hosted newsletter tool — the EMEA data-residency answer. |
| [c15t/c15t](https://github.com/c15t/c15t) | **Apache-2.0** | 2,045 | 287 | 2026-11-26 | Headless consent manager; optional `@c15t/iab` TC-string add-on. Best-licensed active CMP. |
| [coralproject/talk](https://github.com/coralproject/talk) | **Apache-2.0** (file read, © 2025 Vox Media) | **2,005** | 374 | 2026-11-26 | **The only comment platform built for newsrooms.** Per-stream moderation, queues, AI-assisted moderation, publisher owns the data. |
| [maizzle/framework](https://github.com/maizzle/framework) | MIT (file read) | 1,624 | 69 | 2026-11-25 | Tailwind email framework. **Not** `maizzle/maizzle` — see the decoy note below. |
| [domainaware/parsedmarc](https://github.com/domainaware/parsedmarc) | Apache-2.0 | 1,321 | 277 | 2026-11-23 | Parses DMARC aggregate/forensic reports. The quiet high-value row. |
| [unitaryai/detoxify](https://github.com/unitaryai/detoxify) | Apache-2.0 | 1,320 | 149 | 2026-11-11 | Open toxicity model; nothing wires it to a comment platform. |
| [apache/unomi](https://github.com/apache/unomi) | Apache-2.0 | **382** | 148 | 2026-11-26 | **The only genuinely Apache-licensed CDP that exists.** |
| [mozilla-services/autopush-rs](https://github.com/mozilla-services/autopush-rs) | MPL-2.0 | 363 | 32 | 2026-11-25 | Mozilla's production push server in Rust. |
| [InteractiveAdvertisingBureau/iabtcf-es](https://github.com/InteractiveAdvertisingBureau/iabtcf-es) | Apache-2.0 | **156** | 101 | 2026-11-03 | Official TCF v2 encode/decode suite. |
| [IABTechLab/uid2-operator](https://github.com/IABTechLab/uid2-operator) | Apache-2.0 | **18** | 19 | 2026-11-26 | **The cookie replacement for the open web, with eighteen stars.** Pushed today — not abandoned, just not self-served. |

### Slower-moving but in-plane

| Repo | License | Stars | Last push | Note |
|---|---|---|---|---|
| [ory/kratos](https://github.com/ory/kratos) | Apache-2.0 | 13,983 | 2026-07-29 | Identity capture / registration wall. **Four months idle** — watch it. |
| [isso-comments/isso](https://github.com/isso-comments/isso) | MIT | 5,316 | 2026-10-25 | Disqus alternative. **Org renamed** — `posativ/isso` no longer resolves in GitHub search. |
| [mettle/sendportal](https://github.com/mettle/sendportal) | **MIT** | 2,193 | 2026-10-22 | **The only permissive newsletter manager** — 9% of listmonk's stars. |
| [web-push-libs/pywebpush](https://github.com/web-push-libs/pywebpush) | MPL-2.0 | 381 | 2026-09-01 | Python push payload encryption. |
| [InteractiveAdvertisingBureau/Global-Privacy-Platform](https://github.com/InteractiveAdvertisingBureau/Global-Privacy-Platform) | **CC-BY-3.0 spec, not code** | 128 | 2026-11-04 | One consent string across GDPR + US state regimes. Documents, not software — demoted per pass 4's rule. |

### ⛔ Do not ship — measured this pass

| Repo | Stars | Finding |
|---|---|---|
| [rudderlabs/rudder-server](https://github.com/rudderlabs/rudder-server) | 4,521 | **Elastic License 2.0** (file read). Not OSI. The CDP every 2026 listicle calls open source; ELv2 forbids managed-service provision to third parties. |
| [ConsentOS/consentos](https://github.com/ConsentOS/consentos) | 25 | **Elastic License 2.0** (file read). TCF v2.3 + GPP v1 + Consent Mode v2, source-available only. |
| [stalwartlabs/stalwart](https://github.com/stalwartlabs/stalwart) | 16,395 | **Licence unresolved.** No `LICENSE`, `LICENSE.md`, `COPYING`, `LICENSE-AGPL` or `LICENSES/` file at the repo root on `main` (six paths checked), no `license` key in the workspace `Cargo.toml`, and the GitHub API reports none. A 16,395-star mail server with no licence discoverable at the root — **do not ship until the client's counsel resolves it.** |
| ⛔ [djyde/cusdis](https://github.com/djyde/cusdis) | 2,773 | **ARCHIVED** 2026-07-17. Recorded so a directory listing does not resell it. |

### The gradient, as a one-line reading of the tables above

Deliver a byte (**16,982★**) → send to a list (**24,473★**) → host a conversation generically
(**48,117★**) → host a *newsroom* conversation (**2,005★**) → encode consent lawfully (**156★**) →
carry consent across jurisdictions (**128★, not software**) → operate identity (**18★**).

**1,360× from one end of the plane to the other, and the variable is liability** — not layer, not
lineage, not distance from money. The control case is exact: hosting comments differs **24×** between
the generic and newsroom versions of the *same function*, because only one makes the operator answer
for what gets published.

### The licence finding: the first **star-count decoy** in this KB

`maizzle/maizzle` (**2,864★**) is what search returns for the Maizzle framework. No licence file (six
paths, all 404), no `license` field in `package.json`, README claims MIT while linking to a `./LICENSE`
that **404s**. npm points elsewhere: **`maizzle/framework` (1,624★) has a real MIT LICENSE.** The
more-starred repo is the *starter template*. **Rule for all twelve industries: when a name resolves to
two repos, check which one the package registry points at before quoting stars or licence.**

### Deliverability became the binding constraint, and `parsedmarc` is the only open answer

Gmail retired High/Medium/Low domain and IP reputation in Postmaster Tools v2 for a compliance
checklist plus a deliverability verdict; Apple Mail Privacy Protection already broke the open rate
(vendor estimates of **4–8pp** inflation, unverified); and Gmail's Gemini summaries appear to
**auto-open** messages — inflating opens while clicks fall, because the reader is satisfied by the
summary. **When the open rate dies, DMARC reports plus clicks are the evidence that remains**, and
[domainaware/parsedmarc](https://github.com/domainaware/parsedmarc) (Apache-2.0, 1,321★) is the way
to own it rather than rent it.

### Regulatory clock on the consent rows — already past, not upcoming

**TCF v2.3 mandatory for TC strings generated on/after 1 March 2026** (Google publisher guidance;
iubenda says 28 Feb 2026). **TCF v2.4 specs + updated GVL published 23 July 2026**, website deadline
**23 October 2026**, later for apps and CTV. **And no open-source CMP is IAB-registered** — `c15t`
and `iabtcf-es` give the string and the UI, never the standing. Say so before a client assumes the
open stack discharges the duty.

## 2026-11-26 — pass 23: the still-image, photo-desk & print-production plane (**the describe layer is permissive and dying at the top: the three most-starred models are dormant and the canonical captioning model is archived**)

**Probe before search, as in passes 11–22.** 65 vocabulary terms against the eight live files.
`libvips`, `ImageMagick`, `imgproxy`, `thumbor`, `darktable`, `RawTherapee`, `fontTools`,
`Ghostscript`, `CMYK`, `ICC profile`, `color management`, `stock photo`, `photo editorial`,
`photojournalism`, `prepress`, `Scribus`, `PhotoPrism`, `image captioning`, `upscal*` — **0 hits
out of 19.** The decisive measurement: `print` matched 124 lines, and **121 were
`fingerprint`/`Chromaprint`** — bare `print` occurred three times in the whole KB. Candidate planes
`playout`/`EPG`, comics, data journalism and GLAM/IIIF came back already covered by passes 4, 8, 18
and 20; this one was empty.

### New this pass — AI arriving inside the classic darkroom

| Project | Repo | License | Stars | Last push | What moved |
|---|---|---|---|---|---|
| darktable | [darktable-org/darktable](https://github.com/darktable-org/darktable) | GPL-3.0 | 13,508 | 2026-11-26 | **5.6 (June 2026) shipped an opt-in AI subsystem**: `neural restore` (RAW denoise, denoise, upscale), an AI object-mask tool, HEIF export. Models are **NIND UNet** (denoise) and **RawNIND UtNet2** (RAW denoise); RAW denoise writes DNG, denoise/upscale write TIFF. **Disabled by default, behind a build flag.** 5.6.1 (August 2026) made RAW denoise *refuse* legacy Fujifilm Super CCD sensors the models were never trained on. |
| Upscayl | [upscayl/upscayl](https://github.com/upscayl/upscayl) | AGPL-3.0 | 53,276 | 2026-11-26 | The most-starred AI image tool in this plane, pushed the day of the pass. **AGPL** — fine as a desktop app for a client's own staff, disclosable the moment it becomes a service. |
| c2pa-rs | [contentauth/c2pa-rs](https://github.com/contentauth/c2pa-rs) | MIT OR Apache-2.0 | 455 | 2026-11-26 | Reference C2PA implementation, pushed the day of the pass. Dual-licensed (`LICENSE-MIT` read; API says `NOASSERTION`). |
| c2patool | [contentauth/c2patool](https://github.com/contentauth/c2patool) | Apache-2.0 OR MIT | 174 | 2026-11-26 | CLI to sign/verify Content Credentials — the drop-in for an ingest pipeline. |

**darktable's model-provenance policy is the governance detail worth copying.** The team ships the
models separately, with documented licences, and states that models of unclear provenance are
excluded. That is a defensible answer to "what is in your AI feature", and it came from a
GPL volunteer project rather than a vendor.

### Dormant or archived at the top of the describe layer — measured 2026-11-26

| Project | Repo | License | Stars | Last push | State |
|---|---|---|---|---|---|
| Real-ESRGAN | [xinntao/Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN) | BSD-3-Clause | 37,679 | **2024-08-06** | **Dormant 2y 3m.** Still the upscaling weights the ecosystem ships. |
| LLaVA | [haotian-liu/LLaVA](https://github.com/haotian-liu/LLaVA) | Apache-2.0 | 25,093 | **2024-08-12** | **Dormant 2y 3m.** Still the VLM most captioning guides target. |
| BLIP | [salesforce/BLIP](https://github.com/salesforce/BLIP) | BSD-3-Clause | 5,699 | 2026-03-03 | **ARCHIVED by its owner** — read-only. The canonical open captioning model for alt text. |
| CLIP | [openai/CLIP](https://github.com/openai/CLIP) | MIT | 34,666 | 2026-03-25 | Reference-only, 8 months idle. Use `open_clip` instead. |
| imagededup | [idealo/imagededup](https://github.com/idealo/imagededup) | Apache-2.0 | 5,688 | 2025-08-15 | ~15 months idle; stable algorithms, low risk. |
| imaginary | [h2non/imaginary](https://github.com/h2non/imaginary) | MIT | 6,091 | 2025-11-08 | ~12 months idle. |
| mozjpeg | [mozilla/mozjpeg](https://github.com/mozilla/mozjpeg) | IJG + BSD-3-Clause | 5,748 | 2025-06-23 | ~17 months idle, still best-in-class baseline JPEG. |

**The one live base in the describe layer:** `mlfoundations/open_clip` (MIT, 14,292★, pushed
2026-11-21). Licence confirmed by reading the file — the API reports `NOASSERTION`.

### Moving this week (pushed within 5 days of the pass)

| Repo | License | Stars | Last push |
|---|---|---|---|
| [huggingface/transformers](https://github.com/huggingface/transformers) | Apache-2.0 | 169,360 | 2026-11-26 |
| [immich-app/immich](https://github.com/immich-app/immich) | AGPL-3.0 | 120,170 | 2026-11-26 |
| [mozilla/pdf.js](https://github.com/mozilla/pdf.js) | Apache-2.0 | 54,196 | 2026-11-26 |
| [facebookresearch/faiss](https://github.com/facebookresearch/faiss) | MIT | 41,936 | 2026-11-25 |
| [photoprism/photoprism](https://github.com/photoprism/photoprism) | AGPL-3.0 | 40,481 | 2026-11-26 |
| [qdrant/qdrant](https://github.com/qdrant/qdrant) | Apache-2.0 | 35,725 | 2026-11-26 |
| [lovell/sharp](https://github.com/lovell/sharp) | Apache-2.0 | 32,872 | 2026-11-26 |
| [danielgatis/rembg](https://github.com/danielgatis/rembg) | MIT | 25,686 | 2026-11-24 |
| [google/fonts](https://github.com/google/fonts) | per-family OFL/Apache/UFL | 20,807 | 2026-11-26 |
| [ImageMagick/ImageMagick](https://github.com/ImageMagick/ImageMagick) | ImageMagick License | 17,946 | 2026-11-26 |
| [mm2/Little-CMS](https://github.com/mm2/Little-CMS) | MIT | 764 | 2026-11-26 |
| [scribusproject/scribus](https://github.com/scribusproject/scribus) | GPL-2.0-or-later | 659 | 2026-11-26 |

### The agent layer over photo *operations* — measured, and it is contaminated noise

| Query | Total repos | Top result | Stars | Verdict |
|---|---|---|---|---|
| `caption agent newsroom` | **0** | — | — | Literal zero. |
| `photo desk agent` | 11 | `danderfer/Comp_Sci_Sem_2` | 228 | Coursework repo. Contamination. |
| `image licensing agent` | 31 | `danderfer/Comp_Sci_Sem_2` | 228 | **Same coursework repo, second query.** |
| `alt text agent` | 47 | `zszszszsz/.config` | 373 | Dotfiles repo. Contamination. |
| `photo archive agent` | 16 | `CNTRUN/Termux-command` | 120 | Contamination by name. **Indexed but not git-servable** — not verifiable as a live repo. |
| `prepress automation` | 26 | `sams-joseph/prepress-automation` | **1** | Genuinely on-topic, one star. |
| `image metadata agent` | 93 | `wiltodelta/remove-ai-watermarks` | 6,530 | On-topic, pointing **the wrong way** — it strips provenance. |

**Contamination warning.** `danderfer/Comp_Sci_Sem_2` (228★) tops two unrelated queries in this
plane. Second repo in this KB to contaminate two planes, after `jettbrains/-L-` (passes 4 and 22).
Recorded so no later pass "discovers" it.

### Verification-channel disclosure for this pass

The GitHub REST `/repos/*` endpoint returned **HTTP 403** throughout (session-scoped to this
account's own repositories), so all stars and last-push dates come from
`gh api -X GET search/repositories`. **Six of 65 repos return HTTP 422 from the search index while
serving git normally** — `Beep6581/RawTherapee`, `artpixls/ART`, `googlefonts/fontbakery`,
`JohannesBuchner/imagehash`, `ente-io/ente`, `UKPLab/sentence-transformers`. Their star counts are
written `n/a` in this pass's tables, **not estimated**. Existence was confirmed by `git ls-remote`
for all 65.

## 2026-11-26 — pass 22: podcast & spoken-audio infrastructure (**44 slugs probed, 42 resolve on GitHub, 2 live off-GitHub; the substrate is the most permissive in this KB and the money layer is empty**)

Infrastructure and platform repos for the podcast plane. Agents are in `agents/trending.md` pass 22.

### Moving this week (measured 2026-11-26, pushed within 10 days)

| Repo | License | Stars | Last push | What moved |
|---|---|---|---|---|
| [skymethod/op3](https://github.com/skymethod/op3) | MIT | 144 | **2026-11-26** | Open Podcast Prefix Project — pushed the day of this pass. The only open measurement-of-record implementation. |
| [Podcastindex-org/web-ui](https://github.com/Podcastindex-org/web-ui) | MIT | 73 | **2026-11-26** | Public index front end. |
| [Podcastindex-org/helipad](https://github.com/Podcastindex-org/helipad) | MIT | 37 | **2026-11-26** | Boostagram receiver; the v4v payment rail. |
| [advplyr/audiobookshelf](https://github.com/advplyr/audiobookshelf) | GPL-3.0 | 15,123 | 2026-11-19 | The plane's largest project; self-hosted audiobook + podcast server. |
| [AntennaPod/AntennaPod](https://github.com/AntennaPod/AntennaPod) | GPL-3.0 | 8,357 | 2026-11-25 | Reference open Android client, still shipping. |
| [microfeed/microfeed](https://github.com/microfeed/microfeed) | AGPL-3.0 | 4,143 | 2026-11-24 | Cloudflare-hosted agentic CMS for feeds. |
| [martinrotter/rssguard](https://github.com/martinrotter/rssguard) | GPL-3.0 | 2,858 | 2026-11-24 | Desktop feed reader + podcast player. |
| [gpodder/gpodder](https://github.com/gpodder/gpodder) | GPL-3.0 | 1,457 | 2026-11-24 | The original desktop podcast client, 20 years on and still pushed. |
| [SkyD666/PodAura](https://github.com/SkyD666/PodAura) | GPL-3.0 | 1,278 | 2026-11-23 | Material You Android podcast app. |
| [madeofpendletonwool/PinePods](https://github.com/madeofpendletonwool/PinePods) | GPL-3.0 | 1,089 | 2026-11-25 | Rust self-hosted podcast management system. |
| [ubuntu-flutter-community/musicpod](https://github.com/ubuntu-flutter-community/musicpod) | GPL-3.0 | 673 | 2026-11-23 | Flutter music/radio/podcast player. |
| [podverse/podverse-rn](https://github.com/podverse/podverse-rn) | AGPL-3.0 | 287 | 2026-11-16 | The most complete open Podcasting 2.0 client stack (`-web` 100★, `-api` 34★, all AGPL). |
| [podlove/podlove-publisher](https://github.com/podlove/podlove-publisher) | MIT | 310 | 2026-11-17 | **The only MIT publishing platform in the plane.** |
| [opawg/user-agents-v2](https://github.com/opawg/user-agents-v2) | MIT | 69 | 2026-11-24 | Current user-agent corpus for server-side audience measurement. |
| [opawg/podcast-rss-useragents](https://github.com/opawg/podcast-rss-useragents) | MIT | 65 | 2026-11-17 | Feed-fetching agents, so crawlers are not counted as listeners. |
| [Podcastindex-org/podping.cloud](https://github.com/Podcastindex-org/podping.cloud) | MIT | 50 | 2026-11-25 | Publish-notification bus. |
| [vpetersson/podcast-rss-generator](https://github.com/vpetersson/podcast-rss-generator) | MIT | 54 | 2026-11-23 | Compliant feed generator for self-hosted media. |
| [opawg/podcast-prefixes](https://github.com/opawg/podcast-prefixes) | MIT | 14 | 2026-11-10 | Prefix providers + their privacy policies. |

### Stable, not trending — and load-bearing

| Repo | License | Stars | Last push | Note |
|---|---|---|---|---|
| [Podcastindex-org/podcast-namespace](https://github.com/Podcastindex-org/podcast-namespace) | **CC0-1.0** | 496 | 2026-10-10 | The Podcasting 2.0 namespace. Public domain. Adopted by Apple (`transcript` Mar 2024, now `chapters` + Chapters JSON) and Spotify (`transcript`). |
| [Podcastindex-org/docs-api](https://github.com/Podcastindex-org/docs-api) | MIT | 78 | 2026-07-08 | API docs for the open catalogue. |
| [opawg/user-agents](https://github.com/opawg/user-agents) | MIT | 123 | 2025-01-07 | Superseded by v2; kept for historical mappings. |
| [opawg/podcast-hosts](https://github.com/opawg/podcast-hosts) | MIT | 52 | 2026-09-22 | Host identification from audio URL patterns. |
| [akhilrex/podgrab](https://github.com/akhilrex/podgrab) | GPL-3.0 | 1,990 | 2026-07-16 | Self-hosted archiver/downloader. |
| [amugofjava/anytime_podcast_player](https://github.com/amugofjava/anytime_podcast_player) | **BSD-3-Clause** | 627 | 2026-04-22 | **The only living permissive listener-facing app in the plane.** Flutter/Dart. |
| [getAlby/nostr-wallet-connect](https://github.com/getAlby/nostr-wallet-connect) | Apache-2.0 | 115 | — | Wallet-connect rail used by the v4v boost ecosystem. |
| [valcanobacon/BoostBots](https://github.com/valcanobacon/BoostBots) | BSD-3-Clause | 15 | — | Boostagram bots. |
| [v4v-info/v4v-info.github.io](https://github.com/v4v-info/v4v-info.github.io) | MIT | 32 | — | value4value reference/documentation site. |

### Dead or legally unavailable — recorded so a later pass does not "discover" them

| Repo | License | Stars | Last push | Why it is excluded |
|---|---|---|---|---|
| [GetStream/Winds](https://github.com/GetStream/Winds) | BSD-3-Clause | 9,078 | **2021-10-11** | The only large permissive podcast app, **dead five years**. The exception that proves layer 3's rule. |
| [Yetangitu/Spodcast](https://github.com/Yetangitu/Spodcast) | GPL-3.0 | 373 | 2024-06-04 | Spotify→RSS proxy. Dormant, and its premise is ToS-hostile for client work. |
| [leandromoreira/scte-35-scte-104-scte-67](https://github.com/leandromoreira/scte-35-scte-104-scte-67) | BSD-3-Clause | 35 | **2021-04-13** | The top hit for `dynamic ad insertion` in all of GitHub — and it is **documentation** about broadcast markers, not an implementation. The whole DAI result set is this thin. |
| [panyanyany/Twocast](https://github.com/panyanyany/Twocast) | **NONE** | 1,292 | 2025-07-01 | Most-starred AI podcast generator; **no licence file** → all rights reserved. |
| [Mtillmann/chaptertool](https://github.com/Mtillmann/chaptertool) | **NONE** | 45 | 2026-01-24 | Active and genuinely useful; unlicensed, so not vendorable. |
| [cclawton/podcastindex-mcp-server](https://github.com/cclawton/podcastindex-mcp-server) | **NONE** | 3 | — | The entire MCP layer over the open podcast index: 3★, unlicensed. |

### Off-GitHub, and therefore not measured here

- **Castopod** — AGPL-3.0, canonical home `code.castopod.org`; project docs give 1.15.0 (Feb 2026)
  as current, with ActivityPub federation and built-in analytics. The dead `Castopod/castopod`
  GitHub slug was already recorded by pass 21 in this file; `ls-remote` confirms it still does not
  resolve. **No star or push figure is asserted.**
- **Funkwhale** — AGPL-3.0, `dev.funkwhale.audio`. `ls-remote` on the GitHub slug fails.
- Both hosts are **blocked by this session's egress proxy** (403 `connect_rejected`), so neither
  could be read directly. Recorded as an informed gap, not as coverage.

### Verification note

44 slugs probed with `git ls-remote`: **42 resolve, 2 absent** (the two off-GitHub platforms above).
All stars, licences and push dates measured 2026-11-26 via `search/repositories`. `nostr-wallet-connect`,
`BoostBots` and `v4v-info` were measured for stars and licence but their push dates were not captured
in this pass — the cell reads `—` rather than carrying a guess.

## 2026-11-26 — pass 21: spatial, immersive & volumetric infrastructure (**71 slugs probed, 69 resolve, 2 absent; 17 licence files read, 5 licence categories corrected**)

**Probe results.** 71 candidate slugs; **69 exist** by `git ls-remote`, **2 do not**
(`tracel-ai/brush` — the correct slug is `ArthurBrussee/brush`; `opensimulator/opensim` — hosted
outside GitHub). GitHub reported `NOASSERTION` or `NONE` for **nineteen** of them; **seventeen
licence files were read directly** and **four** were control-tested as having no licence file at all.
Reading changed the answer in every case where a file existed.

**The infrastructure layer is permissive and very large — it is the capture layer that is gated.**

| Repo | Stars | Licence (verified) | HEAD | Layer |
|---|---|---|---|---|
| https://github.com/godotengine/godot | 120,865★ | MIT | 2026-11-25 | Engine |
| https://github.com/mrdoob/three.js | 119,448★ | MIT | 2026-11-26 | Web runtime |
| https://github.com/pmndrs/react-three-fiber | 33,957★ | MIT | 2026-10-21 | Web runtime |
| https://github.com/BabylonJS/Babylon.js | 26,457★ | Apache-2.0 | 2026-11-26 | Engine + WebXR |
| https://github.com/playcanvas/engine | 17,382★ | MIT | 2026-11-26 | Engine |
| https://github.com/aframevr/aframe | 17,721★ | MIT | 2026-07-13 | Declarative WebXR |
| https://github.com/CesiumGS/cesium | 15,990★ | Apache-2.0 | 2026-11-26 | 3D Tiles streaming |
| https://github.com/colmap/colmap | 13,302★ | new BSD (read) | 2026-11-26 | SfM substrate |
| https://github.com/alicevision/Meshroom | 13,116★ | MPL-2.0 (`COPYING.md`) | 2026-11-26 | Photogrammetry |
| https://github.com/o3de/o3de | 9,929★ | **Apache-2.0 OR MIT, elected** | 2026-11-26 | Engine |
| https://github.com/zeux/meshoptimizer | 8,948★ | MIT | 2026-11-25 | Compression |
| https://github.com/google/draco | 7,569★ | Apache-2.0 | 2026-11-16 | Compression |
| https://github.com/PixarAnimationStudios/OpenUSD | 7,676★ | **Tomorrow OSS Technology License 1.0** | 2026-11-25 | Scene interchange |
| https://github.com/openMVG/openMVG | 6,609★ | MPL-2.0 | 2026-11-07 | Multi-view geometry |
| https://github.com/KhronosGroup/OpenXR-SDK | 1,175★ | Apache-2.0 | 2026-10-16 | Device API |
| https://github.com/MPEGGroup/mpeg-pcc-tmc2 | 177★ | **BSD, no patent grant** | 2026-11-17 | V-PCC codec |

**Five licence corrections that an SPDX field would have got wrong.**

1. **`PixarAnimationStudios/OpenUSD` is not Apache-2.0.** Its `LICENSE.txt` (49,827 B) is the
   **Tomorrow Open Source Technology License 1.0**, which differs from Apache-2.0 in §6
   ("Trademarks"). Permissive in substance, but earlier passes citing it as Apache need this
   correction in any client-facing licence table.
2. **`o3de/o3de` is a genuine dual grant** — `LICENSE.txt` states Apache-2.0 by default with the
   licensee free to elect MIT, and requires contributions under both. The cleanest terms in the plane.
3. **`colmap/colmap` is new BSD**, and its own licence text warns that *"building COLMAP with these
   dependencies may affect the resulting COLMAP license"* — the linked-library problem cycle 8 found
   in Chromaprint, here declared by the project itself.
4. **`MPEGGroup/mpeg-pcc-tmc2`** is BSD **that explicitly grants no patent rights**. Open code,
   closed codec, 177★ installed base.
5. **`zju3dv/EasyVolcap` and `zju3dv/EasyMocap`** are **PRL v1.0** — permissive with a pre-use
   project registration gate, not non-commercial. See `agents/trending.md` for the full terms.

**Four spec repositories with no licence grant at all — control-tested.** `KhronosGroup/glTF`
(7,907★), `CesiumGS/3d-tiles` (2,653★), `KhronosGroup/glTF-Sample-Assets` (1,180★) and
`needle-tools/needle-engine-support` (613★) return 404 for **thirteen licence filenames across both
`main` and `master`**, while `README.md` returns 200 on both branches and a known-good positive
control passes. So the files are genuinely absent, not misnamed — the false negative cycle 8 warned
about is ruled out. This is the **second industry** in which a standards repository whose entire
purpose is interoperability ships without a licence (pass 5: `rslstandard/rsl`), which makes it a
pattern rather than an anecdote. **Take the terms from the published specification, never from the
spec repo.**

**The dormancy sits exactly on the temporal axis.** `hustvl/4DGaussians` (Apache-2.0, 4,047★) last
pushed **2024-10-27**; `nerfstudio-project/nerfstudio` (Apache-2.0, 12,264★) last pushed
**2025-07-29** while its own `gsplat` component stays current — the framework is slowing and the
component is not. The only permissive, active 4D production pipeline is
`ASU-NEM-Labs/open4dgs-core` at **161★**.

**Unverifiable from this session, recorded as such.** `gitlab.freedesktop.org` is refused by the
egress proxy (HTTP 403), so **Monado** — the leading open OpenXR runtime — is **not investigated**
rather than absent. `videolan/x265`, the open MV-HEVC multiview path, has a GitHub mirror **last
pushed 2023-09-11**; canonical development is at VideoLAN and must be verified there.

---

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

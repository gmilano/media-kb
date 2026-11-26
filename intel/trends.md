---
industry: media
region: Global
updated: 2026-11-26
---

# 📡 Trends — Media & Entertainment

> What changed, with the evidence attached. Previous version of this file listed five 0-star
> non-media repos as "most active this week"; that section is replaced.

## 1. The models have stalled; the orchestration layer is where the movement is

Measured, not asserted. Last-push dates as of 2026-11-21:

| Layer | Repo | Last push | Gap |
|---|---|---|---|
| Model | hpcaitech/Open-Sora | 2026-04-09 | ~7 months |
| Model | Wan-Video/Wan2.1 | 2026-03-05 | ~8 months |
| Model | facebookresearch/audiocraft | 2026-03-03 | ~9 months |
| Model | zai-org/CogVideo | 2025-11-04 | ~12 months |
| Model | hexgrad/kokoro | 2025-08-06 | ~15 months |
| Agent | JuneYaooo/rea-video | 2026-11-21 | same day |
| Agent | harry0703/MoneyPrinterTurbo | 2026-11-20 | 1 day |
| Agent | krillinai/OpenCreator | 2026-11-20 | 1 day |

Open-weight video generation has plateaued as a race; **composing** those weights into pipelines is
where every active repo now sits. Practical consequence: pick a model once, pin it, and invest the
engineering in the pipeline around it.

## 2. Provenance has become law, and the open tooling is ready

**Six** jurisdictions now mandate some form of synthetic-media labeling: EU (AI Act Art. 50), South
Korea (AI Basic Act, 2026-01-22), **Taiwan (AI Basic Act, in force 2026-01-14 — new to this KB on
2026-11-22)**, Vietnam (2026-03-01), India (IT Rules, 2026-02-20), and Mexico for performer likeness
(effective 2026-05-15). C2PA is the only interoperable answer, the spec is royalty-free, and
`contentauth/c2pa-rs` is **dual MIT/Apache-2.0** — re-confirmed 2026-11-22 by reading both license
files — with a push on 2026-11-21.

**Retraction, 2026-11-22.** The previous version of this trend stated that no Apache-licensed open
watermarking library existed, that SynthID was Google-internal, and that this was "the clearest
open-source gap in media today." **All three were wrong**, and the error mattered because it told a
reader the compliance stack could not be completed. The correction:

- [`facebookresearch/videoseal`](https://github.com/facebookresearch/videoseal) — **MIT**, 828★,
  pushed 2026-11-10. Video watermarking, models and training code included.
- [`facebookresearch/audioseal`](https://github.com/facebookresearch/audioseal) — **MIT**, 804★,
  pushed 2026-11-03. Audio, with sample-level localized detection.
- [`adobe/trustmark`](https://github.com/adobe/trustmark) — **MIT**, 189★, pushed 2026-11-11. Images.
- [`google-deepmind/synthid-text`](https://github.com/google-deepmind/synthid-text) — **Apache-2.0**,
  1,258★. SynthID for *text* is open; for image/video/audio it is not. The precise statement is
  "SynthID-Text is open, SynthID for AV is not."

The caveat that survives, and it is now sharper: C2PA credentials are opt-in and fragile — screenshots,
re-encoding and most upload paths strip them — and watermarks are **actively attacked**, which is
trend 8 below.



## 3. The typed layer for broadcast hardware already exists — what is missing is the agent bridge

**Revised 2026-11-22, and this is the most actionable correction in the file.** The previous version
said the scarcity was "typed access to media systems" and that "no open MOS-protocol implementation
exists at all, so newsroom playout integration remains unautomatable off-the-shelf." The second
claim is simply false, and it changes the first one's conclusion.

**Sofie** — commissioned by NRK as an open replacement for Vizrt Mosart, MIT, in daily news
production at NRK, the BBC and TV 2 Norway since 2018 — already provides both halves:

- [`sofie-mos-connection`](https://github.com/Sofie-Automation/sofie-mos-connection) (MIT, 29★/18f)
  speaks **MOS Protocol v2.8.4** to newsroom computer systems.
- [`sofie-timeline-state-resolver`](https://github.com/Sofie-Automation/sofie-timeline-state-resolver)
  (MIT, 25★/25f) **is** the typed device-abstraction layer: declare desired state on a timeline and
  it diffs and drives ATEM, CasparCG, Lawo, HyperDeck, Quantel, Kairos, OBS and vMix behind one
  interface — with the safety properties an agent needs, because the agent proposes state rather than
  issuing device commands.

So the restated scarcity is narrow, specific and buildable: **nothing exposes that resolver to an
agent.** Every media MCP server found is still embryonic and aimed at *file-level* editing, not at
broadcast devices — `KyaniteLabs/kinocut` 278★ (re-measured 2026-11-22; the most mature, 206 tools
with loudness/quality gates), `ayushozha/AdobePremiereProMCP` 149★, `misbahsy/video-audio-mcp` 91★
and stale since 2025-05-24, then a cliff to 0–5★ projects.

**The build is an MCP server in front of `sofie-timeline-state-resolver`** — days of work against an
MIT library, not a protocol reverse-engineering project, and it lands Globant in the gallery rather
than in post. `compose/patterns.md` Pattern 7.

**The methodological lesson, which generalizes to all twelve industries.** This gap was never a market
fact; it was a vocabulary artifact. Measured this pass: the query `mos protocol broadcast` returns
**total=1**, and that result is a dead 2★ project from 2018. Sofie is undiscoverable by capability
because its repos are named after the project, not after what they do. The previous healthcare pass
learned to *shorten* a zero-result query before concluding a field is empty; this pass adds the
complement — **also search the proper noun**: the project, the vendor, the standards body, the
national broadcaster. The institutional index ([`ebu/awesome-broadcasting`](https://github.com/ebu/awesome-broadcasting),
CC0, 1,803★) had Sofie listed the whole time.

## 4. Permissive at the pipeline, copyleft at the platform

A structural feature of M&E open source, and the reverse of most industries: the standards and
pipeline layer is permissive (ASWF Apache/BSD, Netflix BSD+Patent, hls.js and shaka-player Apache),
while the turnkey platforms are AGPL/GPL (MediaCMS, PeerTube, OvenMediaEngine, Jellyfin) or
source-available (Directus's Monospace SCL, Strapi's `ee/`). Architecture has to follow: own the
pipeline, rent the platform at arm's length.

## 5. License terms are now a geographic constraint, not just a legal one

New this pass: **HunyuanVideo's license excludes the EU, UK and South Korea outright.** A model
choice is now a market choice. Combined with the territorial labeling rules, "which model may we use
in this country" is a real architecture question — and the answer differs per region for the first time.

## 6. Authenticity is becoming the scarce asset

EY's 2026 read: AI accelerates production, but authenticity becomes the industry's rarest asset, with
experiential entertainment moving from side business to strategic priority. Deloitte's counterpart
warning is a content glut — AI-generated content burying higher-quality work, and so few shared
cultural moments that personalization itself erodes the product. Both point the same way: tooling that
*proves* provenance and human authorship gains commercial value, which is trend 2 seen from the
demand side rather than the regulatory one.

## 7. Spending is internal, and that is where to sell

Adobe's research finds AI investment concentrated in internal workflows while consumer-facing agentic
experiences are underinvested. Deloitte frames gen AI as core infrastructure across the pipeline from
storyboarding to post. Localization, archive retrieval and post production are the near-term buyers;
consumer-facing agents are not yet funded.

## 8. Watermark removal is a 10× larger open-source movement than watermarking

**New and measured this pass, and it is the number that should shape every provenance pitch.**
Having retracted the "no watermarking exists" claim in trend 2, the honest follow-up is that the
embedders are the *smaller half* of this field:

| Side | Projects measured | Total stars | Most-starred |
|---|---|---|---|
| Embedders (watermark *in*) | 5 | **4,138** | `ShieldMnt/invisible-watermark` 1,993★ (dormant since 2023) |
| Removers (watermark *out*) | 6 | **42,896** | `guillaumemeyer/watermarks-remover` 28,124★/3,162f, MIT, pushed 2026-11-16 |

A **10.4× asymmetry**, and the removers are the better-maintained side — three of the six were pushed
within three weeks of measurement, while the most-deployed embedder has not been touched since 2023.
One project, `froggeric/gemini-watermark-and-synthid-remover` (MIT), names a specific scheme in its
title. Full slugs and figures in `repos/trending.md` under 2026-11-22.

**Why this is commercially useful rather than merely discouraging.** It kills the pitch "we watermark
your content, therefore it is protected" — which a client's own engineer can disprove in an afternoon
with a 28k-star MIT repo. What it supports instead is a stronger and more expensive product: a
**verification service at ingest**, dual-marked assets (C2PA manifest + VideoSeal/AudioSeal payload),
and explicit language that provenance is a probabilistic chain of custody. The regulations in trend 2
require a *good-faith marking effort*, not an unbreakable one — so the asymmetry is a design
constraint, not a compliance blocker. Say it before the client's engineer does.

## 9. Public broadcasters are writing AI codes, and each one is a procurement trigger

New this pass, EMEA-specific and unusually concrete. Rather than waiting for the AI Act, European
public broadcasters have adopted their own binding internal AI policies through 2026: **ARD, ZDF,
Deutschlandradio and Deutsche Welle** adopted a joint AI code in **January 2026**; Switzerland's
**SRG SSR** rules took effect **2026-06-01**; **RAI's** board approved a policy in **February 2026**;
**Radio France** added a rule prohibiting synthetic voices that could replace its staff's vocal
identity. Published rules in southern Europe are concentrated in **Spain**, and most state-controlled
broadcasters have **no published policy** at all (State Media Monitor, October 2026).

**Read it as a sales map, because that is what it is.** An organization that has just published an AI
code has (a) named an internal owner, (b) created written obligations it cannot yet technically
verify, and (c) no tooling to enforce them. That is the shortest path from policy to purchase order
in this industry — and Radio France's synthetic-voice rule is a *voice-provenance* requirement
written in plain language, which Pattern 8 satisfies directly.

## 10. One MIT platform breaks this KB's "copyleft at the platform" rule

Trend 4 below holds as a generalization — permissive at the pipeline, copyleft at the platform — with
one exception discovered 2026-11-22 that is large enough to change an architecture. **Sofie** (MIT) is
a mature *platform* at the layer where broadcasters feel the most vendor pain: live studio and news
automation, where the incumbent is Vizrt Mosart. Its existence means a news or live engagement no
longer has to be framed as "agents bolted onto a copyleft platform's REST API." Globant can propose
owning and extending the automation platform itself, with no copyleft obligation, in a stack two
national broadcasters co-maintain. Nothing comparable exists for MAM, CMS or VOD — so this is one
exception, not a repeal of trend 4.

## 11. The monetization plane is open at both ends and dormant in the middle

Researched for the first time on 2026-11-22 (second pass), and the shape is unusually clean:

| Layer | Best permissive option | Last push | State |
|---|---|---|---|
| Auction | [prebid/Prebid.js](https://github.com/prebid/Prebid.js), [prebid-server](https://github.com/prebid/prebid-server) (Apache-2.0) | 2026-11-22 | Canonical, active, pushed today |
| **Ad signalling (SCTE-35)** | [Comcast/scte35-js](https://github.com/Comcast/scte35-js) (Apache-2.0, 51★) | 2026-05-21 | **Thin** — and the Python alternative, [futzu/threefive](https://github.com/futzu/threefive), is dormant since 2024-11-27 |
| Channel assembly | [Eyevinn/channel-engine](https://github.com/Eyevinn/channel-engine) (Apache-2.0) | 2026-11-06 | Active, small, EMEA-origin |
| Measurement | [apache/druid](https://github.com/apache/druid), [pinot](https://github.com/apache/pinot), [snowplow](https://github.com/snowplow/snowplow) (Apache-2.0) | 2026-11-21/22 | ASF-maintained, industrial |
| **Decisioning / agents** | — | — | **Nothing. Measured, see `agents/top.md`.** |

The ends of this chain are in excellent health. The **hinge** — the cue-parsing layer that connects a
broadcaster's playout to an ad auction — is 51 stars of maintained TypeScript and a dormant
two-year-old Python library whose sibling (`x9k3`) has no LICENSE file at all. The layer *above* the
whole chain, decisioning, does not exist in open source in any form this KB could verify.

**Why this is a trend and not a list:** it inverts the pattern everywhere else in this KB. In
generation, the models are the fast-moving part and integration is the drudgery. Here the
infrastructure is mature and *someone else maintains it*, while the two pieces that decide whether a
deal is differentiated — the cue bridge and the decisioning agent — are the empty ones. Both are
small. Neither needs a GPU.

## 12. Advertising overtook subscription as the growth engine — and that is the LATAM story

The KB has carried LATAM market totals for several cycles without the mechanism. The mechanism is ads:

- **LATAM media revenues reach ~$65B in 2026, and Omdia names advertising and bundling as the
  drivers** — advertising is now the *primary* driver of regional media growth, not subscriptions.
- **Brazil is the world's #3 FAST market by revenue (~$152M), behind only the US and UK.** A
  mid-sized market punching far above its weight in exactly the ad-supported format whose assembly
  layer (`channel-engine`) is Apache-2.0.
- **PwC: advertising passed $1T globally for the first time in 2025 and is projected at $1.4T by
  2030**, with streaming still the largest single revenue component (~$56.3B) in 2030.
- Netflix holds ~50% of LATAM streaming revenue, and ad-supported tiers at the major streamers are
  the growing part of the US market (Chambers, July 2026).

**Consequence for engagement framing:** in LATAM the ad stack is not a back-office add-on to a
content play — it is the growth line. This is the first trend in this file where the *commercial*
driver and the *permissive-licence* position point at the same build, and `compose/patterns.md`
Pattern 9 is that build.

## 13. Four of the "repos" in the ad plane are documents, not code

A licence-class trap worth recording, because it is specific to this plane. The three IAB Tech Lab
repos (`openrtb`, `AdCOM`, `GDPR-Transparency-and-Consent-Framework`) report `NONE` to GitHub's
licence detector and carry **Creative Commons Attribution 3.0** in their READMEs. CC BY is a
documentation licence: it grants the right to implement a specification, not working code.

Two adjacent measurement errors found the same way, both of which an API-only pass would have shipped:

- **`NOASSERTION` is not "no licence."** Both Video.js repos report it; the LICENSE files are
  Apache-2.0. Read the file.
- **A declared licence is not a licence.** `futzu/x9k3` has **no LICENSE file**; MIT appears only as a
  `setup.py` classifier. `Eyevinn/hls-vodtolive` has no LICENSE file either; MIT appears only in
  `package.json`. Both are usable, both need the licence confirmed in writing before a deliverable.

This is the same class of defect as this file's `threefive` note (an MIT grant carrying a stale
"Python Packaging Authority" copyright line) and the sister KBs' rule that **the MIT incipit is not a
licence identifier.** Four distinct failure modes, one remedy: open the file.

## 14. Europe's broadcasters are lobbying against the labelling duty this KB's flagship pattern assumes

The strongest claim in this file is trend 2 — provenance has become law, and Article 50 is the forcing
function. A counter-signal surfaced this pass and belongs on the record next to it, because it is the
regulated industry itself pushing back:

- **ACT**, the Association of Commercial Televisions in Europe, published AI principles for
  audiovisual media services (issue paper dated June 2026) arguing that restrictions on AI in
  audiovisual media must be **proportionate**, and **specifically opposing blanket measures such as
  mandatory labelling of generative-AI content under AI Act Article 50.** Their argument is that
  broadcasters already carry editorial responsibility under EMFA and the AVMS Directive, so a
  general-purpose labelling duty duplicates an existing accountability regime.
- **DIGITALEUROPE** is arguing the adjacent line: technology-neutral horizontal rules rather than
  extending sector-specific AVMSD obligations.
- Counterweight: EU law does **not** extend freedom-of-expression protection to content produced
  solely by AI (Taylor Wessing), and Cineuropa records AI Act transparency rules beginning
  enforcement in July 2026, with European film associations pressing for vigilance.

**Dates are genuinely contested and should not be quoted as settled.** The AI Act's main application
date is 2 August 2026 with some provisions live since 2 August 2025, while Reed Smith's timeline puts
AI Omnibus amendments at 27 July 2026. Sources disagree; check the final text before putting a date
in a client deck.

**What this does and does not change.** It does not weaken Pattern 1 or Pattern 8 — a broadcaster
that wins a proportionality argument still needs internal provenance to *prove* editorial
responsibility, which is the same C2PA build with a different buyer and a different justification. It
does change the pitch: in EMEA, lead with editorial accountability under EMFA, not with Article 50
compliance, because the broadcaster you are selling to may be actively lobbying against the clause you
are citing.

## 15. Accessibility is the only plane in media with a statutory deadline — and the third proof of this KB's structural rule

Added 2026-11-22 (pass 3). Every other plane this KB maps is sold on ambition: better content, cheaper
localization, new revenue. Accessibility is sold on a **date set by a regulator**. The EAA has applied
since 2025-06-28; the FCC's caption-display-settings rule hit compliance on 2026-08-17; Australia's
subscription-TV targets rise 5 points every financial year by legislation.

And the plane has the **same shape this KB has now found three times**:

| Plane | The edges (active) | The middle (dead) |
|---|---|---|
| Provenance (pass 1) | `c2pa-rs`, watermarking | verification at ingest, unbuilt |
| Monetization (pass 2) | Prebid, measurement | SCTE-35 tooling, dormant |
| Accessibility (pass 3) | `ttconv`, `imscJS`, `dash.js` — all pushed within 48h | `imscHRM` 920 days, `ebu-tt-live-toolkit` ~5 years |

**The rule, stated generally: open source reliably builds the pipeline and reliably abandons the
proof.** Byte-moving code attracts contributors; conformance validators do not. Wherever a regulator
asks for *evidence* rather than *output*, there is a maintained gap — and evidence-on-demand is
exactly what a services firm is paid for. This is now the most reusable finding in the media KB and
it should be tested against the next plane rather than assumed.

## 16. The FCC has turned against automated captions — ASR alone became a liability in October 2026

The FCC's 2026 CVAA report (released **2026-10-07**) explicitly flagged **inaccurate automated
captions**, inconsistent caption controls on video-conferencing platforms, and accessibility barriers
in emerging AI-driven communication tools. The FCC sets **no accuracy percentage** — it weighs errors
in context and treats live as harder than prerecorded.

This inverts the obvious pitch. "We will caption your library with AI" is now a regulatory *risk*
transfer onto the client in the US. The defensible offer is the workflow the regulator's complaint
implies: **AI draft → human review → timing and conformance check**, with the conformance step
citing `w3c/imsc-tests` rather than in-house samples. That is more billable than pure automation, not
less — and it is the rare case where the compliant architecture is also the more profitable one.

⚠️ Do not repeat the widely circulated claim that the CVAA requires **99% accuracy for AI live
captions**. It could not be confirmed against any primary source and contradicts the FCC's own
stated approach.

## 17. Audio description is the largest unmet mandate in media — a 56-star ceiling under a hard quota

The FCC requires **50 hours of AD per calendar quarter** in prime time or children's programming. The
EAA requires AD **wherever the picture carries information the sound does not**, and requires
platforms to pass through broadcasters' AD. México's new Ley Federal de Cine y el Audiovisual (April
2026) orders subtitulaje audiodescriptivo. Brazil's ANCINE regulates audiodescrição formats for
cinema. Argentina's Ley 26.522 art. 66 names it.

Against all of that, the **entire open audio-description layer is prototypes**: the largest is
`microsoft/ai-audio-descriptions` at **56 stars**, whose README calls it research and experimentation
and which ships no authentication. Next door in the caption layer, `SubtitleEdit` has **15,100**.
This pass also found **no market sizing for audio description at all**, while captioning has eight
competing vendor estimates.

A statutory mandate, in four regions, with no open tooling, no measured market and no incumbent of
any kind. **This is the clearest build opportunity in the media KB** — and the reason to treat AD as
a first-class track in architecture now rather than retrofitting it.

## 18. Regulators mandate the artefact and are silent on the method — which is standing permission to automate

Across every jurisdiction examined this pass — US (FCC/CVAA/ADA), EU (EAA), Australia (ACMA Part 9D),
México, Brasil, Argentina, Uruguay — the law specifies **what must exist**: captions, audio
description, sign language, player controls. **This pass found no regulation anywhere that governs
whether a human or a machine produces them.** The LATAM silence is the widest.

Two consequences, and they pull in opposite directions, which is why both must be said:

1. **Automation is permitted.** There is no legal barrier to AI-generated accessibility assets, and
   clients who believe otherwise are wrong — a useful thing to be able to tell them with sourcing.
2. **Automation carries the full liability.** Because the rule is about the artefact's *quality*, the
   producer owns every ASR error. Trend 16 is the FCC acting on exactly that.

The method is unregulated; the outcome is not. Sell the QC gate, not the model.

## 19. Accessibility obligations ratchet upward on a published schedule — the business case grows by law

Most compliance work is a threshold: meet it once, you are done. Accessibility is a **ratchet**:

- **Australia:** subscription-TV captioning targets are legislated to **rise 5 percentage points per
  year until they reach 100%**. Movie channels already sit at a 100% target in FY 2025/26.
- **EU:** the EAA's exemption for pre-2025 content expires for existing content and platforms in
  **June 2030**, so the remediation backlog has a four-year, dated runway.
- **US:** S.4322 (introduced April 2026) would add recommended deadlines for captioning *and* AD on
  online video.

For a client, the obligated volume increases every year on a schedule published in advance while the
budget does not. That is the strongest recurring-revenue argument in this KB, and unusually, it does
not depend on any claim about AI capability.

## 20. Sign language is mandated most where the tooling is least — and the one project everyone cites is not open source

LATAM law names sign language far more consistently than US or EU rules do: **LIBRAS** in Brazil
(ANCINE-regulated for cinema), **lengua de señas** in Argentina (Ley 26.522 art. 66) and Uruguay's
2026 recommendations. Able Player supports a synchronized sign-language video track, so the
*delivery* side is MIT-licensed and solved.

The *production* side is not. The most visible project, `sign/translate` — formerly `sign.mt`, now
**Rylo Translate** (Nagish Inc.) — reads as open source and is **not**: its LICENSE.md is dual-tier
source-available, free for individuals, non-profits and education, with **a separate commercial
licence required for for-profit organizations**. No open sign-language *generation* with meaningful
adoption was found at all.

So the region with the broadest sign-language duty has no permissive tooling to discharge it. Say
this in the proposal rather than discovering it in delivery — and note that an engagement can still
deliver the *carriage* (Able Player track, LIBRAS asset management) while the translation itself
stays human or licensed.

## 21. The fourth plane, the fourth identical result — the law is not a coincidence any more

Pass 4 measured broadcast QC, loudness compliance and archive preservation. The result is the same
shape this KB has now found in provenance, monetization and accessibility:

> **Permissive open source follows the file format, not the judgment.**

What makes the conformance plane the strongest evidence yet is that both halves are unusually crisp.
The format half: six permissive implementations of measurement and identification, several pushed the
same day as this pass (`MediaInfo` BSD-2-Clause 2075★, `MediaInfoLib` BSD-2-Clause 806★, `libebur128`
MIT 498★, `pyloudnorm` MIT 796★, `fido` Apache-2.0, `bagit-python` public domain). The judgment half:
`broadcast QC agent` → **0 results**, `file-based quality control video stars:>=20` → **0 results**.

Four planes, four confirmations, two of them literal zeros. This is now the most reliable predictive
rule in this KB: **to find where the margin is, find the regulated decision whose inputs are already
free.** It transfers to every industry in the rotation.

## 22. A license can live in an HTML file, or in nothing but a packaging classifier

This pass found three distinct channels for a license declaration, and GitHub's license field reads
only the first:

- a plain `LICENSE`/`COPYING` file — `fido` (Apache-2.0), `jhove` (LGPL-2.1+), `archivesspace` (ECL-2.0);
- **an HTML file** — `bavc/qctools` and `MediaArea/MediaConch` both ship `License.html`, and GitHub
  reports `NOASSERTION`/`NONE` for both;
- **packaging metadata with no license file at all** — `LibraryOfCongress/bagit-python` declares
  `License :: Public Domain` in a `pyproject.toml` classifier and ships no license file.

Six repos in this plane carry a GitHub license field that is **wrong, not merely vague**. The
operational upgrade to this KB's existing "`NOASSERTION` is a pointer, open the file" rule: when
plain filenames come back empty, **search the repo for `filename:LICENSE`** (that is what surfaced
`License.html`) and then read the packaging manifest. A plain-name probe alone would have
mis-licensed three of the rows now in `repos/foundations.md`.

The single most commercially useful thing it uncovered: **MediaConch is dual-licensed GPLv3+ *or*
MPLv2+.** Every secondary source records it as "GPL". Under the MPL-2.0 option it can be linked into
a closed client product. That fact was sitting in an HTML file.

## 23. The US just extended loudness guidance to streaming — and it is guidance, not law

**ATSC revised A/85, its loudness Recommended Practice, on 2026-07-08 (announced 2026-07-15), and
the revision extends guidance beyond traditional television to hybrid broadcast and streaming.**
That is the material change in this plane in 2026.

The nuance decides the architecture, and it is this KB's P9 rule applied again — **do not overstate
the mandate**:

- The **CALM Act** is the law. Its FCC rules took effect 2012-12-13 (47 CFR § 73.682(e)) and they
  cover **television commercials only** — not radio, not internet or streaming delivery. Enforcement
  is complaint-driven and has reportedly not gone beyond warnings.
- **A/85:2026-07 is a Recommended Practice**, not a regulation. It is the document the industry
  treats as the method, and the FCC's rules reference the ATSC practice — but a streaming service is
  not breaking the CALM Act by ignoring it.

So never tell a client "streaming loudness is now regulated in the US." Tell them: *the statutory
duty still stops at broadcast commercials; the industry's reference method was extended to streaming
in July 2026; and the only permissive implementations of the measurement are two small MIT repos.*
That sentence is defensible, and it is also the pitch.

## 24. LATAM is deploying archive AI faster than anyone is building archive-AI tooling

LATAM out-evidenced its own narrative again — the fourth industry in this rotation where that has
happened — and this time the evidence is **named production systems over archives**:

- **Listín Diario** (Dominican Republic) built a RAG platform over its **136-year archive**, cutting
  research that took full days down to minutes, with **25% of the archive searchable** so far.
- **La Silla Vacía** (Colombia) runs **SillaBot**, which lets readers query its archive, plus a
  fact-checking prototype.
- **ABC Color** (Paraguay) runs semantic archive search and automated news monitoring.
- The **IAPA/SIP**, with Google News Initiative backing, launched an **AI Video Lab 2026 for more
  than 40 outlets** (its earlier AI Product Lab has closed).
- The **EBU** and **Alianza Informativa Latinoamericana** signed a news-sharing agreement effective
  **2026-05-01** — not AI-specific, but it is the pipe regional content moves through.

The asymmetry is the finding: the region has **named, shipped, production archive-AI deployments and
no open archive-AI tooling of its own**. Every preservation platform in `verticals/solutions.md`
comes from the North American and European library world. For a studio that sells delivery rather
than product, deployments without tooling is the better market.

## 25. The canonical open conformance checker has been dormant for five years

`MediaArea/MediaConch` is the tool the preservation field cites for Matroska/FFV1/LPCM conformance.
Its repository has **not been pushed since 2021-09-29** and carries 35 stars. Meanwhile its siblings
from the same vendor are alive and were pushed the day of this pass — `MediaInfoLib` (2026-11-22),
`RAWcooked` (2026-11-22), `MediaInfo` (2026-11-19).

Two things follow. First, this is the **third plane in a row where conformance is the weakest link** —
the accessibility plane found the same (T15/T16 and the BSD-licensed caption conformance gap), and
the ad plane found it in SCTE-35 signalling. Validation is consistently the least-maintained layer in
open media tooling, across three unrelated planes. Second, MediaConch's own license file records that
bundled libraries and `libcurl`/`zlib` support are **disabled pending consent of the PREFORMA
Consortium**, the EU programme that funded it. A client build that depends on it should budget to
carry it. Do not present it as a maintained upstream.

## 26. The fifth plane, the fifth identical result — and the law now has a three-step gradient

Five planes of this KB have now been measured independently — provenance, monetization,
accessibility, conformance/preservation, and identification/rights — and the law has not broken once:

> **Permissive open source follows the file format, not the judgment.**

The identification plane is the most precise case yet, because here the same subject matter splits by
*function* rather than by subject, giving a three-step gradient inside a single plane:

| Function | Nature | Measured state (2026-11-22) |
|---|---|---|
| **Declare** a rights reservation | Format problem | `ai-robots-txt/ai.robots.txt` — MIT, 4,265★, **pushed the day of this pass** |
| **Honour** a reservation | Judgment problem | `Spawning-Inc/datadiligence` — MIT, 41★, **dormant since 2024-10-09** |
| **Settle** the obligation | Pure judgment | **Literal zero.** `pay-per-crawl` top six = 5, 2, 2, 0, 0, 0 stars |

**Publishers are tooled to say no; nobody maintains the code that listens; nothing at all computes
what is owed.** After five planes this is no longer a pattern to note — it is the planning assumption.
Where a client's problem is a *format*, assume a permissive implementation exists and go find it.
Where it is a *judgment*, assume there is nothing and price the build.

## 27. The rights-reservation standard is itself unlicensed — and two of its three tools are too

**RSL 1.0** (Really Simple Licensing) is the most significant new rights layer in media this year:
launched September 2025 with the spec finalised in December 2025, backed by **Reddit, Yahoo, Medium,
Quora and Ziff Davis**, governed by the nonprofit **RSL Collective** (Doug Leeds, Eckart Walther),
with Fastly and Adweek supporting without joining. It extends `robots.txt` from yes/no into XML
licensing terms: **free, attribution, subscription, pay-per-crawl and pay-per-inference** — that last
one meaning payment falls due only when content is used to generate a response. It reached UK
Parliament as written evidence (AIC0023). An RSS co-creator is behind the protocol.

And the official repository — [`rslstandard/rsl`](https://github.com/rslstandard/rsl), 47★ —
**contains no licence file.** Checked across `master` and `main` against eleven filenames. Neither
does [`jeffpaul/rsl-wp`](https://github.com/jeffpaul/rsl-wp) (35★), the active WordPress plugin that
implements it. Without a grant, default copyright applies: **all rights reserved.** The only properly
licensed RSL tool found is [`onurkanbakirci/rsl-editor`](https://github.com/onurkanbakirci/rsl-editor)
(MIT, 22★).

*The irony is quotable and the risk is real:* a client building AI-licensing compliance could end up
with an unlicensed dependency at the root of its compliance stack. **Commercial read:** use the
published spec and the MIT tool, raise the packaging defect explicitly in any rights engagement, and
do **not** treat this as a reason to dismiss RSL — the publisher bloc is real and the direction of
travel is clear. Whether AI labs will honour it is genuinely unresolved; do not build a business case
on the assumption that they will.

## 28. A licence can be a property of the compile, not of the repository

T22 recorded that a licence can hide in an HTML file or a packaging classifier. `chromaprint` — the
industry-standard audio fingerprinter, 1,432★ — is worse, and it says so itself:

> *"Chromaprint's own source code is licensed under the MIT license, but we include some parts of the
> FFmpeg library, which is licensed under the LGPL 2.1 license. As a whole, Chromaprint should be
> therefore considered to be licensed under the LGPL 2.1 license."*

Then a third layer: *"when distributing Chromaprint in binary form, you should also take into
consideration the license of the external FFT library that you compile Chromaprint with."* The
candidates are FFmpeg (LGPL-2.1), **FFTW3 (GPL-2.0+)** and KissFFT (BSD-3). **Build against FFTW3 and
the redistributed binary is arguably GPL.**

So the licence of the shipped artefact is a function of the build configuration. No SPDX field, no
GitHub licence badge, and **no SBOM scan of the source tree** can capture that — which is why the
GitHub API reports `NOASSERTION` here and why a licence-automation gate would have waved it through.

**CI rule, generalisable to all twelve industries:** for any native dependency, resolve the licence of
the **linked** libraries, not the repository. If the build graph is not in the licence report, the
licence report is incomplete.

## 29. The only genuinely open content identifier is the one nobody has adopted

| Identifier | Controlled by | Open implementation |
|---|---|---|
| ISRC (recordings) | IFPI, decentralised national agencies | None |
| ISWC (works) | CISAC | None |
| ISAN (audiovisual, ISO 15706) | ISAN-IA | ⛔ None — `isan` → 1,942 results, **zero relevant** |
| EIDR (audiovisual, commercial) | EIDR Association (membership) | ⛔ None — `eidr` → 160 results, **zero relevant** |
| CWR (works registration) | CISAC societies | Two, dead since **2015** and **2018** |
| DDEX ERN (release delivery) | DDEX (licence to implement) | ✅ `miqwit/dedex`, MIT, live |
| **ISCC** | **ISO 24138:2024 — open** | ✅ `iscc-core`, Apache-2.0 — **26★** |

The two identifiers with usable open implementations are **the two that are not gated by a membership
registry.** That is not a market oversight; it is the licence structure of the industry showing
through the code. Where the scarce asset is the *allocation*, an open parser has no value, so nobody
writes one.

**The honest two-sided reading, and a proposal must carry both halves:** ISCC is the only content
identifier in media Globant can build on with no licence negotiation — ISO-published, Apache-2.0,
designed to *complement* DOI, ISBN, ISAN, ISRC, ISSN and ISWC rather than replace them. And a
26-star reference implementation is evidence the industry has not adopted it. **Pitch it as the
internal join key, never as the identifier a client's partners will recognise.** (ISO 24138 is first
edition, 2024-05 — there is **no 2026 revision**; checked, because an invented version number is
exactly the error this KB has been punished for.)

## 30. A government has now measured music data's biggest unsolved problem — and put a number on it

The UK government's **music streaming metadata report (April 2026)** found that there is **no central
registry for ISRCs**, producing duplication and confusion, and — the number worth carrying —
**ISRC-to-ISWC matching rates ranging from 0% to 85% depending on the source.** Music Business
Worldwide describes linking songs (ISWC) to recordings (ISRC) as music data's *"single biggest
unsolved problem"*, and DDEX convened a Meta-backed summit on it in Toronto on **19 November 2026**
— three days before this pass, **with no coverage of the outcome yet found.**

**Why this is the most sellable fact in the plane:** a government report has converted a vague
industry complaint into a measured defect with a range. The gap between 0% and 85% is a reconciliation
problem — fuzzy matching, confidence scoring, human adjudication of the residue — which is precisely
the *judgment* layer that §26 shows has no open implementation. It is also auditable, which means it
can be sold as an outcome rather than a tool. Watch for the summit readout; it is a procurement
trigger.

⚠️ **Unverified and must not be asserted:** `new.ddex.net` does not resolve from this session, so
**DDEX's implementer-licence terms and fees are unresearched.** Search results indicate DDEX is a
not-for-profit body (20 years old in 2026) whose standards require a licence to implement, that some
Sony DDEX compliance capability has been released as open source, and that DDEX is **developing a
rights-reservation message for AI** — all of it to be confirmed at source before it reaches a client.
Treat the terms as *unresearched, not free*.

## 31. There is no actively maintained permissive audio fingerprinter

Measured, and it is a precise gap rather than a lament:

- **Actively maintained:** `JorenSix/Olaf` (**AGPL-3.0**, 426★, 2026-10-16), `JorenSix/Panako`
  (**AGPL-3.0**, 276★, 2026-09-17). Both copyleft.
- **Permissive:** `worldveil/dejavu` (MIT, 6,789★ — **last push 2024-04-22**),
  `adblockradio/stream-audio-fingerprint` (MPL-2.0, 781★ — **2021-11-05**), `dpwe/audfprint`
  (MIT, 622★ — **2019-09-24**). All dormant.
- **And the one in the middle:** `chromaprint` is active but, per §28, effectively LGPL-2.1.

A client wanting permissive audio fingerprinting is choosing between **vendoring dead MIT code** and
**accepting network copyleft on a service**. Both are defensible; neither is free. `dejavu`'s
star:fork ratio of 4.6 and `audfprint`'s Columbia/Google provenance mean the dormant code is
*reference-grade*, not abandoned junk — vendoring is the pragmatic answer, and the maintenance cost
should be in the estimate rather than discovered later.

## 32. The sixth plane breaks the pattern — the agent layer is misallocated, not missing

Added 2026-11-25 (pass 6). Passes 2–5 each ended identically: high obligation, no agent layer. Four
repetitions made it tempting to conclude that regulation suppresses open tooling. **The production
plane kills that reading**, because here the substrate is the healthiest in this entire KB — **22
ASWF repos over 100★, 20 of them Apache-2.0 or BSD-3-Clause** (the two exceptions are an image
corpus and the governance repo), 15 pushed within 9 days of the pass, under a
Linux Foundation umbrella with studio funding — and the *studio-facing* agent layer is still **one
star**.

What the stars actually track, measured:

| Layer the bridge targets | Best open bridge | Stars |
|---|---|---|
| Blender — free, mass individual base | `ahujasid/mcp-for-blender` (MIT) | **35,788★** |
| Houdini — paid, studio | `healkeiser/fxhoudinimcp` (MIT) | 437★ |
| Maya — paid, studio | `PatrickPalmer/MayaMCP` (MIT, dormant) | 124★ |
| OpenUSD — studio interchange | `dcc-mcp/dcc-mcp-openusd` (MIT) | **2★** |
| OpenAssetIO — studio asset resolution | `OpenAssetIO/openassetio-mcp` (Apache-2.0) | **1★** |

**The law, restated for six planes:** the open agent layer tracks the size of the **individual
practitioner population** — not the regulatory obligation, and not the substrate's health. Where the
user is a person, the bridge is enormous; where the user is a pipeline, it is a rounding error.

This is the more general statement, and it predicts: in any plane, find where individuals install
software and you will find the agents; find where *systems* talk to each other and you will find the
gap. It also tells you where the money is, since the 35,788★ bridge is crowded and undifferentiated
while the 1★ bridge has **no commercial alternative a client could buy instead**.

## 33. OpenUSD is not Apache-2.0 — the fourth distinct way a licence hides

Added 2026-11-25. `PixarAnimationStudios/OpenUSD` (**7,675★ / 1,486f**, pushed 2026-11-23) — the
foundation of the modern 3D pipeline — is licensed under the **"Tomorrow Open Source Technology
License 1.0"** (`LICENSE.txt`, 49,827 B). Its preamble states the whole delta: it *"differs from the
original Apache License 2.0 in the following manner. Section 6 ('Trademarks') is different."*

Functionally Apache-2.0 with a modified trademark clause — but a **separate, renamed licence**, and
the GitHub API reports `NOASSERTION`. This KB has now recorded four hiding places for a licence:

1. a non-standard filename (`license.txt` lowercase, `COPYING.md` — pass 5);
2. a licence owned by the **compile**, not the repo (Chromaprint's LGPL-as-a-whole — pass 5);
3. an HTML file or nothing but a packaging classifier (trend 22);
4. **a renamed fork of a standard licence whose only difference is trademarks** (this pass).

None of the four is visible to an SPDX field, a badge, or an SBOM scan of the source tree. Also
`AcademySoftwareFoundation/OpenRV` (797★): Apache-2.0 **except components enumerated in
`Notice.txt`** — case 2 again, in a repo clients will want.

## 34. A third licence category at the platform tier: delayed-open, and it splits one product

Added 2026-11-25. This KB's law — *permissive at the pipeline, copyleft at the platform* — held in
five planes with copyleft at the platform. AYON adds a third category and puts the boundary **inside
a single product**: `ayon-backend` and `ayon-frontend` are **FSL-1.1-ALv2** (Functional Source
Licence, ALv2 *Future* Licence: source-available now, Apache-2.0 only after a delay — **not
OSI-approved**), while **every** AYON client and DCC integration is plain Apache-2.0 (`ayon-core`
80★, `ayon-launcher` 55★, `ayon-blender` 20★, `ayon-houdini` 18★, `ayon-kitsu` 14★).

"AYON is Apache-2.0" is therefore true of everything a developer touches and false of the server a
client deploys. Compare `cgwire/kitsu` (AGPL-3.0) whose Python client `gazu` is **LGPL-3.0** — a
vendor deliberately marking the integration seam with a weaker copyleft. Read that signal and build
on the client, never the server.

## 35. The UK now subsidises AI inside VFX — and the apportionment duty is the product

Added 2026-11-25. The UK's additional VFX tax relief allows claims on up to **100% of eligible UK VFX
spend**, and the proposal to **exclude generative AI from the uplift was dropped after industry
consultation**, so AI costs incurred in the VFX process are eligible. But relief covers VFX costs and
**not** other production costs such as shooting against an LED volume — so a virtual-production shoot
must **apportion** its spend between eligible and ineligible portions.

That apportionment is an evidence problem over artefacts this KB already types: `OpenTimelineIO`
timelines, `OpenAssetIO` asset identity, `OpenCue` job records, `camdkit` stage metadata. **A
tax-credit evidence trail is CFO-sponsored and deadline-bound** — the strongest buying signal in this
file. See Pattern 18.

⚠️ **Confidence:** `www.gov.uk` does not resolve from this session, so this trend rests on trade-press
and advisory-firm reporting and is **not verified against the primary policy paper**. A 2024
consultation indicated existing film/HETV reliefs cease after **1 April 2027**; current status
unconfirmed. Verify before it reaches a deck.

## 36. India's VFX recovery runs straight into the AI paradox

Added 2026-11-25. FICCI-EY 2026: Indian animation and VFX grew about **1.6% in 2025** after falling
**9% to ₹103bn in 2024**; the VFX segment is recalibrating toward **₹48bn**, with the combined
segment projected at **₹138bn by 2028**. The same report attributes **up to 40% time savings** to AI
in **rotoscoping, clean-up and pipeline work**.

Those are the *billable* tasks of the world's largest production-services industry. The efficiency
story and the disintermediation threat are **the same sentence applied to the same P&L** — which is
why the APAC (and LATAM) offer has to be pipeline ownership, priced per seat and per system, rather
than fewer hours of the thing the client sells. Netflix's Eyeline Studios in Hyderabad is the
up-stack signal to point at.

## 37. In North America this plane is governed by a labour contract, not a statute

Added 2026-11-25. The IATSE Basic Agreement permits AI **"as a tool"** with limitations and sets up
standing AI meetings; VFX workers on Marvel/Disney and *Avatar* projects ratified **first IATSE
contracts**, and Apple Studios' in-house VFX artists reached a first contract with AI protections.
SAG-AFTRA's four-year agreement limits AI performers with **no strike rights over AI until 2030**;
2026 WGA and DGA agreements expand AI governance.

**The deliverable a statute wants and the one a contract wants are different.** A statute wants a
label on the output (EU AI Act Art. 50, the APAC labelling regimes — trends 2, 14, 18). A collective
agreement wants a **per-shot record of what the AI did, who approved it, and what human work it did
or did not displace.** Nobody is selling that. Meanwhile production jobs fell **over 35% from October
2022 to February 2026**, so the framing must be capacity and compliance evidence, never headcount.

## 38. The orchestration tier licenses like a platform, and OpenCue is the exception

Added 2026-11-25. Render management is a tiny field — `render farm manager` returns **32 results in
total** — and its licences line up with this KB's *platform* tier rather than its *pipeline* tier:
`CGRU/cgru` is **LGPL-3.0** (302★) and the 2026 entrant `uberware/sqi` chose **AGPL-3.0** (44★,
pushed the day of the pass). The only permissive option at scale,
`AcademySoftwareFoundation/OpenCue` (**Apache-2.0**, 1,010★), is permissive because a **foundation**
holds it — not because the market trends that way.

Consequence for a hosted-render proposal: build on OpenCue and the licence position is clean; build
on `sqi` and a service offering is a network-copyleft question to answer *before* the architecture
is drawn.

## 39. Generic English is worthless in this plane — two of the KB's worst contaminated queries

Added 2026-11-25. Both measured, both would have produced fictional rows:

| Query | Total | What the top of the page is |
|---|---|---|
| `virtual production` | **1,291** | A Go static-asset embedder (`knadh/stuffbin`, 205★ — matches "production"), a dumped W3C report (176★), a mainframe emulator self-describing as "production-quality" (113★), an unlicensed 121★ setup guide. One defensible hit in the top six. |
| `color grading open source` | 42 | **Four of the top six are the Bee Movie script** (228★, 98★, 53★, 40★, each opening *"According to all known laws of aviation…"*). |

Meanwhile the *standard's name* works perfectly: `opentrackio` returns **8 results of which 4 are
real and permissively licensed**, and the genuine colour infrastructure (`OpenColorIO` 2,145★,
`OpenColorIO-Config-ACES` 440★) is reachable only by project name. Pass 5's rule gets its sharpest
case: **1,291 looks like abundance and is noise. Read the results, never the total.**

## 40. The scarce thing is the right to observe — and this pass put a price on it

This KB's structural law has been restated six times. Pass 7 measures it in the one plane where the
barrier can be **costed from a primary document**, and the law comes out sharper than any previous
formulation.

CIMM's *"Funding the Fiesta: The Economics of National TV Currency in the US Market"* (January 2026,
downloaded and read, not summarised) gives the floor:

- **$1.5–2B/year** total addressable market for US national video currency.
- **85–90%** of it goes to Nielsen → **$1.2–1.8B** of revenue.
- **~$110M/year** operating cost for an *entry-level* currency-grade service; **~$250M/year** of
  revenue needed for a competitive one.
- **42,000+ homes** in Nielsen's panel, at an estimated **$150–250M/year**; every challenger panel
  targets **5,000**.

Now place that against the open-source health of the same plane, measured the same day:

| Step | What it must observe | Open source |
|---|---|---|
| Recommend the next item | your own log | `recommenders-team/recommenders` **MIT, 22,012★**, pushed 2026-11-05 |
| Model what media did | your spend + outcomes | `meridian` **Apache-2.0, 1,616★**; `Robyn` **MIT, 1,540★**; `pymc-marketing` **Apache-2.0, 1,314★** — all ≤15 days |
| Count audience as currency | a national panel | **`reach frequency curve media` = 1 result and it is an ML tutorial** |

**The refinement:** earlier passes said the *licence of the knowledge content* decides whether open
source can comply (CPT, MedDRA, ISRC). This plane has no content licence to blame — there is no
copyrighted codebook. What is scarce is **a continuously operated observation apparatus plus an
accreditation regime** (MRC accreditation, JIC certification). So the law generalises:

> **Open source appears wherever compliance can be *written*, and is absent wherever it must be
> *operated*.** A permissive licence cannot produce a $110M/year panel, and no amount of community
> goodwill substitutes for the right to observe.

**Commercial consequence, and it is the one to lead with:** eMarketer's H1 2026 read is that
**outcome-based measurement is overtaking the currency debate** in TV/CTV. Advertisers routed around
the closed currency, and they routed into exactly the layer open source is strong in. Sell
incrementality on the client's own data; never sell a currency substitute.

## 41. A licence can be a PDF — the fifth distinct way a licence hides, and the first that defeats every scanner

Running total of how a licence has hidden from automated detection in this KB:

1. **A non-standard filename** — `license.txt` lowercase, `COPYING.md` (pass 5: Panako, musicbrainz-server).
2. **A licence owned by the compile** — Chromaprint's own code MIT, the linked FFT library deciding the
   binary's terms (pass 5).
3. **An HTML file, or nothing but a packaging classifier** (pass 4).
4. **A modified standard licence** — OpenUSD's "Tomorrow Open Source Technology License 1.0", Apache-2.0
   with Section 6 rewritten (pass 6).
5. **NEW — a binary document referenced by a text stub.** `comScore/ComScore-Android`'s `LICENSE` is
   **145 bytes of prose** saying *"Please refer to the license agreement document on the following
   URL"*, pointing at **`LicenseAgreement.pdf`, 58,057 bytes**.

Category 5 is the worst for tooling, because categories 1–4 all leave *text* somewhere a scanner can
read. Here there is text, and it is a sentence telling a human to open a PDF. GitHub reports
`NOASSERTION` for all three Comscore repos.

**And the content matters more than the format.** Read, the PDF is **not a software licence in the OSI
sense** — it is a **data-collection agreement**, granting Comscore rights to viewing data collected
through the SDK "for inclusion in syndicated and/or custom products and services … as well as use in
its work with certain industry associations and market currency initiatives or joint industry
committees." The code is published; what the integrator accepts is that **their audience becomes someone
else's currency.** That is the exact inverse of the rights-reservation plane (pass 5), where the entire
*purpose* of the artefacts was machine-readable terms. All three repos were **pushed on measurement
day** — live, maintained code.

**New rule, and it generalises past media:** **a `LICENSE` file under ~300 bytes is a pointer, not a
licence.** Treat it as unresolved and follow it, including into binary documents. Add to the CI gate
alongside pass 5's "resolve the licence of linked native libraries, not the repo".

## 42. Three of this plane's most-cited "open source" platforms are not open source, or not the licence everyone says

The audience plane produced a higher rate of licence error than any previous plane, and every case was
caught by **reading the file** rather than trusting a badge, a vendor comparison or the GitHub API:

- **`Unleash/unleash` is AGPL-3.0, not Apache-2.0.** Third-party comparisons — including one dated
  2026 — describe its open-source core as Apache-2.0. `LICENSE` on both `main` and `master` is **34,523
  bytes of GNU Affero GPL v3**, and the API agrees. For a client embedding flag evaluation in a
  streaming service this is the difference between a permissive dependency and network copyleft.
- **`rudderlabs/rudder-server` is under the Elastic License 2.0** (3,793 B) — **source-available, not
  open source.** ELv2 forbids providing the software to third parties as a managed service, which is
  the systems-integrator business model. It is described as open-source CDP infrastructure nearly
  everywhere, and it was pushed on measurement day, so staleness gives no warning.
- **`bytedance/monolith` is Apache-2.0 but ARCHIVED** (`LICENSE` 12,621 B; the API says `NOASSERTION`
  only because a copyright preamble precedes the Apache text). 9,283 stars, last push **2025-10-13**.
  Permissive and dead — the licence check passes and the project is still unusable.

Alongside these: **`twitter/the-algorithm`** (74,125★) is **AGPL-3.0 and 14 months stale**, and
**`google/lightweight_mmm`** (1,055★) is **archived**, replaced by Meridian — yet both remain top
search results for their categories.

**The pattern across all five:** in this plane, **the signals that normally substitute for reading —
star count, recent push, a vendor's own comparison page, the SPDX field — each failed on at least one
repo, and no single signal caught all five.** The only method that worked was: resolve existence with
`git ls-remote`, resolve health with `pushed_at` **and** `archived`, and resolve the licence by reading
the file and following what it points at.


## 43. The eighth plane is the first where copyright is not the gate — patents and DRM keys are

Seven planes, one answer: the gate was always a **copyright** licence, on the code (copyleft at the
platform) or on the content (CPT, MedDRA, a measurement currency). The live & delivery plane breaks
that. Here the code is permissive nearly everywhere — `ossrs/srs` MIT 29,457★, `bluenviron/mediamtx`
MIT 20,772★, `pion/webrtc` MIT 16,926★, `shaka-packager` BSD-3, `trafficserver` Apache-2.0 — and two
**non-copyright** instruments gate it absolutely:

1. **Patent pools.** The codecs' own reference implementations refuse to license the patents.
2. **DRM key agreements.** Packaging and encryption are open; the key server is unobtainable as open
   source by design.

Neither appears in a licence badge, a GitHub label or any listicle. **This is the most commercially
important structural finding in eight passes**, because it means a licence audit — the thing every
procurement process actually does — returns "all clear" on a stack with two hard commercial gates in
it. Verified 2026-11-26 across 45 repos, 45/45 resolving.

## 44. `BSD-3-Clause-Clear` is a patent carve-out, and the "Clear" is the whole point

The industry reads "BSD" and stops. Read from the licence files:

| Repo | Licence | Clause |
|---|---|---|
| `fraunhoferhhi/vvenc`, `fraunhoferhhi/vvdec` | BSD-3-Clause-Clear | "NO EXPRESS OR IMPLIED LICENSES TO ANY PARTY'S PATENT RIGHTS ARE GRANTED BY THIS LICENSE" |
| `v-novaltd/LCEVCdec` | The Clear BSD License | same |
| `AOMediaCodec/SVT-AV1` | BSD-3-Clause-Clear | no patent grant |
| `Fraunhofer-IIS/mpeghdec` | Fraunhofer FDK MPEG-H | §3 titled **"No PATENT LICENSE"** |
| `Dash-Industry-Forum/dash.js` | BSD-3 variant | "including patent rights, and **no such rights are granted** under this license" |
| **`Netflix/vmaf`** | **BSD-2-Clause-Patent** | **"an express patent grant"** |

VMAF is the control case that makes this deliberate rather than accidental: same industry, same era,
**opposite** licence — because VMAF is an unpooled metric and VVC/LCEVC/MPEG-H/AV1 are pooled. **The
licence tracks the patent pool, not the generosity of the author.** Corollary for every engagement:
a permissive codec licence is not a cost signal. Budget pool royalties as a separate line item.

## 45. The only DRM you can run entirely on open source is the one no studio will accept

The chain is open right up to the key and then stops dead. Packaging (`shaka-packager`, BSD-3),
CMAF/DASH/HLS, and Common Encryption (CENC, ISO/IEC 23001-7) are all open — one encrypted asset can
serve all three DRMs, split only by scheme (`cenc`/AES-CTR vs `cbcs`/AES-CBC, and **FairPlay requires
`cbcs`**). But Widevine, PlayReady and FairPlay each require **their own licence request, endpoint
and key-delivery protocol under a signed agreement**: Google's partner programme with a Master
Licence Agreement and security questionnaire, a Microsoft agreement for any PlayReady service
provider, Apple's developer agreement for FairPlay. **ClearKey** is the only fully-open DRM, and it
is a test mechanism no rights holder accepts for premium content.

Three private companies hold the cryptographic root of trust for premium video and issue it by
contract. No amount of engineering changes this. **It is a procurement dependency for week one, not
a build task** — and it is the structural reason this plane has no agent anywhere near the DRM step.

## 46. A licence can live one directory below root — the sixth distinct hiding place, on a tool everyone recommends

`axiomatic-systems/Bento4` (2,530★, pushed 2026-11-22): GitHub's API reports **`NONE`**. The truth is
**GPL-2.0 with a paid commercial alternative**, and the text sits at **`Documents/LICENSE.txt`**
(18,693 B): "Bento4 is available under two different licenses… a non-GPL commercial license is
available from Axiomatic Systems LLC."

Bento4 is one of the two tools every multi-DRM packaging guide names — a commercial DRM vendor even
publishes a Bento4 configuration guide for it. A client who links it into a proprietary packaging
service has shipped GPL-2.0 obligations or owes a commercial fee, **and GitHub told them there was no
licence at all.** The taxonomy is now six: an HTML file; a packaging classifier; compile flags; a
modified Apache that keeps the name; a PDF; **a non-root path**. Six mechanisms, one rule: the
licence *field* is not evidence. Only the file is.

## 47. A standards body minted its own licence, and production use carries no patent rights

The **5G-MAG Public License v1.0** (`5G-MAG/rt-libflute`) is Apache-2.0 in structure and wording with
the patent grant rewritten:

- **§3.1** licenses Essential Patents "to make, have made, use, and otherwise transfer **(excluding
  selling)** the Work, **solely for study, testing and research purposes**."
- **§3.2**, for every other purpose, grants nothing: "**You commit to be prepared to negotiate**" a
  licence with **each Contributor** on **FRAND** terms.

A field-of-use restriction on selling means **this is not open source** under the OSI definition,
however the file is named — and it governs the reference stack for 5G Broadcast/MBMS, precisely the
technology a European public broadcaster would pilot. It reads as permissive to every scanner and to
every engineer who recognises the Apache shape. **A pilot that quietly becomes a service has
acquired an unbounded patent obligation.** Seventh licence shape, and the most dangerous yet, because
the disguise is structural rather than clerical.

## 48. The compile-flag licence is now a pattern, not an anecdote — FFmpeg is the second case

Pass 5 recorded Chromaprint as "a licence decided by the compile" and called it a new category.
`FFmpeg/FFmpeg` (68,197★) confirms it: `LICENSE.md` states most files are **LGPL-2.1+** and that
LGPL-2.1+ applies in combination — but `--enable-gpl` produces a **GPL** binary. Two independent
instances make it a pattern, and the operational rule follows: **audit your build flags, not just
your dependency list.** A dependency manifest cannot express this, which means no SCA tool catches
it. The same binary is two different licences depending on how it was compiled.

## 49. The platform tier broke its own law twice in one plane — and one project went to public domain

This KB's "copyleft at the platform, permissive at the pipeline" law held across six planes.
This plane produced two exceptions at once:

- `DDVTECH/mistserver` (521★) — **Unlicense, public domain**. `COPYING.md`: "dedicated to the public
  domain… anyone can use MistServer for any purpose - including commercial purposes - without any
  restrictions." A platform-tier streaming server with **zero** obligations.
- `ant-media/Ant-Media-Server` (4,747★) — **no LICENSE file at root at all** (404 across six
  filename probes while `README.md` returns 200), selling an Enterprise Edition against a Community
  Edition. Open-core; get terms in writing.

`OvenMediaLabs/OvenMediaEngine` still obeys the law at AGPL-3.0. But MistServer goes further than the
MIT exception recorded in §10: **public domain is the most permissive outcome this KB has found at
the platform tier**, and at 521★ essentially nobody has noticed it exists.

## 50. APAC owns the permissive substrate in this plane — the first inversion of that pattern in this KB

In every earlier plane the permissive layer was Western-origin and the Asian contribution was
downstream. Here it is reversed: the two most-starred self-hosted streaming servers on earth are
**both China-origin and both MIT** — `ossrs/srs` (29,457★) and `ZLMediaKit/ZLMediaKit` (17,729★,
licence read from file; the API said `NOASSERTION`). `nttcom/moq-wasm` (MIT, NTT) puts Japan in the
MoQ implementer set.

The consequence is regional and practical: an APAC delivery engagement can run on region-native
MIT-licensed infrastructure with **no copyright gate at all**, which makes the licence conversation
there purely about codec patents. It also matters commercially: APAC adspend is growing at
**+5.2% in 2026, the slowest since the pandemic**, against a screen economy racing toward
**USD 200 billion** with a monetisation gap — so cost per delivered stream is a board number, and
the MIT substrate is the answer to it.

## 51. Media over QUIC is the first new media transport since this KB began, and it is permissive in all four regions

Status on 2026-11-26: `draft-ietf-moq-transport` is a **Standards-Track Internet-Draft, not an RFC**
(revision -22, 1 October 2026), with an IETF milestone to request IESG publication on
**2026-12-31**. Eleven vendors demonstrated interoperable implementations at **NAB 2026**; the MoQ
Alliance includes **Akamai, AWS, Cisco, Cloudflare and Fastly**. The LOC container draft carries a
**March 2027** milestone.

What makes it unusual for this KB: the implementations are permissive (`moq-dev/moq` Apache-2.0 and
pushed **2026-11-26**; `facebookexperimental/moxygen` Apache-2.0; `Quicr/libquicr` BSD-2;
`mengelbart/moqtransport` MIT; `nttcom/moq-wasm` MIT), **all four regions are already in the
implementer set**, and the standard is still open to influence before year end. Pilot in 2026,
production expected 2027 — so an engagement starting now is early rather than late.

Honest caveats, because the trade press is bullish: ad insertion is only partially supported, VOD is
unresolved, and **MoQ does not replace HLS/DASH today**. Claims that Cloudflare runs relays in 330+
cities and that Meta moved Instagram Live ingest to MoQ in October 2026 come from vendor blogs and
**could not be verified against primary sources** — flagged, not promoted. `kixelated/moq-js` is
**archived** (2025-06-20): do not start there.

## 52. Europe regulates delivery with a stopwatch, and the political risk has already inverted

EMEA is the only region where a regulator imposes a **latency** requirement on an operational
response. Italy's Piracy Shield lets AGCOM order blocks **without prior judicial review**, to be
implemented **within 30 minutes**; by mid-2026 it had reportedly blocked **120,000+ domains and IPs**
(press-attributed, not AGCOM-confirmed); resolution **47/25/CONS** extended the duty to **VPN and
public DNS** providers, and **Cloudflare was fined multimillion euros** for refusing DNS-level
blocks. An EU study now proposes a **binding Regulation** with the same 30-minute window across
**DNS resolvers, VPNs and CDNs**.

But the criticism has flipped direction. The European Commission (June 2025) raised **overblocking,
opacity and absence of prior judicial review**; Spain's Congress committee voted on **2026-04-29** to
direct reform of the regime; LaLiga is **blocking entire IP ranges rather than specific domains**; and
the EU's own assessment concluded rapid blocking **comes up short** for sports and broadcast.

**So the sellable product is not the blocking — it is the proportionality evidence.** Detection,
evidence capture, an auditable order trail, a 30-minute actuation path across intermediaries, and a
defensible overblocking record. Everyone is building the first half; the regulator is now asking for
the second.

## 53. The US has a dated delivery deadline and no open tooling for it

ATSC 3.0 is the only delivery-side deadline in this KB that forces re-engineering of a live chain:
broadcasters running ATSC 3.0 must currently simulcast "substantially similar" ATSC 1.0 content
**through at least 2027-07-17**, which the FCC's proposal would end; deployment is already past
**80 markets and 70% of population**; NAB wants ATSC 1.0 gone **by 2028 in the top 55 markets and
everywhere by 2030**. The proposal sets **no cutoff date and no tuner mandate**, asking instead for
comment on a tuner requirement and a **labelling** rule for incapable sets.

⚠️ These are a **proposal and a draft order** — this pass found no source confirming a **final
adopted FCC order**, and says so rather than smoothing it.

Underneath the deadline there is a vacuum: **`libatsc3` has no canonical repository.**
`libatsc3/libatsc3` and `Sony/libatsc3` both fail `ls-remote`; the survivors are forks at 13★ (2019)
and 12★ (2023). A regulated, dated, capital-intensive transition with no maintained open
implementation is the cleanest engagement shape in this plane.

## 54. Brazil switched on a national standard built entirely on patent-pooled codecs

The largest LATAM finding in eight passes. Brazil's **DTV+ / TV 3.0** went live on **2026-06-11**
across Rio de Janeiro, São Paulo and the Federal District, timed to the 2026 FIFA World Cup under a
decree signed in August 2025. The stack: **VVC (H.266) + MPEG-5 LCEVC** two-layer video — reportedly
the first national standard built that way — with **MPEG-H Audio mandatory, including over HDMI on
every receiver**, and a physical layer borrowing MIMO and LDM from ATSC 3.0. Globo ran the Rio
lighthouse station; Intelbras and Aquario shipped the first receivers from 2026-06-08.

**All three mandated codecs have reference implementations that refuse to grant patents** (trend 44),
and **one has no open encoder at all**: `Fraunhofer-IIS/mpeghdec` is a decoder, so every DTV+ audio
encode in the country must pass through commercial equipment. A whole nation's broadcast standard now
rests on three royalty-bearing codecs whose open implementations point licensees at "the respective
patent owners". The royalty exposure is **accruing now**, which makes codec-royalty mapping a
CFO-sponsored engagement with a deadline already in the past.

## 55. The best substrate in this KB has the emptiest agent layer — and the queries prove it

Eighth consecutive confirmation of the structural law, and the most extreme instance. The substrate:
four repos above 16,000★ all pushed within 24 hours of measurement. The agent layer: five
stars-sorted `search/repositories` queries, of which **`streaming agent llm video ops` returned zero
results**, and the others returned general video-*editing* agents. The only genuine real-time agent
at any star count is **`yondonfu/ai-rtc-agent` — 26★, MIT, last pushed 2024-11-04.**

Nothing open source watches an encoder ladder, reacts to a QoE collapse, re-packs a failing rendition
or drives an origin. Meanwhile the industry consensus for 2026 is that **agentic AI** is the theme
and that the question has shifted from adoption to **business value** (Akamai), with
**87% of M&E boards having approved major AI investments** (Grant Thornton) while North American
firms remain **stuck in early experimentation** (Forrester). Authorised budget, named priority,
empty shelf — on the layer that runs the business.

## Low-confidence items — flagged, not promoted

- Market sizing diverges ~2× across vendors (see `intel/market.md`); every figure is a vendor estimate.
- "94% AI adoption by 2026" and "204,000 jobs disrupted by 2026" circulate widely; the first has no
  clear sourcing and the second comes from a 2024 study. Do not quote either.
- A 40% LATAM production-cost reduction (VidTech, AI-generated hosts in Colombia and Brazil) rests on
  a single trade article.
- "Google open-sourced Credentio (C2PA validator), Aug 2026" — **no such repo at `google/credentio`**.
  Reported by secondary sources only; unverified at the slug everyone cites. (Unchanged 2026-11-22.
  Note this is *not* the same question as SynthID: `google-deepmind/synthid-text` **is** real and
  Apache-2.0 — see trend 2.)

Added 2026-11-22:

- **Deepfake incidents in Latin America and the Caribbean "rose 255% between 2023 and 2024"** —
  Sumsub, cited in Caribbean trade coverage. Single vendor, methodology not published. Directionally
  useful, not a figure for a client deck.
- **Media *localization* market "$5.6B (2024) → $12.8B (2033), APAC fastest at 12.3% CAGR"** —
  DataIntelo via a trade blog. Narrower and therefore more plausible than the all-in "AI in M&E"
  numbers, but still one vendor at second hand. Better than what this KB had; not primary.
- **"68% reduction in subtitle generation costs"** and **"150+ languages dubbed in real time at
  IBC 2026"** — both from unsourced vendor blogs. Do not quote.
- **"Over 3,500 live shows produced with Sofie"** — vendor claim (SuperFly.tv). The *verifiable* part
  of the Sofie story is the code, its MIT license, its push dates and that NRK/BBC/TV 2 use it; lead
  with those and leave the show count out.
- **`chatfire-AI/drama-skills` "~4.4k stars, MIT"** and **`huobao-drama` "~18k stars"** — promoted by
  an AI-microdrama directory site. The first slug does not resolve; the second was not confirmable at
  any slug and is reported CC-BY-NC-SA (non-commercial). Do not re-adopt either.

---

## Trend 9 (added 2026-11-26, pass 9) — the enforcement stack went open, and the licence retreated into the weights

**What changed.** Trust & safety tooling was, until roughly 2025, something a platform either bought
(Hive, ActiveFence, Checkstep) or built from nothing. In 2026 three operators donated the parts they
run in production: **Discord's rules engine** became
[roostorg/osprey](https://github.com/roostorg/osprey) (Apache-2.0, 511★), **ROOST** shipped
[coop](https://github.com/roostorg/coop) (Apache-2.0, 150★, pushed 2026-11-26), **Google Jigsaw**
published [Altitude](https://github.com/Jigsaw-Code/altitude) and
[conversationai-moderator](https://github.com/conversationai/conversationai-moderator) (both
Apache-2.0), **Meta** published [content-review-filters](https://github.com/meta/content-review-filters)
and keeps [ThreatExchange](https://github.com/meta/ThreatExchange) (BSD, 1,417★) current, and
**Bluesky** published [Ozone](https://github.com/bluesky-social/ozone) (dual MIT/Apache-2.0, 548★).

**And what did not change.** The *judgment* layer stayed closed, and it closed itself with **model
licences** rather than code licences:

- [Roblox/RobloxGuard-1.0](https://github.com/Roblox/RobloxGuard-1.0) — **RAIL Research-Only**
- [Roblox/voice-safety-classifier](https://github.com/Roblox/voice-safety-classifier) — **CC-BY-SA-3.0**
- [meta-llama/PurpleLlama](https://github.com/meta-llama/PurpleLlama) (Llama Guard) — **Llama 3.2 Community**, acceptable-use terms + MAU threshold
- [SCLBD/DeepfakeBench](https://github.com/SCLBD/DeepfakeBench) — **CC-BY-NC-4.0**

while the same companies' *libraries* went Apache-2.0 ([Roblox/Sentinel](https://github.com/Roblox/Sentinel)).

**Why it is the pattern and not an accident.** The training data is the moat. A safety model trained
on a decade of real abuse reports from a platform with hundreds of millions of users cannot be
reproduced from public data, and the weights are the only place that advantage can be defended. The
code around it is worth more as a standard than as a secret.

**The consequence for a client.** The cleanly usable judgment layer is short and must be named
precisely: [ibm-granite/granite-guardian](https://github.com/ibm-granite/granite-guardian)
(Apache-2.0, 192★), [openai/gpt-oss-safeguard](https://github.com/openai/gpt-oss-safeguard)
(Apache-2.0, 67★ — takes the client's *own written policy* as input), and
[unitaryai/detoxify](https://github.com/unitaryai/detoxify) (Apache-2.0, 1,320★). Everything more
famous is either archived ([yahoo/open_nsfw](https://github.com/yahoo/open_nsfw) 6,018★ archived
2018; [protectai/llm-guard](https://github.com/protectai/llm-guard) 3,223★ archived 2026), stale
([GantMan/nsfw_model](https://github.com/GantMan/nsfw_model) 2024,
[bumble-tech/private-detector](https://github.com/bumble-tech/private-detector) 2023), copyleft
([notAI-tech/NudeNet](https://github.com/notAI-tech/NudeNet) AGPL-3.0), or unlicensed
([LAION-AI/CLIP-based-NSFW-Detector](https://github.com/LAION-AI/CLIP-based-NSFW-Detector) 473★, no
licence file at all).

**Falsifiable prediction.** The share of leading open safety models under research-only /
non-commercial / community licences will **rise** through 2027, not fall. If a state-of-the-art
safety classifier ships Apache-2.0 weights, this trend is wrong and the next pass should say so.

## Trend 10 (added 2026-11-26, pass 9) — four regulators, four different compliance artifacts, one calendar

Minor protection and platform accountability became enforceable in all four regions within about
fifteen months, and **they do not ask for the same artifact.** The buyer in each region is paying for
a different thing, which is why a single "content moderation" pitch lands in none of them:

| Region | The instrument | What it actually demands | Open artifact that discharges it |
|---|---|---|---|
| **EMEA** | DSA + the Age Verification Blueprint | A *verifiable age signal* and a *machine-readable statement of reasons* per enforcement action | The Commission's own code — [av-app-android-wallet-ui](https://github.com/eu-digital-identity-wallet/av-app-android-wallet-ui) (EUPL-1.2) and [transparency-database](https://github.com/digital-services-act/transparency-database) (GPL-2.0) |
| **North America** | 18 U.S.C. §2258A + state AI transparency laws | A *filed report to a named authority*, plus provenance labelling | Essentially nothing: [ello/ncmec_reporting](https://github.com/ello/ncmec_reporting) is 7★, unlicensed and dead since 2022 |
| **APAC** | Australia's under-16 regime, app-store codes, divergent national rules | *Account-level age assurance at signup*, per jurisdiction | No open implementation found; the EU libraries are the only reusable ZKP age primitives |
| **LATAM** | Brazil's ECA Digital (Law 15.211/2025, in force 2026-03-17) + Decree 12,880/26 | *Preventive design*: age assessment, parental supervision, no profiling of minors, removal without a court order | None specific; the EU estate plus ROOST Coop is the only credible assembly |

**The reusable observation**: three of the four regions demand an artifact for which **no
region-specific open implementation exists**, and the one estate that does exist was published by
the European Commission under EUPL-1.2 and Apache-2.0 — so it is legally reusable outside Europe. The
EU's compliance code is, in practice, **the only open age-assurance toolkit on earth**, and that is
an export opportunity rather than a European curiosity. Details and dates by region in
`intel/market.md`.

## 56. The tenth plane is the first that is copyleft end to end — and it inverts trend 4 completely

Trend 4 of this file says *permissive at the pipeline, copyleft at the platform*. It has held, with
named exceptions, across nine planes. **The theatrical chain reverses it outright.** Every DCP
authoring tool, every validator but one, and every key manager is GPL-2.0, GPL-3.0 or AGPL-3.0:
`dcpomatic` (GPL-2.0, 175★, pushed 2026-11-24), `libdcp` (GPL-2.0), `libsub` (GPL-2.0+), `opendcp`
(GPL-3.0), `backports`/`dcp_inspect` (GPL-3.0), `dcpdoctor` (AGPL-3.0), `kdmcourier` (AGPL-3.0). The
permissive licences sit **beneath** the pipeline, in the codec and container (`openjpeg` BSD-2,
`asdcplib` BSD-3), and in exactly one tool: **`ClairMeta`, BSD-3-Clause — the validator.**

The practical consequence is unusually clean, so it belongs in the first week of any theatrical
engagement rather than the last: **validation can be built permissively and embedded in a client's
own stack; authoring cannot.** The fortunate part is that validation is also where the client's pain
is highest. The unfortunate part is that nobody planned it that way, so the alignment should be
verified per-component rather than assumed.

## 57. The key that gates every cinema screening on earth has three stars

A KDM (Key Delivery Message) is the dated, per-screen cryptographic key without which a film does
not play. `KDM cinema` returns **eight repositories whose star counts are 1, 1, 1, 0, 0, 0, 0, 0.**

Three stars, total, for the lifecycle management of the instrument that gates roughly **$34.6bn of
box office** across every commercial screen on the planet. It **ties healthcare's `medical
necessity` (3)** as the crudest number ever recorded in this knowledge base, and it is attached to a
materially harder object: medical necessity is a contested judgement, a KDM is **a file with a
published SMPTE schema**. `asdcplib` can write them, permissively. Nothing open manages their
windows, expiry or per-screen reissue. For a circuit running 400 screens against 30 distributors,
key expiry is a daily operational risk with no open tooling and no open commercial alternative — and
the artifact is typed, which is precisely the shape an agent can reason over.

## 58. Absence of a licence file is evidence of *neither* answer — the rule this KB had half-right

Pass 5 found `rslstandard/rsl` with no licence file and correctly concluded **all rights reserved**.
Pass 8 established that **a 404 from the raw channel is never by itself proof a licence is missing**.
This pass supplies the half that was still missing, and it reversed a verdict mid-pass:

- `cth103/libsub` (9★) has **nothing licence-shaped at root** — a shallow clone confirms it — and
  **73 source files carrying a full GPL-2.0-or-later header.** It is unambiguously GPL-2.0+.
- `wolfgangw/backports` (`dcp_inspect`, 40★, active) has no `LICENSE`, `LICENCE` or `COPYING` — it
  has **`gpl.txt`**, 32,473 bytes of GNU GPL **v3**. A fourteen-filename probe across two branches
  missed it; the GitHub API reports `NONE`; the README is silent. **This was written down as
  "unlicensed" until a shallow clone corrected it.**

Put the two side by side and the rule is finally right: `rsl` = no file, no headers → default
copyright; `libsub` = no file, 73 headers → GPL-2.0+. **"No licence file" means you have not
finished looking.** The resolving step is reading the source tree, it costs one shallow clone, and
it finds both failure modes in the same call. Ways nine and ten a licence can hide, for a KB that
had catalogued eight.

## 59. The container layer under every DCP and every broadcast master has been retired by its maintainers

Measured, not inferred, and three of the four data points are from the last fourteen months:

| Project | Licence | ★ | State |
|---|---|---|---|
| `bbc/bmx` | BSD-3-Clause | 88★ | **ARCHIVED** 2025-09-29 |
| `sandflow/regxmllib` (MXF→XML, SMPTE ST 2001-1) | BSD-2-Clause | 39★ | **ARCHIVED 2026-11-22 — four days before this pass** |
| `bbc/libMXF` | BSD-3-Clause | 15★ | **Relocated into the BBC's `-archive` org** |
| `Limecraft/ebu-libmxf` | BSD-3-Clause | 17★ | The EBU's library last moved in **2013**; survives only as a Belgian vendor's fork |

**The format every DCP and every broadcast master is wrapped in is permissively licensed and no
longer maintained by anyone holding a public mandate.** This is the clearest case in this KB of
**permissive-and-abandoned being the worse risk than copyleft-and-alive** — and the two risks sit one
layer apart in the same stack: the container beneath the DCP is free to use and unmaintained, while
the tools that write the DCP are maintained and copyleft. Neither condition appears in a licence
scan, an SPDX field or an SBOM. A new corollary for the method: **when a repo's 422 resolves to an
`*-archive` org, the relocation is itself the finding** — it means the maintainer has formally
retired the project.

## 60. In open source, "cinema" means "cinematic" — the sharpest false friend measured in this KB

`cinema AI agent` returns **205 results with 526 stars in the top six and zero relevance to cinema.**
The hits are a ComfyUI creative studio (262★ MIT), an agent skill for *website* design (119★ MIT),
and three "cinematic look" prompt skills for video models. Not one concerns theatrical exhibition.

This is worse than pass 7's false friend — which was merely numerous — because these results are
**numerous, well-starred, permissively licensed and actively maintained: every property a pass uses
as a quality signal.** A careless hour writes five plausible rows and all five are about video
generation. Two companion lessons:

- **The artifact name is the only query that works.** `DCP`, `KDM`, `asdcplib`, `digital cinema
  package`. Pass 6's rule — *the standard's name is the query* — holds exactly.
- **Shortening a query can manufacture a false abundance, not just cure a false zero.**
  `cinema ticketing platform` returns **350 results** whose top five are 12★/6★/6★/4★/4★, all student
  CRUD. Pass 8 said read the results, not the total. This plane is the strongest case for it: the
  350 results are *why* the absence of an open TMS went unnoticed for ten passes.

## 61. Theatrical accessibility: a zero-star ceiling under a mandate that is nine years old

Pass 3 recorded a 56-star ceiling for audio-description tooling under a statutory mandate and called
it the largest unmet mandate in media. Theatrical beats it. The US DOJ's ADA Title III rule
(published **2016-12-02**) requires every US theatre with a digital auditorium to acquire and
maintain closed-captioning and audio-description equipment delivered to a patron's individual seat,
on a published scaling table. `cinema accessibility app captioning` returns **one repository, with
zero stars.**

The rule's own limiting clause explains the market, and it is the part worth selling against: the
rule **does not require theatres to add captions or audio description to films not already
distributed with those features.** The equipment duty lands on the exhibitor, the content duty on
the distributor, and **the artifact that joins them — an accessibility track correctly authored into
the DCP and verified before the key is issued — has no platform, open or commercial, that treats it
as a first-class object.** Trend 18 of this file applies verbatim: the regulator mandates the
artefact and is silent on the method, which is standing permission to automate.

## 62. LATAM has the most concrete theatrical compliance calendar on earth, and zero tooling for it

Earlier passes recorded Brazil's *"in all formats in which cinematographic works are presented"* and
Mexico's new cinema law as **regulatory** intelligence. This pass supplies the missing half: **the
tooling that would discharge those duties does not exist anywhere.**

- **Brazil**: **Decree 12.796 of 2025-12-23** makes exhibition of Brazilian features mandatory in
  cinemas for the 2026 calendar year, Ancine enforcing — and Ancine has already issued **Instrução
  Normativa 175** to update the quota after finding **Cinemark had exploited a loophole**.
  Accessibility is separately binding on distributors *and* exhibitors under **IN 165/2022**, with
  Ancine's good-practice guide published July 2026.
- **Mexico**: a new **Federal Film and Audiovisual Act** retains the **10% national screen-time
  minimum** with stricter exhibitor enforcement and reportedly covers accessibility for visual and
  hearing impairments. **Enactment status is contradicted between sources and is flagged, not
  asserted.**

**A quota that was gamed and re-regulated inside twelve months is the strongest evidence a market
can give that the evidence trail is the product.** Nobody is selling it one.

## 63. The theatrical recovery is a price story, not an attendance story — in every region measured

The headline numbers look like recovery: global box office **$34.6bn in 2025, up 7%** (Futuresource),
2026 forecast ~**$34.55bn** (Gower Street, revised down from $35bn). Underneath, attendance is
falling almost everywhere:

- **Europe**: admissions **down 5.3% to 863.6m** (UNIC) while box office held **stable at €6.9bn**.
- **LATAM**: revenue **+9% to $2.65bn** for 2026 while **admissions fell 8%** in 2025.
- **China**: industry revenue **+6.6% to $7.9bn** in 2026 while the **business count has shrunk at a
  0.7% CAGR since 2021**, and box office is forecast **down 5%**. Omdia's reading is structural —
  young audiences leaving for cheaper, more interactive uses of time.
- **India** is the exception that proves the dependency: growth is real, and **~90% of it is national
  titles.**

Every one of those gaps is price, premium formats and mix. The commercial reading for a studio is
that **yield management and title-supply analytics are the live questions**, and the open estate for
both is 103 repositories of 2017–2020 coursework summing **29 stars**. One caution on citation: UNIC
reports 863.6m admissions and the European Audiovisual Observatory reports 796m **for the same
year**, because their territory coverage differs. **Cite the body, not the number.**

## The description & semantic-interchange plane — trends measured 2026-11-26 (pass 11)

### T1. The structural law meets its control case, and survives in a sharper form

Ten passes found planes with no agent layer because the knowledge content was licensed shut. This
plane is the first where **the knowledge content is openly licensed**: IPTC's own repository states
that "the Creative Commons Attribution (CC BY) 4.0 license applies to all NewsCodes", and NewsML-G2's
grant explicitly permits building on it "even commercially". The prediction was a healthy plane. The
measurement is a **three-step gradient**:

| Layer | Problem type | State | Evidence |
|---|---|---|---|
| **DESCRIBE** with a standard | Format | **HEALTHY** | schema.org 6320★ Apache-2.0; ninjs MIT; NewsML-G2 CC BY 4.0; EBUCorePlus MIT; Skosmos 269★ MIT; TemaTres 142★ — IPTC pushed 6 repos in Nov 2026 |
| **ASSIGN** the right term | Judgment | **ONE REPO DEEP** | Annif, 280★, Apache-2.0, from a national library. `subject indexing` ranks 2-6 are unrelated 2014-era noise |
| **AGENTIC** cataloguing at scale | Judgment at scale | **PAPERS, NOT CODE** | arXiv 2504.05711 and 2605.16338; `archival metadata LLM agent` = 8 results, top-6 star sum **3**; the one live repo is 3★ and unlicensed |

**The refinement, which is new:** an open licence on the *schema* unblocks the format layer and
leaves the judgment layer untouched — because judgment is trained on **annotated records**, and those
are the asset institutions keep. Proof inside a single organisation: `NatLibFi/Annif` is Apache-2.0
and `NatLibFi/Annif-corpora`, the labelled training data without which it assigns nothing, **has no
licence file at all.** The withheld layer did not disappear; it moved down one level.

### T2. Standards-body openness does not propagate to the repo level

IPTC licenses its flagship standards CC BY 4.0 and ships MIT code — and **three of its twenty public
repos have no licence file**: `sport-schema` (38★), `rightsml-dev`, `json-for-concepts-vocabularies`.
Control requests pass, so the filenames are not at fault; the grant is simply absent, and default
copyright applies. Same trap as `rslstandard/rsl` in pass 8, now found *inside* a permissive org.
**Audit the repo, never the organisation's reputation.**

### T3. The successor is free and the installed base is NonCommercial

**EBUCore** (EBU Tech 3293), the descriptive/technical metadata spec most European broadcasters have
actually deployed, is **CC BY-NC-SA 3.0 — NonCommercial**. **EBUCorePlus**, its successor, is **MIT**.
A client's commercial usability therefore depends on *which generation of the standard they are on* —
and the unusable one is the widely installed one. Second occurrence of a predecessor/successor licence
split in this KB; treat it as a pattern and ask the version question before scoping.

### T4. 2026 is the year media AI moved from adoption to accountability — which is a metadata problem

Akamai: AI adoption "is no longer the question"; the challenge is converting experimentation into
business value. TV Tech calls 2026 the year of **scaling** AI through the media enterprise while
expecting "several false starts" in agentic deployments. EY: the question moved from whether to adopt
to **how to apply it responsibly**. Every one of those framings cashes out as description work —
you cannot audit, attribute, retrieve or report on assets that carry no structured description. The
EUIPO's 2026-05-28 mapping study put an institutional number on the same defect: the lack of
interoperability between copyright-related metadata standards "triggers major inefficiencies."

### T5. Structured data is now load-bearing for discovery — and the causal evidence does not exist

Contently reports **25.11% of Google searches triggered an AI Overview in Q1 2026**, and AlphaSense
notes AI Overviews often reference news publications while sending **fewer clicks** to the source.
Against that, Search Engine Land states there are **no peer-reviewed studies** on schema markup's
effect on AI search visibility or LLM citation behaviour. **Sell structured-data correctness as
hygiene and risk reduction, never as a ranking guarantee** — and note the reported finding that stale
or inaccurate structured data is *more* harmful than missing markup, which makes accuracy the
deliverable rather than coverage.

### T6. The retrieval bottleneck is description, and it is why "AI over the archive" stalls

Every vendor framing of the MAM market now describes AI automating "metadata tagging, content
indexing, quality control and rights management" (Coherent) and archives becoming "intelligent
workflow orchestration hubs" (Technavio). The honest engineering read: retrieval over an archive is
impossible where assets carry no description, so **the first deliverable of any archive-AI programme
is a description backfill, not a model**. ABC (Australia) is the clearest production case — Gemini
2.0 Flash via Vertex AI generating descriptive metadata, integrated directly into the content
pipeline — and the gap it leaves open is auditability against a controlled vocabulary, which is
exactly what Annif or GLiNER constrained to a client thesaurus provides.

### T7. The institutional open-source base for this plane is European and public, not commercial

INA (France), the National Library of Finland, and the EBU maintain the tools; the EU funds the data
space (TEMS, 2023-**2026**, concluding this year); the EU Publications Office runs the vocabulary
platforms. No North American or APAC media company maintains a comparable public cataloguing stack.
The one notable non-European exception is **LATAM**: TemaTres, Argentine-built, 142★, pushed the day
before this pass. For Globant this inverts the usual regional story — in this plane, LATAM has a
reference implementation to lead with rather than import.

### T8. Copyleft dominates the systems tier, with IIIF as the single permissive escape hatch

Every purpose-built open newsroom and cataloguing system is AGPL or GPL: Superdesk AGPL-3.0,
CollectiveAccess GPL-3.0, Omeka S GPL-3.0, VuFind GPL-2.0, Islandora GPL-2.0, TemaTres GPL-2.0.
The permissive options are the *repository and delivery* tiers — Dataverse Apache-2.0, DSpace BSD-3,
Blacklight Apache-2.0, Fedora Apache-2.0 — and **IIIF, where three of four components (Mirador
Apache-2.0, Universal Viewer MIT, Cantaloupe NCSA) are permissive and all four were pushed within six
days of this pass.** If a client refuses AGPL for a hosted service, there is no open newsroom CMS for
them, and the honest answer is Wagtail (BSD-3) plus custom workflow.

## Sound, music & immersive audio — added 2026-11-26 (pass 12)

### 1. Immersive audio stopped being a differentiator and became a deliverable requirement

SMPTE's March 2026 position is that immersive sound is "table stakes" rather than a premium feature,
and the 2026 delivery calendar is what made it so: NBC carried the **2026 Winter Olympics and the
Super Bowl** in Dolby Atmos on Peacock, **Brazil's DTV+** demonstrated MPEG-H as a core feature at
CES 2026, and the **FIFA World Cup 2026** is the next milestone across both broadcast and OTT. The
**ATSC 3.0 suite approved on 2026-04-14** standardises MPEG-H audio for North America.

**The consequence this KB can measure:** demand is now contractual, and the open supply is the EBU's
ADM stack — whose normative renderer has **105 stars**. The encoder side (MPEG-H) is Fraunhofer's and
is not open. Teams will meet an immersive deliverable with proprietary tools or with a 105-star
reference implementation; there is no third option today.

### 2. The licence constraint in audio is positional, not ideological

The finding of this pass, stated as a trend because it is a stable property of the market: code that
runs **beside** a proprietary host stays permissive (7/7 measured), code that must run **inside** one
is dual-licensed or copyleft (6/6 measured, no exception). Plugin frameworks sell exceptions because
their customers ship closed plugins. Expect this to hold wherever a plane's deliverable is an
in-process extension of someone else's product — it is the most portable prediction this KB has made.

### 3. The restriction keeps migrating to the weights — now found inside a single licence file

Pass 9 recorded the licence moving from the code into the model. Pass 12 adds the sharpest instance:
`madmom` ships **BSD source and CC BY-NC-SA 4.0 models in one `LICENSE` file**, naming pickled
Processors explicitly. No repo-level scanner, directory or awesome-list can see a split that lives in
the prose of a licence file. **Licence due-diligence that stops at the repository badge is no longer
sufficient in the model era** — and this is now the third independent confirmation across three
planes.

### 4. Revenue-threshold licences have arrived in media models, and they are written at service firms

`fish-speech`'s **Fish Audio Community License v1.0** (2026-10-13, 33,872★) caps free commercial use
at **USD 500,000 annual revenue** and writes explicit rules for *"contractor, integrator, consultant,
or on-premises vendor"* delivery — extending the licence to that work only if **the client** is also
under the threshold, while carving out agencies that deliver finished audio. This is a licence drafted
with systems integrators in view. Expect more of them: it lets a model vendor court the open-source
community while charging exactly the enterprises a studio sells to.

### 5. Voice is the most-regulated AI modality in media, and the rules diverge sharply by region

Synthetic voice now carries real statutory exposure, and — unusually — **the strictest sector-specific
law is in LATAM, not North America or the EU.** Mexico's decree (DOF **2026-05-14**, in force the
following day) requires express consent and specific remuneration to clone a performer's voice or
image, and introduces *"actor de doblaje"* as a legal concept. See `intel/market.md` for the regional
breakdown. The practical effect: **voice is the one AI capability where the legal review must precede
the technical pilot**, and where the answer differs per market.

### 6. The agent layer is absent for the twelfth consecutive plane — and here the vocabulary hides it

`audio post production agent` returns **six repositories in all of GitHub**, top-six star sum **7**.
But the more useful observation is *why the absence is hard to see*: audio's vocabulary is homonymous
with agent vocabulary. "Supervision" means music clearance to a studio and sub-agent routing to a
framework. "Dialogue" means production sound to post and conversation to AI. A casual search returns
plausible-looking, well-starred repositories from entirely different domains — which is how a plane
this empty can appear populated.

### 7. AI dubbing is growing fast and the market sizing is unusable without a named scope

Six firms, same year, for overlapping definitions: **USD 52m** (Intel Market Research, AI video
dubbing), **USD 600.8m** for 2025 (Astute Analytica), **USD 750m** (Mordor, AI dubbing for OTT),
**USD 1.15bn** for 2025 (The Business Research Company, AI dubbing tools), **USD 5.29bn** (Mordor,
generative AI in media localisation). CAGRs cluster **17-31%**. That is a **greater than 100× spread**
between the narrowest and widest scopes — wider than pass 11's 3.7× MAM spread, and the same lesson:
**never quote a dubbing figure without naming the firm and the scope.** Mordor also notes quality
still limits AI dubbing in premium scripted work, which is the honest ceiling on the pitch.

## The subscription, entitlement & reader-revenue plane — trends measured 2026-11-26 (pass 13)

### 1. The licence hardens as the code approaches the money — the cleanest gradient in this KB

Pass 12 found a licence gradient ordered by *whose process the code runs inside*. This plane's is
ordered by **distance from the recurring charge**, and it is monotone with no counterexample:

| Layer | What it decides | Licence shape |
|---|---|---|
| Identity | who are you | Apache-2.0 (Keycloak 38,060★) |
| Entitlement | what may you watch | Apache-2.0 (SpiceDB 7,243★, OpenFGA 6,197★, Cerbos 4,669★) |
| Billing | the recurring charge | **AGPL-dominant** (Lago 10,922★, flexprice 6,874★, Meteroid 1,370★) |
| Reader revenue | the conversion funnel | **one MIT repo at 138★** (REMP) |

Authorization is treated as infrastructure and given away. The recurring charge is treated as the
business and protected. **This is the thirteenth plane measured and the first in which the licence
outcome is predicted by proximity to revenue rather than by layer or by runtime.**

### 2. The open-source `paywall` ecosystem is adversarial, not absent — a 156 : 1 ratio

Trend 28 recorded that watermark *removal* is a 10× larger open-source movement than watermarking.
This plane is the same shape, four times more extreme, and it attacks a revenue model rather than a
compliance artefact. `topic:paywall`, top ten by stars, 2026-11-26: **ten of ten are circumvention
tools, totalling 21,592 stars.** The one publisher-side implementation in the same measurement has
**138**. And **`topic:reader-revenue` returns zero repositories** — the topic does not exist.

The practical consequence for a pitch: a media client asking "what does open source offer us for
subscriptions" is asking about an ecosystem whose most popular, most actively maintained artefacts
are built to **defeat** them. That is not a reason to avoid open source here; it is a reason to sell
funnel resilience, and the evidence is public and verifiable in under a minute.

### 3. Four regulators, four different instruments, and for the first time they target the *transaction*

Every previous plane in this KB was regulated on its **content** — labelling, accessibility,
provenance, age-gating. This plane is regulated on the **contract**:

| Region | Instrument | Status as at 2026-11-26 |
|---|---|---|
| **EMEA (UK)** | Consumer Subscription Contracts (Cancellation and Information) Regulations 2026 under the DMCCA | Draft **laid 2026-10-19**, **in force 2027-01-01**, contracts entered on/after only |
| **North America (US)** | FTC Negative Option / "click-to-cancel" | **Vacated 2025-07-08** on procedural grounds; ANPRM March 2026; **no replacement rule**; ROSCA + §5 enforcement continues |
| **LATAM (Mexico)** | LFDA + LFT amendments; separate audiovisual law | **Published 2026-05-14** and **2026-05-22**; VOD platforms in scope |
| **LATAM (Brazil)** | Streaming regulation bill | In Senate; SVOD services contesting tax provisions |
| **APAC** | — | **No regional regime found by this pass** — stated as an evidence gap, not a finding of absence |

**The UK and US have inverted postures, and that is the sellable insight.** The UK specifies the
artefact and dates it. The US specifies nothing and enforces anyway. A client operating in both
cannot satisfy them with one design: the UK build is a *calendar* (reminders, dual cooling-off
clocks), the US build is an *evidence log* (what was disclosed, when consent was captured, how many
steps cancellation took).

### 4. The UK renewal cooling-off right lands in the billing scheduler, not the marketing site

Worth isolating because it is the clause most likely to be mis-scoped. The DMCCA regime as drafted
gives consumers **two** 14-day cooling-off periods: an initial one at sign-up **and a new one at
certain renewal payment dates**. A sign-up-time consent checkbox does not discharge it. It is a
recurring, date-triggered obligation on every qualifying renewal — which means it is owned by
whatever runs the renewal cron, and **no open billing platform implements it**: not Kill Bill, not
Lago, not REMP.

### 5. Growth stopped being the lever, and the four levers that replaced it are all unserved

Omdia puts 2026 online subscription growth at **6.7%**; AlixPartners puts global OTT growth at **5%**
and reports that the major streamers now optimise for profitability, engagement and ARPU rather than
subscriber count. The levers that remain are retention, involuntary churn, plan mix and ARPU — and
the open-source estate implements **none** of them: no churn system for media, no dunning agent
(57 repos, nothing above 200★), no model of ad-tier/paid-tier switching, no media entitlement schema.
The industry's own analysts have named the four things that matter, and the shelf is empty.

### 6. The agent layer is absent for the thirteenth consecutive plane — and here the vocabulary inverts

The contamination pattern is now precisely characterised. **Generic** terms return tens of thousands
of stars of general-purpose agents with no connection to media revenue (`billing agent` → agenticSeek
27,701★; `subscription agent` → Paradev 16,696★). The **precise** term — `dunning`, which cannot mean
anything else — returns **57 repos and nothing above 200 stars**. Both measurements describe the same
absence; only the second one is honest about it. **The rule for future passes: when the generic query
is contaminated, find the industry's own unambiguous word and measure that instead.**

### 7. The licence tracks the business model, not the layer — the sharpest form of this KB's law

`verticals/solutions.md` has held since pass 2 that open source is "permissive at the library,
copyleft at the platform". This plane breaks it at two platforms, and both breaks have the same
explanation. **Kill Bill (Apache-2.0) and Ghost (MIT)** are full platforms under permissive licences;
both monetise through a hosted service run by the project's own company, so their moat is operations
and they lose nothing by permissive licensing. **Lago and flexprice (AGPL-3.0)** sell the same
software they publish, so copyleft is what makes self-host-and-resell unattractive. The layer does
not predict the licence; **the business model does**.

### 8. Directus's licence has a professional-services clause, and a four-year fuse

The Monospace Sustainable Core License v1.0 (`MSCL-1.0-GPL`), read in full at 4,481 bytes. Three
facts no licence scanner will surface, because there is no SPDX identifier to report:

1. The **only** prohibition is Competing Use — reselling a hosted Directus against the licensor's own
   paid offering. It is a non-compete, not a general commercial restriction.
2. Permitted Purposes **explicitly include** use "in connection with professional services that you
   provide to a licensee". **For a services firm this is the decisive clause, and it permits the
   work** — provided the client's own use is itself permitted (internal use is listed).
3. A **Grant of Future License** makes each version **GPL-3.0 on its fourth anniversary**. Directus is
   delayed-open on a four-year clock, and the destination is **copyleft** — it never becomes
   permissive. A version adopted today is GPL-3.0 in 2030.

### 9. A licence can be a directory path — the pattern is now three-for-three

PostHog (`ee/`), GrowthBook (three `enterprise` directories) and SuperTokens (`ee/`) all report
`NOASSERTION` on GitHub and all are MIT-except-a-path. This is no longer an anecdote; it is how
open-core projects now express themselves. **The answerable question is not "is it MIT?" but "does my
build import anything under that path?"** — a dependency-graph question, not a licence-scan question,
and the tooling most firms run answers the wrong one.

### 10. LATAM's subscription funnel is under the most active circumvention pressure measured

Of the top ten `topic:paywall` repositories, the two largest non-English projects target the
**Brazilian** press — `marreta` (GPL-3.0, 1,229★) and `burlesco` (MIT, 948★) — and both were pushed
**this month**. The third-largest non-English project targets the **German** press (`bibbot`, 656★).
No other region measured carries comparable, currently-maintained circumvention tooling aimed at its
own national press. For LATAM engagements this converts an abstract "paywall resilience" pitch into a
demonstrable one.

## The localization & translation-management plane — trends measured 2026-11-26 (pass 14)

### 64. The job format is maintained; the asset format is abandoned — and the asset is what the client owns

This is the finding to lead a localization conversation with, because it is a measured fact and it
reframes the purchase.

Translation runs on two interchange formats from the same standards lineage. **XLIFF** carries *this
week's job* out to linguists and back. **TMX** carries the *translation memory* — every segment the
client has ever paid to have translated, accumulated over a decade.

| | Carries | Best maintained open tooling | State |
|---|---|---|---|
| **XLIFF** | this week's work | `vslavik/poedit` MIT **2,061★**, pushed 2026-11-09 | Healthy, permissive, boring |
| **TMX** | ten years of paid output | `bitextor/bitextor` GPL-3.0 302★, pushed **2024-11-11** | **Dead.** Nothing above 17★ is alive |

The full TMX estate, by stars: `302 (dormant) → 17 → 12 → 8 → 7 → 6 → 6 → 4`.

Why it matters commercially: **the translation memory is the client's switching cost.** It is the one
asset that determines whether they can leave their current localization vendor, and the only
multilingual corpus they own outright — including for training. There is no maintained open tool to
read it, merge it, dedupe it, or audit it for quality. Whoever reconstructs that asset owns the
account, and nobody is competing for the job.

### 65. Split "translation quality" by who signs the number, and the open estate splits 1,000:1

The law this KB has recorded across six industries — *format problems get maintained code, judgment
problems get none* — was measured this pass **inside a single discipline**, which is the tightest
control case yet. All four rows are Apache-2.0 or MIT, so licence is not the variable. Only the
nature of the judgment is.

| Kind of quality | Who has to agree | Repos | Stars | Alive? |
|---|---|---|---|---|
| Computable from text | nobody — it is arithmetic | `mjpost/sacrebleu`, `Unbabel/COMET` | **2,058** | Yes (2026-08, 2026-04) |
| Predicted without a reference | a model | `Unbabel/OpenKiwi`, `NJUNLP/njuqe` | 248 | **No** (OpenKiwi dead 2022-06) |
| **Contractual (MQM typology)** | **the buyer and the vendor** | `BYU-TRG-Team/mqm-scorecard` + its API | **2** | Barely (2025-06) |

MQM is not academic: it is the error typology that commercial localization contracts and SLAs are
actually written against. The open implementation is **two repositories at one star each, from a
single university team.** Meanwhile the metric a machine can compute unaided has a thousand times
the investment. The scarce thing is never the computation; it is the agreement.

### 66. GitHub-only discovery cannot see this industry's incumbents — a method defect, not a market fact

Two of the most important tools in this plane are **not on GitHub at all**:

- **The Okapi Framework** — the standard open filter/segmentation toolkit that converts ~50
  proprietary formats into XLIFF — is on **Bitbucket**. `okapiframework/okapi` was the only failure
  in the first 35 `ls-remote` checks. GitHub holds three satellites, the largest at 7★.
- **OmegaT**, the most widely used open-source CAT tool, is a **SourceForge** project. GitHub returns
  only plugins (41★, 30★) and name collisions.

Thirteen prior passes of this KB, and every pass of the other eleven industries, used GitHub-shaped
discovery. That method has a blind spot shaped exactly like **mature, pre-2010, standards-implementing
open source** — which is disproportionately where industrial standards tooling lives. The correction
is cheap: *when a plane has an obvious incumbent and the sweep does not return it, check another
forge before concluding absence.*

### 67. The restrictive licence is in the wrapper, and the engine underneath it is MIT

`LibreTranslate` (AGPL-3.0, 17,851★) is the self-hosted MT API the whole market names. Its own
`pyproject.toml` pins **`argos-translate-lt==1.12.1`** — and `argosopentech/argos-translate` is
**MIT** (6,696★, pushed 2026-11-17).

So the network-copyleft obligation lives in the API server, one layer above an engine that has none.
This is the **mirror image of pass 12's Chromaprint finding**, where a permissive repo was hardened
by its GPL/LGPL dependencies. Both break the same lazy assumption — that a project's licence
describes the stack. Here the direction of the error is in Globant's favour, and it is worth real
money: the same translation capability is available without AGPL §13 duties by building one layer
lower. ⚠️ The pinned fork ships via **PyPI** with no resolving GitHub repo, so confirm *its* licence
on the published artefact before shipping.

### 68. Name collisions in this plane are severe enough to fabricate a table

Pass 8 recorded `eidr` (160 results, zero relevant) and `isan` (1,942, zero relevant). This plane is
worse, because the collisions are *high-star and plausible*:

- **`localization platform`** → rank 1 is **`cartographer-project/cartographer`, 8,021★** — robotics
  SLAM. "Localization" means *knowing where the robot is*.
- **`omegat`** → rank 1 is `THE-OMEGATHREAD`, 392★, a piracy-megathread list; rank 3 `omegatube`.
- **`translation memory`** → rank 2 is `dlbeer/dhara`, 508★, a **NAND flash translation layer**.

A pass that read result counts instead of results would have written robotics and flash-memory repos
into a media localization table. **Read the descriptions. The count is not the finding.**

### 69. What the mandated generic searches returned this pass: nothing media-specific

Recorded so the silence is not mistaken for coverage. The four required global queries
(`top open source AI agents media 2026 github MIT`, `github trending media AI 2026`,
`open source platform media ERP CRM MIT Apache`, `AI media industry trends 2026`) returned, at this
point in the rotation, **general-purpose agent-framework roundups** (OpenHands, browser-use, DeerFlow,
LangGraph) and vendor outlook PDFs — nothing media-specific that fourteen passes had not already
covered. Two useful confirmations only: Akamai's *State of AI in Media 2026* reports time spent in
generative-AI apps **doubled between H1 2025 and H1 2026**, and the sector's own commentary (TV Tech,
TVBEurope) now frames 2026 as scaling and "agentic", with several false starts expected.

**The honest read:** generic industry queries have saturated for media. Value now comes from naming
an unexamined plane and measuring it, which is what this pass did. The generic sweep should be
treated as a cheap regression check, not as a source of findings.

## The out-of-home, signage & retail-media plane — trends measured 2026-11-26 (pass 15)

1. **Retail media is colonising physical space, and in-store screens are where the growth is.**
   In-store DOOH is forecast to drive **~56% of total DOOH growth between 2025 and 2029**. Retailers
   are extending their media networks into DOOH with programmatic creative that reacts to local
   conditions such as weather. *(Vendor forecast — directional, not measured.)*
2. **Programmatic is becoming the default buying mode, not the innovation.** US programmatic reached
   **24% of DOOH spend in 2024** and is projected at **65% by 2029**; one trade report has US
   programmatic DOOH spend rising **49%** as budgets shift. Global programmatic DOOH was
   **US$1.339B in 2025** (World Out of Home Organization — the most credible figure found this pass).
3. **AI's real effect is on the sell side, not the creative.** The most defensible argument found is
   that AI's largest DOOH impact is **matching inventory to demand** — real-time pricing and yield
   control for media owners — rather than generating artwork.
4. **The "25% of campaigns planned by AI agents in 2026" figure is a prediction with no traceable
   method.** It recurs across vendor posts and originates in a guest article. **Do not put it in a
   client deck as measured.** Recorded here specifically so a later pass does not relaunder it.
5. **Measurement is the stated blocker across every region.** Buyers want DOOH measurement comparable
   to Meta and Amazon. The IAB's **July 2025 DOOH Measurement Guide** set shared standards, but
   adoption is early-stage — and the open-source measurement spec has been **dormant since 2021 and
   carries no licence** (see `agents/top.md`). The standard exists on paper; the implementation does
   not exist at all.
6. **Platform consolidation is the trade-show theme.** DMEXCO and IDOOH World 2026 produced three
   recurring themes: consolidation, retail media becoming central to DOOH sales, and measurement
   catching up.
7. **Self-serve is opening DOOH to local advertisers.** Lower entry barriers are bringing convenience-
   store and ATM screens into the addressable pool — which multiplies the number of screens needing
   cheap, permissive playback software, the one layer open source already serves well.
8. **Sustainability is becoming an EMEA procurement criterion.** Media owners are scoring screens for
   energy use and reporting real-time emissions. This is a *requirement* that favours efficient
   players — and is a direct argument for `flutter-pi` (MIT, KMS/DRM, no desktop stack) over a
   full-browser player on the same hardware.
9. **The agent layer is forming as vendor adapters.** See the measured table in `agents/top.md`: of
   14 `signage mcp` repos, the identifiable ones bridge to closed SaaS CMSs. The window to define a
   neutral abstraction is open **now** and will close as those adapters accumulate users.

## The avails, windowing & distribution-rights plane — trends measured 2026-11-26 (pass 16)

### The industry-wide framing for 2026, and why this plane contradicts it

The analyst consensus for 2026 is that adoption is settled and value capture is the open question.
Akamai's *State of AI in Media 2026* puts it as: AI adoption is no longer the question; the challenge is
turning widespread experimentation into business value. TVBEurope's year-ahead roundup calls 2026 "very
much the era of agentic AI". TV Tech predicts the generative "shiny object" phase gives way to scaling
across the enterprise, with **several false starts in agentic advertising** and creative production as
the first genuine breakthrough. Deloitte's 2026 outlook links more than half its predictions to AI.

**This plane inverts that framing, and the inversion is the finding.** Here the agent layer did not
mature — it was *born*, all at once, in 2026-Q3/Q4, and has **zero users**. Six rights-clearance agents,
every one created between June and October 2026, every one still at 0 stars except one at 3. "Agentic AI
is scaling" is true of production and advertising; in rights it is not yet true of a single repository.

### Three trends with evidence, and one measured non-trend

**1. Clearance is being attacked from the research end, not the decision end.** All six 2026 agents do
*discovery* — scan a screenplay, scan a trademark register, derive a cue sheet from an EDL. None makes
an availability decision and none computes a payment. That is consistent with where LLMs are actually
strong, and it predicts where the open layer will keep stopping: judgment steps that carry liability.

**2. Content identification standards keep arriving without implementations — and 2026 added another
instance.** Pass 5 established that ISRC, ISWC, ISAN, EIDR and CWR have no usable open implementation
because what is scarce is *registry assignment*, not parsing. This plane adds the distribution-side
proof: the **EMA Avails** interchange has four open implementations and **three of the four are dormant**
(2016, 2017, 2023). The one maintained authoring tool found (`UltimateAvailMaker`, pushed 2026-11-12) has
**no licence**. Standards activity and code activity have decoupled in this plane for a decade.

**3. The regulatory direction of travel is toward catalogue composition as a measurable duty.** EMEA
already requires it (AVMSD Art. 13, ≥30% European works, counted by title and enforced per national
catalogue). Brazil's PL 8.889/2017 would add a ~10% national quota. Both turn "what is in my catalogue,
by territory" from a commercial question into a **reportable** one. That is the trend most likely to
create budget in this plane, because a report is a deliverable with a deadline.

**4. The measured non-trend: settlement.** `residuals calculation film` = **0 repositories**.
`film royalty statement` = **1**, off-topic. Pass 8 measured the music half of the same hole
(`music royalty accounting` = 14 results, top six summing to **0 stars**). Two passes, two years of
GitHub, and the film/TV settlement layer has produced nothing at all. There is no emerging trend here to
watch; there is an absence to stop re-checking hopefully. If a client needs residuals, that is bespoke
work, and this KB should say so in the first meeting.

### What to watch, with dates

- **The French `chronologie des médias` litigation.** Windows are statutory in France and tiered by
  investment commitment; Netflix and Prime Video have gone to court seeking alignment to 12 months. The
  current month values are **disputed across sources** (see `intel/market.md`, EMEA). A resolution would
  be the first court ruling anywhere on a *legally mandated* release window, and it either entrenches or
  dismantles the only jurisdiction where a window engine must encode statute rather than contract.
- **Brazil's PL 8.889-C/2017 in the Senate.** Approved by the Chamber of Deputies 2025-11-05. Enactment
  would make LATAM the second region with a machine-checkable catalogue-composition duty.
- **The Commission's AVMSD evaluation.** Industry submissions on revising Art. 13 are in (CCIA,
  DIGITALEUROPE arguing for technology-neutral horizontal rules instead of sector-specific expansion);
  no outcome confirmed. A revision changes the counting method, which changes every compliance report
  built against it.
- **`survos/omc`** — created 2026-11-24, MIT, OMC 2.8 DTOs. One day old when measured. If it is alive in
  three months it is the first new permissively-licensed entrant in this plane since 2023.

## The development & pre-production plane — trends measured 2026-11-26 (pass 17)

### 1. The structural law holds for a sixth time, and this pass found the version that **removes the leverage**

The law as formulated in pass 5 and refined through pass 11: *declaring* something is a format problem and
gets permissive, maintained code; *honouring* it is a judgment problem and gets dormant code; *settling*
the money is pure judgment and gets nothing. Pass 17's gradient, inside one workflow:

| Step | Nature of the problem | What exists | Measured |
|---|---|---|---|
| **WRITE** the script | format | `nyousefi/Fountain` MIT **690★**, `betterfountain` MIT **454★**, `screenplain` MIT **187★**, `screenplay-tools` MIT 29★ | Healthy, permissive, maintained |
| **BREAK DOWN & SCHEDULE** | judgment | `OpenShotDesigner` GPL-3.0 47★, `CineSched` GPL-3.0 15★, `FilmOrganizer` MIT 1★, `method-scheduling` Apache-2.0 1★, `opengate` GPL-3.0 1★, two unlicensed at 0★ | **73★ across eight repos** |
| **SETTLE** the money | pure judgment | `CineSpend` MIT 8★; residuals/payroll **0** | Effectively nothing |

**But the consequence inverts, and this is the new part.** `intel/trends.md` trend 4 has said since pass 1
that M&E open source is "permissive at the pipeline, copyleft at the platform", and everywhere else in
this KB that is *good news*: the permissive layer is the valuable substrate (codecs, colour, OTIO, ASR)
and the copyleft layer is a replaceable turnkey app. **Here it is the reverse.** The permissive layer is a
plain-text parser — a weekend of work, and eleven of them already exist. The layer carrying all the domain
knowledge, the one a production office actually pays for, is GPL-3.0, proprietary, or absent.

**So the law is structural, not commercial.** It predicts *where* permissive code appears; it does not
promise that the permissive code is worth having. In this plane the permissive licences sit on the
cheapest asset in the pipeline. **Refinement to carry forward: before valuing a permissive layer, ask
what it would cost to rewrite. If the answer is "a weekend", the licence is not leverage.**

### 2. The money follows the restriction — now with a ratio

Across this plane's agent layer: **15,261 stars on the source-available-or-unlicensed side** (`waoowaoo`
ELv2 14,989★, `film-studio-skills` unlicensed 186★, `motion-graphics-skills` all-rights-reserved 69★,
`script-weaver` unlicensed 11★, `Script-Breakdown-Skills` unlicensed 6★) against **301 stars on the
permissive side** (`story-shot-agent` 248★, `how-to-make-script` 21★, three others at 10–11★). A **50:1
ratio**, and the split is not random: every permissive agent generates *story*, every restricted one
claims to run a *production*. Pass 13 observed the licence hardening as it approaches the money; pass 17
measures the same gradient inside a single workflow.

### 3. A regulator has produced a duty with no supply anywhere — the first clean case in the KB

Eleven passes have concluded that regulatory pressure does not predict permissive supply, and that the
correlation is often inverse. Mexico's reform (in force **2026-05-15**) is the first instance of
something stronger: a **dated, sector-specific, labour-side consent duty** — express consent per purpose,
revocable, surviving the contract, extending to AI *training* on a worker's voice or image, naming dubbing
actors explicitly — whose **system of record is the production office**, a layer with **73 stars of open
tooling in total**. Not copyleft supply. **Absent supply, against an enacted duty.** That is the
cleanest build case this KB has recorded, and the inversion is worth watching for in the other eleven
industries.

### 4. The format layer is moving this week; the management layer is being born 0-star

Seven of fourteen tracked repos pushed within ten days of measurement (`story-shot-agent` and
`visual-storytelling-skills` **on** measurement day). But **five of the eight management-tier repos were
first pushed within the last ten weeks** and sit at 0–1 stars with licences ranging from Apache-2.0 to
nothing at all. That is the signature of freshly generated single-author projects, not an emerging
ecosystem. **Do not read "eight repositories appeared this quarter" as momentum** — read the stars, the
forks and whether a second contributor ever arrived. `method-scheduling` (Apache-2.0, 1★/1f) is the one
worth a revisit next pass, on licence and scope rather than traction.

### 5. The measured non-trend: the stripboard has no digital commons, and its name is taken

`stripboard` returns **112 GitHub repositories and not one is about film.** They are modular-synthesizer
perfboard layouts and PCB autorouters. The stripboard — the board of coloured strips that *is* the
shooting schedule — is the central artefact of production planning, and on GitHub the word belongs
entirely to electronics. Meanwhile every artefact downstream of the script (stripboard, day-out-of-days,
call sheet, budget top-sheet) exists only in proprietary formats, while **the one open interchange format,
Fountain, sits upstream of all of them.** There is no trend to track here and no pipeline to watch: there
is an absence, and the correct response is to stop re-checking it hopefully and price the build.

---

## Trends in the book, ebook & scholarly-publishing plane — measured 2026-11-26 (pass 18)

### 1. Accessibility stopped being a virtue and became a market-access condition — but only in EMEA

The European Accessibility Act (Directive (EU) 2019/882) has applied to ebooks sold in the EU since
**28 June 2025**, with a transition for backlist titles reported as running to **June 2030**. The
technical baseline cited across guidance is **EN 301 549** (V3.2.1, based on WCAG 2.1 AA; **V4.1.1
published September 2026** aligning with WCAG 2.2) together with **EPUB Accessibility 1.1**. Two
requirements recur and both are machine-checkable: accessibility features must be **discoverable in
metadata**, and **DRM must not switch them off**.

The commercial mechanism matters more than the penalty: a non-compliant title risks **removal or
suppression from EU storefronts**, which does not require a regulator to act. That is why this is a
trend and not a compliance footnote — the enforcement is retail, not judicial.

**Contested, and recorded as contested:** one source claims a first EAA court ruling in **June
2026**; another reports that after fourteen months **no publisher, bookseller or ebook platform had
been fined or sued** over ebook accessibility. Neither was verifiable against a primary source in
this pass. Penalties are set per member state, so there is no single EU sanctions regime, and one
tracker notes there is **no EU-wide enforcement dataset** and the Commission's first review is not
due until **2030**.

### 2. The open-source answer to that duty is permissive — the first time in this KB that the regulated layer is the free one

`w3c/epubcheck` is **BSD-3-Clause** and `daisy/ace` is **MIT** (both verified from their licence
files, 2026-11-26). The validation layer under a statutory duty carries **no copyleft obligation**.

Every comparable finding in this KB ran the other way: healthcare's pharmacovigilance duty sat
behind a paid MedDRA licence; AV conformance sat behind GPL `MediaConch`; US coding sat behind CPT.
Here the regulator created a duty and the standards body published the checker permissively. **The
reason is the producer: DAISY and W3C exist to make the format spread, and a toll would defeat
that.** It is the cleanest regulated-demand/permissive-supply pairing in eighteen passes.

### 3. AI adoption in book publishing is majority behaviour, and accessibility is one of its top uses

The BookNet Canada / BISG **2026** survey of the North American book industry found **63% of
respondents' organizations are using AI**. Among university presses (n=32) the leading uses were
administrative/operational (47%), marketing (44%) and **accessibility (44%)** — alt-text generation
in InDesign is given as a concrete example. At the same time **86% were concerned about AI accuracy
for consumers**, including difficulty distinguishing AI-generated from human-made work.

Remediation at scale is already demonstrated: **Elsevier reports completing remediation of over
8,000 of its most widely used ebooks as of May 2026**, adding accessible EPUB files and alt text.
That is the reference point for sizing a backlist programme — a real number from a real publisher,
not a vendor estimate.

### 4. Two regulatory clocks now overlap, and publishers are "deployers" under one of them

The **EU AI Act Article 50** transparency obligations — labelling of AI-generated content — took
effect **August 2026**, with Commission guidelines published **20 July 2026**. A publisher using
third-party AI tools in editorial work is generally a **deployer** under the Act, not a provider,
which is the lighter of the two roles but not an exemption. One guide notes that where AI-assisted
content has been reviewed and approved by a person with documented editorial responsibility,
labelling is not required — which turns **documented human editorial sign-off into a compliance
artefact**, and therefore into something a workflow has to record.

Sources disagree on the high-risk timetable (one says obligations became enforceable 2 August 2026;
another says EAA compliance becomes a legal requirement for high-risk AI providers only from
**December 2027**). Recorded as unresolved rather than picking a date.

### 5. Audiobook generation is the one genuinely hot open-source category in this plane

The most active AI projects measured are all ebook→audio: `DrewThomasson/ebook2audiobook`
(Apache-2.0, last commit 2026-11-24), `p0n1/epub_to_audiobook` (MIT, 2026-10-26, gained stars late
October 2026), `santinic/audiblez` (MIT, Kokoro-82M TTS). The driver is that **open TTS became good
enough** — and note the licence shape: these are **MIT and Apache-2.0**, i.e. the generative edge of
this plane is permissive while its platforms are copyleft.

### 6. The substrate is not legacy — 28 of 40 verified repos committed in November 2026

Including `pkp/ojs`, `calibre`, `edrlab/thorium-reader` and `internetarchive/openlibrary` all on
**2026-11-26 itself**. Any pitch that treats open publishing infrastructure as dormant is factually
wrong, and this is the measurement that refutes it.

### 7. The agent layer is almost entirely absent, and where it exists it targets PDF, not EPUB

Measured, not assumed. The only verified EPUB-aware agent is a **reviewer**
(`Community-Access/accessibility-agents`, MIT, 2026-11-07), not a generator. Everything generative
in document accessibility targets PDF: `CUNY-AI-Lab/pdf-accessibility-app` (AGPL-3.0), Equalify
Reflow (PDF→accessible Markdown), `AIScientists-Dev/AI-Powered-PDF-Accessibility` (no licence file —
see `agents/top.md`). The single EPUB-specific result was a paper, **"AltGen: AI-driven alt text
generation for enhancing EPUB accessibility"**, with no public code located. A 2026 case study found
in the same search argues there are **no mature open-source tools for end-to-end document
remediation** — consistent with what this pass measured independently.

**So the shape of the opportunity is: statutory EU demand, permissive validators, a documented
backlist precedent at 8,000 titles — and no generator.** The missing piece is the one Globant would
build.

### 8. Content-licensing pressure has reached physical books

A Japanese book distributor reportedly agreed to sell large quantities of books to an AI company;
the report, citing US court documents, describes AI firms buying physical books, **removing bindings,
cutting and scanning pages** to produce training data. A publishing expert quoted argues the legal
question of **resale rights** may matter more than the AI training use itself. Recorded as reported,
not verified — but the direction is the one every rights-holder conversation in this plane now
starts from.

## The sports-media plane — trends measured 2026-11-26 (pass 19)

### 1. The rights market peaks this year and is forecast to fall — the first falling number in this KB

The SportBusiness Global Media Report 2026 puts global sports media rights at a record
**$65.82bn in 2026, up 15% year on year**, and forecasts a **drop to $62.2bn in 2027**, then a
plateau rather than renewed growth. Nearly every market figure elsewhere in this KB points up and to
the right; this one does not, and it changes how to pitch. **The 2027 buying conversation is about
cost per hour of produced content, not about growth.** That is precisely the conversation automation
wins.

Note a genuine conflict between two credible sources, which this pass does not resolve: Ampere
Analysis projects streaming services' sports-rights spend **rising** to **$14.2bn in 2026** (from
$13.2bn in 2025), while SportBusiness projects the **total** falling in 2027. Both can hold —
streaming taking share of a shrinking whole — but no source states that explicitly, so it is flagged
rather than asserted.

### 2. Prime Video displaces DAZN at the top of streaming sports spend — first time since 2018

Ampere expects **Prime Video ranked first** for sports-rights spend in 2026, ending DAZN's lead in
every year since 2018. A platform shift of that size at the top of the spend table is a procurement
signal: the incoming leader is an AWS-native buyer with its own ML stack, which raises the bar on
what an integrator must bring beyond raw model capability.

### 3. Automated highlights have shipped; automated commentary and direction have not

This is the clearest adoption line in the plane, and the asymmetry is the useful part:

| Capability | Status 2026 | Evidence |
|---|---|---|
| Automated highlights / clipping | **Shipping in production** | Spiideo launched AI Highlights in Spiideo Play on **2026-05-05**, starting with soccer, ice hockey, basketball and handball, combining video + event data + audio commentary. Sky's "Recap" builds personalized highlights with ML/CV across football to tennis |
| Olympic-scale AI workflows | **Deployed** | Olympic Broadcasting Services expanded AI-powered content workflows for **Milano-Cortina 2026** |
| AI commentary | **Deployed but fragile** | IBM watsonx commentary at the Masters and Wimbledon; publicly criticized for mispronouncing a player's name |
| End-to-end automated production | **Not demonstrated** | LiveU's 2026 outlook states AI proved useful for *focused* tasks — highlights, metadata, commentary — and treats end-to-end workflow automation as the open question for 2026 |

**Read against the repo evidence this is a near-perfect match**, which is why it is trustworthy: the
open-source layer has real, active, permissive highlight/clip tooling (`roboflow/sports` MIT 5,517★,
`line/lighthouse` Apache-2.0, two MIT clippers above 1,000★) and essentially nothing for commentary
(one MIT repo at **111★**) or automated direction (**nothing**). The vendor roadmap and the open
source agree on where the frontier is.

### 4. The detection/tracking layer is one of open source's largest permissive-vs-AGPL forks

Measured this pass, last-push dates included:

| Repo | License | Stars | Last push |
|---|---|---|---|
| `ultralytics/ultralytics` | **AGPL-3.0** | 63,769 | 2026-11-26 |
| `roboflow/supervision` | **MIT** | 51,730 | 2026-11-26 |
| `mikel-brostrom/boxmot` | **AGPL-3.0** | 8,330 | 2026-11-20 |
| `roboflow/trackers` | **Apache-2.0** | 4,022 | 2026-11-25 |

Both camps are actively developed and roughly matched in capability. The trend worth naming:
**the permissive side is consolidating around Roboflow while the AGPL side consolidates around
Ultralytics**, and a 2027 engagement will have to pick a side deliberately rather than inherit one
from a tutorial. Most tutorials teach the AGPL one.

### 5. The content law now has a control group — the methodological trend of this pass

Nineteen passes have restated that the licence of the underlying content, not regulatory pressure,
decides whether open source can serve a plane. Sports is the first plane that **tests** it: one
problem, three substrates, difficulty held constant. Pixels you license → permissive and abundant.
Vendor optical feeds → 3,847★ / 2,870★ / 757★ of code with **no usable grant**. Client-side esports
replays → three independent MIT parsers, all active within four days of this pass.

**Esports telemetry is open because the file is on the player's disk; football telemetry is closed
because the file is on Opta's server.** The trend to watch is whether substrate B ever opens: the
falsifiable prediction registered in `agents/top.md` is that a permissive client library appears
within two quarters of any league publishing tracking data under a real open licence — and that no
amount of developer demand produces one while the feed stays contractual.

### 6. Where the plane collapses: the money layer, measured

The gradient runs SEE → STANDARDIZE → ACCESS → MONETIZE, and it dies at the last step.
`fan engagement` returns **28★, 6★, 5★, 4★, 3★, 3★** for its top six results, the leader unlicensed
and last touched **2023-12-12**. The most-starred open odds library has been **dead since
2022-12-08**. Against a $65.82bn rights market and documented nine-figure fan-monetization spend,
this is the largest gap between money and code anywhere in this KB — larger than cycle 8's music
royalty accounting, because there the spend was contested and here it is not.

---
industry: media
region: Global
updated: 2026-11-22
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

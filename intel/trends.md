---
industry: media
region: Global
updated: 2026-11-27
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

## The investigative-journalism & verification plane — trends measured 2026-11-26 (pass 20)

### 1. The agent layer arrived here, and it arrived as skills rather than code

Measured, not asserted. The two most active journalism-agent repositories were both pushed the day
before this measurement: `jamditis/claude-skills-journalism` (462★, MIT, 2026-11-25) and
`buriedsignals/spotlight` (67★, 2026-11-25). Nineteen previous passes over this KB found agent layers
that were absent, dormant or vendor-captured; this is the first that is permissive **and** alive.

The shape matters more than the fact. Both ship **skills — methodology prose an agent follows** — not
libraries. `spotlight`'s own licence file names its sources: GIJN publications, Bellingcat training
material, an EBU Eurovision News piece. The competence is in the text. That is why the licence
analysis in `agents/top.md` lands on the content rather than the code, and it is a trend worth
tracking across all twelve industries: **as agent layers mature, the binding licence moves from the
dependency tree to the prompt.** Nothing in an SBOM sees that move.

### 2. Automated fact-checking has not happened, and the measurement has a control group

`DEFAME` (64★, Apache-2.0) is the only non-trivial open fact-checking system and its default branch
has not moved since **2025-09-30**. Beneath it, four repositories with **literally zero stars**
(`ClaimVerify`, `Ai-Claim-Verification`, `claimcheck`, `ClaimLedger`), three pushed within the last
eight weeks — new work, no adoption. The query `claim verification fact check newsroom` returns
**one repository in the world**, with one star and no licence.

The control group is in the same channel on the same day: `sherlock-project/sherlock` at
**117,843★**. Open source is not weak at investigation — it is weak at **adjudicating a claim**.
This is the content law of the healthcare passes in its purest form: gathering is a format problem
and it gets built; judgement stays closed.

### 3. The live layer is self-hosted copyleft, because the buyer asked for that

The GIJN technology agenda from the GIJC25 pre-conference records practitioners asking for ways to
analyse large document troves, connect datasets and **triage leaks without exposing sensitive data
to third-party platforms**. That requirement selects the architecture, and the measurement matches:
Datashare (AGPL) pushed today, DocumentCloud (AGPL) 2026-11-24, Prophecies (AGPL) 2026-10-15,
SecureDrop/Dangerzone/GlobaLeaks (AGPL) all current. **In this plane, "we will host it in your
infrastructure" is the price of entry, not a differentiator** — and a SaaS-first proposal is
disqualified before the licence conversation starts.

### 4. The newsroom's AI problem in 2026 is governance it can evidence, not capability

Three independent 2026 signals, all pointing the same way:

- **EMEA:** the Future Newsrooms Study (July 2026) found **52%** of surveyed newsrooms name cultural
  resistance or scepticism as the main barrier to AI adoption and **61%** a lack of technical skills
  — not cost, and not capability. The imec-SMIT (VUB) mapping study (May 2026) argues adoption alone
  delivers no value; **control of infrastructure, data, models and rights** does.
- **LATAM:** legacy outlets are writing policies rather than restricting use — Listín Diario
  (Dominican Republic) announced AI guidelines to its readers in January 2026, El Comercio (Lima)
  put a roughly 10-page guide in place in early 2026, and SiPreBA with the Heinrich Böll Foundation
  published "Notes Toward Regulating Artificial Intelligence in the Media" in May 2026. At the IAPA
  midyear meeting (April 2026) the reported friction was **everyday use against absent institutional
  frameworks**.
- **MENA/APAC:** reporting on the Arab media market puts AI spending at **$520M in 2026** while
  noting that most journalists using AI have had little or no formal training and nearly **eight in
  ten** work in newsrooms with no formal AI policy.

Pass 8's insight holds and sharpens: **an organisation that has published a policy has committed to
being able to evidence it.** This plane is where that evidence is produced — provenance of a
document, chain of custody of a leak, the record of which claim was checked against what. The
product is the audit trail, and it is sellable precisely because the policy already exists.

> ⚠️ **Attribution discipline.** The figures in §4 come from **search-result snippets**. None of
> `cnti.org`, `reutersinstitute.politics.ox.ac.uk`, `latamjournalismreview.org` or `acma.gov.au`
> resolves from this session (DNS failure, verified by probe), so none was read at source. Treat
> every number here as **reported, not verified**, and re-check before putting one in a client
> deliverable.

---

## The spatial, immersive & volumetric plane — trends measured 2026-11-26 (pass 21)

### 1. The research licence, not the registry, is what gates this plane — and the market already routed around it

Twenty passes of this KB converged on a law about content: the regulator creates the obligation and
the **licence of the knowledge content** decides whether open source can discharge it. This plane has
no registry and no membership body, and it is still gated — at the **origin**. The reference
implementation of 3D Gaussian splatting (`graphdeco-inria/gaussian-splatting`, **24,564★**) is
research-and-evaluation-only under the Inria/MPII **Gaussian-Splatting License**, with commercial use
by explicit consent through tech transfer. `NVlabs/instant-ngp` (**17,604★**) is non-commercial under
the NVIDIA Source Code License.

The resolution was reimplementation, and it worked: `nerfstudio-project/gsplat` is Apache-2.0 and is
why a 3DGS engagement is legal at all. But it carries **5,961★ — 24% of the stars of the repo it
replaces.** The trend to state plainly: **in this plane popularity and usability are inversely
correlated**, because the famous artefact is the paper's code and the usable one is the clean-room
rewrite. Every tool that ranks by stars gets this exactly backwards.

### 2. A new licence shape is appearing: permissive with a pre-use registration gate

`zju3dv/EasyVolcap` and `zju3dv/EasyMocap` carry **Project Registration License (PRL) v1.0**,
copyright 2026. Commercial and organisational use is **free and allowed**; what is required is
**registration of each distinct project before use begins**, by form, with no fee and no approval
step. No patent grant. GitHub renders it `NOASSERTION`.

Two things make this a trend worth watching rather than a curiosity. First, it is **invisible to the
entire compliance toolchain** — no SPDX identifier, no badge, no SBOM scan of the source tree can
express "register before you start", so it can only be caught by reading the file, and it must be
handled in engagement setup rather than in CI. Second, it is a **rational response by research labs**
to the Inria problem: it preserves commercial adoption while giving the lab the one thing a
non-commercial licence was really buying them, which is knowing who is using their work. If it
spreads, the binary "permissive vs copyleft vs non-commercial" taxonomy this KB has used for twenty
passes acquires a fourth column.

### 3. The dormancy is on the time axis, and that is exactly where the product is

Measured, not assumed:

| Layer | Best permissive option | Stars | HEAD | State |
|---|---|---|---|---|
| Static capture (SfM) | `colmap/colmap` (new BSD) | 13,302★ | 2026-11-26 | Healthy |
| Static splatting | `nerfstudio-project/gsplat` (Apache-2.0) | 5,961★ | 2026-09-19 | Healthy |
| Static splatting, CUDA-free | `ArthurBrussee/brush` (Apache-2.0) | 5,392★ | 2026-11-23 | Healthy |
| **Temporal / 4D capture** | `hustvl/4DGaussians` (Apache-2.0) | 4,047★ | **2024-10-27** | **Dormant 25 months** |
| **Temporal / 4D production** | `ASU-NEM-Labs/open4dgs-core` (MIT) | **161★** | 2026-11-21 | Active, tiny |
| Headset delivery | `three.js` (MIT) / `godot` (MIT) | 119,448★ / 120,865★ | 2026-11-26 | Enormous |

The industry can photograph a static scene and can deliver to a device. **The layer that converts 3D
photography into volumetric video — time — collapses to 161 permissive, active stars.** Everything the
market narrative calls "volumetric video" sits on that 161. This is the plane's single most sellable
measurement and it is **falsifiable**: if `4DGaussians` is revived or `open4dgs-core` passes ~1,000★
within two quarters, the finding expires and should be rewritten rather than defended.

### 4. Standards bodies ship specs without licence grants — now confirmed across two industries

`KhronosGroup/glTF` (7,907★), `CesiumGS/3d-tiles` (2,653★),
`KhronosGroup/glTF-Sample-Assets` (1,180★) and `needle-tools/needle-engine-support` (613★) have **no
licence file at the repo root** — 404 across thirteen filenames and both branches, with `README.md`
returning 200 and a positive control passing, so the naming-convention false negative is ruled out.
Pass 5 found the same thing in `rslstandard/rsl`, the repo of a licensing standard. Two industries,
same shape: **the artefacts whose entire purpose is interoperability are the ones shipped without
terms.** Operational rule: cite the published specification, never the spec repository, and never let
a dependency scanner's reading of these repos stand as the answer in a client licence table.

### 5. Vendor identity has stopped predicting licence terms

NVIDIA ships `instant-ngp` (17,604★, non-commercial, slowing) and `nv-tlabs/3dgrut` (2,515★,
**Apache-2.0**, pushed 2026-11-06) in the same plane. The newer, permissive one is the smaller one.
Google shipped `three-live` (Apache-2.0) **this month** as an explicitly "AI-first" 3D runtime,
compiling generated Three.js into glTF, USDZ and WebXR — a bet that spatial assets will be generated
rather than authored. The practical consequence is a method rule, not a market opinion: **read the
licence file on every repo, every pass**; a remembered vendor policy is now a liability.

### 6. The delivery format for spatial video is proprietary where it matters

Spatial/immersive video's consumer format is MV-HEVC. Open tooling reaches it only through x265's
multiview encoder plus an ffmpeg remux (GitHub mirror of x265 is GPL-2.0 and **last pushed
2023-09-11**; canonical development is at VideoLAN), and small project-level efforts whose own authors
note that headset playback is untested. The first **live** MV-HEVC broadcast encoder announced in 2026
is **proprietary** (SpatialGen, AWE USA). Meanwhile the ISO/IEC reference software for volumetric
point-cloud compression, `MPEGGroup/mpeg-pcc-tmc2`, is BSD-licensed text that **explicitly grants no
patent rights** and has 177★. So: capture is open, carriage is patent-encumbered. Any "end-to-end
open volumetric pipeline" claim should be refused at the delivery step.

## Pass 22 (2026-11-26) — the podcast & spoken-audio plane: what is actually changing

### 1. The open podcast standard is winning adoption where it costs the platforms nothing

The Podcasting 2.0 namespace (`Podcastindex-org/podcast-namespace`, **CC0-1.0**, 496★) is being
absorbed by the closed platforms one tag at a time: **Apple adopted `podcast:transcript` in March
2024 and now supports `podcast:chapters` plus the Chapters JSON format**, and auto-generates chapters
from a show's transcript; **Spotify supports the transcript tag** and auto-chapters episodes that
lack them. **iHeartRadio is going further** — adding video to its app via **standard RSS with
`alternateEnclosure`**, so one feed carries audio and video and the creator keeps hosting their own
video (Podnews).

Read the pattern, not the individual wins: the platforms adopt the tags that **describe** content
and ignore the tags that would **move money or listeners**. Nothing in the namespace carries ad
signalling, and nothing carries an AI-disclosure field (see item 3). Adoption of a CC0 standard is
real but **selective, and the selection is commercial.**

Reported adoption of the tags themselves is still low and the figures are weak: one vendor analysis
citing Podcast Industry Insights puts **~7.74 m episodes (≈4.84 % of 160.07 m discovered episodes)**
pointing at a transcript file, and **65,185 podcasts / 1.62 m episodes** using chapters — with the
per-episode chapter data **dated April 2024**. Directional only; not verified against a primary
source.

### 2. The licence gradient completes: at the money, open source stops existing

Measured this pass across four layers of one plane, same day, same method:

| Layer | What it owns | Licence | Living example |
|---|---|---|---|
| Standard | nothing | **CC0 / MIT** | `podcast-namespace` CC0; `op3`, `opawg/*`, `podping.cloud`, `podlove-publisher` MIT |
| Library / generator | one pipeline step | **Apache-2.0 / MIT** | `podcastfy` Apache-2.0 6,860★; `notebookllama` MIT |
| App | the listener relationship | **GPL / AGPL** | `audiobookshelf` GPL-3.0 15,123★; `AntennaPod` GPL-3.0 8,357★; `podverse/*` AGPL |
| Ad server | the revenue | **nothing exists** | `audio ad insertion server stars:>=20` → **0** |

Pass 13 recorded that the licence hardens as code approaches the money. **The end of that gradient
is not AGPL — it is absence.** And the control case is unusually clean: the community *did* build a
permissive payment rail (`helipad` MIT, `BoostBots` BSD-3, `nostr-wallet-connect` Apache-2.0) for
**value4value** micropayments, a rounding error of industry revenue, while writing **nothing** for
the **$2.9 bn** of US podcast advertising (IAB/PwC 2025). Open source followed the ideology, not the
revenue. Expect no open DAI project to appear; the incentive that would create one is absent.

### 3. Synthetic voice became a compliance object this year, and the open format has no field for it

The EU AI Act's **Article 50 transparency duties have applied since 2026-08-02**: synthetic content
must be machine-readably marked and disclosed on first use, which audio counsel reads as reaching
**cloned voices, synthetic dialogue, podcast ads and AI jingles** even in partly-synthetic
productions. In parallel, licensed-voice supply became normal: **ElevenLabs' Iconic Voices
marketplace**, **McConaughey and Caine licensing their voices**, and the **Stan Lee Universe deal
(2026-05-27)** for a deceased performer's voice and likeness.

The gap between those two facts is the finding: **an AI-voiced podcast is now legally required to
declare itself, and the CC0 RSS namespace that the whole open ecosystem publishes through has no tag
to declare it with.** Marking has to happen somewhere — in the audio (C2PA, pass 5), in the feed (a
tag that does not exist), or in prose nobody can parse. This is the most concrete standards-shaped
opening this KB has found: the namespace is public domain and takes proposals in the open.

### 4. Measurement is being standardised, and the standard is server-side — which suits open source

IAB Tech Lab circulated **Podcast Technical Measurement Guidelines v2.3** in 2026 (downloads,
audience and ad delivery from **server-side log data**; public comment closed **2026-08-19**), and
the trade consensus is that measurement has lagged consumption because the definitions keep moving.
Because podcast apps mostly do not confirm playback client-side, the audience number *is* a log plus
a user-agent corpus — and that corpus is **MIT and open** (`opawg/user-agents-v2`,
`podcast-rss-useragents`, `podcast-hosts`, `podcast-prefixes`), with `op3` (MIT) as the only open
prefix implementation. **This is the one layer of the plane where a permissive open base and a fresh
written standard coincide and no incumbent holds the ground.**

### 5. Video is eating podcasting's distribution, and RSS is the hedge

~**71 % of US podcasters** now make video versions; **Edison has YouTube ahead of Spotify** among US
weekly podcast listeners (33 % vs 26 %) and **YouTube is now the UK's most-used podcast platform**.
One 2026 newsletter reports Spotify podcast listening **down 26 %**, which could not be verified and
is noted only as a claim. Meanwhile ad effectiveness readings **conflict**: eMarketer has audio
outperforming video on purchase conversion by **18–25 %**, while another trade source reports video
converting modestly better. Do not build a recommendation on either.

What is not in dispute: the shows moving to platform-hosted video **leave the measurable RSS
ecosystem**, which is why `alternateEnclosure` and iHeart's open-RSS video move matter more than
their size suggests. "Ship video without leaving the open feed" is a defensible engagement for any
rights-holder who intends to keep its audience data.

### 6. The ops agent layer does not exist — and the vocabulary makes it look like it does

Measured: `podcast ad agent` 11 results (top **1★**), `podcast discovery agent` 5 (top **3★**, and it
is an **unlicensed** MCP server), `podcast seo agent` 6 (top **4★**), `podcast monetization` 59 (top
**2★**). `show notes agent` returns 85 and the top two are a **SARS-CoV-2 mRNA sequence archive**
(3,352★) and a GitHub Desktop release-notes mirror — collision, not a field. Meanwhile the
*generation* agents are permissive and healthy (`SurfSense` Apache-2.0 16,962★, `autoclip` MIT
16,708★, `podcastfy` Apache-2.0 6,860★). The asymmetry is consistent with every other plane in this
KB: **open source generates; it does not run the business.**

## Pass 23 (2026-11-26) — the still-image, photo-desk & print-production plane

### 1. The industry-wide trend, and what it means for still images specifically

The 2026 consensus across Akamai, Deloitte, EY, TV Tech and TVBEurope is that **the adoption
question is closed and the value question is open**: Akamai's *State of AI in Media 2026* frames the
challenge as turning widespread experimentation into business value, and reports **time spent in
generative AI apps doubling between H1 2025 and H1 2026**. TV Tech calls 2026 "the year of scaling
AI throughout the media enterprise" and expects **several false starts with agentic advertising**;
EY says the strategic question has shifted to applying AI **responsibly**; more than half of
Deloitte's 2026 predictions link directly to AI.

**For the still-image plane this general trend resolves into something unusually concrete.** The
"responsible application" everyone is describing in the abstract already has, for images, a
*specified* form: a labeling duty (EU Article 50, China's Measures), an editorial prohibition
(AP, dpa, Getty), a consent duty (Mexico), and a signing standard (C2PA, shipping in Leica, Nikon
and Sony bodies). **Images are the one media type where "responsible AI" has stopped being a
principle and become a file format.** That is why this plane is a buildable engagement rather than
a policy conversation.

### 2. The structural law of this KB, refined: licence tracks lineage, not layer

Every prior pass found a version of *"the substrate is permissive and healthy; the judgment layer is
empty"*. This plane is the first to contain **two substrates with different ancestries**, and they
are licensed oppositely:

| Substrate | Ancestry | Typical licence | State |
|---|---|---|---|
| Pixel pipeline — `sharp`, `libvips`, `imgproxy`, `thumbor`, `imagor`, `libjxl`, `libavif`, `libwebp` | Web infrastructure / CDN | **Apache-2.0, MIT, BSD** | All pushed within days |
| Page & print pipeline — `scribus`, `ghostpdl`, `mupdf`, `pdfarranger`, GIMP, Krita, darktable, RawTherapee | Desktop applications | **GPL-2.0, GPL-3.0, AGPL-3.0** | All actively maintained |

Both are mature, both are fundamental, both are alive. **One can become a product and the other
cannot** — and the predictor is not the layer's depth in the stack, it is whether the code grew up
in a browser-and-CDN world or a desktop-publishing world. **Refinement to the law: permissiveness
is inherited from a project's origin community, not determined by its technical position.**
Practical consequence: an imaging engagement is cleanly separable into a productisable half
(serving, transforming, searching) and a deployable-only half (layout, RIP, darkroom), and the
licence boundary falls in a predictable place.

### 3. The sharpest trend in the plane: the describe layer is decaying while the move layer sprints

Measured 2026-11-26, same day, same method:

- **Move pixels:** `sharp` (Apache-2.0, 32,872★) pushed **today**. `ImageMagick` (17,946★) **today**.
  `libvips` (11,841★) yesterday. `imgproxy` (11,220★) two days. `libjxl`, `libavif` **today**.
- **Describe pixels:** `Real-ESRGAN` (37,679★) last pushed **2024-08-06**. `LLaVA` (25,093★)
  **2024-08-12**. `BLIP` (5,699★) **archived**. `openai/CLIP` (34,666★) eight months idle.

**Four of the five best-known open image-understanding projects are frozen on a 2024 snapshot while
the plumbing beneath them ships continuously.** The reason is visible in the star counts: the
plumbing has paying infrastructure users and the models were research artefacts whose authors moved
on. The operational lesson for a client is not "avoid them" — they work — but **"vendor and pin
them, and own the inference wrapper"**, because there is no upstream to receive a bug report.

The one live, permissive base is **`open_clip` (MIT, 14,292★, pushed 2026-11-21)**. Any
natural-language image search built in 2026 should sit on it rather than on `openai/CLIP`.

### 4. AI is arriving inside the classic tools, opt-in and with model provenance stated

**darktable 5.6 (June 2026)** added an AI subsystem to a 13,508-star GPL-3.0 RAW developer:
`neural restore` (RAW denoise, denoise, upscale), an AI object-mask tool, HEIF export. Three details
make it a governance template rather than a feature:

1. **Opt-in and off by default** — the AI path requires a build flag.
2. **Models ship separately with documented licences**, and the project states that **models of
   unclear provenance are excluded.**
3. **5.6.1 (August 2026) made RAW denoise refuse legacy Fujifilm Super CCD sensors** the models were
   never trained on — a deliberate refusal to run out of distribution.

User reports are mixed (one found output noticeably less vibrant), which is the honest state of it.
But **"optional, provenance-documented, and refuses inputs it was not trained for"** is a better
articulated AI policy than most vendor datasheets, and it came from a volunteer project. Worth
quoting in a client conversation about what a defensible AI feature looks like.

### 5. Provenance: the standard is settled, the implementation is tiny, the counter-tool is bigger

- The open implementation of C2PA is **`c2pa-rs` (455★) + `c2patool` (174★)**, both dual
  MIT/Apache-2.0, both pushed the day of this pass. **629 stars for the entire thing.**
- The most-starred on-topic `image metadata agent` is **`wiltodelta/remove-ai-watermarks`
  (6,530★, Apache-2.0)** — a tool for removing watermarks and provenance. **~10× the provenance
  stack.**
- Capture-side adoption is real but fragmented: Leica signs in hardware (M11-P, SL3-S); Nikon's
  Authenticity Service requires Nikon Imaging Cloud; Sony enabled pro bodies by firmware but
  **full validation requires Sony Ci Media Cloud** — a vendor tier above the open standard. One
  secondary source claims Leica, Nikon and Canon are **not** in the official C2PA Conformance
  Program as of mid-2026; unverified.

**The trend to state honestly: provenance has won the argument and lost the build.** Everyone
specifies C2PA; 629 stars implement it; a better-resourced project deletes it. A client proposal
should therefore lean on **capture-side hardware signatures plus platform-side verification at
ingest**, and should not promise that metadata survives the open internet.

### 6. Alt text is the clearest "model is not the product" case in the whole KB

- The models are commodity and free (BLIP BSD-3 but archived, LLaVA Apache-2.0 but dormant, plus
  every hosted VLM).
- The accuracy evidence says drafting is **nearly, but not quite, good enough**: a 2026 engineering
  primer testing **~600 images** found AI drafts usable as a **first draft for the photo column**
  and **actively risky for decorative images** unless the workflow handles them separately.
- Drupal's `ai_image_alt_text` module — the most serious implementation found — leads with a
  **customisable prompt template, multilingual output, bulk back-processing** and explicit
  **human-in-the-loop verification.**
- The open GitHub field for the editorial workflow is **one repo with one star.**

**Everything hard about alt text is the review loop, the bulk back-catalogue run, the
decorative-image exception and the audit trail — and none of it is the model.** This is the most
sellable gap in the plane and the easiest to explain to a non-technical buyer, because the
compliance driver (accessibility law) already exists in every region.

### 7. The regional asymmetry is the strongest this KB has recorded

| Region | What binds an image | Artefact required |
|---|---|---|
| **APAC (China)** | **Binding law since 2025-09-01**: explicit *and* implicit (metadata) labels on AI-generated images; platforms must verify; removal prohibited; GB 45438-2025 sets the method | A metadata label writer + ingest verification gate |
| **EMEA** | AI Act Article 50 horizontal transparency — **date contested** (2026-08-02 vs 2026-12-02); UK training question **unresolved** after *Getty v Stability* | A configurable label + a rights-reservation posture |
| **North America** | **No statute.** Editorial policy (AP bars AI in news photography, disclosure on "material" use — undefined), Getty's AI-free libraries, 2026 guild agreements | A materiality + consent record |
| **LATAM** | Mexico's May 2026 amendments — a **performer-consent** duty, not a labeling duty | A likeness-and-consent record per person depicted |

**Four regions, four different artefacts, one pipeline.** The design consequence is the
deliverable: write the metadata once, and make the *regime* a per-market policy object rather than a
branch in the code. A publisher operating in Mexico and the EU needs a consent record **and** a
label; they are different data models, and a single "AI disclosure" field satisfies neither.

### 8. Informed gaps from this pass

- **No market figure** for the still-image, stock, photo-archive or print-production segment could be
  verified in any region. See the refusal in `intel/market.md` pass 23 addendum. This is the third
  such refusal (after passes 16 and 17) and the pattern now reads: **this KB can size consumer-facing
  media segments and cannot size production-tooling segments.**
- **ResourceSpace**, named in 2026 roundups as a leading open-source DAM, **could not be verified** —
  not on GitHub under `montala/ResourceSpace`, and its site was unreachable from this environment.
  No URL is asserted.
- **The CMS plugin registries were not enumerated.** The real alt-text agent layer lives on
  drupal.org and wordpress.org, not GitHub, so this pass's GitHub measurement **understates** that
  layer. Named modules (`ai_image_alt_text`, `aidmi`, and the WordPress AI Client plugins) are
  recorded, but no systematic count was taken. A later pass measuring CMS-side agents should start
  there.
- **No image-specific rule found for Japan or India**, and none in the AVMSD overhaul. Recorded as
  unverified, **not** as permissive.
- **RawTherapee's and fontbakery's star counts are unknown** (search index returns 422 while git
  serves normally). Written `n/a` rather than estimated.

## Pass 24 (2026-11-26) — the owned-channel & audience-relationship plane: what is actually changing

### 1. The industry trend that created this plane: discovery collapsed, so publishers are buying back the relationship

This is the clearest cause-and-effect chain in the KB, and every link is sourced:

- **AI answers replaced the click.** Google's AI Overviews cite news publications but produce fewer
  clicks to the source (Reuters Institute, *Journalism, media and technology trends and predictions
  2026*). Google **Discover** referrals fell **21% YoY**. Facebook referrals to publisher sites had
  already halved over a year (Chartbeat/Similarweb).
- **The revenue effect is not marginal.** Trade reporting puts declines at **50–90%** for publishers
  most exposed to referral traffic.
- **The response is owned channels.** The April 2026 **IAB survey of 109 US publishers** found news
  publishers prioritising **subscriptions, attribution and direct audience ownership**; large
  publishers scaling licensing and third-party distribution instead. Newsletter revenue grew **~30%**
  in a year at one marketplace (Paved, via The Current). The Guardian's stated goal is moving readers
  from one-off sends to **always-on weekly products**; Punchbowl's CEO says **even site visits are
  driven through the newsletter**.
- **And the industry framing has changed with it.** eMarketer now describes newsletters as
  **"first-party media"** — an inventory class, not a retention tactic.

**What this means for an engagement:** the owned channel has stopped being a marketing deliverable and
become **infrastructure**. Piano's guidance is the right opening diagnostic to run with a client:
*what percentage of your current audience can you reach without a referral source?* Most clients do
not know, and the number is the business case for everything in this plane.

### 2. The structural law of this KB, now with a single explanatory variable: **liability**

Twenty-three passes recorded the same law in different vocabularies — by layer (pass 4), by lineage
(pass 23), by distance from the recurring charge (pass 13), by where the code runs (pass 12), by what
the code owns (pass 22). This plane isolates the variable, because it contains one function measured
under two liability regimes:

| Function | Open implementation | Stars | Who answers for the record |
|---|---|---|---|
| Deliver a byte to an inbox | postal | 16,982 | nobody |
| Send to a list | listmonk | 24,473 | nobody |
| Host a conversation, generically | discourse | 48,117 | the operator, weakly |
| **Host a *newsroom* conversation** | **coralproject/talk** | **2,005** | **the publisher, fully** |
| Encode consent lawfully | iabtcf-es | 156 | the publisher, under GDPR |
| Carry consent across jurisdictions | IAB GPP | 128 (**not software**) | the publisher |
| Operate identity without a cookie | uid2-operator | **18** | the operator, fully |

**1,360× across one plane.** And the middle two rows are the control case: *the same function*,
hosting comments, differs **24×** depending only on whether the operator answers for what gets
published. No earlier pass had two implementations of one function under different liability.

**The corollary that sells:** open source stops at the point where someone must stand behind the
record. That is where an integrator's work is actually worth money — the code is free and the
accountability is not.

### 3. The cookie replacement for the open web has 18 stars, and it is not abandoned

`IABTechLab/uid2-operator` is **Apache-2.0 and was pushed 2026-11-26**. This is not a dormancy
finding — it is an **adoption** finding, and a different shape from anything in passes 1–23.

The reason is in the operator model: UID2's code has been open since The Trade Desk published it, but
the **public operator role went unfilled**. Prebid.org was slated to be the first public operator and
**paused** its integration; participants such as Fubo, Optable, InfoSum and AWS run **private or
closed** operators over their own users' emails. Governance reporting conflicts — one source says UID2
moved to Prebid.org's independent governance, AdExchanger reported Prebid stepping back — **so treat
UID2's governance as unsettled and verify it against a primary source before advising a client.**
Adoption: **1,000+ publisher and technology partners** as of mid-2025 per The Trade Desk's own
disclosures (the most recent figure found; **no 2026 primary figure surfaced**).

**The read:** the code is free, the liability of holding other parties' hashed email addresses under
GDPR and LGPD is not, and that is why eighteen people starred it. For a client, **operating** an
identity graph is a decision about indemnity, not about software.

### 4. The measurement the owned channel was built on is being destroyed as it is adopted

The sharpest irony in the plane: publishers moved to email to escape platform intermediation, and the
inbox is being intermediated.

- **Apple Mail** writes **pre-open** summaries with Apple Intelligence that *replace the preheader* —
  the publisher's own subject-line craft is overwritten before anyone opens anything.
- **Gmail** shows **post-open** Gemini summaries, and appears to **auto-open** messages to generate
  them: **opens inflate while clicks fall**, because a reader satisfied by the summary never clicks.
- **Apple MPP** already broke opens; vendor estimates put inflation at **4–8 percentage points**
  (unverified — treat as directional).
- **Gmail Postmaster Tools v2** retired High/Medium/Low domain and IP reputation for a **compliance
  checklist plus a deliverability verdict**.

**Consequence, and it is actionable:** the open rate is no longer a metric a client can plan on.
What remains is **clicks, conversions, replies and DMARC evidence** — which is why
[domainaware/parsedmarc](https://github.com/domainaware/parsedmarc) (Apache-2.0, 1,321★) is the most
under-starred useful repo found this pass. **Caveat to carry:** these are vendor-blog findings. No
independent 2026 dataset on publisher open/click rates under AI summaries surfaced; searched, not found.

### 5. A new licence shape: the star-count decoy

Five ways a licence hides were already recorded (pass 4's three channels, Chromaprint's build flags,
OpenUSD, the directory-vs-repo mismatch, pass 23's `composer.json`-only declaration). This pass adds a
sixth, and it is the first that is a **naming** problem rather than a **location** problem:

`maizzle/maizzle` (**2,864★**) — the repo search returns, the repo directories link — has **no licence
file** (six paths checked, all 404), **no `license` field in `package.json`**, and a README asserting
MIT while linking to a `./LICENSE` that **404s**. The npm registry points at a different repository:
**`maizzle/framework` (1,624★), which has a real MIT LICENSE file.** The better-starred repo is the
**starter template**, and starters are what maintainers forget to license.

**Reusable across all twelve industries:** when a project name resolves to two repos, resolve it
through the **package registry** before quoting either the stars or the licence.

### 6. "Open source" is now a marketing claim in the privacy layer specifically

Two **Elastic License 2.0** projects sit in this plane, both in privacy infrastructure:
`rudderlabs/rudder-server` (**4,521★** — the CDP recommended by essentially every 2026 "open source
Segment alternative" listicle) and `ConsentOS/consentos` (25★). Licence files read; neither is OSI
open source, and ELv2's prohibition on providing the software to third parties as a managed service is
aimed precisely at integrator work.

**Why the privacy layer specifically?** Because that is where the commercial value of *trust* is
highest and the code is cheapest to copy. The pattern to expect: as a layer becomes compliance-bearing,
its vendors relicense to source-available. The permissive survivors in this plane are the ones with
institutional owners — **Apache Unomi (382★, ASF)** and **c15t (Apache-2.0)**.

### 7. The consent clock has already struck, and nothing open is registered

**TCF v2.3 mandatory** for TC strings generated on/after **1 March 2026** (Google publisher guidance;
iubenda gives 28 February 2026). **TCF v2.4 specs + updated GVL published 23 July 2026**; **website
deadline 23 October 2026**, later for apps and CTV. Both dates are **in the past**.

And the structural problem underneath: **no open-source CMP is IAB-registered.** The open stack gives
a client a consent *string* (`iabtcf-es`, 156★) and a consent *UI* (`c15t`, `cookieconsent`) and no
*standing in the framework*. This is the single most likely late-stage surprise in an EMEA engagement
in this plane.

Meanwhile the EU is actively relitigating consent itself: media bodies **EMMA, ENPA, EPC and NME**
jointly objected to the **Digital Omnibus**'s Articles 88a/88b, arguing the media exemption does not
preserve publishers' ability to ask readers directly for consent; EU governments **dropped
browser-level cookie-consent preferences** (October 2026), which publishers read as a win; and the
European Publishers Council wants low-risk first-party processing to run on **legitimate interest**
rather than consent. **Adoption of the broader package is not expected before 2028** — so design the
consent layer to be *re-configurable*, not correct-for-today.

### 8. The agent layer does not exist, and the vocabulary makes it look like it does

Searching `AI newsletter agent` returns hundreds of results and **almost nothing editorial**: sales
and outbound growth tooling, plus a long tail of 0-star personal digests. The entire on-topic,
licensed set is **seven repos**, whose best-starred member (`finaldie/auto-news`, MIT, 915★) **has not
been pushed since 2025-07-19**, and whose only permissive active member has **11 stars**. Four of the
seven carry **no licence file at all**.

The adjacent zero is worth more than the seven rows: **there is no open agent for newsletter
operations** — list hygiene, send-time optimisation, deliverability triage, churn-risk scoring on an
owned list — even though the substrate beneath it (`parsedmarc` Apache-2.0, `postal` MIT, `novu` MIT)
is permissive, healthy and pushed this week. That is the most commercially obvious unbuilt agent found
in twenty-four passes.

### 9. Informed gaps from this pass — searched, and genuinely not found

- **No independent 2026 data on publisher email engagement under AI inbox summaries.** All findings
  trace to email-vendor blogs. Recorded as directional.
- **No newsletter *advertising* market figure.** Searched; the vendors size email-marketing
  *software* ($1.6B–$13.7B depending on scope, see `intel/market.md` pass 24 addendum) and nobody
  sizes newsletter sponsorship revenue, which is the number a publisher actually wants.
- **No open publisher CRM or media ERP** under any permissive licence (see `verticals/solutions.md`).
- **No open WhatsApp/LINE publisher-distribution tooling**, despite messaging being *the* owned
  channel in LATAM and parts of APAC.
- **No 2026 primary figure for UID2 adoption**, and conflicting reporting on its governance.

---

## Pass 25 (2026-11-26) — the traffic, sales-order-to-air & billing plane: what is actually changing

> **Source note for this section.** Repo facts are verified (`ls-remote`, canonical-slug check,
> licence files read). The market and regulatory facts below come from **web-search result extracts**:
> the publisher domains (`thedesk.net`, `tech.ebu.ch`, `ebu.ch`, `mediapost.com`, `adexchanger.com`,
> `ppc.land`, `lw.com`, `bnamericas.com`, `radioworld.com`, `wideorbit.com`, `bitmovin.com`,
> `playboxtechnology.com`, `akamai.com`, `digitalheroesco.com`) are **outside this session's allowed
> network domains**, so the URLs could not be opened and the claims are **attributed but not
> independently confirmed**. Verify any figure against the primary source before putting it in front
> of a client. Marked **†** throughout.

### 1. The commercial layer is where 2026's money went — and all of it went proprietary

This is the widest incumbent-vs-open-source gap recorded in any plane of this KB.

- **Fox** launched what it and the trade press call the TV industry's **first end-to-end agentic
  advertising platform on 2026-06-17**, built on Fox AdStudio: agents handle planning, transactions
  and activation across linear and streaming, with **agent-to-agent negotiation replacing the phone
  calls, faxes and spreadsheets** linear buys have traditionally required.†
- **NBCUniversal + FreeWheel** completed what they describe as the **first AI-agent-led programmatic
  guaranteed deal**, covering live sports across **linear and streaming**: a buy-side agent sends
  campaign goals to a sell-side agent, which returns matching linear and streaming proposals.†
- **Magnite + ITN** announced agentic **local linear** buying on **2026-09-10**, full integration in
  **Q4 2026**, one RFP across local linear and CTV — reportedly cutting buying from weeks to hours.†
- **WBD** applied agentic automation in **Q2 2026** to direct-response workflows and audience
  forecasting, against advertising revenue down **7% YoY in Q1 2026 to $1.85 bn** on linear declines.†

**Against that: the open-source total for the same plane is a 2-star repo created seven days ago whose
billing step is a roadmap item.** Every incumbent initiative above is closed. The thing being
automated — negotiating, booking and settling linear inventory — is exactly the step this KB measured
as an empty set.

### 2. The scepticism is on the record, and it is the reason to sell the layer *underneath*

Quote these to a client rather than the launch announcements:

- Magnite's CEO capped a **2027 agentic ad-spend forecast at "somewhere between negligible and
  $700 million"** (reported August 2026).†
- A Yahoo DSP finding: **55%** of marketers trust the technology to plan and execute tasks, while
  **about one in five actively distrust** agentic AI.†
- TV Tech's 2026 outlook expects **"several false starts"** with agentic advertising and names
  **creative production** as the likelier first real breakthrough.†
- Akamai's *State of AI in Media 2026*: adoption is no longer the question; **turning widespread
  experimentation into business value** is. Time spent in generative-AI apps **doubled** between H1
  2025 and H1 2026 (Sensor Tower via Akamai).†

**The implication is the commercially useful one.** The honest pitch is not "agentic ad sales now". It
is the **reconciliation and evidence layer underneath** agentic selling: if agents negotiate the buy,
somebody still has to prove what aired and settle what is owed — and nobody, open or closed, has
built that in a way a client can own. Patterns 25.1 and 25.2.

### 3. FAST turned the schedule into the cost centre — the economic driver of this plane

- **~2,170 FAST channels globally** as of July 2026, **+17.5% YoY** from ~1,850 (Gracenote Data Hub).
  A second source gives 2,120 in Q2 2026 at +19%; treat ~2,100–2,200 as the range.†
- **Programming volume is growing much faster than channel count**: sports channels **+13.8%** while
  unique sports titles **+31.2%** and individual games/events **+37.5%**.†
- Therefore **the bottleneck moved from launching channels to operating them** — one analysis puts it
  as the challenge shifting to *reliably operating increasingly complex* channels.†
- And the revenue base is thinning: PlayBox (October 2026) argues **supply has outrun demand**; one
  vendor model puts **effective CPMs near $5** at a ~10-minute-per-hour ad load and a **sustainable
  ceiling near 400 channels per platform**.†
- Operating cost, vendor estimates only: **$250–500 per channel** to start on managed playout,
  **~$1,500–2,000/month** for a serious single channel before content; AWS MediaTailor at **$0.10/hr**
  VOD-only and **$0.35/hr** with live sources.†

**More channels × far more events × thinning CPMs = scheduling and reconciliation labour is now the
margin.** That is the business case for this plane, and it does not depend on agentic hype.

### 4. The incumbent stack is consolidating — which is when replatforming budget appears

- **Imagine Communications** (LandmarkOSI for traffic and billing, xG Linear for MVPD traffic,
  GamePlan ad decisioning) was reported **acquired by Lumine Group on 2026-07-01**. **Single secondary
  source — verify before citing.†** Its CEO publicly conceded in February 2026 that *"we set ambitious
  expectations that our delivery didn't fully meet."*†
- **WideOrbit** (WO Traffic v24.0, WO Fusion cross-platform sales, WO Aurora radio automation) is
  moving customers from **CapEx to subscription OpEx** (vendor's own framing) and partnered with
  Pattison Media in **September 2026** on programmatic for broadcast radio.†
- **Operative** (AOS) sits in an older Imagine partnership connecting order management to ad
  execution; current status unconfirmed.†
- A third-party build-vs-buy analysis concludes that **WideOrbit and Marketron are "the backbone of
  American broadcast traffic"** and recommends groups **keep the core system and build a
  cross-platform order and reconciliation layer around it.**†

**That last sentence is the engagement shape, written by someone other than us** — and it is precisely
the layer this KB measured as having no open-source implementation.

### 5. The provenance obligation has landed on the traffic desk, and no traffic system has a field for it

This is the most concrete unbuilt thing in the plane, and it is a *data-model* gap, not a model gap.

- A political or AI-disclosed spot is **traffic's object**: it is booked, logged, aired and invoiced
  by the traffic system.
- **North America:** at least **31 states** regulate AI in political ads and **only about half**
  require disclosure; federal **reasonable-access** rules mean a broadcaster **cannot censor a federal
  candidate's ad**, which collides with state laws prescribing specific disclosure wording. Broadcast
  counsel's advice includes **preserving rather than stripping** standards-compliant provenance
  metadata and signatures through editing and web publishing.†
- **EMEA:** EU AI Act **Article 50** requires machine-readable marking of synthetic output, with
  systems already on the market before 2 August due to comply by **2 December**; deepfakes disclosed
  no later than first exposure.†
- So the duty attaches to an object the traffic system owns, varies **per state and per
  jurisdiction**, and **cannot live in the creative** — the broadcaster does not control it. It has to
  be enforced where the spot is **booked** and proven from the **log**. No open traffic system models
  it. Pattern 25.4, which has a hard deadline in LATAM.

### 6. What this pass confirms about the KB's structural law — sixth time, and the sharpest gradient yet

The law: **the regulator or the market creates the obligation; the licence of the content and the
nature of the problem decide whether open source can discharge it.** This plane reproduces pass 5's
three-step gradient inside a single product category:

**plan what airs (format → healthy: Nebula 332★, 14 years in production) → book the inventory
(constrained placement → 2★, 7 days old) → prove it aired and bill it (judgment → literal zero).**

Open source solves the arithmetic and stops exactly where commercial *policy* begins — because the
tolerance that counts as "aired", the value of a pre-empted spot and the equivalence of a makegood are
the client's judgment, not a shared format. **That is also why this step is worth selling: it cannot be
commoditised by the next open-source release, and it is the step that produces revenue.**

And a seventh data point for the **content-licence** half of the law: after CPT and MedDRA (taxed
content, pass 11 healthcare), BXF adds a new category — **free of charge, published on GitHub, and
still All Rights Reserved.** Easier to get wrong than a paywall, because nothing about fetching it
feels like a licence event.

---

## Pass 26 trends (2026-11-26) — the energy, carbon & environmental-footprint plane

### 1. The hardest-enforced obligation in this KB has zero open implementations, and the reason is structural

Measured, not asserted. On 2026-11-26 the GitHub search API returns **0 repositories** for
`film production carbon footprint` and **0** for `albert carbon calculator`. Against that: the **BBC**
makes BAFTA albert certification mandatory for all new commissions and recommissions of TV broadcast
content; **ITV** requires certification plus the end-board logo as a delivery item; **Channel 4** requires
productions to use albert tools. No statute in this KB is enforced this reliably — and the open-source
total is nil.

Every earlier pass would have predicted supply here. Pass 11 (healthcare) established that permissive
open source appears when the **knowledge content is freely licensed**, and in this plane it largely is:
Ember and Green Web Foundation intensity data under **CC-BY-SA**, Electricity Maps under **ODbL**, USEEIO
factors public. Free content plus a hard mandate, and still zero. **The law needed a third condition,
and this plane isolated it — see P39 in `compose/patterns.md`.** The short form: the obligation is
discharged by **attestation to a single private gatekeeper**, not by producing a computable artefact. You
cannot implement albert certification; you can only submit to it.

The control case is in the same plane and it is clean. Where the deliverable *is* a number or a document
— SCI (**ISO/IEC 21031**), CSRD/ESRS filings, cloud footprints, per-pod energy — the layer is populated
and permissive: **16 adoptable repos, six of them above a thousand stars.** Same industry, same year,
same freely-licensed inputs, two different kinds of deliverable, two opposite outcomes.

### 2. The substrate is healthy and the media-specific layer is one repo with three stars

The plane's open toolchain is institutional and alive: [electricitymaps-contrib](https://github.com/electricitymaps/electricitymaps-contrib)
4,057★ (AGPL-3.0), [scaphandre](https://github.com/hubblo-org/scaphandre) 2,018★ (Apache-2.0),
[codecarbon](https://github.com/mlco2/codecarbon) 1,955★ (MIT), [kepler](https://github.com/sustainable-computing-io/kepler)
1,605★ (Apache-2.0, pushed today), [cloud-carbon-footprint](https://github.com/cloud-carbon-footprint/cloud-carbon-footprint)
1,054★ (Apache-2.0), [carbon-aware-sdk](https://github.com/Green-Software-Foundation/carbon-aware-sdk)
600★ (MIT).

And the complete media-native intersection is
[BreakTools/deadline-energy-cost-calculator](https://github.com/BreakTools/deadline-energy-cost-calculator):
**MIT, 3 stars, last push 2025-09-17**, a Deadline render-farm plugin. That is not an excerpt of a list.
It is the list.

**This is pass 6's "misallocated" shape, now in a plane with a real regulatory driver.** The agent layer
is neither missing (pass 8) nor vendor-captured (pass 15): it is pointed at the wrong workload. Seven
agents found, five permissive, most pushed within weeks, totalling **~293 stars** — of which **256 are
one tool that measures a coding assistant**. Not one reads a call sheet, a render queue, a transcode
ladder, a playout schedule or a CDN log.

### 3. A licence obligation that collides with DRM — new, and it reaches the whole delivery layer

[co2.js](https://github.com/thegreenwebfoundation/co2.js) is the natural substrate for any per-stream
carbon metric. GitHub reports `NOASSERTION`; its `LICENSE` is **12,678 B** where canonical Apache-2.0 is
11,357 B, and reading it shows four licences stacked: **Apache-2.0** code, **CC-BY-SA** Ember data,
**CC-BY-SA** Green Web Foundation marginal data (from the UNFCCC **IFI TWG** dataset), and Electricity
Maps grid data under **ODbL** — which requires attribution, **share-alike on derivative databases**, and
**"provide unrestricted versions if using DRM."**

This KB says **`DRM` 53 times, `Widevine` 13, `PlayReady` 12.** DRM is the default state of commercial
media delivery. So the most obvious build in the plane — compute per-title emissions, surface them in a
DRM-protected service — triggers an ODbL parallel-distribution duty that **no SPDX field, badge or
source-tree SBOM scan can detect**, because the repo-level answer is "Apache-2.0" and the repo-level
answer is wrong.

This is the **third** confirmation of the pass-8 law that *the licence can belong to the compilation, not
the repository* (after `chromaprint` and `musicbrainz-server`), and the **first where the compilation's
duty conflicts with a technical norm of the industry** rather than merely adding copyleft.
[green-metrics-tool](https://github.com/green-coding-solutions/green-metrics-tool) is the fourth: a
**35,429 B "License Index"** stacking AGPL-3.0 source, co2.js's Apache terms and Electricity Maps ODbL.

**And the inversion worth carrying to the other eleven industries:** in this plane the *code* is
permissive and the *facts* are share-alike. Licence risk enters through a **dataset**, not a framework —
the exact inverse of pass 1's finding for M&E platforms.

### 4. Standards bodies keep publishing standards without an OSI licence

[Green-Software-Foundation/sci](https://github.com/Green-Software-Foundation/sci) has 298 stars and is
**not open source**. Its licence lives at **`LICENCE.md`** — British spelling, which is why a
`LICENSE*`-only probe reports "no licence" — and the 2,347 B file is a Joint Development Foundation
"AS IS" materials grant under **W3C patent mode**: warranty disclaimers and a patent pledge, with **no
copyright grant to reproduce or modify**. The specification is **ISO/IEC 21031**: implement the standard,
do not vendor the repo.

Second body in this KB to do this, after `w3c-cg/tdm-reservation-protocol` (pass 5) — and **the third
reason to keep `LICENCE` with a C in every licence probe**, alongside pass 8's `license.txt` and
`COPYING.md` corrections.

### 5. The vibe-coded-compliance pattern, and the trap that comes with it

`ghg protocol scope 3 accounting` returns 16 repositories and **eight of the first eight have 0 stars**,
most created or pushed within six months. `esg reporting agent` returns 62 with the same profile. A
regulation creates visible demand, dozens of single-author repos appear within weeks, none acquires
users. **Counting repositories here measures enthusiasm, not supply.**

Two traps came with it, both recorded so a future pass does not repeat them:

- **The false friend.** [crbnos/carbon](https://github.com/crbnos/carbon) has **2,863 stars**, was pushed
  today, and ranks first for `carbon mcp server` — and it is a **manufacturing ERP/MES/QMS named
  "Carbon"** with no relation to emissions. By stars alone it becomes this plane's flagship. The sharpest
  false friend since `eidr` and `isan` in pass 5.
- **False abundance in two languages.** `huella de carbono` returns **467** repositories and
  `pegada de carbono` **177** — and every first-page result is a student or personal project at 0–4
  stars, mostly unlicensed, **none audiovisual**. Pass 8's rule holds: **read the results, not the
  total.** Trusting these numbers would have made LATAM the best-covered region in the plane; it is the
  emptiest.

### 6. A dated trigger: the mandated toolkit is being replaced within weeks

albert's current toolkit is closing — **16 December 2026** by albert's own figure, **17 December**
according to one industry guide (**conflict recorded, unresolved; confirm with albert**) — and is being
replaced by a **Next Generation Toolkit** with a redesigned calculator, which the BBC said would launch
16 September 2026. Meanwhile the **MEDIA Carbon Calculator** (EU-backed, free, EU Login, GHG Protocol
Scope 2 + 3) launched **13 February 2026** at the EFM and explicitly does **not** replace national
calculators.

**So the number of calculators a European producer may face went up this year, not down**, and the
incumbent one expires within weeks. Reconciliation between albert, the MEDIA calculator, Carbon'Clap and
Green Film is a live client problem with a date attached — the most concrete buying trigger this pass
found.

### 7. Where the emissions are, there is no measurement tool at all

`video encoding energy efficiency` returns **1** repository and it is a 2022 bibliography.
`broadcast energy consumption` returns **1**, an Arduino mains monitor last pushed 2014-11-25. Encoding,
transcoding and delivery are the largest energy lines in a streaming business, and the open-source
measurement surface for them is **empty** — while the generic cloud and Kubernetes layer beneath them is
mature and permissive. The instruments exist; nothing points them at the workload.

### 8. The AI footprint is becoming a broadcaster deliverable before anyone has built the tool

The 2025 **Green Animation Guide** (EcoProd) already documents a German studio appending an **AI
traceability annex** to production reports for broadcasters, and recommends smaller fine-tuned models.
**Greening of Streaming's OWL** bench explicitly measures streaming **and AI workloads**. So the
disclosure is beginning to be *asked for* — and the only measurement tool with real adoption,
[codecarbon](https://github.com/mlco2/codecarbon) (MIT, 1,955★), is generic, with nothing mapping its
output to a broadcaster-shaped deliverable. **This is the plane's clearest unbuilt product** (Pattern
26.4), and it sits exactly where this KB's own industry is heading.

## 9. Incentives moved from pricing to rationing — and that changes what software the plane needs

Measured across four jurisdictions in 2026, and it is the clearest directional shift this pass found:

| Jurisdiction | 2026 move | Mechanism |
|---|---|---|
| Germany | Federal pot doubled to €250M and **exhausted on 2026-08-20**; next window opened Nov 2026 for 2027 shoots | **First-come exhaustion** |
| Italy | Fund cut €700M → €610M; **first-ever per-work and per-company caps**, closed annual budget, fixed windows — after **revoking €66M of credits in 2025** | **Caps + clawback** |
| Manitoba (CA) | **Mandatory pre-certification** announced | **Gate before spend** |
| Japan | JLOX+ **closed to applications 2026-01-31**; IP360 requires **¥800M minimum domestic spend**, ¥1.5B cap | **Instrument switch + eligibility floor** |

For twenty years the incentive question was *"what rate can we get?"* — a tax-planning question
answered by a spreadsheet and a consultant. In 2026 it is increasingly *"is the window open, do we
clear the floor, are we under the cap, and can we survive a clawback?"* — **four questions about
state, deadlines and evidence**, none of which a spreadsheet answers and all of which are ordinary
software. The trend is what converts this plane from advisory work into a buildable product, and
Italy's €66M revocation is the number that makes it urgent rather than tidy.

## 10. The money plane's open source is strong, permissive and pointed somewhere else

The inversion measured in pass 27, and worth stating as a trend because it is the opposite of every
other plane in this KB. Searched as *media*, the plane is a desert: `completion bond film` = **0**,
`production incentive eligibility` = **0**, `ERPNext media production` = **0**, `film tax credit` =
**7 repos total** with the only agent among them licensed *"all rights reserved … proprietary and
confidential"*. Searched as *computation*, the same plane holds
[Catala](https://github.com/CatalaLang/catala) (Apache-2.0, 2,456★, pushed on measurement day),
[tigerbeetle](https://github.com/tigerbeetle/tigerbeetle) (Apache-2.0, 17,467★),
[apache/incubator-kie](https://github.com/apache/incubator-kie) (Apache-2.0, 6,344★),
[frappe/frappe](https://github.com/frappe/frappe) (**MIT**, 11,164★) and
[Timefold](https://github.com/TimefoldAI/timefold-solver) (Apache-2.0, 1,882★).

**Everywhere else in this KB the generic layer is weaker than the vertical layer and the advice is to
own the pipeline. Here it is the reverse**: the generic layer is stronger, better licensed and better
maintained than anything vertical, and the entire missing piece is the **mapping** — an industry chart
of accounts, a cost-report shape, and per-jurisdiction eligibility rules. That is weeks of domain
modelling on top of mature permissive engines, not a platform build. It is the cheapest high-value
position identified in twenty-seven passes.

## 11. "Open source accounting" is where the licence traps have moved

Three readings this pass, and the pattern is that **star count now correlates with licence risk** in
this category. [akaunting](https://github.com/akaunting/akaunting) — **10,349★**, top-of-search for
open-source accounting — is **Business Source License**, not open source (`LICENSE.txt`, 3,654 B,
MariaDB BSL text, read in full). [odoo/odoo](https://github.com/odoo/odoo) reports `NOASSERTION` and
is **LGPL-3.0** for Community only, with Enterprise separately licensed. [ledger/ledger](https://github.com/ledger/ledger)
also reports `NOASSERTION` and is in fact **BSD-3-Clause** — the API hides a *permissive* licence that
makes it the best-licensed plain-text ledger of the three. **The API's `NOASSERTION` is directionless:
it concealed a BSL trap, a dual-edition copyleft and a clean BSD grant in the same search.** Pass 5's
rule stands and now has a commercial edge: in this category, **read the file before you quote the
licence** — the most-starred result is the one most likely to be unusable.

## The age-rating & classification plane — trends, measured 2026-11-26 (pass 28)

### T1 — The rating itself is becoming a regulated artefact, not a courtesy label

For thirty years an age rating was a board's advisory output, printed on a box. In 2026 four
jurisdictions moved it into the compliance surface at once, and in two of them **the obligation is
specifically about the rating's presence in the metadata**:

- **Brazil, Portaria 1.048/2025.** Main provisions in force since **2025-11-17**; **articles 48–57
  take effect 2026-03-17.** Ratings must be displayed before the work *and be available in catalogue
  descriptions, trailers and promotional materials*, covering streaming and VOD. **This is a metadata
  obligation, not a display obligation** — it is satisfied by a catalogue pipeline, which is exactly
  what this plane is.
- **EU, the proposed KIDS Act** (COM(2026) 681, procedure **2026/0286 (COD)**, Commission text
  September 2026, Council working documents October 2026). App-store providers would have to operate
  an age-rating system **and publish, in clear and accessible terms, the methodology, criteria and
  sources used.** Article 17 provides for voluntary EU codes of conduct to harmonise age-rating
  methods. **Still a proposal — not adopted law.**
- **AVMSD** is formally scheduled for revision in **Q3 2026**, and a Council working document notes
  the directive refers only to *age verification* and does not mention *age estimation* as an
  alternative assurance method.
- **Korea.** Per Microsoft's publishing guidance, **before January 2026 the GCRB could only rate
  titles below 19+; it has since expanded to rate 19+ alongside GRAC.** For digital-only content IARC
  ratings can apply **unless the title is rated 19**, which requires a GRAC rating.

**The trend to sell against:** a rating is becoming a *data-quality and traceability* problem with a
statutory deadline attached. The firm that treats it as a metadata pipeline wins; the firm that
treats it as a UI badge rebuilds it in March.

### T2 — The duty is shifting from "restrict" to "explain", and that favours open vocabularies

The KIDS Act's distinctive feature is not the restriction — it is the **publication of methodology,
criteria and sources.** A board certificate is a black box: it yields a rung and no reasoning. A
model is worse: it yields a rung and unreproducible reasoning. **An OARS-style declared-criteria
vocabulary is the only one of the three that is natively explainable**, because the criteria *are*
the data.

This is the most commercially useful inference in the pass: **where regulation demands explanation,
the deliverable is a data model, not a classifier.** It also explains the empty agent layer — see T4.

### T3 — Age *assurance* got code from a regulator; age *rating* got nothing from anyone

Pass 9 recorded the European Commission shipping the **Age Verification Blueprint as working
software** (EUPL-1.2 / Apache-2.0, nine repos). Set that against this plane: the equivalent artefact
for *rating* does not exist anywhere. **The regulator published code for checking the user and
nothing for classifying the content** — even though the KIDS Act would impose duties on both.

The asymmetry is the opportunity. Checking the viewer is a solved, commoditised, well-funded problem
(age-assurance platforms are a multi-billion-dollar market; see `intel/market.md` pass 28). Rating
the title is unsolved, unfunded and about to be mandatory in two regions.

### T4 — Fourth mechanism for an empty agent layer: legal attribution of judgment

This KB has now explained empty agent layers four ways: regulatory burden (pass 3), closed content
licence (passes 5, 16), operating cost (pass 7) and — new here — **legal attribution**. A statutory
classification is an act attributed to a named party. `content classification agent MCP` returns
**literally nothing**; `OARS rating` returns **one repository in all of GitHub**.

**Generalisable rule for the other eleven industries:** before promising an agent, ask whether the
judgment it would make is one a *named party must sign*. If it is, the agent can prepare the
evidence, draft the declaration and check consistency — but a human or an institution issues it, and
the product is the **evidence pack**, not the decision.

### T5 — The open estate's deprecation debt is now measurable

Three findings in this plane are the same finding: **open rating data outlives the ladders it
describes, and nothing carries the expiry.** Jellyfin's `br.json` has a `9` rung that is not on
ClassInd's current ladder, inherited from an upstream entry flagged `Deprecated=true` whose flag did
not travel. The MovieLabs dataset's newest `LastChecked` anywhere is **2023-07-11**, with 25 of 110
systems carrying none at all and the **US/MPAA entry unvalidated since 2013**. AppStream's authority
is a Wikipedia article.

**The practical control:** any ratings table a client depends on needs a `validAsOf` date and an owner,
and a test that fails when it ages past a threshold. None of the open implementations has one. This is
a small, concrete, sellable piece of engineering hygiene — and it is the kind of thing that turns a
compliance finding into a maintenance contract.

### T6 — One ladder per medium, not one per country — and the open mapping gets this wrong

Measured in the dataset: Germany carries **three** systems (`USK` for games, `FSK` for film, `FSF`
for broadcast); the UK carries `BBFC` for film while AppStream maps `GB → PEGI`. A film catalogue
rated through the games mapping is **wrong in Germany and wrong in the UK**. Any client-facing model
must key ratings by `(territory, medium, system)` — and the open estate keys them by country alone.


## Pass 29 (2026-11-26) — the interactive, branching & playable-story plane: what is actually changing

### 1. The buyer left before the technology did — and that is the whole story of this plane

Netflix removed most of its interactive titles on **2024-12-01** and the final two — *Black Mirror:
Bandersnatch* and *Unbreakable Kimmy Schmidt: Kimmy vs. the Reverend* — on **2025-05-12**, stating
that the interactive-TV technology "served its purpose, but is now limiting as we focus on
technological efforts in other areas". The pivot was to games, where branching fiction continues
inside *Netflix Stories* as downloaded games rather than as a watched video stream. Some Bear Grylls
interactive specials returned as **linear** cut-downs.

Read what that implies, because it is unusual: the open-source substrate for this plane is *healthier
than the commercial channel*. 190,000+ stars of permissive narrative tooling, pushed daily, serving a
format the largest streamer publicly abandoned. **Any 2026 proposal that opens with "interactive
video for a streaming service" is pitching into a category its biggest buyer exited.** The same
components are worth real money pointed elsewhere; see patterns 29.1–29.6.

⚠️ **Source hygiene:** an SEO page claiming a 2026 "interactive boom", a "400% engagement increase"
and a "Branch Manager 2.0" could not be corroborated by any Netflix statement or major outlet. Do not
quote it. It is exactly the kind of fabricated revival narrative this plane attracts.

### 2. The money moved from interactive *video* to interactive *characters*

The commercial energy in 2026 is in real-time digital humans, and it is overwhelmingly APAC-origin
and permissively licensed: [lipku/LiveTalking](https://github.com/lipku/LiveTalking) (Apache-2.0,
11,338★, pushed the day of this pass, **supports being interrupted mid-sentence**),
[datascale-ai/opentalking](https://github.com/datascale-ai/opentalking) (Apache-2.0, 3,421★),
[HumanAIGC-Engineering/OpenAvatarChat](https://github.com/HumanAIGC-Engineering/OpenAvatarChat)
(Apache-2.0, 3,907★). `digital human interactive` returns 314 repositories;
`second screen companion tv` returns **2**. That ratio is the trend in one line.

The licence trend inside it is the warning: the two highest-starred avatar runtimes —
`duixcom/Duix-Mobile` (8,362★) and `Tencent-Hunyuan/HunyuanVideo-Avatar` (2,226★) — are **both**
under bespoke community licences, not OSI licences.

### 3. Disclosure duties now attach to the *character*, not just the content

Three regimes landed within one year, and they bite hardest exactly where this plane operates — a
synthetic performer that improvises:

- **EU:** AI Act Article 50 transparency obligations applied from **2026-08-02** (Commission guidance
  **2026-07-21**); the amending regulation the Council approved on **2026-06-29** gives systems
  already on the market until **2026-12-02**. The duty reaches production companies and rights
  holders *deploying* AI to generate or manipulate content, and reaches non-EU businesses whose
  content is distributed in the EU.
- **Korea:** the **AI Basic Act**, live **2026-01-22**, is described as the first in Asia to impose
  mandatory disclosure on AI-generated *or AI-assisted* content, reaching global services counting
  Korea as a market (Webtoon, Tapas, Tappytoon), with watermark disclosure under a **one-year grace
  period** for webtoon creators and platforms.
- **LATAM:** Mexico published amendments to the Federal Copyright Law and Federal Labour Law on
  **2026-05-14** — its first sector-specific AI rules — and Brazil's CONAR extended its 2026
  influencer guidance to **avatars, virtual profiles and AI-generated content**, including child
  participation and transparency duties.

**The branching case is the unsolved one.** Disclosure regimes assume a *fixed* work that can carry a
label. An interactive experience generates a path per viewer, and an AI character generates lines that
existed nowhere at publication. Nothing in the open stack emits a per-path or per-utterance
disclosure record. That is a product, and it is unbuilt.

### 4. Authoring consolidated on two languages, and both are MIT

`ink` (5,067★) and Yarn Spinner (2,883★) have become the de-facto pair — ink for branching prose
structure, Yarn for screenplay-shaped dialogue — each with engine bindings maintained separately
(`inkjs` 673★, `godot-ink` 793★, `YarnSpinner-Unity` 856★). Both MIT. For a studio, this is the rare
case where **the standard question has a safe answer**: pick ink for structure-heavy narrative, Yarn
for performance-heavy dialogue, and neither choice creates licence exposure.

The tooling *around* them is the weak point: the only open node-graph design tool,
[mhgolkar/Arrow](https://github.com/mhgolkar/Arrow) (MIT, 1,378★), has not been pushed since
**2025-09-05**, and the in-editor Unity option, `radiatoryang/merino`, has been **archived since
2021**. Writers get a language; they do not get a maintained GUI.

### 5. The narrative-QA agent is the clearest unbuilt product in the plane

A branching story is a graph, and graphs have coverage. [chaoz23/inkcheck](https://github.com/chaoz23/inkcheck)
(MIT, 2★, pushed 2026-10-26) already compiles an ink story, **playtests every branch exhaustively**
and reports dead content. Six MCP servers touch narrative at all and sum to **36 stars**. Meanwhile
the substrate carries 190,000+. The capability gap in this plane is not generation — it is
**verification**: dead ends, unreachable nodes, contradictory state, and branches that break a
territory's age rating (the pass 28 junction, unbuilt on both sides).

### 6. Visual novels are the format that never stopped working — and the open source is APAC's

While interactive video collapsed, the VN format kept shipping: `renpy` (MIT, 7,065★, pushed
2026-11-26), `WebGAL` (MPL-2.0, 4,054★), `VoidNovelEngine` (MIT, 1,715★), `dialogic` (MIT, 6,194★).
Two of the four are CN-origin with bilingual documentation. `visual novel engine` returns 1,204
repositories — six times `object based media` (187) and 600× `second screen companion tv` (2). The
format with no broadcaster, no standard and no platform deal is the one with a living ecosystem.

### 7. Interactive narrative is where "AI slop" is most visible, which raises the value of structure

EY's 2026 M&E read is that AI is accelerating volume, speed and personalisation while **flattening**
content, making credibility and emotional resonance more valuable; McKinsey expects growth in more
immersive, personalised and participatory entertainment. Both point the same way for this plane: the
differentiator is **authored structure** — a graph a human designed, verified and signed off — with
AI filling performance, localisation and variation inside it. That is also the only version of this
plane that survives a disclosure audit, because the structure is reviewable.

---

## Pass 30 (2026-11-26) — the discovery trend: the click is disappearing faster than any replacement arrives

### The one-paragraph version

Search referrals to publishers are collapsing at measured double-digit rates, AI referrals are
replacing **approximately none** of them, and the dominant AI surface emits no click to count. This
is not a channel shift. **A channel shift would show up as substitution, and the substitution is not
in the data.**

### The numbers, with their sources and their disagreements

| Measurement | Source | Period |
|---|---|---|
| Search referrals **−60% small / −47% medium / −22% large** publishers | **Chartbeat** (via Axios, 2026-03-17) | over two years; "small" = <10,000 daily page views |
| Global publisher Google traffic **down by a third**; Discover **−21% YoY**, search **−33%** | **Press Gazette** | to Nov 2025 |
| Regional split: **US −38% vs Europe −17%** | Press Gazette | 2025–26 |
| Publishers forecast search traffic **−43% over three years**; a fifth expect **>75%** losses | **Reuters Institute** survey | 2026 |
| **ChatGPT = 0.02% of total referral traffic** | **Reuters Institute** | 2026 |
| **All AI platforms combined ≈ 1% of publisher traffic** | Conductor | 2026 |
| UK: news publishers **−5% average quarterly** vs **−18%** consumer/B2B | **AOP** (8 leading UK publishers) | Jul 2026 |
| 25.11% of Google searches triggered an AI Overview | Contently | Q1 2026 — *recorded in this file at pass 7; re-stated for continuity* |

**Read the 0.02% and the 1% next to the −60%.** That juxtaposition is the whole trend: the inbound
channel is being withdrawn and nothing is arriving in its place. Any client deck that frames AI
search as "a new traffic source to optimise for" is mis-stating the measured position. The honest
framing is **loss mitigation plus direct-audience substitution** — which is why this plane routes
straight into pass 13 (subscription/reader revenue) and pass 24 (owned channel) rather than standing
alone.

⚠️ **Google disputes the causality**, and the KB should carry the dispute rather than suppress it:
Google states that data linking referral declines to AI Overviews is *"often based on flawed
methodologies, isolated examples, or traffic changes that occurred prior to the roll out of AI
features in Search."* Note also that the figures above use **different baselines, windows and
publisher mixes** and are not directly comparable. The defensible claim is the **direction and rough
magnitude**, not any single percentage.

### The instrument that appeared in June 2026 — and what it refuses to tell you

Google launched **Search Generative AI performance reports** in Search Console (announced
**2026-06-03**, since rolled out to all sites worldwide):

- Covers **impressions inside AI Overviews, AI Mode and generative features in Discover**
- Breakdowns by **pages and countries**; the Search report adds **devices**
- Data begins **2026-05-18**, with **no historical backfill** — nobody can measure their own
  pre-AI baseline from this instrument
- **Impressions, not clicks.** It shows where your pages appear inside AI features and **not how many
  clicks those appearances produced**
- Page-level impressions **do not sum** to the property total
- Position reflects **where the AI block sat on the page**, not where your link sat inside the block
- Opt-out exists and is **total**: excluded content gets no traffic and no impressions. It is
  **separate from `Google-Extended`**, which governs training

So the industry's authoritative new instrument measures **appearance** and is structurally silent on
**value**. That silence is the plane.

### The structural law — sixth confirmation, and the most extreme terminal step yet

Pass 5 recorded a three-step gradient on the *reservation* side. Pass 30 is the same gradient on the
*discovery* side, and its final step is worse than any previously recorded:

| Step | Problem type | State |
|---|---|---|
| **Be readable** by an engine | format | ✅ **Solved, permissive, thriving** — MarkItDown MIT 198,609★, Docling MIT 71,109★, Crawl4AI Apache-2.0 87,986★, Trafilatura Apache-2.0 7,182★ (375,000★+, nearly all pushed within three weeks) |
| **Declare** yourself via the purpose-built standard | format | ❌ **Measured dud** — `llms.txt`: Google says Search does not use it; **97% of files got zero traffic** (Ahrefs, 137,210 domains); leading generator **unlicensed and dormant since 2025-06-17** |
| **Count** the referral | judgment | ⚠️ **Partial, licence-trapped** — `referer-parser` `chatbot:` = **9 entries vs `search:` 232**, and the data is **GPL-3.0 by provenance** |
| **Measure** the dominant surface | — | ⛔ **Structurally impossible.** AI Overviews/AI Mode serve from `google.com`: **no referrer, no click.** Impressions only, UI-confirmed, API unverified |
| **Liquidate** the value | judgment | ⛔ **Nothing.** No open tool turns an AI impression into money. ChatGPT referrals = **0.02%** |

Five previous passes recorded planes whose terminal step had **zero code**. This is the first plane
whose terminal step has **zero measurable event**. You cannot write the settlement software for an
interaction that emits nothing — which is the precise, technical reason the pay-per-crawl zero that
pass 5 measured has not moved.

### The 2026 industry frame this sits inside

Akamai's *State of AI in Media 2026* argues adoption is no longer the question — converting
experiments into **business value** is; Sensor Tower measured time spent in gen-AI apps **doubling**
between H1 2025 and H1 2026. TV Tech's panel calls 2026 the year of **scaling** AI across media
enterprises and expects **several false starts in agentic advertising**. Deloitte's 2026 outlook has
gen-AI lowering content-creation barriers, with more than half its predictions tied to AI. EY reads
AI as accelerating volume and personalisation while **flattening** content, making credibility and
emotional resonance more valuable — which, for this plane, is the argument for **attribution as a
product**: if everything is abundant, being *identifiably the source* is the scarce asset. Reuters
Institute expects news media squeezed further; Nieman Lab frames the year as opportunity-and-threat.
DPP's *European Media Trends 2026* names AI the dominant driver of change and records rising
**digital-sovereignty** concern — the EMEA-specific reading in `intel/market.md`.

## 41. The seventh plane, the seventh identical result — and this time the gated content is a *device definition*

Pass 31 measured the live-event, show control and stagecraft plane. The structural law this KB has
been testing since healthcare holds again, and it has now been confirmed in seven consecutive planes:

**The regulator or the standards body creates the obligation; the licence of the knowledge content
decides whether open source can meet it.**

Here the shape is unusually clean, because the gated content is not a code set or an identifier
registry — it is the **machine-readable description of a physical device**:

- **The format is genuinely open.** GDTF is recognised as **DIN SPEC 15800:2022**. Its parsers are
  **MIT** (`pygdtf` 16★, `pymvr` 19★), its visualiser is GPL-3.0 (`blender-dmx` 291★).
- **The library is gated.** GDTF Share requires a **free account with no anonymous download path**,
  and each manufacturer publishes its fixture files **under its own terms**.
- **The only ungated channel is Open Fixture Library** (MIT code, 274★) — and the licence of its
  fixture *data* is unstated in the repo.

A lighting console with no fixture definitions can set channel 37 to 128. It cannot point a specific
manufacturer's moving head at a specific angle. **The code is free and the knowledge that makes the
code useful is registration-gated** — identical in shape to CPT in healthcare, MedDRA in
pharmacovigilance, and ISRC/ISWC/EIDR in pass 5. Seventh plane, seventh identical result. **The law is
now the single most generalisable finding in this KB, and it should be the first question asked in any
of the twelve industries: not "is there open code", but "who owns the content the code consumes".**

## 42. A licence can forbid modification outright — the worst instance of the compilation law yet

Pass 8 established that a licence can be a property of the **compilation** rather than the repository
(Chromaprint: MIT code that is LGPL-2.1 as a whole). Pass 31 found the severe case.

[FalconChristmas/fpp](https://github.com/FalconChristmas/fpp) — 747★, pushed the day before this pass
— reports `NOASSERTION`. Its `LICENSE` is a **manifest**: the core is LGPL-2.1-or-later, other parts
are GPL-2, and **some components are CC-BY-ND and "may not be modified and redistributed."**

**CC-BY-ND inside a 747-star "open source" project is stricter than any copyleft in this KB.** GPL
demands you share your changes; **ND forbids the changes.** And modification is exactly what a client
engagement is. No SPDX field, no badge, no source-tree SBOM scan surfaces it — only reading the file
does, and the file does not look like a licence.

Two further licence categories arrived in the same pass, taking this KB's taxonomy to **thirteen**:

- **EUPL-1.2** — `wled/WLED`, 19,132★, the most-starred repo in the plane. Copyleft, drafted by the
  European Commission, **governed by EU law**. First EUPL repo recorded here. For an EU client,
  unremarkable; for a US or APAC client embedding it, the governing-law clause is a pre-build question.
- **MIT + CLA** — `bitfocus/companion`, 2,376★. `LICENSE.md` **Part 1** is plain MIT; **Part 2** is a
  Contributor Licence Agreement granting the vendor a perpetual, transferable, **sublicensable**
  copyright licence over contributions. Benign for *use*; material for a consultancy that contributes
  upstream on a client's time. This is a second distinct reason the API reports `NOASSERTION` — and it
  means **`NOASSERTION` is not a warning sign, it is an instruction to read.** Across passes 8, 30 and
  31 it has concealed: a stricter whole-work licence, a missing licence, a British-spelled filename, a
  grant in `COPYING`, a CLA, and a no-derivatives component.

## 43. Web search cannot find an industrial plane — and the failure mode is newborn repos, not phantom ones

Pass 30's lesson was that listicle-driven research invents **plausible slugs that do not exist**. Pass
31 found the sharper failure, and it is the more dangerous of the two because the rows it produces
*verify*.

Four web searches for open-source lighting and show-control software returned **six candidate
repositories**. Verified against the GitHub search API:

- **Stars: 0, 0, 1, 1, 1, 6. Created: all within the previous seven weeks. Forks: zero, all six.**
- **One of them does not exist** (`ciechomir/BlindCUE`, returned with a near-identical description to
  a repo under a different owner).

And the same searches named **none** of: `bitfocus/companion` (2,376★), `benkuper/Chataigne` (1,718★),
`mcallegari/qlcplus` (1,593★, Apache-2.0, pushed the day before the pass), `OpenLightingProject/ola`
(773★), `xLightsSequencer/xLights` (768★), `mapmapteam/mapmap` (731★) or `wled/WLED` (19,132★).

**A pass that trusted the search layer would have produced eight rows that all pass a `ls-remote`
check, all have real licences, and are collectively worthless** — while missing the only fully
permissive production lighting console in this entire KB. The reason is structural: a repository
created last month is written to be discovered, and twenty-year-old infrastructure is not.

**The rule, and it costs one API call per organisation:** in any plane with real industrial tooling,
**source candidates from the GitHub search API by organisation, not from web search**, and gate every
row on **stars + `created_at` + `forks_count` together**. Stars alone would have passed `typoirl/Lumora`
(6★); `created_at` alone would have failed `qlcplus` (old) and passed nothing useful. The conjunction
is what works. Two name collisions in this plane make the same point from the other direction:
`TheCraftedTech/opencue` (1★ DMX console) vs `AcademySoftwareFoundation/OpenCue` (1,010★ render farm,
already in this KB), and `raydeoliveira/luxdmx` (0★, open-core) vs `tombueng/LuxDMX` (104★,
Apache-2.0). **Match on the full `owner/name`, never on the name.**

## 44. The first paywalled MCP tool surface — and it is invisible to a read-only evaluation

`raydeoliveira/luxdmx` exposes DMX control as an MCP server in which **read-only and dry-run tools are
free, while live apply and atomic scene execution require a paid Pro licence.**

This is the first time this KB has measured **per-tool commercial gating inside an MCP server**, and it
defeats the obvious evaluation method. An agent harness that probes a new MCP dependency with safe,
read-only calls — which is exactly what a careful engineer does — will record the server as working,
and will meet the wall in production on the first call that changes something.

**The rule, and it applies to all twelve industries, not just media: when evaluating any MCP
dependency, test the write path.** Open-core has arrived at the tool-surface level, where the licence
file does not describe it and the tool list does not distinguish it.

## 45. This plane breaks the KB's platform rule — the most complete platform in it is Apache-2.0

This KB's standing finding, stated in `repos/foundations.md` and reconfirmed across a dozen planes, is
**permissive at the pipeline, copyleft at the platform**: the interchange and standards layer is
Apache/BSD/MIT, and anything turnkey is GPL or AGPL.

Pass 31 is the clearest counter-example found so far. **QLC+ (`mcallegari/qlcplus`, 1,593★) is a full
production lighting console — patching, cue lists, effects, virtual console, GDTF import — under
Apache-2.0, and it was pushed the day before this pass.** A client can embed, rebrand and ship it
without a copyleft conversation. Pass 17's "one MIT platform breaks the rule" (trend 10) was the first
exception; this is the second and the stronger one, because QLC+ is not a thin platform.

The rest of the tier behaves as the rule predicts (Chataigne GPL-3.0, xLights GPL-3.0, Linux Show
Player GPL-3.0, MapMap GPL-3.0, BlenderDMX GPL-3.0), so the rule survives — but it is now a tendency
with two named exceptions rather than a law, and **both exceptions are worth more commercially than
the rule's compliant cases**, precisely because permissive platforms are rare. **When an exception
appears, it is the lead, not a footnote.**

## 46. The standards layer of a whole industry is a 44-star repository, published by the incumbent

Every modern lighting rig on earth is controlled over **ANSI E1.31 (sACN)**. The reference
implementation is [ETCLabs/sACN](https://github.com/ETCLabs/sACN): **Apache-2.0, 44 stars**, pushed
2026-11-16, maintained by **Electronic Theatre Controls** — the market-leading console manufacturer.
Device discovery (E1.33, RDMnet) is 56 stars. The RDM message helper is 11.

This is precisely Netflix's posture in the generative tier of this KB — publish the measurement and
delivery standards (VMAF, Photon/IMF), keep the product — at **one-hundredth of the star count**. And
ETC adds a governance signal worth reading: **every repository it publishes that is a *tool* rather
than a *standard* has its description prefixed "UNOFFICIAL"** (`OSCRouter`, `Sound2Light`,
`ETCDmxTool`, `EosSyncLib`, `lighthack`). The manufacturer open-sources what it must interoperate on
and disclaims the rest in the shop window.

**Two consequences.** First, star count is worthless as a proxy for load-bearingness in an industrial
plane — a 44-star repo here carries more production weight than a 100,000-star agent framework.
Second, the **agent opportunity is on the inventory side**: E1.33/RDMnet makes a rig enumerable and
configurable over IP, it is Apache-2.0, and nothing in the eight-project agent layer uses it. An agent
that reads what is *in* a rig and reasons about it has a permissive substrate from the incumbent and
no competition. See `compose/patterns.md` pattern 31.2.

## Pass 32 (2026-11-27) — the device, TV-app & client-playback plane: what is actually changing

## 47. A licence can forbid *consulting* by name — the worst licence finding in this KB for Globant specifically

Pass 26 recorded licences that collide with DRM; pass 31 recorded one that forbids modification.
This pass found the one that matters most to a services business.
[`cta-wave/device-observation-framework`](https://github.com/cta-wave/device-observation-framework)
(1★, pushed 2026-10-14) — the component that turns playback observations into a **pass/fail
verdict** — is Apache-2.0 **plus a Commons Clause** rider. Its grant excludes *"the right to Sell
the Software"*, and defines "Sell" as providing to third parties *"for a fee or other consideration
(including without limitation fees for hosting or consulting/ support services related to the
Software), a product or service whose value derives, entirely or substantially, from the
functionality of the Software."* Licensor: **Consumer Technology Association**. Contributor:
**Resillion UK Limited**, a commercial test house.

Every licence trap this KB has recorded until now could be engineered around: AGPL by not hosting,
BSL by waiting out the clock, Llama by checking the acceptable-use list, GPL by not linking. **This
one has no engineering answer** — the prohibited act is *billing a client for a service built on
it*, which is the business. The surrounding repos (`dpctf-tests`, `dpctf-test-runner`,
`dpctf-deploy`, `Test-Content*`, `mezzanine`) are all plain BSD-3; a sweep of four siblings found
**zero** further Commons Clause hits. So this is not an org policy — **it is a deliberate fence
around the verdict**, placed by a standards body with a test house as contributor.
**Operational rule for all twelve industries: grep every incoming `LICENSE` for `commons clause`.**
No SPDX field, licence badge or source-tree SBOM scan can see a prose rider.

## 48. The open-source gradient now has a measured number: ~1,400 to 1 from decoding to deciding

This KB has recorded eleven times that formal work attracts open implementations and judgment work
does not. This plane lets the law be *measured*, because all four layers sit in one supply chain:

| Layer | What it decides | Stars | Licence shape |
|---|---|---|---|
| Players (`video.js`, `hls.js`, `shaka-player`, `dash.js`) | nothing — it decodes | **71,173** | Apache-2.0 / BSD-3, all pushed within 4 days of this pass |
| TV app frameworks (`enact`, `blits`, `zombiebox`, RDK; excl. `react-native-tvos`) | layout and focus | **~1,421** | Apache-2.0 / MIT, maintained |
| Regional broadcast middleware (ORB, HbbTV, DVB-I, Hybridcast, Ginga, openBA) | territory conformance | **432** | MIT-heavy, **half dormant 1–8 years** |
| Device certification (`dpctf-*`, WAVE, `ott_device_matrix`) | **pass / fail** | **51** | BSD-3 — except the verdict, which is Commons-Claused |

**Decoding a video is 1,400× better served by open source than deciding whether it played
correctly.** And at the exact point where judgment becomes a billable verdict, the licence turns
commercial. This is the cleanest confirmation the content law has had, and the first one where the
gradient is a single number from one plane's own repository list.

## 49. Star count has become actively misleading — two deprecations prove it in one plane

Two of the four largest repos in this plane are dead or dying, and both outrank their own successors:

- [`sampotts/plyr`](https://github.com/sampotts/plyr) (MIT, **29,977★**) now describes itself as
  *"Deprecated in favour of Video.js 10; security updates only."* The beneficiary,
  [`videojs/video.js`](https://github.com/videojs/video.js) (40,260★), has rebranded from "player"
  to **"Video.js v10 — media player framework for HTML and React."**
- [`google/ExoPlayer`](https://github.com/google/ExoPlayer) (**21,935★**) is *"deprecated and
  stale"* by its own description, last pushed 2025-12-23. The live engine is
  [`androidx/media`](https://github.com/androidx/media) (**3,094★**) — **7× fewer stars, and it is
  the only correct answer** for Android TV / Fire TV.

Add the archived [`react-tv`](https://github.com/raphamorim/react-tv) (2,033★, dead 4.7 years) and
[`mautilus/sdk`](https://github.com/mautilus/sdk) (102★, dead 9.5 years), and **~54,000 stars in
this plane point at code nobody should start on in 2027.** → Read the `description` field and
`pushed_at`, never the star count. A proposal citing ExoPlayer or Plyr today is citing a tombstone,
and it will be read as such by any client engineer.

## 50. Every region runs a different interactive-TV stack, and each ships its own MIT reference client

The most Globant-relevant structural fact in this plane: **there is no global TV application
target.** EMEA runs **HbbTV 2.0.5** (published by the HbbTV Association 2026-03-02; ETSI TS 102 796
V1.8.1, September 2026) with **DVB-I** service lists; North America runs **ATSC 3.0 / NextGen TV**;
Japan runs **Hybridcast** (IPTV Forum Japan, STD-0010/0011); Brazil runs **TV 3.0 / DTV+** —
ATSC 3.0's physical layer with **Ginga** as the application layer. Four regions, four stacks, four
app models.

And each one published an open reference implementation, nearly all **MIT**: ORB and the HbbTV
Reference Application (EMEA), the DVB-I Reference Client (EMEA/global), NHK's four Hybridcast
Connect SDKs (APAC), Sinclair's OpenBA (NA), TeleMidia's Ginga (LATAM, GPL-2.0). Standards bodies
license permissively because they want adoption. **But six of the twelve have not been pushed in
over a year, and the NA and APAC artefacts are 4–5 years cold.** → The regional work is
*specification compliance*, not SDK integration, and it is **repeated per region** rather than
abstracted. That is billable scope, and it is the reason a pan-regional CTV engagement cannot be
quoted as one build.

## 51. The steering brain is unbuilt, the telemetry vocabulary is standardised, and the metrics spec has been dormant since 2019

Everything needed to optimise delivery is specified and permissive: **CMCD** (CTA-5004,
[35★](https://github.com/cta-wave/common-media-client-data), **no licence file**), **CMSD** (25★, no
licence file), SVTA's [`common-media-library`](https://github.com/streaming-video-technology-alliance/common-media-library)
(Apache-2.0, 86★, pushed 2026-11-23), [`OC-API`](https://github.com/streaming-video-technology-alliance/OC-API)
(MIT, 4★), and content-steering support inside hls.js / dash.js / shaka-player themselves. dash.js
v5 has begun emitting **CMCD v2** keys (`ltc`, `msd`), and a shaka-player PR implements the CMCD
parameters of **ISO/IEC 23009-1:2026 Annex K** so a DASH manifest can configure reporting — that PR
was **open, not merged**, when checked.

What does not exist: **any public open-source multi-CDN steering implementation.** Four slugs
probed, four 404s. The SVTA's own pages and an IBC paper describe a client-side switcher library and
an open steering framework; neither has a locatable public repo as of 2026-11-27. Meanwhile
[`cta-wave/R4WG20-QoE-Metrics`](https://github.com/cta-wave/R4WG20-QoE-Metrics) (28★) — the
industry's QoE metrics definition — **has not been touched since 2019-03-04, 7.7 years.**
→ **The nervous system is standardised and free; the brain is a product nobody has shipped openly.**
An agent that consumes CMCD and decides steering has a permissive substrate, a dormant metrics spec
to revive, and no open competition. See `compose/patterns.md` pattern 32.2.

---

## Pass 33 (2026-11-27) — the sixth confirmation of the structural law, and the cleanest three-step gradient yet measured

**The law, as this KB has stated it since cycle 8:** in media, *format* problems get permissive,
actively-maintained open source; *judgment* problems get dormant repos, copyleft, or nothing. This
plane — media monitoring and earned-media measurement — splits into three steps that can be dated
precisely, and the gradient is monotonic.

### Step 1 — COLLECT (a format problem): permissive, and committed the day of this pass

| Repo | Licence | Last commit |
|---|---|---|
| [dgtlmoon/changedetection.io](https://github.com/dgtlmoon/changedetection.io) | Apache-2.0 | **2026-11-27** |
| [DIYgod/RSSHub](https://github.com/DIYgod/RSSHub) | AGPL-3.0 | **2026-11-27** |
| [FreshRSS/FreshRSS](https://github.com/FreshRSS/FreshRSS) | AGPL-3.0 | **2026-11-27** |
| [huginn/huginn](https://github.com/huginn/huginn) | MIT | **2026-11-27** |
| [flairNLP/fundus](https://github.com/flairNLP/fundus) | MIT | 2026-11-26 |
| [miniflux/v2](https://github.com/miniflux/v2) | Apache-2.0 | 2026-11-26 |
| [ArchiveBox/ArchiveBox](https://github.com/ArchiveBox/ArchiveBox) | MIT | 2026-11-26 |
| [scrapy/scrapy](https://github.com/scrapy/scrapy) | BSD-3-Clause | 2026-11-25 |
| [apache/tika](https://github.com/apache/tika) | Apache-2.0 | 2026-11-25 |
| [adbar/trafilatura](https://github.com/adbar/trafilatura) | Apache-2.0 | 2026-11-23 |

**Four repos committed on 2026-11-27 itself.** Fetching, parsing and watching are solved to the day.

### Step 2 — INDEX (half a format problem): one organisation, one licence, a three-year split

| Repo | Licence | Last commit | Gap |
|---|---|---|---|
| [mediacloud/story-indexer](https://github.com/mediacloud/story-indexer) | Apache-2.0 | 2026-08-28 | ~3 months |
| [mediacloud/web-tools](https://github.com/mediacloud/web-tools) | Apache-2.0 | **2023-12-14** | **~3 years** |

Same org, same permissive licence. The **pipeline** is maintained; the **interface a human uses to
interpret the corpus** is abandoned. The split is not about licence or funding — it is about which
half is a format problem.

### Step 3 — MEASURE (pure judgment): dormant, non-commercial, or six days old

| Repo | Licence | Last commit | Status |
|---|---|---|---|
| [pysentimiento/pysentimiento](https://github.com/pysentimiento/pysentimiento) | ⛔ **non-commercial only** | **2024-06-20** | **~2.5 years dormant AND unusable commercially** |
| [fhamborg/NewsMTSC](https://github.com/fhamborg/NewsMTSC) | MIT (new files only) | 2025-07-18 | ~16 months dormant |
| [cjhutto/vaderSentiment](https://github.com/cjhutto/vaderSentiment) | MIT | 2026-03-02 | English-only lexicon |
| [Scognamiglio1969/radar-intelligence](https://github.com/Scognamiglio1969/radar-intelligence) | **AGPL-3.0** | 2026-09-17 | single maintainer |
| [Etipufhu/pr-radar](https://github.com/Etipufhu/pr-radar) | MIT | 2026-11-26 | **18 commits, created 2026-11-21** |

→ **The instruments that gather are maintained to the day. The instrument that decides what the
gathering means is 2.5 years old, licensed against commercial use, or a week old.**

**And the terminal zero, which is the sharpest in this KB after pass 5's settlement zero:** there is
**no open-source implementation of AMEC's Integrated Evaluation Framework at all** — not dormant, not
copyleft, *absent*. The industry's own measurement standard, free to adopt, with zero code behind it.

## Pass 33 — the measurement trend that dates this plane precisely

**Gartner published its first-ever Magic Quadrant for PR and Media Monitoring Tools on 2026-10-20.**
A first-edition Magic Quadrant is the single most reliable signal that a category has become a
budgeted procurement line rather than a discretionary tool purchase. Its abstract names three forces
reshaping the market: **AI visibility**, **evolving media-relations dynamics**, and
**outcome-based earned-media measurement**.

That third phrase is the whole opportunity. The industry is formally moving off **AVE** (advertising
value equivalency) — the metric that prices earned coverage as if it were bought advertising, which
the **Barcelona Principles** and AMEC have rejected since 2016 in favour of
**outputs → out-takes → outcomes → impact**, tagged across **PESO** (paid, earned, shared, owned).

**The asymmetry to exploit:** the *standard* is settled, public and free; the *implementations* are
all proprietary (Cision, Meltwater, Brandwatch, Truescope); and the *open-source substrate to build
one* is Apache-2.0 and committed today. ⚠️ Note Gartner's Leader placements are known here only via
**Meltwater's own press release**, a vendor source — cite the placement, not the ranking.

## Pass 33 — consolidation on the buy side

**Cision owns both Brandwatch and PR Newswire**, marketing the combined datasets as the broadest
source collection available. So one vendor holds the **wire** (distribution), the **clipping**
(monitoring) and the **social listening** (Brandwatch) tiers of the same workflow. Meltwater
positions as the all-in-one alternative.

For a media or brand client this is a single-vendor dependency across three functions that used to be
three purchases — and it is the strongest commercial argument for a self-hosted, permissively
licensed collection tier underneath whatever analysis vendor is chosen. **Own the corpus; rent the
analysis.** That inverts the current default, in which the vendor owns both.

⚠️ **Market-size spread, and an unusual result:** $6.1B (2026) → $14.4B (2034);
$5.7B (2025) → $13.8B (2034); $7.34B (2026) → $18.56B (2034). On a 2026 base that is a
**~1.20× spread — the *narrowest* headline disagreement recorded in this KB**, against pass 32's
~28× and pass 30's ~7.3×. Monitoring is an established software category with real seats and real
contracts, so the estimators broadly agree. Still vendor-sponsored research; quote the range.

---

## Pass 34 (2026-11-27) — the structural law gets a **five-step** gradient, and a refinement: **accreditability, not content licensing, is the binding constraint**

Pass 5 measured a three-step gradient (declare → honour → liquidate). Pass 33 measured another three
steps. **The ad-integrity plane yields five steps inside a single plane, and every number below was
verified on 2026-11-27.**

| # | Step | Kind of problem | Best open artifact | License | Stars | Last push |
|---|---|---|---|---|---|---|
| 1 | **Declare** who may sell the inventory | format | [10up/ads-txt](https://github.com/10up/ads-txt) + 8 more tools | GPL-2.0 | 61 | **2026-11-24** |
| 2 | **Prove** the declaration cryptographically | format + crypto | [IABTechLab/adscert](https://github.com/IABTechLab/adscert) | Apache-2.0 | **8** | **2023-07-05** |
| 3 | **Detect** invalid traffic | judgment, and the labels are the vendors' product | [Nameles-Org/Nameles](https://github.com/Nameles-Org/Nameles) | Apache-2.0 | 72 | **2019-09-06** |
| 4 | **Judge** brand suitability | pure judgment, no maintaining body | **nothing** | — | — | — |
| 5 | **Count** it so an auditor accepts it | accreditation | [OM-JSClients](https://github.com/InteractiveAdvertisingBureau/Open-Measurement-JSClients) (web only) | Apache-2.0 | 76 | 2026-11-02 |

Read the last column downward: **2026-11-24 → 2023-07-05 → 2019-09-06 → nothing.** Monotone decay as
the problem moves from parsing a file to forming a judgement someone else must accept.

### The refinement, and it matters more than the sixth confirmation would have

Passes 5, 11 and 33, and the healthcare CPT/MedDRA findings, pointed at a content-licence law: *the
regulator creates the obligation, the licence on the knowledge content decides whether open source can
discharge it.* **This plane partially falsifies the strong form of that law**, and the correction is
worth more than another confirmation:

- The content **is** open. The IAB **Content Taxonomy** — the exact vocabulary a brand-safety
  classifier needs — is **CC BY 3.0, free to implement commercially with attribution**
  ([InteractiveAdvertisingBureau/Taxonomies](https://github.com/InteractiveAdvertisingBureau/Taxonomies),
  229★, pushed 2026-10-27). So is OpenRTB (CC BY 3.0, 532★, 2026-11-11). So is the TCF spec.
- And brand-safety open source is **a literal zero.**

So the content licence was not the binding constraint here. **What stops open source on this plane is
accreditability: whether a third party must accept the number.** Three independent demonstrations
inside one plane:

1. **MRC accreditation (invalid traffic).** You can compute GIVT from MIT-licensed lists. You cannot
   make the result accredited. GIVT is required for MRC accreditation; SIVT is *strongly recommended*
   and not mandated — so even the paid, accredited tier does not have to catch the hard half.
2. **OM SDK compliance (viewability).** Web clients Apache-2.0 and public; **native iOS/Android/CTV
   library is a Tools Portal download inside a compliance programme.** The licence boundary and the
   accreditation boundary are the same line.
3. **CMP registration (consent).** `iabtcf-es` (Apache-2.0, 156★) gives the codec; a valid TCF string
   requires a **CMP ID issued by IAB Europe**. The most-starred consent UI in open source
   (`orestbida/cookieconsent`, MIT, 5,786★) cannot emit one. `consent management platform TCF` returns
   **six repositories in total.**

**Revised formulation, and the version to carry into the other eleven industries:** the regulator
creates the obligation; the licence on the knowledge content decides whether open source can *access*
the problem; and **accreditation decides whether open source can close it.** Where a number must be
*accepted* rather than merely *correct*, expect a literal zero, however open the spec and the
vocabulary are.

### The one number from this pass that belongs in every client conversation

| Query (GitHub, by stars, 2026-11-27) | Repos | Top-8 stars | Ratio |
|---|---|---|---|
| `bypass bot detection` — **the attack** | 245 | **18,425** | — |
| `bot detection library` — **the defence** | 91 | **2,461** | **7.5 : 1** |
| …including [CloakHQ/CloakBrowser](https://github.com/CloakHQ/CloakBrowser) (MIT, 33,093★, 2026-11-26) | — | **51,518** | **20.9 : 1** |

**Open source builds the evasion 7× to 21× more heavily than it builds the detection**, and the
evasion side is the fresher of the two: CloakBrowser, camofox-browser (12,507★), invisible-playwright
(2,616★), httpcloak (1,394★) and rebrowser-patches (1,475★) were all pushed within 25 days of this
pass, are all MIT, and are all built explicitly for **AI browsing agents**. The defence a publisher can
assemble from open source is user-agent and client-signal matching — exactly what these are built to
defeat. ⚠️ **No IVT proposal resting on open-source detection alone should go out without this table
attached.**

### The sophisticated half of the problem is now AI-generated, and the measurements disagree violently

| Source | Figure | Note |
|---|---|---|
| Lunio, *2026 Global Invalid Traffic Report* | **$63B** lost to IVT in 2025, against $740B+ ad spend | Click-based methodology; Augustine Fou argues publicly that this **undercounts**, because it counts invalid clicks arriving on sites rather than invalid *impressions*. |
| Juniper Research (via secondary source) | **>$100B in 2026**, ~$172B by 2028; ~22% of global digital ad spend | ⚠️ Secondary citation, not read at source. |
| Anura (via eMarketer) | **$165B** in 2025; global IVT **26% Jan → 31% Feb → 40% Jun 2026** | Vendor data. |
| Spider Labs | **$25.3B in H1 2026** | Half-year; not comparable to annual figures. |
| Fraudlogix / Q1 2026 programmatic | **18.1%–20.6%** of programmatic impressions invalid | |
| DoubleVerify | fraud/IVT **down 41% YoY in North America, down 45% in EMEA** | ⚠️ **Points the opposite way from Anura.** Both are vendors with commercial interest in the number. |

⚠️ **$63B to $165B is a 2.6× spread on overlapping periods, and two vendors disagree on the
direction of travel.** Quote the range, name the methodology, and note that every figure on this plane
is produced by a company selling the remedy. There is no MRC-accredited public market size.

## Pass 34 — the governance vacuum: the framework everyone uses has no owner, and cannot get one

- **GARM (Global Alliance for Responsible Media)** published the Brand Safety & Suitability Framework
  that the entire industry classifies against. The WFA **discontinued GARM in August 2024**, days after
  X sued it on antitrust grounds.
- X and the WFA **settled**, and multiple secondary sources report that as part of the settlement the
  **WFA agreed never to revive GARM or any similar initiative.** ⚠️ Settlement date reported
  inconsistently (July 2026 in one source); verify against the court record before citing a date.
- **Who maintains it now: nobody, and sources conflict on even that.** Some claim IAB Tech Lab absorbed
  it; others say only that the Tech Lab **Content Taxonomy** evolved to accommodate GARM's categories —
  which is a vocabulary, not a framework. Multiple sources state plainly that no body replaced it.
- **And it is still in use anyway.** IAS, DoubleVerify, Pinterest and YouTube continued on GARM's
  taxonomy after the shutdown "since it's impractical to start over."

**Why this is a trend and not trivia:** this is the first plane in 34 where the governing framework is
not merely unmaintained but **contractually un-revivable by its author.** The practical consequence for
delivery: a brand-safety engagement cannot be sold as conformance to a standard, because there is no
standard-keeper. It has to be sold as *the client's own documented suitability policy, implemented
against a CC BY 3.0 taxonomy, with the classifier as the deliverable.* That is a better consulting
engagement than certification work — and it is the only honest one available.

## Pass 34 — the method trend: licence metadata has now failed in four distinct ways

Cycle 8 found that a licence can belong to the **compilation** (Chromaprint: MIT code, LGPL-2.1 whole,
and a third layer in the linked FFT library). This pass adds three more failure modes, all found by
reading files rather than trusting fields:

1. **Prose-only licence.** `adstxtcrawler` (202★): no licence file under any of nine names — confirmed
   by shallow clone — API says `NONE`, README says *"license used is the 2-clause BSD license."*
   `Taxonomies` (229★): identical pattern, README says CC BY 3.0. **No SPDX field, licence badge or
   SBOM scan of the source tree can see a licence that exists only as a sentence.**
2. **Component-scoped licence.** `snowplow/snowplow` is Apache-2.0 (7,052★); `snowplow/enrich`, the
   component you deploy, is the **Snowplow Limited Use License Agreement v1.0** (31★). The brand-named
   repo is permissive; the shipped artifact is not.
3. **Directory-scoped licence.** `PostHog/posthog`: MIT Expat for everything **outside `ee/`**.
   `IABTechLab/OpenProposal`: Apache-2.0 granted to `scripts/` and `workflow/` only.

And the inverse error, which is just as expensive: **`NOASSERTION` is not a verdict.** `ua-parser/uap-core`
is Apache-2.0 and `kiprotect/klaro` is BSD-3-Clause; the API reports `NOASSERTION` for both because the
file opens with a non-standard header. **CI rule for all twelve industries: for every dependency, resolve
the licence of the component you ship, from the file, and grep the README when the field is empty.**

⚠️ **And the relicensing trap:** [faisalman/ua-parser-js](https://github.com/faisalman/ua-parser-js) is
**AGPL-3.0** at 10,217★, pushed 2026-11-26. Most teams remember it as MIT. In a hosted service the
network clause is live. Replacement: `ua-parser/uap-core` (Apache-2.0) plus a permissive binding.

## Pass 34 — the agent layer that is three weeks old, and the window that implies

`AdCP`, `ARTF` and `AAMP` were at **0 files** in this KB before today. The agentic-advertising layer is
**nine repositories holding 91 stars**, four of them pushed in November 2026, and for the first time in
34 planes **the standards body shipped the agent framework before the market shipped a product**:

- [IABTechLab/AAMP](https://github.com/IABTechLab/AAMP) — **Apache-2.0**, 28★, 2026-11-02.
- [IABTechLab/agentic-real-time-framework](https://github.com/IABTechLab/agentic-real-time-framework) —
  spec CC BY 3.0, **reference implementation AGPL-3.0**, 35★, 2026-11-04.
- [franks33/agentic-advertising-stack](https://github.com/franks33/agentic-advertising-stack) — CC0-1.0,
  4★: the fastest orientation map of the plane.

**Build on AAMP, not ARTF** — same body, same plane, Apache-2.0 instead of network copyleft. And note
the irony this plane now contains in full: the same industry is simultaneously standardising
**agent-to-agent ad buying** and failing to detect **agent-driven invalid traffic**, whose best tools
are MIT-licensed, 33,000-star stealth browsers built for AI agents. The buy side is being automated
faster than the integrity side can describe what automation looks like.

---

## Pass 35 (2026-11-27) — the graphics desk: trends in the one plane where open source already won

### Trend 1 — **The open stack is complete, so the spend moved to hosting.** This is the plane's defining economics

Thirty-four passes of this KB describe planes where the open tooling is partial and a vendor fills the
gap with capability. The graphics desk is the opposite: **every layer is permissive and actively
maintained** — D3 (ISC, 114,024★), Chart.js (MIT, 67,825★), ECharts (Apache-2.0, 67,808★), Vega-Lite
(BSD-3), Plot (ISC), Leaflet (BSD-2), MapLibre (BSD-3), mapshaper (MPL-2.0), OpenRefine (BSD-3),
Datasette (Apache-2.0), csvkit (MIT), Quarto (MIT). A newsroom can render anything it wants for free.

And newsrooms still pay, because **what they buy is not rendering — it is a hosted responsive embed
with an edit UI a non-developer can use on deadline.** Datawrapper's newsroom plans run roughly
**$33–$564/month**. No open-source project in this plane provides that, and the one that used to was
**archived in September 2021**.

The structural lesson generalises past media: *when a rendering substrate commoditises, value
migrates to the hosted workflow around it, not to the renderer.* Check it against the prior passes —
it is the same shape as transcoding (FFmpeg free, packaging-as-a-service paid) found in pass 8.

### Trend 2 — **Momentum inverted against reputation.** Sorting this plane by stars returns a museum

| Frozen and famous | Stars | Last push | | Active and invisible | Stars | Last push |
|---|---|---|---|---|---|---|
| [Quartz/Chartbuilder](https://github.com/Quartz/Chartbuilder) | 2,095 | **2017-09-13** | | [abcnews/chart-builder](https://github.com/abcnews/chart-builder) | **3** | **2026-11-27** |
| [idyll-lang/idyll](https://github.com/idyll-lang/idyll) | 2,044 | 2023-02-04 | | [ZeitOnline/scrolleo](https://github.com/ZeitOnline/scrolleo) | **9** | **2026-11-26** |
| [bbc/bbplot](https://github.com/bbc/bbplot) | 1,645 | **2021-07-02**, no licence | | [abcnews/odyssey](https://github.com/abcnews/odyssey) | **22** | **2026-11-26** |
| [newsdev/ai2html](https://github.com/newsdev/ai2html) | 969 | 2025-10-22 | | [tryopendata/openchart](https://github.com/tryopendata/openchart) | **35** | **2026-11-25** |
| [newsdev/archieml-js](https://github.com/newsdev/archieml-js) | 215 | 2021-11-12 | | [nprapps/interactive-template](https://github.com/nprapps/interactive-template) | **70** | **2026-11-25** |

Two different causes, and they need different responses. **Chartbuilder and Idyll are abandonment** —
a newsroom product and an academic format tool, both of which stopped when their funding or founder
did; fork them or avoid them. **ArchieML and TopoJSON are completion** — a text format and a topology
encoding, finished, with nothing left to change; a 2021 push there is stability, not rot. Telling the
two apart is the diligence step, and the test is simple: *does the artifact still do its whole job?*

### Trend 3 — **The AI layer has settled on "model proposes a spec, deterministic compiler renders it"**

Of the five NL→chart projects verified this pass, the architecturally correct one is also the smallest:
[yuqisun/chartwright](https://github.com/yuqisun/chartwright) (MIT, **0★**) has the agent emit a
library-agnostic **chart spec** and a deterministic compiler produce the config, so the model never
writes renderer code. [Canner/WrenAI](https://github.com/Canner/WrenAI) (Apache-2.0, 18,413★) applies
the same principle a layer down — natural language resolves against a **governed semantic layer**
before any SQL is emitted.

This is why **Vega-Lite (BSD-3-Clause) is the strategically important library of 2026** even at 5,566★
versus Chart.js's 67,825: it is a small, declarative, *validatable* JSON grammar, which makes it the
only mainstream permissive target an LLM can emit safely — you can reject a malformed spec before it
renders, which you cannot do with imperative D3. Note the inversion worth watching: **Altair, the
Python binding (10,522★), has 1.9× the stars of the grammar it binds.** The agent ecosystem is
arriving through Python, not JavaScript.

### Trend 4 — **The licence field is wrong often enough that reading it is negligence**

Resolved from files this pass, against an API that reported `NOASSERTION`: MapLibre GL JS → **BSD-3-Clause**;
Quarto → **MIT** (Posit); ai2html, archieml-js, elex → **Apache-2.0** (NYT); guardian/frontend →
**Apache-2.0**; mapshaper → **MPL-2.0**; and CJ Workbench → **AGPL-3.0** (Columbia University) — the
one case where the resolution makes the project *unusable* in a hosted client deliverable rather than
usable. Two repos resolved to **nothing at all**: `datawrapper/datawrapper` (1,465★) and `bbc/bbplot`
(1,645★) have no licence file on any branch checked. **Three thousand stars of apparently-open
tooling with no grant behind it**, and both are routinely recommended in 2026 newsroom guides.

### Trend 5 — **Election graphics are the plane's hard commercial edge, and open source has retreated from it**

In the cycle where **ABC, CBS, NBC and CNN all moved to AP's tabulation data for the 2026 and 2028 US
elections**, the only open-source client for that feed —
[newsdev/elex](https://github.com/newsdev/elex) (Apache-2.0, 169★) — sits **archived since
2022-09-07**. The free alternatives that appeared (civicAPI, Open America's JSON feed) are **hosted
services, not repositories**: no licence, no self-host, no SLA. So the most consequential graphic any
newsroom publishes rests on a commercial feed with no maintained open client — while the *display*
layer above it (D3, MapLibre, TopoJSON, PMTiles) is entirely free. **The data is the moat; the chart
never was.**

## Pass 36 (2026-11-27) — the 2D animation plane: four trends, and the law gets its cleanest proof

### Trend 1 — the structural law now has a four-step gradient inside one plane, measured on one day

Five previous passes established that the licence of the *knowledge or registry content* — not
regulatory pressure — decides whether open source can do a job. This plane proves it without needing a
second industry for contrast, because all four steps of one craft are measurable at once:

**play** (format) → ~100,000★ of MIT/Apache runtimes, several pushed today;
**draw** (tool) → healthy but 7-of-9 copyleft, permissive only in the Toonz lineage;
**inbetween** (judgment) → **55 repos in all of GitHub**, top result 373★ **unlicensed**;
**schedule** (owned registry) → **six repos, 32★ combined**, public spec frozen at **November 2018**.

The gradient is monotonic and it is the sixth independent confirmation. The refinement this pass adds:
**the collapse is driven by who owns the artefact, not by how hard the problem is.** Inbetweening is
genuinely hard and has 55 repos; the exposure sheet is trivially easy — JSON with a text header — and
has six. Difficulty predicts nothing; ownership predicts everything.

### Trend 2 — the demand pull is landing exactly on the unlicensed step

IMARC's account of Japanese production has AI-assisted work becoming mainstream in **background art,
in-between frames and quality control**, explicitly because of timelines and a labour shortage. Two of
those three are well served by permissive open source (background/upscale: `waifu2x` MIT 28,239★,
`style2paints` Apache-2.0 18,143★; QC/segmentation: `anime-segmentation` Apache-2.0). The third — **the
in-between** — is served by `AnimeInbet` (373★, **no licence**), `FCVG` (120★, **no licence**),
`AnimeInterp` (465★, **licence in README prose only**) and `ToonCrafter` (Apache-2.0, 6,071★, **unpushed
since 2025-03-19**).

**The falsifiable prediction this pass records:** if the demand is real, the gap closes from the
*permissive* side within 12 months — either ToonCrafter resumes, or a new Apache/MIT line-inbetweening
model passes 1,000★ before 2027-11-27. If instead the 2026 state persists, the conclusion is that
inbetweening is being absorbed by **closed** vendors and studios' internal tools, and the open stack
will never hold the plane's most expensive operation. Checkable with one query.

### Trend 3 — the newest permissive platforms in this plane are Chinese, and they are platforms, not models

The two largest openly-licensed AI animation production systems found in this pass were **both created
in 2026 and both target China's 短剧/漫剧 vertical-video market**: Toonflow (**MIT, 22,960★**, created
2026-01-29) and Jellyfish (**Apache-2.0, 7,353★**, created 2026-03-06). They are not weights releases —
they are script→storyboard→asset→video *pipelines* with production UIs.

This inverts the pattern the KB recorded in earlier media passes, where APAC supplied **models**
(Wan, CogVideoX, HunyuanVideo) and the West supplied **tooling**. Here APAC supplies the tooling too,
permissively, at a scale no other region matches in this plane. Any 2026 claim that the open AI
animation stack is Western is simply false, and the two repositories settle it.

### Trend 4 — the method trend: licence metadata has now failed in **six** distinct ways

Pass 34 recorded four failure modes. This plane adds two more, and one of them inverts the risk direction:

| # | Failure mode | Canonical example from this pass |
|---|---|---|
| 1 | Licence of the **compilation**, not the repo | `chromaprint` — MIT code, LGPL-2.1 as a whole, plus the linked FFT library's terms (pass 5) |
| 2 | **Naming convention** defeats the probe | `Panako` → `license.txt`; `musicbrainz-server` → `COPYING.md` (pass 5) |
| 3 | Published standard repo with **no licence at all** | `rslstandard/rsl` (pass 5); here, **`lottie/lottie-spec`** — the Lottie spec repo, 120★, no licence file resolving under 13 names while `README.md` returns 200 |
| 4 | Licence present but **archived/dead** project | `enve` (GPL-3.0, archived 2022); `SVGAPlayer-Android` (Apache-2.0, archived 2023) |
| 5 | **`EULA.txt`** — a 13th name, and the first failure that points the *dangerous* way | **`aseprite/aseprite`, 41,192★**: no `LICENSE`/`COPYING` under 12 names, terms sitting in `EULA.txt` on both branches. Every earlier miss made a permissive repo look unlicensed (safe); this makes a **forbidden** repo look merely unlicensed |
| 6 | **Grant exists in prose only** — the inverse of #1 | **`AnimeInterp`**: no licence file, API reports NONE, README says *"released under MIT License"*. Same shape: **`ebsynth`** (1,695★), README says *"released into the public domain"* |

Consolidated rule for CI and for any proposal gate: **the SPDX field is a hint, never an answer.**
Resolve a licence by reading the repository's own file (13 names × `master`+`main`), then the README if
no file exists, then the terms of anything the build **links** against. `NOASSERTION` means *the parser
gave up* — in this plane it flagged four permissive repos (`opentoonz`, `tahoma2d`, `xdts_viewer`,
`rhubarb-lip-sync`: BSD-3 ×3, MIT ×1) whose files simply open with third-party notices.

### Trend 5 — labelling duties are now in force in the two largest producing markets, and they do not match

Korea's **AI Basic Act took effect 2026-01-22** (AI-content labelling, advance notice for generative and
high-impact systems); China has had **AI-content-labelling rules since September 2025** with penalties to
**¥50M**; **Vietnam**'s comprehensive law took effect 2026-03-01; the **EU AI Act Article 50** applies from
**2026-08-02**; **Peru**'s regulation took effect January 2026 covering AI-generated *or edited* content.
North America has no federal statute — its binding constraint is a **union contract** instead.

For a 2D plane this is operationally specific: the same drawn asset, co-produced across regions, needs
**different disclosure in each market and a contractual notification in one of them**. The deliverable
is a per-jurisdiction policy engine with per-shot AI provenance — pass 8's APAC conclusion, now
extended by a labour clause that North America can be held to.

## Pass 37 (2026-11-27) — the consumer-products & brand-licensing plane: four trends, and **the structural law gets a five-step proof inside a single plane**

### Trend 1 — The law now has a five-step gradient, measured in one plane in one hour

Every pass in this KB has restated the same structural law: **open source solves format problems and
abandons judgment problems.** Pass 5 found a three-step gradient inside the rights-reservation plane
(declare → honour → liquidate). This plane produces **five steps, monotonically decreasing**, and it is
the cleanest proof the law has received.

| Step | Problem type | Supply |
|---|---|---|
| Match an image | format / math | `imagededup` **Apache-2.0, 5,689★** |
| Identify the product | format, paid registry | `biip` **Apache-2.0, 59★**, alive |
| See the mark | perception | `DeepLogo` **MIT, 529★ — dead since 2022** |
| Judge the infringement | judgment | `brand-protection-analyst-agent` **MIT, 5★** |
| Settle the money | judgment + relationship | **1 search result, 0★, no licence** |

Five thousand six hundred and eighty-nine stars down to one search result, in five steps, with no step
out of order. The slope *is* the finding: it predicts where Globant's work is billable, which is wherever
the stars run out.

### Trend 2 — Perception got solved and then abandoned, which is a new failure mode

Steps 1 and 3 are both perception problems, and they diverged. Image matching is maintained
(`imagededup` 2025-08-15, `imagehash` 2025-09-17, `CLIP-API-service` **2026-11-09**). Logo detection is
**uniformly dead**: 2022-08-28, 2021-10-24, 2024-12-02 for the three usable repositories, against
**1,202 search results**.

The distinction is that generic image similarity is **infrastructure other things depend on**, while logo
detection is a **finished academic task** — once the papers were published there was no reason to
maintain the code. This is a trend worth naming because it inverts the usual advice: a 529★ MIT repository
with 153 forks looks like a dependency and is actually a **baseline to re-train**. The practical read for
2026: logo detection is a fine-tune on a current detector, not an adoption decision.

### Trend 3 — The regulatory driver is real, dated, and lands on the exemption that covers this plane

EU AI Act Article 50 transparency took effect **2 August 2026**, with existing providers obliged by
**2 December 2026** — five days after this pass. Fines reach **€15M or 3% of turnover**, and the reach is
extraterritorial.

The trend is not "regulation is coming". It is that **the Act's own exemption is where the work is.**
Article 50 exempts *artistic, satirical, fictional or creative* works, and licensed character art is
precisely that category. So the duty cannot be discharged by reading the exemption; it has to be
**determined per asset and per channel**, and then **allocated between licensor and licensee by contract**.
Determination plus allocation plus retained evidence is a software product. Nobody has built it: the only
repository in the world with fields for territory, permitted channel and embargo date is
`pwnera/artbucket`, **AGPL-3.0, 34 stars, pushed 2026-11-24**.

### Trend 4 — The method trend: licence metadata has now failed in **seven** distinct ways

Pass 34 recorded four. This plane adds three more, each of which would have produced a wrong row, and all
three are worth propagating to the other eleven industries:

5. **`spdx_id` under-reports, so NOASSERTION must be read as "parser gave up".** The GitHub search API
   returned NOASSERTION for `medusajs/medusa` and `leboncoin/trademark-monitor`; **both are MIT**, verified
   by reading `master/LICENSE` (1,075 B / 1,114 B). The second one *upgraded the most relevant repository
   in the plane's judgment tier* from "no grant" to usable. Under-reporting costs findings, not just accuracy.
6. **The licence can be declared by file path instead of by identifier.** `resourcespace/resourcespace`
   sets `"license": "documentation/licenses/resourcespace.txt"` in both `composer.json` and `package.json`
   — a path where SPDX expects an identifier, which is why every scanner reports NOASSERTION. Its 76-byte
   root `license.txt` is only a pointer to a folder of ~30 **third-party** licences. The real grant is
   **BSD-3-Clause plus a fourth trademark clause** (no derivative may be called "ResourceSpace"; use
   "Powered by ResourceSpace"). The repository has **no README at all**.
7. **Publicly readable source can be proprietary by default.** `pimcore/pimcore` (3,891★) carries the
   **Pimcore Open Core License** (June 2025) at `2026.x/LICENSE.md`, which states: *"if not provided for
   otherwise, a software element is Proprietary Software."* Visibility is not a grant. **And the probe
   detail generalises:** `LICENSE.md` 404s on `master` and `main` because the default branch is `2026.x`.
   Resolve the default branch **before** concluding a licence is missing — `search/repositories` with
   `-f q='repo:<slug>'` returns `default_branch` in the same call that returns stars and forks.

**The corollary that keeps earning its place:** a 404 on the raw channel is never, by itself, proof that a
licence is missing. In this pass it meant the wrong branch (Pimcore), a pointer file (ResourceSpace) and a
lazy parser (Medusa, leboncoin) — three different causes, zero of them "unlicensed".

### Trend 5 — A named open-source project that does not exist

An aggregator page describes **"UnRoyalty"** as open-source royalty-management software *"available on
GitHub to extend and modify"*. GitHub search for `unroyalty` returns **TOTAL=0**.

This is recorded as a trend, not an anecdote, because of **where** it appeared: in the one tier of this
plane that has no code at all. Content describing software that does not exist accumulates fastest
precisely where real software is absent, and it is shaped to be plausible — a sensible name, a correct
feature list, a claim of a GitHub repository. **In an empty tier, verify existence before relevance.**

---

## Pass 38 (2026-11-27) — the type, font & multi-script text-rendering plane

### 1. The type engine layer is being rewritten in Rust, under uniformly permissive licences

Measured by last-push date and licence file on 2026-11-27, not asserted:

| New (Rust) | License | Stars | Last push | Replaces | Its licence |
|---|---|---|---|---|---|
| `googlefonts/fontations` (read-fonts/skrifa) | **Apache-2.0** | 857 | 2026-11-25 | font parsing inside FreeType/HarfBuzz | FTL/GPL-2.0 dual; "old MIT" |
| `dfrg/swash` | **Apache-2.0** | 886 | 2026-11-13 | shaping + rendering | HarfBuzz "old MIT" + FreeType |
| `harfbuzz/rustybuzz` | **MIT** | 666 | 2026-07-26 | HarfBuzz | "old MIT", `NOASSERTION` |
| `googlefonts/fontc` | **Apache-2.0** | 196 | 2026-11-25 | `fontmake` (Apache-2.0, Python) | Apache-2.0 |
| `fonttools/fontspector` | **Apache-2.0** | 123 | **2026-11-27** | `fonttools/fontbakery` (**stale 12.8 months**) | Apache-2.0 |

**Why it is a trend and not a preference:** four of the five were pushed within the last 14 days and one
on the day of the pass, while the tool being replaced has not moved since **2025-11-04**. The commercial
consequence is licensing, not language: the new stack is uniformly **Apache-2.0/MIT and compiles to
WASM**, which turns client-side shaping in a browser player or a TV app into a licensing non-event, where
the C stack required a per-component licence-file read and included one dual-licensed (FreeType) and one
bespoke-licensed (ICU) dependency.

**Falsifiable prediction, recorded for the next pass of this plane:** `fonttools/fontbakery` will still
show a last-push date in 2025 and will still not be archived, while `fontspector` will have gained stars
faster in percentage terms than any other repo in Layer B. If fontbakery moves again, this trend is
wrong and the migration stalled.

### 2. Codepoint coverage is not language support — and there are now two tools that prove it

`rosettatype/hyperglot` (**Apache-2.0, 208★**) answers *which languages does this font support*;
`googlefonts/shaperglot` (**Apache-2.0, 58★**) answers *does it shape them correctly* — whether the font
carries the OpenType features the Indic, Arabic or Khmer shaping engines call for. A font can contain
every Devanagari codepoint and still render the script wrongly.

This matters because it converts a market question into a measurement. "Can our brand typeface serve
India?" has had no cheap answer until now; it now has a CLI answer per font file. At 208 and 58 stars,
these are the usual shape of this KB's most useful findings: **critical, permissive, nearly unknown.**

Reference point for a fallback decision: **Noto covers 162 of the 168 scripts defined in Unicode 16.0**
and **over 77,000 characters**, which is roughly half of Unicode 18.0's 172,808 (Wikipedia, Noto fonts).
A lower-quality aggregator claims 166 of 172 as of November 2025; **the two sources disagree and neither
is the Noto project's own page**, so cite the range, not the number.

### 3. The font licence is a content licence, and the Reserved Font Name clause is the trap

The OFL-1.1 text defines a **Modified Version** as *"any derivative made by adding to, deleting, or
substituting — in part or in whole — any of the components of the Original Version"*, and requires the
copyright holder's **written permission** for a Modified Version to carry a Reserved Font Name,
restricted to *the primary font name as presented to users*. SIL's own FAQ, as summarised by LWN, goes
further: **converting the format counts as modification, and so does rebuilding from source if the
result is not byte-identical to the designer's release.**

**Subsetting deletes components.** On the licence text's own definition a subset is therefore a Modified
Version, and where an RFN is declared the subset must be renamed internally before distribution. *This
conclusion is a reading of the licence definition, not a quotation of SIL's FAQ:* `openfontlicense.org`
does not resolve from this session, so the FAQ's exact wording on subsetting is **unverified** — see the
informed-gaps note below.

Measured on five fonts this pass: **Andada-Pro, Amiri and Mukta declare no RFN; Skeena ("Skeena") and
Charis ("Charis", "SIL") do.** Three of five are free to subset-and-ship under the same name and two are
not, and the split does not correlate with publisher, region or recency. **It is a per-font fact that
only the licence file answers.**

### 4. Informed gaps — two channels this pass could not reach

| Channel | Why it matters | Status |
|---|---|---|
| `almanac.httparchive.org` (Web Almanac **Fonts** chapter) | The only population-scale measurement of web-font usage: WOFF2 share, variable-font adoption, `unicode-range` subsetting prevalence, median font bytes per page | **Does not resolve from this session** (outside allowed network domains). **No population-scale font figure in this pass is verified.** The three subsetting figures in `repos/trending.md` are single-project self-reports and are labelled as such. |
| `openfontlicense.org` (OFL FAQ) | The authoritative gloss on whether subsetting creates a Modified Version | **Does not resolve from this session.** Licence *text* definition obtained via search result and SPDX; the FAQ's own wording on subsetting is unverified. Treat the subsetting-equals-modification conclusion as a defensible reading, and say so in a client deck. |

Recorded the same way as `new.ddex.net` in pass 5: **an informed gap is information; silence looks
exactly like coverage.**

### 5. The font market number is unusable, and that is worth knowing before a deck is built

Vendor market-research estimates for the 2026 global font/typeface market span **roughly $1.2B to $8.5B —
a ~7x spread** — because each report defines the market differently. The most consistently reported
cluster is **$1.23–1.26B for 2026** (Global Growth Insights $1.23B; Business Research Insights $1.24B for
2026 rising to $1.81B by 2035). Verified Market Research publishes **$8.51B (2026) → $12.5B (2033)** on
one page and **$1.26B** for the same report on another.

**Rule: never put a font-market number in a client deck without naming the source and the definition.**
The useful framing is not market size at all — it is that the *engineering* layer is free and permissive
while the *entitlement* layer is entirely commercial (see `verticals/solutions.md`).

---

## Pass 39 (2026-11-27) — the digitisation & text-layer plane

### 1. The restriction moved from the code to the weights, and the dollar thresholds are now explicit

The headline trend in document AI through 2026 is not capability, it is **licence architecture**. In a
single plane, six verified cases separate the code licence from the weights licence — and two of them
name a number:

- **$5M** funding or revenue: beyond that, `marker` and `surya` model weights need a commercial licence.
- **$20M monthly revenue or 100M MAU** (consolidated with affiliates): beyond that, `MinerU` needs one,
  and every online service built on it must display a "uses MinerU" notice regardless of size.
- **Research only**: `Churro`'s weights (Qwen research licence) and dataset — the best-suited historical
  OCR model in the plane is the one that cannot be shipped.

This is the 2026 successor to the "open source" label problem the KB has tracked elsewhere: the badge in
the README is accurate about the tree and silent about the artefact that does the work. **An SBOM scan of
the source tree reports clean for all six.** Expect this pattern to spread; expect procurement not to
catch it.

### 2. A content licence is now being applied to software by public institutions

Japan's National Diet Library publishes **NDLOCR-Lite under CC BY 4.0** — a licence designed for content,
applied to a program. It is well-intentioned transparency (the file is right there, 18,653 B, spelled
`LICENCE`), but CC BY 4.0 carries **no patent grant** and none of the source-distribution machinery a
software licence provides, and Creative Commons itself does not recommend its licences for software. The
same repo then **inherits Meta's DINOv3 Agreement** through a distilled ViT-Tiny backbone, which *does*
have sticky redistribution terms. Net effect: a repo that reads as maximally open is the most legally
layered one in the plane. **Watch for more of this** — national institutions default to CC because that
is what their open-data policies specify.

### 3. LLM post-correction is a measured disappointment, and that is sellable

*No Free Lunches* (Kanerva et al., RESOURCEFUL 2025, [arXiv 2502.01205](https://arxiv.org/abs/2502.01205))
found open-weight LLMs frequently **reduced** OCR quality on historical English and Finnish. ICDAR 2026
ran the HIPE-OCRepair competition on exactly this. The trend is therefore **away from "AI will fix our
archive" and toward measured, bounded correction** with CER/WER gates — and the KB's existing P45 shape
applies: when the dominant approach cannot be shown to work, the deliverable is a **refusal with a
measurement attached**, which is a shorter sale than a pipeline and a far more defensible one.

### 4. The institutions are re-OCRing, not newly scanning — and that is the budget

The money in 2026 is in **reprocessing collections already digitised**. The Library of Congress shipped
new OCR-reprocessing software plus a datasets portal for Chronicling America in **August 2026**; the
National Library of Luxembourg built nautilusocr specifically to turn METS/ALTO into *better* METS/ALTO;
Uruguay's National Library's 2026 plan asks to retrofit OCR and handwriting recognition across archives
that are already online. A decade of scanning produced searchable-but-poor text, and engine quality has
moved far enough that the same pages are worth running again. **This is a much easier sale than
scanning**: the asset is already in hand, the cost is compute, and the before/after is measurable on the
client's own pages.

### 5. The standards layer is unlicensed, and nobody has noticed

ALTO and METS — the formats national digitisation programmes **require** — are published on GitHub from
repositories with **no licence file**. Three for three in this plane with pass 8's RSL. The specifications
are properly published by the Library of Congress and are usable; the GitHub copies grant nothing. The
trend to watch is whether any standards body fixes this, because the same defect in the rights-reservation
plane (pass 8) has now gone two passes unaddressed.

## Pass 40 (2026-11-27) — trends in the puzzles, games-desk & word-play plane

### 1. Games are now a retention instrument, and publishers are buying the thesis, not testing it

The NYT case is treated as settled across the trade press: subscribers who play **and** read retain
far better than news-only subscribers, retention rises with the number of games played, and family
plans test higher still. Games sit deliberately inside the higher-priced bundle. In 2026 the
followers arrived — **Time** and **Business Insider** launched puzzle destinations explicitly on the
NYT playbook, **The Atlantic** launched daily puzzles with metering designed to convert free players,
the **Guardian** added web games in May 2026 on top of a 1.7M-user paid app, and **Nine** (Australia)
uses puzzles to drive premium bundles. **The caution worth carrying into a pitch:** every retention
claim in public is qualitative and comes from the seller. No publisher has disclosed an audited
games-attributable retention or revenue figure (see the refusal in `intel/market.md`).

### 2. AI took the American grid and left the cryptic one

The clearest capability split in this plane, and it is published, not speculated:
LLM-plus-search reaches **93% on NYT-style puzzles** ([arXiv
2406.09043](https://arxiv.org/abs/2406.09043)), while on single **cryptic** clues Gemma2, LLaMA3 and
ChatGPT stay **significantly below human** ([arXiv 2412.09012](https://arxiv.org/abs/2412.09012)).
Wordplay, not vocabulary, is the barrier. Operationally that makes the EMEA cryptic tradition the
one part of the plane where human expertise is still the product and AI is the assistant — and makes
`rjkat/anagrind` (MIT, 2026-10-11) the only active permissive tool pointed at it.

### 3. Much of "AI puzzle ability" turns out to be document understanding

CrossWordBench ([arXiv 2504.00043](https://arxiv.org/abs/2504.00043)) reports that solving
performance correlates with **grid-parsing accuracy at r = 0.94** across >20 models, and that
reasoning models beat non-reasoning ones by actually exploiting crossing-letter constraints. The
practical reading: a large share of measured puzzle skill is *reading the grid*, which puts this
plane directly downstream of pass 39's OCR and layout findings. A pipeline that hands the model
structured grid data rather than an image is not a convenience, it is most of the benchmark.

### 4. The research has gone quiet while the tooling woke up

A search on 2026-11-27 surfaced **no 2026 papers** on this plane — the newest located work is 2025 —
and the strongest permissive solver, `Berkeley-Crossword-Solver` (MIT), has been **untouched since
2023-12-06**. Meanwhile the *authoring and format* layer moved in the days around this pass: `exet`
2026-11-25, `kotwords` 2026-11-26, `puzpy` 2026-11-22, `exolve` 2026-11-22, `crosshare` 2026-11-25,
`xd` 2026-11-25. **The hobbyist tooling is alive and the published science is a year stale** — the
inverse of most planes in this KB, where research outruns usable code.

### 5. The archive is being opened one copyright renewal at a time

The xd corpus's November 2026 policy drafts show the mechanism in detail: pre-1931 puzzles are public
domain outright (**459** held), *Judge* 1931–39 cleared because **no issue was renewed** (**227**
more), and NYT 1942–63 **blocked because every issue was renewed** — **5,267 puzzles locked until
2037–2058**, with an earlier release having published them by mistake and the maintainers now
deciding what to do. Simultaneously the **Every Puzzle Project** is digitising pre-1931 material
across a dozen active repositories, including early Black-press crosswords. **The trend is real but
slow and legally gated, and the renewal check is the gate.**

### 6. Provenance obligations are arriving before the products do

Three regimes now bear on an AI-generated puzzle or clue: **EU AI Act Article 50** transparency for
AI-generated content; **APAC labelling duties** across the risk-based and targeted frameworks
(Latham & Watkins, September 2026 — South Korea, Vietnam's Law No. 134/2025/QH15 in force 1 March
2026, China's targeted rules); and **Mexico's May 2026** copyright and labour amendments. None names
puzzles, all cover them. Design the provenance field — generated vs human-set, which model, which
word list — into the content model now; retrofitting it across a year of dailies is the expensive
version.

### 7. Rights-holders are declaring terms they openly admit they cannot enforce

The xd corpus states it plainly: terms are attached "as signals: fields on the Hugging Face dataset
card, and machine-readable training opt-outs where the venue supports them. **They are terms we ask
people to honor, not locks**" — alongside the acknowledgement that the public clue file "has already
been used to train crossword-solving models" and, for public-domain puzzles, "we cannot restrict them
and do not pretend to." This is pass 5's declare → honour → settle gradient, articulated by the
declaring party. **The trend: content owners are moving from silence to explicit, documented,
unenforceable asking** — which is still the right move, because it is what makes a licensing
conversation possible later.

### 8. The engagement mechanic is drifting toward wagering, and it is a trust risk

The Guardian's May 2026 web games reportedly include a fantasy prediction-market game built on
**Kalshi and Polymarket** data (SiGMA, secondary source). A March 2026 Jordan Center warning, via
the same outlet, holds that news-organisation partnerships with betting platforms can undermine trust
in journalism. **Raise this before a client asks for it**: prediction and wagering mechanics are the
highest-engagement, highest-trust-cost options on the table, and the decision belongs to the
newsroom, not the growth team.

## Pass 41 (2026-11-27) — trends in the content-protection, soft-binding & anti-piracy enforcement plane

### 1. The obligation is becoming machine-speed, which is what makes this a software engagement

Across every region the unit of compliance is collapsing toward **30 minutes**, and no human
workflow meets that. Italy has enforced a 30-minute blocking obligation since February 2024 via
AGCOM's Piracy Shield, extended by AGCOM rules in February 2025 to **VPN services and public DNS
resolvers**, and in August 2025 from live sport to **film and TV premieres and live music**. The
European Parliament's JURI-commissioned study (July 2026) argues for **binding EU-wide 30-minute
blocking** — while explicitly acknowledging over-blocking risk. The AAPA proposed a three-layer
regulatory response on **2026-11-18**. **The deadline, not the detection, is the product
requirement.**

### 2. The EU's own assessment says the voluntary route failed — a regulator-sourced sales argument

Recommendation (EU) 2023/1018 is non-binding, and the Commission's **November 2025** assessment
concluded it *"has not resulted in considerable curbing of the overall level of piracy of live
events"*, with limited improvement in notice-handling promptness. A targeted copyright consultation
opened **2026-09-29**, and a formal recommendation was expected in November 2026. **As of this pass
it has not been published** (searched 2026-11-27). This is the cleanest kind of evidence in the KB:
the body that wrote the voluntary rule published the measurement of its failure. **It is also a dated,
falsifiable watch item — if the recommendation lands, the EMEA pipeline changes within a quarter.**

### 3. Provenance is shifting from metadata to *recovery*, and a registry now gates it

The year's real movement is not more watermarking research — it is the C2PA **soft binding** layer:
the mechanism for recovering a manifest once metadata is stripped, which is the normal state of any
asset that has been through a social platform. The approved-algorithm registry holds **80 entries**,
**19 of them entered in November 2026 alone** and 55 across 2026. **But only 13 of 80 declare a
resolution endpoint**, so the naming layer is outrunning the lookup layer roughly five to one. The
direction is unambiguous and the infrastructure deficit is specific.

### 4. A permissive licence, not a partnership, is what buys a standards position

Eleven registry entries wrap Meta FAIR's MIT-licensed seal models, filed by **five different third
parties**; **none** is registered by Meta. The registry's rules permit this explicitly — a submission
may come from *"a maintainer of the submitted open source algorithm or its fork."* AudioSeal's README
records the decision that enabled it, dated **2024-04-02**: relicensed to *"full MIT license
(including the license for the model weights)."* **This is the counter-example to the pass-39 law**
("the code is permissive, the weights are not"): the law describes a *choice*, and here one lab chose
the other way and measurably captured the registry's largest algorithm family — for other companies.

### 5. The open-source community continues to build the attack harder than the defence — now with a proof

Measured in this plane: **28,928★** for the top watermark remover
([guillaumemeyer/watermarks-remover](https://github.com/guillaumemeyer/watermarks-remover), MIT,
pushed 2026-11-23) against **456★** for `c2pa-rs` (**63×**) and **243★** for Meta's current marking
framework (**119×**). Pass 34 measured 7×–21× for ad-fraud evasion versus detection; **this is the
same law at five to seventeen times that severity.** What is new is the academic backing:
`XuandongZhao/WatermarkAttacker` (281★, MIT) is NeurIPS 2024, *"Invisible Image Watermarks Are
Provably Removable Using Generative AI."* The removal side has reached the agent-skill layer too
(`minhhieust/ai-meta-cleaner` — a Claude Code / Codex skill to strip C2PA, EXIF and XMP — which
carries **no licence file** and is therefore unusable itself).

**The trend's practical consequence: stop selling marks as prevention.** A mark is evidence for an
attribution claim, a guild audit or a blocking application. Sold as protection it will be defeated by
a better-maintained, more popular, MIT-licensed tool, and the client will have paid for the loss.

### 6. Enforcement is the least automated layer in this entire KB

`takedown automation copyright` returns **0 repos**. `restream detection live stream` returns **0**.
`piracy monitoring` returns 21, of which the top result is off-topic BitTorrent mapping and the rest
hold 0–1 stars. Yet the identical technical mechanism is a 29,211-star GPL-3.0 ecosystem when the
target is advertising. **The asymmetry is legal, not technical: a copyright blocklist is an
instrument of state authority and cannot be crowd-maintained.** That is precisely why the work is
consulting work rather than an open-source adoption exercise.

### 7. Regional divergence is now wide enough that "the compliance mode" is the deliverable

In force and administrative: **Italy** (30 minutes, VPN/DNS in scope, €14.2M fine issued to a
resolver operator in January 2026) and **Brazil** (Anatel administrative blocking, with a public
near-real-time dashboard since May 2026). In force and judicial: **India** (Delhi High Court
real-time dynamic injunctions). Not in force at all: **the United States**, where three competing
bills disagree on whether VPNs are even in scope. A single global "takedown feature" cannot satisfy
these; **the asset is a per-jurisdiction policy engine** — the same conclusion pass 8 reached for
APAC AI rules, now reached independently in enforcement.

## Pass 42 (2026-11-27) — trends in the archive-monetisation plane

1. **The archive became the clearest AI business case in media, and the trade press is explicit that
   it is a data-cleanup project first.** NewscastStudio (2026-03-30), *"Broadcasters look to AI to
   unlock value from content archives"*, ties archive work to returns **and** states archives only
   become useful once metadata, taxonomy and cleanup are done. Moments Lab's 2026 outlook
   (NewscastStudio, 2025-12-31) predicts the defining problem of the year is the gap between AI spend
   and working deployment, naming legacy on-prem content migration as the obstacle. **Sell the
   taxonomy, not the model.**

2. **A second buyer arrived for the same asset, and in 2026 it changed what it wants.** Trackers
   surveyed this pass report the training share of new publisher deals collapsing in favour of
   **display/grounding rights** — one counts 47 display-only deals against 61 including training, and
   another puts display rights in 58.7% of news-publisher deals. Microsoft's Publisher Content
   Marketplace (Copilot as first buyer) is the platform expression of this. *Treat these counts as
   directional: they come from secondary trackers, several of which disagree, and this session could
   not fetch primary sources (see channel note below).*

3. **Collective licensing is being tried and simultaneously rejected, by region.** The News/Media
   Alliance signed a non-exclusive opt-in deal with Bria (March 2026, ~2,200 members, revenue split
   50-50). In Europe the ACT — the commercial broadcasters' association — argued in its June 2026
   issue paper that licensing must be *voluntary, direct and under full rightsholder control* and
   that **collective licensing cannot accommodate the complexity of AV rights**. Same year, opposite
   conclusions, and the split runs along the news/AV line as much as the geographic one.

4. **Music settled; audiovisual did not.** UMG–Udio (Oct 2025) and Warner–Suno (Nov 2025) each paired
   a settlement with a licensed platform launching in 2026. An ABA analysis from mid-2026 states that
   **no industry-wide content-licensing framework analogous to the music model has been announced for
   film and TV.** Music is the template everyone cites and AV is the market nobody has built.

5. **The engineering is solved and asleep; the money went to retail search.** Shot detection and
   shot-level retrieval exist under MIT/Apache and are dormant (TransNetV2 2023-12, hecate 2023-05,
   clifs 2022-03, natural-language-youtube-search 2021-10, towhee 2024-10). The alive, well-starred
   content-retrieval projects are ecommerce and general search: Marqo 5,026★ (2026-09-03), Vespa
   7,202★ (today). Media-specific Shotit: **27★**. Pushed three days apart from Marqo, same licence,
   **186× apart**.

6. **Open source describes licences fluently and transacts them not at all.** Openverse (MIT, 828★,
   alive today) and free-for-creators (CC0-1.0) model licence metadata well — for **free** content
   only. Croissant (Apache-2.0, 923★) carries a `license` field and RAI provenance for datasets.
   Nothing quotes, invoices or records a sale. Measured: `stock footage licensing` = **4 repos**
   (top stars 1,0,0,0); `rights clearance` = 40 repos, top six = 2,2,1,1,1,1.

7. **The content law (health's CPT law, pass 5's registry law) holds again, with a new face.** What
   is scarce is never the parser — it is the *allocation* and now the *price*. Clip-level pricing,
   territory-by-term rate cards and residual splits are the scarce artefacts, and they are scarce
   because they are commercially confidential, not because they are hard to encode.

8. **A new licence pathology, worse for scanners than pass 8's Chromaprint case.** `resourcespace/resourcespace`
   (96★, pushed today) reports `NOASSERTION`: its `license.txt` is **76 bytes of pointer** to a folder
   holding 30 files, 29 of which are *other projects'* licences (including a **GPL-2.0** component).
   The real grant sits at `documentation/licenses/resourcespace.txt` and is **BSD-3-Clause plus a
   trademark clause**. Full detail and the CI rule in `verticals/solutions.md` (pass 42).

**Channel note, recorded as an informed gap.** This session's network policy allows GitHub but not the
article hosts: `curl -sI` returned `000` and WebFetch returned `ENOTFOUND` for newscaststudio.com,
acte.be, acma.gov.au, lw.com, chambers.com, cisac.org, americanbar.org, imec-publications.be,
research.google and arxiv.org. **Every repository row in this pass is `ls-remote`+API verified; every
market claim above is attributed to the publisher and date that WebSearch surfaced and was NOT
independently fetched.** Treat the deal counts and market figures as leads to confirm, not as audited
numbers. Repo facts: verified. Press figures: cited, unfetched.

## The composition side: lyrics, chords, score capture & publishing rights — added 2026-11-27 (pass 43)

Measured 2026-11-27. Repo evidence in `repos/foundations.md` and `agents/top.md`; opportunities by
region in `intel/market.md`, all for the same date.

### 1. The regulator has started pricing a field that no open format can express

This is the trend of the pass, and it arrived in four jurisdictions inside one year. Royalty
eligibility is becoming a function of the **human-authorship share, per element**:

- **Japan — JASRAC, June 2026.** Manages AI-involved music only where human creative contribution is
  recognised, and it is the only body anywhere that has published a **number**: a **100%** management
  rate where AI wrote just one element (AI lyrics over a human composition), and **50%** where both
  lyrics and melody involve AI. Fully-AI works are excluded from management entirely.
- **South Korea — KOMCA, August 2026.** Adopted AI-assisted registration criteria and **withdrew them
  22 days later** after government pushback. Now selecting an AI-detection vendor with five other
  bodies; reporting says the tools fail precisely on *partly* AI-made tracks.
- **North America — ASCAP/BMI/SOCAN.** Aligned: AI-**assisted** works registrable, wholly-AI works
  ineligible. Eligibility therefore rests on a declaration made at registration time.
- **EMEA — GEMA v. Suno, Munich Regional Court I, 31 July 2026** (not final). Training, memorisation,
  model provision and output were assessed as **four separate levels**, and a licence was held
  necessary even for training performed outside Europe.

**Note what JASRAC's rule is computed over: lyrics versus melody.** That is the composition-side split
exactly. And no open format in this plane has a field for it. MusicXML and MEI describe notes and
carry `<identification>`/`<creator>`; LRC carries timings; ChordPro carries chords; OpenLyrics carries
words. The only places to put "what authored this element" are free-text escape hatches
(`<miscellaneous>`, encoding descriptions). **The datum four regions' royalty eligibility now turns on
is unrepresentable in every open format that touches a song.**

*Falsifiable prediction, recorded for the next pass:* the first format to standardise a per-element
provenance field takes the registration workflow. Watch the MusicXML and MEI issue trackers and
DDEX's output; if such a field appears before mid-2027, this call was right. If the industry instead
settles on affidavits at registration and no format changes, it was wrong.

### 2. The three-step gradient, and the sixth confirmation of this KB's structural law

The law first recorded in healthcare and sharpened in pass 8 holds again, and this plane gives it the
cleanest three steps yet:

| Step | What it is | Measured state |
|---|---|---|
| **Render** the song | a **format** problem | **Healthy.** lrcget 3,392★, Audiveris 3,019★, lrclib 2,314★, alphaTab 1,951★, tuxguitar 1,666★, USDX 1,320★ — two pushed *on the day of this pass* |
| **Identify** the work | a **registry-allocation** problem | **No open implementation.** ISWC/CWR closed by membership (p5); the acronym is unusable as a search term |
| **Pay** the writer | a **judgment** problem | **Zero.** `mechanical royalty` → relevant top-six **0★**; `music royalty accounting` → **4★** |

Pass 8 measured `music royalty accounting`'s relevant top six at **0 stars**. Five days later, with a
wider query set, it is **4**. The emptiness is stable, reproducible, and still the most extreme in
this KB — worse than healthcare's `medical necessity` at 3★. The top *search* result for
`mechanical royalty` is a 228★ joke repo containing the Bee Movie script: **the most-starred thing
GitHub offers for a phrase describing a money flow of roughly $900M a year through the MLC alone.**

### 3. In score capture, the licence and the maintenance status are the same choice

Measured, not inferred: **every maintained OMR engine is copyleft and every permissive one is
dormant.** Audiveris (AGPL-3.0) pushed 2026-11-25 and homr (AGPL-3.0) pushed 2026-11-27, against
oemer (HEAD 2025-04-18), Mozart (Apache-2.0, 2022-08-24), OMR-Datasets (MIT, 2024-04-01),
MeasureDetector (2026-06-14) and SMT (MIT, 2026-09-27). The karaoke platforms repeat the pattern —
USDX, Performous and Vocaluxe are all maintained and all GPL.

The permissive half of this plane is the **library** layer, and the aligners within it (WhisperX
BSD-2 at 25,723★, MFA MIT, ctc-forced-aligner BSD-2) are permissive because they are **shared with
the speech plane (p7)** — nobody built them for music. The practical consequence: you can assemble a
permissive *lyric-timing* pipeline today, and you cannot assemble a permissive *score-capture* one.

### 4. The content law again, now over words

**Displaying lyrics in time with music is a licensed act, and the right sits with the publisher** —
a different counterparty from the recording owner a media client usually has a deal with. The open
stack reaches the timing and stops at the words. `LRCLIB` is MIT and its README has **zero** mentions
of licence, copyright, DMCA or takedown for the corpus it serves (checked). `LyricsGenius` is MIT code
over a third party's API and words. Never scope a lyrics product as open source end to end.

### 5. Licence-reading rules, extended twice by this pass

- **New file location: `docs/LICENSE`** (tuxguitar, LGPL-2.1, 24,838 B). Root-only scanners —
  GitHub's included — report `NOASSERTION`. Three of this pass's four `NOASSERTION` repos were in
  fact **MPL-2.0, LGPL-2.1 and Artistic-2.0**. A `NOASSERTION` is never, alone, evidence of a missing
  licence.
- **New defect category: the unfilled licence template.** `oemer`'s `LICENSE` still reads
  `Copyright (c) [year] [fullname]` while `setup.py` asserts the MIT classifier — a grant naming no
  grantor. It joins pass 8's "licence owned by the compilation" (Chromaprint) and pass 12's font
  exception (MuseScore) in this KB's taxonomy, and it is the same defect this KB's own quality bar
  forbids, found in the wild.
- **Artistic-2.0 appears for the first time** (ChordPro, 549★). OSI-approved, permissive in practice,
  outside the MIT/Apache/BSD comfort set — flag, don't wave through.

### 6. The market is the mirror image of the technology

Sheet music is quoted at a **1.11% CAGR** — the lowest growth figure anywhere in this KB, against the
25–36% CAGRs recorded for AI media generally — while its **digital** slice grows at 8.5–10.7%, roughly
**eight times faster than the whole**. The composition side is not a growth market; it is a
*migration* market, and that is a different sale: moving a flat, century-old catalogue into data,
not riding a wave. Figures and their spreads are in `intel/market.md` under the pass-43 addendum.

## Pass 44 (2026-11-27) — the IP broadcast plant: **the control plane went permissive while the measurement plane went dark**

Measured 2026-11-27 against 58 repos, all URLs resolving, every ambiguous licence read from the file.

### 1. The plane's law, and it is a three-step gradient inside one plane

This KB's recurring structural finding — that the permissive, maintained open source clusters where
the problem is a **format**, and thins to nothing where the problem is a **judgment** — reproduces
here with unusual clarity, and for the first time **the gradient is about operations rather than
content**:

1. **DISCOVER and CONNECT — a format problem → permissive, active, well-staffed.** `sony/nmos-cpp`
   Apache-2.0 204★ pushed 2026-11-20; the AMWA IS-0x specification repos all pushed 2026-11-24;
   `NVIDIA/nvnmos` Apache-2.0 pushed 2026-11-25; `AMWA-TV/nmos-testing` Apache-2.0 pushed 2026-11-26.
   A device announcing itself over REST is a schema question, and open source answers schema questions.
2. **MEASURE — a judgment problem → copyleft, unlicensed, or abandoned. No exceptions found.**
   `ebu/pi-list` GPL-3.0; `pkeroulas/st2110-toolkit` GPL-3.0; **`ebu/smpte2110-analyzer` Apache-2.0
   but frozen since 2020-05-01**; `OpenBroadcastSystems/ptpmeasure` 65★ with **no licence at all**;
   all four `NEOAdvancedTechnology` Wireshark dissectors and pcap fixtures **unlicensed and dead since
   2020–2022**; `philhartung/aes67-monitor` MIT 360★ but 15 months idle.
3. **TIME — the layer everything else depends on → GPL-2.0, and its measurement half is unlicensed.**
   `richardcochran/linuxptp` is the de-facto PTP implementation at GPL-2.0, and the only open tool
   that measures whether PTP is behaving (`ptpmeasure`) may not be lawfully reused.

**The operative conclusion:** a vendor can build and ship a permissive product that *controls* a
broadcast plant, and cannot ship the thing that proves the plant is *healthy*. That is the exact
inverse of what a broadcast engineering buyer assumes when they hear "open source", and it should be
said out loud in the first meeting.

### 2. MXL is the real event of the year in this plane, and it is permissive

`dmf-mxl/mxl` — Apache-2.0, 192★, **pushed the day of this pass** — is the EBU Dynamic Media Facility
**Media eXchange Layer**, hosted by the **Linux Foundation** and driven by the EBU with **NABA** and
**AMWA**. It is the data-plane component of the DMF reference architecture, whose premise is replacing
dedicated hardware appliances with orchestrated software microservices. Reported: **v1.0.0 on
2026-02-26**, **v1.1 at IBC 2026** extending it from a single server to clusters over **RDMA**, and
contributions from **BBC, CBC/Radio-Canada, France Télévisions, SVT, RTÉ and VRT**.† The EBU
published **version 2 of the DMF Reference Architecture** (dated 2026-04-15†), which moves
orchestration to a cross-cutting concern.

**Why it matters more than its star count suggests:** until MXL, the permissive open source in this
plane was all *control* — telling hardware what to do. MXL is the first permissively-licensed,
vendor-neutral **data plane**, which is what makes a software-defined facility buildable rather than
merely describable. Six independent satellite projects appeared around it within roughly twelve months
(`repos/trending.md`), which is what a forming standard looks like before the vendors arrive.

### 3. The control plane is being pointed at the software data plane — NMOS now controls MXL

AMWA has published a specification allowing **MXL connections to be managed over NMOS**,† and
`AMWA-TV/jt-dmf-crm` (Apache-2.0, 9★) carries the Joint Task Force on Dynamic Media Facilities
conceptual reference model. Work continues in EBU/AMWA JT-DMF on how MXL is controlled, how software
is placed on available servers, and timing. **This convergence is the thing to track in this plane in
2027**: the same IS-04/IS-05 verbs that route hardware are becoming the verbs that schedule software.

### 4. SDI is not dying on the schedule the vendors imply — and the two 2026 surveys disagree

| Source | Date | ST 2110 adoption | SDI still in use |
|---|---|---|---|
| TV Tech industry survey | 2026-10-07 | **more than half** have deployed ST 2110, but mostly as **"IP islands"** | **primary infrastructure for 70%** |
| Haivision Broadcast Transformation Report (n > 1,300) | 2026 | **30%** using ST 2110 | **82%** still running SDI |

**These do not reconcile, and the disagreement is the useful part.** On 2110 share they are roughly
**1.7–1.8× apart**; on SDI persistence they broadly **agree** (70% vs 82%). So the quotable claim is
*not* an adoption percentage — it is that **SDI remains the primary or coexisting infrastructure for
the large majority of facilities in both surveys**, and therefore that **hybrid SDI/IP operation is the
default engagement context, not a transitional edge case**. Scopes differ (a trade survey weighted to
one readership versus a global vendor survey), which is the likeliest source of the gap. Quote the
range and name the source, never a single adoption number.

The "IP islands" phrasing is the most actionable detail in either survey: most facilities have 2110
*somewhere*, which means the common engagement is **joining islands and proving conformance across the
seams**, not a greenfield build.

### 5. The knowledge-content law, third instance — and this time a fee cannot unblock it

This KB has twice found that **the licence of the knowledge content, not the regulatory pressure,
decides whether open source can do the job** — CPT codes and MedDRA, both *taxed* content. The IP
plant supplies a third instance with a **new failure mode**:

- **AMWA NMOS** (`AMWA-TV/nmos`, licence read in full): API definitions and software **Apache-2.0**;
  the markdown specification documents **CC BY Attribution-NoDerivatives 4.0**.
- **SMPTE ST 2110** itself (`SMPTE/st2110-10`, `SMPTE/st2110-30`, licence read in full):
  **"No part of this material may be reproduced, by any means whatsoever, without the prior written
  permission"** — all rights reserved, published on GitHub, not open source.

**The new flavour: this content is not expensive, it is derivative-blocked.** CPT and MedDRA could be
licensed by paying; **no payment makes CC BY-ND permit a derivative work.** The practical consequence
lands precisely on the most obvious AI deliverable in the plane:

- **Blocked:** an agent or RAG product that paraphrases, abridges, restructures or **translates** the
  standards into client-facing guidance; a Spanish-language annotated NMOS handbook for a LATAM
  engineering team; "AI-generated 2110 documentation".
- **Clear:** implementing the specifications in code (Apache-2.0); running `nmos-testing` and
  `sdpoker` against a client's own devices; generating documentation **of the client's own facility,
  its own SDP files and its own conformance results**.

**The rule to carry into every industry in this rotation:** when a plane is governed by a standards
body, read the licence of the *document* separately from the licence of the *code*. They differ here,
they differed for CPT and MedDRA, and the document licence is the one that constrains an AI
deliverable.

### 6. The agent layer is empty, and the substrate for it is unusually good

No deployed open-source AI agent for broadcast IP operations exists (measured in `agents/top.md`); the
only artefact is a **2025 SMPTE Media Technology Summit** paper proposing a multi-agent LLM system for
ST 2110 automation, in simulation, with no released code.† Meanwhile NMOS makes every device in a
facility **network-addressable and self-describing over a documented REST API**, and
`AMWA-TV/nmos-testing` makes compliance **machine-checkable** — which is a better agent substrate than
most planes in this KB ever offer. **The gap is not capability, it is that nobody has built it.**

### 7. The regional constraint is skills, not technology — and it is strongest where adoption is fastest

APAC reporting identifies a **critical shortage of IT and networking skills for IP workflows** as the
limiting factor on 2110 deployment,† at the same time as ST 2110 moves from trials into operation
across the region.† This inverts the usual read: in this plane the binding constraint on a broadcaster
is **people who can run a routed network**, which makes integration-plus-enablement the sellable unit
rather than software. EMEA frames the same migration through **sovereignty** — the EBU/NVIDIA
sovereign-AI work for public service media, and EBU HORIZONS 2026 on sovereignty and resilience† —
which is a procurement argument for permissive, self-hostable components rather than a technical one.


## Pass 45 (2026-11-27) — trends in the public-warning & emergency-alerting plane

### 1. The new structural law: where the scarce asset is a **credential**, the supply curve is a barbell

This KB's running law said that **the licence of the knowledge content** decides whether open source
can discharge a regulated obligation — CPT in healthcare billing, MedDRA in pharmacovigilance, the
registry-allocation monopolies behind ISRC/ISWC/EIDR in rights (pass 5). Emergency alerting is the
**control case that breaks the old formulation and replaces it with a better one**, because here
there is *no* gated content:

- **CAP is a free OASIS standard.** No membership, no fee, no licence on the vocabulary.
- **The hazard data is public.** NWS, MeteoAlarm, JMA, CWA — all published.
- **The formats are documented** and the profiles are public.

Every input is free, the obligation is absolute in every region, and the supply at the decisive step
is still **effectively zero**. The reason is not licensing. **It is that the scarce asset is the
right to speak** — a signing credential and a statutory mandate, held by the state. Open source
cannot compete for a monopoly on origination, so it colonises both ends and abandons the middle:

> **Detect (MIT, 408★) → Encode (archived / MPL) → ORIGINATE & SIGN (dead since 2015) → Deliver
> (22 repos, ~20★) → Authenticate (nothing) → Consume (MIT, active, Home Assistant)**

**The generalisable prediction, and it is falsifiable:** in any plane where the gate is a credential
rather than a dataset or a licence, expect healthy permissive tooling at the sensor and at the
receiver, and a hole in the middle that no amount of developer enthusiasm fills. If a jurisdiction
ever opens originator credentials to private parties, step-3 code should appear within two years.
**Nothing resembling it exists today** — which is the measurement that makes this a prediction rather
than an opinion.

### 2. The trend that is actually a non-trend: nothing new **sends**

Six repos in this plane were pushed within the week of this pass — `EEWBot/EEWBot` (the day of it),
`capparselib`, `eas-station`, `ipaws-alerts`, `wmo-raf/cap-aggregator`, `TREM-Lite`. **Every single
one of them listens, parses, maps or notifies.** Not one originates, signs or disseminates. The
activity is real and it is all on the receive side. Stop looking for an open originator; there is an
absence here to stop re-checking hopefully, exactly as pass 17 concluded for residuals.

### 3. Authentication is the gap the standards themselves admit — and 2026 supplied the proof

**ETSI TS 102 900**, the technical basis for EU-Alert over cell broadcast, states that the service
*"does not provide any capability for the UE to authenticate that the EU-Alert messages received are
from a genuine source."*† In **June 2026**, attackers breached Brazil's emergency alert system and
triggered **millions of false "extreme" alerts**.† The only open project that ever authenticated and
signed CAP alerts — `CAPTools/CAPCollector`, BSD-3-Clause — **has been dead since 2015-06-02**, and
of every CAP library measured here exactly **one** mentions XML signatures (`cB-Sigma/cap`,
Apache-2.0, **0★**, 2026-10-11).

A specification that documents its own trust gap, a national-scale incident inside the same year, and
a measured void between them. **This is the most sellable triple in any media pass**, and it is
regionally complete: the admission is EMEA, the incident is LATAM, the regulatory response is NA.

### 4. Regulation moved first in North America, and it moved to **cybersecurity**, not to alerting

The FCC's EAS cybersecurity rules are **in force**, with the implementation date **2026-09-29**
already passed.† Three requirements — strong passwords or alternative authentication, prompt
patching, firewall or comparable segmentation — across a scope that includes **automation systems,
audio processors, STLs, RDS encoders and transmitters**, at **every** licensed station.† The
nationwide test of **2026-11-17** is usable to assess compliance, and a station that misses an alert
because its equipment was not updated **can be found in violation**.†

**The trend to name:** the regulator did not ask broadcasters to send better alerts. It asked them to
prove nobody else can send one through their plant. **Alerting compliance has become an
infrastructure-security problem**, which moves the budget from the news division to engineering and
makes the deliverable an evidence trail. That reframing is the commercial news in this plane.

### 5. The rich-alert capability is pending, and the two regions are moving in opposite order

| Region | Rich / advanced alerting status | What it means |
|---|---|---|
| **North America** | **AWARN petitioned the FCC in late Sept 2026** (five recommendations, multimedia alerts with standardised symbols and graphics), framed as **voluntary**. **No decision located.** Constraint: channel capacity during ATSC 1.0 simulcast; adoption pace tied to the missing 1.0 sunset date.† | Capability exists, **permission pending**. Roadmap conversation only. |
| **LATAM (Brazil)** | Alerting is **in the standard by decree** (TV 3.0 / DTV+, Aug 2025), with a **published June 2026 operational guideline**, **ABNT NBR 25607:2025**, and **IDAP** monitoring defined.† | **Permission settled, build pending.** An engagement available now. |

**Brazil has the obligation specified and the US has the capability unauthorised.** For a global
services firm that inverts the usual order of operations: the reference implementation for advanced
TV alerting will most plausibly be built in **Portuguese, for a World Cup deadline**, and then sold
north — the same direction of travel as `openeew` (Grillo, Mexico → Linux Foundation).

### 6. The aggregation layer is being reinvented by public institutions who all forget the licence

`alert aggregator CAP` returns **six repositories worldwide.** The **WMO**'s Africa regional office
(active 2026-11-25), the **IFRC** Alert Hub, and **Parks Australia** have each independently written
a CAP aggregator, and **all three are unlicensed** — absence verified against 200 READMEs. The only
permissively licensed one authenticates and signs, and died in 2015.

**The trend:** institutional need is rising fast enough that three unrelated public bodies built the
same tool within two years, and the open-source commons captured **none** of it, because nobody
attached nine lines of licence text. **This is the cheapest high-credibility contribution available
anywhere in this KB** — a licence conversation with WMO RA-I or the IFRC costs nothing and unlocks
code that is already maintained.

### 7. Volunteer capability is now decoding national warning systems, and that cuts both ways

One person's **MIT**-licensed SDR++ plugin demodulates **J-ALERT**, Japan's national instantaneous
warning system (161★, active).† `GlobalQuake` (**MIT**, 408★) *issues its own early warnings*.
`EEWBot` (MIT) pushes Japanese EEW to **Discord**. `astrbot_plugin_disaster_warning` (AGPL-3.0, 104★)
wires global hazard feeds into an **LLM chatbot**.

Two readings, both true and both worth saying to a client. **The opportunity:** the protocols are
tractable, the receive side is solved cheaply, and monitoring/verification can be built today.
**The risk:** if a hobbyist can decode and redistribute a national alert, then the gap between
*"an alert exists"* and *"a trustworthy alert reached the right people"* is now occupied by
unaccountable software — and ExpTech's own data carries a **"reference only"** disclaimer while
`dsame` disclaims life-safety use outright. **The trust layer is the product, and nobody is selling
it.**


## Pass 46 (2026-11-27) — trends in the radio delivery & hybrid-radio metadata plane

### 1. The structural law, inverted for the first time in 46 passes: **licence quality tracks how little the real world has to permit**

Every previous plane in this KB produced the same finding — rich permissive substrate, empty agent layer,
and a licence or content paywall as the blocker. **This plane inverts all three**, and the mechanism is
clean enough to state as a law:

| Layer | Permission required from the world | Licence | Health |
|---|---|---|---|
| AI-DJ agents | **none** | **MIT** | `subwave` 1,687★, pushed day of pass |
| IP stream delivery | **none** | **MIT / Apache-2.0** | `srs` 29,466★; `tinyice` Apache-2.0 373★, day of pass |
| Stream orchestration | none | GPL-2.0 | `liquidsoap` 1,763★, day of pass |
| DAB+ transmission | **spectrum licence + AAC patents** | GPL-3.0 + 4 others | 30–60★, maintainer disclaims redistribution |
| RDS transmit | **a transmitter** | **GPL-3.0, 7 of 7** | hobby scale |
| Hybrid-radio metadata | **be a licensed broadcaster with an OEM contract** | Apache-2.0 | **96★ across 8 repos, half dormant since 2008–2011** |

**The law: the more the real world must permit before you can run the code, the worse the open supply —
regardless of licence.** The bottom row proves the licence is not the variable: six of its eight repos are
Apache-2.0 or MIT and it is still the most abandoned layer in the plane. **What collapsed there was not
permission to use the code. It was the population able to use it.** Hobbyists can run an internet radio
station; they cannot sign a contract with Audi.

**Falsifiable prediction, recorded for a future pass:** if this law holds, then any plane whose
participation requires a credential, a licence or a counterparty will show thin open supply **even when
its licences are permissive** — the inverse of pass 45, where the credential barrier coincided with
copyleft. Check it against the next plane with a permissive standard and a gated participant set.

### 2. The agent layer is the healthiest layer, and that is genuinely new

`perminder-klair/subwave` (MIT, **1,687★**, 144f, pushed **2026-11-27**), `robert-dean/deadair` (MIT,
145★, **0 open issues**, 2026-11-24), `johncrash64/radio-dj` (MIT, 63★). Three MIT agents, one of them
pushed the day of the pass, **all three targeting Icecast directly** — `radio-dj` describes itself as
*"persistent ffmpeg→Icecast with live ducking, LLM banter, BYOK"*. Pass 44 recorded "the agent layer is
empty, and the substrate for it is unusually good"; here the agent layer arrived **first** and the
substrate it chose was the **permissive** one. Agents colonise the layer with no gatekeeper.

**The caution, measured:** three further AI-radio repos (`writ-fm` 384★, `Claudio-FM` 79★, `tysa` 27★)
carry **no licence at all** — **490 of the 2,385 stars in the layer are unusable**, absence verified
against 200 READMEs on both branches.

### 3. The dated event in this plane: Icecast's old line goes end-of-support in **34 days**

Icecast **2.5.0** became the stable line on **2025-12-31**; **support for 2.4.4 ends 2026-12-31**; and
**Debian's tracker shows the 2.5.0 migration BLOCKED** ("Updating icecast2 would introduce bugs in
testing"). Simultaneously two things moved: **Liquidsoap now ships an experimental built-in
Icecast-compatible server** (so the separate daemon becomes optional), and **`DatanoiseTV/tinyice`
(Apache-2.0, 373★) was pushed the day of this pass** — the only permissively-licensed Icecast-compatible
server located anywhere.

**So the incumbent is EOL inside the month, its distro successor is blocked, and both replacements
appeared this year — one inside the orchestration layer, one permissive.** This is the clearest migration
trigger in the plane and it needs no client education: the date does the arguing.
*(Caveat: `icecast.org` is outside this session's network policy; both dates are secondary-source.)*

### 4. The commercial centre of radio moved to the dashboard, and the open standard lost

The two platforms between a station and a car screen are **DTS AutoStage** (Xperi, proprietary) and
**RadioDNS** (open ETSI standard). The scoreboard as of this pass:

- **AutoStage:** daily in-car audience measurement from **6 million vehicles**, **300+ US local
  markets**, new **Broadcaster Portal** at NAB 2026, **free to stations** because carmakers pay Xperi.
- **RadioDNS:** self-reported **2.5M+ cars**, "thousands of stations" — and Radio World describes
  **"limited take-up by car manufacturers"**. Its entire open toolchain is **96 stars**; the standards
  body's own Java library has **10**; the EBU's full-featured manager has been **dormant since 2023 with
  89 open issues**; two client libraries have not moved since **2011** and **2008**.

**The open standard is not losing on licensing or on technical merit — it is losing on maintenance and
OEM distribution.** And the carmakers hold the last word regardless: per Radio World, both RadioDNS and
AutoStage only *"provide guidelines and suggestions for the OEMs"*, while automakers retain
*"a lot of creative license in how they take the information and display it."*

**The trend to watch:** AutoStage is becoming a **measurement currency**, not just a display layer. Once
in-car listening from 6M vehicles is reported across 300+ markets, the station that does not feed it is
not merely invisible — it is **under-counted in the ratings that price its inventory**. Townsquare's
**0.5 share before supplying metadata** is the first published number quantifying that penalty. Expect
more such figures in 2027; they are the strongest sales evidence this plane will produce.

### 5. The knowledge-content law, fourth instance — and the first time the gate is an **IEC paywall**

This KB has recorded the law three times (CPT in healthcare, MedDRA in pharmacovigilance, MDS/standards
in the IP plant): *the regulator creates the obligation, but the licence on the knowledge content decides
whether open source can meet it.* Radio supplies the cleanest test yet, because the **same plane contains
both outcomes**:

| Standard | Body | Access | Open implementations |
|---|---|---|---|
| DAB (EN 300 401), DRM (ES 201 980), SPI (TS 102 818 / 102 371), MOT (EN 301 234) | **ETSI** | **free** | **They exist** — ODR chain, dablin, welle.io, AbracaDABra, python-dabepg |
| **RDS (IEC 62106)** | **IEC** | **sold per document** | **Monoculture**: 7 of 7 transmit encoders GPL-3.0, hobby scale |
| **HD Radio (NRSC-5)** | NRSC / **Xperi patents** | document published, **technology patent-licensed** | **Receive only, permanently** — `nrsc5` decodes; nothing encodes |

**ETSI's free publication is why European radio has an open stack at all.** Where the specification costs
money (IEC), the implementations are hobby-scale and uniformly copyleft; where the **technology** is
patented (HD Radio), the transmit side is **structurally impossible** rather than merely thin. **Same
industry, same decade, three access regimes, three completely different supply curves.** This is the
strongest natural experiment supporting the law anywhere in this KB.

### 6. Three standards, three regions, and LATAM has not chosen — which is itself the trend

EMEA runs **DAB+** (166.6M receivers, +>10% YoY, ~100% factory fit in Italy, 98% in France). North America
runs **HD Radio** (~125M vehicles, but only **18–21% of FM stations**). APAC's largest deployment is
**DRM** in India (37–41 high-power MW transmitters, ~13M cars). **LATAM has no decided standard**, and the
closest source to the question argues the eventual Brazilian answer will be **none of the three** — with
Anatel historically declining to mandate one at all.

**Consequence for 2027 planning:** the terrestrial-digital engagement that is real in EMEA has **no LATAM
equivalent to sell yet**, and pretending otherwise is how a regional plan goes wrong. What *is* sellable
in LATAM is the **standard-independent** layer — internet delivery (where the Icecast EOL lands on
everyone equally) and the MIT agent layer. See `intel/market.md` for the full informed gap, including the
Argentina and Mexico **zeros**.

### 7. AI on air is becoming a regulated act, and radio is where it is most visible

The AI-DJ repos are MIT and ready, but putting a synthetic voice on a licensed transmitter is now a
regulated act in several jurisdictions, and **2026 is the year the dates landed**: China's synthetic-content
labelling (from 2025-09-01, fines to **¥50m**); India's intermediary obligations for synthetically
generated content (**2026-02-20**); Korea's AI Basic Act (**2026-01-22**); Vietnam's AI law
(**2026-03-01**); California's AI Transparency Act provenance duties (**2026-08-02**); most EU AI Act
requirements (**August 2026**), with the AI Omnibus in force **2026-07-27** pushing Annex III high-risk
obligations to **2027-12-02**; Canada's "AI for All" strategy (**2026-06-04**) including watermarking.
Two are radio-specific and worth naming: **Australia's media regulator published sector papers in April
2026 mapping AI use across television, radio and news** — the only regulator found to examine radio
directly — and **Radio France added an annex in April 2026** restricting synthetic voice (already in this
KB from an earlier pass). **Chile's bill** on AI-generated imitations of a person's image, body or
**voice** is the most on-point LATAM instrument for an AI presenter, and **Brazil's electoral court
prohibits synthetic audio** favouring or harming a candidacy.

**The composable consequence:** the MIT agent layer plus a per-jurisdiction policy engine is now a
product shape, not a thought experiment — and radio is the medium where an unlabelled synthetic voice is
hardest to hide and easiest for a regulator to sample off-air.

---

## Pass 47 (2026-11-27) — trends in the weather desk, environmental data & on-air meteorology

**1. The AI weather models became permissively licensed, and almost nobody in media has noticed.**
Within roughly eighteen months, global AI forecasting went from research demos to **operational systems
with open code**: Microsoft's **Aurora** is MIT for code *and* weights; Google's **WeatherNext 2 /
Cyclones** line is Apache-2.0 code with **CC BY 4.0** on everything else; ECMWF's **anemoi** is
Apache-2.0 *and is the backbone of operational AIFS*. A capability that was a national-institution
monopoly is now a dependency a studio can install. This is the single most actionable trend in the plane.

**2. The licence moved from the repository to the artefact — and tooling has not followed.** For an AI
model, the governing licence attaches to the **weights**, which no SPDX field, badge or source-tree SBOM
scan can see. Both failure directions were observed this pass in the same plane: **Pangu-Weather** has
*no licence file at all* while its README forbids commercial use, and a widely-cited public catalogue
still reports **GraphCast's weights as non-commercial** when the repo's own 2026 README licenses them
CC BY 4.0. Expect "weights licence" to become a distinct CI check in 2027; today it is a manual read.

**3. Open data policy is diverging from open data *supply* in North America.** ECMWF went **fully open
(CC-BY-4.0, no information cost) on 2025-10-01**; NOAA data remains public domain but the FY2026
submission cuts NOAA **>25 %**, eliminates the research office, ends the billion-dollar-disasters
database and has already curtailed **weather-balloon launches**, with GeoXO satellite capability cut.
The licence terms improve while the observation base thins — and AI models that were trained on that
public record are the beneficiaries of its past, not its future.

**4. The licence on the *act* is emerging as a harder gate than the licence on the data.** Japan's
amended **Meteorological Service Act (full effect end of May 2026)** requires a **JMA permit to provide
forecasts to users in Japan regardless of operator location**, with public naming of unlicensed
operators. This is new vocabulary for this KB: a state permit on the *activity*, orthogonal to every
code and data licence. Any plane where a profession is licensed (medicine, law, engineering,
meteorology) should now be checked for it.

**5. Acquisition route is becoming a licence determinant.** The same physical fields — **BoM, CMA,
CPTEC, IMD, JMA, MF, NCMRWF** — are **CC BY-NC-4.0 through ECMWF's TIGGE** while the originating
services publish on open terms directly. Provenance metadata must now record *where a feed was
obtained*, not just what it is. Generalises to every dataset in every industry in this KB.

**6. Open source is the actual infrastructure of global weather data exchange.** **89 of 116 operational
WIS2 nodes (76 %), covering 92 WMO Members, run the Apache-2.0 `wis2box`** as of 2026-06-30. This is the
clearest case in the whole KB of open source being not an alternative to the institutional system but
*the institutional system itself* — with bandwidth in LDCs/SIDS, not licensing, as the binding constraint.

**7. Weather is the lever local media is actually pulling for engagement.** TEGNA's weather-led
personalised apps across **50 markets** and vendor-reported app video lifts (WDBJ: **6 000 → 236 000**
monthly views) place weather at the centre of the local-news retention strategy — while publishers lose
search referrals to AI answer engines (pass 30's plane). Weather is first-party, habitual, and
immune to the referral collapse: a structural reason it is where budget goes.

**8. The on-air layer is a stable, crowded, entirely proprietary market and shows no sign of opening.**
Eleven-plus active vendors shipping through 2026 (Chyron Weather 2.3 in February, 2.4 in June), zero open
peers. The honest prediction is that this does **not** change, because the deliverable is brand rather
than capability — see the falsifiable prediction recorded in `compose/patterns.md` for this pass.

## Pass 48 (2026-11-27) — the post-publication plane: corrections, retractions and the erasure request

The eight-file grep that opened this pass found the whole post-publication vocabulary missing. What the
research then found is a plane where the law is accelerating in three regions and the code is going
backwards.

### 1. The judgment layer regressed — a first for this KB

Across 47 prior passes the structural law held in three steps: declaring is a format problem (healthy),
honouring is a judgment problem (dormant), liquidating is pure judgment (nothing). Pass 48 confirms it a
sixth time and adds a new failure mode: **`ethyca/fides`, the only mature open-source DSAR platform —
484★, 4,774 commits, Apache-2.0, CLI + admin UI + Privacy Center — was archived on 2026-08-28.** Its
predecessor `fidesops` was archived in 2022. The layer did not fail to appear; it appeared, matured and
was switched off, and what replaced it is ★2–4 micro-tools pushed in Nov 2026. When a plane's economics
do not support a maintainer, open source does not degrade gracefully — it stops.

### 2. The standards ceiling is three enum values

Read from the schema files rather than the documentation: ninjs `pubstatus` is an enum of exactly
`usable` / `withheld` / `canceled`, **unchanged across v1.2, v1.4 and v2-rc**. That is the complete
machine-readable vocabulary the news industry has for "do not read this story any more". No reason code,
no correction text, no pointer to the corrected version, no de-indexing instruction, no effective date.
schema.org does better (`correction`, `correctionsPolicy`, `CorrectionComment`, from The Trust Project)
and still files `correction` under "new/pending". **The interchange format cannot express the remedy that
courts are now ordering** — which is exactly why every implementation above it is bespoke.

### 3. "De-index" is an SEO word, not a legal one

In open source the plane's vocabulary exists only in its marketing sense: `noindex` returns 4,902 repos,
all sitemap and SEO tooling; `deindex` returns 24, of which the top hits are an **Illumina DNA-barcode
deindexer** and an OpenCOLLADA deindexer. `noindex takedown` returns **zero repositories**. `errata
newsroom`, zero. `right of reply`, 77 results and zero relevant. A publisher served with a de-indexing
order is, in open-source terms, alone.

### 4. The remedy the law actually wants is *anonymise and hide*, not *delete*

This is the most commercially useful trend of the pass, and it inverts the obvious product. Italian
practice reported this year has the **publisher insert metatags** that hide an article from general search
engines **while keeping it in the historical archive** — and a 2026 ruling attached damages to *delay* in
de-indexing. So the deliverable is not an erasure button. It is: keep the URL resolving, suppress the
search footprint, record the effective date, and prove it. Note the source quality: this comes from legal
commentary (edit.legal), not the ruling text, so it is carried here as **reported, not confirmed** —
see the informed gaps in `intel/market.md`.

### 5. The compliance layer grows at half the rate of everything else in this KB

Subject-access-request software: **$1.57B (2025) → $1.78B (2026), 13.3% CAGR** (The Business Research
Company via Research and Markets). Every creative plane in this KB runs 25–36%. The gap is the finding:
the obligation is growing fast while the *tooling* market grows slowly, because the work is absorbed by
lawyers and editors rather than software. That is a services opportunity, not a licence opportunity —
which is the right shape for Globant.

### 6. Where AI adoption actually lands in European media

imec-SMIT (May 2026) finds Europe's media sector most active at the application layer, in three areas:
**archive search and retrieval**, newsroom productivity, and audience-facing products. The first of those
is this plane's liability surface — the better the archive search, the more findable the article somebody
has a legal right to make unfindable. Adoption of retrieval and exposure to erasure duties are the same
project, and nobody is selling them as one.

## Pass 49 (2026-11-27) — trends in the local & community news plane

### Trend 1 — **The supply of local coverage is collapsing on a measured curve, and the demand signal is now unambiguous**

United States, from the Medill State of Local News 2026 report published **2026-10-13**, as reported by
Poynter, Editor & Publisher and Radio Ink (see the sourcing caveat below):

| Measure | 2026 figure |
|---|---|
| Counties with no locally based professional news source | **238** — up 26 year-on-year, the largest single-year jump in Medill's research |
| Newspapers closed or merged in the past year | **170** — more than three a week |
| People with limited or no access to local news | **~47 million** |
| New local news operations launched in the year | **75**, most of them digital-only |
| Traffic to the websites of the 100 largest local newspapers | **−50% over four years** |
| Share of local commercial TV newsrooms owned by 10 chains | **75%** |

Poynter attributes the desert spike primarily to consolidation at two smaller Midwest newspaper
chains, and Medill links the traffic decline to growing consumer use of AI platforms. Illinois has lost
more newspapers than any other state.

**Sourcing caveat, stated rather than hidden:** the Medill primary report is **not reachable from this
session** (`localnewsinitiative.northwestern.edu` is outside the allowed network domains), so these
figures come from secondary reporting. The secondary sources **disagree on the prior-year baseline** —
one gives the 2025 desert count as 212, Poynter gives the prior year's closures as 136, and Medill's
own 2025 report is cited at 148. The **2026 figures above are consistent across sources; the
year-on-year deltas are not.** Quote the levels, not the deltas.

### Trend 2 — **The gathering layer is twelve years mature and permissive; the judgment layer does not exist**

Measured this pass, not asserted: `public meeting agenda scraper` returns **3 repos in the world**;
`council minutes summarization` returns **7**, top four holding **2, 0, 0, 0** stars;
`city council meeting transcript` returns **19**, top four summing to **7** stars. Below them sits a
mature, permissive, actively-pushed stack — `city-scrapers` (MIT, 381★, 2026-11-24), `pupa` (BSD-3,
91★, 2026-11-13), `python-legistar-scraper` (BSD-3, 53★, 2026-11-06), `civic-scraper` (Apache-2.0,
82★), `klaxon` (MIT, 685★, pushed the day of this pass).

And the demand is live: **three of the seven** `council minutes summarization` repos were pushed in the
three weeks before this pass, all at 0–2 stars, by people who have evidently not found each other.
The plane's shape is therefore the inverse of the generative-media planes: *the plumbing is solved and
free; the editorial judgment layer is unbuilt.*

### Trend 3 — **The incumbent runs on an open model, so the moat is ingest and review, not AI**

Hearst's **Assembly** automates transcription, keyword detection and summarisation of city-council,
school-board and other public meetings, and its transcription runs on a **self-hosted Whisper**
instance (INMA, reporting Hearst's own account); its newsroom guidance still tells journalists to
refer to the source material before publishing. Independent reporting on AI-native newsrooms (iMEdD
Lab) describes the same pattern — a live transcription-to-draft pipeline with a human editing and
fact-checking every draft. One small newsroom's published pipeline goes further and **kills the post**
if the generated summary attributes a statement to an official that is not in the transcript.

Three consequences. The model layer is commodity and already banked in this KB (`whisper` 58×,
`pyannote` 17×). The defensible work is per-jurisdiction ingest and the verification gate. And the
**verification gate is the sellable artefact**, because it is what makes the output publishable.

### Trend 4 — **A CC0 registry produced a healthy ecosystem: the first positive instance of this KB's own law**

Eleven passes recorded the law negatively — paywalled registries (CPT, MedDRA) and membership-closed
identifiers (ISRC, ISWC, ISAN, EIDR) each produced a tooling vacuum. Here the jurisdiction identifier
is **CC0-1.0** (`opencivicdata/ocd-division-ids`, 186★/99f) and the legislator dataset is **CC0-1.0**
(`openstates/people`, 162★/126f) — and the surrounding tooling is permissive and alive. **The law
predicts both directions, and this is the control case it previously lacked.**

### Trend 5 — **Stars are the wrong metric here; forks are the installed base**

`City-Bureau/city-scrapers-template` has **42 stars and 94 forks** (0.45 ★/fork). `openstates-core`
30/44. `openstates/people` 162/126. `scrapers-ca` 36/30. In the generative-media planes this KB
records ratios of 5–20×. A template forked more often than it is starred is a template being **run**,
once per jurisdiction. Corollary for every future pass in this plane: a 3★ repo pushed yesterday
(`city-scrapers-atl`, `city-scrapers-det`) is a live newsroom deployment, not a toy.

### Trend 6 — **Money is arriving as public and philanthropic funding, which changes what the deliverable is**

The UK prices council coverage directly: the BBC's Local Democracy Reporting Service funds **165
reporters** across **118 contract areas** at **£40,790 per reporter per year** outside London and
**£43,190** in London, +2% annually from year two, under contracts running to **end-2027** —
coterminous with the BBC Charter. In the EU, EMFA requires public funding of media to be allocated on
**public, proportionate and non-discriminatory criteria** and to be adequate, sustainable and
predictable, preferably multi-year. In both cases the buyer is accountable for *how the money was
allocated*, which makes an auditable allocation-and-output record part of the product rather than a
nice-to-have. See `intel/market.md` for the regional detail and `compose/patterns.md` Pattern 108.

---

## Pass 50 (2026-11-27) — trends in the talent, casting & performer-consent plane

### 1. The structural law of this KB now has a second subject, and the shape is identical

Pass 8 measured the rights-reservation gradient on **content**: declaring a reservation is a format
problem and `ai.robots.txt` has 4,265★; honouring it is a judgment problem and `datadiligence` has 41★
and has been asleep since 2024; liquidating the obligation is pure judgment and measured **literal
zero**. Pass 50 measured the same gradient on **human identity** and got the same answer:
**declare** → HCS 1.0 draft plus a live public registry plus `grantmark` (Apache-2.0) binding it to
C2PA `cawg.consent`; **honour** → `consentor` (MIT, 0★) and `pratidhvani` (Apache-2.0, 26★);
**settle** → `residuals calculation film` = **0 results**, now confirmed across passes 5, 17 and 50.

**The law is therefore not about content versus identity. It is that a declaration is a schema and a
payment is a judgment** — and open source ships schemas. This is the most generalisable finding of
fifty passes because it predicts, before any search, which half of a new plane will be empty.

### 2. The plane is being started constantly and finished never — and the licence is the tell

Eight of the nine purpose-built artefacts in this plane were **created in the last ninety days**, three
were **pushed on measurement day**, and **eight of nine carry no licence file at all**. This is not a
dormant plane and it is not a healthy one. It is a plane where unconnected people repeatedly build a
casting pipeline, publish it, and never add a grant. The defect is not abandonment — several are
actively pushed — it is that **the artefacts never become adoptable**, so every new builder starts over
instead of forking. Nine repositories, 2 stars between all nine.

### 3. The most-starred thing in the plane shipped consent as a feature, not as policy

[svayatta/pratidhvani](https://github.com/svayatta/pratidhvani) took **26★ in eight days** (created
2026-11-19, 5 forks, pushed 2026-11-27) as a self-hosted Indian-language voice cloner whose headline
features include **consent and an inaudible watermark**. Every dedicated consent-*registry* repo in the
plane sits at **0★**. The signal is commercial, not ethical: **a generator with consent built in is a
product; a consent registry is an obligation, and obligations do not accrue stars.** Prediction
recorded in `agents/trending.md` so it can be falsified next pass.

### 4. The law arrived in 2026 — in the wrong order, from a North American assumption

For eleven passes this KB treated the US guild agreements as the operative constraint on performer AI.
That is now only partly right, and the ranking inverts:

| Region | Instrument | Status on 2026-11-27 |
|---|---|---|
| **LATAM** | Mexico: Federal Labour Law + Federal Copyright Law reforms | **IN FORCE 2026-05-15.** Statutory, survives the contract, names dubbing actors, IMPI can fine |
| **North America** | SAG-AFTRA 2026 TV/Theatrical | **In force 2026-07-01**, but **contractual** — it binds signatories, not everyone |
| **North America** | NO FAKES Act (S.4591 / H.R.8915) | **Still a bill.** On the Senate calendar since 2026-06-24; Congress ends 2027-01-03 |
| **EMEA** | Denmark L 49 §65a | **Bill**, introduced 2026-10-08, hoped in force start of 2027 |
| **APAC** | China virtual-human rules | **Draft** (April 2026). Labelling Measures themselves in force since 2025-09-01 |

**The only in-force statute creating a performer's right against AI replication is Mexican.** Any deck
that presents this plane as a Hollywood compliance story is describing a contract and calling it a law.

### 5. The judgment layer is migrating to courts, which changes what software has to do

India's Delhi High Court issued a run of interim personality-rights orders through 2026 (Kriti Sanon
2026-10-29, next hearing 2026-12-10; Akira Nandan; Vivek Oberoi; Aman Gupta; Ravi Kishan; Jubin
Nautiyal over a synthesised singing voice) while **explicitly refusing blanket injunctions** and asking
for claims framed defendant by defendant and content by content. That is a different software
requirement from a statute: not a compliance mode but **per-item evidence** — which item, which
defendant, which date, which consent. It is the same conclusion pass 5 reached about EMEA reservation
and pass 20 about source protection: **the deliverable is the audit trail.**

### 6. A measurement defect worth a standing rule: repository metadata can fabricate relevance

`Grey59Queen/codev` (1★) ranked **first** for both `performer consent` and `likeness rights` with zero
relevance, because its GitHub **description field contains the entire text of the CC0 licence** — every
rights term in the vocabulary, in the field search ranks on. Combined with this pass's other false
abundances (`self-tape` = 106 results topped by a **373★ dotfiles repo**; `synthetic performer` = 14
results that are all AI-content *taggers*; `right of publicity` topped by a repo named
`GNU-GENERAL-PUBLIC-LICENSE-Version-3-29-June-2007-Copy`), the rule hardens: **rank on what a repo
does, never on what its metadata contains, and never on the total.**

### 7. Three licence readings a scanner got wrong in a single pass

`sfuentes/casting-profile-manager` was **asserted to be MIT by a search result** and has **no licence
file** (14 names probed, control README 200). `method-scheduling` is **dual MIT/Apache-2.0** where the
API reports Apache only. `OpenCATS` is **MPL-2.0 plus a bespoke 2007 "CATS Project" licence** where the
API reports `NOASSERTION` — the pass-8 `chromaprint` mechanism again, **the licence belonging to the
compilation rather than the repository**. And the plane's sharpest irony: `eliem08/likeness-license`, a
tool for licensing your likeness, carries a LICENSE reading **"proprietary and confidential… All rights
reserved."** Licence by file read, every time.

## Over-the-air transmission — trends, added 2026-11-27 (pass 51)

**1. The licence of a media pipeline tracks its transport, not its function — new law, logged.**
Pass 8 measured contribution → transcode → package → origin → edge → player and found it **permissive
nearly everywhere**, gated by **patent pools** rather than copyright. Pass 51 measures the *same
function* over the air and finds **GPL-2.0, GPL-3.0 and AGPL-3.0 with a single BSD-2 exception**, no
patent question raised at the modulation layer at all, and star counts two orders of magnitude lower
(19–195★ versus 20,000–30,000★). The function did not change; the transport did. **Mechanism:** IP
delivery is a CDN business with corporate contributors; over-the-air delivery is an instrument business
whose authors are researchers and whose users hold licences. **Falsifiable prediction, baseline today:**
if a corporate contributor ever enters the modulation layer it will arrive **permissively licensed and
on the receiver side** (ROUTE/DASH), not the transmitter, because the receiver ships in silicon.
Baselines to re-measure: `gr-atsc3` 51★, `gr-isdbt` 195★, `rt-mbms-modem` 26★, `tsduck` 1,103★.

**2. A rights grant can arrive with its legal basis deleted — a new licence category, and the worst
seen so far for a regulatory input.** NTIA/ITS releases its propagation models under a notice resting on
**17 U.S.C. §105** (works of federal employees are outside US copyright) **plus** an express
"non-exclusive irrevocable and unconditional… royalty-free" grant covering countries where NTIA *does*
hold rights. The ITU-R model implementations reuse **that same text with the §105 paragraph and the
express grant removed**, leaving a warranty disclaimer and a bare statement of permission from a
**personal account that has no statutory equivalent of §105 to stand on**. GitHub reports
`NOASSERTION`. **This is not an OSI licence**, and it governs the propagation mathematics behind
coverage filings in EMEA, APAC and LATAM. **Worse than the pass-8 `chromaprint` case**, because
chromaprint's problem was ambiguity about *which* licence applied; here the question is whether an
effective grant was ever made.

**3. The compilation licence has a second, more dangerous form: it can live in the build, not the
source.** Pass 8 found `chromaprint`'s **source tree** was a compilation. **TSDuck inverts it:** the
source tree is clean BSD-2 with **no third-party source at all** — a source-tree SBOM scan passes —
while `OTHERS.txt` records that the **build scripts download Dektec's proprietary, binary-only DTAPI**
and the **installers ship it**, alongside libsrt (MPL-2.0) and librist (BSD-2) binaries. **Rule for CI
across all twelve industries: resolve the licence of what the build downloads and what the installer
ships, not of what the repository contains.** A clean source scan is not evidence of a clean
redistributable.

**4. Four regions, four standards, and for the first time in this KB the divergence is physical.**
Earlier passes found divergence in *rules* (AI disclosure, consent, reservation) and concluded each time
that the portable asset is a **per-jurisdiction policy engine**. Here the divergence is in **silicon and
spectrum**: ATSC 3.0 (US, Korea, now Brazil), DVB-T2 (Europe), ISDB-T → Advanced ISDB-T (Japan), 5G
Broadcast (European trials). **A policy engine cannot abstract a modulation scheme.** This is the one
plane where "build once, configure per region" is **false**, and saying so early is worth more to a
client than any architecture diagram.

**5. The regulator-maintained reference library is a real and rare asset class.** `NTIA/itm`, `p528`,
`ehata`, `if77`, `LFMF`, `p2108`, their **separate test-data repositories**, **Python wrappers** and a
**published Quarto wiki** were all pushed in a **single coordinated sweep on 2026-11-24**. That is CI and
release discipline, not a code dump — from a government research arm. Compare the ITU-R equivalents:
one personal account, **P.1546 untouched since 2024-08-16**, top artefact **15 stars**. **Where a
regulator maintains its own models, open source in that plane is healthy; where it does not, the plane
runs on key-person risk.** This is the formatting-versus-judgment law of passes 6/11 extended to
*regulatory inputs*: the regulator does not have to mandate the code, it has to **maintain** it.

**6. Europe has been formally told not to expect a common answer, and that is a product spec.** The
**RSPG concluded a common post-2030 UHF spectrum policy across Europe is impracticable**, and the
**EBU's September 2026 WRC-27 opinion** records it. Meanwhile the decisive conference is **WRC-31, not
WRC-27** — a widely-held misreading worth correcting in any client conversation — and EU law protects
470–694 MHz only **until at least 2030**. A regulator-level admission that harmonisation will not happen
converts "roadmap uncertainty" from a risk into a **billable, per-country deliverable**.

**7. The successor that never inherited the audience.** `drmpeg/gr-dvbt2` is **archived, read-only,
last pushed 2018-10-31, 73★**; its living replacement `gr-dvbt2ll` sits at **19★**. Europe's terrestrial
standard has its most-followed open transmitter frozen for eight years while the maintained one is
largely undiscovered. **`OpenCaster` shows the sibling pathology: 79 forks against 74 stars** — more
people modify it privately than follow it publicly, which is what a stale-but-necessary tool looks like
from the outside. **Diagnostic to reuse: when forks exceed stars in an infrastructure plane, the tool is
load-bearing and unmaintained — and that is an engagement, not a red flag.**

**8. The agent layer of an infrastructure plane is one repository deep, for the second pass running.**
Pass 50 found nine casting repos at 0★. Pass 51 finds **one maintained ML tool in the entire
over-the-air chain** — `SpectrumAlert`, GPL-3.0, **22★** — with everything else behind papers and no
public maintained code. **Two consecutive infrastructure planes where the "AI agent" layer is
rounding-error-sized.** The pattern is now strong enough to predict: in planes whose users are licensed
operators rather than consumers, **the agent layer does not exist yet and the engines do**. Sell the
engine integration; do not promise an agent ecosystem that is not there.


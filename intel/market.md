---
industry: media
region: Global
updated: 2026-11-25
---

# 🗺️ Market Map — Media & Entertainment

> Key players, market size, and opportunities **placed by region**.
> This file previously held two all-em-dash placeholder rows and four unfilled research stubs as
> live data. Replaced below with sourced findings, and with gaps stated explicitly as gaps.

## Market size — treat as a range, not a number

Published estimates for "AI in Media & Entertainment" **disagree by a factor of two**, and several
widely-quoted figures trace back to vendor marketing pages rather than primary research. Use the
range, and say it is a range:

| Estimate | Source type | Note |
|---|---|---|
| $35.77B (2026) → $87.44B (2030), ~25% CAGR | Market-research vendor | The figure earlier cycles of this KB carried as fact. It is one vendor's estimate among several. |
| $30.32B (2026), ~26.1% CAGR | Second vendor | Grand View / Business Research-class estimate. |
| $30.32B (2026) → $194.08B (2034) | Third vendor | Same 2026 base, wildly different horizon — the clearest evidence these are not interchangeable. |
| +$30.72B growth (2024–2028) | Technavio | Measures *growth*, not market size; frequently misquoted as a total. |
| **Media localization: $5.6B (2024) → $12.8B (2033), APAC fastest at 12.3% CAGR** | DataIntelo, via trade press | Added 2026-11-22. **A segment figure, not an "AI in M&E" figure** — and therefore the most usable number in this table, because localization is the segment this KB recommends leading with (trend 7) and the one where the open stack is ~80% complete. Still one vendor at second hand. |
| **Captioning & subtitling solutions: estimates for 2026 span ~$0.39B to ~$7.2B** | Eight market-research vendors | Added 2026-11-22 (pass 3). **An order-of-magnitude disagreement — the widest spread in this file, and the most honest thing in it.** High cluster: GMI ~$7.2B (2026) from $6.7B (2025) → $16.5B by 2035 at 9.4% CAGR; Research Nester $6.25B (2026); Data Bridge $6.50B (2025) → $13.28B (2033). Low cluster: MarketGrowthReports $407.33M (2026) → $796.67M (2035); Business Research Insights $0.41B → $0.8B; MarkWide $385.6M; WENKH $590.48M. Narrower cuts: services-only $732M (2025) → ~$1.3B (2032); another subtitling-and-captioning cut $3.16B (2026) → $6.47B (2035). **The spread is a scope artefact**, not noise: the high cluster counts live captioning, transcription and translation services, the low cluster counts software licences only. **Ask which definition a client means before quoting any of them.** |
| **Audio description market: no data found** | — | Added 2026-11-22 (pass 3). Searched; **no vendor sizing for audio description surfaced at all** — despite AD being a hard FCC quota and an EAA duty. An unsized market with a statutory mandate and a 56-star tooling ceiling. Recorded as an informed gap, and arguably the most interesting line in this table. |

| **Production / post-production (this plane): no AI-specific sizing found** | — | Added 2026-11-25 (pass 6). Searched; **no vendor sizing for "AI in VFX/animation production" surfaced at all.** The usable regional figures are segment figures from trade bodies, not AI figures: India animation+VFX **₹48bn** VFX / **₹138bn** combined by 2028 (FICCI-EY 2026), Indian VFX **$1.1B (2025) → $1.8B (2034)** at 5.58% CAGR (IMARC), LATAM screen/VFX **~$1.5B (2026)** (vendor directory, unverified — see LATAM). **The plane with the healthiest open substrate in this KB is the one with no market sizing**, which is a finding about analyst coverage, not about the market. |

**Low confidence on all of them.** The defensible statement to a client is directional: double-digit
CAGR, mid-$30B scale in 2026, with generative video the fastest-moving segment.

## Global players

| Company | Type | Strength | Weakness |
|---|---|---|---|
| Adobe | Incumbent tooling | Firefly + the Content Authenticity Initiative; owns the provenance standard's reference implementations | Inspect/CAI apps proprietary; subscription resistance among creators |
| Netflix | Operator / open source | Publishes the quality and delivery standards the industry measures with (VMAF, Photon/IMF) | Tooling is infrastructure, not creative AI |
| **NRK · TV 2 Norway · SVT · BBC · EBU** | **Public broadcasters as open-source producers** | Added 2026-11-22. They do not sell software, they *publish* it: **Sofie** (MIT live/news automation, NRK-commissioned, used daily by NRK/BBC/TV 2), **CasparCG** (SVT), **sisyfos** (TV 2 Denmark + NRK), and the EBU's CC0 index of the whole field. This is where the permissive broadcast stack actually comes from. | No commercial support, no roadmap guarantees, and documentation written for their own engineers — which is precisely the gap an integrator fills |
| ElevenLabs | Voice AI (EMEA) | Raised $500M at an $11B valuation (Feb 2026); de facto voice standard | Closed; licensing cost at scale |
| Synthesia | Avatar video (EMEA/UK) | Enterprise comms video at scale | Template-bound output |
| HeyGen | Avatar/agentic video | Released Hyperframes as Apache-2.0 (87,525★) — rare genuinely-open vendor play | Core product still closed |
| Runway / Luma / Pika | Generative video | Frontier quality | Closed weights; no on-prem story |
| Suno / Udio | Generative music | Licensing deals with Warner and Universal respectively | Active Sony litigation |
| Tencent / Alibaba / Zhipu | APAC model labs | Ship real open weights (HunyuanVideo, Wan, CogVideo) | Custom or territorially-limited licenses |
| Accenture · Capgemini · HCLTech · IBM · Infosys | SI competitors | Named ISG Leaders in EMEA M&E services | Generic AI practice, little media-standards depth — **this is the gap Globant can attack** |

## Opportunities by region

### North America

- **Union-compliant AI production.** The 2026 WGA, SAG-AFTRA and DGA agreements now govern AI use:
  informed consent plus compensation for digital replicas, fully AI-generated performers limited to
  exceptional cases, and WGA transparency/notice duties. The 2025 video game agreement already
  carries consent and disclosure terms. **Opportunity:** a consent-and-provenance ledger for digital
  replicas — who consented, to what, for which usage window — built on C2PA. Nobody is selling this
  as a product; studios are tracking it in spreadsheets.
- **Licensing-and-litigation posture.** Warner↔Suno and Universal↔Udio are licensed; Sony is
  litigating both. Rights-clearance tooling that can prove training-data provenance is directly
  commercially relevant.
- **Internal workflows are where the money is.** Adobe's research finds AI spend concentrated in
  internal workflows with consumer-facing agentic experiences underinvested — so lead with post
  production, localization and archive, not a consumer chatbot.
- **The regulatory picture is state-level and in open conflict — added 2026-11-22.** There is still no
  comprehensive US federal AI statute. What binds a media client:
  - **California AI Transparency Act** — obligations for **AI hosting platforms begin 2027-01-01**.
    This is the next hard deadline on the North American calendar and it lands on *platforms that
    host* synthetic content, which is most streamers and UGC services.
  - **TAKE IT DOWN Act** — the main narrow federal statute, covering non-consensual intimate imagery
    **including AI-generated**. Directly relevant to UGC moderation pipelines.
  - **Texas TRAIGA** (effective 2026-01-01) and **California SB 53** (frontier models).
  - **New Jersey** treats deceptive AI media used for an unlawful purpose as a crime.
  - **Executive Order 14365** (2025-12-11) created a DOJ task force to challenge state AI laws, and a
    June 2026 bipartisan federal preemption draft has stalled. **Net effect: the state rules are the
    operative ones, and they are being litigated.** Advise clients to build to the strictest state
    requirement rather than bet on preemption.
  - ⚠️ **Colorado is genuinely unclear.** Sources conflict: one reports the AI Act was repealed and
    replaced before taking effect (refocused on automated decision-making), another reports xAI suing
    to block it with DOJ intervening. **Do not state a Colorado position in a client document without
    checking the current statute directly.**
- **Canada — new, and it names watermarking.** The federal **"AI for All" strategy (2026-06-04)**
  covers AI literacy, **watermarking** and a certification program. There is still no federal AI
  statute (AIDA died with Bill C-27 in January 2025), so **PIPEDA and Quebec's Law 25 are the binding
  instruments** for any AI system touching personal information — which includes a performer's voice
  and likeness. A Canadian engagement is a privacy-law engagement, not an AI-act engagement.
  The watermarking line in a national strategy is a direct hook for the VideoSeal/AudioSeal + C2PA
  stack in `compose/patterns.md` Pattern 8.

- **The monetization plane — new 2026-11-22.** PwC puts global advertising **past $1T for the first
  time in 2025, rising to ~$1.4T by 2030**, with streaming still the largest single revenue component
  (~$56.3B) in 2030, and it names the **2026 World Cup in North America** as the region's major shared
  live event. Ad-supported tiers at the major streamers are the growing part of the US market and
  bundling has returned as the antidote to churn (Chambers, July 2026). **Opportunity:** the ad-break
  and yield stack in `compose/patterns.md` Pattern 9, with the audience graph of Pattern 10 as the
  prerequisite — Deloitte names fragmented cross-platform audience intelligence as the thing actually
  hampering monetization, and that is an Apache-2.0 data build, not a model build.
- **Buy-vs-build is shifting toward partnership.** Chambers records Netflix acquiring **InterPositive**
  (the AI-tools startup founded by Ben Affleck) and notes media companies increasingly **allying with
  AI developers rather than building in-house** — which is the engagement shape Globant sells into,
  and an argument for proposing composition over custom model work.
- **Informed gap, stated rather than implied:** the regional query returned **no specifics on US state
  AI statutes, Canadian federal legislation, or advertising-disclosure requirements**. The US voice-
  cloning activity already recorded above is the only concrete federal-level hook this pass confirmed.
  Treat NA ad-disclosure obligations as *unresearched*, not as *absent*.


#### Accessibility compliance — added 2026-11-22 (pass 3)

- **The deadline already passed, and that is the opening.** The FCC's caption **display-settings**
  rule reached its compliance date on **2026-08-17** (implementing CVAA §203). It applies to TVs,
  streaming devices and apps, and is judged on four factors: **proximity, discoverability,
  previewability, and consistency/persistence**. These are properties of the *player UI*, not of the
  caption file — so a client who bought "AI captions" has not addressed this rule at all. One useful
  scoping limit: a consumer-installed streaming app on a smart TV is **not** the manufacturer's
  responsibility.
- **The regulator has turned explicitly skeptical of automated captions.** The FCC's 2026 CVAA
  report (released **2026-10-07**) flagged *inaccurate automated captions*, inconsistent caption
  controls on video-conferencing platforms, and accessibility barriers in emerging AI-driven
  communication tools. **Commercial read:** pure-ASR captioning is now a regulatory liability in the
  US, not a saving. What is sellable is the workflow the regulator implicitly asks for — AI draft →
  human review → timing/conformance check — which is a *services* shape, and therefore Globant's.
- **The FCC sets no accuracy percentage.** It weighs errors in context and treats live captioning as
  harder than prerecorded. ⚠️ A widely repeated claim that the CVAA mandates **99% accuracy for AI
  live captions could not be confirmed against any primary source** and conflicts with the above —
  do not put it in a client deck.
- **Audio description is a hard quota here:** 50 hours per calendar quarter, in prime time or
  children's programming. Against that, the entire open AD tool layer peaks at 56 stars
  (see `agents/top.md`) — the sharpest mismatch between duty and tooling in this KB.
- **Online video scope:** programming that aired on US TV with captions must be captioned when
  distributed over the internet, including in OTT apps. Pure-online originals fall under ADA
  expectations rather than the CVAA — a distinction worth drawing explicitly in scoping, because it
  changes who the obligated party is.
- **Pipeline to watch:** **S.4322, the Communications, Video, and Technology Accessibility Act of
  2026** (119th Congress, introduced April 2026) would have the government recommend deadlines for
  captioning *and* audio description on online video. Not law — a reason to design for AD now.
- **Broadcast-grade is a real technical constraint:** US broadcast captions must conform to
  **CEA-608/708**, and consumer AI captioning tools do not emit those formats. `CCExtractor`
  (GPL-2.0) is the only maintained open path, and there is no permissive equivalent.
- **Low confidence, flagged not promoted:** a DOJ **ADA Title II** deadline of April 2027 for larger
  public entities appears in vendor material; not verified against a primary source.
- **Informed gap:** this pass found **no sourced data on the North American accessibility-vendor
  landscape or market shares** (Verbit, 3Play, AI-Media et al. appear only in their own marketing).
  Treat NA competitive positioning in this segment as *unresearched*, not *absent*.

- **Loudness compliance just moved into streaming — as a method, not a mandate (new 2026-11-22).**
  **ATSC revised A/85, its loudness Recommended Practice, on 2026-07-08** (announced 2026-07-15) and
  the revision extends guidance beyond traditional TV to **hybrid broadcast and streaming**. The
  statutory instrument, the **CALM Act** (FCC rules effective 2012-12-13, 47 CFR § 73.682(e)), still
  covers **television commercials only** — not radio, not internet delivery — and enforcement is
  complaint-driven. *The sellable framing:* the duty has not expanded, the industry's reference
  method has, and a streaming operator that ignores A/85 is out of step with its distribution
  partners rather than in breach of the law. Never pitch it as "streaming loudness is now regulated".
- **The opportunity is the workflow, not the measurement.** The permissive loudness layer is two
  small MIT repos (`libebur128` 498★, `pyloudnorm` 796★). Measurement is solved and free; the
  **auditable compliance workflow around it is not open source anywhere** (`broadcast QC agent` → 0
  results). A delivery-QC gate that produces an evidence trail is a small build against an
  obligation that touches every distributor in the region. See `compose/patterns.md` P13.
- **Public-domain primary sources are an asset here.** NARA publishes its preservation policy as a
  public-domain repository (`usnationalarchives/digital-preservation`), and `bagit-python` — the
  reference implementation of the archival transfer format — is public domain. For a US public-sector
  engagement, the standards and the reference code carry **no licensing cost at all**.
- **Adoption is board-level, which changes who the buyer is.** A Grant Thornton 2026 survey reports
  **87% of media and entertainment boards have approved major AI investments**; Akamai's *State of AI
  in Media 2026* frames the problem as converting broad experimentation into value. A 2026
  NewscastStudio survey found ~45% expecting broadcast/production technology budgets to rise.
- **Regulatory risk is comparatively low and that is a selling point.** Radio World reports **no
  federal AI law enacted** as of this pass, with legislation under debate. Media is lightly regulated
  next to banking or health, so in North America the binding constraints on an AI media build are
  **union agreements and the loudness/accessibility duties**, not an AI statute.
- **Informed gap:** this pass found **no sourced market-share data for broadcast QC or preservation
  vendors** in North America. Treat competitive positioning in this plane as *unresearched*.

#### Content identification & AI licensing — added 2026-11-22 (pass 5)

- **The buyer-side bloc for AI content licensing is American, and it has a standard now.** **RSL 1.0**
  (Really Simple Licensing) is governed by the US nonprofit **RSL Collective** and endorsed by
  **Reddit, Yahoo, Medium, Quora and Ziff Davis**, with Fastly and Adweek supporting without joining.
  It extends `robots.txt` into XML licensing terms including **pay-per-crawl and pay-per-inference**.
  **Commercial read:** North American publishers have declared terms faster than anyone has built the
  systems to administer them — there is no console, no audit trail, no per-asset policy store
  (see `verticals/solutions.md`). That administration gap is the engagement.
- **The enforcement posture is hardening on the infrastructure side.** Fast Company reports
  **Cloudflare taking a hard line against AI ingesting publisher content without compensation**, and
  TV Tech expects the industry to need a durable economic model for open-web media. Both point the
  same way: the metering and settlement layer is being demanded before it exists.
- **⛔ The compliance stack has an unlicensed root.** `rslstandard/rsl` ships **no licence file**, and
  nor does the active WordPress plugin implementing it. For a US client building AI-licensing
  compliance this is a real supply-chain finding, not a pedantic one — raise it in scoping. See
  `intel/trends.md` §27.
- **Regulatory asymmetry is the selling point here, as elsewhere in NA.** Radio World reports **no
  federal AI law enacted**; Grant Thornton notes regulatory uncertainty weighs less on media than on
  banking or insurance. So in North America the binding constraints on an identification/rights build
  are **guild agreements and contract law**, not an AI statute — which makes it a *faster* region to
  ship in, and worth saying out loud in a proposal.
- **EIDR is a North American institution with no open client.** The audiovisual registry US studios
  and distributors actually exchange IDs through is a membership association, and `eidr` returns
  **160 GitHub results with zero relevant hits**. Any NA studio integration is **registry
  integration against paid membership**, never an open-source adoption. Do not scope it as the
  latter.
- **Market weight, with the conflict stated:** compilations put North America at roughly **33.6%–40.6%**
  of the AI-in-media market depending on the research firm and the definition used, attributed to US
  studios and platforms. ⚠️ Cite the **direction** (largest region, by a wide margin), not the point
  estimate. One widely repeated vendor claim — **82% of global media organisations using AI in at
  least one production workflow**, attributed to IAB — **could not be verified against IAB itself**;
  do not put it in a deck.
- **Informed gap:** this pass found **no sourced data on North American rights-administration or
  content-ID vendor market shares** (the incumbents in royalty administration are private and
  publish nothing comparable). Treat NA competitive positioning in this plane as *unresearched, not
  absent*.

#### Added 2026-11-25 (pass 6) — the production plane: the gate here is a *labour contract*, not a statute

- **North America is the one region where AI in production is governed by collective bargaining
  rather than regulation, and that is an easier sell, not a harder one.** The IATSE Basic Agreement
  permits AI **"as a tool"** with limitations and establishes standing meetings on AI use; VFX workers
  on Marvel/Disney and *Avatar* projects have **ratified their first IATSE contracts**, and Apple
  Studios' in-house VFX artists reached a first contract including AI protections. SAG-AFTRA's
  four-year deal constrains AI performers with **no strike rights over AI until 2030**, and the 2026
  WGA and DGA agreements expand AI governance further.
- **What that means for a build.** A statute wants a label on the output (EMEA, APAC — see those
  sections). A labour agreement wants something different and more technical: **a per-shot,
  per-task record of what the AI actually did, who approved it, and which human work it did or did
  not replace.** That is an evidence-trail product, it maps exactly onto `OpenTimelineIO` +
  `OpenAssetIO` + render-job metadata, and no vendor is selling it. See `compose/patterns.md`
  Pattern 17 and Pattern 18.
- **The demand context is contraction, not growth.** Production jobs fell **over 35% between October
  2022 and February 2026** (Duke Tech Policy Center analysis). Pitch AI in NA production as *capacity
  per remaining head* and as *contract-compliance evidence*. A pitch framed as headcount reduction
  walks into the one constraint that is contractually enforceable here.
- **The substrate is already in the building.** Every ASWF project in `repos/foundations.md` pass 6
  originated in or is funded by North American studios (Pixar, Sony Imageworks, ILM, DreamWorks,
  Netflix). An engagement here does not need to introduce the open stack — it needs to **agent-enable
  the stack the client already runs**, which is a far shorter sale.
- **Informed gap:** this pass found **no sourced data on how widely NA studios have adopted the agent
  bridges** named in `agents/top.md` pass 6, and **no public figures for OpenCue or Kitsu/AYON
  deployment counts** at named studios. Treat NA pipeline-agent penetration as *unresearched, not
  absent*.

### EMEA

- **EU AI Act Article 50 is the forcing function, and the date is now confirmed.** Transparency
  duties for generative content: machine-readable marking of AI-generated media and deepfake
  disclosure by deployers. **Article 50 has applied since 2026-08-02** — the previous pass flagged
  this as "verify the exact date"; multiple independent sources now agree, though one gives 3 August
  for the wider Act's phased start.
  **⚠️ The live deadline, and it is imminent: AI systems placed on the market *before* 2026-08-02 have
  until 2026-12-02 to meet the Article 50(2) marking-and-detection duty.** That is **ten days** after
  this pass. Any client running a generative pipeline that predates August is out of compliance in
  under two weeks, and the remediation is exactly the Pattern 8 stack. **This is the single most
  time-sensitive sales fact in this KB** — it should lead any EMEA conversation this month.
  Supporting instruments to cite by date: the Commission's **voluntary code of practice on marking and
  labelling AI-generated content (2026-06-10)** and the **final Article 50 guidelines (2026-07-20)**.
  **Opportunity:** C2PA Content Credentials pipelines as a compliance product — `contentauth/c2pa-rs`
  is MIT-or-Apache dual-licensed, so this is buildable today with no license friction.
- **The broadcasters are lobbying to soften exactly this duty — know which side of it you are on.**
  On **2026-06-17** the **EBU**, with the main European commercial-broadcaster associations, wrote to
  the Commission asking it to narrow the deepfake definition, clarify when on-screen disclosure is
  required, and keep marking standards technically feasible. **Commercially this is a tell:** the
  industry's own trade bodies are saying the marking requirement is technically hard. That is a
  statement of demand for someone who can implement it, and it is why the measured watermarking
  tooling in `repos/foundations.md` matters more than the legal text.
- **Public broadcasters now have their own binding AI codes** — ARD/ZDF/Deutschlandradio/DW (joint
  code, January 2026), SRG SSR (2026-06-01), RAI (February 2026), Radio France (synthetic voices
  prohibited where they could replace staff vocal identity); published rules in southern Europe are
  concentrated in **Spain**, and most state-controlled broadcasters have none. Each published code is
  a written obligation with no enforcement tooling behind it — see `intel/trends.md` trend 9.
- **Smart TV platforms may become regulated gatekeepers.** In March 2026 the ACT (commercial
  broadcasters' association) asked the Commission to designate **smart TV operating systems and AI
  assistants** under the DMA. If that lands it reopens distribution and discovery terms for every
  broadcaster in the region — worth tracking, not yet actionable.
- **ElevenLabs has a studio/broadcaster unit** (ElevenProductions) on top of its $500M raise at an
  $11B valuation (February 2026). The competitive read: the voice incumbent is moving *up* into
  production services, which is Globant's layer.
- **⚠️ HunyuanVideo is unusable here.** Its license states it does not apply in the **European Union,
  United Kingdom or South Korea**. Any EMEA engagement must use Wan 2.2, LTX-Video, Open-Sora or
  CogVideo instead. This disqualifies a model that earlier cycles of this KB recommended without
  qualification.
- **Public money is on the table.** A €10M Horizon Europe call for a shared media AI platform
  (HORIZON-BRIDGING-2027-01-09, deadline 2027-02-16) requires watermarking and provenance tracking
  for newsroom-deployed AI modules — i.e. it is funding exactly the C2PA work above.
- ISG reports EMEA telecom/media firms moving to cloud-native AI-led supply chains, with Accenture,
  Capgemini, HCLTech, IBM and Infosys already positioned as Leaders.

- **The monetization plane — new 2026-11-22.** EMEA is the only region with a **consent-signalling
  obligation layered on top of the ad stack**: the IAB Europe TCF consent string (a **CC BY 3.0
  specification, not code** — see `intel/trends.md` trend 13) plus a banner layer for which
  `orestbida/cookieconsent` (MIT, 5,779★) is the practical permissive start. Budget the consent layer
  as a distinct workstream in any EMEA ad engagement; it does not exist in the other three regions.
- **The one EMEA-origin vendor in this KB's repo set.** `Eyevinn/channel-engine` (Apache-2.0) and
  `Eyevinn/hls-vodtolive` (MIT) come from **Eyevinn, Sweden** — notable because this KB's repos are
  otherwise overwhelmingly US- and China-origin. For a European public broadcaster, a FAST build on
  Swedish Apache-2.0 components alongside Norwegian-commissioned MIT Sofie is a procurement story
  about European technological autonomy, not just a licence position. Pair with the Commission's own
  finding that trustworthy, ethically-trained, financially sustainable AI remains **out of reach for
  many European creators and media organisations** — that is a stated funding gap, publicly argued.
- **Sell editorial accountability, not Article 50 compliance.** See trend 14: **ACT**, the commercial
  broadcasters' own trade body, is lobbying *against* blanket generative-AI labelling under Article 50
  (issue paper, June 2026), arguing EMFA and the AVMS Directive already impose editorial
  responsibility. The provenance build is unchanged; the justification must change, because the buyer
  may be opposing the clause you are quoting.
- **Informed gap:** the regional query returned **no concrete EMEA AI-adoption figures and no 2026
  market survey** for media specifically. Every EMEA number in this file is regulatory or
  trade-association material. Do not present an EMEA adoption percentage — this pass could not source one.


#### Accessibility compliance — added 2026-11-22 (pass 3)

- **The European Accessibility Act (Directive (EU) 2019/882) has applied since 2025-06-28**, and this
  is the strictest accessibility regime in the KB. Scope detail that matters for scoping: pre-recorded
  video published *before* 2025-06-28 is exempt; video published from that date inside an in-scope
  consumer service needs captions, **plus audio description where the picture carries information the
  sound does not**. Platforms must also *pass through* the audio description broadcasters provide.
  **Existing content and platforms have until June 2030** — so the backlog remediation market has a
  four-year runway and has barely been touched.
- **Enforcement is national, so the numbers are national.** Example found this pass: **Spain
  (CNMC / LGCA) — 75–90% subtitling and a minimum of 2 hours/day of audio description** on public and
  commercial channels. ⚠️ Vendor-sourced; verify against the LGCA text before quoting. A claimed
  general **90% caption threshold** and **€1M penalty ceiling** circulating in vendor material could
  **not** be confirmed against the Directive or any national law — excluded from this KB as data.
- **Two deadlines now stack in this region.** The EAA duty (above) and the EU AI Act Article 50
  marking duty already recorded in this section — pre-existing systems due **2026-12-02**. A client
  shipping AI-assisted subtitles in the EU is inside *both*: the caption is an accessibility artefact
  **and** AI-generated content. **No competitor is selling one pipeline that answers both.** That is
  this KB's single best-defined EMEA offer, and `compose/patterns.md` Pattern 11 now specifies it.
- **The tooling gap is EMEA-shaped, which is unusual and exploitable.** `ebu-tt-live-toolkit` — the
  reference implementation of **EBU-TT Live**, Europe's live-subtitle contribution spec — has been
  **abandoned for ~5 years (last push 2021-12-21)**, while the EAA made live subtitling a legal duty
  in June 2025. Europe has the strictest rule and the deadest reference tooling. Reviving a BSD-3
  EBU toolkit is a credible, cheap, high-visibility move in exactly the region where public
  broadcasters procure on open-source credibility (see trend 9).
- **Compliance, not efficiency, is the actual adoption driver here** — captioning and subtitling are
  regulated in most EMEA markets, which creates a dated obligation that internal-efficiency business
  cases never match. Trade reporting this pass is explicit that localization is what pulls AI into
  broadcast, and that **for smaller languages the economics of traditional dubbing simply do not
  work** — which is the honest case for AI in the EU's 24-official-language market.
- **Corroboration of this KB's trend 14:** the **EBU and the main commercial broadcaster
  associations** have asked the Commission to narrow the deepfake definition, clarify when on-screen
  disclosure is required, and keep marking standards proportionate. The lobbying this KB flagged is
  real and ongoing — so the labelling duty our flagship pattern assumes may be *softened*, not
  tightened. Design the marking layer to be configurable, not hardcoded.
- **One vendor interpretation worth knowing and not repeating as fact:** that caption/subtitle
  workflows which transcribe and translate *without generating a new voice track* sit outside the AI
  Act's disclosure scope. Plausible, legally untested, vendor-authored. Flag it to counsel; do not
  build a compliance promise on it.

- **The conformance layer this plane depends on was built with EU public money (new 2026-11-22).**
  `MediaArea/MediaConch`, the canonical open conformance checker for Matroska/FFV1/LPCM, carries a
  licensing condition naming the **PREFORMA Consortium** — the EU programme that funded it — and
  records that bundled libraries plus `libcurl`/`zlib` support are **disabled pending the
  consortium's consent**. The open conformance stack is EMEA-origin, and its constraints are
  EMEA-origin too. It has also **not been pushed since 2021-09-29**: an EMEA engagement that depends
  on it must budget to carry it.
- **R128 is the region's loudness target and the permissive implementation is European.**
  **EBU R128** sets integrated loudness at **−23 LUFS** with true peak at or below **−1 dBTP**;
  **EBU Tech 3341** specifies the meter. *Numbers in conflict across sources:* the tolerance is given
  as **±0.5 LU** for non-live in one source and **±1 LU for live** in two — cite the **direction and
  the primary document (EBU R128 v5.0)**, not a tolerance figure, in front of a client.
- **Sovereignty is the EMEA argument, and there is now research behind it.** An **imec-SMIT (VUB)
  report, May 2026** finds European media use AI heavily but **do not control the infrastructure,
  models or rights that generate the value** — value accrues to whoever controls those layers. That
  is the strongest available case for a client-owned stack assembled from permissive parts, which is
  exactly what this plane offers: `MediaInfoLib` (BSD-2-Clause), `fido` (Apache-2.0), `fcrepo`
  (Apache-2.0), `libebur128` (MIT).
- **Build-in-house is already the trend — sell capability, not product.** The **DPP European Media
  Trends 2026** report finds **a quarter of European media companies shifted strategy toward building
  more in-house or taking on greater integration responsibility**, enabled by AI-assisted coding.
  A studio that helps them build and own beats one that sells them a platform.
- **The labelling fight continues and it cuts against this KB's flagship pattern.** The commercial
  broadcasters' association **ACT**, in a **2026-06-16 issue paper**, argues for proportionate rules
  respecting editorial control and **objects to blanket measures including the AI Act's Article 50
  labelling duty**. Reinforces T14: Article 50 is in force, and the industry is lobbying against the
  assumption that Pattern 1 is built on.
- **Convening points for 2026:** the **EBU AI Forum 2026** (March 2026, with NVIDIA, Google and
  Perplexity on the lineup) and the DPP Broadcaster Summit. Bloomberg reports European media facing
  AI disruption alongside weak ad demand, with the Stoxx 600 media subindex's 2026 earnings growth
  put at **6.9%** against ~10% for the broader index — budgets are tight, which favours
  cost-reduction pitches like QC automation over growth pitches.

#### Content identification & AI licensing — added 2026-11-22 (pass 5)

- **EMEA is the only region where the rights reservation is a legal instrument, and it has a
  machine-readable vehicle with a name.** The EU DSM Directive's **Article 4** text-and-data-mining
  exception applies **unless rights are expressly reserved in a machine-readable form** — and the
  W3C community-group protocol built for exactly that is
  [`w3c-cg/tdm-reservation-protocol`](https://github.com/w3c-cg/tdm-reservation-protocol) (**TDMRep**,
  17★ / 14f, ratio **1.2** — this KB's signature of real infrastructure rather than attention).
  ⚠️ It carries the **W3C Software and Document Licence**, not an OSI-style permissive licence: read
  it before vendoring.
- **This is the region's strongest single opportunity in the plane, and the reason is structural.**
  Elsewhere a rights reservation is a commercial preference; in the EU it is **the thing that
  determines whether mining your catalogue was lawful**. A reservation that is not machine-readable
  is, in effect, not made. So an EMEA client needs the reservation **emitted, stored per asset, and
  evidenced over time** — a compliance artefact with an audit trail, which is a services shape and
  therefore Globant's. See `compose/patterns.md` **P15**.
- **A European government has already measured the defect this plane exists to fix.** The **UK
  government's music streaming metadata report (April 2026)** found **no central registry for ISRCs**
  and **ISRC-to-ISWC matching rates ranging from 0% to 85%** by source. A measured range, from a
  primary public source, is the rarest kind of asset in this KB — it converts a vague complaint into
  a scoped reconciliation problem. **DDEX** convened a Meta-backed summit on precisely this in
  Toronto on **19 November 2026**; no readout found yet, and it is a procurement trigger worth
  watching. See `intel/trends.md` §30.
- **The standards bodies in this plane are European, which matters for access and for cost.** CISAC
  (ISWC, CWR) is France-based; DDEX operates from Europe; ISAN-IA is Swiss. ⚠️ **DDEX's
  implementer-licence terms and fees could not be verified in this pass — `new.ddex.net` does not
  resolve from this session.** Treat them as *unresearched, not free*, and confirm at source before
  any proposal depends on them.
- **Digital sovereignty makes an open identification layer unusually sellable here.** The **DPP's
  European Media Trends 2026** report identifies AI as the dominant driver of transformation and
  finds European media increasingly wanting **digital sovereignty**; an imec-SMIT (VUB) mapping
  argues value accrues to whoever controls infrastructure, data, models, interfaces **and rights**,
  flagging the risk that smaller regional players fall behind; VSN argues many cloud MAM systems lean
  on AI engines running outside Europe. **Commercial read:** a content-derived, self-hosted identifier
  (ISCC, Apache-2.0, ISO 24138) is a *sovereignty* story in EMEA, not merely a technical one — the
  client owns the join key and it never leaves their estate.
- **The regulatory backdrop is live, not settled.** The European Parliament backed its position on the
  **AI Act Omnibus simplification proposal by 569 votes to 45**, and DIGITALEUROPE is arguing for
  technology-neutral horizontal rules over more sector-specific AVMSD rules. The **EBU held an AI
  Forum in Brussels on 25 March 2026** on governance for public-service media. Design for Article 50
  and Article 4 as they stand; do not assume the simplification lands.
- **MENA is a distinct, funded sub-market inside this region.** Arab media **AI spending is reported
  to reach $520 million in 2026**, with commentary noting AI regulation there cannot be separated from
  existing privacy, misinformation and platform-responsibility rules.
- **Informed gap:** this pass found **no EMEA-specific data on adoption of TDMRep or RSL by
  broadcasters or publishers** — the protocols are documented, the uptake is not measured anywhere
  found. Treat EMEA reservation-adoption rates as *unresearched*.

#### Added 2026-11-25 (pass 6) — the production plane: the UK now *subsidises* AI in VFX, and requires apportionment

- **The single most sellable regional fact found this pass.** The UK's additional tax relief for
  visual effects lets qualifying productions claim relief on up to **100% of eligible UK VFX spend**,
  and the proposal to **exclude generative AI from the uplift was dropped after industry
  consultation** — AI costs incurred in the VFX process are **eligible**. The UK is described in trade
  coverage as the largest VFX hub in Europe and the second largest in the world.
- **And here is the build.** Relief covers **VFX** costs but **not** other production costs such as
  filming in front of an LED volume, so a production using virtual production **must apportion its
  spend between the VFX and non-VFX portions**. Apportionment is a cost-attribution-and-evidence
  problem over exactly the artefacts this KB already types: timelines (`OpenTimelineIO`), asset
  identity (`OpenAssetIO`), render-job records (`OpenCue`) and camera/stage metadata
  (`SMPTE/ris-osvp-metadata-camdkit`). **A tax-credit evidence trail is a CFO-sponsored project with a
  statutory deadline, which is the best buying signal in this file.** See `compose/patterns.md`
  Pattern 18.
- ⚠️ **Confidence caveat, stated plainly:** `www.gov.uk` **does not resolve from this session**
  (egress policy), so every sentence above is carried at **trade-press and advisory-firm confidence
  only** — not verified against the primary policy paper. A 2024 consultation also indicated the
  existing film and high-end TV reliefs cease after **1 April 2027**; this pass could **not** confirm
  that date's current status. **Verify against gov.uk before it goes in a client deck.** This is a
  channel limitation, not a finding.
- **Digital sovereignty is the procurement frame.** EMEA trade reporting (DPP's European Media Trends
  2026) puts AI and digital sovereignty together as the dominant driver of European media technology
  strategy, and the EBU ran an AI Forum in Brussels in March 2026 on public-service-media governance.
  For this plane that favours **self-hostable, permissively licensed pipeline components over
  cloud-only vendor stacks** — which is precisely what the ASWF substrate is. Lead EMEA conversations
  with "runs in your own infrastructure, Apache-2.0", not with model capability.
- **Informed gap:** no EMEA-specific data was found on **adoption of OpenCue, Kitsu or AYON by
  European facilities**, and no measured uptake figures for OpenTrackIO among EMEA virtual-production
  stages. Unresearched, not absent.

### APAC

- **Four separate labeling regimes landed in 2026** — the most regulated region for synthetic media,
  and each rule is a build:
  - **South Korea — AI Basic Act**, in force 2026-01-22: advance notice of generative AI use and clear
    labeling of deepfake-style content. Regulator has signaled 2026 as a pilot period with limited
    enforcement. *Note: HunyuanVideo's license also excludes South Korea.*
  - **Taiwan — AI Basic Act**, in force **2026-01-14**. **New to this KB on 2026-11-22** — this is a
    *fifth* APAC regime the previous pass missed, and it matters disproportionately because Taiwan is
    a major production and post-production hub. Count the region as **five** labeling regimes, not four.
  - **Vietnam — AI law**, in force 2026-03-01: machine-readable labels on AI-generated audio, image and video.
  - **India — amended IT Rules**, effective 2026-02-20: obligations for platforms hosting synthetic content.
  - **China:** targeted rules on algorithmic recommendation and deepfakes rather than one framework.
- **Opportunity:** one provenance pipeline, four compliance profiles. A multi-country broadcaster or
  streamer needs per-jurisdiction labeling policy driven from a single C2PA manifest — a
  configuration product, and the regulatory diversity is the moat.
- Regional generative-AI-in-media is projected ~$1.97B (2024) → ~$20.7B (2034), ~26% CAGR; China is
  reported at ~46.5% of regional share. Players: Tencent, Sony, Kakao Entertainment, Zee, Star India,
  Samsung and Naver. Broad live-broadcast AI is expected only post-2028 with 6G.
- **Added 2026-11-22 — the infrastructure signal is more useful than the adoption forecasts.**
  **SMPTE ST 2110** (IP-based media transport) is reported as becoming established across APAC
  broadcasters. That is the precondition for everything in `compose/patterns.md` Pattern 7: once a
  facility is on ST 2110, device control is network-addressable, and an agent layer over
  `sofie-timeline-state-resolver` becomes deployable rather than theoretical. **Ask "are you on
  2110 yet?" early — it is the single best qualifying question for an APAC broadcast engagement.**
- **Localization is the segment to lead with here.** APAC is reported the fastest-growing media
  localization market at **~12.3% CAGR** (DataIntelo, second-hand — see the sizing table), which is
  consistent with the region's language fragmentation and with Pattern 2 being the most complete open
  stack in this KB.
- **IABM** (the broadcast-technology trade body) is moving toward shared agentic-AI tooling for its
  members, and BroadcastAsia 2026 programmed digital-radio deployment sessions. Trade-body-led
  tooling is a partnership channel, not a competitor.
- **Honest gap, carried forward:** no *measured* APAC broadcaster AI-adoption figure was found. The
  available claims ("second only to North America in adoption pace", "pilots moving to production in
  2026") are trade commentary and forecasts, not survey data. Regulation and ST 2110 readiness are
  the defensible APAC narrative; adoption percentages are not.

- **The monetization plane — new 2026-11-22.** APAC's ad-supported format is the **microdrama**, and
  it is now both industrialised and regulated. State media claim **over 95% of the 120,000+
  microdramas released in Q1 2026 were AI-generated**, against near-zero a year earlier, with Hangzhou
  firms reportedly producing 100-minute AI dramas for **under ¥20,000 (~$2,981)**. Regulation arrived
  with it: a rule effective **1 September** brings all microdramas with episodes under 20 minutes into
  a **unified national framework**, and enforcement is live — roughly **53,000 takedowns in Q1**, with
  one platform (Hongguo) handling 670 offending AI works. Incumbents have followed: **TVB's "You, and
  Only You"** was Hong Kong's first short drama with AI-generated characters, and **CCTV** produced an
  AI comic drama in January 2026.
- **What that means commercially.** At ~$3K per title, the production cost has collapsed and the
  binding constraints become **compliance throughput and monetization efficiency** — which are exactly
  Pattern 1 (provenance/labelling at generation) and Pattern 9 (ad breaks and yield), not generation
  capability. A platform shipping thousands of titles a quarter under a takedown regime needs an
  auditable pipeline more than it needs a better model. Note the per-title figures come from Chinese
  trade press and state media and vary by source; treat them as directional.
- **Informed gap, explicit:** **India returned almost nothing.** The only India signal this pass
  confirmed is that download growth is driven by emerging markets including India while paying users
  stay concentrated in mature markets. A low-authority page claiming India platform issues reshaped
  inventory toward Thailand and Taiwan is **unverified and deliberately not carried as a finding**.
  India's IT Rules, AI-labelling obligations and OTT regime are **unresearched** in this KB — the
  single largest named gap in this file, and the first thing to fix on the next APAC pass.


#### Accessibility compliance — added 2026-11-22 (pass 3)

- **Australia is the region's concrete, quantified regime, and the best entry point.** ACMA enforces
  it under **Part 9D of the Broadcasting Services Act**, with quality judged against the
  **Broadcasting Services (Television Captioning) Standard 2023**:
  - **Free-to-air** (commercial and national): caption **all main-channel programs 06:00–24:00**, and
    **all news and current affairs at any time**.
  - **Subscription TV:** targets are **legislated to rise 5 percentage points per year until they
    reach 100%**. As at **FY 2025/26 all movie channels are at a 100% target**; the sports-channel
    target example is **70%**, and **each individual sports channel must caption at least two-thirds
    of the target** every financial year.
  - **Commercial read:** a rising statutory percentage is the ideal AI-captioning business case,
    because the client's obligation grows every single year on a published schedule while their
    budget does not. This is the cleanest "volume must go up, cost must come down" argument in the KB.
  - ⚠️ Figures are from ACMA's own pages via secondary guides; verify the current financial year's
    table before quoting, since it changes annually by design.
- **South Korea — a one-year enforcement window that is open right now.** Korea's comprehensive
  **risk-based AI law** is in force, but the ministry has indicated **2026 is effectively a pilot
  period with limited enforcement, and a one-year grace period on penalties.** For AI-assisted media
  work this is the most permissive moment Korea will offer; it closes, and clients who start in the
  grace period are compliant-by-design when it does. Note this is the AI statute, **not** a
  captioning mandate — the search returned no Korean captioning quota.
- **The regional asymmetry is the finding, and it cuts the other way from EMEA.** An industry source
  (AVIA, *Regulating for Growth*) states that for **some Asian pay-TV and streaming markets there is
  no regulation or requirement for dubbing, subtitling or captioning at all.** ⚠️ That page is
  roughly 690 days old and may be outdated. Where it holds, accessibility in APAC is a
  **competitive-differentiation** sale (reach, searchability, sponsor-friendly inventory), **not a
  compliance sale** — the NA/EMEA pitch does not port, and using it will land wrong.
- **Informed gaps — searched and not found, which is not the same as absent:**
  - **Japan (MIC) subtitling/AD targets:** searched directly; no accessible primary or secondary
    source surfaced. Japan's public broadcaster obligations are known to exist; **this KB does not
    have the numbers.** Go to MIC's own publications before any Japanese engagement.
  - **India:** nothing relevant to captioning or accessibility regulation found this pass.
  - **No Australian or Japanese audio-description quota** was found, in contrast to the FCC's explicit
    50-hours-per-quarter rule. APAC AD duties should be treated as unresearched.

- **Japan has its own loudness instrument, and the number is not verified (new 2026-11-22).**
  **ARIB TR-B32**, *Operational Guidelines for Loudness of Digital Television Programs*, is the
  Japanese operational guideline. A vendor comparison table gives the target as **−24 LKFS / −1
  dBTP**, but that is a **secondary source this pass could not confirm against the ARIB document** —
  recorded as a lead, not a fact. The practical consequence is architectural and certain even when
  the figure is not: **the loudness target is a per-region configuration value, not a constant**, so
  any delivery-QC gate built for APAC must carry a per-territory profile (`libebur128` and
  `pyloudnorm` both take the target as a parameter).
- **Public broadcasters here are explicitly testing archive AI — which places this plane in APAC.**
  The **ABU (Asia-Pacific Broadcasting Union)** reports public broadcasters in **Australia and
  Singapore** exploring AI for newsroom work, **archiving and verification**. Archiving is named, not
  inferred: this is the clearest regional demand signal for the preservation plane found in any
  region this pass.
- **Regulation accelerated sharply in the last year, and it fragmented.** A **Latham & Watkins
  client alert (September 2026)** reports significant acceleration of AI regulation across APAC and
  groups it into **risk-based frameworks (South Korea, Vietnam)** and **targeted rules (China)**.
  South Korea has a comprehensive risk-based AI law. For a regional rollout this means the
  compliance artefact differs per market — the same per-territory profile problem as loudness, one
  layer up.
- **Australia's regulator has published on AI in media.** **ACMA** issued a report on AI in media in
  **April 2026**. This pass could not retrieve its findings; flagged as a primary source worth
  reading before an Australian engagement.
- **Adoption pace is second only to North America** (ASIAtechX 2026 trends), with the region split
  between early-stage adopters and digitally mature, saturated markets. Kantar's Media Reactions
  2026 puts Google ahead on consumer ad equity across APAC, followed by Netflix, YouTube, TikTok and
  Instagram.
- **Informed gap:** no authoritative regional survey of AI adoption **specifically among APAC
  broadcasters** was found, and **no APAC-origin open preservation or QC tooling** turned up in any
  query this pass. The tooling for this plane is entirely North American and European in origin.

#### Content identification & AI licensing — added 2026-11-22 (pass 5)

- **The region's regulation is the opposite of a single market, and that is the design constraint.** A
  **Latham & Watkins alert (September 2026)** groups APAC approaches into three categories: binding
  risk-based frameworks (**South Korea**, **Vietnam** given as examples), **targeted** AI regulation
  such as **China's**, and a third grouping. CX Network covers how **nine APAC countries** regulate
  AI, including **disclosure and labelling of generative content**. **Commercial read:** an
  identification/labelling build for APAC is **per-jurisdiction by construction** — the asset is a
  policy engine with pluggable per-market rules over one identification core, not a single compliance
  mode. Sell the engine; charge per market.
- **Labelling obligations make content identification load-bearing here.** Where a regulator requires
  generative content to be *disclosed*, the operator must be able to say reliably **which asset is
  which and how it was made** across a catalogue — identification plus provenance, joined. That is
  exactly the pairing this KB already has permissive parts for (`iscc-sdk` + C2PA tooling in
  `repos/foundations.md`), and it is a stronger pitch in APAC than in any region except EMEA.
- **Adoption is fast, which shortens the sales cycle and raises the integration risk.** Broadcasting
  trade coverage puts APAC **second only to North America in overall adoption pace**, and the Asia
  Tech x Singapore 2026 outlook expects AI embedded in the core of production, operations and viewer
  experience. Kantar's Media Reactions 2026 finds roughly **one in three APAC consumers using AI to
  research brands**.
- **The monetisation gap is the regional headline, and identification is upstream of it.** Variety
  reports the **Asia-Pacific screen economy racing toward $200 billion with a monetisation gap
  defining the decade**, while APAC **adspend grows just 5.2% year on year in 2026 — the slowest rate
  since the pandemic**. Scale without proportional monetisation is, concretely, an attribution
  problem: you cannot pay out or price inventory against content you cannot identify. That is the
  commercial bridge from this plane to the monetization plane already in this file.
- **Players to name:** Kantar ranks **Google** first for consumer Ad Equity across APAC, followed by
  **Netflix, YouTube, TikTok and Instagram**; **Tencent Video** and **iQIYI** are investing in
  generative AI; and the **Asia-Pacific Broadcasting Union (ABU)** notes public broadcasters in
  markets such as **Australia and Singapore** exploring AI for newsroom workflows, **archiving and
  verification** — the last two being identification work by another name, and a warmer entry point
  than commercial streamers.
- **The permissive-fingerprinting gap bites hardest here.** With no actively maintained permissive
  audio fingerprinter (`intel/trends.md` §31) and the maintained options under **AGPL-3.0**, an APAC
  client shipping an on-device or embedded matcher faces a genuine licence decision. `JorenSix/Olaf`
  is the technically right answer for embedded work **and it is AGPL** — surface that early, because
  it changes the architecture, not just the paperwork.
- **Informed gap:** this pass found **no APAC-specific sourced data on content-ID or
  rights-administration adoption**, and **no evidence of regional uptake of RSL or TDMRep**. China's
  labelling regime was identified only at the level of secondary legal commentary, not primary text.
  Treat all three as *unresearched, not absent*.

#### Added 2026-11-25 (pass 6) — the production plane: the region with the most to gain and the most to lose

- **India is the global production-services centre of this plane, and it is recovering from a real
  contraction.** FICCI-EY's 2026 report has animation and VFX growing about **1.6% in 2025** — read as
  early stabilisation after the segment **fell 9% to ₹103 billion in 2024** — with the VFX segment
  recalibrating toward **₹48 billion** and the combined animation/VFX/post segment projected to reach
  **₹138 billion by 2028**. A narrower IMARC cut puts Indian VFX at **$1.1B (2025) → $1.8B (2034),
  5.58% CAGR**. Netflix's Eyeline Studios facility in **Hyderabad** is the clearest signal of the
  shift from outsourcing hub toward high-end digital production.
- **The paradox, and it is the strategic point of this whole section.** The same FICCI-EY report links
  AI in **rotoscoping, clean-up and pipeline work** to time savings of **up to 40%** — and roto,
  paint and camera tracking are precisely the labour-intensive tasks the regional outsourcing model
  **bills for**. Industry commentary (ORF, VFX Voice) states the risk directly: AI attacks the
  billable task. **AI is simultaneously the efficiency story and the disintermediation threat to the
  same P&L.**
- **Therefore the APAC offer is up-stack, not cheaper.** A studio whose revenue is per-hour roto
  cannot be sold 40% fewer hours. It can be sold **pipeline ownership**: the agent bridges, the
  asset-resolution layer and the evidence trails in `compose/patterns.md` Patterns 17–19 — work that
  is per-seat and per-system rather than per-frame. This is the clearest case in the KB for leading
  with *margin architecture* rather than *tooling*.
- **Regulatory divergence remains the regional constant.** Latham & Watkins (September 2026) sorts
  APAC into binding risk-based frameworks (South Korea, Vietnam), targeted rules (China) and lighter
  regimes; Malaysia is weighing AI provisions inside a copyright overhaul. For this plane the
  consequence is the one already recorded in the LATAM/APAC sections of earlier passes: **the asset
  is a per-jurisdiction policy engine**, and in production that policy must attach to the *shot*, not
  the delivery master.
- **Informed gap:** this pass found **no APAC-specific data on open-source pipeline adoption** —
  nothing on OpenCue, Kitsu or AYON deployment in Indian, Chinese, Korean or Japanese facilities,
  despite the region holding the largest artist headcount in the world. That is the single most
  commercially interesting unmeasured number in this file, and it is unresearched, not absent.

### LATAM

- **Mexico now has the region's first sector-specific AI law for entertainment.** Amendments to the
  Federal Copyright Law and Federal Labour Law published **2026-05-14** and **effective 2026-05-15**
  create a framework for AI use of a performer's voice, image and performances. A separate criminal
  decree on AI-enabled crimes passed the Chamber of Representatives 2026-04-29 and is still pending.
  **Refined 2026-11-22 — who is protected is now explicit, and it widens the buyer list:** the
  reform expressly names **broadcasters, commercial voice-over artists and voice actors** as
  protected parties, and reaches **radio stations and television networks**, with significant
  restrictions on use of voice, image and performances.
  **This is the strongest sales filter in the region:** every Mexican production touching synthetic
  voice or likeness needs a consent and compensation trail, and it maps onto the same C2PA +
  consent-ledger build as the North American union work. One build, two markets. The fact that
  *broadcasters and dubbing houses* are named — not just studios — means the Mexican dubbing industry,
  which serves all of Spanish-speaking LATAM, is a directly addressable segment for Pattern 2 + 4
  together. Note Mexico still has **no general AI law**; several risk-tiered initiatives modelled on
  the EU are before Congress.
- **Peru's horizontal AI law** is operational (in force January 2026). **New detail 2026-11-22:** it
  amends **Article 296 of the Criminal Code** so that identity impersonation carried out with AI is an
  **aggravated** offence. That is a criminal-liability hook, not just an administrative one — which
  changes the risk conversation for any synthetic-voice or likeness work delivered into Peru.
- **Brazil:** electoral court Resolution 23.732/2024 bars synthetic audio/video altering the image or
  voice of a real, deceased or fictional person to favor or harm a candidacy — live constraint for
  political and news media. Brazil, Argentina, Chile, Colombia and Costa Rica are all advancing
  AI governance frameworks. **New 2026-11-22 and architecturally different from everything else in
  this file:** Brazil's AI bill carries a provision requiring **AI-based content *recommendation*
  systems to provide access to local, community and independent outlets.** Every other regime in this
  KB regulates *generation and labeling*; this one regulates the **recommender**. If it passes, the
  deliverable is a auditable diversity/provenance constraint inside a recommendation engine — a
  different engineering problem, and one no competitor is positioned for. Track it; it is a bill, not
  yet law.
- **LATAM leads the world in naming journalism in AI legislation** (Knight Center / LatAm Journalism
  Review) — unusually open ground for newsroom-specific provenance tooling.
- **Adoption is real but thinly evidenced.** AI-generated hosts are in regional programming in
  Colombia and Brazil (VidTech), with a claimed 40% production cost reduction — single trade source,
  unverified; do not quote it to a client as fact.
- **Newsroom AI policy is being written right now, and that is the entry point.** Legacy outlets are
  adopting internal rules rather than banning AI: **El Comercio** (Lima) implemented a ~10-page AI
  guide in early 2026, and a May 2026 report, *"Notes Toward Regulating Artificial Intelligence in the
  Media,"* was published by **SiPreBA** with the **Heinrich Böll Foundation**. Same dynamic as EMEA
  trend 9: a published policy with no tooling behind it is a procurement trigger.
- **The Caribbean is explicitly asking for this, and nobody is selling it.** At the **Caribbean
  Broadcasting Union's 2026 assembly** a Guyanese government minister urged regional broadcasters to
  *set* AI standards — covering synthetic-content disclosure and deepfake verification — rather than
  inherit whatever arrives from outside. A regional bloc of small broadcasters with a shared standards
  ambition and no in-house capability is an unusually clean fit for one shared Pattern 8 deployment.
  The IICOM Latin America & Caribbean Digital Communications and Media Forum (23–25 June 2026)
  programmed AI policy and Brazil's broadcasting evolution.
- **Honest gap, still open after two passes:** no credible LATAM-specific market-size figure was found.
  Earlier cycles carried "LATAM $2.1B → $6.5B by 2030" and "LATAM $65B, 10.7% YoY" — two different
  claims in consecutive cycles, neither traceable to a primary source. **Both remain unsourced.**
  Searched again 2026-11-22 against regional and trade sources; the only new quantity found is a
  Sumsub claim that deepfake incidents in LATAM and the Caribbean **rose 255% between 2023 and 2024**,
  which is a single vendor without published methodology (flagged in `intel/trends.md`). The Knight
  Center's own read is that the number of AI laws actually *enacted* in the region remains very low,
  so the effect on journalism is still unclear. **Regulation, not market sizing, remains the
  defensible LATAM narrative** — and that is now a two-pass finding rather than an impression.

- **The monetization plane — new 2026-11-22, and this is the region where it matters most.** Omdia
  puts **LATAM media revenues at ~$65B in 2026 with advertising and bundling as the drivers** —
  advertising is now the *primary* driver of regional growth, not subscription. **Brazil is the world's
  #3 FAST market by revenue (~$152M)**, behind only the US and UK, while **Netflix holds ~50% of LATAM
  streaming revenue**. A regional broadcaster cannot out-subscribe Netflix; it can out-target it on
  local inventory. **Opportunity:** Pattern 10 (first-party audience graph, all Apache-2.0, no AI
  exposure) as the entry engagement, then Pattern 9's FAST-and-ad-break stack on top. This is the only
  place in this file where the growth line, the licence position and an existing permissive component
  set (`Eyevinn/channel-engine`) all agree.
- **Brazil's advertising rules now name synthetic presenters explicitly.** **CONAR's 2026 influencer
  guidance** covers **avatars, virtual profiles and AI-generated content**, alongside child
  participation and transparency duties — so an AI-generated brand presenter is already inside a
  self-regulatory advertising code, separate from the electoral rules above. And platforms with **over
  5 million monthly active users in Brazil** had to file compliance plans documenting content
  moderation, **AI governance** and coordinated-behaviour detection by **16 August 2026**. Both are
  direct ad-side hooks that this file previously recorded only on the generation side.
- **Mexico's film-law draft would add a distribution obligation to the AI-labour one.** Beyond the
  14 May 2026 LFDA/LFT amendments already recorded above, a draft **Federal Film and Audiovisual Law**
  would replace the 1992 framework with a **10% screen quota, mandatory streaming visibility
  requirements, AI-related labour protections and progressive public funding**. If it passes, "local
  content must be findable" becomes a catalogue-and-recommender requirement — the same inspectable
  ranking layer Brazil's recommender provision would demand. Draft status: **before Congress, not law.**
- **Low-confidence, flagged not promoted:** a report that **Neymar signed with a Chinese microdrama
  platform for 16 AI-and-live-action titles** would be a significant APAC→LATAM content-format bridge,
  but it rests on a single Korean-language trade source. Not carried as a finding; worth re-checking
  next pass.


#### Accessibility compliance — added 2026-11-22 (pass 3)

- **México is the live trigger, and it is new.** The **Senado approved a new Ley Federal de Cine y el
  Audiovisual (April 2026)**, which orders the incorporation of **subtitulaje audiodescriptivo and
  subtitulaje adaptado in all formats in which cinematographic works are presented**, with coverage
  describing subtitles, audiodescripción and further access tools for both cinemas and streaming.
  ⚠️ Verify the final published text and its *reglamento* before scoping — the obligation's edges
  (which formats, what timetable, who enforces) are exactly what a reglamento settles, and it was not
  found this pass. **This is the single most actionable accessibility opportunity in LATAM right now**
  because the law is fresh, the implementing detail is still unsettled, and nobody has tooled for it.
- **Brasil — the framework is old and the cinema rules are concrete.** **Lei 13.146/2015 (Estatuto da
  Pessoa com Deficiência)** first brought audiovisual accessibility into Brazilian law, and **ANCINE**
  regulated the delivery formats — **legenda descritiva, audiodescrição and LIBRAS** — for cinema
  exhibition, with a published register of rooms. The Ministério da Cultura's own accessibility guide
  is the practical reference. Note the shape: Brazil mandates **three** distinct accessibility tracks,
  one of which is sign language.
- **Argentina — Ley 26.522 (Servicios de Comunicación Audiovisual), artículo 66** requires
  accessibility of programming content and names **subtitulado oculto, lengua de señas and
  audiodescripción** explicitly. The **Defensoría del Público** supports implementation with
  diagnostics and training, which makes it the natural first conversation for an Argentine engagement
  — and Globant's home market.
- **Uruguay** published official **recommendations for accessible audiovisual content in July 2026**
  (subtitles, transcription, lengua de señas, audiodescripción) via AGESIC/ICAU. **Paraguay** has a
  **bill pending** that would require closed captioning and audiodescripción on broadcast TV —
  approval unconfirmed. Both are small markets that signal regional direction.
- **The LATAM-specific insight, and it is genuinely different from NA/EMEA.** LATAM law mandates
  **sign language** (LIBRAS in Brazil, lengua de señas in Argentina and Uruguay) far more consistently
  than US or EU rules do — and **sign language is precisely where the open stack is weakest.** The
  most visible project, `sign/translate` (ex-`sign.mt`, now **Rylo Translate**, Nagish Inc.), is
  **source-available with a mandatory commercial licence for for-profit use**, and no open
  sign-language *generation* with real adoption was found at all. So the region with the broadest
  sign-language duty has **no permissive tooling to discharge it**. That is either the hardest
  blocker in LATAM accessibility work or its biggest build opportunity, and it should be said out
  loud in any proposal rather than discovered in delivery.
- **Informed gap:** **no LATAM regulation was found that governs the use of AI** to produce
  accessibility assets (automatic audiodescripción, machine captions as legal compliance). As
  everywhere else in this pass, regulators mandate the **artefact** and are silent on the **method**.
  In LATAM that silence is widest, which is permission to automate — and the reason an AI-assisted
  accessibility pipeline can be sold here before the rules harden.

- **The region is deploying archive AI faster than anyone is building archive-AI tooling (new
  2026-11-22).** This is the pass's clearest regional finding, and unusually it rests on **named
  production systems**, not vendor forecasts:
  - **Listín Diario** (Dominican Republic) built an AI document platform over its **136-year
    archive**, cutting research that took full days to minutes, with **25% of the archive searchable**.
  - **La Silla Vacía** (Colombia) runs **SillaBot**, a reader-facing archive query tool, plus a
    fact-checking prototype.
  - **ABC Color** (Paraguay) runs semantic archive search and automated news monitoring.
  - Industry voices at **BVS Media Connect 2026** framed the goal as turning a video library into a
    searchable, reusable asset rather than a passive archive.
- **The asymmetry is the opportunity.** Every preservation and QC platform catalogued in this KB
  (`fcrepo`, `archivematica`, `archivesspace`, `islandora`, `MediaInfo`, `MediaConch`) originates in
  the North American or European library and broadcast world. **No LATAM-origin open tooling for this
  plane was found in any query this pass.** Named deployments plus absent tooling is the best
  possible shape for a delivery business: the demand is proven and there is no incumbent product.
- **The funded entry points are identifiable and currently open.** The **IAPA/SIP**, with Google
  News Initiative support, launched an **AI Video Lab 2026 for more than 40 Latin American outlets**
  (its earlier AI Product Lab has closed), and runs a 2026 dialogue series on AI and media.
  **IFPIM** backs regional AI media initiatives and convenes CTRL+J on AI regulation and
  sustainability. **Aspen Digital** published *Mind the Gap: AI and the Future of News in Latin
  America* in January 2026. The **EBU–Alianza Informativa Latinoamericana** news-sharing agreement
  took effect **2026-05-01**.
- **What the outlets themselves say the problem is:** audience trust, business models and **control
  over their own content** — which is an argument for client-owned stacks on permissive licences, not
  for a hosted product. Note that `fcrepo` (Apache-2.0) is the one platform in the preservation tier
  a client can genuinely own.
- **Informed gap, stated rather than filled: no LATAM AI-media regulation was found this pass.**
  The regional search returned adoption and funding coverage and **no specific 2026 national AI rules
  for media** in any LATAM country. This is an *unsearched-to-conclusion* gap, not evidence of
  absence — national AI bills and AI-training copyright rules in Brazil and Mexico are the obvious
  next queries and were not run.
- **Informed gap on loudness:** no LATAM loudness instrument was verified this pass. Several
  countries in the region broadcast on ISDB-T/ISDB-Tb, whose Japanese lineage makes an ARIB-derived
  loudness practice **plausible** — explicitly a hypothesis to test against a primary document, not
  a finding, and not to be repeated to a client as fact.

#### Content identification & AI licensing — added 2026-11-22 (pass 5)

- **The regional regulatory direction is set, and it is the one that makes this plane matter.** LATAM
  is broadly **following the EU model** (IBA), which means the machine-readable-reservation logic of
  EU DSM Article 4 is the likely destination here too — with regional commentators warning that
  copying it risks **over-regulation** that hinders innovation. **Uruguay** became the first country
  in the region to sign the **Council of Europe Framework Convention on AI and Human Rights,
  Democracy and the Rule of Law** (2025). **Chile** is the regional leader, with an **AI bill before
  Congress** and **Latam-GPT**, the first open-source LLM trained on Latin American data. No LATAM
  country yet has a **fully mature, harmonised AI regime** across sectors.
- **Content labelling is already arriving through the platforms, ahead of the statutes.** **Google
  introduced AI transparency features across Search, YouTube and Discover in July 2026**, and
  regional communications commentary is already framing **content labelling** as the thing brands
  must prepare for. **Commercial read:** in LATAM the near-term forcing function is **platform
  policy, not law** — which is faster to arrive and easier to scope against, because the requirement
  is published and testable rather than litigated.
- **The newsroom is the warmest buyer in this region, and it is already writing the rules it will buy
  against.** Colombia's **FLIP** and Argentina's **ADEPA** have researched newsroom AI adoption while
  tracking regulation, and ADEPA has published a tool-and-workflow guide; Lima's **El Comercio**
  implemented a nearly 10-page AI guide in early 2026; **SiPreBA** (with the Heinrich Böll
  Foundation) published *Notes Toward Regulating Artificial Intelligence in the Media* in **May
  2026**; the **IAPA** describes newsroom AI as ongoing practice under strong human oversight, and
  **Aspen Digital** published a January 2026 report on AI and the future of news in Latin America.
  **IFPIM** funds regional work and convenes **CTRL+J** on AI regulation and media sustainability.
  Every one of those documents is a procurement trigger: an outlet that has written a policy has
  committed to being able to *evidence* compliance with it, and evidencing requires identification.
- **The identification build here should be content-derived and self-owned.** With registry
  memberships (ISRC national agencies, CISAC societies, EIDR) priced for Northern-hemisphere
  incumbents, the **ISCC** route (ISO 24138:2024, `iscc-core`/`iscc-sdk`, Apache-2.0) is
  disproportionately attractive in LATAM: no membership, no per-use fee, client owns the join key.
  State the limit honestly in the same breath — **26 stars means no installed base**, so it is the
  *internal* key, and registry integration is still required wherever assets cross borders.
- **Where this plane meets the region's actual growth.** This file already records advertising as
  LATAM's growth engine and archive AI as a region where deployment outpaces tooling (§24). Both run
  through identification: ad attribution and archive dedupe are the same matching problem.
  `beets` (MIT) plus a vendored permissive fingerprinter is a genuinely low-cost entry for a
  broadcaster's existing library — see `compose/patterns.md` **P16**.
- **Informed gap, stated rather than implied:** this pass found **no LATAM-specific coverage of music
  rights administration, collecting-society AI policy, or adoption of RSL/TDMRep**, and **no
  country-level bill text** for AI-in-media beyond the Chilean bill's existence. The regional search
  returned press-freedom and newsroom-governance material, which is genuinely where the activity is —
  but it means **LATAM rights-administration opportunity is unresearched, not absent.** The one hard
  regional data point this pass could not obtain is whether any LATAM collecting society has published
  an AI policy; treat that as an open question to raise with the client rather than an answer.

#### Added 2026-11-25 (pass 6) — the production plane: real studios, and the thinnest data in this file

- ⚠️ **Read the confidence warning before the numbers.** The only regional sizing this pass could
  find for LATAM animation/VFX comes from a **vendor marketing directory** (Vitrina), not from a
  government or trade body: ~**$1.5B** screen/VFX production market in 2026 and ~**20,000** VFX and
  post-production professionals regionally; separately an animation-market figure of **$27.9B (2024)
  → $66.1B (2033), 9.3% CAGR**. **Those two figures cannot both describe the same thing** — a $27.9B
  "animation market" alongside a $1.5B production market is a scope mismatch of ~19×, which is itself
  the useful signal: **treat all LATAM production sizing in this file as unverified vendor material
  and say so to the client.**
- **The studios, by contrast, are concrete and checkable.** Brazil is the primary hub — **O2 Filmes**
  (São Paulo), **Copa Studio** (animation), **Raccoon VFX** (Porto Alegre, feature VFX and game
  cinematics). Argentina runs a long-standing service industry out of Buenos Aires (**Hook Up
  Animation**, and **Bellolandia** with the anime-style series *Electro Andes*). **Colombia, Chile and
  Peru** are the emerging tier, with regional recognition through Annecy's La Liga focus and Ventana
  Sur's animation pitching sessions.
- **The regional trade-body source worth reading is Premios Quirino's *Laboratorio de Futuros*
  (April 2026)** — the one non-vendor regional document this pass surfaced on the future of LATAM
  animation. Use it in preference to directory sites.
- **Why this plane fits LATAM's actual position.** The region's strength is **service production for
  foreign clients**, which makes it structurally identical to India's exposure (see APAC) — and it has
  far less domestic scale to fall back on. The defensible offer is the same and more urgent: own the
  **pipeline**, not the frame count. The ASWF substrate costs nothing in licence fees, runs on
  self-hosted infrastructure, and the agent bridges that matter are **1–2 star repos** — a regional
  studio can realistically become the maintainer of one, which is a positioning no amount of seat
  licensing buys.
- **Informed gap, and it is a large one:** this pass found **no official government or trade-body data
  on Argentine or Colombian VFX output**, and the frequently cited **Colombian 40% cash rebate** was
  found only in vendor material and **could not be verified** against a film-commission source. No
  LATAM-specific data on open-source pipeline adoption was found either. Unresearched, not absent —
  and for LATAM this plane is the *least* measured of the six.

## Globant positioning

1. **Compete on media standards, not on model access.** The SIs named as EMEA leaders have generic AI
   practices. Depth in OpenTimelineIO, VMAF, IMF/Photon and C2PA is a differentiator none of them
   lead with, and it is all permissively licensed.
2. **Sell provenance as compliance — and sell *verification*, not a seal.** Five APAC regimes
   (Korea, **Taiwan**, Vietnam, India, China), EU Article 50, Mexico's performer law and Canada's
   national strategy all converge on one artifact: a signed, machine-readable claim about how an asset
   was made. Build it once on `c2pa-rs` + VideoSeal/AudioSeal. **Updated 2026-11-22:** because the
   watermark-removal ecosystem is 10.4× the size of the embedding one (`intel/trends.md` trend 8), the
   defensible product is dual marking **plus an ingest-side verification service**, described honestly
   as a probabilistic chain of custody. Competitors who promise tamper-proof watermarking will be
   caught out by the client's own engineer.
3. **Lead with internal workflows** — localization, archive, post — where the industry is actually
   spending, and where `VideoLingo` + `whisperX` + **`pyannote-audio`** + `OpenCreator` already give an
   80% pipeline. Localization is also the one segment with a credible sizing figure ($5.6B→$12.8B by
   2033, APAC fastest).
4. **Be the one who knows the license traps**: HunyuanVideo excludes the EU/UK/Korea, OpenMontage is
   AGPL, Directus is not OSI-approved, Strapi is only half-MIT, `mlt` is LGPL (so linkable) while
   every other NLE engine is GPL (so not). That knowledge de-risks a bid.
5. **New on 2026-11-22 — go up a layer in news and live: own the automation platform.** **Sofie**
   (MIT, NRK-commissioned, daily production at NRK/BBC/TV 2 Norway) means a news or live engagement no
   longer has to be "agents bolted onto a vendor's API." Globant can extend an MIT broadcast
   automation platform, against the expensive incumbent (Vizrt Mosart), with no copyleft obligation —
   and the specific unbuilt piece is an **MCP bridge to `sofie-timeline-state-resolver`**
   (`compose/patterns.md` Pattern 7). This is the highest-differentiation, lowest-competition position
   in this KB, because the stack is invisible to anyone doing discovery through GitHub search or
   AI listicles.
6. **Two dated deadlines to lead conversations with this quarter.** EMEA: **2026-12-02**, when
   pre-August AI systems must meet the Article 50(2) marking-and-detection duty. North America:
   **2027-01-01**, when the California AI Transparency Act's obligations on AI *hosting platforms*
   begin. Both are remediated by the same Pattern 8 build.

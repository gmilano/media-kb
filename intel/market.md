---
industry: media
region: Global
updated: 2026-11-26
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
| **Production / post-production (pass 6): no AI-specific sizing found** | — | Added 2026-11-25 (pass 6). Searched; **no vendor sizing for "AI in VFX/animation production" surfaced at all.** The usable regional figures are segment figures from trade bodies, not AI figures: India animation+VFX **₹48bn** VFX / **₹138bn** combined by 2028 (FICCI-EY 2026), Indian VFX **$1.1B (2025) → $1.8B (2034)** at 5.58% CAGR (IMARC), LATAM screen/VFX **~$1.5B (2026)** (vendor directory, unverified — see LATAM). **The plane with the healthiest open substrate in this KB is the one with no market sizing**, which is a finding about analyst coverage, not about the market. |
| **Audience measurement (pass 7): US national TV currency = $1.5B–$2B / year** | **CIMM, January 2026 — a primary document, read directly** | Added 2026-11-25. **The only primary-sourced figure in this table.** From *"Funding the Fiesta: The Economics of National TV Currency in the US Market"*: TAM **$1.5–2B/yr**, of which Nielsen takes **85–90%** (**$1.2–1.8B**); an entry-level currency-grade service costs **~$110M/yr to operate**, a competitive one needs **~$250M/yr** of revenue; Nielsen's panel is **42,000+ homes** at an estimated **$150–250M/yr** while every challenger panel targets **5,000**. The US is **2–3× the most expensive** measurement market on earth and holds **~two thirds of global video currency spend**. **Quote these numbers in preference to anything else in this table** — and note what they explain: there is no open-source audience currency because a currency is an operating cost, not a codebase. |
| **Content moderation solutions (pass 9): 2026 base ~$10.8B–$13.3B, CAGR 8.1%–17.5%** | Six market-research vendors | Added 2026-11-26. A **factor-of-two spread on the base year and a factor-of-two spread on the growth rate** — the second-widest disagreement in this table after captioning. Low cluster: Global Info Research $11.8B (2025) → $20.3B (2032) at 8.1%; GII ~$10.78B (2026) → $18.22B (2032) at 9.14%. Middle: The Business Research Company $13.31B (2025) → $26.14B (2030) at 14.5%; Expert Market Research 13.10% CAGR (2026–2035) → ~$33.05B. High: Market Research Future ~$9.99B (2024) base at 17.49%. Narrower regional cut: **AI content moderation for OTT in North America ~$600M (2026)** (Mordor). **The scope artefact to ask about is services**: the high cluster counts outsourced human moderation labour, the low cluster counts software licences only. Since the open stack in `repos/foundations.md` replaces *software*, not *labour*, the **low cluster is the addressable figure** for an open-source engagement. |

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

#### The audience & measurement plane — added 2026-11-25 (pass 7). The only plane in this KB with a verified price on the barrier

- **This is the best-sourced economic finding in these eight files, and it comes from a primary
  document.** CIMM's *"Funding the Fiesta: The Economics of National TV Currency in the US Market"*
  (January 2026) was downloaded and read directly — not summarised from trade press. It answers, with
  numbers, why no open-source audience currency exists:
  - **Total addressable market: $1.5–2 billion/year** for national cross-platform video currency.
  - **Nielsen holds an estimated 85–90% of national video currency spending** → revenues of **$1.2–1.8
    billion**. All competitors share the remaining **10–20%**.
  - **An entry-level currency-grade service costs ~$110M/year to maintain**, needing **$135–140M** of
    annual revenue at a 20% margin. A competitive one needs **~$250M/year**.
  - **Nielsen's panel is "more than 42,000 homes"**, with ongoing panel costs the authors conservatively
    estimate at **$150–250M/year** (Nielsen's pre-2024 SEC filings referenced panel costs of "hundreds
    of millions of dollars"). Adding a proprietary panel of that scale adds **$150–250M** to any
    challenger's cost base.
  - **Competing panels (TVision, HyphaMetrics, Kantar) all target 5,000 households** — Nielsen's is
    **8–10× larger**. CIMM explicitly does not expect any provider to attempt to match it.
  - **The US is the most expensive measurement market in the world**, with data users spending **2–3×**
    comparable countries, and **roughly two thirds of all global video currency spend is in the US.**
- **What that means for open source, stated precisely.** The barrier is not a licence, not a patent and
  not neglect — it is a **fixed operating cost of observation plus an accreditation regime** (MRC
  accreditation and JIC certification are named by CIMM as entry barriers). This is the sixth
  confirmation of this KB's structural law and the first with a dollar figure: **where compliance
  requires an asset that must be continuously operated rather than written, open source does not
  appear.** No amount of permissive licensing produces a $110M/year panel.
- **The certification picture, and the inconsistency worth knowing.** The Joint Industry Committee has
  certified **both Comscore and VideoAmp** as national TV currencies, yet most buyers and sellers still
  transact on Nielsen numbers. Separately, trade press reports that **Nielsen and VideoAmp both withdrew
  from the MRC accreditation process** (date not precisely established — treat as reported). So the
  market has more certified currencies than it uses, and the dominant two have stepped back from the
  older accreditation body. **A client's "which currency?" question is political, not technical.**
- **Where the open stack actually wins, and this is the engagement.** Because the currency is closed,
  advertiser demand migrated to what *can* be done without a panel — and eMarketer's H1 2026 read is
  that **outcome-based measurement is overtaking the currency debate** in TV and CTV. That is exactly
  the layer where open source is strong: **`google/meridian` (Apache-2.0, 1,616★), `Robyn` (MIT,
  1,540★) and `pymc-marketing` (Apache-2.0, 1,314★), all pushed within 15 days of this measurement.**
  Pitch *incrementality and media-mix modelling on the client's own data*, not a currency substitute.
  See Pattern 20.
- **The agent bridge is adoptable here and nowhere else.** `googleanalytics/google-analytics-mcp`
  (Apache-2.0, **3,866★**, 802 forks, pushed 2026-11-24) is a real dependency. Nielsen has announced a
  natural-language AI-assisted interface as part of cross-platform products slated for **early 2027**,
  and plans **2027 content measurement built on publisher streaming data** — so the incumbent's agent
  surface is a year out and will be proprietary. **The window for an open, client-owned agentic
  analytics layer is now and it is about twelve months wide.**
- **Informed gap:** the **MRC withdrawal dates could not be pinned to a primary source**, and no
  figure was found for how many NA broadcasters self-host a recommender versus licensing one.
  Unresearched, not absent.


#### The live & delivery plane — added 2026-11-26 (pass 8). The region with a **dated engineering deadline** nobody has tooling for

**The regulatory event.** The US over-the-air transition to ATSC 3.0 ("NextGen TV") is the only
delivery-side deadline in this KB that forces a re-engineering of a live chain:

- Under current rules, a broadcaster running ATSC 3.0 must **simulcast "substantially similar"
  content in ATSC 1.0 through at least 2027-07-17**. The FCC's proposal would **end** that
  simulcast obligation.
- The proposal **does not** set an ATSC 1.0 cutoff date and **does not** mandate ATSC 3.0 tuners in
  new televisions. The FCC instead sought comment on whether a tuner requirement should apply to all
  new receivers, on its cost, and on an informational **labelling** rule for sets that cannot
  receive the new signals.
- Deployment per a draft order: full-power ATSC 3.0 live in **more than 80 markets, covering over
  70% of the population**. NAB's stated aim is to be rid of ATSC 1.0 **by 2028 in the 55 largest
  markets and everywhere by 2030**.
- Advocacy is live: the National Religious Broadcasters urged the FCC in **February 2026** to adopt a
  tuner requirement and reaffirm must-carry; cable operators object to the equipment cost.

⚠️ **Status caveat, stated rather than smoothed:** these are a **proposal and a draft order**. This
pass found **no source confirming a final adopted FCC order**. Check the FCC docket before quoting a
rule as settled in a client conversation.

**Why this is an opportunity rather than a news item.** The transition is a dual-chain problem —
two encodes, two packagings, two carriage paths, a conformance duty on both, and a labelling regime
under discussion — and **there is no maintained open-source ATSC 3.0 implementation to build on.**
`libatsc3/libatsc3` and `Sony/libatsc3` both fail `ls-remote`; the only survivors are forks at 13★
(2019) and 12★ (2023), all MIT and all stale. A regulated, dated, capital-intensive transition with
a verified tooling vacuum underneath it is the cleanest engagement shape in this plane.

**Site-blocking arrives in the US.** Two site-blocking bills were introduced in **September**, which
would let courts order blocking of foreign pirate sites **including live sports streams**. If either
passes, the EMEA operational playbook (below) becomes directly sellable here — and North American
broadcasters have no 30-minute-response muscle because they have never needed it.

**Adoption and buyers.** Grant Thornton's 2026 survey reports **87% of M&E boards have approved
major AI investments** — budget is authorised, which is why the board-level barrier is gone and the
delivery barrier is what remains. Forrester describes North American M&E as enthusiastic about
generative AI but **still stuck in early experimentation**. Netflix and Disney are the named
large-scale deployers. Market-share estimates put North America at roughly **34–41%** of the global
AI-in-media market depending on the vendor — treat as a range, not a number.

**The DRM gate is a North American procurement reality.** All three premium DRM roots of trust are
held by US companies (Google, Microsoft, Apple) and issued **by contract**: a Widevine Master
Licence Agreement and security questionnaire, a Microsoft agreement for any PlayReady service
provider, Apple's developer agreement for FairPlay. There is no open-source path to a Widevine L1 /
HDCP premium service. Put the agreement in week one of the plan, not in the build.

**MoQ is being built here.** `facebookexperimental/moxygen` (Apache-2.0, Meta) and `Quicr/libquicr`
(BSD-2-Clause, Cisco) are both North American, and the MoQ Alliance includes Akamai, AWS, Cisco,
Cloudflare and Fastly. Influence over the standard is still available before the **2026-12-31** IESG
publication-request milestone.

#### Trust & safety and minor protection — added 2026-11-26 (pass 9)

**The regulatory shape here is the inverse of EMEA's: the hardest obligation is federal and old, and
the newest obligations are state-level and about AI labelling.**

- **The statutory duty with no usable tooling.** Under **18 U.S.C. §2258A**, electronic service
  providers must report apparent child sexual exploitation to the **NCMEC CyberTipline**. The only
  open client is [ello/ncmec_reporting](https://github.com/ello/ncmec_reporting) — **7★, no licence
  file, last pushed 2022-03-29**. A US UGC or streaming client therefore has a mandatory reporting
  pipeline with no open code behind it, and the hash lists it would match against (NCMEC, PhotoDNA)
  are distributed by membership and vetting, not by licence. This is the clearest
  "obligation without an implementation" in any region of this file.
- **Federal AI policy went the other way.** The **White House National Policy Framework for AI**
  (March 2026, non-binding) names government pressure on platforms to suppress lawful content as a
  primary risk and leans toward restraint rather than new platform liability. There is still **no
  comprehensive federal AI or platform statute**, so enforcement remains sectoral — FTC, FCC and
  state law.
- **The state layer is where the dates are.** The **California AI Transparency Act** phases in from
  **August 2026**, reaching *hosting platforms* and *capture devices* in **2027–2028**, and applies
  to generative providers above **1,000,000 monthly California users**. Deloitte expects generative
  video to push US regulators toward age verification and AI-content labelling, naming **New York,
  Tennessee and Utah** as early movers.
- **Who the buyers are.** North America is the largest regional market for AI content moderation
  (~**$600M in 2026** for the OTT slice alone, per Mordor — vendor figure, treat as indicative), and
  the open substrate was largely *donated by North American operators*: Discord (Osprey), Google
  Jigsaw (Altitude, conversationai-moderator), Meta (ThreatExchange, content-review-filters),
  Bluesky (Ozone), Roblox (Sentinel). **The engagement is integration, not invention**, and the
  credibility move is knowing that Llama Guard and RoGuard cannot be deployed commercially.
- ⚠️ **Unverified claims encountered and deliberately not carried as fact**: a market report
  referenced a "Meta–OpenAI real-time filtering partnership" and a "Jigsaw expansion across North
  America". Neither could be confirmed against a primary source. Recorded here so a later pass does
  not re-import them from the same vendor page as established.



#### Theatrical & digital cinema — added 2026-11-26 (pass 10)

**The channel.** Global box office was **$34.6bn in 2025, up 7%** (Futuresource), with 2026
forecast at roughly **$34.55bn** — Gower Street revised down from an initial $35bn, mostly on a weak
Chinese Q1. Every figure in every source remains **below the 2017–2019 average**; the European
Audiovisual Observatory puts 2025 at about €29.6bn and ~30% below the pre-pandemic average. Treat
as a range, not a number.

**The regulatory artifact that matters here, and it is nine years old.** The DOJ's ADA Title III
rule (published **2016-12-02**) requires every US movie theatre with an auditorium showing digital
movies to **acquire and maintain** closed-captioning and audio-description equipment, delivered to
an individual patron's seat, on a scaling table (a single-auditorium site: 4 captioning devices and
1 audio-description device; 16+ auditoriums: 12 and 8 or more). The rule's limiting clause is the
commercial opening: it **does not require theatres to add captioning or audio description to films
not already produced or distributed with those features.** So the equipment duty sits on the
exhibitor and the content duty sits with the distributor, and **nothing joins them.** Open tooling
for cinema accessibility: **one repository, zero stars.**

**The standards position.** NATO required domestic exhibitors to be SMPTE-DCP-ready by
**2019-04-09**, and ISDCF's registry now states that most DCPs are distributed in SMPTE format.
SMPTE's own `DPROVE2` verifier has **dropped Interop support** — and is a member tool, not open
source. North America is the region furthest through the transition, which makes it the region where
**Interop fallbacks can be removed from a pipeline** rather than maintained.

**Opportunities — North America**

1. **Accessibility conformance gate (highest urgency, lowest build).** Verify that mandated caption
   and audio-description tracks are present, correctly labelled and actually render, *before* the
   key ships. The duty is nine years old, the enforcement surface is ADA litigation, and the open
   estate is one 0-star repo. Pattern 29.
2. **Ingest triage for circuits and distributors.** `ClairMeta` (BSD-3, so embeddable in a client's
   own stack) emits structured validation per DCP; an agent clusters hundreds of weekly results into
   supplier-systematic versus one-off failures. Pattern 28.
3. **KDM lifecycle management.** The entire open estate is **3 stars across three repos** against an
   artifact without which no screening happens. Pattern 30.
4. **The identifier landing zone.** EIDR is a North American institution with no open client (pass
   5); theatrical is where EIDR and ISAN identifiers are actually *used*. A permissive bridge from
   DCP metadata to EIDR is small and nobody has built it.

**Informed gap — North America.** No 2026 US screen count was verifiable from this session: the
Omdia Cinema Sites & Screens database is paywalled. **Not estimated.** Also unverified: any
2025–2026 DOJ enforcement action or amendment to the 2016 rule — searched, nothing found, so the
rule is treated as in force and unamended.

#### Pass 11 (2026-11-26) — the description & semantic-interchange plane

**The region owns the vocabulary that AI answer engines read, and it is Apache-2.0.**
`schemaorg/schemaorg` (6320★, Apache-2.0, pushed 2026-11-25) is governed by a W3C community group
founded by Google, Microsoft, Yahoo and Yandex. `NewsArticle`, `VideoObject` and `ClaimReview` are the
structured-data types that decide whether a North American publisher is legible to AI search. That
makes schema.org the one asset in this plane with no licence friction and a direct revenue story.

**But the causal claim is not evidenced, and selling it as if it were is a liability.** Search Engine
Land states plainly that there are **no peer-reviewed studies** on schema markup's effect on AI
search visibility or on LLM citation behaviour, and that the link rests on assumptions that cannot be
verified for most platforms. Vendor sources assert the opposite (one claims schema was "the only
factor" determining AI Overview appearance, without naming the study). Contently reports **25.11% of
Google searches triggered an AI Overview in Q1 2026**, and a DEV post citing the 5W Citation Source
Index (May 2026) says news and media sites dominate AI citation rankings — both are real signals of
*stakes*, neither is evidence of *mechanism*.

**The sellable framing is therefore hygiene, not ranking:** accurate, current `NewsArticle` markup,
consistent publisher naming, a 48-hour news sitemap, and the `isAccessibleForFree` flag. Stale or
wrong structured data is reported as *more* harmful than missing markup, which makes correctness —
not coverage — the deliverable. One single-source claim to verify before repeating: that Google
removed FAQ rich results from Search on 2026-05-07.

**Institutional gap.** North America has no equivalent of INA or the National Library of Finland
shipping maintained open cataloguing tools for media. The region sets the *vocabulary* and buys the
*tooling*; EMEA builds the tooling. For a North American engagement, expect to supply the cataloguing
layer from European open source and the schema layer from schema.org itself.

#### Pass 12 (2026-11-26) — the sound & immersive-audio plane: a standardised deadline with no open encoder

**The deadline is real and dated.** The **ATSC 3.0 suite was approved 2026-04-14** and standardises
**MPEG-H** as the next-generation audio system for North American broadcast (ATSC A/342 Part 3).
Deliverables already assume it: NBC carried the **2026 Winter Olympics and the Super Bowl** in Dolby
Atmos on Peacock, and the **FIFA World Cup 2026** is the next milestone across broadcast and OTT.
SMPTE's March 2026 read is that immersive sound is now "table stakes".

**The supply gap, measured rather than asserted.** There is **no open MPEG-H encoder** — the
implementations are Fraunhofer's. The open stack reaches ADM/BW64 and stops: `ebu/ebu_adm_renderer`
(BSD-3-Clause-Clear, **105★**), `ebu/bear` (Apache-2.0, 32★), `ebu/libadm` (Apache-2.0, 51★). **A
continental broadcast mandate is served, on the open side, by repositories in the double digits.**

**Voice regulation is state-level and fragmented.** Tennessee's **ELVIS Act** (in force 2024-07-01)
was the first statute to name voice in AI cloning, extending the right of publicity to AI voice
replicas. California's **AB 2602** makes digital-replica contract clauses unenforceable without
specific, informed consent, with **AB 1836** covering deceased performers. The federal **NO FAKES
Act** was reported advanced by the Senate Judiciary Committee on 2026-06-18 but **is not law** — do
not plan against it. There is still no comprehensive federal AI voice statute, so exposure is
per-state and contractual.

**Opportunity for Globant in this region.**
1. **ADM/BW64 conformance and delivery tooling** against the 105-star reference implementation —
   the gap between "we must ship immersive" and "the open stack is a reference renderer" is
   billable integration work, and it is permissive (Apache/BSD) end to end.
2. **Rights-clean voice pipelines**: the technical work is small, the consent/provenance
   recordkeeping is what a studio cannot buy off the shelf, and it is what AB 2602 makes
   contractually necessary.
3. **Avoid** promising DAW plugins without pricing `JUCE` (AGPL-3.0 or commercial) first.

#### Pass 13 (2026-11-26) — the subscription layer: enforcement without a rule

**The regulatory position is the inverse of the UK's, and that is the whole opportunity.** The FTC's
"click-to-cancel" amendments to the Negative Option Rule were **vacated in full by the Eighth Circuit
on 2025-07-08** (*Custom Communications, Inc. v. FTC*) on **procedural** grounds — the Commission
skipped a required preliminary regulatory analysis — so they never took effect. Reporting indicates
the FTC then removed the 2024 amendments from the CFR on **2026-02-12** and issued an **Advance
Notice of Proposed Rulemaking in March 2026**, asking whether to re-adopt provisions of the vacated
rule. **No replacement rule has been proposed**; commentary suggests a final rule could run into 2027
or later. *(Sources are law-firm commentary; the CFR removal date in particular should be checked
against the Federal Register before it is quoted to a client.)*

Meanwhile **enforcement has not paused**: the FTC continues to bring cases under **ROSCA** and
**Section 5** over undisclosed material terms, charges without express informed consent, and
deliberately difficult cancellation.

**Why this is commercially sharper than a prescriptive rule, not weaker.** A rule tells a client what
to build. Enforcement without a rule tells them only that they will be judged later, on facts. What
survives that is **evidence**: a recorded, replayable cancellation journey showing what was disclosed,
when consent was captured, and how many steps cancellation took. That is an engineering artefact, and
nothing open source produces it (see Pattern 13.1).

**Demand context.** Deloitte reports that as of March 2026, **68% of SVOD-subscribing households have
at least one ad-supported service, up from 54% a year earlier** — plan-switching between ad and paid
tiers is now the normal subscriber motion, and each switch is a billing, entitlement *and* disclosure
event. Grant Thornton's survey of 950 business leaders reports **87% of M&E boards have approved
major AI investments**, while Forrester's North America spotlight finds firms "bullish on genAI but
bogged down in early experimentation" — budget exists, deployment does not.

**Opportunity for Globant in this region.**
1. **The evidentiary cancellation journey** — build the artefact that survives a ROSCA enquiry.
   Highest-value because the duty is live and the specification is absent.
2. **Dunning and involuntary churn** on Kill Bill (Apache-2.0): failed-payment recovery is the most
   automatable task in the plane, and `dunning agent` returns 57 repos with nothing above 200★.
3. **Ad-tier / paid-tier switching** as a first-class entitlement and disclosure flow, not a billing
   edge case — this is where the 68% figure turns into engineering work.

#### Localization substrate — added 2026-11-26 (pass 14)

**The regional distinction that decides the pitch:** Grant Thornton's *2026 Media & Entertainment AI
Impact Survey* reports that M&E is **less exposed to regulatory uncertainty than sectors such as
banking**, because it operates under lighter statutory regulation. Forrester's AWS-sponsored *State
of GenAI in Media and Entertainment — North America* spotlight describes North American M&E firms as
bullish on generative AI but **still largely in early experimentation**.

Read together: in North America the localization buy is **not** compliance-driven — it is margin- and
capability-driven. That is the opposite of EMEA (sovereignty and the AI Act) and of LATAM
(a dated statutory calendar). Do not reuse the EMEA deck here.

What *is* regulated in NA is **the voice, not the translation**. Chambers' *Media & Entertainment
2026* guide (USA–New York) records new protections against unauthorised AI voice clones, alongside
the 2026 WGA, SAG-AFTRA and DGA agreements already documented in this section. For a dubbing
programme that means the consent artefact attaches to the performer, while the text pipeline above it
is commercially unconstrained.

**Openings, in order of how ready the buyer is:**

1. **Translation-memory recovery and audit.** The highest-value, least-contested work in this plane.
   NA enterprises buy localization on SLAs and hold a decade of TMX, and there is no maintained open
   tool to read, merge or audit it (`bitextor` GPL-3.0 dormant since 2024-11-11; nothing above 17★
   alive). Deliverable: the client's own memory, deduped, quality-scored and portable — which is also
   the asset that breaks vendor lock-in. See Pattern 34.
2. **The MQM gate as a contractual instrument.** Because NA localization is bought on contracts, the
   `2★` state of the open MQM scorecard is a *sellable* gap here specifically. COMET (Apache-2.0) as
   an automatic pre-filter deciding what reaches human MQM review is buildable now. See Pattern 36.
3. **Union-safe synthetic voice**, wired to the existing consent-artefact pattern (12.1) rather than
   rebuilt — the guild agreements make provenance the deliverable, not the audio.

⚠️ **Unverified, do not quote:** an Intel Market Research page claims "82% of media organisations use
AI in at least one production workflow", attributed to an IAB survey; the primary source was not
located. A companieshistory.com roundup puts NA at 33.6%–40.6% of global AI-in-media revenue
depending on firm and scope — secondhand, with the scope spread doing all the work. Treat both as
unsourced until the originals are read.



#### Pass 15 (2026-11-26) — out-of-home, signage & retail media

**The most programmatic DOOH market in the world, and the one where the measurement standard exists.**
EMARKETER forecasts **~US$4.8B of US DOOH ad spend in 2026**. Programmatic reached **24% of US DOOH
spend in 2024**, projected to **65% by 2029**; a trade report has programmatic spend rising **49%** as
marketers shift budgets. North America's share of global DOOH revenue is reported inconsistently
(**~35%–42%** depending on publisher) — quote the range, never one figure. Digital is **~36.9% of
2025 OOH revenue** here (WOO-based).

**Players.** Lamar Advertising and OUTFRONT Media dominate inventory; newer entrants include Wow Media
in premium digital formats and OBM's *Ike* smart-city kiosks. Buying runs through DV360 and The Trade
Desk. JCDecaux and Clear Channel are also present.

**Standards.** The **IAB DOOH Measurement Guide (July 2025)** is the region's distinguishing asset —
shared standards exist here that do not exist elsewhere — but adoption is early-stage.

**Regulation — two fronts, neither federal.** There is no federal AI statute bearing on DOOH. The real
constraints are **local permitting for physical installations** and **privacy rules for audience
measurement**. Compliance with municipal rules is repeatedly cited as a cause of approval delay and
operational complexity.

**Opportunity.** The measurement *standard* is published and the open *implementation* is absent
(`openooh/measurement-spec`: dormant since 2021, no licence). A credible proof-of-play and
measurement implementation built against the IAB guide is the single most sellable asset in this
plane, and NA is the only region where the specification to build against is already agreed.


#### Avails, windowing & distribution rights — pass 16 (2026-11-26)

**The incumbents are all North American, and none of them is open.** FilmTrack, Whip Media, Rightsline,
FADEL and Vistex are the systems that hold avails and deal terms in production. There is no open-source
competitor to any of them (see `verticals/solutions.md`). NA is therefore the region where the
engagement is **integration beside an incumbent**, never replacement.

**Confirmed integration surface.** API Evangelist published independent third-party profiles of the
public API surfaces of `api-evangelist/filmtrack` (2026-10-30) and `api-evangelist/whip-media-group`
(2026-11-01). Both are 0 stars with no licence and are **profiles, not code** — but they establish that
these incumbents expose public APIs, which is what makes a side-by-side build designable rather than
speculative.

**The settlement layer here is contractual, not software, and that is a structural fact about NA.**
Residuals are set by guild agreement — SAG-AFTRA and the WGA — and the recently negotiated Hollywood
guild contracts now carry explicit AI terms (Chambers *Media & Entertainment 2026*, USA–New York trends).
There is also state-level legislation protecting musicians from unauthorised AI voice clones. So the
rules that decide what is owed are bargained, change on a contract cycle, and are not expressible as a
stable schema. This is the clearest reason the settlement step of the gradient is a literal zero in open
source: the spec itself is renegotiated every three years.

**Regulation is otherwise light and that cuts against budget.** There is no federal AI statute bearing
on distribution rights. Grant Thornton's 2026 media AI survey finds regulatory uncertainty is a *lower*
concern in media (34%) than across sectors generally (44%). Unlike EMEA, NA has **no catalogue-composition
duty** — nothing obliges a US VOD service to report what share of its catalogue is domestic. There is no
compliance deadline to sell against.

**EIDR is a North American institution with no open client** (established pass 5, unchanged). The
canonical title registry for this plane is headquartered in the region and reachable only by membership.

**Opportunity — ranked for NA.** The sellable asset is *not* compliance, it is **exposure control**:
titles live outside their window, windows expiring unnoticed, territories licensed but unpublished. That
is a revenue-and-liability dashboard built on P16.1, sold on money rather than on a deadline. It is a
harder sale than EMEA's statutory report and a larger one, because it touches the catalogue of the
companies that own the incumbents' biggest contracts.

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

#### The audience & measurement plane — added 2026-11-25 (pass 7). The one region where the *measurement method itself* was legally blocked

- **The finding of this plane, and the most sellable one in this file: in EMEA the measured party can
  veto the sensor.** In **January 2026 YouTube sent cease-and-desist letters to Barb and Kantar Media**
  over the **audio-matching ACR** used to report some 200 YouTube channels on UK television sets, and
  **Barb paused that service on 28 January 2026.** Nowhere else in this KB has a *measurement
  technique* — not a licence, not a model — been stopped by the entity being measured.
  - **Why it matters commercially:** ACR is the only panel-free way to see what a TV is actually
    playing, and the open matcher exists today (`a-gram/audioneex`, **MPL-2.0**, 61★ — weak per-file
    copyleft, so linkable from proprietary code). The technology was never the obstacle. **The
    obstacle is permission**, which is the same law this KB found in the rights-reservation plane,
    arriving here through contract rather than copyright.
  - **The design consequence, and it is concrete:** any EMEA measurement product must be built on
    **consented first-party and device-level data the client already has the right to observe**, not on
    recognising third-party platform content. Sell the audience graph, not the ACR.
  - **Source caveat, stated plainly:** `www.barb.co.uk` and `videoweek.com` **do not resolve from this
    session** (outside the allowed network domains), so this is recorded from trade-press summaries and
    **has not been confirmed against Barb's own statements.** The post-pause status of the service is
    **unknown**. Verify before putting it in a client deck.
- **EMEA is also the only region where audience measurement is being pulled into media *law*.**
  Germany's AGF reports that it is engaged, through its membership of the Audience Measurement
  Coalition, on **how the European Media Freedom Act (EMFA) applies to audience measurement** — and AGF
  names **deduplicated cross-media reach** as the market's dominant demand. Measurement methodology
  becoming a regulated subject is a procurement trigger: a methodology that cannot be explained cannot
  be defended.
- **A regional consolidation is underway and it is an opening.** **CIMM and the WFA announced a
  strategic review of cross-media measurement in Europe in January 2026**; the UK's **Origin**
  cross-media project uses Médiamétrie's **Virtual ID** model; Barb has added pre-campaign planning to
  its Ads Hub. Médiamétrie's own public position is that AI must be integrated in a **"governed,
  explainable"** way faithful to independence and rigour. **The deliverable EMEA is asking for is an
  auditable method, not a better model** — which is the same shape as the EU AI Act Article 50 work
  already recorded in this section.
- **Where to lead:** permissively licensed, self-hostable components, because the regional constraint is
  data residency and auditability rather than model capability — `splink` (**MIT**, 2,604★, UK Ministry
  of Justice, pushed on measurement day) for identity resolution with a public-sector provenance that
  survives procurement review, plus `cube-js/cube` (**Apache-2.0**) as the single semantic definition of
  "a viewer" that an auditor can read. Avoid `rudderlabs/rudder-server` entirely: **Elastic License
  2.0**, which forbids offering it to third parties as a managed service — i.e. it forbids the SI model.
- **Informed gap:** **no EMEA-specific figure was found for open-source recommender or analytics
  adoption by European broadcasters**, and the **commercial terms of JIC/currency data licences could
  not be obtained** from any reachable source. Treat currency data as *not researched and not free*.


#### The live & delivery plane — added 2026-11-26 (pass 8). The only region where delivery is governed by a **stopwatch**

**The 30-minute rule is the commercial fact of this plane in EMEA.** Nowhere else in this KB does a
regulator impose a *latency* requirement on an operational response.

- **Italy (Piracy Shield)** is the reference model. AGCOM can issue near-instant blocking orders
  **without prior judicial review**, and blocks must be implemented **within 30 minutes**. By
  mid-2026 it had reportedly blocked **more than 122,000 domains and IP addresses** (press-attributed;
  **not** confirmed against AGCOM directly — flagged, not promoted). Resolution **47/25/CONS**
  (approved February 2025) extended the duty to **VPN and public DNS providers**, and a
  **multimillion-euro fine was levied on Cloudflare** for refusing to implement blocks via its public
  DNS service.
- **EU level:** the study *Countering online piracy of sports and broadcast in the EU* (Prof. Giovanni
  Maria Riccio) recommends moving from voluntary guidance to a **binding Regulation** for
  live-streaming piracy, with a **30-minute compliance window modelled on Italy**, extended across
  **DNS resolvers, VPNs and CDNs**. The Audiovisual Anti-Piracy Alliance filed a plea on
  **2026-11-17**; Commission recommendations were expected "in November" — **this pass could not
  confirm they have been published.** An EU assessment separately concluded that rapid blocking
  **comes up short** for sports and broadcast.
- **Spain:** a Commercial Court order of **February 2026** requires blocking of **IP addresses**, and
  LaLiga is **blocking entire IP ranges rather than specific infringing domains** — the overblocking
  complaint in one sentence. On **2026-04-29** Spain's Commission on Economy, Trade and Digital
  Transformation voted to direct the government to reform the legal framework behind the regime. A
  European Commission letter of June 2025 had already raised **overblocking of legitimate sites,
  lack of transparency and absence of prior judicial review**. LaLiga has asked the Commission to add
  several **VPN providers** to the EU piracy watch list, arguing they damage territorial exclusivity.

**The product this creates.** A rights holder or broadcaster in Italy or Spain needs: live detection,
evidence capture, an auditable order trail, a 30-minute actuation path across DNS/CDN/VPN
intermediaries, **and** a defensible overblocking record — because the political risk has now
inverted from "too slow" to "blocked the wrong thing". That last item is the differentiator: the
Commission, the Spanish Congress and the EU's own assessment have all criticised the regimes from the
**overblocking** side. Sell the evidence-and-proportionality trail, not the blocking.

**⛔ The licence trap that lands precisely on the EMEA pilot.** 5G Broadcast/MBMS — the technology a
European public broadcaster would pilot for stadium and mass-event delivery — has its reference stack
under the **5G-MAG Public License v1.0**. It is Apache-2.0 in structure and wording, and its patent
grant covers Essential Patents **"solely for study, testing and research purposes"**, explicitly
**"excluding selling"**; for anything else you merely "**commit to be prepared to negotiate**" FRAND
terms with every contributor. A field-of-use restriction on selling means **it is not open source**,
and a pilot that quietly becomes a service has acquired an unbounded patent obligation. Flag it at
the architecture review, not at go-live. (`5G-MAG/rt-mbms-modem` is separately AGPL-3.0.)

**Sovereignty is now a delivery requirement, not a slogan.** The DPP's *European Media Trends 2026*
report describes AI as the dominant driver of change in European media and records a growing
appetite for **digital sovereignty** as part of business resilience. An imec-SMIT (Vrije Universiteit
Brussel) mapping from **May 2026** sharpens it: AI adoption **does not automatically translate into
control, revenue or strategic autonomy** — value is captured by whoever controls **infrastructure,
data, models, interfaces, rights and business arrangements**. That is an argument for self-hosted
origin and packaging, and this plane is where it is actually winnable: `ossrs/srs`, `mediamtx`,
`pion/webrtc`, `shaka-packager`, `trafficserver` and `mp4ff` are MIT/Apache/BSD end to end.

**The permissive EMEA toolchain exists and is Swedish.** `Eyevinn/mp4ff` (MIT, 669★),
`Eyevinn/whip` (Apache-2.0), `Eyevinn/srt-whep` (Apache-2.0), `Eyevinn/webrtc-player` (MIT) and
`Eyevinn/channel-engine` (Apache-2.0) are a coherent, permissively-licensed, region-native delivery
kit. `mengelbart/moqtransport` (MIT) puts EMEA in the MoQ implementer set too.

**Regulatory context carried from earlier passes:** the EU AI Act's Article 50 transparency duties
remain the labelling spine (the **2026-12-02** deadline already recorded in this file), and the
European Parliament voted **569 to 45** to adopt its position on the AI Act Omnibus simplification
proposal. The EBU convened its **AI Forum in Brussels in March 2026**.

**MENA, within EMEA, stated as its own figure:** Arab media AI spending is projected at
**USD 520 million in 2026**, with one report expecting AI adoption to exceed **95% among media
organisations in the UAE and Saudi Arabia by 2030**. Reported, not independently verified.

#### Trust & safety, age verification and DSA transparency — added 2026-11-26 (pass 9)

**EMEA is the only region where the compliance artifact is itself open source, published by the
regulator. That makes it the only region where a fixed-price compliance build is honest.**

- **The Commission shipped code, not just a specification.** The **Age Verification Blueprint** is a
  nine-repo estate under the [`eu-digital-identity-wallet`](https://github.com/eu-digital-identity-wallet)
  organisation: the white-label Android and iOS apps under **EUPL-1.2**, the ZKP libraries, issuer,
  verifier UI, trust validator and — one star, and a media use case written by the regulator — a
  **cinema age-gate reference frontend**. The design reveals only whether the user meets the
  requested threshold, using zero-knowledge proofs. Full table in `repos/foundations.md`.
- **Dates, with their confidence stated.** First blueprint **July 2025**; second version with
  technical specifications and open-source implementation **October 2025**; a **Commission
  Recommendation on a common EU approach to age verification reported for 29 April 2026**; pilots
  reported in **Denmark, France, Greece, Italy and Spain**; a **31 December 2026** rollout date
  reported by a single vendor blog. ⚠️ **`ageverification.dev` does not resolve from this session**
  (outside allowed network domains), so **the rollout deadline and the current blueprint version are
  reported, not verified.** Verify from an unrestricted network before putting either in a proposal.
  One security vendor (which sells a competing wallet product) has publicly criticised the April 2026
  release as a white-label reference implementation rather than a hardened product — one-sided, and
  consistent with what the repos are.
- **DSA enforcement is now measured in hundreds of millions.** Reported decisions: **X — €120M**
  (5 December 2025, the first non-compliance decision, now under court challenge in *X v
  Commission*); **Temu — €200M** (May 2026, inadequate systemic-risk assessment); **AliExpress —
  €550M** (July 2026, the largest to date, with an action plan due 20 October 2026). Open matters
  include preliminary findings against **TikTok** on addictive design, a **Meta** investigation into
  minors' access (29 April 2026) and a **Shein** investigation (17 February 2026). Ceiling is **6% of
  worldwide annual turnover**. ⚠️ Sources are secondary legal commentary and **disagree on whether
  the 28 May 2026 second decision was X or Temu** — cite the amounts, not the sequence, until
  checked against Commission press releases.
- **The transparency obligation has open code on both sides.** The Commission's own
  [transparency-database](https://github.com/digital-services-act/transparency-database) is
  **GPL-2.0** (55★, pushed 2026-11-25), and the submission SDK
  [afkzonagroup/rationale](https://github.com/afkzonagroup/rationale) is Apache-2.0 with **zero
  stars**, four days old at the time of this pass. **Every statement of reasons a platform files is a
  per-action structured record** — that is an integration, a volume problem and an audit trail, which
  is exactly the shape of work Globant sells.
- **The sellable opening.** EUPL-1.2 and Apache-2.0 mean the EU estate is **legally reusable outside
  Europe** (see `intel/trends.md` trend 10). EMEA is therefore not just a compliance market — it is
  where the reference implementation for every other region's age-assurance build comes from.



#### Theatrical & digital cinema — added 2026-11-26 (pass 10)

**The channel, with a measured disagreement worth carrying.** UNIC's **Annual Report 2026**
(published at CineEurope, June 2026; UNIC covers **39 territories**) reports 2025 European
admissions **down 5.3% to 863.6m** with box office **stable at €6.9bn**. France fell 13.6% to
156.8m, Spain 11% to 65m, both attributed to "a lack of strong local titles". The European
Audiovisual Observatory reports the same year as **796m, down 5.5% from 843m.** The two numbers
differ by ~68m admissions because the territory coverage differs. **Cite the body, not the number** —
a deck that quotes "European admissions" without saying whose is wrong by 8% whichever it picked.

**EMEA is where the permissive theatrical code is actually being written.** This is a small finding
with a disproportionate consequence, and it is the second confirmation of a pattern this KB first
recorded in pass 8:

- [`Limecraft/ebu-libmxf`](https://github.com/Limecraft/ebu-libmxf) (BSD-3, 17★, 2024-11-15) — a
  **Belgian vendor's fork**, and the most recently touched copy of the MXF container library in
  existence. The EBU's own last moved in 2013; the BBC's is in an `-archive` org.
- [`brightfish-be/DcpToolkit`](https://github.com/brightfish-be/DcpToolkit) (**MIT**, 3★, 2026-06-22)
  — a Belgian cinema-technology company's DCP read/write library, and **the only permissively
  licensed authoring-side code in the entire theatrical plane.**

So the one escape route from a copyleft-end-to-end plane is being built by two small Belgian
companies, at 17 and 3 stars. **That is a partnership or contribution target, not a dependency** —
but it is the only one on the map.

**Opportunities — EMEA**

1. **Validation-as-a-service, permissively licensed.** `ClairMeta` is BSD-3 and European in origin
   (Ymagis/Éclair). A European exhibitor or post house can have validation embedded in its own stack
   with no copyleft obligation — the one thing this plane permits. Pattern 28.
2. **Back the Belgian permissive cluster.** Contributing to `DcpToolkit` and `ebu-libmxf` buys
   influence over the only non-copyleft authoring path at a cost of single-digit stars.
3. **Local-title analytics for a market that just proved it depends on them.** UNIC's own explanation
   for the French and Spanish declines is title supply. The open box-office estate is 103 repos of
   2017–2020 coursework summing 29 stars.

**Informed gaps — EMEA, stated rather than filled.** (a) **Whether the European Accessibility Act
reaches cinema exhibition was searched and not established** — the search returned the US DOJ rule
and nothing connecting the EAA to theatres. Treated as *not investigated*, not as "no duty".
(b) The Observatory's FOCUS 2026 screen-density figure appeared only in a garbled form in the
retrieved snippet and is **not recorded here** rather than guessed at. (c) `new.isdcf.com` does not
resolve from this session, so **ISDCF commercial terms and the current Interop-deprecation status
are unverified** — the May 2026 ISDCF minutes are indexed but their contents were not readable here.

#### Pass 11 (2026-11-26) — the description & semantic-interchange plane

**EMEA is where this plane's open-source infrastructure is actually built and maintained**, and the
only region with public institutions shipping it:

- **INA** (Institut national de l'audiovisuel, France) — `ina-foss`, 22 repos.
  `inaSpeechSegmenter` (MIT, 919★, 2026-03-12) is the most-starred purpose-built archive-indexing
  tool found in this plane, and `ground-control-frontend` was pushed 2026-11-25.
- **National Library of Finland** (`NatLibFi`) — **Annif** (Apache-2.0, 280★) and **Skosmos**
  (MIT, 269★), the two tools that do the actual subject-assignment and vocabulary-publishing work,
  plus Finto/Finto AI as live national services since May 2020.
- **EBU** — EBUCorePlus (MIT), `awesome-broadcasting` (CC0-1.0, 1805★), and 108 public repos.

**The licence trap is also European, and it is the sharpest in this pass.** EBU's **EBUCore**
(Tech 3293), the descriptive/technical metadata spec most European broadcasters have actually
deployed, is **CC BY-NC-SA 3.0 — NonCommercial** (verified: `ebu/ebucore/master/LICENSE.md`, 386 B).
Its successor **EBUCorePlus is MIT**. So the modern model is commercially usable and the installed
one is not. Any EMEA broadcast engagement that touches metadata modelling must establish **which of
the two the client is on** before a line of code is written; the answer changes what Globant may
ship. This is the second time this KB has found a standards body whose predecessor and successor
differ in commercial usability.

**Policy and funding context, 2026:**
- **TEMS (Trusted European Media Data Space)**, EBU a founding partner, selected by the European
  Commission and funded by the Digital Europe Programme, **runs 2023-2026 — i.e. it concludes this
  year**, which makes its final deliverables a near-term buying trigger. Partner counts disagree
  across sources (EBU: 43 partners / 14 countries; a Gaia-X document: 42 / 12) — unresolved.
- **EUIPO published a metadata mapping study on 2026-05-28** finding that the lack of
  interoperability between copyright-related metadata standards "triggers major inefficiencies."
  That is an EU-institutional source measuring the exact defect this plane addresses — the most
  sellable single citation in this pass for EMEA.
- EBU has called for **sovereign cloud and AI infrastructure** in Europe and announced a
  **sovereign-AI partnership with NVIDIA** for public broadcasters. A vendor analysis separately
  warns that cloud media-asset tools relying on third-party AI engines **outside Europe** are a
  regulatory exposure — which is precisely the argument for self-hosted Annif/Skosmos over an API.
- The European Parliament voted **569 to 45** to adopt its position on the **AI Act Omnibus**
  simplification proposal; Article 50 transparency duties are already reshaping adland practice.
- An imec-SMIT (VUB) paper, May 2026, argues adoption alone confers neither control nor revenue —
  value accrues to whoever controls infrastructure, data, models and rights — and warns that smaller
  and regional media players risk being left behind. That is the pitch for giving a regional
  broadcaster its own description layer rather than renting one.

#### Pass 12 (2026-11-26) — the sound & immersive-audio plane: **this region builds the open stack**

**The finding for EMEA is a supply finding, and it is the strongest in this file.** The entire open
object-based-audio stack is European public-service infrastructure: the **EBU**, the **BBC** and the
former German **IRT** wrote `ebu_adm_renderer` (BSD-3-Clause-Clear), `bear` (Apache-2.0, BBC
copyright), `libadm`, `libbw64` (Apache-2.0) and the `ear-production-suite` (GPL-3.0-or-later, BBC/
EBU/IRT, licence at `packaging/LICENSE.md`). Nowhere else in this KB does a region so clearly *own*
a plane's permissive substrate. An EMEA engagement in immersive audio is working with the
standard-setters' own code, under Apache and BSD terms, with the specifications (ITU-R BS.2076,
BS.2127, BS.2051) public.

**Regulation: transparency duties apply to synthetic audio.** The EU AI Act's transparency
obligations for synthetic content reportedly took effect **2026-08-02**, and one market report states
the practical consequence plainly — user-facing synthetic dubbing must disclose that it is
artificial. **ACT**, the commercial broadcasters' association, argues in its June 2026 issue paper
that broadcasters' own AI use should fall under existing editorial-responsibility rules and that
blanket Article 50 labelling would be disproportionate; the **EBU** has separately called for clearer
rules on big tech and AI. The direction of travel is settled; the detail for broadcasters is still
contested.

**Market context.** The DPP's *European Media Trends 2026* reports AI as the dominant driver of
strategic change and that **a quarter of European media companies have shifted toward in-house
development** — which is a direct read on buying behaviour: more integration, fewer black boxes.

**Opportunity for Globant in this region.**
1. **Be the integrator of the EBU/BBC stack** — it is permissive, institutionally credible, and
   under-tooled. The reference renderer at 105 stars is an opportunity, not a risk, when the client
   is the institution that wrote it.
2. **Synthetic-audio disclosure plumbing**: Article 50 compliance is a metadata-and-provenance
   problem, which connects directly to the C2PA work recorded in pass 9.
3. The in-house-development shift favours **capability transfer engagements** over managed services.

#### Pass 13 (2026-11-26) — the subscription layer: a dated statutory deadline, five weeks out

**The UK DMCCA subscription regime is the most concrete near-term compliance deadline in this entire
KB.** Draft regulations — the **Consumer Subscription Contracts (Cancellation and Information)
Regulations 2026** — were **laid before Parliament on 2026-10-19** and come into force on
**2027-01-01**, subject to approval. They apply to subscription contracts **entered into on or after
that date**; existing contracts and B2B contracts are out of scope.

What the regime requires, as drafted:

| Duty | Detail |
|---|---|
| **Reminder notices** | Roughly every six months on rolling contracts; before a trial or discount ends; before renewal onto a term of 12 months or more, with an additional earlier reminder for long-term renewals |
| **Two cooling-off periods** | A 14-day *initial* right at the start, **and a new 14-day *renewal* cooling-off right** at certain renewal payment dates |
| **Exit parity** | Online cancellation must be available where the consumer signed up online |
| **Charging** | A consumer may end a subscription at any time and cannot be charged for a renewal before the contract actually renews |

The **renewal** cooling-off right is the part worth flagging to any client: it is not a sign-up-time
checkbox but a **recurring, date-triggered obligation on every qualifying renewal**, which means it
lands in the billing scheduler, not in the marketing site. *(The date has moved more than once —
Spring 2027 and an unspecified January were both briefed earlier in 2026 — so confirm against the
final SI before contracting.)*

**No open-source tooling implements any of this.** The reminder calendar, the dual cooling-off clock
and the exit-parity audit trail are all absent from Kill Bill, Lago and REMP alike.

**Wider EMEA context.** Member States are pressing for an overhaul of the **AVMSD**; the Commission
has consulted on EU copyright rules bearing on AI training and licensing; and the proposed **EU KIDS
Act** (child safety, not an AI-media rule) had a feedback period running to **2026-12-03**, with
adoption not expected before 2028. On capability, an **imec/VUB report (May 2026)** finds Europe's
media sector most active at the *application* layer — archive search, newsroom productivity,
audience-facing products — and **DPP's European Media Trends 2026** reports that **a quarter of
European media companies have shifted strategy toward building in-house or taking greater
integration responsibility**. That is a direct demand signal for an integration partner.

**A regional asset worth naming in a pitch:** the only open reader-revenue platform that exists,
[REMP](https://github.com/remp2020/remp) (MIT, 138★), is **EMEA-origin** — built and run by
Denník N in Slovakia. An EMEA publisher engagement can start from a European reference
implementation rather than a US SaaS.

**Opportunity for Globant in this region.**
1. **The DMCCA compliance build** — a dated deadline, a specified artefact, and zero open tooling.
   This is the highest-urgency item in this pass and it has roughly five weeks to run.
2. **REMP integration and modernisation** for European publishers, including replacing its dead,
   unlicensed churn component (`pythia-tools`, no licence, dormant since 2023) with `lifelines` (MIT).
3. **Avoid** proposing Lago or flexprice (AGPL-3.0) as an embedded component for a client who intends
   to modify them — Kill Bill (Apache-2.0) is the permissive equivalent.

#### Localization substrate — added 2026-11-26 (pass 14)

**EMEA is the only region where a self-hosted localization stack is a *sovereignty* product rather
than a cost product** — and that reframing is worth more than the cost saving.

- The DPP's *European Media Trends 2026* report finds a **growing appetite for digital sovereignty as
  part of business-resilience planning** inside European media companies — i.e. sovereignty has moved
  from a policy topic to a procurement criterion.
- A VSN analysis makes the specific technical complaint: **standard cloud DAM offerings rely on
  third-party public AI engines that aggregate data on extra-European servers.** Translation is
  exactly such a call — every segment sent to a hosted MT API is content leaving the jurisdiction.
- Legislative state, dated: the **European Parliament voted 569–45 to adopt its position on the AI
  Act Omnibus simplification proposal**, so the Act's obligations are being actively reshaped rather
  than settled. A 2026 engagement should treat the compliance surface as *moving*, and build a policy
  engine rather than hard-code a compliance mode. Article 50 transparency and the August 2026
  synthetic-dubbing disclosure duty are already recorded above (pass 12) and are unchanged.
- Convening bodies to track: the **EBU AI Forum, 25 March 2026, Brussels**; the European Commission's
  Futurium initiative on *Supporting AI Adoption in Europe's Cultural and Creative Sectors*; and
  DIGITALEUROPE's call for technology-neutral horizontal regulation in the AVMSD evaluation.
- A May 2026 **imec** study supplies the sharpest line for a sovereignty pitch: *adoption does not
  automatically translate into control, revenue, or strategic autonomy.*

**The buildable asset — a fully on-premises localization stack with no permissive-licence problem:**

| Layer | Pick | Licence | Why this one in EMEA |
|---|---|---|---|
| MT engine | `argosopentech/argos-translate` | **MIT** | Runs offline. No content leaves the client's estate — and no AGPL duty, unlike LibreTranslate above it. |
| Platform | `mozilla/pontoon` | **BSD-3-Clause** | The only mature *permissive* platform in the tier; the client can own and relicense the result. |
| Platform (alt) | `WeblateOrg/weblate` | GPL-3.0 | More capable and actively pushed; GPL is acceptable for a self-hosted deployment the client does not redistribute. |
| Termbase | `gaois/terminologue` | MIT | Per-market terminology, which in EMEA is per-language *and* per-regulator. |
| Linguist desktop | `vslavik/poedit` | MIT | What the human actually uses. |

**MENA, which this KB has been thin on:** media AI spending in the MENA region is reported as
expected to reach **USD 520 million in 2026** (Khaleej Times, trade reporting — single secondhand
source, treat the figure as indicative). Arabic adds a bidirectional-text and dialect dimension that
the open stack above handles poorly, which is a differentiator rather than a blocker.

**Regional method note:** the REUSE licence layout (`LICENSES/<SPDX-ID>.txt`) that defeated the
licence probe this pass is an **FSFE** standard, disproportionately used by European and EU-funded
projects. A licence sweep tuned to American repo conventions will systematically under-report
compliance in exactly the estate a sovereignty engagement draws from. Probe `LICENSES/` here.



#### Pass 15 (2026-11-26) — out-of-home, signage & retail media

**The regulated region, and the only one with a measured programmatic-penetration league table.**
Europe's DOOH market was **~US$3.6–3.73B in 2025**, with projected CAGR **~9.5%–10.7%**. Of the
**US$1.339B** global programmatic DOOH spend in 2025 (World Out of Home Organization), **EMEA
generated US$521M at 9.4% penetration** — and **Germany led all major markets at 31.8% penetration**,
the highest figure of its kind found in any region this pass.

**Players.** JCDecaux (with its **VIOOH** SSP) is the structural incumbent; it launched an AI-powered
programmatic DOOH platform in January 2025 and expanded high-resolution networks across European
transport hubs in June 2026. **Displayce** was the first specialist platform to add generative AI for
suggesting DOOH strategies (September 2024). Clear Channel is also present.

**Regulation is the binding constraint, and it is municipal rather than EU-level.** Frameworks differ
widely by country *and by city*: limits on digital billboard placement and on lighting near
residential and sensitive areas. A pan-European rollout is therefore a per-city permitting programme,
not one compliance exercise.

**Sustainability is a procurement criterion unique to this region.** Media owners score screens for
energy use and report real-time emissions — which makes player efficiency a *commercial* requirement,
not an engineering preference.

**Informed gap, stated rather than implied.** Two searches found **no EU-level rule specific to AI in
DOOH**. The adjacent hook is the AI Act's treatment of biometric categorisation, but **no DOOH-specific
provision was verified in this pass** — treat it as *unresearched*, not as *absent*, and go to primary
sources before advising a client.

**Opportunity.** Germany's 31.8% penetration is the proof that programmatic DOOH scales in a strict
regulatory regime. The sellable asset is a **privacy-by-construction measurement design** (count
on-device, discard frames, emit aggregates, never form a biometric template — P15.4) plus per-city
permitting workflow. Both are judgment work, which is exactly what has no open-source substitute.


#### Avails, windowing & distribution rights — pass 16 (2026-11-26)

**EMEA is the only region on earth where catalogue composition is a measurable statutory duty, and the
only one where release windows are law rather than contract.** For this plane that makes it the strongest
of the four regions by a wide margin.

**AVMSD Article 13 — the duty, with its counting method.** Article 13(1) requires on-demand providers to
"secure at least a 30% share of European works in their catalogues and ensure prominence of those works".
The specifics that make it buildable:

- The Commission's **2020 guidelines count the share by total number of titles** — not by hours, not by
  catalogue value.
- The 30% must hold **in each national catalogue** of a multi-country provider, not as a group average.
  The Commission's stated view is that the objective "can only be effectively achieved if the 30% share
  is secured in each of the national catalogues offered by multi-country VOD providers."
- Article 13(2) permits member states to impose **financial contributions**, reaching services
  established in another member state but targeting their audience.
- Article 13(6) exempts providers with **low turnover or low audience**.
- **17 Member States** had implementing measures in force during the 2020–21 reference period
  (COM(2024)261).

**The measured gap — the most sellable number in this plane.** European works are reported at roughly
**30% of VOD catalogues but only ~25% of actual consumption**; a separate breakdown puts EU works at 28%
of catalogues with UK works adding a further 9%. A provider can therefore satisfy the catalogue duty and
still fail the *prominence* half, and the gap is demonstrable on a chart. Treat these as secondary
reporting, not Commission data — but the shape of the gap is corroborated across sources.

**France: the one jurisdiction where a window engine must encode statute.** The `chronologie des médias`
fixes release windows by law, tiered by each platform's investment commitment to French production.
⚠️ **The 2026 month values are disputed and this KB will not assert one.** Trade press places Netflix at
15 months and Prime Video at 17 on grounds of insufficient investment in French cinema, and reports both
platforms **litigating for alignment to 12 months**; a French observatory page states the SVOD window
changed on **2026-01-01**, ending Netflix's 15-month position. Sources also conflict on the framework's
origin (an interprofessional agreement of 2022-01-24 vs. one signed 2025-02-06, each made binding by
ministerial order). **No official text was located from this session.** Verify against the **CNC** and
**Légifrance** before quoting any number to a client. What is *not* in doubt: the windows are statutory,
they are tiered by investment, and they are under active litigation.

**Regulatory direction.** The European Parliament adopted its position on the AI Act Omnibus
simplification proposal by **569 to 45**. DIGITALEUROPE is arguing for technology-neutral horizontal
regulation rather than expanding sector-specific AVMSD rules; CCIA has filed recommendations for the
Commission's AVMSD evaluation. An Art. 13 revision would change the counting method and therefore every
compliance report built against it — watch this before committing to an implementation.

**Opportunity — ranked first across all four regions.** An **auditable AVMSD Art. 13 catalogue-composition
reporter** (P16.2). The obligation is in force, the counting method is published, the computation is
mechanical, the per-title European-works classification is the defensible judgment layer, and **nothing
open source computes it today**. France adds a second, narrower asset: a window engine whose rules are
statutory, which is the only place that work can be sold as compliance rather than as operations.

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

#### The audience & measurement plane — added 2026-11-25 (pass 7). The region where fragmented measurement is the named cause of the revenue gap

- **APAC's monetisation gap is attributed, by the trade press covering it, specifically to
  measurement.** Variety's 2026 reporting on the Asia-Pacific screen economy racing toward **$200
  billion** records that ad dollars have **not** followed audiences onto the streaming screen, and
  attributes the lag to **fragmented measurement standards across streaming platforms, device makers
  and ad-supported channels.** Alongside it, **APAC ad spend is on track to grow just 5.2% in 2026 — the
  slowest rate since the pandemic.** The diagnosis in the region's own press is therefore not "not
  enough AI" but "no comparable numbers", which is exactly a measurement-infrastructure engagement.
- **The strongest independent confirmation of that reading is a vendor survey that argues against its
  own product category.** Braze's June 2026 APAC report on media and entertainment concludes the biggest
  barrier to effective personalisation is **not a lack of AI** but a **lack of unified data,
  measurement discipline and clear** goals. When a marketing-automation vendor tells the region its
  problem is upstream of AI, the upstream work is the sale: **event collection, identity resolution and
  a semantic layer before any model.** See Pattern 20.
- **ACR is being deployed commercially here while it is being litigated in EMEA.** Nexxen has expanded
  its ACR-based TV Intelligence in **Australia** across **more than 1.9 million devices**, covering
  linear and streaming. Same technique, opposite regulatory weather — which makes **APAC the region
  where a panel-free measurement product is most likely to be permitted to run.** Note this is a vendor
  announcement, so treat the device count as claimed rather than audited.
- **Regulation that bears on *this* plane — distinct from the labelling regimes already recorded
  above.** The rules that constrain personalisation and measurement are **data-protection and
  automated-decision rules**, not synthetic-media labelling:
  - **India — the Digital Personal Data Protection Act** is the main compliance driver for streaming and
    media audience data, and consent architecture is the gating work.
  - **Australia** is progressing a **second tranche of Privacy Act reforms**, a **"digital duty of
    care"**, and — most directly relevant — a **new transparency obligation for automated
    decision-making**. A recommender is an automated decision system; this is where a ranking layer has
    to become inspectable.
  - **South Korea and China** add content-approval and digital-content standards that, per Deloitte's
    regional read, demand substantial investment in governance infrastructure.
  - *(India's February 2026 IT Rules amendment and MeitY's April labelling proposal, Japan's election
    deepfake rule and Vietnam's machine-readable marking requirement are labelling obligations and
    belong to this KB's provenance plane — cross-referenced here, not re-counted as measurement
    regulation.)*
- **The APAC-specific opportunity:** the region has the industry's largest audience and its weakest
  comparability, and **no incumbent currency has the lock Nielsen has in the US.** A regional
  broadcaster or streamer can therefore own a **consent-aware first-party measurement and
  personalisation stack** built from permissive components — `recommenders-team/recommenders` (MIT,
  22,012★), `Transformers4Rec` (Apache-2.0) for session-shaped viewing, `alibaba/RecIS` (Apache-2.0,
  APAC-origin and therefore an easier internal sell) — rather than waiting for a currency to arrive.
- **Informed gap:** this pass found **no APAC-specific data on open-source recommender or analytics
  adoption** by broadcasters in India, China, Korea or Japan, and **no audited figure** for ACR device
  coverage in any APAC market. Unresearched, not absent.


#### The live & delivery plane — added 2026-11-26 (pass 8). The region that owns the permissive substrate *and* the hardest delivery problem on earth

**APAC is the only region in this KB that owns a permissive substrate outright.** The two
most-starred self-hosted streaming servers in the world are both China-origin and both MIT:

| Repo | Licence | Stars | Last push |
|---|---|---|---|
| https://github.com/ossrs/srs | MIT | 29,457 | 2026-11-25 |
| https://github.com/ZLMediaKit/ZLMediaKit | MIT *(read; API said `NOASSERTION`)* | 17,729 | 2026-11-25 |

In every other plane of this KB the permissive layer is Western-origin and the Asian contribution is
downstream. Here it is inverted. `nttcom/moq-wasm` (MIT, NTT Communications) puts Japan in the MoQ
implementer set as well. **Practical consequence:** an APAC engagement can be built on
region-native, MIT-licensed infrastructure with no copyright gate at all — the licence conversation
in this region is about *codec patents*, not about code.

**The scale record is here, and it is the reference proof point.** JioHotstar peaked at
**72.5 million concurrent viewers** on the **ICC Men's T20 World Cup 2026 final** — stated by
JioStar's CEO and repeated in a Southeast Asia marketing release. The earlier **65.2 million** peak
(India v England semi-final, reported 2026-03-05) was described at the time as the highest
concurrency ever recorded for a live event on any digital platform. JioStar reports delivering over
**1 billion viewers every IPL season** and **FY26 revenue of ₹31,048 crore**.

⚠️ **Contamination caught in this figure.** A Medium write-up claims **821 million concurrent
viewers** for the same final. It conflicts with every other source by an order of magnitude and is
**not credible** — do not repeat it. The verified ceiling is 72.5M, and the gap between 72.5M and
821M is exactly the kind of number that destroys credibility in a pitch. *(Also note: the
"engineering story" posts about this stack are secondary blogs, not primary disclosures.)*

**Regulation is accelerating and diverging — which is itself the selling point.** A Latham & Watkins
alert of **September 2026** reports "a significant acceleration in the enactment of AI regulation
across the Asia-Pacific" and sorts regimes into groups: **binding risk-based frameworks** (South
Korea, Vietnam) and **targeted rules** (China), with a third category this pass could not read in
full. A CX Network survey (January 2026) covers nine APAC countries and centres on **disclosure and
labelling of generative AI** and high-impact systems. **Malaysia** is weighing AI rules inside a
**copyright law overhaul** (July 2026). An ASEAN policy brief (April 2026) records that policymakers
recognise the need for regional cooperation on media regulation but that **progress is slow**.

Divergence, not strictness, is the commercial fact: a regional streamer serving South Korea, China,
Malaysia and ASEAN markets must satisfy several incompatible labelling and disclosure regimes **from
one delivery chain**. That is a packaging-and-metadata problem — exactly where this plane's
permissive tooling (`shaka-packager`, `mp4ff`, `gpac`) operates.

**Demand-side pressure.** APAC adspend is tracking **+5.2% year-on-year in 2026, the slowest rate
since the pandemic**, while the Asia-Pacific screen economy is described as racing toward
**USD 200 billion** with a **monetisation gap** defining the decade. Delivery cost per stream is
therefore a board-level number here in a way it is not in North America — and the MIT substrate above
is the direct answer. APAC is reported as **second only to North America** in generative-AI adoption
pace, and the ABU notes public broadcasters in **Australia and Singapore** exploring AI for newsroom
workflows, archiving and verification. AI is the central theme of **APOS 2026** in Bali. One survey
of APAC PR professionals names **lack of structured training** as the most persistent barrier to
adoption — a services opportunity attached to every delivery build.

**Players named in the sources:** Tencent Video and iQIYI investing in generative AI (market-research
page, weaker source); Google, Netflix, YouTube, TikTok and Instagram ranking highest for consumer ad
equity across APAC per Kantar, which also finds roughly **one in three APAC consumers use AI to
research brands**, varying considerably by market.

#### Trust & safety and age assurance — added 2026-11-26 (pass 9)

**APAC has the most aggressive obligations in the world and the least open tooling. That gap is the
opportunity, and it is a build, not an integration.**

- **Australia is the live case, and the numbers are real.** The under-16 regime is **in force**:
  age-restricted platforms must take reasonable steps to prevent under-16s holding accounts, and by
  mid-December **4.7 million under-16 accounts had been removed**. Messaging, gaming, professional
  networking and education/health services are **carved out** under the 2025 rules, **amended in
  March 2026** to clarify scope. The **app-store age-assurance code applied from 9 September 2026**,
  and a **Digital Duty of Care** bill is pending (an exposure draft is reported for 8 September
  2026). Critically for design: **platforms may not require government ID as the sole method of age
  assurance**, and age-verification data falls under Privacy Act handling obligations partly enforced
  by the OAIC. **That combination — mandatory assurance, no ID-only route, strict data handling — is
  precisely the problem the EU's zero-knowledge libraries solve**, and nobody has ported them.
- **The rest of the region diverges, deliberately.** Reported in comparison guides: **Malaysia**
  mandates government ID; **Singapore's** app-store code uses a "reasonable accuracy" standard with
  app stores as the primary target; **Indonesia** is tiered by age with parental consent mandatory
  under 17. These are different *mechanisms*, not different thresholds, so a single implementation
  cannot satisfy them — **the asset is a policy engine per jurisdiction**, which is the same
  conclusion pass 8 reached for APAC on synthetic-content rules, now from a second direction.
- **India: measured as a gap, not as silence.** Searches returned **nothing current on the IT Rules'
  age-verification provisions**. The only result was a Supreme Court petition in which the court
  proposed to the Central Government that age verification be required and under-16/18 use
  prohibited, with **no law passed as of the most recent reliable snapshot**. This KB's existing
  record notes an **India IT Rules amendment dated 2026-02-20** (see `intel/trends.md`) on synthetic
  content; whether it reaches age assurance is **not established here**. Treat India as unresolved
  and verify with MeitY directly before advising.
- **Zero open implementations found.** No APAC-specific age-assurance or moderation artifact
  surfaced in this pass. The reusable primitives are the EU's Apache-2.0 ZKP libraries
  ([av-lib-android-zkp-age-icao](https://github.com/eu-digital-identity-wallet/av-lib-android-zkp-age-icao),
  [av-lib-ios-longfellow-zkp](https://github.com/eu-digital-identity-wallet/av-lib-ios-longfellow-zkp)),
  and the one platform-scale safety model trained on genuinely APAC-relevant abuse —
  Roblox's RoGuard — is **research-only licensed**. Stated as a gap: the region with the hardest
  deadlines has the thinnest open stack.



#### Theatrical & digital cinema — added 2026-11-26 (pass 10)

**The channel, split in two.** APAC is simultaneously the drag on the global number and the growth
story, and conflating them produces a wrong strategy:

- **China is the drag.** IBISWorld puts the Chinese cinema industry at **$7.9bn in 2026, up 6.6%**,
  while its **business count has declined at a 0.7% CAGR from 2021 to 2026** — revenue up, estate
  shrinking. Futuresource estimates China **down 5% against 2025**, and Gower Street attributed its
  downgrade of the global 2026 forecast largely to a disappointing Chinese New Year and Q1. Omdia's
  explanation is structural rather than cyclical: young audiences are leaving for cheaper and more
  interactive uses of their time.
- **India and the rest are the growth.** India's box office crossed **INR 13,000 crore**, with
  **national titles at ~90% market share** in 2025 — the most locally-dependent major market in the
  world. Hong Kong, South Korea and India all improved while China moved sharply the other way. IMAX
  is expanding across APAC and broadening its **PVR Inox** partnership to additional exhibitors.
- One vendor report puts APAC at **over 40% of new global screen installations.** Flagged as
  vendor-sourced and directional.

**Second confirmation: APAC owns the permissive substrate.** Pass 8 recorded this for live delivery
and called it the first inversion of the KB's usual pattern. It holds again here, and more starkly,
because the sample is the whole tier: **the only real open theatre-management system found anywhere
is [`1105821037/CineTMS`](https://github.com/1105821037/CineTMS) — 影院自动化放映控制系统, Apache-2.0
(verified, 11,357B `LICENSE`), 5★, 2026-07-30.** In a plane that is GPL/AGPL end to end, the single
Apache-2.0 platform-shaped artifact is Chinese.

**APAC is also the one region where Interop DCP persistence is documented.** ISDCF's October 2024
minutes recommend that the move to SMPTE for **Japanese subtitle cases** wait until fixes are
verified in theatres still running Interop. A pipeline serving Japan cannot drop Interop on the
schedule North America can — this is a concrete, dated, region-specific engineering requirement, and
the only one of its kind found in this plane.

**Regulation.** Latham & Watkins (September 2026) describes **three divergent categories** across
APAC: binding risk-based frameworks with tiered obligations (South Korea, Vietnam), targeted AI
regulation (China), and a third grouping. The consequence carried from pass 8 is unchanged and
applies here too: **the sellable asset is a per-jurisdiction policy engine, not a single compliance
mode.**

**Opportunities — APAC**

1. **The permissive TMS bet.** `CineTMS` is Apache-2.0 at 5 stars. Either it becomes the base of an
   open exhibition stack or nothing does — there is no second candidate on earth.
2. **A Japan-aware DCP pipeline.** Interop-and-SMPTE dual-path authoring with subtitle verification,
   against a documented ISDCF caution. Narrow, dated, and defensible.
3. **Local-title dependency analytics for India.** 90% national share means title supply *is* the
   business, and the open forecasting estate is coursework.

**Informed gap — APAC.** No verifiable 2026 country-level screen count for China or India: Omdia's
tracker is paywalled and Statista's China series was not retrievable. One snippet reporting "active
screens falling by 42 year over year to 498" **names no country and is therefore not recorded.**
Deliberately left as a gap rather than estimated.

#### Pass 11 (2026-11-26) — the description & semantic-interchange plane

**APAC has the most concrete *recent* work product in this plane of any region, and it is Japanese.**
The W3C **Media Content Metadata Japanese Community Group (`mcm-jp`)** published a final report,
**"Practical Use Cases of Media Content Metadata Interoperability", dated 2026-06-09**. A
jurisdiction-specific, standards-body-published, 2026 document on exactly this plane is a rare
artefact — most regions in this pass offered trade-press forecasts instead. Use it as the anchor
reference for any Japanese media-metadata engagement.
*(Channel note: the W3C report URL did not resolve from this session; it is recorded from search
results and should be re-fetched when w3.org is reachable.)*

**The region also has the clearest production deployment.** **ABC (Australia)** used **Gemini 2.0
Flash via Vertex AI** to generate descriptive metadata for its archive and has integrated AI tagging
**directly into the content pipeline** — not a pilot. The **ABU** (Asia-Pacific Broadcasting Union)
reports public broadcasters in **Australia and Singapore** exploring AI for newsroom workflows,
**archiving and verification**, and frames the regional challenge as complexity rather than pace.

**What that combination means commercially:** APAC is the region where the buyer is most likely to
have *already chosen a hosted frontier model* for cataloguing. The competitive position for open
source here is not "instead of Gemini" but **the vocabulary and validation layer around it** — Annif
or GLiNER constrained to the client's own controlled vocabulary, so output is auditable against a
thesaurus rather than free text. ABC's own framing (AI tagging in the pipeline) implies they already
need that constraint.

**Regulation is divergent by design.** Latham & Watkins (September 2026) sorts APAC into three
categories — binding risk-based frameworks (South Korea, Vietnam), targeted rules (China's), and a
third — with **content labelling** a particular focus. Malaysia is weighing AI rules and anti-piracy
provisions in a copyright overhaul. ASEAN policymakers see a need for regional cooperation on media
regulation but progress is slow. The asset for this region is therefore a **per-jurisdiction policy
engine**, the same conclusion pass 8 reached for rights reservation — labelling obligations are
metadata obligations, and they differ by country.

**Market context:** the Asia-Pacific screen economy is reported racing toward **$200bn** with a
monetisation gap defining the decade (Variety); APOS 2026 in Bali ran AI through the whole programme,
with Tencent Video and iQIYI named as generative-AI investors. Kantar finds roughly **one in three
APAC consumers** use AI to research brands, varying widely by market.

#### Pass 12 (2026-11-26) — the sound & immersive-audio plane: labelling is enforced, not announced

**APAC is the region where synthetic-audio rules have actually been enforced.** China's AI content
labelling measures (issued 2025-03-14, in force **2025-09-01**) run alongside the mandatory national
standard **GB 45438-2025**, and require **both** a visible label and **embedded metadata for
tracing**, with content sorted into confirmed / possible / suspected tiers. Audio is in scope as one
of the covered formats. Enforcement is documented: in **April 2026 the CAC acted against the Jianying
and Maoxiang apps and the Jimeng AI website** for failing to implement labelling properly, issuing
rectification orders and warnings. State-aligned reporting claims **150 billion+ pieces** of content
labelled across text, images, audio and video — treat the figure as platform-reported, but the
enforcement actions are specific and dated.

**Elsewhere in the region the picture is thinner but real:** Australia's **ACMA** published an *AI in
media* report in **April 2026**; the ABU notes public broadcasters in Australia and Singapore
exploring AI for newsroom, archiving and verification workflows. Commentary places APAC second only
to North America in adoption pace, and Mordor projects APAC as the **fastest-growing AI-dubbing-for-
OTT region at 27.96% CAGR**.

**An honest gap, stated rather than left silent:** none of the sources surfaced describes
**audio-specific technical requirements** under GB 45438-2025 — audio appears only as a covered
format. The watermarking and metadata field specifics would have to be read from the standard text
itself, which this pass did not obtain. **Do not quote audio-specific Chinese technical requirements
to a client on the strength of secondary reporting.**

**Opportunity for Globant in this region.**
1. **Label-and-trace pipelines for synthetic audio** — the one market where the obligation is
   enforced, and where "we can prove the label and the embedded metadata survived the transcode" is a
   procurement answer, not a nice-to-have.
2. **Dubbing at the region's growth rate**, with the licence caveat from this pass: an on-premises
   model delivery into a large APAC broadcaster is exactly the case `fish-speech`'s licence excludes.
3. **Brazil's DTV+ MPEG-H demonstrations** (CES 2026) make the APAC/LATAM standards split worth
   tracking jointly — see the LATAM section.

#### Pass 13 (2026-11-26) — the subscription layer: a commercial story, and an explicit regulatory gap

**Stated as a gap, not left as silence: no APAC-wide subscription-contract regime was found.** The
searches run for this plane returned no equivalent of the UK DMCCA regime or the US ROSCA/FTC
position for any APAC jurisdiction. An ASEAN policy brief notes that regional cooperation on media
regulation is recognised as necessary but **progressing slowly**. Country-level consumer-contract
rules (Australia, Japan, Korea, India) were **not** covered by these searches and should be checked
per-engagement rather than assumed absent — the gap recorded here is in *this pass's evidence*, not
necessarily in the law.

**The APAC story in this plane is commercial, and it is about monetisation mix.** Variety frames the
Asia-Pacific screen economy as racing toward **$200 billion** with a "monetisation gap" defining the
decade. Media Partners Asia puts the premium streaming market for Netflix, Prime Video, Disney+ and
HBO Max at about **$10 billion annually in APAC by end-2026**. The transition **from
subscription-first to hybrid monetisation** is described as the defining commercial story in the
region right now, and Kantar reported **Netflix with ads topping APAC marketers' list for the first
time**. Omdia forecasts **Asia & Oceania as the strongest region for revenue expansion in 2026**.

**Adoption is production-grade, not pilot-grade.** The headline example from APOS 2026 (Bali, June)
is **JioHotstar's conversational discovery feature, built with OpenAI, reporting 60% voice adoption
at scale**. Tencent Video and iQIYI are investing in generative AI; microdramas and AI-native
production were standing agenda items.

**The permissive-substrate inversion holds again.** Trend 50 recorded that APAC owns the permissive
substrate in the live & delivery plane. It repeats here: the **largest permissive project anywhere in
this plane is [Hyperswitch](https://github.com/juspay/hyperswitch) (Apache-2.0, 45,917★), built by
Juspay in India** — payments orchestration across PSPs, self-hostable. For an APAC engagement the
payments layer can be open, regional and permissive, which is not true in any other region measured.

**Opportunity for Globant in this region.**
1. **Hybrid plan mechanics** — ad-tier/paid-tier switching, downgrade paths and win-back, which is
   precisely the "monetisation gap" the regional analysis names, and which no open platform models.
2. **Hyperswitch-centred payment orchestration** for multi-country launches: many PSPs, many
   currencies, one permissive Apache-2.0 layer.
3. **Per-jurisdiction consumer-contract review before any cancellation-flow build** — the absence of
   a regional regime is not the absence of national ones, and this pass did not measure them.

#### Localization substrate — added 2026-11-26 (pass 14)

**APAC is where this plane has the most volume and the worst tooling fit**, because the binding
constraint is the *number of languages*, not the cost per language.

- Adoption pace: APAC is reported **second only to North America** in generative-AI adoption
  (AsiaTechX broadcasting trends, 2026), with AI described as moving into the core of production,
  operations and viewer experience.
- Consumer-side signal: Kantar's *Media Reactions 2026* finds roughly **one in three APAC consumers
  use AI to research brands and products**, with wide variation by market. Google ranks first for
  consumer Ad Equity across APAC, followed by Netflix, YouTube, TikTok and Instagram.
- Public-broadcaster demand is specific and matches this plane: the ABU reports public broadcasters
  in **Australia and Singapore** exploring AI for **newsroom workflows, archiving and verification** —
  all three of which are translation-adjacent in multilingual markets.
- Commercial AI investment named by market reporting: **Tencent Video and iQIYI** investing in
  generative AI.
- Regulatory shape is unchanged from pass 8 and still governs the build: Latham & Watkins (September
  2026) sorts APAC into **divergent regulatory categories** — binding risk-based regimes (South
  Korea, Vietnam), targeted regulation (China), and lighter-touch approaches — so **the asset is a
  per-jurisdiction policy engine, not a single compliance mode.** The ASEAN policy brief adds that
  regional cooperation on media regulation is recognised as needed but **slow**, so do not design for
  a harmonised ASEAN rule that does not exist.

**Why the open stack fits APAC badly, stated as a gap rather than glossed:** every platform in the
tier is built around European-style string catalogues and Latin-script segmentation. The specific
weaknesses — measured, not assumed, from what the repos are and are not —

- Segmentation for languages without spaces (Chinese, Japanese, Thai) is handled by the *filter*
  layer, and the filter layer's incumbent (**Okapi**) is not on GitHub at all, so the GitHub-native
  stack has no mature segmenter to inherit.
- The highest-star *applied* CAT tool in the whole plane is **`dmMaze/BallonsTranslator` (GPL-3.0,
  5,321★, pushed 2026-11-21)** — a Chinese-language comic/manga translation tool with OCR, inpainting
  and typesetting. ⚠️ GPL-3.0, so it informs an architecture rather than shipping inside a product.
  Its existence is the evidence: **the most active applied localization engineering in open source is
  happening in APAC, on CJK content, outside the Western TMS tradition entirely.**
  See also `xulihang/BasicCAT` (GPL-2.0, 141★) from the same ecosystem and `dlsandy/Transub` (222★,
  "MIT (Core)", pushed 2026-11-25) for subtitles. ⚠️ `xulihang/ImageTrans-docs` (128★, pushed
  2026-11-21) has **no licence file at all** — 10 filenames probed on both branches against a
  passing control — so default copyright applies and it is readable reference, not reusable code.

**Openings:**

1. **Low-resource and offline MT.** `argos-translate` (MIT) plus `argos-train` (MIT) is the only
   permissive path to a *client-owned, per-language* engine, which matters most where commercial MT
   coverage is thinnest. This is the strongest technical fit of the pass to this region.
2. **Archive-and-verify for public broadcasters** (ABU demand above), wired to the description
   backfill already in this KB as Pattern 31 — translation is the step that makes a multilingual
   archive searchable at all.
3. **The per-jurisdiction policy engine**, reused from pass 8 rather than rebuilt.



#### Pass 15 (2026-11-26) — out-of-home, signage & retail media

**The most digitised region in the world by share, and the one where the market numbers cannot be
trusted to a single figure.** APAC digital is **55.7% of OOH revenue — the highest of any region**
(WOO, via secondary source). Market-size estimates for 2026 **diverge about fourfold**: Mordor
Intelligence puts APAC DOOH at **~US$23.93B** (9.62% CAGR to 2031) while Marketdataforecast puts it at
**~US$6.05B** (11.5% CAGR to 2034). **Never quote a single APAC number** — the spread is the finding.

**Players.** JCDecaux's **VIOOH** SSP expanded to **over 30,000 digital screens** (February 2026).
Also active: Hivestack; **Moving Walls** (Indonesia, Malaysia, Philippines); **CodyOOH** (Hong Kong,
AI audience tracking); Broadsign; **Times Innovative Media** (India). Clear Channel opened a Singapore
network in July 2026, and **NTT DOCOMO launched DOOH in Ho Chi Minh City in April 2026** via a joint
venture. Japan is repeatedly named as an AI-driven DOOH leader, though the supporting statistic found
was weak and is not repeated here as fact.

**Regulation — an explicit, informed gap.** Two targeted searches returned **no concrete APAC
regulatory detail** for camera-based signage measurement. What exists is an industry *initiative* to
harmonise privacy frameworks, measurement protocols and content approval across APAC nations — an
aspiration, not a rule. **The primary sources a client engagement must go to directly: Japan's PPC
(APPI), Singapore's PDPC (PDPA), India's DPDP Act and its rules, and China's PIPL.** This KB has not
verified any of them for DOOH and should not be read as having done so.

**Carried forward from pass 8 of this KB:** a Latham & Watkins analysis (September 2026) found **three
divergent regulatory categories** across APAC. That conclusion holds here and sharpens the
recommendation: for APAC the deliverable is **a per-jurisdiction policy engine**, not a single
compliance mode.

**Opportunity.** Highest digital share plus the most fragmented regulation plus a 4× disagreement about
market size means the buyer's first problem is *not* more screens — it is knowing what they own and
what they may legally measure. A screen inventory and per-jurisdiction policy engine is the wedge.


#### Avails, windowing & distribution rights — pass 16 (2026-11-26)

**The regulatory picture makes a single compliance mode impossible, so the asset is a policy engine per
jurisdiction.** Latham & Watkins (September 2026) finds "a significant acceleration in the enactment of
AI regulation across the Asia-Pacific region" and sorts it into divergent categories: binding,
risk-based frameworks with tiered compliance obligations (**South Korea**, **Vietnam**) versus targeted
AI regulation (**China**). CX Network covers nine APAC countries separately, with **disclosure and
labelling of generative AI** as a recurring theme. For this plane the consequence is concrete: a window
and territory engine for APAC must be **multi-jurisdictional by construction** — one Rego package per
country, not one compliance mode with country flags. That is a design decision worth making on day one,
because retrofitting it is a rewrite.

**No catalogue-composition duty of the AVMSD kind was found in the region from this session.** For media
specifically, an ASEAN policy brief notes that while policymakers recognise the need for regional
cooperation in media regulation, "the progress is slow". ⚠️ Recorded as an **informed gap**: this pass
did not locate an APAC national VOD quota comparable to AVMSD Art. 13 or Brazil's PL 8.889. Several APAC
markets have historically operated local-content rules for broadcast; whether any extends to on-demand
catalogues with a reportable share was **not established** and should be checked per country (Korea,
Australia and Indonesia are the likeliest candidates) before a regional compliance pitch.

**The format that breaks the avails model.** APOS 2026 in Bali frames the year around **AI and
microdrama**, with global streamers, Indian conglomerates, Chinese tech platforms and "a wave of AI and
microdrama upstarts". This matters structurally and is the most distinctive APAC finding in this plane:
**the classical avails model assumes a sequence — theatrical → PVOD → SVOD → FTA — and short-form
vertical microdrama has no such sequence.** An avails schema inherited from Hollywood distribution does
not describe the fastest-growing APAC format at all. A greenfield rights model for short-form is an open
design question in the region with the most volume behind it.

**Scale and the monetisation gap.** Variety reports the Asia-Pacific screen economy racing toward **$200
billion**, with a monetisation gap defining the decade. One market report describes the region as second
only to North America in generative-AI adoption pace, and names **Tencent Video** and **iQIYI** as
investing in generative AI. Public broadcasters in **Australia** and **Singapore** are exploring AI for
newsroom workflows, archiving and verification (ABU). Kantar ranks Google first for consumer ad equity
across APAC, followed by Netflix, YouTube, TikTok and Instagram. Treat the market-research figures as
commercial estimates.

**Opportunity — ranked third, but with the most upside.** Two assets, both design-led rather than
compliance-led: (1) a **per-jurisdiction policy engine** for windows and territories, which the
divergence documented by Latham makes necessary rather than nice; (2) a **rights model for short-form
vertical**, where no incumbent schema fits and the volume is growing fastest. Neither has a deadline
attached, which makes them harder to sell than the EMEA report and more valuable if won.

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

#### The audience & measurement plane — added 2026-11-25 (pass 7). The region where the panel is smallest and the first-party graph therefore wins soonest

- **The measurement incumbency in LATAM is real but thin, and the numbers are the argument.** Nielsen
  IBOPE's streaming panel expansion in **Mexico** took it from **900 to 1,650 households** — against
  Nielsen's **42,000+** in the US (CIMM, January 2026; see the North America section). A national
  currency resting on ~1,650 homes is **statistically fragile for exactly the long-tail, local-language
  inventory a regional broadcaster sells.** That is the opening: a client's own first-party graph, built
  on its own logs, can be more granular about its own audience than the regional currency is — a claim
  that is simply not available in the US.
- **Ownership of the region's measurement changed hands and the brand reverted.** **Kantar Media was
  acquired from the Kantar Group by H.I.G. Capital in August 2025** and is rebranding globally as
  **Fifty5Blue**, while in Latin America it continues to operate under the **Ibope** name (and in
  Argentina as Ibope). **Source caveat: `www.fifty5blue.com` does not resolve from this session**
  (outside the allowed network domains), so this is recorded from trade press, **not** from the
  company. An ownership change at the regional measurement incumbent is a commercial window —
  integration work, re-contracting, methodology review — but **verify the corporate facts before
  citing them.**
- **Cross-media measurement in the region is explicitly at "first step" stage.** Kantar launched a daily
  dashboard combining **broadcast TV and VoD streaming consumption** in Brazil, described by the company
  itself as the **first step** toward cross-media audience measurement in Brazil; **Cross-Platform View**
  was introduced in **Peru in July 2025**; and **Nielsen launched streaming ad measurement within
  Digital Ad Intel in Brazil in August 2026.** The region is therefore buying the capability this plane
  describes *right now*, and nobody has finished building it.
- **The regulation that bites here is automated decisions, and it has become enforceable.** Brazil's
  **ANPD became a fully independent regulatory agency in February 2026**, and **Decrees 12.975 and
  12.976 in force since May 2026** expanded its competence over platforms and user rights. Its stated
  enforcement priorities **explicitly include the use of personal data for advertising**, and its open
  interpretive work includes **LGPD Article 20 — the right to review automated decisions.**
  - **A recommender is an automated decision**, so Article 20 is the provision that lands on the ranking
    layer. This **reinforces, from a second direction, the Brazilian bill already recorded in this
    section** requiring AI-based content *recommendation* systems to surface local, community and
    independent outlets: one obligation requires the ranker to be **explainable**, the other requires it
    to be **steerable**. Both are implemented in the same place.
  - **Build consequence:** the ranking layer must be inspectable and overridable by construction. That
    rules out an opaque hosted recommender and favours `recommenders-team/recommenders` (**MIT**) or
    `RUCAIBox/RecBole` (**MIT**, 90+ algorithms on a common benchmark — the tool for *evidencing* that
    one ranker was chosen over another on measured grounds).
  - **Contested, and recorded as contested:** sources disagree on whether **PL 2338/2023** has become
    law — one states Brazil has no AI-specific statute yet and LGPD governs, others claim enactment in
    December 2025 with phased 2026 implementation. **Not asserted here. Verify against an official
    source before relying on it either way.**
- **Consent is already the practical blocker for measurement tags.** Regional privacy guidance reports
  that firing analytics or advertising tags **before** consent violates the law in **Brazil, Mexico and
  Colombia** — which makes a self-hosted, consent-gated collection layer (`jitsucom/jitsu`, **MIT**;
  `snowplow/snowplow`, **Apache-2.0**) not a preference but a compliance requirement. Note this came
  from commercial guidance, so treat it as orientation.
- **Informed gap:** this pass found **no LATAM-specific source on streaming or CTV *measurement*
  regulation** — the regulatory material that exists is general data protection and AI governance, not
  audience-measurement rules — and **no figure for open-source recommender adoption** by LATAM
  broadcasters. Searched in Spanish and Portuguese; unresearched, not absent.


#### The live & delivery plane — added 2026-11-26 (pass 8). The region with a **live national standard** and the hardest patent problem in this KB

**This is the most consequential LATAM finding in eight passes: Brazil has switched on a next-generation
national broadcast standard, and every codec it mandates is patent-pooled.**

**DTV+ / TV 3.0 — what is verified:**

- A presidential decree signed in **August 2025** created the system. The public signal went live on
  **2026-06-11**, reaching **Rio de Janeiro, São Paulo and the Federal District simultaneously**,
  timed to the **2026 FIFA World Cup**.
- The video stack is **VVC (H.266) with an MPEG-5 LCEVC enhancement layer** — making Brazil, per the
  vendor's own account, the **first country to build a national broadcast standard on a two-layer
  design**.
- **MPEG-H Audio is mandatory**, and the standard requires MPEG-H support **over the HDMI connection
  of every DTV+ receiver**.
- The physical layer **borrows from ATSC 3.0**, including MIMO and Layered Division Multiplexing.
- **Globo** ran the Rio lighthouse station on Harmonic equipment with VVC and LCEVC. **Intelbras** and
  **Aquario** began selling the first compatible receivers and converters, with deliveries from
  **2026-06-08**, so existing TVs can receive the improved signal without replacement.

*Source caveat: much of the above comes from vendor and trade material (V-Nova, IBC, broadcaster
releases). The launch date and the codec mandate are consistently reported across them; performance
claims are not independently verified. This pass found **nothing** on DTV+'s broadband/MPEG-DASH
interactivity side — recorded as an open question, not as an absence.*

**⛔ Why this is the hardest patent problem in this KB.** All three mandated codecs have reference
implementations whose licences **affirmatively refuse to grant patent rights** — read from the files
on 2026-11-26:

| Mandated by DTV+ | Reference implementation | Licence | The clause |
|---|---|---|---|
| VVC (H.266) | https://github.com/fraunhoferhhi/vvenc (enc), https://github.com/fraunhoferhhi/vvdec (dec) | BSD-3-Clause-Clear | "NO EXPRESS OR IMPLIED LICENSES TO ANY PARTY'S PATENT RIGHTS ARE GRANTED BY THIS LICENSE" |
| MPEG-5 LCEVC | https://github.com/v-novaltd/LCEVCdec | The Clear BSD License | same |
| MPEG-H 3D Audio | https://github.com/Fraunhofer-IIS/mpeghdec | Fraunhofer FDK MPEG-H licence | §3 titled **"No PATENT LICENSE"**; licences "may be obtained from the respective patent owners individually and/or under FRAND conditions" |

So a Brazilian broadcaster, receiver maker or systems integrator can legally **compile and ship** the
open reference code and still owe royalties to the VVC, LCEVC and MPEG-H pools. The open source is
not a route around the pool and was never meant to be one.

**And one of the three has no open encoder at all.** `Fraunhofer-IIS/mpeghdec` is a **decoder**
(100★, last push 2026-07-24). There is **no open-source MPEG-H Audio encoder** — while the standard
mandates MPEG-H support in every receiver in the country. Every DTV+ audio encode must therefore go
through commercial equipment. That is a verified, dated, country-sized gap.

**The engagement shapes this creates, in priority order:**

1. **Codec-royalty and conformance advisory for DTV+.** Nobody in the region has mapped which pool
   covers which layer, and the licences themselves point the client at "the respective patent
   owners". This is a CFO-sponsored piece of work with a hard deadline already passed, which means
   the exposure is **accruing now**.
2. **Dual-chain delivery during the transition** — legacy ISDB-Tb alongside DTV+, two encodes, two
   audio paths, receiver-compatibility matrices. The permissive tooling (`shaka-packager`, `gpac`,
   `mp4ff`, `ffmpeg`) covers everything **except** the three codec layers and the DRM key.
3. **Receiver and converter validation** at the Intelbras/Aquario tier, including the mandatory
   MPEG-H-over-HDMI requirement.

**Mexico — the region's other dated regulatory event, and it is media-specific:**

- **2026-05-14:** amendments to the **Federal Copyright Law and Federal Labour Law** were published,
  introducing **the first sector-specific AI regulation in Mexico**.
- **2026-05-22:** the new **Federal Law on Cinema and Audiovisual** was published, extending
  regulatory oversight **for the first time to digital video-on-demand (VOD) platforms**.

A VOD platform operating in Mexico is now inside a licensing regime it was previously outside — and
that is a compliance-reporting and content-metadata build, directly adjacent to this plane.

**Wider LATAM regulatory state.** **No Latin American country has a fully mature, harmonised AI
regime.** **Peru** is furthest along: the regulation of **Law No. 31814** took effect in
**January 2026**. **Deepfakes, synthetic media and identity fraud** are named as rapidly becoming
enforcement priorities — which ties this plane to the provenance work already in Patterns 1 and 8.
Several firms in the region are also tracking the EU AI Act's transparency obligations (applicable
from 2026-08-02) because they reach LATAM operations of multinationals.

**Capability and ecosystem.** **Latam-GPT**, led by Chile's **CENIA** with support from **30+
institutions across eight countries**, is the region's flagship sovereign-model effort. Colombia's
**FLIP** and Argentina's **ADEPA** have researched AI adoption in media while tracking regulation,
and **ADEPA has published a guide for media** recommending platforms, tools and workflows. The
**International Fund for Public Interest Media** supports outlets charting their own AI paths.
Aspen Digital's **January 2026** report records leaders stressing careful adoption with
**human-in-the-loop checks and clear guardrails**.

⚠️ **Low-confidence figure, flagged not promoted:** a LatAm Journalism Review figure cited by Forbes
México says **only 6% of Latin Americans access news through AI tools**, mainly chatbots. Verify
before using it in a deck — it is a striking number and it is third-hand here.

#### Trust & safety and minor protection — added 2026-11-26 (pass 9)

**Brazil has moved from a takedown regime to a design regime, and it is the most demanding
minor-protection law outside the EU. It is also the LATAM engagement most likely to be funded.**

- **ECA Digital is in force.** **Law 15.211/2025** took effect **17 March 2026**, with
  **Decree 12,880/26** (published 18 March 2026, **54 articles**) detailing obligations on
  prevention, protection, age assessment, inappropriate and prohibited content, and parental
  supervision. Scope covers **social networks, games, app stores and operating systems**, reaches
  **services likely to be used by minors**, and applies to **foreign providers**. Enforcement sits
  with the **ANPD**, alongside a new screening centre within the **Federal Police**.
- **What it demands is design, not reaction.** Reported duties include **age verification**,
  stricter moderation, and removal of harmful material involving minors **without a court order** —
  a significant departure from Marco Civil's judicial-order tradition. The law **bans loot boxes** in
  games aimed at or likely accessed by children, and providers advertising to minors must **prevent
  profiling and the use of emotional analysis or AR/XR/VR**. Platforms with **more than one million
  minor users** face extra reporting, reportedly **semiannual data-protection impact reports to the
  ANPD**. Penalties run to warnings and fines **up to ~$10M**, with suspension or banning available
  in severe cases. ⚠️ Sources disagree on the law's number (most say 15.211/2025, one says 15.100)
  and most are compliance-vendor commentary; **no ANPD enforcement action or guidance since March
  surfaced in this pass** — enforcement intensity is therefore **unconfirmed**.
- **The demand signal is measured, and it is large.** A pre-enforcement study found **21 of 25
  services did not verify age at sign-up**. That is not a market forecast; it is a count of
  non-compliant products in the market that each now need the same component built.
- **Nothing region-specific exists to build it with.** No Brazilian or Spanish-language open T&S or
  age-assurance project surfaced. The credible assembly is **ROOST Coop + Osprey** (Apache-2.0) for
  review and rules, **meta/ThreatExchange** (BSD) for hashing, **granite-guardian** or
  **gpt-oss-safeguard** (Apache-2.0) for classification, and the **EU EUPL-1.2/Apache-2.0 age
  estate** for the age signal — none of it written for Brazil, all of it legally reusable there.
  **Portuguese-language safety classification is the specific unmet need**, and it is unmet for the
  same reason pass 8 found: the classifiers worth having are trained on English-language abuse and
  licensed research-only.
- **Why this is a *regional* opportunity and not a Brazilian one.** ECA Digital, the EU's DSA and
  Australia's under-16 regime converge on the same three components — an age signal, a review
  pipeline and a reporting trail. A Brazilian build is therefore **reusable into EMEA and APAC with
  the policy layer swapped**, which is the argument that justifies building rather than buying. It
  also compounds with what this file already records for LATAM: the region's hottest buyer is the
  newsroom, because an organisation that has written a policy has committed to being able to
  **evidence** it.



#### Theatrical & digital cinema — added 2026-11-26 (pass 10)

**The channel.** Gower Street puts **Latin America at $2.65bn for 2026, up 9% on its 2025 estimate
and still 5% below the 2017–2019 average.** The important detail is the composition: **admissions
fell 8% in 2025** while revenue rose, so the growth is **price and premium formats, not attendance.**
LATAM is also named across the sources as one of the Hollywood-driven markets carrying global
growth, and — per an undated SMPTE note — one of the regions **still in transition to SMPTE-DCP**
while North America is largely through it.

**LATAM has the most concrete theatrical compliance calendar on earth, and zero tooling for it.**
This is the sharpest regional finding of the pass. Three instruments, all real, all current:

- **Brazil — screen quota.** **Decree 12.796 of 2025-12-23** makes the exhibition of Brazilian
  feature films mandatory in cinemas nationwide **for the 2026 calendar year**, signed by President
  Lula, with **Ancine** responsible for enforcement and for setting criteria for award-winning or
  broad-audience works. Ancine then published **Instrução Normativa 175** to update the 2026 quota
  rules after finding that **Cinemark had exploited a loophole** in the original framing. A
  compliance obligation that was *already gamed and re-regulated inside one year* is the strongest
  possible signal that the evidence trail is the product.
- **Brazil — accessibility.** Ancine's accessibility obligations for commercial screenings are set
  by **Instrução Normativa nº 165, de 2022**, binding on **both distributors and exhibitors**, with
  Ancine's accessibility good-practice guide published in **July 2026**.
- **Mexico — the new Film and Audiovisual Act.** A new **Federal Film and Audiovisual Law** replaces
  the 1992 framework, retaining the **10% minimum screen time for national films** (Article 19 of the
  1992 law) with **stricter enforcement on exhibitors**, monitored by the Ministry of the Interior,
  and reportedly covering **accessibility for people with visual or hearing impairments**. **Status
  flagged as unconfirmed**: a February 2026 source describes it as a proposal still advancing, a July
  2026 summary describes it as enacted. Verify before a client commitment. This sits alongside the
  Mexican copyright and labour amendments of **2026-05-14** already recorded in this file.

**Note how this closes a loop in this KB.** `intel/market.md` already carried the Brazilian
accessibility phrase *"in all formats in which cinematographic works are presented"* and Mexico's
new cinema law — recorded as *regulatory* intelligence in earlier passes. This pass supplies the
other half: **the tooling that would discharge those duties does not exist.** Open cinema
accessibility code is **one repository with zero stars**, worldwide. The duty was in the KB for
months with nothing to point at.

**Opportunities — LATAM**

1. **The quota-and-accessibility evidence trail (the flagship LATAM build).** One pipeline producing
   two regulator-ready artifacts: a per-screening record proving the Brazilian quota was met under
   IN 175, and a per-title record proving the IN 165 accessibility tracks were present and rendered.
   Built on `ClairMeta` (BSD-3, so the client can own it). Pattern 29 and Pattern 30.
2. **An Interop-and-SMPTE dual-path pipeline.** LATAM is still mid-transition; North American
   pipelines are dropping Interop. A regional distributor needs both for longer than a US one does.
3. **Premium-format yield analytics.** Revenue is rising on falling admissions, which is a pricing
   and format-mix question, and the open box-office estate is 29 stars of 2017–2020 coursework.
4. **Follow the Mexican statute.** If the Act is enacted as summarised, it pairs a 10% screen quota
   with an accessibility duty and *stricter exhibitor enforcement* — the same artifact as the
   Brazilian build, in a second large market, on a different legal basis.

**Informed gap — LATAM.** Brazil's exact 2026 accessibility percentages and audio-description
quotas under IN 165 were **not retrievable** (the Ancine guide is a `.docx` behind a gov.br
download handler); the enactment status of Mexico's Act is **contradicted between sources**. Both
recorded as gaps. No LATAM screen count was verifiable either.

#### Pass 11 (2026-11-26) — the description & semantic-interchange plane

**The finding of this pass for LATAM: the region is not a consumer of this plane's infrastructure —
it built a piece of it.** **TemaTres** (https://github.com/tematres/TemaTres-Vocabulary-Server) is a
SKOS/thesaurus vocabulary server at **142★, pushed 2026-11-25** — the day before this pass — and it
is **Argentine**: copyright Diego Ferreyra, `tematres@r020.com.ar`, GPL-2.0-or-later declared in
`readme.md` and in every source header. It is the **second most-starred controlled-vocabulary server
on GitHub**, behind Finland's Skosmos (269★) and ahead of everything else in the category.

This matters beyond pride. Every prior pass placed LATAM as a *buyer* of open source built elsewhere.
Here a LATAM-origin, two-decade-old, actively maintained tool **is** the regional reference
implementation, and it is the natural anchor for a Spanish-language cataloguing engagement — the
vocabulary layer speaks the client's language because it was written in it. Two caveats to state
honestly: it is **GPL-2.0-or-later** (copyleft, so a hosted-service client must accept that or
contribute back), and its licence is **not in a `LICENSE` file**, so automated SBOM scanning and the
GitHub API both report it as unlicensed. Expect to have to prove the grant to a client's legal team;
the evidence is `readme.md` plus the header of every `.php` file.

**The archival-standards angle is also LATAM-specific.** arXiv **2605.16338** ("Vidya") describes an
LLM + FOSS pipeline for semantic enrichment and archival ingestion reported compliant with
**NOBRADE** (the Brazilian archival description standard) and **ISAD(G)**, explicitly designed for
low-cost deployment on modest hardware in memory institutions — which is the correct shape for the
region's budgets. **No code was found on GitHub under that name** (`vidya archival metadata` = 0
results). Treat it as a design to implement, not a dependency to adopt; and note that a NOBRADE-aware
description pipeline is a genuinely differentiated offer, because nothing open implements it.

**Regulation moved in 2026, and it moved first for media:**
- **Mexico** published amendments to its **copyright and labour laws on 2026-05-14** — reported as
  **the first sector-specific AI regulation in Mexico** — and a new **audiovisual law extended
  regulatory oversight for the first time to digital VOD platforms**. Sector-specific plus
  VOD-in-scope is the combination that creates metadata and labelling duties.
- **Peru**: the regulation of **Law No. 31814 took effect in January 2026**, promoting AI while
  reducing risks across health, education, justice and citizen security.
- No regional model exists; no LATAM country has a fully harmonised AI regime. **Deepfakes, synthetic
  media and identity fraud are becoming enforcement priorities** — which is a provenance-and-
  description demand, not only a moderation one.

**The buyer remains the newsroom, and now there is a reason it can act.** Pass 8 established the
newsroom as LATAM's hottest buyer (FLIP in Colombia, ADEPA in Argentina, SiPreBA, IAPA, Aspen
Digital's "Mind the Gap") because an organisation that has written an AI policy has committed to
evidencing it. This pass supplies what that evidencing actually requires: a controlled vocabulary, a
description schema, and a subject-assignment tool — **TemaTres + ninjs + Annif, all three usable in
Spanish, two of three LATAM- or EU-public-institution maintained.** Latam-GPT (CENIA Chile, 30+
institutions across 8 countries) is the regional model to pair with them. Adoption headroom is real:
only **6% of Latin Americans access news through AI tools**.

#### Pass 12 (2026-11-26) — the sound & immersive-audio plane: **the world's strictest AI-voice law is here, and so is the exposure**

**This is the clearest case in the KB of regulation following industrial concentration.** Mexico
holds, by its own industry council's (CEMID) account, **about 60% of the global Spanish-language
dubbing market**. It is also, as of 2026, the jurisdiction with **the most specific AI-voice statute
in the world**:

- A decree reforming the **Ley Federal del Derecho de Autor** and the **Ley Federal del Trabajo** was
  published in the **DOF on 2026-05-14** and entered into force the following day.
- It requires **express consent and specific remuneration** to use AI to clone the voice or image of
  performers, and introduces **"actor de doblaje"** as a legal category.
- Reporting puts the scope at **7 articles of the LFT and 20 of the LFDA**; the Chamber of Deputies
  approved it in April 2026 by **368 votes**, with PAN and PRI abstaining and calling it ambiguous.
- It is **not a ban**: digitally generated voices remain permitted **with the performer's express
  permission**. Penalty figures reported in the press (up to 40,000 days of salary) appeared in a
  single headline and should be verified against the decree before being quoted.

**The commercial tension is live, not theoretical.** TelevisaUnivision has publicly moved to AI
dubbing for its catalogue; the dubbing industry has been lobbying through 2026 for fiscal incentives
and warning about exclusion from Mexico's audiovisual incentive policy; and in **November 2026** a
dispute surfaced over a Netflix promotional piece allegedly using voice actor Diana Gálvan's voice
without permission. Bloomberg Línea frames the stake as the livelihood of **~10,000 families**.

**Standards:** **Brazil's DTV+** demonstrated **MPEG-H** as a core feature at CES 2026 — so LATAM is
adopting next-generation audio on a different standards track from North America's ATSC 3.0, and a
regional deliverable may need both.

**An honest data gap:** CEMID's market-size figure (reported as "more than USD 60 million") is
inconsistent with a 60% share of global Spanish dubbing, and no published methodology was found. **Do
not use that number in a proposal** — use the share and the regulation, which are better sourced.

**Opportunity for Globant in this region.**
1. **Consent-and-remuneration infrastructure for voice.** Mexico's law creates a *recordkeeping*
   obligation — who consented, to what use, for what payment — that no open tool covers. This is the
   highest-conviction opportunity in this pass, because the statute is in force, the industry is
   concentrated, and the tooling does not exist.
2. **Rights-clean dubbing pipelines**, built so the consent artefact travels with the asset — wiring
   this plane to the identification and provenance planes (p5, p9).
3. **The licence point matters most here**: a studio delivering *finished dubbed audio* to a client
   is explicitly permitted under `fish-speech`'s licence; delivering *the model* on-premises to a
   large broadcaster is not. In the region where dubbing volume is concentrated, that distinction is
   the difference between a compliant engagement and an unlicensed one.

#### Pass 13 (2026-11-26) — the subscription layer: two enacted laws, and the most hostile open-source environment measured

**Mexico has moved first, and it is enacted law, not proposal.** Amendments to the **Federal Copyright
Law (LFDA)** and the **Federal Labour Law (LFT)** were **published on 2026-05-14**, described as
Mexico's first sector-specific AI regulation. A separate **audiovisual law published on 2026-05-22**
introduces regulatory obligations for **VOD platforms** — meaning the platform layer this pass
measures is directly in scope.

**Brazil's fight is over the streaming bill's tax provisions.** Global SVOD services (Netflix,
Amazon, Disney+, HBO Max) are seeking to block parts of a streaming-regulation bill approved in the
Senate, on the basis that it would roughly double their taxation in the country; trade coverage
reports streamers accepting regulation in principle while demanding equal rules across the market.
Separately, Brazil's advertising self-regulator updated its influencer guidance in 2026 to cover
**avatars, virtual profiles and AI-generated content**.

**There is no harmonised regional regime.** No Latin American country has a fully mature,
cross-sector AI framework; Brazil, Argentina, Chile, Colombia and Costa Rica are each advancing their
own, and 15 LAC countries agreed a regional AI roadmap at a UNESCO summit in late 2024.

**⚠️ The finding that is specific to this region, and it is uncomfortable.** The open-source
circumvention ecosystem measured in `agents/top.md` is **disproportionately aimed at the Brazilian
press**. Of the top ten `topic:paywall` repositories by stars, the two largest non-English projects
are **[marreta](https://github.com/manualdousuario/marreta) (GPL-3.0, 1,229★, pushed 2026-11-20)** and
**[burlesco](https://github.com/burlesco/burlesco) (MIT, 948★, pushed 2026-11-22)** — both
Brazilian-Portuguese, both actively maintained *this month*, both built to read paywalled Brazilian
news without subscribing. A LATAM publisher's subscription funnel is under live, popular,
well-maintained attack in a way no other region measured matches. **This is a reason to sell paywall
*resilience* in LATAM, and it is evidence a client can verify in thirty seconds.**

**Players.** Vix (TelevisaUnivision) holds exclusive FIFA World Cup 2026 streaming rights in Mexico
and is investing heavily in originals; Globo announced a free ad-supported **vertical micro-drama
app** in January 2026 to compete with Kwai and TikTok; Netflix has described a microseries strategy
plus more live events for the region. *(One industry claim that online piracy accounts for ~80% of
total economic impact, with ~$2.5bn/year of government losses, comes from a truncated
rights-holder-sourced item and is **not** treated as verified here.)*

**Opportunity for Globant in this region.**
1. **Paywall resilience and circumvention-aware funnel design** — the only region where this is
   demonstrably urgent, and the evidence is public and current.
2. **Mexican VOD-platform compliance** against the 2026-05-22 audiovisual law, wired to the
   entitlement layer rather than bolted onto the front end.
3. **Spanish/Portuguese-language reader-revenue builds on REMP** (MIT) — a European publisher's
   production tooling, not a US SaaS, which matters for both cost and data residency.

#### Localization substrate — added 2026-11-26 (pass 14)

**This is the plane where LATAM's existing industrial advantage and an explicit regional policy ask
line up exactly** — and it is the strongest LATAM argument in this KB that is not about compliance.

**The statutory instrument, now precisely dated.** This section already records Mexico as the
jurisdiction with the most specific AI-voice provisions. The instrument: **amendments to the Federal
Copyright Law and the Federal Labour Law, published 14 May 2026**, reported as the **first
sector-specific AI regulation in Mexico** (Chambers *Media & Entertainment 2026*, Mexico — Trends and
Developments). Cite the instrument and the date, not "Mexico regulates AI voices".

**The regional policy ask that this plane answers directly.** Aspen Digital's January 2026 report
*Mind the Gap: AI and the Future of News in Latin America* argues for experimenting boldly while
**standardising carefully**, and specifically calls for **shared regional AI assets and licensing
frameworks.** That is a request for pooled language infrastructure — which is what a translation
memory and a termbase *are*. Supporting context, all previously recorded here and unchanged: SiPreBA
+ Heinrich Böll (May 2026), FLIP (Colombia) and ADEPA (Argentina) newsroom-adoption research, Uruguay
as the first LATAM signatory of the Council of Europe AI treaty (2025), Chile's Latam-GPT, and the
ITU's *AI Trends in LAC* report.

**The asset nobody is competing for.** LATAM is the centre of global Spanish- and
Portuguese-language dubbing (the frequently-quoted ~60% share of Spanish dubbing remains
**unverified** — no published methodology was found, and this KB should keep saying so). Decades of
that work sit in the dubbing houses' **translation memories and glossaries**. Per §64, there is no
maintained open tooling to read, merge, dedupe or audit a TMX file anywhere in the world. So:

- the region holds the largest Spanish/Portuguese parallel corpora in the industry,
- those corpora are the only multilingual training asset the region owns outright,
- the tool that would consolidate them does not exist in open source,
- and the region's own convening body has just asked for shared regional language assets.

**The terminology point is the specific, buildable version of this.** Spanish is not one target:
es-MX, es-AR, es-CO, es-ES and neutral "español latino" differ in exactly the way a **termbase**
exists to manage. Terminology is also the one tier of this plane with live permissive tooling —
**`gaois/terminologue` (MIT, 76★, pushed 2026-11-24)**. A shared Spanish-variant termbase, built on
MIT code, is a concrete answer to the Aspen ask and is deliverable at a studio's scale.

**Openings:**

1. **Dubbing-house TM consolidation** (Pattern 34) — recover and audit the memory before anyone
   trains on it, and keep the consent artefact travelling with the asset per Pattern 12.1.
2. **The shared es-variant termbase** on `terminologue` (MIT) — small, fundable, and answers a
   published regional request rather than a hypothesis.
3. **Newsroom localization for the Spanish-language press**, reusing Pattern 33's evidencing
   approach: the outlets that wrote AI policies in 2026 now have to demonstrate compliance, and
   translation provenance is part of that evidence.

⚠️ **Keep the licence discipline that this region's buyers cannot absorb:** a dubbing house is not a
large broadcaster and cannot carry an AGPL or BSL surprise. In this plane that means **Pontoon
(BSD-3-Clause) over Traduora (AGPL-3.0)**, **argos-translate (MIT) over LibreTranslate (AGPL-3.0)**,
and **never Texterify** (BSL 1.1, no use grant).



#### Pass 15 (2026-11-26) — out-of-home, signage & retail media

**The least digitised of the four regions, which is precisely the opportunity, and the region with the
most concrete dated event of this pass.** LATAM digital is **~27.7% of 2025 OOH revenue**, against
~36.9% in North America and 55.7% in APAC. **Brazil is the largest market (~45% of regional base-year
revenue)**, with Brazil and Mexico leading. Forecasts diverge badly — one report runs **~US$1.72B
(2025) → ~US$4.86B (2034)**, another puts regional OOH/DOOH at **US$1.33B by 2030** — so use the range
and say it is a range.

**The dated event to build a pitch around.** On **2026-07-20 JCDecaux connected 100% of its DOOH
inventory to programmatic across nine Latin American markets** — including Panama, Costa Rica,
Guatemala and Ecuador — sold through **VIOOH**, which is integrated with **50+ DSPs**. JCDecaux México
and VIOOH also ran a Mazda CX-70 launch campaign in Mexico City. The regional inventory became
programmatically addressable this year; the tooling around it did not.

**Regulation — the most distinctive regime in the world, and an imminent deadline.**
- **São Paulo's Lei Cidade Limpa (2006)** remains among the world's most restrictive outdoor
  advertising laws: its article 18 prohibits outdoor advertising, which pushed signage operators
  indoors and into other Brazilian cities, while **digital panels integrated into bus shelters are
  permitted**. Regulation is **municipal**, so it varies city by city.
- **Brazil's LGPD** enforcement scope continues to expand through updated ANPD guidance in 2026.
- **Chile's Law No. 21,719 — "Chile's GDPR" — becomes fully enforceable in December 2026.** This is a
  hard, dated trigger, now weeks away. It bites **pDOOH audience-extension tactics that use mobile
  IDs**, even though DOOH itself is IP-free.
- Facial recognition on screens is a live regional debate, with facial-recognition boarding trials in
  Rio bus depots foreshadowing contextually triggered advertising under unsettled oversight.

**Claims deliberately NOT asserted.** A reported **midnight curfew on outdoor screens in Chile**
(single market-report mention, uncorroborated) and **Mexican rules on electronic-screen billboards**
(source dated) could not be verified. Recorded as leads; verify against São Paulo, Mexico City and
Santiago municipal ordinances before using either with a client.

**Opportunity.** Chile's December 2026 enforcement date is the most actionable item in this plane
anywhere in the world: a buyer with a compliance deadline weeks away, a measurement design problem
with no open-source answer, and newly programmatic regional inventory. The P15.4 privacy-by-
construction measurement design sells into Chile first and then ports to Brazil under LGPD.


#### Avails, windowing & distribution rights — pass 16 (2026-11-26)

**Brazil is about to become the second jurisdiction in the world with a machine-checkable
catalogue-composition duty, and that is the whole LATAM opportunity in this plane.**

**PL 8.889/2017 — status and terms.** The Chamber of Deputies approved the final text on **2025-11-05**
and sent it to the Senate as **PL 8.889-C/2017**. As reported, it would require a minimum share of
Brazilian titles in streaming catalogues — **~10%, with half from independent producers** — and extend
the **Condecine** levy to VOD, with proposals also reaching content-sharing platforms such as YouTube and
TikTok.

⚠️ **The Condecine rate is disputed across every source consulted and this KB will not assert one.**
Reported figures: **3%** of annual revenue (Protecting Taxpayers), **4%** (The Brazilian Report), and
**6%** of gross revenue with up to **60% creditable** against direct local production spend (FICDC/CCIA);
earlier IIPA analysis cited a 6% ceiling. Senate passage and any 2026 enactment are **unverified** here.
Check the current text and status of PL 8.889-C/2017 on the Senate or Chamber site before any figure
reaches a client. Note also that most available analysis is advocacy: CCIA and IIPA (2026 Special 301)
argue the quota and levy are trade barriers and ask Brazil to drop or reduce them, which is a position,
not a forecast.

**Why this is the same build as EMEA.** A ~10% national-title quota with an independent-producer
sub-share is **the identical computation** to AVMSD Art. 13 with different constants: classify titles by
origin, count per national catalogue, report with an audit trail. P16.2 covers both. A reporter built
for an EU client is re-pointable at a Brazilian one for the cost of a classification ruleset — which is
the strongest cross-regional reuse argument this plane offers.

**Regional regulatory frame.** LATAM broadly follows the EU model (IBA), but no country yet has a fully
mature harmonised AI regime. **Uruguay** became the first in the region to sign the Council of Europe's
Framework Convention on AI (2025). **Chile** has an AI bill before its Congress and hosts **Latam-GPT**,
the first open-source LLM trained on Latin American data. Baker McKenzie tracks emerging AI rules across
the region for multinationals.

**Where the buyer actually is today.** Until PL 8.889 passes, the active LATAM buyer in media AI is the
**newsroom**, not the distributor — a finding this KB established in pass 8 and which holds: IAPA
describes adoption guided by editorial need with strong human oversight; Peru's **El Comercio** adopted a
near-10-page AI guide in early 2026; Colombia's **FLIP** and Argentina's **ADEPA** research adoption
while tracking regulation; **SiPreBA** co-produced a May 2026 report with the Heinrich Böll Foundation;
**IFPIM** launched **CTRL+J** convenings on AI regulation and media sustainability. Distribution-rights
work in LATAM is a *2027 pipeline* contingent on the Senate, not a 2026 sale.

**Opportunity — ranked second, contingent on one vote.** Pre-build the Brazilian variant of the P16.2
reporter now and hold it. If the Senate passes PL 8.889, every VOD service operating in Brazil acquires a
reporting obligation on a statutory clock with no open-source tool to meet it — and the asset is already
written. If it stalls, the same code still serves EU clients, so the downside is bounded. That asymmetry
is the reason to build before the vote rather than after it.

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

## Market size — pass 11 addendum (2026-11-26): the description & cataloguing segment

The plane this pass covers has its own sizing, and it is **the most scope-dependent number in this
KB.** Media Asset Management for 2026, from four firms:

| Source | 2026 size | Forecast | Note |
|---|---|---|---|
| Coherent Market Insights | **$2.39bn** | → $6.47bn by 2033 | Archive & storage management is the **largest segment, 25.8% share in 2026** |
| Fortune Business Insights | **$2.58bn** | → $7.29bn by 2034 | |
| MarkWide Research | **$3.8bn** | → $10.04bn by 2035 | |
| The Business Research Company | **$8.8bn** | — | **3.7× the lowest estimate for the same year** |
| Meticulous Research | — | → $7.23bn by 2035, CAGR 13.9% from 2025 | |

**A 3.7× spread between firms for the same year is the finding, not a detail.** Some count only
media-specific MAM software; others fold in broader digital asset management, services, hardware and
archive storage. **Never quote a single MAM figure to a client without naming the firm and the
scope.** A separate Media Archive Solution report gives CAGR **8.31%** (2025-2032) and notes that
AI-driven automated metadata tagging "revolutionised archive searchability" by enabling frame-accurate
retrieval — which is the benefit statement this plane sells, from a market-research source rather than
a measured study.

What the vendors agree on, and what it means for Globant: Coherent says AI is automating **metadata
tagging, content indexing, quality control and rights management**; Technavio describes the market
"rapidly transitioning from passive archive storage into highly intelligent, automated workflow
orchestration hubs." Both are describing *the judgment layer this pass measured as one repo deep.*
The demand is priced in; the open supply is Annif. That gap is the commercial opportunity, and it is
also the reason not to promise it as off-the-shelf.

## Market size — pass 12 addendum (2026-11-26): AI dubbing, and a 100× scope spread

Pass 11 recorded a 3.7× spread between firms sizing MAM for the same year. This plane is worse, and
the lesson is identical.

| Source | Figure | Scope | Forecast |
|---|---|---|---|
| Intel Market Research | **USD 52m (2026)** | AI *video dubbing* | → USD 620m by 2034, ~31% CAGR |
| Astute Analytica | **USD 600.8m (2025)** | AI dubbing & localization | → USD 8.16bn by 2035, 29.8% CAGR |
| Mordor Intelligence | **USD 750m (2026)** | AI dubbing **for OTT** | → USD 2.45bn by 2031, 26.71% CAGR |
| The Business Research Company | **USD 1.15bn (2025)** | AI dubbing *tools* | → USD 2.56bn by 2030, 17.3% CAGR |
| Mordor Intelligence | **USD 5.29bn (2026)** | GenAI in media **localisation** (broad) | 28.41% CAGR to 2031 |
| Coherent Market Insights | **USD 70.2m (2026)** | *Localization strategies* | → USD 155.2m by 2033, 12.0% CAGR |

**The narrowest and widest 2026 scopes differ by more than 100×.** They are not measuring the same
thing: "dubbing tools", "dubbing for OTT", "localisation" and "GenAI in localisation" are four
different markets wearing similar names. CAGRs are the only thing the firms agree on — **17-31%**.

Two qualifications worth carrying into any pitch:
- **Mordor states that quality differences continue to limit AI dubbing in premium scripted
  programming.** The volume is in catalogue, unscripted and short-form, not in prestige drama.
- **Astute flags the EU AI Act**: by August 2026, user-facing synthetic dubbing must disclose that it
  is artificial. Disclosure is a *feature* of the deliverable, not a legal footnote.

**Regional growth:** Mordor puts APAC fastest at **27.96% CAGR** for AI dubbing in OTT. LATAM's
significance is not growth rate but concentration and regulation — see the LATAM subsection above.

**No usable sizing was found for immersive/next-generation audio as a segment.** Searches returned
adoption evidence (ATSC 3.0 approval 2026-04-14, NBC Atmos deliverables, Brazil DTV+ MPEG-H demos)
but no market figure that separates immersive audio from broader broadcast equipment spend. **Stated
as a gap rather than filled with a proxy number.**

## Market size — pass 13 addendum (2026-11-26): the subscription segment, and why growth has stopped being the story

Treat every figure as a range from a named source, not a number. Sources disagree on scope, and the
disagreement is itself the finding.

| Figure | Source | Scope caveat |
|---|---|---|
| **6.7%** online subscription growth in 2026 | Omdia | Omdia also says the industry is "nearing maturity with growth in single digits" |
| **5%** global OTT growth in 2026 | AlixPartners | Lower than Omdia's; different basket |
| **$10bn/yr** APAC premium streaming by end-2026 | Media Partners Asia | Netflix + Prime Video + Disney+ + HBO Max only — four services, one region |
| **~$200bn** Asia-Pacific screen economy | Variety | Whole screen economy, not subscription — not comparable to the row above |
| **68%** of SVOD households with ≥1 ad-supported service (Mar 2026) | Deloitte | US households; up from 54% a year earlier |
| **~$277bn** global streaming video revenue 2026 | SQ Magazine | ⚠️ **Low-confidence secondary source — do not quote to a client.** Recorded only so a later pass does not rediscover it as new |

**The structural read, which matters more than any single number.** Subscriber *growth* has fallen to
mid-single digits in every credible source, and AlixPartners reports that Netflix and Disney+ now
optimise for **profitability, engagement and ARPU rather than subscriber count**. Deloitte's framing
is the same: as subscription growth slows, ad-supported tiers take the lead, and AlixPartners adds
that hybrid ad–subscription models have expanded reach **but not consistent profits**.

**What that means for where the work is.** When growth stops being the lever, the levers that remain
are **retention, involuntary churn, plan mix and ARPU** — every one of which lives in the layer this
pass measured, and every one of which is unserved by open tooling:

- retention → no open churn system for media (`lifelines` is a statistics library, not a product),
- involuntary churn → no open dunning agent (57 repos, none above 200★),
- plan mix → no open model of ad-tier/paid-tier switching,
- ARPU → no open entitlement schema expressing what a subscriber may actually watch.

The commercial argument writes itself: **the industry's own analysts have named the four levers that
matter in 2026, and the open-source estate implements none of them.**

**Not found, and stated as a gap:** no sizing was located for *subscription-management software* as a
segment within M&E — every figure available sizes the subscription *revenue*, not the spend on the
systems that run it. A later pass should not fill this with an adjacent SaaS-billing TAM figure,
which would be a scope substitution of the kind recorded in the pass-12 addendum.

## Market size — pass 14 addendum (2026-11-26): the localization segment, and the one figure this KB can stand behind

This KB already records media localization at **USD 5.6B (2024) → USD 12.8B (2033), APAC fastest at
12.3% CAGR** (DataIntelo, secondhand) and the AI-dubbing sizing spread of **>100×** across six firms
documented in the pass-12 addendum. Nothing found this pass changes either, and this addendum
deliberately adds **no new vendor TAM figure** — the pass-12 lesson was that "dubbing tools",
"dubbing for OTT", "localisation" and "GenAI in localisation" are four different scopes quoted as one
number, and adding a fifth would repeat the error.

What this pass adds instead is a **supply-side measurement**, which is more defensible than any of
the demand-side forecasts because it was counted rather than projected:

| Layer of the localization stack | Best maintained open option | Stars | Alive? |
|---|---|---|---|
| Job format (XLIFF) | `vslavik/poedit` MIT | 2,061 | Yes — 2026-11-09 |
| Platform / TMS | `WeblateOrg/weblate` GPL-3.0 | 6,185 | Yes — 2026-11-26 |
| MT engine | `argosopentech/argos-translate` MIT | 6,696 | Yes — 2026-11-17 |
| Terminology | `gaois/terminologue` MIT | 76 | Yes — 2026-11-24 |
| Automatic quality | `mjpost/sacrebleu` Apache-2.0 | 1,266 | Yes — 2026-08-20 |
| **Translation memory (TMX)** | `bitextor/bitextor` GPL-3.0 | 302 | **No — 2024-11-11** |
| **Contractual quality (MQM)** | `BYU-TRG-Team/mqm-scorecard` Apache-2.0 | **1** | Barely — 2025-06-11 |
| **Format filters (Okapi)** | — | — | **Not on GitHub at all** |

**Five of eight layers are healthy and permissively licensed. Three are not — and the three are the
client's accumulated asset, the contract the work is judged against, and the converter that feeds the
whole pipeline.** That is a precise, countable statement of where paid engineering is needed, and it
does not depend on anyone's CAGR.

**Not found, and stated as a gap:** no sizing was located for *translation-management software* or
*TMS* as a segment within M&E specifically. Every figure available sizes localization **services**
(what gets spent on translating) rather than the **systems** that route and store it — the same
scope defect recorded for subscription management in the pass-13 addendum. A later pass should not
substitute a general enterprise-TMS or language-services TAM here.

## Market size — pass 15 addendum (2026-11-26): out-of-home, and the one figure to stand behind

**Stand behind this one:** global programmatic DOOH spend was **US$1.339B in 2025**, from the **World
Out of Home Organization** — an industry body publishing a measured figure, with the regional split
that makes it usable (**EMEA US$521M at 9.4% penetration; Germany highest at 31.8%**). It was the only
figure this pass that came with a method and a breakdown.

**Treat everything else as a range.** Global DOOH ad spend for 2026 is given as **">US$33B"** by one
source and **"US$28B"** by another. Regional 2026 figures disagree by up to **4×** (APAC: US$23.93B vs
US$6.05B). A long-range projection of **US$194.67B by 2033** circulates via press release and should
not be repeated to a client.

**The structurally useful number is the digital-share ladder**, because the three sources agree on the
ordering even where they disagree on absolute size:

| Region | Digital share of OOH revenue (2025) | Reading |
|---|---|---|
| APAC | **55.7%** | Most digitised; fragmented regulation |
| North America | **~36.9%** | Most programmatic; measurement standard published |
| LATAM | **~27.7%** | Least digitised — the conversion opportunity |
| EMEA | *not isolated in sources found* | Programmatic penetration measured instead: **9.4%**, Germany 31.8% |

**Retail media is the growth vector and has no open-source layer at all.** In-store DOOH is forecast to
drive **~56% of total DOOH growth 2025–2029**. The open-source implementation of retail media is a
**3-star list of links**. That combination — fastest-growing ad channel, zero open tooling — is the
clearest build-versus-integrate signal in this KB.

## Market size — pass 16 addendum (2026-11-26): the avails & rights-administration segment, and a refusal

**This pass declines to give a market-size figure for the avails and rights-administration segment, and
the refusal is the finding.**

Every credible datum located is about the *media AI* market as a whole, not this segment. The segment's
revenue sits inside privately held vendors (FilmTrack, Whip Media, Rightsline, FADEL) and inside studio
business-affairs cost centres that are not reported separately. No analyst figure for "rights
administration software" was found from this session that could be traced to a primary source, and this
KB has recorded enough laundered market-research numbers to know what an untraceable one is worth.

**What can be stood behind, with its provenance:**

| Figure | Value | Source and caveat |
|---|---|---|
| European works share of EU VOD catalogues | ~30% catalogue, ~25% consumption | Secondary reporting (March 2026 analysis); corroborated in shape by a separate breakdown giving EU 28% + UK 9%. Not Commission data |
| Member States with Art. 13 measures in force | 17 | COM(2024)261, 2020–21 reference period — **primary**, and the most defensible number in this plane |
| Brazilian-title quota proposed in PL 8.889 | ~10%, half independent | Reported; bill passed Chamber 2025-11-05, Senate pending |
| Condecine rate on VOD in PL 8.889 | **Disputed: 3% / 4% / 6%** | Four sources, four figures. Do not quote |
| APAC screen economy | approaching $200B | Variety; regional total, **not** this segment |
| NA share of global AI-in-media market | 33.6%–40.6% | Grand View 2024 / Precedence 2025 generative scope; ranges by scope definition |
| Mid-sized firm AI integration cost | ~$2.4M | Single commercial market report, unverified — recorded only because it recurs |

**The one number that should drive a proposal in this plane is 17, not a market size.** Seventeen member
states with an in-force catalogue-composition duty, a published counting method, and no open-source
implementation is a better qualified-pipeline estimate than any TAM figure available for this segment.

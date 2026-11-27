---
industry: media
region: Global
updated: 2026-11-27
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

#### Development & pre-production — pass 17 (2026-11-26)

- **The federal digital-replica bill is still not law, and the date matters for how it is sold.**
  The **NO FAKES Act** was reintroduced **2026-05-20** as **S.4591** with House companion **H.R. 8915**,
  advanced out of the **Senate Judiciary Committee on a unanimous vote 2026-06-18**, and was placed on
  the Senate Legislative Calendar under General Orders **2026-06-24**. **No floor vote and no enactment
  was found as of this pass.** The 2026 text's main new feature is a **DMCA-style counter-notification
  process** letting users contest takedowns. Preemption is genuinely disputed in the sources: the
  sponsors' own summary says it would preempt *future* state digital-replica laws, while Holland &
  Knight reads Tennessee's ELVIS Act as surviving it. **Sell against the guild agreements, which are in
  force, not against this bill, which is not.**
- **Why that puts the obligation in the production office.** The in-force instrument in NA remains the
  2026 WGA / SAG-AFTRA / DGA agreements requiring informed consent and compensation for digital
  replicas (recorded above). Consent is not created in post — it is created when a performer is booked,
  which means the **deal memo, the call sheet and the day-out-of-days are the system of record**, and
  pass 17 measured that layer as having no permissive maintained base anywhere (73 combined stars across
  eight repositories; see `repos/foundations.md` Tier 3).
- **Opportunity — ranked second for NA, behind exposure control.** A **consent-and-replica ledger wired
  into the booking artefacts** rather than bolted onto delivery: capture at call-sheet time, carry the
  claim through the C2PA layer this KB already has (Pattern 4 / Pattern 8), and produce the per-performer
  evidence trail a guild audit or a NO FAKES claim would demand. It is the same build as the Mexican
  LFT/LFDA obligation in LATAM — **one build, two markets** — and it is a build, because the
  pre-production layer has nothing to integrate with.
- **Honest gap, stated rather than inferred.** California **AB 1836** (deceased personalities' digital
  replicas) and **AB 2602** (contractual replica provisions) were searched for directly in this pass and
  **the query returned nothing on either bill**; their current status is therefore **not verified here**
  and must not be asserted to a client from this file. Next pass should query the California Legislature
  bill pages by number rather than by topic.

#### Book, ebook & scholarly publishing — pass 18, measured 2026-11-26

**Adoption is majority behaviour and the figures are primary.** The BookNet Canada / BISG survey
*AI use across the North American book industry 2026* found **63% of respondents' organizations are
using AI**. Among **university presses (n=32)**, the top uses were administrative/operational
(47%), marketing (44%) and **accessibility (44%)** — with alt-text generation in InDesign given as
a concrete example. **86% reported concern about AI accuracy for consumers**, including difficulty
telling AI-generated from human-made work.

**The regulatory driver is indirect, and its date is genuinely unsettled.** The US has no EAA
equivalent for commercial ebooks. Pressure arrives through **ADA Title II**, which binds state and
local government entities and therefore reaches publishers through **public universities and
libraries** as a procurement condition. Sources conflict on the deadline: BISG's accessibility page
refers to the ADA Title II update as **effective April 2026**, while another source says it takes
effect **26 April 2027** for larger public entities after a one-year extension. **Recorded as
conflicting; verify against the DOJ rule before putting a date in a proposal.** The practical
consequence does not depend on which is right: accessible EPUB is becoming a condition of selling
into the public-sector education market.

**The precedent that sizes a programme:** Elsevier reports that **as of May 2026 it had completed
remediation of over 8,000 of its most widely used ebooks**, adding accessible EPUB files and alt
text. This is the most useful number in the plane — a real backlist programme at a known scale,
better evidence for a bid than any market-size estimate.

**Key open-source players anchored in this region:** **PKP** (Public Knowledge Project, Canada —
`pkp/ojs`, `pkp/omp`, GPL-3.0, both committed within the last three days); **Posit**
(`quarto-dev/quarto-cli`, MIT); **Internet Archive** (`openlibrary`, AGPL-3.0); **Standard Ebooks**
(US volunteer project, GPL-3.0 + CC0 templates); **Pressbooks**, the backbone of open-textbook
publishing in NA higher education (GPL-3.0).

**Opportunity, specific to this region:** the buyer is the **university press and the academic
library**, not the trade publisher, because that is where both the ADA Title II exposure and the
measured 44% accessibility-AI adoption sit. The offer is a **remediation pipeline whose automated
stages are permissive end to end** — `w3c/epubcheck` (BSD-3) + `daisy/ace` (MIT) + an alt-text
generator Globant builds — with `Sigil` (GPL-3.0) for human fix-up, deployed as a separate tool so
no copyleft reaches the client's proprietary code. Pressbooks (GPL-3.0) is the natural integration
target for the open-textbook segment.

**Informed gap:** no primary DOJ source for the ADA Title II date was located in this pass, and the
two secondary dates differ by a year. Flagged rather than resolved.

#### Sports media & live events — pass 19 (2026-11-26). The region **is** the market, and it is the most licence-sensitive

- **The US is 53.9% of the entire global sports media rights market**, up from 46% in 2022
  (SportBusiness Global Media Report 2026). No other segment in this KB is this concentrated in one
  region. The jump is driven chiefly by the **NBA's 11-season agreements with Comcast, Disney and
  Amazon**.
- **Streaming is now the top buyer.** Ampere Analysis expects **Prime Video to rank first** in
  sports-rights spend in 2026, ending DAZN's run as leader in every year since 2018, within a
  streaming total of **$14.2bn** (from $13.2bn in 2025).
- **AI is already on air here.** IBM watsonx supplied commentary at the **Masters and Wimbledon**
  (and was publicly criticized for mispronouncing a player's name); **Fox Sports** built World Cup
  AI agents with Google Cloud. The precedent problem is solved; the quality problem is not.
- **Regulatory gate is contractual, not statutory.** There is no federal AI statute reaching this;
  the operative constraints are the **WGA, SAG-AFTRA and DGA agreements** plus state privacy law
  (CCPA) over fan data. For sports specifically, the labour gate bites on **synthetic commentary and
  synthetic on-air talent**, not on highlight clipping — which is why clipping shipped first.

**Opportunity, specific to this region:** the differentiator here is **licence cleanliness, not
model quality**. US enterprise procurement runs the deepest open-source legal review of any region,
and the default sports-CV tutorial stack is built on **`ultralytics` (AGPL-3.0, 63,769★)** and
**`boxmot` (AGPL-3.0, 8,330★)** — both of which reach a hosted service through AGPL §13. Globant's
offer is a **capability-equivalent permissive stack**: `roboflow/supervision` (MIT, 51,730★) +
`roboflow/trackers` (Apache-2.0) or `tryolabs/norfair` (BSD-3) + `roboflow/sports` (MIT, 5,517★),
with `line/lighthouse` (Apache-2.0) for highlight retrieval. That is a deliverable a general counsel
can approve, and most competitors will arrive carrying AGPL without knowing it.

**Second opportunity:** the **regional sports network** segment is under the most cost pressure in
US media, and the 2027 rights forecast falls (see the pass 19 market addendum). Automated highlight
and overlay production is the one capability that lowers cost per produced hour without touching a
rights payment.

**Informed gap:** no US league or federation was found publishing optical tracking data under an open
licence. `USSoccerFederation/ussf_ssac_23_soccer_gnn` (MIT) shows a federation *can* publish
permissively — it is research code, not a feed.


#### Investigative journalism & source protection — pass 20 (2026-11-26). The region that **builds** this plane, and the one clear build gap

**This plane's institutional core is North American, and it is almost entirely AGPL.** The
**Freedom of the Press Foundation** maintains `securedrop` (3,897★, AGPL-3.0, pushed 2026-11-24),
`dangerzone` (5,858★, AGPL-3.0) and `securedrop-client` (59★, AGPL-3.0); **MuckRock** maintains
`documentcloud` (54★, AGPL-3.0) and `muckrock` (124★, AGPL-3.0); **ICIJ** — headquartered in
Washington, operating globally — maintains `datashare` (784★, AGPL-3.0, pushed the day of
measurement), `extract` (257★, MIT) and `prophecies` (31★, AGPL-3.0). A US engagement in this plane
is therefore an **AGPL operating engagement**, not a licensing one: operate unmodified, build beside.

**Regulatory gate is contractual and state-level, not federal.** Consistent with pass 19's finding
for sport: there is no federal AI statute reaching newsroom practice. What binds instead is state
privacy law over source and audience data, shield-law variation by state, and — for anything touching
talent — the WGA/SAG-AFTRA/DGA agreements already catalogued. For this plane the operative constraint
is evidentiary rather than statutory: **a newsroom must be able to show chain of custody**, and no
statute defines the format, which is precisely why the audit trail is a product rather than a
compliance checkbox.

**Opportunity, specific to this region: the records-access bridge.** The measurement is unambiguous.
`FOIA freedom of information request` returns 19 repositories whose top six hold **35 stars**, five
of six carry **no licence file**, and the most-starred was last pushed **2017-12-11**. The only FOIA
MCP bridge in existence, `morisy/muckrock-mcp` (3★), has **no licence file** and is described by its
own author as "highly experimental, insecure, and unstable" — while MuckRock's actual platform is
healthy and pushed 2026-11-24. US federal and state records work is the highest-volume, most
template-driven task in American journalism, and it has **no licensed, tested agent surface**.
Building one against `okfde/froide` (MIT) or MuckRock's API is small, self-contained and publishable.

**Second opportunity: the licence-cleanliness play, same shape as pass 19.** US enterprise
procurement runs the deepest open-source legal review of any region, and the default investigative
stack a competitor will arrive carrying is AGPL (SecureDrop, Datashare, DocumentCloud). The
capability-equivalent permissive chain exists and is current — `huridocs/uwazi` (MIT, pushed
2026-11-26), `ICIJ/extract` (MIT), `Horizontal-org/Tella-Android` (MIT), `OpenRefine` (BSD-3),
`simonw/datasette` (Apache-2.0) — and Pattern 42 in `compose/patterns.md` is wired entirely from it.

**Informed gap:** no US-specific open fact-checking deployment was found. The one non-trivial open
system, `DEFAME` (Apache-2.0), is from a European research lab and dormant since 2025-09-30.

**Pass 21 (2026-11-26) — the spatial, immersive & volumetric plane.** North America is the revenue
centre of this plane and the sources disagree on by how much: one analyst puts the region at
**36.37% of 2026 XR revenue**, another at **~41% for 2025**. Consumer depth is the more useful
number and it is modest — one 2026 industry report has **48% of US consumers having tried VR but
only 13% of households owning a headset** — so the near-term buyer is enterprise and production, not
consumer reach. AWE USA 2026 (Long Beach) is the region's anchor event, with Snap, Qualcomm and
XREAL as the named hardware actors.

**Regulation: there is effectively none specific to XR.** No federal statute reaches immersive
capture or spatial telemetry. The only identified federal instrument is the **Leadership in Immersive
Technology Act of 2024**, which would establish an Immersive Technology Advisory Panel; its current
legislative status could not be confirmed from available sources and should be treated as
unverified. What binds in practice is state privacy law over biometric-adjacent data — eye tracking,
gaze, hand and body geometry — which is why a US engagement's governance work is a data-minimisation
argument rather than a compliance filing.

**Opportunity, specific to this region: the open delivery gap under a proprietary format.** The
consumer format for spatial video is MV-HEVC, and the first **live** MV-HEVC broadcast encoder
announced in 2026 — SpatialGen, launched at AWE USA — is **proprietary**. Open tooling reaches the
format only through x265's multiview encoder plus an ffmpeg remux, and the GitHub mirror of x265 was
**last pushed 2023-09-11**. Meanwhile the ISO/IEC volumetric codec reference, `mpeg-pcc-tmc2`, is BSD
text that **grants no patent rights** and has **177★**. For a US client that means the capture side
can be assembled from permissive parts and the carriage side cannot: the sellable work is the
**capture-to-controlled-client pipeline** (splats over HTTP into a managed app), with codec licensing
priced explicitly rather than assumed away.

**Second opportunity: the licence-cleanliness play, sharper here than in any other plane.** US
enterprise procurement runs the deepest open-source legal review of any region, and the stack a
competitor will arrive carrying in this plane is **not merely copyleft — it is research-only**. The
default citation, `graphdeco-inria/gaussian-splatting` (24,564★), is usable for research and
evaluation only; `NVlabs/instant-ngp` (17,604★) is non-commercial. The capability-equivalent
permissive chain exists and is current — `gsplat` (Apache-2.0), `brush` (Apache-2.0, pushed
2026-11-23), `supersplat` (MIT), `3dgrut` (Apache-2.0), `colmap` (new BSD), `glTF-Transform` (MIT),
`model-viewer` (Apache-2.0), `OpenXR-SDK` (Apache-2.0) — and Pattern 44 is wired entirely from it.
Being able to say "no copyleft, no research licence, no registration gate" is the differentiator.


**Pass 22 — the podcast plane, and North America is where the missing layer has a price tag.**
The US is the centre of gravity of this business: **$2.9 bn of podcast ad revenue in 2025 inside
$8.4 bn of digital audio, +10.2 % YoY** (IAB/PwC), out of **$9.2 bn globally with ~$6 bn of it in the
US** (Owl & Co., 2025, up from $7.5 bn in 2024). Against that, the open-source ad and measurement
layer is **zero repos** (`audio ad insertion server stars:>=20` → 0, measured 2026-11-26).

- **First opportunity: measurement-of-record, and the standard arrived this year.** IAB Tech Lab
  circulated **Podcast Technical Measurement Guidelines v2.3** in 2026 — downloads, audience and ad
  delivery computed from **server-side log data** — with public comment closing **2026-08-19**.
  Podcast measurement is server-side by necessity: most apps never confirm playback client-side, so
  a download log plus a user-agent corpus *is* the audience figure. Every input to a compliant
  implementation is permissive and open: `opawg/user-agents-v2` (MIT), `opawg/podcast-rss-useragents`
  (MIT, to exclude crawlers), `opawg/podcast-hosts` (MIT), `opawg/podcast-prefixes` (MIT) and
  `skymethod/op3` (MIT, pushed 2026-11-26). **There is no open incumbent.** A certified
  IAB-v2.3-conformant measurement service is a buildable, auditable product and the one piece of
  this plane a US buyer is already being asked about — the trade press reads the Upfront as
  "measurement has not kept pace, because the definitions keep shifting".
- **Second opportunity: the video-podcast fork in the road, and it is an RSS question.** ~**71 % of
  US podcasters now produce video versions**, and Edison's Infinite Dial has **YouTube at 33 % of US
  weekly podcast listeners against Spotify's 26 %** (reported via secondary summaries — treat the
  split as directional). The strategic datapoint is the counter-move: **iHeartRadio is adding video
  through standard RSS feeds and supporting `alternateEnclosure`**, so one feed carries both audio
  and video and the creator keeps hosting their own video (Podnews). `alternateEnclosure` is a
  **CC0** tag in `podcast-namespace`. That makes "keep your catalogue platform-independent while
  shipping video" an implementable engagement rather than a slogan, and it is the opposite of a
  YouTube-first migration.
- **Third: the ad stack itself.** Zero open repos touch podcast DAI. The US is the only region where
  the revenue justifies building one, and the signalling inputs are free. See Pattern 47.
- **Informed gap.** Searches for **US regulation of AI-generated podcast audio** returned nothing
  podcast-specific — no disclosure rule, no FTC action on synthetic hosts surfaced. The nearest hook
  is **industry guidance, not law**: the IAB's early-2026 framework recommends a **spoken disclosure
  adjacent to AI-generated segments**. Written down as a gap: a US client asking "must we disclose
  our AI host?" has a *reputational* answer today, not a statutory one — unlike EMEA (below).

- **The picture desk is where AI policy has actually bitten, and the rule has an undefined term in
  it.** AP's newsroom standards still **bar generative AI from creating, altering or enhancing news
  photography**, and additionally require disclosure whenever generative AI plays a **"material"
  role** in published content. The reporting on the July 2026 update notes that **"material" is not
  defined**, leaving it to editorial judgment. Getty Images runs the same policy on the supply side:
  it **does not accept generative-AI visuals in its Creative or Editorial libraries** at all.
  **Opportunity:** the artefact nobody sells is a *materiality record* — per asset, what model
  touched it, at which pipeline stage, and which editor accepted that it stayed below the disclosure
  threshold. `exiftool` writes it, `c2patool` signs it, and the whole open field for the workflow
  around it is one repo with one star (`agents/trending.md` pass 23).
- **Capture-side provenance is already shipping in North American channels, with a lock-in twist.**
  Leica (M11-P, and now the SL3-S) signs at capture with a dedicated secure chip; **Nikon's
  Authenticity Service** adds Content Credentials on select bodies but **requires registration with
  Nikon Imaging Cloud**; Sony enabled it by firmware on pro bodies including the A1 and A7S III.
  The twist worth knowing before a proposal: for Sony, a valid C2PA certificate alone does not prove
  a Sony camera took the picture — the image must carry **both** the certificate and Sony's
  proprietary authenticity signature, and that combination **can only be validated in Sony Ci Media
  Cloud**. **So the open standard has a vendor-validated tier sitting on top of it.** A client told
  "we are C2PA compliant" may still be unable to verify their own archive without a vendor cloud.
  One secondary source (Wikipedia, mid-2026) further claims Leica, Nikon and Canon **do not
  participate in the official C2PA Conformance Program**; unverified against the C2PA site and
  recorded as a claim, not a fact.
- **The training-rights question is still open in the US, and the UK ruling does not settle it.**
  Getty's US action against Stability AI continues and Getty has said it will carry findings of fact
  from the UK judgment into it. North America is therefore the region where an image-rights posture
  has to be defensible **without** a controlling precedent.
- **Informed gap.** Searches for a **US federal rule on AI-generated or AI-altered images in news**
  returned nothing statutory — no disclosure mandate, no labeling requirement for still images. The
  binding constraints in this region are **editorial policy (AP, Getty), contract, and the 2026
  guild agreements**, not image law. A US client asking "must we label an AI-retouched photo?" has a
  **policy and contractual** answer, not a legal one — the opposite of APAC (below), and this is the
  sharpest regional contrast in the plane.

#### The owned-channel & audience-relationship plane — added 2026-11-26 (pass 24). The region that decided first-party data is structural, and the only region where UID2 is real

- **The demand signal is a survey, not a vendor claim.** The **April 2026 IAB survey of 109 US
  publishers** found news publishers prioritising **subscriptions, attribution and direct audience
  ownership**, while large publishers scale **licensing and third-party distribution** instead. Two
  different strategies in one region, and they need different builds: the first needs this plane, the
  second needs pass 5's rights-reservation plane.
- **The framing has hardened.** AdExchanger's position is that AI **settled** the third-party-cookie
  debate — first-party data is now structurally necessary rather than a hedge. The Alliance for
  Audited Media (July 2026) describes audience data as **strategic assets to be protected, managed and
  monetised**. eMarketer now calls newsletters **"first-party media"** — an inventory class.
- **Where publishers say they already use AI:** ad sales, subscriptions and data analytics (Piano
  research) — i.e. the *commercial* stack, not the editorial one. That is this plane.
- **The buy-side complaint is the opening.** At an IAB roundtable, a Prudential buyer said the **lack
  of first-party data from AI platforms** is what holds back budget flowing to LLM surfaces. A
  publisher with a provable reachable audience is selling into a measurement vacuum.
- **Opportunity 1 — the reachable-audience number (Pattern 24.1).** Deliver *reachable audience / total
  audience*, split by channel and legal basis, refreshed daily, on Unomi + Kratos + Novu (all
  permissive). No US client currently has this number, and it is the business case for everything else
  in the plane.
- **Opportunity 2 — UID2, and this is the only region where it is a real conversation.**
  `IABTechLab/uid2-operator` is **Apache-2.0, 18 stars, pushed 2026-11-26**. The operator model is
  North American in origin (The Trade Desk) and adoption is NA-led: **1,000+ publisher and technology
  partners** per The Trade Desk's own disclosures (mid-2025; **no 2026 primary figure found**). Public
  operators never materialised — Prebid.org **paused** its integration and participants run **private**
  operators over their own users' emails. **So the engagement is not "install UID2", it is "decide
  whether the client will hold other parties' hashed emails, and under what indemnity."**
  Governance reporting conflicts (Prebid.org independent governance vs AdExchanger reporting Prebid
  stepping back) — **verify against a primary source before advising.**
- **Opportunity 3 — deliverability evidence (Pattern 24.3)**, which lands hardest here because Gmail
  and Apple Mail are the duopoly of the US inbox and both have changed the rules: Postmaster Tools v2
  replaced reputation scores with a compliance checklist and deliverability verdict; Apple Mail writes
  **pre-open** summaries that overwrite the preheader; Gmail's Gemini summaries appear to **auto-open**
  messages. `parsedmarc` (Apache-2.0, 1,321★) is the open way to own that evidence.
- **Legal posture: contract and policy, not statute.** The live matter is **Penske Media** (Rolling
  Stone, Billboard, Variety) suing Google over AI Overviews — the first major US publisher action of
  its kind. On the channel itself the baseline is CAN-SPAM plus state privacy regimes, which is why the
  **GPP** multi-jurisdiction string matters more here than TCF.
- **Informed gap.** Searches for a **US federal rule governing consent capture or newsletter
  operations for publishers** returned nothing statutory in 2026 — no federal consent framework, no
  publisher-specific duty. The binding constraints are **state privacy law, platform policy (Gmail,
  Apple) and contract.** A US client asking "what must our consent banner say?" has a **fifty-state
  and two-platform** answer, not a federal one — the inverse of EMEA below, and the reason the
  consent object in Pattern 24.4 must be configurable rather than correct.
- **Market share note:** North America holds **~40% of the newsletter-software market** (Verified
  Market Research) — the largest regional share in the plane. See the pass 24 market-size addendum,
  including why that figure sizes *tooling* and not publisher revenue.



#### The traffic, sales-order-to-air & billing plane — added 2026-11-26 (pass 25). The region where this plane *is* the business, and where political advertising makes it urgent

> Non-repo facts in this block come from web-search extracts; the publisher domains were **outside
> this session's allowed network domains**, so URLs could not be opened. Attributed, not independently
> confirmed — marked **†**.

- **The incumbent core is North American and named.** A third-party build-vs-buy analysis calls
  **WideOrbit and Marketron "the backbone of American broadcast traffic"**, alongside **Imagine
  Communications** (LandmarkOSI traffic and billing, xG Linear for MVPD, GamePlan ad decisioning) and
  **Operative** (AOS order management).† There is **no open-source alternative** to any of them — see
  the measured zeros in `verticals/solutions.md` pass 25.
- **The same analysis states the engagement shape for us:** groups should **keep the core traffic
  system and build a cross-platform order and reconciliation layer around it.**† Written by someone
  with no stake in our proposal, and it describes exactly the layer that has no open implementation.
- **Consolidation is the opening.** Imagine Communications was reported **acquired by Lumine Group on
  2026-07-01** (single secondary source — **verify first**), and its CEO conceded in February 2026
  that *"we set ambitious expectations that our delivery didn't fully meet."*† WideOrbit is pushing
  customers from **CapEx to subscription OpEx**.† Platform transitions are when reconciliation layers
  get funded.
- **Opportunity 1 — the as-run reconciliation service (Pattern 25.1).** The highest-value unbuilt
  thing in the plane: `broadcast as-run reconciliation` returns **zero** GitHub repos, and the only
  as-run artefact in existence is unlicensed and dead since 2016. Spot-level matching of the intended
  log against the playout as-run log, emitting *aired as booked / aired wrong / not aired*. Client-owned,
  permissively licensable, and it is what the invoice depends on.
- **Opportunity 2 — the makegood engine (Pattern 25.2).** `makegood` has **zero hits** in this entire
  KB and **zero inside 9eye's own codebase**. Every US broadcaster owes makegoods on pre-empted spots
  and settles them in spreadsheets or in the incumbent's rigid module.
- **Opportunity 3 — the political-spot compliance gate, and it is sharper here than anywhere.** At
  least **31 states** regulate AI in political advertising and **only about half** require disclosure;
  meanwhile federal **reasonable-access** rules mean a station **cannot censor a federal candidate's
  ad**, so a state law prescribing disclosure wording collides with federal law on the same spot.†
  Counsel's advice is to **preserve rather than strip** provenance metadata and signatures through
  editing and publishing.† The logic therefore cannot live in the creative — it must live in **booking
  and the log**, configured **per station and per state**. See Pattern 25.4.
- **Legal posture: state law, FCC and the FTC — not a federal AI statute.** **Informed gap:** searches
  for a federal AI-disclosure mandate for advertising found **none in force** — efforts have stalled in
  Congress and at the FEC, which **lacks a quorum**. The **FTC** is the active federal enforcer,
  focused on AI-washing and undisclosed AI-generated endorsements (a "double disclosure" where a paid
  relationship and AI generation coincide).† **A US client asking "what must we disclose?" has a
  fifty-state + FCC + FTC answer, not a federal one** — which is the same shape as pass 24's consent
  finding and the reason the policy object in Pattern 25.4 must be configurable rather than correct.
- **Unverifiable claim flagged:** sources conflict on New York's synthetic-performer law (signed
  December 2025 and effective 2026-06-09 then repealed/replaced in May 2026, versus signed January
  2026). **Do not cite New York specifics without reading the statute.†**

#### Pass 26 addendum (2026-11-26) — the energy & carbon plane: studio-led, unregulated, and free at the point of use

- **There is no federal mandate, and that is the whole character of the region.** Unlike EMEA, nothing
  in North America compels a production to measure its footprint. The driver is studio procurement: the
  **Sustainable Entertainment Alliance** (the major studios; note the KB correction — "Sustainable
  Production Alliance" is the former name) publishes the **Green Production Guide** and the **PEAR**
  carbon calculator, **free for US productions**, covering the US and Canada.
- **Opportunity — the voluntary-disclosure asymmetry.** Because nothing is mandatory, nothing is
  standardised, and a studio cannot compare two suppliers' numbers. The sellable artefact is a
  **comparable, auditable footprint per production** that survives a procurement review: PEAR-shaped
  output, with the underlying per-asset data retained by the client. No open implementation competes —
  `film production carbon footprint` returns **0 repositories**.
- **Opportunity — the render farm, which is where the region's emissions actually are.** North America
  hosts the heaviest concentration of VFX, animation and cloud-render capacity in the industry, and the
  entire open-source surface for it is **one MIT plugin with 3 stars**
  ([BreakTools/deadline-energy-cost-calculator](https://github.com/BreakTools/deadline-energy-cost-calculator)).
  Deadline is standard in these facilities. Pattern 26.2 is a North America-first build for this reason.
- **Opportunity — the AI-workload line item.** The region's studios are also its largest GenAI adopters,
  and the only measurement tool with real adoption is [codecarbon](https://github.com/mlco2/codecarbon)
  (MIT, 1,955★). Attaching an energy figure to an AI-assisted sequence is unbuilt everywhere and most
  valuable where the AI spend is largest.
- **⚠️ Informed gap.** No AI-adoption statistics for North American media *production sustainability*
  were found, and the Green Production Guide shows **no sign of AI-specific standards**. Searched:
  `AI media sustainability North America 2026 adoption Green Production Guide Sustainable Production
  Alliance`. The trade-body surveys that would settle it are not public. **Treat regional AI-adoption
  figures as unresearched, not as zero.**


#### The production-finance & soft-money plane — added 2026-11-26 (pass 27). The region where the *federal* layer is a live legislative question and the state layer is the product

- **Section 181 expired on 2025-12-31 and has not been reinstated** — reported as still unreinstated as
  of September 2026. It allowed an immediate deduction of up to **$15M** of production cost ($20M in
  designated distressed areas). Its lapse is why the federal conversation reopened at all, and why a
  2026 engagement cannot assume it in a model.
- **Two federal vehicles are in play, and they are different instruments.** The **CREATE Act**,
  announced 2026-08-01 with four bipartisan sponsors, would extend Section 181 (a *deduction*) through
  2030. Separately, a **bipartisan bill reported 2026-10-06 would create a transferable federal tax
  credit of up to 30%** for qualifying US productions — described as **uncapped**, which would favour
  productions with large US labour costs far more than §181 ever did. A *transferable* credit implies a
  secondary market, a buyer-side diligence problem, and a per-claim evidence burden — all three are
  software problems, and the only GitHub repo touching the credit **buyer** side is 0★ and unlicensed.
- ⚠️ **Verification state, stated plainly.** These are trade-press, law-firm-newsletter and tax-guide
  readings, not bill text. A reported presidential endorsement (2026-08-31) appeared in a **single
  low-quality source** and should not be quoted. Commentators split on whether anything attaches to a
  year-end 2026 extenders package or slips to 2027. **Do not build a client business case on the
  federal credit existing**; build it on the state layer, which is enacted.
- **The state layer is the real market and it is large and fragmented: incentives in 39 states plus
  DC and Puerto Rico.** California more than doubled its programme from **$330M to $750M** in July
  2025, and a **standalone post-production credit was signed 2026-09-19** (effective 2027) — the
  state's first. ⚠️ Sources disagree on the bill number (AB vs. SB 2319) and on the post rate
  (35–50%); a further proposal to raise the main programme to **$1B** is a proposal, not law.
- **Canada moved on administration, not just rates**, and administration is where the software lives:
  **BC**'s 2026 motion-picture credit changes became official **2026-04-16** (Production Services Tax
  Credit plus a new **Major Production Tax Credit**); **Manitoba** announced **mandatory
  pre-certification**; **Ontario** proposed restricting OCASE eligibility to film and television
  producers only. Pre-certification and narrowed eligibility both convert a finance question into a
  **documentation workflow with a deadline** — the exact shape Pattern 27.1 and 27.5 address.
- **The opportunity, placed.** North America is the only region where a single production routinely
  claims against **two or three jurisdictions with different qualifying-spend definitions** and where
  credits are **transferable and therefore traded**. The buyer-side diligence pack — does this claim
  survive audit, at what discount — has **no open-source tooling at all** (`film tax credit` = 7 repos,
  the one buyer-side repo 0★/unlicensed), and PolicyEngine has already proven the 50-state
  rules-as-code pattern for a different statute. That is the most directly fundable build in the plane.

#### The age-rating & child-audience plane — added 2026-11-26 (pass 28). The region with the most statutory motion and the least classification infrastructure

**What moved in 2026, and it is privacy law doing the work rather than classification law:**

- **The FTC's amended COPPA rule carries a compliance date of 2026-04-22** — the first major overhaul
  of the rule in more than a decade, tightening notice and parental-consent standards and extending
  coverage to biometrics and government identifiers. Reported consistently across several practice
  summaries; **one secondary source states it requires separate parental consent before children's
  data is used for AI training — treat that specific claim as unverified** against the FTC text.
- **Federal legislation is unfinished.** The House Energy and Commerce Committee advanced the
  **KIDS Act (H.R. 7757)** and **COPPA 2.0 (H.R. 6291)**; the Senate passed its own **COPPA 2.0
  (S. 836)**. The chambers diverge on the strength of the protections, so **do not plan a client
  roadmap around a federal standard landing in 2026.**
- **State AI-companion law is already in force: California SB 243 took effect 2026-01-01** (AI
  disclosure, restrictions on sexually explicit content for minors, crisis protocols); New York
  passed its own AI-companion law at the end of 2025.
- **The AI-content-in-kids-catalogues fight is live:** over 200 organisations have asked YouTube to
  ban AI-generated content from YouTube Kids, and COPPA's "Made for Kids" designation applies whether
  the content is AI-generated or not.

**The structural gap, and it is the sellable one.** North America regulates the **child's data** hard
and the **content's classification** barely at all — MPA ratings remain a voluntary industry scheme,
and there is **no open client for ESRB submission**. Meanwhile the one dataset that models the US
ladder, MovieLabs' `US_MPAA_Ratings.xml`, **has not been validated since 2013-09-28**. So a US
streamer faces a strict consent-and-data regime layered on top of a classification layer that is
voluntary, undocumented in code and stale in every open dataset.

**Opportunity (NA):** a **kids-catalogue compliance pipeline** — "Made for Kids" determination
evidence, per-title descriptor records, AI-provenance flags on children's content, and the consent
artefacts the amended COPPA rule now expects — delivered as an auditable record rather than a UI
badge. The buyer is a platform with a children's tier and an April deadline. Pair it with the
C2PA/consent-ledger work already recorded in this region from the digital-replica plane: it is the
same evidence-pack shape, and the same buyer.

⚠️ **Channel note:** `ESRB API` returns **zero relevant repositories** (all IGDB/RAWG hobby
projects). There is no open integration to ESRB. Do not promise one.

#### The interactive, branching & playable-story plane — added 2026-11-26 (pass 29). **The region that abandoned the format and is now buying the capability back through gaming**

This is the region where the format died commercially. Netflix removed most interactive titles on
**2024-12-01** and the last two on **2025-05-12**, saying the interactive-TV technology "served its
purpose, but is now limiting", and pivoting to games. Branching fiction survived inside *Netflix
Stories* as **downloaded games**, not as streamed video, and some Bear Grylls interactive specials
were re-released as **linear** cut-downs.

What the region is buying instead, measured:

- **Interactive is an M&A thesis, not a programming slate.** Chambers' 2026 New York guide reports
  that strategic buyers now prioritise deals that **bridge premium IP with interactive ecosystems —
  gaming, creator platforms and proprietary ad-tech**. The capability is being acquired, not
  commissioned.
- **Board-level AI money with a frontline gap.** Grant Thornton's 2026 survey of 950 leaders found
  **87% of M&E boards have approved major AI investments**, while **54%** say the frontline — writers,
  editors, production staff — is where adoption most urgently needs support. Regulatory uncertainty
  registers at only **34%**, the sector being more lightly regulated than banking or insurance.
  Forrester's North America spotlight finds firms "bullish on genAI but bogged down in early
  experimentation".
- **The one scheduled mass-participation event.** PwC flags the **2026 World Cup in North America**
  as likely among the longest shared-reality experiences in history — the region's clearest near-term
  demand for second-screen and participatory formats, and the layer with **2 repositories in all of
  open source**.

**The structural gap, and it is the sellable one.** North America has the IP, the buyers and the
budget, and no runtime: there is no interactive-video standard in HLS or DASH, the only open players
are `OpenFMV` (MIT, 241★) and a `Bandersnatch` reimplementation (MIT, 255★), and
`second screen companion tv` returns **2 repositories, both 0★**. Every participatory experience in
this region is bespoke today.

**Opportunity (NA):** the **narrative-QA and branch-coverage service** — a branching story treated as
a graph with a test suite: unreachable nodes, dead ends, contradictory state, and a signed-off
coverage report per release. `chaoz23/inkcheck` (MIT, 2★) proves the shape; the buyer is a studio or
publisher whose writers room is the stated adoption bottleneck (54%), and the artefact is the thing a
showrunner can approve. Sell it against the 87% board mandate, not as an interactive-video revival.
Pair it with the digital-replica consent work already recorded in this region: same buyer, same
evidence-pack shape.

⚠️ **Channel note:** do not open a North American conversation with "interactive video for
streaming". The region's largest buyer exited the category publicly, and the client will know.


### Pass 30 (2026-11-26) — the answer-engine discovery layer in North America

The region where the referral collapse is **measured hardest, disputed loudest, and now litigated.**

| Finding | Source |
|---|---|
| Search referrals over two years: **−60% small / −47% medium / −22% large** publishers ("small" = <10,000 daily page views) | Chartbeat, via Axios 2026-03-17 |
| **US decline −38%**, against Europe's −17% | Press Gazette |
| **ChatGPT = 0.02% of total referral traffic**; all AI platforms ≈1% | Reuters Institute; Conductor |
| **Search Console generative-AI reports** launched **2026-06-03**, worldwide; impressions only, data from **2026-05-18**, no backfill | Google Search blog |
| Penske Media (Rolling Stone, Variety, Billboard) suing Google over AI Overviews | *recorded earlier in this file* |
| Google rejects the causality as *"flawed methodologies, isolated examples, or traffic changes that occurred prior to the roll out"* | Google |

**The region-specific structural fact:** North America is where the *instrument* and the *dispute*
coexist. Google's own Search Console gen-AI reports are the only authoritative record of appearing
inside an AI answer — and they report **impressions and not clicks**, from a start date of
2026-05-18 with **no historical backfill**. So in the one jurisdiction where publishers are suing
over the harm, **no party can reconstruct its own pre-AI baseline from the official instrument.** The
baseline has to be built from the publisher's own server logs, which most publishers either discard
on a short retention window or never parsed by crawler identity.

The gradient reading for NA: the region leads on **readability** tooling (MarkItDown MIT 198,609★ is
Microsoft's; the heavyweight permissive stack is substantially North American) and has **nothing** on
settlement — the pay-per-crawl zero pass 5 measured is a North American zero.

**Opportunity (NA):** the **litigation-grade referral baseline** — a defensible, documented
reconstruction of a publisher's pre- and post-AI inbound position, built from **server and CDN logs**
(`goaccess` MIT + `monperrus/crawler-user-agents` MIT) rather than from any vendor's dashboard, with
the methodology written to survive challenge: retention window, crawler-identity method, verified vs
spoofed user agents, and an explicit statement of what cannot be measured. The buyer is a publisher
whose counsel needs numbers that Google's stated objection does not dissolve, and the deliverable is
the methodology document as much as the figures. Two reasons this sells here and nowhere else:
Google has **publicly pre-committed to attacking methodology**, which makes a rigorous one an asset;
and log retention is an **engineering** problem Globant can fix in weeks. Secondary, same buyer:
extend retention and start the crawler-identity ledger **now**, because the official instrument has
no backfill and every week undocumented is a week unrecoverable.

### Pass 31 (2026-11-27) — the live-event & show-control layer in North America

**The region that writes the standards code, and the region where the AI is still in patent filings.**

| Finding | Detail | Source quality |
|---|---|---|
| **The plane's permissive standards layer is maintained from the US** | Electronic Theatre Controls (Wisconsin) publishes Apache-2.0 reference implementations of ANSI E1.31 (sACN, 44★), E1.33 (RDMnet, 56★), E1.20 (RDM, 11★) and EtcPal (21★) — and marks every non-standards tool it publishes **"UNOFFICIAL"** | **Measured directly** via the GitHub search API, 2026-11-27 |
| **Theme-park AI is at the filing stage, not the shipping stage** | Disney filed two patent applications in **August 2026**: ML monitoring performers to adjust animatronic responses, and ML for attraction maintenance | Trade press reporting on USPTO filings — **filings are not products; do not present these as deployed** |
| **Venue operations is where AI is actually live** | AEG's O2 Arena runs AI cameras + IoT sensors feeding live foot-traffic heat maps | Vendor/trade case study |
| **Ticketing is consolidating on AI** | Live Nation has indicated nearly all new Ticketmaster features in development use AI, concentrated on venue value-added services and customer experience | Secondary summary, **not** Live Nation filings — attribute accordingly |
| **The labour frame carried from pass 37 of `intel/trends.md` applies here too** | This plane is governed by collective agreements (IATSE-class crew terms) rather than an AI statute. A show-control agent touching crew scheduling or performer tracking (PosiStageNet) is a **bargaining** question before it is a technical one | Structural inference from this KB's pass-19 and pass-37 findings |

**The opportunity, and it is narrow and real:** the standards layer is permissive, maintained, and
**tiny** (44–56 stars). An agent that can read a rig's RDMnet inventory and reason about it has no
competitor, and the dependency is Apache-2.0 from the market-leading manufacturer. Sell **rig-aware
diagnostics and documentation**, not creative lighting design — the former is an inventory problem
with a permissive substrate, the latter is a designer's craft and a labour question.


### Pass 32 (2026-11-27) — the device, TV-app & client-playback layer in North America

**The regulatory position is the opportunity, and it is unusually legible: the US is the only region
whose next-generation TV transition has no date, and its single open broadcast-app artefact has been
dormant for four years.**

| Finding | Detail | Source quality |
|---|---|---|
| **The ATSC 3.0 transition has no deadline** | The FCC adopted a Further NPRM in late October 2025 proposing to end the ATSC 1.0 simulcast requirement. As reported, the proposed rules set **no ATSC 1.0 cutoff date and no ATSC 3.0 tuner mandate** | Federal Register + ATSC + trade press; **the FCC had not finalised rules when checked — verify GN Docket 16-142 before quoting** |
| **The largest station groups are lobbying for one** | **Gray Media, Sinclair, Nexstar and Scripps** filed in January 2026 asking the FCC to set an ATSC 1.0 end date **and mandate 3.0 tuners in new TVs**. NAB's earlier petition proposed **February 2028** for the top 55 markets and **February 2030** elsewhere | Trade press + FCC docket |
| **Must-carry is unresolved** | NAB wants cable/satellite to carry ATSC 3.0 signals; the FCC has set no deadline | Trade press |
| **The consumer base cannot receive it** | Commissioner Anna Gomez noted NextGen TV **is not backward compatible**, **most TVs sold in the US cannot receive it**, and there is **no federal funding** for consumer education. Lawmakers wrote to the Chairman on **2026-03-27** urging a firm plan | FCC statement + House letter — primary |
| **Simulcast obligation near-term** | One consumer guide states stations offering 3.0 must simulcast in 1.0 **through at least 2027-07-17** | ⚠️ Consumer guide only — **not verified against FCC rules** |
| **Device share: the two readings of the same analyst conflict** | Parks Associates is reported both as **Roku OS 28% / Tizen 23%** (US, April 2026) **and** as **Tizen 36% / Roku 17%** ("most-used", Q1 2026) | ⚠️ **Two secondary readings of one analyst that contradict each other.** Do not quote either — the metrics mix installed base, shipments and "most-used" |
| **Region weight** | North America ~**31%** of the global smart-TV market (2026); leads AI-in-M&E with **33.6%** share (2024, Grand View) | Vendor estimates — directional |
| **Regulation touching the app layer** | California **AI Transparency Act (SB 942)** delayed to **2026-08-02**; federal **Take It Down Act** compliance deadline **2026-05-19** | Law-firm guides — verify against statute |

**The strategic read, and it is the sharpest supply-side gap in this pass.** The United States runs
on **Roku OS and Samsung Tizen**, and **neither has an open platform**. The entire open Roku surface
is a volunteer community toolchain — [`brighterscript`](https://github.com/rokucommunity/brighterscript)
(MIT, 212★), [`roku-deploy`](https://github.com/rokucommunity/roku-deploy) (MIT, 60★),
[`roku-debug`](https://github.com/rokucommunity/roku-debug) (MIT, 19★),
[`vscode-brightscript-language`](https://github.com/rokucommunity/vscode-brightscript-language)
(MIT, 132★) — **~423 stars, no vendor backing, all pushed within a week of this pass.** For Tizen
there is only [`Samsung/Wits`](https://github.com/Samsung/Wits) (Apache-2.0, 125★).

And the region's only open broadcast-application artefact,
[`openBA-NextGenTV/OpenBA-NextGenTV`](https://github.com/openBA-NextGenTV/OpenBA-NextGenTV)
(**MIT**, 15★) — Sinclair's own open-sourced ATSC 3.0 app — **has not been pushed since
2022-09-21**. So the broadcasters petitioning for a mandatory transition have, between them, one
MIT reference application that is four years cold.

**Two deliverables that follow directly.** (1) **A Roku/Tizen certification-and-submission
practice**: the platforms that matter most in NA are the two with the least open tooling, and
pattern 32.1's BSD-3 harness plus the RokuCommunity toolchain is the only licence-clean route —
noting that the WAVE verdict component is **Commons-Claused against consulting revenue**, so the
pass/fail logic must be client-owned. (2) **Reviving `openBA` as the ATSC 3.0 app substrate**: it is
MIT, it is the only one, and if the FCC sets a date it becomes load-bearing overnight. ⚠️ Scope it
as adopt-and-maintain; there is no upstream.
### Pass 33 (2026-11-27) — the media-monitoring & earned-media measurement layer in North America

- **The category just became a budget line.** Gartner published its **first-ever Magic Quadrant for
  PR and Media Monitoring Tools on 2026-10-20**, naming AI visibility, evolving media-relations
  dynamics and **outcome-based earned-media measurement** as the forces reshaping it. A
  first-edition MQ is the clearest signal that procurement has a line item where it previously had a
  discretionary purchase. ⚠️ Leader placements known here only from **Meltwater's own release** — a
  vendor source.
- **The buy side has consolidated into one vendor across three functions.** **Cision owns Brandwatch
  and PR Newswire**: the wire, the clipping and the social-listening tiers of one workflow, sold as a
  combined dataset. Meltwater positions as the all-in-one alternative. Both proprietary.
- **AI is explicitly redrawing the paid/owned/earned split.** S&P Global Market Intelligence
  published on this directly (2026-04). Combined with the answer-engine referral collapse documented
  in pass 30, earned media is simultaneously **harder to attribute and more valuable** — which is
  precisely why "outcome-based measurement" is the phrase analysts reach for.
- **Opportunity — the AMEC-conformant measurement layer nobody ships.** AMEC's Integrated Evaluation
  Framework (outputs → out-takes → outcomes → impact, tagged across PESO) is the settled, free,
  industry-endorsed standard, and **no open-source implementation of it exists** (verified
  2026-11-27). Meanwhile the collection substrate beneath it is Apache-2.0 and committed daily
  (`story-indexer`, `trafilatura`, `changedetection.io`). **The build: own the corpus on permissive
  infrastructure, implement AMEC outcomes on top, and retire AVE for metrics a CFO accepts.** This is
  the plane's flagship North American engagement — see `compose/patterns.md` pattern 51.
- **Why "own the corpus, rent the analysis" sells here.** The consolidation above is the argument: a
  client whose wire, clipping and listening all sit with one vendor has no leverage and no portable
  history. A self-hosted Apache-2.0 collection tier restores both, without requiring the client to
  abandon their analysis vendor on day one.

### Pass 34 (2026-11-27) — the ad-integrity, supply-chain-transparency & verification layer in North America

**The region where accreditation is the product.** North America is where the accreditation bodies sit,
and that makes it the only region where the binding constraint on this plane is institutional rather
than technical.

- **MRC accreditation is the gate, and it is weaker than clients assume.** The Media Rating Council
  accredits invalid-traffic measurement and splits it into **GIVT** (general — declared bots, spiders,
  datacenter traffic) and **SIVT** (sophisticated — hijacked devices, falsified impressions, ad
  stacking). **GIVT is required for accreditation; SIVT is "strongly recommended" and not mandated.**
  HUMAN's platform was accredited for both under the IVT 2.0 addendum per an MRC letter of
  **2026-04-14**, and the MRC published a quarterly accreditation update on **2026-07-14**.
  **Opportunity:** the highest-value, lowest-competition deliverable here is not a detector — it is a
  **vendor-accreditation diligence service**: read the client's verification contracts against the MRC
  accreditation letters and show them, line by line, which of the invalid traffic they are paying to
  remove is actually inside the accredited scope. Nobody sells this, every large advertiser needs it,
  and it requires no model and no data licence.
- **TAG Certified Against Fraud is a second, separate gate**, run by the Trustworthy Accountability
  Group since 2016, certifying supply-chain participants on anti-fraud practice rather than certifying
  a measurement. ⚠️ One secondary source reports **GroupM mandated TAG CAF status for all programmatic
  partners** in a May supply-chain standards update; single-sourced, verify before quoting to a client.
  If it holds, it converts certification from a differentiator into a condition of trading with the
  largest buyer in the market — and that is a compliance-engineering engagement.
- **Regulatory posture: thin, and one widely-repeated claim does not check out.** One trade article
  reports an **FTC advanced notice of proposed rulemaking on "deceptive traffic practices"**, with
  potential liability for intermediaries that knowingly facilitate invalid traffic. ⚠️ **Not found on
  any FTC primary source during this pass — do not put it in a client deck.** Recorded here because
  it is circulating and will be quoted back at you; the honest position is that ad fraud in the US
  remains **governed by private certification, not statute.**
- **Measured direction of travel is contested.** DoubleVerify reports fraud/IVT **down 41% YoY in North
  America**; Anura reports global IVT rising **26% (Jan) → 40% (Jun) 2026**. Pixalate publishes
  quarterly North America benchmarks (Q2 2026 available). **Opportunity:** a client-side
  **methodology-reconciliation engagement** — the disagreement is not noise, it is two different
  denominators, and whoever can explain it to a CMO owns the relationship.
- **The build that is clean here:** Prebid Server (Apache-2.0, 595★, 2026-11-26) self-hosted, with
  `schain` enforcement and `sellers.json` graph verification via
  [adops-tool/SPO-sellers-json-crawler](https://github.com/adops-tool/SPO-sellers-json-crawler)
  (Apache-2.0). Supply-path optimisation has **zero open-source presence anywhere** (53 repos
  searched, all logistics and crypto), and Prebid Server is the only auction a consultancy can
  legally modify. **That combination — a real need, a permissive platform and no competing tooling —
  is the strongest greenfield position found in any of the 34 planes.**

- **The graphics desk, pass 35 (2026-11-27): own the rig modernisation, because the lineage is here
  and it is ageing.** North America wrote the newsroom graphics playbook and still holds the rigs:
  [nprapps/interactive-template](https://github.com/nprapps/interactive-template) (MIT, 70★,
  2026-11-25), [nprapps/dailygraphics-next](https://github.com/nprapps/dailygraphics-next) (MIT, 72★,
  2026-09-03), [newsdev/ai2html](https://github.com/newsdev/ai2html) (Apache-2.0, 969★, 2025-10-22),
  [newsdev/archieml-js](https://github.com/newsdev/archieml-js) (Apache-2.0, 215★, 2021-11-12),
  [the-pudding/svelte-starter](https://github.com/the-pudding/svelte-starter) (MIT, 475★, 2026-11-05).
  Note the dates: **the ideas everyone copied are maintained slowly or not at all**, and
  `nprapps/dailygraphics` still carries **4× the stars of its own successor** (294 vs 72) — adoption
  inertia in plain numbers. **Opportunity:** a rig-modernisation engagement — Svelte build, PMTiles
  basemaps, Frictionless schema validation in CI, ai2html retained for annotation — sold to
  mid-market publishers who forked NPR's 2019 template and never upgraded.
- **The election-graphics squeeze is a North American contract problem, not a technology problem.**
  ABC, CBS, NBC and CNN all moved to **AP tabulation data for 2026 and 2028**, and the only
  open-source client for that feed, [newsdev/elex](https://github.com/newsdev/elex) (Apache-2.0,
  169★), has been **archived since 2022-09-07**. The free alternatives (civicAPI, Open America) are
  hosted services with no licence and no self-host path.
  [openelections/openelections-data-us](https://github.com/openelections/openelections-data-us) (5★,
  no licence field) is a historical archive, not a live client. **Opportunity:** build and maintain a
  licensed-feed ingestion client — schema-validated, replay-testable against the 2024 and 2026
  results, with a race-call audit trail. Every US broadcaster and large regional publisher needs
  exactly one of these every two years, and nobody is selling it.
- **The one thing not to propose here:** a self-hosted Datawrapper. Its open core was archived in
  September 2021 and the repo bearing the name has no licence file. Scope the hosted embed as a
  vendor line item or build a bespoke one; do not plan to fork it.


#### Pass 36 (2026-11-27) — the 2D animation plane: **the only region where the labour terms are written down, and they say the animator cannot opt out**

North America is the one region in this plane where the AI question has a *contractual* answer rather
than a policy aspiration, and that answer is the most sellable fact on this page.

- **The Animation Guild (TAG, IATSE Local 839) 2024–27 contract governs all 2026 work.** Ratified by
  **76.1% of voting members** — a large dissent for an animation agreement, and two negotiating-committee
  leaders publicly opposed it over AI.
- **What the AI clauses actually grant:** written notification when GenAI is used, the right to consult
  with the production, and the right to identify alternative non-GenAI tools. Studios may implement
  "technological change" provided they offer **retraining and severance** to displaced workers.
- **What they do not grant — the part a studio's AI programme turns on:** members **cannot opt out of
  GenAI use**, and **cannot prevent their work from being used to train models**. Critics' concrete
  scenario: a board artist is handed an AI-generated script and expected to board it.
- **The guild's own number:** a TAG-commissioned survey found **29% of animation jobs could be disrupted
  by AI within three years**.
- **2026 union activity:** IATSE District 2 convention resolutions reaffirmed that AI "shall be used as a
  tool to enhance member work, not as a replacement for member labour", and backed federal labelling bills.
- **The date that matters commercially: 2027**, when TAG negotiates again. Any 2D AI programme designed
  for a North American studio has a **known contractual expiry**, and the 2027 table will be set by
  what the 2026 deployments look like.

**The engagement shape this implies.** The contract makes *notification and alternative-tool identification*
an operational obligation, not a nicety. Nobody sells that system today: there is no open tool that records
which shots used GenAI, which artist was notified, and what non-GenAI alternative was offered. Built on
Kitsu (AGPL-3.0, run as a service) with a per-task AI-provenance field, it is a compliance deliverable
with a named clause behind it — and it is reusable at every TAG signatory.

**Market context for the region:** North America is the largest regional M&E market (estimates put its
share of global revenue at **33.6%–40.6%** depending on scope), and Forrester/AWS characterise North
American M&E as bullish on GenAI but **still stuck in early experimentation**. There is no federal AI
statute; the constraint is collectively bargained, not legislated.

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

#### Development & pre-production — pass 17 (2026-11-26)

- **The region's AI agenda for media is now explicitly a *sovereignty* agenda, and that is the hook for
  this plane.** The **DPP's European Media Trends 2026** report names AI **and digital sovereignty**
  together as the dominant forces reshaping media technology strategy. Separately, broadcasters are
  weighing the EU AI Act against the fact that standard cloud DAM offerings route content through
  third-party public AI engines that aggregate data on **extra-European servers**. Pre-production is
  where a sovereignty argument is cheapest to satisfy: scripts are small, plain-text and
  pre-publication, and the one Apache-2.0 artefact in the management tier
  (`method-production-suite/method-scheduling`) is explicitly **local-first**. A **local-first,
  self-hosted breakdown and scheduling layer over Fountain** is a sovereignty deliverable that needs no
  model hosting at all.
- **Where European media AI effort actually sits, measured rather than asserted.** An **imec-SMIT (VUB)
  report of May 2026** maps the European media sector across compute, model and application layers and
  finds activity concentrated in the **application layer — archive search, newsroom productivity and
  audience-facing products** — while warning that **smaller and regional media risk being left behind.**
  Pre-production tooling appears in none of those three buckets, which is consistent with this pass's
  own measurement and is why the plane is open ground rather than a contested one.
- **Regulatory direction of travel, with the vote attached.** The EU's **Apply AI Strategy** (launched
  October 2025) targets sectoral adoption; the **European Parliament adopted its position on the AI Act
  Omnibus simplification proposal by 569 votes to 45**; and Member States are pressing for an overhaul of
  the **AVMSD**, with industry preference reported for **horizontal** regulation over expanding
  sector-specific audiovisual rules. For this plane the practical consequence is that **no EU instrument
  places a duty on pre-production** — the duties land at transparency and distribution. Do not sell this
  plane in EMEA as compliance; sell it as sovereignty and cost.
- **Market-structure constant worth repeating here.** EU providers represent only **16% of the EU SVoD
  market** (2025 Commission outlook), so the European buyer for production tooling is the public
  broadcaster and the independent producer, not a regional streamer of scale.
- **Opportunity — ranked third for EMEA.** Below the Art. 13 catalogue reporter and the Art. 50
  transparency work, both of which have deadlines. This one has none, which makes it a slower sale;
  it is listed because the sovereignty framing converts it from "nice tooling" into an infrastructure
  decision, and because the EBU/DPP bloc of small broadcasters buys collectively.

#### Book, ebook & scholarly publishing — pass 18, measured 2026-11-26

**This is the region where accessibility is a condition of market access.** The **European
Accessibility Act (Directive (EU) 2019/882)** has applied to ebooks sold in the EU since **28 June
2025**, with a reported backlist transition to **June 2030**. Technical baseline: **EN 301 549**
(V3.2.1 = WCAG 2.1 AA; **V4.1.1 published September 2026**, aligning with WCAG 2.2) plus **EPUB
Accessibility 1.1**. Two obligations recur and both are machine-testable — accessibility features
must be **discoverable in metadata**, and **DRM must not disable them**.

**The enforcement mechanism is commercial before it is legal.** Reported consequence of failure is
**suppression or removal from EU storefronts, with no formal warning process** — a retailer decision,
not a regulator's. That is what makes this urgent independently of fines.

**Enforcement state, recorded as contested because the sources genuinely conflict:**

| Claim | Source character | Status |
|---|---|---|
| First EAA court ruling landed **June 2026** | Vendor compliance blog | **Unverified** |
| After 14 months, **no** publisher, bookseller or platform fined or sued over ebook accessibility | Vendor analysis, Sept 2026 | **Unverified, and contradicts the above** |
| First **French** lawsuits reported late 2025; **Dutch and German** authorities signalled audits in 2026 | Vendor compliance pages | Directional |
| Penalties set **per member state**; no single EU sanctions regime | Multiple | Consistent across sources |
| **No EU-wide enforcement dataset**; Commission's first review due **2030** | EAA tracker | Consistent |

**Overlapping clock — the EU AI Act.** Article 50 transparency obligations (labelling AI-generated
content) took effect **August 2026**; Commission guidelines published **20 July 2026**. A publisher
using third-party AI editorial tools is generally a **deployer**. Where AI-assisted content has been
**reviewed and approved by a person with documented editorial responsibility, labelling is reported
not to be required** — which converts documented human sign-off into a compliance artefact the
workflow must capture. Timing for high-risk obligations is disputed (2 August 2026 vs **December
2027** for the EAA-compliance requirement on high-risk providers); recorded as unresolved.

**Readiness, and therefore the size of the gap:** one vendor cites **fewer than 4 in 10 European
publishers producing accessible ebooks**. Unverified and probably dated, but no counter-figure was
located.

**Key open-source players anchored in this region — EMEA owns the reading-system stack:**
**EDRLab** (France) — `edrlab/thorium-reader` and the `readium/*` stack, **all BSD-3-Clause**, the
reference implementation of accessible reading and of LCP; **COPIM/Thoth** (UK) —
`thoth-pub/thoth`, **Apache-2.0**, OA book metadata with ONIX/MARC export; **EDItEUR** (UK) —
custodian of **ONIX** and **Thema**, with **freely available code lists**; **DAISY Consortium** —
`daisy/ace` (MIT) and the Pipeline modules (LGPL).

**Opportunity, specific to this region, and it is the strongest in this plane:** statutory demand
with a date already passed, a backlist deadline in 2030, a measured supply gap, **permissive
validators** (`epubcheck` BSD-3, `ace` MIT), **permissive reading systems** (`readium/*` BSD-3) —
and **no open generator for the remediation itself**. The deliverable is a metadata-first
remediation service: assert `schema:accessibilityFeature` correctly, prove it with `ace` and
`epubcheck` in CI, and keep an auditable record of human editorial approval to satisfy AI Act
Article 50 at the same time. **Compliance evidence, not just compliance, is the billable artefact.**

**Informed gap:** no primary regulator or court source for any EAA enforcement action was located;
every enforcement claim traces to a vendor page. Stated as a gap, because the difference between
"enforced" and "claimed enforced" changes how a proposal should be pitched.

#### Sports media & live events — pass 19 (2026-11-26). The only region where **sovereignty makes the permissive stack the cheap answer**

- **Scale, in proportion:** Europe's five largest markets are together worth about **one third of the
  US** sports-rights total, and the **Premier League alone is 7.8% of the global total**
  (SportBusiness 2026). The region is a collection of strong national markets rather than one block.
- **The sovereignty argument is now the procurement argument.** The DPP's *European Media Trends
  2026* reports digital sovereignty entering business-resilience planning at European media
  companies. VSN states the mechanism plainly: standard cloud DAM offerings **rely on third-party
  public AI engines that aggregate data on extra-European servers**. For sports this is acute — match
  footage is the single most valuable asset a rights-holder owns, and sending it to a third-party
  inference endpoint is the exact thing sovereignty policy is written to prevent.
- **The AI Act continues to tighten and simplify at once.** Article 50 transparency duties have
  applied since **2026-08-02** (recorded at pass 9 in this file); the **European Parliament voted
  569–45** to adopt its position on the AI Act Omnibus simplification proposal. Synthetic commentary
  and synthetic presenters fall under Article 50 marking and disclosure; automated highlight
  selection does not.
- **Mid-tier clubs and leagues are the at-risk buyer, per a primary academic source.** The
  **imec-SMIT (VUB)** mapping of May 2026 concludes that value accrues to whoever controls
  infrastructure, data, models, interfaces, rights and business arrangements, and warns explicitly
  that **smaller and regional media players risk being left behind**. In sports that is every league
  outside the top five — the ones that cannot fund a broadcast operation per match.
- **Piracy enforcement remains measurably inadequate for sport.** This file already records the EU
  study *Countering online piracy of sports and broadcast in the EU*, whose own assessment found
  rapid blocking **comes up short** for sports and broadcast specifically — a live, unsolved,
  EU-acknowledged problem in exactly this plane.
- **MENA:** media-company AI spending in the region is expected to reach **$520m in 2026**.
- **Public service media are organizing.** The EBU AI Forum (March 2026) featured structured AI
  adoption, governance frameworks and strategic direction across public broadcasters — and public
  broadcasters hold large shares of national sports rights in EMEA.

**Opportunity, specific to this region:** **on-premise, sovereign sports analysis — and it is cheap
here for a structural reason.** Every component of the permissive sports-CV stack runs locally on a
single GPU: `roboflow/sports` (MIT), `roboflow/supervision` (MIT), `roboflow/trackers` (Apache-2.0),
`Sports2D` (BSD-3), `PySport/kloppy` (BSD-3). There is **no inference API in the critical path**, so
"your footage never leaves your datacentre" is an architectural fact rather than a contractual
promise. This is the one plane in the KB where the sovereignty requirement and the open-source
licence shape point the same way, and the buyer is the mid-tier league the imec report identifies.

**Informed gap:** no EMEA-specific open-source sports project of consequence was located; the
football-analytics tooling is maintained by individuals and small groups across several countries
rather than by any European institution.


#### Investigative journalism & source protection — pass 20 (2026-11-26). **The institutional heartland, and the only region where the FOI platform layer is permissive**

**The civic-tech institutions of this plane are European, and unlike North America's they are not all
copyleft.** `globaleaks/globaleaks-whistleblowing-software` (1,529★, AGPL-3.0, Hermes Center, Italy);
`mysociety/alaveteli` (421★, AGPL-3.0, UK, pushed 2026-11-25); **`okfde/froide` (413★, MIT, Open
Knowledge Foundation Deutschland, pushed 2026-11-09)**; `huridocs/uwazi` (330★, MIT, pushed
2026-11-26). Froide and Uwazi are **the two permissive platforms in a tier that is otherwise
copyleft worldwide** — which makes EMEA the region where a records-access or documentation capability
can be embedded in a proprietary product without an AGPL conversation. That is a regionally specific
commercial fact, not a general one.

**The regulatory stack is the densest of the four regions**, and this plane sits where three
instruments overlap: the **AI Act**, the **DSA**, and the **European Media Freedom Act** — of which
reporting one year after entry into force describes public-service broadcasters as still under severe
pressure, raising doubts about its practical effect. Add the pass-5 finding that EMEA is the only
region where rights reservation is a **legal instrument** (DSM Art. 4 requiring machine-readable
form), and the result is a buyer who must evidence compliance across several regimes at once.

**Two 2026 studies that together make the sales argument.** The **imec-SMIT (VUB)** mapping study
(May 2026) argues that adopting AI delivers no value by itself — **control of infrastructure, data,
models and rights** is what does. The **Future Newsrooms Study** (July 2026) measures the blocker:
**52%** of surveyed newsrooms name cultural resistance or scepticism as the main barrier and **61%**
a lack of technical skills — neither of which is cost or capability. A buyer like that does not want
a model; it wants **an architecture it controls and staff who can run it**, which is exactly the
self-hosted chain in Pattern 40 plus training.

**MENA, within this region's bucket.** Reporting puts Arab media AI spending at **$520M in 2026**,
with UAE and Saudi adoption projected to exceed 95% by 2030, while most journalists using AI have
had little or no formal training and nearly **eight in ten** work in newsrooms with **no formal AI
policy**. Saudi Arabia's Ministry of Media and SDAIA launched a Media Innovation Bootcamp and an **AI
Principles in Media** document in **February 2026**. This is the one sub-region where the policy
itself is still being written — so the sellable asset is **the policy-plus-implementation pair**, not
an audit trail for a policy that does not yet exist.

**Opportunity, specific to this region:** the compliance-evidence layer, sold against three overlapping
regimes rather than one. Pattern 40's human-validation record (`ICIJ/prophecies`, AGPL-3.0) is the
artefact that answers "show me" under the AI Act, the DSA and an EMFA-era editorial-independence
question with the same data. **And note the provenance already inside the agent layer**:
`buriedsignals/spotlight`'s licence file cites a **Derek Bowler, EBU Eurovision News Spotlight**
piece (Dec 2025) — European broadcast institutions are already the methodology source for the OSINT
agent layer, which is a credible door into the EBU membership.

**Informed gap:** `reutersinstitute.politics.ox.ac.uk` and `acma.gov.au` do not resolve from this
session, so the Future Newsrooms and imec-SMIT figures above are **from search snippets, not read at
source**. Treat as reported, not verified.

**Pass 21 (2026-11-26) — the spatial, immersive & volumetric plane.** EMEA is the only region where
immersive telemetry is **already constrained by binding law**, and that is this region's commercial
story. **Regulation (EU) 2024/1689 (the AI Act), in force since 2024-08-01**, prohibits emotion
recognition in workplaces and educational settings and certain biometric categorisation. XR is the
technology that reads exactly those signals continuously: eye tracking, gaze dwell, gesture and body
geometry are not optional extras in a headset, they are how it works. European analysis of the Act
states its implications for XR directly, and policy alignment work ties it to the **EU Virtual Worlds
Strategy** and the **European Accessibility Act**, funded through Horizon Europe and the DIGITAL
Europe Programme.

No XR-specific European rule was identified as adopted or amended during 2026 — stated as a finding,
not a gap in searching. The constraint is the AI Act plus GDPR, applied to a device class that
happens to be a biometric sensor array.

**The region's institutional presence is real and verifiable.** `overte-org/overte` (Apache-2.0,
pushed 2026-11-23) is governed by **Overte e.V., a German registered association** — the only
EMEA-domiciled open immersive platform found in this pass, and the third custodian of a codebase whose
copyright headers run High Fidelity (2013–2019) → Vircadia/DigiSomni (2019–2022) → Overte e.V.
(2022–2026). Khronos runs **UnitedXR Europe in Brussels, 7–9 December 2026**, with OpenXR positioned
as the vendor-neutral substrate; **Immersive Tech Week (Rotterdam)** and **XR Expo (Stuttgart)** are
the other recurring venues.

**Opportunity, specific to this region: the telemetry-minimising capture and playback profile.** In
NA the data-minimisation argument is a prudent choice; in EMEA it is a legal requirement with a
named instrument behind it. No open project found in this pass implements gaze/gesture minimisation
as a configurable profile — the engines expose the sensors and leave the policy to the application.
The product is therefore a **documented, auditable XR telemetry profile** built on
`KhronosGroup/OpenXR-SDK` (Apache-2.0), with on-device landmark processing via
`google-ai-edge/mediapipe` (Apache-2.0) so that raw biometric streams never leave the headset, and
evidence output a DPO can file. The same argument that made pass 8's rights-reservation work sellable
in EMEA applies here: **whoever has written the policy has committed to being able to evidence it.**

**Second opportunity: accessibility, already a statutory hook here.** The European Accessibility Act
is named in the same alignment work as the AI Act, and this KB already holds an accessibility plane
(pass 3). Immersive content has no established accessibility conformance practice — captioning,
audio description and comfort/motion mitigation in a 3D scene are unsolved in the open stack. EMEA is
the only region where that gap has a legal lever attached to it.


**Pass 22 — the podcast plane, and EMEA is the only region where disclosure of a synthetic host is
law rather than etiquette.**

- **First opportunity: Article 50 compliance for synthetic voice, and the date has passed.** The EU
  AI Act's transparency duties took effect **2026-08-02**: users must be told when they are dealing
  with a machine, and synthetic content must be **marked in a machine-readable way and labelled on
  first use**. Audio-industry counsel reads the scope as covering **cloned voices and synthetic
  dialogue**, and explicitly **podcast ads, synthetic voice-overs and AI-generated jingles** — even
  where only part of a production is synthetic (Gleiss Lutz; Production Expert). An open podcast feed
  reaches the EU by default, so the duty attaches to any show the client distributes publicly.
  Penalties are reported at **up to €15 m or 3 % of global turnover**; that figure comes from vendor
  commentary and **should be checked against the regulation before it enters a deck**.
- **Why this is a build and not a memo: the namespace has no disclosure tag.** This is the sharpest
  finding of the pass for EMEA. `Podcastindex-org/podcast-namespace` is **CC0-1.0** and carries tags
  for transcripts, chapters, funding, person credits and `alternateEnclosure` — and **nothing for
  AI-generated or synthetic content**. The law now requires a machine-readable mark; the open
  distribution format for podcasting has no field to carry it. Because the namespace is public-domain
  and takes proposals in the open, **the compliance artefact and the standards contribution are the
  same piece of work**: specify a disclosure tag, implement it in a publishing path (Podlove
  Publisher, MIT), and emit per-episode evidence a DPO can file. That is a first-mover position in a
  CC0 standard, which is cheap to take and hard to take twice.
- **Second opportunity: GDPR-defensible audience measurement.** Prefix analytics means a third party
  sees every listener request. `opawg/podcast-prefixes` (MIT) exists precisely to list prefix
  providers **and their privacy policies**, and `skymethod/op3` (MIT) is self-hostable. An EMEA
  broadcaster can therefore be given measurement that runs **inside its own infrastructure** with the
  transfer question answered in the architecture rather than in an addendum — the same argument that
  made rights-reservation work sellable in this region.
- **Market context, and a platform shift.** Edison's UK data has **YouTube now the UK's most-used
  podcast platform, narrowly ahead of Spotify** — the same inversion as the US, in a market with
  stricter content duties. The **EBU** convened a joint session of its Legal & Policy AI Group and
  its Audio & Radio Futures Network in **June 2026**, which is the access route to public
  broadcasters on exactly this topic.
- **Informed gap.** No EMEA-specific podcast **market-size or adoption** figures surfaced in this
  pass's searches — the retrievable material was legal commentary, not measurement. Recorded rather
  than estimated.

- **Europe's media sector is most active in exactly this plane, and that is measured, not asserted.**
  The imec-SMIT (Vrije Universiteit Brussel) report of May 2026 finds that at the application layer
  Europe's media sector is most active in **archive search and retrieval**, newsroom productivity,
  and audience-facing products. **Archive search and retrieval is the still-image plane's primary
  use case**, and the permissive stack for it exists and has almost no users: `Cantaloupe` (MIT,
  308★) to serve, `OpenSeadragon` (BSD-3) to view, `open_clip` (MIT, alive) to embed, `exiftool` to
  carry the IPTC. **Opportunity:** a European archive-search engagement can be built end to end
  with **no copyleft and no vendor** — and the demand side is the one the research names first.
- **AI Act Article 50 is the forcing function for image labeling, and the date is genuinely
  contested.** BDO reports the transparency obligations applying from **2 August 2026**; the
  European Audiovisual Observatory reports a Council-approved revision of **29 June 2026** moving
  the updated Article 50 requirements to **2 December 2026**; Chambers (updated 21 May 2026) records
  formal adoption and Official Journal publication as still pending, and the political agreement
  postponing Annex III high-risk obligations to **December 2027**. **These do not reconcile.**
  For a client deliverable, cite the Official Journal, not a secondary tracker — and design the
  labeling pipeline so the *date* is configuration rather than architecture.
- **The publishers are fighting the enforcement mechanism, not the obligation.** A coalition of
  news, media and entertainment organisations attacked the draft code of practice as
  **"fundamentally flawed"** and pressed the EU to overhaul or reject it, while over 100 companies —
  Amazon, Google, Microsoft, OpenAI, alongside Airbus, Nokia and Orange — signed the voluntary code.
  **A European publisher client is institutionally on the opposite side of this from the model
  vendors**, which matters for how a provenance proposal is framed: as leverage, not as compliance
  cost.
- **UK: the training question was left open, and the appeal is live.** In *Getty Images v Stability
  AI* (High Court, 4 November 2025) Getty **dropped its primary training-infringement claim
  mid-trial**, partly for lack of evidence that training occurred in the UK, and the court dismissed
  secondary infringement on the reasoning that a model which **does not store or reproduce** the
  works is not an "infringing copy". Getty won a **narrow** trademark finding on watermarks in
  outputs, which the judge called "both historic and extremely limited in scope", and has been
  granted **permission to appeal** on the meaning of "infringing copy". **The UK therefore has no
  meaningful ruling on the lawfulness of learning from copyrighted images** — a UK client's image
  position rests on licensing and reservation, not on case law.
- **Agencies have already set the editorial floor.** dpa's internal AI directive (reviewed as of
  June 2026) **generally prohibits AI-generated photos and videos in a news context.** Combined with
  AP and Getty, the practical standard across the Atlantic is converging on *no synthetic news
  imagery, disclosure for everything else* — which is a workflow specification, and nobody has built
  the workflow.
- **Informed gap.** No EU instrument specific to **photographic** or print production surfaced in
  this pass — Article 50 is a horizontal transparency duty over synthetic content, not an
  image-sector rule. The sectoral pressure in EMEA is coming through the **AVMSD overhaul** that
  Member States are pushing, and this pass found **no image-specific provision** in it.

#### The owned-channel & audience-relationship plane — added 2026-11-26 (pass 24). The region where the consent layer *is* the engagement, and every deadline is already past

- **Both TCF deadlines are behind us, not ahead.** **TCF v2.3 became mandatory for TC strings
  generated on or after 1 March 2026** (Google publisher guidance; iubenda gives 28 February 2026 —
  a one-day discrepancy that changes nothing). **TCF v2.4 specifications and the updated Global Vendor
  List published 23 July 2026**, with the **website deadline 23 October 2026** and a later date for
  apps and CTV. A client that has not moved is already non-conformant, which makes this the only plane
  in this KB with a **remediation** sale rather than a transformation sale.
- **⛔ And no open-source CMP is IAB-registered.** `c15t` (Apache-2.0, 2,045★) and
  `iabtcf-es` (Apache-2.0, **156★**) produce a valid TC string and a consent UI; they do **not**
  produce standing in the framework. **Raise this in week one** — it is a procurement line item, not a
  build, and it is the most likely late-stage surprise in an EMEA engagement in this plane.
- **Consent itself is being relitigated right now, which changes the design.** Media bodies **EMMA,
  ENPA, EPC and NME** jointly objected to the **Digital Omnibus**'s **Articles 88a/88b**, arguing the
  media exemption does **not** preserve publishers' ability to ask readers directly for consent. EU
  governments **dropped browser-level cookie-consent preferences** (MLex, October 2026) — publishers
  read that as a win, and MLex's own headline notes the advertising fight is **unresolved**. The
  **European Publishers Council** wants low-risk **first-party** processing to run on **legitimate
  interest** rather than consent, while objecting that AI developers may invoke legitimate interest for
  systemic processing. **Adoption of the wider package is not expected before 2028.**
  → **Design consequence (Pattern 24.4): store the `legal_basis` field, not a boolean.** A consent
  record that only says true/false cannot survive a shift to legitimate interest; one with a legal
  basis, jurisdiction, spec version and the UI version shown can.
- **The AI-labelling clock also runs here:** marking obligations for AI-generated content carry a
  **2 December 2026** deadline for systems already on the market before 2 August 2026.
- **A revenue-side tailwind worth naming:** the EU Court has confirmed that publishers **can be granted
  rights to fair remuneration** when platforms use their content — which strengthens the business case
  for the identification and rights-reservation work in pass 5 alongside this plane.
- **Opportunity 1 — the re-configurable consent spine (Pattern 24.4).** c15t + iabtcf-es + the consent
  object in Apache Unomi, with an audit export of *what was asked, when, in which words, under which
  spec version*. All Apache-2.0, all client-owned.
- **Opportunity 2 — data residency has a named answer.** [pentacent/keila](https://github.com/pentacent/keila)
  (AGPL-3.0, 2,269★, pushed 2026-11-24) is a newsletter tool **built and hosted in the EU**. When the
  blocker is "we cannot send our subscriber list to a US processor", this is the row to open with —
  with the AGPL service-boundary caveat from `verticals/solutions.md`.
- **⛔ Avoid in this region specifically:** `rudderlabs/rudder-server` and `ConsentOS/consentos` are
  **Elastic License 2.0** (licence files read) — source-available, not open source, and ELv2 forbids
  providing the software to third parties as a managed service. Recommending either to an EMEA client
  with a compliance-driven procurement process would not survive legal review.
- **Informed gap.** Searched for **EMEA-specific adoption figures** for publisher owned-channel or
  consent tooling; **none surfaced.** The EMEA evidence in this plane is **regulatory and advocacy
  material, not market data** — several sources are trade-body objections and newsletters rather than
  primary texts, and one result carried contradictory dates. Verify the Omnibus status against
  official Commission or Council documents before quoting it to a client.



#### The traffic, sales-order-to-air & billing plane — added 2026-11-26 (pass 25). The region where the buyer is a public broadcaster, the constraint is sovereignty, and **ad traffic is the wrong pitch**

> Non-repo facts from web-search extracts; publisher domains (`ebu.ch`, `tech.ebu.ch`) were **outside
> this session's allowed network domains** and could not be opened. Marked **†**.

- **The structural fact: much of EMEA broadcast has no ad traffic to sell.** Licence-fee-funded public
  service media do not book spots — so pitching ad sales automation here misreads the region. **What
  they do have is the hardest scheduling and obligation problem in the world:** programming quotas,
  multi-language and multi-region opt-outs, archive obligations and now AI labelling. Sell
  **scheduling + provable compliance**, not order-to-cash.
- **Sovereignty is the buying criterion, and it favours what we can deploy.** The **EBU and NVIDIA**
  expanded a **sovereign-AI framework for public service media**, announced at a Berlin event on
  **19 October**, aimed at giving European media technological autonomy; the EBU network is cited at
  **110+ media organisations** reaching **over 1 billion people**.† **Informed gap / conflict:** one
  source dates the original partnership to **June 2025** and another presents an **October 2026**
  announcement — **verify against the primary EBU release.†**
- **Why that matters commercially:** a sovereignty requirement **disqualifies a US SaaS traffic
  system** and favours a **self-hosted, European-origin, GPL-3.0 platform**. That is exactly
  **Nebula** ([nebulabroadcast/nebula](https://github.com/nebulabroadcast/nebula), 332★, pushed
  2026-11-23, in 24/7 use since 2012) — the one row this KB had previously written off as dead. EMEA
  is the region where that correction has the most commercial consequence.
- **The regulatory load is real and dated.** EU AI Act **Article 50** requires machine-readable
  marking of synthetic output; systems on the market before **2 August** must comply by **2 December**;
  deepfakes must be disclosed **no later than first exposure**, with a lighter standard for artistic or
  satirical work.†
- **And the broadcasters are pushing back, which is itself the opening.** In **June 2026** the **EBU**
  with private broadcaster groups **VAUNET** and **ACT** wrote to the European Commission asking it to
  **narrow the deepfake definition and reduce labelling burdens**.† The EBU has separately pushed
  **C2PA** provenance and, in **April 2026**, called for an **AVMSD revision** addressing Big Tech and
  AI gatekeeping of media services.† **A client lobbying to narrow an obligation is a client who will
  have to evidence the obligation that survives.**
- **Opportunity 1 — the obligation-evidence layer on the schedule.** Quotas, opt-outs and Article 50
  marking all resolve to: *prove what was transmitted, in which territory, in which language, with
  which disclosures.* That is Pattern 25.1's reconciliation service pointed at a compliance question
  instead of an invoice — the same build, a different buyer, and the EMEA version does not need a
  billing engine at all.
- **Opportunity 2 — shared tooling, because this region actually shares.** Public broadcasters are
  piloting common tools: a **France Télévisions metadata tool** made available to EBU members, and a
  **BBC–EBU toolkit** for benchmarking AI assistants' news integrity.† A component built for one EBU
  member has a distribution path to 110+ others, which is unlike any other region in this KB.
- **Informed gap:** no source found giving **adoption rates for AI in European broadcast traffic or
  scheduling operations specifically**. EBU material covers newsroom, metadata, provenance and
  recommendation; the commercial/scheduling desk is unmeasured here. Treat EMEA traffic-desk adoption
  as **not researched, not absent**.

#### Pass 26 addendum (2026-11-26) — the energy & carbon plane: the only region where this is enforced, and it is enforced by contract, not by law

**This is the region that makes the plane commercial.** It is also the clearest instance in this KB of an
obligation that binds harder than legislation while not being legislation at all.

- **The binding mechanism is the commissioning condition.** The **BBC** makes **BAFTA albert**
  certification mandatory for all new commissions and recommissions of TV broadcast content. **ITV**
  requires full-length productions to complete certification *and* carry the required end-board logo as
  an expected delivery item. **Channel 4** requires productions to use albert tools to measure and
  report. Commentary across the industry makes the same observation: albert certification has become one
  of the most consistently enforced requirements in UK commissioning **and it is not a legal obligation
  at all**. A production that skips it does not get fined — it does not get delivered.
- **📅 A dated trigger to watch, with a conflict left unresolved.** The current albert toolkit is being
  replaced by a **Next Generation Toolkit** with a redesigned calculator. **albert's own figure for the
  closure of the current toolkit is 16 December 2026**; one industry guide states 17 December. The BBC
  stated the new version would launch 16 September 2026. **The conflict is recorded, not resolved —
  confirm with albert before committing a delivery date.** Either way, every integration built against
  the current toolkit expires within weeks, which is a buying trigger rather than a risk.
- **The EU instrument arrived this year.** The **MEDIA Carbon Calculator** launched **13 February 2026**
  at the European Film Market (Berlinale): EU-backed, **free**, accessed via **EU Login**, following the
  **GHG Protocol** across **Scope 2 and Scope 3** (transport, waste, business travel, purchased goods).
  It is the first single EU-backed tool for live-action project footprints and explicitly does **not**
  replace national calculators — so EMEA now has *more* tools, not fewer, and **reconciliation between
  them is a real client problem**. It was presented by Florian Reimann of **Yamdu**, a
  production-management vendor already catalogued in `verticals/solutions.md`: that is the integration
  surface.
- **National frameworks remain in force alongside it:** **Carbon'Clap** and the Ecoprod label (France,
  collective founded 2009), **Green Film** (Trentino Film Commission, Italy — present at the EFM
  12–18 February 2026). Italy additionally reports rising green-production and cinema energy-efficiency
  activity.
- **CSRD/ESRS reaches the sector indirectly.** A Council of Europe report on the green transition in the
  audiovisual sector concludes the CSRD affects AV **indirectly**, via obligations on all undertakings
  large enough to fall in scope; AV actors meeting the large-undertaking threshold report directly.
  ⚠️ **Scope and timing have been amended since those publications (Omnibus) and were not verified in
  this pass — do not quote a CSRD threshold to a client from this KB.**
- **A second regulatory edge, and it is the one nobody in media is watching:** EU **green-claims** rules
  taking effect **September 2026** bar generic environmental claims such as "eco-friendly" without
  recognised proof. A broadcaster or streamer that markets a "carbon-neutral" production or a "green"
  streaming tier is making exactly such a claim. **The compliance artefact is the evidence trail behind
  the claim** — which is the same artefact Pattern 26.3 produces.
- **Opportunity — the permissive institutional asset nobody uses.**
  [ABC-TransitionBasCarbone/bilan-carbone](https://github.com/ABC-TransitionBasCarbone/bilan-carbone)
  is **MIT**, pushed **2026-11-26**, and has **5 stars** — code from the body that owns France's official
  corporate carbon methodology. For a French or francophone engagement this is a credible, licence-clean
  starting point that no competitor has noticed.
- **Opportunity — ESRS machine-readability.** [esrs-xbrl-parser](https://github.com/aimabel-ai/esrs-xbrl-parser)
  (**ISC**, 12★) is the only permissive, correctly-licensed ESRS/XBRL piece found; the best-starred
  alternative, [report-analyst](https://github.com/climateandtech/report-analyst) (42★, pushed today),
  has **no licence file at all**. An AV group that must file ESRS has no adoptable open tool.


#### The production-finance & soft-money plane — added 2026-11-26 (pass 27). The region where the binding constraint is a **cap and a closed window**, not a rate

- **The rate stopped being the differentiator in EMEA during 2026; availability did.** Three of the
  four largest schemes now ration rather than price, and rationing is a scheduling and
  evidence-sequencing problem — which is software — rather than a tax-planning one.
- **Germany is the sharpest case: the federal pot was doubled to €250M for 2026 and was exhausted on
  2026-08-20.** The window for shoots starting in 2027 opened in **November 2026**. A production that
  misses a window does not get a smaller credit; it gets **none this year**. ⚠️ One source describes a
  restructured DFFF under a new film law — single-sourced, treat as unconfirmed.
- **Italy tightened in both directions at once.** The 2026 budget law cut the national cinema fund
  from **€700M to €610M** with a further cut projected for 2027, and introduced the country's
  **first-ever cap on production tax credits** — per-work and per-company caps, a closed annual budget
  and **fixed application windows** — after the authorities **revoked €66M of credits in 2025**.
  Revocation after the fact is the single strongest argument in Europe for a traceable, per-line,
  auditable claim pack: the risk is no longer "will we qualify" but "will it be clawed back".
- **UK** replaced legacy Film Tax Relief with **AVEC**, reported as fully applying to commercial
  productions from **2026-04-01**, with a **VFX uplift whose qualifying costs are exempt from the 80%
  cap** — a structural gift to VFX-heavy work and to Globant's own delivery shape. ⚠️ **The published
  rates are a gross/net minefield**: trade sources give 39% gross ≈ 29.25–29.5% net for AVEC, and for
  the Independent Film Tax Credit both "AVEC raised to 39.75% for budgets ≤ £15M" **and** "53%"
  appear. These are almost certainly gross and net expressions of the same relief, but **the KB does
  not assert which**; confirm against HMRC before quoting a number to a client.
- **France** (TRIP/C2I): 30%, rising to **40% when French VFX spend exceeds €2M**, capped at €30M per
  project — unchanged in these sources. **Spain**: 30% on the first €1M of eligible Spanish spend and
  25% above, capped at €20M per film, with the **Canary Islands** higher (sources give ~45–50%, and
  they disagree — do not quote a Canaries rate without the ICAA/Canaries primary document).
- **The primary source worth more than any aggregator.** The **Council of Europe / European
  Audiovisual Observatory IRIS** consolidated report, *Fiscal incentives and cash rebates in the
  audiovisual sector*, is a public, cross-border, institutionally maintained comparison. Every other
  figure in this subsection came from commercial blogs that **contradict each other**, which is itself
  the finding: **EMEA's incentive data is published by vendors with an interest in the answer.** For a
  rules-as-code build, the IRIS report is the citation that survives review.
- **The opportunity, placed.** EMEA is where an incentive engine must model **caps, closed windows,
  budget exhaustion and clawback** rather than just a percentage — and where the per-jurisdiction rule
  sets differ most per euro of spend. It is also the region where **AGPL is least often a blocker**,
  because deployments are typically client-owned and single-tenant: OpenFisca and PolicyEngine-core
  are usable here in ways a North American multi-tenant SaaS could not risk.

#### The age-rating & classification plane — added 2026-11-26 (pass 28). **The only region where the age rating itself becomes a published-methodology duty — and that makes it the best region in this plane**

**The headline, and it is new since any previous pass.** The European Commission has proposed the
**EU KIDS Act** — **COM(2026) 681, procedure 2026/0286 (COD)**, Commission text September 2026,
Council working documents October 2026. For providers of **software application stores** it would
require:

1. **an age-rating system** for every application distributed through the service;
2. **publication, "in clear and accessible terms, [of] the methodology, criteria and sources used"**
   for that rating system;
3. **prevention of minors accessing or purchasing apps rated inappropriate for their age**;
4. **carriage of the EU age-verification solution**, certified as conforming with the EU Age
   Verification Scheme;
5. **Article 17** — voluntary EU-level **codes of conduct** to harmonise age-rating methods and
   criteria, Commission-facilitated and multi-stakeholder.

Council working documents also record exemptions (not-for-profit encyclopaedias; scientific, research
and primarily educational platforms; services run by public authorities) and note that **for services
within scope of the minimum age, the age rating need not be the same**.

**This is a proposal, not adopted law.** Say so to clients. But the *direction* is the asset: it is
the first instrument anywhere that treats an age rating as something that must be **explained**, and
an explanation is a data model.

**Supporting EMEA motion:**

- **AVMSD is formally scheduled for revision in Q3 2026.** A Council working document notes the
  directive refers only to *age verification* and **does not mention *age estimation*** as an
  alternative assurance method — a live drafting gap.
- **National activity through 2026:** Spain signed a **co-regulation agreement on classifying
  audiovisual content in June 2026**; Belgium's CSA advisory board was reviewing **draft age-rating
  criteria in March 2026**; **Poland and Greece notified draft age-limit laws** to the Commission.
  One source reports **France's under-15 social-media ban was struck down by the Conseil
  constitutionnel in August 2026** — **flagged as requiring primary-source verification** before use
  with a client.
- **The ladder fragmentation is in the data, not just the law:** Germany runs **three** systems
  (`USK` games, `FSK` film, `FSF` broadcast) and the UK runs `BBFC` for film while the open mapping
  sends `GB → PEGI`. EMEA is where the "one ladder per medium" error does the most damage.

**Opportunity (EMEA), and it is the strongest in this plane.** A **published-methodology age-rating
engine**: declared criteria in an OARS-shaped vocabulary, a versioned per-territory ladder with
`validAsOf` provenance, a per-title decision record, and a generated public methodology page that
discharges duty (2). Nothing in the open estate produces that artefact, the duty is unusual enough
that no incumbent sells it, and Article 17's code-of-conduct route means **early implementers help
write the criteria everyone else will adopt.** Sell it to an app-store or large-catalogue operator
before the code of conduct is drafted, not after.

#### The interactive, branching & playable-story plane — added 2026-11-26 (pass 29). **The only region whose public funder names this plane as a priority — and the only one with a labelling duty that a branching work cannot satisfy**

EMEA is where this plane has an actual policy tailwind, and the evidence is first-party:

- **The European Commission's Apply AI approach commits support for European AI models "focusing on
  interactive and immersive media storytelling".** That is this plane, named, in a funding instrument.
  No other region's public sector names it.
- **Public-service R&D is the open source.** BBC R&D's [storyplayer](https://github.com/bbc/storyplayer)
  (**GPL-3.0**, 19★, pushed 2026-11-03) and [audio-orchestrator](https://github.com/bbc/audio-orchestrator)
  (**GPL-3.0**, 11★) are the only broadcaster-grade object-based-media tools that are open at all,
  along with the Object Based Media Schema. BBC Click's 1000th episode shipped as an interactive
  factual programme on this stack. **30 stars carry the entire category**, and both are copyleft.
- **The labelling duty, with dates.** AI Act Article 50 transparency obligations applied from
  **2026-08-02**, with Commission guidance published **2026-07-21**; the amending regulation approved
  by the Council on **2026-06-29** gives systems already on the market until **2026-12-02**. The duty
  reaches production companies and rights holders *deploying* AI to generate or manipulate content,
  and reaches non-EU businesses whose content is distributed in the EU. EACA has published practical
  Article 50 guidance for agencies.

**The structural gap, and it is specific to this plane.** Disclosure law assumes a **fixed work** that
can carry a label. A branching experience generates a *path per viewer*; an AI character generates
lines that existed nowhere at publication. Nothing in the open stack emits a per-path or
per-utterance disclosure record — and the EMEA-origin runtime that would host one is GPL-3.0 with 19
stars.

**Opportunity (EMEA):** the **per-path disclosure ledger** — an Article 50 artefact for non-linear
work: every path a viewer could take, every AI-generated or AI-manipulated element on it, the
provenance records (C2PA work already in this KB), and a queryable record per transmission rather
than a badge on a frame. The buyers are public broadcasters and their production suppliers; the
deadline is already in force; the competitive moat is that **nobody has modelled disclosure over a
graph**. Sell the ledger as the compliance evidence pack, and the object-based player as the delivery
option — noting the GPL-3.0 boundary before the first commit, exactly as pass 26 did with ODbL data.

⚠️ **Licence note for this region:** the EMEA stack here is copyleft (StoryPlayer, Audio Orchestrator,
Twine, the H5P hosts). Scope it as a service deployment or behind an API boundary, not as embedded
components in a closed product.


### Pass 30 (2026-11-26) — the answer-engine discovery layer in EMEA

The only region where **both halves of the same crawler are legal instruments** — and the only one
whose own trade body says the damage is **not yet quantified**.

| Finding | Source |
|---|---|
| European publishers report traffic and ad-revenue decline post-AI-search, but there is **no quantitative consensus on scale or economic impact within Europe** | **IAB Europe**, Mar 2026 |
| In IAB Europe's own early European traffic dataset, changes were **driven primarily by adjustments within traditional channels, with AI referrals still marginal**; it states the dataset is **not exhaustive** | IAB Europe |
| UK: news publishers **−5% average quarterly** vs **−18%** consumer/B2B; **guide and how-to content hit hardest, opinion and commentary held up** | **AOP**, Jul 2026, 8 leading UK publishers |
| Projection: search traffic to leading UK publishers roughly **halves by Q3 2027** | Press Gazette / AOP |
| **Europe −17%** against the US −38% | Press Gazette |
| AI Act **Article 50** transparency duties; Parliament adopted the **AI Act Omnibus** simplification position **569–45** | European Parliament; trade press |
| Rising **digital-sovereignty** concern in media tech strategy; cloud DAM tools routing to third-party AI engines on **extra-European servers** | DPP *European Media Trends 2026*; VSN |

**Why EMEA is structurally different.** Pass 5 established that EMEA is the one region where
*reserving* rights is a legal instrument — **DSM Article 4** requires machine-readable reservation.
Pass 30 adds the other half: the same crawler's *arrival* is now measurable with permissive tooling.
Put together, EMEA is **the only region where the gap between a declared refusal and an observed
crawl is a legal fact rather than a curiosity.** No other region has the declaration side in statute.

**The AOP genre finding is the most commercially actionable number in this region** and it is widely
overlooked: exposure is **not uniform across a publisher's catalogue**. Guide and how-to content —
precisely what an AI Overview answers completely — fell hardest, while opinion and commentary held.
That converts a boardroom panic into an **asset-level triage question**, and triage is schema and
taxonomy work, which is buildable.

⚠️ Note the EMEA-specific evidentiary gap honestly in any proposal: **IAB Europe says the European
scale is not established.** A consultant quoting US figures into a European boardroom is quoting the
wrong region by roughly a factor of two (−38% vs −17%).

**Opportunity (EMEA):** the **reservation/arrival reconciliation gate** — the compliance delta
between what a publisher declared under DSM Art. 4 (`ai.robots.txt` MIT, already in this KB) and
which crawlers actually fetched, proven from logs (`goaccess` + `crawler-user-agents`, both MIT).
Nobody ships this, every component is permissive, and in EMEA alone the output is **evidence of a
breach of a statutory reservation** rather than a dashboard. Pair it with the second deliverable the
AOP data unlocks: a **genre-level exposure map** of the client's own catalogue — which content types
are answerable-and-therefore-exposed versus defensible — ranked for investment and paywalling, which
routes into pass 13's reader-revenue work with the same taxonomy. ⚠️ Keep sovereignty in scope: the
DPP finding means a stack sending logs or content to a non-European AI service can fail the client's
own procurement, so self-hosted `umami`/`goaccess` is a **requirement** here, not a preference.

### Pass 31 (2026-11-27) — the live-event & show-control layer in EMEA

**EMEA owns this plane's standards, and it is the only region where they are being written *right
now*.** This is the strongest regional placement in pass 31.

| Finding | Detail | Source quality |
|---|---|---|
| **The device-description standard is German** | **GDTF** (General Device Type Format) is recognised as **DIN SPEC 15800:2022**. The MIT parsers (`pygdtf`, `pymvr`) implement a German standard | Standard identifier, verifiable |
| **Stage machinery has a live EU standards family** | **EN 17206** — Part 1 (2020) machinery for stages; **Part 2 (2024)** stage stands and truss lifts; **Part 3 (2026)** safety for **UAS/drones in entertainment**, published by NEN **1 October 2026**, tied to the EU Machinery Directive and Regulation 2019/945 | Standards catalogues + trade press; **Part 3's status was reported inconsistently across sources — verify against the CEN/NEN listing before quoting** |
| **A national standard is being withdrawn in its favour** | **DIN 56950-1** is in the process of withdrawal and replacement by EN 17206 | Trade press |
| **Enforceability is not uniform** | Adoption and legal enforceability of EN 17206 **varies by member state**, and compliance does not automatically satisfy national requirements | Commercial source — treat as directional, but the variance itself is the point for a pan-European client |
| **The hardware incumbents are European** | MA Lighting (grandMA, Germany) and Robe (Czech Republic) are among the manufacturers behind GDTF; the ecosystem's news hub is `gdtf.eu` | Industry structure |
| **Regional AI spend datapoint** | MENA media-company AI spending expected to reach **$520M in 2026** | Trade press, single source |

**The opportunity — and it has a date on it, which is rare in this KB:** **EN 17206-3 (drone shows)
published 1 October 2026** creates a brand-new documentation and conformance obligation for a
production technique that has gone mainstream, in the one region that regulates it. Nothing open
addresses it. See `compose/patterns.md` pattern 31.4.

**The sovereignty angle compounds it.** The DPP's *European Media Trends 2026* finding already in this
file — rising digital-sovereignty concern in European media procurement — applies with unusual force
here, because show control is **on-premise by nature**: a rig runs on a local network, in a venue,
often air-gapped. A self-hosted agent that never leaves the venue LAN is not a compromise in this
plane; **it is the architecture the plane already has**, and it passes a sovereignty review by
construction. This is the easiest EMEA procurement story in the whole KB.

**One licence consequence specific to EMEA:** the plane's most-starred repo, `wled/WLED` (19,132★), is
**EUPL-1.2** — a copyleft licence drafted by the European Commission and governed by EU law. For an
EU client that is unremarkable; for a US or APAC client embedding it, the governing-law clause is a
question to raise before the build, not after.


### Pass 32 (2026-11-27) — the device, TV-app & client-playback layer in EMEA

**EMEA is the region where this plane's standards are current, enforced and *being written now* —
and the only region where broadcasters are trying to regulate the TV device itself as a gatekeeper.
It is the strongest placement in pass 32.**

| Finding | Detail | Source quality |
|---|---|---|
| **HbbTV 2.0.5 is the current core spec** | Published by the HbbTV Association **2026-03-02**; formally published by **ETSI as TS 102 796 V1.8.1 in September 2026** | Association press release + ETSI identifier — **primary, verifiable** |
| **What 2.0.5 adds** | **Formal DRM support, WebAssembly, and next-generation codecs (AV1 and VVC)**; clarifies how **DVB-I applications associated with whole service lists** are supported — explicitly so a platform or aggregator can **obtain GDPR consent or agreement to terms and conditions** | Association + trade press |
| **Operator Apps are the commercial vehicle** | The updated Operator Application spec lets an operator app **manage streaming and presentation of a set of IP-delivered linear channels discovered from a DVB-I service list**. **OSN launched a direct-to-TV pay-TV service on Samsung Smart TVs using the HbbTV OpApp standard** | Association + trade press — a live deployment, not a pilot |
| **Conformance is members-only, and being extended** | The HbbTV conformance test suite is **licensed/distributed only to member companies** and tracked in a members-only SVN repository. The association planned an **RFP to extend it to 2.0.5**; the suite was extended using experience **from Italy and the UK** | Association materials |
| **Next version** | 2.0.6 tentatively listed, timing uncertain (*"Perhaps 2027?"*) | Association technical keynote |
| **⭐ Broadcasters want smart TVs designated as DMA gatekeepers** | A coalition of European broadcasters asked the EU to designate **smart TV platforms and virtual assistants as gatekeepers under the Digital Markets Act**, warning that *"the lack of designation of virtual assistants creates a regulatory void, allowing powerful AI assistants to become de facto gatekeepers for media content"* | Trade press quoting the coalition — **the most on-plane regulatory development in any region this pass** |
| **EU AI Act Article 50 is live** | Applies since **2026-08-02**: machine-readable marking of AI-generated content, deepfake disclosure by deployers, lighter touch for artistic/fictional works. Penalties up to **€15M or 3% of global turnover**. Commission voluntary code of practice on marking/labelling issued **2026-06-10**; systems on the market before the deadline have until **2026-12-02** | Mixed primary/secondary — **verify dates against the Commission's texts** |
| **The device market is fragmenting away from the top two** | **Hisense's Vidaa has overtaken LG's webOS** in European share; **Titan OS ~4%** in Europe. Europe is the **second-largest** smart-TV region at ~**24%** | Vendor/aggregator estimates — directional, but the direction is the point |
| **Public broadcaster AI policies cluster here** | Published AI policies are most common among **Western/Northern European** public media and rare in Central/Eastern Europe. ARD, ZDF, Deutschlandradio and Deutsche Welle adopted a **joint AI code in January 2026**; SRG SSR's rules took effect **2026-06-01**; **Radio France** added an annex in April 2026 **banning synthetic voices capable of replacing its journalists' vocal identity** | State Media Monitor 2026 + trade press |

**The strategic read.** EMEA is the only region where the open device stack is **permissive,
maintained and standards-current at the same time**: [`OpenRedButtonProject/orb`](https://github.com/OpenRedButtonProject/orb)
(**Apache-2.0**, 24★, pushed **2026-11-19**) is the world's only open-source HbbTV stack;
[`DVBProject/DVB-I-Reference-Client`](https://github.com/DVBProject/DVB-I-Reference-Client) (MIT,
74★, pushed **2026-11-17**) ships a back end for service lists plus **an HbbTV OpApp and an Android
PWA** as front ends; [`DVB-I-Reference-CSR`](https://github.com/DVBProject/DVB-I-Reference-CSR)
(MIT, 14★) is the discovery registry; [`HbbTV-Association/ReferenceApplication`](https://github.com/HbbTV-Association/ReferenceApplication)
(MIT, 90★) is the association's own app. **A complete, permissive, currently-maintained path from
service list to certified operator app exists only in this region.**

**Three deliverables.** (1) **The DVB-I aggregator build** — service list → CSR discovery →
HbbTV OpApp, all MIT/Apache, with 2.0.5's **GDPR consent and T&C gate** as a first-class feature
rather than a retrofit; OSN proves the commercial pattern on Samsung hardware. (2) **A 2.0.5
migration audit**: AV1/VVC and WebAssembly support plus formal DRM are new, the conformance suite
is **members-only and still being extended to 2.0.5**, so "is our app 2.0.5-ready" is a question no
client can self-answer — and membership or a registered test centre is a **line item, not an
assumption**. (3) **DMA-readiness positioning**: if smart TV platforms and virtual assistants are
designated, prominence, default placement and data access on the device become regulated surfaces,
and broadcasters will need both evidence and engineering. ⚠️ Keep EU AI Act Article 50 marking in
scope for anything the app itself renders — the disclosure has to appear **on the device**, and
nothing in the open TV stack implements it.
### Pass 33 (2026-11-27) — the media-monitoring & earned-media measurement layer in EMEA

- **⛔ The informed gap of this pass: Europe runs the world's largest public media monitor and ships
  none of its code.** The European Commission's Joint Research Centre operates **Europe Media Monitor
  (EMM)**: **~20,000 news sites, ~500,000 pages/day, 80 languages, 150 countries**, with clustering,
  multi-label classification, cross-script name-variant matching and topic detection/tracking, now
  with LLMs integrated. It partners with WHO on the EIOS epidemic-intelligence initiative, and its
  public applications sit at `media-monitor.europa.eu`. **Searched 2026-11-27: there is no public JRC
  EMM code repository.** It is an institutional system, not open source.
- **And the market is simultaneously demanding sovereignty.** The DPP's **European Media Trends 2026**
  report names AI the dominant driver of transformation *and* records a growing appetite for
  **digital sovereignty**. So the regional requirement — EU-resident, self-hosted, multilingual
  monitoring — is a **build**, not a procurement: the capable system is unforkable and the commercial
  systems are US-owned.
- **The substrate for that build is unusually good.** `changedetection.io` (Apache-2.0),
  `miniflux` (Apache-2.0), `rss-bridge` (Unlicense), `trafilatura` (Apache-2.0), `tika` (Apache-2.0),
  `story-indexer` (Apache-2.0) and `stanza` (Apache-2.0, 70+ languages NER) are all self-hostable and
  all permissive. **Multilingual entity resolution is solved permissively; multilingual *sentiment*
  is not** — see the LATAM subsection for the sharpest instance.
- **Regulation shapes the output, not just the hosting.** EU AI Act **Article 50** transparency duties
  apply to synthetic content a monitoring system might both detect and generate (briefs, summaries);
  the European Parliament adopted its position on the **AI Act Omnibus** simplification by **569–45**.
  DIGITALEUROPE is pressing for technology-neutral horizontal rules in the AVMSD evaluation.
- **The structural warning worth quoting to a client.** imec-SMIT (Vrije Universiteit Brussel) mapped
  Europe's AI media landscape and concluded that **adoption does not translate into control** — value
  is captured by whoever controls infrastructure, data, models, interfaces, rights and business
  arrangements. For this plane that is an argument for owning the corpus and the index, which is
  exactly the layer Europe currently rents.
- **Institutional buyers to approach.** The **EBU** convened its AI Forum in Brussels in March 2026
  focused on public service media; public broadcasters are the natural first buyers of a sovereign,
  self-hosted monitoring stack.
- **MENA, placed explicitly:** Arab media AI spending is projected at **~$520M in 2026**. Analysis
  from the region stresses that AI-in-media rules cannot be separated from existing privacy,
  misinformation and platform-responsibility regimes — a compliance-led sale rather than an
  efficiency-led one. ⚠️ MENA figure is region-specific; do not restate it as EMEA-wide.

### Pass 34 (2026-11-27) — the ad-integrity, supply-chain-transparency & verification layer in EMEA

**The region where the obligation is statutory, the deadlines are dated, and compliance is measurably
failing.** EMEA is the only region on this plane with hard law, and the enforcement gap is documented
in peer-reviewed research rather than vendor marketing.

- **DSA Article 39 advertising repositories: a measured 29% non-compliance.** A peer-reviewed study
  (ScienceDirect, 2026) found that **only 17 of the 24 services obliged to comply by April 2026
  (70.8%) actually provided a publicly accessible interface-based ad repository**, and concluded that
  the Commission has enforced other DSA obligations proactively while **ad-repository compliance has
  not been adequately enforced.** TikTok made **binding commitments on 2025-12-05** to improve its
  repository.
- **⏰ A live deadline that lands inside the next week.** The European Commission opened a **call for
  evidence on technical guidelines for DSA advertising repositories on 2026-11-04, closing
  2026-12-02.** Whatever those guidelines specify becomes the build target for every VLOP and VLOSE
  repository. **Opportunity, and it is time-boxed: a repository-conformance service** — ingest,
  completeness, queryability, retention — positioned before the guidelines land rather than after.
- **Political advertising is already in force separately:** the EU Transparency and Targeting of
  Political Advertising Regulation's **repository provisions apply from 2026-04-10**.
- **TCF's legal basis moved in the publisher's favour, and the engineering did not change.** The
  Belgian Market Court ruled on **2026-01-07**, annulling the Belgian DPA's validation of IAB Europe's
  TCF action plan and indicating that **IAB Europe should not necessarily be treated as a joint
  controller** for processing carried out for TCF purposes, since it has no influence over that
  processing. ⚠️ Read the consequence carefully before advising: relieving the *framework operator* of
  joint controllership does not relieve the *publisher and its vendors*. If anything it concentrates
  responsibility on the party running the CMP. **Opportunity:** consent-chain audits that establish who
  the controller actually is per data flow — demand rose, not fell, with this ruling.
  ⚠️ One vendor blog gives a **TCF 2.3 mandatory enforcement date of 2026-02-28**; unverified against
  an official source.
- **What is permissively buildable here, and it is more than anywhere else:**
  [iabtcf-es](https://github.com/InteractiveAdvertisingBureau/iabtcf-es) (Apache-2.0, 156★) for the TCF
  codec, [iabgpp-es](https://github.com/IABTechLab/iabgpp-es) (Apache-2.0, 37★) for the
  multi-jurisdiction GPP signal, [altcha](https://github.com/altcha-org/altcha) (MIT, 2,923★) as a
  **GDPR / WCAG 2.2 AA / EAA-compliant** human check that keeps the data in-region, and
  [cookieconsent](https://github.com/orestbida/cookieconsent) (MIT, 5,786★) for capture. ⚠️ **None of
  this yields a registered CMP** — a CMP ID from IAB Europe is required for a valid TCF string, and
  `consent management platform TCF` returns **six repositories in total.** Scope the difference
  explicitly: consent *capture* is buildable, TCF *participation* is a registration.
- **Direction of travel:** DoubleVerify reports fraud/IVT **down 45% YoY in EMEA** — the largest
  reported regional improvement anywhere, and vendor-sourced.

- **The graphics desk, pass 35 (2026-11-27): EMEA is the thinnest rig layer of the four regions, and
  that is the opening.** Scanning the public-broadcaster and publisher orgs for charting, mapping and
  graphics tooling returned almost nothing reusable. The most-starred EMEA artifact in the plane,
  [bbc/bbplot](https://github.com/bbc/bbplot) (an R/ggplot2 package for BBC-style charts, **1,645★**),
  has **no licence file on any branch** and **no push since 2021-07-02**. The only new EMEA library
  found is [ZeitOnline/scrolleo](https://github.com/ZeitOnline/scrolleo) (MIT, **9★**, 2026-11-26) —
  a dependency-free, ESM-only, typed modernisation of Scrollama, pushed the day before this pass.
  The Guardian open-sources its **entire production website** —
  [guardian/frontend](https://github.com/guardian/frontend) (Apache-2.0, 5,896★, 2026-11-26) and
  [guardian/dotcom-rendering](https://github.com/guardian/dotcom-rendering) (Apache-2.0, 277★,
  2026-11-26) — and still publishes no chart tooling. **Opportunity:** EMEA public-service media
  already behave as open-source *producers* in broadcast (Sofie, CasparCG, sisyfos — pass 22 of this
  KB). The graphics desk is the obvious next commission and nobody has taken it: a licensed,
  maintained, accessible EMEA chart-and-map component set, EBU-adjacent, the way Sofie was
  commissioned for playout.
- **Digital sovereignty is the budget line that pays for it.** The DPP's European Media Trends 2026
  report names AI plus a growing appetite for **digital sovereignty** as the forces reshaping European
  media strategy, and the sovereignty objection to cloud DAM — that standard tooling aggregates data
  on extra-European servers — **applies with full force to hosted chart embeds**, which are third-party
  JavaScript executing in the reader's browser on a page the publisher is legally responsible for.
  [protomaps/basemaps](https://github.com/protomaps/basemaps) (BSD-3-Clause) +
  [maplibre/maplibre-gl-js](https://github.com/maplibre/maplibre-gl-js) (BSD-3-Clause) give a
  **fully self-hosted basemap with no vendor key and no per-view call home** — a GDPR and sovereignty
  story, not merely a cost story. **This is the cleanest sovereignty-framed build in the plane.**
- **EU AI Act Article 50 reaches this plane through a side door.** An AI-generated chart is not
  usually a deepfake, but an **AI-generated chart *annotation* or an AI-written chart caption is
  synthetic text published as fact.** Any NL→chart agent deployed in an EMEA newsroom needs the same
  disclosure plumbing the generative-video work needs. **Opportunity:** extend the provenance ledger
  already scoped for North American digital replicas to cover agent-produced graphics copy.


#### Pass 36 (2026-11-27) — the 2D animation plane: **the region that funds the series and has not decided about the tool**

EMEA is where European 2D series are actually financed, and the 2026 figures are precise because the
market itself publishes them.

- **Cartoon Forum 2026** (Toulouse, 14–17 September): **66 projects** selected from **111 submissions** —
  61 TV series and 5 TV specials — with a **combined budget of €283.58M**. By country: **France 32,
  Ireland 6, Germany 5, Spain 4**.
- **Historical scale:** Cartoon Forum reports **1,053 animation series financed since 1990**, totalling
  **more than $4.43B**.
- **The direction of travel is harder, not easier:** Cartoon Media states financing is *increasingly
  difficult*, and added an initiative to reconnect producers with buyers and co-producers, plus a new
  **Ecoprod–Cartoon sustainability award**. Fewer projects, more companies, is how the trade press read
  the 2026 edition.
- **AI is explicitly unresolved, publicly.** Euronews (2026-07-12) reported AI as "the elephant in the
  room" at Annecy, Europe's biggest animation festival, with a French producer stating plainly that
  plenty of French studios **do not** use generative AI — while Amazon MGM Studios and AWS launched a
  fund to bankroll AI-made shows. Italian coverage reports a **€4M production funding call** due to open
  by November and a national training programme that deliberately **combines traditional animation
  practice with generative AI**.
- **Regulation:** EU AI Act **Article 50 transparency obligations apply from 2026-08-02** — the operative
  date for any AI-assisted European series in production now. The European Parliament voted **569–45** to
  adopt its position on the AI Act Omnibus simplification proposal. DIGITALEUROPE is pressing for
  technology-neutral horizontal rules rather than extending AVMSD sector rules.
- **Industry posture:** the DPP's European Media Trends 2026 names AI the dominant driver of strategic
  change and reports that **a quarter of European media companies have shifted toward building more
  in-house**, enabled by AI coding tools. An imec–SMIT (VUB) study (May 2026) argues value accrues to
  whoever controls infrastructure, data, models, interfaces, **rights** and business arrangements.
- **Recorded as unverified:** commonly-quoted incentive rates (France CNC rebate up to 30% of qualifying
  spend; UK Animation Tax Relief 25% of qualifying costs) come from a commercial guide in this pass's
  sources, **not** from CNC or HMRC primary text. Treat as indicative and confirm before quoting to a client.

**The engagement shape this implies.** A European co-production financed at Cartoon Forum must satisfy
Article 50 from August 2026 while working with partners who may contractually refuse GenAI. That is a
**per-production AI policy engine plus disclosure artifacts**, not a tooling project — and it pairs
directly with the plane's permissive base (OpenToonz BSD-3) because a disclosure obligation is far easier
to satisfy on a pipeline whose components you can read.

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

#### Development & pre-production — pass 17 (2026-11-26)

- **The only permissive, maintained agent in this entire plane is APAC-origin and APAC-shaped.**
  [neopen/story-shot-agent](https://github.com/neopen/story-shot-agent) (PenShot, **Apache-2.0**, 248★,
  pushed **2026-11-26**) turns a script into shot-level segments and video prompts, and its own
  description names its target formats as **film, anime, short drama (短剧) and novels**. That is not a
  Hollywood feature-film tool; it is built for the **microdrama** pipeline. Pass 17 found nothing
  comparable from any other region.
- **Why that is strategically significant rather than incidental.** Microdrama is the highest-volume
  pre-production workload in the world — hundreds of episodes per title, shot on schedules where
  breakdown and scheduling *are* the bottleneck. The **2026 APOS summit** (Hollywood Reporter) had AI as
  its main theme and seated **streamers, Indian conglomerates, Chinese tech platforms and AI-and-microdrama
  upstarts** at the same table, while **Variety** reports the **Asia-Pacific screen economy approaching
  $200B with a monetisation gap defining the decade.** The volume is here, the tooling is being written
  here, and it is being written permissively.
- **Regulation remains three different problems, not one.** **Latham & Watkins (September 2026)** sorts
  APAC AI regulation into divergent categories — binding risk-based frameworks (**South Korea's AI
  Framework Act**, which pairs business obligations with support measures such as public data sharing and
  R&D funding; **Vietnam**), and targeted rules (**China**). A third category is described only in
  truncated form in the source and **is not recorded here as a finding.** The consequence for this plane
  is unchanged from pass 16: the sellable asset is a **per-jurisdiction policy engine**, not a single
  compliance mode.
- **Public-broadcaster adoption is real but is pointed elsewhere.** The **Asia-Pacific Broadcasting Union
  (March 2026)** reports public broadcasters in **Australia and Singapore** testing AI for **newsrooms,
  archiving and verification** — none of which is pre-production. **Informed gap:** no APAC-specific
  pre-production or production-management adoption datum was located in this pass, and no APAC regulation
  touching the production office was found.
- **Opportunity — ranked first for APAC in this plane, which is unusual.** Everywhere else in this file
  APAC ranks behind EMEA. Here it leads, because this is the one plane where the region supplies both the
  volume **and** the permissive starting point. The asset is a **breakdown-and-scheduling layer for
  episodic short-form built on PenShot's Apache-2.0 base** — the segment where no incumbent schema fits
  (pass 16's finding) and where the shot list, not the stripboard, is the governing artefact.

#### Book, ebook & scholarly publishing — pass 18, measured 2026-11-26

**The asymmetry that defines this region: APAC has reading-access law aimed at *libraries*, not a
conformance duty on *publishers*.** Japan's **Reading Barrier-Free Act** (読書バリアフリー法, enacted
**June 2019**) encourages public libraries to collect and provide accessible reading materials so
that everyone can access printed culture regardless of disability. It **encourages** publishers to
produce accessible content; it does not impose the EAA's product-level obligation. That is the
single most important commercial distinction between EMEA and APAC in this plane.

**And the encouragement has visibly not been enough — by a major publisher's own admission.**
Kadokawa states that several years after the law, "the inclusive publication of books and the
improvement of accessibility **have not advanced sufficiently**" in published content such as
novels, comics and picture books. A self-assessment from one of Japan's largest publishers is
stronger evidence of a gap than any analyst estimate, and it is a stated commercial intent to close
it — the opening for a vendor is explicit rather than inferred.

**The adjacent mandate that does bite, and it has a date:** on **7 April 2026** Japan's cabinet
approved a bill to recognise **digital textbooks as official textbooks**, with a 2030 mandate
trajectory. Analysis ties the accessibility case directly to adjustable text size, read-aloud audio
and **automatic furigana** for children with dyslexia or visual impairment. **This is the APAC entry
point: the obligation arrives through education procurement, not trade publishing.**

**Market and content signals:**

| Signal | Detail |
|---|---|
| AI-generated content already winning commercially | An AI-generated YA comic topped the young-adult category on **Comic CmoA**, described as Japan's largest ebook platform, with the listing openly stating "This work was created using AI-generated images". The source notes it alarmed other creators |
| Public-domain corpus | **Aozora Bunko**: over **17,700 works** as of January 2026 — a clean, licence-safe Japanese-language corpus for pipeline development and evaluation |
| Copyright term | Japan extended to **70 years** on 30 December 2018, tied to the EU–Japan trade agreement — relevant to any public-domain-based offer |
| Training-data pressure | A Japanese book distributor reportedly agreed to supply large volumes of physical books to an AI company for scanning; a publishing expert quoted argues **resale rights** may be the more consequential legal question |

**Key open-source player anchored in this region:** **Vivliostyle** (`vivliostyle/vivliostyle.js`,
**AGPL-3.0**, last commit 2026-11-24) — a Japanese-origin CSS typesetting engine and the best open
answer for **CJK vertical writing, ruby/furigana and complex layout**. It is also the clearest
licence trap in the region: the one engine that solves the hardest APAC typography problem is
**network copyleft**, so it belongs in a separately deployed rendering service, never linked into a
client's proprietary product.

**Opportunity, specific to this region:** the buyer is the **education publisher and the textbook
supplier**, driven by the 2026 digital-textbook decision and its 2030 trajectory — not the trade
publisher, who faces no conformance duty. The differentiating capability is **Japanese-language
accessible production**: furigana generation, vertical-writing EPUB, read-aloud alignment. Vivliostyle
(AGPL) handles layout behind a service boundary; `daisy/pipeline-modules` (LGPL) handles TTS and
DAISY output; `epubcheck` (BSD-3) and `ace` (MIT) validate. **Globant's differentiator here is
language and script competence, not compliance pressure** — the reverse of the EMEA pitch, and it
should be sold that way.

**Informed gaps — searched, and genuinely not found:**
- **No ebook accessibility regulation located for Korea or China.** Searched in English; nothing
  returned on either country's rules for ebooks or digital publishing accessibility. This is a real
  hole, not an absence of regulation — it needs searching **in Korean and Chinese**, and against
  each country's disability and publishing statutes directly. Flagged for a future pass.
- **No APAC-wide AI-adoption figure for publishing** comparable to the NA BookNet/BISG 63%. The NA
  number must not be reused as a proxy for this region.
- **No India/ANZ-specific finding** emerged from the regional search despite both being substantial
  English-language publishing markets.

#### Sports media & live events — pass 19 (2026-11-26). The region whose **sports are absent from the open-source stack**

- **Cricket is the money, and the numbers are large.** The **IPL's 2023–2027 cycle is valued at
  approximately INR 48,390.32 crore (US$5.23bn)**, and in **July 2026 JioStar acquired exclusive
  Indian rights to all 68 matches of The Hundred**. The Asia-Pacific screen economy is described as
  racing toward **$200bn**, with the **monetisation gap defining the decade** — this file records
  that framing at pass 5 and it applies with full force to sport.
- **Adoption is second only to North America.** APAC is reported as adopting generative AI faster
  than every region except NA. The **ABU** reports public broadcasters in **Australia and Singapore**
  testing AI for newsroom workflows, archiving and verification — all three of which are sports
  workloads at a broadcaster that carries live sport. **APOS 2026 (Bali)** ran AI as its central
  theme.
- **Regulation does not converge, and that is the design constraint.** Latham & Watkins (September
  2026) groups the region into divergent categories — binding risk-based frameworks (**South Korea**,
  **Vietnam**), targeted rules (**China**), and others — with a recent acceleration in AI legislation
  across APAC. This file's cycle-8 conclusion holds and extends here: **the sellable asset is a
  policy engine keyed by jurisdiction, not a single compliance mode.** Content labelling and
  disclosure is the recurring specific obligation across the nine-country overviews.

**Opportunity, specific to this region, and it is the sharpest placed finding of this pass:** the
entire open-source sports stack is **football-first and essentially football-only**. Every
foundational component recorded in `repos/foundations.md` was built for association football —
`SoccerNet/*`, `PySport/kloppy`, `mplsoccer`, `penaltyblog`, `UnravelSports` — with American sports
covered by the R cluster (`nflfastR`, `hoopR`, `cfbfastR`). **Cricket, kabaddi, sumo, Australian
rules and the Asian baseball leagues have no equivalent at any star level.** Cricket is the
second-most-watched sport on earth and anchors a $5.23bn rights cycle, and its open tooling is a
blank.

That gap is addressable rather than merely noted, because the generic layer transfers: detection,
tracking and pose (`supervision` MIT, `trackers` Apache-2.0, `mmpose` Apache-2.0, `Sports2D` BSD-3)
are sport-agnostic. What is missing is **sport-specific geometry, event taxonomy and state
machines** — pitch/crease calibration, over and innings structure, dismissal types. That is a
well-bounded build on permissive foundations, and it is defensible IP in the region that has the
largest unserved rights market.

**Informed gap:** no APAC-origin open-source sports analytics project was located. The one APAC
corporate contribution found in this plane is **`line/lighthouse`** (LINE, Apache-2.0, 274★) for
video moment retrieval — not sports-specific, but the most research-credible highlight component in
the plane and a live indication that the capability exists regionally.


#### Investigative journalism & source protection — pass 20 (2026-11-26). **The region where journalism is nearly absent from AI law — measured, and the number is 2 of 23**

**The regulatory finding, and it is the hardest number in this pass.** A CNTI review of East Asia and
Pacific AI policy proposals found that of **23 proposals reviewed, only 2 specifically mention
journalism**, and that Fiji, Laos, Mongolia and Myanmar have begun planning for AI regulation without
publishing official documents. CNTI's warning is the operative part: the absence of clear rules,
**especially in jurisdictions with lower press freedom**, can make it harder for journalists both to
report on AI and to use it. Regional coordination is slow — an ASEAN policy brief (April 2026)
records that policymakers recognise the need for cooperation on media regulation while progress
remains slow — and **Australia's ACMA published an AI in media report in April 2026** with a section
on news-media adoption.

**Adoption is fragmented by newsroom size, language and infrastructure**, with reporting that more
than **80% of Southeast Asia** remains at an early adoption stage. In the Philippines most news
organisations adopted AI in the early 2020s, private outlets leading. At the **India AI Impact Summit
(February 2026)** the Digital News Publishers Association argued that journalism should not be
treated as free input for AI systems — the same reservation-of-rights argument pass 5 placed in EMEA,
arriving here as an industry position rather than a statute.

**The one component in this plane with proven APAC deployment at scale is a tipline.** Meedan's
**Check** (`meedan/check` 131★ MIT — the dev environment; **`meedan/check-api` 21★ MIT, pushed
2026-11-24** — the actual backend) ran WhatsApp tiplines with AFP, BOOM, India Today and Africa
Check, including roughly **335,000 questions across four WhatsApp tiplines** during India's 2021
election cycle, with Meedan reporting Check tiplines supporting 34 languages and dialects across 58
tiplines. For an APAC engagement this is a **proven starting point, not a greenfield build** — and
the multilingual requirement is the part most likely to be underestimated.

**Opportunity, specific to this region — and it is the same shape pass 8 found, now confirmed on a
second plane.** With 23 jurisdictions diverging and only 2 naming journalism, the sellable asset is a
**policy engine per jurisdiction**, not a single compliance mode: one deployment, per-country rules
for what may be automated, what must be disclosed, and what must never leave the country. Pair it
with the Pattern 40 chain, because in lower-press-freedom jurisdictions **self-hosting is a safety
requirement, not a procurement preference** — and `Horizontal-org/Tella-Android` (MIT, offline-first,
hides files on-device) exists precisely for the case where the device may be inspected.

**Informed gap:** `cnti.org` and `acma.gov.au` do not resolve from this session. The "2 of 23" figure
and the ACMA report's contents are **from search snippets, not read at source** — verify the CNTI
report directly before putting that number in a client deliverable. No APAC-specific open
source-protection or fact-checking project was found; the tools deployed in the region are built
elsewhere, which is itself the regional gap.

**Pass 21 (2026-11-26) — the spatial, immersive & volumetric plane.** APAC is the growth region on
every source consulted: one analyst projects a **~41% CAGR for 2027–2032**, the fastest of any
region, against North America's larger current base. Regional volumetric-video figures are smaller
and more concrete than the global ones: **USD 1.16B (2025) rising to USD 1.52B (2026)** for APAC, with
country-level 2026 estimates of roughly **USD 0.381B (China)**, **USD 0.323B (Japan)** and
**USD 0.202B (India)**. These come from market-research summaries and do not reconcile with the global
totals, so use them for relative weight, not as absolutes.

**Country roles, as reported.** **China**: volumetric activity attached to 5G build-out, live
commerce, virtual influencers and smart-venue experiences — the highest-volume applied market.
**South Korea**: strong 5G penetration, esports, virtual production and immersive broadcasting
readiness, with continued **government-backed spatial-computing development** cited for 2026.
**Japan**: demand tied to gaming, entertainment and creator tooling, with public programmes (the MITOU
programme recognised XR projects in 2025) as a funding route.

**Regulation: little published, and that is the finding.** No XR-specific statute in any APAC market
surfaced in this pass's searches. What is documented instead is **government funding and industrial
policy** as the lever — China and Japan supporting immersive development through programmes rather
than rules. The practical consequence for a proposal is the inverse of EMEA: the asset is not a
compliance profile but **alignment with a funded programme**, and the buyer is often a
public-private consortium rather than a studio.

**Opportunity, specific to this region: the temporal layer, built where the capture volume already
exists.** APAC has the live-commerce and virtual-influencer volume that makes a moving-subject capture
pipeline economically rational, and this is precisely the layer the open stack does not serve:
`hustvl/4DGaussians` (Apache-2.0, 4,047★) has been **dormant since 2024-10-27**, and the only
permissive active 4D production pipeline, `ASU-NEM-Labs/open4dgs-core` (MIT), stands at **161★**. A
regionally-built 4D pipeline on a permissive base — Pattern 45 — has a clearer buyer here than
anywhere else, and Korea's virtual-production and immersive-broadcasting capacity is the natural
delivery partner.

**Informed gap.** The strongest 4D research codebase in the plane, `zju3dv/EasyVolcap`, and its
companion `zju3dv/EasyMocap`, are **APAC-origin** (Zhejiang University) and carry the new **PRL v1.0**
registration gate. If this licence shape spreads among Chinese and Japanese university labs — which
is plausible, since it preserves commercial adoption while telling the lab who its users are — then
**APAC becomes the region where the registration step is a routine part of engagement setup**. Watch
for it; it is currently one lab.


**Pass 22 — the podcast plane, and APAC is the growth case with the thinnest regulatory and
open-source story.**

- **The growth is the opportunity, and it is early-stage.** Vendor forecasts put APAC at the
  highest regional growth rate for podcasting — **KBV Research: 26.0 % CAGR 2024–2031, India 26.7 %,
  Japan 25.3 %**, with China the largest market by value. **India's listenership is reported to have
  risen 22 points in one year to 52 % (2025)**, and YouGov's 2025 data has **Indonesia at 59 % of
  consumers listening ≥1 h/week, with Thailand and India at 54 %**. These are paid-research and
  survey figures on different bases and **they do not reconcile with each other** — use them as
  direction, not as a number in a model. The recurring obstacle named in the same sources is **low
  consumer awareness**, not capacity.
- **First opportunity: the white-label client, and it is a licence problem before it is a product
  problem.** APAC growth is app-mediated — commuter-friendly short episodes, telco and OEM bundles,
  Japanese corporates running branded shows with executive hosts. Every living open podcast app is
  **GPL-3.0 or AGPL-3.0** (`AntennaPod` 8,357★, `PodAura` 1,278★, `Podverse` ×5, `gpodder`,
  `PinePods`, `musicpod`), so the default engineering instinct — fork the best Android client —
  **makes the client's app disclosable** and is incompatible with most OEM and carrier deals. The
  only living permissive base in the plane is **`amugofjava/anytime_podcast_player` (BSD-3-Clause,
  627★, Flutter)**. For this region that single row is the most commercially consequential line in
  the pass: it is the difference between a shippable white-label and a legal dead end.
- **Second opportunity: vernacular audio at catalogue scale.** The generation layer is permissive
  and runs locally — `podcastfy` (Apache-2.0), `video-podcast-maker` (MIT, local TTS, no external
  API), `autoclip` (MIT) — which suits markets where per-call API economics do not work and
  multi-language output is the whole product. Pairs with the localization plane (pass 14).
- **Informed gap, stated explicitly.** Searches for **podcast or audio-platform regulation in India,
  Japan and China returned nothing podcast-specific.** No disclosure rule for synthetic hosts, no
  measurement standard, no platform duty surfaced for this plane. The nearest adjacent hook is the
  **four synthetic-media labeling regimes pass 21 recorded for this region** — which would, if read
  across, reach an AI-voiced podcast, but **no source in this pass says so**. Written down as a gap
  because silence here looks exactly like coverage: an APAC engagement should treat labeling as
  *probable and unconfirmed*, and check the national rule before committing to a disclosure design.

- **China has the world's strongest image-provenance mandate, and it maps almost one-to-one onto the
  open toolchain in this plane.** The **Measures for Labeling of AI-Generated Synthetic Content**,
  issued 14 March 2025 by four agencies and **in force since 1 September 2025**, together with the
  **mandatory national standard GB 45438-2025**, require two kinds of label on AI-generated content
  **including images**: an **explicit** label (a visible notice) and an **implicit** label
  **embedded in the content's metadata**. Obligations fall on generation-service providers,
  content-propagation platforms, app distribution platforms **and users**; platforms must **check
  for implicit labels**, users must proactively declare AI content, and **maliciously deleting,
  tampering with, forging or concealing the identifiers is prohibited.**
  **This is the single clearest commercial opportunity in the still-image plane in any region.**
  An "implicit label" is metadata written into an image file — which is precisely `exiftool`
  (Artistic/GPL, and the permissive option is available) plus `c2patool` (Apache-2.0/MIT) plus a
  verification gate on ingest. The obligation is binding, the tooling is permissive and mature, and
  the open provenance stack has **629 stars worldwide**.
- **The adversarial tool is better resourced than the compliance tool.** The most-starred on-topic
  result for `image metadata agent` is `wiltodelta/remove-ai-watermarks` (**6,530★, Apache-2.0**) —
  a tool for stripping exactly the identifiers the Chinese Measures forbid removing. It out-stars
  the entire open C2PA implementation by roughly ten to one. Any APAC compliance proposal should
  assume label-stripping is easy and widely tooled, and argue from **capture-side signatures and
  platform-side verification** rather than from metadata durability.
- **The rest of the region is diverging, not converging.** A Latham & Watkins alert (September 2026)
  sorts APAC into **binding risk-based frameworks** (South Korea, Vietnam) versus **targeted rules**
  (China). **Vietnam's dedicated AI law, Law No. 134/2025/QH15, took effect 1 March 2026.** A
  nine-country survey finds the common threads are high-impact systems, **labeling of generative AI**
  and human oversight. **Consequence for delivery:** a regional client cannot ship one labeling
  configuration. Build the label writer once and make the *regime* a per-market policy object.
- **Players to expect in the room:** Tencent (Tencent Video), Alibaba, Baidu, Naver, Samsung,
  ByteDance, Sony, and iQIYI — with Tencent Video and iQIYI named as investing in generative media.
  Adoption is strongest in China, India and Southeast Asia and slower in the mature markets.
- **Informed gap.** This pass found **no APAC rule specific to news photography or print
  production**, and **no Japanese or Indian image-labeling instrument** — China's Measures and
  Vietnam's law were the only binding image-reaching rules located. Japan and India are recorded
  here as **unverified, not as permissive**: absence of a found rule is absence of evidence.

#### The owned-channel & audience-relationship plane — added 2026-11-26 (pass 24). The region where the owned channel is a messaging app, and there is no open tooling for it

- **The regulatory direction is acceleration.** Latham & Watkins (September 2026) records a
  **significant acceleration in the enactment of AI regulation across APAC** over the preceding
  12 months. BowerGroupAsia's Indo-Pacific overview notes that several countries have introduced
  **mandatory AI-content labelling** since 2025, and that compliance duties may land on **AI
  developers, online intermediaries, advertisers, publishers and press agencies** depending on the
  market. Unlike EMEA, there is **no single consent framework to implement** — the obligations are
  per-market and labelling-shaped.
- **The audience behaviour that defines the plane here:** users spend **more than 50% of their time in
  messaging and social** (DigiconAsia). An ASEAN policy brief records regional players — **LINE**
  (Thailand) and **Zalo** (Vietnam) — **disrupting traditional media distribution and advertising
  models**, while noting that regional media regulation moves slowly. **Malaysia** required major
  messaging and social platforms to be **registered from January 2026**. In Korea, **KakaoTalk**
  carries news channels and most readers get news from domestic platforms (**Naver, Kakao**) rather
  than from publisher sites.
- **So the "owned" channel in APAC is rented.** LINE's publisher-relevant inventory spans the chat
  list, the VOOM feed, LINE News and the wallet tab. A publisher's reachable audience in Thailand,
  Japan or Korea sits inside a platform account, not an email list — which **inverts this plane's
  thesis** for the region: the email/push stack in `repos/foundations.md` is necessary but not
  sufficient here, and the Pattern 24.1 "reachable audience" metric must count **platform followers as
  a separate, non-portable class** with its own risk note.
- **AI-assisted discovery is already mainstream with consumers, and trust is the constraint.** Kantar's
  **Media Reactions 2026** finds roughly **one in three APAC consumers use AI to research brands and
  products** (varying considerably by market), while only **20% trust brand recommendations from AI
  assistants** against **24% for influencers and creators**. *Methodology changed in that study — do
  not compare its rankings with earlier years.*
- **Opportunity 1 — the non-portable-audience audit.** For an APAC publisher, the deliverable is
  sharper than in any other region: *how much of your audience exists only inside LINE, Kakao or
  Zalo, and what happens to it if the platform changes terms?* Build it on Unomi (Apache-2.0) with
  platform-follower counts as a distinct profile class. No open tooling does this; it is pure
  integration work, which suits a studio engagement.
- **Opportunity 2 — labelling-aware editorial digests (Pattern 24.5).** Because APAC's duties are
  labelling-shaped rather than consent-shaped, the human-approval gate in Pattern 24.5 is the compliance
  artefact that matters most here, and it is cheap to implement.
- **Opportunity 3 — localization adjacency.** APAC is the **fastest-growing media-localization region
  at 12.3% CAGR** (DataIntelo, recorded in this file's pass-22 addendum) and the localization open
  stack is ~80% complete (trend 7). A multilingual owned channel — one digest, many languages, one
  consent record — is the composition of pass 14's plane with this one.
- **⚠️ Informed gap, and it is a large one.** Searched specifically for **2026 publisher metrics on
  LINE, KakaoTalk and Zalo** as distribution channels: **nothing current found.** The available
  publisher evidence is from the mid-2010s and must be labelled historical — The Economist's LINE
  account reached nearly 1 million followers with popular posts driving roughly as much referral
  traffic as its Facebook presence, and LINE's then-cited 212 million MAU is **outdated**. On **Zalo
  specifically, nothing relevant surfaced at all.** And there is **no open-source WhatsApp/LINE
  publisher-distribution tooling** in existence — searched, genuinely absent. An APAC messaging
  engagement is therefore built on **platform APIs under platform terms**, with no open substrate to
  fall back on: price the platform risk explicitly.



#### The traffic, sales-order-to-air & billing plane — added 2026-11-26 (pass 25). The region where the break is addressable per household, which makes reconciliation a *harder* problem, not an easier one

> Non-repo facts from web-search extracts; publisher domains (`lw.com`, `asiatechxsg.com` and others)
> were **outside this session's allowed network domains**. Marked **†**.

- **The adoption shape: operational, not generative — and it lands on this plane.** APAC broadcast AI
  adoption is described as **practical rather than generative**, with **AI recommendation engines
  deployed for live linear broadcasting, tailoring content and advertising to individual households
  via addressable-TV technologies**.† That is a traffic statement: **a household-addressable break
  cannot be reconciled with a single as-run line.** The more addressable the inventory, the more the
  missing step in this plane becomes the binding constraint.
- **Integration is shallower than the announcements suggest.** Only **~30% of agencies, brands and
  publishers had fully integrated AI across the media campaign lifecycle in 2025**, with many
  intending to during 2026.† Sell the plumbing, not the transformation.
- **Regulation is per-jurisdiction, so the asset is a policy engine — the pass 5 finding, instantiated
  on the traffic desk.** The regional landscape as of mid-2026 is characterised as **a patchwork of
  three broad approaches** (Latham & Watkins).† Specifics:
  - **South Korea** requires realistic synthetic video or audio to be labelled so users can
    **"clearly recognise"** its AI origin; MSIT has signalled **2026 as effectively a pilot period
    with limited enforcement**.†
  - **India** amended its **IT rules in February 2026**, placing obligations on platforms hosting
    AI-generated content.†
  - **China** operates layered, targeted rules; **Vietnam** has issued a decree.†
- **Opportunity 1 — the per-jurisdiction labelling policy engine, wired into booking (Pattern 25.4).**
  A broadcaster or platform operating across KR/IN/CN/VN cannot run one compliance mode. The sellable
  asset is a **policy object per jurisdiction** (what must be labelled, how, from when, what evidence
  to retain) attached to the campaign and enforced at placement. **This is the same asset pass 5
  identified for APAC rights reservation — the second plane in which APAC's answer is a policy engine
  rather than a compliance setting, which makes it a regional pattern rather than a one-off.**
- **Opportunity 2 — addressable-break reconciliation (Pattern 25.1, hard mode).** Per-household
  delivery means reconciliation moves from "did the spot air" to "which households were served, and
  does that match what was sold". [openmeterio/openmeter](https://github.com/openmeterio/openmeter)
  (Apache-2.0, 2,471★) is the permissive metering substrate for the impression side; the matching
  policy is the client's IP.
- **Market context.** Generative AI in APAC media and entertainment is projected from **~$1.97 bn
  (2024) to ~$20.7 bn (2034)** per one study, and regional **digital ad spend is on a path to
  $489.3 bn by 2029**, with AI in campaign execution named as a growth driver.† Treat both as
  single-source ranges. **SMPTE ST 2110** is described as firmly established as the IP broadcast
  standard in the region† — relevant because an ST 2110 facility has the signal plumbing to support
  addressable insertion and still no commercial system to settle it.
- **Informed gap:** results named **innovation hubs (Shenzhen, Seoul, Hyderabad)** and tech-readiness
  leaders (**Singapore, Japan, South Korea**) but **no specific APAC traffic/ad-sales vendors**.† The
  incumbent vendor map for APAC broadcast traffic is **unresearched** — do not assume WideOrbit and
  Imagine hold the region as they do North America.

#### Pass 26 addendum (2026-11-26) — the energy & carbon plane: albert's methodology travelled here, and the regulation arrives from outside the sector

- **Australia is the region's developed case, and it is an albert derivative.** **Sustainable Screens
  Australia** partnered with BAFTA albert and **localised its carbon calculator for the Australian
  market**, then launched the country's first **Sustainability Supervisor** training programme in 2025,
  backed by **Netflix** and **Screen Australia**. Production-level practice is visible and specific: the
  Melbourne feature *Wilderness* tracked emissions using **HVO renewable diesel** and battery-powered
  lighting and generators; **Disney Studios Australia** was recognised at the **2026 Global Production
  Awards** as the first studio in Australia to install solar.
- **Korea and Japan are regulated, but not as media.** Korea announced in **July 2026** that large
  companies must align with the **ISSB's IFRS S1 and S2** standards from **FY27**. Japan's **GX-ETS**
  has entered its mandatory phase, covering an estimated **300–400 companies** by direct CO2 emissions.
  Neither instrument is sector-specific, so for a large Korean or Japanese broadcaster the driver is
  **group-level sustainability reporting**, not a commissioning condition — a different buyer, in
  finance rather than production.
- **Opportunity — the methodology-localisation pattern, now proven.** Australia demonstrated that
  albert's framework can be re-based onto local emission factors and accepted locally. That is a
  repeatable engagement shape for any APAC market with a growing screen sector and no national
  calculator, and it is **data and methodology work, not platform work** — which is fortunate, because
  the platform does not exist to fork.
- **Opportunity — ISSB-shaped disclosure for media groups.** Korea's FY27 date is a hard planning
  horizon announced in 2026. A media group needs its energy and emissions data assembled and auditable
  before then, and the open toolchain for the infrastructure half ([kepler](https://github.com/sustainable-computing-io/kepler),
  [scaphandre](https://github.com/hubblo-org/scaphandre), [cloud-carbon-footprint](https://github.com/cloud-carbon-footprint/cloud-carbon-footprint))
  is permissive and mature.
- **Regional scale, for sizing a practice:** the Asia Pacific Screen Forum projects the regional screen
  economy at **$179 billion in 2026**, rising to **$200 billion by 2031**, and its 2026 edition carries
  an explicit sustainability theme.
- **⚠️ Informed gaps, stated rather than left silent.** Searches for sustainable *film production*
  practice in **Korea and Japan** returned **regulation only and nothing sector-specific**; any claim
  about adoption in those two markets would be invention. The same search surfaced unrelated
  "carbon film" manufacturing reports (heating film, protective film) — **a false-friend query class to
  avoid**: use *screen production* or *audiovisual*, never *film*, when searching this plane in APAC.


#### The production-finance & soft-money plane — added 2026-11-26 (pass 27). The region with the cleanest primary sources and the least verifiable trade press

- **Australia is the best-documented incentive regime found in any region, and the source is the tax
  authority itself.** The **ATO**'s *Film industry incentives 2026* confirms the **Location Offset
  rose to 30%** of qualifying Australian expenditure (Treasury Laws Amendment … Act 2024), with the
  **Producer Offset at 40% for features and 20% for other formats**. Ausfilm and Screen Australia
  publish current factsheets alongside it. ⚠️ **Any source still citing 16.5% for the Location Offset
  is out of date** — a live trap, since older aggregator pages remain highly ranked.
- **Japan changed instrument, not just rate, and the old one is closed.** **JLOX+** (reported at 50%
  with a ¥1B cap) **closed to applications on 2026-01-31**. Support now runs through **IP360**, which
  subsidises **half of eligible Japanese production spend**, capped at **¥1.5B per project**, and
  requires at least **¥800M of domestic spend**. A minimum-spend floor of that size is an eligibility
  *gate*, not a sliding scale — exactly the kind of rule a decision table expresses well and a
  spreadsheet expresses badly.
- **India and South Korea: informed gaps, and they are the honest answer.** For **India**, sources
  conflict — one reports the federal incentive rising from 30% to **40% reimbursement in 2026** with a
  **$3.6M cap**, another gives 30–40% with a ₹30,000,000 minimum spend, and **no official source was
  found confirming a 2026 change**. For **Korea**, **no 2026 rate change was found at all**; a
  directory lists a 25% cash rebate with a ₩400,000,000 minimum, and its KOFIC detail is vague and
  unverified. **Both are recorded as unverified rather than written as data.** Needed next:
  India's Ministry of Information & Broadcasting and **KOFIC** primary pages.
- **Regulatory context for the same region, carried from pass 5 and still the governing frame.** The
  Latham & Watkins alert of September 2026 groups APAC into **three divergent regulatory categories**
  (binding risk-based frameworks — Korea, Vietnam; targeted regulation — China; and a third), which
  means an APAC incentive engine and an APAC AI-compliance engine have the **same architecture**: a
  per-jurisdiction policy engine, not a single compliance mode. The same Catala/Drools substrate
  serves both, which is a genuine reuse argument for a regional engagement.
- **The opportunity, placed.** APAC pairs the region's **best primary-source hygiene** (ATO, KOFIC,
  Screen Australia) with the **worst aggregator reliability**, and two of its four major markets
  switched or capped instruments inside twelve months. The defensible build is a **versioned,
  citation-carrying rule set** where every number links to the government page it came from and
  carries a commencement date — which is precisely what Catala's literate style produces by
  construction, and precisely what a spreadsheet cannot.

#### The age-rating & classification plane — added 2026-11-26 (pass 28). The region that is enforcing hardest, with the most divergent ladders and a private-standard trap in Japan

**Australia — the live enforcement case, and the most consequential one anywhere:**

- The **under-16 social-media ban took effect 2025-12-10**. Platforms must take "reasonable steps" to
  keep under-16s off; the named services include YouTube, Instagram, TikTok and Snapchat. **Penalties
  reach A$50M and fall on companies, not families.**
- **It is being tested in court:** Reddit and a Sydney rights group have challenged the ban, and the
  Australian government defended it in court in **November 2026**.
- **The government has conceded the circumvention problem** — an Al Jazeera report of November 2026
  records the admission that many under-16s still reach social media by getting around
  age-verification processes. **This is the most useful sentence in the region for a client
  conversation:** the regulator has publicly accepted that the control under-performs, which moves
  the discussion from *whether* to assure age to *how to evidence reasonable steps.*
- **The ladder matters here and the open mapping cannot express it.** Australia's National
  Classification Scheme has **8 rungs** including **`RC` — Refused Classification**, which forbids
  distribution. AppStream's Australian projection carries **3** and **cannot represent `RC` at all.**

**South Korea — a 2026 change with direct product consequences.** Per Microsoft's publishing
guidance, **before January 2026 the GCRB could only rate titles below 19+; it has since expanded to
rate 19+ alongside GRAC.** For digital-only content **IARC ratings can apply unless the title is
rated 19**, which requires a GRAC rating. On the film side, **the 19 rating replaced the 18 rating on
2024-05-01, retrospectively.** Sources conflict on the bodies' names and histories (GCRB / GRAC /
GRB / KMRB) — **resolve the body before quoting the ladder.** The dataset's `KR_KMRB` entry carries
12 label entries across `전체 관람가 / 12 / 15 / 19 / 청소년 관람불가`.

**Japan — the trap in this region, and it is a licence-shaped one.** Eirin operates four categories
(`G`, `PG12`, `R15+`, `R18+`), but **Eirin classifications do not automatically apply to TV or video
channels: those outlets reference Eirin ratings and maintain their own internal standards.** So for
Japanese VOD **the operative rating is a private standard**, and there is nothing public to implement
against. An engagement that assumes a national VOD ladder exists in Japan will not find one — budget
for per-broadcaster rule capture instead.

**Singapore — the clearest obligation to implement.** IMDA requires pay-TV and video-on-demand
services to offer a **PIN-based parental lock** restricting NC16 and M18 content. The open mapping's
Singapore ladder (`General, ADV, M18`) is the shortest of the 16 and does not carry NC16 — another
instance of projection loss, in the one APAC market with an explicit technical mandate.

**Informed gap, recorded rather than left silent:** no 2026 official rule was found on how KMRB or
GRAC ratings apply to **streaming services** specifically, and nothing on Eirin VOD classification.
The searches that returned nothing relevant were `KMRB streaming rating 2026` and `Japan streaming
age rating`; the board sites (`kmrb.or.kr`, `grac.or.kr`, `eirin.jp`) were **not** reachable or
checked from this session. **Treat Korea-streaming and Japan-VOD as not investigated, not as absent.**

**Opportunity (APAC):** a **per-jurisdiction policy engine** — the same conclusion pass 5 reached for
this region, now confirmed from a second direction. APAC's ladders diverge more than any other
region's (8 rungs in Australia, 4 in Japan, a contested set in Korea, 3 in Singapore), one major
market runs on private broadcaster standards, and the Australian regulator has conceded its control
under-performs. **The asset is a rules engine with a per-market ruleset and an evidence trail, not a
compliance mode.**

#### The interactive, branching & playable-story plane — added 2026-11-26 (pass 29). **The region that owns the open source and already regulates AI-assisted interactive content**

APAC is the only region where this plane's open source, its commercial format and its regulation are
all live at once.

**The open source is APAC's.** Two of the four leading visual-novel engines are CN-origin with
bilingual documentation — [WebGAL](https://github.com/OpenWebGAL/WebGAL) (MPL-2.0, 4,054★) and
[VoidNovelEngine](https://github.com/VoidmatrixHeathcliff/VoidNovelEngine) (MIT, 1,715★) — as is the
interactive-avatar tier: [LiveTalking](https://github.com/lipku/LiveTalking) (Apache-2.0, 11,338★),
[OpenTalking](https://github.com/datascale-ai/opentalking) (Apache-2.0, 3,421★),
[OpenAvatarChat](https://github.com/HumanAIGC-Engineering/OpenAvatarChat) (Apache-2.0, 3,907★). The
avatar *format* is APAC's too: [UniVRM](https://github.com/vrm-c/UniVRM) (MIT, 3,432★) and
[three-vrm](https://github.com/pixiv/three-vrm) (MIT, 2,309★). Japan's AI-character production
tooling is real but licence-trapped: [aituber-kit](https://github.com/tegnike/aituber-kit) (1,149★)
is **non-commercial by default**, and [pixiv/ChatVRM](https://github.com/pixiv/ChatVRM) (MIT, 847★)
is **archived**.

**The regulation is already in force, and it covers AI *assistance*, not just AI generation.** Korea's
**AI Basic Act** took effect **2026-01-22** and is described as the first in Asia to impose mandatory
disclosure on AI-generated **or AI-assisted** content, reaching every service that counts Korea as a
market — including Webtoon, Tapas and Tappytoon — with watermark disclosure under a **one-year grace
period** for webtoon creators and platforms. Concrete standards are still missing for synthesising an
actor's face or a singer's voice and for training-data use; where AI is used for only *part* of
production, the disclosure level is left largely to self-regulation and private contracts.

**Adoption is split between the firm and the creator, and the numbers are far apart.** A 2025 labour
survey found **34.1% of content businesses** formally incorporate AI, and a separate report puts AI in
content production at **1 in 3 companies**. But KOCCA's 2024 survey of **800 webtoon artists** found
only **18.3%** had ever used generative AI and only **36.1%** intended to. Naver Webtoon's *Toon
Filter* drew organised artist objection, and Korean cartoonists took AI consent and copyright demands
to UNESCO in **October 2026**. Export concentration matters commercially: **49.5% of K-webtoon
exports go to Japan**.

**The structural gap.** Korea mandates disclosure of **partial** AI assistance, and the plane's
tooling has no concept of partial provenance: no open webtoon or VN pipeline records *which panels,
lines or frames were AI-assisted*, at what stage, under whose consent. The duty is per-asset and
graduated; the tooling is per-file and binary.

**Opportunity (APAC):** a **partial-assistance provenance pipeline for serialised interactive content**
— per-panel/per-line assistance records, consent references for any likeness or voice, watermark
emission under the Korean grace period, and a disclosure artefact that survives localisation into
Japan (where half the exports go). The buyers are the webtoon and VN platforms already inside the
Act's reach; the open substrate (VRM, WebGAL, Ren'Py) is permissive; and the piece nobody has built is
the **graduated** record. Build it on the MIT/MPL engines, and keep `aituber-kit` and `Duix-Mobile`
out of the delivery — both are non-OSI licensed.


### Pass 30 (2026-11-26) — the answer-engine discovery layer in APAC

The region with the clearest **demand-side** case for answer-engine presence and the **thinnest
referral measurement** — and this pass must record the measurement gap explicitly.

| Finding | Source |
|---|---|
| **Australian publishers report a double-digit decline in search traffic** attributed to new AI models | **AdNews** |
| Framing: *"the great clarification"* — publishers **trading reach for relevance**, shifting from volume to **value-based audiences** | AdNews |
| **~1 in 3 APAC consumers use AI to research brands and products**, varying considerably by market | Kantar |
| Public broadcasters in **Australia and Singapore** testing AI for newsrooms, archiving and verification | ABU (Asia-Pacific Broadcasting Union) |
| **Three divergent regulatory categories** — binding risk-based tiers (South Korea, Vietnam), targeted rules (China), and a third; sharp increase in AI legislation including **content-labelling rules** | **Latham & Watkins**, Sep 2026 |
| APOS 2026 (Bali): global streamers, Indian conglomerates, Chinese platforms, AI and microdrama upstarts, with AI the central theme | Hollywood Reporter |

⚠️ **Informed gap, searched and missing — do not read silence as coverage.** Beyond Australia, **no
China, Japan, Korea, India or Southeast Asia referral figures were found** in this pass. Searched in
English including a CJK-term query. For a Japan, Korea or India engagement the referral baseline
**does not exist publicly and must be measured first** — which is itself the first deliverable, not a
gap in the proposal.

**The region-specific inversion.** Everywhere else this plane is a loss story. In APAC the Kantar
figure makes it partly a **demand** story: if a third of consumers are already asking an AI assistant
about brands and products, then **presence inside AI answers has commercial value even when it sends
no click** — brand consideration rather than traffic. That reframes the deliverable from referral
recovery to **share-of-answer measurement**, and it is the one region where that framing is supported
by consumer data rather than vendor assertion.

Pass 5's APAC conclusion carries in unchanged and now has a second application: with three divergent
regulatory categories plus content-labelling duties, **the asset is a per-jurisdiction policy engine,
not a single compliance mode** — and the same engine that decides per-territory *reservation* can
decide per-territory *disclosure* of AI-assisted content.

**Opportunity (APAC):** **share-of-answer measurement as a brand-equity instrument**, not a traffic
tool — a repeatable harness that asks the region's answer engines a fixed prompt set per market and
records whether the client is named, cited, or absent, built on `crawl4ai` (Apache-2.0, 87,986★) with
`Auriti-Labs/geo-optimizer-skill` (MIT, 1,398★) supplying the on-site audit. The buyers are the
brand and consumer-insight teams the Kantar data describes, **plus** the broadcasters ABU names, and
the pitch does not depend on referral traffic that in this region has not been measured. Second
play, for the Australian market where the decline *is* measured: instrument the **volume-to-value
pivot** — if a publisher is deliberately trading reach for relevance, it needs the engaged-audience
metrics (pass 7) and the reader-revenue stack (pass 13) to prove the trade is working, and today it
is asserting the strategy without a scoreboard.

### Pass 31 (2026-11-27) — the live-event & show-control layer in APAC

**The region that manufactures the fixtures and is growing the fastest, and the region with no open
tooling presence at all in this plane.**

| Finding | Detail | Source quality |
|---|---|---|
| **Live music has passed its pre-pandemic size** | Pollstar's Asia focus (**October 2026**): a Summer Sonic promoter executive describes the sector as recovered and growing beyond pre-pandemic scale; Live Nation Japan reports strong demand and names **music tourism** (fans pairing concerts with travel) as the major opportunity | **Trade press — the best source in this section** |
| **The stated obstacle is operational, not creative** | The primary hurdle in international touring is **matching venue capacity to the market** while executing **localised promotion** precisely | Pollstar, same piece |
| **Market scale (vendor, use with care)** | APAC ≈ **23% of global live music**; 2026 revenue ≈ **$2.7B China / $1.5B Japan / $0.9B South Korea**, growing ~**8–11%/yr** | Cognitive Market Research — **its headline and 2026 figures do not fully reconcile; quote only with that caveat** |
| **Lighting hardware growth (vendor, multiple disagreeing)** | APAC show/stage lighting ≈ **5.4% CAGR** to 2033; China stage illumination **8.80% CAGR** to 2031; global LED stage lighting ≈ **7.4%**, China ≈ **7.6%** | Four separate market-research vendors; ranges 5–9% |
| **Demand drivers named without data** | K-pop touring and Japanese anime-music concerts cited as drivers of high-end rig demand, with **no hard figures offered** | Market-research summaries — **recorded as an unsourced claim** |

**The gap, stated as a gap:** none of the 28 verified repos in this plane's substrate originates from
an APAC organisation, and no APAC open-source lighting or show-control project surfaced in any search
this pass. The region that **builds most of the world's fixtures** has no presence in the open layer
that describes and controls them. That is either the clearest supply-side opportunity in pass 31 or a
sign that the work happens inside manufacturers and never reaches GitHub; **this pass cannot
distinguish between those two, and says so.**

**The opportunity:** the obstacle Pollstar names — venue-capacity matching and localised promotion
across many markets — is a **data and planning** problem, not a show-control problem. Lead in APAC
with touring/routing analytics, and treat the rig as the second engagement.


### Pass 32 (2026-11-27) — the device, TV-app & client-playback layer in APAC

**APAC's position in this plane is a live standard with a dormant open toolchain, plus the region's
real differentiator: four jurisdictions now legally require AI-content labelling, and the label has
to be rendered on the device.**

| Finding | Detail | Source quality |
|---|---|---|
| **Japan runs its own interactive-TV stack** | **Hybridcast**, specified by **IPTV Forum Japan** (IPTVFJ **STD-0010** integrated broadcast-broadband system, **STD-0011** HTML5 browser). **Hybridcast Connect** standardised **September 2018** | W3C Media & Entertainment IG materials + IPTV Forum Japan — primary |
| **NHK publishes MIT reference implementations — and they are cold** | [`hyconet4j`](https://github.com/nhkrd/hyconet4j) (Java SDK, **MIT**, 15★, 2021-11-17), [`antwapp4hc`](https://github.com/nhkrd/antwapp4hc) (**TV emulator**, MIT, 21★, 2021-11-17), [`hyconet.js`](https://github.com/nhkrd/hyconet.js) (MIT, 7★, 2020-09-29), [`node-red-contrib-hyconet`](https://github.com/nhkrd/node-red-contrib-hyconet) (MIT, 7★, 2020-09-30) | **Verified by reading repo metadata 2026-11-27.** All four MIT; **all four dormant 5+ years** |
| **But the standard itself is still advancing** | A **March 2026** NHK paper proposes using the Hybridcast Connect Protocol to transition **from a connected-TV app to a broadcast service** and reports verification on **commercially available receivers**, noting *"it has not been possible to switch from an application to a broadcast service using existing standard technologies"* | ITE conference paper — primary, and it dates the gap |
| **Installed base (stale figure)** | Hybridcast reported on **300+ TV models, 20 million units** — but that figure is from **2022** | ⚠️ W3C minutes, 4 years old. **Do not quote as current** |
| **South Korea has the region's broadest AI law** | **AI Basic Act in force 2026-01-22.** Generative-AI transparency rules require operators to **warn users in advance** that a service is generative-AI-powered; **synthetic-media watermarking is in force** | Law-firm alerts — verify against statute |
| **India regulates through the intermediary framework** | Amendments to the **IT Intermediary Guidelines effective 2026-02-20**, requiring AI-generated content labelling | Law-firm alerts |
| **Four jurisdictions require labelling; Japan does not** | **China, South Korea, India and Vietnam** require AI-generated content to be labelled (**Vietnam's AI law effective 2026-03-01**). **Japan relies on voluntary guidelines and industry self-regulation**; Taiwan is drafting | Multiple law-firm sources agree |
| **Market weight** | APAC M&E ~**$905.5B (2026)**, ~**9.1% CAGR**; smart TV APAC CAGR ~**10.2%** through 2033 | ⚠️ Vendor estimate. **Sources contradict each other on whether APAC or North America holds the largest smart-TV share** — do not assert either |
| **Timing of AI in live broadcast** | Early Japanese/Korean deployments cover synthetic environments, scriptwriting, automated dubbing and subtitling; **wider live-broadcast use expected after 2028**, tied to 6G | Regional trade analysis — directional |

**The strategic read.** APAC is the mirror image of EMEA in this plane: **the standard is live and
advancing while its open toolchain has been abandoned for five years.** NHK standardised Hybridcast
Connect, published four MIT reference implementations including **a TV emulator** — the single most
useful artefact for anyone building without a lab full of Japanese receivers — and then stopped
touching them in 2021. Meanwhile NHK's own March 2026 paper demonstrates a **new app-to-broadcast
transition** that the published SDKs do not implement.

**Two deliverables.** (1) **Revive the Hybridcast Connect toolchain as a Globant asset.** All four
repos are MIT, so there is no licence friction; `antwapp4hc` plus `hyconet4j` give a second-screen /
companion-device capability for the Japanese market that no maintained competitor offers, and the
2026 transition technique is a concrete feature to add. ⚠️ Adopt-and-maintain — there is no
upstream. (2) **The AI-disclosure rendering layer, which is a device-layer problem nobody has
solved.** Korea requires an **advance warning** that a service is generative-AI-powered; China,
India and Vietnam require content labels. A label is only legally effective if the **viewer sees it
on the TV** — and nothing in the open TV stack (`blits`, `enact`, `zombiebox`,
`react-native-tvos`, ORB, the Hybridcast SDKs) implements a disclosure surface. This is the same
finding EMEA produces from Article 50, arriving from four separate statutes, which makes it a
**reusable component rather than a per-country compliance job**.

**⛔ Stated as a gap:** no APAC-specific open device-certification or QoE tooling was found. The
certification layer in this plane is CTA/SVTA (North-America-led) and HbbTV (EMEA); searches for an
APAC equivalent returned the ITU-R integrated broadcast-broadband reports and nothing implementable.
### Pass 33 (2026-11-27) — the media-monitoring & earned-media measurement layer in APAC

- **The adoption gap here is a *services* gap, which is the most directly billable finding of this
  pass.** A 2026 survey of APAC PR professionals found **over half embrace AI, but lack strategic
  adoption and structured training**. That is not a tooling deficit — the tools are free and
  permissive. It is a methodology and enablement deficit, and it is exactly what a studio sells.
- **Regulation diverges sharply, so the compliance story must be per-country.** Latham & Watkins
  (2026-09) sorts the region into three groups: **binding risk-based frameworks** (South Korea's
  **AI Framework Act**, Vietnam), **targeted rules** (China, including **labelling of
  generative AI output**), and lighter-touch regimes. Korea's Act notably also *supports* adoption
  via public data sharing and R&D, so it is not purely a compliance cost.
- **Data residency pushes monitoring in-region, which favours self-hosting.** India's **Digital
  Personal Data Protection Act** is reported to be pushing vendors toward local data centres. A
  self-hosted Apache-2.0 collection tier satisfies this by construction, where a US SaaS monitoring
  contract does not.
- **Vernacular capability is the regional moat, and it is held by local vendors.**
  **Konnect Insights** (India) specialises in vernacular-language sentiment and integrates local
  platforms such as **ShareChat** and **Koo**; **Germin8** (Mumbai) and **Truescope** (Australia) are
  also active. Japanese buyers reportedly favour automated clipping plus AI sentiment, with local
  vendors competing on compliance-tailored offerings.
- **⛔ Gap stated explicitly rather than left silent:** searched 2026-11-27 for **permissively
  licensed open-source sentiment models for Indic and Southeast Asian languages** on this plane and
  **found none**. `stanza` (Apache-2.0) covers NER across 70+ languages, so *entity* detection works
  regionally; *sentiment* in Hindi, Bahasa, Thai, Vietnamese or Japanese has no permissive
  off-the-shelf option found this pass. The vernacular sentiment layer is where local vendors have
  moat and open source has nothing — and it is buildable, since the DimABSA/XLM-R route used by
  `pr-radar` is language-agnostic.
- **Public broadcasters are testing exactly this workflow.** The ABU reported (March 2026) that public
  broadcasters in **Australia and Singapore** are piloting AI for **newsroom workflows, archiving and
  verification** — the same three functions a monitoring stack serves.
- **Demand-side context.** Kantar's Media Reactions 2026 ranks Google first for APAC consumer ad
  equity (then Netflix, YouTube, TikTok, Instagram) and finds **about one in three APAC consumers use
  AI to research brands** — which pulls pass 30's answer-engine visibility work into this plane's
  remit regionally. APAC ad spend growth is ~5.2% for 2026, the slowest since the pandemic, so budget
  arguments must be efficiency-led.

### Pass 34 (2026-11-27) — the ad-integrity, supply-chain-transparency & verification layer in APAC

**The region with the worst measured invalid traffic on earth, no ad-fraud-specific regulation, and no
locally-built tooling.** That combination is the opportunity and it should be stated as bluntly as that.

- **The highest IVT rates measured anywhere — and the sources contradict each other about which
  country is worst.** This contradiction is itself the finding:

  | Source | Claim |
  |---|---|
  | Fraudlogix 2025 (via trade guide) | Southeast Asia open-exchange programmatic IVT **up to 40%**; APAC the highest-risk region globally |
  | GeoSpot | APAC **CTV IVT 33–36%**, the world's highest; app-install fraud concentrated in **India, Vietnam, Indonesia** |
  | Lunio dataset | **China highest at 16.37%**, Japan 6.07%, **India *lowest* at 5.50%** |
  | Pixalate Q2 2025 APAC benchmarks | **India *highest* web IVT at 19%**, and 42% on mobile apps |

  ⚠️ **Lunio and Pixalate place India at opposite ends of the same ranking.** Different channels, different
  denominators, both vendor datasets. **Opportunity:** in APAC the first deliverable is not detection, it
  is **a measurement baseline the client owns** — self-hosted, documented methodology, comparable
  quarter to quarter. Every number a client currently holds comes from a vendor whose benchmark
  disagrees with the next vendor's.
- **Malvertising is a scaled, documented problem here.** Bitdefender tracked **more than 400,000 scam
  ad sightings across more than 12,000 campaigns in 13 APAC countries between January and April 2026**,
  with **Australia accounting for 52% of campaigns and India 14%.** This is the one place where
  [andpalmier/seads](https://github.com/andpalmier/seads) (Apache-2.0, 50★, 2026-09-05) — a maintained
  search-engine ad scanner, and the only live tool in a 57-repository category — has an obvious
  commercial application: continuous brand-impersonation monitoring for Australian financial-services
  and Indian consumer brands.
- **⛔ Regulation: there is no ad-fraud regulation in APAC, and that is the honest finding.** Searched
  2026-11-27. What exists is privacy law that *constrains the remedy*: **China PIPL** (cross-border
  transfer restrictions), **India DPDPA** (data-localisation obligations in effect), and divergent
  consent requirements across **Japan, Korea and Singapore**. ⚠️ **Practical consequence that changes
  architecture:** a US verification vendor's SDK phoning home is a cross-border transfer problem in
  China and a localisation problem in India. **A self-hosted, in-region IVT stack is not a cost
  optimisation in APAC — it is frequently the only lawful option.** That is the strongest technical
  argument for the permissive stack anywhere in this KB.
- **⛔ No APAC-specific ad-integrity repository was found.** The tooling on this plane is Global and
  North-American; the fraud is concentrated here. The regional vendor tier is proprietary:
  **mFilterIt** (India-based, ad-traffic validation and mobile fraud detection) alongside IAS, HUMAN
  and CHEQ. ⚠️ Vendor listicle as source — treat as presence, not market share.
- **Adjacent signal, different problem, worth knowing:** Sumsub's *Identity Fraud Report 2026-2027*
  reports **APAC holding about a third of the world's fraud networks** and **Japan's fraud rate up
  219% YoY to 5.1%**, the highest in APAC. That is identity fraud, not ad fraud — do not conflate them
  in a deck, but the same infrastructure and the same operators sit behind both.

- **The graphics desk, pass 35 (2026-11-27): APAC owns this plane twice over, and the KB had never
  noticed.** First, the **libraries**: the permissive charting substrate outside D3 and Chart.js is
  substantially APAC-origin — [apache/echarts](https://github.com/apache/echarts) (Apache-2.0,
  **67,808★**, 2026-11-25, Baidu-origin and now ASF-governed),
  [antvis/G2](https://github.com/antvis/G2) (MIT, 12,678★, Ant Group) and
  [pyecharts/pyecharts](https://github.com/pyecharts/pyecharts) (MIT, 15,781★). Second, the **desk**:
  [abcnews](https://github.com/abcnews/odyssey) — ABC Australia's Story Lab, **231 repos** — is the
  most actively maintained open graphics desk found anywhere in the world, with
  [chart-builder](https://github.com/abcnews/chart-builder) (MIT) pushed **2026-11-27, the day of this
  pass**, [odyssey](https://github.com/abcnews/odyssey) (MIT) 2026-11-26,
  [svelte-scrollyteller](https://github.com/abcnews/svelte-scrollyteller) 2026-11-25 and
  [interactive-isobands](https://github.com/abcnews/interactive-isobands) (MIT) 2026-11-26.
- **The APAC risk is the mirror image of the EMEA one: maintained but unwatched.** ABC's repos carry
  **0–22 stars each** (`chart-builder` 3, `svelte-scrollyteller` 6, `odyssey` 22). A desk this good
  with this little external contribution is a **bus-factor dependency**, and three of its most
  reusable pieces — `palette` (the colour system), `components-dataviz` (the shared components) and
  `svelte-scrollyteller` (the newest work) — **carry no licence field at all.** **Opportunity, and it
  is a cheap one:** engage ABC-adjacent or ABU-member broadcasters to put a licence on the shared
  design system and co-maintain it. The engineering is done; the governance is missing, and
  governance is what an integrator sells.
- **Regulatory divergence makes a single APAC graphics compliance story impossible, and that is
  billable.** AI rules across the region accelerated sharply in the year to September 2026 and now
  split into binding risk-based frameworks (South Korea, Vietnam), targeted rules (China) and lighter
  regimes elsewhere, with **generative-AI disclosure and labelling obligations differing by market**.
  A chart generated or annotated by a model therefore carries different disclosure duties in Seoul,
  Shanghai and Sydney. **Opportunity:** per-market disclosure configuration in the publishing rig —
  one build, market-specific labelling — for regional broadcasters and the public broadcasters
  (Australia, Singapore) already exploring newsroom AI through the ABU.


#### Pass 36 (2026-11-27) — the 2D animation plane: **the centre of gravity, and the two biggest permissive AI animation platforms on Earth are here**

APAC is not a secondary market in this plane; it is the plane. Both of the largest openly-licensed AI
animation *production platforms* found in this pass are Chinese, and the format that schedules Japanese
animation production is the KB's crudest measured open-source zero.

- **The repositories, which are the regional story:**
  **[Toonflow](https://github.com/HBAI-Ltd/Toonflow-app) — MIT, 22,960★, created 2026-01-29**, an AI
  pipeline for China's **短剧 / 漫剧** (short-drama / comic-drama) vertical-video market: script →
  storyboard (智能分镜) → character and scene assets → image and video generation.
  **[Jellyfish](https://github.com/Forget-C/Jellyfish) — Apache-2.0, 7,353★, created 2026-03-06**, the
  same category as a workbench. Nothing of comparable size and licence exists in any other region.
- **Japan, from the industry's own trade body (AJA, *Anime Industry Report 2025*, covering 2024):**
  market **¥3.84 trillion (~$25B), +14.8% — the highest on record**; **overseas revenue ~$14.25B = 56%
  of the total, +26%**, versus domestic **+2.8%**; the **production-side segment ¥466.2B (~$3.06B), +9.1%**.
  The overseas majority is the single most important structural fact for a services engagement: the
  money is already outside Japan.
- **Japan, AI in production:** IMARC describes AI-assisted production becoming mainstream across
  **background art, in-between frames and quality control**, tied explicitly to shorter timelines and a
  **labour shortage** — i.e. the demand pull sits exactly on the operation with no licensed open
  implementation. **Utopai Studios + DeNA** announced (September 2026) an AI-assisted animation
  production collaboration in Japan with **artists retaining final creative control**; Utopai is also
  working with Chinese producer **Huace Film & TV** on a fully AI-generated series (*Journey to the West:
  The Lost Five Hundred Years*), holding distribution rights outside China, and its Seoul subsidiary
  **Utopai East acquired Alquimista Media** in February 2026. **Kadokawa** opened **Studio One Base** in
  Ikebukuro's Sunshine City in autumn 2026.
- **The registry fact that defines the region's workflow:** **XDTS** (eXchange Digital Time Sheet) was
  released **in 2018 by Celsys in cooperation with Toei Animation**; **TDTS** is Toei's native variant.
  The **public specification is still the November 2018 version**, even though Clip Studio Paint 1.13.0
  added 2D camera-folder data. Total open tooling: **six repositories, 32 stars combined**, with the
  spec delta carried by one unofficial, **unlicensed** extension. The control surface of Japanese
  animation production is effectively closed.
- **Regulation, which is the sharpest in the world here:**
  **South Korea — AI Basic Act in force 2026-01-22**, the second comprehensive AI law after the EU:
  advance notice for generative and high-impact AI, **labelling of AI-generated content**, tighter
  deepfake rules. Korea's government deliberately chose a loose framework and rejected a moratorium.
  **China** — layered binding regime: generative-AI measures (2023) plus **AI-content-labelling rules
  (September 2025)**, with penalties up to **¥50M**. **Vietnam** — comprehensive law effective
  **2026-03-01**. A Latham & Watkins analysis (recorded in pass 8) already established that APAC's
  categories diverge; for animation this means **content labelling is a hard requirement in the two
  largest producing markets**, and a Chinese 漫剧 pipeline and a Korean release of the same asset
  need different disclosure.

**The engagement shape this implies.** Two of them, and they are the most concrete in this pass.
(1) **The XDTS bridge** — the only place in this KB where the open stack can plausibly *shape* an
interchange rather than implement one, since the incumbent spec is eight years stale and its only
extension is one person's. (2) **Labelling-aware localisation for 漫剧/webtoon → global**, because the
manga/comic translation tier is the healthiest permissive sub-plane found (koharu Apache-2.0 6,853★ pushed
the day of this pass; comic-translate Apache-2.0 3,024★) while the Korean and Chinese labelling duties are
already in force.

**Informed gap:** this pass found **no adoption-rate data for AI in animation production across APAC** —
not for Japan, Korea or China. The regulation is documented, the market is documented by AJA, and the
penetration is not. Treat any adoption percentage for this plane in APAC as unsourced.

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

#### Development & pre-production — pass 17 (2026-11-26): the obligation lands exactly where the tooling does not exist

The Mexican reform is already recorded above. **What pass 17 adds is the *labour-law mechanics*, and they
are what make this plane the most sellable in the region.**

- **The consent duty is per-purpose, revocable, and it outlives the contract.** Under the reformed
  **Federal Copyright Law Article 87**, image rights are extended to cover **voice and results generated
  by AI systems**, and such use requires the **express consent of the holder for specific purposes, with
  revocation possible for justified cause.** On the labour side — **the first time AI is addressed in
  Mexico's Federal Labour Law** — performers **retain rights over AI-generated reproductions of their
  likeness after the underlying contract has ended**, and employers and production companies **must
  obtain explicit consent to use a worker's image or voice to train AI models or generate synthetic
  performances.** AI-generated modification of **advertising** content featuring a performer requires
  **separate, specific consent and remuneration.**
- **Legislative path and dates, for a proposal that has to cite them.** Chamber of Deputies **2026-04-07**
  (335 in favour, 129 abstentions); Senate **2026-04-15**; decree published in the **Diario Oficial de la
  Federación 2026-05-14**; **in force 2026-05-15**.
- **⚠️ Correction — do not quote penalties.** **Economic sanctions were removed from the final bill.**
  The figures circulating in secondary coverage — up to **MX$586,000 (~US$34,000)**, and the
  **1,000–5,000 UMA** ranges — belong to the **earlier 2025 draft**, not the enacted text. The Federal
  Copyright Law's own pre-existing penalties still apply to improper use of protected content. A proposal
  that cites a dropped fine as live exposure will be corrected by the client's counsel.
- **Political risk attached to the same instrument.** The industry association **AMITI** has warned that
  the measure may be technically unfeasible and **could complicate the 2026 USMCA review.** Mexico still
  has **no general AI statute**: the broader **CONAIA** governance bill remained in Senate committee as of
  late April 2026.
- **The thesis, and it is the sharpest in this file.** Mexico is the hub of Spanish-language dubbing for
  all of LATAM, and the reform **names dubbing actors, voice-over artists and locutors explicitly** as
  protected performers. From 2026-05-15, consent for voice, likeness and **AI training** is a
  per-purpose, revocable, post-contract obligation on the production company. **Consent is created at
  booking, not at delivery** — so the system of record is the call sheet, the deal memo and the
  day-out-of-days. Pass 17 measured that layer and found **73 combined stars across eight repositories,
  the only broad-scope one GPL-3.0, and the only permissive ones at 1 and 8 stars.** The obligation has
  landed precisely on the layer with no open tooling.
- **This inverts the usual pattern in this KB.** The recurring finding across sixteen passes is that
  regulatory pressure does not produce permissive supply. Here the regulation is **enacted, dated,
  sector-specific and labour-side**, and the supply is not merely copyleft — **it is absent.** That is a
  cleaner sale than a compliance report, because there is no incumbent to displace.
- **Opportunity — ranked first for LATAM in this plane.** A **consent-capture layer inside the production
  office**: performer consent recorded per purpose at booking, revocation tracked, scope carried forward
  past wrap, and the evidence trail joined to the C2PA/provenance stack already in Patterns 4 and 8. It
  is the same engine as the North American guild build (**one build, two markets**), and the Mexican
  version has a statutory date to anchor the urgency. Regional reinforcement: **Uruguay** was the first
  LATAM signatory of the Council of Europe AI framework convention; **Peru** published its AI law
  regulation in September 2025; and **Aspen Digital's** regional recommendation is explicitly to build
  **shared regional AI assets and attribution and licensing frameworks** — which is an argument for one
  reusable consent asset rather than twelve bespoke ones.

#### Sports media & live events — pass 19 (2026-11-26). The region where the **creator is the rights-holder**, and the stack fits that buyer exactly

- **The 2026 World Cup is the organizing event, and the rights are unusually fragmented.** Per
  Dataxis, **21 companies across the region's six biggest markets** hold broadcast rights tied to the
  tournament, and **76% are betting on streaming**. Fragmentation at that level means many buyers
  each needing their own production capability — the opposite of a single national broadcaster.
- **Brazil — a YouTuber holds free-to-air Olympic rights.** **CazéTV** took FTA rights in Brazil for
  the **2026 and 2028 Olympics**, and is reported at **25.9m subscribers** with announced World Cup
  advertising deals worth around **$400m**. ⚠️ Those two figures come from a single trade source and
  are flagged as unverified; the rights award itself is reported consistently. Alongside it,
  **Globo** holds Brazilian Olympic **pay-TV** rights through **2032** and F1 through **2028**;
  **Warner Bros. Discovery** carries the Champions League on TNT Sports and HBO Max; World Cup
  coverage is shared across **Globo, YouTube, CazéTV, SBT and N Sports**.
- **Mexico.** **TelevisaUnivision** holds exclusive Olympic rights through **2032**, with **ViX**
  positioning as the only home for all **104 World Cup matches** digitally; **Amazon added El Tri**
  matches (August 2026); **Sky Sports** (Televisa) took F1 from Fox Sports Mexico in 2025.
- **Region-wide.** **América Móvil** renewed LATAM Olympic rights through **2032**; **ESPN** retains
  F1 for LATAM and the Caribbean through **2028**; the Champions League in Spanish-speaking LATAM is
  split **50/50 between Disney and Paramount**, with the Mexican deal expiring at the end of
  2026/27 — a dated, near-term renewal to watch.
- **Regulation is arriving sector-first.** **Peru's Law 31814** took effect in **January 2026** with
  a risk-based structure and a government programme running to 2030. **Mexico** passed 2026 AI
  amendments to its **copyright and labour** laws — the first sector-specific AI rules there — plus a
  new **audiovisual law reaching video-on-demand platforms**, which is the one most likely to touch a
  sports streamer. Baker McKenzie notes no LATAM country yet has a mature harmonized regime and that
  **deepfakes and synthetic media are becoming enforcement priorities**. **Latam-GPT** (Chile's
  CENIA, 30+ institutions across eight countries) remains the regional model effort.

**Opportunity, specific to this region:** **the creator-broadcaster.** CazéTV is the archetype and
it is not an anomaly — a digital-native rights-holder with a real audience, real advertising revenue
and **no broadcast infrastructure**. That buyer cannot staff a highlights desk per match, and cannot
sign an AGPL obligation or a per-minute inference bill either. The permissive local stack is
precisely sized for them: `roboflow/sports` (MIT) for detection and tracking,
`Anil-matcha/AI-Youtube-Shorts-Generator` or `jipraks/yt-short-clipper` (both MIT, both >1,000★, both
pushed within two days of this pass) for vertical clipping, a browser-source overlay driven from that
output, running on one GPU at near-zero marginal cost per match. **It is the only plane in this KB
where the LATAM-native buyer is better served by the open stack than an incumbent broadcaster is.**

**Second opportunity:** with 21 rights-holders across six markets and 76% streaming-committed, the
repeatable product is a **per-rights-holder clipping and overlay deployment**, not a single
enterprise platform — the same offer sold 21 times.

**Informed gap, stated explicitly:** **no sports-specific open-source project originating in LATAM
was found**, at any star level, despite LATAM being the most streaming-committed region in this
plane. The region is a buyer here, not a producer of this tooling — which is the commercial argument
for Globant building it regionally rather than integrating something that already exists.

**Pass 21 (2026-11-26) — the spatial, immersive & volumetric plane.** LATAM is a buyer and a
production location in this plane, not a producer of the tooling. The regional anchor is concrete and
dated: the **Virtual Production LATAM Summit runs 11–13 December 2026 at 555 Studios, São Paulo**.
Regional overviews place **Mexico, Colombia, Brazil, Chile and Argentina** as the markets expanding
virtual-production capacity, supported by **government incentives and international co-production
treaties** — the same incentive machinery this KB recorded for the production plane in pass 6, now
pointed at LED volumes and 3D capture.

**Figures, with their confidence stated.** One consultancy puts South American immersive
entertainment at **~USD 1.8B for 2026**; the methodology is not published and the figure should not be
quoted to a client without a primary source. Location-based VR is the one segment with named, dated
events: **Mixtou and Hopi Hari opened a dedicated VR area in January 2026**, with a reported plan of
60 new units in Brazil over five years. Volumetric video specifically is described across sources as
**early and gradual** in the region, with no country-level detail available.

**A caveat that changes how the Mexico evidence should be used.** The strongest-sounding Mexican
claims in this plane come from **vendor self-description** — a Mexico City studio describing itself as
the country's leading immersive studio with a 60 m² LED volume. That is a real capability signal but
not independent evidence, and Brazil's evidence base is materially stronger than Mexico's. Treat
Mexico as under-measured rather than as the second market by default.

**Opportunity, specific to this region: capture-for-export, on a licence-clean base.** The regional
logic that made virtual production work here — skilled crews, incentives, co-production treaties, cost
differential against US production — applies identically to 3D and volumetric capture, which is more
labour-intensive and less capital-intensive than an LED stage. A **LATAM capture service producing
permissively-licensed splat and 3D assets for NA and EMEA clients** is the most direct offer in this
plane, and Pattern 44 is the delivery spine: COLMAP (new BSD) → gsplat or brush (Apache-2.0) →
SuperSplat (MIT) → glTF-Transform (MIT) → model-viewer (Apache-2.0). Because the whole chain is
permissive, the asset can be handed to a client in any jurisdiction without a licence negotiation —
which is exactly what a research-licensed pipeline cannot do.

**Second opportunity: the LBE venue as the repeatable unit.** As in pass 19's sports finding, the
regional product is not one enterprise platform but **the same deployment sold many times**: a venue
capture-and-playback stack built once on Hubs Community Edition (MPL-2.0) or Godot (MIT) and installed
per site, against a named pipeline of new VR locations.

**Informed gap, stated explicitly: no LATAM-origin open-source project in this plane surfaced in any
of this pass's 71 repository probes**, at any star level. Every permissive component in Patterns 44
and 45 originates in North America, EMEA or APAC. The region is a buyer and a capture location here,
which is the commercial argument for Globant building the regional capability rather than integrating
something that already exists locally.

- **Mexico is the one sector-specific move, and for images it is a consent duty, not a label duty.**
  Amendments to Mexico's copyright and labour laws published in **May 2026** are described as the
  **first sector-specific AI regulation in Mexico**. As pass 22 recorded for audio, the shape of the
  Mexican obligation is **performer consent**, not horizontal transparency — so for the still-image
  plane the artefact is a **likeness-and-consent record per person depicted**, not a label per file.
  A Mexican client distributing into the EU needs **both**: consent records for Mexico and Article 50
  labels for Europe. These are different data models, and conflating them is the common error.
- **The regional strategy is collective bargaining over image rights, and it is explicit.** Aspen
  Digital's **"Mind the Gap: AI and the Future of News in Latin America"** (January 2026) describes
  a regional push toward **shared AI assets and attribution and licensing frameworks**, finding that
  such coalitions strengthen Latin America's long-term capacity and bargaining position.
  **Opportunity:** a *shared* rights-and-attribution registry for photo archives across several
  outlets is a better-fitting product here than a per-publisher tool — and it is the one engagement
  shape where the region's fragmentation is an asset rather than an obstacle.
- **The permissive path matters more here than anywhere else, and this plane makes it acute.**
  Budgets in the region favour self-hosting, and **self-hosting is exactly what triggers AGPL.**
  Five of the seven self-hostable photo platforms in `verticals/solutions.md` pass 23 are AGPL-3.0,
  including both of the attractive ones (Immich 120,170★, PhotoPrism 40,481★). The permissive route
  is narrow and should be named in the proposal: **`LibrePhotos` (MIT) for a library**, or
  **`Cantaloupe` (MIT) + `OpenSeadragon` (BSD-3) + `open_clip` (MIT)** for an archive — plus
  `Little-CMS` (MIT) if print is in scope. It is the difference between an archive the client owns
  and an archive whose source they must offer to their own users.
- **Who is already organising:** IFPIM backing regional initiatives; **FLIP** (Colombia) and
  **ADEPA** (Argentina) studying adoption and the regulatory debate; **SiPreBA** with the Heinrich
  Böll Foundation publishing a May 2026 report on regulating AI in media; and the **Inter American
  Press Association (SIP/IAPA)** convening on governance and business models, noting in July 2026
  that adoption is no longer hypothetical while trust and business-model control remain unresolved.
  Beyond Mexico, **Brazil, Argentina, Chile, Colombia and Costa Rica** are developing AI governance
  frameworks and **Uruguay signed the Council of Europe AI treaty in 2025**; no country has a fully
  harmonised regime.
- **Informed gap, stated plainly.** This pass found **no LATAM instrument addressing AI-generated or
  AI-altered photography in news**, and **no regional figure for the stock-image, photo-archive or
  print-production market.** Searches returned commentary, law-firm summaries and newsroom-policy
  studies, not image-sector market data. **No LATAM revenue or volume figure is asserted for this
  plane.** The regional anchors available here are regulatory (Mexico) and organisational (the
  coalitions above), and those are what a proposal should be built on.

#### The owned-channel & audience-relationship plane — added 2026-11-26 (pass 24). The region with the best *evidence* in this plane, a regulator who just opened the channel, and an adequacy decision that makes the EMEA build portable

- **WhatsApp is the owned channel, and the penetration figures are not close.** A regional analysis
  (Infobip) puts WhatsApp at **85% in Brazil**, **80% in Argentina** and **75% in Colombia** as the
  top messaging channel. In Brazil WhatsApp ranks **first for social platform use (83%)**, with just
  under half — **48%** — using it for **news** (WARC; undated in the source, treat as recent-but-unpinned).
- **⭐ The strongest single piece of evidence found in this plane, and it is academic, not vendor.**
  A **2026 *New Media & Society*** field experiment by **Mont'Alverne, Rossini and Kalogeropoulos**
  tested **WhatsApp news channels in Brazil**. Findings: receiving news via WhatsApp **does not alter
  more stable attitudes** — belief in misinformation and trust were unmoved — but it **reduces news
  fatigue** and **increases engagement with news on WhatsApp**. **Quote this in preference to any
  vendor material in this plane**, and note precisely what it supports: WhatsApp distribution is an
  **engagement and retention** intervention, **not** a trust or misinformation remedy. A client
  pitching it as a misinformation fix is pitching something this study does not support.
- **⭐ And the regulator just opened the channel.** Brazil's competition authority **CADE ordered Meta
  to suspend contractual terms prohibiting third-party AI providers from using the WhatsApp Business
  API**, and later reporting has Meta **paying daily fines for non-compliance with the interim
  measures**. **This is the single most actionable regulatory fact in this pass:** the terms that
  would have blocked an AI-assisted publisher distribution agent on WhatsApp in Brazil are under
  suspension order. **Verify the current procedural status before building** — interim measures move —
  but the direction of travel is open.
- **LGPD adequacy makes the EMEA build portable.** The **European Commission recognised Brazil's LGPD
  as essentially equivalent to EU standards (January 2026)**. The practical consequence for this plane:
  **the Pattern 24.4 consent object — legal basis, purpose, jurisdiction, spec version — ports from an
  EMEA engagement to a Brazilian one** with the vocabulary intact. That is a reusable asset across two
  regions, and it is the cheapest cross-region leverage in this KB.
- **What the ANPD will be looking at, 2026–2027:** children's data, **targeted advertising**, AI and
  emerging tech (**facial recognition, recommendation systems**), public-sector data sharing, and
  biometric processing. Three of those five touch this plane directly.
- **The rest of the regulatory frame.** Brazil's AI bill **No. 2,338/2023** passed the Federal Senate
  and, as of July 2026, awaited the rapporteur's opinion in a Chamber special committee — **still
  pending**. **Decrees 12,975 and 12,976** added content-moderation, reporting and transparency duties
  for intermediaries including AI services, **effective 20 July 2026** — which is what Pattern 24.2's
  moderation log discharges. **TSE Resolution No. 23,755/2026** governs deepfakes and synthetic content
  in electoral advertising. Regionally the picture is **fragmented — Latin America does not follow one
  regional model**, so build per-jurisdiction and configure.
- **Ecosystem that an engagement can plug into:** the **International Fund for Public Interest Media
  (IFPIM)** supports media AI initiatives across Latin America and launched **CTRL+J**, holding its
  inaugural LatAm conference in **São Paulo in March**; **ADEPA** publishes a guide for media on AI
  tools and workflows. These are partners and credibility, not competitors.
- **Opportunity 1 — the WhatsApp-first owned channel.** Compose Pattern 24.1's spine (Unomi + Novu,
  both permissive) with WhatsApp Business API delivery, under the CADE opening above. **There is no
  open-source WhatsApp publisher-distribution tooling** — searched, genuinely absent — so this is
  greenfield integration work in the region where the channel has 85% penetration. Price the platform
  dependency honestly: the channel is rented, and CADE's measures are interim.
- **Opportunity 2 — moderation with an evidence trail (Pattern 24.2)** against Decrees 12,975/12,976,
  on Coral (Apache-2.0) + detoxify (Apache-2.0), with Spanish- and Portuguese-language policy-as-code.
  Pass 11's reference implementation for a Spanish-language newsroom AI policy (Pattern 33) is the
  nearest precedent.
- **Opportunity 3 — email as the hedge against the rented channel.** Because WhatsApp is a platform
  and CADE's remedy is interim, the strategically correct advice to a LATAM publisher is to run
  Pattern 24.1's email/push spine **underneath** the WhatsApp channel, so the audience survives a terms
  change. SendPortal (MIT) or Keila (AGPL, EU-hosted) plus Postal (MIT) are the permissive options.
- **Informed gap.** Searched specifically for **newsletter and audience-data practices under the LGPD**
  and for **2026 LATAM publisher adoption figures** for owned channels: **nothing found.** Older
  Brazilian evidence exists but is group-based rather than Channels-based — the daily *Correio*
  reported WhatsApp sharing accounting for **7–10% of its daily audience** — and should be labelled as
  such. Reuters Institute's Digital News Report would be the place to close this gap next pass.



#### The traffic, sales-order-to-air & billing plane — added 2026-11-26 (pass 25). **The most time-boxed opportunity in this KB: an electoral deadline that makes a traffic-system rule mandatory**

> Non-repo facts from web-search extracts; publisher domains (`bnamericas.com` and others) were
> **outside this session's allowed network domains**. Marked **†**.

- **Brazil has turned a traffic-desk rule into law with a date on it.** Brazil's electoral court
  approved AI rules for the **October 2026 elections**: publishing or boosting AI-altered content that
  changes a candidate's **image, voice or statements** is **banned in the 72 hours before a vote and
  the 24 hours after**, and **any campaign advertisement using AI must carry a clear and visible
  notice**.† Free election advertising on radio and TV runs **until 1 October**, three days before the
  first round.†
- **Why this is a traffic problem and nothing else.** A broadcaster carrying **free, mandatory
  electoral advertising does not control the creative.** It cannot fix the spot; it can only control
  **when the spot may be placed** and **what it can prove afterwards**. A 72-hour prohibition window
  and a notice requirement are therefore enforced **at booking** and evidenced **from the log** — the
  two functions this KB measured as having no open-source implementation. **Pattern 25.4.**
- **Mexico is moving the same way.** A proposed reform provides for **labels on AI-generated content**
  and **expanded INE powers to remove disinformation**.† Regionally, Brazil's AI bill, **Chile's**
  framework, **Colombia's CONPES** on AI and **Mexico's** sectoral rules are advancing at different
  speeds† — so, as in APAC, the asset is a **policy object per country**, not one compliance mode.
- **Opportunity 1 — the electoral-window booking gate, delivered before October 2026 (Pattern 25.4).**
  Smallest credible scope in the plane and the only one with an externally fixed deadline: a policy
  object (window, notice requirement, evidence to retain) attached to the spot in Nebula or 9eye,
  blocking placement inside a prohibited window and emitting the evidence record a regulator or court
  would request. Reusable afterwards for NA's fifty-state patchwork and APAC's divergence.
- **Opportunity 2 — reconciliation as the entry product (Pattern 25.1).** LATAM broadcasters are the
  least likely in this KB to be running a modern incumbent traffic suite, which makes the
  **reconciliation layer sellable on its own**, without a replatform: it reads the existing log and the
  existing as-run file and produces the exception report nobody has.
- **Advertising demand signal:** OpenAI said in **May 2026** that its **ChatGPT ads pilot** would
  expand to the UK, **Mexico**, **Brazil**, Japan and South Korea — making Brazil and Mexico the first
  named Latin American markets for paid advertising inside ChatGPT.† Relevant to this plane because a
  new inventory surface arrives with **no as-run concept at all**.
- **Consumer adoption, for sizing conversations only:** a 2025 Google/Ipsos survey found **44% in
  Mexico**, **39% in Chile** and **35% in Brazil** had used AI in the previous 12 months; a different
  measure puts **5–10%** of the general population using AI tools daily.† Different measures, not
  contradictory figures — do not merge them.
- **Informed gaps, stated plainly.** (1) **No source was found on AI adoption in LATAM television
  advertising operations specifically** — the evidence is consumer adoption and electoral regulation,
  not traffic-desk practice. Treat it as **unresearched, not absent**. (2) One frequently surfaced
  LATAM "AI impact 2026" source **ships unfilled `[VERIFY]` placeholders where its adoption statistics
  should be — do not cite it**, and treat any figure traceable to it as fabricated.

#### Pass 26 addendum (2026-11-26) — the energy & carbon plane: self-regulation, private offsetting, and the emptiest open-source layer in the plane

- **No regulation was found, and the search was explicit.** Queried in Portuguese and Spanish
  (`produção audiovisual sustentável LATAM 2026 huella de carbono cine Brasil regulación`), the Brazilian
  picture is **self-regulation and private certification**, with no sectoral carbon rule for audiovisual
  production. ⚠️ **This is an informed gap, not a verified absence**: the authoritative check would be
  **ANCINE**, the Ministry of Culture, and public-procurement policy for audiovisual commissioning, and
  **this pass did not reach those sources.** Treat as "no sectoral mandate found", not "no mandate
  exists".
- **What exists instead is a voluntary layer with real volume.** **Grupo Globo** has run a
  *Guia de Produções Verdes* since **2023** — fleet electrification, replacing generators on live
  programmes — making it the region's largest adopter, self-authored and uncertified. **BrLab 2026**
  closed its 15th edition with a *carta-manifesto* for a more sustainable audiovisual industry,
  positioning Brazil and Latin America as active agents of that change. Private vendors supply the rest:
  **Eccaplan's Set Neutro** seal for offsetting shoot emissions nationwide, **Set Sustentável** reporting
  **>650 t CO2** offset via **Carbonext**, **Publicis Production's A.L.I.C.E.** mapping campaign
  emissions since 2023, and the **FAM** festival (Florianópolis) offsetting **50 t CO2** in its 30th
  edition.
- **Read the category carefully before proposing anything:** this market buys **offsetting and
  measurement services**, not certification against a public standard. The artefact that sells is a
  **credible inventory** — the number itself, defensible to a brand or a co-producer — rather than a
  compliance pack aimed at a certifier, which is what EMEA buys.
- **Opportunity — the co-production compliance bridge, and it is the strongest play in the region.** A
  LATAM producer in a European co-production inherits the **EMEA** obligation: albert certification for a
  UK commissioner, or the **MEDIA Carbon Calculator** for an EU-backed project. The deliverable is a
  LATAM-side data pack that satisfies a European calculator built on European assumptions and emission
  factors. **That is an emission-factor and methodology problem, and nobody is selling it.**
- **Opportunity — the green-claims exposure that travels.** The EU green-claims rules effective
  **September 2026** bind the claim, not the claimant's address. A LATAM production or campaign marketed
  as carbon-neutral into an EU market needs the evidence trail behind the claim (Pattern 26.3), and the
  offsetting seals above are **not** that evidence.
- **⛔ The measured zero, and a trap worth recording.** The open-source layer here is the emptiest in the
  plane, and the totals actively mislead: `huella de carbono` returns **467** repositories and
  `pegada de carbono` **177**, yet **every first-page result is a student or personal project at 0–4
  stars, mostly unlicensed, and not one is audiovisual.** The only LATAM-adjacent, correctly-licensed
  repos found anywhere in the plane are generic. A pass that reported those totals as coverage would have
  called LATAM the best-served region here; it is the worst.


#### The production-finance & soft-money plane — added 2026-11-26 (pass 27). The region where the money grew fastest and the incentive is being **simplified by decree**

- **Colombia is the strongest incentive story in the region this year, and it has two separate
  instruments that are routinely conflated.** **CINA** (the transferable tax-credit certificate) was
  allocated **COP 350,000 million for 2026 — a 49% rise over 2025 and the largest since the incentive
  began** — and offers a **35% transferable tax credit** on eligible audiovisual and logistical
  services for foreign productions. The **FFC** (Colombia Film Fund) is a much smaller **cash** scheme
  at **COP 6,680 million (~USD 2M)** for 2026, paying **40% on audiovisual services and 20% on
  logistical services**. One is a credit you sell; the other is cash you receive — different balance
  sheet, different timeline, different evidence.
- ✅ **This narrows a gap the KB itself recorded.** The pass-6 LATAM note states the *"frequently cited
  Colombian 40% cash rebate was found only in vendor material and could not be verified against a
  film-commission source."* It is now corroborated by **non-vendor** reporting (Hollywood Reporter
  España, Yahoo Finance) and by coverage quoting **Proimágenes Colombia**, the body that administers
  the schemes — and the 40% is specifically the **FFC**, not CINA. It is **still not the primary
  administrative document**, so the figure is now *well-corroborated trade reporting attributed to the
  administering body*, not *verified against the regulation*. Treat it as the former.
- **Colombia also simplified access by decree, which is the operationally interesting part.**
  **Decreto 876 de 2026**, signed **2026-07-29**, amends **six articles of Decreto 1080 de 2015** to
  simplify the domestic film-law tax incentive, extending it to national features and shorts
  **regardless of the contributor's line of business**. A decree that changes eligibility mid-year is
  the canonical argument for **versioned, date-effective rules** rather than a hard-coded calculator.
- **Sub-national incentives are real in LATAM and are usually missed.** **Medellín**'s municipal
  scheme (**ICAM**, via the Comisión Fílmica) awarded **more than COP 2,700 million to 131 projects**
  in its 2026-I call, with a further **COP 1,300 million** pool in 2026-II. A claim engine that models
  only national schemes understates the achievable benefit in exactly the territories where Globant's
  LATAM delivery sits.
- **Brazil's largest instrument is not a rebate, and calling it one is a costly error.** The **Lei
  Paulo Gustavo** is **Complementary Law 195 of 2022**, **R$3.862 billion** in total with
  **R$2.797 billion ring-fenced for audiovisual**. The Union **transfers funds to states, the Federal
  District and municipalities, which each run their own calls, tenders and awards** — so it is a
  **distributed public-selection programme with hundreds of local windows and accountability
  (*prestação de contas*) obligations**, not an automatic rebate. Separately, **Spcine** runs the City
  of São Paulo's production-attraction programme, described as **Brazil's first audiovisual cash
  rebate** — municipal, and distinct from LPG. **No 2026 change to LPG was found.**
- ⚠️ **Informed gaps, stated so silence is not read as coverage.** **Mexico's EFICINE** and
  **Argentina's INCAA** were searched explicitly in this pass **and returned nothing usable** —
  unresearched, not absent. Both are needed before any LATAM-wide incentive engine could claim
  coverage. Note the adjacent live risk already in this file: the Mexican dubbing sector spent 2026
  lobbying for fiscal incentives and warning about **exclusion from Mexico's audiovisual incentive
  policy**, so Mexico's incentive perimeter is itself contested.
- **The opportunity, placed.** LATAM's defining feature in this plane is **many small windows with
  short deadlines and heavy accountability paperwork** — national, state and municipal — rather than a
  few large automatic schemes. The highest-value artefact is therefore not a rate calculator but a
  **calendar-plus-evidence engine**: which calls are open, what each demands, and whether this
  production's own documents already satisfy it. `docassemble` (MIT, 1,019★) is a better fit for the
  *prestação de contas* shape than any accounting tool, and nothing in the market does this.

#### The age-rating & classification plane — added 2026-11-26 (pass 28). **The region with a hard 2026 deadline, a metadata-shaped obligation, and a measured open-source zero**

**Brazil — the deadline, and it is the most concrete date in this plane.** Portaria **1.048/2025**
(Ministério da Justiça) governs *classificação indicativa*. Its main provisions took effect
**2025-11-17**, and **articles 48–57 take effect 2026-03-17.** The rule requires ratings to be
**displayed before the start of works and to be available in catalogue descriptions, trailers and
promotional materials**, and it applies to **streaming and video-on-demand platforms** as well as
games, apps and public shows. Bands: **`L, 10, 12, 14, 16, 18`**, assessed on sex and nudity,
violence, drugs and interactivity. Later-hours guidance (20h for 12, 21h for 14) applies to
free-to-air TV, not streaming.

**Why this is the best-shaped obligation in the whole plane.** It is not a display requirement that a
front-end team can satisfy with a badge. *"Available in catalogue descriptions, trailers and
promotional materials"* means the rating has to be **correct in the metadata, everywhere the title
appears** — catalogue feeds, trailer assets, promo cut-downs, partner deliveries. **That is a
pipeline problem with a date on it**, and Brazil is the largest streaming market in LATAM with more
than **40 million households** on at least one VOD platform.

**And there is a precision detail worth carrying into the pitch.** The MovieLabs dataset's Brazilian
entry records that **"only 10 reasons are currently accepted in Brazil. All other reasons are
considered invalid,"** citing the gov.br ClassInd 2021 practical guide. A closed descriptor list is
exactly the thing a generic nudity-or-violence classifier cannot emit. **The deliverable is a mapping
from detector output to Brazil's ten permitted descriptors, with the evidence retained per title.**

**The measured open-source zero — an informed gap, not silence.** `classificacao indicativa` returns
**8 repositories, every one at 0 stars**, all student or coursework projects (Flask demos, cinema
exercises, a games-classification analysis). **There is no open implementation of Brazilian
classification — none.** This is the cleanest regional zero recorded in this plane, and it sits
against a statutory deadline eleven weeks after this pass.

**The rest of the region is covered by data, not by code.** The MovieLabs dataset carries **13 LATAM
territories** — `AR BO BR CL CO CR EC HN MX PE SV UY VE` — and AppStream maps `AR → INCAA` and
`BR → DJCTQ`. Two caveats, both measured:

- **AppStream still calls Brazil's system `DJCTQ`**, the retired board name, where the current
  identity is ClassInd.
- **AppStream's Argentine projection has 3 rungs where INCAA has 5** — it cannot express
  `mayores de 16` or **`condicionada`**, the conditional-exhibition outcome that constrains
  distribution. For a LATAM rollout, that is a correctness bug, not a cosmetic one.

**Informed gap:** no 2026 regulatory change was found for **Mexico**, and no harmonised LATAM
standard exists. The search `regulación clasificación edad contenido México 2026` returned Brazilian
material only. **Mexico is not investigated, not absent** — and it is the obvious second market to
check before a regional proposal.

**Opportunity (LATAM):** a **ClassInd conformance pipeline** sized to the 2026-03-17 deadline —
per-title descriptor records drawn from Brazil's ten permitted reasons, rating propagation into
catalogue, trailer and promo metadata, and an audit trail per asset. The buyer is any VOD operator
serving Brazil, the deadline is public and fixed, no open implementation exists, and the same engine
re-points at Argentina for the cost of a ruleset — provided the `(system, value)` pair is modelled
properly, which is the one thing none of the open implementations does.

#### The interactive, branching & playable-story plane — added 2026-11-26 (pass 29). **The region where this plane is a *games* conversation, with public money behind it and an avatar rule nobody has implemented**

The honest regional finding first: **LATAM has no interactive-video market to address, and it does
have a fast-growing narrative-games sector.** A targeted search for Latin American visual-novel or
webcomic studios and their market size returned **nothing usable** — no 2026 figures, no Mexico
narrative-market number. That is an informed gap, not coverage: the region is **not investigated for
this format, not absent from it**.

What is measurable:

- **Narrative games are the channel.** gamescom latam 2026 (São Paulo, Distrito Anhembi,
  **30 April – 3 May 2026**) listed **28 competing Latin American titles — 15 from Brazil, 3 from
  Argentina**, plus Mexico, Colombia, Costa Rica and Uruguay. Narrative entries named in coverage
  include Brazil's *ARIDA 2* (survival narrative) and Colombia's *SOPA* (narrative adventure).
  Brazilian studio counts in 2026 reporting run from **~1,042 to ~1,200**.
- **There is public money, because of a legal reclassification.** Brazil recategorised the legal
  framework for games in **2024**, which opened access to cultural funding programmes, and grants are
  now reaching studios. Abragames is explicitly pushing internationalisation and foreign investment.
  This is the same "public money as the sizeable number" pattern pass 27 recorded for production
  finance.
- **The regulation that lands on this plane is about avatars.** Brazil's **CONAR** extended its 2026
  influencer-advertising guidance to **avatars, virtual profiles and AI-generated content**, including
  child participation and transparency duties. Mexico published **LFDA + LFT amendments on
  2026-05-14** (its first sector-specific AI rules) and has a **proposed film/audiovisual law**
  reaching exhibitors, streaming platforms, producers and creative labour. Region-wide there is **no
  harmonised AI regime**; Uruguay was the first LATAM signatory to the Council of Europe's AI
  convention (2025).
- **Timing caution worth quoting internally:** practitioners describe LATAM as adopting US standards
  and protocols **six to twelve months** after they settle — which means the EU/Korea disclosure work
  above is a preview of this region's 2027 requirement, not an irrelevance.

**The structural gap.** CONAR's rule now covers a **virtual influencer**, and there is no open tooling
anywhere that produces the disclosure record it implies — nothing that ties an avatar's utterances to
a transparency artefact or to child-participation safeguards. Combine that with the plane's measured
zeros (`second screen companion tv` = 2 repos, no interactive-video standard) and the region's real
asset (a funded, growing narrative-games sector) and the shape of the work is clear.

**Opportunity (LATAM):** a **virtual-influencer compliance kit for Brazil** — per-campaign records of
which avatar said what, which parts were AI-generated, the transparency labelling CONAR expects, and
the child-participation safeguards it names — built on the permissive avatar stack (UniVRM/three-vrm
MIT, LiveTalking Apache-2.0) and deliberately **not** on `Duix-Mobile` (bespoke community licence).
The buyers are agencies and brand teams already running avatar campaigns; the rule is already
published; and no open implementation exists. Secondary play: narrative-tooling delivery for the
funded Brazilian games sector — the whole authoring chain (Godot + dialogic + godot-ink + Yarn) is
MIT, so a studio engagement carries **no licence exposure at all**, which is a rare sentence in this
KB.


### Pass 30 (2026-11-26) — the answer-engine discovery layer in LATAM

The region with the **highest structural exposure** to this plane, a **live factual dispute** over it,
and **no public measurement at all.**

| Finding | Source |
|---|---|
| Pressure is strongest in **Latin American newsrooms dependent on Google search for ad-generating traffic** | Latin Times |
| LatAm publishers have been **slower to adapt to digital and multiplatform working**, leaving them less ready for AI-driven disruption | **Nic Newman**, Reuters Institute |
| **Brazil: Google publicly rejected accusations from Brazilian journalism groups** that AI Overviews caused sharp traffic drops to news outlets | MLex, Mar 2026 |
| **Mexico: amendments to the Federal Copyright Law and Federal Labour Law published 2026-05-14** — the first sector-specific AI regulation in Mexico | Chambers; EC IP Helpdesk |
| Calls for **shared regional AI assets and coalitions on attribution and licensing** to strengthen bargaining position | **Aspen Digital**, *Mind the Gap*, Jan 2026 |
| Newsroom AI policies being written at FLIP (Colombia), ADEPA (Argentina), SiPreBA (May 2026) | *recorded earlier in this file, pass 5* |

⚠️ **Informed gap, searched and missing.** **No LATAM-specific referral-decline percentage was
found** — searched in English and with Spanish-language terms. The region that is described as most
exposed is the region with **no published number.** State this plainly to a client rather than
substituting the US figure (−38%), which would overstate it, or the European figure (−17%), which may
understate it.

**The region-specific structural fact, and it is the strongest commercial hook in this plane.** In
Brazil there is now a **named, public, factual disagreement**: journalism groups assert AI Overviews
caused sharp traffic drops; **Google denies it.** Pass 5's law reappears here in a new form — what is
scarce is not the tooling but **an agreed measurement**. Both sides are arguing about a number that
nobody has produced to a standard either would accept. That is a measurement-methodology engagement,
and it exists because of the dispute, not in spite of it.

Compounding it: Newman's point means the region is **least instrumented** — publishers slower to
adapt digitally are precisely those least likely to retain parsed server logs, which (per the NA
section) is the only surviving route to a pre-AI baseline now that Google's instrument offers **no
backfill**. Every month of un-retained logs is a month of the dispute that cannot be reconstructed.

**Opportunity (LATAM):** the **neutral referral-measurement baseline for a publisher coalition** —
one documented methodology, applied identically across several outlets, producing the number that the
Brazilian dispute lacks and that Aspen Digital's call for regional **attribution and licensing**
coalitions needs as its evidentiary floor. Built entirely on permissive, self-hostable tooling
(`goaccess` MIT, `crawler-user-agents` MIT, `umami` MIT) so no participant has to route its traffic
data through a competitor or a vendor — which is the governance precondition that makes a *coalition*
measurement possible at all. The buyers are the associations already writing AI policy (ADEPA, FLIP,
SiPreBA, IAPA) rather than any single newsroom, because a coalition number is worth more than any
member's own, and the second deliverable is **log retention and crawler-identity instrumentation** at
each member — unglamorous, urgent, and the thing that stops the evidence expiring. Mexico is the
separate, nearer-term play: with copyright **and labour** law amended on 2026-05-14, a Mexican
engagement has a statutory hook that no other LATAM market yet offers.

### Pass 31 (2026-11-27) — the live-event & show-control layer in LATAM

**The demand story of this plane, the region where the venues are being built, and — for the first
time in this KB — the region that authored part of a plane's agent layer.**

| Finding | Detail | Source quality |
|---|---|---|
| **Brazil is the regional anchor** | **#1 in Latin America and #9 worldwide** by music market size (IFPI 2025), described as one of the industry's fastest-growing markets, with legacy artists increasingly routing through South America | **Pollstar South America special, January 2026 — trade press citing IFPI** |
| **Mexico entered the global top ten for the first time** | Concert attendance has **more than tripled since 2019** | Rolling Stone citing Reuters |
| **Capital is consolidating, with figures** | Live Nation raised its stake in Mexico's **OCESA to 75% for $646M (2025)**, after paying **over $400M** for a controlling stake in 2021; it also took a majority of **Movistar Arena, Buenos Aires**, bought into a major **Santiago** arena, and entered **Peru** | Rolling Stone + Río Times — **the hardest numbers in this section** |
| **Regional share (vendor)** | LATAM ≈ **6.0% of the global concert-halls-and-theatres market = ~$2.28B (2026)**, growth tied to venue development and touring in Brazil and Mexico | Fairfield Market Research — single vendor, unverified |
| **Volume claims to treat with suspicion** | ~28,000 annual concerts and festivals in Brazil; LATAM live-music events up ~40% in 2023 YoY (ILMC) | Dataintelo / Market Data Forecast — **sources unclear, not independently verified** |
| **LATAM authored two of the plane's eight AI agents** | `Gamartinhos/lumina-ai-controller` (Portuguese) and `guillegar/show_designer` (Spanish). **Both are unlicensed** — one has no licence file, the other reports NOASSERTION | **Measured directly**, 2026-11-27 |

**The strategic read, and it is the sharpest opportunity in pass 31.** Everywhere else in this plane
an engagement means **retrofitting** a rig and a workflow that already exist. In LATAM the venues are
being **built and bought right now**, at known prices, by a consolidating owner. A show-control and
venue-operations stack specified at **construction time** — rather than bolted onto a 20-year-old
patch — is a greenfield opportunity that does not exist in North America or Europe. See
`compose/patterns.md` pattern 31.5.

**And the finding that makes this more than a sales line:** the only regional concentration in any
agent layer this KB has measured across 31 passes is **here** — two of eight projects, both
Spanish/Portuguese-documented, both built in the last six months. The appetite is local and already
demonstrated. **Both are unlicensed, so neither can be adopted as-is**; the correct move is to
contribute a licence upstream or rebuild the idea on QLC+ (Apache-2.0), not to fork them silently.


### Pass 32 (2026-11-27) — the device, TV-app & client-playback layer in LATAM

**LATAM holds something no other region in this KB has had in any plane: a brand-new national
interactive-TV platform going live *this year*, with government-subsidised device distribution
pending approval. This is the only genuine greenfield in pass 32.**

| Finding | Detail | Source quality |
|---|---|---|
| **Brazil's TV 3.0 / DTV+ is launching now** | Decree signed **2025-08-27**. Signal launched **2026-06-11** alongside the World Cup, covering **Rio de Janeiro, São Paulo and the Federal District** | ⚠️ **Sources disagree on status**: one describes June 2026 as the move *"from pilot deployments and regulatory preparation into commercial operation"*, another calls the June 11 signal **experimental**. Say "launching", not "launched", until confirmed |
| **The architecture is a hybrid of two regional standards** | TV 3.0 uses the **ATSC 3.0 physical layer** (US) with **Ginga** retained as the **application layer** (Brazilian). **MPEG-H audio is mandatory and now on air** | Standards/academic sources + trade press |
| **The RF plant is *not* the US one** | Brazil uses **MIMO** (horizontally and vertically polarised components) and **new spectrum around 300 MHz**, requiring **different transmitters and antennas** from the US deployment | Trade press — the point for anyone assuming ATSC 3.0 equipment is portable |
| **Receivers are shipping** | **Intelbras and Aquário** began customer deliveries **2026-06-08**; **Vivensis** also in market; more TVs and STBs expected. **Mirakulo's AstroTV NEXT** middleware is in some receivers, with Android TV and mainstream SoC support | Regional trade press |
| **⭐ A subsidy could create the installed base at a stroke** | A proposal to invest **~$236M in TV 3.0 converter devices for ~910,000 low-income households**, **still requiring Anatel board approval** | Trade.gov market intelligence — **pending, not approved. Flag as conditional** |
| **The application layer is GPL-2.0 with a 53-star reference implementation** | [`TeleMidia/ginga`](https://github.com/TeleMidia/ginga) — PUC-Rio's implementation of **ITU-T H.761 / ABNT NBR 15606** — **GPL-2.0**, 53★, last push **2024-11-25**. Ginga has been the mandated interactivity standard since **2007** and is reported to ship in millions of TVs and STBs across Brazil and Latin America | **Licence and dates verified 2026-11-27.** The installed-base claim is a secondary source |
| **A LATAM-origin player with global reach** | [`clappr/clappr`](https://github.com/clappr/clappr) — **BSD-3-Clause, 7,543★, pushed 2026-11-26** — built and still maintained by **Globo (Brazil)**. The most successful piece of open media infrastructure to come out of the region | Verified 2026-11-27 |
| **Mexico legislated performers' voices and images first** | Amendments to the **Federal Copyright Law and Federal Labour Law published 2026-05-14**, creating a framework for using performers' voices, images and performances — described as Mexico's first sector-specific AI rule. A separate reform requiring **human dubbing** for foreign audiovisual works translated into Spanish or Indigenous languages **passed the Chamber of Deputies** | Law-firm guides; **the dubbing reform's final status is unconfirmed** |
| **Brazil's broader framework is still pending** | A **streaming bill** in Congress could add a **cinema-fund levy and Brazilian-content prominence** duties; on AI the **ANPD sandbox consultation is running while the Marco Legal is stalled**. Brazil's electoral court restricts synthetic media favouring or harming a candidate | Law-firm analysis |
| **Peru** | AI regulation **in effect January 2026** | Secondary |
| **Chile** | A Santiago streaming industry event framed **CTV, advertising and measurement** as the current focus, with panelists saying **self-regulation counts for more than settled law**, especially on betting ads | Vendor event report — directional |

**The strategic read, and it is the clearest opportunity in pass 32.** Everywhere else in this plane
Globant would be arriving after the platform is set: Roku and Tizen are closed, HbbTV is twelve
years mature, Hybridcast is eight years old. **In Brazil the application platform is being populated
right now**, its app layer is an **open (if GPL-2.0) standard with a 53-star reference
implementation and no agent layer whatsoever**, the receivers started shipping five months ago, and
a **$236M public device subsidy is awaiting a regulator's signature**. There is no incumbent
systems-integrator position to displace because the platform is younger than this KB.

**Three deliverables.** (1) **A DTV+ / Ginga application practice** — the first serious one.
Interactivity on TV 3.0 means Ginga (declarative NCL / imperative), and the only reference
implementation is a university repo last pushed two years ago. ⚠️ **It is GPL-2.0**: keep
Ginga-facing code in a separate process behind IPC, or scope the Brazilian app as a distinct
artefact under its own licence terms, or the client's proprietary deliverable inherits the
obligation. (2) **A TV 3.0 receiver/app conformance offering**, using pattern 32.1's BSD-3 harness:
new platform, new receivers from three manufacturers, MPEG-H mandatory, and **no established test
practice in-region** — and if the subsidy lands, ~910,000 devices arrive needing exactly this.
(3) **Build on Clappr, and say so.** A Brazilian client being shown a BSD-3 player maintained by
Globo is a materially easier conversation than a US or European dependency, and at 7,543 stars and a
push the day before this pass it is a serious engineering choice, not a courtesy.

**⛔ Stated as a gap, honestly:** searches found **no open-source Ginga *tooling* beyond the
reference implementation itself** — no linter, no emulator, no test harness, no agent. For a
platform mandated since 2007 and now carrying a national transition, the developer tooling layer is
empty. That is either the supply-side opportunity of this pass or a signal that the work is done
in-house by the three receiver manufacturers; **it is worth one direct conversation with the SBTVD
Forum to find out which, before committing a build.**
### Pass 33 (2026-11-27) — the media-monitoring & earned-media measurement layer in LATAM

- **⛔ The hardest regional finding of this pass, and it is a blocker: the Spanish/Portuguese
  sentiment substrate is licensed against commercial use.**
  [`pysentimiento/pysentimiento`](https://github.com/pysentimiento/pysentimiento) is the best
  open social-NLP library for **Spanish and Portuguese** (sentiment, hate speech, irony). Its entire
  337-byte licence reads: *"an open-source library for **non-commercial use and scientific research
  purposes only**"*, and adds that its **models carry the TASS and SemEval-2017 dataset licences**.
  It was last committed **2024-06-20 — ~2.5 years dormant**.
  **A Globant LATAM engagement cannot ship it.** There is no architectural workaround: no service
  boundary or API indirection makes a paid client deliverable non-commercial.
- **Place that precisely:** on this plane, English sentiment tooling is MIT (`vaderSentiment`,
  `NewsMTSC`); multilingual *entity* resolution is Apache-2.0 (`stanza`, 70+ languages); and the
  es/pt *sentiment* tier is non-commercial and abandoned. **The region's language is the one the
  licence excludes.**
- **✅ Therefore the LATAM opportunity is a build with a proven recipe.** Fine-tune a permissively
  licensed multilingual encoder for es/pt **news** sentiment — the exact route
  [`Etipufhu/pr-radar`](https://github.com/Etipufhu/pr-radar) (MIT) took with **XLM-R on DimABSA
  (SemEval-2026)**, reporting 6–53% lower error than baseline across all 10 official test sets and
  then adapting to news headlines. **An Apache-2.0 or MIT es/pt news-sentiment model does not
  currently exist, the training path is published, and the demand is regional.** This is the single
  most defensible open-source contribution identified in this pass.
- **The regional institutions are already organised around AI-in-media policy** — and they are the
  natural partners and references: **FLIP** (Colombia) and **ADEPA** (Argentina) research AI adoption
  in media while tracking regulation; **SiPreBA** with the **Heinrich Böll Foundation** published
  *"Notes Toward Regulating Artificial Intelligence in the Media"* (May 2026); **IFPIM** launched
  **CTRL+J**, convenings on media sustainability, AI regulation and technological disruption with a
  Global South focus.
- **Newsroom adoption is operational, not experimental.** Panels at the Inter-American Press
  Association's midyear meeting described AI in LATAM newsrooms as ongoing practice under strong human
  oversight; **Peru's El Comercio** implemented a ~10-page internal AI guide in early 2026. Clients
  here want governance and measurement, not a demo.
- **Regulation is uneven and must be checked per country.** A **Chilean** AI bill is before Congress;
  **Uruguay** became the first LATAM country to sign the Council of Europe's Framework Convention on
  AI and Human Rights, Democracy and the Rule of Law (2025); several other initiatives are proposed or
  enacted. Observers split on whether the region should follow the EU model or risk over-regulation.
- **Market demand is real where it has been looked at:** Brazil, Mexico and Argentina are cited as
  the regional leaders in adopting media monitoring for **brand reputation and crisis management**,
  with local vendors and resellers packaging vernacular dashboards. ⚠️ The specific vendor counts in
  that source (an aggregator directory) are weak; treat the *direction* as reliable and the *numbers*
  as unverified.

### Pass 34 (2026-11-27) — the ad-integrity, supply-chain-transparency & verification layer in LATAM

**The region with the best time series on this plane and the thinnest institutional response.**

- **Pixalate's LATAM benchmarks give a rising, consistent series** — the same methodology across
  quarters, which is rarer than it sounds on this plane:

  | Report | Brazil | Mexico |
  |---|---|---|
  | Q3 2024 | mobile app **26%**, web 14%, CTV 15% | mobile app 21%, web 12%, CTV 10% |
  | Q1 2025 | mobile app **42%**, web 23%, **CTV 37%** | mobile app 36%, web 14%, CTV 22% |
  | Q4 2025 *(published 2026-03-09)* | — | **mobile app 41%**, desktop+mobile web **32%**, **CTV 37%** |
  | Global baseline, Q4 2025 | web 23%, mobile app 36%, CTV 21% | built from **>103 billion impressions** |

  **Mexican CTV at 37% against a 21% global baseline, and Mexican mobile web at 32% against 23%.**
  Brazil's mobile-app rate went from 26% to 42% in two quarters. ⚠️ Pixalate's data is predominantly
  buy-side open-auction traffic and is a vendor benchmark, not an audit — but it is the **same** vendor
  measuring the **same** way over two years, which makes the *direction* usable even if the level is
  arguable.
- **⛔ The institutional gap, stated explicitly because silence would look like coverage.** Searched
  2026-11-27 for **CONAR**, **IAB Brasil**, and Mexican programmatic-advertising regulation:
  **nothing found on ad fraud, invalid traffic or verification standards from any of them.** There is no
  LATAM equivalent of the MRC, no regional accreditation, and no published regional IVT standard. The
  region with CTV invalid traffic at 37% has **no institution that defines the term.**
- **What regulation does exist is privacy-side and dated, and it is coming.** Brazil's **ANPD**
  published its **2026–2027 priority map in December 2025**, including **five enforcement activities on
  the secondary use of personal data for targeted advertising, especially profiling** — scheduled for
  **H1 2027.** ⚠️ One source reports the ANPD **became a fully independent regulatory agency in
  February 2026** (single-sourced; verify officially). ⚠️ One Brazilian article cited an **R$153.7M
  TikTok fine dated 2026-08-25** which could not be confirmed in this pass — **do not quote it.**
  **Opportunity, and it has an 18-month runway:** profiling-and-targeting readiness for Brazilian
  advertisers and publishers, built now against the ANPD's own published priorities, delivered before
  the enforcement window opens.
- **⛔ No LATAM-specific ad-integrity repository was found**, and no Spanish- or Portuguese-language
  tooling on this plane. The one Spanish-language artifact located was an explainer article
  (programaticalatam.com) rather than code.
- **The build that fits the region.** LATAM clients are the least likely to be paying for accredited
  verification and the most exposed to IVT, which inverts the usual sequencing: lead with the
  **self-hosted GIVT gate** — CrowdSec (MIT, 15,814★) + OWASP CRS/Coraza (Apache-2.0) +
  crawler-user-agents (MIT, 1,416★) in front of Prebid Server (Apache-2.0, 595★) — because it removes
  a measurable double-digit percentage of waste **at zero licence cost**, which is a conversation a
  Mexican or Brazilian publisher can have without a procurement cycle. Then sell the measurement
  baseline. Do **not** lead with accreditation: there is no body in-region to accredit against, and
  pretending otherwise is the fastest way to lose the account.

- **The graphics desk, pass 35 (2026-11-27): an informed gap, stated as a gap.** Seven LATAM
  newsroom and civic-data organisations were scanned for a reusable charting or mapping library
  (`lanacion`, `OjoPublico`, `chequeado`, `agenciapublica`, `InfoAmazonia`, `estadao`, `datasketch`).
  **No permissive, reusable, maintained graphics library was found in any of them.** What exists is
  real work in three other shapes:
  - **Live, maintained, and copyleft/WordPress-coupled:**
    [InfoAmazonia/jeo-plugin](https://github.com/InfoAmazonia/jeo-plugin) (**GPL-3.0**, 10★,
    2026-11-13) — interactive map blocks for WordPress Gutenberg — and
    [InfoAmazonia/amazonia-minada](https://github.com/InfoAmazonia/amazonia-minada) (**AGPL-3.0**, 9★,
    2026-11-10), a daily-updated illegal-mining map and bot. Genuinely active, and both licences keep
    them out of a proprietary client deliverable.
  - **Per-story code, not libraries:** [estadao](https://github.com/estadao/basometro) publishes
    story repos under **GPL-3.0** (`basometro` 51★ 2020-01-20, and the 2018 tweet- and
    facial-expression-analysis pieces at 54★ and 52★). Excellent transparency practice; nothing to
    reuse.
  - **Components without grants:** `datasketch` (Colombia) has **202 repositories**, overwhelmingly
    R/Shiny building blocks (`shinypanels` 81★, `shinyinvoer`, `hgchmagic`), and **most carry no
    licence field.** `chequeado` (Argentina) has [chequeabot-legacy](https://github.com/chequeado/chequeabot-legacy)
    (MIT, 15★, 2025-05-27) and an active `botletin-oficial` (2026-03-13) — fact-checking automation,
    adjacent to this plane rather than in it.
- **Read the asymmetry precisely, because it sets the engagement shape.** APAC and North America
  export **permissive libraries**; LATAM publishes **copyleft applications and unlicensed
  components**. A LATAM newsroom that wants a shipped, relicensable graphics system is therefore
  building on North American rigs (NPR/Pudding MIT) or APAC libraries (ECharts/G2) **today** — there
  is no regional alternative to adopt. **Opportunity:** the first permissive, Spanish- and
  Portuguese-language newsroom chart-and-map component set, with LATAM-specific cartography
  (municipal boundaries, electoral geographies) as PMTiles. The regional appetite is documented —
  Aspen Digital's January 2026 "Mind the Gap" report describes a regional push toward **shared AI
  assets and collaboration on attribution and licensing** — and the supply does not exist.
- **The licence conversation is already open here, which shortens the sale.** Mexico's amendments to
  the Federal Copyright Law and Federal Labour Law (published **14 May 2026**) are the region's first
  sector-specific AI rules for media; Argentina's SiPreBA and partners published *Notes Toward
  Regulating Artificial Intelligence in the Media* in May 2026; Uruguay was the first in the region to
  sign the Council of Europe's AI framework convention. **Opportunity:** pair the component set with
  a disclosure-and-attribution layer, which is the part regional publishers are being asked about
  first and the part the copyleft tooling above does not provide.
- **One honest caveat on method:** this scan covered seven organisations by GitHub org name and
  cannot prove absence across the whole region — a library published under an individual developer's
  account would not appear. It does establish that **the region's best-known data-journalism
  institutions do not publish one**, which is the fact that matters for sourcing a starting point.


#### Pass 36 (2026-11-27) — the 2D animation plane: **the usage is real, the largest 2D studio in the region is in distress, and the "AI animation studio" lists are fabricated**

LATAM is the region where this pass had to separate a genuine signal from a dense layer of invented
content, so both halves are recorded.

**What is verifiable:**

- **Brazil ranks second in the world for GenAI animation projects.** Animaker's 2026 analysis of
  ~2 million animated videos: **India 154,035, Brazil 36,928, Pakistan 24,215, United States 24,010**.
  This is **platform usage data from one vendor, not a market study** — but it is a measured count, and
  it places Brazil ahead of the US on volume.
- **Brazil has an AI-studio layer.** A Claqueta IA (Substack) survey counts **19 AI studios in Brazil**,
  with the visible pattern being large production companies and agencies opening their own AI labels.
  **Purga Studio won a Bronze Lion at Cannes Lions 2026** with an AI-made campaign produced with **GUT
  México** — a juried international award, which is the hardest evidence of regional AI craft capability
  in this pass. A **Madrid–Santiago–Mexico City hub** is behind *Pelagius*, presented as the first
  Spanish feature made end-to-end with AI.
- **Mexico: the region's biggest 2D animation house is in trouble.** **Ánima Estudios** paused
  production and announced a corporate restructuring in **July 2026**, with layoffs and unpaid-wage
  claims it declined to comment on. **Sources disagree on whether it closed or only restructured** — one
  says it ceased operations, another says it paused and restructured. Either way it is the most important
  single LATAM data point in this plane: the region's flagship 2D studio contracted in the same year AI
  tooling arrived.
- **Mexico added a production tax credit of up to 30% in 2026**, open to domestic and international
  projects. **Netflix** moved to a larger Buenos Aires office in **April 2026** (first Argentine office 2021).
- **Regional project volumes** (from Mercado Audiovisual, **year not stated in the source — treat as
  undated**): Argentina 83, Mexico 44, Colombia 41, Brazil 35. Pixelatl co-founder José Iniesta's quote
  about the region producing significant animation volume for international studios is **from 2023**.
- **Festivals, 2026:** Anima (Córdoba) best Latin American short went to ***Kabuki*** (dir. Tiago
  Minamisawa, Brazil); the Argentine competition was won by ***My Gut Friend*** (Argentina–Mexico
  co-production); the festival programmed 114 animation pieces.
- **Regulation:** **Peru's AI law regulation took effect in January 2026**, with labelling obligations
  covering AI-generated **or edited** content — broader than advertising alone. **Brazil's Superior
  Electoral Court Resolution 23.732/2024** prohibits digitally generated or altered audio and video
  intended to favour or harm a candidate. And **EU AI Act Article 50 (from 2026-08-02) reaches LATAM
  content distributed into Europe** — which is most co-produced animation.

**What this pass refused to write, and why — the informed gaps:**

1. **There is no reliable list of LATAM AI-native animation studios.** The animation-specific pages
   returned for this query were SEO marketing content (vitrina.ai), naming Brazil and LATAM as "emerging
   hubs" while giving **no verifiable regional studio names** — the only studio actually named in one such
   piece was **Toonz Media Group, which is Indian**.
2. **One source carried literal `[VERIFY]` placeholders where its headline statistics should be.** Its
   figures are therefore unusable, including an otherwise attractive claim that a regional broadcaster
   cut subtitle and dubbing turnaround by more than half.
3. **A Ciencia Latina academic article's claim that "more than 200,000 animators face disruption risk
   within five years" has no stated methodology** and is **not** recorded as data.
4. **A trade page's claimed €2.1M Netflix fine and associated specifics could not be verified** and look
   doubtful. Not used.

**The engagement shape this implies.** Brazil's measured GenAI animation volume plus a Cannes Lion say
the craft capacity exists; Ánima's contraction says the **studio-scale 2D production capacity is
shrinking at the same time**. The opportunity is therefore not "bring AI to LATAM animation" — it is
**service-studio throughput for North American and European series work**, on the permissive base
(OpenToonz BSD-3) with Kitsu run as a service, sold against Mexico's 30% credit and priced against the
outsourcing numbers in this file's pass-36 market section. The compliance layer is already required:
Peru's labelling rule is in force, Brazil's electoral rule binds synthetic audio/video, and anything
shipped into Europe meets Article 50.

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

## Market size — pass 17 addendum (2026-11-26): the pre-production segment, and a refusal with a number behind it

**No market-size figure is given for pre-production and production-management software, and as in pass 16
the refusal is the finding** — but this time a *supply-side* measurement can stand in for it, which is
better than a TAM.

The incumbent vendors in this segment (Movie Magic/Entertainment Partners, Showbiz, Gorilla,
StudioBinder, Yamdu, SetHero, Croogloo; Wrapbook and Cast & Crew on payroll) are privately held or sit
inside larger payroll businesses, and none reports this segment separately. Every figure located in this
pass was for "AI in media" as a whole and could not be traced to this segment.

**What can be stood behind, with its provenance:**

| Figure | Value | Source and caveat |
|---|---|---|
| Combined stars, **all eight** open production-management repos | **73★** | Measured 2026-11-26 via GitHub `search/repositories`. **Primary.** Fewer than `betterfountain` (454★) alone |
| Most-starred artefact in the plane | **14,989★**, and **Elastic License 2.0** | `waooAI/waoowaoo`, licence read from file. **Primary** — and it is not open source |
| Permissive management-tier repos, by stars | **1★** and **8★** | `method-scheduling` (Apache-2.0), `CineSpend` (MIT). **Primary** |
| Open repos for film residuals/payroll | **0** | `residuals calculation film`, confirmed in pass 5 and again here. **Primary** |
| Mexican reform in force since | **2026-05-15** | Diario Oficial, published 2026-05-14. **Primary** |
| NO FAKES Act status | **Not law**; Senate calendar 2026-06-24 | Committee vote 2026-06-18, unanimous. **Primary-adjacent** (congressional records) |
| APAC screen economy | approaching **$200B** | Variety; regional total, **not this segment** |
| NA share of global AI-in-media market | 33.6%–40.6% | Grand View 2024 / Precedence 2025; ranges by scope. Carried, not re-verified |

**The number that should drive a proposal in this plane is 73, not a market size.** Seventy-three stars
is the entire open-source answer to the question "what runs a production office", against an enacted
Mexican consent duty, in-force US guild agreements, and a segment whose incumbents are wholly
proprietary and own every file format downstream of the script. **A supply-side zero next to a dated legal
duty is a stronger qualified-pipeline argument than any TAM this KB could have cited.**

#### Book, ebook & scholarly publishing — pass 18, measured 2026-11-26

**The concrete opportunity of this entire pass sits in this region, and it is a measured number
against an installed base this KB can name.**

Of **1,119 Latin American journals indexed in Scopus, 72.8% (815 journals) have no explicit
guidelines on the use of AI on their websites** (*Publications*, 2026 — a peer-reviewed source, not
a vendor estimate). Meanwhile **Open Journal Systems** (`pkp/ojs`, GPL-3.0, committed 2026-11-26)
runs **25,000+ journals worldwide** and is the dominant scholarly platform in LATAM.

**815 named institutions, one shared open-source platform, and a policy gap they are all aware
of.** That is a repeatable engagement — an OJS plugin for AI-disclosure policy capture, submission
screening and editorial sign-off recording — sold once and deployed many times, with
`pkp/pkp-lib` (GPL-3.0) as the correct integration seam. Delivered as a GPL plugin it carries no
contamination risk, because the plugin *is* the deliverable.

**The regulatory picture — AI rules are arriving, and IP is the sharp edge:**

| Jurisdiction | Position | Date / status |
|---|---|---|
| **Mexico** | Reforms made **AI-enabled IP infringement sanctionable** — described as the **first jurisdiction in Latin America** to address this at statutory level | **April 2026** |
| **Brazil** | **PL 2.338/2023** (Senate version): risk-based, transparency duties; training-data disclosure still debated. The regional bellwether for a comprehensive horizontal statute | In progress |
| **Mexico, Brazil, Chile, Colombia** | **Authorship treated as a human attribute** — purely AI-generated output is not protected | Settled |
| **Region-wide** | **No major LATAM jurisdiction provides a comprehensive TDM exception** for AI training. **Ecuador is the sole exception** with an express TDM provision | Current |

The TDM position is the commercially important one: a publisher in this region cannot assume a
training-data exception, so **rights-cleared corpus construction is a service, not a formality** —
and Ecuador's outlier provision is worth knowing by name.

**Accessibility runs through Marrakesh, not through a product mandate.** There is **no LATAM
equivalent of the EAA**. Access is delivered via the **Marrakesh Treaty** and authorized entities:

| Signal | Detail |
|---|---|
| Argentina's implementation | **Article 36 bis** permits authorized entities to reproduce accessible-format copies — explicitly including **audio and digital** formats |
| The measured supply gap | Argentina has roughly **25,000** accessible books against Spain's **~100,000** (World Blind Union figure) |
| Spanish-language supply | **70,000** Spanish-language titles via the ABC **Global Book Service** |
| Regional coordination | A **ULAC** congress in Lima brought together representatives of **19 countries**, highlighting the need for better distribution, greater digital accessibility and cross-border exchange of accessible books |
| Treaty scale | **103–105 contracting parties** (sources differ by reporting date; ~129 countries) |

**Opportunity, specific to this region — two distinct offers, and they have different buyers:**

1. **The AI-policy and editorial-integrity plugin for OJS.** Buyer: universities, journal
   consortia, national science agencies. Evidence: **815 of 1,119** Scopus-indexed LATAM journals
   with no AI guidelines, on a platform Globant can extend conventionally. **This is the
   highest-confidence, most repeatable offer identified in pass 18, in any region.**
2. **Accessible-format production for authorized entities.** Buyer: libraries, Marrakesh authorized
   entities, ministries of education. Evidence: a **25,000 vs 100,000** supply gap against Spain and
   an explicit regional call for digital accessibility. The pipeline is the permissive one —
   `epubcheck` (BSD-3), `ace` (MIT), `daisy/pipeline-modules` (LGPL) for DAISY/TTS output,
   `ebook2audiobook` (Apache-2.0) for Spanish-language audio. **Note the difference from EMEA: the
   driver is a service gap under a treaty exception, not a conformance duty on a product**, so the
   buyer is public-sector and the pitch is capacity, not compliance.

**Informed gaps — searched, and genuinely not found:**
- **No 2026 Brazilian or Mexican ebook-accessibility statute** located. Both have general
  accessibility and consumer law, but nothing EAA-equivalent for ebooks surfaced. The next step is
  each country's copyright and accessibility statutes directly, and the **2026 IFLA Marrakesh
  Monitoring Report**.
- **No LATAM ebook-market or AI-adoption figures** comparable to NA's 63%. The *Publications* journal
  study and the Chambers IP guide carried the region; no publisher survey was located.
- Ratification counts differ between sources (103 by 4 March 2026 vs 105 by September 2026); likely
  just different reporting dates, recorded rather than reconciled.

## Market size — pass 19 addendum (2026-11-26): the sports segment, and **the first falling number in this KB**

Sports is the rare segment where a credible primary-style figure exists and **points down**. Every
other addendum in this file reports growth; this one does not, and that reframes the sale.

| Figure | Value | Source |
|---|---|---|
| Global sports media rights value, 2026 | **$65.82bn** (record, **+15% YoY**) | SportBusiness Global Media Report 2026 |
| Global sports media rights value, 2027 | **$62.2bn** — a **forecast decline**, then a plateau | SportBusiness Global Media Report 2026 |
| US share of that global total | **53.9%** (was 46% in 2022) | SportBusiness 2026 |
| Europe's five biggest markets, combined | ≈ **one third of the US** total | SportBusiness 2026 |
| Premier League share of global total | **7.8%** | SportBusiness 2026 |
| Streaming services' sports-rights spend, 2026 | **$14.2bn** (from $13.2bn in 2025); **Prime Video ranked first**, ending DAZN's lead since 2018 | Ampere Analysis |
| IPL rights cycle 2023–2027 | ≈ **US$5.23bn** | reported |
| MENA media-company AI spend, 2026 | **$520m** | reported |

**An unresolved conflict, flagged rather than smoothed over.** Ampere projects streaming sports
spend **rising**; SportBusiness projects the **total** market **falling** in 2027. Both can be true
if streaming takes share of a shrinking whole, but **no source consulted states that**, so this KB
does not assert it. Use the two figures separately and attribute each.

**Why the falling number is the better sales position.** A market that grew 15% buys capability; a
market forecast to contract buys **cost per produced hour**. Automated highlight and overlay
production is the only lever in this plane that reduces cost per hour without renegotiating a rights
payment — and the 2027 forecast gives the conversation a date. The segment where that lands hardest
is the one with the thinnest margins and the most matches: mid-tier leagues in EMEA (the buyer the
imec-SMIT report identifies as at risk), regional sports networks in North America, and the
creator-broadcasters in LATAM.

**What this addendum does NOT contain, and will not pretend to.** No verified commercial terms for
**Sportradar, Genius Sports or Stats Perform** — the three vendors that actually price the data layer
this whole plane depends on. No public pricing exists and none was reachable from this session.
Following the discipline cycle 8 applied to DDEX: **treat as not investigated, not free.** Any
proposal that assumes a data-feed cost is guessing, and should say so to the client.

#### Investigative journalism & source protection — pass 20 (2026-11-26). **The buyer pass 8 identified, now with its tooling catalogued**

**Why this plane closes a loop in this KB.** Pass 8 concluded that LATAM's hottest buyer is the
**newsroom**, because an organisation that has written an AI policy has committed to being able to
**evidence** it. Twelve passes later the KB still had no entry for the tools that produce that
evidence — `journalism` occurred four times in the entire knowledge base. This section is the other
half of that argument.

**The policy wave is real, dated, and attributable.** **Listín Diario** (Dominican Republic)
announced AI guidelines to its readers in **January 2026**. **El Comercio** (Lima) put a roughly
10-page AI guide in place in **early 2026**. **SiPreBA** (Argentine press workers' federation) with
the **Heinrich Böll Foundation** published *"Notes Toward Regulating Artificial Intelligence in the
Media"* in **May 2026**. At the **IAPA midyear meeting (April 2026)** the reported friction was
precisely **everyday use against absent institutional frameworks**. **Derechos Digitales** filed a
submission on AI and freedom of expression. The regional pattern is governance-first: outlets are
writing policies rather than restricting use.

**The regulatory measurement, including a tension this KB will not smooth over.** CNTI's analysis of
Latin American and Caribbean AI policy found that **only 5 of 80 policies mention journalism**,
calling the effect on the press an open question given how few have been enacted — while a separate
CNTI item states that **Latin America leads in mentions of journalism in AI laws**. Both come from
the same body of work and both can hold (leading a field in which nearly nobody legislates for
journalism is a low bar), but **no source consulted states that reconciliation**, so this KB does not
assert it. Use the figures separately and attribute each. Most regional measures focus on labelling
or consent for manipulated content and differ on who is responsible and when journalism is exempt.

**Field deployment already exists here, and it is permissive.** Horizontal's user stories record a
custom **Tella** build for **forest defenders in Brazil** — simplified UI, default connection to the
monitoring organisation's own servers — alongside Belarusian and Russian translations for other
deployments. `Horizontal-org/Tella-Android` is **MIT** and pushed 2026-11-17. Meedan brought on
Brazilian fact-checking partners and reported **fewer** public verification requests than expected at
the close of Brazil's 2024 municipal elections — a demand-side caution worth carrying into any
tipline proposal.

**Opportunity, specific to this region.** The buyer has a written policy, little technical staff and
no audit trail — so the deliverable is **Pattern 42 plus Pattern 40's validation record**: offline
encrypted capture (Tella, MIT) → structured documentation (Uwazi, MIT) → human-validated entity
review (Prophecies, AGPL, operated unmodified). The entire Pattern 42 chain is **MIT/BSD** except an
ExifTool invocation that does not reach the surrounding code, which matters here because LATAM
engagements are more likely to need embedding in a client product than a hosted operation.

**And the regional reason to lead with evidence rather than capability:** per CNTI most enacted
measures in the region turn on **labelling and consent for manipulated content**. A newsroom that can
produce provenance for its own material is complying with the rule that actually exists, rather than
the one being debated.

**Informed gap:** `cnti.org`, `latamjournalismreview.org` and the IAPA site do not resolve from this
session — every figure and date in this section comes from **search snippets, not primary sources**.
The SiPreBA/Böll report was not read. No LATAM-built open source project in this plane was found: as
in APAC, the tools are built in North America and Europe and deployed here, and that asymmetry is
itself the regional finding.

## Market size — pass 21 addendum (2026-11-26): volumetric video, and the widest source spread in this KB

The volumetric-video segment has the **worst source agreement of any figure this KB has recorded** —
worse than pass 12's dubbing spread, because here the sources disagree on the *same base year*:

| Source framing | 2026 base | Forecast | Implied CAGR |
|---|---|---|---|
| Market-research release, July 2026 | **USD 3.21B** | USD 7.01B by **2032** | **13.27%** |
| Second analyst | **USD 4.67B** | USD 13.87B by **2030** | **31.3%** |
| Third analyst | not given | — | **23.2%** (2026–2035) |

The two base-year figures are **45% apart** and the CAGRs differ by a factor of **2.4**. A single
number from this segment cannot be defended, so **do not put one in a deck**. What can be defended is
the direction and the mechanism: every source names the same cost lever — **AI reconstruction reducing
the camera count**, with Gaussian splatting cited explicitly as what makes capture cheaper. Claims of
specific rendering-speed gains (~39–40%) appear only in vendor-style market blogs with no primary
technical source and should not be repeated.

**The regional split is also contested**, though less wildly: North America is given as **36.37% of
2026 XR revenue** by one analyst and **~41% of 2025** by another, with APAC projected fastest-growing
at **~41% CAGR (2027–2032)**. APAC volumetric is put at **USD 1.16B (2025) → USD 1.52B (2026)**, which
does not reconcile with either global total.

**The one figure this pass will stand behind** is not a market size at all, because it was measured
rather than modelled: **the permissive, actively-maintained open-source capacity for *temporal* 3D
capture is 161 stars** (`ASU-NEM-Labs/open4dgs-core`, MIT, pushed 2026-11-21), while the Apache-2.0
alternative with 4,047★ has been dormant since **2024-10-27** and the field's most-cited
implementation (24,564★) is **research-licensed**. Whatever the volumetric market is worth in 2026,
the open substrate underneath the word "volumetric" is that thin — and that gap, not the forecast, is
the commercial argument.

**Consumer-depth reality check, for any deck that opens with headset growth:** one 2026 industry
report has **48% of US consumers having tried VR and 13% of households owning a headset**, and a
separate analysis describes headset adoption as **behind schedule** — which is the counterweight to
every CAGR above.


**Pass 22 — the podcast plane, and LATAM is the region where this KB's existing law already applies
to it.**

- **Audience scale is real and under-monetised.** The region had **135.2 m podcast listeners (2023,
  Podnews)** — **Brazil 51.8 m** and **Mexico 27.5 m**, the world's third- and fourth-largest
  podcast audiences — while podcast advertising remains a small share of digital ad spend. The gap
  between audience and revenue is the commercial opening, and it is a **measurement and ad-serving**
  gap before it is a sales gap, which is exactly the layer this pass found empty everywhere.
- **First opportunity: the news-podcast pipeline, because news is what this region listens to.**
  Triton Digital's **2026 LATAM Audio Insights** finds **news is 32 % of podcast listening/downloads
  and 42 % of new episodes** on the networks it measures — the highest news concentration of any
  region in this KB. That makes a **newsroom-to-podcast pipeline** the highest-fit build here:
  published article set → script → multi-voice episode → chapters, transcript and show notes →
  compliant feed, assembled from `podcastfy` (Apache-2.0), `sofit` (MIT), `autoclip` (MIT) and
  Podlove Publisher (MIT), and wired to the newsroom platforms pass 20 catalogued. Pattern 49.
- **Second opportunity, and it is a legal one this KB already holds: Mexico's performer-voice law
  lands squarely on synthetic podcast hosts.** The amendments to the Federal Copyright Law and
  Federal Labour Law **published 2026-05-14, effective 2026-05-15** create a framework for AI use of
  a performer's **voice**, image and performances. An AI-voiced podcast host, a cloned presenter for
  a branded show, or a synthetic read of a sponsor spot is **precisely** that use. LATAM is therefore
  the **second** region after EMEA where synthetic-voice podcasting has a statutory hook — and
  unlike the EU's horizontal transparency duty, Mexico's is a **performer-consent** duty, which
  requires a different artefact: a consent and licensing record per voice, not a label per episode.
  A Mexican engagement needs both if it distributes into the EU.
- **Third: the permissive path matters more here.** Budgets in the region favour self-hosting, which
  is exactly where AGPL bites (Castopod, microfeed, Funkwhale, Podverse). The permissive route —
  Podlove Publisher (MIT) + OP3 (MIT) + the CC0 namespace + Anytime (BSD-3) — is the one that lets a
  LATAM client own the deployment without inheriting network copyleft. State it in the proposal; it
  is the difference between a platform they own and a platform they must publish.
- **Informed gap.** Statista's LATAM digital-audio ad-spend series runs through 2026 but its figures
  were **not retrievable** in this pass, and no 2026 regional ad-revenue total could be verified. The
  2023 listener counts are the strongest anchors available here; **no 2026 LATAM revenue figure is
  asserted.**

## Market size — pass 23 addendum (2026-11-26): the still-image & print segment, and a refusal

**No market figure is asserted for this plane, and the reason is worth recording rather than
quietly omitting.**

What was searched: open-source image-processing and DAM comparisons, 2026 media/AI industry
outlooks (Akamai, Deloitte, PwC, EY, Reuters Institute, Nieman Lab, TV Tech, TVBEurope), the four
regional adoption-and-regulation sweeps above, and the photo-specific threads (Getty v Stability,
agency AI policies, C2PA camera adoption, alt-text tooling, prepress and font tooling).

What came back: **no sizing for the still-image segment at all.** The 2026 outlooks size
"AI in media and entertainment" as a whole — and even there the spread is wide enough to be
unusable (North America's share is put at **33.6%** by one firm for 2024 and **40.60%** by another
for 2025 on a generative-AI scope), while one vendor-style report claims an **82% adoption rate**
among media organisations from a March 2026 IAB survey **that could not be verified**. None of it
separates stock imagery, photo archives, picture-desk operations, prepress or print production.

**Why the refusal rather than a proxy.** A general "AI in M&E" number applied to the still-image
plane would be wrong in both directions at once: it includes video generation, dubbing and
recommendation (which dwarf still imagery), and excludes commercial print, which is a large,
declining, non-AI market this plane sits inside. Passes 16 and 17 made the same refusal for the
avails and pre-production segments; this is the third, and the pattern is now clear enough to state
as guidance: **this KB has reliable figures for consumer-facing media segments and no reliable
figures for production-tooling segments.** Do not manufacture one from an adjacent scope.

**What to use instead in a proposal.** The defensible quantities in this plane are **structural, not
monetary**, and they are measured in this pass:

| Quantity | Measured value | Why it carries weight |
|---|---|---|
| Permissive photo-library platforms | **1 of 7** (`LibrePhotos`, MIT) | Decides whether a picture archive can be a product at all. |
| Stars behind the entire open C2PA implementation | **629** (`c2pa-rs` 455 + `c2patool` 174) | The provenance layer every 2026 trust panel assumes exists. |
| Stars behind the leading label-*stripping* tool | **6,530** | Roughly 10× the whole provenance stack. |
| Open editorial alt-text agents on GitHub | **1 repo, 1 star** | The size of the competition for the workflow product. |
| Stars behind ICC colour management (`Little-CMS`, MIT) | **764** | Load-bearing for Scribus, GIMP and Krita; the print path's quiet dependency. |
| Stars behind the RIP that turns a page into ink (`ghostpdl`, AGPL-3.0) | **310** | A single point of failure with a licensing question attached. |
| Days since the most-starred open upscaler was touched | **~840** (`Real-ESRGAN`, last push 2024-08-06) | "37,679 stars" is not maintenance. |

These are checkable, they are current as of 2026-11-26, and each one changes a decision. A market
size that is wrong by a factor of three changes none.

## Market size — pass 24 addendum (2026-11-26): the owned-channel segment, an 8× scope artefact, and a refusal

Added 2026-11-26 (pass 24). Searched for sizing on the owned-channel plane. What exists is
**email-marketing *software* sizing**, which is not what a publisher is asking about — and the one
figure a publisher actually wants **does not exist**. Both findings are recorded.

| Estimate | Source type | Note |
|---|---|---|
| **"Email marketing" market: $13.72B (2026) → $22.93B (2031)** | Market-research vendor | The broad cut. |
| **"Email marketing" market: $12.45B (2026), ~15.5% CAGR** | The Business Research Company | Agrees with the above on the base year. Its definition is explicit and it is the reason for the spread below: **platforms + email design tools + marketing automation software + tracking and analytics tools.** |
| **"Email marketing *software*": $1.92B (2025) → $3.47B (2030), 12.2% CAGR** | Market-research vendor | The narrow cut — licences only. |
| **"Email marketing *software*": $2.39B (2025) → $6.05B (2033)** | Second vendor | Same narrow scope, same order of magnitude on the base, very different horizon. |
| **"Newsletter software": $1.60B (2025) → $3.20B (2033), 9.2% CAGR** | Verified Market Research | The closest cut to this plane. **North America ~40% share** — the largest regional share recorded in this plane. |
| **"Newsletter software": 11.12% CAGR (2025–2032)** | Third vendor | Growth-rate agreement within ~2pp of VMR, which is unusually tight for this file. |
| **Newsletter *advertising / sponsorship* revenue: NO DATA FOUND** | — | **The refusal. See below.** |

### The scope artefact: ~8×, and it is the question to ask before quoting anything

**"Email marketing" ($12.45–13.72B) is roughly 8× "email marketing software" ($1.92–2.39B)**, and the
gap is not noise — TBRC states the definition outright. The broad figure counts **automation
platforms, design tools and analytics**; the narrow figure counts **licences**. This is the same
artefact this file recorded for captioning (pass 3, an order of magnitude) and content moderation
(pass 9, services vs software), now with the vendor's own definition available to prove it.

**Which figure is addressable for an open-source engagement?** The **narrow cluster** — the
**$1.6B–$3.5B newsletter/email-software** range — because the open stack in `repos/foundations.md`
replaces **software licences**, not services or media spend. This is the same reasoning as pass 9's
moderation conclusion, and it holds for the same reason.

### ⛔ The refusal: the number a publisher actually wants is unsized

A publisher in this plane is not buying email software — it is replacing **lost referral revenue with
newsletter revenue**. **No vendor sizes newsletter advertising or sponsorship revenue.** Searched;
nothing surfaced. The only quantitative signal found anywhere is a marketplace datapoint —
**newsletter revenue grew ~30% in a year at Paved** (via The Current) — which is **one intermediary's
book, not a market**, and must be labelled as such.

**So this file will not state a newsletter-revenue market size, and neither should a pitch.** What can
be said honestly, and is stronger than a fabricated total:

- The **loss** side is attested: Google Discover referrals **−21% YoY**; exposed publishers reporting
  **50–90%** revenue declines; Facebook referrals already halved over a year.
- The **response** side is attested: the April 2026 **IAB survey of 109 US publishers** shows news
  publishers prioritising subscriptions, attribution and **direct audience ownership**; The Guardian
  moving readers to always-on weekly products; Punchbowl stating that **even site visits are driven
  through the newsletter**; eMarketer reclassifying newsletters as **"first-party media"**.
- The **tooling** side is sized, narrowly: **$1.6B–$3.5B** (above).

**Lead with the client's own reachable-audience ratio (Pattern 24.1), not with a market number.** It is
measurable in weeks, it is specific to them, and it is the only figure in this plane that is not a
vendor estimate. That is a better opening than any row in this table.

### One methodological note carried from this pass

The engagement data underneath this plane — AI inbox summaries, open-rate inflation, deliverability
verdicts — is **almost entirely email-vendor blog material**. The direction is consistently attested
across many independent vendors; the **magnitudes are not independently verified**, and the
frequently-quoted "**4–8 percentage points**" of MPP open-rate inflation traces to a single secondary
source. **No independent 2026 dataset on publisher open or click rates under AI inbox summaries
exists** — searched, not found. Quote the mechanism, not the magnitude.

---

## Market size — pass 25 addendum (2026-11-26): the traffic & billing segment, and **a refusal**

> All figures below come from **web-search extracts**. The publisher domains (`thedesk.net`,
> `bitmovin.com`, `playboxtechnology.com`, `wideorbit.com`, `digitalheroesco.com`, `akamai.com`,
> `adexchanger.com`, `mediapost.com`, `ppc.land`) are **outside this session's allowed network
> domains**, so no URL could be opened to confirm them. Attributed, **not** independently verified.

### The refusal

**No credible sizing of the broadcast traffic-and-billing software segment surfaced, and this KB will
not invent one.** The queries that would price it return vendor listicles and review-aggregator pages
("Best Broadcast Traffic Software: 2026 Comparison"), which are not evidence. There is no analyst
figure here comparable to the ones this KB carries for localization, subscriptions or out-of-home.
**Do not put a TAM number on this plane.**

### What can be stood behind instead — channel count × cost per channel

The defensible framing is bottom-up, and both inputs are sourced:

| Input | Figure | Source quality |
|---|---|---|
| Global FAST channels | **~2,170** as of July 2026, **+17.5% YoY** from ~1,850 | Gracenote Data Hub via trade press.† A second source gives **2,120** in Q2 2026 at **+19%** — use **~2,100–2,200** as the range. |
| Sports growth inside that | Channels **+13.8%**, unique titles **+31.2%**, individual games/events **+37.5%** | Same.† The spread between channel growth and event growth is the operational load. |
| Managed playout, start-up | **$250–500 per channel** | Vendor blog.† |
| A serious single channel | **~$1,500–2,000/month** before content | Vendor blog.† |
| AWS MediaTailor | **$0.10/hr** VOD-only, **$0.35/hr** with live sources | Vendor blog.† |
| Sustainable ceiling | **~400 channels per platform**; effective CPMs **~$5** at ~10 min/hr ad load | One vendor's model, explicitly not an industry standard.† |

**Read it as a labour argument, not a software-market argument:** channel count is rising ~17–19% a
year while programming volume inside those channels rises 30–38%, and the revenue per channel is
thinning (PlayBox, October 2026: supply has outrun demand†). The cost being added is **scheduling and
reconciliation labour** — which is what this plane automates and what has no open-source
implementation.

### Adjacent figures that are *not* this segment (do not substitute them)

- **Agentic advertising spend, 2027: "somewhere between negligible and $700 million"** — Magnite's
  CEO, reported August 2026.† This is the *ceiling a seller's own CEO put on the hype*, and it is the
  single most useful number in this plane for managing a client's expectations. It is **not** a
  traffic-software figure.
- **APAC digital ad spend on a path to $489.3 bn by 2029**† and **GenAI in APAC M&E ~$1.97 bn (2024)
  → ~$20.7 bn (2034)**† — regional advertising and AI totals, orders of magnitude away from the
  traffic-software segment. Carried in the APAC block above with the same caveat.
- **WBD advertising revenue −7% YoY in Q1 2026 to $1.85 bn** on linear declines.† A demand-side
  pressure indicator, not a market size.

### Global players — pass 25 addendum (the traffic & billing layer)

| Player | Products in this plane | Note |
|---|---|---|
| **WideOrbit** | WO Traffic (v24.0), WO Fusion (cross-platform sales), WO Aurora (radio automation) | Described with Marketron as **"the backbone of American broadcast traffic"**.† Moving customers CapEx → subscription OpEx; partnered with Pattison Media (Sept 2026) on programmatic for broadcast radio.† |
| **Imagine Communications** | LandmarkOSI (traffic **and billing**), xG Linear (MVPD traffic), GamePlan (ad decisioning) | Reported **acquired by Lumine Group 2026-07-01 — single secondary source, verify.†** CEO conceded Feb 2026 that delivery had not met expectations.† |
| **Operative** | AOS (order management) | Older Imagine partnership feeding GamePlan orders into AOS; **current status unconfirmed.†** |
| **Marketron** | Traffic/billing for radio and local TV | Named as co-backbone of US broadcast traffic.† |
| **Fox** (seller-side entrant) | Fox AdStudio agentic advertising platform | Launched **2026-06-17**, described as the TV industry's first end-to-end agentic advertising platform; agent-to-agent negotiation for linear and streaming.† |
| **NBCUniversal + FreeWheel** | Agent-led programmatic guaranteed | First AI-agent-led PG deal including live sports across linear and streaming.† |
| **Magnite + ITN** | Agentic local linear buying | Announced **2026-09-10**, full integration **Q4 2026**, one RFP across local linear and CTV.† |

**The structural observation for positioning:** every player in the table is proprietary, and the two
newest entrants are **sellers building their own agents** rather than vendors selling software. A
broadcaster that is not Fox or NBCU cannot buy what Fox and NBCU built — and the open-source total for
the same function is a 2-star repo whose billing step is a roadmap item. **That asymmetry is the
opening, and it is why the sellable artefact is the reconciliation and evidence layer (Patterns 25.1,
25.2, 25.4) rather than an agentic sales platform.**

---

## Market size — pass 26 addendum (2026-11-26): the carbon-software segment, and an order-of-magnitude disagreement

**⛔ The refusal first: there is no media-specific figure for this segment.** No analyst sizing of carbon
or sustainability software *for media and entertainment* was found. Anyone quoting one is sub-segmenting a
general-purpose carbon-software forecast without saying so. **Stated as an informed gap, not estimated.**

And the general-purpose figures cannot be averaged, because they disagree by **more than three orders of
magnitude** — a wider spread than the 100× dubbing spread recorded in pass 12, and the widest in this KB:

| Source | Figure | Note |
|---|---|---|
| IMARC | **USD 22.2 M** (2025) | Narrowest definition found; three orders of magnitude below the high end |
| Astute Analytica | **USD 1.2 B** (2025) → USD 10.1 B (2035) | — |
| Verdantix / GII, *Carbon Accounting Software Platforms* | **USD 1.93 B** (2026) → USD 4.12 B (2032), **13.54% CAGR** | Named platform category; the most conservatively-scoped multi-year series |
| Meticulous Research, *Carbon Management Software* | **USD 2.4 B** (2026), **16.8% CAGR** to 2036 | **Includes ESG reporting** as a segment — broader than carbon accounting alone |
| P&S Intelligence | **USD 14.5 B** (2025) | — |
| Fortune Business Insights | **USD 27.51 B** (2026) → USD 136.44 B (2034) | High end; broadest scope |
| Technavio | **32.1% CAGR**, 2025–2030 | Growth rate only, no base published in the result |
| MarkNtel Advisors | **25.73% CAGR**, 2026–2032 | Growth rate only |

### What can be stood behind

**For the narrow software category, roughly USD 1.9–2.4 B in 2026, growing in the mid-teens.** That is
the band where two independently-scoped sources (Verdantix/GII and Meticulous) land, and it is the only
defensible quotation here. The spread above the band comes from folding in broader carbon management and
ESG reporting; the figure below it comes from a far narrower definition. **Quote the band, name the
source, and say which definition it uses** — the same discipline pass 11 applied to the scope artefact.

**The methodological point, and it recurs across this KB:** where a market is defined by a *regulation*
rather than by a *product*, analyst scope boundaries move with each firm's reading of the regulation, and
the forecasts stop being comparable. Pass 11 (healthcare, CPT at 18.50 vs 14 USD) found conflicting
secondaries for a single published price. This is the same defect one level up — and unlike MedDRA, whose
rates are published by the official source, **no authoritative body publishes a size for this market at
all.**

### Global players — pass 26 addendum (the carbon & footprint layer)

| Player | Role | Position | Limit for a media client |
|---|---|---|---|
| **BAFTA albert** | Certification body (UK, used internationally) | **Holds the enforced mandate.** BBC, ITV and Channel 4 all require its tooling or certification by contract | Closed web tool; no API or open schema found. Current toolkit closes **16 Dec 2026** (albert's figure; an industry guide says 17 Dec — conflict unresolved) |
| **European Commission / Creative Europe MEDIA** | Public instrument (EMEA) | **MEDIA Carbon Calculator**, launched 13 Feb 2026 at the EFM: free, EU Login, GHG Protocol Scope 2 + 3 | Does not replace national calculators, so it **adds** a reconciliation burden rather than removing one |
| **Sustainable Entertainment Alliance** | Studio consortium (North America) | Owns the **Green Production Guide** and the free **PEAR** calculator for US productions | Voluntary; no comparability requirement between suppliers |
| **DIMPACT** (Carnstone + University of Bristol) | Membership modelling tool (Global) | The streaming-side reference. The Carbon Trust work on DIMPACT produced the sector's most-quoted figure, **~55 gCO2e per hour** of European video streaming | Membership-gated; its own representatives concede consistent cross-supply-chain measurement is unsolved |
| **Greening of Streaming** | Industry body (Global) | Hardware-measurement counterweight to DIMPACT's modelling: the **REM** platform and **OWL**, a live measurement bench for streaming **and AI workloads**; convenes the **LESS Accord** | Membership; measurement standard still in formation |
| **Accedo** (Ecoflow / Ecoflow X) | Commercial vendor (Global) | Streaming-application energy efficiency, named in the 2026 standardisation effort | Proprietary |
| **EcoProd** (Carbon'Clap) · **Green Film** (Trentino) · **Sustainable Screens Australia** | National/regional bodies | The national calculator and label layer: France, Italy, Australia — the Australian tool is a **localised BAFTA albert calculator** | Each with its own factors and framework: the fragmentation *is* the client problem |
| **Eccaplan** (Set Neutro) · **Set Sustentável** · **Publicis Production** (A.L.I.C.E.) | Private vendors (LATAM) | Offsetting seals and campaign-emissions mapping; Set Sustentável reports >650 t CO2 offset via Carbonext | Sell offsetting and services, **not** certification against a public standard |
| **Green Software Foundation** · **Green Web Foundation** | Standards and open-source bodies (Global) | Produce the plane's permissive toolchain: SCI (**ISO/IEC 21031**), Carbon Aware SDK, Impact Framework, co2.js | Generic by design — **nothing in their output knows what a title, a render or a stream is** |

**The structural observation for positioning.** Every player holding a *mandate* is closed, and every
player shipping *permissive code* is sector-agnostic. There is no overlap, and the gap between them is
exactly one layer wide: **the connector that turns a media company's own operational data into the
evidence a certifier or a regulator will accept.** That layer is permissively licensable, client-owned,
has no incumbent, and is the subject of Patterns 26.1 to 26.6. It is also the reason this plane's
open-source count for the mandated task is zero without the opportunity being zero — see **P39**.

## Market size — pass 27 addendum (2026-11-26): the production-finance segment, and **the first segment this KB can size from government money rather than vendor estimates**

### The refusal first

**There is no defensible figure for "film production accounting software" or "incentive management
software" as a market, and this pass will not invent one.** The incumbents — Entertainment Partners,
Cast & Crew, Wrapbook, GreenSlate, Movie Magic/Showbiz — are private, several are PE-held, and none
publishes segment revenue. Every "market size" page returned for these terms was a generated
market-research listing of the kind pass 26 already caught selling an order-of-magnitude disagreement.

### What can be stood behind instead — the public money, which is published by governments

The addressable value in this plane is not software seats; it is **the incentive money that must be
qualified, documented and defended**. Those numbers are published by the bodies that allocate them:

| Jurisdiction | Published 2026 allocation or terms | Source type |
|---|---|---|
| California | **$750M/yr** main programme (up from $330M, July 2025); standalone post credit signed 2026-09-19, effective 2027 | State legislation / trade |
| Germany (federal) | **€250M for 2026**, doubled — and **exhausted 2026-08-20** | Trade press, consistent across sources |
| Italy (national cinema fund) | **€610M for 2026**, cut from €700M; first-ever per-work and per-company credit caps; **€66M revoked in 2025** | Budget law / trade |
| Colombia CINA | **COP 350,000M** (+49% YoY, largest ever), 35% transferable credit | Trade press quoting Proimágenes |
| Colombia FFC | **COP 6,680M (~USD 2M)**, 40% audiovisual / 20% logistics cash | Trade press quoting Proimágenes |
| Brazil Lei Paulo Gustavo | **R$3.862B** total, **R$2.797B audiovisual**, disbursed via state/municipal calls | Statute (LC 195/2022) + Ministry of Culture |
| Japan IP360 | 50% of eligible Japanese spend, **¥1.5B cap/project**, **¥800M minimum domestic spend** (JLOX+ closed 2026-01-31) | Programme terms |
| Australia | Location Offset **30%**; Producer Offset **40%** features / **20%** other | **ATO**, *Film industry incentives 2026* |
| US states | Incentives in **39 states + DC + Puerto Rico** | Trade aggregate |

**The honest framing for a client conversation.** These are *allocations and rates*, not a software
market, and they should never be presented as TAM — a 35% credit is not revenue to a services vendor.
What they do establish, defensibly, is that **the cost of getting a claim wrong is measured in
millions per production**, that **three of these schemes ration or claw back** (Germany exhausted,
Italy capped and revoking €66M, Manitoba requiring pre-certification), and that the **penalty for bad
documentation is now larger than the cost of good documentation**. That is the whole business case,
and it rests on published government figures rather than on an estimate anyone sells.

### Why this segment is unusual in this KB

Every other plane measured in twenty-seven passes had the same shape: a commercial market with vendor
estimates and no open source. This one has **public, primary, per-jurisdiction numbers** — and still
no open source. It is the cleanest separation yet between *the money is documented* and *the code does
not exist*.

### Global players — pass 27 addendum (the production-finance & incentive layer)

| Player | Type | What they hold | Constraint for an open build |
|---|---|---|---|
| **Entertainment Partners (EP)** | Commercial, global | Payroll, EP Budgeting (the de facto budget format), a global incentives database and comparison tools, Production Lot | Proprietary and **deeply wired into union reporting and auditor expectations**. The budget *format* is a near-standard with no open specification |
| **Cast & Crew** (incl. Media Services) | Commercial, NA | Payroll, production accounting (Movie Magic / Showbiz lineage), incentive advisory | Proprietary; owns the incumbent **cost report shapes** auditors expect |
| **Wrapbook** · **GreenSlate** | Commercial, NA | Modern payroll + production accounting; both publish free incentive centres and credit-management tools | Proprietary. Their **free** incentive trackers are the real competitive fact: the lookup layer is already commoditised, so **no open build should compete on lookup** — only on qualification and evidence |
| **SceneIQ** · **Jarvus CreditScout** · **Vitrina** | Commercial tooling | Incentive comparison across jurisdictions (SceneIQ cites 23; CreditScout reads EP Budgeting directly) | Proprietary. CreditScout reading EP Budgeting files confirms where the integration seam is |
| **Proimágenes Colombia** · **Spcine** · **Screen Australia / Ausfilm** · **KOFIC** · **ICAA** · **CNC** · **FFA** · **Ontario Creates** · **BC/Manitoba** | Public administrators | The **rule sets, the windows, the certification and the audit** | Not competitors and never to be displaced. They are the **authoritative source a rules-as-code engine must cite**, and several publish official calculators (Ontario Creates) that an engine should agree with, not replace |
| **Council of Europe / European Audiovisual Observatory (IRIS)** | Public research body | The only institutionally maintained cross-border comparison of audiovisual fiscal incentives and cash rebates | Free and citable. **The reference that makes an EMEA rule set reviewable** |
| **Completion-bond and E&O underwriters** | Commercial, opaque | Risk transfer that gates most independent financing | `completion bond film` = **0 repositories**. Entirely absent from open source; not a software gap Globant should attack first |

**The structural observation for positioning, and it mirrors pass 26's exactly.** Every player holding
a **rule or a mandate** is a government body publishing prose, and every player holding **working
software** is a proprietary payroll company. The gap between them is one layer wide: **executable,
versioned, citation-carrying incentive rules plus the evidence pack that proves a claim against them.**
It has no open-source incumbent in any jurisdiction, the public bodies will never build it, and the
payroll incumbents have no commercial reason to make it portable. See **P41** and **P42**.

## Market size — pass 28 addendum (2026-11-26): age assurance is sized nine ways, and **age *rating* is not sized at all**

Added 2026-11-26 (pass 28). Searched for sizing on the age-rating and classification plane. The
result splits cleanly into one over-sized adjacent market and one **refusal**, and the gap between
them is the commercially interesting part.

### What exists — age assurance / age verification, with a ~9× spread on the same base year

| Estimate (2026 unless noted) | Source | Scope note |
|---|---|---|
| **$6.11B (2026) → $13.97B (2031), 17.99% CAGR** | Mordor Intelligence — *age assurance platforms* | Platform cut |
| **$6.14B (2026) → $13.37B (2031)** | Mordor Intelligence — *age verification* | Software was **66.45%** of 2025 revenue; services growing faster |
| **$2.5B (2026) → $6.32B (2035), 12.35% CAGR** | Business Research Insights — *age verification software* | The narrow, licences-only cut |
| **$1.5B (2026) → $20.0B (2036), 29.6% CAGR** | Fact.MR via OpenPR — *verification + online-safety compliance **services*** | **Services, not software.** The outlier growth rate |
| **$12.4B (2025) → $32.6B (2034), 11.3% CAGR** | Dataintelo — *age verification systems* | The widest scope; its e-commerce variant reaches $38.6B by 2034 |
| **~$13.8B (2026)** | Incode (vendor blog) | Vendor marketing; the top of the range |
| **9.8B transactions/yr and >$7.37B revenue/yr by 2028** | Biometric Update, 2026 Age Assurance & Digital Age Credentials report | **Transactions rather than market size** — a different and more auditable unit |

**The scope artefact to raise before anyone quotes a number: the 2026 figures span roughly
$1.5B to $13.8B — about 9× — on the same base year.** The spread is definitional (services vs
software vs full platforms), not empirical. Pass 24 recorded an ~8× artefact in the owned-channel
segment; this is the same failure mode and slightly worse. **Ask which of the three scopes a figure
uses before repeating it.** Growth rates are tighter and more quotable: most cluster at **11–18%
CAGR**, with one services outlier at 29.6%.

### ⛔ The refusal — content classification and age *rating* is unsized

**No standalone forecast was found for content-classification or age-rating software.** Not a wide
range, not a disputed figure: nothing. None of the seven sources above addresses it, and none of their
scope definitions states whether title classification is included or excluded.

**Do not substitute an age-assurance figure for it.** They are different buyers solving different
problems: age assurance checks the *viewer* at the gate and is a multi-billion-dollar, vendor-dense,
well-funded market; age rating classifies the *title* in the catalogue and has — as measured in
`repos/foundations.md` — one vocabulary at 28 stars, one unlicensed dataset at 1 star, and no agent
layer at all.

**What can be stood behind instead.** Size this plane bottom-up from the obligation, which is the
method pass 27 used for public money and pass 25 used for channel counts:

- **titles in catalogue × territories served × ladders per medium** = the classification decisions a
  client must hold evidence for, each one a record that must exist and be defensible;
- **the two fixed deadlines** — Brazil's Portaria articles 48–57 on **2026-03-17** and the FTC's
  amended COPPA compliance date on **2026-04-22** — which bound the delivery window rather than the
  market;
- **the 110 systems / 77 territories** in the industry dataset as the upper bound on ladder
  complexity, with the caveat that its newest validation is **2023-07-11**.

That produces a number a client can check against their own catalogue, which is worth more here than
a vendor total addressable market for a market no vendor has yet defined.

## Market size — pass 29 addendum (2026-11-26): interactive storytelling is sized four ways, and **branching video is not sized at all**

Added 2026-11-26 (pass 29). Searched for sizing on the interactive, branching and playable-story
plane. The result is this KB's familiar pattern with a new twist: the *adjacent* categories are sized
generously and inconsistently, and **the specific thing a media client would commission — interactive
film or branching video — has no figure anywhere.**

### ⛔ The refusal first

**Do not quote a market size for interactive video, interactive film or branching video.** No figure
was found in any source. The reason is visible in this plane's history rather than in its research:
the category's largest buyer exited it (Netflix, staged removals ending **2025-05-12**), so the
analysts sizing "interactive media" are sizing games, social and immersive formats, not branching
video. A number borrowed from those reports would be **two or three categories wide** of the thing
being proposed.

### What exists — and the spreads, which are the real information

| Segment | Figure quoted | Source shape |
|---|---|---|
| Interactive media (broad) | **$61.34B (2026) → $157.30B (2033), 14.4% CAGR** | Single vendor estimate; the category includes games and social, so it is an **upper bound on everything**, not this plane. |
| Interactive story apps | **$4.2B (2025) → $9.8B (2034)** *vs* **$7.8B (2025) → $21.4B (2034)** | Two vendors, **same base year, ~1.9× apart**. |
| Interactive fiction | **$6.4B (2025) → $14.8B (2034)** | Single vendor estimate. |
| AI-generated interactive storybooks | **$3.2B (2025) → $18.7B (2034), 21.8% CAGR** | Single vendor; the only segment that is explicitly AI-native. |
| Digital storytelling platforms | **$2.81B (2026)** *vs* **$1.33B (2026)** | Two vendors, **same year, ~2.1× apart**. |

**Two spreads on the same base year, 1.9× and 2.1×.** Treat every figure above as a direction, and
state the spread whenever one is quoted — a client who hears "$7.8B" and later reads "$4.2B" stops
believing the rest of the deck.

### What can be stood behind instead — count the substrate, not the market

This plane is unusually easy to evidence without analyst numbers, because the supply side is
measurable and was measured this pass:

- **190,000+ GitHub stars** of permissive, actively-maintained narrative tooling (ink 5,067★,
  Ren'Py 7,065★, dialogic 6,194★, Godot Dialogue Manager 4,005★, WebGAL 4,054★, Yarn Spinner 2,883★,
  Twine 2,964★ …), with **five of those repos pushed on 2026-11-26**.
- **36 stars** across the entire agent bridge (six MCP servers).
- **2 repositories** in all of open source for second-screen/companion TV.
- **0** interactive-video primitives in HLS or DASH.

That contrast — a mature substrate, no agent layer, no standard, no platform — is a stronger argument
than any sized market, and every number in it is reproducible in an afternoon.

### Global players — pass 29 addendum (the interactive & playable layer)

| Player | Position in this plane |
|---|---|
| **Netflix** | Exited interactive video (final removals 2025-05-12); branching fiction continues inside *Netflix Stories* as downloaded games. The reference case for why this plane is a games/learning conversation. |
| **BBC R&D** | The only broadcaster with an open object-based-media stack (`storyplayer`, `audio-orchestrator`, Object Based Media Schema — all GPL-3.0, 30★ combined). The EMEA partner of record. |
| **inkle** | Owns the plane's de-facto scripting language (`ink`, MIT) and its editor (`inky`, MIT). A dependency, not a competitor. |
| **Yarn Spinner Pty Ltd / Secret Lab** | Owns the dialogue language (MIT) and sells the commercial tooling around it. |
| **H5P / Joubel + Lumi Education** | The platform through which branching narrative actually ships at scale — content types MIT, **hosts GPL-3.0**. |
| **Naver Webtoon / Kakao** | The serialised-interactive buyers inside Korea's AI Basic Act disclosure duty; Naver's *Toon Filter* is the region's reference AI-assistance controversy. |
| **Tencent / Alibaba (HumanAIGC) / Duix** | The interactive-avatar runtime tier. Two of the three ship **bespoke community licences**, not OSI licences. |
| **RDK / Comcast (Lightning)** | The Apache-2.0 CTV app framework — the only open route onto an operator set-top box. |
| **Unity / Epic** | The commercial runtimes clients name, both outside this KB's licence remit; the MIT alternative (Godot) now has a complete narrative stack above it. |

## Market size — pass 30 addendum (2026-11-26): the discovery segment is sized **7.3× apart on the same base year**, and the number publishers actually need is unsized

### What exists — five vendor estimates, one base year, and a definitional gap doing all the work

| Estimate (2026 base unless noted) | Source | Stated scope |
|---|---|---|
| **GEO software: $370M (2026)** → $4.12B by 2036, **27.3% CAGR**; 2025 base $210M | **Meticulous Research** | **Software licences only** — the narrow cut |
| **GEO platform: $2.70B (2026)** → $26.85B by 2033, **13.6% CAGR** | **Coherent Market Insights** | **Software + analytics tools + services** — the broad cut |
| GEO overall: **~$1.09B (2026)** | Dimension Market Research (via Superlines) | Unstated middle |
| GEO **services**: $1.23B (2025) → **$1.78B (2026)** | Intel Market Research | Services only |
| GEO **services**: **$1.966B (2026)**, **42.0% CAGR** to 2032 | QY Research | Services only |

### The scope artefact: ~7.3×, and it is the question to ask before quoting anything

**$2.70B (platform) ÷ $370M (software) = 7.3× on the same base year**, and as with pass 24's email
artefact (~8×) and pass 3's captioning artefact (an order of magnitude), the gap is **definitional,
not empirical**: the broad figure counts **analytics tools and services**, the narrow one counts
**licences**. The two services-only figures ($1.78B, $1.966B) agree within ~10% and both **exceed the
entire software figure by ~5×** — which is the single most useful fact in this table. **This segment
is overwhelmingly a services market.** For Globant that is favourable and should be said plainly: the
money here is in delivery, not in a licence, and the two independent services estimates corroborate
each other more tightly than anything else in this file.

⚠️ The **CAGR spread is 13.6% to 42.0% — a 3.1× disagreement on growth**, which is wider than the
spread on size. When vendors disagree more about the rate than the level, the category is too young
to forecast; quote the base year and refuse the horizon.

⚠️ Coherent segments **"AI visibility monitoring" at 35.0% of the GEO platform market in 2026**,
implying ~$945M. That is a **vendor's own segmentation of a vendor's own aggregate** — recorded for
completeness, not corroborated, and it should not be re-quoted as a measured figure.

### ⛔ The refusal: what a publisher actually wants to know is unsized

Every figure above sizes **spend on GEO tooling and services**. **No source found sizes the thing a
media client asks about: the revenue lost to zero-click answers, or the value of an AI-answer
citation.** That is not an oversight in this pass's searching — it follows from the structural
finding in `intel/trends.md`: **an AI Overview emits no click and no referrer**, and Google's own
instrument reports **impressions without clicks**. You cannot size a market in events that are not
emitted. So the honest position for a proposal is:

- ✅ **Quotable:** the segment's own spend, as a **services** market, ~$1.78–1.97B in 2026 (two
  independent, mutually corroborating estimates), with the 7.3× scope caveat stated.
- ✅ **Quotable:** the measured referral declines in `intel/trends.md` (Chartbeat −60/−47/−22%,
  Press Gazette US −38% vs Europe −17%), with Google's stated methodological objection attached.
- ⛔ **Refuse:** any figure for "value of an AI citation", "revenue lost to AI Overviews" per
  publisher, or an ROI multiple on GEO work. These do not exist, and a number invented here is the
  one a client's CFO will test first.

### Global players — pass 30 addendum (the discovery & measurement layer)

| Player | Position in this plane |
|---|---|
| **Google** | Owns both sides: the surface that removes the click (AI Overviews, AI Mode) **and** the only authoritative instrument for observing it (Search Console gen-AI reports, 2026-06-03, impressions only, no backfill). Also the defendant in the Penske action and the public disputant of the causality. |
| **Cloudflare** | The CDN-layer measurement and enforcement tier (Attribution Business Insights; pay-per-crawl). **Proprietary**, and pass 5's measured zero on settlement is still unmoved. |
| **Ahrefs / Semrush / Conductor** | The commercial measurement tier, and — notably — the main **publishers of evidence** about this plane (Ahrefs' 137,210-domain `llms.txt` study; Conductor's ~1% figure). Vendors with a stake, producing the best available data. ⚠️ Cite with the conflict noted. |
| **AthenaHQ / Rankscale / Profound / Writesonic** | The pure-play AI-visibility vendors. All closed-source; they define buyer expectations for the category. |
| **Microsoft** | Owns the highest-starred permissive readability tool in the plane (**MarkItDown**, MIT, 198,609★) and a listed `chatbot:` referrer (Copilot). |
| **Answer.AI (AnswerDotAI)** | Author of the `llms.txt` standard (Apache-2.0, 2,702★). Recorded as the plane's **measured failure**, not as an incumbent. |
| **Matomo / Umami / GoAccess (allinurl)** | The open measurement substrate. Only **Umami and GoAccess are MIT**; Matomo is GPL-3.0. The licence line runs straight through this tier. |
| **IAB Europe / AOP / Chartbeat / Reuters Institute** | The evidence institutions. For this plane they matter more than most vendors, because **the dispute is about measurement** — and AOP's genre-level finding and IAB Europe's explicit "no European consensus" are the two most useful things any of them has published. |

## Market size — pass 31 addendum (2026-11-27): live entertainment is sized, **show control is not sized at all**, and the one number worth quoting is a transaction price

Added 2026-11-27 (pass 31). Searched for sizing on the live-event, show-control and stagecraft plane.
The pattern is now familiar enough to state as a rule: **the audience-facing market is sized by
several vendors who disagree, and the technology layer this KB actually builds in is unsized.**

### ⛔ The refusal first

**No show-control market sizing exists.** Searched explicitly for lighting-console, media-server and
show-control market data; the result was *"I found no dedicated show-control market data (such as
lighting or media-server console sales)."* The closest proxies are **stage-lighting hardware**
figures, which measure fixtures and fittings — a different business from the control layer, and not a
substitute for it. **Do not convert a stage-lighting hardware number into a show-control number.**

This is the ninth plane in this KB whose software layer is unsized while its hardware or audience
layer is sized, and the explanation is the same every time: analysts size what is purchased in
catalogues, and control software here is either bundled with a console, free, or built in-house.

| Estimate | Source type | Note |
|---|---|---|
| **Global live entertainment: ~5.9% CAGR (2026–2035)** | Market-research vendor | The broad audience-facing cut. Directional only. |
| **APAC ≈ 23% of global live music; 2026 ≈ $2.7B China / $1.5B Japan / $0.9B South Korea, ~8–11% CAGR** | Cognitive Market Research | **Internally inconsistent** — its headline and 2026 figures do not fully reconcile. Quote only with that caveat. |
| **LATAM ≈ 6.0% of global concert halls & theatres = ~$2.28B (2026)** | Fairfield Market Research | Single vendor, unverified. |
| **Stage/show lighting hardware: APAC ~5.4% CAGR to 2033; China stage illumination 8.80% CAGR to 2031; global LED stage lighting ~7.4%, China ~7.6%** | Four separate vendors | A **5–9% spread** on the same question. This is *hardware*, not control software. |
| **Show-control / console software market** | — | **NO DATA FOUND. The refusal above.** |

### What can be stood behind instead — a transaction price, which beats every estimate in this table

The most defensible numbers in this plane are not market estimates at all; they are **what a buyer
actually paid**, reported by trade press:

- **Live Nation paid $646M for an additional stake in OCESA (Mexico) in 2025**, taking it to 75%,
  after **over $400M** for control in 2021.
- It also took a **majority of Movistar Arena, Buenos Aires**, bought into a major **Santiago** arena,
  and entered **Peru**.
- **Brazil is the #9 music market worldwide** (IFPI 2025); **Mexico entered the global top ten for the
  first time**, with concert attendance **more than tripling since 2019**.

**Use these in a LATAM conversation in preference to anything in the table above.** A disclosed
transaction price and a federation's market ranking are primary-adjacent facts; a 5.9% CAGR is a
vendor's model. This is the same preference order this KB applied to the CIMM audience-measurement
figures in pass 7 and to government incentive data in pass 27 — and it has now held three times.

### Global players — pass 31 addendum (the live-event & show-control layer)

| Company / body | Type | Strength | Weakness |
|---|---|---|---|
| Electronic Theatre Controls (ETC) | Console & fixture manufacturer (US) | Publishes the **Apache-2.0 reference implementations** of ANSI E1.31/E1.33/E1.20 — the interoperability layer the whole industry depends on | Labels every non-standards tool "UNOFFICIAL"; the console product itself is proprietary |
| MA Lighting / Robe | Console & fixture manufacturers (DE / CZ) | Behind **GDTF/MVR**, now DIN SPEC 15800:2022 — EMEA sets the device-description standard | The fixture library (GDTF Share) is **account-gated**, with per-manufacturer terms |
| Live Nation / Ticketmaster | Promoter, venue owner, ticketing | Consolidating LATAM venue ownership at disclosed prices; AI across ticketing | Dominance is itself a regulatory exposure; its AI claims reach this KB only through secondary summaries |
| AEG | Venue operator | Running live AI crowd-flow analytics at The O2 | Vendor case-study evidence only |
| Disney / Europa-Park | Attraction operators | Investing in attraction AI (two Disney patent filings, Aug 2026; Europa-Park's "AI Suite") | **Filings and statements, not shipped products**; ride control stays closed and safety-rated |
| Audinate (Dante) | Audio-over-IP | De-facto standard for venue audio transport | **No open implementation**; AES67 is the open alternative |

## Market size — pass 32 addendum (2026-11-27): the connected-TV segment is sized **~28× apart on the same base year** — the widest headline spread in this file — and device certification is not sized at all

Added 2026-11-27 (pass 32). Searched for sizing on the device, TV-app and client-playback plane.

### ⛔ The refusal first

**There is no defensible single number for "connected TV" in 2026.** Five vendors, same base year:

| Source framing | 2026 figure | Forecast | Implied CAGR |
|---|---|---|---|
| Grand View Research | **USD 318.6B** | USD 757.6B by 2033 | 13.2% |
| Business Research Insights | **USD 285.36B** | — (to 2035) | 15.23% |
| Fortune Business Insights | **USD 264.61B** | USD 414.57B by 2034 | 5.77% |
| Future Market Insights | **USD 192.0B** | USD 489.0B by 2036 | — (from a $175.0B 2025 base) |
| Persistence Market Research | **USD 11.4B** | — (to 2033) | 12.1% |

**Low to high is ~28×, and the CAGRs disagree by a factor of 2.6 on top of that.** This **supersedes
pass 3's captioning spread (~18×) as the widest headline disagreement in this file**. Pass 21
(volumetric video) keeps the separate record for *worst agreement on an identically-scoped base
year*; here the spread is a **scope artefact**, and naming it is the whole value:

- The **$264B–$319B cluster** is counting the **device and advertising economy** — TV hardware,
  platform revenue and CTV ad spend together.
- The **$11.4B figure** is plainly counting something narrow (platform software / a device-services
  cut).
- A **$192B** figure sits between the two definitions.

→ **Never put a CTV market number in a deck without the definition attached.** The question to ask a
client is: *"does your figure include hardware, advertising, or neither?"* The answer moves the
number by a factor of 28.

### ⛔ The second refusal, and it is the one that matters for this plane: **device certification and QoE testing are unsized**

Globant's addressable work here is **app engineering, certification and playback quality** — and no
source sizes any of those. What exists is adjacent and must not be substituted:

| Adjacent figure | 2026 value | Why it is NOT this segment |
|---|---|---|
| CTV ad solutions | ~**USD 6.72B** (10.4% CAGR to 2034) | Ad-tech spend, not app or device engineering |
| CTV demand-side platforms | **USD 7.35B** (2025), 30.20% CAGR | Same — the buy side |
| TV operating systems | → **USD 9.36B by 2034**, 15.80% CAGR | Platform licensing, not services on top |
| Communication test & measurement | **USD 11.37B (2026)** → USD 19.73B (2032), 9.6% | **Not TV-specific** — network test equipment at large |

### What can be stood behind instead — count the certifications, not the market

The honest substrate is **per-platform certification volume**, which is observable:

- **A single streaming app faces separate certification on each store.** One vendor's CTV testing
  practice lists **Samsung Tizen, LG webOS, Google TV, Apple TV and Roku**; add **Fire TV, Hisense
  Vidaa, Titan OS** and operator STBs (RDK) and the realistic matrix is **8–10 targets per release**.
- **Observed test load at one monitoring vendor: "over 300,000 test runs a month across 69 mobile
  devices and six smart TV platforms."** That is a measured production figure, and it is the right
  order-of-magnitude anchor for a certification engagement — **six** smart TV platforms, not one.
- **Reach anchor:** connected TV reached **96.4 million US households** (Comscore, 2025).
- **The open substrate is 51 stars** (`dpctf-*` + WAVE + `ott_device_matrix`, verified 2026-11-27)
  and its verdict component is **Commons-Claused against consulting revenue**. So the work is real,
  recurring, per-platform, and has **no open product competing for it** — which is a far better
  argument than any of the five numbers above.

→ **Quote releases × platforms × devices, not market size.** A client with four releases a year
across nine platforms has a concrete, defensible scope; the CTV "market" does not.

### Global players — pass 32 addendum (the device & client-playback layer)

**The platform owners (these are the gatekeepers, and all are closed):** **Roku** (Roku OS),
**Samsung** (Tizen), **LG** (webOS — open-core via webOS OSE), **Google** (Android TV / Google TV),
**Amazon** (Fire TV), **Apple** (tvOS), **Hisense** (Vidaa — *gaining European share from webOS*),
**Titan OS** (~4% Europe), **Comcast/Sky** (RDK — open via `rdkcentral`). ⚠️ **Share estimates for
these conflict badly across sources and mix installed base, shipments and "most-used"** — see the
North America block for two contradictory readings of the same analyst.

**The test and QoE houses — and note who contributes to the open stack:** **Resillion UK** (named
**contributor** to the Commons-Claused `device-observation-framework`), **Witbe** (QoE monitoring at
the 300,000-runs/month scale), **Norigin Media** (OTT testing-as-a-service across the certification
matrix), **Mozark** (which **open-sourced its own test framework** as
[`mozarkai/optics-framework`](https://github.com/mozarkai/optics-framework), Apache-2.0, 104★).

**📌 The structural read of this player map.** A commercial test house is a named contributor to the
one open component whose licence forbids selling services built on it, while a different test vendor
has published its framework under Apache-2.0 with no such restriction. **The incumbents are not
uniformly closed — they are strategically closed at the verdict and open at the harness.** Globant's
entry point is therefore the harness plus client-owned pass/fail criteria (pattern 32.1), not a
certification product that competes with the bodies writing the licences.

**Standards bodies as the real "players" in this plane:** **HbbTV Association** (EMEA; conformance
suite members-only), **DVB Project** (DVB-I; **MIT** reference client), **ATSC** (NA), **IPTV Forum
Japan** (Hybridcast; NHK's **MIT** SDKs), **SBTVD Forum / PUC-Rio TeleMídia** (Brazil; Ginga,
**GPL-2.0**), **CTA WAVE** and **SVTA** (device conformance and CMCD/CMSD/Open Caching). **In this
plane the standards bodies, not the vendors, publish the reusable code** — which is why the regional
blocks above are organised around standards rather than around suppliers.

## Market size — pass 33 addendum (2026-11-27): the media-monitoring segment, and **the narrowest headline agreement in this KB**

Three estimates, and for once they do not contradict each other by an order of magnitude:

| Source | Base year | Base value | Forecast | Horizon |
|---|---|---|---|---|
| ResearchAndMarkets | 2026 | **$6.1B** | $14.4B | 2034 |
| IMARC-derived | 2025 | **$5.7B** | $13.8B | 2034 |
| Fortune Business Insights | 2026 | **$7.34B** | $18.56B | 2034 |

**On a common 2026 base: $6.1B vs $7.34B = ~1.20× spread.** Set that against pass 32's **~28×**,
pass 30's **~7.3×** and pass 12's **~100×**. This is the **tightest headline agreement recorded in
this file**, and the reason is informative: media monitoring is a mature software category sold as
named seats on annual contracts to identifiable buyers (comms teams, agencies, public bodies). When
analysts can count seats, they converge. Where this KB finds 10×–100× spreads, it is almost always
because the category boundary is contested, not because the measurement is hard.

⚠️ Still vendor-sponsored research with unreconciled scopes (some include social listening, some do
not). **Quote the range $5.7–7.34B, never a single figure**, and say which scope you mean.

### ⛔ The refusal — what a comms client actually wants to know is unsized

None of the above sizes the thing being bought. A client asks: *what is the value of earned coverage
we obtained?* The industry's answer used to be **AVE** (advertising value equivalency), which the
**Barcelona Principles** and AMEC have rejected since 2016. The replacement — **outcome-based
measurement** (outputs → out-takes → outcomes → impact, tagged across PESO) — is a *framework*, not a
number, and **has no open-source implementation** (verified 2026-11-27).

So the segment is well-sized and the *deliverable* is unsized. That is a better position than most
planes in this KB: the budget exists and is agreed, and the method it is meant to fund does not ship.

### Global players — pass 33 addendum (the media-monitoring & press-intelligence layer)

| Player | Position in this plane |
|---|---|
| **Cision** | The consolidated incumbent: owns **Brandwatch** (social listening) and **PR Newswire** (the wire) alongside its own clipping and PR suite, marketed as a combined dataset. One vendor across three functions that were formerly three purchases. Proprietary. |
| **Meltwater** | The all-in-one challenger; **named a Leader in Gartner's first PR & Media Monitoring MQ (2026-10-20)** — ⚠️ per Meltwater's own press release, a vendor source. Proprietary. |
| **Gartner** | Not a vendor but the decisive actor this year: its **first-edition** Magic Quadrant (2026-10-20) converted the category into a procurement line and named **outcome-based earned-media measurement** as a reshaping force. |
| **AMEC** | The standards body. Owns the **Integrated Evaluation Framework** and, with the **Barcelona Principles**, the rejection of AVE. Publishes the method, ships **no code** — the central asymmetry of this plane. |
| **JRC / European Commission (Europe Media Monitor)** | The largest *public* monitoring system in the world — ~20,000 sites, ~500,000 pages/day, 80 languages, 150 countries, LLM-integrated, WHO/EIOS partner. **No public code repository.** Capability without redistributable artifact. |
| **Media Cloud (MIT / UMass / Northeastern)** | The academic counterweight and **the only mature permissive index**: `story-indexer` **Apache-2.0** and alive (2026-08-28); `web-tools` Apache-2.0 and **dormant since 2023-12-14**. ⚠️ Widely mis-reported as AGPL-3.0 from a 2015-era fork — corrected in `repos/foundations.md` pass 33. |
| **Konnect Insights / Germin8 / Truescope / YouScan** | The regional tier, and the real moat-holders: vernacular-language sentiment and local platform integrations (ShareChat, Koo) that global vendors do not cover. Proprietary. |
| **Sprinklr / Hootsuite (Talkwalker) / Sprout Social** | The adjacent social-suite tier; monitoring as a feature of a publishing suite rather than a standalone discipline. Proprietary. |
| **LexisNexis** | The licensed-archive tier — and notable as a publisher of evidence that *defends* AVE's continued use, against AMEC's position. ⚠️ Cite with the conflict noted. |
| **Etipufhu (pr-radar)** | A single developer holding the only end-to-end open implementation of this plane (MIT, created 2026-11-21). Recorded as the measure of how empty the open category is, not as an incumbent. |

---

## Market size — pass 34 addendum (2026-11-27): the ad-fraud loss figure is **2.6× apart**, two vendors disagree on the *direction*, and the one number a buyer needs does not exist

Every figure on this plane is published by a company that sells the remedy. There is no
MRC-accredited public market size for ad fraud, and there is no neutral estimator.

| Estimate | Source | Period | Note |
|---|---|---|---|
| **$63B** lost to invalid traffic | Lunio, *2026 Global Invalid Traffic Report* | 2025, vs $740B+ ad spend | Click-based. Augustine Fou argues publicly it **undercounts**, because it counts invalid clicks landing on sites rather than invalid *impressions*. |
| **>$100B (2026)**, ~$172B by 2028; ~22% of global digital ad spend | Juniper Research | 2026–2028 | ⚠️ Reached via secondary citation only, not read at source. |
| **$165B** | Anura, via eMarketer | 2025 | Described by the source as a *conservative* estimate — i.e. 2.6× Lunio's for an overlapping period. |
| **$84B** | Trade publication | 2026 | A fourth point inside the same spread. |
| **$25.3B** | Spider Labs | **H1 2026 only** | Not comparable to the annual figures; roughly $50B annualised. |
| IVT **26% (Jan) → 31% (Feb) → 40% (Jun)** | Anura | 2026 | Rate, not loss. Driven by **AI-enabled SIVT**. |
| Programmatic IVT **18.12%** / **20.64%** | Q1 2026 / Fraudlogix | 2026 | Two measurements, close agreement — the narrowest on this plane. |
| Mobile app traffic **31% invalid** globally | Vendor report | 2026 | SDK spoofing, click injection, install farms. |
| Fintech **~43%** of ad budget to fraudulent clicks; gaming **18.49%** IVT | mFilterIt / vendor | 2026 | Sector spread is wider than the regional spread. |
| fraud/IVT **down 41% NA, down 45% EMEA** YoY | DoubleVerify | 2026 | ⚠️ **Opposite direction to Anura.** |

### ⛔ The refusal — what a buyer actually needs is unsized

The question a CMO asks is *"how much of my spend was wasted, and what would recovering it cost?"*
There is **no accredited answer at any level of aggregation**: the loss estimates are 2.6× apart, two
vendors disagree on whether the problem is growing or shrinking by ~40 points, and the two most
granular datasets (Lunio and Pixalate) **rank India at opposite ends of the same table**. Nobody sizes
the **verification and brand-safety software market** itself in any source found this pass.

### What can be stood behind instead — a price list, not an estimate

The only hard, officially-published numbers on this plane are the **cost of the gated inputs**, and
they are far more useful in a proposal than a loss estimate nobody can defend:

| Artifact | Published price | Terms |
|---|---|---|
| **IAB/ABC International Spiders and Bots List** | **$5,000** IAB Tech Lab member / **$7,500** IAB associate member / **$15,000** non-member, per year | 12 months from sign-up; delivered via Tech Lab Tools Portal or FTP; **access withheld until payment *and* a signed Data Subscription Agreement**; grant is *limited, non-exclusive, non-transferable, revocable*; fee non-refundable; renewal fee changeable on 60 days' notice. Membership not required to subscribe. |
| **Same service via ABC UK** | **from £4,285 + VAT** per year | Parallel operator; figures and currency differ from Tech Lab's — confirm current fee before budgeting. |
| **IAB Content Taxonomy** | **free** | **CC BY 3.0** — implementable commercially with attribution. |
| **OpenRTB / AdCOM / TCF / GPP specifications** | **free** | **CC BY 3.0.** |
| **OM SDK — JavaScript clients** | **free** | **Apache-2.0**, on GitHub, 76★, pushed 2026-11-02. |
| **OM SDK — native (iOS/Android/CTV)** | not published | Tools Portal download + Tech Lab **compliance programme**. v1.5 (June 2024) current; CTV format support expanded **2026-11-10**. |

**This is the third gated knowledge artifact with a published price list recorded in this KB**, after
the AMA's CPT and MedDRA in healthcare. Three industries, three price lists, same structure: the
specification is free and the *data that makes it operational* is a revocable annual subscription.
That is a pattern, and it is quotable as one.

### Global players — pass 34 addendum (the ad-integrity & verification layer)

| Player | Position |
|---|---|
| **Media Rating Council (MRC)** | The accreditation body, and therefore the real gatekeeper of this plane. Accredits IVT measurement; **requires GIVT, only "strongly recommends" SIVT.** Publishes accreditation letters and quarterly status updates (Q2 2026 update dated 2026-07-14) — **primary, free, and almost never read by the buyers who depend on it.** |
| **IAB Tech Lab** | Owns the specifications (OpenRTB, AdCOM, `ads.txt`, `sellers.json`, `ads.cert`, TCF, GPP, Content Taxonomy, OM SDK) and the **compliance programmes** that gate them. Simultaneously the most generous publisher on this plane (CC BY 3.0 specs, Apache-2.0 reference code) and the operator of its paywall ($5k–$15k bot list, Tools Portal native SDK). |
| **TAG (Trustworthy Accountability Group)** | *Certified Against Fraud* since 2016 — certifies supply-chain practice rather than measurement. ⚠️ Reportedly mandated by GroupM for all programmatic partners (single secondary source). |
| **DoubleVerify / Integral Ad Science (IAS)** | The two scaled verification incumbents. Both continued on **GARM's taxonomy** after GARM was discontinued. DV publishes the most optimistic regional trend data on this plane (−41% NA, −45% EMEA YoY). |
| **HUMAN Security** | MRC-accredited for **GIVT *and* SIVT** under the IVT 2.0 addendum (letter 2026-04-14) — one of the few to hold the harder half. |
| **Anura / Lunio / Pixalate / Fraudlogix / Spider Labs / CHEQ** | The measurement tier, and the source of every loss figure in circulation. **Their estimates span 2.6× and disagree on direction.** Pixalate is the most useful of them for consulting work because it publishes consistent quarterly **regional** benchmarks (NA, EMEA, APAC, LATAM) from >103B impressions/quarter. |
| **mFilterIt** | The India-based regional challenger; ad-traffic validation and mobile fraud detection. The only non-US/EU vendor surfaced on this plane. |
| **GARM / WFA** | **Discontinued August 2024**, days after X's antitrust suit; the settlement reportedly binds the WFA never to revive it or anything similar. Its Brand Safety & Suitability Framework remains in universal use **with no maintaining body.** The governance vacuum of this plane — see `intel/trends.md` pass 34. |
| **Prebid.org** | The only open, permissive institution on the plane: `prebid-server` (Apache-2.0, 595★), `Prebid.js` (Apache-2.0, 1,619★), `prebid/openrtb` (Apache-2.0, 89★). **The one place a consultancy can change the auction's behaviour rather than report on it.** |
| **CrowdSec / OWASP (CRS, Coraza, ModSecurity)** | The security community, holding **~33,000 stars of permissive bot-detection infrastructure** that the advertising industry does not cite and does not use. The largest arbitrage on this plane. |

---

## Market size — pass 35 addendum (2026-11-27): the graphics desk has **no market figure at all**, and the only priced number in the plane is a subscription

Thirty-four passes of this KB have recorded market sizings of varying honesty. This plane has none to
record, and the absence is itself the finding: **no analyst tracks "newsroom data visualisation" as a
market**, because the rendering is free and the spend is distributed across generic SaaS lines.

The only hard price discovered: **Datawrapper's newsroom plans run roughly $33–$564/month**, with a
limited free tier. That is the entire visible monetisation of a plane whose open-source substrate
carries over **450,000 GitHub stars** across the artifacts verified this pass.

What a client engagement is actually priced against, therefore, is **not** the chart tooling:

| Cost line | Open-source status | What it means for a proposal |
|---|---|---|
| Chart rendering | **Free and permissive at every layer** (ISC/MIT/BSD/Apache, 5k–114k★) | Zero licence cost. Do not put it in the budget; put it in the risk-reduction column. |
| Hosted responsive embed + editor UI for non-developers | **Does not exist in open source** (Datawrapper core archived 2021-09) | Either a vendor line item (~$33–$564/mo) or a build. **This is the engagement.** |
| Map tiles / basemap serving | **Removable cost** — [protomaps/basemaps](https://github.com/protomaps/basemaps) (BSD-3) + [maplibre-gl-js](https://github.com/maplibre/maplibre-gl-js) (BSD-3) = single-file PMTiles on static hosting | A permanent per-view fee becomes a build-time artifact. The clearest hard-dollar saving in the plane. |
| Election tabulation data | **Commercial feed; open client archived** ([newsdev/elex](https://github.com/newsdev/elex), 2022) | Feed licence + a bespoke client every cycle. No way around the licence. |
| Chart/annotation design system | **Published but frequently ungranted** (`abcnews/palette`, `abcnews/components-dataviz`, `bbc/bbplot` — all no licence) | Budget for authoring one, not adopting one. |

### Global players — pass 35 addendum (the graphics-desk layer)

| Player | Position | Why it matters | The catch |
|---|---|---|---|
| **Datawrapper** (Germany) | The de facto newsroom chart service | The hosted embed the whole plane is missing. Used across newsrooms by non-developers. | **Not open source despite 2026 guides saying so**: core repos archived 2021-09-06/08, the 1,465★ `datawrapper/datawrapper` has **no licence file**. No self-host path. |
| **Flourish** (Canva-owned, UK) | The most-named tool in a LATAM survey of investigative/data journalists | Template-driven interactive charts, no code | Proprietary; no repository; now inside a design-SaaS roadmap. |
| **Highsoft / Highcharts** (Norway) | The enterprise JS charting incumbent | 12,502★ public repo, mature, extremely complete | **Commercial licence** (`license.txt` → `shop.highcharts.com`, no `LICENSE` file). A public repo that reads as permissive at a glance. |
| **Observable** (US) | D3's authors, commercialised | Publishes [plot](https://github.com/observablehq/plot) (ISC) and [framework](https://github.com/observablehq/framework) (ISC) — a genuinely open core | `framework` last pushed 2026-05-15; the hosted notebook business sets the roadmap, not the OSS. |
| **Apache Software Foundation / Baidu-origin** | Governs **ECharts** (Apache-2.0, 67,808★) | Foundation governance + patent grant: the lowest-risk charting dependency in existence for client work | Chinese-origin provenance is a procurement question in some Western public-sector tenders — raise it before the client does. |
| **Ant Group** (`antvis`) | **G2** (MIT, 12,678★), grammar of graphics | APAC-origin, permissive, actively released | Documentation and issue discussion substantially in Chinese. |
| **Posit** (US) | **Quarto** (MIT), the reproducible publishing spine | One source → HTML/PDF/print; MIT | Company's centre of gravity is R/academic, not newsroom deadlines. |
| **ABC Australia** (`abcnews`) | **The most active open graphics desk in the world** | 231 repos, MIT libraries, `chart-builder` pushed 2026-11-27 | 0–22 stars per repo; `palette` and `components-dataviz` **unlicensed**; bus-factor risk. |
| **NPR / NYT / The Pudding** (US) | The rig lineage (MIT / Apache-2.0) | The templates and formats (`ai2html`, ArchieML, `copytext`, `pym.js`) the profession still runs on | Maintenance has slowed to a trickle: ArchieML 2021, `copytext` 2018, `elex` archived. |
| **The Guardian** (UK) | The only major publisher open-sourcing its **production website** (Apache-2.0) | Reference architecture for a publisher platform | No chart tooling published; not a graphics vendor. |
| **Associated Press** (US) | **Owns the election-data layer** | ABC, CBS, NBC, CNN all on AP tabulation for 2026 and 2028 | Commercial feed; its only open client archived in 2022. **The moat in this plane is the data, never the chart.** |
| **Canner (WrenAI)** | The NL→chart leader by an order of magnitude (Apache-2.0, 18,413★) | Governed text-to-SQL → charts/dashboards over a semantic layer | Young; "governed" is an architecture claim a client will ask you to prove. |

## Market size — pass 36 addendum (2026-11-27): animation is sized four ways **$80B apart**, and the plane's own 2D segment is quoted **5.4× apart** — a scope artefact, not a forecast disagreement

| Scope | Source | 2026 figure | Forward figure | Note |
|---|---|---|---|---|
| Global animation market | Research and Markets | **$449.78B** | $580.11B by 2030, **6.6% CAGR** | The mid estimate |
| Global animation market | Precedence Research | **$492.14B** | $953.31B by 2035 | The high estimate; implies ~7% compounding for a decade |
| Global animation market | Markwide Research | **$412.6B** | — | The low estimate |
| **Headline spread** | — | **~$80B (19%)** | — | One analysis found four firms placing the market between **$371B and $472B** on overlapping years, and warns the larger figures fold in **software licences, hardware, gaming and streaming advertising** alongside animation work |
| Animation **outsourcing** | Mordor Intelligence | **$226.71B** | **10.47% CAGR** to 2031 | The segment a services studio is actually in |
| Animation **outsourcing** | The Business Research Company | **$263.08B** | $431.29B by 2030, **13.2% CAGR** | Spread of **$36.4B (16%)** against Mordor on the same year |
| **2D animation segment** | Precedence Research | **$146.36B (2025)** | — | — |
| **2D animation segment** | Animaker | **$26.9B (2026)** | — | **5.4× below Precedence on an adjacent year** |
| Game animation outsourcing | Business Research Insights | **$3.9B** | — | With **2D ≈ 40% of outsourced demand** — the only 2D-share figure found this pass |
| Anime (Japan, primary trade body) | **AJA, Anime Industry Report 2025** (2024 data) | **¥3.84T (~$25B), +14.8%** | — | Overseas **~$14.25B = 56%, +26%**; production segment **¥466.2B (~$3.06B), +9.1%**. The only figure on this page from an industry body rather than a research vendor |

**What to actually quote.** Use the **outsourcing range ($227–263B, growing 10.5–13.2%)**, because it is
the line a services engagement sits on and the two sources are within 16% of each other. Use **AJA's
¥3.84T** for anime, because it is primary. **Do not quote a 2D segment number**: the two available
figures are 5.4× apart on adjacent years, which is a definitional dispute about whether "2D animation"
means produced content, services, or software seats — a gap of that shape cannot be reconciled by
picking the middle.

**And the number that does not exist:** nobody sizes **inbetweening, clean-up or timing/exposure-sheet
work** as a market, even though those are the line items an outsourcing contract is actually written
against, and even though they are precisely the operations AI is being sold into. The plane's spend is
visible only as undifferentiated "outsourcing".

### Global players — pass 36 addendum (the 2D animation & cel-production layer)

| Player | Position | Why it matters | The catch |
|---|---|---|---|
| **Toon Boom** (Canada) | The 2D production incumbent (Harmony, Storyboard Pro) | The seat every professional 2D pipeline is priced against; the de facto standard in series work | Proprietary, seat-licensed. No self-host or fork path, which is the entire reason OpenToonz's BSD-3 matters |
| **Celsys** (Japan) | Clip Studio Paint — the drawing tool of the manga/anime workflow, **and the publisher of XDTS** | Defined the exposure-sheet interchange format in 2018 with Toei Animation | **The public XDTS spec is frozen at November 2018** while the product has moved on. Controls the plane's registry and is not maintaining its public form |
| **Toei Animation** (Japan) | Studio co-author of XDTS; holds the native **TDTS** variant | The format's authority sits inside a production company, not a standards body | No open client for TDTS exists. A studio-owned format is not a standard |
| **Dwango / OpenToonz project** (Japan) | Released the Toonz lineage as **BSD-3-Clause** (8,386★) | **The single most valuable licence decision in this plane**: the only permissive full 2D authoring base on Earth | `LICENSE.txt` carves out `thirdparty/`, the MyPaint brushes and Tahoma2D portions — resolve those before redistribution |
| **KDE / Krita Foundation** | Krita (GPL-3.0, 10,816★), pushed daily | Where 2D artists actually work, and where AI arrives via plugins (`krita-ai-diffusion` 10,960★) | GPL-3.0: plugin, don't fork-and-ship |
| **Airbnb** (US) | Owns the **Lottie** runtimes (MIT/Apache-2.0, ~95k★ combined) | Made the 2D playback layer free and permissive for the whole industry | **`lottie-web` has not been pushed since 2025-09-01.** The most-used player in the tier is its stalest; ThorVG (MIT) and dotLottie (MIT) are the live paths |
| **Esoteric Software** (Spine) | The 2D skeletal-animation incumbent | `spine-runtimes` is public at 5,384★ and reads as open at a glance | **Spine Runtimes License Agreement requires a paid Spine editor licence.** The most expensive misreading available in this plane |
| **Adobe** (US) | After Effects defines the format Lottie serialises | The whole runtime tier exists to render *Adobe's* output | The authoring side stays proprietary; open source owns playback only |
| **HBAI / Toonflow, Forget-C / Jellyfish** (China) | The two largest **permissively licensed** AI animation production platforms (MIT 22,960★; Apache-2.0 7,353★), both created in 2026 | The 短剧/漫剧 boom produced open platforms, not just products — nothing comparable exists in NA, EMEA or LATAM | Both are months old; model dependencies carry their own licences; documentation is substantially Chinese |
| **Utopai Studios** (US/Korea/Japan) | The best-funded AI-animation pure play: **$60M raised at a ~$1B valuation** (per Wikipedia — secondary) | Working with **DeNA** (Japan, Sept 2026) and **Huace Film & TV** (China); **Utopai East acquired Alquimista Media** (Feb 2026) | Company-reported figures, secondary sourcing. Treat the valuation as unconfirmed |
| **Cartoon Media** (EU) | Runs Cartoon Forum — the financing venue for European 2D series | **1,053 series financed since 1990, >$4.43B**; 2026 edition: 66 projects, **€283.58M** | A market, not a vendor. Publishes the only precise European animation financing numbers in this file |
| **The Animation Guild / IATSE Local 839** (NA) | **The binding constraint in North America** | 2024–27 contract sets GenAI notification and consultation duties; guild survey: **29% of animation jobs disruptable within three years** | Members cannot opt out of GenAI, nor stop their work training models. Renegotiation: **2027** |
| **Ánima Estudios** (Mexico) | Was LATAM's flagship 2D studio | Its July 2026 pause/restructuring with unpaid-wage claims is the region's defining event this year | Sources disagree whether it closed or restructured — do not assert either in a client deck |

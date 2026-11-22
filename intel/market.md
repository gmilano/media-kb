---
industry: media
region: Global
updated: 2026-11-22
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

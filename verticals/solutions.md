---
industry: media
region: Global
updated: 2026-11-22
---

# 🏭 Vertical Platforms — Media & Entertainment

> Real, running systems to start from and add an agentic layer on top — the M&E equivalent of Odoo
> for ERP or OpenMRS for healthcare.
> All rows verified 2026-11-21. **This file previously shipped a single all-em-dash placeholder row
> ending in "Por completar" as live data; it is replaced below with verified platforms.**

## The license shape of this layer — read before choosing

M&E has **no permissively-licensed turnkey platform** comparable to Odoo. The mature
self-hostable platforms are copyleft or source-available, and the permissive options are either
narrow (Owncast, SRS) or headless CMSs borrowed from adjacent industries (Ghost, Payload). This is
the single most important procurement fact in this KB:

- **MIT / Apache → embed freely**: SRS, Owncast, Ghost, Payload, shaka-player, hls.js, Opencast,
  and — new on 2026-11-22, and the most consequential entry in this file — **Sofie**, the MIT
  broadcast automation platform (see below).
- **AGPL-3.0 → deploy unmodified, integrate over REST/API, keep client code in a separate process**:
  MediaCMS, PeerTube, OvenMediaEngine, Immich. Modify the source and you owe source to network users.
- **GPL-2.0/3.0 → separate process, no linking**: Jellyfin, Janus, Navidrome.
- **Source-available, not open source**: Directus, Strapi EE. Commercial terms apply; check before a bid.

## Platforms

| Platform | License | Repo | Stars | Last push | Stack | Use case |
|---|---|---|---|---|---|---|
| Ghost | MIT | [TryGhost/Ghost](https://github.com/TryGhost/Ghost) | 55,872 | 2026-11-21 | Node.js | Publishing + newsletters + memberships. The permissive base for a digital-publisher engagement. |
| Payload | MIT | [payloadcms/payload](https://github.com/payloadcms/payload) | 45,937 | 2026-11-21 | TypeScript/Next.js | Headless CMS, MIT throughout. The cleanest permissive base for a custom media back office. |
| SRS | MIT | [ossrs/srs](https://github.com/ossrs/srs) | 29,445 | 2026-11-18 | C++ | Live streaming origin: RTMP/WebRTC/HLS/SRT. License file read — MIT, not Apache-2.0 as commonly listed. |
| Owncast | MIT | [owncast/owncast](https://github.com/owncast/owncast) | 11,683 | 2026-11-21 | Go | Self-hosted live stream + chat. Only actively-developed MIT live platform. |
| Opencast | ECL-2.0 | [Opencast/opencast](https://github.com/Opencast/opencast) | 512 | 2026-11-20 | Java | Lecture/event capture, scheduling and automated publishing. Permissive (Apache-derived ECL), low stars but used by universities and broadcasters. |
| Strapi | MIT core + Enterprise (`ee/`) | [strapi/strapi](https://github.com/strapi/strapi) | 73,531 | 2026-11-20 | Node.js | Headless CMS. License read: core is MIT, but anything under `ee/` is Enterprise-licensed — **"Strapi is MIT" is only half true**. |
| Jellyfin | GPL-2.0 | [jellyfin/jellyfin](https://github.com/jellyfin/jellyfin) | 59,598 | 2026-11-21 | C#/.NET | VOD/media server with a strong metadata model. GPL — separate process. |
| Directus | Monospace Sustainable Core License v1.0 | [directus/directus](https://github.com/directus/directus) | 38,611 | 2026-11-20 | TypeScript | Data platform / headless CMS over any SQL DB. **Correction: not "BSL" as an earlier cycle recorded** — license file read, it is Monospace SCL v1.0 and is *not* OSI-approved. |
| Navidrome | GPL-3.0 | [navidrome/navidrome](https://github.com/navidrome/navidrome) | 24,872 | 2026-11-20 | Go | Music streaming server (Subsonic API). |
| PeerTube | AGPL-3.0 | [Chocobozzz/PeerTube](https://github.com/Chocobozzz/PeerTube) | 15,421 | 2026-11-20 | TypeScript | Federated video platform (ActivityPub). AGPL — deploy, don't fork into client code. |
| Janus | GPL-3.0 | [meetecho/janus-gateway](https://github.com/meetecho/janus-gateway) | 9,208 | 2026-11-16 | C | WebRTC gateway for low-latency interactive media. |
| MediaCMS | AGPL-3.0 | [mediacms-io/mediacms](https://github.com/mediacms-io/mediacms) | 5,198 | 2026-11-19 | Django/React | The most complete open video CMS: upload, transcode, playlists, REST API. AGPL. |
| OvenMediaEngine | AGPL-3.0 | [OvenMediaLabs/OvenMediaEngine](https://github.com/OvenMediaLabs/OvenMediaEngine) | 3,306 | 2026-11-18 | C++ | Sub-second latency streaming (WebRTC/LLHLS). **Correction: AGPL-3.0, not Apache-2.0** as an earlier cycle recorded — 34,452-byte license file read to confirm. Also **renamed from `AirenSoft/`**. |
| Phraseanet | GPL-3.0 (project-declared; API reports `NOASSERTION`) | [alchemy-fr/Phraseanet](https://github.com/alchemy-fr/Phraseanet) | 276 | 2026-11-20 | PHP | One of the few real open DAM/MAM systems still maintained. |

## Broadcast automation & playout — the layer this KB had no row for

Every platform in the table above is a *web* platform: publishing, VOD, streaming. None of them runs
a **channel** or a **live gallery**, which is what an actual broadcaster buys. That layer exists in
open source, it is mature, and until 2026-11-22 this KB did not list a single one of these.

| Platform | License | Repo | Stars | Forks | Last push | Use case |
|---|---|---|---|---|---|---|
| **Sofie** | **MIT** | [Sofie-Automation/sofie-core](https://github.com/Sofie-Automation/sofie-core) | 349 | 63 | 2026-11-19 | **Live studio & news automation** — rundowns, show styles, MOS/NRCS integration, device control. Commissioned by **NRK** as an open replacement for Vizrt Mosart; in daily news production at **NRK, the BBC and TV 2 Norway since 2018**. The only *permissively licensed* broadcast automation platform of any maturity, and the most significant find in this KB's history. Libraries listed in `repos/foundations.md`. |
| CasparCG | GPL-3.0 | [CasparCG/server](https://github.com/CasparCG/server) | 1,112 | 329 | 2026-11-11 | On-air **graphics and clip playout**, from **SVT** (Swedish public broadcaster). The de facto open graphics engine; Sofie drives it over its own protocol, which is also how you keep the GPL at arm's length. |
| ffplayout | GPL-3.0 | [ffplayout/ffplayout](https://github.com/ffplayout/ffplayout) | 607 | 146 | 2026-11-20 | **24/7 linear channel playout** from playlists (Rust + FFmpeg). The pragmatic way to stand up a FAST/linear channel. GPL-3.0 → run as the service it already is. |
| LibreTime | AGPL-3.0 | [libretime/libretime](https://github.com/libretime/libretime) | 940 | 250 | 2026-11-22 | **Radio automation and scheduling** (the maintained fork of Airtime). Pushed on measurement day. AGPL → deploy unmodified, integrate over its API. |
| OpenBroadcaster | AGPL-3.0 | [openbroadcaster/observer](https://github.com/openbroadcaster/observer) | 187 | 55 | 2026-11-13 | **MAM + scheduling + automation** for community radio/TV and IPTV. The closest thing to an open broadcast MAM that is still maintained. |
| OpenBroadcaster Player | AGPL-3.0 | [openbroadcaster/obplayer](https://github.com/openbroadcaster/obplayer) | 144 | 54 | 2026-09-23 | Its playout client, with **CAP / emergency alerting** built in — a real regulatory capability, not a convenience feature. |
| TVPlay | GPL-2.0 | [jaskie/PlayoutAutomation](https://github.com/jaskie/PlayoutAutomation) | 224 | 43 | 2026-04-28 | .NET channel playout automation. The only other real open playout system found. |

**The architectural consequence is large enough to change a bid.** This KB's standing thesis has been
"permissive at the pipeline, copyleft at the platform — so own the pipeline and rent the platform."
Sofie is the exception that breaks it: an MIT platform at the point in the stack where a broadcaster
has the most vendor pain (Vizrt/Mosart licensing) and where the incumbents are most expensive. For a
news or live engagement, Globant can propose **owning and extending the automation platform itself**,
not just bolting agents onto someone's REST API — and do it without inheriting a copyleft obligation.

**Discovery note:** the EBU publishes its own public-domain index of this layer at
[ebu/awesome-broadcasting](https://github.com/ebu/awesome-broadcasting) (CC0-1.0, 1,803★). It is the
right starting point for broadcast tooling; generic GitHub search is not — the measured query
`mos protocol broadcast` returns exactly one result, a dead 2★ student project from 2018.

## Gap: there is no open broadcast MAM

Searched for a permissively-licensed media asset management / MAM system suitable for broadcast and
**did not find one**. What exists:

- `atrocore/atrodam` — **archived** (129★, last push 2025-05-07).
- `immich-app/immich` (119,745★, AGPL-3.0) — excellent, but a personal photo/video library, not MAM.
- `MUKE-coder/mediakit` — recommended by current search results as the MIT option; **the repo does not exist** (404).
- Phraseanet (above) is the closest, at 276 stars and GPL-3.0.

**Refined 2026-11-22 — the gap is narrower than "there is no open MAM".** Two real systems were
found this pass that earlier passes missed, both copyleft:

- [`openbroadcaster/observer`](https://github.com/openbroadcaster/observer) — **AGPL-3.0**, 187★/55f,
  pushed 2026-11-13. Genuine MAM + scheduling + automation, actively maintained.
- [`Sofie-Automation/sofie-package-manager`](https://github.com/Sofie-Automation/sofie-package-manager)
  — **MIT**, 6★/8f, pushed 2026-11-16. Not a MAM, but it is the permissive *ingest, transfer and
  transcode orchestration* piece, which is the half of a MAM that is expensive to build.
- [`immstudios/nebula`](https://github.com/immstudios/nebula) — **ARCHIVED** (GPL-3.0, 20★, last push
  2023-04-26). Current search results still recommend it as an open MAM; it is dead. Do not adopt.

**Implication for Globant, restated precisely:** the accurate claim is not "MAM is a build" but
"**the catalogue is a build; the plumbing is not.**" Asset *movement* can be assembled from
`sofie-package-manager` (MIT) and the pipeline in `repos/foundations.md`; the searchable
asset/metadata/rights **catalogue** is still the custom, high-margin deliverable, because every
permissive option stops short of it and the one maintained full MAM is AGPL. That is a sharper and
more defensible pitch than the previous blanket statement.

## Ad serving and audience analytics — the monetization platforms

New on 2026-11-22 (second pass). This file had no row for the systems a media client uses to **sell**
inventory and **count** audiences, which is the other half of every broadcaster and publisher P&L.

| Platform | License | Repo | Stars | Forks | Last push | Use case |
|---|---|---|---|---|---|---|
| Revive Ad Server | GPL-2.0 | [revive-adserver/revive-adserver](https://github.com/revive-adserver/revive-adserver) | 1,522 | 618 | 2026-11-21 | **The only maintained open-source ad server**, and still actively pushed. Descendant of OpenX. Built for display/banner inventory — it is *not* a CTV/SSAI ad server, so do not propose it as one. |
| Eyevinn Channel Engine | Apache-2.0 | [Eyevinn/channel-engine](https://github.com/Eyevinn/channel-engine) | 134 | 34 | 2026-11-06 | Permissive FAST channel assembly with ad-break signalling. The one platform-shaped component in this plane that carries no copyleft obligation. |
| Matomo | GPL-3.0 | [matomo-org/matomo](https://github.com/matomo-org/matomo) | 22,046 | 2,944 | 2026-11-22 | Self-hosted web analytics; the GDPR-defensible Google Analytics replacement for a publisher. |
| Plausible | AGPL-3.0 | [plausible/analytics](https://github.com/plausible/analytics) | 29,912 | 1,945 | 2026-11-21 | Lightweight, cookie-free analytics. AGPL — deploy unmodified, integrate over its API. |
| PostHog | **MIT with a proprietary `ee/` carve-out** | [PostHog/posthog](https://github.com/PostHog/posthog) | 41,022 | 3,722 | 2026-11-22 | Product analytics with session replay and flags. The LICENSE file is MIT **except** everything under `ee/`, which has its own terms. Read as MIT-core, commercial-enterprise — closer to Directus/Strapi in this file's taxonomy than to Ghost. |

**Excluded after reading the licence, not before:** `countly/countly-server` presents as open source
in roundups, but its LICENSE.md is the **"Countly Lite License"** — a vendor licence, not an OSI one.
It does not belong in a permissive recommendation and is listed here only so the next pass does not
re-add it.

### This plane obeys this file's licence law exactly

The rule at the top of this file — **permissive at the pipeline, copyleft at the platform** — was
derived from generation and delivery repos. The monetization plane was researched independently this
pass and lands in precisely the same shape, which is the strongest confirmation the rule has had:

- **Permissive at the primitives:** Prebid (Apache-2.0, all three), SCTE-35 parsers (Apache-2.0/MIT),
  Druid, Pinot, Superset, Snowplow (all Apache-2.0), channel-engine (Apache-2.0).
- **Copyleft at the platforms:** Revive GPL-2.0, Matomo GPL-3.0, Plausible AGPL-3.0, PostHog's `ee/`.

The practical consequence is the same prescription: **assemble the ad stack from permissive
primitives you own, and keep any copyleft platform in a separate process behind its API.** There is
one genuine difference from the generation side. In generation, the permissive layer is where the
innovation is. Here the permissive layer is *infrastructure that already works* — Prebid was pushed
the day this was written — and the value Globant adds sits in the decisioning and creative layer
above it, which `agents/top.md` measured as empty.

## How to add the AI layer

1. Deploy the platform **unmodified** — this preserves your license position for AGPL/GPL bases.
2. Integrate over its REST/GraphQL API from a separate service you own.
3. Put agents (`agents/top.md`) in that service; keep model weights and prompts on your side of the line.
4. Emit C2PA Content Credentials on every generated asset (`compose/patterns.md`, Pattern 1) — in the
   EU, South Korea, Vietnam and India this is now a legal requirement, not a nice-to-have.

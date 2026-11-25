---
industry: media
region: Global
updated: 2026-11-25
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

## The accessibility layer of this plane — and the platform that is missing

Added 2026-11-22 (pass 3). The EAA does not only require a caption *file*; it requires the service
to deliver it and the player to expose it. That makes accessibility a **platform** question, not just
a tooling one — so it belongs in this file, not only in `agents/top.md`.

### Gap: there is no open collaborative subtitling platform — and there is a reason

This is the second structural gap this file records, alongside "there is no open broadcast MAM".

**Amara** was the open collaborative subtitling platform — the one every list still cites. Its own
about page continues to describe the project as AGPL. **It is not: Amara announced it was closing its
source code in January 2020**, and the code has been proprietary since. The docs that promise "the
source code to Amara is available on GitHub" are stale, and the ReadTheDocs build behind them has not
been rebuilt in roughly three years. No current repository or self-hosting path was found.

Do not promise a client a self-hosted Amara. The honest position: the *tools* for subtitling are
permissive and excellent (Subtitle Edit MIT, subaligner MIT, ttconv BSD-2), the *multi-user
workflow platform* around them does not exist in open source and has to be built. That is a scoped,
fundable engagement rather than a disappointment, and it is the strongest platform-shaped opportunity
in this plane.

### The one platform here with accessibility as a core service — verified in the source tree

| Platform | License | Repo | Last push | What was verified |
|---|---|---|---|---|
| Opencast | ECL-2.0 (Apache-derived, permissive) | [Opencast/opencast](https://github.com/Opencast/opencast) | 2026-11-22 | Already in the table above for lecture capture. **Re-examined this pass for accessibility, and it is the standout:** caption is a first-class service (`modules/caption-api`, `caption-impl`, `caption-remote`), with converters for **DFXP/TTML, WebVTT, SubRip and MPEG-7**, plus a transcription subsystem with engines for **Whisper, whisper.cpp and Vosk** — i.e. fully local ASR, no cloud dependency — alongside Google and Azure. Confirmed by listing the repo tree, not from documentation. |

For a client that needs an auditable captioning pipeline on permissive licences, this is the shortest
path in the whole KB: Opencast already has the service, the formats and local Whisper wired in. What
it lacks is an **IMSC** converter (DFXP is the older TTML profile) — which is exactly the hole
`sandflow/ttconv` fills as a sidecar.

### Accessibility capability of the rest of this table — stated honestly

The remaining platforms carry caption *files* as assets without treating conformance as a feature.
MediaCMS and PeerTube both accept subtitle uploads and serve them; neither validates them, neither
handles audio description as a distinct track, and both are AGPL-3.0 — so they are deploy-and-
integrate, not fork-and-embed. Jellyfin has the richest client-side subtitle handling of the group
and is GPL-2.0.

### The player tier — where the duty is actually discharged

| Component | License | Repo | Last push | Role |
|---|---|---|---|---|
| Able Player | MIT | [ableplayer/ableplayer](https://github.com/ableplayer/ableplayer) | 2026-11-20 | The accessible player: audio description via a described `<source>` or a WebVTT `descriptions` track, and sign language in a second synchronized player. MIT, so it can be embedded in client code directly. |
| dash.js | BSD-3-Clause | [Dash-Industry-Forum/dash.js](https://github.com/Dash-Industry-Forum/dash.js) | 2026-11-22 | DASH reference player, accessibility track selection. |
| axe-core | **MPL-2.0** | [dequelabs/axe-core](https://github.com/dequelabs/axe-core) | 2026-11-16 | Automated conformance checking of the player *UI*. MPL-2.0 is file-level copyleft: ship it unmodified and the client's own code stays closed. |

The FCC's caption-display-settings rule (compliance date **2026-08-17**) is judged on four factors —
proximity, discoverability, previewability, and consistency/persistence. Those are properties of the
player UI, not of the caption file. A pitch that only promises machine captions does not answer this
rule at all; Able Player plus an axe-core gate does.

## The preservation & repository tier — added 2026-11-22 (pass 4)

The platform layer for archives. This KB already recorded that **there is no open broadcast MAM**
(see the gap section above); that remains true. What does exist — and what this file had no row for —
is the **library/archive** repository tier, which is mature, standards-based, and the natural host
for a media archive that has to survive longer than any vendor.

| Platform | License | Stars / forks | What it is | Customizable with AI? |
|---|---|---|---|---|
| [Fedora (fcrepo)](https://github.com/fcrepo/fcrepo) | **Apache-2.0** | 255★ / 138f | Durable repository core with a linked-data API. Built to outlive its own software. | Yes — permissive, API-first; embeddings and enrichment attach cleanly alongside it. |
| [Archivematica](https://github.com/artefactual/archivematica) | **AGPL-3.0** | 527★ / 136f | The reference **OAIS-conformant** preservation pipeline: ingest → normalize → package → store. | Yes, as an integrated system. AGPL means the obligation follows a networked deployment. |
| [ArchivesSpace](https://github.com/archivesspace/archivesspace) | **ECL-2.0** | 449★ / 255f | Archival description, accessioning and public access. 255 forks on 449 stars — institutions run it. | Yes — ECL-2.0 is Apache-2.0-shaped and permissive in practice. |
| [Islandora](https://github.com/Islandora/islandora) | **GPL-2.0** | refs=1659 (stars unavailable — see note) | Drupal front end over Fedora: the "repository with a website" option. | Yes, as a deployed system; GPL-2.0 constrains redistribution of derivatives. |

### This tier obeys this file's licence law — with one exception that matters

This file's standing rule is **permissive at the pipeline, copyleft at the platform**. It holds again:
Archivematica is AGPL, Islandora GPL-2.0. The exception is the important part — **Fedora is
Apache-2.0**, which makes it the one platform in this tier you can build a client-owned product
*around* rather than merely *deploy*. It is also the quietest: 255 stars, 138 forks. A fork ratio of
1.8 is what real infrastructure looks like, and it is why star count is the wrong way to choose here.

**Note on Islandora's numbers.** `search/repositories` returns nothing for `Islandora/islandora`
while `git ls-remote` returns 1659 refs. The repository plainly exists and is substantial; the search
index simply does not have it. Stars are recorded as unavailable rather than guessed. This is the
fifth time this KB has measured that false negative — **existence is `ls-remote`, full stop.**

### The gap, stated plainly: nothing here was built for broadcast

Every platform above comes from the library, museum and university-archive world. They model
*objects and descriptions*, not **frames, timecode, essence and carriage**. There is no open platform
that does both — OAIS-grade preservation *and* broadcast-grade media handling. That is a real,
measured hole in the open landscape and the reason `compose/patterns.md` P14 assembles the archive
path from a permissive repository core plus the conformance tooling in `repos/foundations.md`,
instead of naming a product. If a client already runs Archivematica or ArchivesSpace, integrate; if
they are starting clean and want to own the result, start at Fedora.

## The identification & catalogue tier — added 2026-11-22 (pass 5)

The platforms that answer *"which asset is this, and what do we know about it?"* This tier was absent
from this file entirely.

| Platform | Licence (verified) | Stars / forks | Last push | What it is, and the honest limit |
|---|---|---|---|---|
| [beets](https://github.com/beetbox/beets) | **MIT** (`LICENSE`, 1079 B) | 15,972★ / 2,207f | 2026-11-22 | Catalogue manager with a real plugin API; ships MusicBrainz lookup **and** Chromaprint fingerprinting. Audio-only, CLI-first, single-user by design — it is a **library spine, not a multi-tenant service**. |
| [MusicBrainz Server](https://github.com/metabrainz/musicbrainz-server) | **GPL-2.0-or-later** (`COPYING.md`; `leaflet` BSD-2) | 1,114★ / 347f | 2026-11-19 | The open music-metadata encyclopedia. The *database* is the asset; self-hosting the server is a real operation, not a weekend. |
| [Picard](https://github.com/metabrainz/picard) | GPL-2.0 (`COPYING.txt`, 17983 B) | 5,398★ / 479f | 2026-11-19 | Desktop tagger: AcoustID fingerprint → MusicBrainz identity. The working **proof** that the ID→metadata join is solvable with open parts. Desktop, not a service. |
| [ListenBrainz](https://github.com/metabrainz/listenbrainz-server) | GPL-2.0 (`LICENSE`, 18205 B) | 1,077★ / 402f | 2026-11-22 | Open listening-history + recommendation data. Ratio 2.7 = genuinely deployed. |
| [ISCC Web](https://github.com/iscc/iscc-web) | Apache-2.0 | 9★ / 4f | 2026-11-09 | HTTP service around ISO 24138 content codes. A **deployment template**, not a platform — treat it as the 200 lines you would otherwise write. |

### This tier obeys this file's licence law — and names the exception precisely

The law this file records (*permissive at the pipeline, copyleft at the platform*) holds for all three
MetaBrainz platforms: **GPL-2.0 across the board.** The exception is **`beets`, which is MIT at
15,972 stars** — the second MIT platform-tier entry this KB has found (cf. T10), and the more useful
of the two, because it sits exactly where an identification build starts.

**Scoping consequence, stated plainly:** a client product can embed and extend `beets` without
copyleft reaching the product. It cannot do that with MusicBrainz, Picard or ListenBrainz — those are
**services you run and integrate with**, not code you ship. For a music or archive engagement, that
is the single most important line in this file.

### Gap: there is no open rights-management or royalty platform — and the reason is licensing, not neglect

Measured this pass, not inferred: `music royalty accounting` returns **14 results whose top six hold
zero stars between them**, four of them with no licence at all. `rights management media stars:>=50`
returns five hits, **four of which are keyword collisions** (including a DRM-circumvention toolkit —
do not carry it, do not cite it).

So there is no Odoo-of-royalties, no OpenMRS-of-rights. This KB has met this shape before: in
healthcare, the absence of a permissive revenue-cycle platform turned out to be a **licensing
impossibility**, because the output of the process must be expressed in proprietary CPT codes. Media
is the same trap in a different costume:

- **ISRC** (recordings) — IFPI via national agencies. **ISWC** (works) — CISAC. **ISAN** — ISAN-IA.
  **EIDR** — membership association. **CWR** — CISAC society membership.
- A royalty statement is *expressed in those identifiers*. The obligation travels with the content,
  not the code.
- Therefore a royalty platform cannot be bought open **or** built open end to end, and its open layer
  starved: the only two CWR implementations have been dead since **2015** and **2018**.

**This does not close the business — it relocates it**, exactly as healthcare's pass concluded. The
client already pays for the registry memberships. Globant builds the **attribution and judgment layer
on top**, and the deliverable with margin is the rules/attribution logic the client owns, versions and
audits. **What must never be promised is an "all open source" rights or royalty platform.**

The one genuinely open identifier is **ISCC** (ISO 24138:2024, Apache-2.0 implementation) — usable as
the *internal* join key, never as the identifier a client's partners will already recognise. A
26-star reference implementation is a standards-backed bet, not an installed base.

### Gap: the rights-reservation surface has no platform at all

The declaration formats are real and permissive (`ai.robots.txt` MIT 4,265★, TDMRep, RSL 1.0), but
there is **no platform that manages reservations across a catalogue** — no console, no audit trail, no
per-asset policy store. The library for *honouring* reservations (`Spawning-Inc/datadiligence`, MIT)
has been **dormant since 2024-10-09**, and the settlement layer (`pay-per-crawl`) is a measured zero.
See `compose/patterns.md` **P15**.

## How to add the AI layer

1. Deploy the platform **unmodified** — this preserves your license position for AGPL/GPL bases.
2. Integrate over its REST/GraphQL API from a separate service you own.
3. Put agents (`agents/top.md`) in that service; keep model weights and prompts on your side of the line.
4. Emit C2PA Content Credentials on every generated asset (`compose/patterns.md`, Pattern 1) — in the
   EU, South Korea, Vietnam and India this is now a legal requirement, not a nice-to-have.

## The production-pipeline tier — added 2026-11-25 (pass 6)

The systems a studio actually runs to track shots, versions, tasks and renders. This is the tier the
agents of `agents/top.md` pass 6 would sit on, and the tier where this file's licence law gets its
**third** category.

All rows verified 2026-11-25: existence by `git ls-remote`, stars / forks / `pushed_at` / SPDX from
`search/repositories`, licences read from the file where the API returned `NOASSERTION`.

| Platform | Licence (verified) | Stars / forks | Last push | What it is |
|---|---|---|---|---|
| [cgwire/kitsu](https://github.com/cgwire/kitsu) | **AGPL-3.0** | 776★ / 190f | 2026-11-25 | Collaboration platform for animation and VFX production — the closest thing to an open ShotGrid |
| [cgwire/zou](https://github.com/cgwire/zou) | **AGPL-3.0** | 203★ / 148f | 2026-11-24 | Kitsu's API server. Fork ratio **1.4** — the lowest in this file, meaning people *deploy* it |
| [cgwire/gazu](https://github.com/cgwire/gazu) | LGPL-3.0 | 98★ / 67f | 2026-11-24 | Python client for the Kitsu/Zou API — **the integration surface, and weaker copyleft than the platform** |
| [cgwire/kitsu-docker](https://github.com/cgwire/kitsu-docker) | Apache-2.0 | 60★ / 37f | 2026-11-24 | Containerised deployment |
| [ynput/ayon-core](https://github.com/ynput/ayon-core) | Apache-2.0 | 80★ / 93f | 2026-11-25 | AYON pipeline client core. Fork ratio **0.86 — more forks than stars**, the strongest deployment signal in this file |
| [ynput/ayon-backend](https://github.com/ynput/ayon-backend) | ⚠️ **FSL-1.1-ALv2** (3,744 B) | 40★ / 40f | 2026-11-25 | **The AYON server. Source-available, not open source** — see below |
| [ynput/ayon-frontend](https://github.com/ynput/ayon-frontend) | ⚠️ **FSL-1.1-ALv2** (3,744 B) | 31★ / 45f | 2026-11-25 | The AYON web UI. Same licence as the backend |
| [ynput/ayon-launcher](https://github.com/ynput/ayon-launcher) | Apache-2.0 | 55★ / 29f | 2026-11-25 | Desktop launcher |
| [quadproduction/quadpype](https://github.com/quadproduction/quadpype) | MIT | 10★ / 1f | 2026-11-25 | **MIT** pipeline for 2D/3D/VFX productions — an OpenPype-lineage fork, tiny but permissive and active |
| [tumblehead/TumblePipe](https://github.com/tumblehead/TumblePipe) | MIT | 31★ / 2f | 2026-11-25 | A small studio pipeline for animation/VFX in Houdini. Owner-sized and honest about it |

**DCC integrations for AYON, all Apache-2.0 and all pushed within days of this pass:**
[ayon-blender](https://github.com/ynput/ayon-blender) (20★), [ayon-houdini](https://github.com/ynput/ayon-houdini)
(18★), [ayon-python-api](https://github.com/ynput/ayon-python-api) (17★),
[ayon-shotgrid](https://github.com/ynput/ayon-shotgrid) (15★),
[ayon-kitsu](https://github.com/ynput/ayon-kitsu) (14★),
[ayon-resolve](https://github.com/ynput/ayon-resolve) (13★).

### Render-farm platforms

| Platform | Licence | Stars / forks | Last push | Note |
|---|---|---|---|---|
| [AcademySoftwareFoundation/OpenCue](https://github.com/AcademySoftwareFoundation/OpenCue) | **Apache-2.0** | 1,010★ / 273f | 2026-11-23 | Deploy unmodified; the only permissive farm manager at this scale |
| [CGRU/cgru](https://github.com/CGRU/cgru) | LGPL-3.0 | 302★ / 117f | 2026-10-18 | CGRU/AFANASY |
| [uberware/sqi](https://github.com/uberware/sqi) | **AGPL-3.0** | 44★ / 1f | 2026-11-25 | 2026 entrant. AGPL — a hosted render service built on it is a network-copyleft question |

### ⚠️ This tier obeys this file's licence law — and adds a third category to it

The law as this file has carried it: **permissive at the pipeline, copyleft at the platform.** Five
planes upheld it. This tier upholds it *and extends it*:

- **Permissive at the pipeline** — ✅ emphatically. The ASWF substrate under this tier is 19 code
  projects over 100★, all Apache-2.0/BSD-3 (`repos/foundations.md`), and every AYON *client* and DCC integration is Apache-2.0.
- **Copyleft at the platform** — ✅ Kitsu and Zou are **AGPL-3.0**; the independent farm managers are
  **LGPL-3.0** and **AGPL-3.0**.
- **New: delayed-open at the platform** — ⚠️ AYON's server and web UI are **FSL-1.1-ALv2**
  (*Functional Source Licence, ALv2 Future Licence*): source-available now, Apache-2.0 only after a
  delay. **This is not an OSI-approved open-source licence.**

**The practical trap, stated for a proposal.** "AYON is Apache-2.0" is true of everything a developer
touches and false of the server a client would deploy. The licence boundary runs *inside one product*,
between the clients (Apache-2.0) and the service (FSL). Before any AYON engagement, read
`ayon-backend/LICENSE` and decide deliberately — and note that `gazu` (LGPL-3.0) is deliberately
weaker copyleft than the Kitsu platform it talks to, which is the vendor telling you exactly where
the intended integration seam is. **Use it.**

### ⛔ Archived — do not start new work here

| Repo | Licence | Stars / forks | Last push | Status |
|---|---|---|---|---|
| [ynput/OpenPype](https://github.com/ynput/OpenPype) | MIT | 301★ / 118f | 2024-09-18 | **ARCHIVED.** Superseded by AYON. The most-starred pipeline in this lineage is the dead one — a listicle will still recommend it |

### Gap: there is still no open broadcast MAM — and now we can say *why* precisely

The gap recorded earlier in this file stands, and this pass sharpens it. The production world has
**three** maintained open asset platforms (Kitsu AGPL, AYON split-licence, quadpype MIT) plus a
permissive asset-resolution *standard* (`OpenAssetIO`, 353★, Apache-2.0). None of them is a broadcast
MAM: they are built around **shots, tasks and versions**, not around **programmes, rights windows and
playout**. The vocabulary is wrong, not the maturity. A client wanting a MAM cannot be handed Kitsu;
a client wanting shot tracking should never be sold a MAM build.

### How to add the AI layer to this tier, specifically

The generic four-step recipe in **§ *How to add the AI layer*** above applies unchanged. Two
additions this pass measured, continuing its numbering:

5. **Put the agent on the Apache-2.0 client, never on the copyleft server.** For Kitsu that means
   `gazu` (LGPL-3.0, 98★); for AYON that means `ayon-core`/`ayon-python-api` (Apache-2.0) and
   **not** `ayon-backend` (FSL).
6. **Prefer `OpenAssetIO` (Apache-2.0) as the agent's view of "what is an asset"** rather than a
   platform's own schema — it is the one layer here designed to be vendor-neutral, and it keeps the
   build portable between Kitsu, AYON and a studio's in-house tracker. The MCP bridge for it exists
   and has **one star** (`OpenAssetIO/openassetio-mcp`); see `compose/patterns.md` Pattern 17.

---
industry: media
region: Global
updated: 2026-11-26
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

## The audience & personalization tier — added 2026-11-25 (pass 7)

The platforms a media client would **run** to recommend content, test whether the recommendation worked,
and count the audience. Pass 2 added the ad-serving and web-analytics platforms (Revive, Matomo,
Plausible, PostHog — still in the table above, not repeated here). This tier is the demand side.

| Platform | License | Repo | Stars | Forks | Last push | Use case |
|---|---|---|---|---|---|---|
| Jellyfin | **GPL-2.0** | [jellyfin/jellyfin](https://github.com/jellyfin/jellyfin) | 59,763 | 5,878 | 2026-11-25 | The only mature open media server with a real catalogue, user profiles and watch history — **the realistic test bed for a recommender before it touches a client's production OTT stack.** GPL-2.0: deploy it, integrate over its API, do not fork it into a product. |
| Umami | **MIT** | [umami-software/umami](https://github.com/umami-software/umami) | 40,358 | 8,656 | 2026-11-25 | **The only large self-hosted analytics platform that is genuinely MIT** — Matomo is GPL-3.0, Plausible AGPL-3.0, PostHog MIT-with-carve-out. For a publisher that needs to *modify* its analytics platform, this is the one row in this file that permits it. |
| Redash | **BSD-2-Clause** | [getredash/redash](https://github.com/getredash/redash) | 28,902 | 4,647 | 2026-11-25 | Query + dashboard layer over the audience warehouse. Lighter than Superset and more permissive. |
| Cube | **Apache-2.0** by default (dual Apache-2.0 / MIT, `LICENSE` 254 B) | [cube-js/cube](https://github.com/cube-js/cube) | 21,294 | 2,210 | 2026-11-25 | Semantic layer: define "a view", "a unique viewer", "completion" **once**, so the recommender, the ad stack and the board deck cannot disagree. **The highest-leverage small platform in this plane** and the cheapest fix for the cross-platform fragmentation Deloitte names as the binding constraint. |
| Unleash | **AGPL-3.0** (`LICENSE` read, 34,523 B) | [Unleash/unleash](https://github.com/Unleash/unleash) | 14,342 | 933 | 2026-11-25 | Feature flags and staged rollout. **Widely mis-described as Apache-2.0 — it is not.** Run unmodified behind its API or choose Flagsmith. |
| Flagsmith | **BSD-3-Clause** | [Flagsmith/flagsmith](https://github.com/Flagsmith/flagsmith) | 9,879 | 659 | 2026-11-25 | Flags + remote config, self-hostable. **The most permissive real platform in this tier — the default recommendation for client work.** |
| GrowthBook | **MIT with an enterprise carve-out** (`packages/{back-end/src,front-end,shared/src}/enterprise`) | [growthbook/growthbook](https://github.com/growthbook/growthbook) | 8,659 | 919 | 2026-11-25 | The only one here with real statistics — CUPED variance reduction and sequential testing. **This is how you prove a recommender earned its keep** rather than asserting it. |
| Gorse | **Apache-2.0** | [gorse-io/gorse](https://github.com/gorse-io/gorse) | 9,928 | 931 | 2026-11-25 | A recommender **service** with REST/gRPC, not a notebook library — the only component in this plane that is deployable as a platform rather than assembled. Pushed on measurement day. |
| Trieve | **MIT** | [devflowinc/trieve](https://github.com/devflowinc/trieve) | 2,727 | 254 | 2026-01-25 | Search + recommendations + RAG + analytics in one Rust service. MIT and genuinely useful, but **10 months without a push — verify maintenance before proposing it.** |
| OP3 | **MIT** | [skymethod/op3](https://github.com/skymethod/op3) | 144 | 10 | 2026-11-25 | **The only open audience-measurement service in this file.** Podcast download analytics as an open prefix. Works because podcast delivery is an open HTTP download — see the gap note below. |
| iptv-org/epg | **Unlicense** | [iptv-org/epg](https://github.com/iptv-org/epg) | 3,560 | 561 | 2026-11-21 | EPG grabbers for hundreds of sources emitting XMLTV — programme metadata without a vendor feed. Public-domain dedication; **the legality of the underlying *streams* is a separate question from the data.** |

### ⚠️ This tier adds a FOURTH licence category to this file's taxonomy

The rule at the top of this file — **permissive at the pipeline, copyleft at the platform** — held for
generation, delivery, monetization, accessibility, preservation and identification. This tier is the
first that **partly breaks it**, and the exceptions are instructive:

1. **Copyleft at the platform, as expected:** Jellyfin GPL-2.0, Unleash AGPL-3.0, Matomo GPL-3.0.
2. **Permissive at the platform, breaking the rule:** **Flagsmith BSD-3-Clause, Umami MIT, Redash
   BSD-2-Clause, Gorse Apache-2.0, Trieve MIT.** Five permissive platforms in one tier — more than the
   rest of this file combined. The reason appears to be commercial rather than cultural: these products
   monetise **hosting**, not the licence, so they have no reason to use copyleft as a moat.
3. **MIT with a carve-out:** PostHog (`ee/`), GrowthBook (three `enterprise` directories).
4. **NEW — source-available, which is not open source at all:**
   [rudderlabs/rudder-server](https://github.com/rudderlabs/rudder-server) (4,520★, pushed on measurement
   day) is under the **Elastic License 2.0** (`LICENSE`, 3,793 B). **ELv2 forbids providing the software
   to third parties as a managed service** — which is precisely the systems-integrator model. It is
   excluded from the table above and named here so no later pass adds it. Use **Jitsu (MIT)** or
   **Snowplow (Apache-2.0)**.

This joins **delayed-open (FSL-1.1-ALv2, AYON — pass 6)** as the second non-OSI category this file has
had to carry. **Read the LICENSE file of every platform before it reaches a client proposal:** four of
the eleven rows above have a licence that a badge or an SPDX field reports incorrectly or not at all.

### Gap: there is no open audience-measurement platform for video, and podcasting shows exactly why

OP3 is the only open measurement *service* in this file, and it covers **podcasts**. That is not an
accident of community interest — it is structural:

- **Podcast delivery is an open RSS/HTTP download.** The observation point is the publisher's **own**
  redirect. No panel is required, and no gatekeeper can withhold it. So an open, privacy-respecting
  measurement service appeared, and the shared reference data that makes two counts comparable
  ([opawg/user-agents-v2](https://github.com/opawg/user-agents-v2), MIT, **more forks than stars**) is
  maintained collaboratively.
- **Television and streaming are not observable that way.** Measuring them requires either a
  **nationally representative panel** — which CIMM prices at **$110M/year minimum to operate** (see
  `intel/market.md` North America) — or **ACR against third-party content**, which in EMEA was
  **stopped by cease-and-desist** (see `intel/market.md` EMEA). So no platform exists at any star count.

**Prescription, and it is the honest one:** never propose an open-source *currency*. Propose the
client's **own** first-party audience platform — assembled from the permissive rows above — and prove
its value with media-mix modelling and controlled experiments rather than against a rating. Pattern 20.

**Two caveats to carry into any proposal:** OP3 states IAB v2 compliance as a **goal contingent on
sponsorship, not certification** — do not claim it is certified. And `growlfm/odl`, the alternative
open download-counting spec, **exists but has no licence file at all** (verified across six filename
probes while `README.md` returns 200). Use its specification, not its code.

## The live & delivery tier — added 2026-11-26 (pass 8)

> Running systems for contribution, origin, packaging and playout that a studio can deploy and then
> add an agentic layer to. All rows verified 2026-11-26 (`git ls-remote` + `search/repositories`,
> licence read from file wherever the API returned `NOASSERTION` or `NONE`).

| Platform | Repo | Licence | Stars | Last push | What you get |
|---|---|---|---|---|---|
| SRS | https://github.com/ossrs/srs | MIT | 29,457 | 2026-11-25 | Full streaming server: RTMP/SRT/WebRTC/HLS, clustering. **APAC-origin, MIT — the most permissive platform-tier option at scale.** |
| MediaMTX | https://github.com/bluenviron/mediamtx | MIT | 20,772 | 2026-11-25 | Single Go binary, SRT/RTSP/WebRTC/HLS in and out. The fastest credible starting point. |
| ZLMediaKit | https://github.com/ZLMediaKit/ZLMediaKit | MIT *(read)* | 17,729 | 2026-11-25 | C++11 media server, broad protocol coverage. **APAC-origin.** |
| LiveKit | https://github.com/livekit/livekit | Apache-2.0 | 22,396 | 2026-11-25 | Self-hostable WebRTC SFU + agents framework; the interactive/low-latency end. |
| OvenMediaEngine | https://github.com/OvenMediaLabs/OvenMediaEngine | **AGPL-3.0** | 3,309 | 2026-11-25 | Sub-second LL-HLS/WebRTC origin. **Note the rename** — guides still cite `AirenSoft/…`. |
| MistServer | https://github.com/DDVTECH/mistserver | **Unlicense (public domain)** | 521 | 2026-11-23 | Ingest/transcode/playout platform with **zero licence obligations**. |
| Ant Media Server | https://github.com/ant-media/Ant-Media-Server | **no root LICENSE** — open-core | 4,747 | 2026-11-23 | Ultra-low-latency WebRTC platform; Community vs Enterprise split. **Verify terms in writing.** |
| Jellyfin | https://github.com/jellyfin/jellyfin | GPL-2.0 | 59,765 | 2026-11-25 | Media server/library with transcoding and client apps. |
| Tvheadend | https://github.com/tvheadend/tvheadend | GPL-3.0 | 3,587 | 2026-11-25 | DVB/IPTV backend — the broadcast-input platform. |
| Eyevinn Channel Engine | https://github.com/Eyevinn/channel-engine | Apache-2.0 | 135 | 2026-11-06 | FAST/linear channel assembly from VOD. **EMEA-origin.** |
| Apache Traffic Server | https://github.com/apache/trafficserver | Apache-2.0 | 2,001 | 2026-11-25 | Caching proxy / CDN core — the self-hosted edge. |
| RDK Thunder | https://github.com/rdkcentral/Thunder | Apache-2.0 | 61 | 2026-11-25 | Set-top/device framework: the far end of the chain. |

### ⚠️ This tier **breaks** this file's licence law twice — the first plane in which it fails

This file's law has been "copyleft at the platform, permissive at the pipeline" since pass 2, with one
MIT exception. The live & delivery tier produces two exceptions at once, and one of them goes further
than MIT has ever gone:

- **`DDVTECH/mistserver` is public domain.** `COPYING.md`: "dedicated to the public domain… anyone can
  use MistServer for any purpose - including commercial purposes - without any restrictions." A
  platform-tier streaming server with **no obligations of any kind**. At 521★, almost nobody knows.
- **`ossrs/srs` and `ZLMediaKit` are MIT at 29,457★ and 17,729★** — platform-tier systems, not
  libraries, at the permissive end and at the top of the star rankings.

So in this tier the law is not merely bent, it is **inverted**: the most-adopted platforms are the
most permissive ones. The copyleft options (`OvenMediaEngine` AGPL-3.0, `Jellyfin` GPL-2.0,
`Tvheadend` GPL-3.0) are real but are *not* where the adoption is.

### ⛔ The two gates this tier cannot give you, no matter which platform you pick

Every platform above will ingest, transcode, package and deliver. **Neither of the following is
obtainable from any of them**, and both must be sourced commercially — see `repos/foundations.md`:

1. **Premium DRM.** The key/licence server for Widevine, PlayReady and FairPlay requires a signed
   agreement with Google, Microsoft and Apple respectively. ClearKey is the only fully-open DRM and
   no studio accepts it. There is **no open-source path to a Widevine L1 / HDCP premium service.**
2. **Codec patent rights.** The VVC, LCEVC, MPEG-H and AV1 reference implementations are permissive
   in copyright and explicitly grant **no** patent rights (`BSD-3-Clause-Clear` / "No PATENT
   LICENSE"). Pool royalties are a separate budget line.

### Gap: there is no open-source broadcast-grade **playout and channel origination** platform

Searched this pass and stated as a gap rather than left silent. `Eyevinn/channel-engine` (135★)
assembles FAST/linear channels from VOD and is the closest thing that exists; `MistServer` and `SRS`
do playout only in the streaming sense. Nothing open source provides broadcast playout with
as-run logging, secondary events, branding/graphics insertion and redundancy — the capabilities a
channel actually needs. This is the **second** structural MAM/playout gap this KB has recorded (the
first being the absent open broadcast MAM, passes 2 and 6), and it has the same cause: the buyers are
few, large, and already locked to vendors with certification obligations.

### Gap: no maintained open ATSC 3.0 stack, while the US transition runs

`libatsc3/libatsc3` and `Sony/libatsc3` both fail `ls-remote`. Only stale MIT forks exist (13★/2019,
12★/2023). See `intel/market.md` → North America for the deadline this sits under.

### How to add the AI layer to this tier, specifically

The agent layer here is a **measured zero** (`agents/top.md`, pass 8), so everything below is
unbuilt — which is the point:

1. **Start from MediaMTX or SRS** (both MIT) rather than an AGPL platform, so the agent you write
   stays yours.
2. **Instrument before you automate.** Join player-side QoE (`hls.js`/`shaka-player` events) to
   origin and edge logs; `Netflix/vmaf` (BSD-2-Clause-**Patent**, express patent grant) gives you an
   objective quality number an agent can act on.
3. **Give the agent the ladder, not the pixels.** Rendition selection, segment re-packing and origin
   failover are decisions; generative work belongs in the production plane (pass 6).
4. **Keep the DRM step out of the agent's reach.** It is a contractual boundary, and nothing in this
   plane's tooling can cross it.

---

## The trust & safety tier — added 2026-11-26 (pass 9)

The platform layer that decides whether content may be published, shown to a minor, monetised or
reported. Until this pass this file had **no row** for it, while `intel/market.md` had been
describing the obligations for three passes.

| Platform | Repo | Licence | ★ / forks | Last push | What it replaces |
|---|---|---|---|---|---|
| **ROOST Coop** | [roostorg/coop](https://github.com/roostorg/coop) | Apache-2.0 | 150★ / 55f | **2026-11-26** | The review console of a commercial T&S suite (Hive, ActiveFence, Checkstep). Dashboard, queues, routing, automatic enforcement rules, integrations — **self-hosted, so content never leaves the client's infrastructure.** |
| **ROOST Osprey** | [roostorg/osprey](https://github.com/roostorg/osprey) | Apache-2.0 | 511★ / 73f | 2026-11-23 | The rules engine. **Discord's production engine, donated.** |
| **Jigsaw Altitude** | [Jigsaw-Code/altitude](https://github.com/Jigsaw-Code/altitude) | Apache-2.0 | 44★ / 11f | 2026-06-21 | A whole T&S function for a platform too small to staff one. Explicitly designed for small platforms. |
| **Conversation AI Moderator** | [conversationai/conversationai-moderator](https://github.com/conversationai/conversationai-moderator) | Apache-2.0 | 208★ / 31f | 2026-06-22 | Machine-assisted human moderation for comment sections — the newsroom use case. |
| **Ozone** | [bluesky-social/ozone](https://github.com/bluesky-social/ozone) | dual MIT/Apache-2.0 | 548★ / 94f | 2026-11-23 | Labelling console for atproto. The only **stackable** model here: third parties publish labels, users subscribe. |
| **Draupnir** | [the-draupnir-project/Draupnir](https://github.com/the-draupnir-project/Draupnir) | Apache-2.0 (via REUSE) | 253★ / 30f | **2026-11-26** | Community management and moderation for Matrix. Successor to mjolnir. |
| **EU Age Verification app** | [av-app-android-wallet-ui](https://github.com/eu-digital-identity-wallet/av-app-android-wallet-ui) | **EUPL-1.2** | 309★ / 52f | 2026-11-07 | A commercial age-assurance vendor (Yoti, AU10TIX, VerifyMy). Published by the European Commission, with a ZKP design that reveals only whether the threshold is met. |
| **DSA Transparency Database** | [digital-services-act/transparency-database](https://github.com/digital-services-act/transparency-database) | **GPL-2.0** | 55★ / 10f | 2026-11-25 | Nothing — it *is* the regulator's system. Read it to understand what a statement of reasons must contain. |
| **Marble** | [checkmarble/marble](https://github.com/checkmarble/marble) | **Elastic-2.0 — source-available, not open source** | 629★ / 97f | 2026-11-16 | A fraud/AML decision engine. Listed because it is good and widely recommended, and flagged because the licence class is wrong for a resold build. |

### ⚠️ This tier **breaks** this file's licence law — and the replacement is better

Since pass 2 this file has recorded that **the platform tier is copyleft** (PeerTube AGPL, MediaCMS
AGPL, Castopod AGPL, Funkwhale AGPL, Janus GPL, OpenMontage AGPL, Directus BSL). In the trust &
safety tier, **every platform is Apache-2.0 or MIT**.

The exception is systematic, not random, and it rewrites the law into something that predicts rather
than describes:

> **The publisher sets the licence, not the layer.** An **operator** donating infrastructure it runs
> itself wants adoption and ships permissive (Discord → Osprey, Jigsaw → Altitude, Meta →
> content-review-filters, Bluesky → Ozone). A **vendor** protects a business model and ships
> copyleft or source-available (Marble → Elastic-2.0). A **public body** ships copyleft because
> reuse-with-reciprocity is its mandate (the Commission → GPL-2.0, EUPL-1.2).

Test it against this file's existing rows and it holds: PeerTube, Funkwhale and Castopod are
community/vendor projects, while **Sofie** — the MIT exception this file already flagged as unusual —
was commissioned by **NRK, an operator**. The law was right about the pattern and wrong about the
cause.

### Gap: there is no open age-gated **streaming** platform

Searched. The EU estate provides the age-verification *app*, the *verifier UI* and even a
**cinema** reference frontend, but **no open OTT/VOD platform integrates any of it**. None of the
platforms in this file's main table — PeerTube, MediaCMS, Owncast, Funkwhale, Castopod — has an
age-assurance hook at all. A Brazilian or EU streaming client facing ECA Digital or the DSA has to
have that integration built, and the pieces to build it with are all permissive or EUPL-1.2.
**This is the most concrete unbuilt thing in this file** — see `compose/patterns.md` Pattern 17.

### Gap: no open T&S platform speaks a statutory reporting format

Coop, Osprey, Altitude and Ozone all end at "enforcement action taken." None of them files a
CyberTipline report, a DSA statement of reasons, or an ANPD notification. The only artifacts that do
are [ello/ncmec_reporting](https://github.com/ello/ncmec_reporting) (7★, no licence, dead since
2022-03-29) and [afkzonagroup/rationale](https://github.com/afkzonagroup/rationale) (0★, Apache-2.0,
2026-11-22). **The gap between "we removed it" and "we told the regulator we removed it" is
unbuilt**, and it is the half with legal consequences.

## The theatrical & exhibition tier — added 2026-11-26 (pass 10)

This is the shortest tier in this file, and the shortness **is** the finding. Theatrical exhibition
is a ~$34.6bn channel (2025 box office, Futuresource) running on roughly 200,000 screens worldwide,
and it has **no open-source platform layer at all.** Not a weak one — an absent one.

| Platform | Licence | ★ / forks | Last push | What it is |
|---|---|---|---|---|
| [1105821037/CineTMS](https://github.com/1105821037/CineTMS) | Apache-2.0 | 5★ / 1f | 2026-07-30 | 影院自动化放映控制系统 — cinema automation and theatre management. **The only real open TMS candidate found, anywhere.** Apache-2.0 verified in its own `LICENSE` (11,357B). APAC-origin |
| [cth103/dcpomatic](https://github.com/cth103/dcpomatic) | GPL-2.0 | 175★ / 38f | 2026-11-24 | Not a platform, but the de-facto standard *application* of the tier: the tool festivals, distributors and post houses actually run to produce a DCP |
| [ClairMeta/ClairMeta](https://github.com/ClairMeta/ClairMeta) | **BSD-3-Clause** | 106★ / 30f | 2026-10-10 | The validation service a platform would wrap. The only permissively licensed component in the whole tier |
| [PostPerfection/kdmcourier](https://github.com/PostPerfection/kdmcourier) | AGPL-3.0 | 1★ / 0f | 2026-11-13 | KDM distribution for distributors — cinemas from FLM files, bookings. Two weeks old, 1 star. The nearest thing to a distribution platform |

Four rows, and three of them are libraries or applications rather than platforms. Compare the
trust & safety tier added in pass 9, which had a healthy permissive platform layer that arrived by
donation; this tier has nothing to donate.

### ⚠️ This tier does not merely break this file's licence law — it inverts it

The law stated at the top of this file is *permissive at the component, copyleft at the platform*.
Pass 8 recorded the first plane where it failed twice. **In the theatrical tier the inversion is
total**: the applications and distribution tools are GPL/AGPL, and the only permissive licences are
the validator and the codec substrate. The commercial consequence is concrete and belongs in the
first week of any engagement:

- **Validation, metadata and QC → can be built permissively** on `ClairMeta` (BSD-3) and
  `asdcplib` (BSD-3). This is also where the client's pain is highest, which is a fortunate
  alignment rather than a designed one.
- **Authoring and packaging → cannot.** `dcpomatic`/`libdcp`/`libsub` are GPL-2.0(+),
  `opendcp` GPL-3.0, `DcpToolkit` is MIT but 3★. Either contribute upstream, keep the copyleft
  boundary at a process boundary (a service the client calls, not a library they link), or rewrite on
  `asdcplib`.
- **Key management → does not exist.** 3 stars across the entire open estate.

### Gap: there is no open theatre management system, and the query proves why nobody noticed

`theatre management system cinema` returns **31 results** and `cinema ticketing platform` returns
**350** — and the ceiling across both is **12 stars**. They are student projects, bootcamp
capstones and portfolio pieces, in volume. The abundance is what has kept this gap invisible: a
search looks productive, and every result is a seat-booking form. The real artifacts of the tier —
**TMS, LMS, playout scheduling, KDM ingest, FLM (Facility List Message) exchange** — have, between
them, one 5-star Apache-2.0 repo.

The incumbents are entirely proprietary: GDC, Dolby (CineAsset / CineInspect), Unique, Barco, Sony.
**SMPTE's own `DPROVE2` DCP verifier is a member tool, not open source** — noted so nobody spends a
pass looking for its repository.

### Gap: no open cinema accessibility platform, under a nine-year-old US federal mandate

The DOJ's ADA Title III rule (published 2016-12-02) requires every US movie theatre with a digital
auditorium to **own and maintain** closed-captioning and audio-description equipment delivered to
the patron's individual seat, on a scaling table — 4 captioning devices and 1 audio-description
device for a single-auditorium site, 12 and 8+ for sixteen or more. `cinema accessibility app
captioning` returns **one repository, with zero stars.**

This is the **hardest version of pass 3's finding** anywhere in this KB. Pass 3 recorded a 56-star
ceiling for audio description under a statutory mandate and called it the largest unmet mandate in
media. Theatrical accessibility has a **0-star ceiling under a mandate nine years old**, and the
rule's own limiting clause explains the market precisely: theatres must have the *equipment*, but
the rule **does not require them to add captions or audio description to films not already
distributed with those features.** So the obligation sits on the exhibitor, the content duty sits
with the distributor, and the artifact that connects them — an accessibility track correctly
authored into the DCP and verified before the key is issued — **has no platform, open or
commercial, that treats it as a first-class object.** LATAM has gone further than the US here (see
`intel/market.md`: Brazil's IN 165/2022 and Mexico's new Federal Film and Audiovisual Act), with the
same zero tooling.

### How to add the AI layer to this tier, specifically

The chain is deterministic and already automated; what is missing is judgement *across* steps. Do
not put a model inside `asdcplib`. Put an agent above the pipeline:

1. **Ingest triage.** `ClairMeta` emits structured validation output per DCP. An agent reads 400 of
   those a week, clusters failure modes, and tells an operations team which are reissues, which are
   supplier-systematic and which are one-off — the pass-9 pattern of an agent over typed results.
2. **Key-window reasoning.** KDMs carry dated validity per screen. An agent that joins bookings to
   key windows and flags "this Thursday 19:40 screening has no valid key" is a small build against a
   daily operational risk with **no open competitor at all**.
3. **Accessibility conformance gate.** Check that mandated caption and audio-description tracks are
   present, correctly labelled and actually render, *before* the key ships. This is Pattern 29.

Full recipes: Patterns 28–30 in `compose/patterns.md`.

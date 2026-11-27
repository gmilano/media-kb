---
industry: media
region: Global
updated: 2026-11-27
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
AGPL, Castopod AGPL, Funkwhale AGPL, Janus GPL, OpenMontage AGPL, Directus MSCL-1.0-GPL). In the trust &
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

## Description, cataloguing & syndication platforms — measured 2026-11-26 (pass 11)

Pass 4 catalogued archival *repositories* as preservation systems. This section is the different
question a client actually asks: **what do we run that lets a human or an agent describe, catalogue
and then syndicate the asset?** Licences below are the verified file, not the API's guess.

### Newsroom & editorial systems — the plane's commercial centre, and it is all copyleft

| Platform | Repo | License | Stars / forks | Last push | What you get |
|---|---|---|---|---|---|
| Superdesk | https://github.com/superdesk/superdesk | **AGPL-3.0** | 760★ / 236f | 2026-11-23 | Sourcefabric's end-to-end newsroom: ingest, authoring, curation, archive, distribution. Python. The only serious open newsroom CMS |
| Superdesk Core | https://github.com/superdesk/superdesk-core | AGPL-3.0 | 32★ / 89f | 2026-11-25 | The backend you actually extend (note forks ≫ stars — a build-on repo) |
| Superdesk Newshub | https://github.com/superdesk/newsroom | GPL-3.0 | 24★ / 32f | 2026-11-23 | **Content distribution / syndication** store fed by Superdesk output — the closest open thing to a wire-service delivery tier |
| Wagtail | https://github.com/wagtail/wagtail | BSD-3-Clause | 20779★ / 4750f | 2026-11-26 | Django CMS. **The only permissive option in this table**, and the pragmatic base when AGPL is refused |

**The constraint to state in any proposal:** every purpose-built open newsroom system is AGPL or GPL.
If the client will not accept AGPL for a hosted service, there is **no open-source newsroom CMS for
them** — the honest answer is Wagtail plus custom editorial workflow, not Superdesk.

### Cataloguing & description systems

| Platform | Repo | License | Stars / forks | Last push | What you get |
|---|---|---|---|---|---|
| ArchivesSpace | https://github.com/archivesspace/archivesspace | **ECL-2.0** (`COPYING`, 748 B — Educational Community License, an OSI-approved Apache-2.0 variant) | 450★ / 255f | 2026-11-25 | Archival description **and a metadata authoring tool** — emits EAD, MARCXML, MODS, Dublin Core, METS |
| CollectiveAccess Providence | https://github.com/collectiveaccess/providence | GPL-3.0 | 389★ / 200f | 2026-11-25 | Cataloguing with **out-of-the-box PBCore support**; the configurable choice for AV collections |
| Omeka S | https://github.com/omeka/omeka-s | GPL-3.0 | 534★ / 179f | 2026-11-24 | **Dublin Core native** publishing platform |
| ↳ OAI-PMH Repository module | https://github.com/Daniel-KM/Omeka-S-module-OaiPmhRepository | GPL-3.0 | 5★ / 7f | 2026-10-05 | Exposes Omeka S items to harvesters **and appends IIIF `info.json` + manifest links to the Dublin Core records** — the single cheapest way to make a collection both harvestable and IIIF-viewable |
| Pinakes | https://github.com/fabiodalez-dev/Pinakes | GPL-3.0 | 95★ / 11f | 2026-11-25 | Library cataloguing app; the one real hit from `automatic cataloging library` |

### Repositories & discovery — the exposure tier

| Platform | Repo | License | Stars / forks | Last push | Role |
|---|---|---|---|---|---|
| DSpace | https://github.com/DSpace/DSpace | BSD-3-Clause | 1116★ / 1509f | 2026-11-23 | Repository; **permissive**, and forks ≫ stars |
| Dataverse | https://github.com/IQSS/dataverse | Apache-2.0 (`LICENSE.md`, 10889 B) | 1080★ / 574f | 2026-11-24 | Repository for datasets; **permissive** |
| Blacklight | https://github.com/projectblacklight/blacklight | Apache-2.0 (`LICENSE`, 788 B) | 800★ / 254f | 2026-11-24 | Solr-backed **discovery UI**; permissive |
| Fedora | https://github.com/fcrepo/fcrepo | Apache-2.0 | 255★ / 138f | **2026-11-26** | Repository architecture with OAI-PMH support; permissive, pushed the day of this pass |
| VuFind | https://github.com/vufind-org/vufind | GPL-2.0 | 311★ / 404f | 2026-11-25 | Discovery layer |
| Islandora | https://github.com/Islandora/islandora | GPL-2.0 (`LICENSE`, 18092 B) | *not in the search index* — see method note in `repos/foundations.md` | — | Drupal + Fedora repository framework |
| ↳ Islandora documentation | https://github.com/Islandora/documentation | MIT | 112★ / 69f | 2026-11-25 | The citable, indexed companion repo |
| ↳ Islandora Metadata Committee | https://github.com/islandora-interest-groups/Islandora-Metadata-Committee | no licence file | 37★ / 42f | 2026-11-20 | Where the community's metadata mappings are argued out |

### IIIF — the one genuinely permissive, genuinely healthy sub-stack in this plane

| Platform | Repo | License | Stars / forks | Last push | Role |
|---|---|---|---|---|---|
| Mirador | https://github.com/ProjectMirador/mirador | Apache-2.0 | 625★ / 280f | 2026-11-25 | Multi-window IIIF viewer; comparison and annotation |
| Universal Viewer | https://github.com/UniversalViewer/universalviewer | MIT (`LICENSE.txt`, 1227 B — Wellcome, British Library, NLW) | 576★ / 210f | 2026-11-25 | Embeddable IIIF viewer |
| Cantaloupe | https://github.com/cantaloupe-project/cantaloupe | **NCSA** (`LICENSE.txt`, 1870 B — University of Illinois/NCSA Open Source License, BSD-style permissive) | 308★ / 124f | 2026-11-23 | IIIF **image server**; dynamic derivatives |
| Goobi viewer | https://github.com/intranda/goobi-viewer-core | GPL-2.0 | 27★ / 17f | 2026-11-20 | Presentation of digitised cultural assets |

Three of four IIIF components are permissive (Apache-2.0, MIT, NCSA) and all four were pushed within
six days of this pass. **IIIF is the recommendation when a client needs image/AV delivery with
structure and annotation and cannot take copyleft** — it is the exception to this plane's copyleft rule.

### Informed gaps — searched, and genuinely not there

- **VocBench 3** is real and BSD-3-licensed per the EU's SEMIC catalogue, and was the system used to
  manage **EuroVoc** — but it has **no canonical GitHub repository**. Searching `vocbench` returns
  only third-party Dockerfiles at 1-4★. Its home is outside GitHub; do not cite a GitHub slug for it.
- **ShowVoc**, the second platform the EU Publications Office runs alongside VocBench, has **no
  meaningful GitHub presence** — the top `showvoc` result is 0★.
- **pymarc** (MARC record handling in Python) is **archived on GitHub** at `edsu/pymarc` (259★, last
  push 2020-02-03). The live project is on GitLab at https://gitlab.com/pymarc/pymarc — the only one
  of the 60 URLs in this pass that returned HTTP 200 through curl. Cite the GitLab URL.
- **No open-source system was found that does IIIF delivery *and* OAI-PMH harvesting out of the
  box.** The Omeka S module above is the closest, and it is a 5★ module. Assembling that pair is
  integration work, not adoption.
- **No open implementation of EBUCorePlus tooling** was found beyond the ontology itself — the only
  Java port, `jebu-core`, targets the old EBUCore and died in 2018.

## Audio & music platforms — added 2026-11-26 (pass 12)

Real systems a client may already be running, that can be customised with AI on top. Note the
licence column harder than usual: in this plane the **applications** are copyleft almost without
exception, so "customise and ship" is a different proposition from "customise and operate".

| Platform | Repo | License | Stars | What it is | How AI layers onto it |
|---|---|---|---|---|---|
| **Ardour** | https://github.com/Ardour/ardour | GPL-2.0 | 5,459 | Full professional DAW with surround/Atmos-capable busses; Linux-first, used in broadcast post | Drive it over Lua/OSC for batch dialogue cleanup and conform; keep models out-of-process so the GPL boundary stays clean |
| **Audacity** | https://github.com/audacity/audacity | GPL-3.0 | 19,185 | The most-installed audio editor on earth; standard in newsroom and podcast workflows | Ships a plugin interface; the realistic AI pattern is a **sidecar service** (DeepFilterNet/Whisper) the editor calls, not in-tree model code |
| **EBU EAR Production Suite** | https://github.com/ebu/ear-production-suite | GPL-3.0-or-later | 126 | **The open object-based (ADM) production toolset** — VST plugins + renderer, Reaper-optimised | The only open route from a mix to a conformant ADM/BW64 deliverable. Automate the authoring, render with `bear`/`ebu_adm_renderer` |
| **Zrythm** | https://github.com/zrythm/zrythm | AGPL-3.0 + §7 terms | 3,223 | Modern DAW, active daily | Licence is declared by REUSE pointer — read `LICENSES/` before any derivative |
| **LMMS** | https://github.com/LMMS/lmms | GPL-2.0 | 10,736 | Pattern-based production suite | Generation models (YuE, ACE-Step) produce stems; LMMS is the arrangement surface |
| **Mixxx** | https://github.com/mixxxdj/mixxx | GPL-2.0+ | 7,445 | DJ and radio playout system | Beat/key analysis is built in; `basic-pitch` and `aubio` extend it |
| **MuseScore** | https://github.com/musescore/MuseScore | GPL-3.0 + font exception | 15,489 | Notation application with a very large install base | Pair with `basic-pitch` (audio→MIDI) and `verovio`/`music21` for score interchange |
| **beets** | https://github.com/beetbox/beets | **MIT** | 15,983 | Music library management, tagging, metadata | **The one permissive platform in this table.** Plugin architecture; the natural host for an AI cataloguing step — and the bridge to the description plane (p11) |
| **MusicBrainz Picard** | https://github.com/metabrainz/picard | GPL-2.0 | 5,408 | Reference music tagger over the MusicBrainz database | Pairs with the fingerprinting layer from pass 5 (Chromaprint/AcoustID) |
| **Sonic Pi** | https://github.com/sonic-pi-net/sonic-pi | MIT source, **GPLv3 by linkage** | 12,293 | Live-coding music environment; strong education footprint | Education engagements; note the real distribution obligation is GPLv3 |

**The pattern that works commercially in this plane.** Every application above except `beets` is
copyleft, so the safe architecture is the same one in all of them: **keep the AI out of the
application process.** Run models as a service, have the DAW or editor call it, and ship your own
code under your own terms. The permissive substrate for that service is in `repos/foundations.md` —
`sherpa-onnx`, `DeepFilterNet`, `speechbrain`, `spleeter`, `bear`, `libadm`.

**And the reverse warning:** if the client's ask is literally "a plugin in our Pro Tools rig", there
is no permissive plugin framework. `JUCE` is AGPL-3.0 or a paid commercial licence, and
`tracktion_engine` is the same model. That is a budget line, and it should appear in the proposal
rather than in the third sprint.

## The subscription & reader-revenue tier — added 2026-11-26 (pass 13)

Real, deployable platforms a client can run for the **subscriber** side of media revenue. Pass 2
covered ad serving; this covers identity, entitlement, billing and the publisher's conversion funnel.

| Platform | License | Repo | Stars | Last push | What it is |
|---|---|---|---|---|---|
| Kill Bill | **Apache-2.0** | [killbill/killbill](https://github.com/killbill/killbill) | 5,869 | 2026-11-26 | Subscription billing and payments platform: plans, trials, proration, invoicing, **dunning**. Plugin architecture for PSPs. The permissive anchor of this tier. |
| Keycloak | **Apache-2.0** | [keycloak/keycloak](https://github.com/keycloak/keycloak) | 38,060 | 2026-11-26 | Identity and access management — OIDC/SAML, federation, social login. The subscriber front door. |
| Hyperswitch | **Apache-2.0** | [juspay/hyperswitch](https://github.com/juspay/hyperswitch) | 45,917 | 2026-11-26 | Payments orchestration across PSPs, self-hostable, PCI-compliant posture. APAC-origin (Juspay, India). |
| SpiceDB | **Apache-2.0** | [authzed/spicedb](https://github.com/authzed/spicedb) | 7,243 | 2026-11-24 | Zanzibar-style permission database — the entitlement brain for territory, concurrency and device limits. |
| OpenMeter | **Apache-2.0** | [openmeterio/openmeter](https://github.com/openmeterio/openmeter) | 2,471 | 2026-11-26 | Usage metering and aggregation; pairs with Kill Bill to keep the whole chain permissive. |
| **REMP** | **MIT** | [remp2020/remp](https://github.com/remp2020/remp) | 138 | 2026-11-25 | **The only open reader-revenue platform in existence.** Four services: SSO, Beam (events, conversions, segments), Campaign (offer/banner targeting on those segments), Mailer (newsletters, A/B). Docker-compose. Run in production by Denník N (Slovakia). |
| Lago | AGPL-3.0 | [getlago/lago](https://github.com/getlago/lago) | 10,922 | 2026-11-25 | Metering and usage-based billing. The most-starred billing platform here, and network copyleft. |
| flexprice | AGPL-3.0 | [flexprice/flexprice](https://github.com/flexprice/flexprice) | 6,874 | 2026-11-26 | Usage-based pricing and billing, self-host or cloud. |
| ZITADEL | AGPL-3.0 | [zitadel/zitadel](https://github.com/zitadel/zitadel) | 15,654 | 2026-11-25 | Identity infrastructure — the AGPL alternative to Keycloak. |
| Ghost | MIT | [TryGhost/Ghost](https://github.com/TryGhost/Ghost) | 55,913 | 2026-11-26 | Publishing with **native memberships, subscriptions and newsletters**. Already in this file as a CMS; it belongs here too — it is the one mainstream MIT platform that ships a paid-membership funnel out of the box. |

### ⚠️ This tier obeys this file's licence law — and names the exception precisely

The law recorded across passes 2–12 is "permissive at the library, copyleft at the platform". Here it
holds at the billing tier (Lago, flexprice, Meteroid, keygate all AGPL) and **breaks cleanly at two
platforms**: Kill Bill is a full platform under Apache-2.0, and Ghost is a full platform under MIT.

The distinguishing factor is visible in both cases: Kill Bill and Ghost both monetise through a
**hosted service run by the project's own company**, and neither needs copyleft to protect that,
because the moat is operations rather than source. Lago and flexprice sell the same software they
publish, so they use AGPL to make self-hosting-and-reselling unattractive. **The licence tracks the
business model, not the layer** — which is the sharpest version of this file's law so far.

### Gap: there is no open subscriber-management platform built for video

Searched `topic:subscription-management`, `topic:billing`, `topic:membership` and
`subscription paywall publisher` (6 results). Everything found is either **generic SaaS billing**
(Kill Bill, Lago, flexprice, Meteroid — built for API metering and seat-based plans) or **publisher
reader-revenue** (REMP). Nothing models what a video service actually sells:

- concurrent-stream limits and device registration,
- territory and windowing rights,
- offline-download entitlements with expiry,
- hybrid ad-tier/paid-tier plan switching,
- pause/win-back flows, which is where streaming churn is actually fought.

A video operator today assembles this from Keycloak + SpiceDB + Kill Bill and writes the media
semantics itself. **That assembled schema is the reusable asset, and it does not exist in the open.**

### Gap: the one open churn component is unlicensed and dead

[remp2020/pythia-tools](https://github.com/remp2020/pythia-tools) — churn-propensity aggregation over
REMP's Beam data — has **no licence file at all** (4★) and has not been pushed since **2023-03-20**.
The only open reader-revenue platform did build a churn layer; it is the single unusable piece of it.

### Correction to an earlier cycle of this file

Line ~553 of this file still lists "Directus BSL" in a summary of copyleft/source-available
platforms. **Directus is not BSL**, as the platform table above (line ~40) already records — it is
the **Monospace Sustainable Core License v1.0 (MSCL-1.0-GPL)**. Pass 13 read the licence in full;
its terms, including a professional-services permission and a four-year GPL-3.0 change date, are in
`repos/foundations.md`.

### How to add the AI layer to this tier, specifically

The agent layer here is a measured zero (13th consecutive plane — see `agents/top.md`), so every item
below is a build, not an integration:

1. **Dunning triage** over Kill Bill's failed-payment events — the most obviously automatable task in
   the plane, and `dunning agent` returns 57 repos with nothing above 200★.
2. **Churn-risk scoring** on `lifelines` (MIT) fed by REMP Beam events, replacing the dead
   `pythia-tools`.
3. **Entitlement reasoning** over a SpiceDB graph: "why can this subscriber not play this title in
   this territory on this device" is a question the graph can answer and no product asks.
4. **Cancellation-journey compliance** — see Pattern 13.1 in `compose/patterns.md`; the UK regime
   starts **1 January 2027**.

## The localization & translation-management tier — added 2026-11-26 (pass 14)

These are the Odoo-equivalents of this plane: complete, deployable, self-hostable systems that run a
localization programme end to end, and that AI can be layered **on top of** rather than replacing.
All are real products with real deployments — Weblate and Pontoon run the localization of major open
source estates, and Pontoon is Mozilla's production system.

| Platform | Repo | Licence | Stars | Forks | Pushed | Why it matters |
|---|---|---|---|---|---|---|
| **Weblate** | [WeblateOrg/weblate](https://github.com/WeblateOrg/weblate) | GPL-3.0 | 6,185 | 1,392 | 2026-11-26 | The reference self-hosted continuous-localization server, with tight VCS integration. Highest-star platform in the tier and pushed the day of this pass. GPL-3.0: fine to deploy and to extend for a client; a derived work you distribute is GPL. |
| **Pontoon** | [mozilla/pontoon](https://github.com/mozilla/pontoon) | **BSD-3-Clause** | 1,680 | 620 | 2026-11-25 | Mozilla's own production localization platform. **The only permissively-licensed mature platform in this tier** — the default pick when the client must own and relicense the result. |
| **Lingo.dev** | [lingodotdev/lingo.dev](https://github.com/lingodotdev/lingo.dev) | Apache-2.0 | 5,400 | 812 | 2026-11-20 | Localization-engineering toolchain (CLI/CI oriented). Apache-2.0 core; connects to the vendor's paid engine, so check which half you are depending on. |
| **Tolgee** | [tolgee/tolgee-platform](https://github.com/tolgee/tolgee-platform) | ⚠️ Apache-2.0 **+ `ee/`** | 4,164 | 381 | 2026-11-25 | Developer- and translator-friendly platform. GitHub says `NOASSERTION`; the LICENSE file says **Apache-2.0 by default**, with everything under `ee/` and `/webapp/src/ee` under a separate enterprise licence. Usable — *better* than its badge implies. |
| **Traduora** | [ever-co/ever-traduora](https://github.com/ever-co/ever-traduora) | AGPL-3.0 | 2,140 | 224 | 2026-11-25 | Open translation-management platform. ⚠️ AGPL-3.0: offering it as a hosted service to a client's users triggers the source-offer duty. |
| **inlang** | [generaltranslation/inlang](https://github.com/generaltranslation/inlang) | MIT | 2,012 | 184 | 2026-11-24 | Git-based translation management — the memory and the review history live in the repo. MIT, actively pushed. |
| **Mojito** | [box/mojito](https://github.com/box/mojito) | Apache-2.0 | 389 | 73 | 2026-11-09 | Box's continuous-localization automation platform. Apache-2.0, real corporate maintenance, string-centric. |
| **Localess** | [Lessify/localess](https://github.com/Lessify/localess) | MIT | 75 | 20 | 2026-11-25 | Translation management **plus** CMS in one — unusual and directly relevant to a publisher. MIT, small, current. |
| **Texterify** | [txty-io/texterify](https://github.com/txty-io/texterify) | ⚠️ **BSL 1.1** | 203 | 17 | 2026-10-09 | ❌ **Do not build on this.** See the licence table below. |
| **Serge** | [serge-community/serge](https://github.com/serge-community/serge) | ⚠️ "same terms as Perl 5.10.0" | 228 | 48 | 2024-06-13 | Continuous localization, originally from Evernote. Dormant since mid-2024 and the grant is prose, not SPDX. Reference architecture only. |

### ⚠️ Four platforms, four different licences, one identical GitHub label

Every one of the four rows below is reported by the GitHub API as **`NOASSERTION`**. They are not
remotely the same thing, and the spread runs from *more* permissive than advertised to effectively
proprietary. All four licence files were fetched and read on 2026-11-26.

| Repo | GitHub API says | The LICENSE file actually says | Can Globant build on it? |
|---|---|---|---|
| [tolgee/tolgee-platform](https://github.com/tolgee/tolgee-platform) | NOASSERTION | Apache-2.0 by default; `ee/` and `/webapp/src/ee` under `ee/LICENSE` | **Yes**, outside the `ee/` directories. The label understates it. |
| [txty-io/texterify](https://github.com/txty-io/texterify) | NOASSERTION | **Business Source License 1.1**, *Additional Use Grant: **None***, four-year change date | **No.** BSL with no use grant is proprietary until the change date. |
| [serge-community/serge](https://github.com/serge-community/serge) | NOASSERTION | "the same terms as Perl 5.10.0" → Artistic-1.0 / GPL-1.0-or-later dual | Legally yes, but the grant is unparseable prose and the project is dormant. |
| [dlsandy/Transub](https://github.com/dlsandy/Transub) | NOASSERTION | "MIT License **(Core)**" — with `_advanced/`, "Pro algorithms" and **prompts** excluded | Partially. The MIT half is real; the half that works is not. |

**Rule: `NOASSERTION` is never a verdict. It is an instruction to open the file.** Reading it costs
one request and changes the answer in both directions — it *cleared* Tolgee for use and it
*disqualified* Texterify, and no badge, SPDX field or SBOM scan distinguishes the two.

### A new licence category for this KB: the prompts are the proprietary asset

Pass 12 recorded that a licence can belong to the **compilation** rather than the repository
(Chromaprint: MIT source, LGPL as a whole). `dlsandy/Transub` adds a category that only exists in
the AI era. Its LICENSE reads, verbatim:

> *Transub Pro algorithms, prompts, and the closed module shipped as `_advanced/` are NOT licensed
> under MIT. See LICENSE-PRO and NOTICE.*

**The code is MIT and the prompts are not.** In a repo whose product *is* a prompt chain, that
inverts the usual assumption: the source tree scans clean, every `.py` file is MIT, an SBOM reports
no issue — and the asset that makes the tool work is withheld. Clone it and you have an engine with
the tuning removed.

**Rule, generalisable to all twelve industries: for any AI-era repository, grep the LICENSE and
NOTICE for `prompt`, `model`, `weights` and `Pro` before accepting the badge.** A permissive licence
over code says nothing about the artefacts the code loads.

## The out-of-home, signage & retail-media plane — measured 2026-11-26 (pass 15)

The customisable-platform question for this plane has an unusually clean answer: **three permissive
CMSs you can put AI on top of, one copyleft family you cannot ship closed, and no retail-media
platform at any licence.**

| Platform | Licence | Stars | Last push | Customisable for AI-on-top? |
|---|---|---|---|---|
| [concerto/concerto](https://github.com/concerto/concerto) | **Apache-2.0** | 485\* | 2026-11-26 | **Yes — the Odoo-equivalent of this plane.** Rails + Docker, 18 years of deployment history, permissive |
| [screentinker/screentinker](https://github.com/screentinker/screentinker) | **MIT** | 281\* | 2026-11-26 | Yes, and multi-tenant already — the fastest route to a managed offering |
| [screenlite/screenlite](https://github.com/screenlite/screenlite) | **MIT** | 368\* | 2026-05-08 | Yes, but confirm the project is still moving (quiet ~6 months) |
| [xibosignage/xibo-cms](https://github.com/xibosignage/xibo-cms) | AGPL-3.0 | 520\* | 2026-11-24 | Technically the most capable and complete; **AGPL blocks a closed deliverable** |
| [garlic-signage/garlic-hub](https://github.com/garlic-signage/garlic-hub) | AGPL-3.0 | 151\* | 2026-11-22 | Only if SMIL interop is a hard requirement |
| [Screenly/Anthias](https://github.com/Screenly/Anthias) | GPLv2 + Commercial | 3,745\* | 2026-11-26 | Only under the commercial licence |
| **Retail media network** | — | — | — | **Nothing exists.** `retail media network` = 37 results, the only genuine hit a 3\* link-list. This is a greenfield build |

**The comparison that matters for a studio pitch:** healthcare has OpenMRS, education has Moodle, ERP
has Odoo — each a permissive, decade-old, deployable platform. Out-of-home *does* have its equivalent
in **Concerto** (Apache-2.0, 2008, pushed today), and almost nobody names it, because the search
results and the comparison blogs lead with Anthias and Xibo, which are the two least licence-friendly
options in the plane. **That gap between what ranks and what is usable is itself the finding.**

## The avails, windowing & distribution-rights tier — measured 2026-11-26 (pass 16)

**The headline for a studio engagement: there is no open-source rights-management platform.** Not a weak
one, not a dormant one — none. The systems that actually hold avails and deal terms in production are all
proprietary: **FilmTrack**, **Whip Media**, **Rightsline**, **FADEL**, **Vistex**. A search for
`content licensing rights platform` returns 11 repositories, whose on-topic entries are one GPL-2.0
TypeScript DRM experiment at 1 star and a commercial product's marketing repo at 0.

That changes the shape of the engagement. In every other plane in this KB the question is *which open
platform do we extend*. Here the question is **what do we build beside the incumbent**, and the answer
depends on its API surface.

### The substrate you actually compose from

Since no vertical platform exists, this plane is assembled from horizontal pieces. All verified
2026-11-26:

| Platform | Repo | Stars | Licence | Role in this plane |
|---|---|---|---|---|
| Open Policy Agent | https://github.com/open-policy-agent/opa | 12529* | Apache-2.0 | The window/territory decision engine. Rego expresses "title X, territory Y, date Z, deal D → permitted?" cleanly; this is the only credible answer to step 2 of the gradient |
| Cerbos | https://github.com/cerbos/cerbos | 4669* | Apache-2.0 | Same role, policy-as-config rather than policy-as-code; easier to hand to a rights analyst who is not an engineer |
| Apache Superset | https://github.com/apache/superset | 75692* | Apache-2.0 | Catalogue-composition reporting — the AVMSD 30% share, the Brazilian quota, window-gap exposure by territory |
| ERPNext | https://github.com/frappe/erpnext | 41645* | GPL-3.0 | Where deal and settlement records would land if the client wants one system of record. GPL-3.0 — raise before designing |
| Odoo | https://github.com/odoo/odoo | 56111* | **NOASSERTION** | Contract and subscription modules are the nearest ERP fit. Repo-level licence does not resolve to a single SPDX id; the community/enterprise split must be settled with counsel before it is proposed |
| Metabase | https://github.com/metabase/metabase | 50557* | **NOASSERTION** | Alternative to Superset for analyst-facing avails reporting; same licence caveat — the open-core boundary is the risk, not the code |

### Digital asset management: live, and not licensed for this

Avails records point at assets, so DAM is adjacent. Two real systems are actively maintained, and
**neither is usable under the MIT/Apache/BSD bar this KB works to**:

| Platform | Repo | Stars/Forks | Licence as published | Last push |
|---|---|---|---|---|
| Phraseanet | https://github.com/alchemy-fr/Phraseanet | 276*/106f | **GPL, version unspecified** — its own `LICENSE` reads "Licensed under GPL license" with no version | 2026-11-25 |
| ResourceSpace | https://github.com/resourcespace/resourcespace | 95*/29f | **Unresolved** — `license.txt` says only "Please see the documentation/licenses folder for all applicable licenses" | 2026-11-26 |

Both are **NOASSERTION** on the GitHub API, and this pass establishes *why* in each case, which is the
part a badge cannot tell you:

- **Phraseanet names a licence family without a version.** "GPL" is not a licence; GPL-2.0-only and
  GPL-3.0-or-later have materially different implications for a hosted deployment. An SBOM will happily
  record "GPL" and a reviewer will happily approve it.
- **ResourceSpace defers to a folder** — the compilation-owned licence pattern pass 8 recorded for
  `acoustid/chromaprint`. The effective licence is the *union* of whatever is in that directory, and the
  directory is not readable from an unauthenticated API call. Clone it and read the folder before
  quoting a licence to a client.

Open-source DAM built *specifically for media* is dead: `myabc/mediateca` (2015), `mymam/mymam` (2013),
`jcftang/hydradam` — WGBH's own — (2012). Nothing since.

### ⚠️ Kaltura's GitHub repositories no longer resolve

`kaltura/server` and `kaltura/platform-install-packages` — for a decade the standard citation for "the
open-source video platform" — both return **nothing from `git ls-remote`**. They are gone or no longer
public.

This KB has **never** cited Kaltura (checked: 0 mentions across all eight files), so there is nothing to
correct. It is recorded here so that no future pass, reaching for the obvious open-source video platform
from memory, writes a row that 404s. A decade-old reflex citation is exactly the kind of thing that
survives in a model's memory long after it stops being true on disk.

### Why "no vertical platform" is the sellable finding

A client in this plane already owns FilmTrack or Whip Media and is not replacing it. The opportunity is
**the layer beside it**: validated avails ingest, a window-decision service, and catalogue-composition
compliance reporting. API Evangelist published independent public-API profiles for both
`api-evangelist/filmtrack` (2026-10-30) and `api-evangelist/whip-media-group` (2026-11-01) — 0 stars, no
licence, and not code, but they confirm the thing that matters commercially: **the incumbents expose
public API surfaces**, so integration is a real design and not a hope.

## The development & production-management tier — added 2026-11-26 (pass 17)

The Odoo-equivalent question for this plane is: **is there a production-management platform you can
deploy, then put an agent on top of?** Measured answer: **no.** This is the thinnest vertical tier in the
KB — thinner than the "no open broadcast MAM" gap recorded earlier in this file.

### What exists

| Platform | License | Repo | Stars | Last push | Deployable today? |
|---|---|---|---|---|---|
| Open Shot Designer | **GPL-3.0** | [koosoli/OpenShotDesigner](https://github.com/koosoli/OpenShotDesigner) | 47★ / 9f | 2026-11-16 | Partly. Broadest scope in the tier — lined script, shot list, storyboard, floor plan, scheduling, call sheets, crew/cast, budget, locations, continuity log, all in a browser tab. Single-author, 47 stars: pilot it, do not stake a studio on it. **GPL-3.0 → deploy unmodified and integrate over its boundary** |
| Beat | **GPL-3.0-or-later** | [lmparppei/Beat](https://github.com/lmparppei/Beat) | 368★ / 60f | 2026-11-02 | Yes, as an *authoring* app on macOS only. Mature and maintained, but it is a screenwriting editor, not a production platform |
| Trelby | GPL-2.0 | [trelby/trelby](https://github.com/trelby/trelby) | 354★ / 107f | 2025-10-21 | Yes, cross-platform authoring. Thirteen months without a push |
| CineSched + CineSpend | GPL-3.0-or-later / **MIT** | [ChrisTempel/CineSched](https://github.com/ChrisTempel/CineSched) · [ChrisTempel/CineSpend](https://github.com/ChrisTempel/CineSpend) | 15★ / 8★ | 2026-10-11 / 2026-10-06 | macOS only, and they are two separate apps — scheduling and budgeting do not share a model. CineSpend is **MIT** and is the only permissive budgeting code located anywhere in this plane |
| method-scheduling | **Apache-2.0** | [method-production-suite/method-scheduling](https://github.com/method-production-suite/method-scheduling) | 1★ / 1f | 2026-11-21 | Not yet. But it is **the only Apache-2.0 licence in the tier**, it covers breakdown → stripboard → day-out-of-days → reports, and it declares an open file format. **The one to watch**: a permissive licence on the right scope is worth more here than 47 stars on a GPL one |
| Open Gate | GPL-3.0 | [opengateapp/opengate](https://github.com/opengateapp/opengate) | 1★ / 1f | 2026-11-03 | Not yet. Widest single-project scope on paper (screenplay → breakdown → stripboard → call sheets → storyboards + budget), one star |

### 🚫 What looks like the answer and is not

[waooAI/waoowaoo](https://github.com/waooAI/waoowaoo) — **14,989★ / 3,232f, last push 2026-09-21** —
presents itself as the "industry-first industrial-grade full-pipeline AI film and TV production platform"
and is, by star count, 60× larger than anything else in this plane. **Its LICENSE file is the Elastic
License 2.0** (3,860 B, verified by reading). That is a source-available licence, not open source: ELv2
prohibits providing the software to third parties as a hosted or managed service and prohibits working
around its licence-key functionality. **A studio engagement delivered on top of it is the prohibited use
case.** The GitHub API reports only `NOASSERTION` here, so a metadata scan will not catch it.

This is the third distinct non-open "open" licence the KB has now recorded on a plane's largest artefact
(after Tencent Hunyuan's territorial community licence and the BSL on Directus) and it is the pattern to
check first whenever a plane has exactly one dominant repository.

### Gap: there is no open production-management platform, and the reason is structural

**The incumbents are wholly proprietary and they own the file formats:** Movie Magic Scheduling and
Budgeting, Showbiz, Gorilla, StudioBinder, Yamdu, SetHero, Croogloo; Wrapbook and Cast & Crew on payroll.
A production office's artefacts — the stripboard, the day-out-of-days, the call sheet, the budget
top-sheet — exist as proprietary formats, and the only interchange that is actually open is **Fountain, at
the script end, before any of the production data is created.**

That asymmetry is the whole finding. The open format sits at the *beginning* of the pipeline; every
artefact downstream of the breakdown is proprietary. So integration work in this plane is import-only:
you can read the script, and from there you are writing the model yourself. **Scope accordingly — this is
a build with a permissive front door, not a platform customisation.**

### Honest gap statement

A single Odoo-class candidate would change this tier completely, and none was found. Searched
2026-11-26: `open source film production scheduling breakdown call sheet github`,
`open source film production accounting budgeting payroll software github`, GitHub
`search/repositories` for `stripboard`, `script breakdown agent`, `call sheet agent`,
`production scheduling MCP`, plus the 27-term grep listed in `agents/top.md`. The directory sites
(SourceForge, Slashdot, G2) return only proprietary products for these categories. **If a client needs
production management, the correct answer is that the open base does not exist — say so and price the
build.**

---

## Book & scholarly-publishing platforms — measured 2026-11-26 (pass 18)

Real, running systems a client already operates or could be stood up on, with an agentic layer added
on top — the publishing equivalent of Odoo for ERP or OpenMRS for healthcare. All rows verified
2026-11-26 by reading the licence file and taking the last-commit date from a filtered clone.

**The deployment rule for this whole section, in one line:** every platform here is **GPL-3.0,
AGPL-3.0 or LGPL** — there is no permissive publishing *platform*. Globant's engagement model in
this plane is therefore **deploy, configure and extend as separate services**, not link into
proprietary code. The permissive components are the *conformance and rendering* libraries
(`repos/foundations.md`), which is where proprietary value can sit.

### Scholarly & academic publishing — the most-deployed open platforms on earth

| Platform | Repo | Licence (file) | Last commit | What it runs | Why it matters |
|---|---|---|---|---|---|
| **Open Journal Systems (OJS)** | https://github.com/pkp/ojs | GPL-3.0 (`LICENSE`) | 2026-11-26 | Journal submission → peer review → publication | **25,000+ journals worldwide.** The single largest installed base in this plane. Dominant in LATAM — see the opportunity in `intel/market.md` |
| **Open Monograph Press (OMP)** | https://github.com/pkp/omp | GPL-3.0 (`LICENSE`) | 2026-11-23 | Monographs, edited volumes, scholarly editions | Same PKP stack and workflow model as OJS, applied to books |
| **pkp-lib** | https://github.com/pkp/pkp-lib | GPL-3.0 (`LICENSE`) | 2026-11-23 | Shared framework under OJS/OMP | **Integrate here, not in OJS directly** — the stable seam for plugins across both |
| **PubPub** | https://github.com/pubpub/pubpub | LGPL (`LICENSE`) | 2026-11-24 | Drafting, peer review, journal and book hosting | **LGPL = weak copyleft**, the mildest licence of any platform in this plane. Where a client needs proprietary extension, this is the least constrained starting point |
| **Manifold** | https://github.com/manifoldscholar/manifold | GPL-3.0 (`LICENSE.md`) | 2026-11-19 | Scholarly monograph reading and annotation | University-press reading platform; strong annotation model |
| **Fidus Writer** | https://github.com/fiduswriter/fiduswriter | AGPL-3.0 (`LICENSE`) | 2026-11-12 | Collaborative academic authoring | AGPL — network copyleft applies if hosted for third parties |
| **Thoth** | https://github.com/thoth-pub/thoth | **Apache-2.0** (`LICENSE`) | 2026-11-25 | OA book metadata management, ONIX/MARC export | **The one permissive platform-adjacent system here.** EMEA (COPIM/UK). If metadata is the engagement, start here |

### Trade publishing, books & open textbooks

| Platform | Repo | Licence (file) | Last commit | What it runs |
|---|---|---|---|---|
| **Pressbooks** | https://github.com/pressbooks/pressbooks | GPL-3.0 (`LICENSE.md`) | 2026-11-25 | Book production on WordPress multisite; outputs PDF, EPUB and web from one source. Heavily used for open textbooks in NA higher education |
| **Calibre** | https://github.com/kovidgoyal/calibre | GPL-3.0 (`LICENSE`) | 2026-11-26 | Library management and format conversion; the de facto desktop standard, scriptable headless via `calibredb`/`ebook-convert` |
| **Sigil** | https://github.com/Sigil-Ebook/Sigil | GPL-3.0 (`COPYING.txt`) | 2026-11-25 | WYSIWYG EPUB editor — the tool a human remediator sits in front of |
| **Standard Ebooks tools** | https://github.com/standardebooks/tools | GPL-3.0 + **CC0** for `./se/data/templates` | 2026-11-25 | Production pipeline with a genuinely reusable CC0-dedicated template set |
| **Omeka S** | https://github.com/omeka/Omeka-S | GPL-3.0 (`LICENSE`) | 2026-11-24 | Digital collections and exhibits publishing — the archive-facing option |

### Reading, distribution & catalogue systems

| Platform | Repo | Licence (file) | Last commit | What it runs |
|---|---|---|---|---|
| **Thorium Reader** | https://github.com/edrlab/thorium-reader | **BSD-3-Clause** (`LICENSE`) | 2026-11-26 | Reference desktop reading app (EDRLab, France): EPUB, LCP, audiobooks, **and the accessibility behaviour the EAA expects of a reading system** |
| **Komga** | https://github.com/gotson/komga | **MIT** (`LICENSE`) | 2026-11-24 | Ebook/comic server with OPDS. **The only permissive reading server verified** |
| **Kavita** | https://github.com/Kareadita/Kavita | GPL-3.0 (`LICENSE`) | 2026-11-22 | Self-hosted reading server, broad format support |
| **Calibre-Web** | https://github.com/janeczku/calibre-web | GPL-3.0 (`LICENSE`) | 2026-11-22 | Web front end over an existing Calibre library — the fastest path to a browser-based catalogue |
| **Audiobookshelf** | https://github.com/advplyr/audiobookshelf | GPL-3.0 (`LICENSE`) | 2026-11-19 | Self-hosted audiobook and podcast server — the delivery end of any ebook→audiobook pipeline |
| **Open Library** | https://github.com/internetarchive/openlibrary | AGPL-3.0 (`LICENSE`) | 2026-11-26 | Bibliographic catalogue and work/edition identifiers; usable as an enrichment source |
| **KOReader** | https://github.com/koreader/koreader | AGPL-3.0 (`COPYING`) | 2026-11-25 | E-ink device reading application |

### Which platform to start from, by engagement type

| If the engagement is… | Start from | Licence consequence |
|---|---|---|
| Journal or scholarly workflow, incl. AI editorial policy | **`pkp/pkp-lib`** (plugin seam), deployed as OJS/OMP | GPL-3.0 — deploy and extend via plugins; keep proprietary models behind a service boundary |
| Scholarly platform needing proprietary extension | **PubPub** | LGPL — weak copyleft; the only platform here that tolerates linking |
| Book metadata, ONIX/MARC, catalogue distribution | **Thoth** + `titusz/onixcheck` + `chrisribal/onix-parser` | **Apache-2.0 / Apache-2.0 / MIT — fully permissive path, end to end.** The cleanest commercial route in this plane |
| Open textbook or multi-format book production | **Pressbooks** | GPL-3.0 — WordPress plugin model makes extension conventional |
| EAA backlist remediation at scale | **`w3c/epubcheck` + `daisy/ace` + Sigil for human fix-up** | **BSD-3 + MIT** for the automated layer; GPL-3 only for the desktop editor a human drives |
| Reading app or accessible reading system | **Thorium Reader** / `readium/*` | **BSD-3-Clause** — permissive, embeddable |
| Ebook/audiobook delivery to end users | **Komga** (MIT) or Audiobookshelf (GPL-3) | Komga if the product must stay proprietary |

## The sports & live-event plane — measured 2026-11-26 (pass 19)

**The shape of this layer, and it is worse than the M&E average.** This file already records that
M&E has no permissively-licensed turnkey platform comparable to Odoo. Sports is the extreme case:
there is **no open-source sports-media platform at all** — nothing that manages rights, schedules a
linear sports channel, runs a fan community or reconciles a rights payment. What exists splits into
two unrelated groups: **generic event/ticketing platforms** (healthy, copyleft, not sports-aware)
and **scoreboard overlay utilities** (tiny, permissive, genuinely useful). The middle is empty.

### Group 1 — Event & ticketing platforms (real systems, all copyleft)

| Platform | Repo | License | Stars | Forks | Last push | What it is |
|---|---|---|---|---|---|---|
| Hi.Events | https://github.com/HiEventsDev/Hi.Events | ⚠️ **AGPL-3.0 + §7(b) attribution** (file `LICENCE`, 35,725 B) | 4,201 | 760 | 2026-11-26 | Event management and ticket selling; actively developed. **The §7(b) clause requires you to retain their attribution** — read it before white-labelling |
| Attendize | https://github.com/Attendize/Attendize | `NOASSERTION` — treat as unresolved | 4,278 | 1,233 | 2024-08-20 | Ticket selling + event management (Laravel). **Dormant 2+ years** |
| Dreeve | https://github.com/dreeveapp/dreeve | AGPL-3.0 | 2,224 | 150 | 2026-11-25 | Self-hosted dashboard for sports and fitness data; the most active sports-adjacent platform found |
| Zammad | https://github.com/zammad/zammad | AGPL-3.0 | 6,150 | 1,112 | 2026-11-26 | General helpdesk — relevant because **no sports-specific fan-support system exists** |
| Frappe Helpdesk | https://github.com/frappe/helpdesk | AGPL-3.0 | 3,517 | 1,032 | 2026-11-25 | Same role, same caveat |

**Licence consequence for the studio.** Every usable platform in this group is AGPL-3.0, and
Hi.Events adds an attribution term on top. A client-facing deployment therefore means either
honouring AGPL §13 (publish the modified source of the hosted service) or keeping the platform at
arm's length behind an API boundary, with Globant's proprietary value in a separate service. This is
the same architecture this file recommends for the rest of M&E; sports does not offer an exception.

### Group 2 — Scoreboard & overlay utilities (permissive, tiny, and the honest finding is their size)

| Tool | Repo | License | Stars | Forks | Last push |
|---|---|---|---|---|---|
| sport-streamer | https://github.com/JimThatcher/sport-streamer | **MIT** | 31 | 3 | 2023-06-07 |
| Froggi | https://github.com/obfedder/Froggi | **MIT** | 12 | 1 | 2025-05-14 |
| fly-scoreboard (OBS overlay) | https://github.com/mmlTools/fly-scoreboard | GPL-2.0 | 12 | 10 | 2026-10-26 |

Three real tools, none above 31 stars, two dormant. **Fewer real rows beat padding:** these are the
only open scoreboard/overlay projects located, and their size *is* the finding — the graphics layer
of a live sports broadcast, which every regional broadcaster needs, is served by hobby projects.
The composable alternative is to drive overlays from `roboflow/sports` (MIT) output into a browser
source, which `compose/patterns.md` Pattern 18 sets out.

### Group 3 — Odds & market data (one entry, and it is a wrapper)

| Tool | Repo | License | Stars | Last push | Note |
|---|---|---|---|---|---|
| odds-api | https://github.com/odds-api/odds-api | **Apache-2.0** | 41 | 2026-11-05 | OpenAPI spec, SDKs, MCP server and mocks for a **commercial** odds feed. Permissive client, paid data |
| soccerapi | https://github.com/S1M0N38/soccerapi | MIT | 182 | **2022-12-08** | The most-starred open odds scraper, **dead four years** |

### What does not exist — stated as gaps, not omissions

Searched this pass and **not found at any usable star level**:

- **No open-source sports rights-management or avails system.** Pass 16 built out the avails and
  windowing plane generally; nothing in it is sports-aware, and sports rights are the most
  fragmented in M&E (per-territory, per-competition, per-window, per-platform).
- **No open-source fan-engagement or fan-community platform.** The entire category tops out at
  **28 stars** with no licence (see `agents/top.md`). Clubs and leagues buy this; nobody has built it
  openly.
- **No open-source sports federation / league management system** (fixtures, officials, discipline,
  registrations) comparable to what OpenMRS is for health or Moodle for education.
- **No open-source officiating or VAR tooling.**
- **No sports-specific DAM.** The general M&E options already in this file apply unchanged.
- **Sportradar, Genius Sports and Stats Perform commercial terms are NOT verified** — no public
  pricing, nothing reachable. Treat as *not investigated, not free*.

**Why this matters for an engagement.** In every other plane this KB has mapped, the question is
*which* open platform to extend. In sports it is the opposite: the platform layer is the deliverable.
Globant can build the sports-aware layer — rights, fixtures, fan identity — on a generic AGPL event
platform held at arm's length, with the permissive CV and data stack doing the sport-specific work.

## Newsroom & investigation platforms — measured 2026-11-26 (pass 20)

> Real, running systems a newsroom already operates, that an agentic layer can sit on top of — the
> journalism equivalent of Odoo for ERP. All verified 2026-11-26 (existence, stars, licence file,
> default-branch HEAD).

| Platform | Repo | Stars | Licence | HEAD | What it is, and who runs it |
|---|---|---|---|---|---|
| Superdesk | https://github.com/superdesk/superdesk | 760★ | AGPL-3.0 | 2026-11-26 | Headless newsroom CMS — end-to-end news creation, curation, distribution (Sourcefabric) |
| Ghost | https://github.com/TryGhost/Ghost | 55,920★ | MIT | 2026-11-26 | Publishing + membership/subscription platform; the permissive option at the publishing end |
| Datashare | https://github.com/ICIJ/datashare | 784★ | AGPL-3.0 | 2026-11-26 | Self-hosted document search with OCR and NER; built and run by ICIJ for cross-border investigations |
| Uwazi | https://github.com/huridocs/uwazi | 330★ | MIT | 2026-11-26 | Structured documentation database (HURIDOCS); the permissive platform in this tier |
| DocumentCloud | https://github.com/MuckRock/documentcloud | 54★ | AGPL-3.0 | 2026-11-24 | Document hosting, annotation and embedding for publication (MuckRock) |
| Alaveteli | https://github.com/mysociety/alaveteli | 421★ | AGPL-3.0 | 2026-11-25 | Public FOI request platform; mySociety, deployed across many jurisdictions |
| Froide | https://github.com/okfde/froide | 413★ | MIT | 2026-11-09 | FOI platform of Open Knowledge Foundation Deutschland — **the permissive FOI option** |
| MuckRock | https://github.com/MuckRock/muckrock | 124★ | AGPL-3.0 | 2026-11-24 | US federal/state records requests, with a public request archive |
| Meedan Check | https://github.com/meedan/check | 131★ | MIT | 2026-09-23 | Collaborative media-annotation and tipline platform used by fact-checking orgs |
| SecureDrop | https://github.com/freedomofpress/securedrop | 3,897★ | AGPL-3.0 | 2026-11-24 | The source-intake system a newsroom installs; Freedom of the Press Foundation |

**Read this before quoting Meedan Check.** The 131★ repo `meedan/check` is, by its own description,
the *"development environment for Meedan Check"* — a compose wrapper. The application backend is
**`meedan/check-api` (21★, MIT, pushed 2026-11-24)**. Both are real and both are MIT; the star count
that looks like adoption belongs to the scaffolding. Quote the component you intend to deploy.

**The licence shape of this tier, and why it differs from the rest of the KB.** Nine of the eleven
rows above are the *turnkey platform* layer, and seven of those are copyleft — consistent with the
pattern this file recorded in pass 1 (permissive pipelines, copyleft platforms). What is specific to
journalism is that the copyleft here is **AGPL rather than GPL**, and the deployments are **hosted
services** — so §13 is live, not theoretical. Two consequences for an engagement:

- **Froide (MIT) and Uwazi (MIT) are the two escape hatches in this tier.** If a client needs a
  records-access portal or a documentation database inside a proprietary product, those are the
  starting points, and they are both currently maintained.
- **For the AGPL platforms, the cleanest posture is "we operate it for you, unmodified, and build
  our value beside it"** — agents that call the platform's API, not forks of the platform. That is
  how every pattern in `compose/patterns.md` for this plane is wired.

---

## Spatial & immersive platforms — measured 2026-11-26 (pass 21)

The brief for this file is the Odoo/OpenMRS/Moodle shape: a **real system you can stand up and
customise with AI on top**. For immersive media that system mostly does not exist, and the honest
finding is the custodianship history rather than the feature list.

### Group 1 — Social/immersive-space platforms you can self-host

| Platform | Repo | Stars | Licence (verified) | HEAD | Note |
|---|---|---|---|---|---|
| Hubs (Community Edition) | https://github.com/Hubs-Foundation/hubs | 2,228★ / 1,387f | MPL-2.0 | 2026-10-29 | The closest thing to an "Odoo of immersive" — rooms, avatars, scene upload, WebXR in-browser. **Custodian changed: Mozilla shut the hosted service on 2024-05-31 and the codebase is now maintained by the Hubs Foundation** (Mozilla's own support pages state both) |
| Overte | https://github.com/overte-org/overte | 289★ / 83f | Apache-2.0 (`LICENSE`) | 2026-11-23 | Full 3D social platform with its own server stack. **Governed by Overte e.V., a German association — the only EMEA-domiciled open immersive platform found** |
| Vircadia | https://github.com/vircadia/vircadia-native-core | 543★ / 173f | Apache-2.0 (`LICENSE`) | 2025-07-01 | Overte's predecessor, **17 months without a push** — use Overte instead |

**The lineage is the risk disclosure.** Read the copyright headers in sequence: High Fidelity, Inc.
(2013–2019) → Vircadia contributors / DigiSomni LLC (2019–2022) → Overte e.V. (2022–2026). The same
codebase has been handed down through **two abandonments**, and the category's most-starred entry
(Hubs) survived a third when its corporate sponsor withdrew. Any client proposal that puts a social-VR
platform at the centre of a multi-year engagement has to carry a maintenance plan, because **every
platform in this category has already outlived at least one owner.** The permissive licences (MPL-2.0,
Apache-2.0) are what made each handover legally possible — which is the argument for insisting on them.

### Group 2 — 3D asset management and publishing (the DAM layer for spatial)

| Platform | Repo | Stars | Licence (verified) | HEAD | Note |
|---|---|---|---|---|---|
| Manyfold | https://github.com/manyfold3d/manyfold | 2,264★ / 152f | AGPL-3.0 | 2026-11-26 | Self-hosted 3D asset manager (Rails + three.js); tagging, previews, library organisation. AGPL reaches a hosted offering |
| xeokit SDK | https://github.com/xeokit/xeokit-sdk | 969★ / 335f | AGPL-3.0 | 2026-11-25 | Web viewer SDK for very large models; BIM-focused but format-general. AGPL — dual licensing is sold commercially |
| CesiumJS | https://github.com/CesiumGS/cesium | 15,990★ / 3,906f | Apache-2.0 | 2026-11-26 | Streams massive 3D Tiles datasets; the permissive option when the scene is bigger than memory |
| `<model-viewer>` | https://github.com/google/model-viewer | 8,360★ / 965f | Apache-2.0 | 2026-11-18 | One tag to put a glTF on a page with an AR handoff on both mobile platforms — the lowest-effort production surface in this plane |

### Group 3 — Engines as platforms

| Platform | Repo | Stars | Licence (verified) | HEAD | Note |
|---|---|---|---|---|---|
| Godot | https://github.com/godotengine/godot | 120,865★ / 27,647f | MIT | 2026-11-25 | The only large engine under MIT; with `GodotVR/godot-xr-tools` (MIT, 749★) the entire XR chain is permissive end to end |
| O3DE | https://github.com/o3de/o3de | 9,929★ / 2,601f | **Apache-2.0 OR MIT, licensee elects** | 2026-11-26 | Linux Foundation governance; the cleanest licence terms of any engine here |
| PlayCanvas | https://github.com/playcanvas/engine | 17,382★ / 2,075f | MIT | 2026-11-26 | Web-first; same house as SuperSplat, so the splat path is native |
| Babylon.js | https://github.com/BabylonJS/Babylon.js | 26,457★ / 3,748f | Apache-2.0 | 2026-11-26 | Strongest out-of-the-box WebXR feature coverage |

### What does not exist — stated as gaps, not omissions

- **There is no open-source volumetric-video *platform*.** Ingest, process, store, version, transcode
  and deliver a volumetric asset: no single system does this. `ASU-NEM-Labs/open4dgs-core` (MIT,
  161★) is the only permissive production 4D pipeline found, and it is a pipeline, not a platform.
  This is a build opportunity, not an integration.
- **No open media-asset-management system handles spatial assets as first-class.** Manyfold is built
  for 3D-print libraries; the broadcast MAM layer catalogued in earlier passes has no notion of a
  splat, a point cloud or a USD stage.
- **No open-source Apple Immersive Video / MV-HEVC production chain.** Verified absent this pass; the
  only live broadcast encoder announced in 2026 is proprietary (SpatialGen, AWE USA).
- **Monado** — the leading open OpenXR runtime, and the piece that would make a self-hosted headset
  stack complete — **could not be verified from this session**: `gitlab.freedesktop.org` was refused
  by the egress proxy (HTTP 403). Recorded as not investigated. Treat as "exists, terms unconfirmed
  here", not as absent.
- **`opensimulator/opensim` is not on GitHub** (`git ls-remote` negative). OpenSimulator is hosted
  elsewhere and was not verified this pass.

## Podcast & spoken-audio platforms — measured 2026-11-26 (pass 22)

Real, customizable systems for publishing, hosting, serving and measuring podcasts. The pattern that
governs this file's earlier rows holds here too, and harder: **every platform that owns the listener
relationship is copyleft, and the one permissive publishing platform is the smallest of them.**

| Platform | Repo / home | License | Stars | What it is | AI layer Globant can add |
|---|---|---|---|---|---|
| **Podlove Publisher** | [podlove/podlove-publisher](https://github.com/podlove/podlove-publisher) | **MIT** | 310 | WordPress-based podcast publishing: episode management, standards-compliant feed generation, chapters, contributors. **The only MIT publishing platform in this plane** — and therefore the default base for a client-owned, white-labelled podcast CMS. | Auto chapters + show notes + transcript (`sofit`, `autoclip`), episode SEO, feed validation against `podcast-namespace`. |
| **Audiobookshelf** | [advplyr/audiobookshelf](https://github.com/advplyr/audiobookshelf) | **GPL-3.0** | 15,123 | Self-hosted audiobook and podcast server with its own clients. The plane's biggest project and the practical choice for an internal/enterprise spoken-audio library. | Semantic search over transcripts, per-title summarisation. Deploy unmodified and integrate over its API; **do not link client code in**. |
| **Castopod** | `code.castopod.org` (**not GitHub**) | **AGPL-3.0** | not measured | Purpose-built open podcast *hosting* platform (PHP/CodeIgniter 4) with ActivityPub federation, built-in analytics, RSS generation; project docs give **1.15.0, Feb 2026**. | Fediverse-native distribution + auto-transcripts. **Network copyleft: unsuitable as the base of a hosted multi-tenant product.** Host blocked by this session's proxy — terms from project docs, figures not asserted. |
| **microfeed** | [microfeed/microfeed](https://github.com/microfeed/microfeed) | **AGPL-3.0** | 4,143 | Lightweight CMS on Cloudflare for podcasts, blogs and media; self-hosted, "agentic". | Same AGPL constraint as Castopod, with the same consequence for SaaS. Viable for a client hosting their *own* single tenant. |
| **PinePods** | [madeofpendletonwool/PinePods](https://github.com/madeofpendletonwool/PinePods) | **GPL-3.0** | 1,089 | Rust, self-hosted podcast management + playback for a household or team, with sync. | Internal "listening library" for a research or comms team; recommendation over the team's own feed set. |
| **Podverse** | [podverse/podverse-rn](https://github.com/podverse/podverse-rn) | **AGPL-3.0** | 287 | The most complete open **Podcasting 2.0** stack: app (`-rn`), web (`-web`, 100★), API (`-api`, 34★), ops (`-ops`, 17★) — all AGPL-3.0. Chapters, transcripts, cross-app playlists, v4v. | The reference to *read* when implementing namespace features. Not a fork candidate: AGPL across all five repos. |
| **AntennaPod** | [AntennaPod/AntennaPod](https://github.com/AntennaPod/AntennaPod) | **GPL-3.0** | 8,357 | The reference open Android podcast client, actively developed. | Nothing shippable: a white-label fork inherits GPL-3.0, which kills most OEM and app-store arrangements. Listed so that it is **ruled out on purpose**, not by omission. |
| **Anytime Podcast Player** | [amugofjava/anytime_podcast_player](https://github.com/amugofjava/anytime_podcast_player) | **BSD-3-Clause** | 627 | Flutter/Dart podcast player, cross-platform. | **The only clean white-label client base in the plane.** Smaller and slower-moving than the GPL options — that trade-off is the conversation to have with the client, and it is a short one, because the alternative is disclosing their source. |
| **OP3** | [skymethod/op3](https://github.com/skymethod/op3) | **MIT** | 144 | The Open Podcast Prefix Project: a self-hostable analytics prefix that counts downloads transparently. | The base for an auditable, GDPR-reviewable measurement service — see `intel/market.md` EMEA and Pattern 48. |
| **Funkwhale** | `dev.funkwhale.audio` (**not GitHub**) | **AGPL-3.0** | not measured | Federated audio hosting (music + podcasts), ActivityPub. Already carried in this file's main table. | Host blocked by this session's proxy; no figures asserted this pass. |

### The licence law of this file, tested again and confirmed

This file's earlier passes established that **self-hostable media platforms are copyleft by default**
(PeerTube AGPL, MediaCMS AGPL, Owncast, Funkwhale AGPL, Castopod AGPL, Janus GPL, OpenMontage AGPL).
Pass 22 tested it against a plane the file had never measured and it held — with a refinement worth
recording:

> The copyleft is not a property of "self-hostable". It is a property of **owning the audience
> relationship**. In the podcast plane the *spec* is CC0, the *analytics prefix* is MIT, the
> *publishing plugin* is MIT — and every single artefact that sits between a listener and a show is
> GPL or AGPL, with the only permissive large exception (`GetStream/Winds`, BSD-3, 9,078★) dead
> since **2021-10-11**.

**Consequence for a proposal.** There is a permissive path through this plane, but it is narrow and
it has to be chosen deliberately: **Podlove Publisher (MIT) to publish, OP3 (MIT) to measure, the
namespace (CC0) to describe, Anytime (BSD-3) if a client-branded app is required.** Any other
combination of this plane's platforms puts GPL or AGPL into the client's delivery, and in the hosted
case the AGPL ones put it into their service.

### What does not exist as a platform at all

There is **no open-source podcast ad server, dynamic-ad-insertion service, or ad-measurement
platform** — not a weak one, not an abandoned one, none (`audio ad insertion server stars:>=20`
→ 0 results, measured 2026-11-26). Every commercial system in that slot is proprietary
(Megaphone, Acast, Triton, ART19, Spreaker). For a client who needs it, that is not an integration;
it is a build, and the inputs for it are all permissive. Pattern 47.

## Pass 23 (2026-11-26) — still-image platforms: photo libraries, image servers, IIIF and page layout

Real, running systems for the still-image and print plane — the ones a client may already have, or
should start from. All licences read from the actual LICENSE file; stars and last-push from
`search/repositories`. `n/a` = exists and serves git, invisible to the search index.

### The licence shape of this layer — read before choosing

**The photo-library layer is almost entirely AGPL-3.0, and that is the single most important
commercial fact in this plane.** Of the seven self-hostable photo platforms below, five are
AGPL-3.0, one is GPL-2.0, and **exactly one is permissive.** AGPL means that if the client's
deployment is reachable by users over a network, the source — including modifications — must be
offered to those users. For a media client who wants to *own* a differentiated picture archive,
that is usually disqualifying, and it is almost never noticed at the pilot stage.

| Platform | Repo | License | Stars | Last push | What it is, and the catch |
|---|---|---|---|---|---|
| **LibrePhotos** | [LibrePhotos/librephotos](https://github.com/LibrePhotos/librephotos) | **MIT** | 8,187 | 2026-11-26 | **The only permissive self-hosted photo library in this plane.** Albums, faces, semantic search, timeline, map view. If the engagement needs a photo archive the client owns outright and can extend as a closed product, this is the start point — there is no second option. |
| Immich | [immich-app/immich](https://github.com/immich-app/immich) | AGPL-3.0 | 120,170 | 2026-11-26 | The most popular self-hosted photo platform by a wide margin, and the best AI story: **CLIP-based natural-language smart search** plus face recognition, with native iOS/Android background backup. Pushed daily. **AGPL** — deploy it, extend it internally, but a hosted product built on it is disclosable. Memory requirements are the practical constraint on small servers. |
| PhotoPrism | [photoprism/photoprism](https://github.com/photoprism/photoprism) | AGPL-3.0 | 40,481 | 2026-11-26 | The photographer-grade option: **strong RAW handling and disk-based archives**, on-device models via ONNX Runtime, AI tagging and scene search. API reports `NOASSERTION`; LICENSE (33,824 B) read — AGPL-3.0. Sources disagree on how open-ended its semantic search is versus Immich's; verify against its own docs for a search-led brief. |
| Pixelfed | [pixelfed/pixelfed](https://github.com/pixelfed/pixelfed) | AGPL-3.0 | 7,155 | 2026-11-25 | Federated (ActivityPub) image-sharing platform — the base for a publisher-owned, non-Instagram visual community. AGPL. |
| Piwigo | [Piwigo/Piwigo](https://github.com/Piwigo/Piwigo) | GPL-2.0 | 3,891 | 2026-11-22 | Long-lived PHP photo library / light DAM with a real plugin ecosystem. API reports `NOASSERTION`; `LICENSE.txt` (18,092 B) read — **GPL-2.0, not LGPL.** GPL-2.0 without the network clause, so a hosted deployment does not trigger disclosure the way AGPL does. |
| Ente | [ente-io/ente](https://github.com/ente-io/ente) | AGPL-3.0 | n/a | — | End-to-end-encrypted photo storage. The one to look at when confidentiality of unpublished images is the requirement. Invisible to the search index; exists and serves git. |
| Nextcloud Photos | [nextcloud/photos](https://github.com/nextcloud/photos) | AGPL-3.0 | 725 | 2026-11-24 | The photo app for an existing Nextcloud estate. Relevant mainly when the client already runs Nextcloud — then it is a configuration, not a project. |

### Editorial / enterprise DAM — thin, and one licence trap

| Platform | Repo | License | Stars | Last push | Note |
|---|---|---|---|---|---|
| Phraseanet | [alchemy-fr/Phraseanet](https://github.com/alchemy-fr/Phraseanet) | GPL-3.0 | 276 | 2026-11-25 | A genuine media-company DAM — ingest, IPTC/XMP metadata editing, controlled vocabularies, publication. API reports `NOASSERTION`; LICENSE (35,414 B) read — GPL-3.0. Actively pushed, and at 276 stars it is the most credible open editorial DAM found. |
| Pimcore | [pimcore/pimcore](https://github.com/pimcore/pimcore) | **POCL — source-available, NOT open source** | 3,891 | 2026-11-26 | **Licence trap, and widely mis-stated.** Pimcore (DAM + PIM + CMS) is listed as "open source" in most 2026 DAM roundups. Its `LICENSE.md` on the default branch is the **Pimcore Open Core License (POCL)**, last updated June 2025 — a negotiated agreement between Pimcore GmbH and the licensee, not an OSI licence. The GitHub API reports `NOASSERTION`, and **its default branch is `2026.x`**, so a probe of `master`/`main` returns 404 and looks like a missing file. **Do not put Pimcore in a proposal as open source without legal review.** |

**Informed gap — ResourceSpace.** Named in several 2026 roundups as a leading fully open-source DAM
(and the one most often recommended for media libraries). **It could not be verified in this pass:**
`montala/ResourceSpace` and `montala/resourcespace` both return no refs from `git ls-remote`, and
`resourcespace.com` was not reachable from this environment. Its source is distributed from the
vendor's own infrastructure rather than GitHub. **No row is written for it and no URL is asserted** —
if a client raises it, verify the licence and source channel directly with Montala first.

### IIIF — the standards-based way to serve an image archive, and it is permissive

This is the quiet good news of the layer. The archive-image delivery stack is **MIT, BSD and
Apache-2.0 end to end** — the opposite of the photo-library layer above. IIIF is already in this KB
from the preservation and journalism passes; the serving and viewing components enter here.

| Component | Repo | License | Stars | Last push | Role |
|---|---|---|---|---|---|
| OpenSeadragon | [openseadragon/openseadragon](https://github.com/openseadragon/openseadragon) | BSD-3-Clause | 3,543 | 2026-11-20 | Deep-zoom viewer for very large images — scanned pages, maps, high-resolution art. The front end of any archive-image product. |
| Mirador | [ProjectMirador/mirador](https://github.com/ProjectMirador/mirador) | Apache-2.0 | 626 | 2026-11-25 | Multi-window IIIF workspace: compare several images or manuscript openings side by side, with annotation. |
| Cantaloupe | [cantaloupe-project/cantaloupe](https://github.com/cantaloupe-project/cantaloupe) | **MIT** | 308 | 2026-11-23 | IIIF Image API server — dynamic tiling, cropping and scaling of archive masters on the fly. API reports `NOASSERTION`; `LICENSE.txt` (1,870 B) read — MIT. **A permissive, standards-compliant image server at 308 stars.** |

**A permissive archive-image delivery stack exists, is standards-based, and has almost no
constituency.** Cantaloupe (MIT, 308★) plus OpenSeadragon (BSD-3) plus Mirador (Apache-2.0) is a
complete, ownable IIIF product that a cultural-heritage, publishing or broadcast-archive client can
deploy and extend without any disclosure obligation — the direct contrast with Immich's 120,170
stars under AGPL.

### Page layout, prepress and the desktop darkroom

These are applications, not services — the systems a design desk or print operation already runs.
**All of them are copyleft**, which is fine for deployment on staff machines and fatal for a
productised fork.

| Platform | Repo | License | Stars | Last push | Role |
|---|---|---|---|---|---|
| Krita | [KDE/krita](https://github.com/KDE/krita) | GPL-3.0 | 10,812 | 2026-11-26 | Professional digital painting and illustration — the production tool for original editorial artwork. |
| GIMP | [GNOME/gimp](https://github.com/GNOME/gimp) | GPL (**with an explicit plug-in exemption**) | 6,627 | 2026-11-26 | Raster retouching. **The exemption is the commercially useful part:** its LICENSE states that arbitrarily-licensed programs such as GIMP plug-ins do not automatically assume the GPL merely by invoking (or being invoked by) GIMP procedures. **A proprietary GIMP plug-in is explicitly contemplated** — so "automate the retouching desk with a closed plug-in" is a legitimate engagement shape. |
| Scribus | [scribusproject/scribus](https://github.com/scribusproject/scribus) | GPL-2.0-or-later | 659 | 2026-11-26 | **The only open professional page-layout application** — the InDesign substitute. Exports PDF/X-1a, PDF/X-3 and PDF/X-4 with an embedded ICC profile defining the intended press condition. Requires Ghostscript for EPS/PS import and print preview (a documented beginner stumbling block). Reported stable **1.6.6** and preview **1.7.3**, both 2026-04-13; 1.6.6 added MSVC 2026 project files. |
| darktable | [darktable-org/darktable](https://github.com/darktable-org/darktable) | GPL-3.0 | 13,508 | 2026-11-26 | The RAW darkroom, now with an opt-in AI subsystem (5.6, June 2026). See `repos/trending.md` pass 23. |
| RawTherapee | [Beep6581/RawTherapee](https://github.com/Beep6581/RawTherapee) | GPL-3.0 | n/a | — | The other major open RAW developer. **Default branch `dev`**; invisible to the search index. |
| CUPS | [OpenPrinting/cups](https://github.com/OpenPrinting/cups) | Apache-2.0 | 1,803 | 2026-11-25 | The printing system — queues, IPP, drivers. **The one permissive component in the physical-output path.** |

### How to choose, in one paragraph per engagement shape

- **"We need a picture archive we own and can sell."** `LibrePhotos` (MIT) or build on
  `Cantaloupe` + `OpenSeadragon` + `open_clip`. Do not start from Immich or PhotoPrism, however much
  better they look in a demo — AGPL will surface in the first legal review.
- **"We need the best internal photo tool, fastest."** Immich (AGPL-3.0), and say plainly in the
  proposal that it is an internal deployment, not a product base. Its CLIP search and mobile backup
  are genuinely ahead of everything permissive.
- **"We have a print operation."** Scribus + Ghostscript + Little-CMS, and treat the **Ghostscript
  AGPL question as a first-week decision**, not a detail: it is a 310-star AGPL project that Scribus
  depends on to turn a page into ink, with a commercial licence sold alongside.
- **"We already run Pimcore and were told it is open source."** Stop and read `LICENSE.md` on the
  `2026.x` branch. It is the POCL.

## The owned-channel & audience-relationship tier — added 2026-11-26 (pass 24)

Real, customisable platforms for the channel a publisher **owns**: the newsletter, the push
subscription, the on-site community, and the consent and profile store underneath them. This tier
entered the KB because the vocabulary probe found the string **`email` zero times in 20,389 lines** —
the KB had the audience-*measurement* platforms (pass 7) and none of the audience-*relationship* ones.

All rows verified 2026-11-26 (GitHub API; licence files read where the API reported nothing).

| Platform | Repo | License | Stars | Last push | What it is, and what to customise |
|---|---|---|---|---|---|
| **Ghost** | [TryGhost/Ghost](https://github.com/TryGhost/Ghost) | **MIT** | 55,925 | 2026-11-26 | Publishing + memberships + subscriptions + newsletters in **one MIT codebase**. The shortest path from "we have articles" to "we have a paying, reachable audience". Customise: the members/tiers model, the newsletter template, webhooks into the client's CDP. |
| **Discourse** | [discourse/discourse](https://github.com/discourse/discourse) | GPL-2.0 | 48,117 | 2026-11-26 | The general-purpose community platform. Plugin API is excellent; copyleft, so run it as a service with SSO rather than forking it. |
| **Novu** | [novuhq/novu](https://github.com/novuhq/novu) | **MIT** (file read) | 40,432 | 2026-11-26 | Not a channel — the **orchestration layer over all of them**: one API for email/SMS/push/in-app, subscriber preference centre, digest batching. The piece that keeps "breaking news" from arriving three times on three channels. |
| **listmonk** | [knadh/listmonk](https://github.com/knadh/listmonk) | **AGPL-3.0** | 24,473 | 2026-11-26 | The default self-hosted newsletter manager: templates, segments by subscriber attribute, bounce processing. **AGPL — operate it, do not fork it into client code.** |
| **NodeBB** | [NodeBB/NodeBB](https://github.com/NodeBB/NodeBB) | GPL-3.0 | 15,254 | 2026-11-26 | Real-time forum. Lighter than Discourse, same copyleft posture. |
| **Mautic** | [mautic/mautic](https://github.com/mautic/mautic) | **GPL-3.0-or-later** (file read) | 11,123 | 2026-11-26 | The only platform here with real **campaign logic** — segments, drip, scoring, landing pages. Heavy (PHP), copyleft, and the right answer when the client's ask is lifecycle marketing rather than a newsletter. |
| **Postal** | [postalserver/postal](https://github.com/postalserver/postal) | **MIT** | 16,982 | 2026-11-20 | A complete mail-delivery platform the client **owns**: queues, per-domain DKIM, bounce/click webhooks, message tracing. The MIT answer to "we don't want to depend on SES/SendGrid". |
| **Mailu** | [Mailu/Mailu](https://github.com/Mailu/Mailu) | **MIT** (file read) | 7,642 | 2026-11-25 | Mail server as Docker images — the simplest self-hosted SMTP estate to stand up. |
| **Coral** | [coralproject/talk](https://github.com/coralproject/talk) | **Apache-2.0** (file read, © 2025 Vox Media) | **2,005** | 2026-11-26 | **The only commenting platform on earth built for newsrooms** — per-stream pre/post moderation, moderation queues, banned and suspect word lists, Slack integration, AI-assisted moderation, **publisher owns the audience data**, ad-free. Born Mozilla + Washington Post; maintained by Vox Media. **Apache-2.0 and pushed today: the best licence/fitness combination in this tier.** |
| **Keila** | [pentacent/keila](https://github.com/pentacent/keila) | **AGPL-3.0** | 2,269 | 2026-11-24 | Newsletter tool **built and hosted in the EU**. Name this first when an EMEA client's blocker is data residency. |
| **SendPortal** | [mettle/sendportal](https://github.com/mettle/sendportal) | **MIT** | 2,193 | 2026-10-22 | **The only permissively-licensed newsletter manager in the open set** — and it has 9% of listmonk's stars. The licence/adoption trade-off in this tier, in one row. |
| **Apache Unomi** | [apache/unomi](https://github.com/apache/unomi) | **Apache-2.0** | **382** | 2026-11-26 | **The only genuinely Apache-licensed customer data platform that exists.** ASF-governed profile and segment store, consent-aware by design. The permissive profile store under everything above. |
| **c15t** | [c15t/c15t](https://github.com/c15t/c15t) | **Apache-2.0** | 2,045 | 2026-11-26 | Headless consent manager with an optional `@c15t/iab` TC-string add-on. The consent UI a publisher can actually own. |

### ⚠️ This tier obeys this file's licence law — and supplies its cleanest proof

The law recorded across passes 4–8: **the pipeline and standards layer is permissive, the turnkey
platform layer is copyleft.** Here it holds, with a twist worth selling:

- **Transport and orchestration are permissive**: Postal (MIT), Mailu (MIT), Novu (MIT), react-email
  and MJML (MIT), Unomi and c15t (Apache-2.0).
- **List management — the turnkey platform — is copyleft**: listmonk (AGPL), Mautic (GPLv3+), Mailtrain
  (GPLv3), Keila (AGPL). The single MIT exception, SendPortal, has **9%** of the leader's adoption.
- **The two exceptions both have a funder.** Ghost (MIT, 55,925★) and Coral (Apache-2.0, 2,005★) are
  permissive *turnkey platforms* — and both exist because an organisation with a publishing business
  paid for them (Ghost Foundation; Mozilla + the Washington Post, now Vox Media). **Permissive
  platform software in media appears where a publisher funded it, not where a community formed.**

**Practical posture:** put the copyleft list manager behind a service boundary the client's
proprietary code calls over HTTP; keep the permissive layers (Postal, Novu, Unomi, Coral, c15t) in the
client's own build, where the differentiation is.

### Gap: there is no open publisher CRM, and the reason is the same as the royalty gap

Searched 2026-11-26 for a media/publisher-specific CRM or ERP under a permissive licence. **Nothing
exists.** The closest results are general-purpose: Dolibarr (Apache-2.0, general ERP), Open Mercato
(MIT, general), Flectra (GPLv3), Ever Gauzy (AGPLv3), and a "Cream CRM" aimed at media agencies whose
licence could not be established. Mautic is marketing automation, not a subscriber CRM.

This mirrors pass 5's finding that there is **no open rights-management or royalty platform**: the
systems that touch the **recurring charge and the subscriber record** are the ones nobody
open-sources, because they carry the money and the liability. A publisher subscriber CRM is a
build-on-Unomi engagement, not an adopt-a-platform one.

### Gap: no IAB-registered open-source CMP, and this one has a date attached

A publisher integrating the IAB TCF needs a **registered** CMP. None of the open options are
registered. `c15t` (Apache-2.0) and `iabtcf-es` (Apache-2.0, 156★) produce a valid TC string and a
consent UI; they do not produce standing in the framework. Against **TCF v2.3 mandatory since 1 March
2026** and **v2.4's website deadline of 23 October 2026**, this is the gap most likely to be
discovered late in an EMEA engagement. State it in week one.

### How to add the AI layer to this tier

The agent layer here is a measured near-zero (`agents/top.md` pass 24: best repo 915★ and dead 16
months), so **the AI work in this tier is an integration, not an adoption**:

1. **Coral + [unitaryai/detoxify](https://github.com/unitaryai/detoxify)** (Apache-2.0, 1,320★) — an
   open moderation assistant over the newsroom comment queue. Both Apache-2.0; **nothing currently
   wires them together.** Smallest unbuilt component in the plane.
2. **Unomi + the recommender stack** in `repos/foundations.md` — segments as features, consent state
   as a hard filter on activation.
3. **listmonk/SendPortal + an LLM editorial step** — generate the digest *draft* from the day's CMS
   output; never the send decision. See `compose/patterns.md` Pattern 24.1.
4. **parsedmarc + an ops agent** — the deliverability triage loop nobody has built (Pattern 24.3).

---

## The traffic, sales-order-to-air & billing tier — added 2026-11-26 (pass 25)

Real running systems for the commercial administration of linear and FAST inventory, and an honest
statement of where the tier stops. All rows verified 2026-11-26 (existence, canonical slug, stars,
forks, last push; licence files read where the API returned `NONE`/`NOASSERTION`).

### ⚠️ Correction to this file

Line ~94 of this file records `immstudios/nebula` as **ARCHIVED** and dead. The project is alive at a
new org: **[nebulabroadcast/nebula](https://github.com/nebulabroadcast/nebula)**, GPL-3.0, **332★**,
38 forks, pushed **2026-11-23**, in 24/7 broadcast use since 2012. The old entry is left in place
(this file's history is not rewritten); treat the row below as the current one.

| Component | Repo | License | Stars | Last push | Role |
|---|---|---|---|---|---|
| **Nebula** (the anchor) | [nebulabroadcast/nebula](https://github.com/nebulabroadcast/nebula) | **GPL-3.0** | 332 | 2026-11-23 | **The platform to start from in this plane.** Broadcast automation + MAM for TV, radio and VOD: linear planning, scheduling, playout and asset management in one system. Python + React; worker and (deprecated) desktop client in sibling repos. GPL-3.0 ⇒ deploy unmodified behind a service boundary and integrate over its API. |
| AzuraCast | [AzuraCast/AzuraCast](https://github.com/AzuraCast/AzuraCast) | **AGPL-3.0** | **4,118** | 2026-11-25 | **New to this KB.** Self-hosted web radio management suite, turnkey installers for the full stack — the most widely adopted broadcast-operations platform in the plane. Station, playlist and scheduling operations; **no rate cards, no invoicing.** AGPL ⇒ unmodified, integrate over HTTP. |
| Rivendell | [ElvishArtisan/rivendell](https://github.com/ElvishArtisan/rivendell) | **GPL-2.0** (read from `COPYING`, 17,992 B; API says `NONE`) | 250 | 2026-08-26 | Professional radio automation. **Read its README before proposing anything in this plane:** it imports schedules from *third-party traffic and music scheduling systems* — the reference open platform assumes the traffic system is **somebody else's proprietary product.** |
| LibreTime | [libretime/libretime](https://github.com/libretime/libretime) | AGPL-3.0 | 941 | 2026-11-22 | Already catalogued above (pass 5). Radio automation/scheduling, maintained Airtime fork. |
| 9eye | [9eye9/9eye](https://github.com/9eye9/9eye) | **AGPL-3.0** | 2 | 2026-11-26 | The **only** open system that models traffic as such: layouts → scheduling → frame-accurate playlists → **clients, deals, campaigns and spot booking** → playout XML export, with an MCP server and agents under a per-action approval table. **Seven days old; as-run, BXF and billing are roadmap.** Evaluate for its design; do not propose as a client core yet. |
| BEAMS | [efeone/beams](https://github.com/efeone/beams) | **MIT** (lowercase `license.txt`, 1,069 B) | 21 | 2026-04-30 | **Not what the name suggests, and the row that would have become wrong data.** A Frappe/ERPNext app whose README is four lines; characterised by reading its doctypes: `job_portal`, `roster`, `manpower_transaction_log`, `substitute_booking`, **`stringer_bill`**, `courier_log`, `vehicle_log_detail`, `fuel_card_log`, `key_log`, `visitor_log`, `security_patrol_log`, plus ERPNext's inherited `sales_order`/`sales_invoice`. So: a broadcaster **back-office** system — HR, rostering, fleet, security, and settling with freelance correspondents. **Not traffic, not ad sales.** Still notable as the only MIT-licensed broadcast-specific business app in 25 passes, and `stringer_bill` models an object no other repo here does. |
| adam-RMS | [adam-rms/adam-rms](https://github.com/adam-rms/adam-rms) | **AGPL-3.0** | 64 | 2026-11-17 | Rental/asset management for theatre, AV and broadcast: crew and kit booking. **Books the kit, not the airtime** — adjacent to this plane. Fork:star ratio 0.73 means people actually deploy it. |
| Kill Bill | [killbill/killbill](https://github.com/killbill/killbill) | **Apache-2.0** | **5,870** | 2026-11-26 | The billing platform this plane has to borrow, because no broadcast-specific open one exists. Invoices reconciled spots; carries makegood obligations as credits. Permissive ⇒ the client owns the integration. |
| Aureus ERP | [aureuserp/aureuserp](https://github.com/aureuserp/aureuserp) | **MIT** | **12,301** | 2026-11-24 | **New to this KB.** Laravel ERP with invoicing/accounting — the permissive accounting back end when the client will not adopt a Java billing platform. |

### Where this tier stops — state this before a proposal, not during it

There is **no open-source broadcast traffic-and-billing system.** The tier above covers *what airs*
(Nebula, AzuraCast, Rivendell, LibreTime) and, in one seven-day-old repo, *what was booked* (9eye).
Nothing covers **proving it aired and collecting for it**:

- `broadcast as-run reconciliation` → **0 GitHub results**; `spot booking advertising` → **0**.
- 9eye's own roadmap lists *as-run and reconciliation*, *BXF export* and *sales and billing* as **not
  built**.
- The only as-run repo that exists is unlicensed, undocumented and dead since **2016**.
- `makegood`, `pre-empt`, `affidavit`, `post-log` → **0 hits** anywhere in this KB or inside 9eye.

**Never promise a broadcaster an "all open source" order-to-cash stack.** The defensible proposal is
the one a third-party build-vs-buy analysis independently reaches (see `intel/market.md` pass 25):
**keep the incumbent traffic core (WideOrbit, Marketron, Imagine LandmarkOSI) and build the
cross-platform order and reconciliation layer around it** — which is permissively licensable,
client-owned, and the subject of Patterns 25.1 and 25.2.

---

## Carbon & sustainability platforms for screen production — added 2026-11-26 (pass 26)

**This section has an unusual shape, and the shape is the finding.** Every other plane in this KB offers
at least one startable open platform — PeerTube, Owncast, Strapi, OpenMRS-equivalents. Here there is
**none**. Every system a media client actually uses to discharge its carbon obligation is a **closed web
tool run by a private body or a public agency**, and `film production carbon footprint` returns **zero**
GitHub repositories. So this section catalogues the incumbents you must **integrate with and feed**,
rather than platforms you can fork — and that reframing is the sellable work (Pattern 26.3).

### The tools that carry the mandate

| Platform | Owner / region | Access | Status | What it is |
|---|---|---|---|---|
| **BAFTA albert** toolkit + certification | BAFTA (UK, used internationally) | Closed web tool; free to productions | **The enforced standard.** BBC makes certification mandatory for all new commissions and recommissions of TV broadcast content; ITV requires certification plus the on-screen end-board logo as a delivery item; Channel 4 requires productions to use albert tools to measure and report | Carbon calculator plus a certification process awarding stars. **Not a legal obligation — a commissioning condition**, which is why it binds harder than most statutes in this KB |
| **albert Next Generation Toolkit** | BAFTA | Closed | **In transition, and this is a dated trigger.** albert's own figures put the closure of the current toolkit at **16 December 2026**; one industry guide says 17 December (**conflict recorded, not resolved** — confirm against albert directly before planning). The BBC stated a new version with a redesigned carbon calculator would launch 16 September 2026 | A rebuilt calculator replacing the current one. **Any integration built against the current toolkit has a known expiry date** |
| **MEDIA Carbon Calculator** | European Commission / Creative Europe MEDIA (EMEA) | **Free**, sign-in via **EU Login** | Launched **13 February 2026** at the European Film Market, Berlinale | The first EU-backed single tool for calculating the footprint of live-action projects. Follows the **GHG Protocol**, covering **Scope 2 and Scope 3** including transport, waste, business travel and purchased goods. Explicitly does **not** replace national calculators. Presented by Florian Reimann of **Yamdu** — a production-management vendor already listed in this file, which is the integration path |
| **Carbon'Clap** + Ecoprod label | EcoProd collective (France, founded 2009) | Free / membership | Established national standard | The French film and TV carbon calculator, with a shared label reference framework |
| **Green Film** | Trentino Film Commission (Italy) | Tool + certification | Active; present at the EFM, 12–18 February 2026 | A sustainability rating tool, a certifying label and a partner network. The Italian counterpart to albert, and the one with the strongest festival-market presence |
| **Green Production Guide / PEAR** calculator | **Sustainable Entertainment Alliance** (major studios; US + Canada) | **Free** for US productions | The de facto North American toolkit | Studio-backed toolkit and carbon calculator. ⚠️ **Naming correction for this KB:** the body is the *Sustainable Entertainment Alliance*; "Sustainable Production Alliance" is the former name and still circulates widely |
| **DIMPACT** | Carnstone + University of Bristol, with media members (Global) | **Membership** | The reference tool for streaming-side reporting | Models energy and emissions across data centres, networks and user devices for digital media services. The Carbon Trust work built on DIMPACT produced the sector's most-quoted figure: **~55 gCO2e per hour** of video streaming in Europe. DIMPACT's own representatives concede that consistent measurement across media supply chains remains unsolved |
| **Greening of Streaming** — REM platform, **OWL**, **LESS Accord** | Industry body (Global) | Membership | Active; **OWL** presented as a live measurement bench for streaming **and AI workloads** | Takes a hardware-measurement approach — smart-meter-based real-world energy measurement at scale — against DIMPACT's modelling approach. The **LESS Accord** is the cross-industry effort to standardise how the sector measures at all |
| **Accedo Ecoflow / Ecoflow X** | Accedo (Global) | Commercial | Active | Streaming-application energy efficiency tooling, named alongside LESS Accord and DIMPACT in the 2026 standardisation effort |
| **Sustainable Screens Australia** | Industry body (APAC) | Free tools + training | Active | **Partnered with BAFTA albert and localised its carbon calculator for Australia**; launched the country's first Sustainability Supervisor training programme in 2025, backed by Netflix and Screen Australia. The clearest instance in APAC of albert's methodology travelling |
| **Globo — Guia de Produções Verdes** | Grupo Globo (LATAM) | Internal | In force since 2023 | Broadcaster-wide green production guide: fleet electrification, replacing generators on live programmes. The largest single LATAM adopter and it is self-authored, not certified |
| **Set Neutro** (Eccaplan) · **Set Sustentável** · **A.L.I.C.E.** (Publicis Production) | Private vendors (LATAM, Brazil) | Commercial | Active | Offsetting seals and campaign-emissions mapping. Set Sustentável reports **>650 t CO2** offset via Carbonext; Publicis Production has used A.L.I.C.E. to map campaign emissions since 2023. **Note the category: these sell offsetting and measurement services, not certification against a public standard** |

### What is open, and where it sits

| Layer | Open option | Licence | Verdict |
|---|---|---|---|
| Production footprint (the mandated task) | **None** | — | `film production carbon footprint` = **0 repos**. Integrate with albert / MEDIA Carbon Calculator; do not propose replacing them |
| Streaming/delivery footprint | [co2.js](https://github.com/thegreenwebfoundation/co2.js) + [grid-intensity-go](https://github.com/thegreenwebfoundation/grid-intensity-go) | Apache-2.0 code, **CC-BY-SA + ODbL data** | Viable and permissive **after** the ODbL/DRM gate is cleared (Pattern 26.1) |
| Render / transcode energy | [cats](https://github.com/GreenScheduler/cats) + [carbon-aware-sdk](https://github.com/Green-Software-Foundation/carbon-aware-sdk) + [Deadline plugin](https://github.com/BreakTools/deadline-energy-cost-calculator) | **MIT** throughout | The one place in this plane where a complete permissive stack exists (Pattern 26.2) |
| Infrastructure energy | [kepler](https://github.com/sustainable-computing-io/kepler), [scaphandre](https://github.com/hubblo-org/scaphandre), [powerapi](https://github.com/powerapi-ng/powerapi) | Apache-2.0 / BSD-3 | Mature and permissive |
| Corporate / CSRD reporting | [esrs-xbrl-parser](https://github.com/aimabel-ai/esrs-xbrl-parser) | **ISC** | Thin and dormant 23 months; the best-starred alternative has **no licence** |
| Embodied hardware carbon | [boaviztapi](https://github.com/Boavizta/boaviztapi) | **AGPL-3.0** | Real, institutional, **copyleft** |

### The build-vs-buy line for this plane

**Never propose replacing albert, the MEDIA Carbon Calculator, PEAR or DIMPACT.** Two of them are
commissioning conditions, one is an EU instrument with EU Login identity, and the fourth owns the
sector's only widely-cited emissions figure. Nothing about them is a technology problem that an open
build solves, and a client who fails certification because a bespoke tool disagreed with albert has been
actively harmed.

The defensible proposal is the **evidence layer around them**: pull the data these calculators demand out
of the systems that already hold it — the production-management platform (**Yamdu**, Croogloo, SetHero,
StudioBinder, all already catalogued in this file), the payroll and accounting system, the render farm,
the CDN logs — assemble it into a submission-ready pack, and keep the per-asset numbers the client owns
and the certifier never sees. That layer is permissively licensable, client-owned, and the subject of
**Patterns 26.1 through 26.5**.

## The production-finance platform layer — added 2026-11-26 (pass 27)

**The structural fact for this plane.** There is **no open-source vertical platform for media
finance** — `ERPNext media production` and `film production ERP` return **zero usable projects**
(5 results, all 0★, all unlicensed). What exists is the horizontal ERP/accounting layer, which is
large, mature, actively maintained and in two cases **permissively licensed at the framework level**.
This is the Odoo-for-ERP / OpenMRS-for-healthcare position the KB asks for, and in media finance it
is **unoccupied**: the customisation is an industry chart of accounts plus a cost-report shape, not a
new platform.

| Platform | Repo | Licence — read where the API was unclear | Stars / Forks | Last push | What it gives a production-finance build |
|---|---|---|---|---|---|
| **ERPNext** | [frappe/erpnext](https://github.com/frappe/erpnext) | GPL-3.0 | 41,661★ / 13,646f | 2026-11-26 | Full ERP: GL, AP/AR, purchase orders, projects, timesheets, multi-currency, multi-company. The general ledger posts automatically from every submitted transaction. **The strongest starting point in the tier** — and its framework is separately MIT |
| **Frappe Framework** | [frappe/frappe](https://github.com/frappe/frappe) | **MIT** | 11,164★ / 5,561f | 2026-11-26 | The platform ERPNext is built on, and **permissive**. A production-accounting app can be built as a Frappe app and stay MIT-compatible; this licence split is the most useful fact in this section |
| **Odoo** (Community) | [odoo/odoo](https://github.com/odoo/odoo) | **LGPL-3.0** — API said `NOASSERTION`; `LICENSE` (43,529 B) read: *"Odoo is published under the GNU LESSER GENERAL PUBLIC LICENSE, Version 3"* | 56,124★ / 34,425f | 2026-11-26 | Analytic accounting is the key module: cost centres per production, per episode, per department. ⚠️ Community only — **Odoo Enterprise is separately licensed**, and the two are routinely confused in client conversations |
| **Dolibarr** | [Dolibarr/dolibarr](https://github.com/Dolibarr/dolibarr) | GPL-3.0 | 7,903★ / 3,634f | 2026-11-26 | Lighter ERP/CRM with accounting, projects and expense reports. Realistic for a single production company or a regional studio rather than a group |
| **Apache OFBiz** | [apache/ofbiz-framework](https://github.com/apache/ofbiz-framework) | **Apache-2.0** | 1,151★ / 771f | 2026-11-26 | The only **fully permissive** ERP framework in the tier, with a real accounting module. Lower adoption and a steeper build, but no copyleft question ever arises — the right answer when the deliverable must ship closed |
| **Firefly III** | [firefly-iii/firefly-iii](https://github.com/firefly-iii/firefly-iii) | AGPL-3.0 | 25,348★ / 2,415f | 2026-11-26 | Personal/small-entity finance manager with a strong API. Useful as a **cashflow and petty-cash surface** for a single production, not as a group ledger. ⚠️ AGPL |
| **LedgerSMB** | [ledgersmb/LedgerSMB](https://github.com/ledgersmb/LedgerSMB) | GPL-2.0 — `LICENSE` (12,339 B) read | 579★ / 178f | 2026-11-25 | Double-entry accounting/ERP with a long operational history. Dependable, unfashionable, genuinely open |
| **GnuCash** | [Gnucash/gnucash](https://github.com/Gnucash/gnucash) | GPL-2.0-or-3.0 — `LICENSE` (19,423 B) read: *"mutually-compatible set of licenses … GNU General Public License, Version 2, or (at your option) Version 3"* | 4,429★ / 1,010f | 2026-11-26 | Desktop double-entry with proper accounting semantics. Its real value here is as a **reference implementation of a chart of accounts**, not as a deployment target |
| **EspoCRM** | [espocrm/espocrm](https://github.com/espocrm/espocrm) | AGPL-3.0 | 3,674★ / 1,060f | 2026-11-26 | The CRM half: financier, sales-agent, distributor and co-producer relationships — the pipeline that *precedes* the ledger. ⚠️ AGPL |
| **Kitsu / Zou** | [cgwire/kitsu](https://github.com/cgwire/kitsu) · [cgwire/zou](https://github.com/cgwire/zou) | AGPL-3.0 (both) | 779★ / 190f · 203★ / 148f | 2026-11-26 (both) | Production tracking with real man-day and bid data — the **operational source of truth a cost report must reconcile against**. Already catalogued in this file for the production plane; it is listed again because it is the join point for Pattern 27.5 |
| **CineSpend** | [ChrisTempel/CineSpend](https://github.com/ChrisTempel/CineSpend) | **MIT** | 8★ / 1f | 2026-10-06 | The only open film **budgeting** app, ten currencies, macOS-only. Unchanged since pass 17: prior art and a data-shape reference, **not** a base to build a client platform on |
| **Open Shot Designer** | [koosoli/OpenShotDesigner](https://github.com/koosoli/OpenShotDesigner) | **GPL-3.0** — API said `NOASSERTION`; `LICENSE` (35,809 B) read: GPL-3.0-or-later | 47★ / 9f | 2026-11-26 | Production-planning suite (scheduling, call sheets). Now the **best-starred** open production-planning tool found; pushed on measurement day. Carries no accounting, and GPL-3.0 constrains redistribution |

### 🚫 Not open source, despite appearing in every search

**[akaunting/akaunting](https://github.com/akaunting/akaunting) — 10,349★ — is licensed under the
Business Source License** (`LICENSE.txt`, 3,654 B, read in full: MariaDB BSL text, Licensor
"Akaunting, Inc.", with a limited Additional Use Grant). GitHub reports `NOASSERTION`. It is the
highest-starred licence trap in this knowledge base and it sits in the exact category a media-finance
engagement searches first. See `repos/foundations.md` pass 27 for the full reading.

### What to propose, and what never to propose

**Never propose replacing the production accounting system of record** where one is in place.
Movie Magic Budgeting, Showbiz, Wrapbook, Cast & Crew, GreenSlate and Entertainment Partners are not
merely incumbent — they are **wired into payroll, union reporting and the auditors' expectations**,
and in several jurisdictions the incentive auditor expects reports in their shapes. A client who
cannot produce an auditor-recognised cost report because a bespoke ledger disagreed with the payroll
company has been actively harmed, and the credit itself can be delayed or lost.

**The defensible proposal is the layer those systems do not occupy**: an **incentive-eligibility and
claim-evidence layer** that reads the budget, the ledger, the payroll export and the production
tracker, computes qualification per jurisdiction as versioned rules-as-code, and emits a
submission-ready claim pack with every number traceable to its source document. It is permissively
licensable end to end (Catala Apache-2.0 + Frappe MIT + ledger BSD-3 + Timefold Apache-2.0), the
client owns the rule sets, **no incumbent sells it**, and it is the subject of **Patterns 27.1–27.5**.

## Platforms that enforce age ratings — added 2026-11-26 (pass 28)

The question this section answers: **if a client needs a catalogue where every title carries the right
rating in every territory and the player acts on it, what real system can be customised?** The answer
is honest and slightly uncomfortable: the enforcement platforms are the self-hosted media servers,
and the vocabulary comes from the Linux desktop.

| Platform | Licence | Scale | What it gives you in this plane | The catch |
|---|---|---|---|---|
| **Jellyfin** | **GPL-2.0** | 59,787★ / 5,879f, pushed 2026-11-26 | The most complete open enforcement surface: **45 per-territory rating tables**, per-user profiles, rating ceilings, and a working parental-control UI. Already in this KB as a media server; **this is the first pass to place it as a ratings platform.** | GPL-2.0 — fine for a self-hosted client deployment, a decision to make deliberately for a product. And the string-matching defect in `repos/foundations.md` must be fixed before it is trusted across territories. |
| **Seerr** | **MIT** | 13,359★ / 1,169f, pushed 2026-11-26 | Request and discovery layer in front of Jellyfin/Plex/Emby, with **per-user maximum movie and TV rating ceilings and an unrated-titles toggle**. Ratings are centralised in one constants file, which makes a territory-aware refactor tractable. | MIT and active — **the best-licensed starting point in the plane.** Its predecessor Overseerr is archived; do not start there. |
| **Kodi** (`xbmc/xbmc`) | **NOASSERTION** on the API (GPL-2.0 in practice) | 21,551★ / 6,692f, pushed 2026-11-26 | The client-side player with the widest device reach, where a rating has to actually gate playback. | Resolve the licence from the tree, and apply pass 8's rule: for a native stack, the licences that bind are those of the **linked** libraries, not the repo. |
| **AppStream / Flathub** | **LGPL-2.1** | 283★ / 147f, pushed 2026-11-24 | Not a media platform — **the vocabulary and the territory mapping.** This is where OARS becomes a per-country ladder. Treat it as the reference implementation to port, not a dependency to adopt. | A games/apps ladder, and a lossy projection of each board's real one. See the measured rung loss for AR and AU. |
| **Nebula** (`nebulabroadcast/nebula`) | already in this KB (pass 25) | — | The broadcast MAM/playout system where a rating has to reach the schedule and the on-air compliance log. | Its rating field is a free-text metadata key, not a typed `(system, value)` pair — the same defect as everything else in the plane. |

### What does **not** exist, stated plainly so nobody promises it

There is **no open-source equivalent of a classification-submission system** — no open client for
lodging a title with ESRB, PEGI, USK, GRAC, CERO, the BBFC or Brazil's ClassInd, and no open
implementation of the IARC questionnaire that Google Play, the Microsoft Store and Nintendo use to
issue ratings across territories from one self-declaration. `IARC age rating` returns **two
repositories, both at 0 stars**. The allocation of the certificate is the closed step, exactly as the
registry allocation was the closed step for ISRC and ISWC in pass 5 and for CPT and MedDRA in the
healthcare KB.

**So the honest architecture for a client is a hybrid:** OARS/AppStream for the declared criteria and
the territory mapping, Seerr/Jellyfin for enforcement, the board's own submission process for the
certificate, and **a typed `(system, value)` store of your own in the middle**, because nothing in the
open estate provides one. That middle piece is the billable work, and it is small.

## The interactive & branching-story tier — added 2026-11-26 (pass 29)

This tier answers one question: **if a client wants a branching experience in production next
quarter, what existing system do we customise?** All rows verified 2026-11-26 (`git ls-remote` plus a
licence read).

| Platform | Repo | Licence | Stars | What it is, and who runs it |
|---|---|---|---|---|
| **H5P** (content types) | [h5p/h5p-branching-scenario](https://github.com/h5p/h5p-branching-scenario) · [h5p/h5p-interactive-video](https://github.com/h5p/h5p-interactive-video) | **MIT** | 36★ / 267★ | The de-facto platform for branching scenarios in learning, onboarding, museum and brand experiences. Decision trees over video, with scoring. |
| **H5P** (host — PHP) | [h5p/h5p-php-library](https://github.com/h5p/h5p-php-library) | **GPL-3.0** | 156★ | The core runtime/host. ⚠️ Different licence from the content types above. |
| **H5P** (host — Node/TS) | [Lumieducation/H5P-Nodejs-library](https://github.com/Lumieducation/H5P-Nodejs-library) | **GPL-3.0** | 207★ | The host a web team would actually pick. Also copyleft. |
| **H5P in Moodle / WordPress** | [h5p/moodle-mod_hvp](https://github.com/h5p/moodle-mod_hvp) · [h5p/h5p-wordpress-plugin](https://github.com/h5p/h5p-wordpress-plugin) | GPL-3.0 / platform-GPL | 160★ / 77★ | The two deployment routes that need no new infrastructure. Moodle is GPL already, so the host licence costs nothing there. |
| **Twine** | [klembot/twinejs](https://github.com/klembot/twinejs) | **GPL-3.0** | 2,964★ | The authoring platform the client's writers may already know (it is taught in schools and newsrooms). Use it as a tool; do not embed it. |
| **Twine, headless** | [tmedwards/tweego](https://github.com/tmedwards/tweego) · [videlais/extwee](https://github.com/videlais/extwee) · [klembot/chapbook](https://github.com/klembot/chapbook) | BSD-2 / MIT / MIT | 169★ / 44★ / 103★ | The permissive half: compile Twine stories in CI and ship them inside your own product. |
| **Ren'Py** | [renpy/renpy](https://github.com/renpy/renpy) | MIT (docs-tree grant) | 7,065★ | The commercial visual-novel platform. Ships to Windows/macOS/Linux/Android/iOS/web from one script. |
| **WebGAL** | [OpenWebGAL/WebGAL](https://github.com/OpenWebGAL/WebGAL) | MPL-2.0 | 4,054★ | Browser-native VN platform, CN-origin, bilingual. The right pick when the deliverable is a URL. |
| **Godot + dialogue stack** | [godotengine/godot](https://github.com/godotengine/godot) + [dialogic](https://github.com/dialogic-godot/dialogic) + [godot_dialogue_manager](https://github.com/nathanhoad/godot_dialogue_manager) + [godot-ink](https://github.com/paulloz/godot-ink) | **all MIT** | 120,887★ / 6,194★ / 4,005★ / 793★ | The only **fully-MIT** authoring-to-shipping chain in this plane, across desktop, mobile, console and web. |
| **RDK Lightning** | [rdkcentral/Lightning](https://github.com/rdkcentral/Lightning) · [rdkcentral/Lightning-SDK](https://github.com/rdkcentral/Lightning-SDK) | Apache-2.0 | 204★ / 138★ | The TV/set-top app framework. This is the *only* open answer to "and how does it run on the operator's box?". |
| **BBC StoryPlayer** | [bbc/storyplayer](https://github.com/bbc/storyplayer) | **GPL-3.0** | 19★ | Broadcaster-grade object-based media player plus the Object Based Media Schema. Public-service R&D, still pushed this month, and the only broadcaster-shaped runtime that is open. |
| **BBC Audio Orchestrator** | [bbc/audio-orchestrator](https://github.com/bbc/audio-orchestrator) | **GPL-3.0** | 11★ | Companion-device orchestrated audio. A prototype, and the only one. |
| **OpenFMV** | [Comedian1926/OpenFMV](https://github.com/Comedian1926/OpenFMV) | MIT | 241★ | Local-first editor for interactive video and branching scenes; the project is new in 2026. The best permissive starting point for branching *video* specifically. |

### This tier does **not** obey this file's licence law — and that is the finding

Every earlier tier in this file bent one way: permissive at the edges, copyleft in the middle. Here it
is **split by role**: the *authoring* tools are copyleft (Twine GPL-3.0, H5P hosts GPL-3.0,
StoryPlayer GPL-3.0) while the *runtimes and formats* are permissive (ink, Yarn, Godot, Ren'Py,
Lightning, OpenFMV). The practical consequence is the opposite of the usual advice: **adopt the
copyleft tools as tools** — nobody ships Twine to a customer — **and build the shipped artefact on
the permissive runtimes.** A proposal that embeds an authoring UI is a GPL conversation; a proposal
that embeds a player is not.

### Gap: there is no open interactive-experience *delivery platform*

There is no interactive equivalent of PeerTube or Owncast — nothing that stores, versions, serves,
measures and A/B-tests a branching experience. The pieces exist separately (a player, a story format,
an analytics pipeline from pass 7) and nothing joins them. Note that **the market retreated from this
category**: Netflix withdrew its interactive catalogue in stages ending 2025-05-12, citing the
technology as "limiting". So the honest reading is not "an obvious product is missing" but **"the
platform shape failed once already"** — which is why `compose/patterns.md` pass 29 points the same
components at learning, brand experience, CTV and AI characters instead.

---

## Pass 30 (2026-11-26) — platforms for answer-engine discovery & referral measurement

### ⛔ The platform refusal, stated first

**There is no open-source "AI visibility platform" in the sense this file normally means the word** —
no Odoo, no OpenMRS, no Moodle for this plane. Searched and measured. What exists is three tiers, and
the shape of the tiering is the commercial finding:

| Tier | What's in it | Licence reality |
|---|---|---|
| **Permissive, self-hostable, general-purpose** | `umami` (MIT, 40,403★), `goaccess` (MIT, 21,158★), `lissy93/web-check` (MIT, 35,661★) | ✅ Buildable. But **none of them is about AI discovery** — they are analytics and inspection tools you must *extend* into this plane. |
| **Copyleft analytics** | `matomo` (GPL-3.0, 22,064★), `plausible` (AGPL-3.0, 29,945★), `matomo-org/device-detector` (LGPL-3.0) | ⚠️ Matomo is the most *customisable* platform here and the most licence-constrained. AGPL on a hosted service is the hard one. |
| **Purpose-built for AI visibility** | `loamly` (MIT, **21★**, dormant since 2026-01-28); a handful of WordPress plugins (RowanWeb Bot Traffic, Referenced, Crawlantix, BotSieve) | ❌ Not a platform tier. Several plugins ship data to an external service on a token, which is a **data-governance question before it is a feature question**. |
| **Proprietary** | Ahrefs Bot Analytics, Cloudflare Attribution Business Insights, Semrush AI Visibility Toolkit, AthenaHQ, Rankscale, Writesonic | 🔒 Closed. These define what buyers expect the category to do. |

**The consequence for a Globant engagement is unusually clean:** in most planes this KB records, the
advice is "customise the incumbent open platform." Here the incumbent open platform **does not
exist**, and the two permissive bases (`umami`, `goaccess`) are generic. So this is a **build**
engagement on permissive foundations, not a customisation engagement — and it is one of the few
planes in this KB where that is the honest recommendation rather than a sales preference.

### Where the discovery metadata is actually emitted — the CMS tier

The platforms that decide whether a media client is machine-readable are the ones already recorded in
this file: **WordPress** and **Drupal** (both carry `llms.txt` modules/plugins — note pass 30's
finding that the file is a measured dud before installing one), plus the headless tier. The practical
point: schema.org markup, news sitemaps and clean main-content extraction are **CMS template work**,
not a separate product. `schemaorg/schemaorg` (Apache-2.0, 6,320★, already in this KB) and
`ekalinin/sitemap.js` (MIT, 1,710★) are the artefacts; the CMS is where they ship.

### The one platform-shaped gap worth naming

**A publisher-side "answer-engine ledger" product does not exist in open source**: one place that
joins (a) crawler hits from logs, (b) chatbot referrals, (c) Google Search Console generative-AI
impressions, and (d) human sessions, into a single weekly view with an explicit, honest statement of
what is **unmeasurable**. Every component is permissive and available (`goaccess`,
`crawler-user-agents`, `umami`), the demand is evidenced by the proprietary tier's existence, and the
integration is the product. See `compose/patterns.md` pass 30, pattern **P17**.

⚠️ One hard dependency is **unverified**: whether Search Console's generative-AI data is reachable
through the **Search Console API** or only the UI could not be confirmed — `developers.google.com`
does not resolve from this session (outside the allowed network domains). Treat the API as **not
confirmed**; scope the first iteration around a manual export and say so in the proposal.

## The live-event, show-control & stagecraft tier — added 2026-11-27 (pass 31)

These are the "Odoo for live events": complete, installable systems that a venue, touring production
or installation already runs, and that an AI layer can sit on top of. **The licence shape of this tier
breaks the rule that holds elsewhere in this file** — the KB's standing finding is *permissive at the
pipeline, copyleft at the platform*, and here the single most complete platform, QLC+, is
**Apache-2.0**. It is the clearest counter-example in the whole KB, and it is the reason this plane is
worth leading with commercially.

| Platform | Repo | Licence | Stars | What it replaces | AI layer to add |
|---|---|---|---|---|---|
| **QLC+** | [mcallegari/qlcplus](https://github.com/mcallegari/qlcplus) | **Apache-2.0** | 1,593★ | An entry/mid-tier lighting console (dot2, Onyx-class) | Cue generation from a script or audio; natural-language patching. `lights-pi` already bridges MCP→QLC+ |
| **Bitfocus Companion** | [bitfocus/companion](https://github.com/bitfocus/companion) | MIT + CLA | 2,376★ | Proprietary control-surface middleware | Agent-authored button pages per show; anomaly alerts on device state |
| **Chataigne** | [benkuper/Chataigne](https://github.com/benkuper/Chataigne) | GPL-3.0 | 1,718★ | QLab-class cueing for installations and museums | Sensor→state-machine authoring; the agent writes the state machine, a human approves it |
| **xLights** | [xLightsSequencer/xLights](https://github.com/xLightsSequencer/xLights) | GPL-3.0 | 768★ | Pixel-show sequencing suites | Music→sequence generation; this is the one place the agent layer already has traction (32★, 10 forks) |
| **Falcon Player (FPP)** | [FalconChristmas/fpp](https://github.com/FalconChristmas/fpp) | ⚠️ GPL-2 + LGPL-2.1 + **CC-BY-ND** | 747★ | Dedicated show-playback appliances | **Read the licence manifest before any client work** — some components may not be modified at all |
| **Open Lighting Architecture** | [OpenLightingProject/ola](https://github.com/OpenLightingProject/ola) | LGPL-2.1 (in `COPYING`) | 773★ | Proprietary protocol-conversion boxes | The integration substrate: one daemon between an agent and every DMX transport |
| **Linux Show Player** | [FrancescoCeruti/linux-show-player](https://github.com/FrancescoCeruti/linux-show-player) | GPL-3.0 | 314★ | QLab (macOS-only, proprietary) for sound playback | Cue-list generation from a script; auto-levelling |
| **BlenderDMX** | [open-stage/blender-dmx](https://github.com/open-stage/blender-dmx) | GPL-3.0 | 291★ | Proprietary pre-visualisation (WYSIWYG-class) | Pre-vis from an MVR scene; render a look before the rig is built |
| **MapMap** | [mapmapteam/mapmap](https://github.com/mapmapteam/mapmap) | GPL-3.0 | 731★ | MadMapper / Resolume-class mapping | Automated surface calibration; content fitting |
| **WLED** | [wled/WLED](https://github.com/wled/WLED) | **EUPL-1.2** | 19,132★ | Proprietary LED controllers | Scene generation; but note the EU-law copyleft before embedding |

### How to add the AI layer in this tier

The integration seam is unusually clean, and it is the reason this plane is a good first engagement:
**QLC+ exposes a web API, OLA exposes a daemon, and both speak sACN/Art-Net.** An agent never has to
touch a fixture directly — it writes to a console or a daemon that already knows how to. That is the
opposite of the generative-media planes, where the agent *is* the pipeline.

Sequence it: (1) agent proposes, (2) console holds the authoritative show file, (3) a human programmer
reviews in pre-vis, (4) the rig executes. The reviewable artefact in step 2–3 is **MVR**
([python-mvr](https://github.com/open-stage/python-mvr), MIT) — treat it exactly as this KB treats
`.otio` in the editorial handoff.

### Gaps in this tier — stated as gaps

- **There is no open venue-operations platform.** Ticketing has open options already recorded in this
  file from pass 19; **crewing, scheduling, equipment inventory and stage management do not** —
  `stage management`, `front of house` and `touring` were absolute zeros across 1.9 MB of this KB
  before this pass, and the search produced no open platform for any of them. The industry runs on
  spreadsheets and proprietary SaaS. This is the largest unserved platform gap found in this plane.
- **Ride and attraction control is not open and should not be proposed as such** — safety-rated PLC
  engineering with injury liability. See `repos/foundations.md`.
- **Fixture data is registration-gated** (GDTF Share account, per-manufacturer terms). The platform is
  free; the data that makes it useful is not. Resolve this before quoting any live-event build.

## The device, TV-platform & middleware tier — added 2026-11-27 (pass 32)

Added 2026-11-27 (pass 32). These are the runnable systems on the *endpoint* side of the plane — the
TV OS, the broadcast middleware and the reference clients a client engagement can actually start
from and put an agentic layer on. All verified 2026-11-27; licences read from file where the GitHub
API returned `NOASSERTION`/`NONE`.

### The regional middleware — and this is the part that is **MIT, by design**

Every region runs a *different* interactive-TV stack, each with its own open reference
implementation. A pan-regional client needs all four; none of them was in this KB before this pass.

| Platform | Repo | Licence | Stars | Last push | Region & role |
|---|---|---|---|---|---|
| **ORB (Open Red Button)** | [OpenRedButtonProject/orb](https://github.com/OpenRedButtonProject/orb) | **Apache-2.0** | 24★ | **2026-11-19** | **EMEA.** The only open-source HbbTV stack: JS + C++ over Android WebView/Chromium and RDK/WPE. Launched by Ocean Blue Software (2021); vendor claims it is the only mass-deployed open HbbTV solution. ⚠️ Production needs browser patches, platform integration and DRM — commercial support exists. |
| **HbbTV Reference Application** | [HbbTV-Association/ReferenceApplication](https://github.com/HbbTV-Association/ReferenceApplication) | MIT | 90★ | 2026-03-03 | **EMEA.** The association's own reference app. MIT — unusually open for a broadcast body. |
| **DVB-I Reference Client** | [DVBProject/DVB-I-Reference-Client](https://github.com/DVBProject/DVB-I-Reference-Client) | MIT | 74★ | **2026-11-17** | **EMEA/Global.** Built by Sofia Digital for the DVB Project. Back end generates/edits **service lists**; front ends are an **HbbTV OpApp** and an **Android PWA**. The single best starting point for an IP-linear channel product. |
| **DVB-I Central Service Registry** | [DVBProject/DVB-I-Reference-CSR](https://github.com/DVBProject/DVB-I-Reference-CSR) | MIT | 14★ | 2025-09-23 | **EMEA/Global.** Service-list discovery registry — the piece that makes DVB-I work across territories. |
| **Hybridcast Connect SDKs** | [nhkrd/hyconet4j](https://github.com/nhkrd/hyconet4j) (Java) · [nhkrd/antwapp4hc](https://github.com/nhkrd/antwapp4hc) (TV emulator) · [nhkrd/hyconet.js](https://github.com/nhkrd/hyconet.js) · [nhkrd/node-red-contrib-hyconet](https://github.com/nhkrd/node-red-contrib-hyconet) | **MIT** (all four) | 15★ / 21★ / 7★ / 7★ | 2021-11-17 / 2021-11-17 / 2020-09-29 / 2020-09-30 | **APAC (Japan).** NHK's own reference implementations of Hybridcast Connect (IPTVFJ STD-0010/0011, standardised Sep 2018). ⚠️ **All four dormant 5+ years** — see the warning below. |
| **Ginga** | [TeleMidia/ginga](https://github.com/TeleMidia/ginga) | **GPL-2.0** | 53★ | 2024-11-25 | **LATAM (Brazil).** PUC-Rio's implementation of the Ginga standard (ITU-T H.761, ABNT NBR 15606). The application layer of Brazil's **TV 3.0 / DTV+**. ⚠️ GPL-2.0, and 2 years since last push. |
| **OpenBA NextGen TV** | [openBA-NextGenTV/OpenBA-NextGenTV](https://github.com/openBA-NextGenTV/OpenBA-NextGenTV) | **MIT** | 15★ | **2022-09-21** | **North America.** Sinclair's open-sourced ATSC 3.0 broadcast application. ⚠️ **Dormant 4.2 years** — the NA region's only open broadcast-app artefact, and nobody has touched it. |
| **node-hbbtv** | [fraunhoferfokus/node-hbbtv](https://github.com/fraunhoferfokus/node-hbbtv) | **LGPL-3.0** | 51★ | 2025-03-07 | **EMEA.** Fraunhofer FOKUS' feature-complete HbbTV 2.0 **companion-screen** implementation, incl. a polyfill for web apps. ⚠️ LGPL — dynamic linking is fine, static bundling is not. |
| **HbbPlayer** | [Samsung/HbbPlayer](https://github.com/Samsung/HbbPlayer) | MIT | 61★ | **2018-06-26** | **EMEA.** Samsung's HbbTV media player, open-sourced then abandoned 8.4 years ago. Reference only. |

**⚠️ The pattern to brief a client on: the regional middleware is permissive and dormant.** Nine of
the twelve repos above are MIT or Apache-2.0 — standards bodies license openly because they want
adoption. But **six of them have not been pushed in over a year, and three are 4–8 years cold.**
The NA artefact (`openBA`) and the whole APAC Hybridcast toolchain are the extreme cases. These are
**specifications with reference code attached, not maintained products.** Budget to adopt and
maintain the code, not to depend on it — and read each one as evidence of what the standard requires
rather than as a supported SDK.

### The TV operating systems and consumer media platforms — **and here the licence flips to copyleft**

| Platform | Repo | Licence | Stars | Last push | Role |
|---|---|---|---|---|---|
| **webOS Open Source Edition** | [webosose/build-webos](https://github.com/webosose/build-webos) | **Apache-2.0** (declared in README; **no licence file**) | 732★ | 2025-04-01 | LG's open TV OS build layer. The only open TV *operating system* of a top-3 vendor. Pair with [`enactjs/enact`](https://github.com/enactjs/enact) (Apache-2.0, 347★) for the app layer. |
| **RDK Services** | [rdkcentral/rdkservices](https://github.com/rdkcentral/rdkservices) | Apache-2.0 | 44★ | 2026-11-18 | The operator set-top stack (Thunder plugins) — Comcast/Sky lineage. With [`ThunderJS`](https://github.com/rdkcentral/ThunderJS) (Apache-2.0, 6★) for JS control. |
| **Jellyfin** | [jellyfin/jellyfin](https://github.com/jellyfin/jellyfin) | **GPL-2.0** | 59,790★ | 2026-11-26 | The free media system — server + API, with clients on every TV platform. The largest platform in this tier by two orders of magnitude. |
| **Kodi** | [xbmc/xbmc](https://github.com/xbmc/xbmc) | **GPL-2.0-or-later** (read from `master/LICENSE.md`, 290 B) | 21,552★ | **2026-11-27** | The media-centre application; the de facto reference for TV-UI navigation patterns. Pushed the day of this pass. |

**📌 This tier confirms `intel/trends.md` trend 4 ("permissive at the pipeline, copyleft at the
platform") and adds a sharper rule.** The split here is not pipeline-vs-platform, it is
**standards-body-vs-product**: the four regional broadcast stacks written by standards bodies and
public broadcasters (DVB, HbbTV Association, NHK, Sinclair) are **MIT**, while every consumer
*product* in the tier (Jellyfin GPL-2.0, Kodi GPL-2.0+, Ginga GPL-2.0, node-hbbtv LGPL-3.0) is
**copyleft**. → For a client deliverable that must stay proprietary, the regional reference clients
are the safe starting point and the media platforms are not. ORB (Apache-2.0) is the one place where
a *platform-grade* implementation is also permissive, which is why it matters out of proportion to
its 24 stars.

### ⛔ Gaps in this tier, stated as gaps

- **There is no open Roku platform.** Roku OS is closed; the open ecosystem is *tooling only* —
  [`rokucommunity/brighterscript`](https://github.com/rokucommunity/brighterscript) (MIT, 212★,
  pushed 2026-11-27), [`roku-deploy`](https://github.com/rokucommunity/roku-deploy) (MIT, 60★),
  [`roku-debug`](https://github.com/rokucommunity/roku-debug) (MIT, 19★),
  [`vscode-brightscript-language`](https://github.com/rokucommunity/vscode-brightscript-language)
  (MIT, 132★). All four MIT, all pushed within a week of this pass, all community-run with **no
  vendor backing**. For the #1–#2 TV OS in the United States, the entire open toolchain is ~423
  stars maintained by volunteers.
- **There is no open Tizen platform either** — only [`Samsung/Wits`](https://github.com/Samsung/Wits)
  (Apache-2.0, 125★, 2026-05-12), Samsung's own hot-reload tool for Tizen web apps.
- **The HbbTV conformance test suite is not open at all**: licensed only to member companies and
  tracked in a members-only SVN repository. A client needing certified HbbTV output must buy
  membership or use a registered test centre — budget for it.

---

## Pass 33 addendum (2026-11-27) — monitoring, watching & archiving platforms

> Verified 2026-11-27: existence via `git ls-remote`, licence by reading the file, last commit via
> shallow clone. No star counts this pass (API scoped to session repos — see `agents/top.md` pass 33).

**The procurement fact for this plane:** unlike every other plane in this file, **the permissive
options here are the good ones**. The copyleft tier is real but avoidable, and the one self-hostable
product that calls itself "media intelligence" is both AGPL-3.0 and a single-maintainer project.

### ✅ Permissive — embed freely in a client deliverable

| Platform | Licence | Last commit | What it is |
|---|---|---|---|
| [dgtlmoon/changedetection.io](https://github.com/dgtlmoon/changedetection.io) | **Apache-2.0** (11,381 B) | **2026-11-27** | Self-hosted web-page change detection with notifications (email, Slack, Discord, Telegram, webhooks). **The "watch this page" primitive** — competitor newsrooms, regulator pages, rival press rooms, pricing pages. Committed on the day of this pass. The single most reusable platform on this plane. |
| [miniflux/v2](https://github.com/miniflux/v2) | **Apache-2.0** (10,173 B) | 2026-11-26 | Minimalist, single-binary feed reader with a clean API. **The permissive feed-ingestion service** — the Apache-licensed answer where FreshRSS and RSSHub are AGPL. |
| [RSS-Bridge/rss-bridge](https://github.com/RSS-Bridge/rss-bridge) | **Unlicense** (public domain) | 2026-11-25 | Generates feeds for sites that publish none. Public domain — no obligations whatsoever. Licence found only in `UNLICENSE`; see the probe correction in `agents/top.md` pass 33. |
| [huginn/huginn](https://github.com/huginn/huginn) | MIT (1,097 B) | **2026-11-27** | Self-hosted agent system for watching and acting on events — the permissive orchestration layer between collection and alerting. Committed the day of this pass. |
| [ArchiveBox/ArchiveBox](https://github.com/ArchiveBox/ArchiveBox) | MIT (1,069 B) | 2026-11-26 | Self-hosted web archiving. **MIT, which makes it the clearance-safe archive tier** — contrast browsertrix-crawler below. |
| [meilisearch/meilisearch](https://github.com/meilisearch/meilisearch) | MIT | 2026-11-26 | Fast typo-tolerant search. The retrieval surface over a clippings corpus when OpenSearch is heavier than needed. |
| [ranahaani/GNews](https://github.com/ranahaani/GNews) | MIT (1,068 B) | 2026-10-25 | Google News query client. ⚠️ Small library, and see the **14-edition duplication trap** in `compose/patterns.md` pattern 51 before using it to compute anything. |

### ⚠️ Copyleft — useful, but keep out of the shipped artifact

| Platform | Licence | Last commit | Note |
|---|---|---|---|
| [FreshRSS/FreshRSS](https://github.com/FreshRSS/FreshRSS) | **AGPL-3.0** (34,522 B) | **2026-11-27** | Mature self-hosted aggregator, very actively maintained. Run as a separate service; do not link into a deliverable. |
| [DIYgod/RSSHub](https://github.com/DIYgod/RSSHub) | **AGPL-3.0** (34,522 B) | **2026-11-27** | Feeds for "anything", with a very large adapter library — operationally the most capable collector here, and the most licence-constrained. |
| [searxng/searxng](https://github.com/searxng/searxng) | **AGPL-3.0** (34,519 B) | 2026-11-26 | Self-hosted metasearch; a discovery tier for finding mentions search APIs will not return. |
| [webrecorder/browsertrix-crawler](https://github.com/webrecorder/browsertrix-crawler) | **AGPL-3.0** (34,522 B) | 2026-11-26 | High-fidelity WACZ crawling — better capture quality than ArchiveBox, worse licence. **If the archive must ship inside the product, use ArchiveBox (MIT); if it is an internal service, use this.** |
| [Scognamiglio1969/radar-intelligence](https://github.com/Scognamiglio1969/radar-intelligence) | **AGPL-3.0** (34,522 B) | 2026-09-17 | **The only self-hostable platform that positions itself as "media intelligence / social listening"** — an open alternative to Talkwalker/Brandwatch. ⚠️ Single maintainer, ~2 months quiet, AGPL. Recorded because it is the category's *only* entrant, not because it is ready. |

### ⛔ The institutional gap — the world's largest public media monitor has no repo

**Europe Media Monitor (EMM)**, run by the European Commission's **Joint Research Centre**, tracks
**~20,000 news sites, ~500,000 pages per day, in 80 languages across 150 countries**, with
clustering, multi-label classification, cross-script name-variant matching and topic
detection/tracking, and now integrates LLMs. It partners with WHO on the EIOS epidemic-intelligence
initiative. Public applications at `media-monitor.europa.eu`.

**It is not open source.** There is no repository to clone, fork or build on — it is an institutional
system with public web applications and a research contact address. Searched on 2026-11-27 for a JRC
EMM code repository; **none exists publicly.**

This is the informed gap of the pass: **Europe operates the most capable multilingual media
monitoring system in the world and publishes none of its code**, while the EMEA market simultaneously
demands digital sovereignty and self-hosting (DPP European Media Trends 2026). An EU-resident,
self-hosted monitoring stack assembled from the Apache/MIT substrate above is therefore a *build*,
not a *procurement* — see `intel/market.md` → Opportunities by region → EMEA.

### ⛔ And the category that genuinely does not exist

There is **no open-source implementation of AMEC's Integrated Evaluation Framework** — the industry's
own measurement standard (see `intel/trends.md` pass 33). The framework is free to use and the
standard is settled; **no repo implements it.** Searched 2026-11-27: the open-source results for
"PR measurement dashboard" are overwhelmingly GitHub *pull-request* dashboards, which is a naming
collision, not a market. `pr-radar` (MIT, 6 days old) is the only thing in the vicinity.

---

## Pass 34 addendum (2026-11-27) — the ad-integrity, verification & consent platform tier

Verified 2026-11-27. The question this tier answers: **what can a client actually run, self-hosted,
to check that the ads it bought or sold were real, authorised, viewable and safely placed?**

### What you can self-host today

| Platform | Repo | License | Stars | Last push | What it gives a client |
|---|---|---|---|---|---|
| **Prebid Server** | [prebid/prebid-server](https://github.com/prebid/prebid-server) | Apache-2.0 | 595 | 2026-11-26 | The real-time auction, self-hosted. **The only permissively-licensed, production-grade auction platform in open source** — and the place where a supply-chain (`schain`) policy can actually be *enforced* rather than reported on, because you own the code path. |
| **Prebid.js** | [prebid/Prebid.js](https://github.com/prebid/Prebid.js) | Apache-2.0 | 1,619 | 2026-11-27 | The client-side half; pushed on the day of this pass. |
| **Matomo** | [matomo-org/matomo](https://github.com/matomo-org/matomo) | GPL-3.0 | 22,066 | 2026-11-27 | Self-hosted analytics with real bot exclusion. The client owns the counting party — the single most useful structural change available to a publisher on this plane. Copyleft: deploy, do not embed. |
| **Jitsu** | [jitsucom/jitsu](https://github.com/jitsucom/jitsu) | **MIT** | 5,142 | 2026-11-26 | Scriptable event ingestion. **The permissive choice in this tier.** |
| **PostHog** | [PostHog/posthog](https://github.com/PostHog/posthog) | MIT Expat except `ee/` | 41,180 | 2026-11-27 | Product analytics; usable permissively if `ee/` is avoided. |
| **CrowdSec** | [crowdsecurity/crowdsec](https://github.com/crowdsecurity/crowdsec) | MIT | 15,814 | 2026-11-25 | Deployed as the pre-bid GIVT gate: crowdsourced malicious-IP intelligence, free, updated continuously. **The highest-leverage unused component on this plane.** |
| **OWASP CRS + Coraza** | [coreruleset/coreruleset](https://github.com/coreruleset/coreruleset) / [corazawaf/coraza](https://github.com/corazawaf/coraza) | Apache-2.0 / Apache-2.0 | 3,376 / 4,061 | 2026-11-27 / 2026-11-26 | Rules plus an embeddable engine — put traffic filtering *inside* the ad server. |
| **ALTCHA** | [altcha-org/altcha](https://github.com/altcha-org/altcha) | MIT | 2,923 | 2026-11-20 | Proof-of-work human check that does not export user data to a US vendor — the EMEA-safe CAPTCHA. |
| **Ads.txt Manager (WordPress)** | [10up/ads-txt](https://github.com/10up/ads-txt) | GPL-2.0 | 61 | 2026-11-24 | For the very large population of publishers whose CMS is WordPress, this is the entire declaration-management product, maintained, free. |
| **Cookie Consent + iabtcf-es** | [orestbida/cookieconsent](https://github.com/orestbida/cookieconsent) + [InteractiveAdvertisingBureau/iabtcf-es](https://github.com/InteractiveAdvertisingBureau/iabtcf-es) | MIT + Apache-2.0 | 5,786 + 156 | 2026-11-22 / 2026-11-03 | A self-hosted consent UI plus the official TCF encoder. ⚠️ **Read the limit below before quoting this as a CMP.** |

### ⛔ The three things you cannot self-host, and why — read before scoping

This is the procurement core of the plane. Each of these is blocked by an **accreditation**, not by a
licence or a missing repository.

1. **An MRC-accredited invalid-traffic number.** The Media Rating Council accredits IVT measurement,
   and accreditation distinguishes **GIVT** (general — bots, spiders, datacenter traffic; *required*
   for accreditation) from **SIVT** (sophisticated — hijacked devices, falsified impressions, ad
   stacking; MRC *strongly recommends* removing it but does not mandate it for accreditation).
   HUMAN's platform was accredited for both GIVT and SIVT under the IVT 2.0 addendum per an MRC letter
   of **2026-04-14**. **You can compute GIVT yourself from the permissive substrate above. You cannot
   make the resulting number accredited.** When a client says "we need IVT measurement", establish
   first whether they need the *number* or the *accreditation* — the costs differ by orders of magnitude.
2. **In-app and CTV viewability.** The OM SDK **JavaScript** clients are Apache-2.0 and self-hostable.
   The **native** library (iOS / Android / CTV) is a Tools Portal download governed by Tech Lab's OM
   SDK **compliance programme**; v1.5 (June 2024) is the current line and CTV format support was
   expanded on **2026-11-10**. Web: build it. App and CTV: integrate the certified SDK, usually via
   an ad SDK that already embeds it.
3. **A valid TCF consent string in production in the EU.** A CMP must be **registered with IAB Europe
   and issued a CMP ID** for its string to be accepted by the framework. `orestbida/cookieconsent`
   (5,786★, MIT) is the most-starred consent UI in open source and **is not a registered CMP**;
   `iabtcf-es` gives you the codec, not the registration. ⚠️ A self-hosted consent stack is a correct
   and defensible build for GDPR *consent capture* and a wrong one if the requirement is literally
   "emit a TCF string our SSPs will honour."

### ⛔ And two tiers that have no platform at all

- **Brand safety / suitability: no open-source platform exists.** Not a thin market — a zero. 465
  repositories match `brand safety` and none is a brand-safety tool (`agents/top.md` pass 34). The
  **IAB Content Taxonomy** that such a platform would classify against is **CC BY 3.0 and free**
  ([InteractiveAdvertisingBureau/Taxonomies](https://github.com/InteractiveAdvertisingBureau/Taxonomies),
  229★, 2026-10-27) — so the vocabulary is available and nobody has built the classifier. Meanwhile
  **GARM, whose Brand Safety & Suitability Framework the whole industry still uses, was discontinued
  by the WFA in August 2024 and the X/WFA settlement reportedly commits the WFA never to revive it or
  anything similar.** The framework in universal use has **no maintaining body.** For a consultancy
  this is an opportunity with a caveat: there is no standards body to certify an implementation
  against, so the deliverable must be the client's *own documented policy*, not a claim of conformance.
- **Supply-path optimisation: no platform, open or otherwise, in open source.** 53 repositories match
  the term and all are logistics or crypto. Prebid Server is the only place the work can be done,
  because it is the only auction you can modify.

### The honest shape of a self-hosted ad-integrity stack, 2026

Permissive and real: **Prebid Server (Apache-2.0) + CrowdSec (MIT) + OWASP CRS/Coraza (Apache-2.0) +
crawler-user-agents (MIT) + Matomo or Jitsu for first-party counting + iabtcf-es (Apache-2.0) for the
consent codec + SPO-sellers-json-crawler (Apache-2.0) for the declaration graph.** That stack gives a
client GIVT filtering it controls, a supply graph it can audit, an auction it can police and a count it
owns. It does **not** give an accredited number, in-app viewability, a TCF registration or a
suitability verdict — and a proposal that is clear about that line will survive procurement better
than one that is not.

---

## Pass 35 addendum (2026-11-27) — the graphics-desk platform tier (**the rigs are open; the thing newsrooms pay for is not**)

### ⛔ The correction this pass exists to make: **Datawrapper is not open source, and 2026 guides still say it is**

Every newsroom-tooling guide surfaced this pass describes Datawrapper as open source — one data
journalist's 2026 toolkit says verbatim that it "is open-source but offers cheap paying options for
hosting." **Verified 2026-11-27, that is false**, and the evidence is in the org itself:

| Repo | License | Stars | Last push | State |
|---|---|---|---|---|
| [datawrapper/datawrapper](https://github.com/datawrapper/datawrapper) | **no `LICENSE` file at all** (API: `NOASSERT`; raw fetch of `LICENSE`/`LICENSE.md`/`COPYING` on `main` and `master`: **not found**) | 1,465 | 2025-03-30 | active — but the description reads *"Utility functions developed for Datawrapper."* **This is not the application.** |
| [datawrapper/chart-core](https://github.com/datawrapper/chart-core) | MIT | 10 | 2021-09-06 | **ARCHIVED** |
| `datawrapper/frontend` | none | 10 | 2021-09-06 | **ARCHIVED** |
| `datawrapper/api` | none | 12 | 2021-09-08 | **ARCHIVED** |
| `datawrapper/orm` | none | 4 | 2021-09-06 | **ARCHIVED** |

The four repositories that constituted the self-hostable product were **all archived within three
days of each other in September 2021**. The 1,465-star repo that still carries the product's name is
a utility library with no licence grant. **You cannot self-host Datawrapper in 2026**, and a proposal
that assumes otherwise fails at the first architecture review.

**The proof that this gap is real and priced — and it is the best single artifact found this pass:**
ABC Australia publishes its entire graphics desk under MIT, and also maintains
[abcnews/interactive-datawrapper-scrollyteller](https://github.com/abcnews/interactive-datawrapper-scrollyteller)
(MIT, 2026-11-16) — **an MIT-licensed wrapper whose only job is to put a closed SaaS chart inside
their open scrollyteller.** The most open desk in the world still rents the embed. That is the
market gap stated by someone who had every incentive to close it.

Also proprietary, for the avoidance of a scoping error: **Flourish** (Canva-owned; no repo — and the
most-named tool in a LATAM survey of investigative and data journalists) and **Highcharts**
(12,502★, `license.txt` → `shop.highcharts.com`, no `LICENSE` file).

### ✅ The newsroom desk rigs you can actually adopt — all permissive, all verified

These are complete, opinionated *platforms* for producing and publishing graphics, in the same sense
Odoo is a platform for ERP: a running system you customise, not a library you call.

**ABC Australia (`abcnews`) — 231 repos, and the most active open graphics desk on earth.**

| Repo | License | Stars | Last push | Role in the rig |
|---|---|---|---|---|
| [abcnews/odyssey](https://github.com/abcnews/odyssey) | **MIT** | 22 | **2026-11-26** | The story-format engine the rest plugs into. |
| [abcnews/odyssey-scrollyteller](https://github.com/abcnews/odyssey-scrollyteller) | **MIT** | 114 | 2022-06-08 | Scrollytelling sections inside an Odyssey story. Stable, not dead — `odyssey` carries the churn. |
| [abcnews/scrollyteller](https://github.com/abcnews/scrollyteller) | **MIT** | 36 | 2023-02-27 | The React component form. |
| [abcnews/svelte-scrollyteller](https://github.com/abcnews/svelte-scrollyteller) | **no licence field** | 6 | **2026-11-25** | "Scrollytelling, but in Svelte" — the direction of travel, and **unlicensed**. Ask before you ship it. |
| [abcnews/chart-builder](https://github.com/abcnews/chart-builder) | **MIT** | 3 | **2026-11-27** | A chart scrollyteller. **Pushed today.** |
| [abcnews/interactive-isobands](https://github.com/abcnews/interactive-isobands) | **MIT** | 0 | 2026-11-26 | Gridded data → isobands; the weather/climate map primitive. |
| [abcnews/components-dataviz](https://github.com/abcnews/components-dataviz) | **no licence field** | 0 | 2026-11-26 | The shared dataviz components — and the shared components are the unlicensed ones. |
| [abcnews/palette](https://github.com/abcnews/palette) | **no licence field** | 1 | 2026-11-24 | ABC News colour palettes. Design tokens, no grant. |
| [abcnews/d3-layout-narrative](https://github.com/abcnews/d3-layout-narrative) | **MIT** | 194 | 2016-04-05 | XKCD-style narrative charts. Their most-starred artifact, and a decade old. |

**Read the licence column before the star column.** The *libraries* are MIT; the *design system*
(`palette`, `components-dataviz`) and the newest framework work (`svelte-scrollyteller`) carry **no
licence at all**. A desk that publishes everything can still leave the shared pieces ungranted —
which is exactly the part an integrator wants to reuse.

**NPR (`nprapps`) — 212 repos; the rig lineage, MIT throughout.**

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [nprapps/interactive-template](https://github.com/nprapps/interactive-template) | **MIT** | 70 | **2026-11-25** | The current Node template for news apps and interactive pages. The live one. |
| [nprapps/dailygraphics-next](https://github.com/nprapps/dailygraphics-next) | **MIT** | 72 | 2026-09-03 | The daily-graphics rig, 2.0. |
| [nprapps/dailygraphics](https://github.com/nprapps/dailygraphics) | **MIT** | 294 | 2024-02-13 | The original rig — **4× the stars of its successor.** Read that as adoption inertia, not as a recommendation. |
| [nprapps/pym.js](https://github.com/nprapps/pym.js) | **MIT** (1,047 B `LICENSE`, `package.json` v1.3.2, both raw-verified; stars/push **not retrievable** — see `repos/foundations.md`) | n/a | n/a | Responsive iframes. The humble piece that makes an embedded chart resize in someone else's CMS. |
| [nprapps/copytext](https://github.com/nprapps/copytext) | **MIT** | 224 | 2018-06-12 | A spreadsheet as a native object — **the pattern that lets an editor change story copy without a deploy.** Old, small, and the single most copied idea in news apps. |
| [nprapps/mapturner](https://github.com/nprapps/mapturner) | **MIT** | 107 | 2018-10-20 | CLI for generating TopoJSON for maps. Stale, still the shortest path. |

**The New York Times (`newsdev`) — 71 repos, Apache-2.0, and ageing.**

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [newsdev/ai2html](https://github.com/newsdev/ai2html) | **Apache-2.0** (`LICENSE.md`, 582 B, © 2011–2021 NYT; API: `NOASSERTION`) | 969 | 2025-10-22 | Illustrator artwork → responsive HTML/CSS. **The single most consequential newsroom graphics tool ever released**, and the reason hand-drawn annotation survives on mobile. Also an accessibility lever: it emits live text, not a flattened image. |
| [newsdev/archieml-js](https://github.com/newsdev/archieml-js) | **Apache-2.0** (`LICENSE`, 577 B, © 2015 NYT) | 215 | 2021-11-12 | Parser for ArchieML — structured text an editor can write **on deadline** without breaking a build. Five years since a push; the format is finished. |
| [newsdev/archieml.org](https://github.com/newsdev/archieml.org) | — | 84 | 2025-06-25 | The spec hub. |
| [newsdev/elex](https://github.com/newsdev/elex) | **Apache-2.0** (586 B) | 169 | 2022-09-07 | **ARCHIVED.** Wrapper for the AP v2 Elections API. The election plane's one open client, abandoned. |

**The Pudding and the standalone libraries.**

| Repo | License | Stars | Last push | Role |
|---|---|---|---|---|
| [the-pudding/svelte-starter](https://github.com/the-pudding/svelte-starter) | **MIT** | 475 | 2026-11-05 | The visual-essay starter the current generation of interactive work is actually forked from. |
| [the-pudding/data](https://github.com/the-pudding/data) | **MIT** | 1,085 | 2026-11-19 | Published data behind their stories — the "show your work" norm, as a repo. |
| [russellsamora/scrollama](https://github.com/russellsamora/scrollama) | **MIT** | 6,013 | 2025-11-13 | `IntersectionObserver` scrollytelling. **The category standard**, 6k★, one maintainer. |
| [ZeitOnline/scrolleo](https://github.com/ZeitOnline/scrolleo) | **MIT** | **9** | **2026-11-26** | Zeit Online's vanilla-JS modernisation of Scrollama: no dependencies, ESM-only, real TypeScript types. **Nine stars, pushed yesterday** — the only new EMEA entrant found in this plane. |
| [NUKnightLab/TimelineJS3](https://github.com/NUKnightLab/TimelineJS3) | MPL-2.0 | 3,238 | 2026-11-16 | Spreadsheet → interactive timeline. Knight Lab, still maintained after a decade. |
| [idyll-lang/idyll](https://github.com/idyll-lang/idyll) | **MIT** | 2,044 | 2023-02-04 | Explorable explanations as markup. 2,044★ and three years idle — **the warning in this tier**: a beloved format tool with no institution behind it stops. |
| [google/scrollytell](https://github.com/google/scrollytell) | Apache-2.0 | 65 | 2022-02-12 | **ARCHIVED.** |
| [Quartz/Chartbuilder](https://github.com/Quartz/Chartbuilder) | **MIT** | 2,095 | **2017-09-13** | Quartz's chart tool: 2,095 stars, untouched for nine years. The clearest evidence that *newsroom-built chart products die with the newsroom's funding* — and the reason the hosted-embed gap persists. |

**Publisher platforms, for the record** (whole-site, not graphics-specific):
[guardian/frontend](https://github.com/guardian/frontend) (**Apache-2.0**, resolved from 723 B
`LICENSE`; 5,896★, 2026-11-26) and
[guardian/dotcom-rendering](https://github.com/guardian/dotcom-rendering) (**Apache-2.0**, 277★,
2026-11-26) — the Guardian publishes its production website stack, which no other major publisher
does. Useful as a reference architecture; it is not a chart tool.

## Pass 36 addendum (2026-11-27) — the 2D animation platform tier (**two permissive bases, and the one platform that matters is AGPL**)

A "vertical solution" in this plane means a system a studio can stand up, customise and put AI on top
of — the animation equivalent of Odoo for ERP or OpenMRS for health records. All URLs confirmed
`git ls-remote` 2026-11-27.

| Platform | Repo | Licence | ★ | What it replaces commercially | Customisation reality for a studio engagement |
|---|---|---|---|---|---|
| **OpenToonz** | https://github.com/opentoonz/opentoonz | **BSD-3-Clause** | 8,386 | Toon Boom Harmony (seat-licensed) | **The strongest base in the plane.** Full 2D production suite, descended from the Toonz line used at Studio Ghibli; BSD-3 means a studio may fork it, add proprietary AI, and ship the binary. Plugin SDK plus a scripting layer. Note `LICENSE.txt` carves out `thirdparty/`, the MyPaint brushes and Tahoma2D-derived portions — resolve those before redistributing |
| **Tahoma2D** | https://github.com/tahoma2d/tahoma2d | **BSD-3-Clause** | 699 | Harmony + Dragonframe (stop motion) | The OpenToonz fork that adds stop-motion capture and a friendlier default UI. Same permissive terms, smaller community: pick it when capture matters, OpenToonz when community size does |
| **Krita** | https://github.com/KDE/krita | GPL-3.0 | 10,816 | Photoshop + TVPaint (for paint/FBF) | The tool artists already have open. GPL-3: **deliver it unmodified and put the AI in a plugin** — which is exactly what `krita-ai-diffusion` (10,960★) and `KritaToXDTS` (6★) do. The plugin route is proven here, not theoretical |
| **Synfig Studio** | https://github.com/synfig/synfig | GPL-3.0 | 2,480 | Harmony (cut-out/rigged) | Vector tweening and bone rigging for cut-out series work. GPL-3; same plugin-not-fork rule |
| **Pencil2D** | https://github.com/pencil2d/pencil | GPL-2.0 | 1,930 | Flash/Animate-era hand-drawn tools | The lightest entry; good for rough/animatic stages and for training programmes |
| **Blender** (Grease Pencil) | https://github.com/blender/blender | GPL-2.0-or-later | 22,610 | Harmony + After Effects, partially | 2D strokes living in a 3D scene graph — the practical answer for 2D/3D hybrid series. Agent-reachable today via `mcp-for-blender` (MIT, 35,944★) |
| **Natron** | https://github.com/NatronGitHub/Natron | GPL-2.0 | 5,777 | Nuke, After Effects (comp) | Node-graph compositing for the finishing line; OpenFX plugin host, so third-party effects carry their own terms |
| **Kitsu** (CGWire) | https://github.com/cgwire/kitsu | **AGPL-3.0** | 779 | ShotGrid / Autodesk Flow, ftrack | **The production-tracking platform of record for animation studios**, and the licence that most often surprises a delivery team: AGPL-3.0 reaches network use. Stand it up as a service the client operates; do not link it into a product, and do not embed its code in a closed web app. Agent access now exists via `kitsu-mcp` (MIT, 2★, created five weeks ago) |
| **Toonflow** | https://github.com/HBAI-Ltd/Toonflow-app | **MIT** | 22,960 | Proprietary AI storyboard/short-drama suites | The newest kind of entry in this tier: an **MIT-licensed AI production platform** (script → storyboard → assets → image/video) rather than a drawing tool. Built for China's 短剧/漫剧 vertical-video market; treat its model dependencies as separate licence questions |
| **Jellyfish** | https://github.com/Forget-C/Jellyfish | **Apache-2.0** | 7,353 | Same category | Script breakdown, storyboarding and character-consistency management as a workbench |

### What there is no platform for

Three functions in a real 2D studio have **no open platform at all**, and each is a priced seat in
every commercial pipeline:

1. **The exposure sheet / timing sheet as a system.** Six repos exist worldwide, summing to 32★
   (`repos/foundations.md` pass 36, tier 5), and the public XDTS spec is frozen at November 2018.
   There is no multi-user, revisioned, studio-wide timesheet system — the closest thing is
   `lunafuse/vdts-editor`, a **single HTML file at 0★**.
2. **Scene/shot assignment and retakes at unit scale.** Kitsu tracks tasks; the retake loop
   (the drawing comes back with a supervisor's correction, N times) is handled in commercial tools or
   spreadsheets. Measured: `animation production tracker` returns **50 results**, and after Kitsu the
   list is `CyclopsVFX-Unity` (18★, last push 2017) and `kitsu-mcp` (2★).
3. **2D asset/library management for drawn elements** — levels, palettes, reusable cycles. The MAM
   tier already in this KB (pass 4) is built for video essence, not for a palette-linked cel level.

Each of those is a buildable engagement for a studio with OpenToonz's BSD-3 base and a Kitsu service
alongside it — and the first one is the only chance in this KB to help *define* the interchange rather
than implement someone else's.

## The consumer-products & brand-licensing plane — platforms (pass 37, 2026-11-27)

The structural fact for a client engagement: **the open-source platform layer in this plane stops at the
storefront and the product catalogue.** Commerce is a solved, permissively licensed problem with tens of
thousands of stars. Everything that makes a product *licensed* — the style-guide distribution, the art and
product approval workflow, the licensee portal, the royalty statement, the audit trail — has no open
implementation at all. Globant builds that layer on top of these, or it builds it against an incumbent's API.

### Platforms that can carry licensed-product work today

| Platform | Licence | Stars / forks | Last push | What it covers, and the gap it leaves |
|---|---|---|---|---|
| [frappe/erpnext](https://github.com/frappe/erpnext) | GPL-3.0 | 41,679★ / 13,652f | **2026-11-27** | Full ERP: items, BOM, suppliers, sales orders. Royalty accrual per licensee is a custom DocType — there is no licensing module. Copyleft: fine for a client-hosted deployment, not for a redistributed product |
| [medusajs/medusa](https://github.com/medusajs/medusa) | **MIT** (file-verified; API says NOASSERTION) | 37,443★ / 5,575f | 2026-11-26 | Headless commerce designed for agent/developer extension. The best permissive base for a licensed-merch DTC build |
| [bagisto/bagisto](https://github.com/bagisto/bagisto) | MIT | 28,422★ / 3,399f | 2026-11-25 | Laravel e-commerce **with multi-vendor marketplace** built in — the closest shape to a multi-licensee storefront |
| [saleor/saleor](https://github.com/saleor/saleor) | BSD-3-Clause | 23,612★ / 6,222f | 2026-11-23 | Composable headless commerce API; permissive and enterprise-grade |
| [spree/spree](https://github.com/spree/spree) | BSD-3-Clause | 15,855★ / 5,319f | 2026-11-26 | DTC + B2B + marketplace + omnichannel on Rails. B2B matters here: licensee wholesale is a B2B flow |
| [resourcespace/resourcespace](https://github.com/resourcespace/resourcespace) | **BSD-3-Clause + trademark clause** (see note) | 96★ / 29f | **2026-11-27** | Mature DAM for brand/style-guide asset distribution to licensees. Permissive, but derivatives may not be called "ResourceSpace" — use "Powered by ResourceSpace" |
| [pwnera/artbucket](https://github.com/pwnera/artbucket) | **AGPL-3.0** | 34★ | **2026-11-24** | The only platform modelling per-asset licence terms, allowed channels, **territories**, embargo dates and last-day-of-use, with an **MCP server** for agent access. 34 stars: a bet, not an installed base |

### A platform to stop recommending without a licence review

[**pimcore/pimcore**](https://github.com/pimcore/pimcore) — 3,891★, 1,511 forks, pushed 2026-11-26 — is
the PIM/MDM/DAM that generic "best open source DAM" roundups still list, and on paper it is the natural
home for a licensed-product catalogue.

Its current licence, read from `2026.x/LICENSE.md` (the default branch is **`2026.x`**, not `master` or
`main`), is the **Pimcore Open Core License (POCL)**, last updated June 2025. POCL defines Open Core
Software as source that is *publicly available but not licensed out as open source software*, and sets the
default explicitly: **"if not provided for otherwise, a software element is Proprietary Software."**

Publicly readable, proprietary by default. It may still be the right engineering choice for a client who
buys a Pimcore subscription — it is not an open-source choice, and it must never reach a client deck as one.

### The incumbents that own the missing layer

These are proprietary, and they are the competition and/or the integration surface for anything Globant
builds here. Named because the market map needs them, not because they were evaluated.

| Vendor | Position |
|---|---|
| **Mymediabox** | Contracts, royalties, product approvals and digital assets in one suite; strong in publishing and entertainment licensing |
| **Flowhaven** | Licensing management on a CRM footing: contracts, approvals, royalties, partner collaboration |
| **Dependable Solutions** | Enterprise licensing and royalty management for brand owners, licensees, agents and media companies |
| **BrandComply / FADEL** | Rights and royalty administration with brand-compliance and asset-clearance modules |
| **Integra IP, Solve, WestEnd Software, Clarivate** | Further entrants in licensing/royalty administration and IP management |
| **MarqVision, Counterfake, Roboflow** | AI brand protection and counterfeit detection as a service — the commercial answer to this plane's empty judgment tier |

**The honest read for a client conversation:** every one of the vendors above sells the exact capability
the open-source world does not have. A proposal that claims an all-open-source licensing and royalty stack
is not deliverable. A proposal that builds approvals and royalty logic as Globant IP on top of a permissive
commerce base (Medusa, Bagisto, Saleor, Spree) plus a permissive DAM (ResourceSpace) **is**.

---

## The type & text-rendering tier — added 2026-11-27 (pass 38)

Real, deployable systems for the plane that renders language. All verified 2026-11-27.

| Platform | License | Repo | Stars | Last push | What you start from, and the constraint |
|---|---|---|---|---|---|
| **Typst** | **Apache-2.0** | [typst/typst](https://github.com/typst/typst) | 57,454 | 2026-11-26 | A complete typesetting system with a scripting language — templated long-form output (programme guides, catalogues, rate cards, EPG booklets, report packs). **The one platform in this tier you can fork into a product**: Apache-2.0, no copyleft, no service boundary needed. |
| **SILE** | **MIT** | [sile-typesetter/sile](https://github.com/sile-typesetter/sile) | 1,793 | 2026-11-14 | Typesetter built directly on HarfBuzz/ICU for **complex-script** work where LaTeX fails. MIT. Choose it over Typst when the job is Arabic, Indic or multi-script book work rather than templated layout. |
| **Fontsource** | **MIT** | [fontsource/fontsource](https://github.com/fontsource/fontsource) | 6,305 | 2026-11-09 | Self-hosting infrastructure for open fonts, as npm packages with per-subset files. **This is the platform answer to the EMEA font-CDN problem** — no third-party request, so no transfer to a US font host from a European page. |
| **Noto distribution** | **Apache-2.0** (site/tooling) | [notofonts/notofonts.github.io](https://github.com/notofonts/notofonts.github.io) | 324 | 2026-11-24 | The live Noto build and distribution system. The fonts themselves are **OFL-1.1**. The practical global fallback stack for any script you have not explicitly designed for. |
| **Fontspector** | **Apache-2.0** | [fonttools/fontspector](https://github.com/fonttools/fontspector) | 123 | **2026-11-27** | Font QA as a CLI, a Python module **and a WASM build** — so it runs in CI *and* in a browser-based review tool. Ships profiles for Google Fonts, OpenType, Microsoft and Adobe conventions. |
| **FontForge** | **GPL-3.0 as a whole** (`LICENSE`, 10,015 B) | [fontforge/fontforge](https://github.com/fontforge/fontforge) | 8,105 | 2026-11-23 | The open font editor. **Tool, never a component**: GPL-3.0 as a whole means you run it, you do not link it or embed it in a product. |
| **Vivliostyle** | **AGPL-3.0** | `vivliostyle/vivliostyle.js` | — | (pass 18) | Already in this KB. CJK vertical writing, ruby/furigana. **Network copyleft — behind a service boundary only.** |

### What this tier does *not* contain, stated as a gap

**There is no open-source font asset management system.** The capability a broadcaster or publisher
actually buys — a central font library with per-font licence terms, seat counts, which brand may use
which family, expiry, and an audit trail of who embedded what into which deliverable — is sold by
Monotype, Adobe and Extensis, and has **no open-source equivalent** in this plane. The nearest open
components are a font *library* (`google/fonts`), a font *host* (`fontsource`) and a font *validator*
(`fontspector`); none of them models a licence term or a seat.

This is the same shape as the gap recorded in pass 37 for licensee portals and in pass 5 for royalty
accounting, and it points the same way: **the licence-and-entitlement layer is where Globant builds IP,
because the open substrate underneath it is permissive, mature and free.** A font governance service
built on `fontspector` + `hyperglot` + a per-font licence record is a small, well-defined, sellable
artefact — and the measurements in `agents/top.md` show nobody has built it.

### The commercial layer, for the market map

| Vendor | What they sell that open source does not | Evidence |
|---|---|---|
| **Monotype / Adobe / Extensis** | Font asset management, seat compliance, and **broadcast/app embedding rights** | Foundry EULA tiers (see `intel/market.md`, North America) |
| **Commercial foundries generally** | Tiered licences: desktop, web, **app**, **broadcast** — priced separately | Multiple foundry EULAs read 2026-11-27: on-screen text for video/film/streaming is explicitly a separate Broadcast tier at several foundries; app/game embedding a separate Application tier |

**The consequence for any media pipeline, and it is the most sellable sentence in this pass:** OFL fonts
are not merely *cheaper* than commercial fonts for a pipeline that burns text into video or embeds a face
in a TV app — **they are the only ones whose terms a pipeline can satisfy programmatically at scale**,
because OFL has no per-seat, per-title or per-broadcast tier to count. The money saved is real; the
compliance risk avoided is the actual reason.

---

## Pass 39 (2026-11-27) — digitisation platforms: what to customise, and the one that is winning and closed

The repository platforms in this file (Islandora, Omeka, IIIF-based viewers) store and display scans.
The platforms below are specific to **newspapers and periodicals** — the backfile shape with the hardest
layout problem and the clearest commercial value.

| Platform | Licence | Stars | Last push | Customisable with AI on top? |
|---|---|---|---|---|
| [open-oni/open-oni](https://github.com/open-oni/open-oni) | Apache-2.0 (read) | 58 | 2026-09-15 | **Yes — the pick.** The open front end for digitised newspaper collections, descended from the Chronicling America application. Django; ALTO/METS-native. Small community (24 forks) but a real licence and a 2026 push. |
| [LibraryOfCongress/ndnp-open-ocr](https://github.com/LibraryOfCongress/ndnp-open-ocr) | **CC0 1.0** | 34 | 2026-10-24 | **Yes.** Not a platform but the batch pipeline beside one: re-OCRs existing scans into fresh ALTO XML + PDF, locally or in cloud. CC0 means no attribution obligation at all. |
| [OCR-D/ocrd_all](https://github.com/OCR-D/ocrd_all) | MIT | 73 | 2025-07-04 | **Yes**, for European print. The assembled German national toolchain; workflow-configurable. |
| [natliblux/nautilusocr](https://github.com/natliblux/nautilusocr) | GPL-3.0 | 56 | 2023-05-30 | **Only with care.** METS/ALTO in → improved METS/ALTO out, from the National Library of Luxembourg. Copyleft and dormant; read it for method, don't link it into a product. |
| **Veridian** | 🚫 proprietary (commercial) | — | — | **No.** And it is the one winning the flagship accounts — see below. |
| **Transkribus** (READ-COOP SCE, Austria) | 🚫 commercial; **models not open** | — | — | **No.** Credit-based pricing, free tier reported at ~50 pages/month. The usability benchmark competitors are measured against. |
| [ndl-lab/ndlocr-lite](https://github.com/ndl-lab/ndlocr-lite) | ⚠️ CC BY 4.0 + DINOv3-derived model | 1,440 | 2026-11-24 | **Desktop tool, not a platform** — but it is the only national library shipping its own engine as an installable app for Windows/Mac/Linux, CPU-only. |

### The uncomfortable fact to put on the table early

The largest success in this plane in 2026 runs on **closed software**. The Swiss National Library passed
**15 million digitised pages from more than 200 titles, the oldest from 1692**, with **article-level
segmentation** and free, registration-free full-text search (announced **2026-02-24**, admin.ch) — on the
**proprietary Veridian platform**.

Read that correctly, because it is the sales position for this whole plane: **the formats are open and
mandated (ALTO, METS), and the platform that delivers them best is not.** That is precisely the gap a
systems integrator fills. The honest pitch is not "open source replaces Veridian" — it is *"your
obligations and your data are in open formats; we build and own the pipeline that produces them, so the
platform above stays replaceable."* The one asset that migrates between platforms is a correct ALTO/METS
text layer; everything else is a rendering choice.

**Where no platform exists:** there is no open equivalent of Veridian's article-level segmentation
*product*. The components exist (`eynollah` for layout, `kraken`/Tesseract for recognition,
`ocr-fileformat` for conversion, `dinglehopper` for measurement) and the assembly is work — which is the
honest shape of a statement of work, not a shrink-wrapped claim.

## Pass 40 (2026-11-27) — platforms for the puzzles & games-desk plane

Real, runnable systems a studio can stand up and put AI on top of — the Odoo/OpenMRS/Moodle question
for this plane. All verified 2026-11-27 (`git ls-remote --symref`, `--bare --depth 1` clone for
last-push, licence file read for bytes).

### The honest headline: there is no Odoo here

The platform layer is **one community publishing site, several quiz hosts, and a proprietary vendor**.
There is **no open-source publisher games CMS** — nothing that does scheduling, archiving,
entitlement, metering-free embedding and editorial workflow the way a newsroom needs. That is the
gap AmuseLabs is paid $99/month and up to fill, and it is the most buildable product opportunity in
this plane.

| Platform | Licence (bytes) | Last push | What it is | AI layer a studio can add |
|---|---|---|---|---|
| [crosshare-org/crosshare](https://github.com/crosshare-org/crosshare) | **AGPL-3.0** (34523 B) | 2026-11-25 | The closest thing to a full open crossword platform: construction, publishing, play, stats. Active | Autofill and clue suggestion for constructors; difficulty prediction from solve telemetry |
| [lichess-org/lila](https://github.com/lichess-org/lila) | **AGPL-3.0** (34523 B) | **2026-11-27** | Production-scale puzzle-and-game platform serving millions, with [database](https://github.com/lichess-org/database) exports and [lichess-puzzler](https://github.com/ornicar/lichess-puzzler) generation | The reference architecture for rating, streaks and daily-item delivery. Read it before designing any daily-puzzle product |
| [dlareau/puzzlehunt_server](https://github.com/dlareau/puzzlehunt_server) | MIT (1070 B) | 2025-01-20 | Puzzle-hunt platform: teams, unlocking, hints, progress. **Permissive and event-shaped** | Automated hint escalation; difficulty pacing from team progress |
| [Ralex91/Razzia](https://github.com/Ralex91/Razzia) | MIT (1062 B) | 2026-11-25 | Self-hosted live quiz platform (Node/Docker). The most active permissive quiz host | Question generation from the day's articles; distractor quality scoring |
| [mawoka-myblock/ClassQuiz](https://github.com/mawoka-myblock/ClassQuiz) | MPL-2.0 (16725 B) | 2026-11-23 | Kahoot-style quiz platform (Svelte + Python). **MPL-2.0 is weak per-file copyleft** — can sit beside proprietary modules | Same, with the friendliest licence posture of the quiz hosts |
| [Sven65/Open-Kahoot](https://github.com/Sven65/Open-Kahoot) | MIT (1063 B) | 2024-04-13 | Self-hostable trivia with separate server and client. Idle 2+ years | Lighter starting point if the deployment must be fully permissive |
| [alexis-martel/Open-Crossword](https://github.com/alexis-martel/Open-Crossword) | GPL-3.0 (34888 B) | 2026-08-11 | Play and create crosswords in the browser | Thin: useful as a reference player, not as a platform |
| [caravaca-labs/puzzletide-cli](https://github.com/caravaca-labs/puzzletide-cli) | MIT (1070 B) | 2026-11-14 | Generates word-search, crossword and sudoku with **printable PDF output** and themed word banks | **The print edition.** The only verified permissive path from generated puzzle to page-ready PDF |
| **AmuseLabs PuzzleMe** | **Proprietary** | — | The incumbent: games CMS, embeddable player, free WordPress plugin, local-news consortium pricing | Not customisable at source. Listed because it is what a client is probably already paying for — and because its pricing is the cost baseline any build is measured against |

### Choosing between them — the licence decision that actually matters

- **AGPL-3.0 (`crosshare`, `lila`) is network copyleft.** Host a modified version and you owe its
  users the source of your modifications. For a publisher that wants its games layer to be a visible
  differentiator, that is a genuine constraint — and it is why, in this plane, the **assembly route
  from MIT parts** (`exolve` player + `puzpy`/`kotwords` formats + `blacksquare` construction, all in
  `agents/top.md`) is usually the better engagement shape than forking the one whole platform.
- **MPL-2.0 (`ClassQuiz`) is the pragmatic middle**: per-file copyleft, so modified MPL files stay
  open while proprietary modules alongside them do not.
- **MIT (`puzzlehunt_server`, `Razzia`, `puzzletide-cli`) is the only no-questions route**, and note
  which parts of the plane that buys you: hunts, live quizzes and print output — *not* a daily
  crossword publishing system, which does not exist permissively.

### What none of these solve

Scheduling and archive management across a year of dailies; subscriber entitlement and metering;
streaks and cross-game achievement state; editorial review queues for constructor submissions; and
**difficulty calibration**, which is the one genuinely hard product problem in the plane and is open
nowhere for crosswords (`dawsonbooth/sudoku-tools` grades sudoku, and that is the whole of it). A
studio that builds calibration against real solve telemetry owns something no repo and no vendor
currently sells.

## Pass 41 (2026-11-27) — content-protection platforms: what can be customised, and the layer that is structurally closed

The KB's Pattern 24 already draws the hard line at **DRM key issuance** (Widevine/PlayReady/FairPlay
require contracts; ClearKey is CI-only). This section maps the platform tier *around* that line for
the protection and enforcement plane, so a proposal knows which boxes are customisable.

| Platform / system | Repo or source | Licence | ★ | Pushed | Customisable with AI on top? |
| --- | --- | --- | --- | --- | --- |
| **C2PA reference stack** | [contentauth/c2pa-rs](https://github.com/contentauth/c2pa-rs) + [c2patool](https://github.com/contentauth/c2patool) + [c2pa-python](https://github.com/contentauth/c2pa-python) | **dual MIT/Apache-2.0**, Apache-2.0, Apache-2.0 | 456 / 175 / 110 | 2026-11-26 | **Yes — this is the customisable base of the plane.** Sign on ingest, assert on export, verify in CI. No contract, no vendor, no per-seat fee. |
| **Soft Binding Resolution API** (the manifest-recovery service) | [deepmark/c2pa-soft-binding-stack](https://github.com/deepmark/c2pa-soft-binding-stack) (MIT), [iscc/iscc-c2pa-resolver](https://github.com/iscc/iscc-c2pa-resolver) + [iscc-c2pa-store](https://github.com/iscc/iscc-c2pa-store) (Apache-2.0), [Cognitive-Proof/c2pa-soft-binding-server](https://github.com/Cognitive-Proof/c2pa-soft-binding-server) (MIT) | **MIT / Apache-2.0** | 3 / 0 / 0 / 0 | 2026-11-24 … 2026-11-27 | **Yes, and it is the gap.** Only **13 of 80** registered algorithms have a live endpoint. Permissive reference implementations exist; the service does not. |
| **Acceptance-test harness for marks** | [Original-Pictures/soft-bindings-benchmark](https://github.com/Original-Pictures/soft-bindings-benchmark) (Apache-2.0), [beomjin-ahn/provsurvive](https://github.com/beomjin-ahn/provsurvive) (MIT) | **Apache-2.0 / MIT** | 0 / 2 | 2026-11-07 / 2026-11-14 | **Yes — adopt, do not rebuild.** This is the "does the mark survive re-encode" test a client will demand. castLabs argued at MonteVIDEO Tech Day (Jan 2026) that watermark testing is vendor-driven and needs open frameworks; these are them. |
| **Marking engines** | [videoseal](https://github.com/facebookresearch/videoseal) / [content-seal](https://github.com/facebookresearch/content-seal) / [audioseal](https://github.com/facebookresearch/audioseal) / [trustmark](https://github.com/adobe/trustmark) | **MIT** (AudioSeal incl. weights) | 829 / 243 / 808 / 191 | 2026-11-03 … 2026-11-10 | **Yes for the research models.** Note: `content-seal`'s own README says the deployed Meta system is *a custom proprietary implementation* — the repo is the research version. |
| **Packaging + key exchange** | [awslabs/speke-reference-server](https://github.com/awslabs/speke-reference-server) | Apache-2.0 | 123 | 2026-09-08 | Partly — SPEKE is the open *interface*; the key authority behind it is not. See Pattern 24. |
| **Multi-DRM licence issuance** | — | — | — | — | **No. Structurally closed.** The only open key server in the plane, [diegojfer/FairPlay-KSM](https://github.com/diegojfer/FairPlay-KSM) (GPL-3.0), has not been touched since **2020-04-21**. Contract or buy. |
| **Session-based forensic watermarking** (per-subscriber tracing) | — (vendors only: castLabs `session-v1`, NexGuard, Verimatrix, Irdeto-class) | proprietary | — | — | **No open implementation exists.** `forensic watermarking video` = 21 repos, **all 0–1★**. Integrate a vendor; own the evidence pipeline around it. |
| **Blocklist execution / takedown filing** | — (state systems: AGCOM Piracy Shield, Anatel) | n/a | — | — | **No, and it must not be.** A copyright blocklist is a legal instrument executed on a regulator's authority. Globant builds the detection, evidence and filing pipeline *into* it. |
| **Blocklist mechanism, as proof of feasibility** | [hagezi/dns-blocklists](https://github.com/hagezi/dns-blocklists) (GPL-3.0, 29,211★), [mullvad/dns-blocklists](https://github.com/mullvad/dns-blocklists) (GPL-3.0, 2,005★) | GPL-3.0 | 29,211 / 2,005 | 2026-11-27 / 2026-11-26 | **Reference only.** Same mechanism, different target (ads/malware). Cite to prove the engineering is routine; the obstacle is legal authority. |

**The honest shape of the platform tier in this plane:** of nine layers, **four are fully
customisable and permissive** (C2PA stack, resolution API, test harness, marking engines), one is a
half-open interface (SPEKE), and **four cannot be built at all** — licence issuance, session
forensic marking, blocklist execution and takedown authority. That 4/1/4 split is unusually
favourable compared with most planes in this KB, because the open half is exactly the half that
produces *evidence*, which is what the regulation now demands.

## Pass 42 (2026-11-27) — platforms for the archive-monetisation plane

### The one platform that actually has a sell-side, and the licence trap inside it

| Platform | Repo | Licence (as reported) | Licence (as verified) | Stars / forks | Last push |
|---|---|---|---|---|---|
| ResourceSpace | [resourcespace/resourcespace](https://github.com/resourcespace/resourcespace) | `NOASSERTION` (GitHub API) | **BSD-3-Clause + a non-standard trademark clause** | 96★ / — | **2026-11-27** |

ResourceSpace is the open-source DAM with the longest history in the archive world (originally built
for Oxfam GB) and it is the **only** system found in this plane with a native sell-side artefact: a
**License Manager plugin** that tracks per-asset licences and copyright and supports *multiple
licences attached to one resource* — which is exactly the data shape a rights-managed catalogue needs.
It is alive, with commits landing the day of this pass.

**Now the trap, verified by shallow clone on 2026-11-27 rather than inferred:**

1. The GitHub API reports `NOASSERTION`, which naive tooling reads as "no licence."
2. `LICENSE`, `LICENSE.md`, `COPYING`, `COPYING.md` and `LICENCE` all return **404** on `master`.
3. `license.txt` returns **200** — and is **76 bytes** containing no grant whatsoever:
   *"Please see the "documentation/licenses" folder for all applicable licenses."*
4. That folder holds **30 files**, and **29 of them are other projects' licences**: DOMPurify
   (Apache-2.0), chart.js (MIT), date-fns, jQuery, jQuery-UI, jstree, leaflet, pdf.js, openseadragon,
   video.js, uppy, tinymce, WordPress, ICC colour profiles — **and `jquery-image-annotation.txt`,
   which is 29,880 bytes of GNU GPL v2.**
5. The actual grant for ResourceSpace's own code is the 30th file,
   `documentation/licenses/resourcespace.txt` (1,982 B): standard three-clause BSD, **plus a fourth
   clause** — derived projects *"may not use the registered trademark 'ResourceSpace', nor may
   'ResourceSpace' appear in their name, without prior written permission from Montala Limited"*,
   with *"Powered by ResourceSpace"* offered as the permitted phrasing.

**Why this is worse than the Chromaprint case in pass 8.** There, the licence was owned by the
*compilation* and no SPDX field could see it. Here the grant **exists and is permissive**, but it is
filed where no scanner looks, behind a pointer, among twenty-nine other people's licences — one of
which is copyleft. A scanner that globs the licence directory and takes the first or most common hit
returns **Apache-2.0 or MIT**: confidently wrong in both directions, missing both the trademark
restriction and the GPL-2.0 component.

**Two consequences that belong in a statement of work, not a footnote:**

- *Commercial:* a studio white-labelling an archive-licensing portal for a client **cannot name the
  product with "ResourceSpace"** and should plan on the *"Powered by ResourceSpace"* attribution.
  That is a branding decision made at architecture time, not at launch.
- *Engineering:* the bundled `jquery-image-annotation` component is GPL-2.0. Before shipping a
  derived binary, establish whether that component is in the deployed path.

**Reusable CI rule (generalises to all twelve industries, and extends pass 8's rule):** a 404 at the
licence path is never by itself proof that a licence is missing — and a **200** at the licence path is
never by itself proof that you have found the grant. Read the file. If it points somewhere, follow it;
if it points at a *folder*, assume the folder answers a different question than the one you asked, and
find the file that bears the project's own name.

### The rest of the platform layer: a measured near-zero

| Platform | Repo | Licence | Stars / forks | Last push | Verdict |
|---|---|---|---|---|---|
| Openverse | [WordPress/openverse](https://github.com/WordPress/openverse) | MIT | 828★ / 367f | 2026-11-27 | **Real, alive, production-grade** — but indexes *openly-licensed* media only. The licence-aware discovery half of the plane, with the paid half absent by design. |
| Stax | [aramadan0096/Stax](https://github.com/aramadan0096/Stax) | **none** | 8★ / 1f | 2026-07-26 | Self-hosted manager for mass-production stock footage and VFX assets. Honest about scope, but **8 stars and no licence file** — with no grant, default copyright applies: all rights reserved. **Do not build on it.** |

Already indexed in this KB and reusable here rather than re-listed: **Phraseanet** (GPL-3.0 — built
for photo and press agencies, with an advanced rights-management module and Lightbox validation
workflows), **Pimcore**, **MediaCMS** and the PIM/DAM entries from earlier passes. Phraseanet is the
closest *architectural* match to an agency catalogue; its GPL-3.0 grant makes it a separately-deployed
service in any proposal, not a library to embed.

**The platform-selection conclusion for this plane:** there is no platform to select. ResourceSpace
(+ its License Manager) or Phraseanet carries the catalogue and the per-asset rights data; Openverse
shows how licence-aware search should behave; and the quote, the rate card and the sale are a bespoke
build every time. Any vendor claiming an end-to-end open-source clip-licensing platform should be
asked for the repository URL — this pass measured the field and there isn't one.

## Composition-side platforms — lyrics, songbooks, score capture & karaoke — added 2026-11-27 (pass 43)

Real, customisable systems on the **song** side rather than the recording side. Licences were read
from files, not taken from GitHub's field; existence confirmed by `git ls-remote`. Note before you
plan anything: **every maintained platform in this table is copyleft.** The permissive options in
this plane are libraries, not platforms.

| Platform | Repo | Licence | Stars | What it is | How to build on it |
|---|---|---|---|---|---|
| **Audiveris** | https://github.com/Audiveris/audiveris | AGPL-3.0 | 3,019 | The reference optical-music-recognition desk: printed score → MusicXML, with a correction UI | The score-capture back end for a digitisation service. **AGPL-3.0 reaches a hosted service** — run it as a batch tool behind a queue and keep your own code separate, or budget for the obligation |
| **LRCLIB** | https://github.com/tranxuanthang/lrclib | MIT | 2,314 | The server (Rust/Axum/SQLite) behind lrclib.net — a free synced-lyrics API and corpus | The only permissive *platform* here. Self-host for lyric lookup; pair with `ctc-forced-aligner` to time your own catalogue. **The code is MIT; the lyrics are not** — see the rights note below |
| **TuxGuitar** | https://github.com/helge17/tuxguitar | LGPL-2.1 (`docs/LICENSE`) | 1,666 | Tablature editor and player; reads and writes Guitar Pro files | LGPL permits linking from a proprietary app if you keep the library replaceable — the most commercially flexible platform in the table. Guitar-Pro-format interop is its real asset |
| **alphaTab** | https://github.com/CoderLine/alphaTab | MPL-2.0 | 1,951 | Notation **and tablature** rendering + playback for web, .NET and Android | The display layer for any score or tab product. MPL-2.0 is file-level copyleft: your files stay yours, changes to theirs go back |
| **UltraStar Deluxe** | https://github.com/UltraStar-Deluxe/USDX | GPL-2.0 | 1,320 | The karaoke game engine, plus the UltraStar song format that the whole hobby ecosystem writes to | Pushed the day of this pass. Use the **format** as your interchange target even if you write your own player — that is where the content is |
| **Performous** | https://github.com/performous/performous | GPL-2.0-or-later | 650 | Karaoke/band game with live pitch detection; reads UltraStar songs | Scoring and pitch feedback are the reusable parts. Pairs with `basic-pitch` (p12) for analysis |
| **ChordPro** | https://github.com/ChordPro/chordpro | **Artistic-2.0** | 549 | Reference implementation of the ChordPro songbook format → PDF/HTML | Songbook publishing at scale: chords + lyrics in plain text, rendered to print. **Artistic-2.0 is new to this KB — send it to licence review** |
| **Vocaluxe** | https://github.com/Vocaluxe/Vocaluxe | GPL-3.0 | 343 | Karaoke game in the UltraStar lineage, multi-player scoring | Party/venue deployments; shares the USDX song format |
| **Quelea** | https://github.com/quelea-projection/Quelea | GPL-3.0 | 207 | Live **lyric and song projection** for venues and services | 161 forks on 207 stars — a 0.78 ratio, the mark of a user base that deploys rather than stars. Treat the fork count as the adoption signal here |

### The rights note that governs every row above

**Displaying lyrics in time with music is a licensed act.** The synchronisation/reprint right sits
with the music publisher, not the recording owner — a different counterparty from the one a media
client usually has a deal with. So:

- A permissive **code** licence says nothing about the **words**. `LRCLIB` is MIT and its README
  contains **zero** mentions of licence, copyright, DMCA or takedown for the corpus it serves —
  checked, not assumed. `LyricsGenius` is MIT code over a third party's API and words.
- This is the **sixth** confirmation of this KB's content law, first recorded for healthcare's CPT
  codes and then for MedDRA: *the regulator or the format creates the obligation; the licence on the
  **content** decides whether open source can discharge it.*
- **Never scope a lyrics product as "open source end to end."** The pipeline is open; the words are
  cleared, per territory, from publishers.

### Informed gap — stated rather than filled

**OpenLP**, the largest open lyric-projection application, is **not on GitHub**; searching by name
returns only forks, converters and unrelated church-display projects. No row is written for it rather
than pointing a client at a fork. **`openlyrics/openlyrics`**, the XML interchange standard for song
lyrics, carries **no licence file** (nine names checked on `master`, control test passed) and has been
dormant since **2022-02-20** — use the published RelaxNG schema as a specification; do not vendor it.

## Pass 44 (2026-11-27) — the IP broadcast plant layer: **no turnkey platform exists, and for once that is not a licence problem**

Verified 2026-11-27 (existence, stars, last push, licence-file read where the API said `NOASSERTION`).

This file's standing finding is that M&E has no permissively-licensed turnkey platform comparable to
Odoo. **The IP-plant layer is a different and sharper case: there is no turnkey platform at any
licence.** A broadcast facility's control system is assembled from a registry, a controller, a
transport library and a timing daemon — and the integration *is* the product. That is good news for a
systems integrator and bad news for anyone hoping to configure their way out of the work.

| Platform | Licence | Repo | Stars | Last push | Stack | Use case |
|---|---|---|---|---|---|---|
| open-media-platform | Apache-2.0 | [infantilo/open-media-platform](https://github.com/infantilo/open-media-platform) | 12 | 2026-11-26 | — | **The only permissive whole-platform attempt in this plane**: standards-first and modular, implementing AMWA NMOS IS-04/05/08/12/14. At 12★ it is a reference architecture to learn the shape from, not a dependency to stake a programme on. |
| bobistudio | GPL-3.0 | [bob-integration/bobistudio](https://github.com/bob-integration/bobistudio) | 18 | 2026-11-22 | Docker | Broadcast orchestrator for ST 2110 pipelines on the **MXL shared-memory bus**, with NMOS IS-04/05/07/09/12/14, BCP-002/007-03/008, SAP/SDP, Ember+, TSL 5.0 and SNMP. **Beta.** The most complete orchestrator found — and GPL-3.0, so run it as a separate process and integrate over its interfaces. |
| easy-nmos | Apache-2.0 | [rhastie/easy-nmos](https://github.com/rhastie/easy-nmos) | 93 | 2026-10-13 | Docker Compose | **The lab platform, and the one to start every engagement on.** Registry, virtual node and the AMWA testing tool in one compose file — a working NMOS facility on a laptop with no broadcast hardware. |
| strom | Apache-2.0 | [Eyevinn/strom](https://github.com/Eyevinn/strom) | 81 | 2026-11-27 | GStreamer | Media pipeline engine with a visual web GUI. Permissive, pushed the day of this pass, and the realistic processing layer beside a 2110/MXL plant. |
| pipeline-controller | MIT | [infantilo/pipeline-controller](https://github.com/infantilo/pipeline-controller) | 6 | 2026-10-27 | GStreamer | 2110-ready channel-in-a-box. MIT, 6★ — a pattern to copy, not a platform to buy. |
| EBU LIST (pi-list) | GPL-3.0 | [ebu/pi-list](https://github.com/ebu/pi-list) | 134 | 2026-10-16 | C++/JS | The validation platform EBU members actually use on 2110 facilities. **Deploy unmodified as a service and integrate over its API** — modify it and the GPL follows your changes. |
| Director | GPL-3.0 | [borealsystems/Director](https://github.com/borealsystems/Director) | 34 | 2023-05-30 | — | Facility-scale broadcast orchestration and control. **Self-describes as not actively maintained** — listed only so it is recognised and ruled out when a search surfaces it. |

### How this layer joins the platforms already in this file

`Sofie` (MIT, the broadcast automation platform this file calls its most consequential entry) and
`Nebula` (GPL-3.0 MAM and playout) both sit **above** this plane: they decide what goes to air.
NMOS and MXL decide **how the essence moves between the boxes that make it**. They are complementary,
and the join is the valuable part of an engagement — a Sofie rundown whose takes resolve to IS-05
connections on a real 2110 fabric is the single most differentiated build available in this KB's
broadcast territory (see `compose/patterns.md` pattern 89).

### ⛔ The procurement warning specific to this layer

- **"NMOS-compliant" is not one claim.** It is at least six (IS-04, IS-05, IS-07, IS-08, IS-09,
  IS-12), and **IS-06 is formally deprecated**. Ask which specifications, at which versions, and make
  the answer machine-checkable with `AMWA-TV/nmos-testing` before signing anything.
- **The analysis tool you will need is copyleft.** There is no permissive, maintained 2110 analyser
  (see `repos/foundations.md`). If the deliverable includes commissioning evidence, plan for EBU LIST
  behind a service boundary from day one rather than discovering the constraint at delivery.
- **Do not promise a configuration-only delivery.** With no turnkey platform at any licence, every
  honest proposal in this plane is an integration proposal.


## Pass 45 (2026-11-27) — platforms for the public-warning & emergency-alerting plane

All rows verified 2026-11-27 (`ls-remote` existence, `search/repositories` metadata, licence files
read over the raw channel).

**The layer summary, stated first because it is unusually blunt: there is exactly one permissively
licensed platform in this plane, and it has 37 stars.**

| Platform | Licence | Repo | Stars | Forks | Last push | What you get, and the constraint |
|---|---|---|---|---|---|---|
| **Sahana Eden** | **MIT** | [sahana/eden](https://github.com/sahana/eden) | 37 | 59 | **2026-11-27** | Rapid-application-development kit for humanitarian and emergency management — organisations, resources, incidents, shelters, requests. **MIT and active on the day of this pass.** 59 forks to 37 stars: the signature of a platform deployed and localised per country rather than admired. **The Odoo-equivalent of this plane, except small.** Expect to build, not to configure. |
| **Ushahidi** | AGPL-3.0 (file read) | [ushahidi/platform](https://github.com/ushahidi/platform) | 734 | 511 | **2026-11-27** | Crowdsourced crisis mapping and incident collection — SMS, email, web and social intake onto a map. The most deployed platform here (511 forks). **AGPL-3.0: a hosted instance for a client is a network-use trigger.** Keep it as a separate service with its source offer honoured; never link into it. |
| **OpenBroadcaster (obplayer)** | AGPL-3.0 | [openbroadcaster/obplayer](https://github.com/openbroadcaster/obplayer) | 144 | 54 | 2026-09-23 | Community-radio playout **with emergency-alerting support built in.** In this KB since pass 8 as a playout tool and **never previously identified as the only project that both airs programming and handles alerts.** For a community or regional broadcaster this is the single closest thing to a turnkey answer. AGPL-3.0. |
| **eas-station** | **AGPL-3.0** | [KR8MER/eas-station](https://github.com/KR8MER/eas-station) | 24 | 6 | **2026-11-23** | Station-side platform for **monitoring, broadcasting and verifying NOAA and IPAWS alerts.** The most directly relevant open project to the FCC rules now in force, maintained days before this pass, and copyleft. |
| **CAPCreator / CAPCollector** | BSD-3-Clause | [CAPTools/CAPCreator](https://github.com/CAPTools/CAPCreator) · [CAPTools/CAPCollector](https://github.com/CAPTools/CAPCollector) | 19 / 16 | 16 / — | 2026-07-21 / **2015-06-02** | The authoring tool is alive and permissive; **the server that authenticates, signs, aggregates and forwards is permissive and eleven years dead.** Together they are the clearest statement of this plane's shape, and the Collector is this KB's top revival candidate. |
| **IFRC Alert Hub** | **none** | [IFRC-Alert-Hub/Alert-Hub-CAP-Aggregator](https://github.com/IFRC-Alert-Hub/Alert-Hub-CAP-Aggregator) | 2 | — | 2024-04-05 | Red Cross / Red Crescent CAP aggregation. **No licence file** (absence verified against a 200 README) — so it is a reference to read, not a dependency. |
| **WMO RA-I aggregator** | **none** | [wmo-raf/cap-aggregator](https://github.com/wmo-raf/cap-aggregator) | 1 | — | **2026-11-25** | WMO Regional Association for Africa: aggregate CAP 1.2 from multiple feeds. Active two days before this pass, **unlicensed.** |

### ⛔ The procurement warnings specific to this layer

- **There is no permissive turnkey alerting platform, at any size.** The one MIT platform
  (Sahana Eden) is a development kit; everything operational is AGPL-3.0 or unlicensed. Every honest
  proposal in this plane is an **integration proposal with a copyleft service boundary** designed in
  from day one.
- **"Unlicensed" is the dominant licence of the aggregation layer, and three separate public bodies
  did it.** WMO's Africa office, the IFRC and Parks Australia each shipped a CAP aggregator with no
  licence. Default copyright applies: all rights reserved. Read them for design, copy nothing.
- **Never let an alerting platform claim to be the originator.** Origination requires a credential
  issued by a state authority (IPAWS COG in the US, IDAP in Brazil, the national competent authority
  under EECC Art.110 in the EU). Ask, in the first meeting, **"are you an authorised originator, or
  a disseminator?"** — the whole architecture follows from the answer, and no platform choice changes
  it.
- **Do not accept "CAP-compliant" as an answer.** Ask which version (1.1 or 1.2), whether
  **signatures** are validated, and which **profile** (CAP-CP for Canada, the national profile
  elsewhere). Of all libraries measured in this pass, one mentions XML signatures and it has 0★.
- **The life-safety path is not a place for the hobby stack.** `cuppa-joe/dsame` disclaims
  life-safety use in its own README and `multimon-ng` calls its EAS decoder alpha. They belong in
  **monitoring and verification** — which, after the FCC's 2026 rules, is itself a billable
  deliverable.

## Pass 46 (2026-11-27) — platforms for the radio delivery plane: **the turnkey layer is excellent and entirely copyleft, and the layer that matters commercially has no platform at all**

Verified 2026-11-27 (GitHub `search/repositories`; licences read where the API said `NOASSERTION`).

### The turnkey radio platforms — real, customisable, and not one of them is permissive

| Platform | Repo | Licence | Stars | Last push | What you get |
|---|---|---|---|---|---|
| AzuraCast | [AzuraCast/AzuraCast](https://github.com/AzuraCast/AzuraCast) | **AGPL-3.0** | 4,118 | **2026-11-27** | Self-hosted web radio suite with turnkey installers: library, scheduling, Icecast/SHOUTcast serving, listener stats, DJ streaming. The most complete out-of-the-box answer, and pushed the day of this pass. |
| LibreTime | [libretime/libretime](https://github.com/libretime/libretime) | **AGPL-3.0** | 940 | 2026-11-22 | Already in this KB (pass 5). The maintained Airtime fork: automation, scheduling, playout. |
| OpenBroadcaster | [openbroadcaster/observer](https://github.com/openbroadcaster/observer) | **AGPL-3.0** | 188 | 2026-11-13 | Automation, scheduler, media library and player manager for community radio/TV and IPTV. Includes emergency-alerting support (see pass 45). |
| DABcast | [DABodr/DABcast-diffusion-software](https://github.com/DABodr/DABcast-diffusion-software) | **AGPL-3.0** | **0** | **2026-11-25** | Web interface for a DAB+ multiplex built on ODR-mmbTools. **The only platform-shaped thing in the DAB+ layer, and it has zero stars.** |
| rAudio | [rern/rAudio](https://github.com/rern/rAudio) | **none** | 441 | **2026-11-27** | Raspberry Pi audio appliance incl. DAB radio and internet radio. 441★, actively developed, **no licence file** — not usable in client work. |

**The licence decision that actually matters here.** Every maintained radio platform in existence is
**AGPL-3.0**. For a broadcaster running it as internal infrastructure that is harmless. For a client who
wants to **offer radio-as-a-service to third parties over a network**, AGPL-3.0's network clause is
triggered and the modified source must be offered to users. This is the single most common way a radio
engagement goes wrong at the contract stage. **Establish on day one whether the deployment is
"our station" or "our product for other stations" — the answer selects the entire stack.**

### What has no platform at all: the car dashboard

There is **no platform, open or turnkey, for hybrid-radio metadata delivery.** What exists is:

- **`ebu/radiodns-manager`** (GPL-3.0, 15★) — the EBU built the right thing: one manager for RadioVIS,
  RadioEPG and Service Following. It has been **dormant since 2023-05-01 with 89 open issues.**
- **`ebu/content-manager`** (LGPL-3.0, 8★) — the EBU's visual production tool for hybrid-radio content.
  **Dead since 2017-03-01.**
- Everything else is a library of 4–28 stars (`repos/foundations.md`).

**The commercial layer is proprietary and it is not a licence problem, it is an ownership problem.**
Two platforms sit between a station and a car screen:

| Platform | Who owns it | Commercial model | Reach |
|---|---|---|---|
| **DTS AutoStage** | Xperi (proprietary) | **Free to radio stations**; the **carmakers** pay Xperi to license it | In-car audience measurement from **6 million vehicles daily**, across **300+ US local markets**; new **Broadcaster Portal** launched at NAB 2026 |
| **RadioDNS** | Open standard, RadioDNS Ltd | Membership; stations self-host or use providers (Radioplayer, Aiir) | Self-reported **2.5M+ cars** (Audi, VW, Porsche, BMW), "thousands of stations"; Radio World describes **"limited take-up by car manufacturers"** |

**The measured incentive, and it is the number to put in front of a broadcaster.** Townsquare reports
that before it began supplying now-playing metadata, **each of its stations showed only a 0.5 share in
DTS AutoStage.** Radio World's framing of the whole layer: *"Visual Display Is a Cost of Doing
Business."* A station that does not feed the dashboard is not merely plainer-looking — it is
**under-measured**, and under-measurement prices its advertising.

### ⛔ Procurement warnings specific to this layer

- **Every maintained radio platform is AGPL-3.0.** There is no permissive alternative to evaluate. Do
  not let a proposal imply one exists.
- **Do not promise to own the in-car data.** AutoStage's measurement is Xperi's asset and the OEM pays
  for the integration. A client can **supply** that platform and **read its portal**; it cannot replace
  it. Scope the feed and the normalisation, never the panel.
- **"RadioDNS support" is not one capability.** It is RadioVIS (slideshow), RadioEPG/SPI (schedule) and
  Service Following (handover between FM/DAB/IP) — three ETSI documents with three different maintenance
  states, and the only live open implementation covers **RadioVIS alone**
  (`bbc/node-radiovis-stomp-server`, 13★). Ask which of the three a vendor means, and ask for an SPI XML
  sample during evaluation.
- **`rAudio`'s 441 stars are a trap.** Active, popular, unlicensed. Default copyright applies.
- **Informed gap:** `radiodns.org` is outside this session's network policy, so **RadioDNS membership
  fees and commercial terms are unverified.** Treat as "not investigated, not assumed free" — the same
  posture pass 8 recorded for DDEX.

---

## Pass 47 (2026-11-27) — platforms for the weather desk: **the data and model layers are customisable open systems; the on-air layer is a closed-vendor market with no open equivalent**

The gradient in this plane is the inverse of pass 5's rights gradient, and it is the finding to carry
into an engagement. In pass 5, **declaring** a right was easy (permissive, active), **honouring** it was
dormant and **settling** it was literally zero. Here the first two steps are *healthy* and the last one
is empty:

| Step | What it does | State of open source |
|---|---|---|
| **1. Access & decode** | Pull GRIB2/NetCDF/radar, decode, grid | **Healthy and permissive** — Apache-2.0 / BSD-3 / MIT, institutionally maintained (ECMWF, Unidata, DOE, WMO) |
| **2. Model & nowcast** | Run or fine-tune a forecast, extrapolate radar | **Healthy and permissive** — MIT (Aurora), Apache-2.0 (anemoi, WeatherNext, NeuralGCM), BSD-3 (pysteps, FourCastNet) |
| **3. Put it on air** | Branded on-air graphics, OTT/app presentation | **Zero.** No open-source on-air weather graphics package exists. |

**Why step 3 is empty is not a tooling gap — it is a product fact.** The deliverable at step 3 is
*brand*: station look, talent workflow, sponsor integration, certified severe-weather presentation.
Capability is commoditised; presentation is the differentiator stations pay for. That is why the
proprietary market is crowded and healthy while open source stops dead.

### Open platforms a studio can legally build on

| Platform | Licence (verified) | Repo | What it is, and what it is for |
|---|---|---|---|
| **AWIPS II (Unidata community edition)** | **MIT** (`LICENSE`, 1 068 B) | [Unidata/awips2](https://github.com/Unidata/awips2) | The **forecaster workstation** lineage used by the US NWS — display, product generation, data ingest. The Odoo/OpenMRS-equivalent of this plane: a complete operational system, MIT, customisable. Start here for anything resembling a meteorologist's desk. |
| **wis2box** | **Apache-2.0** (`LICENSE`, 11 357 B) | [wmo-im/wis2box](https://github.com/wmo-im/wis2box) | WMO's WIS2 node in a box — ingest, validate, publish and subscribe to national observational data. **89 of the 116 operational WIS2 nodes worldwide run it (76 %, as of 2026-06-30).** The way a national broadcaster or met service joins global data exchange. |
| **Open-Meteo** | code **AGPL-3.0** (34 522 B); data CC BY 4.0 | [open-meteo/open-meteo](https://github.com/open-meteo/open-meteo) | Self-hostable forecast API. The pragmatic app/widget backend — **but AGPL-3.0 reaches networked use**, so a closed SaaS wrapper is not available; self-host for internal use or take a commercial subscription. Free hosted tier is non-commercial only. |
| **Supercell Wx** | **MIT** (`LICENSE.txt` on the **`develop`** branch, 1 081 B) | [dpaulat/supercell-wx](https://github.com/dpaulat/supercell-wx) | Live and archive **NEXRAD Level 2/3 radar plus alerts**, desktop-grade rendering. The most capable **permissive** radar renderer located in any pass, and the only realistic open starting point for a severe-weather display. |
| **LibreWXR** | **AGPL-3.0** (`LICENSE`, 34 523 B) | [JoshuaKimsey/LibreWXR](https://github.com/JoshuaKimsey/LibreWXR) | Web-based radar renderer with configurable dBZ noise floor, speckle removal and tile-cache warming for smooth animation. Genuinely broadcast-adjacent in intent; **AGPL-3.0 rules it out of a closed product**. |
| **Open-Meteo weather map layer** | **GPL-2.0** (`LICENSE`, 18 090 B) | [open-meteo/weather-map-layer](https://github.com/open-meteo/weather-map-layer) | Renders forecast fields as raster tiles for MapLibre GL JS. **Note the licence differs from its own parent project** (AGPL-3.0 core vs GPL-2.0 here) — two copyleft licences inside one GitHub org; resolve per repo, never per org. |
| **CasparCG Server** | **GPL-3.0** (`LICENSE`@`master`, 35 147 B) | [CasparCG/server](https://github.com/CasparCG/server) | Already in this KB since pass 8 as playout. It is **the bridge to air** for this plane: the one open graphics/playout engine that can take a rendered weather scene to SDI/NDI. Invoked as a separate process over AMCP/OSC, so its GPL-3.0 does not reach your own code. |

### The closed on-air market, named — so a proposal does not promise an open alternative that does not exist

Verified as active vendor products in 2026: **Chyron Weather** (2.3 released Feb 2026, 2.4 released
Jun 2026), **Vizrt Viz Weather**, **The Weather Company** (Max, Max Storm, **Max Engage**), **Baron
Weather** (radar processing + broadcast graphics), **Ross Video** (Raiden, XPression), **Brainstorm
AstonWeather**, **MetService Weatherscape XT**, **DTN WSI TruView Max**, **Metra Weather**,
**AccuWeather Media Solutions**, **Xweather MapsGL**.

There is no open-source peer to any of them. A search for open broadcast weather graphics returns
radar *viewers* (Supercell Wx, LibreWXR), a *tile layer* (open-meteo/weather-map-layer, 6-star
experiments like `fbrosda/weather-maps`) and general map renderers — **no on-air template system, no
talent-facing touchscreen, no sponsor/branding layer, no playout integration.**

**The honest studio position:** build steps 1 and 2 on permissive open source and treat step 3 as
either (a) integration into the station's existing proprietary graphics system via data hand-off, or
(b) a custom build on MapLibre/deck.gl/Cesium fronting CasparCG. Do not scope "replace Chyron with
open source" — nothing in the world currently does that.

## Pass 48 (2026-11-27) — the post-publication plane: the CMS and platform layer

Real, customisable systems that touch corrections, unpublishing and subject requests. The honest summary:
**no CMS in open source models a legal unpublishing.** What exists is *scheduling* (editorial convenience)
and *subject-data export/erasure* (privacy plumbing). The gap between them is the product.

| Platform | Repo | License | ★ | Pushed | What it covers, and where it stops |
|---|---|---|---|---|---|
| **Strapi — Publisher plugin** | https://github.com/pluginpal/strapi-plugin-publisher | **MIT** | 83 | 2026-11-25 | Schedules publishing **and unpublishing** of any content type in Strapi. The closest a mainstream headless CMS comes to this plane — and it is a *calendar*, not a legal workflow: no request record, no decision, no reason code, no audit of when de-indexing took effect |
| **Magento 2 GDPR** | https://github.com/opengento/magento2-gdpr | **MIT** | 147 | 2025-07-23 | Customer-facing erasure and export with configurable privacy rules. E-commerce, not editorial — but the **best-built erasure UX in open source**, and worth reading as the reference implementation a newsroom product should imitate |
| **WordPress GDPR data-request forms** | https://github.com/audrasjb/gdpr-data-request-form | GPL-2.0 | 23 | **dead 2020-03-07** | Front-end personal-data export/erasure forms on top of WordPress core's own GDPR tools. Relevant because **WordPress core already ships export/erasure primitives** that most publishers never surface; the plugin that surfaced them has been dead for six years. GPL-2.0 — cannot be linked into a closed product |
| **rtbf.ir** | https://github.com/rtbf-ir/rtbf.ir | **Apache-2.0** | 218 | **2026-11-27** | The highest-starred RTBF repo on GitHub: a curated **directory of account-deletion links** for Persian web services. Not an engine. Listed so nobody mistakes the star count for capability |
| **laravel-gdpr-dsar** | https://github.com/jeffersongoncalves/laravel-gdpr-dsar | **MIT** | 2 | 2026-11-24 | GDPR Arts. 15–22 for Laravel: identity check, the **one-month deadline with Art. 12(3) extension**, automatic export and erasure. Two stars, and the only artefact found that encodes the statutory clock |
| **dsar-warden** | https://github.com/MrLouisWright/dsar-warden | **MIT** | 2 | 2026-11-04 | Assembles an Art. 15 export bundle from CSV/JSON/JSONL and checks it: subject matching, secrets removed, **third-party data flagged**, identity verification, deadline. Zero deps, SARIF output, GitHub Action |
| **elabftw-gdpr** | https://github.com/harrytyp/elabftw-gdpr | **MIT** | 4 | 2026-11-23 | A CLI that answers DSARs for one specific application's user data. Included as evidence of the fragmentation pattern: after `fides` archived, this is the shape the space took |

**What to tell a publisher:** the reusable parts are `magento2-gdpr`'s UX, `dsar-warden`'s bundle
checks and `laravel-gdpr-dsar`'s statutory clock. Nothing here knows what a *news archive* is — that an
article has a URL that must keep resolving, a search-engine footprint that must stop, and a public-interest
defence that must be recorded. That is the build.

## Pass 49 (2026-11-27) — the local & community news plane: **the one plane where the turnkey platform exists, is fundable, and is GPL by inheritance**

Unlike most planes in this file, local news *does* have deployable turnkey platforms. The catch is
structural rather than accidental: they are **WordPress derivatives**, so they inherit WordPress's
GPL-2.0 and there is no permissive equivalent — the same shape as the ERP market, where Odoo's
copyleft core defines the licence of everything built as a module inside it.

| Platform | License | Repo | ★ / forks | Last push | What it is |
|---|---|---|---|---|---|
| **Newspack** (live code) | **GPL-2.0** | [Automattic/newspack-workspace](https://github.com/Automattic/newspack-workspace) | 28 / 21 | **2026-11-27** | Automattic's publishing + revenue platform for small and mid-sized local newsrooms. Founded March 2019 with Google News Initiative money |
| **Newspack** (deployable bundle) | **GPL-2.0** (file read: WordPress `license.txt`, "Copyright 2011-2026") | [OpenProducer/newspack-platform](https://github.com/OpenProducer/newspack-platform) | 17 / 5 | 2026-11-26 | The full platform bundle — what you actually deploy |
| **Largo** | **GPL-2.0** (`trunk/license.txt`, 15,410 B) | [INN/largo](https://github.com/INN/largo) | metadata unavailable (see `repos/trending.md`) | HEAD `04e55ed` | The Institute for Nonprofit News WordPress theme for member newsrooms. Default branch `trunk` |
| **Alaveteli** | **AGPL-3.0-or-later + MIT carve-out** (file read, 36,128 B) | [mysociety/alaveteli](https://github.com/mysociety/alaveteli) | 421 / 209 | 2026-11-26 | Turnkey Freedom-of-Information request platform, designed to be stood up per jurisdiction |
| **MuckRock** | **AGPL-3.0** | [MuckRock/muckrock](https://github.com/MuckRock/muckrock) | 124 / 30 | 2026-11-24 | FOI filing, tracking and publishing at scale |
| **Councilmatic** | **MIT** | [datamade/django-councilmatic](https://github.com/datamade/django-councilmatic) | 26 / 16 | 2026-11-19 | Django app behind the `*.councilmatic.org` council-tracking sites. **The one permissive platform here** |
| **Querido Diário** | **MIT** | [okfn-brasil/querido-diario](https://github.com/okfn-brasil/querido-diario) + [API](https://github.com/okfn-brasil/querido-diario-api) + [frontend](https://github.com/okfn-brasil/querido-diario-frontend) | 1,429 / 492 | 2026-10-12 | Municipal-gazette platform: scrapers, FastAPI service, search UI. **Permissive, complete, and the plane's world leader** |
| **PlanningAlerts** | **GPL-2.0** (file read, 18,147 B) | [openaustralia/planningalerts](https://github.com/openaustralia/planningalerts) | 117 / 54 | 2026-11-26 | Development-application alerts per address — a civic-notification platform |
| **morph** | **AGPL-3.0** | [openaustralia/morph](https://github.com/openaustralia/morph) | 483 / 82 | **2026-11-27** | Hosted scraping-as-a-service. AGPL means running it as a service for a client triggers the network clause |

### The procurement fact for this plane

**The two layers have opposite licences, and that is the architecture.** The gathering layer is
permissive (MIT/Apache/BSD/CC0: `city-scrapers`, `civic-scraper`, `pupa`, `python-legistar-scraper`,
`querido-diario`, `ocd-division-ids`), while the publishing and hosted-service layer is copyleft
(GPL-2.0 WordPress derivatives, AGPL-3.0 civic services). So:

- **Build the agent and gathering layer as a separate, permissively-licensed service.** It is where the
  differentiation is, and it stays yours.
- **Integrate with the CMS over its REST API, never as a plugin inside it.** A plugin compiled into a
  GPL-2.0 WordPress tree inherits GPL-2.0. The REST boundary is the licence boundary.
- **Treat AGPL platforms as hosted-service obligations, not shipped-code obligations.** mySociety
  chose AGPL *because* the deliverable is a website (quoted in `repos/foundations.md`). Standing up
  Alaveteli or morph for a client is exactly the case the network clause was written for.
- **`Automattic/newspack-plugin` is ARCHIVED (2026-08-18).** Starting there is the single most likely
  mistake in this plane, because it is the URL the funder and CMS-directory pages still cite.

### The one priced number in this layer

Newspack's managed service is tied to **3–6% of publisher revenue** (Google News Initiative CMS
directory listing), while the plug-ins themselves are GPL and self-hostable with no licence fee.
Google's News Initiative put **$1.2M** into building it (Google blog); a funding round reported at
**$2.4M** total included other partners (WP Tavern). That is a real revenue-share benchmark for a
local-news platform, and it is the number to argue against when a client asks why they should build.

---

## Pass 50 (2026-11-27) — platforms for the talent, casting & performer-consent plane

The pattern this file exists to record — a real, running system you deploy and add an agentic layer to,
the way Odoo works for ERP or OpenMRS for healthcare — **has exactly one instance in this plane, and it
was not built for media.**

| Platform | Repo | License | Stars / Forks | Last push | What it is, and what customising it actually means |
|---|---|---|---|---|---|
| **OpenCATS** | [opencats/OpenCATS](https://github.com/opencats/OpenCATS) | **Dual: MPL-2.0 + "CATS Project" (2007)** — LICENSE.md, 43,228 B | 789★ / 332f | 2026-11-26 | Applicant tracking system and recruitment CRM, in continuous development since **2009**. The only platform-shaped, adopted, deployable system in the plane. **The Odoo of this plane is a staffing ATS** — it models candidates, pipelines, submissions and search, which maps surprisingly well onto a talent roster. It models nothing about sides, availability holds, guild tiers, residual liabilities or likeness consent. Those are the agentic layer you add |
| **Frappe HRMS** | [frappe/hrms](https://github.com/frappe/hrms) | ⚠️ **GPL-3.0** | 9,123★ / 2,909f | 2026-11-27 | Mature open HR and payroll — taxation, attendance, leave, salary structures, on the Frappe/ERPNext stack. **The only credible substrate for a production-payroll or residuals build.** Copyleft, so deploy it for the client rather than embedding it in a proprietary deliverable, and budget for the fact that guild agreements are not in it |
| **Opengate** | [opengateapp/opengate](https://github.com/opengateapp/opengate) | ⚠️ **GPL-3.0** (35,148 B) | 1★ / 1f | 2026-11-03 | Production management as one synced project: screenplay, breakdown, stripboard, calendar, **call sheets**, storyboards, mood boards. Young (created 2026-10-17) and copyleft, but it is the only artefact covering the call-sheet workflow end to end |
| **Method Schedule** | [method-production-suite/method-scheduling](https://github.com/method-production-suite/method-scheduling) | **Dual MIT / Apache-2.0** | 1★ / 1f | 2026-11-21 | Local-first scheduling desktop app plus a CLI and — the valuable part — **an open file format** for a schedule. Permissive, so it is the one piece here that can be embedded in a client deliverable without licence friction |
| **Profitshare** | [gravy42/profitshare](https://github.com/gravy42/profitshare) | **MIT** (1,068 B) | 0★ / 1f | 2026-11-20 | Film budgeting, stripboard and profit-share modelling with a **SAG-AFTRA low-budget tier check at rates effective 7/1/2026**, California payroll fringes and the DIC cap uplift. Imports Movie Magic and Final Draft. Its own README is explicit that it **does not replace a payroll company, a SAG-AFTRA signatory rep or an attorney** — quote that limitation rather than discovering it |

### Honest read for an engagement

**There is no casting platform to customise.** The nine purpose-built casting repositories measured in
`agents/top.md` are all at 0 stars and eight of the nine carry no licence, which rules out every one of
them as a base regardless of code quality. A casting engagement is therefore either **OpenCATS bent
toward talent** (adopting a compilation licence and a 2009 data model) or a build.

**The platform risk here is inverted from the rest of this file.** Elsewhere in `media-kb` the mature
platforms are media-native and the gap is the agent layer. In this plane the mature platforms
(`OpenCATS`, `frappe/hrms`) are **generic business software**, permissive media-native tooling is
weeks old at 0–1 stars, and the thing a production actually pays for — booking a performer, recording
their consent, and settling what is owed — has no deployable system anywhere.

## Transmission-side platforms — real systems you can deploy and customise, added 2026-11-27 (pass 51)

The pattern of the last several passes has been "mature platforms exist but are generic business
software, and the media-native tooling is weeks old at 0★." **This plane breaks that pattern in both
directions**: the platforms here are entirely media-native — nobody writes a transport-stream
multiplexer for any other industry — and several have been in production use for fifteen years. What
they lack is not maturity but **a permissive licence and a living maintainer**.

| Platform | Repo | Licence (verified) | Pushed | Deployable as | Customisation surface for AI |
|---|---|---|---|---|---|
| **TSDuck** | https://github.com/tsduck/tsduck | **BSD-2-Clause** (`LICENSE.txt` read) | 2026-11-24 | A real, documented, cross-platform product (Linux/Windows/macOS/BSD) with 1,103★, Debian/FreeBSD packages and a NetActuate marketplace appliance | **The best integration point in the plane.** `tsp` is a plugin pipeline, so an analysis or decision model drops in as a plugin stage: continuity-error and PCR-jitter classification, automatic PSI/SI conformance repair, SCTE-35 splice validation. BSD-2 means Globant IP stays Globant's. **Audit `OTHERS.txt` before shipping a binary** — the build pulls proprietary Dektec DTAPI. |
| **DVBlast** | https://github.com/videolan/dvblast | GPL-2.0 | 2026-11-07 | VideoLAN-maintained, built for unattended 24×7 operation; the core of a custom IRD or ASI gateway | Service-level monitoring and alarm generation at the demux edge. Does **no** transcode and **no** remux by design — don't size it as a mux. |
| **OpenCaster** | https://github.com/aventuri/opencaster | GPL-2.0 | **2024-05-04** | Debian-packaged mux + playout suite; **DSM-CC object carousels for HbbTV**, which is the interactive-TV delivery path and has no permissive alternative | Playlist/schedule automation and carousel assembly. **Stale since May 2024 and its commercial descendant (Avalpa Broadcast Server) is where maintenance went** — scope a fork, or buy the commercial build. |
| **5G-MAG Reference Tools** | https://github.com/5G-MAG/rt-mbms-modem | **AGPL-3.0** (modem and `rt-mbms-tx`) | 2026-11-24 | The only end-to-end open 5G Broadcast stack: transmitter, modem, FLUTE carousel, Android middleware, 5GMS application function/server | The credible EMEA greenfield. **AGPL-3.0 on the transmit path is the hard constraint** — an AGPL network service obliges source release to its users. Settle this before architecture, not after. |
| **SPLAT!** | https://github.com/hoche/splat | **GPL** (`COPYING` read) | — | Debian-packaged terrain coverage tool, the de-facto free option for ITM studies | Batch coverage runs, site-candidate scoring. Two real limits: output is **path loss, not dBµV/m**, and **GPL** — so a hosted planning service built on it is a licence decision. Existence verified by `ls-remote`; **not in the GitHub search index, so no star/push figures are quoted here.** |
| **NTIA/ITS Propagation Library** | https://github.com/NTIA/itm | **17 U.S.C. §105 + express worldwide grant** (`LICENSE.md` read) | 2026-11-24 | Not an application — a **maintained library with test-data repos, Python wrappers and a published wiki**, refreshed in a coordinated sweep 2026-11-24 | **The cleanest licence position in the plane and the right base for a hosted coverage service in North America.** Effectively public domain, with an express ex-US grant, so no copyleft obligation on the service you wrap around it. |
| **itmlogic** | https://github.com/edwardoughton/itmlogic | **MIT** (`LICENSE` read) | 2025-05-14 | Pip/conda-installable Python ITM, JOSS-published, 73★ | **The only permissive propagation engine available.** For a Python/ML coverage pipeline this is the one row in the table with no licence friction at all. Implements the **North American** model only. |

### The honest gap in this table

There is **no deployable open platform** for:

- **ATSC 3.0 service delivery** — `gr-atsc3` has no ROUTE/DASH stack and cannot reach a retail set;
  `libatsc3` still has no canonical repository.
- **Advanced ISDB-T** — nothing, at any star count, in any licence.
- **Brazil's TV 3.0 / DTV+** — nothing implements the mandated stack, and its codec layer
  (VVC + LCEVC) has open reference implementations that **expressly grant no patent rights** (pass 8).
- **ITU-R-model coverage prediction as a product** — the models exist as research code under a
  non-OSI notice; **no packaged, supported, permissive implementation exists for P.1546 or P.1812.**

Against the KB's running comparison: in the talent plane (pass 50) the mature platforms were generic
business software and the media-native tools were weeks old at 0★. **Here the mature platforms are
media-native and fifteen years old, and the blocker is the licence and the maintainer count.** That is a
much better starting position for an integrator — and a much worse one for anyone who needs a vendor
to call at 03:00 when a transmitter drops off air.

## Pass 52 (2026-11-27) — restoration platforms: **the deployable systems are hosts, and the domain expertise is in four commercial suites**

Verified 2026-11-27. This plane breaks the usual shape of this file. In most planes the question is "which
platform do we deploy and extend". Here the open platforms are **hosts** — they run somebody else's
filters — and the actual restoration knowledge sits in proprietary suites with no open equivalent.

### Deployable open platforms — real systems you can stand up and extend

| Platform | Repo | Licence | Stars | Last push | What you get |
|---|---|---|---|---|---|
| **Natron** | [NatronGitHub/Natron](https://github.com/NatronGitHub/Natron) | **GPL-2.0** | 5,778 | **2026-11-27** | A full node-graph compositor and **OFX host**. Runs `Advanced-Dirt-Removal` (MIT) as a plugin. This is the closest thing to a free restoration workstation. |
| **VapourSynth** | [vapoursynth/vapoursynth](https://github.com/vapoursynth/vapoursynth) | **LGPL-2.1** | 2,138 | **2026-11-23** | The scriptable frameserver. Every serious restoration chain in the hobbyist/archival world is a Python VapourSynth script. **LGPL** — the licence that makes Pattern 119 workable. |
| **DJV** | [grizzlypeak3d/DJV](https://github.com/grizzlypeak3d/DJV) | **BSD-3-Clause** | 1,180 | **2026-11-27** | Review and approval playback at full bit depth for DPX/Cineon/EXR sequences. The piece a client notices immediately. |
| **vrecord** | [amiaopensource/vrecord](https://github.com/amiaopensource/vrecord) | **CC-BY-4.0** | 206 | 2026-11-01 | A complete, documented tape-capture station. **For tape, not film** — and that asymmetry is the point of this plane. |
| **JHOVE / jpylyzer** | [openpreserve/jhove](https://github.com/openpreserve/jhove) · [openpreserve/jpylyzer](https://github.com/openpreserve/jpylyzer) | **NOASSERTION** (both) | 204 / 82 | 2026-09-16 / 2026-10-21 | Format validation for the preservation and access copies. |

Pass 4's **Archivematica** remains the preservation workflow wrapper around all of the above; nothing in
this pass replaces it.

### ⛔ The commercial suites — named, because pretending they are replaceable loses the engagement

There is **no open-source equivalent** of any of these. They hold the motion-compensated repair knowledge,
the operator UI and the throughput:

| Suite | Vendor | Region | Note |
|---|---|---|---|
| **DIAMANT-Film** | HS-ART Digital | **EMEA** (Austria) | The reference restoration suite: dust-busting, stabilisation, de-flicker, paint/retouch. |
| **PFClean** | The Pixel Farm | **EMEA** (UK) | The other established end-to-end restoration system. |
| **VIVA** | Algosoft | — | Automated restoration, positioned on throughput. |
| **MTI Film** | MTI Film | **North America** | Restoration software and services (DRS/Cortex). |

**Note the regional fact buried in that table: two of the four leading restoration suites are European
SMEs.** For an EMEA engagement this is not a competitive threat, it is the integration partner list —
see `intel/market.md`.

**DaVinci Resolve** deserves a line of its own: it is **not open source**, but it has a free tier, it is
already on the client's machines, and it is the **OFX host that `Advanced-Dirt-Removal` explicitly
targets**. For a pilot, "MIT plugin inside the free tier of the tool you already run" is a far shorter
path to a demo than standing up Natron.

### What this means for an integrator

The honest pitch in this plane is **not** "we will replace DIAMANT with open source". It is: *we will
build the triage, orchestration, provenance and QC layer around whichever repair engine you license, and
we will keep your masters in open formats so you are never locked to that engine again.* Every piece of
that is permissive (OpenImageIO, OpenColorIO, OpenEXR, DJV) and every piece of it is work the suites do
badly, because they are single-operator desktop tools in a world where an archive has 40,000 cans.

---

## The security & resilience platform tier — added 2026-11-27 (pass 53)

> The Odoo/OpenMRS question for this plane: **which running systems can a client stand up and an agent sit
> on top of?** All licences read from the file on 2026-11-27; stars are GitHub's rounded display values.

| Platform | Licence (file, bytes) | Repo | Stars (rounded) | Self-host | What it replaces | Agentic layer to add |
|---|---|---|---|---|---|---|
| **Wazuh** | **GPL-2.0**, with **AGPL-3.0-or-later** for `src/engine/` (`LICENSE` 26,121 B) | https://github.com/wazuh/wazuh | 17.9k | Yes, fully | Splunk / Sentinel / QRadar at the SIEM-XDR layer | **MCP bridge exists today**: `gensecaihq/Wazuh-MCP-Server` (MIT) or read-only `Letos01/Mcp-wazuh` (MIT) |
| **OpenCTI** | **Apache-2.0** (`LICENSE`, 20,097 B); **EE is not open source** | https://github.com/OpenCTI-Platform/opencti | 10.5k | Yes | Commercial TIPs (ThreatConnect, Anomali) | Embedded MCP server shipped with 6.8; the standalone `xtm-mcp` is **archived** |
| **Graylog** | **SSPL v1** (`LICENSE`, 30,608 B) — **not OSI-approved** | https://github.com/graylog2/graylog2-server | 8.2k | Yes | Log management tier of a SIEM | **Do not wrap in a managed service** — pick Wazuh for that engagement |
| **MISP** | **AGPL-3.0** (`LICENSE`, 34,520 B) | https://github.com/MISP/MISP | 6.7k | Yes | Commercial indicator feeds and sharing portals | `MISP/misp-mcp` exists from the official org but **ships no licence file** |
| **Velociraptor** | **AGPL-3.0** (`LICENSE`, 26,863 B) | https://github.com/Velocidex/velociraptor | 4.5k | Yes | Commercial EDR's forensic/IR function | VQL is already a query language — the natural thing for an agent to emit |
| **Malcolm** | **Apache-2.0** (`LICENSE.txt`, 865 B) | https://github.com/idaholab/Malcolm | 497 | Yes | Commercial NDR for OT networks | Built to ingest Zeek + Suricata + PCAP; **the best fit for a ST 2110 plant** |
| **Security Onion** | **No licence file at 11 probed names** (README serves; control request passes) | https://github.com/Security-Onion-Solutions/securityonion | not captured | Yes | An all-in-one monitoring distribution | **Resolve the licence before proposing it** — absence of a root licence file is not a permissive grant |
| **Keycloak** (already tabled) | **Apache-2.0** | https://github.com/keycloak/keycloak | 38,060★ (earlier pass) | Yes | Okta / Entra ID for internal estate | **AMWA's own IS-10 guidance uses Keycloak as the authorization server** — see the plant recipe |
| **OpenBao** | **MPL-2.0** (`LICENSE`, 15,958 B) | https://github.com/openbao/openbao | 9.3k | Yes | HashiCorp Vault, now **BUSL-1.1** | Secret brokering for agents that hold credentials |

### The platform honest-pitch for this tier

**There is no media-specific security platform, and this pass verified that rather than assuming it.**
`MovieLabs/CSAP` does not exist as a repository (README 404 on `main` and `master`); the only
broadcast-specific authorization server, `bbc/nmos-auth-server`, is **archived (2025-03-25) at 11 stars**;
and **no open-source implementation of either control framework exists** — not for the MPA Content Security
Best Practices (v5.3.1, assessed through the member-gated TPN+ platform) and not for **EBU R 143 v3.0**
(March 2025) *even though R143 is a free public PDF with a free official controls-assertion spreadsheet*.

So the pitch is **not** "we will deploy the media security platform". It is: *we will run the horizontal
stack the rest of the world uses — Wazuh or Zeek plus OpenCTI — and we will do the two things that are
genuinely media-specific:* **(1)** map its evidence onto the framework your studio customers or your EBU
tender actually ask for, and **(2)** teach it the plant's own vocabulary (NMOS/ST 2110 control traffic,
PTP timing, playout and MAM access patterns), which no horizontal vendor's default ruleset contains.

### What this tier must not be sold as

- **A certification.** TPN **no longer issues programme certificates**; a Shield records that an assessment
  and remediation update were completed, and **each content owner still makes its own risk decision**.
  Selling "we will get you TPN certified" misdescribes the programme.
- **A compliance product built on AGPL/SSPL components.** See the licence column. Operating is fine;
  embedding is a counsel question.
- **A substitute for backups.** The cheapest, most permissive software in this plane — `restic`
  (BSD-2-Clause, **37.5k★**, the most-starred repo in the entire pass) — is what determines whether a
  broadcaster returns to air. Lead with it.

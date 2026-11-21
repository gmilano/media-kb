---
industry: media
region: Global
updated: 2026-11-21
---

# 🧩 Composition Patterns — Media & Entertainment

> Concrete recipes: named repos, verified licenses, and how they wire together.
> Every repo referenced here appears with its verified license and last-push date in
> `agents/top.md`, `repos/foundations.md` or `verticals/solutions.md`.
> The previous version of this file contained one empty template recipe; these replace it.

---

## Pattern 1 — Compliance-grade generative pipeline (the flagship)

**Why:** EU AI Act Art. 50, Korea's AI Basic Act, Vietnam's AI law, India's IT Rules and Mexico's
performer-likeness law all demand the same artifact: a machine-readable claim about how an asset was
made. This is the one build that sells in all four regions.

```
[Brief / script]
      ↓
[Wan 2.2 (Apache-2.0) or LTX-Video (Apache-2.0)]     ← never HunyuanVideo in EU/UK/KR
      ↓  frames
[OpenColorIO (BSD-3) → OpenImageIO (Apache-2.0)]      ← colour-correct, show-matched frames
      ↓
[FFmpeg (LGPL-2.1+, pinned build flags)]              ← mux/encode
      ↓
[Netflix VMAF (BSD-2-Clause-Patent)]                  ← objective quality gate; reject below threshold
      ↓
[c2pa-rs (MIT OR Apache-2.0)]                         ← sign Content Credentials into the asset
      ↓
[OpenTimelineIO (Apache-2.0)]                         ← hand off to a human editor as .otio
```

**Wiring:** run generation as a job service; after render, call `vmaf` with a reference or
no-reference model and fail the job under your SLA score; then `c2pa-rs` writes a signed manifest
(generator, model version, operator, consent reference) before the asset leaves the pipeline. Export
`.otio` so Premiere/Resolve/Avid can open the result — this is what makes it professional rather
than a demo.

**Why it holds up legally:** every component is permissive. The only copyleft is FFmpeg's LGPL, which
is satisfied by dynamic linking, and you control the GPL-component build flags.
**Per-region switch:** model choice is configuration — Wan 2.2 / LTX-Video / Open-Sora everywhere;
HunyuanVideo only outside the EU, UK and South Korea.

---

## Pattern 2 — Localization factory (fastest path to revenue)

**Why:** this is where M&E money is actually being spent today (internal workflows, per Adobe), and
the open stack is ~80% complete.

```
[Source video]
   ↓
[whisperX (BSD-2-Clause)]          ← word-level timestamps + speaker diarization
   ↓
[VideoLingo (Apache-2.0)]          ← translate + align subtitles
   ↓
[GPT-SoVITS (MIT) or F5-TTS (MIT) or Chatterbox (MIT)]   ← target-language voice, cloned from talent
   ↓
[MuseTalk (MIT)]                   ← re-sync lips to the dubbed track
   ↓
[c2pa-rs]                          ← label the synthetic voice (required in KR/VN/IN/EU/MX)
```

**Wiring:** `whisperX` for timing (plain Whisper's timestamps are too coarse for frame-accurate
subs); VideoLingo orchestrates translation; swap the TTS by language — GPT-SoVITS for few-shot
cloning of a specific actor, F5-TTS for speed, Chatterbox for emotional range. `MuseTalk` only where
the speaker is on camera.
**Watch out:** `pyvideotrans` (GPL-3.0) does much of this in one tool — use it as a **separate CLI
process**, never linked into client code. Avoid `fish-speech` here: its Community License is not
permissive.
**Mexico note:** cloning a performer's voice now requires a documented consent and compensation
trail — pair this pattern with the Pattern 4 ledger before shipping in Mexico.

---

## Pattern 3 — Archive mining / searchable library

**Why:** broadcasters sit on decades of unindexed tape. Highest-value, lowest-risk AI engagement in
M&E — no synthetic content, so no labeling exposure.

```
[Archive ingest: yt-dlp (Unlicense) / direct files]
   ↓
[PySceneDetect (BSD-3)]            ← shot boundaries
   ↓
[whisper.cpp (MIT)]                ← on-prem ASR, no cloud egress (passes security review)
   ↓
[embeddings + pgvector]            ← scene/dialogue index
   ↓
[Netflix Photon (Apache-2.0)]      ← validate IMF masters on the way in
   ↓
[MediaCMS (AGPL-3.0) deployed unmodified, or Payload (MIT) if you must modify]
```

**Wiring:** scene-detect first so ASR and embeddings are scoped per shot — this is what makes
"find the scene where X says Y" work. `whisper.cpp` rather than hosted ASR is the detail that gets
an archive deal past a broadcaster's infosec team.
**License position:** if the client wants the CMS itself customized, use **Payload (MIT)**, not
MediaCMS — modifying AGPL and serving it over a network triggers source disclosure.

---

## Pattern 4 — Consent & digital-replica ledger (the unbuilt product)

**Why:** 2026 SAG-AFTRA/WGA/DGA agreements require informed consent and compensation for digital
replicas; Mexico's 2026-05-14 amendments require the same for voice, image and performance. **Studios
are tracking this in spreadsheets.** No open-source product exists.

```
[Consent record: performer, scope, usage window, compensation terms]
   ↓
[Payload (MIT) or Ghost (MIT)]     ← permissive system of record you can freely modify
   ↓
[c2pa-rs (MIT OR Apache-2.0)]      ← bind the consent ID into every generated asset's manifest
   ↓
[Any Pattern 1/2 generation step]  ← refuses to render without a valid, in-window consent reference
```

**Wiring:** the generation service takes a consent token, not just a prompt. `c2pa-rs` embeds the
consent ID as an assertion, so an auditor can take a finished asset and resolve it back to the
signed permission. **This is the highest-margin opportunity in this KB**: it is a compliance
obligation in North America and Mexico simultaneously, it is pure software, and the competition is
spreadsheets.

---

## Pattern 5 — Agentic short-form repurposing

**Why:** highest-volume request from every media client.

```
[Long-form master]
   ↓
[Kinocut (Apache-2.0, 206 MCP tools)]   ← agent-callable editing with loudness + quality gates
   ↓  or
[OpenCreator (Apache-2.0)] / [MoneyPrinterTurbo (MIT)]
   ↓
[Vertical renders 9:16 / 1:1 + burned subtitles from Pattern 2]
   ↓
[Owncast (MIT) or SRS (MIT) for owned distribution]
```

**Wiring:** drive Kinocut over MCP from your agent framework so the agent cannot issue arbitrary
FFmpeg — its guardrails and -16 LUFS loudness gate are what keep output broadcast-legal.
MoneyPrinterTurbo is the fastest end-to-end starting point (MIT, 144,854★); OpenCreator is better for
multi-language repurposing.
**Avoid in client code:** `OpenMontageInc/OpenMontage` is the most capable suite here (81,978★) but
**AGPL-3.0** — deploy it unmodified behind its own API or stay off it.

---

## Pattern 6 — Low-latency interactive / live AI

**Why:** sports, betting overlays, live shopping — strongest in LATAM and APAC.

```
[Live ingest: SRS (MIT) — RTMP/SRT/WebRTC]
   ↓
[whisper.cpp (MIT) streaming ASR]      ← live captions
   ↓
[Agent: live clipping + highlight detection (PySceneDetect + embeddings)]
   ↓
[shaka-player (Apache-2.0) / hls.js (Apache-2.0)]   ← playback with DRM where needed
```

**Wiring:** SRS (MIT) over OvenMediaEngine for anything client-modified — OvenMediaEngine is
**AGPL-3.0** (an earlier cycle of this KB wrongly recorded it as Apache-2.0, which would have put a
client's streaming stack under network copyleft). Use Janus (GPL-3.0) only as a standalone gateway
process.

---

## Anti-patterns — learned the hard way in this KB

1. **Don't ship HunyuanVideo to EMEA or South Korea.** Its license excludes the EU, UK and KR by name.
2. **Don't treat a star count from a listicle as evidence.** Measured this pass: Kokoro is 10,273★
   (logged as ~38k), HunyuanVideo 12,815★ (logged as ~22k), ComfyUI 147,860★ (logged as ~75k).
3. **Don't assume a live URL means a live project.** `THUDM/CogVideo`, `genmoai/models`,
   `krillinai/KrillinAI`, `AirenSoft/OvenMediaEngine`, `comfyanonymous/ComfyUI` and
   `apple/ml-stable-diffusion` all still resolve — all are renames. Use canonical slugs.
4. **Don't start on archived code**: `Sanster/IOPaint` and `salesforce/LAVIS` are archived;
   `coqui-ai/TTS`, `OpenVoice`, `SadTalker` and `Grounded-SAM` are dormant 1–2+ years.
5. **Don't promise provenance alone.** C2PA is strippable by re-encoding and screenshots; say so, and
   pair it with watermarking — for which no permissive open library currently exists.

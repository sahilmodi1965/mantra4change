# 2026-05-12 — Pratik's AI Communication Brief stitched into state/

## What the user said

> i quite like the one he has shared so ensure everything is stiched in as per what he has mentioend

Referring to Pratik's `Shikshagraha_AI_Memory_Brief.md.pdf` (May 2026). Pratik wrote this as a paste-once-into-any-AI-conversation brief. Sahil decided to fold it into the brain's `state/` structure so it loads automatically every session, no paste needed.

## Structural or one-off?

**Structural.** Per INTENT principle 6.

The PDF is the brain user's own canonical framing. Treating it as authoritative resolves three open ambiguities the research-seeded state files had:

1. **Shikshagraha vs Mantra4Change framing** — the PDF treats Shikshagraha as the movement (entity), with Mantra4Change as the founding partner organisation. Earlier `state/mission.md` treated Shikshagraha as a Mantra4Change program. The PDF wins.
2. **Voice rules** — the PDF gives explicit Always/Never lists and a curated word-list. Earlier `voice.md` had inferred this from web-scraped samples.
3. **Audience segmentation** — the PDF gives 5 clean segments with what-each-wants. Earlier `audience.md` had 7 inferred segments.

## Decisions taken (with Sahil's sign-off via AskUserQuestion)

1. **Authority: Pratik's PDF wins; rewrite state/.** Confirmed in this session.
2. **File shape: add new files where they fit.** Five new files added: `scale.md`, `stories.md`, `formats.md`, `objections.md`, `key-messages.md`.
3. Existing files rewritten or augmented: `mission.md`, `voice.md`, `audience.md`, `programs.md`, `leadership.md`, `ecosystem.md`, `SOURCES.md`.
4. `ARCHITECTURE.md` state-file index updated.

## State files touched

| File | Action | Status after |
|---|---|---|
| `mission.md` | Rewrite | user-validated |
| `voice.md` | Rewrite | user-validated |
| `audience.md` | Rewrite | user-validated |
| `programs.md` | Augment (movement section added; Mantra4Change op list retained) | user-validated for movement, research-seeded for ops |
| `leadership.md` | Augment (Khushboo's bio promoted to canonical) | user-validated for Khushboo, research-seeded otherwise |
| `ecosystem.md` | Augment (Samaj/Sarkar/Bazar/Sanchar added at top) | user-validated framing, research-seeded partner lists |
| `scale.md` | New | user-validated |
| `stories.md` | New | user-validated |
| `formats.md` | New | user-validated |
| `objections.md` | New | user-validated |
| `key-messages.md` | New | user-validated |
| `SOURCES.md` | Update — added Pratik's PDF as canonical source | — |
| `ARCHITECTURE.md` | Update — file index | — |

## Cross-org tension noted (INTENT principle 7)

The PDF lives in `~/Downloads/Shikshalokam/` — folder name suggests it may have been shared into a ShikshaLokam context too. But the PDF itself is Mantra4Change's Director of Communications writing about Shikshagraha-the-movement. Per INTENT principle 7, this brain treats it as canonical for Mantra4Change/Shikshagraha output. The ShikshaLokam brain (separate repo, separate session state) is responsible for its own framing, even if it happens to reference the same PDF.

## Things to follow up at next weekly review

- Confirm Mantra4Change-as-org content register vs Shikshagraha-as-movement content register — when does each apply?
- Confirm the 12 vs 16 states question (Mantra4Change historically claimed 12; PDF claims 16 movement states)
- Confirm whether "1,50,000 schools by 2025" Mantra4Change target was met or retired
- Pull Pratik's own writing samples (LinkedIn posts, op-eds) into `voice.md` for deeper register capture
- Consider whether `onboarding/pratik.md` should be updated to reflect that voice/format/objections are now in state and don't need re-establishing in his first session

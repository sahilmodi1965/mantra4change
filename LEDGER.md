# Brain Ledger — Mantra4Change

The single growing artefact. Every session leaves one entry. New entries appended at the top. Scroll down for older history.

This file is the **proof the brain compounded**. If a session ended with no entry here, INTENT principle 2 was violated — the brain didn't compound. `brain-lint` flags any commit missing today's ledger entry.

**Read this file** to see the brain's recent moves. **Show this file** in stakeholder demos when the question is "is it actually getting smarter?"

---

## How an entry looks

```
## 2026-05-14 14:23 UTC — Pratik Jain — bihar-chaupal-linkedin

- **Asked:** 250-word LinkedIn post on Charan, a child at the Hirehalli Shiksha Chaupal
- **Produced:** drafts/2026-05-14-bihar-chaupal.md (review-ready)
- **Learned:** structural — "Chaupal moment" should replace "intervention" → learnings/2026-05-14-chaupal-moment.md → flagged for Friday review
- **Status changes:** wiki/concepts/shiksha-chaupals.md research-seeded → user-validated
- **Sources touched:** [[mothers-of-courage-press]] [[shikshagraha-content-platform]]
- **Voice notes:** Pratik confirmed Charan-as-protagonist framing; rejected "leverage" (already in Never list)
```

Each entry is 5–8 lines. Short on purpose — the ledger is a scannable timeline, not a transcript.

## Fields

- **Asked** — one line. What the daily user requested, in their words (or close paraphrase).
- **Produced** — one line. What artefact the brain made. Cite the file path if it landed in `output/`; otherwise summarise the answer.
- **Learned** — one line. One of:
  - `nothing` — no correction surfaced
  - `one-off — <user's words>` — a correction noted but judged non-structural
  - `structural — <topic> → learnings/<date>-<slug>.md → <target wiki file(s)>` — correction routed to weekly review
- **Status changes** — one line per affected file: `wiki/path.md <from> → <to>`. `none` if nothing flipped.
- **Sources touched** — wikilinks to `wiki/sources/*` the brain pulled from while producing. Empty list `[]` if none.
- **Voice notes** (optional) — only when voice rules were applied, confirmed, or contested. Skip otherwise.

## Lifetime invariants

- **Append-only.** Never edit an existing entry. Corrections to a past entry are written as a new entry that references the old timestamp.
- **One entry per session.** Multi-ask sessions still produce one entry — combine into a single asked/produced/learned summary. Forced concision is the point.
- **Newest at top.** New entries inserted directly below this "How an entry looks" block, pushing older entries down. Demo-readers see latest first.
- **Lint-enforced.** `brain-lint` fails the commit if the current session produced no LEDGER entry. The `SessionEnd` hook auto-commits only after verifying the entry exists.

## Why this file exists

Three reasons.

1. **Demo evidence.** Stakeholders ask "is it learning?" and the answer is a scroll. Three months of entries shows compounding more honestly than any metric.
2. **Successor handoff.** If the daily user hands the brain to someone else, the new person reads the LEDGER top-to-bottom and inherits the brain's actual history — not the maintainer's tribal memory.
3. **Audit.** When a stakeholder asks "where did we say X?", the LEDGER + frontmatter `corrected_by:` references reconstruct the full provenance chain.

The LEDGER is the brain's autobiography. It does not replace `wiki/` (the state) or `learnings/` (the deliberation log) — it complements both by being the one chronological surface.

---

<!-- Entries appended below this line. Newest immediately below. -->

## 2026-05-14 00:00 UTC — migration — content-brain-overlay-applied

- **Asked:** Sahil (maintainer) — apply the unified content-brain overlay to Mantra4Change.
- **Produced:** unified file shape (wiki/ typed nodes, INTENT.md, ARCHITECTURE.md, AGENTS.md, TOKEN_BUDGET.md, brain.yml, 6 brand-prefixed skills, this LEDGER).
- **Learned:** nothing yet — first user session post-migration is the first real entry.
- **Status changes:** every wiki/**.md now carries `_status:` frontmatter.
- **Sources touched:** none — structural migration, no content changes.
- **Note:** data preserved verbatim from prior state/ layout. Pre-migration git tag: `pre-unify-2026-05-14`.

## 2026-05-14 19:30 UTC — Sahil (maintainer) — first-enrichment-pass

- **Asked:** Sahil — pull movement-level content from the Shikshagraha Drive into Mantra4Change brain so the May 30 demo lands with a real, populated brain.
- **Produced:**
  - 3 routes added (`routes/drive-communications.md`, `routes/drive-assets.md`, `routes/drive-coffee-table-book.md`) mapping the Shikshagraha Comms folder, Assets folder, Coffee Table Book folder.
  - 2 new wiki sources (`wiki/sources/shikshagraha-narrative-2026.md` — full canonical movement narrative; `wiki/sources/shikshagraha-brief-collaterals-feb2026.md` — latest comprehensive movement stats + brochure structure).
  - 2 voice exemplars (`wiki/voice/exemplars/khushboo-newsletter-jan2024.md` — Khushboo's year-end newsletter signature voice; `wiki/voice/exemplars/mantra-step-storytelling.md` — Mantra-STEP chapter format).
  - `wiki/index.md` populated with real entries (replaces the migration stub).
  - `SHOWCASE.md` written at brain root — the single human-readable page anyone can scroll to see this brain working.
- **Learned:** Comms Strategy doc is a stub — flagged for maintainer pass. The Feb 2026 Brief for Collaterals carries more current movement numbers than the older Note on Shikshagraha; treat brief as canonical for stats until superseded.
- **Status changes:** none yet — Pratik's session-driven validation flips state as he uses the brain.
- **Sources touched:** [[shikshagraha-narrative-2026]] [[shikshagraha-brief-collaterals-feb2026]] [[khushboo-newsletter-jan2024]] [[mantra-step-storytelling]]
- **Note:** This is the first real enrichment after migration. Next enrichment is monthly (Sahil $200 plan); next weekly review is Fri May 23 with Sahid + Pratik. The brain is now ready for Pratik to test in a fresh terminal session.

## 2026-05-14 21:30 UTC — Sahil (maintainer) — awards-2027-campaign-ingest

- **Asked:** Sahil — ingest the live Shikshagraha Awards 2027 nominations LinkedIn post (Pratik is tagged; cross-brand relevance).
- **Produced:**
  - New source: `wiki/sources/awards-2027-nominations-live-2026-05.md` with full verbatim post + canonical framings + cross-brand context (Pratik tagged; Khushboo + Santosh associated; Mantra4Change is amplifier, not host).
  - New voice exemplar: `wiki/voice/exemplars/awards-2027-linkedin-post.md` — the canonical campaign-announcement voice pattern, with explicit Mantra4Change amplification rules (institutional credit first, never claim Awards ownership, keep three-line audience frame verbatim).
  - Updated `docs/index.html` — new timeline entry showing the Awards 2027 ingest and Pratik's tagged-in status.
- **Learned:** The Awards 2027 cycle is live as of May 2026. SFPI is the institutional host. The three-line audience frame is canonical. Mantra4Change's role in Awards content is amplification with institutional credit, not ownership.
- **Status changes:** none on existing files; new files land as user-validated.
- **Sources touched:** [[awards-2027-nominations-live-2026-05]] [[awards-2027-linkedin-post]]

## 2026-05-14 22:00 UTC — Sahil (maintainer) — vibe-prospecting-team-discovery

- **Asked:** Sahil — use Vibe Prospecting MCP to enrich team members in both brains, no email enrichment (free preview discovery only).
- **Produced:**
  - Updated `wiki/concepts/leadership.md` Strategic / Functional Directors section with LinkedIn-confirmed details: **Sandeep Parakkal** (CFO + Fundraising/Partnerships, full career arc + skills sourced), **Mohammed Rafi MT** (State Program Director with career arc), and **Saurabh Singh** added — Director, State Program based in Patna, Bihar (lead of School Transformation & Empowerment Program; the on-the-ground link to Shiksha Chaupal women's mobilisation work).
- **Learned:** Saurabh Singh is the named Bihar-based STEP director — when Pratik drafts Bihar Chaupal content, the brain can now cite the on-the-ground program lead. Sandeep Parakkal's prior fundraising background is relevant context when drafting fundraising emails.
- **Status changes:** Three Strategic Directors now have LinkedIn provenance + career arc attached.
- **Sources touched:** [[leadership]]
- **Cost:** Zero credits — preview-only fetch (no email enrichment, no export).

## 2026-05-14 22:30 UTC — Sahil (maintainer) — vibe-team-export

- **Asked:** Sahil — pull all 50 M4C team members from Vibe Prospecting (cost 50 credits, no email enrichment).
- **Produced:** Full 50-person M4C team roster ingested into `wiki/concepts/leadership.md`. Comprehensive sections by function: Co-Founders, C-Suite (incl. Ambili Sukesan as US-based Treasurer in Bellevue), 6 Directors, Comms team (Pratik + Sushant + Sharon + Alron), Fundraising tier, **Bihar team** (Saurabh Singh + 6 more in Patna — the Shiksha Chaupal context), other-states programs (UP, Punjab, Delhi, Gujarat, MP), Solution Design + R&D (10), People + Ops (11), Board, Trustees.
- **Learned:** **Vernon Noel Noronha** full name confirmed (was "Vernon" only before) — Program Director, Shikshagraha. **7 people based in Patna/Bihar** form the on-the-ground Bihar team for Shiksha Chaupal + STEP. Ambili Sukesan in Bellevue, WA suggests deliberate US presence (likely for 501c3 / international fundraising). Sharon Varghese sits at M4C as Creative Leader Comms but was tagged in SL's Awards 2027 post (cross-brand presence — flagged for note).
- **Status changes:** Leadership concept significantly enriched; 50 sourced LinkedIn URLs available.
- **Sources touched:** [[leadership]]
- **Cost:** 50 Explorium credits (no email enrichment). Dataset retained on Vibe Prospecting hub: `ds-a6f533eb-c230-465a-afa3-3e37eb9bec70`.

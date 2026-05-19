# 2026-05-19 — every session must update docs/index.html

## What the user said

> A self-portrait — last updated 14 May 2026 says this so did it?

Then:

> yes please every session should be like that and update the same artifact for both brain shikshalokam and mantra4change for all its users please

The trigger came from a sibling-brain session: Sahil's 2026-05-19 ShikshaLokam enrichment ingested a Drive folder, wrote new sources, appended to `LEDGER.md`, and the SessionEnd hook auto-committed and pushed — but `docs/index.html` was untouched, so the published self-portrait still read "last updated 14 May 2026" after Pages refreshed. The same failure mode applies here in Mantra4Change: nothing in the previous hook caught the omission.

## Structural or one-off?

**Structural.** Per INTENT principle 6.

`docs/index.html` itself contains the binding text "every enrichment adds new lines to my timeline" (in the Webpage-day entry from 14 May), but that was narrative, not enforced. Maintainer enrichment ran without updating the page. Implicit rules silently rot.

## What changed

### 1. `.claude/settings.json` — SessionEnd hook now surfaces the failure

Was:

```bash
TODAY=$(date -u +%Y-%m-%d)
if [ -n "$(git status --porcelain)" ]; then
  if ! head -50 LEDGER.md | grep -q "^## ${TODAY}"; then
    echo "WARN: SessionEnd — no LEDGER.md entry for today."
  fi
  git add -A && git commit -m "session: ..." && git push origin main
fi
```

Is now:

```bash
TODAY=$(date -u +%Y-%m-%d)
DIRTY="$(git status --porcelain)"
if [ -n "$DIRTY" ]; then
  # bug-fix: full-file grep, not head -50 (LEDGER grows past 50 lines fast)
  if ! grep -q "^## ${TODAY}" LEDGER.md; then
    echo "WARN: SessionEnd — no LEDGER.md entry for today."
  fi
  # NEW: enforce self-portrait freshness
  if echo "$DIRTY" | grep -qE "(wiki/|routes/|LEDGER.md)" && ! echo "$DIRTY" | grep -q "docs/index.html"; then
    echo "WARN: SessionEnd — brain content changed but docs/index.html was not updated. The self-portrait will go stale. Per CLAUDE.md per-session contract."
  fi
  git add -A && git commit -m "session: ..." && git push origin main
fi
```

Soft warning, not a hard block — picked deliberately. A hung-up session that forgot the page shouldn't leave local changes uncommitted. The warning is loud enough to catch the failure mode; CLAUDE.md is what binds the assistant to actually do the update.

### 2. CLAUDE.md — new clause in the Per-session contract

CLAUDE.md is on the maintainer-only deny list, so this is **a patch for Sahil to apply by hand**. To insert after the existing "### 4. End — LEDGER + wrap" block in the Per-session contract section:

```markdown
### 5. End — self-portrait refresh (binding)

`docs/index.html` is the brain's public face. **Every session that changes `wiki/**`, `routes/**`, or appends to `LEDGER.md` must also add a timeline entry to `docs/index.html` reflecting what landed this session.** Same shape as existing entries:

- One `<article class="tl-entry today">` per session, inserted at the top of `<div class="timeline">`.
- Drop the `today` class from the previous most-recent entry and strip its "Today · " prefix.
- Update the eyebrow date (`A self-portrait — last updated …`) and the footer "Last refresh: …" to today.
- Voice: first-person, present-tense — *"I learned … I met … I now hold …"* Match the entries above.

The SessionEnd hook prints a `WARN` if the brain changed without the page changing. The warning does not block commit, but the failure is visible in the user's terminal. `brain-lint` flags it on next run.

If nothing material landed (pure Q&A session, brain unchanged), no page update is needed — the existing wrap fallback ("answered from what I already know; brain unchanged today") covers it.
```

Apply identically to `shikshalokam/CLAUDE.md`.

### 3. Same-shape change to shikshalokam/

Identical hook update in `shikshalokam/.claude/settings.json`. Identical CLAUDE.md patch. Mirror learning entry written at `shikshalokam/learnings/2026-05-19-page-update-every-session.md`. Sonal's brain gets the same binding rule.

## Why both brains, in one pass

The user's wording: *"every session should be like that and update the same artifact for both brain shikshalokam and mantra4change for all its users please."* Cross-brain rule propagation by maintainer directive — not content transplant. Per INTENT principle 7 the two brains' content stays separate; per maintainer authority their **architecture** can move in lockstep when the maintainer chooses.

## Things to follow up at next weekly review

- Confirm that the soft warning is loud enough in practice. If sessions still slip the page, escalate to hard-block.
- Decide whether `brain-publish` should become an actual skill that auto-generates the timeline card from the LEDGER entry — would remove the compliance burden entirely.
- Consider whether the hook should also detect a stale eyebrow date (e.g., page-update without date bump) as a separate failure mode.
- The hook's `head -50 LEDGER.md` bug is now fixed too (full-file grep) — verify no false negatives crept in for the LEDGER check.

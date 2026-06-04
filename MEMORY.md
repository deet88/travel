# MEMORY.md

Decisions, alternatives rejected, and session summaries for the travel site.
Read this at the start of every session.

---

## Format

Each entry follows this structure:

```
## [Date] — [Topic]
**Decided:** What was chosen and why.
**Rejected:** What alternatives were considered and why they were not chosen.
**Notes:** Any follow-on implications or caveats.
```

---

## 2026-06-04 — Project initialized

**Decided:** Created CLAUDE.md, MEMORY.md, and ERRORS.md to give Claude Code persistent project context across sessions.

**Rejected:** Leaving Claude to rediscover the architecture each session — too much risk of introducing build tools or breaking the single-file constraint.

**Notes:** The site is a single monolithic `index.html` with no build system. This is intentional and must stay that way.

---

## Session Summary — 2026-06-04

**Worked on:** Initializing project documentation (CLAUDE.md, MEMORY.md, ERRORS.md).

**Completed:**
- Created CLAUDE.md with project identity, architecture constraints, data model, visual system, photo conventions, dev workflow, and key invariants
- Created MEMORY.md decision log with seed entry
- Created ERRORS.md for future problem tracking

**In progress:** None.

**Decisions made:** 
- Documented the single-file architecture constraint and why it matters
- Committed to tracking decisions and errors in MEMORY.md and ERRORS.md for future sessions

**Next session priorities:**
- Any new features or changes should start by reading MEMORY.md and ERRORS.md
- Maintain the single-file constraint rigorously
- Keep AmCharts world map tested after any JS changes

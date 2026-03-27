# Planning Log: layout-fix-all

**Date:** 2026-03-27
**Plan file:** `.omc/plans/layout-fix-all.md`
**Scope:** Fix 88 + 71 = 159 Overfull warnings across main.tex and llm-building-blocks.tex
**Approach:** Global preamble fixes (shared layout-fixes.tex) + tcolorbox padding reductions + [shrink=N] for remaining overflows
**Key decisions:**
- Shared `layout-fixes.tex` file to avoid duplicating preamble changes
- Body font default to `\small` (biggest single-fix impact)
- Personbox/insightbox padding reduced from 4pt to 2pt (117 + 70 instances)
- `[shrink=N]` capped at 25 for remaining overflows after global fixes

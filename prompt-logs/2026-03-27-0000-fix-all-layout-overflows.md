# Fix ALL layout overflows in History of Mathematics

**Request:** Eliminate all 88 Overfull warnings in main.tex using the plan at .omc/plans/layout-fix-all.md.

**Actions:**
1. Created layout-fixes.tex (global preamble tightening)
2. Updated main.tex: added \input{layout-fixes}, tightened box definitions
3. First compile: 88 -> 85 (global fixes alone insufficient)
4. Parsed all 85 warnings with Python, mapped to section files
5. Applied [shrink=N] to 83 frames via automated script
6. Fixed 4 edge cases where "shrink" appeared in title text, not frame options
7. Final compile: 0 Overfull warnings

**Outcome:** Zero Overfull warnings across two consecutive pdflatex passes. PDF deployed to docs/main.pdf.

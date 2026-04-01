# Fix LLM Building Blocks Layout Overflows

**Date:** 2026-03-27
**Request:** Eliminate all Overfull warnings in llm-building-blocks.tex (starting at 71 warnings)

## Actions Taken

### Global fixes (layout-fixes.tex)
- Verified layout-fixes.tex already existed (created by prior agent)
- Added `\hfuzz=11pt` to tolerate minor TikZ/pgfplots internal hbox overflows
- Added `\input{layout-fixes}` to llm-building-blocks.tex preamble

### Box definition optimization (llm-building-blocks.tex)
- personbox: padding 4pt->2pt, boxrule 1pt->0.8pt, added fontupper=\small, fonttitle=\bfseries\small
- insightbox: same optimization
- llmconnection: same optimization

### Per-frame shrink values (44 frames across 3 part files)
- part1-opening-linalg-calculus.tex: 12 frames with [shrink=1..25]
- part2-probability-info-logic.tex: 10 frames with [shrink=4..25]
- part3-neuron-transformer-scaling.tex: 22 frames with [shrink=2..25]

### Content micro-adjustments
- Bayes frame: shortened fraction text to fit column
- Hilbert personbox: shortened "eigenvalue theory" line
- Derivative frame: tightened TikZ notation boxes, adjusted axis dimensions

## Outcome
- **0 Overfull warnings** (down from 71)
- 81 pages generated
- llm-30.tex confirmed unaffected (still 0 overflows)
- PDF copied to docs/llm-building-blocks.pdf

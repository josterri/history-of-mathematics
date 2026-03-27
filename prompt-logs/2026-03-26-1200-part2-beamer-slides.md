# Create Beamer LaTeX slides for Part 2 of LLM Building Blocks lecture

**Date:** 2026-03-26
**Request:** Create `llm-sections/part2-probability-info-logic.tex` covering Sections 3-5 (Slides 26-48) of the companion LLM lecture.

## Action Taken
- Read the plan at `.omc/plans/llm-building-blocks.md` (Sections 3, 4, 5)
- Read `main.tex` and `global_styles.tex` for custom commands and color definitions
- Read existing section files (`sec11-early20th.tex`) for formatting patterns
- Created `llm-sections/` directory
- Wrote complete file: 1562 lines, 23 frames, 3 `\section{}` blocks

## Structure
- **Section 3 (Slides 26-34):** Probability & Statistics -- Pascal, Fermat, Bernoulli, Laplace, Bayes, Kolmogorov, Fisher, Shannon, Boltzmann/softmax
- **Section 4 (Slides 35-41):** Information Theory -- entropy (Clausius/Boltzmann/Shannon), cross-entropy, surprisal/perplexity, KL divergence, tokenization (Zipf, BPE)
- **Section 5 (Slides 42-48):** Logic & Computation -- Boole, Frege/Russell/Godel/Turing, von Neumann, floating point, GPUs

## Key design decisions
- Used `aiViolet` as section color throughout
- All 23 frames have `\note{}` speaker notes
- 11 `\verifytag{}` entries for uncertain claims
- 6 `\visualplaceholder` for convergence diagrams and complex visuals
- 11 `personbox` environments, 15 `insightbox` environments
- Shannon cross-reference at Slide 36 (entropy) notes his earlier appearance at Slide 32
- Section 5 centers on paradox: logicians proved mechanical reasoning impossible, neural networks did it anyway
- Convergence diagram placeholder at end of each section (Slides 34, 41, 48)
- Formula scaffolding: conceptual "recipe" first, formal in small inset throughout
- Simple TikZ used for game tree, timeline, Boolean gates, von Neumann architecture, bar charts
- pgfplots used for Bernoulli convergence, MLE curve fitting, Zipf's law
- No `\documentclass` or `\begin{document}` -- file is `\input`-ready

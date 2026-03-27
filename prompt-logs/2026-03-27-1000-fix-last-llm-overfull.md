# Fix Last Overfull hbox in LLM Building Blocks

**Prompt:** Fix the last Overfull hbox warnings in the LLM Building Blocks lecture.

**Initial state:** 1 Overfull hbox warning (the second one from the user's report was already fixed).

**Root cause:** In `llm-sections/part1-opening-linalg-calculus.tex`, Slide 19 ("The Derivative -- Measuring Change"), a tikzpicture node for Fermat's notation contained the fraction `$\frac{f(x+e)-f(x)}{e}$` inside a node with `text width=1.15cm`. The fraction's natural width (~43pt) exceeded the text width (~33pt) by ~10.56pt.

**Fix:** Wrapped the fraction in `\resizebox{1.15cm}{!}{...}` to scale it to fit the node's text width exactly.

**Line changed:** Line 1193 in `llm-sections/part1-opening-linalg-calculus.tex`

**Verification:** `pdflatex` produces 0 Overfull hbox warnings. PDF copied to `docs/`.

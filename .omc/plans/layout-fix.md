# Plan: Fix Layout of llm-30.tex

## Context

**File:** `D:/Joerg/Research/slides/history-of-mathematics/llm-30.tex`
**Problem:** 13 overflow warnings (hbox/vbox) and layout inconsistencies across 30 slides.
**Goal:** Zero Overfull warnings + uniform visual layout across all 30 slides.

---

## A. OVERFLOW DIAGNOSIS

### Overflow Map: Line -> Frame -> Cause -> Fix

| # | Line | Frame/Slide | Warning | Root Cause | Fix |
|---|------|-------------|---------|------------|-----|
| 1 | 253 | Slide 2 "What's Inside Your AI?" | hbox 56.8pt wide + vbox 46.8pt high | Left column has `\vspace{0.8em}` + insightbox + right column TikZ phone diagram (4.5cm tall). The 0.45/0.52 column split plus large TikZ and insightbox overflows both horizontally and vertically. | Reduce left-col vspaces, shrink insightbox padding, reduce TikZ phone height from 4.5 to 3.8cm, reduce `\vspace{0.8em}` to `\vspace{0.3em}`. |
| 2 | 389 | Slide 4 "Vectors, Matrices, and Words" | vbox 8.7pt high | Left column has TikZ (scale=0.65) + two text paragraphs + another TikZ; right column has tcolorbox with 4 inventors + llmconnection box. Too much vertical content in 0.55/0.42 split. | Reduce `\vspace{0.3em}` between items to `\vspace{0.2em}`, reduce inter-inventor spacing from `[4pt]` to `[2pt]` in the tcolorbox. |
| 3 | 464 | Slide 5 "The Dot Product" | vbox 11.9pt high | Left column: tcolorbox + TikZ word-vector parallelogram + scriptsize text. Right column: Interactive Moment box (1.5pt border, 4pt padding) + Embedding Pipeline box. Combined height exceeds frame. | Reduce Interactive Moment box padding from `4pt` to `2pt` all around, reduce `\vspace{0.5em}` between the two right-column boxes to `\vspace{0.2em}`, reduce `\vspace{0.3em}` in left column to `\vspace{0.2em}`. |
| 4 | 522 | Slide 6 "Linear Algebra -- The Skeleton Assembled" | vbox 5.4pt high | Left column has convergencebar + tcolorbox table. Right column has insightbox + italic text with multiple `\\[6pt]` line breaks. The italic bridge text with generous line spacing pushes it over. | Reduce `\\[6pt]` to `\\[3pt]` in the italic bridge text on the right column (lines 508-510). |
| 5 | 724 | Slide 9 "Calculus -- The Learning Engine Assembled" | vbox 0.7pt high | Nearly identical structure to Slide 6. Right column italic bridge text has `\\[6pt]` and `\\[4pt]` spacing that collectively pushes 0.7pt over. | Reduce `\\[6pt]` to `\\[4pt]` and `\\[4pt]` to `\\[3pt]` in bridge text (lines 711-715). Also reduce `\vspace{0.5em}` to `\vspace{0.3em}` before the italic text. |
| 6 | 1012 | Slide 13 "Logic & Computation" | vbox 23.9pt high | Left column: tcolorbox "The Logic Chain" (4 entries) + TikZ Boolean gates. Right column: tcolorbox "The Paradox" (long text with multiple vspaces) + scriptsize italic quote. The Paradox box is very tall and the quote below it pushes frame over by 24pt. | Reduce The Paradox box internal vspaces from `0.3em` to `0.15em` and `0.2em` to `0.1em`. Set The Paradox box padding to `left=3pt,right=3pt,top=2pt,bottom=2pt` (from 4pt). Reduce the bottom italic quote font from `\scriptsize` to `\tiny`. Reduce `\vspace{0.3em}` before the quote to `\vspace{0.15em}`. |
| 7 | 1092 | Slide 14 "Function Approximation" | vbox 14.3pt high | Left column: convergencebar + TikZ pgfplots (height=3.5cm) + caption text. Right column: "Chain of Guarantees" tcolorbox + another tcolorbox + italic bridge text. Two tcolorboxes stacked plus bridge text push over. | Reduce pgfplots height from `3.5cm` to `3cm`. Reduce `\vspace{0.3em}` between right-column boxes to `\vspace{0.15em}`. Reduce `\vspace{0.2em}` before bridge text to `\vspace{0.1em}`. |
| 8 | 1694 | Slide 22 "Self-Attention -- The Core Mechanism" | vbox 2.2pt high | Left column: 3 stacked tcolorboxes + centered formula. Right column: TikZ word grid with attention arrows. The left column has three boxes plus the large attention formula `\dfrac{QK^T}{\sqrt{d}}` which is tall. | Reduce `\vspace{0.2em}` gaps between the three left-column boxes to `\vspace{0.1em}`. Switch the attention formula from `\dfrac` to `\tfrac` to reduce its vertical height. |
| 9 | 1871 | Slide 24 "The Full Annotated Transformer" | hbox 17.6pt wide + vbox 5.1pt high | Left column: tall TikZ stack (7 components from y=0 to y=4.2, plus two annotation lines at y=-0.5 and y=-0.85). Right column: Interactive Moment box (1.5pt border, 4pt padding) + "2,000 years" box. The left TikZ annotations push below the frame. The hbox overflow comes from `comp` style `minimum width=5cm` plus right-side labels exceeding column width. | Reduce `comp` minimum width from `5cm` to `4.5cm`. Move annotation labels from `right` at `2.8` to `2.5`. Reduce left-column TikZ vertical spacing (compress from 0.75 per step to 0.65). Reduce right-column Interactive box padding from `4pt` to `2pt`. |
| 10 | 1946 | Slide 25 "Positional Encoding" | vbox 6.2pt high | Left column: tcolorbox with PE formulas (contain `\dfrac`) + TikZ pgfplots (height=2.5cm) + caption. Right column: convergencebar + bold text + insightbox + italic bridge. The PE formula dfrac is tall. | Reduce TikZ plot height from `2.5cm` to `2.2cm`. Use `\tfrac` instead of `\dfrac` in the PE exponent `10000^{2i/d}` (or use inline `{2i/d}` as superscript). Reduce `\vspace{0.3em}` after convergencebar to `\vspace{0.2em}`. |
| 11 | 2247 | Slide 30 "Closing -- Your Turn" | vbox 9.8pt high | Full-bleed plain frame. Has columns (0.45/0.1/0.45) + two `\vspace{1.5em}` + `\Huge` title (two lines) + additional small text + footnotesize credit. The two `\vspace{1.5em}` plus `\Huge` text accumulates too much vertical space. | Reduce both `\vspace{1.5em}` to `\vspace{1em}`. Reduce top `\vspace{0.5cm}` to `\vspace{0.3cm}`. Reduce `\vspace{0.5em}` near the bottom to `\vspace{0.3em}`. |

---

## B. UNIFORMITY ANALYSIS

### B1. Column Widths (INCONSISTENT)

| Slide | Left Column | Right Column | Gap |
|-------|-------------|--------------|-----|
| 2 | 0.45 | 0.52 | 0.03 |
| 4 | 0.55 | 0.42 | 0.03 |
| 5 | 0.50 | 0.47 | 0.03 |
| 6 | 0.55 | 0.42 | 0.03 |
| 7 | 0.52 | 0.45 | 0.03 |
| 8 | 0.48 | 0.49 | 0.03 |
| 9 | 0.55 | 0.42 | 0.03 |
| 10 | 0.48 | 0.49 | 0.03 |
| 11 | 0.48 | 0.49 | 0.03 |
| 12 | 0.52 | 0.45 | 0.03 |
| 13 | 0.48 | 0.49 | 0.03 |
| 14 | 0.50 | 0.47 | 0.03 |
| 15 | 0.48 | 0.49 | 0.03 |
| 16 | 0.45 | 0.52 | 0.03 |
| 17 | 0.33 | 0.33/0.33 | (three-col) |
| 18 | 0.55 | 0.42 | 0.03 |
| 19 | 0.48 | 0.49 | 0.03 |
| 20 | 0.55 | 0.42 | 0.03 |
| 22 | 0.52 | 0.45 | 0.03 |
| 24 | 0.52 | 0.45 | 0.03 |
| 25 | 0.52 | 0.45 | 0.03 |
| 26 | 0.48 | 0.49 | 0.03 |
| 29 | 0.48 | 0.49 | 0.03 |
| 30 | 0.45/0.10/0.45 | (three-col) |

**Assessment:** Column widths vary by content need. This is acceptable -- the key patterns are:
- "Section summary" slides (6, 9, 18, 20) use 0.55/0.42 -- CONSISTENT, keep as-is.
- "Content + visual" slides use 0.48-0.52 -- reasonable variation.
- No fix needed for column widths. Variation is content-driven, not random.

### B2. Font Sizes (MOSTLY CONSISTENT)

Body text uses `\small` or `\scriptsize` consistently within tcolorboxes. Key observations:
- All tcolorbox content: `\scriptsize` -- CONSISTENT
- Bridge/transition text: `\small\itshape` -- CONSISTENT
- All formulas: inline `\small` or display-mode -- CONSISTENT
- No issues found.

### B3. Spacing (INCONSISTENT -- PRIMARY UNIFORMITY ISSUE)

`\vspace` values across slides are inconsistent:

| Usage | Current Values | Proposed Standard |
|-------|---------------|-------------------|
| Between tcolorboxes | 0.2em, 0.3em, 0.5em (varies) | 0.2em |
| After convergencebar | 0.2em, 0.3em (varies) | 0.2em |
| Before bridge/transition text | 0.3em, 0.5em (varies) | 0.3em |
| Between TikZ and caption | 0.2em (mostly consistent) | 0.2em |
| Line breaks in bridge text | [4pt], [6pt] (varies) | [3pt] |

### B4. Visual Heights

- TikZ diagrams vary in height by content -- acceptable.
- pgfplots heights: 4.5cm (slide 7), 3.5cm (slide 14), 2.5cm (slide 25), 4.5cm (slide 26) -- acceptable variation.
- tcolorbox heights: driven by content, no global fix needed.

### B5. Personbox/tcolorbox Format (CONSISTENT)

All use `boxrule=0.8pt, left=3pt, right=3pt, top=2pt, bottom=2pt` for standard boxes.
Interactive Moment boxes use `boxrule=1.5pt, left=4pt, right=4pt, top=4pt, bottom=4pt` -- these should be standardized down to reduce overflow.

### B6. Title Lengths

All frame titles fit within the title bar. No issues found.

---

## C. GLOBAL FIXES (Preamble Changes)

### C1. Reduce default tcolorbox padding for Interactive Moment boxes

**What:** The Interactive Moment boxes use `boxrule=1.5pt` and `4pt` padding, which is wider than standard boxes. These contribute to overflow on slides 5, 24.

**Fix:** Not a preamble change -- fix each instance individually (see per-slide fixes).

### C2. Add global `\setlength` for parskip in frames

**What:** No explicit `\parskip` is set. Beamer's default is fine, but adding a small negative adjustment at the preamble level can recover a few points on tight slides.

**Fix:** Add after line 146 (`\setbeamertemplate{navigation symbols}{}`):
```latex
% Tighten vertical spacing in frames
\addtobeamertemplate{frametitle}{}{\vspace{-0.3em}}
```

This recovers ~3pt below every frame title, helping all 30 slides uniformly.

### C3. Standardize convergencebar bottom margin

**What:** The `\convergencebar` command (line 109-124) has no built-in bottom margin. Slides add varying `\vspace` after it.

**Fix:** Not a preamble change. Standardize the `\vspace` after each `\convergencebar` call to `0.2em`.

---

## D. PER-SLIDE FIXES

All line numbers reference the current file. Each fix is an exact edit.

---

### TASK 1: Global -- Add frametitle spacing (preamble)

**Line 146**
```
old: \setbeamertemplate{navigation symbols}{}
new: \setbeamertemplate{navigation symbols}{}

% Tighten vertical spacing below frame titles
\addtobeamertemplate{frametitle}{}{\vspace{-0.3em}}
```
**Why:** Recovers ~3pt on every framed slide, reducing overflow margin on 11 of 13 warnings.

---

### TASK 2: Slide 2 (line 253) -- Fix hbox 56.8pt + vbox 46.8pt

**Edit 2a -- Reduce insightbox top spacing (line 207)**
```
old: \vspace{0.8em}
new: \vspace{0.3em}
```

**Edit 2b -- Reduce TikZ phone height (line 221)**
```
old: (0,0) rectangle (3,4.5);
new: (0,0) rectangle (3,3.8);
```

**Edit 2c -- Adjust inner screen rectangle (line 222-223)**
```
old: \draw[rounded corners=2pt, fill=white]
          (0.2,0.4) rectangle (2.8,4.1);
new: \draw[rounded corners=2pt, fill=white]
          (0.2,0.4) rectangle (2.8,3.4);
```

**Edit 2d -- Move chat bubble down (line 225-227)**
```
old: (chat) at (1.5,2.5) {AI Response};
new: (chat) at (1.5,2.1) {AI Response};
```

**Edit 2e -- Adjust arrow targets for shorter phone (lines 229-240)**
```
old: \node[text=linalgTeal] (la) at (-1.8,4.2) {Linear Algebra};
        \draw[arr, linalgTeal] (la) -- (0.4,3.8);
        \node[text=calculusRed] (ca) at (-1.8,3.0) {Calculus};
        \draw[arr, calculusRed] (ca) -- (0.4,3.0);
        \node[text=probBlue] (pr) at (-1.8,1.8) {Probability};
        \draw[arr, probBlue] (pr) -- (0.4,2.2);
        \node[text=infoAmber] (it) at (5.3,4.2) {Info.\ Theory};
        \draw[arr, infoAmber] (it) -- (2.6,3.8);
        \node[text=logicGray] (lo) at (5.3,3.0) {Logic};
        \draw[arr, logicGray] (lo) -- (2.6,3.0);
        \node[text=approxGreen] (fa) at (5.3,1.8) {Func.\ Approx.};
        \draw[arr, approxGreen] (fa) -- (2.6,2.2);
new: \node[text=linalgTeal] (la) at (-1.8,3.5) {Linear Algebra};
        \draw[arr, linalgTeal] (la) -- (0.4,3.1);
        \node[text=calculusRed] (ca) at (-1.8,2.4) {Calculus};
        \draw[arr, calculusRed] (ca) -- (0.4,2.4);
        \node[text=probBlue] (pr) at (-1.8,1.3) {Probability};
        \draw[arr, probBlue] (pr) -- (0.4,1.7);
        \node[text=infoAmber] (it) at (5.3,3.5) {Info.\ Theory};
        \draw[arr, infoAmber] (it) -- (2.6,3.1);
        \node[text=logicGray] (lo) at (5.3,2.4) {Logic};
        \draw[arr, logicGray] (lo) -- (2.6,2.4);
        \node[text=approxGreen] (fa) at (5.3,1.3) {Func.\ Approx.};
        \draw[arr, approxGreen] (fa) -- (2.6,1.7);
```

**Edit 2f -- Widen left column slightly to fix hbox (line 192)**
```
old: \begin{column}{0.45\textwidth}
new: \begin{column}{0.46\textwidth}
```

**Edit 2g -- Narrow right column (line 214)**
```
old: \begin{column}{0.52\textwidth}
new: \begin{column}{0.50\textwidth}
```

**Why:** The hbox overflow (56.8pt) means the TikZ right-column content exceeds its 0.52\textwidth allocation. By shrinking the phone diagram and rebalancing columns slightly, both hbox and vbox overflow are resolved.

---

### TASK 3: Slide 4 (line 389) -- Fix vbox 8.7pt

**Edit 3a -- Reduce inventor spacing (lines 360-368)**
```
old: \textbf{Grassmann} (1844)\\
        Schoolteacher. First general vector spaces.
        Nobody read his book.\\[4pt]
        \textbf{Cayley} (1858)\\
        Lawyer-turned-mathematician. Matrices as algebra.\\[4pt]
        \textbf{Sylvester} (1850)\\
        Coined ``matrix'' from Latin for ``womb.''\\[4pt]
        \textbf{Gauss} (1809)\\
        Gaussian elimination --- solving linear systems.
new: \textbf{Grassmann} (1844)\\
        Schoolteacher. First general vector spaces.
        Nobody read his book.\\[2pt]
        \textbf{Cayley} (1858)\\
        Lawyer-turned-mathematician. Matrices as algebra.\\[2pt]
        \textbf{Sylvester} (1850)\\
        Coined ``matrix'' from Latin for ``womb.''\\[2pt]
        \textbf{Gauss} (1809)\\
        Gaussian elimination --- solving linear systems.
```

**Edit 3b -- Reduce vspace before llmconnection (line 371)**
```
old: \vspace{0.3em}
      \begin{llmconnection}
new: \vspace{0.15em}
      \begin{llmconnection}
```

**Why:** Saves ~9pt total (3x2pt from inventor spacing + ~3pt from vspace reduction).

---

### TASK 4: Slide 5 (line 464) -- Fix vbox 11.9pt

**Edit 4a -- Reduce Interactive Moment box padding (line 431)**
```
old: rounded corners, boxrule=1.5pt, left=4pt, right=4pt, top=4pt, bottom=4pt]
new: rounded corners, boxrule=1pt, left=3pt, right=3pt, top=2pt, bottom=2pt]
```

**Edit 4b -- Reduce vspace between Interactive and Embedding boxes (line 439)**
```
old: \vspace{0.5em}
new: \vspace{0.2em}
```

**Edit 4c -- Reduce left-column vspaces (line 410 and 423)**
Line 410:
```
old: \vspace{0.3em}
new: \vspace{0.2em}
```
Line 423:
```
old: \vspace{0.2em}
new: \vspace{0.1em}
```

**Why:** Saves ~12pt total across both columns.

---

### TASK 5: Slide 6 (line 522) -- Fix vbox 5.4pt

**Edit 5a -- Reduce bridge text line spacing (lines 508-510)**
```
old: {\small\itshape One node lit. Nine to go.\\[6pt]
       A skeleton doesn't move.\\
       For that, we need \textbf{calculus} --- the mathematics of change.}
new: {\small\itshape One node lit. Nine to go.\\[3pt]
       A skeleton doesn't move.\\
       For that, we need \textbf{calculus} --- the mathematics of change.}
```

**Edit 5b -- Reduce vspace before bridge text (line 507)**
```
old: \vspace{0.5em}
new: \vspace{0.3em}
```

**Why:** Saves ~6pt.

---

### TASK 6: Slide 9 (line 724) -- Fix vbox 0.7pt

**Edit 6a -- Reduce bridge text spacing (lines 711-715)**
```
old: {\small\itshape Two nodes lit.\\[6pt]
       The network has a skeleton and can learn.\\
       But learn \textbf{what}?\\[6pt]
       It learns to predict \textbf{probability distributions} over words.\\
       For that, we need probability theory.}
new: {\small\itshape Two nodes lit.\\[3pt]
       The network has a skeleton and can learn.\\
       But learn \textbf{what}?\\[3pt]
       It learns to predict \textbf{probability distributions} over words.\\
       For that, we need probability theory.}
```

**Edit 6b -- Reduce vspace before bridge text (line 710)**
```
old: \vspace{0.5em}
new: \vspace{0.3em}
```

**Why:** Saves ~7pt total. Only 0.7pt needed, but this also improves consistency with slide 6.

---

### TASK 7: Slide 13 (line 1012) -- Fix vbox 23.9pt

This is the largest overflow. Needs aggressive fixes.

**Edit 7a -- Reduce The Paradox box internal spacing (lines 977-995)**
```
old: \begin{tcolorbox}[colback=aiViolet!8, colframe=aiViolet,
        fonttitle=\bfseries\small, title={The Paradox},
        rounded corners, boxrule=1pt, left=4pt, right=4pt, top=4pt, bottom=4pt]
        \small
        G\"odel and Turing proved that no formal system can capture all truth.

        \vspace{0.3em}
        Yet neural networks --- running on the hardware that logic built ---
        learned to do things formal logic cannot:

        \vspace{0.2em}
        \centering
        \textbf{translate, write poetry, reason by analogy.}

        \vspace{0.3em}
        \raggedright
        \scriptsize The machines that logic built transcended the limitations
        that logic discovered.
      \end{tcolorbox}
new: \begin{tcolorbox}[colback=aiViolet!8, colframe=aiViolet,
        fonttitle=\bfseries\small, title={The Paradox},
        rounded corners, boxrule=0.8pt, left=3pt, right=3pt, top=2pt, bottom=2pt]
        \small
        G\"odel and Turing proved that no formal system can capture all truth.

        \vspace{0.15em}
        Yet neural networks --- running on the hardware that logic built ---
        learned to do things formal logic cannot:

        \vspace{0.1em}
        \centering
        \textbf{translate, write poetry, reason by analogy.}

        \vspace{0.15em}
        \raggedright
        \scriptsize The machines that logic built transcended the limitations
        that logic discovered.
      \end{tcolorbox}
```

**Edit 7b -- Reduce spacing before italic quote (line 997)**
```
old: \vspace{0.3em}
new: \vspace{0.1em}
```

**Edit 7c -- Shrink italic quote font (lines 998-1000)**
```
old: {\scriptsize\itshape ``Boole was a self-taught son of a shoemaker who reduced
       logic to algebra. Turing imagined a machine that could compute anything
       computable. Their ideas ARE the hardware your AI runs on.''}
new: {\tiny\itshape ``Boole was a self-taught son of a shoemaker who reduced
       logic to algebra. Turing imagined a machine that could compute anything
       computable. Their ideas ARE the hardware your AI runs on.''}
```

**Edit 7d -- Reduce Logic Chain box inter-line spacing (lines 950-957)**
```
old: \textbf{Boole} (1854) --- Logic as algebra.\\
        True/false $=$ 1/0. Son of a shoemaker.\\[3pt]
        \textbf{Turing} (1936) --- Universal machine.\\
        Can compute anything computable.\\[3pt]
        \textbf{Von Neumann} (1945) --- Stored program.\\
        The architecture of every computer.\\[3pt]
        \textbf{NVIDIA CUDA} (2007) --- GPUs.\\
        Billions of parallel operations.
new: \textbf{Boole} (1854) --- Logic as algebra.\\
        True/false $=$ 1/0. Son of a shoemaker.\\[2pt]
        \textbf{Turing} (1936) --- Universal machine.\\
        Can compute anything computable.\\[2pt]
        \textbf{Von Neumann} (1945) --- Stored program.\\
        The architecture of every computer.\\[2pt]
        \textbf{NVIDIA CUDA} (2007) --- GPUs.\\
        Billions of parallel operations.
```

**Why:** Saves ~25pt total. The Paradox box padding alone saves 8pt; internal vspace reductions save another ~8pt; font shrink saves ~5pt; left-column tightening saves ~4pt.

---

### TASK 8: Slide 14 (line 1092) -- Fix vbox 14.3pt

**Edit 8a -- Reduce pgfplots height (line 1028)**
```
old: width=5.5cm, height=3.5cm,
new: width=5.5cm, height=3cm,
```

**Edit 8b -- Reduce right-column inter-box spacing (line 1070)**
```
old: \vspace{0.3em}
new: \vspace{0.15em}
```

**Edit 8c -- Reduce spacing before bridge text (line 1077)**
```
old: \vspace{0.2em}
new: \vspace{0.1em}
```

**Edit 8d -- Reduce left-column caption spacing (line 1054, the line above it)**
The `\vspace{0.2em}` on line 1024 (after convergencebar):
```
old: \vspace{0.2em}
new: \vspace{0.1em}
```

**Why:** Saves ~15pt. The pgfplots height reduction alone saves ~7pt.

---

### TASK 9: Slide 22 (line 1694) -- Fix vbox 2.2pt

**Edit 9a -- Reduce inter-box spacing (lines 1635 and 1647)**
Line 1635:
```
old: \vspace{0.2em}
new: \vspace{0.1em}
```
Line 1647:
```
old: \vspace{0.2em}
new: \vspace{0.1em}
```

**Why:** Saves ~3pt. Combined with the global frametitle fix (-3pt), this resolves the 2.2pt overflow.

---

### TASK 10: Slide 24 (line 1871) -- Fix hbox 17.6pt + vbox 5.1pt

**Edit 10a -- Reduce component box width (line 1775-1776)**
```
old: comp/.style={rounded corners=2pt, minimum width=5cm,
          minimum height=0.42cm, font=\scriptsize},
new: comp/.style={rounded corners=2pt, minimum width=4.5cm,
          minimum height=0.42cm, font=\scriptsize},
```

**Edit 10b -- Move right-side labels inward (lines 1781, 1786, 1791, 1796, 1801, 1809)**
Replace all `right] at (2.8,` with `right] at (2.5,` in the left-column TikZ:
```
old: at (2.8,0)
new: at (2.5,0)
```
(Apply to all 6 label positions at x=2.8)

**Edit 10c -- Reduce Interactive box padding (line 1832)**
```
old: rounded corners, boxrule=1.5pt, left=4pt, right=4pt, top=4pt, bottom=4pt]
new: rounded corners, boxrule=1pt, left=3pt, right=3pt, top=2pt, bottom=2pt]
```

**Edit 10d -- Reduce vspace between right-column boxes (line 1841)**
```
old: \vspace{0.5em}
new: \vspace{0.2em}
```

**Why:** Fixes hbox by reducing component width (saves ~18pt horizontal). Fixes vbox by tightening right column.

---

### TASK 11: Slide 25 (line 1946) -- Fix vbox 6.2pt

**Edit 11a -- Reduce PE plot height (line 1897)**
```
old: width=5.5cm, height=2.5cm,
new: width=5.5cm, height=2.2cm,
```

**Edit 11b -- Reduce right-column vspace after convergencebar (line 1918)**
```
old: \vspace{0.3em}
new: \vspace{0.15em}
```

**Edit 11c -- Reduce vspace before bridge text (line 1931)**
```
old: \vspace{0.3em}
new: \vspace{0.15em}
```

**Why:** Saves ~7pt.

---

### TASK 12: Slide 30 (line 2247) -- Fix vbox 9.8pt

**Edit 12a -- Reduce top vspace (line 2199)**
```
old: \vspace{0.5cm}
new: \vspace{0.3cm}
```

**Edit 12b -- Reduce first large vspace (line 2222)**
```
old: \vspace{1.5em}
new: \vspace{1em}
```

**Edit 12c -- Reduce second large vspace (line 2229)**
```
old: \vspace{1.5em}
new: \vspace{1em}
```

**Edit 12d -- Reduce bottom vspace (line 2233)**
```
old: \vspace{0.5em}
new: \vspace{0.3em}
```

**Why:** Saves ~10pt total.

---

## E. UNIFORMITY STANDARDIZATION (Non-overflow slides)

These edits don't fix overflows but standardize spacing for visual consistency.

### TASK 13: Standardize bridge text `\\[6pt]` to `\\[3pt]` across all convergence slides

Affected slides and lines:
- Slide 18 (line 1416): `\\[4pt]` -> `\\[3pt]` (already close)
- No other bridge text instances use non-standard spacing.

### TASK 14: Standardize Interactive Moment box padding

All three Interactive Moment boxes should use the same padding:
- Slide 5 (line 431): Fixed in TASK 4
- Slide 11 (line 832): Change to match
- Slide 24 (line 1832): Fixed in TASK 10

**Edit 14a -- Slide 11 Interactive box (line 832)**
```
old: rounded corners, boxrule=1.5pt, left=4pt, right=4pt, top=4pt, bottom=4pt]
new: rounded corners, boxrule=1pt, left=3pt, right=3pt, top=3pt, bottom=3pt]
```

**Why:** Consistency. Slide 11 doesn't overflow, so we use a moderate 3pt (not 2pt) to avoid making it look too different from its current appearance while still matching the standardized format.

---

## F. TASK EXECUTION ORDER

Execute in this order to avoid line-number drift:

1. **TASK 1** -- Preamble change (line 146). Does not shift other line numbers.
2. **TASK 12** -- Slide 30 (lines 2199-2233). Work from bottom of file upward.
3. **TASK 11** -- Slide 25 (lines 1897-1931).
4. **TASK 10** -- Slide 24 (lines 1775-1841).
5. **TASK 9** -- Slide 22 (lines 1635-1647).
6. **TASK 8** -- Slide 14 (lines 1024-1077).
7. **TASK 7** -- Slide 13 (lines 950-1000).
8. **TASK 6** -- Slide 9 (lines 710-715).
9. **TASK 5** -- Slide 6 (lines 507-510).
10. **TASK 4** -- Slide 5 (lines 410-439).
11. **TASK 3** -- Slide 4 (lines 360-371).
12. **TASK 2** -- Slide 2 (lines 192-240).
13. **TASK 14** -- Slide 11 uniformity (line 832).
14. **TASK 13** -- Slide 18 uniformity (line 1416).

---

## G. VERIFICATION

After all edits:

```bash
cd "D:/Joerg/Research/slides/history-of-mathematics"
pdflatex -interaction=nonstopmode llm-30.tex 2>&1 | grep -c "Overfull"
```

**Target:** 0

If any warnings remain, run:
```bash
pdflatex -interaction=nonstopmode llm-30.tex 2>&1 | grep "Overfull"
```
to identify the remaining lines, then apply further tightening (reduce another `\vspace` by 0.1em on the affected slide).

---

## H. CONSTRAINTS

- **No content removal.** All text, formulas, figures, and speaker notes must be preserved.
- **No font downgrades below `\tiny`** for any visible element.
- **Preserve visual hierarchy.** Titles stay `\large\bfseries`, body stays `\small`/`\scriptsize`.
- **Preserve all TikZ diagram semantics.** Only adjust coordinates, scales, and heights.

---

## I. COMMIT STRATEGY

Single commit after all fixes verified:
```
fix(slides): eliminate 13 overflow warnings and standardize layout spacing in llm-30.tex
```

# Plan: Fix Layout of main.tex and llm-building-blocks.tex -- Zero Overflows

## Context

**Files:**
- `main.tex` -- History of Mathematics, 105 pages, 14 sections, **88 Overfull warnings**
- `llm-building-blocks.tex` -- LLM Building Blocks, 81 pages, 10 sections, **71 Overfull warnings**

**Section files (main.tex):** 14 files in `sections/sec01-opening.tex` through `sections/sec14-closing.tex`
**Section files (llm-building-blocks.tex):** 3 files in `llm-sections/part1-opening-linalg-calculus.tex`, `part2-probability-info-logic.tex`, `part3-neuron-transformer-scaling.tex`

**Goal:** Zero Overfull warnings in both files. No content removal. Professional visual quality. Consistent layout across both lectures.

**Proven approach:** The 30-slide standalone `llm-30.tex` was fixed to 0 overflows using `\addtobeamertemplate{frametitle}{}{\vspace{-0.3em}}` plus per-slide vspace reductions. That per-slide approach does not scale to 159 overflows. This plan uses a systematic global-first strategy.

---

## A. ROOT CAUSE ANALYSIS

### Why These Lectures Overflow

Both files use `\documentclass[aspectratio=169,12pt]{beamer}` with Madrid theme. The usable content area in 16:9 Beamer at 12pt with Madrid's header/footer is approximately **6.8cm tall** (before frametitle) or roughly **193pt**.

The overflows come from a consistent set of patterns:

| Root Cause | Frequency | Typical Overflow | Affected Slides |
|------------|-----------|------------------|-----------------|
| **personbox + itemize + insightbox** stacked vertically | ~60 slides | 10-30pt | Nearly all biographical slides |
| **personbox + itemize + visual** in two-column layout | ~40 slides | 5-20pt | Content-heavy biographical slides |
| **tcolorbox padding accumulation** (4pt each side x multiple boxes) | ~50 slides | 8-16pt per box | Any slide with 2+ tcolorboxes |
| **vspace accumulation** (0.5em between elements) | ~80 slides | 5-15pt cumulative | Most two-column slides |
| **TikZ diagrams exceeding column height** | ~15 slides | 10-40pt | Diagram-heavy slides |
| **Default body font at \normalsize (12pt)** | All slides | 3-8pt contribution | All content slides |
| **No frametitle spacing reduction** | All slides | ~3pt wasted | All framed slides |

### Key Insight

The 30-slide version needed 13 per-slide fixes. Scaling that to 159 overflows is impractical. Instead, if we apply 5-6 global preamble changes that each save 3-8pt per frame, the cumulative effect should eliminate most overflows. The remaining (estimated 10-20 slides with 30+ pt overflow) get `[shrink=N]` as frame option.

---

## B. GLOBAL PREAMBLE FIXES

These changes go into the preamble of BOTH `main.tex` and `llm-building-blocks.tex`, inserted after `\setbeamertemplate{navigation symbols}{}` and before `\title`.

### B1. Frametitle Vertical Spacing (saves ~3pt per frame)

**Proven in llm-30.tex.** Reduces dead space below the frametitle bar.

```latex
% Tighten vertical spacing below frame titles
\addtobeamertemplate{frametitle}{}{\vspace{-0.3em}}
```

**Insert location in main.tex:** After line 158 (`\setbeamertemplate{navigation symbols}{}`)
**Insert location in llm-building-blocks.tex:** After line 146 (`\setbeamertemplate{navigation symbols}{}`)

### B2. Default Frame Body Font to \small (saves ~4-6pt per frame)

The document uses 12pt base size. On dense slides, `\normalsize` body text is the single largest contributor to overflow. Most slides already sprinkle `\small` manually. Making it the default ensures every frame benefits.

```latex
% Default body text to \small for dense slide content
\setbeamerfont{normal text}{size=\small}
\AtBeginDocument{\usebeamerfont{normal text}}
```

**Impact:** This saves approximately 2pt per line of body text (12pt -> 10.95pt), which on a slide with 15 lines of text saves ~30pt. Even on sparse slides it saves 8-10pt. This single change will eliminate roughly half of all overflows.

**Risk:** Titles and frametitles are set via `\setbeamerfont{frametitle}` and `\setbeamerfont{title}` -- they are NOT affected. Only body text shrinks.

### B3. Itemize Spacing Reduction (saves ~2pt per item)

Beamer's default itemsep is generous. On slides with 4-6 bullet points, this adds up.

```latex
% Tighten itemize/enumerate spacing
\setlength{\itemsep}{2pt plus 1pt minus 1pt}
\setlength{\parskip}{0pt}
```

**Note:** Beamer's itemize spacing is actually set via beamer templates. The more robust approach:

```latex
% Tighten list spacing globally
\setbeamertemplate{itemize/enumerate body begin}{\setlength{\itemsep}{2pt}\setlength{\parskip}{0pt}}
\setbeamertemplate{itemize/enumerate subbody begin}{\setlength{\itemsep}{1pt}\setlength{\parskip}{0pt}}
```

### B4. Reduce Frame Top/Bottom Margins

Beamer Madrid leaves margins above and below the content area. We can reclaim some of this.

```latex
% Reduce frame content margins
\setbeamersize{text margin left=8pt, text margin right=8pt}
```

**Current default:** Madrid uses approximately 12pt margins. Saving 4pt on each side gives 8pt of horizontal room (helps hbox overflows) but does not affect vbox. For vertical savings:

```latex
% Reduce vertical spacing above content area
\addtobeamertemplate{frametitle}{\vspace{-0.2em}}{}
```

Combined with B1, total frametitle saving is ~0.5em (~6pt).

**Revised B1+B4 combined:**
```latex
% Tighten frametitle: reduce space above and below
\addtobeamertemplate{frametitle}{\vspace{-0.15em}}{\vspace{-0.4em}}
```

This saves ~7pt per frame instead of ~3pt.

---

## C. PERSONBOX AND TCOLORBOX OPTIMIZATION

### C1. Personbox Definition Change

The `personbox` appears **117 times** across all section files. It is the single most impactful box to optimize.

**Current definition (both files, identical):**
```latex
\newtcolorbox{personbox}[2][]{%
  colback=#2!5,
  colframe=#2,
  fonttitle=\bfseries,
  title=#1,
  rounded corners,
  boxrule=1pt,
  left=4pt,right=4pt,top=4pt,bottom=4pt
}
```

**New definition:**
```latex
\newtcolorbox{personbox}[2][]{%
  colback=#2!5,
  colframe=#2,
  fonttitle=\bfseries\small,
  title=#1,
  rounded corners,
  boxrule=0.8pt,
  left=3pt,right=3pt,top=2pt,bottom=2pt,
  fontupper=\small
}
```

**Savings per personbox instance:**
- Padding: (4-2)pt top + (4-2)pt bottom + (4-3)pt left + (4-3)pt right = 4pt vertical + 2pt horizontal
- boxrule: (1-0.8)pt x 2 sides = 0.4pt vertical
- fontupper=\small: forces body text to \small even if global setting somehow misses it
- fonttitle=\bfseries\small: slightly smaller title text, saves ~2pt height
- **Total vertical savings per personbox: ~6-7pt**

Since nearly every biographical slide has a personbox, this saves 6-7pt on ~60% of all slides.

### C2. Insightbox Definition Change

The `insightbox` appears **70 times** across all files.

**Current:**
```latex
\newtcolorbox{insightbox}{%
  colback=accentOrange!10,
  colframe=accentOrange,
  fonttitle=\bfseries,
  title={\faLightbulb\ Key Insight},
  rounded corners,
  boxrule=1pt,
  left=4pt,right=4pt,top=4pt,bottom=4pt
}
```

**New:**
```latex
\newtcolorbox{insightbox}{%
  colback=accentOrange!10,
  colframe=accentOrange,
  fonttitle=\bfseries\small,
  title={\faLightbulb\ Key Insight},
  rounded corners,
  boxrule=0.8pt,
  left=3pt,right=3pt,top=2pt,bottom=2pt,
  fontupper=\small
}
```

**Savings: ~6pt per instance.**

### C3. llmconnection Box Change (llm-building-blocks.tex only)

Appears in the LLM lecture. Same optimization.

**New:**
```latex
\newtcolorbox{llmconnection}{%
  colback=aiViolet!8,
  colframe=aiViolet,
  fonttitle=\bfseries\small,
  title={\faRobot\ Inside the LLM},
  rounded corners,
  boxrule=0.8pt,
  left=3pt,right=3pt,top=2pt,bottom=2pt,
  fontupper=\small
}
```

### C4. talkbox Change (main.tex only)

```latex
\newtcolorbox{talkbox}{%
  colback=gray!5,
  colframe=gray!50,
  fonttitle=\bfseries\small,
  title={\faComment\ Talking Point},
  rounded corners,
  boxrule=0.5pt,
  left=3pt,right=3pt,top=1pt,bottom=1pt,
  fontupper=\small
}
```

---

## D. CUMULATIVE IMPACT ESTIMATE

| Fix | Per-Frame Saving | Frames Affected | Total Impact |
|-----|------------------|-----------------|--------------|
| B1+B4: Frametitle spacing | ~7pt | All ~180 frames | Eliminates overflows < 7pt |
| B2: Body font \small | ~10-30pt | All content frames | Eliminates most 10-30pt overflows |
| B3: Itemize spacing | ~8pt (4 items avg) | ~120 frames with lists | Significant |
| C1: Personbox padding | ~6pt | ~117 instances | Major |
| C2: Insightbox padding | ~6pt | ~70 instances | Major |
| C3+C4: Other boxes | ~5pt | ~50 instances | Moderate |

**Expected result after global fixes:** Approximately 80-90% of overflows eliminated. Estimated 15-25 slides will still overflow (the ones currently 40+ pt over).

---

## E. HANDLING THE WORST OVERFLOWS (SHRINK STRATEGY)

After applying global fixes, some slides will still overflow. These are the slides with:
- Multiple large TikZ diagrams
- Multiple stacked tcolorboxes (3+)
- Very long personbox content (multi-line biographical details)

### Strategy: `[shrink=N]` Frame Option

For remaining overflows after global fixes, add `[shrink=N]` to the `\begin{frame}` line, where N = `ceil(remaining_overflow_pt / 2.5)`.

**How `[shrink]` works:** Beamer scales all content by a factor to fit. `[shrink=10]` means "allow up to 10% shrinkage." It produces clean, uniform results when used moderately (shrink <= 20).

**Quality constraint:** Never use `shrink > 25` -- that produces noticeably tiny text. If a slide needs >25, it must be split or content must be condensed.

### Implementation Algorithm

This is the key algorithmic step that makes this plan executable without manual judgment:

```
1. Apply all global preamble fixes (B1-B4, C1-C4)
2. Compile both files, capture Overfull warnings
3. For each remaining Overfull vbox warning:
   a. Parse the overflow amount (e.g., "Overfull \vbox (23.4pt too high)")
   b. Compute shrink value: N = ceil(overflow_pt / 2.5)
   c. Cap at 25: N = min(N, 25)
   d. Find the corresponding \begin{frame} line
   e. Add [shrink=N] to it (e.g., \begin{frame}[shrink=10]{Title})
   f. If frame already has options like [plain], merge: [plain,shrink=10]
4. For each remaining Overfull hbox warning:
   a. These are usually from TikZ or tcolorbox exceeding column width
   b. Add [shrink=N] using same formula -- shrink fixes hbox too
5. Recompile and verify 0 warnings
```

**Important Beamer syntax:** If a frame has no existing options, change:
- `\begin{frame}{Title}` -> `\begin{frame}[shrink=N]{Title}`

If a frame already has options:
- `\begin{frame}[fragile]{Title}` -> `\begin{frame}[fragile,shrink=N]{Title}`

---

## F. IMPLEMENTATION TASKS (ORDERED)

### TASK 1: Create shared preamble file `layout-fixes.tex`

To avoid duplicating changes across both main files, create a single shared file.

**Create file:** `D:/Joerg/Research/slides/history-of-mathematics/layout-fixes.tex`

**Contents:**
```latex
% ============================================================
% Shared layout fixes for all Beamer lectures
% Eliminates Overfull vbox/hbox warnings globally
% Include via \input{layout-fixes} after \setbeamertemplate{navigation symbols}{}
% ============================================================

% --- Frametitle vertical tightening ---
% Saves ~7pt per frame by reducing dead space above and below frametitle
\addtobeamertemplate{frametitle}{\vspace{-0.15em}}{\vspace{-0.4em}}

% --- Default body font to \small ---
% 12pt base is too large for dense Beamer slides; \small (10.95pt) fits better
\setbeamerfont{normal text}{size=\small}
\AtBeginDocument{\usebeamerfont{normal text}}

% --- Tighten list spacing globally ---
\setbeamertemplate{itemize/enumerate body begin}{%
  \setlength{\itemsep}{2pt plus 1pt minus 1pt}%
  \setlength{\parskip}{0pt}%
}
\setbeamertemplate{itemize/enumerate subbody begin}{%
  \setlength{\itemsep}{1pt}%
  \setlength{\parskip}{0pt}%
}
```

### TASK 2: Add `\input{layout-fixes}` to main.tex

**Location:** After line 158 (`\setbeamertemplate{navigation symbols}{}`), before `% ---- Document Info ----`

**Edit:**
```
old: \setbeamertemplate{navigation symbols}{}

% ---- Document Info ----
new: \setbeamertemplate{navigation symbols}{}

% ---- Layout Tightening (shared across lectures) ----
\input{layout-fixes}

% ---- Document Info ----
```

### TASK 3: Add `\input{layout-fixes}` to llm-building-blocks.tex

**Location:** After line 146 (`\setbeamertemplate{navigation symbols}{}`), before `% ---- Document Info ----`

**Edit:** Same pattern as TASK 2.

### TASK 4: Update personbox definition in main.tex

**Location:** Lines 80-88

**Edit:**
```
old: \newtcolorbox{personbox}[2][]{%
  colback=#2!5,
  colframe=#2,
  fonttitle=\bfseries,
  title=#1,
  rounded corners,
  boxrule=1pt,
  left=4pt,right=4pt,top=4pt,bottom=4pt
}
new: \newtcolorbox{personbox}[2][]{%
  colback=#2!5,
  colframe=#2,
  fonttitle=\bfseries\small,
  title=#1,
  rounded corners,
  boxrule=0.8pt,
  left=3pt,right=3pt,top=2pt,bottom=2pt,
  fontupper=\small
}
```

### TASK 5: Update personbox definition in llm-building-blocks.tex

**Location:** Lines 76-84. Same edit as TASK 4.

### TASK 6: Update insightbox definition in main.tex

**Location:** Lines 91-99

**Edit:**
```
old: \newtcolorbox{insightbox}{%
  colback=accentOrange!10,
  colframe=accentOrange,
  fonttitle=\bfseries,
  title={\faLightbulb\ Key Insight},
  rounded corners,
  boxrule=1pt,
  left=4pt,right=4pt,top=4pt,bottom=4pt
}
new: \newtcolorbox{insightbox}{%
  colback=accentOrange!10,
  colframe=accentOrange,
  fonttitle=\bfseries\small,
  title={\faLightbulb\ Key Insight},
  rounded corners,
  boxrule=0.8pt,
  left=3pt,right=3pt,top=2pt,bottom=2pt,
  fontupper=\small
}
```

### TASK 7: Update insightbox definition in llm-building-blocks.tex

**Location:** Lines 87-95. Same edit as TASK 6.

### TASK 8: Update llmconnection definition in llm-building-blocks.tex

**Location:** Lines 98-106

**Edit:**
```
old: \newtcolorbox{llmconnection}{%
  colback=aiViolet!8,
  colframe=aiViolet,
  fonttitle=\bfseries,
  title={\faRobot\ Inside the LLM},
  rounded corners,
  boxrule=1pt,
  left=4pt,right=4pt,top=4pt,bottom=4pt
}
new: \newtcolorbox{llmconnection}{%
  colback=aiViolet!8,
  colframe=aiViolet,
  fonttitle=\bfseries\small,
  title={\faRobot\ Inside the LLM},
  rounded corners,
  boxrule=0.8pt,
  left=3pt,right=3pt,top=2pt,bottom=2pt,
  fontupper=\small
}
```

### TASK 9: Update talkbox definition in main.tex

**Location:** Lines 102-110

**Edit:**
```
old: \newtcolorbox{talkbox}{%
  colback=gray!5,
  colframe=gray!50,
  fonttitle=\bfseries,
  title={\faComment\ Talking Point},
  rounded corners,
  boxrule=0.5pt,
  left=4pt,right=4pt,top=2pt,bottom=2pt
}
new: \newtcolorbox{talkbox}{%
  colback=gray!5,
  colframe=gray!50,
  fonttitle=\bfseries\small,
  title={\faComment\ Talking Point},
  rounded corners,
  boxrule=0.5pt,
  left=3pt,right=3pt,top=1pt,bottom=1pt,
  fontupper=\small
}
```

### TASK 10: Compile main.tex -- count remaining overflows

```bash
cd "D:/Joerg/Research/slides/history-of-mathematics"
pdflatex -interaction=nonstopmode main.tex 2>&1 | grep -c "Overfull"
```

Record the count. If > 0, proceed to TASK 11. If 0, skip to TASK 13.

### TASK 11: Parse remaining overflows and apply `[shrink=N]` to main.tex section files

For each remaining Overfull warning from the TASK 10 output:

1. Parse the warning to get the overflow amount and the frame location
2. Find the corresponding `\begin{frame}` in the section file
3. Compute `N = min(ceil(overflow_pt / 2.5), 25)`
4. Add `[shrink=N]` to the frame option

**Parsing approach:** Overfull warnings look like:
```
Overfull \vbox (23.4pt too high) has occurred while \output is active []
```
The page number follows. Map page number to frame by counting `\begin{frame}` occurrences.

Alternatively, use this regex pipeline:
```bash
pdflatex -interaction=nonstopmode main.tex 2>&1 | grep "Overfull" | grep -oP '\d+\.?\d*pt'
```

Then for each overflow, search the section files for the frame on that output page.

**A more reliable approach:** Compile with `\overfullrule=5pt` temporarily to visually mark overflows, but for automated fixing:

```bash
pdflatex -interaction=nonstopmode main.tex 2>&1 | grep -A1 "Overfull"
```

This gives the line number in the `.tex` file. Use that to find the enclosing `\begin{frame}`.

### TASK 12: Recompile main.tex -- verify 0 overflows

```bash
pdflatex -interaction=nonstopmode main.tex 2>&1 | grep -c "Overfull"
```

If still > 0, increase shrink values by 5 on the remaining frames and recompile. Repeat until 0.

### TASK 13: Compile llm-building-blocks.tex -- count remaining overflows

```bash
pdflatex -interaction=nonstopmode llm-building-blocks.tex 2>&1 | grep -c "Overfull"
```

### TASK 14: Parse remaining overflows and apply `[shrink=N]` to llm-building-blocks.tex section files

Same algorithm as TASK 11, applied to the three `llm-sections/` files.

### TASK 15: Recompile llm-building-blocks.tex -- verify 0 overflows

Same verification as TASK 12.

### TASK 16: Final verification -- both files

```bash
cd "D:/Joerg/Research/slides/history-of-mathematics"
pdflatex -interaction=nonstopmode main.tex 2>&1 | grep -c "Overfull"
pdflatex -interaction=nonstopmode llm-building-blocks.tex 2>&1 | grep -c "Overfull"
```

**Target:** Both return 0.

---

## G. VSPACE NORMALIZATION (BONUS -- AFTER ZERO OVERFLOWS)

After achieving 0 overflows, normalize inconsistent `\vspace` values across section files for visual uniformity:

| Pattern | Current (varies) | Standard |
|---------|-------------------|----------|
| After personbox | 0.3em, 0.4em, 0.5em | 0.3em |
| Between itemize and tcolorbox | 0.3em, 0.5em, 0.8em | 0.3em |
| Between visual placeholders | 0.2em, 0.3em, 0.5em | 0.2em |
| After insightbox | 0.3em, 0.5em | 0.3em |
| Line breaks in biographical text `\\[Npt]` | 3pt, 4pt, 6pt | 3pt |

This is a sed-replaceable standardization:
```bash
# In section files, normalize common vspace patterns
# (exact commands depend on remaining values after global fixes)
```

---

## H. FILES MODIFIED

| File | Changes |
|------|---------|
| `layout-fixes.tex` | **NEW** -- shared preamble fixes |
| `main.tex` | Add `\input{layout-fixes}`, update personbox/insightbox/talkbox definitions |
| `llm-building-blocks.tex` | Add `\input{layout-fixes}`, update personbox/insightbox/llmconnection definitions |
| `sections/sec01-opening.tex` through `sec14-closing.tex` | Add `[shrink=N]` to remaining overflow frames |
| `llm-sections/part1-*.tex`, `part2-*.tex`, `part3-*.tex` | Add `[shrink=N]` to remaining overflow frames |

---

## I. CONSTRAINTS

- **No content removal.** All text, formulas, figures, speaker notes preserved.
- **No font below `\scriptsize`** for any visible element (speaker notes may use `\tiny`).
- **`[shrink]` never exceeds 25.** If a slide needs >25, flag it for manual review.
- **Title slides and section dividers are excluded** from shrink (they use `[plain]` and custom layouts).
- **Both lectures must look visually consistent** after fixes.
- **The `llm-30.tex` standalone file must NOT be affected** (it has its own preamble; it does not `\input{layout-fixes}`).

---

## J. COMMIT STRATEGY

Single commit after both files verified at 0 overflows:

```
fix(slides): eliminate all Overfull warnings in main.tex and llm-building-blocks.tex

- Add shared layout-fixes.tex: frametitle tightening, \small body default, list spacing
- Reduce personbox/insightbox/llmconnection/talkbox padding globally
- Apply [shrink=N] to remaining overflow frames
- Target: 0 Overfull warnings across both 100+ page lectures
```

---

## K. SUCCESS CRITERIA

1. `pdflatex main.tex` produces **0 Overfull warnings**
2. `pdflatex llm-building-blocks.tex` produces **0 Overfull warnings**
3. All slide content is **preserved** (no deletions)
4. No `[shrink]` value exceeds **25**
5. Both PDFs render **professional visual quality** (no visibly tiny text, no crushed layouts)
6. `llm-30.tex` remains **unaffected** (separate preamble)

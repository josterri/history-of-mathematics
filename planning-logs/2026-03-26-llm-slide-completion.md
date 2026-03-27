# LLM Building Blocks -- Slide-by-Slide Visual Completion Plan

**Created:** 2026-03-26
**Revised:** 2026-03-26 (Iteration 2 -- addresses all Critic feedback)
**Scope:** 79 frames across 3 part files + 2 session breaks in main file, 58 `\visualplaceholder` instances
**Goal:** Replace every placeholder with actual visuals (TikZ, images, pgfplots)

### Frame Count Verification

| File | Frames | Slides |
|------|--------|--------|
| `part1-opening-linalg-calculus.tex` | 26 | 1-25 + 1 interactive frame after Slide 13 |
| `part2-probability-info-logic.tex` | 23 | 26-48 |
| `part3-neuron-transformer-scaling.tex` | 30 | 49-78 |
| `llm-building-blocks.tex` (session breaks) | 2 | (unnumbered break slides) |
| **Total content frames** | **79** | |
| **Total with session breaks** | **81** | |

The interactive frame "Quick Experiment -- Word Vector Arithmetic" appears between Slides 13 and 14 in Part 1. It is a full `\begin{frame}` and Beamer counts it in `\inserttotalframenumber`. The plan refers to it as "Slide 13i" (interactive) to avoid renumbering all subsequent slides. All existing `Slide~N` cross-references in the LaTeX source use the CONTENT numbering (1-78), not the Beamer frame counter, so the interactive frame does not create off-by-one errors in cross-references -- it sits between the content addressed by Slide 13 and Slide 14.

**Numbering convention in this plan:** "Slide N" = the Nth content slide as labeled in the source comments. "Slide 13i" = the interactive frame. Beamer frame numbers will differ from content slide numbers by +1 for all slides after Slide 13 (frames 1-13 = slides 1-13, frame 14 = slide 13i, frames 15-79 = slides 14-78). Session breaks add 2 more frames but use `[plain]` and are excluded from content numbering.

---

## Table of Contents

- [Beamer-Safe TikZ Rules](#tikz-rules)
- [Color Palette Reference](#color-palette)
- [Part 1: Opening + Linear Algebra + Calculus (Slides 1-25 + 13i)](#part-1)
- [Part 2: Probability + Information Theory + Logic (Slides 26-48)](#part-2)
- [Part 3: Function Approx + Neuron + Sequence + Transformer + Scaling (Slides 49-78)](#part-3)
- [Portrait Inventory](#portrait-inventory)
- [Convergence Diagram Strategy](#convergence-diagram-strategy)
- [Exploded Transformer Diagram Strategy](#exploded-transformer-strategy)
- [Fourier Square Wave Precomputation](#fourier-precompute)
- [Prioritized Task List](#prioritized-task-list)
- [Cross-Reference Verification (Complete)](#cross-references)
- [Commit Strategy](#commit-strategy)
- [Success Criteria](#success-criteria)

---

<a id="tikz-rules"></a>
## Beamer-Safe TikZ Rules

All TikZ diagrams MUST follow these constraints:
- **NO** `\foreach` inside frames (use explicit node declarations)
- **NO** `#1` in style definitions inside frames
- **NO** `\pgfmathsetmacro` inside frames
- **Simple** nodes + arrows + draws ONLY
- Complex diagrams: generate externally as PDF/PNG, include with `\includegraphics`
- pgfplots is OK for simple charts (already used in some slides)

---

<a id="color-palette"></a>
## Color Palette Reference

### MANDATORY: LLM Section Colors (lines 30-37 of `llm-building-blocks.tex`)

These are the PURPOSE-BUILT secondary palette for this lecture. All section-colored diagrams (convergence diagram, exploded transformer, etc.) MUST use these:

| Color Name | RGB | Use For |
|------------|-----|---------|
| `linalgTeal` | (0,150,136) | Section 1: Linear Algebra |
| `calculusRed` | (211,47,47) | Section 2: Calculus & Optimization |
| `probBlue` | (25,118,210) | Section 3: Probability & Statistics |
| `infoAmber` | (255,160,0) | Section 4: Information Theory |
| `logicGray` | (97,97,97) | Section 5: Logic & Computation |
| `approxGreen` | (56,142,60) | Section 6: Function Approximation |
| `neuronPink` | (194,24,91) | Section 7: The Neuron & Depth |
| `seqIndigo` | (63,81,181) | Section 8: Sequence Modeling |
| `aiViolet` | (106,13,173) | Section 9: The Transformer (use as primary) |
| `accentOrange` | (230,126,34) | Section 10: Scaling to LLMs |

### Historical/Era Colors (lines 14-27, for era-themed content only)

| Color Name | Use For |
|------------|---------|
| `digitalBlue` | Linear Algebra personboxes (historical styling) |
| `enlightenmentTeal` | Calculus section divider background |
| `aiViolet` | Probability personboxes, section dividers |
| `darkBg` | Dark backgrounds |
| `accentOrange` | Insight boxes, highlights |

**RULE:** When a diagram maps sections to colors (convergence diagram, exploded transformer), always use the LLM section palette (`linalgTeal` through `seqIndigo`), NOT the historical palette.

---

<a id="part-1"></a>
## PART 1: Opening + Linear Algebra + Calculus (Slides 1-25 + Slide 13i)

File: `llm-sections/part1-opening-linalg-calculus.tex`
Frames in file: 26

---

### Slide 1: Title Slide
**Current**: Full-bleed aiViolet background, white text with title/subtitle/author. No placeholder.
**Placeholders**: NONE
**Action items**: None needed. Slide is complete.

---

### Slide 2: What's Inside Your AI?
**Current**: Two-column. Left: bullets + insightbox. Right: one placeholder.
**Placeholders**:
1. `[6cm]` -- Smartphone screen showing AI chat with floating labeled arrows to math fields

**Action items**:
1. **TikZ diagram**: Draw a simplified smartphone outline (rounded rectangle). Inside, show a chat bubble. Around it, draw 6 labeled arrows pointing inward, using the LLM section palette:
   - "Linear Algebra" (`linalgTeal`)
   - "Calculus" (`calculusRed`)
   - "Probability" (`probBlue`)
   - "Information Theory" (`infoAmber`)
   - "Logic" (`logicGray`)
   - "Function Approximation" (`approxGreen`)
   Each arrow is a simple `\draw[->,thick,color]` from an outer label node to the chat rectangle. Beamer-safe: 7 explicit nodes + 6 arrows. No loops.

**Portrait needed**: None

---

### Slide 3: The Exploded Transformer -- What We Will Build Today
**Current**: Full-slide placeholder, plus a small gray caption below.
**Placeholders**:
1. `[12cm]` -- EXPLODED TRANSFORMER DIAGRAM. Color-coded components across all 10 sections.

**Action items**:
1. **External image (HIGH PRIORITY)**: See [Exploded Transformer Diagram Strategy](#exploded-transformer-strategy) for full specification. This is the lecture's signature visual. Create as standalone TikZ document compiled to PDF: `figures/exploded-transformer-base.pdf`. This is the BASE variant (no annotations). The same base is reused with annotations on Slides 73 and 76.

**Portrait needed**: None
**Cross-ref note**: Slide 3 speaker note says "we will return to it in Slide 73". This is correct (Slide 73 = "The Full Transformer -- Annotated").

---

### Slide 4: The Convergence Diagram -- Our Roadmap
**Current**: Full-slide placeholder.
**Placeholders**:
1. `[12cm]` -- CONVERGENCE DIAGRAM initial state. Central "?" node, 10 gray nodes in semicircle.

**Action items**:
1. **Convergence diagram variant 0**: See [Convergence Diagram Strategy](#convergence-diagram-strategy). Use `figures/convergence-0.pdf`. All 10 nodes gray, central "?" node.

**Portrait needed**: None

---

### Slide 5: Section Divider -- Linear Algebra
**Current**: Full-bleed digitalBlue background with section title. No placeholder.
**Placeholders**: NONE
**Action items**: None.

---

### Slide 6: What Is a Vector?
**Current**: Two-column. Left: personboxes for Grassmann and Hamilton. Right: two placeholders.
**Placeholders**:
1. `[5cm]` -- 2D vector, 3D vector, 768-dim vector with fading dots
2. `[5cm]` -- Plaque on Brougham Bridge with Hamilton's quaternion formula

**Action items**:
1. **TikZ diagram**: Three sub-diagrams side by side:
   - Left: 2D arrow from origin to (2,1) with axis labels
   - Middle: 3D arrow sketch (use isometric: nodes at pseudo-3D coords)
   - Right: Column vector notation `[0.23, -0.87, 0.44, ..., 0.12]` with "768 numbers" label and fading dots
   Below: caption text as a `\node` or direct LaTeX. ~6 explicit draw commands + nodes.

2. **Historical photo**: Brougham Bridge plaque.
   - **Wikimedia search**: "Broom Bridge plaque quaternion"
   - **Acceptable licenses**: Public domain, CC0, CC-BY, CC-BY-SA (see [Portrait Licensing](#portrait-licensing))
   - Use: `\includegraphics[width=4.5cm]{figures/brougham-bridge-plaque.jpg}`
   - Fallback: TikZ recreation of the plaque text in a decorative frame

**Portrait needed**: Grassmann (engraving), Hamilton (daguerreotype). LOW -- bridge plaque has more narrative punch.

---

### Slide 7: Modern Vector Notation -- Gibbs and Heaviside
**Current**: Two-column. Left: personboxes for Gibbs and Heaviside. Right: one placeholder.
**Placeholders**:
1. `[6cm]` -- Hamilton quaternion notation vs. Gibbs vector notation side by side

**Action items**:
1. **TikZ diagram**: Two-column comparison inside a single TikZ picture:
   - Left box (labeled "Hamilton's quaternions"): Multiline quaternion expression
   - Right box (labeled "Gibbs's vectors"): Same operation as `\vec{a} \cdot \vec{b} = a_1 b_1 + a_2 b_2 + a_3 b_3`
   - Arrow or "=" sign between them
   - Caption node: "Same math. Simpler notation."
   Implementation: Two `\node[draw,text width=3cm]` boxes side by side with an arrow between.

**Portrait needed**: Gibbs, Heaviside -- MEDIUM

---

### Slide 8: Matrices -- Cayley and Sylvester
**Current**: Two-column. Left: personboxes for Cayley and Sylvester. Right: one placeholder.
**Placeholders**:
1. `[5.5cm]` -- Simple 3x3 matrix (top) vs. huge LLM weight matrix (bottom)

**Action items**:
1. **TikZ diagram**: Two stacked sub-diagrams:
   - Top: A 3x3 matrix in `\begin{pmatrix}` notation, annotation "Cayley (1858)"
   - Bottom: Large matrix suggestion -- first few rows/cols, dots in center, labeled "175,000,000,000 entries"
   - Caption: "This is also a matrix. Same math."
   Two `\node` elements containing matrix LaTeX and a gray dotted rectangle.

**Portrait needed**: Cayley, Sylvester -- MEDIUM

---

### Slide 9: Matrix Multiplication -- The Core Operation
**Current**: Two-column. Left: personbox for Gauss + insightbox. Right: one placeholder.
**Placeholders**:
1. `[6cm]` -- Step-by-step matrix multiplication (top) + same operation as neural network layer (bottom)

**Action items**:
1. **TikZ diagram (MEDIUM-HIGH PRIORITY)**: Two-part visual:
   - Top half: 3x3 matrix times 3x1 vector. Show dot-product row-by-row with colored highlighting. Explicit `\node` for each matrix element and `\draw` arrows connecting row to column.
   - Bottom half: Same operation as neural net layer. 3 input circles on left, 3 output circles on right, connection lines with weights. Label: "Same math. Different picture."
   ~20 nodes, ~15 draws. Feasible inline.

**Portrait needed**: Gauss -- MEDIUM

---

### Slide 10: The Dot Product -- Measuring Similarity
**Current**: Two-column. Left: recipe + formula. Right: two placeholders.
**Placeholders**:
1. `[6cm]` -- Two 2D arrows in three configurations (same dir, perpendicular, opposite)
2. `[6cm]` -- LLM context: Query "it" + Key "cat" dot product explanation

**Action items**:
1. **TikZ diagram**: Three sub-pictures in a row:
   - (a) Two arrows roughly same direction, label "large positive"
   - (b) Two arrows perpendicular, label "zero"
   - (c) Two arrows opposite, label "large negative"
   ~6 draws per sub-picture.

2. **TikZ diagram**: Simplified attention-score visualization:
   - Two word nodes: "it" and "cat"
   - Arrow between with thickness proportional to attention
   - Label: "Large dot product = strong attention"
   2 nodes, 1 thick arrow, 2 text labels.

**Portrait needed**: None

---

### Slide 11: Cosine Similarity
**Current**: Two-column. Left: recipe + formula + insightbox. Right: one placeholder.
**Placeholders**:
1. `[6.5cm]` -- 2D embedding space with word vectors (king, queen, banana) and angle arcs

**Action items**:
1. **TikZ diagram**: 2D coordinate system with:
   - Origin at center
   - Arrow to "king" (45 degrees, length 3)
   - Arrow to "queen" (55 degrees, length 2.8)
   - Arrow to "banana" (170 degrees, length 2.5)
   - Angle arc between king-queen (small, "high similarity")
   - Angle arc between king-banana (large, "low similarity")
   ~5 draws + 4 nodes + 2 arcs.

**Portrait needed**: None

---

### Slide 12: Eigenvalues and Eigenvectors [EXTENDED]
**Current**: Two-column. Left: three personboxes (Euler, Cauchy, Hilbert). Right: one placeholder + text.
**Placeholders**:
1. `[6cm]` -- 2D linear transformation: most arrows change direction, eigenvector arrows only stretch

**Action items**:
1. **TikZ diagram**: Grid of arrows before/after a linear transformation:
   - ~8 arrows from origin in various directions
   - After transformation: most arrows rotate AND stretch
   - Two arrows (eigenvectors) only stretch/shrink, highlighted in bold
   - Label: "Eigenvector: only stretches, does not rotate"
   ~16 explicit arrows + labels. Feasible inline.

**Portrait needed**: Euler, Cauchy, Hilbert -- LOW (extended slide)

---

### Slide 13: High-Dimensional Spaces -- Where Words Live
**Current**: Two-column. Left: text + personbox (Bellman). Right: one placeholder + text about Mikolov.
**Placeholders**:
1. `[6cm]` -- 2D scatter plot of word embeddings with king-man+woman=queen analogy arrows

**Action items**:
1. **TikZ diagram**: 2D scatter plot:
   - ~6 word points: "king", "queen", "man", "woman", "dog", "cat"
   - Famous parallelogram: king-man arrow, woman-queen arrow (same direction/length)
   - Dashed arrow from "king - man + woman" landing near "queen"
   - Caption: "Projected from 768 dimensions down to 2"
   ~8 nodes + 4 arrows.

**Portrait needed**: Bellman -- LOW

---

### Slide 13i (Interactive): Word Vector Arithmetic
**Current**: Large central equation + one placeholder for reveal.
**Placeholders**:
1. `[8cm]` -- Space for student responses, then parallelogram reveal

**Action items**:
1. **TikZ diagram (build/reveal variant)**: The parallelogram diagram from Slide 13, but larger and centered. Use `\only<2>{}` Beamer overlay for reveal:
   - Overlay 1: just the equation (already in source)
   - Overlay 2: parallelogram with "QUEEN" in large text + checkmark + "Mikolov et al., Word2Vec, 2013"
   Or: keep as static with answer visible (simpler for PDF-only builds).

**Portrait needed**: None

---

### Slide 14: From Words to Numbers -- The Embedding
**Current**: Full-width placeholder.
**Placeholders**:
1. `[12cm]` -- Step-by-step pipeline: sentence -> tokens -> vectors -> matrix

**Action items**:
1. **TikZ diagram (HIGH PRIORITY)**: Horizontal pipeline across full width:
   - Step 1: Text box with "The cat sat on the mat"
   - Step 2: Tokenizer box splitting into 6 tokens
   - Step 3: Each token becomes a vector (small column of numbers)
   - Step 4: Vectors stacked = matrix (6 rows x 768 cols)
   - Arrows between each step
   - Caption: "Your sentence is now a matrix."
   ~10 boxes + arrows. Feasible inline.

**Portrait needed**: None

---

### Slide 15: Attention as Matrix Multiplication (Preview)
**Current**: Two-column. Left: step-by-step attention recipe + formula. Right: one placeholder.
**Placeholders**:
1. `[5.5cm]` -- Simplified attention pipeline: X -> W_Q -> Q, X -> W_K -> K, X -> W_V -> V, then scores -> softmax -> output

**Action items**:
1. **TikZ diagram**: Flow chart:
   - Input node "X"
   - Three parallel paths: X -> W_Q -> Q, X -> W_K -> K, X -> W_V -> V
   - Then Q*K^T -> "Scores" -> "Softmax" -> *V -> "Output"
   - Each step labeled with section reference
   ~12 nodes + ~12 arrows. Feasible inline.

**Portrait needed**: None

---

### Slide 16: Convergence Diagram Update -- Linear Algebra
**Current**: Two-column. Left: convergence diagram placeholder. Right: summary table + insightbox.
**Placeholders**:
1. `[6.5cm]` -- Convergence diagram with "Linear Algebra" node lit

**Action items**:
1. **Convergence diagram variant 1**: Node 1 = `linalgTeal`, all others gray. Use `figures/convergence-1.pdf`.

**Portrait needed**: None

---

### Slide 17: Section Divider -- Calculus & Optimization
**Current**: Full-bleed enlightenmentTeal background. No placeholder.
**Placeholders**: NONE
**Action items**: None.

---

### Slide 18: Roots in Antiquity -- Archimedes
**Current**: Two-column. Left: personbox for Archimedes + insightbox. Right: one placeholder.
**Placeholders**:
1. `[6cm]` -- Archimedes' method of exhaustion: circle with inscribed polygons (4, 8, 16, 32 sides)

**Action items**:
1. **TikZ diagram**: Four sub-figures side by side, each a circle with an inscribed polygon:
   - Sub 1: circle + inscribed square (4 sides)
   - Sub 2: circle + inscribed octagon (8 sides)
   - Sub 3: circle + inscribed 16-gon
   - Sub 4: circle + label "..." to suggest continuation
   Caption: "Approximate, refine, repeat."
   Avoid the 32-gon (too many explicit coordinates). Use 4 small circles (~1.5cm radius each) with explicit polygon vertices.

**Portrait needed**: Archimedes (Domenico Fetti painting, public domain) -- MEDIUM

---

### Slide 19: The Derivative -- Measuring Change
**Current**: Two-column. Left: three personboxes (Fermat, Newton, Leibniz). Right: two placeholders.
**Placeholders**:
1. `[6cm]` -- Three notations side by side: Fermat (geometric), Newton (dot), Leibniz (dy/dx)
2. `[6cm]` -- Simple curve with tangent line

**Action items**:
1. **TikZ diagram**: Three framed text nodes:
   - "Fermat" -- geometric tangent sketch
   - "Newton" -- `\dot{y}` notation
   - "Leibniz" -- `\frac{dy}{dx}` notation

2. **pgfplots**: Plot `f(x) = x^2` with tangent line at x=1. Label: "slope = derivative."

**Portrait needed**: Fermat, Newton, Leibniz -- MEDIUM (but crowded slide, omit if tight)

---

### Slide 20: The Chain Rule
**Current**: Two-column. Left: recipe + formula + insightbox. Right: one placeholder.
**Placeholders**:
1. `[6.5cm]` -- Pipeline: x -> f -> u -> g -> y (top), relabeled as neural network (bottom) with backward red arrows

**Action items**:
1. **TikZ diagram**: Two rows:
   - Top: Chain `x -> [f] -> u -> [g] -> y` with forward blue arrows
   - Bottom: Same relabeled `Input -> [Layer 1] -> Hidden -> [Layer 2] -> Output` with backward RED arrows labeled "chain rule"
   ~8 nodes + ~8 arrows.

**Portrait needed**: None

---

### Slide 21: Gradient Descent [EXTENDED]
**Current**: Two-column. Left: personbox (Cauchy) + recipe. Right: one placeholder.
**Placeholders**:
1. `[6.5cm]` -- 3D loss surface with contour lines, ball rolling downhill via gradient steps

**Action items**:
1. **External image or pgfplots 3D plot**: A 3D "bowl" surface:
   - pgfplots 3D surface `\addplot3[surf]` of `x^2 + y^2`
   - Zigzag path of arrows descending from high to low
   - Label: "Gradient descent: always walk downhill. Cauchy, 1847."
   If inline: keep to a simple paraboloid. May be slow to compile -- consider precompiling.

**Portrait needed**: Cauchy -- already listed for Slide 12

---

### Slide 22: Backpropagation
**Current**: Two-column. Left: two personboxes (Linnainmaa, Rumelhart/Hinton/Williams). Right: one placeholder + timeline table.
**Placeholders**:
1. `[6cm]` -- Multi-layer network: blue forward arrows left-to-right, red backward arrows right-to-left

**Action items**:
1. **TikZ diagram**: A 3-layer neural network:
   - 3 input nodes, 4 hidden nodes, 2 output nodes
   - Blue arrows forward (left to right)
   - Red arrows backward (right to left), labeled "chain rule"
   ~9 nodes + ~24 connection lines. Moderate but feasible.

**Portrait needed**: Hinton -- HIGH; Linnainmaa -- SKIP (unlikely available)

---

### Slide 23: Stochastic Gradient Descent
**Current**: Two-column. Left: personbox (Robbins & Monro) + insightbox. Right: one placeholder.
**Placeholders**:
1. `[6.5cm]` -- Side by side: smooth full gradient path vs. noisy SGD zigzag path

**Action items**:
1. **TikZ diagram**: Two contour-plot landscapes side by side:
   - Left: Smooth elliptical contours with clean diagonal path to center. Label: "Full GD: look at ALL data. Too slow."
   - Right: Same contours with noisy zigzag path. Label: "SGD: random samples. Faster."
   ~10 ellipses + ~20 path points total.

**Portrait needed**: None

---

### Slide 24: The Loss Landscape -- A Visual Tour
**Current**: Full-slide placeholder.
**Placeholders**:
1. `[12cm]` -- 3D neural network loss landscape (Li et al. 2018 style)

**Action items**:
1. **External image (MEDIUM PRIORITY)**: Cannot be rendered well inline. Options:
   - Search Wikimedia for CC-licensed loss landscape visualizations
   - Generate using Python matplotlib 3D surface, export as `figures/loss-landscape.pdf`
   - Label: "Global minimum", "Local minima", "Saddle points", "SGD path"
   - **Licensing**: CC-BY or CC-BY-SA required (see [Portrait Licensing](#portrait-licensing))

**Portrait needed**: None

---

### Slide 25: Convergence Diagram Update -- Calculus
**Current**: Two-column. Left: convergence diagram placeholder. Right: summary table + insightbox.
**Placeholders**:
1. `[6.5cm]` -- Convergence diagram: nodes 1-2 lit

**Action items**:
1. **Convergence diagram variant 2**: Nodes 1-2 lit (`linalgTeal`, `calculusRed`). Use `figures/convergence-2.pdf`.

**Portrait needed**: None

---

<a id="part-2"></a>
## PART 2: Probability + Information Theory + Logic (Slides 26-48)

File: `llm-sections/part2-probability-info-logic.tex`
Frames in file: 23

---

### Slide 26: Section Divider -- Probability & Statistics
**Placeholders**: NONE. **Action items**: None.

### Slide 27: The Birth of Probability -- Pascal & Fermat
**Placeholders**: NONE (TikZ already implemented). **Action items**: None. COMPLETE.

### Slide 28: From Gambling to Laws -- Bernoulli and Laplace
**Placeholders**: NONE (pgfplots already implemented). **Action items**: None. COMPLETE.

### Slide 29: Bayes' Theorem
**Placeholders**: NONE. **Action items**: None. COMPLETE.

### Slide 30: Kolmogorov's Axioms [EXTENDED]
**Placeholders**: NONE. **Action items**: None. COMPLETE.

### Slide 31: Maximum Likelihood
**Placeholders**: NONE (pgfplots already implemented). **Action items**: None. COMPLETE.

### Slide 32: Shannon's Statistical Language Models
**Placeholders**: NONE (TikZ already implemented). **Action items**: None. COMPLETE.
**Cross-ref note**: Speaker note references "Slide~36" (Shannon in Information Theory). Correct.

### Slide 33: The Softmax Function
**Placeholders**: NONE (TikZ already implemented). **Action items**: None. COMPLETE.

---

### Slide 34: Convergence Diagram Update -- Probability
**Placeholders**:
1. `[5cm]` -- Convergence diagram: nodes 1-3 lit

**Action items**:
1. **Convergence diagram variant 3**: Nodes 1-3 lit (`linalgTeal`, `calculusRed`, `probBlue`). Use `figures/convergence-3.pdf`.

---

### Slide 35: Section Divider -- Information Theory
**Placeholders**: NONE. **Action items**: None.

---

### Slide 36: Entropy -- Invented Three Times
**Current**: Three-column. Each column has a tcolorbox with a placeholder + text + formula.
**Placeholders**:
1. `[3cm]` -- Clausius: Steam engine diagram
2. `[3cm]` -- Boltzmann: Gas molecules in box + tombstone with S=k log W
3. `[3cm]` -- Shannon: Fair coin vs loaded coin + entropy formula diagram

**Action items** (all very small at 3cm -- keep extremely simple):
1. **TikZ mini-diagram (Clausius)**: Cylinder with piston, steam arrows, heat flow arrows (Q_in, Q_out). ~5 draws.

2. **TikZ mini-diagram (Boltzmann)**: Box with scattered dots (gas molecules). Below: tombstone inscription S = k log W. ~1 rectangle + ~10 small circles + 1 text node.

3. **TikZ mini-diagram (Shannon)**: Two sub-diagrams:
   - Fair coin: two equal bars (50/50). Label: "High entropy"
   - Loaded coin: one tall bar, one short (90/10). Label: "Low entropy"
   ~4 filled rectangles + labels.

**Portrait needed**: Clausius, Boltzmann, Shannon -- Shannon and Boltzmann are HIGH priority

---

### Slide 37: Cross-Entropy -- THE Loss Function
**Placeholders**: NONE. COMPLETE.

### Slide 38: Surprisal and Perplexity
**Placeholders**: NONE. COMPLETE.

### Slide 39: KL Divergence [EXTENDED]
**Placeholders**: NONE. COMPLETE.

### Slide 40: Tokenization
**Placeholders**: NONE. COMPLETE.

---

### Slide 41: Convergence Diagram Update -- Information Theory
**Placeholders**:
1. `[5cm]` -- Convergence diagram: nodes 1-4 lit

**Action items**:
1. **Convergence diagram variant 4**: Nodes 1-4 lit (`linalgTeal`, `calculusRed`, `probBlue`, `infoAmber`). Use `figures/convergence-4.pdf`.

---

### Slide 42: Section Divider -- Logic & Computation
**Placeholders**: NONE. **Action items**: None.

### Slide 43: Boolean Algebra
**Placeholders**: NONE. COMPLETE.

### Slide 44: The Dream and Its Limits -- Frege to Turing
**Placeholders**: NONE. COMPLETE.

### Slide 45: Von Neumann Architecture [EXTENDED]
**Placeholders**: NONE. COMPLETE.

### Slide 46: Floating Point Arithmetic
**Placeholders**: NONE. COMPLETE.

---

### Slide 47: GPU Computing
**Current**: Two-column. Left: text (NVIDIA, AlexNet) + insightbox. Right: one placeholder.
**Placeholders**:
1. `[5cm]` -- CPU vs GPU comparison: 4-16 powerful cores vs. 5000-16000 simple cores

**Action items**:
1. **TikZ diagram**: Side-by-side comparison using a PRACTICAL approach (not 100 explicit rectangles):
   - Left: "CPU" label. Draw 4 large colored squares (cores), each ~0.8cm. Label: "4-16 powerful cores"
   - Right: "GPU" label. Draw ONE large filled rectangle (~3cm x 2cm) in `logicGray!30` with a fine grid overlay drawn as 2 horizontal lines + 2 vertical lines (suggesting many cores). Inside the rectangle, place a centered label: "5,000-16,000 simple cores". Alternatively, draw a 5x5 grid of small squares (25 squares, not 100) as a representative schematic.
   - Below both: "Neural networks = parallel matrix math = perfect for GPU"
   **Key constraint**: Do NOT attempt 100 explicit TikZ rectangles. Use the filled-rectangle-with-overlay-label approach or a small representative grid (5x5 = 25 squares max).

**Portrait needed**: None

---

### Slide 48: Convergence Diagram Update -- Logic & Computation
**Placeholders**:
1. `[5cm]` -- Convergence diagram: nodes 1-5 lit

**Action items**:
1. **Convergence diagram variant 5**: Nodes 1-5 lit. Use `figures/convergence-5.pdf`.

---

<a id="part-3"></a>
## PART 3: Function Approx + Neuron + Sequence + Transformer + Scaling (Slides 49-78)

File: `llm-sections/part3-neuron-transformer-scaling.tex`
Frames in file: 30

---

### Slide 49: Section Divider -- Function Approximation
**Placeholders**: NONE. **Action items**: None.

---

### Slide 50: Fourier Series
**Current**: Two-column. Left: personbox (Fourier) + insightbox. Right: one placeholder.
**Placeholders**:
1. `[5.5cm]` -- Fourier approximation of square wave: 1 sine, 3 sines, 10 sines, 100 sines

**Action items**:
1. **pgfplots with precomputed data (HIGH PRIORITY)**: See [Fourier Square Wave Precomputation](#fourier-precompute) for the complete workflow. Four overlaid plots:
   - N=1: 1 term (smooth sine) -- `calculusRed!50`
   - N=3: 3 terms -- `calculusRed!70`
   - N=10: 10 terms -- `calculusRed`
   - N=100: 100 terms (nearly perfect, Gibbs phenomenon visible) -- `approxGreen`
   For N=1 and N=3, use inline `\addplot` with explicit sine sums. For N=10 and N=100, load precomputed data from `figures/fourier-data-10.csv` and `figures/fourier-data-100.csv`.
   Caption: "Any function = a sum of simple waves."

**Portrait needed**: Fourier -- MEDIUM

---

### Slide 51: Weierstrass Approximation [EXTENDED]
**Current**: Two-column. Left: personbox (Weierstrass) + insightbox. Right: one placeholder.
**Placeholders**:
1. `[5.5cm]` -- Wiggly function with polynomial approximations of increasing degree

**Action items**:
1. **pgfplots**: Plot `sin(3*x) + 0.5*cos(7*x)` with polynomial approximations:
   - Degree 3 (rough fit, dashed `approxGreen!50`)
   - Degree 7 (better, dashed `approxGreen!70`)
   - Degree 15 (close, solid `approxGreen`)
   - Caption: "Any continuous function can be approximated by a polynomial."
   Use explicit `\addplot` for each.

**Portrait needed**: Weierstrass -- LOW (extended slide)

---

### Slide 52: Universal Approximation Theorem
**Current**: Two-column. Left: two personboxes (Cybenko, Hornik). Right: one placeholder + text box.
**Placeholders**:
1. `[5cm]` -- Neural network with increasing hidden neurons fitting increasingly complex functions

**Action items**:
1. **pgfplots (practical approach)**: Four overlaid function plots showing increasing approximation quality:
   - Target function (solid black): a step function or wiggly curve
   - N=5 approximation (dashed, rough)
   - N=20 (less rough)
   - N=100 (close)
   This is more practical than 4 separate network diagrams. Use pgfplots with 4 curves of decreasing error.

**Portrait needed**: Cybenko, Hornik -- SKIP (no portrait space in layout)

---

### Slide 53: Convergence Diagram Update -- Function Approximation
**Placeholders**:
1. `[10cm]` -- Convergence diagram: 6 of 10 nodes active

**Action items**:
1. **Convergence diagram variant 6**: Nodes 1-6 lit. Use `figures/convergence-6.pdf`.

---

### Slide 54: Section Divider -- The Neuron & Depth
**Placeholders**: NONE. **Action items**: None.

---

### Slide 55: The McCulloch-Pitts Neuron
**Current**: Two-column. Left: two personboxes (McCulloch, Pitts). Right: one placeholder.
**Placeholders**:
1. `[5.5cm]` -- McCulloch-Pitts neuron: inputs x1,x2,x3 with weights, sum, threshold, output. Biological neuron alongside.

**Action items**:
1. **TikZ diagram (HIGH PRIORITY)**: Two side-by-side sub-diagrams:
   - Left (Mathematical neuron): 3 input circles (x1, x2, x3) with arrows labeled (w1, w2, w3) pointing to a central circle "sum". Arrow from sum to threshold box. Output arrow labeled "0 or 1".
   - Right (Biological neuron sketch): Cell body (filled circle), 3 dendrite lines as input, 1 axon line as output
   - Light dashed connection lines between corresponding parts
   ~10 nodes + ~10 arrows for the math neuron. Bio neuron: very schematic.

**Portrait needed**: McCulloch -- LOW; Pitts -- SKIP (very few photos exist)

---

### Slide 56: The Perceptron -- Rosenblatt
**Placeholders**:
1. `[5.5cm]` -- Photo of Mark I Perceptron hardware + perceptron learning algorithm

**Action items**:
1. **Historical photograph**: Mark I Perceptron.
   - Wikimedia search: "Mark I Perceptron" (US Navy/Cornell photos, likely public domain)
   - Use: `\includegraphics[width=5cm]{figures/mark-i-perceptron.jpg}`
   - Below: small TikZ diagram of the learning algorithm (3 boxes: present -> compare -> adjust). Simple 3-box flow.

**Portrait needed**: Rosenblatt -- MEDIUM

---

### Slide 57: The XOR Problem and AI Winter
**Placeholders**:
1. `[5.5cm]` -- Top: XOR truth table + scatter plot. Bottom: AI Winter timeline.

**Action items**:
1. **TikZ diagram**: Two parts:
   - Top: XOR scatter plot. 4 points: (0,0)=0, (0,1)=1, (1,0)=1, (1,1)=0. Color 0s and 1s differently. Dashed line showing "no single line separates them."
   - Bottom: Timeline arrow: 1969 -> 1986 with "AI Winter" label.
   ~4 nodes + 1 dashed line + 3 timeline nodes + 1 arrow.

**Portrait needed**: Minsky -- MEDIUM; Papert -- LOW

---

### Slide 58: Multi-Layer Networks -- The Comeback
**Placeholders**:
1. `[5cm]` -- Multi-layer network solving XOR

**Action items**:
1. **TikZ diagram**: 3-layer network:
   - 2 input nodes, 2-3 hidden nodes, 1 output node
   - Connection lines between all layers
   - Caption: "Two layers CAN separate XOR."
   ~6 nodes + ~10 connection lines.

**Portrait needed**: None

---

### Slide 59: Activation Functions
**Placeholders**:
1. `[5cm]` -- Three activation function curves: Sigmoid, ReLU, GELU

**Action items**:
1. **pgfplots (HIGH PRIORITY)**: Three overlaid function plots:
   - Sigmoid: `1/(1+exp(-x))`, dashed `neuronPink!60`, label "1980s-2000s"
   - ReLU: `max(0,x)`, solid `calculusRed`, label "2010s"
   - GELU: `x * 0.5 * (1 + tanh(sqrt(2/pi) * (x + 0.044715*x^3)))`, solid `aiViolet`, label "2016-present"
   x from -4 to 4, y from -1 to 4.

**Portrait needed**: None

---

### Slide 60: Residual Connections (ResNet)
**Placeholders**:
1. `[5.5cm]` -- Standard deep net (fading signal) vs. ResNet (skip connections)

**Action items**:
1. **TikZ diagram**: Two vertical stacks side by side:
   - Left ("Standard"): 5 rectangular layers, color fading from dark to very light
   - Right ("ResNet"): 5 layers, color consistent. Skip arrows bypassing each pair.
   - Below: Formula: input -> [layer] -> ADD input -> output
   ~10 rectangles + ~10 arrows + ~5 skip arrows.

**Portrait needed**: None

---

### Slide 61: Layer Normalization and Dropout
**Placeholders**:
1. `[5.5cm]` -- Top: Layer norm before/after. Bottom: Dropout network with crossed-out neurons.

**Action items**:
1. **TikZ diagram**: Two sub-diagrams stacked:
   - Top (Layer Norm): ~8 vertical bars. "Before": wildly different heights. Arrow. "After": centred heights. Label: "Layer Norm = rescale."
   - Bottom (Dropout): Small network (3 layers, ~3 nodes each). Some nodes with red X marks. Label: "Dropout = randomly disable during training."

**Portrait needed**: None

---

### Slide 62: Convergence Diagram Update -- The Neuron & Depth
**Placeholders**:
1. `[10cm]` -- Convergence diagram: 7 of 10 nodes active

**Action items**:
1. **Convergence diagram variant 7**: Nodes 1-7 lit. Use `figures/convergence-7.pdf`.

---

### Slide 63: Section Divider -- Sequence Modeling
**Placeholders**: NONE. **Action items**: None.

---

### Slide 64: Markov Chains
**Placeholders**:
1. `[5.5cm]` -- State diagram with word transitions + Markov text vs LLM text comparison

**Action items**:
1. **TikZ diagram**: Two parts:
   - Top: State diagram with 4 word nodes ("the", "cat", "sat", "on") connected by arrows with probability labels. ~4 nodes + ~6 arrows.
   - Bottom: Two text boxes comparing Markov output vs LLM output.

**Portrait needed**: Markov -- MEDIUM

---

### Slide 65: Hidden Markov Models
**Placeholders**:
1. `[5.5cm]` -- HMM diagram: hidden states top, observed outputs below

**Action items**:
1. **TikZ diagram**: Two rows of nodes:
   - Top: 3-4 hidden state circles connected by horizontal arrows
   - Bottom: 3-4 observed output rectangles connected to hidden states by vertical dashed arrows
   ~8 nodes + ~10 arrows.

**Portrait needed**: None

---

### Slide 66: Recurrent Neural Networks
**Placeholders**:
1. `[5.5cm]` -- RNN unrolled across time steps

**Action items**:
1. **TikZ diagram**: Unrolled RNN:
   - 3-4 copies of the same network block side by side
   - Each: input arrow below, output arrow above, hidden state arrow going RIGHT
   - Hidden state arrows get lighter (fading memory)
   - Labels: "word 1" through "word 4"
   ~12 nodes + ~16 arrows.

**Portrait needed**: None

---

### Slide 67: LSTM [EXTENDED]
**Placeholders**:
1. `[5.5cm]` -- Simplified LSTM cell

**Action items**:
1. **TikZ diagram (MEDIUM PRIORITY)**: Simplified LSTM cell:
   - Central "cell state" line running horizontally
   - Three gate boxes: "Forget gate", "Input gate", "Output gate"
   - Arrows from gates to cell state line
   - Input arrow from below, output arrow above
   ~8 nodes + ~10 arrows. Simplified, not the full LSTM diagram.

**Portrait needed**: Hochreiter, Schmidhuber -- LOW

---

### Slide 68: The Attention Mechanism -- KEY BREAKTHROUGH
**Placeholders**:
1. `[5.5cm]` -- Attention diagram: French->English with attention weights

**Action items**:
1. **TikZ diagram (HIGH PRIORITY)**: Two parts:
   - Top: French words left ("Le", "chat", "est", "sur", "le", "tapis"), English words right ("The", "cat", "is", "on", "the", "mat"). Lines of varying thickness. "chat"->"cat" thick, "tapis"->"mat" thick.
   - Bottom: Two comparison boxes: "RNN: compress into one vector" vs. "Attention: look back at everything"
   ~12 word nodes + ~15 connection lines + 2 comparison boxes.

**Portrait needed**: Bengio -- MEDIUM

**Convergence note**: Speaker note mentions "Sequence Modeling node lit in teal." This is variant 8 of the convergence diagram. See [Convergence Diagram Strategy -- Sections 8-9 Decision](#sections-8-9-decision).

---

### Slide 69: Section Divider -- The Transformer
**Placeholders**: NONE. **Action items**: None.
**Convergence note**: Speaker note says "8 of 10 nodes lit."

---

### Slide 70: "Attention Is All You Need"
**Placeholders**:
1. `[5cm]` -- First page of the paper + stylized author portraits

**Action items**:
1. **External image**: The paper title page:
   - The paper is freely available (arXiv:1706.03762). Create a stylized crop of the title area.
   - Below: 8 small gray silhouette circles (FontAwesome `\faUser` icons) representing the 8 authors, with names in tiny text below each. Do NOT use actual photographs unless individually licensed.
   - Use: `\includegraphics[width=4.5cm]{figures/attention-paper-title.png}` for the paper crop

**Portrait needed**: The 8 transformer authors. **Decision**: Use `\faUser` silhouette icons in a row. Individual photos are impractical for licensing and layout. Each silhouette labeled with the author's name in `\tiny` text.

---

### Slide 71: Self-Attention -- The Core Mechanism
**Placeholders**: NONE (all content is text/formula).
**Action items**: None. COMPLETE.

**Cross-reference verification (ALL references on this slide)**:
| Reference | Target | Correct? |
|-----------|--------|----------|
| "(Gibbs, Slide~10)" | Slide 10: The Dot Product | YES |
| "(cosine-like scaling, Slide~11)" | Slide 11: Cosine Similarity | YES |
| "(Boltzmann, Slide~33)" | Slide 33: The Softmax Function | YES |
| "(Cayley, Slide~9)" | Slide 9: Matrix Multiplication | YES |

---

### Slide 72: Feed-Forward Block and Multi-Head Attention
**Placeholders**:
1. `[5.5cm]` -- Single transformer block: Multi-Head Attention -> Add&Norm -> FFN -> Add&Norm

**Action items**:
1. **TikZ diagram (HIGH PRIORITY)**: Vertical stack forming one transformer layer:
   - Bottom: "Input" arrow
   - Box 1: "Multi-Head Self-Attention" (fill=`seqIndigo!20`, draw=`seqIndigo`)
   - Box 2: "Add & Norm" (fill=`neuronPink!15`, draw=`neuronPink`, with skip arrow from input)
   - Box 3: "Feed-Forward Network" (fill=`approxGreen!20`, draw=`approxGreen`)
   - Box 4: "Add & Norm" (fill=`neuronPink!15`, draw=`neuronPink`, with skip arrow)
   - Top: "Output" arrow
   - Each box labeled with origin: "(Bahdanau 2014)", "(He 2015 + Ba 2016)", "(Cybenko 1989)", "(He 2015 + Ba 2016)"
   ~6 boxes + 2 skip arrows + 2 through arrows.

**Cross-references verified**: "Cybenko, Slide~52" = correct, "Slide~59" (Hendrycks GELU) = correct, "Slides 60-61" (residual + layer norm) = correct.

---

### Slide 73: THE CLIMAX -- Full Annotated Transformer Diagram
**Placeholders**:
1. `[13cm]` -- FULL DECODER-ONLY TRANSFORMER with all components labeled

**Action items**:
1. **External image (HIGHEST PRIORITY)**: See [Exploded Transformer Diagram Strategy](#exploded-transformer-strategy). This is the ANNOTATED variant. Use `figures/exploded-transformer-annotated.pdf`.

**Cross-references in placeholder text (ALL verified)**:
| Component | Reference | Correct? |
|-----------|-----------|----------|
| Input Embedding | Slide~14 | YES (From Words to Numbers) |
| Positional Encoding | Slide~50 | YES (Fourier Series) |
| Self-Attention dot product | Slide~10 | YES (Dot Product) |
| Self-Attention softmax | Slide~33 | YES (Softmax) |
| Self-Attention matrix mult | Slide~9 | YES (Matrix Multiplication) |
| Self-Attention origin | Slide~68 | YES (Attention Mechanism) |
| Add & Norm (residual) | Slide~60 | YES (Residual Connections) |
| Add & Norm (layer norm) | Slide~61 | YES (Layer Norm & Dropout) |
| FFN (universality) | Slide~52 | YES (Universal Approximation) |
| FFN (GELU) | Slide~59 | YES (Activation Functions) |
| Dropout | Slide~61 | YES (Layer Norm & Dropout) |
| Output Softmax | Slide~33 | YES (Softmax) |
| GPU | Slide~47 | YES (GPU Computing) |

---

### Slide 74: Positional Encoding -- Fourier Meets Transformers
**Placeholders**:
1. `[5.5cm]` -- Heatmap of positional encodings

**Action items**:
1. **External image (MEDIUM-HIGH PRIORITY)**: Generate in Python:
   - Compute PE matrix for 100 positions x 64 dimensions
   - Plot as heatmap with matplotlib (viridis or RdBu colormap)
   - Clear sinusoidal patterns visible
   - Export as `figures/positional-encoding-heatmap.pdf`
   **Workflow**: Python script at `figures/gen-pe-heatmap.py`, run once, produces PDF.

---

### Slide 75: The Scaling Leap
**Placeholders**:
1. `[5.5cm]` -- Log-log plot of parameter count vs year + timeline

**Action items**:
1. **pgfplots (MEDIUM PRIORITY)**: Log-log scatter plot:
   - X: year (2018-2026), Y: parameter count (log scale, 100M to 1T+)
   - Points: GPT-1 (117M), GPT-2 (1.5B), GPT-3 (175B), PaLM (540B), GPT-4 (est. 1.8T)
   - Trend line
   Below: small TikZ timeline with labeled points for ChatGPT, GPT-4, Claude 3.

---

### Slide 76: Return to the Exploded Diagram
**Placeholders**:
1. `[13cm]` -- SAME exploded diagram from Slide 3, now with full annotations

**Action items**:
1. **External image (HIGH PRIORITY)**: Reuse the annotated variant from Slide 73: `figures/exploded-transformer-annotated.pdf`. This is the SAME image.

**Cross-references in placeholder text (ALL verified)**:
| Reference | Correct? |
|-----------|----------|
| Slide~9 (Cayley matrix mult) | YES |
| Slide~10 (Gibbs dot product) | YES |
| Slide~21 (Cauchy gradient descent) | YES |
| Slide~33 (Boltzmann softmax) | YES |
| Slide~37 (Shannon cross-entropy) | YES |
| Slide~22 (Rumelhart/Hinton/Williams backprop) | YES |
| Slide~59 (activation functions) | YES |
| Slide~60 (He residual connections) | YES |
| Slide~61 (Ba layer norm) | YES |
| Slides~68, 71 (self-attention) | YES |
| Slide~74 (Fourier positional encoding) | YES |
| Slide~47 (GPU computing) | YES |
| "Slide~3" (reference to opening) | YES |

---

### Slide 77: Convergence Diagram -- Final State
**Placeholders**:
1. `[10cm]` -- All 10 nodes lit, central "TRANSFORMER" glowing

**Action items**:
1. **Convergence diagram variant 10 (FINAL)**: All nodes lit in LLM section colors. Central node = "TRANSFORMER". Use `figures/convergence-10.pdf`.

---

### Slide 78: Closing -- The Story Is Not Over
**Placeholders**:
1. `[10cm]` -- Reprise of convergence diagram / exploded diagram

**Action items**:
1. **Reuse**: `\includegraphics[width=10cm]{figures/convergence-10.pdf}` (same as Slide 77).
   Below: "2,000+ years of mathematics. One machine. Your turn."

**Cross-references**: "Slide~77" and "Slide~3" in placeholder text -- both correct.

---

<a id="portrait-inventory"></a>
## Portrait Inventory

<a id="portrait-licensing"></a>
### Portrait Licensing Guidance

**Acceptable licenses for all downloaded images:**
- **Public domain** (preferred -- all pre-1900 portraits are almost certainly PD)
- **CC0** (Creative Commons Zero -- public domain equivalent)
- **CC-BY** (Creative Commons Attribution -- must credit author)
- **CC-BY-SA** (Creative Commons Attribution-ShareAlike -- must credit, derivative works must use same license)
- **US Government works** (for Mark I Perceptron photos from US Navy)

**NOT acceptable:**
- CC-NC (Non-Commercial) -- lecture materials may be distributed
- CC-ND (No Derivatives) -- cropping/resizing counts as derivative
- All Rights Reserved / no license stated
- Getty Images, Alamy, or other stock photo watermarked images

**Attribution tracking**: Maintain a file `figures/ATTRIBUTIONS.md` listing every downloaded image, its source URL, license, and attribution text. This file should be included with any distribution of the slides.

### Portraits RECOMMENDED

| Person | Slide(s) | Wikimedia Search Term | Likely License | Priority |
|--------|----------|-----------------------|----------------|----------|
| Hermann Grassmann | 6 | "Hermann Grassmann" | PD (pre-1900) | MEDIUM |
| William Rowan Hamilton | 6 | "William Rowan Hamilton portrait" | PD | LOW |
| Josiah Willard Gibbs | 7 | "Josiah Willard Gibbs" | PD | MEDIUM |
| Oliver Heaviside | 7 | "Oliver Heaviside" | PD | MEDIUM |
| Arthur Cayley | 8 | "Arthur Cayley mathematician" | PD | MEDIUM |
| James Joseph Sylvester | 8 | "James Joseph Sylvester" | PD | MEDIUM |
| Carl Friedrich Gauss | 9 | "Carl Friedrich Gauss portrait" | PD (Jensen painting) | MEDIUM |
| Leonhard Euler | 12 | "Leonhard Euler portrait" | PD (Handmann) | LOW |
| Augustin-Louis Cauchy | 12, 21 | "Augustin-Louis Cauchy" | PD | LOW |
| David Hilbert | 12 | "David Hilbert photograph" | PD | LOW |
| Archimedes | 18 | "Domenico Fetti Archimedes" | PD | MEDIUM |
| Pierre de Fermat | 19, 27 | "Pierre de Fermat" | PD | MEDIUM |
| Isaac Newton | 19 | "Isaac Newton Kneller portrait" | PD | MEDIUM |
| Gottfried Wilhelm Leibniz | 19 | "Gottfried Wilhelm Leibniz portrait" | PD (Francke) | MEDIUM |
| Geoffrey Hinton | 22 | "Geoffrey Hinton" | Check license | HIGH |
| Blaise Pascal | 27 | "Blaise Pascal portrait" | PD | MEDIUM |
| Jacob Bernoulli | 28 | "Jacob Bernoulli" | PD | MEDIUM |
| Claude Shannon | 32, 36 | "Claude Shannon" | Check license | HIGH |
| Ludwig Boltzmann | 33, 36 | "Ludwig Boltzmann photograph" | PD | HIGH |
| George Boole | 43 | "George Boole" | PD | MEDIUM |
| Alan Turing | 44 | "Alan Turing" | Check license | MEDIUM |
| Joseph Fourier | 50 | "Joseph Fourier portrait" | PD | MEDIUM |
| Frank Rosenblatt | 56 | "Frank Rosenblatt" | Check license | MEDIUM |
| Marvin Minsky | 57 | "Marvin Minsky" | Check license | MEDIUM |
| Andrey Markov | 64 | "Andrey Markov mathematician" | PD | MEDIUM |
| Yoshua Bengio | 68 | "Yoshua Bengio" | Check license | MEDIUM |

### Portraits NOT NEEDED (mentioned in text only, no visual space)

All persons listed in personboxes without dedicated portrait slots: Mikolov, Robbins, Monro, Kullback, Leibler, Zipf, Sennrich, Krizhevsky, Sutskever, Cybenko, Hornik, Kaiming He, Michael Jordan (ML), Jeffrey Elman, Bahdanau, Cho, Jared Kaplan, David Rumelhart, Ronald Williams, Verhulst, Linnainmaa, Walter Pitts, McCulloch, Papert, Hochreiter, Schmidhuber.

### 8 Transformer Authors (Slide 70)

**Decision**: Use FontAwesome `\faUser` silhouette icons in a row of 8, each labeled with the author's name. Do NOT attempt to source 8 individual photographs. Rationale: most are not on Wikimedia Commons, and individual licensing for 8 living researchers is impractical.

---

<a id="convergence-diagram-strategy"></a>
## Convergence Diagram Strategy

The convergence diagram appears 12 times (initial + 7 section updates + final + closing reuse + 2 for Sections 8-9). It must be consistent across all instances.

### DECISION: Sections 8-9 Gap (addresses Critic M5)

<a id="sections-8-9-decision"></a>
**Decision: Add convergence diagram thumbnails to existing slides, NOT new slides.**

Rationale: Adding 2 new slides would break all cross-references after Slide 68 and slow the climactic pacing. Instead:
- **Section 8 (Sequence Modeling)**: Add a small (3cm) convergence diagram thumbnail to Slide 68 (Attention Mechanism), alongside the speaker note that already mentions "Sequence Modeling node lit in teal." Place it in the bottom-right corner of the right column after the placeholder is replaced.
- **Section 9 (The Transformer)**: The section divider (Slide 69) already notes "8 of 10 nodes lit." Add a small (3cm) convergence thumbnail to Slide 69's `[plain]` frame, positioned in the bottom-right using TikZ overlay.

This means we need 12 convergence diagram PDFs (not 11):
- Variants 0-7 at regular sizes (as before)
- Variant 8 (thumbnail size) for Slide 68
- Variant 9 (thumbnail size) for Slide 69
- Variant 10 (full final) for Slides 77-78

### Recommended Approach: Standalone TikZ with 12 Compiled Variants

Create `figures/convergence-diagram.tex` (standalone document) that produces:
- `convergence-0.pdf` through `convergence-10.pdf` (11 full-size variants)
- `convergence-8-thumb.pdf` and `convergence-9-thumb.pdf` (thumbnail versions at 3cm width)

### Angular Specification

| Parameter | Value |
|-----------|-------|
| Layout | Semicircle (upper half) |
| Starting angle | 170 degrees (leftmost node = Section 1: Linear Algebra) |
| Ending angle | 10 degrees (rightmost node = Section 10: Scaling) |
| Angular spacing | 160 degrees / 9 gaps = ~17.8 degrees between nodes |
| Radius | 4.5cm (for full-size), 1.8cm (for thumbnail) |
| Center node | At origin (0,0) |
| Center node size | 1.2cm diameter (full), 0.5cm (thumb) |
| Outer node size | text width=2cm, minimum height=0.8cm (full); scaled proportionally for thumb |

### Node Positions (explicit angles, counterclockwise from right)

| Node # | Section | Angle | Color When Lit |
|--------|---------|-------|----------------|
| 1 | Linear Algebra | 170 deg | `linalgTeal` |
| 2 | Calculus & Optimization | 152 deg | `calculusRed` |
| 3 | Probability & Statistics | 134 deg | `probBlue` |
| 4 | Information Theory | 116 deg | `infoAmber` |
| 5 | Logic & Computation | 98 deg | `logicGray` |
| 6 | Function Approximation | 80 deg | `approxGreen` |
| 7 | The Neuron & Depth | 62 deg | `neuronPink` |
| 8 | Sequence Modeling | 44 deg | `seqIndigo` |
| 9 | The Transformer | 26 deg | `aiViolet` |
| 10 | Scaling to LLMs | 10 deg | `accentOrange` |
| Center | "?" / "TRANSFORMER" | 0,0 | white -> `aiViolet!20` fill |

### Legibility at 5cm Scale

At the smallest display size (5cm on convergence update slides), the following must remain legible:
- Node labels: use `\scriptsize` minimum (7pt at 5cm)
- Date ranges: can be omitted at thumbnail scale, shown only at full-size
- Node fill colors: must have sufficient contrast against gray/white background
- Center label: "?" at `\large` bold, "TRANSFORMER" at `\small` bold
- Arrows: 0.6pt minimum line width

### Diagram Where Used (Complete)

| Slide | Variant | Size | Notes |
|-------|---------|------|-------|
| 4 | 0 (initial) | [12cm] | Full-size, all gray |
| 16 | 1 | [6.5cm] | Half-size |
| 25 | 2 | [6.5cm] | Half-size |
| 34 | 3 | [5cm] | Compact |
| 41 | 4 | [5cm] | Compact |
| 48 | 5 | [5cm] | Compact |
| 53 | 6 | [10cm] | Large |
| 62 | 7 | [10cm] | Large |
| 68 | 8 (thumb) | [3cm] | Thumbnail in bottom-right corner |
| 69 | 9 (thumb) | [3cm] | Thumbnail on plain slide |
| 77 | 10 (final) | [10cm] | Full, all lit, "TRANSFORMER" |
| 78 | 10 (reuse) | [10cm] | Same as Slide 77 |

---

<a id="exploded-transformer-strategy"></a>
## Exploded Transformer Diagram Strategy

This is the MOST IMPORTANT visual in the lecture. It appears on Slides 3, 73, and 76.

### Variants

| Variant | File | Used On | Description |
|---------|------|---------|-------------|
| Base | `figures/exploded-transformer-base.pdf` | Slide 3 | Components visible but NOT annotated with names/dates. Intentionally overwhelming. |
| Annotated | `figures/exploded-transformer-annotated.pdf` | Slides 73, 76 | Same layout but every component labeled with person, year, slide number. |

### Complete Component Specification

The diagram shows a DECODER-ONLY transformer stack. From bottom to top:

| Stack Position | Component | Color (fill) | Color (border) | Label (Base) | Label (Annotated) |
|----------------|-----------|-------------|----------------|--------------|-------------------|
| 1 (bottom) | Input Text | white | black | "Input: The cat sat..." | same |
| 2 | Tokenizer | `logicGray!15` | `logicGray` | "Tokenizer" | "Tokenizer (BPE, Sennrich 2016)" |
| 3 | Embedding Layer | `linalgTeal!15` | `linalgTeal` | "Embedding" | "Embedding (Grassmann 1844, Mikolov 2013 -- Slide 14)" |
| 4 | Positional Encoding | `approxGreen!15` | `approxGreen` | "Positional Encoding" | "Positional Encoding (Fourier 1807 -- Slide 50)" |
| 5 | **Transformer Block** (repeated N times, show 3 with "x96" label): | | | | |
| 5a | Multi-Head Self-Attention | `seqIndigo!15` | `seqIndigo` | "Self-Attention" | "Self-Attention (Gibbs 1880s, Boltzmann 1870s, Cayley 1858, Bahdanau 2014 -- Slides 9,10,33,68)" |
| 5b | Add & Norm (first) | `neuronPink!15` | `neuronPink` | "Add & Norm" | "Add & Norm (He 2015 + Ba 2016 -- Slides 60-61)" |
| 5c | Feed-Forward Network | `approxGreen!20` | `approxGreen` | "FFN" | "FFN (Cybenko 1989, GELU Hendrycks 2016 -- Slides 52,59)" |
| 5d | Add & Norm (second) | `neuronPink!15` | `neuronPink` | "Add & Norm" | "Add & Norm (He 2015 + Ba 2016 -- Slides 60-61)" |
| 5e | Dropout (shown as dashed overlay on block) | `neuronPink!10` | `neuronPink!50` dashed | "Dropout" | "Dropout (Srivastava/Hinton 2014 -- Slide 61)" |
| 6 | Output Projection | `linalgTeal!15` | `linalgTeal` | "Linear Projection" | "Linear Projection (Cayley 1858 -- Slide 9)" |
| 7 | Softmax | `probBlue!15` | `probBlue` | "Softmax" | "Softmax (Boltzmann 1870s -- Slide 33)" |
| 8 (top) | Output Probabilities | white | `accentOrange` | "Next Word Probabilities" | same |

### Additional Elements (not in main stack)

| Element | Position | Color | Label (Annotated) |
|---------|----------|-------|-------------------|
| Skip connections | Arrows bypassing Attention and FFN blocks | `neuronPink` dashed | "(He 2015 -- Slide 60)" |
| Gradient descent arrows | Curved arrows from output back to all weights | `calculusRed` | "Backprop (Cauchy 1847, Linnainmaa 1970, RHW 1986 -- Slides 21-22)" |
| Loss function | Arrow from output to "Cross-Entropy Loss" box | `infoAmber` | "Cross-Entropy (Shannon 1948 -- Slide 37)" |
| GPU hardware | Small chip icon in bottom corner | `logicGray` | "GPU (NVIDIA CUDA 2007 -- Slide 47)" |

### Build Approach

Create as a standalone LaTeX document `figures/exploded-transformer.tex`:
- Uses the same `\definecolor` commands from `llm-building-blocks.tex`
- Produces TWO pages: page 1 = base, page 2 = annotated
- Extract as separate PDFs using `pdftk` or compile twice with a toggle flag
- Width: 12cm for Slide 3, 13cm for Slides 73/76 (scale with `\includegraphics[width=...]`)

### Legibility Constraints

- At 12-13cm width on a 16:9 projector, text must be readable from the back of a classroom
- Component labels: `\footnotesize` minimum (8pt)
- Annotation labels: `\scriptsize` (7pt) -- these are reference text, not primary labels
- Use color fills to distinguish blocks even if text is not readable at distance

---

<a id="fourier-precompute"></a>
## Fourier Square Wave Precomputation

### Workflow (addresses Critic M6)

**Problem**: The 100-term Fourier series involves 100 sine terms summed at each sample point. Inline pgfplots computation would be extremely slow to compile.

**Solution**: Precompute the data in Python, save as CSV, load into pgfplots.

**Step 1: Python script** -- `figures/gen-fourier-data.py`
```
Purpose: Generate CSV files for Fourier square wave approximation
Output files:
  - figures/fourier-data-10.csv  (10-term approximation, 500 sample points)
  - figures/fourier-data-100.csv (100-term approximation, 500 sample points)
Format: Two columns: x, y
x range: -pi to 3*pi (two full periods)
Formula: f(x) = sum_{k=1,3,5,...,2N-1} (4/(k*pi)) * sin(k*x)
```

**Step 2: Run script once**
```bash
cd figures/ && python gen-fourier-data.py
```

**Step 3: In the Beamer slide**, use pgfplots `\addplot table`:
```
\addplot[samples=200, thick, calculusRed!50] {(4/pi)*sin(deg(x))};           % N=1 inline
\addplot[samples=200, thick, calculusRed!70] {(4/pi)*(sin(deg(x)) + sin(3*deg(x))/3 + sin(5*deg(x))/5)};  % N=3 inline
\addplot[thick, calculusRed] table[col sep=comma]{figures/fourier-data-10.csv};   % N=10 from file
\addplot[thick, approxGreen] table[col sep=comma]{figures/fourier-data-100.csv};  % N=100 from file
```

This keeps compilation fast while showing the full progression.

---

<a id="prioritized-task-list"></a>
## Prioritized Task List

### HIGH PRIORITY (essential for lecture comprehension)

| # | Slide | Description | Type | Est. Effort |
|---|-------|-------------|------|-------------|
| H1 | 73, 76 | Full annotated transformer diagram (CLIMAX) | External TikZ/PDF | 3-4 hours |
| H2 | 3 | Exploded transformer base diagram (opening) | External TikZ/PDF (shares code with H1) | 1 hour (after H1) |
| H3 | 4,16,25,34,41,48,53,62,68,69,77,78 | Convergence diagram (12 variants) | Standalone TikZ | 3 hours (one-time design) |
| H4 | 14 | Embedding pipeline | TikZ | 1 hour |
| H5 | 55 | McCulloch-Pitts neuron | TikZ | 1 hour |
| H6 | 68 | Attention mechanism (translation) | TikZ | 1.5 hours |
| H7 | 72 | Single transformer block anatomy | TikZ | 1 hour |
| H8 | 59 | Activation function curves | pgfplots | 30 min |
| H9 | 50 | Fourier square wave approximation | pgfplots + precomputed CSV | 1 hour |

### MEDIUM PRIORITY (enhance understanding)

| # | Slide | Description | Type | Est. Effort |
|---|-------|-------------|------|-------------|
| M1 | 9 | Matrix mult = neural net layer | TikZ | 1.5 hours |
| M2 | 22 | Backprop forward/backward | TikZ | 1 hour |
| M3 | 2 | Smartphone + labeled arrows | TikZ | 30 min |
| M4 | 57 | XOR scatter plot + AI winter | TikZ | 30 min |
| M5 | 60 | Standard net vs ResNet | TikZ | 1 hour |
| M6 | 61 | Layer norm + dropout | TikZ | 1 hour |
| M7 | 74 | Positional encoding heatmap | Python + external PDF | 1 hour |
| M8 | 75 | Scaling log-log plot + timeline | pgfplots + TikZ | 1 hour |
| M9 | 67 | LSTM cell simplified | TikZ | 1 hour |
| M10 | 15 | Attention preview (Q,K,V flow) | TikZ | 1 hour |
| M11 | 66 | RNN unrolled | TikZ | 1 hour |
| M12 | 64 | Markov chain states | TikZ | 30 min |
| M13 | 65 | HMM diagram | TikZ | 30 min |
| M14 | 52 | Universal approximation curves | pgfplots | 30 min |
| M15 | 51 | Weierstrass polynomial approx | pgfplots | 30 min |
| M16 | 47 | CPU vs GPU (filled rectangle approach) | TikZ | 30 min |
| M17 | 58 | Multi-layer XOR network | TikZ | 30 min |
| M18 | 70 | Paper title + silhouettes | External image + TikZ | 30 min |

### LOW PRIORITY (decorative, extended slides)

| # | Slide | Description | Type | Est. Effort |
|---|-------|-------------|------|-------------|
| L1-L17 | Various | Small TikZ diagrams, portraits | Mixed | 30 min each |
| L18 | All | Download and integrate portraits | Wikimedia batch | 2-3 hours total |

---

<a id="cross-references"></a>
## Cross-Reference Verification (Complete)

Every `Slide~N` reference in the LaTeX source, verified against content slide numbering:

| Source File | Line | Reference | Points To | Correct? |
|-------------|------|-----------|-----------|----------|
| part1 | 110 | "Slide 73" (note) | Slide 73: Full Annotated Transformer | YES |
| part2 | 95 | "Slide~19" (note) | Slide 19: The Derivative (Fermat) | YES |
| part2 | 438 | "Slide~36" (note) | Slide 36: Entropy | YES |
| part2 | 675 | "Slide~32" (note) | Slide 32: Shannon's Language Models | YES |
| part3 | 401 | "Slide~22" (visible) | Slide 22: Backpropagation | YES |
| part3 | 449 | "Slide~22" (note) | Slide 22: Backpropagation | YES |
| part3 | 601 | "Slide~60" (visible) | Slide 60: Residual Connections | YES |
| part3 | 1042 | "Slide~10" (visible) | Slide 10: Dot Product | YES |
| part3 | 1044 | "Slide~11" (visible) | Slide 11: Cosine Similarity | YES |
| part3 | 1046 | "Slide~33" (visible) | Slide 33: Softmax | YES |
| part3 | 1049 | "Slide~9" (visible) | Slide 9: Matrix Multiplication | YES |
| part3 | 1101 | "Slide~52" (visible) | Slide 52: Universal Approximation | YES |
| part3 | 1137 | "Slide~14" (placeholder) | Slide 14: Embedding | YES |
| part3 | 1139 | "Slide~50" (placeholder) | Slide 50: Fourier Series | YES |
| part3 | 1141 | "Slide~10" (placeholder) | Slide 10: Dot Product | YES |
| part3 | 1141 | "Slide~33" (placeholder) | Slide 33: Softmax | YES |
| part3 | 1142 | "Slide~9" (placeholder) | Slide 9: Matrix Multiplication | YES |
| part3 | 1142 | "Slide~68" (placeholder) | Slide 68: Attention Mechanism | YES |
| part3 | 1144 | "Slide~60" (placeholder) | Slide 60: Residual Connections | YES |
| part3 | 1144 | "Slide~61" (placeholder) | Slide 61: Layer Norm & Dropout | YES |
| part3 | 1146 | "Slide~52" (placeholder) | Slide 52: Universal Approximation | YES |
| part3 | 1146 | "Slide~59" (placeholder) | Slide 59: Activation Functions | YES |
| part3 | 1147 | "Slide~61" (placeholder) | Slide 61: Layer Norm & Dropout | YES |
| part3 | 1149 | "Slide~33" (placeholder) | Slide 33: Softmax | YES |
| part3 | 1153 | "Slide~47" (placeholder) | Slide 47: GPU Computing | YES |
| part3 | 1320 | "Slide~3" (placeholder) | Slide 3: Exploded Transformer | YES |
| part3 | 1323-1337 | Slides 9,10,21,22,33,37,47,59,60,61,68,71,74 | (all verified individually above) | YES |
| part3 | 1416 | "Slide~77" and "Slide~3" | Slides 77 and 3 | YES |

**Note on Beamer frame numbers vs content slide numbers**: Because the interactive frame (Slide 13i) adds +1 to all subsequent Beamer frame numbers, the `Slide~N` references in the source do NOT match `\inserttotalframenumber`. However, these references are in speaker notes and placeholder descriptions (not programmatic `\ref{}` commands), so they refer to the CONTENT numbering used consistently throughout the source file comments. No off-by-one errors exist.

**Impact of session breaks**: The 2 session breaks in `llm-building-blocks.tex` add 2 more frames but do not affect content numbering since they are inserted between part files, not within them.

---

<a id="commit-strategy"></a>
## Commit Strategy

### Phase 1: Infrastructure (~2 hours)
- Create `figures/ATTRIBUTIONS.md` (empty template)
- Create `figures/convergence-diagram.tex` (standalone)
- Create `figures/exploded-transformer.tex` (standalone)
- Create `figures/gen-fourier-data.py`
- Create `figures/gen-pe-heatmap.py`
- Run Python scripts to generate CSV/PDF data files
- **Commit**: "Add diagram infrastructure: standalone TikZ sources, data generation scripts"

### Phase 2: High-Priority Visuals (~8 hours)
- Compile convergence diagram variants (12 PDFs)
- Compile exploded/annotated transformer diagrams (2 PDFs)
- Build embedding pipeline (Slide 14), neuron (Slide 55), attention (Slide 68), transformer block (Slide 72)
- Build activation function curves (Slide 59), Fourier series (Slide 50)
- **Commit**: "Add high-priority visuals: convergence diagrams, transformer diagrams, key TikZ"

### Phase 3: Medium-Priority Visuals (~8 hours)
- Build remaining TikZ diagrams (Slides 2, 9, 15, 22, 47, 57, 58, 60, 61, 64, 65, 66, 67)
- Generate external images (loss landscape, positional encoding heatmap)
- Build pgfplots charts (Weierstrass, universal approximation, scaling plot)
- **Commit**: "Add medium-priority visuals: remaining TikZ diagrams, pgfplots, external images"

### Phase 4: Low-Priority, Portraits & Polish (~4 hours)
- Download portraits from Wikimedia (batch, check licenses, update ATTRIBUTIONS.md)
- Build remaining small TikZ diagrams (Slides 6, 7, 8, 10, 11, 12, 13, 13i, 18, 19, 20, 21, 23)
- Add convergence thumbnails to Slides 68 and 69
- Final consistency pass: compile full document, verify all `\includegraphics` paths resolve
- **Commit**: "Add portraits, remaining visuals, and convergence thumbnails for Sections 8-9"

---

<a id="success-criteria"></a>
## Success Criteria

1. **Zero placeholders remain** -- every `\visualplaceholder` replaced with actual content
2. **All 12 convergence diagram variants** exist and are consistent (0-10 full-size + 2 thumbnails)
3. **Slides 3, 73, and 76** share a coherent transformer diagram (base + annotated variants)
4. **All cross-references** verified correct (see [Cross-Reference Verification](#cross-references))
5. **Convergence diagram colors** use the LLM section palette (`linalgTeal` through `seqIndigo`), NOT ad-hoc colors
6. **Lecture compiles cleanly** in Beamer with no TikZ errors
7. **All external images** have acceptable licenses documented in `figures/ATTRIBUTIONS.md`
8. **Projection test** -- all diagrams legible at 1024x768 or higher
9. **Frame count** verified at 79 content frames + 2 session breaks = 81 total Beamer frames
10. **GPU diagram (Slide 47)** uses filled-rectangle-with-label approach, NOT 100 explicit TikZ rectangles
11. **Fourier data** precomputed via Python script, not computed inline for N=100
12. **Sections 8-9 convergence gap** resolved with thumbnail overlays on Slides 68/69

# The Building Blocks of LLMs: A Mathematical History
## Comprehensive Slide-by-Slide Lecture Plan

## Context

**Original Request:** Create a companion lecture tracing every mathematical concept that powers modern Large Language Models back to its historical origin. A narrative from ancient mathematics to the transformer architecture, showing students that the "AI" they use daily is built from mathematics invented by real people over centuries.

**Target Audience:** High school seniors in mathematics -- the same audience as the main History of Mathematics lecture. They know algebra, geometry, trigonometry, and basic calculus concepts. They have likely used ChatGPT, Claude, or similar LLMs. They do NOT know linear algebra, probability theory, or neural network architecture in any formal way.

**Relationship to Main Lecture:** This is a standalone companion lecture that can be taught independently OR as a deep-dive extension after the main History of Mathematics lecture. It revisits some figures from the main lecture (Euler, Gauss, Cauchy, Shannon, Turing, Hinton) but from a completely different angle: "what did their work contribute to the machine you talk to every day?"

**Estimated Slide Count:** 78 slides (including title, section dividers, visual-only slides, interactive moments, and closing)

**Estimated Lecture Duration:** 95-105 minutes (with breaks), designed for 3-session delivery (recommended) or 2-session delivery (compressed).

**Named Mathematicians/Scientists:** 66

**Core Throughline:** "Every component of an LLM was invented by someone, for a specific purpose, often centuries before AI existed."

**Audience Takeaway:** "I already know some of this math -- I just didn't know it was inside my AI."

---

## Timing and Session Structure

### Per-Section Timing Estimates

| Section | Slides | Est. Minutes | Notes |
|---------|--------|-------------|-------|
| 0. Opening | 1-4 | 5 min | Hook + exploded diagram |
| 1. Linear Algebra | 5-16 | 15 min | The skeleton (now includes dot product + Word2Vec) |
| 2. Calculus & Optimization | 17-25 | 10 min | How it learns |
| **--- SESSION 1 BREAK ---** | | **~30 min** | Break after optimization |
| 3. Probability & Statistics | 26-34 | 10 min | Language of uncertainty |
| 4. Information Theory | 35-41 | 8 min | Measuring meaning |
| 5. Logic & Computation | 42-48 | 8 min | The substrate |
| **--- SESSION 2 BREAK ---** | | **~26 min** | Break after computation |
| 6. Function Approximation | 49-53 | 6 min | Why it works at all |
| 7. The Neuron & Depth | 54-62 | 10 min | Biology to math (now includes residual connections, layer norm, dropout) |
| 8. Sequence Modeling | 63-68 | 7 min | The path to language |
| 9. The Transformer | 69-74 | 9 min | Where everything converges (expanded) |
| 10. Scaling to LLMs + Closing | 75-78 | 5 min | The final leap |
| **--- SESSION 3 ---** | | **~37 min** | Sections 6-10 |
| **TOTAL** | 78 slides | ~93 min | |

### Session Split Points (3-Session Delivery -- RECOMMENDED)

- **Session 1 (Slides 1-25, ~30 min):** Opening through Calculus & Optimization. End on Slide 25 (Optimization Summary). Natural break: "We now know the skeleton of a neural network and how it learns. Next: how does it deal with uncertainty?"
- **Session 2 (Slides 26-48, ~26 min):** Probability through Logic & Computation. End on Slide 48 (GPU Computing). Natural break: "We have the math and the hardware. But can we actually build a brain?"
- **Session 3 (Slides 49-78, ~37 min):** Function Approximation through Closing. The payoff session -- everything converges into the transformer.

### 2-Session Split (Alternative -- COMPRESSED)

- **Session A (Slides 1-41, ~48 min):** Opening through Information Theory. Covers all the "pure math" building blocks. Tight pacing required.
- **Session B (Slides 42-78, ~45 min):** Logic & Computation through Closing. Covers the "building the machine" arc.

**Note:** The 2-session split is aggressive. Instructors should plan for 50+ minutes per session or liberally use the [EXTENDED] cuts below.

### Core vs. Extended Track

If short on time, the following slides can be **cut** (marked [EXTENDED]) without losing narrative coherence:

| Slide | Content | Why Cuttable |
|-------|---------|-------------|
| 12 | Eigenvalues deep dive | Can mention verbally |
| 21 | Cauchy's steepest descent detail | Covered in backprop narrative |
| 30 | Kolmogorov axioms | Conceptual, not essential to LLM story |
| 39 | KL divergence | Specialist interest |
| 46 | Von Neumann architecture detail | Can summarize verbally |
| 51 | Weierstrass approximation | Historical enrichment, not critical path |
| 67 | LSTM deep dive | Can mention en route to attention |

Cutting all [EXTENDED] slides yields ~71 slides (~82 min).

### Interactive Moments (3 planned)

1. **After Slide 13 (Embedding Space):** "Quick experiment" -- give students 3 words (king, queen, woman) and ask them to guess what "king - man + woman" equals in the AI's math. Reveal: queen. (2 min)
2. **After Slide 33 (Softmax):** Quick poll -- "What word comes next: 'The cat sat on the ___'?" Collect answers, show the AI's probability distribution over the same prompt. (2 min)
3. **After Slide 73 (Annotated Transformer):** "Count the building blocks" -- students try to identify which historical section each part of the transformer comes from. (3 min)

---

## Work Objectives

### Core Objective
Produce a complete slide-by-slide lecture plan tracing every mathematical building block of modern LLMs to its historical origin, with mathematicians, dates, contributions, visuals, and narrative connections -- ready for a slide designer to execute in LaTeX Beamer.

### Deliverables
1. Full slide-by-slide outline (78 slides)
2. Mathematician/scientist reference table (every person mentioned, with dates, origin, contribution)
3. Visual asset list (what image/diagram is needed per slide, with source suggestions)
4. Fact-check register (all claims needing verification)
5. "Connection arrow" for every section (how this math block flows into the LLM)
6. Recurring convergence diagram specification

### Definition of Done
- Every mathematician listed has: full name, life dates (or fl./c. dates), origin, contribution, connection to LLM
- Every slide has at least 1 visual described; most have 2
- Every factual claim is either well-established or tagged [VERIFY]
- Every section ends with a clear "connection arrow" to the transformer
- The convergence diagram is consistently updated across sections
- Every component labeled on the climax diagram (Slide 73) has been taught in an earlier slide

---

## Guardrails

### Must Have
- Person-centric narrative (mathematicians as protagonists whose work ended up inside LLMs)
- [VERIFY] tag on any claim with <95% confidence
- At least 2 visuals per section (diagrams, portraits, manuscripts, conceptual illustrations)
- Engaging tone for 17-18 year olds who USE LLMs daily
- "Connection arrow" on every section: explicit link from historical math to transformer component
- Recurring "convergence diagram" visual motif showing cumulative building blocks
- Accessible explanations -- no formal prerequisites beyond high school math
- **Formula scaffolding rule:** Every formula shown on a slide must be classified as either FORMAL (shown as typeset math with all notation explained beforehand) or CONCEPTUAL (shown as a "recipe" in words/pseudocode with the formal version in a small inset or speaker note). Default to CONCEPTUAL unless the audience has been prepared for the notation.

### Must NOT Have
- Invented dates or attributions
- University-level notation without explanation (no unexplained summation/integral symbols, matrix transpose, or nested exponentiation)
- Walls of text on slides (visual-heavy, text-light)
- Condescending tone about the audience's math level
- Hype language about AI ("revolutionary", "groundbreaking") -- let the math speak
- Claims that LLMs "understand" or "think" -- stay precise about what the math does
- Components on the climax transformer diagram (Slide 73) that have not been taught earlier

---

## RECURRING VISUAL MOTIF: THE CONVERGENCE DIAGRAM

**Design:** A single diagram that grows across the lecture. It starts empty in Slide 4 and fills in as each section completes. The final version (Slide 73) shows all 10 building blocks feeding into a central "Transformer" node.

**Layout:**
- Central node: "TRANSFORMER" (large, bold)
- 10 surrounding nodes arranged in a circle/arc, each labeled with a building block
- Color-coded to match section colors
- Arrows from each block to the transformer, labeled with what that block contributes

**Progression:**
- Slide 4: Empty diagram with 10 gray placeholder nodes, central "?" node
- After Section 1 (Slide 16): Linear Algebra node lights up. Label: "Matrix multiplication = neural network layers"
- After Section 2 (Slide 25): Calculus node lights up. Label: "Gradient descent = how it learns"
- After Section 3 (Slide 34): Probability node lights up. Label: "Softmax = next-token prediction"
- After Section 4 (Slide 41): Information Theory node lights up. Label: "Cross-entropy = the loss function"
- After Section 5 (Slide 48): Computation node lights up. Label: "GPUs = the hardware"
- After Section 6 (Slide 53): Function Approximation node lights up. Label: "Universal approximation = why it works"
- After Section 7 (Slide 62): The Neuron & Depth node lights up. Label: "Activation + normalization + residuals = deep networks"
- After Section 8 (Slide 68): Sequence Modeling node lights up. Label: "Attention = context"
- Slide 73: ALL nodes lit. Central "?" becomes "TRANSFORMER". Full diagram with all labels.
- Slide 78: Final reprise with closing message.

---

## SECTION 0: OPENING (Slides 1-4)

### Slide 1: Title Slide
- **Title:** "The Building Blocks of LLMs: A Mathematical History"
- **Subtitle:** "From Archimedes to Attention: 2,000+ Years of Mathematics Inside Your AI"
- **Visual:** Split image -- on the left, a mosaic of historical mathematicians' portraits (Archimedes, Euler, Gauss, Bayes, Shannon, Turing); on the right, a modern chat interface with an LLM. A translucent "bridge" of mathematical symbols connects them.
- **Design note:** Use the same Beamer theme (Madrid, whale colorscheme) and color palette as the main lecture, but add a new accent color (a deep neural-network purple, `aiViolet` from existing palette) for LLM-specific content.

### Slide 2: "What's Inside Your AI?"
- **Key message:** When you type a question to ChatGPT or Claude, the machine that answers you is built entirely from mathematics. Not magic. Not "intelligence." Math. Specific math, invented by specific people, at specific times.
- **Visual:** A smartphone screen showing a chat with an AI. Floating around it, labeled arrows pointing to different parts of the response, each labeled with a branch of mathematics: "Linear Algebra," "Calculus," "Probability," "Information Theory," etc.
- **Talking point:** "You already know some of this math. You just don't know it's inside your AI yet. Today we're going to fix that."

### Slide 3: The Exploded Diagram -- What We Will Build Today
- **Key message:** By the end of this lecture, you will be able to look at this diagram and understand every piece.
- **Visual:** The "exploded diagram" of a transformer architecture, with each component labeled and color-coded by mathematical origin:
  - Matrix multiplication layers (Linear Algebra -- blue)
  - Dot product scores (Linear Algebra -- blue)
  - Gradient descent arrows (Calculus -- green)
  - Softmax probability bars (Probability -- orange)
  - Cross-entropy loss (Information Theory -- red)
  - Boolean gates / GPU chips (Logic & Computation -- gray)
  - Activation function curves (Function Approximation -- purple)
  - Neuron nodes (The Neuron -- yellow)
  - Residual connections / skip arrows (The Neuron & Depth -- yellow)
  - Layer normalization (The Neuron & Depth -- yellow)
  - Attention arrows (Sequence Modeling -- teal)
- **Design note:** This is intentionally overwhelming on first view. The lecture will "decode" it piece by piece. Return to this diagram in Slide 73 with full understanding.
- **Speaker note:** "This looks complicated right now. By the end of today, you'll know what every one of these pieces does and WHO invented it."

### Slide 4: The Convergence Diagram -- Our Roadmap
- **Key message:** Ten branches of mathematics, developed over more than two millennia, all converge in one architecture: the transformer.
- **Visual:** The convergence diagram in its initial state -- 10 gray nodes arranged in a semicircle around a central "?" node. Each gray node is labeled with a section name and a date range:
  1. Linear Algebra (1809-1900s)
  2. Calculus & Optimization (c. 250 BCE-1986)
  3. Probability & Statistics (1654-1933)
  4. Information Theory (1865-1948)
  5. Logic & Computation (1854-1970s)
  6. Function Approximation (1807-1991)
  7. The Neuron & Depth (1943-2016)
  8. Sequence Modeling (1906-2014)
  9. The Transformer (2017)
  10. Scaling to LLMs (2018-2026)
- **Talking point:** "We're going to light up these nodes one by one. Each one is a piece of math that somebody invented, often for a completely different purpose, that ended up inside the machines you use every day."

---

## SECTION 1: LINEAR ALGEBRA -- "The Skeleton of Neural Networks" (Slides 5-16)

**Section color:** Blue (matching `digitalBlue` from existing palette)
**Connection arrow:** Matrix multiplication IS the fundamental operation of every neural network layer. When an LLM processes your sentence, it is literally multiplying matrices.

### Slide 5: Section Divider -- "Linear Algebra: The Skeleton"
- **Visual:** Section title overlaid on an abstract visualization of matrix multiplication (cascading grids of numbers transforming). Convergence diagram in corner with Section 1 node pulsing.
- **Timeline marker:** 1809-1900s (origin of modern formalism), but roots in Gauss and earlier
- **Tagline:** "Neural networks are, at their core, matrix multiplication machines."

### Slide 6: What Is a Vector? -- Forces, Velocities, and Words
- **Key message:** A vector is a list of numbers that represents something. Physicists used vectors for forces and velocities. In an LLM, a vector represents a WORD.
- **Historical persons:**
  - **Hermann Grassmann** (1809-1877, Stettin, Prussia). Published "Die lineale Ausdehnungslehre" (1844), the first general theory of vector spaces in arbitrary dimensions. A schoolteacher whose work was so ahead of its time that almost nobody read it. [VERIFY: confirm 1844 publication date and characterization of reception]
  - **Sir William Rowan Hamilton** (1805-1865, Dublin, Ireland). Invented quaternions (1843) while walking along the Royal Canal in Dublin, famously carving the formula i^2 = j^2 = k^2 = ijk = -1 into Brougham Bridge. Quaternions were an early system of "extended numbers" that acted like vectors in 3D/4D.
- **Visual 1:** Portrait of Grassmann alongside a page from his Ausdehnungslehre
- **Visual 2:** The plaque on Brougham Bridge showing Hamilton's quaternion formula; a diagram showing a 2D vector as an arrow, then a 3D vector, then a "768-dimensional vector" (fading dots)
- **Talking point:** "Hamilton was so excited that he carved his formula into a bridge. Grassmann's far more general idea was ignored for decades. Both were building the language that neural networks would eventually speak."
- **LLM connection:** "In an LLM, every word is converted into a vector -- a list of numbers, often 768 or more. This is called an 'embedding.' Grassmann's abstract vector spaces ARE the embedding spaces of modern AI."

### Slide 7: Modern Vector Notation -- Gibbs and Heaviside
- **Key message:** The vector notation we use today (boldface letters, dot product, cross product) was shaped by two physicists who simplified Hamilton's quaternions.
- **Historical persons:**
  - **Josiah Willard Gibbs** (1839-1903, New Haven, Connecticut, USA). Yale physicist who extracted the useful vector parts from Hamilton's quaternions and created modern vector analysis (~1881-1884, privately printed lecture notes "Elements of Vector Analysis").
  - **Oliver Heaviside** (1850-1925, London, England). Self-taught electrical engineer who independently developed vector calculus and used it to reformulate Maxwell's equations into the compact form we use today.
- **Visual:** Side-by-side: Hamilton's quaternion notation vs. Gibbs's vector notation for the same operation. The simplification is visually obvious.
- **Talking point:** "Gibbs and Heaviside were not trying to build AI. They were trying to make physics easier to write down. But their notation is exactly what we use to describe neural networks today."
- **[VERIFY]:** Gibbs's lecture notes are typically dated 1881-1884. Confirm the exact years of the two printings.

### Slide 8: Matrices -- Cayley and Sylvester
- **Key message:** A matrix is a grid of numbers. Neural networks are built from matrices. The mathematical theory of matrices was created in the 1850s.
- **Historical persons:**
  - **Arthur Cayley** (1821-1895, Richmond, Surrey, England). Published "A Memoir on the Theory of Matrices" (1858), establishing matrices as algebraic objects in their own right. Also a practicing lawyer for 14 years before returning to academia.
  - **James Joseph Sylvester** (1814-1897, London, England). Coined the word "matrix" (1850), from the Latin for "womb" -- because he saw a matrix as a "womb" from which determinants were born. Also coined "discriminant," "invariant," and many other mathematical terms.
- **Visual 1:** A simple 3x3 matrix, annotated: "This is a matrix. Cayley (1858) made it into a mathematical object."
- **Visual 2:** An LLM weight matrix (much larger, represented schematically): "This is also a matrix. It has millions of entries. Same math."
- **Talking point:** "Sylvester literally named it. 'Matrix' -- from Latin for 'womb.' He thought of it as something that gives birth to numbers. He had no idea it would give birth to AI."
- **LLM connection:** "Every layer in a neural network is defined by a matrix of 'weights.' When your prompt passes through GPT, it is multiplied by dozens of these matrices. Each one was learned during training."
- **[VERIFY]:** Cayley's 1858 paper title. Sylvester's coinage of "matrix" in 1850 -- some sources say 1848. Verify the exact year and publication.

### Slide 9: Matrix Multiplication -- The Core Operation
- **Key message:** Matrix multiplication is the single most important operation in deep learning. Every neural network layer is a matrix multiplication followed by a nonlinear function.
- **Historical connection:** Earlier work by **Carl Friedrich Gauss** (1777-1855, Brunswick, Germany) on Gaussian elimination (solving systems of linear equations) laid groundwork for computational linear algebra. Gauss used these methods for astronomical calculations in the early 1800s. [VERIFY: Gauss's elimination method is typically dated to his work on least squares / asteroid orbit calculations, c. 1809-1810, though the method has earlier precedents in Chinese mathematics]
- **Visual 1:** Animated (or step-by-step) diagram of matrix multiplication: a 3x3 matrix times a 3x1 vector, showing dot products row by row
- **Visual 2:** The SAME operation drawn as a neural network layer: inputs on the left, weights as connections, outputs on the right. Caption: "Same math. Different picture."
- **Talking point:** "Every time you send a message to an AI, your words pass through about 96 layers. Each layer multiplies your data by a matrix. That's roughly 96 matrix multiplications just to generate one word of the response."
- **Speaker note:** Emphasize that this is not an analogy -- neural network layers ARE matrix multiplications. The connection is literal and exact.

### Slide 10: The Dot Product -- Measuring Similarity
- **Key message:** The dot product of two vectors produces a single number that measures how "aligned" or "similar" the vectors are. This is the operation at the heart of attention.
- **Mathematical content (CONCEPTUAL):** Show the dot product as a "recipe":
  1. Take two lists of numbers (vectors), same length
  2. Multiply matching entries: first times first, second times second, etc.
  3. Add up all the products
  4. The result is ONE number: big positive = very similar, near zero = unrelated, big negative = opposites
  - **Small inset (formal):** a . b = a1*b1 + a2*b2 + ... + an*bn
- **Historical connection:** The dot product (inner product) was formalized as part of vector analysis by **Gibbs** (1880s) and was implicit in earlier work on projections and angles by Grassmann and others.
- **Visual 1:** Two 2D arrows. When they point the same direction, the dot product is large and positive. When perpendicular, it is zero. When opposite, it is large and negative. Caption: "The dot product measures how much two vectors agree."
- **Visual 2:** In the LLM context: "The Query vector for 'it' and the Key vector for 'cat' have a large dot product. The model attends 'it' to 'cat.' This is how it figures out what 'it' refers to."
- **Talking point:** "The dot product is the simplest possible measure of similarity between two vectors. Multiply matching entries and add up. That's it. This tiny operation, repeated billions of times, is what lets an LLM understand which words relate to which."
- **LLM connection:** "In the attention mechanism, the dot product of a Query vector and a Key vector determines how much 'attention' one word pays to another. Every attention score in every LLM is a dot product."

### Slide 11: Cosine Similarity -- Dot Product Normalized
- **Key message:** Cosine similarity is the dot product divided by the lengths of both vectors. It measures the ANGLE between vectors, ignoring their magnitude. This is how embedding similarity is typically measured.
- **Mathematical content (CONCEPTUAL):** "Recipe: compute the dot product, then divide by the length of each vector. The result is always between -1 (opposite) and +1 (identical direction). Think of it as: how much do these two vectors point the same way?"
  - **Small inset (formal):** cos(theta) = (a . b) / (|a| * |b|)
- **Visual:** A 2D embedding space with word vectors. "King" and "queen" are close together (high cosine similarity). "King" and "banana" are far apart (low cosine similarity). Angle arcs drawn between them. Caption: "Cosine similarity = the angle between word vectors."
- **Talking point:** "When you ask an LLM to find 'similar words,' it computes cosine similarity in embedding space. The math is from the 1880s. The application is from last Tuesday."

### Slide 12: Eigenvalues and Eigenvectors [EXTENDED]
- **Key message:** Eigenvalues reveal the "natural modes" of a transformation. They appear in dimensionality reduction (PCA), which is used in understanding and compressing neural network representations.
- **Historical persons:**
  - **Leonhard Euler** (1707-1783, Basel, Switzerland / St. Petersburg, Russia / Berlin, Prussia). First encountered eigenvalue-like concepts in the study of vibrating strings and rotating bodies (1740s-1750s).
  - **Augustin-Louis Cauchy** (1789-1857, Paris, France). Proved that symmetric matrices have real eigenvalues (1829), a foundational result.
  - **David Hilbert** (1862-1943, Konigsberg/Gottingen, Germany). Extended eigenvalue theory to infinite-dimensional spaces (spectral theory, early 1900s), which connects to modern functional analysis used in machine learning theory.
- **Visual:** A 2D transformation shown as arrows: most arrows change direction, but the eigenvector arrows only stretch or shrink. Caption: "Eigenvectors are the directions a transformation doesn't rotate."
- **LLM connection:** "Principal Component Analysis (PCA), which uses eigenvalues, is used to visualize and understand what LLMs learn. When researchers ask 'what does this neuron represent?', eigenvalue analysis helps answer."
- **[VERIFY]:** Euler's eigenvalue work -- the precise context (vibrating membranes vs. rotating bodies) and dates should be verified. Cauchy's 1829 result on symmetric matrices.

### Slide 13: High-Dimensional Spaces -- Where Words Live
- **Key message:** LLMs represent words as vectors in spaces with hundreds or thousands of dimensions. This sounds impossible to visualize, but the math works the same as in 2D or 3D.
- **Connection to curse of dimensionality:** **Richard Bellman** (1920-1984, New York City, USA). Coined "the curse of dimensionality" (1957) in the context of dynamic programming. In high dimensions, data becomes sparse, and distances behave counterintuitively. [VERIFY: verify Bellman coined this in 1957 and the exact context -- may be from his 1961 book "Adaptive Control Processes"]
- **Visual 1:** A 2D plot showing word embeddings projected down: "king," "queen," "man," "woman" as points, with the famous analogy arrow: king - man + woman = queen
- **Visual 2:** A caption: "This is a projection from 768 dimensions down to 2. In the full space, THOUSANDS of such relationships exist simultaneously."
- **Attribution:** This vector arithmetic on words was demonstrated by **Tomas Mikolov** and colleagues in their **Word2Vec** system (2013). Mikolov et al. published "Efficient Estimation of Word Representations in Vector Space" (2013, arXiv) and "Distributed Representations of Words and Phrases and their Compositionality" (2013, NeurIPS), showing that word vectors trained on large corpora capture semantic relationships as linear directions. The king-queen analogy became the iconic demonstration. [VERIFY: confirm both Mikolov et al. 2013 papers and their venues]
- **Interactive moment:** "Quick experiment" -- ask students what "king - man + woman" should equal. Reveal: the AI says "queen." This works because of the geometry of high-dimensional vector spaces, as Mikolov's Word2Vec demonstrated.
- **Talking point:** "In 768 dimensions, words that mean similar things end up near each other. 'Dog' is near 'puppy.' 'Paris' is near 'France.' The AI doesn't know what these words mean -- it only knows their coordinates. But the coordinates capture meaning. Mikolov showed this in 2013 and it stunned the field."

### Slide 14: From Words to Numbers -- The Embedding
- **Key message:** The process of converting a word to a vector is called "embedding." This is where Grassmann's abstract vector spaces meet natural language.
- **Historical lineage:** Grassmann (1844, abstract vector spaces) -> Mikolov (2013, Word2Vec learned embeddings) -> Modern LLM embedding layers (2017-present, learned jointly with the transformer)
- **Visual:** Step-by-step diagram:
  1. User types: "The cat sat on the mat"
  2. Tokenizer splits it: ["The", "cat", "sat", "on", "the", "mat"]
  3. Each token becomes a vector: [0.23, -0.87, 0.44, ...] (768 numbers)
  4. The sentence becomes a MATRIX: 6 rows (tokens) x 768 columns (dimensions)
- **Caption:** "Your sentence is now a matrix. Everything that follows is linear algebra."
- **Talking point:** "Grassmann imagined abstract spaces with any number of dimensions. Cayley gave us matrices. Mikolov showed words could live in those spaces. Now, 170 years after Grassmann, your words live in his spaces."

### Slide 15: Attention as Matrix Multiplication (Preview)
- **Key message:** The attention mechanism -- the core innovation of the transformer -- is fundamentally three matrix multiplications (Query, Key, Value) plus a dot product similarity step.
- **Visual:** Simplified attention diagram:
  1. Input matrix X (sentence as matrix)
  2. Multiply by W_Q to get Queries
  3. Multiply by W_K to get Keys
  4. Multiply by W_V to get Values
  5. Attention scores = dot product of each Query with each Key (Slide 10!)
  6. Normalize scores with softmax (we will learn this in Section 3)
  7. Output = scores times Values
  8. Label each operation: "matrix multiplication (Cayley)", "dot product (Gibbs/Slide 10)", "softmax (Boltzmann/Section 3)"
- **Mathematical content (CONCEPTUAL):** Show as a pipeline recipe, NOT as the formal equation. The formal version Attention = softmax(Q * K^T / sqrt(d)) * V goes in a small inset labeled "Formal notation (we'll unpack this later)" with a note: "K^T means 'flip the matrix on its side' (transpose). sqrt(d) is a scaling factor to keep numbers from getting too large."
- **Talking point:** "The 'attention' mechanism -- the thing that lets an AI understand context -- is three matrix multiplications, a dot product, and a softmax. That's it. The math was all invented by the 1880s. The architecture was invented in 2017."
- **Speaker note:** This slide is a preview. We will return to attention in detail in Section 9. The point here is to show students early that "attention" is not magic -- it is the linear algebra they just learned about. Do NOT let students get stuck on the formal equation; the conceptual pipeline is what matters here.

### Slide 16: Convergence Diagram Update -- Linear Algebra
- **Visual:** The convergence diagram from Slide 4. The "Linear Algebra" node now lights up in blue. Label appears: "Matrix multiplication = neural network layers."
- **Summary box:**
  - Grassmann (1844): Vector spaces
  - Hamilton (1843): Quaternions / extended number systems
  - Gibbs/Heaviside (1880s-1900s): Modern vector notation, dot product
  - Cayley (1858): Matrix theory
  - Sylvester (1850): Named "matrix"
  - Gauss (early 1800s): Gaussian elimination
  - Mikolov (2013): Word2Vec -- words as vectors
- **Connection arrow:** "Every layer of an LLM is a matrix multiplication. Every attention score is a dot product. The math of 1850 is the engine of 2026."
- **Transition:** "Now we have the skeleton. But a skeleton doesn't move. For that, we need calculus."

---

## SECTION 2: CALCULUS & OPTIMIZATION -- "How Neural Networks Learn" (Slides 17-25)

**Section color:** Green (matching `enlightenmentTeal` or a new calculus green)
**Connection arrow:** Gradient descent + backpropagation IS how neural networks learn from data. Without calculus, you can build the network but cannot train it.

### Slide 17: Section Divider -- "Calculus & Optimization: How It Learns"
- **Visual:** Section title overlaid on a 3D loss landscape (a rugged mountainous surface with a ball rolling downhill). Convergence diagram in corner with Section 2 node pulsing.
- **Timeline marker:** c. 250 BCE - 1986
- **Tagline:** "A neural network learns by rolling downhill on a landscape made of calculus."

### Slide 18: Roots in Antiquity -- Archimedes and Infinitesimals
- **Key message:** The idea of breaking things into infinitely small pieces goes back to antiquity.
- **Historical person:**
  - **Archimedes of Syracuse** (c. 287-212 BCE, Syracuse, Sicily). His "method of exhaustion" calculated areas and volumes by approximating them with ever-finer polygons -- a precursor to integration. His lost "Method" manuscript (rediscovered in 1906 in the Archimedes Palimpsest) shows he used infinitesimal reasoning more explicitly than previously known.
- **Visual:** Archimedes' method of exhaustion: a circle with inscribed polygons (4 sides, 8 sides, 16 sides, 32 sides), converging to the circle's area. Caption: "The core idea of calculus: approximate with simple pieces, take the limit."
- **Talking point:** "Archimedes was doing proto-calculus in the 3rd century BCE, 1,900 years before Newton."

### Slide 19: The Derivative -- Measuring Change
- **Key message:** A derivative measures how fast something is changing. Neural network training asks: "if I change this weight slightly, how much does the error change?" That's a derivative.
- **Historical persons:**
  - **Pierre de Fermat** (1601-1665, Beaumont-de-Lomagne, France). Developed a method for finding tangent lines to curves (c. 1636-1638) that anticipated the derivative. He found maxima and minima by setting a difference quotient to zero.
  - **Isaac Newton** (1642-1726/27, Woolsthorpe, England). Developed "the method of fluxions" (c. 1665-1666), his version of calculus, to describe rates of change. Motivated by physics: velocities, accelerations, planetary motion.
  - **Gottfried Wilhelm Leibniz** (1646-1716, Leipzig, Germany). Independently developed calculus (published 1684-1686) with the notation (dy/dx, integral sign) we still use today.
- **Visual 1:** Fermat's tangent method (geometric diagram), Newton's fluxion notation, Leibniz's dy/dx -- three notations for the same idea
- **Visual 2:** A simple curve with a tangent line, labeled: "The derivative = the slope of this line = how fast things are changing"
- **Talking point:** "Newton and Leibniz famously fought over who invented calculus. Fermat was doing something similar decades earlier. None of them imagined that 300 years later, derivatives would be computed trillions of times to train a chatbot."
- **LLM connection:** "Training an LLM means computing derivatives of the error with respect to every single weight -- billions of weights, billions of derivatives, repeated millions of times."
- **Speaker note:** Fermat also appears in Section 3 (Probability) with Pascal. When he comes up again, note: "Fermat again! He contributed to both calculus and probability -- two separate pillars of the LLM."

### Slide 20: The Chain Rule -- The Key to Backpropagation
- **Key message:** The chain rule says: if y depends on u and u depends on x, then dy/dx = (dy/du) * (du/dx). This simple rule is the mathematical foundation of backpropagation.
- **Historical attribution:** The chain rule was developed as part of the general framework of calculus. Leibniz used the chain rule implicitly; it was made explicit in the work of various 18th and 19th century mathematicians. [VERIFY: the precise attribution of the chain rule is diffuse -- Leibniz, Euler, and others all used it. No single "inventor."]
- **Visual:** A pipeline diagram:
  - x -> [function f] -> u -> [function g] -> y
  - Below it: "If the error changes y, how much did x contribute? Multiply along the chain."
  - Then the SAME diagram labeled as a neural network: "Input -> Layer 1 -> Hidden -> Layer 2 -> Output"
  - Below: "Backpropagation uses the chain rule to figure out which weights to blame for the error."
- **Mathematical content (CONCEPTUAL):** Show as "Recipe: To find how much x affected y through a chain, multiply the effects at each step." The formal dy/dx = (dy/du)(du/dx) appears as a small inset.
- **Talking point:** "Backpropagation -- the algorithm that trains every neural network -- is 'just' the chain rule applied over and over, layer by layer, backwards through the network. It's calculus class, running at scale."

### Slide 21: Gradient Descent -- Rolling Downhill [EXTENDED]
- **Key message:** Gradient descent is an optimization method: compute the gradient (multivariable derivative), then take a small step in the direction that decreases the error.
- **Historical person:**
  - **Augustin-Louis Cauchy** (1789-1857, Paris, France). Published the first description of the method of steepest descent (1847), "Methode generale pour la resolution des systemes d'equations simultanees." He was solving systems of equations, not training neural networks, but the algorithm is the same. [VERIFY: Cauchy 1847 paper on steepest descent -- confirm title and year]
- **Visual:** A 3D landscape (the "loss surface") with contour lines. A ball sits at a high point. Arrows show the gradient direction (steepest uphill). The ball moves in the OPPOSITE direction (steepest downhill). Caption: "Gradient descent: always walk downhill. Cauchy, 1847."
- **Talking point:** "Cauchy described this in 1847 to solve equations. 170 years later, it's how every LLM on Earth is trained. The error is the height. The gradient tells you which way is downhill. You take a step. Repeat a billion times."

### Slide 22: Backpropagation -- The Algorithm That Changed Everything
- **Key message:** Backpropagation applies the chain rule efficiently through all layers of a neural network, computing how to adjust every weight to reduce error.
- **Historical persons:**
  - **Seppo Linnainmaa** (born 1945, Finland). Published automatic differentiation (the general algorithm for computing derivatives of composite functions by computer) in his Master's thesis (1970, University of Helsinki). This is the mathematical core of backpropagation. [VERIFY: confirm 1970 date and that it was his Master's thesis, not PhD]
  - **David Rumelhart** (1942-2011, USA), **Geoffrey Hinton** (born 1947, London, UK/Canada), **Ronald Williams** (USA). Published "Learning representations by back-propagating errors" (1986, Nature), which demonstrated that backpropagation could train multi-layer neural networks effectively. This paper reignited the field.
- **Visual 1:** A multi-layer network diagram. Forward pass shown in blue arrows (left to right). Backward pass shown in red arrows (right to left), labeled "chain rule, chain rule, chain rule" at each step.
- **Visual 2:** Timeline: Cauchy (1847, steepest descent) -> Linnainmaa (1970, automatic differentiation) -> Rumelhart/Hinton/Williams (1986, backprop for neural nets)
- **Talking point:** "Linnainmaa figured out the algorithm in 1970. Rumelhart, Hinton, and Williams showed it could train neural networks in 1986. Hinton shared the Nobel Prize in Physics in 2024 with John Hopfield for foundational work enabling machine learning with artificial neural networks."
- **[VERIFY]:** Linnainmaa's 1970 thesis -- some sources describe it as the invention of reverse-mode automatic differentiation. Others credit earlier work (e.g., Bryson, Dreyfus, Kelley in the 1960s for related ideas in control theory). Present Linnainmaa as the key formalization but note the broader lineage. [VERIFY: Nobel Prize 2024 -- Hinton and Hopfield shared the Nobel Prize in Physics 2024. Confirm exact citation wording.]

### Slide 23: Stochastic Gradient Descent -- Learning from Samples
- **Key message:** In practice, computing the gradient over ALL training data is too expensive. Stochastic gradient descent (SGD) computes gradients on small random batches.
- **Historical persons:**
  - **Herbert Robbins** (1915-2001, New Castle, Pennsylvania, USA) and **Sutton Monro** (1920-1995, USA). Published the Robbins-Monro algorithm (1951), the first stochastic approximation method. This is the theoretical foundation for SGD. [VERIFY: Monro's dates and birthplace]
- **Visual:** Comparison diagram:
  - Left: "Full gradient descent" -- smooth downhill path, but labeled "Must look at ALL data for each step. Too slow."
  - Right: "Stochastic gradient descent" -- noisy, zigzagging path that still reaches the bottom, labeled "Look at a random sample each step. Much faster."
- **Talking point:** "Training GPT-4 used trillions of tokens. You can't compute the gradient on all of them at once. SGD says: just grab a random batch, compute the gradient on that, take a step, repeat. It's noisy, but it works. And it's fast."
- **LLM connection:** "Every LLM you have ever used was trained with some variant of SGD. The Robbins-Monro paper from 1951 is running inside every AI lab today."

### Slide 24: The Loss Landscape -- A Visual Tour
- **Key message:** The "loss" measures how wrong the network's predictions are. Training = finding the lowest point on the loss landscape.
- **Visual (full-slide visual):** A beautiful 3D rendering of a neural network loss landscape (Li et al., 2018, "Visualizing the Loss Landscape of Neural Nets" style). Label the features:
  - "Global minimum" (the best the network can do)
  - "Local minima" (pretty good but not the best)
  - "Saddle points" (flat regions that look like minima but aren't)
  - "The path of SGD" (a noisy trajectory from a random starting point to a good minimum)
- **Source:** Reconstructed from Li et al. 2018 or similar public-domain loss landscape visualizations
- **Talking point:** "This is what training an LLM looks like mathematically. You start at a random point on this landscape and try to find the lowest valley. The landscape has billions of dimensions -- we can only visualize a 2D slice."

### Slide 25: Convergence Diagram Update -- Calculus & Optimization
- **Visual:** Convergence diagram with "Calculus & Optimization" node now lit in green. Label: "Gradient descent = how it learns."
- **Summary box:**
  - Archimedes (c. 250 BCE): Proto-calculus, method of exhaustion
  - Fermat (c. 1636): Tangent lines, maxima/minima
  - Newton (1665-66) / Leibniz (1684-86): Calculus
  - Chain rule: Leibniz et al. -- the backbone of backpropagation
  - Cauchy (1847): Steepest descent / gradient descent
  - Robbins-Monro (1951): Stochastic approximation
  - Linnainmaa (1970): Automatic differentiation
  - Rumelhart/Hinton/Williams (1986): Backpropagation for neural networks
- **Connection arrow:** "Gradient descent + backpropagation = the learning algorithm of every LLM."
- **Transition:** "The network can now learn. But learn WHAT? It learns to predict probability distributions over words. For that, we need probability theory."

---

## SECTION 3: PROBABILITY & STATISTICS -- "The Language of Uncertainty" (Slides 26-34)

**Section color:** Orange (matching `accentOrange` from existing palette)
**Connection arrow:** LLMs are probabilistic: they predict a probability distribution over the next token. Softmax, Bayes, maximum likelihood -- all probability.

### Slide 26: Section Divider -- "Probability & Statistics: The Language of Uncertainty"
- **Visual:** Section title overlaid on a bar chart of token probabilities (like an LLM's output distribution for the next word). Convergence diagram with Section 3 pulsing.
- **Timeline marker:** 1654-1933
- **Tagline:** "An LLM doesn't KNOW the next word. It assigns PROBABILITIES to every possible word."

### Slide 27: The Birth of Probability -- A Gambling Problem
- **Key message:** Probability theory began with a correspondence about gambling between two French mathematicians.
- **Historical persons:**
  - **Blaise Pascal** (1623-1662, Clermont-Ferrand, France). Mathematician, physicist, philosopher. Co-founded probability theory in correspondence with Fermat (1654) about the "problem of points" (how to divide stakes in an interrupted game of chance).
  - **Pierre de Fermat** (1601-1665, Beaumont-de-Lomagne, France). His reply to Pascal's letter laid out the counting arguments that became combinatorial probability.
- **Visual:** A recreation of the letter exchange (two letter icons with key mathematical content between them). The "problem of points" illustrated with a simple coin-flip game tree.
- **Talking point:** "Probability theory was born because a gambler asked Pascal a question about how to split the pot in an unfinished dice game. Pascal wrote to Fermat. Their letters invented a new branch of mathematics."
- **Speaker note:** "Fermat again! We saw him in calculus (tangent lines) and now he appears in probability. He contributed foundational ideas to two separate pillars of the LLM."

### Slide 28: From Gambling to Laws -- Bernoulli and Laplace
- **Key message:** Probability evolved from gambling tricks into a rigorous mathematical theory.
- **Historical persons:**
  - **Jacob Bernoulli** (1655-1705, Basel, Switzerland). Proved the law of large numbers (published posthumously in "Ars Conjectandi", 1713): as you repeat an experiment, the observed frequency converges to the true probability. This is why LLM training on more data gives better results.
  - **Pierre-Simon Laplace** (1749-1827, Beaumont-en-Auge, France). Published "Theorie analytique des probabilites" (1812), which systematized the entire field. Popularized Bayes' theorem and introduced generating functions for probability.
- **Visual:** Bernoulli's law of large numbers illustrated: a sequence of coin flips, with the running average converging to 50%. Caption: "Flip a coin 10 times: anything could happen. Flip it 10 million times: the average WILL be 50%."
- **LLM connection:** "Why do LLMs get better with more training data? Bernoulli's law of large numbers: more data means the learned probabilities converge to the true patterns of language."

### Slide 29: Bayes' Theorem -- Updating Beliefs with Evidence
- **Key message:** Bayes' theorem tells you how to update your beliefs when you get new evidence. LLMs implicitly learn Bayesian-like reasoning from data.
- **Historical persons:**
  - **Thomas Bayes** (c. 1701-1761, London, England). Presbyterian minister and mathematician. His "Essay towards solving a Problem in the Doctrine of Chances" was published posthumously (1763) by his friend Richard Price. [VERIFY: Bayes birth year is uncertain -- some sources give 1701, others 1702]
  - **Pierre-Simon Laplace** (again) independently developed and popularized the same result.
- **Visual:** Bayes' theorem in its classic form: P(A|B) = P(B|A) * P(A) / P(B). Below it, a concrete example: "If a medical test is 99% accurate, and the disease affects 1 in 10,000 people, what's the chance you actually have the disease given a positive test?" (Answer: ~1%. This surprises students.)
- **Mathematical content (CONCEPTUAL):** Present the formula as "Recipe: New belief = (how likely the evidence if your guess is right) times (your original guess) divided by (how likely the evidence overall)." Formal version in inset.
- **Talking point:** "Bayes was a minister, not a professor. He published almost nothing in his lifetime. His one big idea -- how to update beliefs from evidence -- was published after his death by a friend. It became one of the most important ideas in all of science."
- **LLM connection:** "While LLMs don't explicitly compute Bayes' theorem, the training process causes them to implicitly learn conditional probabilities: P(next word | previous words). That IS Bayesian reasoning, learned from data."

### Slide 30: Kolmogorov's Axioms -- Probability Made Rigorous [EXTENDED]
- **Key message:** In 1933, probability finally got a rigorous mathematical foundation.
- **Historical person:**
  - **Andrey Kolmogorov** (1903-1987, Tambov, Russia). Published "Grundbegriffe der Wahrscheinlichkeitsrechnung" (Foundations of the Theory of Probability, 1933), which axiomatized probability using measure theory. This put probability on the same rigorous footing as geometry (Euclid) and calculus (Cauchy/Weierstrass).
- **Visual:** Kolmogorov's three axioms, stated in plain English:
  1. Probabilities are between 0 and 1
  2. Something must happen (total probability = 1)
  3. Probabilities of mutually exclusive events add up
- **Caption:** "Three simple rules. Every probability calculation in every LLM obeys these rules."
- **[VERIFY]:** Publication year 1933 and German title.

### Slide 31: Maximum Likelihood -- Finding the Best Fit
- **Key message:** Maximum likelihood estimation asks: "Given the data I observed, what parameters make this data most probable?" This is how LLMs find their weights.
- **Historical person:**
  - **Ronald Aylmer Fisher** (1890-1962, London, England). Introduced maximum likelihood estimation in a series of papers (1912, 1922). His 1922 paper "On the Mathematical Foundations of Theoretical Statistics" established MLE as a foundational method. [VERIFY: confirm 1912 vs. 1922 as the key date. Fisher introduced the concept in 1912 but formalized it in 1922]
- **Visual:** A curve (probability distribution) being "fit" to data points. Multiple candidate curves shown in light gray; the maximum likelihood curve in bold. Caption: "Which curve best explains the data? The one that makes the data most probable."
- **LLM connection:** "LLM training is essentially maximum likelihood estimation: find the model parameters (weights) that maximize the probability of the training text. Fisher's method from 1922, applied to trillions of words."

### Slide 32: Statistical Language Models -- Shannon's Breakthrough
- **Key message:** Claude Shannon showed that language itself is statistical, and that you can model it by predicting the next character or word.
- **Historical person:**
  - **Claude Shannon** (1916-2001, Petoskey, Michigan, USA). Published "A Mathematical Theory of Communication" (1948), founding information theory. In this paper, he modeled English as a stochastic process and showed that you could approximate English text by predicting the next letter/word from the preceding context. He built n-gram language models decades before AI.
- **Visual 1:** Shannon's example from the 1948 paper: text generated by 0th-order, 1st-order, 2nd-order, and 3rd-order approximations to English. The text becomes increasingly readable as the order increases.
- **Visual 2:** A diagram: "Shannon (1948): predict the next letter using the previous N letters" --> "LLM (2024): predict the next token using ALL previous tokens"
- **Talking point:** "Shannon was doing language modeling in 1948 -- 70 years before GPT. He showed that language has statistical structure, and that you can exploit that structure to predict what comes next. That's exactly what every LLM does."

### Slide 33: The Softmax Function -- From Thermodynamics to Token Prediction
- **Key message:** The softmax function converts raw numbers (logits) into a probability distribution. It is the last step in every LLM prediction. Its history stretches back to 19th-century physics.
- **Historical lineage:**
  - **Ludwig Boltzmann** (1844-1906, Vienna, Austria). His Boltzmann distribution (1868/1870s) describes the probability of a physical system being in a particular state, based on its energy: P(state) proportional to exp(-Energy/kT). [VERIFY: the Boltzmann distribution is typically dated to his work in the 1870s; the exact "1868" date may refer to his early papers]
  - **Josiah Willard Gibbs** (1839-1903, again). Generalized Boltzmann's work into the Gibbs distribution / canonical ensemble.
  - **R. Duncan Luce** (1925-2012, Scranton, Pennsylvania, USA). Published the choice axiom (1959) in psychology: the probability of choosing an option is proportional to its "strength." Mathematically identical to softmax. [VERIFY: Luce's 1959 book "Individual Choice Behavior"]
  - The **softmax function** as used in machine learning: softmax(z_i) = exp(z_i) / sum(exp(z_j)). This is the Boltzmann distribution with temperature = 1.
- **Mathematical content (CONCEPTUAL):** "Recipe: (1) Take each raw score and raise e to that power (this makes everything positive and magnifies differences). (2) Add up all the results. (3) Divide each by the total. Now they are probabilities that add to 1."
  - **Small inset (formal):** softmax(z_i) = exp(z_i) / sum_j(exp(z_j))
- **Visual:** The softmax pipeline:
  1. Raw scores (logits): [2.1, 0.8, 0.3, -1.5, ...]
  2. Exponentiate: [8.17, 2.23, 1.35, 0.22, ...]
  3. Normalize: [0.68, 0.19, 0.11, 0.02, ...]
  4. Now they're probabilities! Bar chart showing: "the" (68%), "a" (19%), "that" (11%), ...
- **Interactive moment:** Quick poll -- "What word comes next: 'The cat sat on the ___'?" Collect student answers, then show the AI's softmax distribution for the same prompt.
- **Talking point:** "Boltzmann invented this formula to describe how gas molecules distribute among energy states. 150 years later, the exact same formula tells an LLM which word to say next."

### Slide 34: Convergence Diagram Update -- Probability & Statistics
- **Visual:** Convergence diagram with "Probability & Statistics" node lit in orange. Label: "Softmax = next-token prediction."
- **Summary box:**
  - Pascal/Fermat (1654): Birth of probability
  - Bernoulli (1713): Law of large numbers
  - Bayes (1763) / Laplace: Updating beliefs from evidence
  - Kolmogorov (1933): Probability axioms
  - Fisher (1922): Maximum likelihood estimation
  - Shannon (1948): Language as a statistical process
  - Boltzmann (1870s) -> Luce (1959) -> Softmax: From physics to token prediction
- **Connection arrow:** "Every time an LLM generates a word, it computes a softmax probability distribution. The math started with a gambling question in 1654."
- **Transition:** "The network predicts probabilities. But how do we measure whether those probabilities are GOOD? For that, we need information theory."

---

## SECTION 4: INFORMATION THEORY -- "Measuring Meaning" (Slides 35-41)

**Section color:** Red (a warm informational red)
**Connection arrow:** Cross-entropy is the loss function used to train LLMs. Entropy measures information content. Tokenization is rooted in information-theoretic analysis of language.

### Slide 35: Section Divider -- "Information Theory: Measuring Meaning"
- **Visual:** Section title overlaid on a visualization of entropy (random vs. structured text). Convergence diagram with Section 4 pulsing.
- **Timeline marker:** 1865-1948 (and beyond)
- **Tagline:** "How surprised should you be by the next word? Information theory measures that."

### Slide 36: Entropy -- From Steam Engines to Bits
- **Key message:** "Entropy" was invented three times: once for heat engines, once for gas molecules, once for information. The same mathematical formula, three completely different domains.
- **Historical persons:**
  - **Rudolf Clausius** (1822-1888, Koslin, Prussia / Zurich / Bonn). Introduced the concept of entropy in thermodynamics (1865) to formalize the second law: entropy of an isolated system always increases. Named it from Greek "entropia" (transformation). [VERIFY: Clausius coined the term in 1865, but the concept appears in his earlier work from the 1850s]
  - **Ludwig Boltzmann** (1844-1906, Vienna, Austria). Connected entropy to probability (1870s): S = k * log(W). The entropy of a system is proportional to the logarithm of the number of microstates. This statistical interpretation bridged physics and probability.
  - **Claude Shannon** (1916-2001, again). Redefined entropy for information (1948): H = -sum(p_i * log(p_i)). This measures the average "surprise" or "uncertainty" in a message. The formula is mathematically identical to Boltzmann's.
- **Speaker note:** "Shannon appears again! We saw him in Section 3 (statistical language models, Slide 32). His 1948 paper is so foundational that it contributes to BOTH probability and information theory sections. He modeled language statistically AND created the measure for how good that model is."
- **Mathematical content (CONCEPTUAL):** For Shannon's formula, present as: "Recipe: For each possible outcome, multiply its probability by the 'surprise' (how unexpected it is, measured as the logarithm). Add them all up. The result is the average surprise." The formal H = -sum(p_i * log(p_i)) goes in a small inset with annotation: "The sigma (sum) sign means 'add up for every possible outcome i'."
- **Visual:** Three columns:
  - Clausius: Steam engine diagram, entropy as "energy unavailable for work"
  - Boltzmann: Gas molecules in a box, entropy as "disorder" / number of arrangements. Boltzmann's tombstone with S = k log W
  - Shannon: A coin flip vs. a loaded coin. Shannon's entropy formula. Caption: "Surprise = information."
- **Talking point:** "Shannon supposedly asked von Neumann what to call his new quantity. Von Neumann said: 'Call it entropy. Nobody knows what entropy really is, so in a debate you will always have the advantage.' Whether or not that story is true, the name stuck." [VERIFY: this anecdote is widely attributed but may be apocryphal]

### Slide 37: Cross-Entropy -- The Loss Function of LLMs
- **Key message:** Cross-entropy measures how well a predicted probability distribution matches the actual distribution. It is THE loss function used to train virtually all LLMs.
- **Mathematical content (CONCEPTUAL):** "Recipe: The true answer is one specific word. Look at the probability your model assigned to that word. Take the logarithm. Negate it. That's the loss. High confidence in the right answer = low loss. Low confidence in the right answer = high loss."
  - **Small inset (formal):** Cross-entropy = -log(predicted probability of correct token). Note: "The full formula uses a summation over all possible tokens, but since only one token is correct, it simplifies to this."
- **Visual:** A concrete example:
  - Correct next word: "mat"
  - Model predicts: "mat" (30%), "rug" (25%), "floor" (20%), "ground" (15%), ...
  - Cross-entropy loss = -log(0.30) = 1.20
  - If model improves to "mat" (80%): loss = -log(0.80) = 0.22
  - Bar chart showing: higher confidence in correct answer = lower loss
- **Caption:** "Training an LLM = minimizing cross-entropy = making the model more confident about the RIGHT next word."
- **Talking point:** "Every time an LLM gets a training example, it predicts the next token, checks how wrong it was using cross-entropy, then uses backpropagation to improve. Cross-entropy is the bridge between information theory and gradient descent."

### Slide 38: Surprisal and Perplexity -- How We Evaluate LLMs
- **Key message:** "Surprisal" is -log(probability). "Perplexity" is the average surprisal, exponentiated. These are how researchers measure how good an LLM is.
- **Visual:** A sentence: "The cat sat on the [____]"
  - "mat" -- low surprisal (expected)
  - "chandelier" -- high surprisal (unexpected)
  - "asdfghjkl" -- very high surprisal (nonsensical)
  - Bar chart of surprisal values for each option
- **Caption:** "A good language model is rarely surprised by real text."
- **LLM connection:** "When researchers say GPT-4 has 'lower perplexity' than GPT-3, they mean it's less surprised by real text -- it predicts better. Shannon would have understood this immediately."

### Slide 39: KL Divergence -- Measuring the Gap Between Distributions [EXTENDED]
- **Key message:** KL divergence measures how different two probability distributions are. It is used in training techniques like RLHF to keep the model from diverging too far from its base behavior.
- **Mathematical content (CONCEPTUAL):** "Recipe: For each possible outcome, ask 'how much more surprising is this outcome under model Q compared to truth P?' Average that over all outcomes. If Q matches P perfectly, KL divergence is zero."
- **Historical connection:** **Solomon Kullback** (1907-1994, USA) and **Richard Leibler** (1914-2003, USA) published the KL divergence in 1951. [VERIFY: the 1951 paper "On Information and Sufficiency"]
- **Visual:** Two probability distributions overlaid: P (true) and Q (model). The shaded area between them represents KL divergence. Caption: "Bigger gap = worse model."
- **LLM connection:** "In RLHF (the technique that makes ChatGPT helpful and harmless), KL divergence is used to prevent the model from changing too much during fine-tuning."

### Slide 40: Tokenization -- Carving Language into Pieces
- **Key message:** Before an LLM sees text, it must split it into "tokens." The way we carve up language is informed by information theory and linguistics.
- **Historical connections:**
  - **George Kingsley Zipf** (1902-1950, Freeport, Illinois, USA). Zipf's law (1935/1949): in natural language, the frequency of a word is inversely proportional to its rank. "The" is #1, "of" is #2, etc. This distribution shapes how tokenizers work. [VERIFY: Zipf's law appears in his 1935 book "The Psycho-Biology of Language" and more fully in his 1949 book "Human Behavior and the Principle of Least Effort"]
  - **Rico Sennrich**, **Barry Haddow**, **Alexandra Birch** (University of Edinburgh). Published Byte Pair Encoding (BPE) for neural machine translation (2016), adapting a compression algorithm from Philip Gage (1994). BPE is the tokenization method used by GPT and most modern LLMs. [VERIFY: Sennrich et al. 2016 ACL paper]
- **Visual:** Tokenization example:
  - Input: "The mathematician calculated the eigenvalue"
  - BPE tokens: ["The", " mathematic", "ian", " calculated", " the", " eigen", "value"]
  - Color-coded: common words get single tokens, rare words get split
  - Caption: "BPE gives short tokens to common patterns (Zipf's law!) and splits rare words into pieces."
- **Talking point:** "The AI doesn't see words -- it sees tokens. Common words like 'the' get one token. Uncommon words like 'eigenvalue' might get split into 'eigen' + 'value.' This encoding scheme is deeply connected to information theory: give short codes to frequent patterns."

### Slide 41: Convergence Diagram Update -- Information Theory
- **Visual:** Convergence diagram with "Information Theory" node lit in red. Label: "Cross-entropy = the loss function."
- **Summary box:**
  - Clausius (1865): Thermodynamic entropy
  - Boltzmann (1870s): Statistical entropy, S = k log W
  - Shannon (1948): Information entropy, the "bit"
  - Kullback-Leibler (1951): Divergence between distributions
  - Zipf (1935/1949): Word frequency laws
  - Sennrich et al. (2016): BPE tokenization
- **Connection arrow:** "LLMs are trained by minimizing cross-entropy loss. Shannon's 1948 formula is literally the objective function."
- **Transition:** "We have the math for learning and the math for measuring. But we need something to run it on. Enter: logic and computation."

---

## SECTION 5: LOGIC & COMPUTATION -- "The Substrate" (Slides 42-48)

**Section color:** Gray/Steel (matching `modernSteel`)
**Connection arrow:** Boolean logic built the hardware. Turing proved what's computable. GPUs made deep learning possible.

**Narrative tension:** This section is structured around a paradox. Logicians dreamed of reducing all reasoning to mechanical rules -- and Turing proved that's impossible (the halting problem, undecidability). And yet, neural networks learned to do things that formal logic cannot: translate languages, write poetry, reason by analogy. The irony: the machines that logic built transcended the limitations that logic discovered.

### Slide 42: Section Divider -- "Logic & Computation: The Substrate"
- **Visual:** Section title overlaid on a circuit board close-up transitioning to GPU array. Convergence diagram with Section 5 pulsing.
- **Timeline marker:** 1854-1970s (and ongoing)
- **Tagline:** "Logicians dreamed of mechanical thought. They proved it was impossible. Then neural networks did it anyway."

### Slide 43: Boolean Algebra -- The Language of Computers
- **Key message:** Every digital computer is built from Boolean logic: AND, OR, NOT. George Boole reduced logical reasoning to algebra.
- **Historical person:**
  - **George Boole** (1815-1864, Lincoln, England / Cork, Ireland). Published "An Investigation of the Laws of Thought" (1854). Self-taught mathematician who became the first professor of mathematics at Queen's College Cork. He showed that logical statements could be expressed as algebraic equations, with variables taking values 0 (false) or 1 (true).
- **Visual:** Boolean logic gates (AND, OR, NOT) drawn as circuit symbols, with truth tables. Below them: "Every GPU in every AI data center is made of billions of these gates."
- **Talking point:** "Boole was a self-taught son of a shoemaker who became a university professor. His algebra of logic is now the foundation of every digital device on Earth."

### Slide 44: The Dream and Its Limits -- From Frege to Godel to Turing
- **Key message:** After Boole, logicians dreamed of reducing ALL reasoning to mechanical symbol manipulation. They almost succeeded -- and then proved it was impossible. But the attempt created the foundation for computers.
- **Historical persons:**
  - **Gottlob Frege** (1848-1925, Wismar, Germany). Created the first formal logical system powerful enough to express mathematics ("Begriffsschrift," 1879). This was the first formal language -- a precursor to programming languages.
  - **Bertrand Russell** (1872-1970, Trellech, Wales, UK) and **Alfred North Whitehead** (1861-1947, Ramsgate, England). Published "Principia Mathematica" (1910-1913), attempting to derive ALL of mathematics from logical axioms.
  - **Kurt Godel** (1906-1978, Brno, Austria-Hungary / USA). Proved (1931) that any consistent formal system powerful enough to express arithmetic contains true statements that cannot be proved within the system. The dream of complete mechanical reasoning was impossible.
  - **Alan Turing** (1912-1954, London, England). Published "On Computable Numbers, with an Application to the Entscheidungsproblem" (1936), introducing the Turing machine. Proved that there is no general algorithm to decide whether an arbitrary program will halt -- the halting problem is undecidable.
- **Visual 1:** A page from Principia Mathematica showing the famously laborious proof that 1 + 1 = 2 (which appears around page 362). Caption: "It took 362 pages to prove 1 + 1 = 2. Then Godel proved the project couldn't succeed." [VERIFY: the exact page number where 1+1=2 appears in Principia -- commonly cited as "page 362" but this may be approximate]
- **Visual 2:** Timeline: Boole (1854) -> Frege (1879) -> Russell/Whitehead (1910) -> **Godel (1931): "Some truths can't be proved"** -> **Turing (1936): "Some questions can't be answered by any algorithm"** -> first computers (1940s)
- **Talking point:** "They tried to reduce all reasoning to logic. Godel proved some truths escape any formal system. Turing proved some questions can't be answered by any algorithm. And yet -- here's the twist -- neural networks, built from Boole's logic gates, learned to translate, to reason, to create. Not by following rules, but by learning patterns from data. The machines that logic built went beyond what logic can do."

### Slide 45: Von Neumann Architecture -- The Hardware Blueprint [EXTENDED]
- **Key message:** The stored-program computer -- where instructions and data share the same memory -- was formalized by John von Neumann.
- **Historical person:**
  - **John von Neumann** (1903-1957, Budapest, Hungary / USA). Published "First Draft of a Report on the EDVAC" (1945), describing the stored-program architecture. Nearly every computer since has followed this basic design. [VERIFY: the 1945 draft was controversial -- it was circulated under von Neumann's name alone, but was based on work by Eckert and Mauchly. Present the architecture concept, not the priority dispute]
- **Visual:** The von Neumann architecture diagram: CPU (control unit + ALU), memory, input, output, with arrows showing data flow. Caption: "This is the basic design of nearly every computer for 80 years."
- **LLM connection:** "LLM inference runs on this architecture. But training requires something different: massively parallel hardware. Enter the GPU."

### Slide 46: Floating Point Arithmetic -- How Computers Handle Real Numbers
- **Key message:** Computers work with integers natively. Representing real numbers (decimals, fractions) requires a clever encoding scheme.
- **Historical connection:** The IEEE 754 standard for floating-point arithmetic (1985) standardized how computers represent real numbers. Earlier work by **Konrad Zuse** (1910-1995, Berlin, Germany) on the Z3 computer (1941) used floating-point arithmetic. [VERIFY: Z3 as first floating-point computer -- the claim is standard but should note it was electromechanical, not electronic]
- **Visual:** How 3.14159 is stored in a computer: sign bit (1 bit), exponent (8 bits), mantissa (23 bits). Caption: "Every weight in an LLM is stored as a floating-point number. In large models, there are hundreds of billions of them." [Note: GPT-4's exact parameter count is not publicly confirmed by OpenAI]
- **Talking point:** "Modern LLMs use reduced-precision floating point (16-bit or even 8-bit instead of 32-bit) to save memory and speed. This means accepting small rounding errors in exchange for being able to fit a bigger model."

### Slide 47: GPU Computing -- Why Matrix Multiplication Won
- **Key message:** GPUs (Graphics Processing Units) were designed for video games but turned out to be perfectly suited for neural network math: they do thousands of matrix multiplications in parallel.
- **Key developments:**
  - **NVIDIA** released CUDA (Compute Unified Device Architecture) in 2007, allowing general-purpose computing on GPUs
  - **Alex Krizhevsky**, **Ilya Sutskever**, **Geoffrey Hinton** demonstrated that GPUs could train deep neural networks dramatically faster in their AlexNet paper (2012), winning the ImageNet competition and launching the deep learning era. [VERIFY: AlexNet -- Krizhevsky et al., NIPS 2012]
- **Visual:** Comparison:
  - CPU: A few powerful cores (4-16), good at sequential tasks
  - GPU: Thousands of simple cores (5,000-16,000), good at parallel tasks
  - Neural network training: millions of independent matrix multiplications -> perfect for GPU
  - Caption: "Video game hardware accidentally enabled AI."
- **Talking point:** "Without GPUs, deep learning would still be a curiosity. The AlexNet result in 2012 showed that GPUs could train networks 10-100x faster than CPUs. That single result changed the trajectory of AI."

### Slide 48: Convergence Diagram Update -- Logic & Computation
- **Visual:** Convergence diagram with "Logic & Computation" node lit in gray/steel. Label: "GPUs = the hardware."
- **Summary box:**
  - Boole (1854): Boolean algebra
  - Frege (1879): Formal logic
  - Russell/Whitehead (1910-13): Principia Mathematica
  - Godel (1931): Incompleteness -- limits of formal reasoning
  - Turing (1936): Computability, the Turing machine
  - Von Neumann (1945): Stored-program architecture
  - Zuse (1941): Floating-point computation
  - NVIDIA CUDA (2007) + AlexNet (2012): GPU revolution
- **Connection arrow:** "Boolean logic built the hardware. Turing defined computation. GPUs made deep learning possible. And neural networks surpassed what formal logic can do."
- **Transition:** "We have math AND hardware. But here's a deep question: WHY should a pile of matrix multiplications be able to learn ANYTHING? For the answer, we need the theory of function approximation."

---

## SECTION 6: FUNCTION APPROXIMATION -- "Why Neural Networks Work at All" (Slides 49-53)

**Section color:** Purple (matching `medievalPurple` or a new math-purple)
**Connection arrow:** The universal approximation theorem guarantees that neural networks CAN represent any continuous function. This is the theoretical justification for the entire enterprise.

### Slide 49: Section Divider -- "Function Approximation: Why It Works at All"
- **Visual:** Section title overlaid on an animation-style sequence of increasingly accurate function approximations. Convergence diagram with Section 6 pulsing.
- **Timeline marker:** 1807-1991
- **Tagline:** "A neural network can approximate any function. Here's why that's remarkable."

### Slide 50: Fourier Series -- Any Function as a Sum of Waves
- **Key message:** Joseph Fourier showed that ANY function can be written as a sum of sine and cosine waves. This was the first great "approximation" result and directly inspired the universal approximation theorem.
- **Historical person:**
  - **Jean-Baptiste Joseph Fourier** (1768-1830, Auxerre, France). Published "Theorie analytique de la chaleur" (Analytical Theory of Heat, 1822, based on work from 1807). To solve the heat equation, Fourier claimed that any function could be decomposed into sines and cosines. This claim was initially controversial (Lagrange objected) but proved enormously fertile.
- **Visual:** A square wave being approximated by adding up sine waves: 1 sine (rough), 3 sines (better), 10 sines (very close), 100 sines (nearly perfect). Caption: "Any function = a sum of simple waves. Fourier, 1807."
- **LLM connection (preview):** "Positional encoding in the transformer uses sine and cosine functions at different frequencies -- directly inspired by Fourier's idea. We'll see this in Section 9."
- **Talking point:** "Fourier wanted to solve the heat equation. To do it, he made a claim so bold that other mathematicians didn't believe him: any function can be written as a sum of sines. He was essentially right, and the idea became one of the most powerful tools in all of mathematics."

### Slide 51: Weierstrass Approximation -- Polynomials Can Do It Too [EXTENDED]
- **Key message:** Karl Weierstrass proved that any continuous function on a closed interval can be uniformly approximated by polynomials. This is a predecessor to the neural network universal approximation theorem.
- **Historical person:**
  - **Karl Weierstrass** (1815-1897, Ostenfelde, Westphalia, Germany). Proved the Weierstrass approximation theorem (1885): for any continuous function f on [a,b] and any epsilon > 0, there exists a polynomial P such that |f(x) - P(x)| < epsilon for all x in [a,b].
- **Visual:** A wiggly continuous function, with polynomial approximations of increasing degree overlaid. The polynomials get closer and closer. Caption: "Any continuous function can be approximated as closely as you want by a polynomial."
- **Talking point:** "Weierstrass proved that polynomials are 'universal approximators' for continuous functions. A century later, Cybenko would prove the same thing for neural networks."

### Slide 52: The Universal Approximation Theorem -- Neural Networks Can Learn Anything
- **Key message:** A neural network with one hidden layer and enough neurons can approximate any continuous function to any desired accuracy. This is the theoretical guarantee that makes deep learning work.
- **Historical persons:**
  - **George Cybenko** (born c. 1952, Canada/USA). Published "Approximation by Superpositions of a Sigmoidal Function" (1989), proving that a feedforward network with a single hidden layer of sigmoidal neurons can approximate any continuous function. [VERIFY: Cybenko's birth year -- often listed as c. 1952]
  - **Kurt Hornik** (born c. 1963, Austria). Published "Approximation Capabilities of Multilayer Feedforward Networks" (1991), generalizing Cybenko's result to a wider class of activation functions. [VERIFY: Hornik's birth year]
- **Visual 1:** A simple neural network with one hidden layer. As the number of hidden neurons increases (5, 20, 100, 1000), the function it represents gets more complex and accurate. Caption: "More neurons = better approximation. Cybenko, 1989."
- **Visual 2:** A quote box: "A neural network can learn any continuous function, given enough neurons. This is not an analogy. It is a mathematical theorem."
- **Talking point:** "This theorem is why people bet on neural networks. It's not that they're the BEST approximators -- it's that they're GUARANTEED to work, at least in principle. The practical challenge is training them, which is where all the other building blocks come in."
- **Speaker note:** Be clear that the theorem says a network CAN approximate any function, not that gradient descent will FIND the right weights. The gap between "existence" and "constructive algorithm" is important.

### Slide 53: Convergence Diagram Update -- Function Approximation
- **Visual:** Convergence diagram with "Function Approximation" node lit in purple. Label: "Universal approximation = why it works."
- **Summary box:**
  - Fourier (1807/1822): Any function as a sum of waves
  - Weierstrass (1885): Polynomial approximation
  - Cybenko (1989): Neural network universal approximation theorem
  - Hornik (1991): Generalized to broader activation functions
- **Connection arrow:** "The universal approximation theorem guarantees that neural networks can represent any continuous function. The LLM's ability to model language is a specific case."
- **Transition:** "We know neural networks CAN learn anything. But what IS a 'neural network'? Where did the idea come from?"

---

## SECTION 7: THE NEURON & DEPTH -- "From Biology to Mathematics to Deep Networks" (Slides 54-62)

**Section color:** Yellow/Gold (matching `renaissanceGold`)
**Connection arrow:** The artificial neuron is the basic unit of every neural network. Activation functions provide the nonlinearity that makes learning possible. Residual connections, layer normalization, and dropout are the engineering innovations that allow networks to be deep.

### Slide 54: Section Divider -- "The Neuron & Depth: From Biology to Deep Networks"
- **Visual:** Split image: a biological neuron (microscopy photo) on the left, a mathematical neuron (circle with inputs and an output) on the right, and a deep network stack on the far right. Convergence diagram with Section 7 pulsing.
- **Timeline marker:** 1943-2016
- **Tagline:** "A real neuron fires or doesn't. A mathematical neuron does the same thing, with an equation. But stacking them deep required more invention."

### Slide 55: The McCulloch-Pitts Neuron -- The First Mathematical Brain Cell
- **Key message:** In 1943, a neuroscientist and a logician created the first mathematical model of a neuron: a simple device that sums its inputs and fires if the sum exceeds a threshold.
- **Historical persons:**
  - **Warren McCulloch** (1898-1969, Orange, New Jersey, USA). Neurophysiologist who sought to understand the brain in logical terms.
  - **Walter Pitts** (1923-1969, Detroit, Michigan, USA). Self-taught logician, a troubled prodigy who ran away from home at 15 and ended up working with McCulloch. Together they published "A Logical Calculus of the Ideas Immanent in Nervous Activity" (1943). [VERIFY: Pitts's biography -- the "ran away at 15" claim is commonly stated but details vary]
- **Visual:** The McCulloch-Pitts neuron: inputs x1, x2, x3 with weights w1, w2, w3. Sum = w1*x1 + w2*x2 + w3*x3. If Sum > threshold, output = 1. Else output = 0. A biological neuron shown next to it for comparison.
- **Talking point:** "A neurophysiologist and a teenage runaway created the mathematical neuron. McCulloch was in his 40s; Pitts was about 20 and had no degree. Their paper launched neural network research."

### Slide 56: The Perceptron -- A Machine That Learns
- **Key message:** The perceptron was the first neural network that could LEARN -- it could adjust its weights from examples.
- **Historical person:**
  - **Frank Rosenblatt** (1928-1971, New Rochelle, New York, USA). Built the Mark I Perceptron (1957-1958) at the Cornell Aeronautical Laboratory. It was a physical machine (not a simulation) that could learn to classify images. The New York Times reported it as a machine that could "walk, talk, see, write, reproduce itself, and be conscious of its existence." [VERIFY: the exact NYT quote and date -- commonly cited as a 1958 article]
- **Visual 1:** Photo of the Mark I Perceptron hardware (a large machine with photocells)
- **Visual 2:** The perceptron learning algorithm: present an example, compare output to desired output, adjust weights in the direction that reduces the error. Caption: "The perceptron is gradient descent on a single neuron."
- **Talking point:** "Rosenblatt's machine could learn. The hype was enormous -- the press said it would think like a human. Then came the crash."

### Slide 57: The XOR Problem and AI Winter
- **Key message:** In 1969, Minsky and Papert proved that a single-layer perceptron cannot learn the XOR function. This result was overgeneralized, and AI research funding collapsed for nearly two decades.
- **Historical persons:**
  - **Marvin Minsky** (1927-2016, New York City, USA) and **Seymour Papert** (1928-2016, Pretoria, South Africa / USA). Published "Perceptrons" (1969), a rigorous mathematical analysis of single-layer perceptrons. Their proof that a single layer cannot compute XOR was correct. But the field interpreted it (and Minsky/Papert were perceived as implying) that multi-layer networks were equally limited, which was wrong.
- **Visual:** The XOR truth table and a scatter plot showing that XOR is not linearly separable. Caption: "A single line cannot separate the 1s from the 0s. A perceptron can only draw a single line. Therefore: a perceptron cannot learn XOR."
- **Visual 2:** A timeline showing the "AI Winter" (~1969-1986): funding dried up, neural network research became unfashionable.
- **Talking point:** "Minsky and Papert's math was correct. But the conclusion the field drew -- that neural networks are a dead end -- was wrong. The solution was right there: add more layers."

### Slide 58: Multi-Layer Networks -- The Comeback
- **Key message:** Multi-layer perceptrons (MLPs) CAN learn XOR and much more. The key was backpropagation (Section 2) applied to multi-layer networks.
- **Historical connection:** The 1986 Rumelhart/Hinton/Williams paper (already covered in Slide 22) demonstrated that backpropagation could train multi-layer networks. This ended the AI winter and relaunched neural network research.
- **Visual:** A multi-layer network solving XOR: input layer -> hidden layer -> output layer. The hidden layer creates a nonlinear boundary. Caption: "Two layers CAN separate XOR. The AI winter was caused by stopping one layer too soon."
- **Talking point:** "It took 17 years for the field to recover from Perceptrons. When backpropagation showed that multi-layer networks could learn, neural networks came roaring back."

### Slide 59: Activation Functions -- The Spice That Makes It Work
- **Key message:** Without a nonlinear activation function, a multi-layer network collapses to a single layer (matrix multiplication is linear). The activation function is what gives neural networks their power.
- **Historical lineage:**
  - **Sigmoid function:** 1/(1 + exp(-x)). A smooth S-curve. Used since the 1980s. Related to the logistic function of **Pierre Francois Verhulst** (1804-1849, Brussels, Belgium), who used it to model population growth (1838/1845). [VERIFY: Verhulst's logistic function dates -- 1838 or 1845 or both?]
  - **ReLU (Rectified Linear Unit):** max(0, x). Popularized by **Vinod Nair** and **Geoffrey Hinton** (2010) for deep networks. Simpler, faster, and avoids the "vanishing gradient" problem of sigmoid. [VERIFY: Nair/Hinton 2010 ICML paper as the key popularization, though ReLU-like functions appeared earlier (e.g., Hahnloser et al. 2000)]
  - **GELU (Gaussian Error Linear Unit):** Used in modern transformers (GPT, BERT). Introduced by **Dan Hendrycks** and **Kevin Gimpel** (2016). [VERIFY: Hendrycks/Gimpel 2016]
- **Visual:** Three activation function curves plotted side by side:
  - Sigmoid: smooth S-curve, labeled "1980s-2000s"
  - ReLU: a hockey stick (flat at 0, then linear), labeled "2010s"
  - GELU: a smooth version of ReLU, labeled "2016-present (used in GPT)"
  - Caption: "These simple curves are what make neural networks nonlinear -- and therefore powerful."
- **Talking point:** "Without activation functions, stacking 100 layers of matrix multiplication would be the same as one layer. The activation function adds the nonlinearity. It's a small thing that makes everything else work."

### Slide 60: The Depth Problem -- Residual Connections and Skip Connections
- **Key message:** Deeper networks should be more powerful, but in practice, adding layers made networks WORSE. The gradient signal degrades as it passes through many layers. Residual connections solved this by letting information skip over layers.
- **Historical person:**
  - **Kaiming He** (born c. 1984, China/USA) and colleagues. Published "Deep Residual Learning for Image Recognition" (2015, also known as the ResNet paper). They introduced the residual connection (skip connection): instead of each layer computing a completely new output, it computes a CHANGE to the input. Mathematically: output = input + layer(input). This simple idea allowed networks to go from ~20 layers to 152 layers (and eventually hundreds more).
- **Visual 1:** Side-by-side comparison:
  - Left: Standard deep network. Signal weakens layer by layer (fading color). After 50 layers, the gradient is nearly zero.
  - Right: ResNet with skip connections. An arrow "skips over" each block, carrying the original signal forward. The gradient stays strong.
- **Visual 2:** The residual connection formula drawn as a simple diagram: input -> [layer computation] -> ADD the input back -> output. The "ADD" is highlighted: "This is the 'Add' in the transformer's 'Add & Norm' block."
- **Talking point:** "He's insight was deceptively simple: instead of asking each layer to compute the full answer, ask it to compute the DIFFERENCE from the input. If a layer has nothing useful to add, it can output zero and the input passes through unchanged. This allowed networks to go from 20 layers to 1,000 layers."
- **LLM connection:** "Every transformer block has a residual connection. The 'Add & Norm' label on the transformer diagram? The 'Add' is He's residual connection from 2015. Without it, transformers could not be deep."

### Slide 61: Layer Normalization and Dropout -- Stabilizing Deep Networks
- **Key message:** Two more engineering innovations were needed to make deep networks trainable: normalization (keeping activations from exploding or vanishing) and dropout (preventing overfitting).
- **Historical persons:**
  - **Jimmy Lei Ba**, **Jamie Ryan Kiros**, **Geoffrey Hinton**. Published "Layer Normalization" (2016). Layer normalization adjusts the outputs of each layer so they have a consistent mean and variance. This stabilizes training and speeds up convergence. [VERIFY: Ba et al. 2016 -- confirm it was an arXiv preprint, not a peer-reviewed venue initially]
  - **Nitish Srivastava**, **Geoffrey Hinton**, **Alex Krizhevsky**, **Ilya Sutskever**, **Ruslan Salakhutdinov**. Published "Dropout: A Simple Way to Prevent Neural Networks from Overfitting" (2014, JMLR). Dropout randomly deactivates neurons during training, forcing the network to learn robust features rather than memorizing. [VERIFY: Srivastava et al. 2014 JMLR as the definitive paper, though Hinton proposed the idea earlier in 2012]
- **Visual 1:** Layer normalization illustrated: a row of neuron activations before normalization (wildly varying heights), then after normalization (centered around zero with consistent spread). Caption: "Layer Norm = rescale so nothing explodes."
- **Visual 2:** Dropout illustrated: a network with some neurons crossed out (deactivated). Caption: "Dropout = randomly disable neurons during training. Like studying for an exam by covering random notes -- you learn the material, not the page layout."
- **Mathematical content (CONCEPTUAL):** Layer Norm "Recipe: (1) Compute the average of all neuron outputs in a layer. (2) Compute how spread out they are. (3) Subtract the average and divide by the spread. Now they are centered at zero with consistent scale."
- **Talking point:** "Layer normalization is the 'Norm' in the transformer's 'Add & Norm.' Dropout is used during training. Both are invisible to the user but essential for making deep networks work."
- **LLM connection:** "In the transformer, every sub-layer (attention, feed-forward) is followed by Add & Norm. The 'Add' is He's residual connection. The 'Norm' is Ba's layer normalization. These two ideas, both from the 2010s, made the transformer possible."

### Slide 62: Convergence Diagram Update -- The Neuron & Depth
- **Visual:** Convergence diagram with "The Neuron & Depth" node lit in yellow/gold. Label: "Activation + normalization + residuals = deep networks."
- **Summary box:**
  - McCulloch-Pitts (1943): First mathematical neuron
  - Rosenblatt (1958): Perceptron -- a neuron that learns
  - Minsky/Papert (1969): XOR problem, AI winter
  - Rumelhart/Hinton/Williams (1986): Multi-layer revival via backpropagation
  - Verhulst (1838/1845) -> Sigmoid: Population growth curve becomes activation function
  - Nair/Hinton (2010): ReLU
  - Srivastava/Hinton et al. (2014): Dropout
  - He et al. (2015): Residual connections (ResNet)
  - Ba/Kiros/Hinton (2016): Layer normalization
  - Hendrycks/Gimpel (2016): GELU
- **Connection arrow:** "The artificial neuron, with its activation function, is the basic unit. Residual connections, layer normalization, and dropout are what allow transformers to be DEEP. There are billions of neurons in GPT, stacked 96+ layers."
- **Transition:** "We can build neurons, stack them into deep layers, and train them. But language is SEQUENTIAL -- word order matters. How do you process a sequence? That took another set of inventions."

---

## SECTION 8: SEQUENCE MODELING -- "The Path to Language" (Slides 63-68)

**Section color:** Teal (matching `enlightenmentTeal`)
**Connection arrow:** Markov chains, RNNs, LSTMs, and attention mechanisms form the intellectual lineage leading directly to the transformer.

### Slide 63: Section Divider -- "Sequence Modeling: The Path to Language"
- **Visual:** Section title overlaid on a sentence with arrows connecting words to later words (attention visualization). Convergence diagram with Section 8 pulsing.
- **Timeline marker:** 1906-2014
- **Tagline:** "Language is a sequence. Modeling sequences required 100 years of invention."

### Slide 64: Markov Chains -- The Simplest Language Model
- **Key message:** A Markov chain predicts the next state based only on the current state, ignoring all history. This is the simplest model of sequential data.
- **Historical person:**
  - **Andrey Markov** (1856-1922, Ryazan, Russia). Introduced Markov chains (1906) by analyzing the alternation of vowels and consonants in Pushkin's poem "Eugene Onegin." He was not studying language per se -- he was disproving a claim that the law of large numbers required independence. But his method became the foundation of all sequence modeling. [VERIFY: the "Eugene Onegin" analysis is dated to 1913 in some sources, while the mathematical framework was published in 1906. Clarify the distinction]
- **Visual:** A state diagram: states are words ("the", "cat", "sat", "on"), arrows labeled with transition probabilities. Caption: "A Markov chain predicts the next word from the current word only."
- **Visual 2:** Text generated by a Markov chain vs. text generated by an LLM. The Markov text is grammatical locally but incoherent globally.
- **Talking point:** "Markov analyzed poetry to prove a point about probability theory. His chain model became the ancestor of every language model, including the one in your phone's autocomplete."

### Slide 65: Hidden Markov Models -- Adding Depth
- **Key message:** HMMs add a hidden state layer -- the observed output depends on an unobserved internal state. Used for speech recognition and early NLP for decades.
- **Historical persons:**
  - **Leonard Baum** ([VERIFY: dates not found]) and colleagues (USA). Developed the mathematical framework for HMMs and the Baum-Welch algorithm (1960s-1972) for training them. [VERIFY: Baum-Welch algorithm dates -- key papers in 1966, 1970, and 1972. Baum's full name and dates are surprisingly hard to pin down]
- **Visual:** An HMM diagram: hidden states on top (connected by transition arrows), observed outputs below (connected to hidden states by emission arrows). Caption: "The hidden states can't be seen directly -- they must be inferred from observations."
- **LLM connection:** "Speech recognition used HMMs for 30+ years before deep learning replaced them. The idea of 'hidden internal states' that produce observable outputs is conceptually similar to the hidden layers of a neural network."

### Slide 66: Recurrent Neural Networks -- Memory in a Loop
- **Key message:** RNNs process sequences by maintaining a hidden state that is updated at each step. They were the first neural networks that could handle variable-length input.
- **Historical persons:**
  - **Michael Jordan** (born 1956, USA). Introduced the Jordan network (1986), an early form of recurrent neural network. [VERIFY: Jordan's 1986 paper -- sometimes cited as 1986 technical report]
  - **Jeffrey Elman** (1948-2018, USA). Published the Elman network (1990), the form of RNN most commonly referenced: the hidden state at time t is fed back as input at time t+1.
- **Speaker note:** "Yes, Michael Jordan the computer scientist. He is one of the most influential figures in machine learning, and students may enjoy knowing that the field has its own Michael Jordan."
- **Visual:** An RNN unrolled across time steps: the same network processing word 1, then word 2, then word 3, with the hidden state carried forward like a "memory" arrow. Caption: "The hidden state is the RNN's memory. But it's a very LEAKY memory."
- **Talking point:** "RNNs have a fatal flaw: the hidden state gets overwritten at each step. By the time you've read 50 words, the memory of word 1 has been washed away. This is the vanishing gradient problem."

### Slide 67: LSTM -- Long Short-Term Memory [EXTENDED]
- **Key message:** LSTMs solved the vanishing gradient problem by adding explicit "memory cells" with gates that control what to remember and what to forget.
- **Historical persons:**
  - **Sepp Hochreiter** (born 1967, Austria) and **Jurgen Schmidhuber** (born 1963, Munich, Germany). Published "Long Short-Term Memory" (1997). Hochreiter's diploma thesis (1991, supervised by Schmidhuber) identified the vanishing gradient problem. The 1997 LSTM paper provided the solution. [VERIFY: Hochreiter's 1991 diploma thesis as the vanishing gradient analysis]
- **Visual:** An LSTM cell diagram (simplified): input gate, forget gate, output gate, cell state. Caption: "The forget gate decides what to remember. The input gate decides what's new. The output gate decides what to reveal."
- **Talking point:** "LSTM was the dominant architecture for language tasks from the late 1990s through 2017. Google Translate used LSTMs. But there was a problem: LSTMs process words one at a time. You can't parallelize them. This bottleneck led to the key idea that changed everything: attention."

### Slide 68: The Attention Mechanism -- The Bridge to Transformers
- **Key message:** Instead of compressing the entire input into a fixed-size hidden state, attention lets the model LOOK BACK at all previous positions and decide which ones are relevant.
- **Historical persons:**
  - **Dzmitry Bahdanau** (Belarus/Canada), **Kyunghyun Cho** (South Korea/Canada), **Yoshua Bengio** (France/Canada). Published "Neural Machine Translation by Jointly Learning to Align and Translate" (2014, arXiv; 2015, ICLR), introducing the attention mechanism for neural machine translation. The key insight: let the decoder attend to different parts of the encoder's output at each step.
- **Visual 1:** An attention diagram: the model is translating "Le chat est sur le tapis." When generating the word "cat," it attends strongly to "chat." When generating "mat," it attends to "tapis." Color-coded attention weights shown as lines of varying thickness.
- **Visual 2:** Comparison: RNN (compresses everything into one vector) vs. Attention (can look back at everything). Caption: "Attention = the ability to look back and focus."
- **Talking point:** "Bahdanau's insight was simple but transformative: why compress everything into one vector when you can look back at the whole input? This idea -- attention -- became the core of the transformer. Without this 2014 paper, there would be no GPT, no Claude, no ChatGPT."
- **Convergence diagram update:** "Sequence Modeling" node lit in teal. Label: "Attention = context."
- **Transition:** "We now have ALL the building blocks. It's time to put them together."

---

## SECTION 9: THE TRANSFORMER -- "Where Everything Converges" (Slides 69-74)

**Section color:** A gradient/multicolor representing convergence of all sections
**Connection arrow:** This IS the convergence point. The transformer uses every previous building block.

### Slide 69: Section Divider -- "The Transformer: Where Everything Converges"
- **Visual:** The convergence diagram, now with 8 of 10 nodes lit. Section 9 pulsing. Caption: "2017: Eight branches of mathematics meet in one architecture."
- **Timeline marker:** 2017
- **Tagline:** "Attention Is All You Need."

### Slide 70: "Attention Is All You Need" -- The Paper That Changed AI
- **Key message:** In 2017, a team at Google published a paper proposing an architecture that used ONLY attention (no recurrence, no convolution). It was simpler, faster, and better.
- **Historical persons:**
  - **Ashish Vaswani**, **Noam Shazeer**, **Niki Parmar**, **Jakob Uszkoreit**, **Llion Jones**, **Aidan Gomez**, **Lukasz Kaiser**, **Illia Polosukhin**. Published "Attention Is All You Need" (2017, NeurIPS). Eight authors, most in their 20s and 30s. Several have since founded major AI companies (Cohere, Adept, Character.AI). [VERIFY: Which authors founded which companies -- Gomez founded Cohere, Jones and Shazeer co-founded Character.AI. Confirm details]
- **Visual 1:** The first page of the "Attention Is All You Need" paper, with the title highlighted
- **Visual 2:** Photo or stylized portraits of the eight authors. Caption: "Eight researchers. One paper. The architecture that powers every major LLM."
- **Talking point:** "The title is bold: 'Attention Is All You Need.' They were right. This single architecture -- the transformer -- is the foundation of GPT, Claude, Gemini, and virtually every LLM in existence."

### Slide 71: Self-Attention -- The Core Mechanism
- **Key message:** Self-attention allows every token in a sentence to attend to every other token, creating a rich web of contextual relationships.
- **Visual:** The Query-Key-Value mechanism, step by step:
  1. Each token generates three vectors: a Query ("what am I looking for?"), a Key ("what do I contain?"), and a Value ("what information do I carry?")
  2. Attention score = dot product of Query and Key (Slide 10!)
  3. Scores are scaled (divided by sqrt(d) to keep numbers manageable)
  4. Scores are normalized by softmax (Slide 33!)
  5. Output = weighted sum of Values
  6. Each step is labeled with its mathematical origin AND the slide where it was taught: "dot product (Gibbs, Slide 10)", "softmax (Boltzmann, Slide 33)", "matrix multiplication (Cayley, Slide 9)", "cosine-like scaling (Slide 11)"
- **Caption:** "Self-attention is the convergence point. Linear algebra, probability, and information theory, all in one equation."
- **Speaker note:** Walk through a concrete example: in "The cat sat on the mat because it was tired," the word "it" attends most strongly to "cat" (self-attention learns that "it" refers to "cat"). This is how the model resolves references across a sentence.

### Slide 72: The Feed-Forward Block and Multi-Head Attention
- **Key message:** Each transformer layer has two sub-blocks: multi-head attention (look at context from multiple angles) and a feed-forward network (process each token independently).
- **Multi-Head Attention:** Instead of one set of Q/K/V, the transformer uses multiple "heads" (8, 12, or more) in parallel. Each head learns to attend to different types of relationships (syntax, semantics, position, etc.). Results are concatenated and projected back.
- **Feed-Forward Network (FFN):** Two matrix multiplications with an activation function (GELU) in between. This is the universal approximation theorem (Cybenko, Slide 52) applied within each transformer layer -- the FFN provides the raw computational power to transform representations.
- **Visual:** A single transformer block annotated:
  - Multi-Head Attention sub-block -> Add & Norm (residual + layer norm, Slide 60-61)
  - Feed-Forward Network sub-block -> Add & Norm (residual + layer norm, Slide 60-61)
  - Every component labeled with its origin section
- **Talking point:** "One transformer layer = attention + feed-forward + two rounds of 'add & normalize.' Stack 96 of these layers and you have GPT-4. Every component was taught in an earlier section of this lecture."

### Slide 73: The Full Transformer -- Annotated with 2,000+ Years of Math
- **Key message:** THIS is the payoff slide. The complete transformer architecture, with every component labeled with its mathematical origin.
- **Visual (FULL SLIDE -- this is the lecture's climax):** The standard transformer diagram (decoder-only, as used in GPT/Claude), with annotations:
  - **Input Embedding:** "Words -> Vectors" (Grassmann 1844, Mikolov/Word2Vec 2013, Slide 14)
  - **Positional Encoding:** "Sine/cosine functions" (Fourier 1807, Slide 50)
  - **Multi-Head Self-Attention:** "Dot product + softmax + matrix multiplication" (Gibbs 1880s Slide 10, Boltzmann 1870s Slide 33, Cayley 1858 Slide 9, Bahdanau 2014 Slide 68)
  - **Add & Norm (Residual connection + Layer Normalization):** "Skip connections + normalize" (He et al. 2015 Slide 60, Ba et al. 2016 Slide 61)
  - **Feed-Forward Network:** "Two matrix multiplications + GELU activation" (Cybenko 1989 Slide 52, Hendrycks/Gimpel 2016 Slide 59)
  - **Dropout** (during training): "Random deactivation" (Srivastava/Hinton 2014 Slide 61)
  - **Add & Norm** (again after FFN)
  - **Output Linear + Softmax:** "Probability distribution over vocabulary" (Fisher 1922, Boltzmann/Luce Slide 33)
  - **Training (not shown in architecture, but labeled):** "Cross-entropy loss + backpropagation + SGD" (Shannon 1948, Cauchy 1847, Robbins-Monro 1951, Linnainmaa 1970)
  - **Hardware (not shown, but labeled):** "GPU arrays" (NVIDIA CUDA 2007, Krizhevsky/AlexNet 2012)
- **Verification check:** Every labeled component on this diagram references a specific earlier slide where the concept was introduced.
- **Interactive moment:** "Count the building blocks" -- students try to identify which of the 10 sections each component comes from. (3 min)
- **Talking point:** "Look at this diagram. Every single piece has a history. The sine functions come from Fourier in 1807. The matrix multiplications come from Cayley in 1858. The softmax comes from Boltzmann in the 1870s. The training algorithm uses Cauchy's gradient descent from 1847 and Linnainmaa's automatic differentiation from 1970. The residual connections come from He in 2015. The layer normalization from Ba in 2016. When you talk to an AI, you're talking to 2,000 years of mathematics, all running at once."
- **Speaker note:** Let this land. Pause. This is the central thesis of the entire lecture, crystallized in one diagram.

### Slide 74: Positional Encoding -- Fourier Meets Transformers
- **Key message:** Transformers have no built-in notion of word order (unlike RNNs). To fix this, they add "positional encodings" -- sine and cosine functions at different frequencies. This is Fourier's idea, applied directly.
- **Mathematical content (CONCEPTUAL):** "Recipe: For each position in the sentence (1st word, 2nd word, ...) and each dimension in the vector, compute a sine or cosine wave with a specific frequency. Different dimensions use different frequencies -- just like Fourier's decomposition. The result: each position gets a unique 'fingerprint' of wave values."
  - **Small inset (formal):** PE(pos, 2i) = sin(pos / 10000^(2i/d)), PE(pos, 2i+1) = cos(pos / 10000^(2i/d)). Note: "The 10000^(2i/d) creates a spectrum of frequencies from very slow (position changes slowly) to very fast. The pattern is the same idea as Fourier's decomposition."
- **Visual:** A heatmap of positional encodings: rows = positions (1st word, 2nd word, ..., 100th word), columns = dimensions. The resulting pattern shows clear sinusoidal waves. Caption: "Fourier's sine and cosine waves, used to tell the transformer which word is which."
- **Talking point:** "Fourier decomposed heat into waves. Vaswani decomposed word position into waves. The same math, 210 years apart, for completely different purposes."
- **Convergence diagram update:** ALL 10 nodes now lit (Sections 9 and 10). Central "?" becomes "TRANSFORMER." The full convergence diagram is complete.

---

## SECTION 10: SCALING TO LLMs + CLOSING (Slides 75-78)

**Section color:** Multi/gradient (the full spectrum)
**Connection arrow:** This is the endpoint. All building blocks, at enormous scale, produce the LLMs students use daily.

### Slide 75: The Scaling Leap -- From Transformer to LLM
- **Key message:** The transformer architecture, scaled up with more parameters, more data, and more compute, produces Large Language Models with emergent abilities.
- **Key developments:**
  - **GPT-1** (2018, OpenAI, 117M parameters): Demonstrated that pre-training a transformer on large text and fine-tuning works
  - **GPT-2** (2019, 1.5B parameters): Text generation so convincing OpenAI initially withheld the full model
  - **GPT-3** (2020, 175B parameters): Demonstrated few-shot learning -- the model could perform tasks it was never explicitly trained for
  - **GPT-4** (2023, parameter count not publicly confirmed by OpenAI): Multimodal, substantially more capable
  - **Claude** (Anthropic, 2023-2026): Constitutional AI, RLHF refinement
  - **Scaling laws:** **Jared Kaplan** et al. (2020) showed that LLM performance scales as a smooth power law with compute, data, and parameters. [VERIFY: Kaplan et al. 2020 OpenAI scaling laws paper]
- **Visual 1:** A log-log plot showing parameter count vs. year: GPT-1 (2018) -> GPT-2 (2019) -> GPT-3 (2020) -> PaLM (2022) -> GPT-4 (2023) -> current frontier models (2025-2026). The growth is exponential.
- **Visual 2:** Timeline showing key milestones: RLHF (Christiano et al. 2017), InstructGPT (2022), ChatGPT (Nov 2022), GPT-4 (Mar 2023), Claude 3 (2024), open-source explosion (Llama, Mistral)
- **Talking point:** "The transformer is the same architecture from 2017. What changed is scale. More parameters, more training data, more compute. And somewhere along the way, these models started doing things nobody programmed them to do -- reasoning, writing code, translating languages they were barely trained on."
- **[VERIFY]:** Christiano et al. 2017 for RLHF. InstructGPT paper date (Ouyang et al. 2022). ChatGPT launch date (November 30, 2022). Model release dates for Claude, Gemini, Llama.

### Slide 76: Return to the Exploded Diagram -- Now You Understand Every Piece
- **Key message:** Return to the "overwhelming" exploded diagram from Slide 3. Now, every piece is labeled, understood, and historically grounded.
- **Visual:** The exact same exploded transformer diagram from Slide 3, but now each label includes the mathematician's name, date, AND the slide number where it was taught:
  - "Matrix multiplication (Cayley, 1858 -- Slide 9)"
  - "Dot product (Gibbs, 1880s -- Slide 10)"
  - "Gradient descent (Cauchy, 1847 -- Slide 21)"
  - "Softmax (Boltzmann, 1870s -- Slide 33)"
  - "Cross-entropy (Shannon, 1948 -- Slide 37)"
  - "Backpropagation (Linnainmaa 1970, Rumelhart/Hinton/Williams 1986 -- Slide 22)"
  - "Activation functions (Verhulst 1838, Nair/Hinton 2010 -- Slide 59)"
  - "Residual connections (He et al. 2015 -- Slide 60)"
  - "Layer normalization (Ba et al. 2016 -- Slide 61)"
  - "Self-attention (Bahdanau 2014, Vaswani 2017 -- Slides 68, 71)"
  - "Positional encoding (Fourier, 1807 -- Slide 74)"
  - "GPU computing (NVIDIA CUDA, 2007 -- Slide 47)"
- **Caption:** "You now know the history of every piece of this machine."
- **Speaker note:** "At the start of this lecture, this diagram was overwhelming. Now you can point to each piece and say who invented it, when, and why. That's the power of understanding the history."

### Slide 77: Convergence Diagram -- Final State
- **Visual:** The completed convergence diagram with all 10 nodes lit and the central "TRANSFORMER" node glowing. Each node label now includes its cumulative date range:
  1. Linear Algebra (1809-2013) -- blue
  2. Calculus & Optimization (c. 250 BCE-1986) -- green
  3. Probability & Statistics (1654-1959) -- orange
  4. Information Theory (1865-2016) -- red
  5. Logic & Computation (1854-2012) -- gray
  6. Function Approximation (1807-1991) -- purple
  7. The Neuron & Depth (1943-2016) -- yellow
  8. Sequence Modeling (1906-2014) -- teal
  9. The Transformer (2017) -- multicolor
  10. Scaling to LLMs (2018-2026) -- gradient
- **Caption:** "Ten streams of human invention, flowing into one machine."

### Slide 78: Closing -- The Story Is Not Over
- **Key content:**
  - "Every component of an LLM was invented by someone, for a specific purpose, often centuries before AI existed."
  - "Grassmann imagined abstract vector spaces. Boltzmann studied gas molecules. Fourier solved the heat equation. Markov analyzed poetry. Archimedes approximated circles. None of them imagined AI."
  - "The math you learn in school -- algebra, calculus, probability -- is the same math running inside the AI you talk to every day."
  - "The next building block hasn't been invented yet. It might come from pure mathematics, from physics, from linguistics, from neuroscience -- or from someone in this room."
- **Visual:** The completed convergence diagram, with all 10 nodes lit and the central "TRANSFORMER" node glowing. Below it: "2,000+ years of mathematics. One machine. Your turn."
- **Final talking point:** "When you talk to an AI, you are talking to the accumulated genius of Archimedes, Grassmann, Cayley, Newton, Leibniz, Cauchy, Boltzmann, Shannon, Turing, Mikolov, McCulloch, Pitts, Rosenblatt, Hochreiter, Schmidhuber, Bahdanau, Vaswani, and dozens of others. Two thousand years of human curiosity, all running at once, on hardware that Boole's algebra made possible. The next invention is yours."

---

## COMPLETE MATHEMATICIAN / SCIENTIST REFERENCE TABLE

| # | Name | Dates | Origin | Key Contribution to LLMs | Slide | Building Block |
|---|------|-------|--------|--------------------------|-------|----------------|
| 1 | Hermann Grassmann | 1809-1877 | Stettin, Prussia | Vector spaces, abstract linear algebra | 6 | Linear Algebra |
| 2 | Sir William Rowan Hamilton | 1805-1865 | Dublin, Ireland | Quaternions, extended number systems | 6 | Linear Algebra |
| 3 | Josiah Willard Gibbs | 1839-1903 | New Haven, USA | Modern vector notation, dot product, Gibbs distribution | 7, 10, 33 | Linear Algebra, Probability |
| 4 | Oliver Heaviside | 1850-1925 | London, England | Vector calculus notation | 7 | Linear Algebra |
| 5 | Arthur Cayley | 1821-1895 | Richmond, England | Matrix theory (1858) | 8 | Linear Algebra |
| 6 | James Joseph Sylvester | 1814-1897 | London, England | Coined "matrix" (1850) | 8 | Linear Algebra |
| 7 | Carl Friedrich Gauss | 1777-1855 | Brunswick, Germany | Gaussian elimination, least squares | 9 | Linear Algebra |
| 8 | Leonhard Euler | 1707-1783 | Basel/St. Petersburg/Berlin | Eigenvalue concepts | 12 | Linear Algebra |
| 9 | Augustin-Louis Cauchy | 1789-1857 | Paris, France | Real eigenvalues of symmetric matrices, steepest descent (1847) | 12, 21 | Linear Algebra, Calculus |
| 10 | David Hilbert | 1862-1943 | Konigsberg/Gottingen | Spectral theory, infinite-dimensional spaces | 12 | Linear Algebra |
| 11 | Richard Bellman | 1920-1984 | New York City, USA | Curse of dimensionality (1957) | 13 | Linear Algebra |
| 12 | Tomas Mikolov | -- [VERIFY: dates not found] | Czech Republic / USA | Word2Vec (2013), word vector arithmetic | 13, 14 | Linear Algebra |
| 13 | Pierre de Fermat | 1601-1665 | Beaumont-de-Lomagne, France | Tangent lines, proto-derivatives; probability (with Pascal) | 19, 27 | Calculus, Probability |
| 14 | Isaac Newton | 1642-1726/27 | Woolsthorpe, England | Calculus (fluxions) | 19 | Calculus |
| 15 | Gottfried Wilhelm Leibniz | 1646-1716 | Leipzig, Germany | Calculus (dy/dx notation), chain rule | 19, 20 | Calculus |
| 16 | Archimedes of Syracuse | c. 287-212 BCE | Syracuse, Sicily | Method of exhaustion, proto-calculus | 18 | Calculus |
| 17 | Seppo Linnainmaa | born 1945 | Finland | Automatic differentiation (1970) | 22 | Calculus |
| 18 | David Rumelhart | 1942-2011 | USA | Backpropagation for neural nets (1986) | 22 | Calculus |
| 19 | Geoffrey Hinton | born 1947 | London, UK/Canada | Backpropagation, deep learning, ReLU, dropout, layer norm; Nobel Prize in Physics 2024 (shared with Hopfield) | 22, 47, 59, 61 | Calculus, Computation, Neuron |
| 20 | Ronald Williams | [VERIFY: dates not found] | USA | Backpropagation for neural nets (1986) | 22 | Calculus |
| 21 | Herbert Robbins | 1915-2001 | New Castle, PA, USA | Stochastic approximation (1951) | 23 | Calculus |
| 22 | Sutton Monro | 1920-1995 [VERIFY: dates uncertain] | USA | Stochastic approximation (1951) | 23 | Calculus |
| 23 | Blaise Pascal | 1623-1662 | Clermont-Ferrand, France | Probability theory (1654) | 27 | Probability |
| 24 | Jacob Bernoulli | 1655-1705 | Basel, Switzerland | Law of large numbers | 28 | Probability |
| 25 | Pierre-Simon Laplace | 1749-1827 | Beaumont-en-Auge, France | Systematized probability, popularized Bayes | 28, 29 | Probability |
| 26 | Thomas Bayes | c. 1701-1761 | London, England | Bayes' theorem (published 1763) | 29 | Probability |
| 27 | Andrey Kolmogorov | 1903-1987 | Tambov, Russia | Probability axioms (1933) | 30 | Probability |
| 28 | Ronald A. Fisher | 1890-1962 | London, England | Maximum likelihood estimation (1922) | 31 | Probability |
| 29 | Claude Shannon | 1916-2001 | Petoskey, MI, USA | Information theory, statistical language models (1948) | 32, 36 | Probability, Information Theory |
| 30 | Ludwig Boltzmann | 1844-1906 | Vienna, Austria | Boltzmann distribution, statistical entropy | 33, 36 | Probability, Information Theory |
| 31 | R. Duncan Luce | 1925-2012 | Scranton, PA, USA | Choice axiom (1959), mathematical basis of softmax | 33 | Probability |
| 32 | Rudolf Clausius | 1822-1888 | Koslin, Prussia | Thermodynamic entropy (1865) | 36 | Information Theory |
| 33 | Solomon Kullback | 1907-1994 | USA | KL divergence (1951) | 39 | Information Theory |
| 34 | Richard Leibler | 1914-2003 | USA | KL divergence (1951) | 39 | Information Theory |
| 35 | George Kingsley Zipf | 1902-1950 | Freeport, IL, USA | Zipf's law of word frequencies | 40 | Information Theory |
| 36 | Rico Sennrich | [VERIFY: dates not found] | Edinburgh, UK | BPE for NMT (2016) | 40 | Information Theory |
| 37 | George Boole | 1815-1864 | Lincoln, England / Cork, Ireland | Boolean algebra (1854) | 43 | Logic & Computation |
| 38 | Gottlob Frege | 1848-1925 | Wismar, Germany | Formal logic, Begriffsschrift (1879) | 44 | Logic & Computation |
| 39 | Bertrand Russell | 1872-1970 | Trellech, Wales, UK | Principia Mathematica (1910-1913) | 44 | Logic & Computation |
| 40 | Alfred North Whitehead | 1861-1947 | Ramsgate, England | Principia Mathematica (1910-1913) | 44 | Logic & Computation |
| 41 | Kurt Godel | 1906-1978 | Brno, Austria-Hungary / USA | Incompleteness theorems (1931) | 44 | Logic & Computation |
| 42 | Alan Turing | 1912-1954 | London, England | Turing machine (1936), computability, halting problem | 44 | Logic & Computation |
| 43 | John von Neumann | 1903-1957 | Budapest, Hungary / USA | Stored-program architecture (1945) | 45 | Logic & Computation |
| 44 | Konrad Zuse | 1910-1995 | Berlin, Germany | Z3 computer, floating-point (1941) | 46 | Logic & Computation |
| 45 | Alex Krizhevsky | [VERIFY: dates not found] | Russia/Canada | AlexNet, GPU training (2012) | 47 | Logic & Computation |
| 46 | Ilya Sutskever | born 1985 [VERIFY] | Russia/Israel/Canada | AlexNet co-author, later co-founded OpenAI | 47 | Logic & Computation |
| 47 | Jean-Baptiste Joseph Fourier | 1768-1830 | Auxerre, France | Fourier series (1807/1822) | 50 | Function Approximation |
| 48 | Karl Weierstrass | 1815-1897 | Ostenfelde, Germany | Polynomial approximation theorem (1885) | 51 | Function Approximation |
| 49 | George Cybenko | born c. 1952 [VERIFY] | Canada/USA | Universal approximation theorem (1989) | 52 | Function Approximation |
| 50 | Kurt Hornik | born c. 1963 [VERIFY] | Austria | Generalized universal approximation (1991) | 52 | Function Approximation |
| 51 | Warren McCulloch | 1898-1969 | Orange, NJ, USA | McCulloch-Pitts neuron (1943) | 55 | The Neuron |
| 52 | Walter Pitts | 1923-1969 | Detroit, MI, USA | McCulloch-Pitts neuron (1943) | 55 | The Neuron |
| 53 | Frank Rosenblatt | 1928-1971 | New Rochelle, NY, USA | Perceptron (1957-1958) | 56 | The Neuron |
| 54 | Marvin Minsky | 1927-2016 | New York City, USA | Perceptrons book, XOR problem (1969) | 57 | The Neuron |
| 55 | Seymour Papert | 1928-2016 | Pretoria, South Africa / USA | Perceptrons book, XOR problem (1969) | 57 | The Neuron |
| 56 | Pierre Francois Verhulst | 1804-1849 | Brussels, Belgium | Logistic/sigmoid function (1838/1845) | 59 | The Neuron |
| 57 | Vinod Nair | [VERIFY: dates not found] | Canada | ReLU activation function (2010) | 59 | The Neuron |
| 58 | Dan Hendrycks | [VERIFY: dates not found] | USA | GELU activation function (2016) | 59 | The Neuron |
| 59 | Kaiming He | born c. 1984 [VERIFY] | China/USA | Residual connections / ResNet (2015) | 60 | The Neuron & Depth |
| 60 | Jimmy Lei Ba | [VERIFY: dates not found] | Canada | Layer normalization (2016) | 61 | The Neuron & Depth |
| 61 | Nitish Srivastava | [VERIFY: dates not found] | Canada | Dropout (2014) | 61 | The Neuron & Depth |
| 62 | Andrey Markov | 1856-1922 | Ryazan, Russia | Markov chains (1906) | 64 | Sequence Modeling |
| 63 | Leonard Baum | [VERIFY: dates not found] | USA | Hidden Markov Models, Baum-Welch algorithm (1960s-70s) | 65 | Sequence Modeling |
| 64 | Michael Jordan (scientist) | born 1956 | USA | Jordan network / RNN (1986) | 66 | Sequence Modeling |
| 65 | Jeffrey Elman | 1948-2018 | USA | Elman network / RNN (1990) | 66 | Sequence Modeling |
| 66 | Sepp Hochreiter | born 1967 | Austria | LSTM (1997), vanishing gradient analysis (1991) | 67 | Sequence Modeling |
| 67 | Jurgen Schmidhuber | born 1963 | Munich, Germany | LSTM (1997) | 67 | Sequence Modeling |
| 68 | Dzmitry Bahdanau | [VERIFY: dates not found] | Belarus/Canada | Attention mechanism for NMT (2014) | 68 | Sequence Modeling |
| 69 | Ashish Vaswani et al. (8 authors) | [VERIFY: individual dates not found] | Google Brain | Transformer architecture, "Attention Is All You Need" (2017) | 70 | The Transformer |

**Total named mathematicians/scientists: 69** (counting the 8 transformer authors as one entry; individually they are Vaswani, Shazeer, Parmar, Uszkoreit, Jones, Gomez, Kaiser, Polosukhin)

---

## VISUAL ASSET MASTER LIST

### Section-Level Visuals

| Section | Visual Type | Description | Suggested Source |
|---------|------------|-------------|-----------------|
| Opening | Composite | Mathematician portraits (including Archimedes) + LLM chat interface | Custom creation |
| Opening | Diagram | Exploded transformer, color-coded by math origin (now includes residual/norm/dropout labels) | Custom creation |
| Opening | Diagram | Convergence diagram (empty, 10 gray nodes) | Custom creation |
| Linear Algebra | Portrait | Grassmann, Hamilton | Wikimedia Commons |
| Linear Algebra | Photo | Brougham Bridge quaternion plaque | Wikimedia Commons |
| Linear Algebra | Diagram | Vector in 2D, 3D, then 768D (fading dots) | Custom creation |
| Linear Algebra | Comparison | Hamilton quaternion notation vs. Gibbs vector notation | Custom creation |
| Linear Algebra | Diagram | Matrix multiplication step-by-step | Custom creation |
| Linear Algebra | Diagram | Same operation as neural network layer | Custom creation |
| Linear Algebra | Diagram | Dot product: two vectors, angle, similarity score | Custom creation |
| Linear Algebra | Diagram | Cosine similarity in embedding space | Custom creation |
| Linear Algebra | Diagram | Eigenvectors under transformation | Custom creation |
| Linear Algebra | Plot | Word embedding space (king/queen/man/woman) with Mikolov attribution | Custom creation |
| Linear Algebra | Diagram | Sentence -> tokenizer -> embedding matrix pipeline | Custom creation |
| Linear Algebra | Diagram | Attention as Q/K/V matrix multiplications (preview) | Custom creation |
| Calculus | Diagram | Archimedes method of exhaustion (polygons in circle) | Custom creation |
| Calculus | Diagram | Fermat tangent / Newton fluxion / Leibniz dy/dx | Custom creation |
| Calculus | Diagram | Chain rule as pipeline / neural network | Custom creation |
| Calculus | 3D Visualization | Loss landscape with gradient descent path | Custom creation or public domain (Li et al. 2018 style) |
| Calculus | Diagram | Forward pass (blue) and backward pass (red) through network | Custom creation |
| Calculus | Comparison | Full gradient descent vs. SGD (smooth vs. noisy path) | Custom creation |
| Probability | Diagram | Pascal-Fermat letter exchange recreation | Custom creation |
| Probability | Chart | Law of large numbers convergence (coin flips) | Custom creation |
| Probability | Formula | Bayes' theorem with medical test example | Custom creation |
| Probability | Diagram | MLE curve fitting | Custom creation |
| Probability | Text | Shannon's n-gram approximations to English | Recreated from 1948 paper |
| Probability | Pipeline | Softmax computation step by step | Custom creation |
| Info Theory | Three-column | Clausius/Boltzmann/Shannon entropy comparison | Custom creation |
| Info Theory | Photo | Boltzmann's tombstone (S = k log W) | Wikimedia Commons |
| Info Theory | Diagram | Cross-entropy loss computation example | Custom creation |
| Info Theory | Chart | Surprisal for expected vs. unexpected words | Custom creation |
| Info Theory | Diagram | BPE tokenization example | Custom creation |
| Logic | Diagram | Boolean gates with truth tables | Custom creation |
| Logic | Manuscript page | Principia Mathematica "1+1=2" page | Public domain |
| Logic | Diagram/Timeline | Boole -> Frege -> Russell -> Godel -> Turing (with limits highlighted) | Custom creation |
| Logic | Diagram | Von Neumann architecture | Custom creation |
| Logic | Comparison | CPU (few cores) vs. GPU (thousands of cores) | Custom creation |
| Func. Approx. | Animation/sequence | Fourier series approximating square wave | Custom creation |
| Func. Approx. | Diagram | Increasing polynomial approximations | Custom creation |
| Func. Approx. | Diagram | Neural network with increasing hidden neurons | Custom creation |
| Neuron | Split image | Biological neuron vs. mathematical neuron vs. deep stack | Custom creation + microscopy (public domain) |
| Neuron | Photo | Mark I Perceptron hardware | Historical photo (public domain) |
| Neuron | Diagram | XOR truth table and scatter plot | Custom creation |
| Neuron | Chart | Three activation functions (sigmoid, ReLU, GELU) | Custom creation |
| Neuron | Diagram | Residual connection: input + layer(input) = output | Custom creation |
| Neuron | Comparison | Without vs. with skip connections (gradient fading) | Custom creation |
| Neuron | Diagram | Layer normalization before/after | Custom creation |
| Neuron | Diagram | Dropout: neurons crossed out | Custom creation |
| Sequence | Diagram | Markov chain state diagram | Custom creation |
| Sequence | Diagram | RNN unrolled across time steps | Custom creation |
| Sequence | Diagram | LSTM cell (simplified) | Custom creation |
| Sequence | Diagram | Attention weights in translation | Custom creation |
| Transformer | Paper | "Attention Is All You Need" first page | Public domain (arXiv) |
| Transformer | Diagram | Q/K/V self-attention step by step (with slide back-references) | Custom creation |
| Transformer | Diagram | Single transformer block: attention + FFN + Add&Norm | Custom creation |
| Transformer | Diagram | Full transformer, annotated with mathematician names AND slide numbers | Custom creation (CLIMAX VISUAL) |
| Transformer | Heatmap | Positional encoding sinusoidal pattern | Custom creation |
| Closing | Chart | Parameter count vs. year (log scale) | Custom creation |
| Closing | Diagram | Exploded diagram from Slide 3, now fully labeled with slide references | Custom creation (reprise) |
| Closing | Diagram | Final convergence diagram, all nodes lit with date ranges | Custom creation (reprise) |

**Total visual assets needed:** ~60
**Custom diagrams needed:** ~50
**Historical photos/manuscripts (existing sources):** ~10

---

## FACT-CHECK REGISTER

All claims tagged [VERIFY] in the plan, consolidated here for systematic verification:

| # | Claim | Location | Issue |
|---|-------|----------|-------|
| 1 | Grassmann's Ausdehnungslehre publication date (1844) | Slide 6 | Standard but verify against primary sources |
| 2 | Hamilton carved quaternion formula on Brougham Bridge (1843) | Slide 6 | Well-documented but verify exact bridge name |
| 3 | Gibbs lecture notes "Elements of Vector Analysis" dates (1881-1884) | Slide 7 | Two printings -- verify exact years |
| 4 | Sylvester coined "matrix" in 1850 vs. 1848 | Slide 8 | Sources disagree -- some say 1848 |
| 5 | Cayley's 1858 paper title | Slide 8 | Verify exact title |
| 6 | Gauss elimination dated c. 1809-1810 | Slide 9 | Chinese precedent (Nine Chapters) should be noted |
| 7 | Euler's eigenvalue work context and dates | Slide 12 | Vibrating strings vs. rotating bodies |
| 8 | Cauchy 1829 result on symmetric matrices | Slide 12 | Verify year and exact statement |
| 9 | Bellman "curse of dimensionality" 1957 vs. 1961 | Slide 13 | May be from 1961 book, not 1957 |
| 10 | Mikolov et al. 2013 Word2Vec papers and venues | Slide 13 | Two papers: arXiv and NeurIPS 2013 |
| 11 | Chain rule attribution -- diffuse, no single inventor | Slide 20 | Present as collective development |
| 12 | Cauchy 1847 steepest descent paper title | Slide 21 | Verify French title |
| 13 | Linnainmaa 1970 Master's thesis vs. PhD | Slide 22 | Commonly stated as Master's -- verify |
| 14 | Earlier backprop-like work (Bryson, Dreyfus, Kelley) | Slide 22 | Note the broader lineage |
| 15 | Hinton/Hopfield Nobel Prize Physics 2024 | Slide 22 | Verify exact citation wording |
| 16 | Monro's dates and birthplace | Slide 23 | Hard to find reliable sources |
| 17 | Bayes' birth year (1701 vs. 1702) | Slide 29 | Uncertain |
| 18 | Kolmogorov 1933 German title | Slide 30 | Verify exact title |
| 19 | Fisher MLE: 1912 vs. 1922 as key date | Slide 31 | Introduced 1912, formalized 1922 |
| 20 | Boltzmann distribution date (1868 vs. 1870s) | Slide 33 | Early papers vs. mature formulation |
| 21 | Luce 1959 book title | Slide 33 | "Individual Choice Behavior" -- verify |
| 22 | Clausius coined "entropy" in 1865 | Slide 36 | Concept from 1850s, term from 1865 |
| 23 | Shannon-von Neumann anecdote about naming entropy | Slide 36 | Widely reported but possibly apocryphal |
| 24 | Kullback-Leibler 1951 paper title | Slide 39 | Verify |
| 25 | Zipf's law: 1935 vs. 1949 book | Slide 40 | Both books exist; 1949 is more commonly cited |
| 26 | Sennrich et al. 2016 ACL paper for BPE | Slide 40 | Verify venue and year |
| 27 | Principia Mathematica page 362 for 1+1=2 | Slide 44 | Commonly cited but may be approximate |
| 28 | Von Neumann 1945 EDVAC report priority controversy | Slide 45 | Note Eckert/Mauchly contributions |
| 29 | Z3 as first floating-point computer (electromechanical) | Slide 46 | Standard claim, note qualification |
| 30 | Krizhevsky et al. AlexNet at NIPS 2012 | Slide 47 | Verify venue (NIPS, now NeurIPS) |
| 31 | Cybenko birth year c. 1952 | Slide 52 | Uncertain |
| 32 | Hornik birth year c. 1963 | Slide 52 | Uncertain |
| 33 | Pitts ran away from home at 15 | Slide 55 | Common claim, details vary |
| 34 | NYT Perceptron article quote and date (1958) | Slide 56 | Verify exact quote and date |
| 35 | Verhulst logistic function: 1838 vs. 1845 | Slide 59 | Both years cited in different sources |
| 36 | Nair/Hinton 2010 ICML as key ReLU paper | Slide 59 | ReLU appeared earlier (Hahnloser 2000) |
| 37 | Hendrycks/Gimpel 2016 for GELU | Slide 59 | Verify year |
| 38 | Kaiming He birth year c. 1984 | Slide 60 | Uncertain |
| 39 | He et al. 2015 ResNet paper | Slide 60 | Verify venue (CVPR 2016? arXiv 2015?) |
| 40 | Ba et al. 2016 Layer Normalization | Slide 61 | Verify -- arXiv preprint vs. peer-reviewed |
| 41 | Srivastava et al. 2014 Dropout paper venue (JMLR) | Slide 61 | Verify; Hinton proposed idea earlier (2012) |
| 42 | Markov's Eugene Onegin analysis: 1906 vs. 1913 | Slide 64 | Mathematical framework 1906, application 1913 |
| 43 | Baum-Welch algorithm dates (1966, 1970, 1972) | Slide 65 | Multiple key papers |
| 44 | Baum's full name and life dates | Slide 65 | Surprisingly hard to pin down |
| 45 | Hochreiter 1991 diploma thesis | Slide 67 | Verify it was a diploma thesis |
| 46 | Transformer author company founding details | Slide 70 | Gomez->Cohere, Jones/Shazeer->Character.AI. Verify |
| 47 | Kaplan et al. 2020 scaling laws | Slide 75 | Verify paper details |
| 48 | Christiano et al. 2017 for RLHF | Slide 75 | Verify year and venue |
| 49 | ChatGPT launch date November 30, 2022 | Slide 75 | Standard but verify |
| 50 | Mikolov dates/origin | Ref table | Not widely documented |

---

## SECTION TRANSITION SCRIPTS

| From | To | Transition Text |
|------|-----|----------------|
| Opening -> Linear Algebra | "Let's start with the most fundamental building block. When an LLM reads your sentence, the first thing it does is convert each word into a vector -- a list of numbers. For that, we need linear algebra." |
| Linear Algebra -> Calculus | "We now have the skeleton of a neural network: matrices, vectors, and dot products. But a skeleton doesn't move. For the network to LEARN -- to get better at predicting words -- it needs to adjust its weights. For that, we need calculus." |
| Calculus -> Probability | "The network can now learn. But learn WHAT, exactly? It learns to predict probability distributions over the next word. For that, we need the mathematics of uncertainty." |
| Probability -> Information Theory | "The network predicts probabilities. But how do we measure whether those probabilities are GOOD? We need a way to score predictions. That scoring function comes from information theory." |
| Information Theory -> Logic & Computation | "We have the math for learning and the math for measuring. But all this math is useless without a machine to run it on. Enter: logic and computation." |
| Logic & Computation -> Function Approximation | "We have math AND hardware. But here's a deep question that deserves an answer: WHY should a pile of matrix multiplications be able to learn anything at all?" |
| Function Approximation -> The Neuron & Depth | "We know neural networks CAN learn any function. But what IS a neural network? Where did the idea come from? And what does it take to make them DEEP? The answer starts in biology and ends in engineering." |
| The Neuron & Depth -> Sequence Modeling | "We can build neurons, stack them into deep layers with residual connections and normalization, and train them. But language is SEQUENTIAL -- word order matters. 'Dog bites man' and 'man bites dog' have the same words but very different meanings. How do you process a sequence?" |
| Sequence Modeling -> The Transformer | "We have all the pieces. Vectors, matrices, dot products, calculus, probability, entropy, logic, universal approximation, neurons, activation functions, residual connections, layer normalization, sequence models, and attention. In 2017, eight researchers put them all together." |
| The Transformer -> Closing | "The transformer is the architecture. Scaling it up -- more parameters, more data, more compute -- is what turned it into the LLMs you use every day." |

---

## COMMIT STRATEGY

**Decision: Standalone file** (`llm-building-blocks.tex`) rather than a section within the main lecture, given the 78-slide scope and independent narrative. Can be `\include`-ed later if desired.

1. **Commit 1:** Create `llm-building-blocks.tex` with Beamer preamble and Section 0 (Opening, Slides 1-4)
2. **Commit 2:** Section 1 (Linear Algebra, Slides 5-16, including new dot product/cosine/Word2Vec slides) and Section 2 (Calculus & Optimization, Slides 17-25)
3. **Commit 3:** Section 3 (Probability & Statistics, Slides 26-34) and Section 4 (Information Theory, Slides 35-41)
4. **Commit 4:** Section 5 (Logic & Computation, Slides 42-48) and Section 6 (Function Approximation, Slides 49-53)
5. **Commit 5:** Section 7 (The Neuron & Depth, Slides 54-62, including new residual/layer norm/dropout slides) and Section 8 (Sequence Modeling, Slides 63-68)
6. **Commit 6:** Section 9 (The Transformer, Slides 69-74, including new FFN/multi-head slide) and Section 10 (Closing, Slides 75-78)
7. **Commit 7:** Convergence diagram TikZ code (recurring across all sections), visual assets, fact-check pass

---

## SUCCESS CRITERIA

- [ ] 78 slides fully specified with title, content, visuals, historical persons, and LLM connections
- [ ] 69 named mathematicians/scientists with dates (or [VERIFY: dates not found]), origins, and contributions
- [ ] Every section has a "connection arrow" to the transformer
- [ ] Convergence diagram progresses across all 10 sections, including final reprise in Slide 77-78
- [ ] Exploded diagram introduced in Slide 3 and reprised with full labels + slide references in Slide 76
- [ ] 3 interactive moments planned
- [ ] Session split points defined for both 2-session and 3-session delivery
- [ ] All uncertain claims tagged [VERIFY] (50 items in fact-check register)
- [ ] Visual asset list specifies at least 1 visual per slide (~60 total)
- [ ] Tone is engaging for high school seniors who use LLMs daily
- [ ] No university-level notation without accessible explanation; formula scaffolding rule enforced
- [ ] No hype language; precise claims about what math does in LLMs
- [ ] **EVERY component on the climax diagram (Slide 73) has been taught in an earlier slide with explicit back-reference**
- [ ] Dot product and cosine similarity taught before attention (Slides 10-11)
- [ ] Residual connections, layer normalization, and dropout taught before transformer assembly (Slides 60-61)
- [ ] Word2Vec / Mikolov properly credited for the king-queen embedding arithmetic (Slide 13)
- [ ] Subtitle reflects the actual scope: "2,000+ Years" covering Archimedes through 2026
- [ ] Shannon cross-referenced between Sections 3 and 4 (speaker note on Slide 36)
- [ ] Fermat cross-referenced between Sections 2 and 3 (speaker note on Slide 19)
- [ ] Hinton Nobel Prize citation specifies: shared with Hopfield, Nobel Prize in Physics 2024
- [ ] 3-session delivery recommended; 2-session marked as compressed

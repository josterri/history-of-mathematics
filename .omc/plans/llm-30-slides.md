# LLM Building Blocks: 30-Slide Condensed Version

**Date:** 2026-03-26 (Revision 2)
**Source:** 78 slides across 10 sections
**Target:** 30 slides, all 10 sections preserved
**Duration:** 40-45 minutes (inclusive of 3 interactive moments totaling ~7 minutes)
**Audience:** High school seniors in mathematics

---

## DELIVERABLE 1: THE STORY IN 5 SENTENCES

### The Story

1. Every time you talk to an AI, you are talking to a machine made entirely of mathematics -- specific math, invented by specific people, for reasons that had nothing to do with artificial intelligence.

2. The machine's skeleton is linear algebra (vectors and matrices from the 1840s-1850s), its ability to learn comes from calculus (derivatives and gradient descent stretching from Archimedes to 1986), and its language of uncertainty is probability theory (born from a gambling question in 1654).

3. Information theory (Shannon, 1948) gave it a way to measure how wrong it is, logic and computation (Boole to Turing) gave it hardware to run on, and the universal approximation theorem (Cybenko, 1989) proved that a neural network can in principle learn anything -- though the path from a single neuron (1943) through hype, an AI winter, and backpropagation's comeback (1986) to deep networks was full of drama.

4. Language required sequence modeling (Markov chains to LSTM to attention), and in 2017 eight researchers at Google combined ALL of these ingredients into one architecture -- the transformer -- where 2,000 years of mathematics converge in a single equation: Attention(Q,K,V) = softmax(QK^T / sqrt(d)) V.

5. Scale the transformer up with more data, more parameters, more compute, and you get the LLMs you use every day -- the same architecture, the same math, just bigger -- and the story is not over, because mathematics is still being invented.

### Reflection on the Story

**Does it build?** Yes. Sentences 1-3 lay foundations (increasing complexity). Sentence 4 is the convergence/climax. Sentence 5 is the resolution and call to action.

**Does it have a beginning, middle, and climax?** Beginning = "it's all math by specific people" (demystification). Middle = the ingredients accumulate, with human drama (AI winter, comeback). Climax = the transformer, where everything meets. Resolution = scaling and the open future.

**Does the audience care?** The hook is personal: "the AI you use every day." Every ingredient connects backward to a specific person and forward to a feature of the AI the students already know. The AI winter arc provides narrative tension. The climax provides catharsis: "now you understand every piece."

**Sentence-to-slide mapping:**
- Sentence 1 -> Slides 1-3 (Opening: demystification + roadmap)
- Sentence 2 -> Slides 4-9 (Linear Algebra + Calculus)
- Sentence 3 -> Slides 10-18 (Probability + Info Theory + Logic + Function Approx + Neuron)
- Sentence 4 -> Slides 19-25 (Sequence + Transformer)
- Sentence 5 -> Slides 26-30 (Scaling + Closing)

---

## DELIVERABLE 2: THREE ENGAGEMENT PROPOSALS

### Proposal A: "The Detective Story"

**Frame:** "We're going to reverse-engineer an AI. What's inside the black box?" Each section peels back a layer. The audience is the detective.

**30-Slide Outline:**
1. Title
2. The Black Box (show ChatGPT, pose the mystery)
3. The Exploded Diagram (overwhelming -- "by the end you'll crack this")
4-6. Linear Algebra (vectors, matrices, dot product = finding clues in the evidence)
7-9. Calculus (gradient descent = following the trail downhill)
10-12. Probability (softmax = weighing the suspects)
13-14. Information Theory (cross-entropy = how close are we to the truth?)
15-16. Logic & Computation (the lab equipment)
17-18. Function Approximation (the theoretical guarantee: the culprit IS in the lineup)
19-22. The Neuron (hype, crash, comeback = a cold case reopened) [4 slides]
23-24. Sequence Modeling (reading the timeline of events)
25-27. The Transformer (the reveal: "case solved" -- annotated diagram)
28-29. Scaling (the bigger picture)
30. Closing (the next mystery: your turn)

**Emotional Arc:** Curiosity -> frustration ("it's complex") -> accumulating "aha" moments -> the breakthrough reveal -> satisfaction

**Key "Wow" Moments:** Slide 2 (the mystery opens), Slide 20 (AI winter = the cold case), Slide 26 (the annotated transformer = case cracked)

**Interactive Beats:** Slide 6 (king - man + woman = ?), Slide 27 ("count the building blocks")

**Strengths:** Mystery drives attention naturally. Each section "reveals a clue." The exploded diagram works perfectly as the "crime scene."
**Weaknesses:** The detective metaphor can feel forced for some sections (calculus as "following the trail" is a stretch). May feel gimmicky for sophisticated students.

---

### Proposal B: "The Time Machine"

**Frame:** Start in the present (show ChatGPT responding). Then: "Let's travel back to find where each piece came from." Jump between past and present. Each historical invention is shown in its original context, then immediately connected to the LLM feature it powers.

**30-Slide Outline:**
1. Title
2. ChatGPT in action NOW -- "What's happening under the hood?"
3. The Convergence Diagram (roadmap: 10 streams flowing to one point)
4-6. Linear Algebra -- 1844 Grassmann -> 2026 embedding layer (back and forth)
7-9. Calculus -- Archimedes -> gradient descent -> backpropagation (the learning engine)
10-12. Probability -- Pascal's gambling question 1654 -> softmax 2026 (the prediction engine)
13-14. Information Theory + Logic + Function Approx (3 sections, 2 slides)
15-18. The Neuron -- McCulloch-Pitts 1943 -> hype -> crash -> deep networks (the drama) [4 slides]
19-20. Sequence Modeling -- Markov 1906 -> attention 2014 (the bridge)
21-25. The Transformer -- "Attention Is All You Need" 2017 (the convergence) [5 slides]
26-28. Scaling + Convergence (the explosion + full diagram)
29-30. Closing -- "your turn"

**Emotional Arc:** Wonder ("I use this every day") -> time-travel excitement -> accumulating connections between past and present -> climax when ALL streams converge -> resolution + agency

**Key "Wow" Moments:** Slide 4 ("Grassmann was a schoolteacher nobody read; his vector spaces ARE the embedding spaces of modern AI"), Slide 10 ("Probability started with a gambling question; now it decides every word an AI says"), Slide 16 (AI winter: "one layer too soon"), Slide 24 (annotated transformer: "2,000 years of math, all running at once")

**Interactive Beats:** Slide 5 (king - man + woman = ?), Slide 11 ("The cat sat on the ___" softmax poll), Slide 24 ("count the building blocks")

**Strengths:** The past-present oscillation keeps energy high. Every historical figure gets an immediate "so what?" payoff. The time-travel framing is natural for a history-of-math lecture. High school seniors respond well to "here's the connection to YOUR phone."
**Weaknesses:** The back-and-forth could feel disorienting if not executed well. Needs strong visual transitions.

---

### Proposal C: "The Recipe"

**Frame:** "We're going to cook an AI from scratch." Each section adds an ingredient. A running recipe card builds on screen. At the end, all ingredients combine into the transformer.

**30-Slide Outline:**
1. Title: "The Recipe for an AI"
2. The Recipe Card (blank, 10 ingredient slots)
3-5. Ingredient 1: Linear Algebra (the flour -- base ingredient) [3 slides]
6-8. Ingredient 2: Calculus (the heat -- makes it learn) [3 slides]
9-11. Ingredient 3: Probability (the seasoning -- prediction) [3 slides]
12. Ingredient 4: Information Theory (the thermometer -- measuring quality)
13. Ingredient 5: Logic (the kitchen -- hardware)
14. Ingredient 6: Function Approximation (the proof it will taste good)
15-18. Ingredient 7: The Neuron (the basic unit -- with drama) [4 slides]
19-20. Ingredient 8: Sequence Modeling (the order matters) [2 slides]
21-25. The Mixing: Transformer (all ingredients combined) [5 slides]
26-28. The Baking: Scaling (turn up the heat) [3 slides]
29-30. Closing: your recipe [2 slides]

**Emotional Arc:** Playful anticipation -> accumulation -> "will it work?" -> the reveal (it works!) -> celebration

**Key "Wow" Moments:** Slide 16 (AI winter = "the souffle collapsed"), Slide 22 (the transformer = "all ingredients combine"), Slide 24 (annotated diagram)

**Interactive Beats:** Slide 5 (king - man + woman = ?), Slide 11 (softmax poll)

**Strengths:** Very accessible metaphor. The running recipe card is a great visual anchor. Playful tone suits high school seniors.
**Weaknesses:** The cooking metaphor trivializes the mathematics. "Calculus is the heat" is cute but doesn't communicate the depth. Some sections resist the metaphor (logic as "the kitchen" is weak). Risk: students remember the metaphor but not the math.

---

### RECOMMENDATION: Proposal B -- "The Time Machine"

**Why Proposal B wins for high school seniors:**

1. **The past-present oscillation is the lecture's natural structure.** The entire lecture IS about connecting historical mathematics to modern AI. Proposal B doesn't impose an external metaphor; it amplifies what the lecture already does.

2. **Immediate payoff for every historical figure.** High school seniors have short patience for "this will matter later." The time-machine structure gives every inventor an instant connection to something the students use daily. Grassmann -> your phone's AI. Pascal -> the word prediction you see every day.

3. **No metaphor fatigue.** The Detective Story and Recipe metaphors are charming for 10 minutes but risk becoming forced by slide 20. "The Time Machine" is not a metaphor at all -- it's literally what we're doing: traveling through the history of math. It won't feel stale.

4. **The convergence diagram IS the time machine.** The existing convergence diagram (nodes lighting up one by one) already serves as a visual time-travel device. Proposal B uses the lecture's strongest existing visual element as the framing device.

5. **The emotional peak lands harder.** When the transformer slide reveals that all 10 streams converge, the audience has been oscillating between past and present for 25 slides. The convergence is not just intellectual but temporal: 2,000 years of scattered invention suddenly snapping into one architecture. This is powerful.

6. **It respects the audience.** High school seniors are smart. They don't need to be told they're "detectives" or "cooking an AI." They need to see the connections and feel the sweep of time. Proposal B treats them as fellow travelers through history.

---

## DELIVERABLE 3: THE 30-SLIDE PLAN

### Slide Distribution

| Section | Original Slides | 30-Slide Allocation | Justification |
|---------|----------------|---------------------|---------------|
| 0. Opening | 4 (1-4) | **3** | Title + hook + roadmap. Must land the premise. |
| 1. Linear Algebra | 12 (5-16) | **3** | Core concepts: vector, matrix, dot product. The embedding pipeline. |
| 2. Calculus | 9 (17-25) | **3** | Derivative, gradient descent, backpropagation. The learning engine. |
| 3. Probability | 9 (26-34) | **3** | Gambling origins, Bayes, softmax. The prediction engine. |
| 4. Info Theory | 7 (35-41) | **2** | Entropy + cross-entropy. Two concepts, one slide each. |
| 5. Logic | 7 (42-48) | **2** | Boole + Turing. The substrate. |
| 6. Function Approx | 5 (49-53) | **2** | Fourier + Cybenko. The guarantee. |
| 7. Neuron & Depth | 9 (54-62) | **4** | McCulloch-Pitts -> Perceptron hype -> XOR crash -> deep networks. The drama. |
| 8. Sequence | 6 (63-68) | **2** | Markov + Attention. The bridge. |
| 9. Transformer | 6 (69-74) | **5** | The climax. Paper + self-attention + one layer + annotated diagram + pos. encoding convergence. |
| 10. Scaling + Close | 4 (75-78) | **4** | Scaling leap + return to diagram + final convergence + closing. |
| **Total** | **78** | **30** | |

**Why the Transformer gets 5 slides:** It is the climax. Everything builds toward this moment. Shortchanging it would undermine the entire narrative arc. The audience has been accumulating ingredients for 20 slides; they need room to see them combine. The 5th slide (positional encoding + convergence) serves double duty as a convergence checkpoint and the last pre-scaling concept.

**Why Neuron & Depth gets 4 slides:** The neuron section contains the lecture's only sustained narrative arc -- hype, crash, AI winter, comeback -- which requires pacing across 4 beats: (1) the invention, (2) the disaster, (3) the depth innovations, (4) the convergence transition. Compressing to 3 would either rush the drama or cut essential technical content (activation/residuals/normalization). The Transformer's 5 slides cover more distinct concepts (paper, self-attention, full layer, annotated diagram, positional encoding), so the allocations are justified differently.

**Why Info Theory, Logic, Sequence get 2 slides each:** These are the "connective tissue" sections. They are essential for the story but can be communicated efficiently. Info Theory: entropy IS the loss function (one concept). Logic: Boole + Turing = the hardware (one concept). Sequence: Markov -> attention = the bridge (one concept).

---

### TIME MACHINE FRAMING: NOW/THEN TRANSITION PROTOCOL

Every slide's speaker story includes a "time jump" transition. The pattern:

**NOW:** [What the student sees/uses today]
**THEN:** [Historical moment -- specific date, specific person, specific place/context]
**BRIDGE:** [The connection between then and now]

This is the operational backbone of the "Time Machine" framing. It is not a gimmick on a single slide -- it is a rhythmic device sustained across all 30 slides, making the past-present oscillation concrete and consistent.

---

### SLIDE-BY-SLIDE PLAN

#### SLIDE 1: Title Slide
- **The ONE thing:** Set the scope and create anticipation.
- **Content:** "The Building Blocks of LLMs: A Mathematical History. From Archimedes to Attention: 2,000+ Years of Mathematics Inside Your AI."
- **Visual:** Full-bleed violet background. Clean typography. No clutter.
- **Speaker's story:** "Welcome. This is not about hype or 'intelligence.' This is about tracing every mathematical component of the AI you use daily back to the person who invented it -- often centuries before AI existed."
- **NOW/THEN:** NOW: You talk to AI every day. THEN: We are about to travel back through 2,000 years of mathematics to find out where every piece came from.
- **Build-up connection:** Creates the question: what IS inside my AI? -> Slide 2 answers.

#### SLIDE 2: What's Inside Your AI?
- **The ONE thing:** The AI you use every day is built entirely from specific mathematics invented by specific people.
- **Content:** Left: "When you type a question to ChatGPT... the machine that answers is built entirely from mathematics. Not magic. Not intelligence. Specific math, by specific people, at specific times." Right: smartphone diagram with labeled math-topic arrows (Linear Algebra, Calculus, Probability, Info Theory, Logic, Function Approx).
- **Visual:** Smartphone with six color-coded arrows pointing in. Insight box: "You already know some of this math. You just don't know it's inside your AI yet."
- **Speaker's story:** "You already know some of this math. You just don't know it's inside your AI yet. Today we're going to fix that."
- **NOW/THEN:** NOW: Your phone, right now, runs a machine built from 10 branches of mathematics. THEN: Each branch was invented by a specific person, at a specific time, for a reason that had nothing to do with AI. We will visit each one.
- **Build-up connection:** "But what does the full machine look like?" -> Slide 3.

#### SLIDE 3: The Roadmap -- Convergence Diagram
- **The ONE thing:** Ten streams of mathematics will converge into one architecture. This is our map.
- **Content:** Convergence diagram with 10 satellite nodes (all gray/unlit), central "?" node. Each labeled with section name and date range.
- **Visual:** The convergence diagram in its initial state. All nodes dim.
- **Speaker's story:** "We're going to light up these nodes one by one. Each one is a piece of math that somebody invented, often for a completely different purpose, that ended up inside the machines you use every day. Ten branches of mathematics, developed over 2,000 years, all converging in one architecture."
- **NOW/THEN:** NOW: This diagram shows ten streams flowing into your AI. THEN: We start our first jump -- to a German schoolteacher in 1844 whom nobody read.
- **Build-up connection:** "Let's start with the skeleton." -> Slide 4.

#### SLIDE 4: Linear Algebra -- Vectors, Matrices, and Words
- **The ONE thing:** Words become lists of numbers (vectors), and neural network layers are matrix multiplications.
- **Content:** COMBINED from original slides 6, 8, 9. Three panels: (a) What is a vector? 2D -> 3D -> 768 numbers. Grassmann (1844). (b) What is a matrix? Cayley (1858), Sylvester coined the name (1850). Small 3x3 -> "175 billion entries. Same math." (c) Neural network layer = matrix multiplication. Gauss (1809).
- **Visual:** Three-panel layout. Left: vector progression. Center: small matrix -> huge matrix. Right: matrix multiply = neural net layer.
- **Speaker's story:** "Grassmann was a schoolteacher nobody read. Sylvester named it 'matrix' from Latin for 'womb' -- he thought of it as something that gives birth to numbers. He had no idea it would give birth to AI. Every time you send a message to ChatGPT, your words pass through about 96 layers. Each layer multiplies your data by a matrix. That's roughly 96 matrix multiplications just to generate one word."
- **NOW/THEN:** NOW: Every message you send to ChatGPT passes through 96 matrix multiplications. THEN: 1844, Stettin, Prussia -- Grassmann publishes a book so abstract that nobody reads it. 1850, London -- Sylvester, a failed barrister, coins the word "matrix." Their inventions ARE the engine of modern AI.
- **Build-up connection:** "But how does the machine know which words are related?" -> Slide 5.

#### SLIDE 5: The Dot Product and Word Embeddings
- **The ONE thing:** The dot product measures similarity between vectors; this is how AI understands which words relate to which.
- **Content:** COMBINED from original slides 10, 13, 14, interactive moment. Left: dot product recipe + three configurations (similar/unrelated/opposite). Right: king-man+woman=queen parallelogram. Below: embedding pipeline (sentence -> tokens -> vectors -> matrix).
- **Visual:** Top-right: word vector parallelogram with king/queen/man/woman. Bottom: embedding pipeline diagram.
- **Speaker's story:** "The dot product is the simplest measure of similarity. Multiply matching entries, add up. This tiny operation, repeated billions of times, is what lets an AI understand which words relate to which."
- **NOW/THEN:** NOW: When you type "king" into an AI, it becomes a list of 768 numbers. THEN: 1881, New Haven -- Josiah Willard Gibbs formalizes the dot product. He was studying physics. 140 years later, his formula is how your AI knows that "king" and "queen" are related.
- **INTERACTIVE MOMENT 1:** "What does king minus man plus woman equal?" Collect guesses. Reveal: queen. "This is not a trick. It's a mathematical property of the space." (~2 minutes)
- **Build-up connection:** "Now we have the skeleton: vectors, matrices, dot products. But a skeleton doesn't move. For that, we need calculus." -> Slide 6.

#### SLIDE 6: Linear Algebra Convergence + Transition
- **The ONE thing:** Linear algebra is the skeleton of neural networks. Convergence node 1 lights up.
- **Content:** Left: convergence diagram with node 1 (Linear Algebra) lit in teal. Right: section summary table (Grassmann 1844, Sylvester 1850, Cayley 1858, Gibbs 1881, Gauss 1809, Mikolov 2013). Insight: "Every layer is a matrix multiplication. Every attention score is a dot product. The math of 1850 is the engine of 2026."
- **Visual:** Convergence diagram (1 of 10 lit). Summary table.
- **Speaker's story:** "One node lit. Nine to go. Now we have the skeleton. But a skeleton doesn't move. For that, we need calculus -- the mathematics of change."
- **NOW/THEN:** NOW: Node 1 lit -- linear algebra runs inside every AI layer you use. THEN: We jump from the 1840s to an even older story -- Archimedes, 250 BCE, Syracuse, computing areas by exhaustion.
- **Build-up connection:** Direct transition to calculus. -> Slide 7.

#### SLIDE 7: Calculus -- The Derivative and Gradient Descent
- **The ONE thing:** Calculus measures change. Gradient descent uses derivatives to roll downhill toward the best answer.
- **Content:** COMBINED from original slides 18, 19, 20, 21. Top: Archimedes (c.250 BCE, method of exhaustion) -> Fermat/Newton/Leibniz (derivative). Bottom: Cauchy (1847, gradient descent). The 3D loss landscape with ball rolling downhill. Recipe: "1. Compute the slope. 2. Take a step downhill. 3. Repeat."
- **Visual:** Left: method-of-exhaustion polygons approaching circle. Right: 3D loss landscape with gradient descent path. Bottom: gradient descent recipe box.
- **Speaker's story:** "Archimedes was doing proto-calculus in the 3rd century BCE. Fermat, Newton, and Leibniz formalized the derivative. But the hero for AI is Cauchy, who in 1847 asked: if I can compute the slope, can I use it to find the bottom of a valley? That's gradient descent. Every AI learns by rolling downhill on a landscape made of calculus."
- **NOW/THEN:** NOW: Every time ChatGPT trains on a new sentence, it rolls downhill on a mathematical landscape. THEN: 250 BCE, Syracuse -- Archimedes approximates circles with polygons. 1847, Paris -- Cauchy asks: "Can I find the bottom of a valley using slopes?" That question IS how AI learns.
- **Build-up connection:** "But how does the learning signal travel backward through the network?" -> Slide 8.

#### SLIDE 8: Backpropagation -- The Chain Rule Applied
- **The ONE thing:** Backpropagation uses the chain rule to send error signals backward through every layer, enabling multi-layer learning.
- **Content:** COMBINED from original slides 22, 23, 24. Linnainmaa (1970, automatic differentiation), Rumelhart/Hinton/Williams (1986, backpropagation in neural networks). Chain rule as the key: derivative of a composition = multiply the derivatives of each piece. Visual: error signal flowing backward through layers.
- **Visual:** Left: chain rule shown as a factoring-through-layers diagram. Right: backpropagation arrows flowing backward through a 3-layer network. Each layer gets its own gradient.
- **Speaker's story:** "The chain rule from your calculus class -- the derivative of a composition is the product of the individual derivatives -- is literally the algorithm that trains every AI. Leibniz's notation from 1684, applied by Linnainmaa in 1970 and popularized by Hinton in 1986. This is how a neural network learns: it makes a prediction, measures how wrong it was, and sends that error signal backward through every layer, adjusting as it goes."
- **NOW/THEN:** NOW: Every AI you use was trained by sending error signals backward through 96 layers -- that's the chain rule, billions of times. THEN: 1684, Hanover -- Leibniz publishes the notation. 1970, Helsinki -- Linnainmaa automates it. 1986, San Diego -- Hinton makes it famous. Three centuries, one idea, powering all of AI.
- **Build-up connection:** "The network can learn. But learn WHAT? It learns to predict probability distributions." -> Slide 9.

#### SLIDE 9: Calculus Convergence + Transition to Probability
- **The ONE thing:** Calculus provides the learning algorithm. Node 2 lights up.
- **Content:** Convergence diagram with nodes 1-2 lit. Summary: Archimedes (c.250 BCE), Fermat/Newton/Leibniz (1660s-1680s), Cauchy (1847 gradient descent), Linnainmaa (1970 auto-diff), Rumelhart/Hinton/Williams (1986 backprop). Insight: "Without calculus, you can build a neural network but you cannot train it."
- **Visual:** Convergence diagram (2 of 10 lit). Brief summary table.
- **Speaker's story:** "Two nodes lit. The network has a skeleton and can learn. But learn WHAT? It learns to predict probability distributions over words. For that, we need probability theory."
- **NOW/THEN:** NOW: Two nodes lit -- linear algebra and calculus run inside every AI. THEN: We jump to 1654, Paris -- a gambler writes a letter to Blaise Pascal, and probability theory is born.
- **Build-up connection:** Direct transition to probability. -> Slide 10.

#### SLIDE 10: Probability -- From Gambling to Prediction
- **The ONE thing:** Probability started as a gambling question; LLMs use it to predict every word.
- **Content:** COMBINED from original slides 27, 29, 32. Top: Pascal & Fermat (1654, problem of points). Middle: Bayes' theorem (1763, updating beliefs). Bottom: Shannon's language model (1948, "more context = more readable"). Shannon's approximation examples (0th order to word-level bigram).
- **Visual:** Top: letter exchange diagram Pascal-Fermat. Middle: Bayes' theorem in "recipe" form. Bottom: Shannon's text approximation examples.
- **Speaker's story:** "Probability was born because a gambler asked Pascal how to split a pot in an unfinished dice game. Pascal wrote to Fermat. Their letters invented a new branch of mathematics. Two centuries later, Bayes showed how to update beliefs from evidence. Then Shannon modeled English as a statistical process -- predicting the next letter using previous letters. That's exactly what every LLM does, 70 years later."
- **NOW/THEN:** NOW: Every word your AI generates is chosen by probability -- a distribution over 50,000+ possible next tokens. THEN: 1654, Paris -- the Chevalier de Mere loses at dice and writes to Pascal. That letter launched the mathematics that decides every word an AI says.
- **Build-up connection:** "But how does the model turn raw scores into probabilities?" -> Slide 11.

#### SLIDE 11: Softmax -- From Thermodynamics to Token Prediction
- **The ONE thing:** The softmax function (from Boltzmann's physics) converts raw scores into probabilities. This is how AI picks words.
- **Content:** From original slide 33. Boltzmann (1870s, energy distribution). Softmax pipeline: logits -> exp -> normalize -> probabilities. Bar chart: "the" 68%, "a" 19%, etc. Formula: softmax(z_i) = e^(z_i) / sum(e^(z_j)).
- **Visual:** Softmax pipeline (three steps). Bar chart of word probabilities.
- **INTERACTIVE MOMENT 2:** Quick poll -- "What word comes next: 'The cat sat on the ___'?" Collect answers. Show the AI's softmax distribution. (~2 minutes)
- **Speaker's story:** "Boltzmann invented this formula to describe how gas molecules distribute among energy states. 150 years later, the exact same formula tells an AI which word to say next. Every time an LLM generates a word, it computes a softmax probability distribution. The math started with a gambling question in 1654 and was perfected by a physicist studying thermodynamics in the 1870s."
- **NOW/THEN:** NOW: Every single word your AI says is chosen by this formula -- softmax. THEN: 1870s, Vienna -- Ludwig Boltzmann is studying how gas molecules distribute among energy levels. He writes e^x / sum(e^x). That exact formula now picks every word an AI says.
- **Build-up connection:** "We can predict probabilities. But how do we measure if they're GOOD?" -> Slide 12.

#### SLIDE 12: Probability + Info Theory Convergence
- **The ONE thing:** Cross-entropy (Shannon, 1948) measures how wrong the model is. Nodes 3-4 light up together.
- **Content:** COMBINED probability summary + info theory core. Left: convergence diagram with nodes 1-4 lit. Right: Cross-entropy loss = -log(p(correct word)). "The cat sat on the ___" example: if model says "mat" with 30% -> loss = 1.20. If 80% -> loss = 0.22. Insight: "Training an LLM = minimizing cross-entropy = making the model more confident about the RIGHT next word."
- **Primary visual:** Convergence diagram (4 of 10 lit) + cross-entropy worked example (bar chart with loss values).
- **Verbal-only content (NOT on slide):** Probability summary table (Pascal 1654, Bayes 1763, Shannon 1948, Boltzmann -> softmax). Shannon's dual contribution to both sections. These are mentioned in speech but the slide stays clean with only the convergence diagram and the cross-entropy example.
- **Speaker's story:** "Shannon's 1948 paper is so foundational it contributes to two sections. He modeled language statistically AND created the measure for how good that model is. Cross-entropy loss. Every time an LLM gets a training example, it predicts the next word, checks how wrong it was using Shannon's formula, then uses backpropagation to improve. Information theory is the bridge between prediction and learning."
- **NOW/THEN:** NOW: Every AI checks its own mistakes using a number called "cross-entropy loss." THEN: 1948, Bell Labs, New Jersey -- Claude Shannon publishes "A Mathematical Theory of Communication." He needed a way to measure information. That measure IS the loss function that trains every LLM.
- **Build-up connection:** "We have the learning math, the prediction math, and the scoring math. But we need something to run it on." -> Slide 13.

#### SLIDE 13: Logic & Computation -- The Substrate
- **The ONE thing:** Boolean algebra gave us digital hardware; Turing gave us the concept of a programmable computer. Without them, there's nothing to run the math on.
- **Content:** COMBINED from original slides 43, 44/45, 47. Boole (1854, true/false as 0/1). Turing (1936, universal machine). Von Neumann (1945, stored-program architecture). GPU computing (NVIDIA CUDA, 2007). Paradox: "Logicians dreamed of mechanical thought. They proved it was impossible. Then neural networks did it anyway."
- **Visual:** Left: Boolean gates (AND/OR/NOT). Center: Turing machine concept. Right: GPU/data center. The paradox statement as a callout box.
- **Speaker's story:** "Boole was a self-taught son of a shoemaker who reduced logic to algebra. Turing imagined a machine that could compute anything computable. Von Neumann built one. And here's the paradox: Godel and Turing proved that no formal system can capture all truth. Yet neural networks -- running on the hardware that logic built -- learned to do things formal logic cannot: translate, write poetry, reason by analogy. The machines that logic built transcended the limitations that logic discovered."
- **NOW/THEN:** NOW: The AI on your phone runs on a chip that processes billions of Boolean operations per second. THEN: 1854, Cork, Ireland -- George Boole, son of a shoemaker, reduces all of logic to algebra. 1936, Cambridge -- Turing imagines a machine that can compute anything computable. Their ideas ARE the hardware your AI runs on.
- **Build-up connection:** "We have hardware. But WHY should a pile of matrix multiplications be able to learn anything?" -> Slide 14.

#### SLIDE 14: Logic + Function Approximation Convergence
- **The ONE thing:** Neural networks are universal approximators -- they can learn ANY continuous function. Nodes 5-6 light up.
- **Content:** COMBINED Logic summary + Function Approximation core. Left: convergence diagram (6 of 10 lit). Right top: Logic summary (Boole 1854, Turing 1936, von Neumann 1945). Right bottom: Fourier (1807, any function as a sum of waves) -> Weierstrass (1885, polynomials can approximate anything) -> Cybenko (1989, neural networks can approximate anything). The key insight box: "A neural network can learn any continuous function. This is not an analogy. It is a mathematical theorem."
- **Visual:** Convergence diagram (6 of 10 lit). Fourier series approximation chart (1 term, 3 terms, 7 terms approaching square wave).
- **Speaker's story:** "Fourier wanted to solve the heat equation, and he made a claim so bold other mathematicians didn't believe him: any function can be written as a sum of sines. A century later, Cybenko proved the same thing for neural networks. This theorem is why people bet on neural networks. It's not that they're the best -- it's that they're guaranteed to work, at least in principle. But guaranteed to work and actually working are different things. For that, we need the neuron."
- **NOW/THEN:** NOW: The reason anyone believes neural networks can learn language, vision, reasoning -- anything -- is a theorem from 1989. THEN: 1807, Paris -- Fourier claims any function is a sum of sines. 1989, Urbana-Champaign -- Cybenko proves the same for neural networks. The guarantee that makes all of AI possible.
- **Build-up connection:** "We know they CAN learn anything. But what IS a neural network?" -> Slide 15.

#### SLIDE 15: The Neuron -- From Biology to Mathematics
- **The ONE thing:** McCulloch & Pitts created the mathematical neuron (1943); Rosenblatt built a machine that could learn (1958).
- **Content:** COMBINED from original slides 55, 56. McCulloch (neurophysiologist) & Pitts (teenage runaway, self-taught logician) -> 1943 paper. Rosenblatt's Perceptron (1957-58): a physical machine that could learn to classify images. NYT: "a machine that could walk, talk, see, write..."
- **Visual:** Left: McCulloch-Pitts neuron diagram (inputs, weights, sum, threshold, output). Right: Perceptron learning loop (present -> compare -> adjust -> repeat). Newspaper headline feel.
- **Speaker's story:** "A neurophysiologist and a teenage runaway created the mathematical neuron. McCulloch was in his 40s. Pitts was about 20 and had no degree. Their paper launched neural network research. Then Rosenblatt built the Perceptron -- a room-sized machine with 400 photocells that could LEARN. The press said it would think like a human. The hype was enormous. And then came the crash."
- **NOW/THEN:** NOW: Every AI is built from billions of artificial neurons. THEN: 1943, Chicago -- a neurophysiologist and a teenage runaway with no degree write a paper that defines the mathematical neuron. 1958, Cornell -- Rosenblatt builds a room-sized machine that can learn. The press goes wild. And then it all collapses.
- **Build-up connection:** Deliberate cliffhanger. "Then came the crash." -> Slide 16.

#### SLIDE 16: The XOR Crash and AI Winter
- **The ONE thing:** Minsky & Papert proved a single-layer perceptron can't learn XOR. The field collapsed for 17 years. The solution: add more layers.
- **Content:** COMBINED from original slides 57, 58. XOR scatter plot (no single line separates). AI Winter timeline (1958 hype -> 1969 crash -> 1986 comeback). The revival: Rumelhart/Hinton/Williams showed backpropagation could train multi-layer networks. "It took 17 years. The AI winter was caused by stopping one layer too soon."
- **Visual:** Left: XOR plot with failed line. Timeline: green (1958) -> red (1969) -> gray winter -> green (1986). Right: Multi-layer network solving XOR. The drama arc in one visual.
- **Speaker's story:** "Minsky and Papert's math was correct: a single-layer perceptron cannot learn XOR. But the conclusion the field drew -- that neural networks are a dead end -- was WRONG. The solution was right there: add more layers. It took 17 years for the field to recover. Remember the chain rule from slide 8? The backpropagation algorithm that Hinton popularized in 1986? That's what saved the field. The chain rule saved an entire research program."
- **NOW/THEN:** NOW: Modern AI uses networks with 96+ layers. THEN: 1969, MIT -- Minsky and Papert prove one layer is not enough and the field dies for 17 years. 1986, San Diego -- Hinton shows that with the chain rule you can train MANY layers. The comeback that made your AI possible.
- **Build-up connection:** "Deep networks work. But they needed more tricks." -> Slide 17.

#### SLIDE 17: Depth -- Activation, Residuals, Normalization
- **The ONE thing:** Three inventions made deep networks practical: activation functions (nonlinearity), residual connections (signal preservation), layer normalization (stability).
- **Content:** COMBINED from original slides 59, 60, 61. Three panels: (a) Activation functions (sigmoid -> ReLU -> GELU). "Without nonlinearity, 100 layers = 1 layer." (b) Residual connections (He et al., 2015). output = input + layer(input). Standard network (fading signal) vs ResNet (preserved signal). (c) Layer norm (Ba et al., 2016). Before/after normalization bars. Key insight: "Add & Norm" in the transformer = He's residual + Ba's normalization.
- **Visual:** Three-panel: activation function curves | standard vs ResNet signal | before/after normalization bars.
- **Speaker's story:** "Three more inventions. Activation functions add nonlinearity -- without them, stacking 100 layers of matrix multiplication would be the same as one layer. Residual connections let the signal flow through without fading. Layer normalization keeps everything stable. These are the 'Add and Norm' blocks you'll see in the transformer. Invisible to the user, essential to the machine."
- **NOW/THEN:** NOW: The "Add & Norm" blocks inside every transformer layer -- you'll see them on slide 23. THEN: 2015, Microsoft Research Beijing -- Kaiming He adds "skip connections" so the signal doesn't fade. 2016, Toronto -- Jimmy Ba adds normalization so the numbers don't explode. Two quiet papers that made 96-layer networks possible.
- **Build-up connection:** Convergence update: node 7 lit. "We can build deep networks. But language is sequential." -> Slide 18.

#### SLIDE 18: Neuron & Depth Convergence + Transition
- **The ONE thing:** We have deep networks. But language requires sequence processing. Node 7 lights up.
- **Content:** Convergence diagram (7 of 10 lit). Summary: McCulloch-Pitts (1943), Rosenblatt (1958), Minsky/Papert (1969), Rumelhart/Hinton/Williams (1986), He (2015 residuals), Ba (2016 layer norm). Connection box: "Billions of neurons, stacked 96+ layers, with activation, residuals, and normalization."
- **Visual:** Convergence diagram (7 of 10 lit).
- **Speaker's story:** "Seven nodes lit. We can build neurons, stack them deep, and train them. But language is SEQUENTIAL. 'Dog bites man' is very different from 'Man bites dog.' Word order matters. How do you process a sequence? That took another set of inventions."
- **NOW/THEN:** NOW: Seven of ten nodes lit -- the AI has neurons, depth, and can learn. But it cannot yet read a sentence in order. THEN: We jump to 1906, St. Petersburg -- Andrey Markov is analyzing the poetry of Pushkin, and he invents sequence modeling.
- **Build-up connection:** -> Slide 19.

#### SLIDE 19: Sequence Modeling -- Markov to Attention
- **The ONE thing:** Markov chains (1906) started sequence modeling; attention (2014) solved the memory bottleneck and became the bridge to the transformer.
- **Content:** COMBINED from original slides 64, 66, 67, 68. Top: Markov (1906, analyzed Pushkin's poetry) -> Markov chain state diagram. Middle: RNN problem (memory fades after 50 words). Bottom: Bahdanau/Cho/Bengio (2014) -> attention: "instead of compressing everything into one vector, look back at the whole input." Attention diagram (French -> English word alignment).
- **Visual:** Top: Markov chain with transition probabilities. Middle: RNN with fading hidden state arrows. Bottom: attention alignment diagram.
- **Speaker's story:** "Markov analyzed poetry to prove a point about probability. His chain model became the ancestor of every language model. But Markov chains and their descendants -- even LSTMs -- have a fatal flaw: the memory fades. After 50 words, the beginning is forgotten. Then in 2014, Bahdanau asked a simple question: why compress everything into one vector when you can look back at the whole input? That's attention. Without this 2014 paper, there would be no GPT, no Claude, no ChatGPT."
- **NOW/THEN:** NOW: Your AI can read a 100,000-word document and remember the first sentence. That is attention. THEN: 1906, St. Petersburg -- Markov analyzes Pushkin's poetry with transition probabilities. 2014, Montreal -- Bahdanau asks: "Why forget anything?" and invents attention. The leap from forgetting to remembering everything.
- **Build-up connection:** "We now have ALL the building blocks. It's time to put them together." -> Slide 20.

#### SLIDE 20: Sequence Convergence + Transition to Transformer
- **The ONE thing:** Attention solves the memory problem. Node 8 lights up. All ingredients are ready.
- **Content:** Convergence diagram (8 of 10 lit). "Attention = context. We now have ALL the building blocks. It is time to put them together."
- **Visual:** Convergence diagram with 8 nodes lit. Two remaining: Transformer and Scaling.
- **Speaker's story:** "Eight nodes lit. Two thousand years of mathematics. Linear algebra, calculus, probability, information theory, logic, function approximation, the neuron, sequences. All of these streams are about to converge in a single architecture, published by eight researchers at Google in 2017."
- **NOW/THEN:** NOW: Eight nodes lit -- eight branches of mathematics running inside your AI. Two remain. THEN: We jump to 2017, Google Brain, Mountain View -- eight researchers are about to write the most influential AI paper of the decade.
- **Build-up connection:** The buildup is complete. -> Slide 21 is the climax.

#### SLIDE 21: "Attention Is All You Need" (2017)
- **The ONE thing:** Eight researchers published the transformer architecture, which uses ONLY attention. It was simpler, faster, and better than everything before.
- **Content:** From original slide 70. The paper title, the eight authors (Vaswani, Shazeer, Parmar, Uszkoreit, Jones, Gomez, Kaiser, Polosukhin). Most in their 20s-30s. Several founded major AI companies. "Eight researchers. One paper. The architecture that powers every major LLM."
- **Visual:** Stylized paper card (arXiv:1706.03762). Eight author silhouettes. Clean, dramatic.
- **Speaker's story:** "The title is bold: 'Attention Is All You Need.' They were right. This single architecture -- the transformer -- is the foundation of GPT, Claude, Gemini, and virtually every LLM in existence. Most of the authors were in their 20s and 30s. Several have since founded major AI companies. One paper changed everything."
- **NOW/THEN:** NOW: GPT, Claude, Gemini, Llama -- every major AI runs on the architecture from this one paper. THEN: 2017, Google Brain, Mountain View -- eight researchers, most in their 20s, publish "Attention Is All You Need." They combined every mathematical ingredient we have covered into one design.
- **Build-up connection:** "But what IS the transformer? Let's look inside." -> Slide 22.

#### SLIDE 22: Self-Attention -- The Core Mechanism
- **The ONE thing:** Self-attention uses the dot product to let every word look at every other word and decide what's relevant.
- **Content:** From original slide 71. Each token generates Q (what am I looking for?), K (what do I contain?), V (what information do I carry?). Step-by-step with back-references: (1) dot product of Q and K (Gibbs, slide 5), (2) scale by sqrt(d), (3) softmax (Boltzmann, slide 11), (4) multiply by V (Cayley, slide 4). Concrete example: "The cat sat on the mat because IT was tired" -> "it" attends to "cat." Formula inset: Attention(Q,K,V) = softmax(QK^T/sqrt(d)) V.
- **Visual:** Q/K/V pipeline diagram with back-reference labels. "it" -> "cat" attention example.
- **Speaker's story:** "Self-attention is the convergence point. The dot product from Gibbs. The softmax from Boltzmann. The matrix multiplication from Cayley. All in one equation. When the model reads 'The cat sat on the mat because it was tired,' self-attention lets the word 'it' look back at every other word and decide: 'I'm referring to cat.' That's how the model resolves references, understands context, grasps meaning."
- **NOW/THEN:** NOW: When your AI reads "it" in a sentence, self-attention lets it look at every other word and decide what "it" means. THEN: This single equation combines Gibbs's dot product (1881), Boltzmann's softmax (1870s), and Cayley's matrix multiplication (1858). Three centuries of math, one line of code.
- **Build-up connection:** "One layer of attention. Stack 96 of them." -> Slide 23.

#### SLIDE 23: The Full Transformer -- One Layer
- **The ONE thing:** One transformer layer = attention + feed-forward network + two rounds of Add & Norm. Stack N of these = the full transformer.
- **Content:** COMBINED from original slides 72, 73. The annotated transformer block: Multi-Head Self-Attention (Bahdanau '14) -> Add & Norm (He '15 + Ba '16) -> Feed-Forward Network (Cybenko '89) -> Add & Norm. With skip connections shown. x96 layers bracket. Attribution labels on every component.
- **Visual:** Vertical block diagram of one transformer layer with inventor attributions. The "x N layers" bracket.
- **Speaker's story:** "One transformer layer: attention, then a feed-forward network, with two rounds of 'add and normalize.' The attention is Bahdanau. The add is He's residual connection. The norm is Ba's layer normalization. The feed-forward network is Cybenko's universal approximation theorem in action. Stack 96 of these layers and you have GPT-4. Every component was taught in an earlier slide."
- **NOW/THEN:** NOW: Your AI stacks 96 copies of this exact block. THEN: Every piece is labeled with its inventor -- Bahdanau 2014, He 2015, Ba 2016, Cybenko 1989. You have already met every one of them in this lecture.
- **Build-up connection:** "Now let's see the FULL picture." -> Slide 24.

#### SLIDE 24: THE CLIMAX -- The Full Annotated Transformer
- **The ONE thing:** Every piece of the transformer was invented by someone, for a specific purpose, often centuries before AI existed. Here they all are in one diagram, annotated with 2,000+ years of math.
- **Content:** From original slide 73. The full annotated transformer pipeline: Input Embedding (Grassmann 1844, Mikolov 2013) -> Positional Encoding (Fourier 1807) -> Multi-Head Self-Attention (slides 5, 11, 19) -> Add & Norm (He 2015, Ba 2016) -> FFN + GELU (Cybenko 1989, Hendrycks 2016) -> Add & Norm -> Output Softmax (Boltzmann 1870s). Training: cross-entropy (Shannon '48) + backprop (Linnainmaa '70) + SGD (Cauchy 1847).
- **Visual:** Full-width annotated vertical pipeline. Every component labeled with inventor and date and slide reference. THIS IS THE MOST IMPORTANT VISUAL IN THE ENTIRE LECTURE.
- **INTERACTIVE MOMENT 3:** "Count the building blocks. Look at this diagram and try to identify which of the 10 sections each component comes from. How many can you find?" (~3 minutes)
- **Speaker's story:** [PAUSE. Let the diagram land.] "Look at this diagram. Every single piece has a history. The sine functions come from Fourier in 1807. The matrix multiplications from Cayley in 1858. The softmax from Boltzmann in the 1870s. The training algorithm uses Cauchy's gradient descent from 1847. When you talk to an AI, you are talking to 2,000 years of mathematics, all running at once."
- **Design note:** The diagram already labels positional encoding (Fourier 1807) as a component within the pipeline. Slide 25 will give positional encoding its own focused explanation. This is intentional: slide 24 shows WHERE it fits; slide 25 explains HOW it works and serves as the section 9 convergence checkpoint.
- **NOW/THEN:** NOW: This is the complete machine. Every word your AI says passes through this pipeline. THEN: [Gesture at annotations.] 1807. 1844. 1847. 1858. 1870s. 1948. 1970. 1989. 2013. 2014. 2015. 2016. 2017. Two thousand years of human invention, all running at once.
- **Build-up connection:** "The architecture is complete. One detail remains: how does it know word order?" -> Slide 25.

#### SLIDE 25: Positional Encoding + Transformer Convergence
- **The ONE thing:** Fourier's sine waves tell the transformer which word is which. The transformer section is complete: node 9 lights up.
- **Content:** COMBINED from original slides 74, 73 convergence. Left: Positional encoding = sine/cosine at different frequencies (Fourier). "Fourier decomposed heat into waves. Vaswani decomposed word position into waves. Same math, 210 years apart." Right: convergence diagram with 9 nodes lit, only "Scaling" remaining.
- **Visual:** Left: positional encoding waves at different frequencies. Right: convergence diagram (9 of 10 lit).
- **Speaker's story:** "One detail we skipped: the transformer has no built-in notion of word order. To fix this, Vaswani added positional encodings -- sine and cosine functions at different frequencies. Fourier's idea from 1807, applied directly. Same math, 210 years apart, for completely different purposes. Nine nodes lit. One to go."
- **NOW/THEN:** NOW: Your AI knows that "dog bites man" and "man bites dog" are different because of positional encoding. THEN: 1807, Paris -- Fourier decomposes heat into sine waves. 2017, Google -- Vaswani decomposes word position into the same sine waves. Same math, 210 years apart.
- **Build-up connection:** "The architecture is ready. Now: scale it up." -> Slide 26.

#### SLIDE 26: Scaling to LLMs
- **The ONE thing:** The transformer architecture, scaled up with more parameters, more data, and more compute, produces LLMs with emergent abilities.
- **Content:** From original slide 75. The GPT series table (GPT-1 117M 2018, GPT-2 1.5B 2019, GPT-3 175B 2020, GPT-4 undisclosed 2023, Claude 2023-26). Scaling laws (Kaplan et al., 2020): performance scales as a smooth power law. Parameter count vs year semilog chart.
- **Visual:** Semilog scaling chart. GPT timeline.
- **Speaker's story:** "The transformer is the same architecture from 2017. What changed is scale. More parameters, more data, more compute. And somewhere along the way, these models started doing things nobody programmed them to do -- reasoning, writing code, translating languages they were barely trained on. The math is the same. Just bigger."
- **NOW/THEN:** NOW: GPT-4, Claude, Gemini -- all the same 2017 architecture, just scaled up. THEN: 2018 -- GPT-1, 117 million parameters. 2020 -- GPT-3, 175 billion. Same blueprint, 1,500x larger. The math didn't change. The scale did.
- **Build-up connection:** "Remember the overwhelming diagram from slide 3?" -> Slide 27.

#### SLIDE 27: Return to the Exploded Diagram -- Now You Understand
- **The ONE thing:** The diagram that was overwhelming at the start is now fully understood. Every piece has a name, a history, and a person.
- **Content:** From original slide 76. The component inventory table: Embedding (Grassmann 1844, Mikolov 2013), Positional Encoding (Fourier 1807), Self-Attention (Bahdanau 2014, Vaswani 2017), Dot product (Gibbs 1880s), Softmax (Boltzmann 1870s), Matrix mult (Cayley 1858), Add & Norm (He 2015, Ba 2016), FFN + GELU (Cybenko 1989, Hendrycks 2016), Output softmax (Boltzmann/Luce), Training (Cauchy 1847, Linnainmaa 1970, Shannon 1948).
- **Visual:** The full attribution table. Clean, authoritative.
- **Speaker's story:** "At the start of this lecture, this diagram was overwhelming. Now you can point to each piece and say who invented it, when, and why. That's the power of understanding the history."
- **NOW/THEN:** NOW: You can read this diagram. Every piece has a name, a date, a person. THEN: Look at the dates -- 1807, 1844, 1847, 1858, 1870s, 1881, 1943, 1948, 1970, 1986, 1989, 2013, 2014, 2015, 2016, 2017. Centuries of work, all running in the machine in your pocket.
- **Build-up connection:** "Let's see the final convergence." -> Slide 28.

#### SLIDE 28: Convergence Diagram -- Final State (All 10 Lit)
- **The ONE thing:** Ten streams of human invention, flowing into one machine. The full convergence. The visual thesis of the entire lecture.
- **Content:** From original slide 77. Convergence diagram with ALL 10 nodes lit in their section colors. Central "?" replaced with "TRANSFORMER." All arrows visible.
- **Visual:** The fully-lit convergence diagram. The most satisfying visual: what was all gray is now all color.
- **Speaker's story:** [Let the diagram speak. Pause.] "Ten streams of human invention, flowing into one machine."
- **NOW/THEN:** NOW: This is the complete picture -- every branch of mathematics that runs inside your AI, all connected. THEN: 2,000+ years of human curiosity, from Archimedes to Vaswani, converging in one architecture.
- **Build-up connection:** "But the story isn't over." -> Slide 29.

#### SLIDE 29: The Story Is Not Over
- **The ONE thing:** Mathematics is still being invented. The LLM is not the end; it is the latest chapter.
- **Content:** From original slide 78. Open questions: Why do transformers work so well? What are the limits of scaling? What comes after transformers? New mathematical frontiers.
- **Visual:** Clean text with three "open question" boxes. Forward-looking.
- **Speaker's story:** "The transformer is not the end of the story. It's the latest chapter. Nobody fully understands why transformers work as well as they do. The math is 2,000 years old but the architecture is only 8 years old. There are open questions everywhere. And the people who will answer them might be sitting in this room."
- **NOW/THEN:** NOW: Transformers power everything, but nobody fully understands why they work this well. THEN: Every breakthrough we covered today started with someone asking a question nobody else was asking. The next breakthrough will start the same way.
- **Build-up connection:** -> Slide 30.

#### SLIDE 30: Closing -- 2,000+ Years. One Machine. Your Turn.
- **The ONE thing:** The audience is part of this story. The relay continues.
- **Content:** "2,000+ Years of Mathematics. One Machine. Your Turn." Further reading suggestions. The final convergence diagram in miniature.
- **Visual:** Full-bleed violet background (matching slide 1). Clean typography. A visual bookend.
- **Speaker's story:** "Every piece of mathematics we covered today was invented by someone who had no idea it would end up inside an AI. Grassmann was a schoolteacher. Pascal was answering a gambling question. Fourier was studying heat. Boltzmann was studying gas molecules. They followed their curiosity and built the future. The next great idea might come from you. Thank you."
- **NOW/THEN:** NOW: You understand the machine. Every piece, every inventor, every date. THEN: They all started by following their curiosity. Your turn.
- **Build-up connection:** End. Applause.

---

### WHAT GETS CUT (AND WHY)

For each of the ~48 slides removed from the original 78, with every original slide's fate accounted for:

**Section 0 - Opening (1 cut):**
- Slide 1 (title): Becomes new slide 1.
- Slide 2 (hook): Becomes new slide 2.
- Slide 3 (exploded transformer): Merged into slide 2's "what's inside" framing; the roadmap diagram (new slide 3) carries the preview role.
- Slide 4 (convergence diagram): Becomes new slide 3.

**Section 1 - Linear Algebra (9 cuts):**
- Slide 5 (section divider): Cut. Replaced by direct entry; 30 slides can't afford section dividers.
- Slide 6 (vectors - Grassmann/Hamilton): MERGED into new slide 4.
- Slide 7 (Gibbs/Heaviside notation): Cut. Notation history is not essential to the story.
- Slide 8 (matrices - Cayley/Sylvester): MERGED into new slide 4.
- Slide 9 (matrix multiplication - Gauss): MERGED into new slide 4.
- Slide 10 (dot product): MERGED into new slide 5.
- Slide 11 (cosine similarity): Cut. Dot product sufficient; cosine is a refinement.
- Slide 12 (eigenvalues - EXTENDED): Cut. Marked EXTENDED in original. Not on the main path.
- Slide 13 (high-dimensional spaces): MERGED into new slide 5.
- Slide 14 (embedding pipeline): MERGED into new slide 5.
- Slide 15 (attention preview): Cut. Attention will be fully covered in slides 22-24; preview is a luxury.
- Slide 16 (convergence diagram - linear algebra): MERGED into new slide 6.
- Interactive moment (king-man+woman): PRESERVED in new slide 5.

**Section 2 - Calculus (6 cuts):**
- Slide 17 (section divider): Cut. Replaced by transition in new slide 6.
- Slide 18 (Archimedes): MERGED into new slide 7.
- Slide 19 (derivative - Fermat/Newton/Leibniz): MERGED into new slide 7.
- Slide 20 (gradient descent - Cauchy): MERGED into new slide 7.
- Slide 21 (GD visualized - loss landscape): MERGED into new slide 7.
- Slide 22 (backpropagation): MERGED into new slide 8.
- Slide 23 (Adam optimizer - EXTENDED): Cut. Adam is a refinement; GD + backprop is sufficient.
- Slide 24 (convergence diagram - calculus): MERGED into new slide 9.
- Slide 25 (convergence diagram variant): Redundant with new slide 9.

**Section 3 - Probability (6 cuts):**
- Slide 26 (section divider): Cut. Replaced by transition in new slide 9.
- Slide 27 (Pascal/Fermat): MERGED into new slide 10.
- Slide 28 (Bernoulli/Laplace): Cut. Law of large numbers is implicit in "more data = better"; not plot-critical.
- Slide 29 (Bayes): MERGED into new slide 10.
- Slide 30 (Kolmogorov - EXTENDED): Cut. Marked EXTENDED in original. Axioms not needed for the narrative.
- Slide 31 (Fisher - MLE): Cut. MLE is important but can be mentioned verbally; not a must-show concept for the audience.
- Slide 32 (Shannon language models): MERGED into new slide 10.
- Slide 33 (softmax): Becomes standalone new slide 11.
- Slide 34 (convergence diagram - probability): MERGED into new slide 12.

**Section 4 - Information Theory (5 cuts):**
- Slide 35 (section divider): Cut. Section merged with probability convergence.
- Slide 36 (entropy - three inventions): Cut. Entropy can be mentioned verbally; cross-entropy is the must-have.
- Slide 37 (cross-entropy): MERGED into new slide 12.
- Slide 38 (surprisal/perplexity): Cut. Evaluation metrics are a refinement; not needed for the core story.
- Slide 39 (KL divergence - EXTENDED): Cut. Marked EXTENDED. RLHF detail not needed.
- Slide 40 (tokenization): Cut. BPE is interesting but not a building block of the transformer architecture.
- Slide 41 (convergence diagram - info theory): MERGED into new slide 12.

**Section 5 - Logic & Computation (5 cuts):**
- Slide 42 (section divider): Cut.
- Slide 43 (Boolean algebra): MERGED into new slide 13.
- Slide 44 (Frege/Russell - EXTENDED): Cut. Formal logic history is a detour.
- Slide 45 (Godel/Turing): MERGED into new slide 13.
- Slide 46 (von Neumann): MERGED into new slide 13.
- Slide 47 (GPU): MERGED into new slide 13.
- Slide 48 (convergence diagram - logic): MERGED into new slide 14.

**Section 6 - Function Approximation (3 cuts):**
- Slide 49 (section divider): Cut.
- Slide 50 (Fourier): MERGED into new slide 14.
- Slide 51 (Weierstrass - EXTENDED): Cut. Marked EXTENDED. Polynomials not needed when we have neural nets.
- Slide 52 (Cybenko): MERGED into new slide 14.
- Slide 53 (convergence diagram - func approx): MERGED into new slide 14.

**Section 7 - Neuron & Depth (5 cuts):**
- Slide 54 (section divider): Cut.
- Slide 55 (McCulloch-Pitts): MERGED into new slide 15.
- Slide 56 (Rosenblatt): MERGED into new slide 15.
- Slide 57 (XOR crash): MERGED into new slide 16.
- Slide 58 (multi-layer comeback): MERGED into new slide 16.
- Slide 59 (activation functions): MERGED into new slide 17.
- Slide 60 (residual connections): MERGED into new slide 17.
- Slide 61 (layer norm/dropout): MERGED into new slide 17.
- Slide 62 (convergence diagram): MERGED into new slide 18.

**Section 8 - Sequence Modeling (4 cuts):**
- Slide 63 (section divider): Cut.
- Slide 64 (Markov chains): MERGED into new slide 19.
- Slide 65 (HMMs): Cut. HMMs are a detour from the main arc (Markov -> RNN problem -> attention).
- Slide 66 (RNN): MERGED into new slide 19.
- Slide 67 (LSTM - EXTENDED): Cut. Marked EXTENDED. LSTM can be mentioned verbally; attention is the must-have.
- Slide 68 (attention mechanism): MERGED into new slide 19.

**Section 9 - Transformer (1 cut):**
- Slide 69 (section divider): Cut. Replaced by buildup in new slide 20.
- Slide 70 (paper intro): Becomes new slide 21.
- Slide 71 (self-attention): Becomes new slide 22.
- Slide 72 (multi-head + FFN): MERGED into new slide 23.
- Slide 73 (full annotated transformer): Becomes new slide 24.
- Slide 74 (positional encoding): Becomes new slide 25.

**Section 10 - Scaling + Close (0 cuts):**
- Slide 75 (scaling leap): Becomes new slide 26.
- Slide 76 (return to diagram): Becomes new slide 27.
- Slide 77 (final convergence): Becomes new slide 28.
- Slide 78 (closing): Split into new slides 29-30.

---

### INTERACTIVE MOMENTS (3 total)

All 3 interactive moments are included in the 45-minute timing estimate.

1. **Slide 5: "King - Man + Woman = ?"** (~2 minutes) -- Students guess. Reveal: queen. Demonstrates word vector arithmetic.

2. **Slide 11: "The cat sat on the ___"** (~2 minutes) -- Quick poll. Collect student answers. Show the AI's softmax probability distribution. Demonstrates how probability picks words.

3. **Slide 24: "Count the Building Blocks"** (~3 minutes) -- Students look at the full annotated transformer and identify which section each component comes from. The payoff moment.

---

### CONVERGENCE DIAGRAM APPEARANCES (9 total)

| Slide | Nodes Lit | Caption |
|-------|-----------|---------|
| 3 | 0 of 10 (all gray) | "Our roadmap" |
| 6 | 1 of 10 | "Linear Algebra = skeleton" |
| 9 | 2 of 10 | "Calculus = learning" |
| 12 | 4 of 10 | "Probability + Info Theory = prediction + scoring" |
| 14 | 6 of 10 | "Logic + Function Approx = substrate + guarantee" |
| 18 | 7 of 10 | "Neuron & Depth = the unit + the stack" |
| 20 | 8 of 10 | "Sequence = the bridge" |
| 25 | 9 of 10 | "Transformer architecture complete" |
| 28 | 10 of 10 | "TRANSFORMER" replaces "?" -- full convergence |

Note: 9 appearances in 30 slides -- averaging one every 3-4 slides, which maintains continuity without repetitiveness. The TRUE convergence moment (all 10 lit, "?" replaced with "TRANSFORMER") occurs on slide 28. Slide 25 marks the completion of the transformer *section* (9 of 10); slide 28 marks the completion of the entire *story* (10 of 10, including scaling).

---

### TIMING ESTIMATE

All times are inclusive of interactive moments and pauses.

| Slide Range | Slides | Minutes | Pace | Notes |
|-------------|--------|---------|------|-------|
| 1-3 (Opening) | 3 | 4 | 1.3 min/slide | |
| 4-6 (Linear Algebra) | 3 | 5 | 1.7 min/slide | Includes interactive moment 1 (~2 min) |
| 7-9 (Calculus) | 3 | 4 | 1.3 min/slide | |
| 10-12 (Probability + Info Theory) | 3 | 5 | 1.7 min/slide | Includes interactive moment 2 (~2 min) |
| 13-14 (Logic + Function Approx) | 2 | 3 | 1.5 min/slide | |
| 15-18 (Neuron & Depth) | 4 | 6 | 1.5 min/slide | Drama arc needs pacing |
| 19-20 (Sequence) | 2 | 3 | 1.5 min/slide | |
| 21-25 (Transformer) | 5 | 8 | 1.6 min/slide | Includes interactive moment 3 (~3 min) |
| 26-28 (Scaling + Convergence) | 3 | 4 | 1.3 min/slide | |
| 29-30 (Closing) | 2 | 3 | 1.5 min/slide | |
| **Total** | **30** | **~45 min** | **1.5 min/slide avg** | **Includes ~7 min interactive** |

Without interactive moments, pure lecture time is ~38 minutes.

---

### IMPLEMENTATION NOTES

1. **Section dividers are gone.** Every original section had a colored divider slide. In the 30-slide version, transitions happen via the convergence diagram updates and spoken transitions. This saves 10 slides.

2. **EXTENDED slides are all cut.** Original slides marked [EXTENDED] (eigenvalues, Kolmogorov, KL divergence, Weierstrass, LSTM, Adam optimizer) are all removed. They were designed as optional content.

3. **The convergence diagram does double duty.** In the 78-slide version, convergence updates got their own dedicated slides. In the 30-slide version, they share slides with section summaries, saving ~5 slides.

4. **Dense slides require strong speaker notes.** Each slide in the 30-slide version carries the content of 2-3 original slides. The visual should remain clean -- the density lives in the speaker's words, not on the screen. Slide 12 is the densest: the visual shows ONLY the convergence diagram and the cross-entropy worked example; the probability summary table lives in the speaker's words.

5. **The "Time Machine" is operationalized, not decorative.** Every slide has a NOW/THEN transition in the speaker notes. This is not a framing gimmick -- it is a rhythmic device that keeps the past-present oscillation concrete and consistent throughout all 30 slides. The pattern: NOW (what the student sees/uses today) -> THEN (specific date, person, place) -> BRIDGE (the connection).

6. **Positional encoding placement.** Slide 24 (the full annotated transformer) labels positional encoding as a component in the pipeline. Slide 25 then gives it a focused explanation. This is intentional: slide 24 shows WHERE it fits in the architecture; slide 25 explains HOW it works (Fourier's sine waves) and also serves as the transformer section's convergence checkpoint (node 9 lights up). The full convergence (node 10, "TRANSFORMER") occurs on slide 28 after scaling is covered.

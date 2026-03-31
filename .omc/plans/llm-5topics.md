# LLM Building Blocks: 5-Topic Anchor Structure

**Date:** 2026-03-31
**Type:** Radical restructuring (NOT a condensation of the 30-slide or 78-slide versions)
**Target:** ~28 slides, 5 topics, 1 anchor concept
**Duration:** ~45 minutes (including 2 interactive moments)
**Audience:** High school seniors in mathematics
**Output:** Standalone Beamer LaTeX file (`llm-5topics.tex`)

---

## WHY THIS STRUCTURE IS BETTER

### The Problem with the 30-Slide Version

The 30-slide version organizes by **mathematical discipline**: linear algebra, calculus, probability, information theory, logic, function approximation, neurons, sequences, transformer, scaling. This is the professor's mental model, not the student's. A high school senior hears "Section 4: Information Theory" and thinks: *why do I need this?* The answer comes minutes later, after the math. Motivation lags behind content.

### Why 5-Topics-from-One-Anchor Wins

| Dimension | 10 Sections (old) | 5 Topics (new) |
|-----------|-------------------|-----------------|
| **Organizing principle** | Math discipline | Function in the LLM |
| **Opening question** | Different each section | SAME every time ("the cat sat on the ___") |
| **Motivation** | "Here is the math. Later you will see why." | "Here is the question. The math answers it." |
| **Recall** | Students remember chapter titles (poorly) | Students remember questions (well) |
| **Pattern** | Different structure each section | SAME structure every topic -- becomes comfortable |
| **Coherence** | 10 disconnected starts | 1 question, 5 facets |
| **Cognitive load** | 10 context switches | 5 context switches, each anchored to the same sentence |

**The key insight:** When you organize by *what the LLM does* instead of *what the math is called*, the "why do I need this?" question is answered BEFORE the math appears. Every topic opens with a question the student naturally wants answered. The math is the answer, not the premise.

**The repeated pattern becomes a learning scaffold.** By topic 3, students know what to expect: question, history, mechanism, inside the LLM, progress check. The familiar structure frees cognitive resources for the content.

---

## THE ANCHOR

### "The cat sat on the ___"

This sentence appears on the OPENING slide and RETURNS at the start of every topic. It is the single through-line.

- Topic 1: "The cat sat on the ___." How does the AI know that "mat" and "rug" are similar, but "quantum" is not?
- Topic 2: "The cat sat on the ___." How does the AI choose "mat" (68%) over "floor" (15%) over "table" (8%)?
- Topic 3: "The cat sat on the ___." The AI said "dog" (wrong). How does it learn from that mistake?
- Topic 4: "The cat sat on the ___." But what if the sentence is longer? "The cat sat on the mat because it was ___." How does "it" know to refer to "cat"?
- Topic 5: "The cat sat on the ___." One layer gets it wrong. 96 layers get it right. How does depth help?

Each topic peels a new layer from the SAME sentence. The student never loses the thread.

---

## THE PATTERN (identical for every topic)

| Beat | Slide count | Purpose |
|------|-------------|---------|
| **The Question** | 1 slide | Return to the anchor sentence. Pose the sub-question. |
| **The History** | 2 slides | Who invented the key math, when, why. Human stories. |
| **The Mechanism** | 2 slides | How it works. Visual, intuitive. Conceptual first, formula in small inset. |
| **Inside the LLM** | 1 slide | Show exactly where this math lives in the transformer diagram. Progress bar updates. |

Total per topic: 5-6 slides. Across 5 topics: 25-30 slides.

---

## THE 5 TOPICS: FULL DEFINITIONS

---

### TOPIC 1: "How does it know which words are similar?"

**The question (exact wording):**
"The cat sat on the ___." The AI thinks "mat" and "rug" are good answers, but not "quantum." How does it know which words are similar?

**Building blocks covered:**
- Vectors (Grassmann, 1844)
- Matrices and matrix multiplication (Cayley, 1858; Gauss, 1809)
- Dot product (Gibbs, 1881)
- High-dimensional spaces
- Word embeddings (Mikolov/Word2Vec, 2013)
- Embedding layers in the transformer

**Key persons (max 4):**
1. Hermann Grassmann (1844) -- schoolteacher nobody read; invented vector spaces
2. Arthur Cayley (1858) -- defined matrix multiplication
3. J. Willard Gibbs (1881) -- formalized the dot product
4. Tomas Mikolov (2013) -- Word2Vec, showed words live in vector space

**The "aha!" moment:**
Words ARE numbers. "King" is a list of 768 numbers. "Queen" is a nearby list. Similarity is literally distance. The dot product -- a formula from 1881 -- is how the AI measures closeness between words. king - man + woman = queen is not a trick; it is geometry.

**The visual that makes it click:**
2D word-vector map showing clusters: {cat, dog, pet} near each other, {mat, rug, carpet} near each other, {quantum, entropy} far away. Arrows showing "similar = close, different = far." Then: the king-man+woman=queen parallelogram.

---

### TOPIC 2: "How does it choose the next word?"

**The question (exact wording):**
"The cat sat on the ___." The AI has 50,000 words to choose from. It picks "mat" 68% of the time, "floor" 15%, "table" 8%... How does it assign these probabilities?

**Building blocks covered:**
- Probability (Pascal & Fermat, 1654)
- Bayes' theorem (Bayes, 1763)
- Language as a statistical process (Shannon, 1948)
- Softmax function (Boltzmann, 1870s)
- Cross-entropy loss (Shannon, 1948)
- Information theory fundamentals (entropy, surprisal)
- Perplexity as evaluation metric

**Key persons (max 4):**
1. Blaise Pascal (1654) -- probability born from a gambling question
2. Ludwig Boltzmann (1870s) -- the softmax formula, from thermodynamics
3. Claude Shannon (1948) -- language as statistics; cross-entropy; information theory
4. Thomas Bayes (1763) -- updating beliefs from evidence

**The "aha!" moment:**
The AI does not "understand" language. It assigns probabilities to every possible next word, then samples. The formula that converts raw scores into probabilities -- softmax -- was invented by a physicist studying gas molecules 150 years ago. Every word your AI says is chosen by Boltzmann's equation.

**The visual that makes it click:**
Bar chart: "the cat sat on the ___" with bars for mat (68%), floor (15%), table (8%), couch (4%), other (5%). Below: the softmax pipeline (raw scores -> exp -> normalize -> probabilities). The transformation from "meaningless numbers" to "probability distribution."

---

### TOPIC 3: "How does it learn from mistakes?"

**The question (exact wording):**
"The cat sat on the ___." The AI said "dog." That's wrong. It checks its mistake (cross-entropy), then adjusts. But HOW does the correction travel backward through 96 layers?

**Building blocks covered:**
- Derivatives (Fermat/Newton/Leibniz, 1660s-1680s)
- Gradient descent (Cauchy, 1847)
- The chain rule
- Backpropagation (Linnainmaa, 1970; Rumelhart/Hinton/Williams, 1986)
- Loss functions (connecting back to cross-entropy from Topic 2)
- Optimization (learning rate, convergence)
- Adam optimizer (brief mention)

**Key persons (max 4):**
1. Augustin-Louis Cauchy (1847) -- gradient descent: "compute the slope, step downhill, repeat"
2. Seppo Linnainmaa (1970) -- automatic differentiation (the algorithm)
3. Geoffrey Hinton (1986) -- backpropagation in neural networks (the comeback)
4. Newton/Leibniz (1680s) -- the derivative itself

**The "aha!" moment:**
The AI learns by rolling downhill on a landscape made of calculus. It predicts a word, measures how wrong it was (cross-entropy from Topic 2), computes the slope (derivative), and adjusts every layer using the chain rule. The chain rule from your calculus class IS the algorithm that trains every AI on Earth.

**The visual that makes it click:**
3D loss landscape with a ball rolling downhill (gradient descent). Arrows showing the backward flow: prediction -> loss -> gradient flows backward through layers -> each layer adjusts. The "recipe" box: 1. Predict. 2. Measure error. 3. Compute slopes. 4. Adjust. 5. Repeat billions of times.

---

### TOPIC 4: "How does it understand context?"

**The question (exact wording):**
"The cat sat on the mat because IT was ___." What does "it" refer to? The cat? The mat? For that, the AI needs to look BACK at the whole sentence. How?

**Building blocks covered:**
- Sequence modeling (Markov, 1906)
- The memory problem (RNNs forget after ~50 words)
- Attention mechanism (Bahdanau, 2014)
- Self-attention (Vaswani et al., 2017)
- Query/Key/Value framework
- Multi-head attention
- Positional encoding (Fourier, 1807 -> Vaswani, 2017)
- The transformer architecture ("Attention Is All You Need")
- The 8 authors

**Key persons (max 4):**
1. Andrey Markov (1906) -- sequence modeling, analyzed Pushkin's poetry
2. Dzmitry Bahdanau (2014) -- attention: "why forget anything?"
3. Ashish Vaswani (2017) -- the transformer, self-attention
4. Joseph Fourier (1807) -- sine waves for position (positional encoding)

**The "aha!" moment:**
Attention lets every word look at every other word and decide what matters. The word "it" looks back at "cat" and "mat" and assigns attention weights. This is the dot product from Topic 1, applied between words in the same sentence. Eight researchers at Google combined attention with everything from Topics 1-3 into one architecture: the transformer. That architecture powers every major AI.

**The visual that makes it click:**
"The cat sat on the mat because it was tired" -- attention heatmap showing "it" attending strongly to "cat." The Q/K/V pipeline: each word asks a question (Q), offers a key (K), and carries information (V). Then: the full annotated transformer diagram with every component labeled with its inventor and the topic where the student learned it.

---

### TOPIC 5: "How does it get so good?"

**The question (exact wording):**
"The cat sat on the ___." One layer gets it partially right. 96 layers get it very right. 175 billion parameters, trained on the entire internet. How does SCALE turn mediocre math into something that feels like intelligence?

**Building blocks covered:**
- The artificial neuron (McCulloch & Pitts, 1943)
- The perceptron and the AI winter (Rosenblatt, 1958; Minsky/Papert, 1969)
- Activation functions (sigmoid -> ReLU -> GELU)
- Residual connections (He, 2015)
- Layer normalization (Ba, 2016)
- Universal approximation theorem (Cybenko, 1989; Fourier, 1807)
- Boolean logic and hardware (Boole, 1854; Turing, 1936)
- GPUs and compute (NVIDIA CUDA, 2007)
- Scaling laws (Kaplan et al., 2020)
- The GPT series (GPT-1 to GPT-4)

**Key persons (max 4):**
1. McCulloch & Pitts (1943) -- the mathematical neuron
2. Frank Rosenblatt (1958) / Minsky & Papert (1969) -- the hype, the crash, the lesson
3. Kaiming He (2015) -- residual connections that made 96 layers possible
4. George Cybenko (1989) -- the universal approximation theorem (the guarantee)

**The "aha!" moment:**
The neuron was invented in 1943. The crash came in 1969 (one layer is not enough). The comeback came in 1986 (backpropagation). But it took three more inventions -- activation functions, residual connections, layer normalization -- to make DEEP networks practical. Then scaling: same architecture, just bigger. The transformer from 2017 is the same architecture in GPT-4. The math did not change. The scale did. And nobody fully understands why scale works this well. The story is not over.

**The visual that makes it click:**
Left: the single neuron (inputs, weights, sum, activation, output). Right: stack of 96 layers with residual connections (skip arrows) and normalization blocks. Below: the scaling chart (GPT-1 117M -> GPT-3 175B -> GPT-4 undisclosed). The exponential curve. The same blueprint, 1,500x larger.

---

## SLIDE-BY-SLIDE PLAN (28 slides total)

---

### OPENING (2 slides)

---

#### SLIDE 1: Title Slide

- **Title:** The Building Blocks of LLMs: A Mathematical History
- **The ONE thing:** Set scope and anticipation.
- **Visual:** Full-bleed aiViolet background. Clean typography. "From One Sentence to One Machine: 2,000+ Years of Mathematics Inside Your AI."
- **Speaker's story:** "This lecture is about one sentence, one question, and the 2,000 years of mathematics that make the answer possible."
- **Connection to anchor:** The sentence is about to appear.

---

#### SLIDE 2: The Anchor -- "The cat sat on the ___"

- **Title:** One Sentence. Five Questions.
- **The ONE thing:** Introduce the anchor sentence that will drive the entire lecture.
- **Visual:** Large text: "The cat sat on the ___." Below: five questions, dimmed (will light up one by one):
  1. How does it know which words are similar?
  2. How does it choose the next word?
  3. How does it learn from mistakes?
  4. How does it understand context?
  5. How does it get so good?
- **Speaker's story:** "Every time you type something into ChatGPT or Claude, the AI is doing one thing: predicting the next word. 'The cat sat on the ___.' That is it. That is the entire game. But to play this game, the AI needs five abilities. We are going to discover them one by one. Each ability was invented by specific people, at specific times, for reasons that had nothing to do with AI. And together, they form the machine you use every day."
- **Connection to anchor:** This IS the anchor. Every subsequent topic returns here.
- **Design note:** The five questions form a vertical list. Each lights up in its topic color as we reach it. By slide 27, all five are lit.

---

### TOPIC 1: "How does it know which words are similar?" (5 slides)

**Topic color:** linalgTeal

---

#### SLIDE 3: The Question -- Words as Numbers

- **Title:** "The cat sat on the ___." How does it know which words are similar?
- **The ONE thing:** To measure similarity, the AI turns words into lists of numbers (vectors).
- **Visual:** Left: the anchor sentence with "mat," "rug," "carpet" highlighted as good candidates, "quantum" crossed out. Right: "mat" = [0.2, 0.8, -0.1, ...] (768 numbers). Question mark: how does the AI know "mat" and "rug" are close but "quantum" is far?
- **Speaker's story:** "Let's start with the most basic question. The AI thinks 'mat' is a good answer. It also likes 'rug' and 'carpet.' But not 'quantum.' How does it know? The answer: it turns every word into a list of numbers -- a vector. And similar words end up as similar lists."
- **Connection to anchor:** Direct. This is the first facet of "predicting the next word."

---

#### SLIDE 4: The History -- Grassmann, Cayley, Gibbs

- **Title:** The Inventors of the Number-World
- **The ONE thing:** Three people invented the math that turns words into numbers: Grassmann (vectors), Cayley (matrices), Gibbs (dot product).
- **Visual:** Three portrait-style panels: (1) Grassmann (1844, Stettin) -- "A schoolteacher nobody read. Invented vector spaces." (2) Cayley (1858, London) -- "Named by Sylvester: 'matrix' = Latin for 'womb.' It gives birth to numbers." (3) Gibbs (1881, New Haven) -- "The dot product: multiply, add, get similarity."
- **Speaker's story:** "Grassmann was a schoolteacher in Prussia. He published a book so abstract that nobody read it. It defined vector spaces -- the exact mathematical structure that AI uses to represent words. Sylvester, a failed barrister, named the matrix. Gibbs, a physicist at Yale, formalized the dot product. None of them had any idea their math would end up inside your phone."
- **Connection to anchor:** "These are the tools that let the AI measure 'mat' vs. 'quantum.'"

---

#### SLIDE 5: The Mechanism -- Embeddings and the Dot Product

- **Title:** Words Live in a Number-World
- **The ONE thing:** Words become vectors (embeddings). The dot product measures similarity. king - man + woman = queen.
- **Visual:** Top: 2D word map with clusters (animals, furniture, abstract). Dot product = similar (high), unrelated (zero), opposite (negative). Bottom: king-man+woman=queen parallelogram.
- **INTERACTIVE MOMENT 1:** "What does king minus man plus woman equal?" Collect guesses. Reveal: queen. "This is not a trick. This is geometry in 768 dimensions." (~2 minutes)
- **Speaker's story:** "Mikolov showed in 2013 that if you train a neural network to predict words from context, the vectors it learns have astonishing properties. Similar words cluster together. And relationships are preserved as directions: king is to queen as man is to woman. The dot product -- Gibbs's formula from 1881 -- is the similarity measure. High dot product = similar. Zero = unrelated."
- **Connection to anchor:** "Now the AI knows 'mat' and 'rug' are similar. But which one should it pick?"

---

#### SLIDE 6: The Mechanism -- How Neural Network Layers Work

- **Title:** Every Layer Is a Matrix Multiplication
- **The ONE thing:** A neural network layer multiplies your data by a matrix. 96 layers = 96 matrix multiplications.
- **Visual:** Left: simple matrix-times-vector diagram. Right: stack of 96 layers, each one a matrix multiplication. Callout: "Cayley's math from 1858, repeated 96 times, is the engine of modern AI."
- **Speaker's story:** "Every layer in a neural network does one thing: multiply your data by a matrix and transform it. That is Cayley's matrix multiplication from 1858. Stack 96 of these and you have GPT-4. The math has not changed. The scale has."
- **Connection to anchor:** "The AI now has a number-world for words and a way to transform them. But it still needs to pick a word."

---

#### SLIDE 7: Inside the LLM -- Where Vectors and Matrices Live

- **Title:** Building Block Found: Vectors, Matrices, Dot Product
- **The ONE thing:** Show where embeddings, matrix multiplications, and dot products appear in the transformer.
- **Visual:** Left: simplified transformer diagram with the embedding layer, attention dot products, and matrix multiplications HIGHLIGHTED in teal. Everything else grayed out. Right: progress bar (1/5 lit). The five-question list from slide 2 with question 1 now lit in teal.
- **Speaker's story:** "The embedding layer -- that is Grassmann's vector space. Every attention score -- that is Gibbs's dot product. Every layer transformation -- that is Cayley's matrix multiplication. One building block found. Four to go."
- **Connection to anchor:** "We know which words are similar. Now: how does the AI CHOOSE?"

---

### TOPIC 2: "How does it choose the next word?" (5 slides)

**Topic color:** probBlue

---

#### SLIDE 8: The Question -- From Scores to Probabilities

- **Title:** "The cat sat on the ___." How does it choose the next word?
- **The ONE thing:** The AI has raw scores for 50,000+ words. It needs to turn them into probabilities and pick one.
- **Visual:** Left: the anchor sentence. Right: a messy list of raw numbers (logits): mat = 3.2, floor = 1.8, table = 1.1, quantum = -4.7... Question: how do these become "mat 68%, floor 15%..."?
- **Speaker's story:** "Back to our sentence. The AI has processed it through its layers and now has a raw score for every word in its vocabulary -- over 50,000 words. 'Mat' scores high. 'Quantum' scores low. But these are just numbers, not probabilities. How does it turn scores into a choice?"
- **Connection to anchor:** Direct return to the anchor. Second facet.

---

#### SLIDE 9: The History -- Pascal, Boltzmann, Shannon

- **Title:** From a Gambling Question to Every Word AI Says
- **The ONE thing:** Probability was born from gambling (Pascal, 1654). The formula that converts scores to probabilities came from physics (Boltzmann, 1870s). The measure of prediction quality came from communication (Shannon, 1948).
- **Visual:** Three-panel timeline: (1) Pascal/Fermat, 1654, the dice letter. (2) Boltzmann, 1870s, gas molecules and energy distributions. (3) Shannon, 1948, "A Mathematical Theory of Communication" -- language as statistics.
- **Speaker's story:** "Probability started because a gambler lost at dice and wrote to Blaise Pascal. Pascal wrote to Fermat. Their letters invented a new branch of mathematics. Then in the 1870s, Boltzmann studied how gas molecules distribute among energy levels and wrote down a formula: e to the x over the sum of e to the x. That exact formula -- now called softmax -- is how every AI picks every word. And Shannon, in 1948, showed how to measure whether the predictions are any good."
- **Connection to anchor:** "Pascal's gambling question -> Boltzmann's gas molecules -> the AI choosing 'mat.'"

---

#### SLIDE 10: The Mechanism -- Softmax

- **Title:** The Softmax Pipeline
- **The ONE thing:** Softmax converts raw scores into probabilities. This is Boltzmann's formula applied to words.
- **Visual:** The pipeline: raw scores (logits) -> exponentiate (e^x) -> normalize (divide by sum) -> probabilities. Bar chart: mat 68%, floor 15%, table 8%, couch 4%, other 5%. Formula inset: softmax(z_i) = e^{z_i} / sum(e^{z_j}).
- **INTERACTIVE MOMENT 2:** "What word comes next: 'The cat sat on the ___'?" Collect answers from the class. Show the AI's actual softmax distribution alongside the class's distribution. "You and the AI are doing the same thing -- predicting the next word. The AI just uses Boltzmann's formula." (~2 minutes)
- **Speaker's story:** "Step 1: exponentiate every score, making them all positive and amplifying differences. Step 2: divide by the total, so they sum to 1. Now they are probabilities. This is Boltzmann's distribution from thermodynamics, applied to words. Every single word your AI says is chosen by this pipeline."
- **Connection to anchor:** "The AI now picks words. But how does it know if it picked WELL?"

---

#### SLIDE 11: The Mechanism -- Cross-Entropy and Information Theory

- **Title:** Measuring Mistakes: Cross-Entropy
- **The ONE thing:** Cross-entropy (Shannon, 1948) measures how wrong the AI's prediction was. This is the loss function that drives all learning.
- **Visual:** Two scenarios: (A) AI says "mat" with 80% confidence -> loss = 0.22 (good). (B) AI says "mat" with 5% confidence -> loss = 3.00 (terrible). Formula inset: loss = -log(p(correct word)). Conceptual: "The more surprised the AI is by the right answer, the higher the loss."
- **Speaker's story:** "Shannon needed a way to measure information. He defined cross-entropy: how surprised you are by the truth, given your predictions. Low surprise = good model. High surprise = bad model. This number -- cross-entropy loss -- is the ONLY thing the AI tries to minimize during training. It connects prediction (Topic 2) to learning (Topic 3). Shannon's 1948 formula is the bridge."
- **Connection to anchor:** "The AI predicted 'mat' but the answer was 'rug.' Loss is high. Now it needs to learn from that mistake."

---

#### SLIDE 12: Inside the LLM -- Where Probability Lives

- **Title:** Building Block Found: Probability, Softmax, Cross-Entropy
- **The ONE thing:** Show where softmax and cross-entropy appear in the transformer.
- **Visual:** Left: transformer diagram with output softmax layer and loss computation HIGHLIGHTED in blue. Everything else grayed out, except Topic 1 components (still teal). Right: progress bar (2/5 lit). Questions 1-2 now lit.
- **Speaker's story:** "The output layer of every transformer is a softmax. The training signal is cross-entropy. Pascal's gambling question, Boltzmann's gas molecules, Shannon's information theory -- all running in one layer. Two building blocks found. Three to go."
- **Connection to anchor:** "The AI made a wrong prediction. Cross-entropy measured the mistake. But how does the correction travel BACKWARD through 96 layers?"

---

### TOPIC 3: "How does it learn from mistakes?" (5 slides)

**Topic color:** calculusRed

---

#### SLIDE 13: The Question -- Learning by Adjusting

- **Title:** "The cat sat on the ___." The AI said "dog." How does it learn from that mistake?
- **The ONE thing:** The AI predicted wrong. It needs to adjust 175 billion parameters so it does better next time. How?
- **Visual:** Left: the anchor sentence with "dog" as the wrong prediction (red X). Right: a cartoon of 175 billion tiny knobs. Question: how do you adjust EACH knob the right amount?
- **Speaker's story:** "The AI said 'dog.' That is wrong. Cross-entropy says the loss is high. Now the AI needs to adjust its parameters -- all 175 billion of them -- so that next time, 'mat' gets a higher score and 'dog' gets a lower score. But you cannot just randomly wiggle 175 billion knobs. You need a systematic way to know WHICH direction to adjust EACH one. That is calculus."
- **Connection to anchor:** Direct return. Third facet.

---

#### SLIDE 14: The History -- Cauchy and the Art of Going Downhill

- **Title:** Gradient Descent: Compute the Slope, Step Downhill, Repeat
- **The ONE thing:** Cauchy (1847) invented gradient descent. The derivative tells you which direction is downhill. Step that way. Repeat.
- **Visual:** Left: Cauchy portrait, 1847 Paris. Right: 3D loss landscape with a ball at a high point, arrows showing the downhill path, landing at the minimum. The recipe: "1. Where am I? 2. Which way is downhill? (derivative) 3. Take a step. 4. Repeat."
- **Speaker's story:** "Archimedes was doing proto-calculus in 250 BCE. Newton and Leibniz formalized the derivative in the 1680s. But the hero for AI is Cauchy. In 1847 he asked: if I can compute the slope at any point, can I find the bottom of a valley by always stepping downhill? Yes. That is gradient descent. Every AI on Earth learns this way: compute the slope, step downhill, repeat. Billions of times."
- **Connection to anchor:** "Cauchy found the valley floor. But how does the slope information travel BACKWARD through 96 layers?"

---

#### SLIDE 15: The Mechanism -- Backpropagation and the Chain Rule

- **Title:** The Chain Rule Trains Every AI
- **The ONE thing:** Backpropagation uses the chain rule to send the error signal backward through every layer, adjusting each one.
- **Visual:** Left: the chain rule as a "telescope" -- derivative of a composition = product of individual derivatives. Right: a 3-layer network with arrows flowing BACKWARD from the loss, each layer receiving its gradient. Labels: Linnainmaa (1970, automatic differentiation), Hinton (1986, backpropagation in neural networks).
- **Speaker's story:** "The chain rule from your calculus class: the derivative of a composition is the product of the individual derivatives. Linnainmaa automated this in 1970. Hinton made it famous for neural networks in 1986. The algorithm: compute the loss at the output, then send the error signal backward, layer by layer, using the chain rule. Each layer learns how much it contributed to the error and adjusts accordingly. This is how 175 billion parameters learn from one wrong prediction."
- **Connection to anchor:** "The error from saying 'dog' instead of 'mat' flows backward through all 96 layers. Each layer adjusts. Repeat this billions of times and the AI gets good."

---

#### SLIDE 16: The Mechanism -- The Learning Loop

- **Title:** The Training Loop
- **The ONE thing:** Training = predict, measure loss, backpropagate, adjust, repeat. Billions of sentences, billions of iterations.
- **Visual:** A circular diagram: Sentence -> Predict next word -> Measure loss (cross-entropy, Topic 2) -> Compute gradients (chain rule) -> Adjust parameters (gradient descent) -> Next sentence. Arrow: "Repeat 300 billion times." Scale callout: GPT-3 trained on 300 billion tokens.
- **Speaker's story:** "The full loop: read a sentence, predict the next word, measure the loss with Shannon's cross-entropy, compute the gradients with the chain rule, adjust the parameters with Cauchy's gradient descent, move to the next sentence. GPT-3 did this loop 300 billion times. The same math, the same loop, 300 billion repetitions. That is how it learned to write, reason, and translate."
- **Connection to anchor:** "The AI can now learn. But there is a problem: 'The cat sat on the mat because it was tired.' What does 'it' refer to?"

---

#### SLIDE 17: Inside the LLM -- Where Calculus Lives

- **Title:** Building Block Found: Derivatives, Gradient Descent, Backpropagation
- **The ONE thing:** Show where gradient descent and backpropagation operate in the transformer.
- **Visual:** Left: transformer diagram with the backward training arrows HIGHLIGHTED in red. Forward pass grayed out (shown), backward pass emphasized. Topic 1 (teal) and Topic 2 (blue) components still visible. Right: progress bar (3/5 lit).
- **Speaker's story:** "The forward pass uses linear algebra and probability. The backward pass uses calculus. Every arrow flowing backward through the transformer is the chain rule in action. Cauchy's gradient descent, Linnainmaa's automatic differentiation, Hinton's backpropagation. Three building blocks found."
- **Connection to anchor:** "The AI can represent words, predict, and learn. But it still processes words one at a time. It has no notion of CONTEXT."

---

### TOPIC 4: "How does it understand context?" (6 slides)

**Topic color:** seqIndigo

---

#### SLIDE 18: The Question -- The Problem of "It"

- **Title:** "The cat sat on the mat because IT was ___." What does "it" mean?
- **The ONE thing:** The word "it" could refer to "cat" or "mat." The AI needs to look at the WHOLE sentence to decide.
- **Visual:** The extended sentence with "it" highlighted and two arrows: one to "cat" (thick, strong) and one to "mat" (thin, weak). Question: how does the AI know to look back at "cat"?
- **Speaker's story:** "Here is a problem the first three topics cannot solve. 'The cat sat on the mat because it was tired.' You know 'it' means 'cat.' But how? Because you understand context -- you looked back at the whole sentence. Before 2014, AI could not do this well. Words were processed one at a time, and early words were forgotten."
- **Connection to anchor:** Direct return, extended sentence. Fourth facet.

---

#### SLIDE 19: The History -- Markov, Bahdanau, Vaswani

- **Title:** From Poetry Analysis to "Attention Is All You Need"
- **The ONE thing:** Markov (1906) started sequence modeling. Bahdanau (2014) invented attention. Vaswani (2017) built the transformer.
- **Visual:** Three-panel timeline: (1) Markov, 1906, analyzing Pushkin's poetry -- state diagram with transition probabilities. (2) Bahdanau, 2014, Montreal -- "Why compress everything into one vector? Look back at the whole input." (3) Vaswani et al., 2017, Google -- "Attention Is All You Need," 8 authors, most in their 20s-30s.
- **Speaker's story:** "Markov analyzed Russian poetry to prove a point about probability. His chain model became the ancestor of every language model. But Markov chains forget. RNNs forget. After 50 words, the beginning is gone. Then in 2014, Bahdanau asked: why compress everything into one vector when you can look back at the whole input? That is attention. Three years later, Vaswani and seven colleagues built an entire architecture using ONLY attention. They called the paper 'Attention Is All You Need.' They were right."
- **Connection to anchor:** "Markov started it. Bahdanau cracked the memory problem. Vaswani assembled the machine."

---

#### SLIDE 20: The Mechanism -- Self-Attention

- **Title:** Every Word Looks at Every Other Word
- **The ONE thing:** Self-attention computes a relevance score between every pair of words using the dot product from Topic 1.
- **Visual:** Top: the sentence "The cat sat on the mat because it was tired." Attention heatmap: "it" attends strongly to "cat" (dark), weakly to other words. Below: the Q/K/V pipeline. Each word generates: Q (what am I looking for?), K (what do I contain?), V (what information do I carry?). Attention score = dot product of Q and K. Formula inset: Attention(Q,K,V) = softmax(QK^T/sqrt(d)) V.
- **Speaker's story:** "Each word asks a question (Q). Each word offers a key (K). Self-attention computes the dot product -- that is Gibbs, from Topic 1 -- between every Q and every K. 'It' asks: 'What am I referring to?' 'Cat' answers: 'I am an animate noun.' Their dot product is high. Then the softmax -- Boltzmann, from Topic 2 -- turns these scores into attention weights. The word 'it' now knows it means 'cat.' One equation, and it uses the dot product, softmax, and matrix multiplication you already learned."
- **Connection to anchor:** "Self-attention resolves 'it.' But the transformer has one more trick: it does not know word ORDER."

---

#### SLIDE 21: The Mechanism -- Positional Encoding and the Full Layer

- **Title:** Fourier's Sine Waves Tell the AI Where Each Word Is
- **The ONE thing:** Positional encoding uses Fourier's sine waves (1807) to inject word order. One full transformer layer = attention + feed-forward + add & norm.
- **Visual:** Top: positional encoding -- sine waves at different frequencies, one per position. "Fourier decomposed heat into waves. Vaswani decomposed word position into waves. Same math, 210 years apart." Bottom: one full transformer layer block diagram: Multi-Head Attention -> Add & Norm -> Feed-Forward Network -> Add & Norm. The "x N layers" bracket.
- **Speaker's story:** "The transformer has no built-in sense of word order. To fix this, Vaswani added positional encodings -- sine and cosine functions at different frequencies. This is Fourier's idea from 1807. Same math, 210 years apart. One transformer layer: self-attention (Bahdanau/Vaswani), then a feed-forward network, with two rounds of 'add and normalize.' Stack 96 of these and you have GPT-4."
- **Connection to anchor:** "Every word in 'The cat sat on the ___' now has a position AND context."

---

#### SLIDE 22: THE CLIMAX -- The Full Annotated Transformer

- **Title:** 2,000 Years of Mathematics in One Diagram
- **The ONE thing:** EVERY component of the transformer was invented by someone we have met. Here they all are, annotated.
- **Visual:** Full-width annotated transformer pipeline. EVERY component labeled with its inventor, date, and the TOPIC where the student learned it:
  - Input Embedding (Grassmann 1844, Mikolov 2013) -- Topic 1
  - Positional Encoding (Fourier 1807) -- Topic 4
  - Multi-Head Self-Attention: Q,K,V dot products (Gibbs 1881 -- Topic 1), softmax (Boltzmann 1870s -- Topic 2), matrix mult (Cayley 1858 -- Topic 1)
  - Add & Norm (He 2015, Ba 2016) -- Topic 5 preview
  - Feed-Forward Network (Cybenko 1989) -- Topic 5 preview
  - Output Softmax (Boltzmann) -- Topic 2
  - Training: Cross-Entropy (Shannon 1948 -- Topic 2) + Backprop (Hinton 1986 -- Topic 3) + SGD (Cauchy 1847 -- Topic 3)
- **Speaker's story:** [PAUSE. Let the diagram land.] "Every single piece has a name, a date, and a topic where you learned it. The sine functions come from Fourier in 1807. The dot products from Gibbs in 1881. The softmax from Boltzmann in the 1870s. The training uses Cauchy's gradient descent from 1847 and Hinton's backpropagation from 1986. When you talk to an AI, you are talking to 2,000 years of mathematics, all running at once."
- **Connection to anchor:** "This is the FULL machine that predicts 'mat' from 'The cat sat on the ___.' But two components are labeled 'Topic 5.' We have not explained those yet."

---

#### SLIDE 23: Inside the LLM -- Where Context Lives

- **Title:** Building Block Found: Attention, Self-Attention, Positional Encoding, the Transformer
- **The ONE thing:** The transformer IS the convergence of Topics 1-4. Topic 4 is the architecture itself.
- **Visual:** Left: transformer diagram FULLY colored (Topics 1-4 components in their colors, Topic 5 components still grayed out). Right: progress bar (4/5 lit).
- **Speaker's story:** "Four of five building blocks found. The transformer is not a new invention layered on top of the others -- it IS the combination of all of them. Attention is the dot product from Topic 1 applied to context. Softmax from Topic 2 weights the attention. Backpropagation from Topic 3 trains it. The architecture from Topic 4 wires them together. One question remains: how does it get so good?"
- **Connection to anchor:** "The machine works. But one layer is mediocre. 96 layers are extraordinary. Why?"

---

### TOPIC 5: "How does it get so good?" (5 slides)

**Topic color:** neuronPink (with accentOrange for scaling)

---

#### SLIDE 24: The Question -- The Mystery of Scale

- **Title:** "The cat sat on the ___." One layer is dumb. 96 layers are brilliant. Why?
- **The ONE thing:** The same architecture, made deeper and bigger, produces dramatically better results. Why?
- **Visual:** Left: 1-layer prediction: "the/a/was" (vague, generic). Right: 96-layer prediction: "mat 68%, floor 15%, table 8%" (precise, contextual). The question: what happens between layer 1 and layer 96?
- **Speaker's story:** "We have the complete machine. But there is a mystery. One layer of self-attention barely works. Stack 96 layers, add 175 billion parameters, train on 300 billion tokens -- and suddenly it writes poetry, solves math problems, and translates languages it was barely trained on. Same architecture. Same math. Just bigger. Why does scale work?"
- **Connection to anchor:** Direct return. Fifth and final facet.

---

#### SLIDE 25: The History -- The Neuron, the Crash, the Comeback

- **Title:** 1943: Invention. 1969: Crash. 1986: Comeback.
- **The ONE thing:** The mathematical neuron was invented in 1943, killed in 1969 (one layer was not enough), and revived in 1986 (backpropagation could train many layers).
- **Visual:** Timeline drama arc: (1) McCulloch & Pitts 1943 -- "A neurophysiologist and a teenage runaway invent the mathematical neuron." (2) Rosenblatt 1958 -- "The Perceptron. Press: 'A machine that could think.'" (3) Minsky & Papert 1969 -- "XOR: one layer cannot learn this. The field dies for 17 years." (4) Hinton 1986 -- "Backpropagation (Topic 3!) revives multi-layer networks. The comeback."
- **Speaker's story:** "McCulloch was a neurophysiologist. Pitts was about 20, self-taught, no degree. Their 1943 paper defined the mathematical neuron. Rosenblatt built the Perceptron -- the press said it would think like a human. Then Minsky and Papert proved that a single-layer perceptron cannot learn XOR -- a simple logic function. The field collapsed for 17 years. The AI winter. The solution was right there: add more layers. But nobody knew how to train multiple layers until Hinton showed that backpropagation -- the chain rule from Topic 3 -- could do it."
- **Connection to anchor:** "Multiple layers work. But 96 layers? That needed three more inventions."

---

#### SLIDE 26: The Mechanism -- Depth, Activation, Residuals, Normalization

- **Title:** Three Tricks That Made Deep Networks Possible
- **The ONE thing:** Activation functions add nonlinearity. Residual connections preserve signals. Layer normalization keeps numbers stable. Together they enable 96+ layers.
- **Visual:** Three panels: (1) Activation: without it, 96 layers = 1 layer. ReLU/GELU curves. (2) Residual connections (He, 2015): output = input + layer(input). Signal preserved through skip arrow. (3) Layer norm (Ba, 2016): numbers re-centered and re-scaled at each layer. Bottom: the "Add & Norm" block in the transformer -- "This is He + Ba."
- **Speaker's story:** "Three inventions. Activation functions add nonlinearity -- without them, stacking 100 matrix multiplications is the same as one. Residual connections let the signal flow through without fading -- Kaiming He, 2015. Layer normalization keeps the numbers stable -- Jimmy Ba, 2016. These are the 'Add and Norm' blocks you saw grayed out in the transformer diagram. Now you know what they do and who invented them."
- **Also covers:** Universal approximation theorem (Cybenko, 1989) -- briefly: "Cybenko proved in 1989 that a neural network CAN learn any continuous function. That theorem is the guarantee. These three inventions are how it actually works in practice." Boolean logic and hardware: "And all of this runs on hardware built from Boole's 0s and 1s (1854), on machines Turing imagined (1936), powered by GPUs."
- **Connection to anchor:** "Now we can go deep. The last step: go ENORMOUS."

---

#### SLIDE 27: The Mechanism -- Scaling Laws

- **Title:** Same Math. Just Bigger.
- **The ONE thing:** The transformer from 2017, scaled up, produces LLMs with emergent abilities. The math did not change. The scale did.
- **Visual:** Left: GPT timeline: GPT-1 (117M, 2018) -> GPT-2 (1.5B, 2019) -> GPT-3 (175B, 2020) -> GPT-4 (undisclosed, 2023). Semilog chart showing exponential growth. Right: scaling laws (Kaplan, 2020) -- "Performance scales as a smooth power law with parameters, data, and compute."
- **Speaker's story:** "GPT-1 had 117 million parameters. GPT-3 had 175 billion. Same transformer architecture. Same math. Just 1,500 times larger. And somewhere along the way, these models started doing things nobody programmed: reasoning, writing code, translating languages they barely saw in training. Nobody fully understands why scale works this well. That is an open question."
- **Connection to anchor:** "The machine that predicts 'mat' from 'The cat sat on the ___' is complete."

---

#### SLIDE 28: Inside the LLM -- Where Depth and Scale Live

- **Title:** ALL Building Blocks Found
- **The ONE thing:** The transformer diagram is now FULLY colored. All five questions answered. Every component attributed.
- **Visual:** Left: transformer diagram with ALL components colored in their topic colors:
  - Teal (Topic 1): embeddings, dot products, matrix multiplications
  - Blue (Topic 2): output softmax, cross-entropy loss
  - Red (Topic 3): backward arrows (backpropagation, gradient descent)
  - Indigo (Topic 4): self-attention blocks, positional encoding, the architecture itself
  - Pink (Topic 5): neurons, activation, residuals, layer norm, the "x96" bracket
  Right: progress bar (5/5 lit). All five questions from slide 2, all lit.
- **Speaker's story:** "Five questions. Five building blocks. Every component of the transformer has a name, a date, an inventor, and a topic where you learned why it matters. The diagram that seemed overwhelming is now a map you can read."
- **Connection to anchor:** "Every time you type 'The cat sat on the ___,' this entire machine activates. 2,000 years of mathematics, all running at once."

---

### CLOSING (2 slides)

---

#### SLIDE 29: The Story Is Not Over

- **Title:** Open Questions
- **The ONE thing:** Nobody fully understands why transformers work this well. The story is not over.
- **Visual:** Three "open question" boxes: (1) Why do transformers generalize so well? (2) What are the limits of scaling? (3) What comes after transformers? Below: "Every breakthrough we covered started with someone asking a question nobody else was asking."
- **Speaker's story:** "The transformer is 8 years old. It was built from 2,000 years of math. Nobody fully understands why it works as well as it does. There are open questions everywhere. And the people who answer them might be sitting in this room."
- **Connection to anchor:** The anchor served its purpose. Now the student IS the anchor.

---

#### SLIDE 30: Closing -- One Sentence. One Machine. Your Turn.

- **Title:** 2,000+ Years. One Machine. Your Turn.
- **The ONE thing:** The audience is part of this story.
- **Visual:** Full-bleed aiViolet background (matching slide 1). The anchor sentence one final time: "The cat sat on the ___." Below: "You now know every piece of the machine that answers this question. They all started by following their curiosity. Your turn."
- **Speaker's story:** "Every piece of mathematics we covered today was invented by someone who had no idea it would end up inside an AI. Grassmann was a schoolteacher. Pascal was answering a gambling question. Fourier was studying heat. Boltzmann was studying gas molecules. Markov was analyzing poetry. They followed their curiosity and built the future. Your turn."
- **Connection to anchor:** Final appearance of the anchor. Closure.

---

## BUILDING-BLOCK COVERAGE MAP

Every essential LLM concept is covered. Nothing is left out.

| Concept | Topic # | Slide # | How It Appears |
|---------|---------|---------|----------------|
| **Vectors** | 1 | 3, 4, 5 | Words as lists of numbers; Grassmann 1844 |
| **Matrices** | 1 | 4, 6 | Cayley 1858; neural net layers = matrix mult |
| **Matrix multiplication** | 1 | 6 | Every layer is a matrix multiplication |
| **Dot product** | 1 | 4, 5, 20 | Gibbs 1881; similarity measure; attention scores |
| **High-dimensional spaces** | 1 | 5 | 768-dimensional word vectors |
| **Embeddings / Word2Vec** | 1 | 5, 7 | Mikolov 2013; king-man+woman=queen |
| **Probability** | 2 | 8, 9 | Pascal/Fermat 1654; prediction as probability |
| **Bayes' theorem** | 2 | 9 | Updating beliefs from evidence |
| **Softmax** | 2 | 10, 20 | Boltzmann 1870s; scores -> probabilities |
| **Cross-entropy loss** | 2 | 11 | Shannon 1948; measuring prediction quality |
| **Information theory / Entropy** | 2 | 11 | Shannon; surprise as information |
| **Perplexity** | 2 | 11 | Brief mention as evaluation metric |
| **Derivatives** | 3 | 14, 15 | Newton/Leibniz; computing slopes |
| **Gradient descent** | 3 | 14, 16 | Cauchy 1847; stepping downhill |
| **Chain rule** | 3 | 15 | The factoring-through-layers mechanism |
| **Backpropagation** | 3 | 15, 16 | Linnainmaa 1970; Hinton 1986 |
| **Loss functions** | 3 | 13, 16 | Cross-entropy driving the training loop |
| **Optimization / learning rate** | 3 | 14, 16 | Part of gradient descent recipe |
| **Sequence modeling** | 4 | 19 | Markov 1906; analyzing poetry |
| **RNN / memory problem** | 4 | 19 | Memory fades after ~50 words |
| **Attention** | 4 | 19, 20 | Bahdanau 2014; look back at whole input |
| **Self-attention** | 4 | 20, 22 | Vaswani 2017; every word looks at every word |
| **Query / Key / Value** | 4 | 20 | Q asks, K answers, V carries information |
| **Multi-head attention** | 4 | 21 | Multiple attention patterns in parallel |
| **Positional encoding** | 4 | 21 | Fourier 1807 -> Vaswani 2017; sine waves for position |
| **Transformer architecture** | 4 | 19, 21, 22 | "Attention Is All You Need"; 8 authors |
| **Neurons / artificial neuron** | 5 | 25 | McCulloch & Pitts 1943 |
| **Perceptron / AI winter** | 5 | 25 | Rosenblatt 1958; Minsky/Papert 1969; XOR crash |
| **Activation functions** | 5 | 26 | Sigmoid -> ReLU -> GELU; nonlinearity |
| **Residual connections** | 5 | 26 | He 2015; signal preservation |
| **Layer normalization** | 5 | 26 | Ba 2016; numerical stability |
| **Universal approximation** | 5 | 26 | Cybenko 1989; the guarantee |
| **Boolean logic / hardware** | 5 | 26 | Boole 1854; Turing 1936; the substrate |
| **GPUs / compute** | 5 | 26, 27 | NVIDIA CUDA 2007; the hardware |
| **Scaling laws** | 5 | 27 | Kaplan 2020; power law performance |
| **GPT series** | 5 | 27 | GPT-1 through GPT-4; same arch, more scale |

**Coverage check:** All 20+ concepts from the original requirement are mapped. No concept is orphaned. Every concept connects back to "predicting the next word."

---

## COMPLETE PERSON INDEX

| Person | Dates | Topic | Slide | Contribution |
|--------|-------|-------|-------|-------------|
| Hermann Grassmann | 1844 | 1 | 4 | Vector spaces |
| James Joseph Sylvester | 1850 | 1 | 4 | Named "matrix" |
| Arthur Cayley | 1858 | 1 | 4, 6 | Matrix multiplication |
| J. Willard Gibbs | 1881 | 1 | 4, 5 | Dot product |
| Carl Friedrich Gauss | 1809 | 1 | 6 | Matrix operations |
| Tomas Mikolov | 2013 | 1 | 5 | Word2Vec embeddings |
| Blaise Pascal | 1654 | 2 | 9 | Probability theory |
| Pierre de Fermat | 1654 | 2 | 9 | Probability theory |
| Thomas Bayes | 1763 | 2 | 9 | Bayes' theorem |
| Ludwig Boltzmann | 1870s | 2 | 9, 10 | Softmax formula |
| Claude Shannon | 1948 | 2 | 9, 11 | Information theory, cross-entropy |
| Archimedes | c.250 BCE | 3 | 14 | Proto-calculus (verbal mention) |
| Newton / Leibniz | 1680s | 3 | 14 | The derivative |
| Augustin-Louis Cauchy | 1847 | 3 | 14 | Gradient descent |
| Seppo Linnainmaa | 1970 | 3 | 15 | Automatic differentiation |
| Geoffrey Hinton | 1986 | 3 | 15, 25 | Backpropagation; deep learning comeback |
| David Rumelhart | 1986 | 3 | 15 | Backpropagation paper |
| Andrey Markov | 1906 | 4 | 19 | Sequence modeling |
| Dzmitry Bahdanau | 2014 | 4 | 19, 20 | Attention mechanism |
| Ashish Vaswani | 2017 | 4 | 19, 21 | Transformer, self-attention |
| Joseph Fourier | 1807 | 4 | 21 | Sine waves -> positional encoding |
| Warren McCulloch | 1943 | 5 | 25 | Mathematical neuron |
| Walter Pitts | 1943 | 5 | 25 | Mathematical neuron |
| Frank Rosenblatt | 1958 | 5 | 25 | Perceptron |
| Marvin Minsky | 1969 | 5 | 25 | XOR critique / AI winter |
| Seymour Papert | 1969 | 5 | 25 | XOR critique / AI winter |
| Kaiming He | 2015 | 5 | 26 | Residual connections |
| Jimmy Ba | 2016 | 5 | 26 | Layer normalization |
| George Cybenko | 1989 | 5 | 26 | Universal approximation theorem |
| George Boole | 1854 | 5 | 26 | Boolean algebra / hardware |
| Alan Turing | 1936 | 5 | 26 | Universal computation |
| Jared Kaplan | 2020 | 5 | 27 | Scaling laws |

---

## INTERACTIVE MOMENTS (2 total)

1. **Slide 5 (Topic 1): "King - Man + Woman = ?"** (~2 minutes)
   Students guess. Reveal: queen. Demonstrates word vector arithmetic. "This is not a trick. This is geometry."

2. **Slide 10 (Topic 2): "The cat sat on the ___"** (~2 minutes)
   Quick class poll. Collect answers. Show the AI's softmax distribution alongside the class's guesses. "You and the AI are doing the same thing."

---

## TIMING ESTIMATE

| Section | Slides | Minutes | Notes |
|---------|--------|---------|-------|
| Opening (1-2) | 2 | 3 | Title + anchor introduction |
| Topic 1 (3-7) | 5 | 8 | Includes interactive moment 1 (~2 min) |
| Topic 2 (8-12) | 5 | 8 | Includes interactive moment 2 (~2 min) |
| Topic 3 (13-17) | 5 | 7 | The training loop |
| Topic 4 (18-23) | 6 | 10 | Includes the climax (slide 22, full diagram) |
| Topic 5 (24-28) | 5 | 7 | Neuron history + scaling |
| Closing (29-30) | 2 | 3 | Open questions + final |
| **Total** | **30** | **~46 min** | **~1.5 min/slide avg, includes ~4 min interactive** |

---

## PROGRESS BAR DESIGN

A visual progress bar appears on each "Inside the LLM" slide (slides 7, 12, 17, 23, 28).

| Slide | Progress | State |
|-------|----------|-------|
| 7 | 1/5 | Topic 1 (teal) lit |
| 12 | 2/5 | Topics 1-2 (teal, blue) lit |
| 17 | 3/5 | Topics 1-3 (teal, blue, red) lit |
| 23 | 4/5 | Topics 1-4 (teal, blue, red, indigo) lit |
| 28 | 5/5 | ALL lit (teal, blue, red, indigo, pink) |

Each progress bar also shows the five-question list from slide 2 with answered questions lit in their topic color.

---

## THE TRANSFORMER DIAGRAM: PROGRESSIVE REVEAL

The SAME transformer diagram appears 6 times, progressively colored:

| Slide | What's colored | What's grayed |
|-------|---------------|---------------|
| 7 (Topic 1) | Embeddings, dot products, matrix mults (teal) | Everything else |
| 12 (Topic 2) | + Output softmax, cross-entropy (blue) | Attention, FFN, Add&Norm, backward |
| 17 (Topic 3) | + Backward training arrows (red) | Attention, FFN, Add&Norm |
| 22 (Climax) | EVERYTHING labeled with inventor + topic | Nothing grayed |
| 23 (Topic 4) | Topics 1-4 colored | Topic 5 components grayed |
| 28 (Topic 5) | ALL colored | Nothing grayed |

This progressive reveal is a powerful teaching device: the student sees the SAME diagram grow from mostly-gray to fully-colored across the lecture, building understanding incrementally.

---

## BEAMER IMPLEMENTATION NOTES

- **Base on existing `llm-30.tex` preamble:** Reuse theme, colors, fonts, packages, custom commands (personbox, insightbox, llmconnection). The convergencebar macro should be adapted from 10-node to 5-node.
- **New macro needed:** `\topicquestion{N}{color}{question}` -- renders the recurring "The cat sat on the ___" anchor with the topic's sub-question highlighted in the topic color.
- **New macro needed:** `\progressbar{N}` -- a 5-block progress bar (one per topic) that lights blocks 1..N.
- **New macro needed:** `\transformerdiagram{topics-lit}` -- the transformer diagram with progressive coloring. This is the most complex TikZ element; define once, parameterize which topics are colored.
- **Section colors:** Reuse `linalgTeal`, `probBlue`, `calculusRed`, `seqIndigo`, `neuronPink` from existing file.
- **Frame structure:** Each topic's first slide uses `\topicquestion`. Each topic's last slide uses `\progressbar` + simplified `\transformerdiagram`.
- **Speaker notes:** Use `\note{}` for speaker stories (consistent with existing file).
- **Output file:** `llm-5topics.tex` in the project root.

---

## COMMIT STRATEGY

1. **Commit 1:** Create `llm-5topics.tex` with preamble, custom macros, and opening slides (1-2).
2. **Commit 2:** Topic 1 slides (3-7) with TikZ diagrams for word vectors and embedding visualization.
3. **Commit 3:** Topic 2 slides (8-12) with softmax pipeline and cross-entropy visualizations.
4. **Commit 4:** Topic 3 slides (13-17) with gradient descent landscape and backpropagation flow.
5. **Commit 5:** Topic 4 slides (18-23) with attention heatmap, Q/K/V diagram, and the CLIMAX full transformer diagram.
6. **Commit 6:** Topic 5 slides (24-28) with neuron history timeline and scaling chart.
7. **Commit 7:** Closing slides (29-30) and final polish.
8. **Commit 8:** Compile verification, fix any LaTeX errors.

---

## SUCCESS CRITERIA

- [ ] Exactly 28-30 slides, compiles as standalone Beamer LaTeX
- [ ] 5 topics, each starting from "The cat sat on the ___"
- [ ] Every topic follows the same 5-6 slide pattern (question, history, mechanism, inside the LLM)
- [ ] ALL building-block concepts from the coverage map appear somewhere
- [ ] At least 2 interactive moments
- [ ] Progressive transformer diagram (gray -> fully colored)
- [ ] Progress bar on each "Inside the LLM" slide
- [ ] Speaker notes for every slide
- [ ] Duration ~45 minutes
- [ ] Every formula appears conceptual-first, formal in small inset
- [ ] No concept is introduced without first answering "why do I need this?"

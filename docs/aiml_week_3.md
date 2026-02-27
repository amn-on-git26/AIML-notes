# From Text To Attention 

### How Transformers See Language
----

Part 1:

Connecting conceptual foundations to mechanical implementations.

----
# Bridging the Knowledge Gap
---


Filling the gaps in our understanding of Neural Networks
----

### What We Know:

1. Neural networks process numbers.

2. Models learn by adjusting weights

3. Attention focuses on relevant words.

----

### The missing pieces:

* How does text transform into numbers?

* What does the model actually "see"?

* How does attention work mechanically?

  ---

# The Fundamental Challenge 
---

Neural networks only understands NUMBERS.

Human language is TEXT.

### We need a translation layer that converts text into numbers while preventing semantic realtionship.



----

** So....HOW?

----



# The Character Level Approach
---

#### Idea 1. One number per character

The most basic way to achieve numerical representation is to assign a unique integer to every individual character in the alphabet.

While simple, this appraoch operates at the smallest possible unit of language,ignoring words and concepts entirely.
---

<img width="478" height="405" alt="Screenshot 2026-02-21 112032" src="https://github.com/user-attachments/assets/7d932298-94fb-4013-8bec-aaf2c750bcb1" />

---

# Why Character level model struggle 
---

The hidden cost of extreme granularity

<img width="1080" height="483" alt="Screenshot 2026-02-21 112218" src="https://github.com/user-attachments/assets/c5dca4da-113d-4bc7-86ba-75a3f2099611" />

----

# The Word-Level Approach
---

#### Idea 2: Assigning one unique number to every whole word.

<img width="1078" height="420" alt="Screenshot 2026-02-21 112330" src="https://github.com/user-attachments/assets/93974e77-db5d-4710-9164-c881b6beb848" />

-----

# The Vocabulary Explosion

---
Scaling challenges of word-level models.
---

<img width="1092" height="428" alt="Screenshot 2026-02-21 112508" src="https://github.com/user-attachments/assets/0dec8667-76e1-40e3-9f2e-c614c272f613" />

----

# The Subword Solution
---

Finding the "Goldilocks" Balance characters and words.
---

<img width="1146" height="462" alt="Screenshot 2026-02-21 112606" src="https://github.com/user-attachments/assets/2b69c1aa-d50a-4f93-806d-f10d35328196" />


----

# Byte Pair Encoding (BPE)
----

Algorithms construction of modern tokenizers.

---

<img width="1096" height="473" alt="Screenshot 2026-02-21 112705" src="https://github.com/user-attachments/assets/a3670b7b-84a4-4204-b51d-e0be2ee6243f" />

----

# Tokenization In modern practice
---

<img width="1111" height="350" alt="Screenshot 2026-02-21 112811" src="https://github.com/user-attachments/assets/6919d4a8-e88b-4c22-a177-26909f4355da" />

----


# WHY TOKENIZATION MATTERS
----
The practical implications of how models "see" text
----

### Operational Impact:-

##### Context Limits:
----

GPT-4's 128K limit refers to tokens, not words. In English, this is roughly 1.3
tokens per word, but code can be much higher.
-----

##### Financial Cost:

API billing is calculated based on token counts, not character counts. Efficient
prompting requires understanding token density.

------

### Model Behavior:-

##### Logical Failures:
-----
Strange failures in counting letters or reversing words often stem from the model
seeing subword units rather than individual characters.
-----

##### Language Equity:
-----

Different languages require different numbers of tokens to express the same
concept, affecting both cost and performance globally. 

-----


# Summary: The Model's "EYES"
------

Tokenization as the foundation of transformer processing
------

<img width="1128" height="493" alt="Screenshot 2026-02-21 113226" src="https://github.com/user-attachments/assets/e4fbf5c1-abc9-4a94-9025-c06004cecf52" />

--------

# From Arbitary IDs to Meaning 
-----

#### Moving beyond simple integer labels .
-----

<img width="1118" height="380" alt="Screenshot 2026-02-21 113418" src="https://github.com/user-attachments/assets/0ff0925d-844c-49f4-bf9b-a3ea5cb405e3" />

----

# The Concept of Embeddings
----

Representing tokens as points in high dimensional space.


<img width="1143" height="480" alt="Screenshot 2026-02-24 115608" src="https://github.com/user-attachments/assets/01ac09fd-f57b-4360-a6a0-c9a13fb92825" />

----

# Visualizing Semantic Space
----

How models organize concepts across dimensions.
----

### Clustering :

----
Related Concepts( e.g., royalty,gender,animals) naturally group together in the high- dimensional vector space.
----

### Emergent Properties :

----
Dimensions like "gender" or "royalty" emerge automatically during trainnig without manual labelling.

----

### Semantic Navigation :
----

The mathematical "distance" between points represents the semantic similiarity of the tokens.

---

<img width="511" height="503" alt="Screenshot 2026-02-24 120020" src="https://github.com/user-attachments/assets/2fa7c37f-0851-4919-97dd-ef37f6cff859" />

----

# Semantic Vector Arithmetic 
---

Mathematical logic embedded in language.

------

### Directional Meaning:
----
The main->woman vector mirrors king->queen.
----

### Relational Encoding :
----

Embeddings encode relations as consistent offsets.
----

### Universal Patterns :
----

These offsets recur across large vocabularies.

<img width="509" height="146" alt="Screenshot 2026-02-24 120337" src="https://github.com/user-attachments/assets/5b10b364-378b-42d4-bb07-ce885d15db80" />

<img width="569" height="264" alt="Screenshot 2026-02-24 120332" src="https://github.com/user-attachments/assets/24abcf09-069d-4d16-98f9-6d563aaf0f3e" />

----

# Embeddings in the Pipeline
---
How tokens transform into dense vectors.

---

### The Lookup Table
-----

Each token ID acts as an index to a specific row in the embedding
matrix. This is a simple, fast lookup operation.

The result is a 768-dimensional vector (for base models) that represents
the token's core semantic profile.

<img width="516" height="220" alt="Screenshot 2026-02-24 120644" src="https://github.com/user-attachments/assets/14a1eac5-1435-44ca-b285-97db92d0ad58" />

-----

### Information Density
-----
A single vector packs multiple layers of semantic information, capturing
nuance that a single integer ID never could.

##### The "Raw" Starting Point
-----

This vector is the isolated representation of the word. It contains the
general meaning of the token before any context from the surrounding
sentence is applied.

---
# Summary: Embeddings
----
Converting discrete tokens into meaningful continuous space.

### Foundational Layer
Every transformer starts by looking up these pre-trained meanings. It is the
bedrock of all subsequent processing.

### The Limitation
Embeddings are "bag-of-words" by default. They represent isolated meaning
but ignore the order of words.

#### Next: Solving the problem of sequence and word order

<img width="485" height="471" alt="Screenshot 2026-02-24 120736" src="https://github.com/user-attachments/assets/d82e31ee-8ffa-4241-a3ef-ab0ab9c69dfa" />

----

# The Problem of Sequence
-----
Attention is "bag-of-words" by default.

### Order Neutrality

* "The dog bit the man"
        vs.
* "The man bit the dog"

Without extra information, attention treats these two sentences
identically. The mathematical operations don't care about position.

This is known as permutation invariance—the model sees a set of words,
not a sequence.

### The Loss of Logic:

In human language, position is often the primary driver of meaning.
Order determines who did what to whom.

#### The Requirement

We must find a way to inject "where" a word is into "what" a word is.
We need to make the model aware of the dimension of time in language.

-----
# Positional Encoding
-----
Adding a sense of time and order to the model

### Injecting Sequence

Transformers process tokens in parallel, so we add tags to show where each token
sits in the sequence.
-----

### Vector Addition
A small positional vector is added to each embedding, encoding both meaning and
position.
----
### Spatial Awareness
This helps the model tell apart different word orders (e.g. who did what) using
position tags.

<img width="491" height="314" alt="Screenshot 2026-02-24 121030" src="https://github.com/user-attachments/assets/9b51d8e7-b6ba-4de5-be73-ba468367689c" />

------
# How Positional Patterns Work
----
Using mathematical waves to encode location

### Periodic Functions

We use sine and cosine waves of varying frequencies. Each dimension of the
embedding follows a different wave.

### Unique Fingerprint

Every position in the sequence (0, 1, 2...) gets a unique combination of values,
creating a "fingerprint" for that location.

### Relative Distance

The model can calculate the relative distance between words because the waves are
mathematically related.

### Generalization

This method allows the model to handle sequences longer than those it saw during
training.

<img width="469" height="499" alt="Screenshot 2026-02-24 121128" src="https://github.com/user-attachments/assets/7adc979e-0964-40a2-a147-0e868b70cabe" />

---

# Why Sine Waves?
---
The logic behind the original transformer's choice
---

### Mathematical Advantages

#### Relative Position
For any fixed offset k, the position p+k can be represented as a linear function of
position p. This allows the model to learn to attend by relative position easily.

#### Generalization
Since the waves are continuous, the model can extrapolate and handle longer
sequences than those it saw during training.
-----
### Efficiency & Logic
------

#### No Learned Parameters

Unlike other methods, sinusoidal encoding doesn't require extra parameters to
learn. The patterns are fixed and pre-calculated.

#### Unique Multi-Scale Patterns
By using multiple frequencies, the model creates a unique fingerprint for every
single position in a very high-dimensional space.
---

# The Pipeline So Far
From raw text to context-ready vectors
----
### Step 1
##### Tokenization
Breaking raw text into discrete subword units (IDs).

### Step 2
###### Embedding
Converting arbitrary IDs into dense semantic vectors.

### Step 3
##### Positional Encoding
Injecting sequence awareness via mathematical wave patterns.

<img width="522" height="370" alt="Screenshot 2026-02-24 121337" src="https://github.com/user-attachments/assets/2f1d4e18-9533-4e3c-b4d4-2fb293ce0c16" />

---
# Summary: Positional Encoding
------
Injecting the dimension of time into language



### Order-Dependent Meaning
Preserves the nuances of language where position determines roles (e.g.,
subject vs. object).

### The Next Step
Now that each token knows "WHAT" it is and "WHERE" it is, we can move to the
core of the transformer.

<img width="457" height="417" alt="Screenshot 2026-02-24 121430" src="https://github.com/user-attachments/assets/da01f844-c1fe-49b5-9223-9aa6ef021431" />



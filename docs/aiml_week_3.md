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




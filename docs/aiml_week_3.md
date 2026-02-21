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





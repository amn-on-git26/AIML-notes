# ** Neural Network from Scratch **

-> How machine actually learn 
---

<img width="463" height="299" alt="Screenshot 2026-02-20 092603" src="https://github.com/user-attachments/assets/b695a8d9-d622-4d49-a144-b102128dd272" />

---

## From rules to patterns: A Quick Recap 
---

### Traditional Programming

#### Rules don't scale:

Humans cannnot write rules for every possible scenario in complex tasks.

### Rigid Logic:

Systems fail when encountering data that doesn't fit predefined rules.

### Machine Learning
---

#### Pattern Discovery: 

Finding Consistent mathematical relationships within large datasets.

#### The Goal:
---

Understanding the fundamental mechanics of how this discovery happens.

----

# ** The Simplest Prediction Problem ** 
---

Neural Networks solve the same problems we do intuitively. Consider the relationship between hiuse size and price.
----
<img width="1078" height="375" alt="Screenshot 2026-02-20 093228" src="https://github.com/user-attachments/assets/255480c9-c72f-4b94-927a-562af3079992" />

----
### The Challenge: 

How do we teach a machine to find a mathematical relationship( e.g., $200/sq ft) automatically?

----


# ** Machine Learning in One Sentence **
----

Training is a simple, iterative loop of guessing and correcting.


## 01.

#### Start with a guess:

Initialize with random values.

## 02.

#### Measure error:

How far is the guess from the truth?

## 03.

#### Adjust:

Modify the guess to be slightly less wrong.


## 04.

#### Repeat:

Do this millions of times until error is minimized.
----


<img width="559" height="417" alt="Screenshot 2026-02-20 093712" src="https://github.com/user-attachments/assets/dd517cbf-6f48-4eec-901e-3d8fa2b98ca6" />

---
#### Explaination Here 

(https://chatgpt.com/share/6997de5c-3180-8010-a60b-0d2cd9a51d46)

---

# ** The NEURON: A Tiny Decision Maker **


The building block of AI is a simple mathematical function,not a biological mystery.
It takes numbers in,performs basic arithmetic, and outputs a signal.
---

<img width="1063" height="363" alt="Screenshot 2026-02-20 094124" src="https://github.com/user-attachments/assets/27158558-49b7-4333-b41e-e8f1009aebc4" />

---


# ** Anatomy of a Neuron **
---

## Neuron

-> An artificial neuron is the smallest decision-making unit inside a neural network.
It's inspired by biological brain neurons, but implements with maths.

Think of it like a mini calculator that:

- receives inputs

- Weighs their importance

- processes them

- outputs a signal

---

### Things to keep in mind when talking about the anatomy of neuron

1. Input

2. Weights

3. Bias(b)

4. Summation (Linear Combiantion)

5. Activation Function(Brain of the Neuron)

6. Output

Read the overview here 

(https://chatgpt.com/share/6997de5c-3180-8010-a60b-0d2cd9a51d46)


## Formula to remember: output = activation(Σ (w)i(x)i + b)

----

** Why do we need Activation Functions **
---

<img width="1114" height="871" alt="Screenshot 2026-02-20 095535" src="https://github.com/user-attachments/assets/fb80123d-17b9-4a13-bf55-57e729bebbc6" />


Activation functions are one of the most important parts of a neural network. Without them, deep learning would barely work.



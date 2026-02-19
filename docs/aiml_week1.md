**# Knowledge**

-There are two types of Knowledge:
1.Explicit Knowledge
2.Implicit Knowledge

---

**# Intelligence**

-Intelligence is the abolity to achieve goals in a wide range of situations.

---

**# AI**

## Stands for Artificial Intelligence

-Making machines do things that would requires intelligence if a human did them.
---
### Examples

:1.Recognizing faces.

2.Understanding Languages

3.Playing chess

4.Driving a car
---
**#Attempt 1: Write the rules**

"If the email contains 'free money"-> spam"

"if temperature > 100F-> fever"

"If the chess piece can move to square and square has enemy piece->capture"

## The is called "Expert Systems" or "Rule Based AI"

** The problem with Rules  **

-How would you write rules for tasks that humans do intuitively?

# Recognizing a Face:

How would you define the exact distance between eyes or the curve of a nose for every possible angle and lighting?

# Understanding Sarcasm:

"Oh. Great." Does it mean something is good,or is it a complaint?Rules can't easily capture tone and context.

# Decoding idioms:

"It's raining cats and dogs." A rule-based system might loook for falling animal instead of understanding the metaphor.
---
**Attempt #2: Let machines learn:**

-Instead of writing rules... Show the machine thousnad of examples and let it figure out the patterns.

This is called Machine Learning(ML)

**How Machine Learning Works(INtuitively)**

01.Show the machine many examples

02.Machine makes a guess

03.Tell it if was right or wrong

04.Machine adjusts itself slightly

05.Repeat millions of times

---

# The Analogy:

"Like a child learning by trial and error"

**AI vs ML:**

<img width="1181" height="628" alt="Screenshot 2026-02-19 100456" src="https://github.com/user-attachments/assets/881264c4-29ec-44ae-ac04-2d7e471dea58" />


---
**Early ML: Modest Successes:**

# What Worked?

-Spam filters got better

-Recommmendations systems(Netflix,Amazon)

-Basic image recognition

# The Bottleneck:

-Couldn't have a conversation

-Couldn't understand a paragraph

-Couldn't recognize objects as well as a toddler
---
**Why Early ML was limited**

# Bottleneck 01:Not Enough data

- Machine Learning requires massive amounts of exampples to learn patterns effectively.

- Where do you get millions of labelled examples?

-The internet was in its infancy.


# Bottleneck 02

-Learning from data requires intense mathematical calculations.

-Computers were too slow for deep training

-Training on millions of examples would take years

---
**AI Winters:When Hope Died(Twice)

# 1970s Winter

## The first Collapse

-Researchers promised human-level AI in 20 years.When they failed to deleiver, funding dried up 
and internet vanished.

 ## 1980s-90s Winter
 
 -Expert Systems were supposed to revolutionize bussiness,but they were too brittle for the real world.Funding vanished again.

 ### "The field become joke.Saying you worked on AI was career suicide."

 ---
 **WHY AI EXPLODED(AFTER 2012)**
 
 # 01.Data
 
 ## The internet
 
 -Massive datasets of text images,and video became available for the first time.
 
 # 02.Compute
 
 ## GPUs
 
 -Graphics cards,built for gaming,turned out to be perfect for the math ML needs.
 
 # 03.Algorithm
 
 ## Deep Learning
 
 -Researchers finaaly cracked how to train much deeper and more complex neural networks.

 ---
 **Why Language is Hard for Computers**
 
 # "Fast tracking the AI Course" and "Fast -tracking the course of AI."

 ** NLP ATTEMPT #1: The Dictionary Approach **

  Apple

  1.The round fruit of a tree of the rose family,which typically has thin red or green skin and crisp flesh.

  ### The problem

  -A dictionary definition isn't enough for real world language

  "Apple" is also a trillion dollar company

   "Apple" is a famous record label.

   Context changes everything.


   ** NLP ATTEMPT #2 : Statistical Patterns **

   If 'New' is followed by 'York' -> City."

   This approach powered Google Translate for nearly a decade.

   ### The Problem:

   Pattern Matching != Understanding

   The machine could provide the next word based on frequency,but it had no concept of what the words actually meant.

---

   **THE BREAKTHROUGH : Words as Numbers **
   ---

   
   <img width="963" height="121" alt="Screenshot 2026-02-19 153531" src="https://github.com/user-attachments/assets/4ca3291c-aa20-437b-b242-630b26f5dcc9" />

---

Computers don't understand words. They understand numbers. The challenge is : How do we turn a word into a list of numbers that captures its meaning?
---

** Word Embeddings (The "Secret Sauce") **

How do we turn a word like "Apple" into a number that captures its meaning?

Instead of one number, we give each word a list of numbers( a vector).
---
<img width="714" height="571" alt="Screenshot 2026-02-19 153828" src="https://github.com/user-attachments/assets/fa5c374e-3433-48a5-acf0-9e86f24fc6c3" />

 ---

 ** Dimensions of Meaning **
 <img width="1135" height="313" alt="Screenshot 2026-02-19 153915" src="https://github.com/user-attachments/assets/c6910f24-47ad-4fc3-9743-edcdd629983f" />

---

"King" and "Queen" have similiar numbers for royalty but vastly different values for gender.

This is how machines represent concepts as data.

---

** Words as Positions in Space **
---
<img width="1182" height="364" alt="Screenshot 2026-02-19 154133" src="https://github.com/user-attachments/assets/71e5d72d-4375-45ce-925c-9aa14ed03892" />

---

If a word is a list of numbers.It's point on a map. Similiar words are close together, while different words are far apart.
---

** Visualizing Words Embeddings **

-Similiar words are placed close together in a multi-dimensional space.Proximity indicates shared meaning.
---
<img width="878" height="686" alt="Screenshot 2026-02-19 154436" src="https://github.com/user-attachments/assets/8932ca48-4417-4f22-a4f0-53c896c909b8" />

---

** The magic of Embeddings-- Word Math ** 

King - Man + Woman = Queen 

Paris - France + Italy = Rome

Walking-Walk + Swim = Swimming

---

**Can Embeddings Solve Our Earlier Problems? **

" I went to the bank to deposit cash."

"I sat on the bank of the river."
---

## The Problem: In basic word embeddings, each word has exactly one position in space.

### The model can't distinguish between a financial institutionn and a riverbank because it doesn't look at the surrounding words.

---

**NLP Attempt #4: Sequence Models(RNNs) **
---
##Idea:

Process the sentence one word at a time,building up understanding as you go.
---
<img width="1149" height="336" alt="Screenshot 2026-02-19 155029" src="https://github.com/user-attachments/assets/ba4c5bff-17de-46b9-aba0-7c3c69182e01" />

---
# The Problem: Forgetting
---

#### Long-Range Dependency Failure

<img width="1250" height="248" alt="Screenshot 2026-02-19 155141" src="https://github.com/user-attachments/assets/f796ae1e-5b7f-4410-bbba-29cf52b34ba5" />

---

By the time a sequence model reaches "was", it has often forgotten the subject at the begginning.

RNNs struggle with long sentences because they process information lineraly and have limited memory capacity.

---

** The Stage Is Set(around 2017)**

### What we had

1.Word Embeddings

2.Sequence Models(RNNs)

3.Tons of Internet data

4.Powerful GPUs
---
<img width="620" height="409" alt="Screenshot 2026-02-19 155513" src="https://github.com/user-attachments/assets/959c7599-1ebb-4a6a-9853-7aae32437844" />

---

** The Transfer Idea **

### The Old Way

## Sequential 

Process words one by one,like reading a book from start to finish.

###  The New Way

## Simultaneous

Look at every word in the sentence at the same time.

<img width="646" height="237" alt="Screenshot 2026-02-19 155811" src="https://github.com/user-attachments/assets/1bc8b62d-4ab8-4ea8-ae3e-7f605cc1ea1d" />

---

** Attention in Action **
---
<img width="1242" height="304" alt="Screenshot 2026-02-19 155850" src="https://github.com/user-attachments/assets/9edd3fa9-5210-4c8f-8f72-576c6f54450e" />

---

When the model looks at word "it", the attention mechanisms tells it to pay the most attention to "animal".

---

** Same Structure,Different Attention **
---

<img width="1084" height="405" alt="Screenshot 2026-02-19 160024" src="https://github.com/user-attachments/assets/c6aa1b65-5b46-412c-a0a4-d27beaf7e80f" />

---
By Changing just one word(tired vs wide), the model's attention shifts,correctly identifying what "it" refers to in each context.

---

** Why Attention is Powerful **
---
<img width="1395" height="391" alt="Screenshot 2026-02-19 160212" src="https://github.com/user-attachments/assets/127d20b8-0cf3-4061-a3ab-63a392846b26" />

---

** THE TRANSFORMER **
---

An Artitecture built entirely on the mechanism of attention.

<img width="1248" height="165" alt="Screenshot 2026-02-19 160313" src="https://github.com/user-attachments/assets/3f96f08a-c124-4363-b1ec-7084c871043d" />

----

** How ChatGPT Works(Simplified)

<img width="1368" height="425" alt="Screenshot 2026-02-19 160410" src="https://github.com/user-attachments/assets/10c0b0cd-8379-420b-a83a-c6e8cf8c2a7a" />

----

** WHY "PRDICT THE NEXT WORD" CREATES UNDERSTANDING **

## Grammer & Syntax:

Predicting the next word requires the model to internalize language structure and rules.

## Factual Knowledge:

Correct predictions rely on learned factual relations between concepts.

## Logic & Reasoning:

Following a chain of reasoning lets the model anticipate the appropriate continuation.

---

** How It Generates Text **
---
<img width="691" height="325" alt="Screenshot 2026-02-19 160829" src="https://github.com/user-attachments/assets/1de7dbd0-144b-4fa6-b766-0cd5f8a0dd09" />

---

Generation is an iterative loop. Each Predicted Word is added back to the input,and the model predicts the next word based on the updated context.

----

<img width="1428" height="1408" alt="Screenshot 2026-02-19 161005" src="https://github.com/user-attachments/assets/e7984240-5ec0-4811-a15b-3ae9745fd203" />

---

** Foundational Models **

### The Old Paradigm 

# Task- Specific AI

1. Model A: Translation

2. Model B:Summarization

3. Model C: Sentiment Analysis
---

### The New Paradigm
---

# General-Purpose AI

One massive model trained on everything,capable of performing any language task through prompting.

---

## The "Foundation" is the base knowledge. We no longer build tools from scratch; we built on the top of these giants.
---

<img width="1373" height="620" alt="Screenshot 2026-02-19 161406" src="https://github.com/user-attachments/assets/35c84e24-f9de-45bb-a23b-a2356700d95e" />





[LLM VISUALIZATIION}(https://bbycroft.net/llm )



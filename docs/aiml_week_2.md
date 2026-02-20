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

<img width="1124" height="595" alt="Screenshot 2026-02-20 095541" src="https://github.com/user-attachments/assets/029c4c72-b620-4014-9949-1605f0f10a2d" />

<img width="1125" height="757" alt="Screenshot 2026-02-20 095553" src="https://github.com/user-attachments/assets/718e801f-9886-4802-8de7-76d64e497435" />

<img width="1111" height="783" alt="Screenshot 2026-02-20 095546" src="https://github.com/user-attachments/assets/47ec3359-d292-4870-9820-1f217f2b4d1b" />

---
Activation functions are one of the most important parts of a neural network. Without them, deep learning would barely work.
---

** 🧠 1. The Core Reason: Adding Non-Linearity ** 
---

A neuron first computes:

## z = w1x1 + w2x2 + ... + b

This is just a linear math(a striaght line)

->If we stack many layers without activation functions.

The whole deep network becomes equivalent to one single linear layer.

Meaning:

1. No complex learning

2. No deep intelligence

3. No pattern understanding
----

Activation functions introduce:

1. Curves instead of straight lines

2. Complex decision boundaries

3. Real learning capability
---

📌 Real-Life Example

Imagine trying to separate:

1. Cats vs Dogs

2. Fraud vs Normal transactions

3. Faces vs Non-faces

These patterns are not linear.

Without activation functions, the model can only draw a straight line to separate data — which fails for real-world problems.

-----

** 🔥 2. They Help Neurons Decide “Should I Fire?” **
---

Activation functions act like a decision switch.

They transform raw numbers into meaningful sugnals:

* Small iuput -> maybe ignore

* Large Inputs -> string signals

### Examples:

* Real ignores negative values.

* Sigmoid converts numbers into probabilities

So instead of just passig numbers forward, neurons become selective.

----

** 🧩 3. They Make Deep Networks Powerful ** 

Why do we build many layers?

because each layer learns higher level features:

Edges → Shapes → Objects → Meaning


Activation functions allow each layer to learn new transformaions, not just repeat the same linear math.

Without activation:

Layer1 + Layer2 + Layer3 = One linear transformation

Which defeats the purpose of deep learning.

----

📉 4. They Help With Gradient Flow During Training

During Backpropagation:

* Gradient flow through activation functions.

* Good Activations help learning stay stable.

### Examples:

* ReLU helps avoid slow learning (vanishing gradients)

* Sigmoid sometimes causes gradients to shrink

SO,activations are also crucial for efficient tranining.

---

** ⚙️ 5. What Happens If We Remove Activation Functions? **

Imagine a deep network:

Input → Linear → Linear → Linear → Output

Mathematically this becomes:

Output = W * Input


Just one big matrix multiplication.

-> No matter how deep you go- the model stays simple.

That's why activation functions are mandatory.
---

** ⭐ 6. Quick Intuition Summary ** 

Activation functions are needed because they:

1. Add non-linaerlity

2. Enable complex pattern learning

3. Act like neuron decision switches

4. Make deep networks meaningful

5. Help gradients flow during training

----


** NOTE : Activation functions introduce non-linearity into neural networks, allowing them to learn complex patterns instead of behaving like a simple linear model **

--- 

Additional : ** ReLU: **  ReLU stands for Rectified Linear Unit — one of the most commonly used activation functions in deep learning.

---

 ** ⚙️ 1. Definition (Simple Math) ** 
------
The ReLU function is:

----

ReLU(x) = max(0, x)

----

### Meaning:

1. If input is negative → output = 0

2. If input is positive → output = same value

#### Examples:

* ReLU(-5) = 0

* ReLU(3)  = 3

* ReLU(0.7)= 0.7

So it basically cuts off negative values.

-----

** 🧠 2. Intuition — What Does ReLU Do? ** 

-----

Think of ReLU like a gate:

* Negative signals → ignored

* Positive signals → allowed to pass

This helps neurons become selective about what information moves forward.

---

Real-life analogy:

A motion sensor light — it turns ON only when enough movement is detected.

---

📈 3. Why ReLU Became So Popular

---

Before ReLU, functions like sigmoid and tanh were common.

But they had problems:

❌ Slow training
❌ Vanishing gradients (learning stops in deep layers)

ReLU solved many issues:

✅ Faster computation (no complex math)
✅ Keeps gradients strong
✅ Helps deep networks learn efficiently

That’s why most modern CNNs and deep models use ReLU in hidden layers.

----

 ** 🧩 4. How ReLU Helps Learning (Key Insight) **

---

Without activation functions, networks are linear.

ReLU introduces non-linearity, which allows:

* Learning complex patterns

* Detecting edges, shapes, objects

* Creating deep representations

Even though ReLU looks simple, it makes deep learning powerful.

---


** ⚠️ 5. Downsides of ReLU (Important)  ** 

----

ReLU is not perfect.

❌ Dying ReLU Problem

If neuron outputs become negative for a long time:

---
Gradient = 0
----

The neuron may stop learning completely.

Solutions:

* Leaky ReLU

* Parametric ReLU

* GELU (used in transformers)

<img width="997" height="492" alt="Screenshot 2026-02-20 112708" src="https://github.com/user-attachments/assets/8d294893-a8d8-43b0-b2e6-9494ea97f2ff" />



------

** The Loss Function **

---

## Loss = A single number measuring how wrong we are

## Lower Loss : Better predictions

## Training Goal : Minimizze loss


# Mean squared Error(MSE):

----
L = (1/n) Σ(prediction - target)^2

----

- Squares make all errors positive
- Big errors penalized more than small errors
- Good for regression tasks

Example:
Predicted: $350,000
Actual: $400,000
Error: $50,000
Squared: 2,500,000,000

-----

Backpropagation: Assigning Blame
---

# The Chain of responsibility

## The Question:

"The prediction was wrong. Which specific weights are responsible
for this error?"

## The Flow: 

Error signals travel backward from the output layer through the hidden
layers to the input.


## Adjustment: 

Each weight is adjusted proportionally to its contribution to the final
mistake.


<img width="467" height="190" alt="Screenshot 2026-02-20 113142" src="https://github.com/user-attachments/assets/9b858aa4-fc4c-427b-8dfd-5061cd9db832" />

<img width="1194" height="677" alt="Screenshot 2026-02-20 113157" src="https://github.com/user-attachments/assets/f912a8ac-31ea-4130-8668-8b74e43473f9" />


Explanation here: https://chatgpt.com/share/6997f9dd-e610-8010-846f-bff5da87eadf
-----
** Gradient Descent : Finding the valley **
---

## The analogy:

->Imagine you are blindfolded on a hilly landscape. Your
goal is to reach the lowest valley.

## The Landscape:

The "Loss Surface" represents all possible errors the
model can make.

## The Gradient :

The slope under your feet. It tells you which direction is
"down" for the loss.

---

## The Stratergy:

#### Step Downhill: 

Feel the slope and take a step in the direction that
reduces the loss.

#### Iterative Progress:

Repeat the process, taking step after step until you
reach the bottom.

#### The Goal:

Reach the global minimum—the point where the model's
error is as low as possible.

-----

** The TRAINING LOOP : Putting It All Together **



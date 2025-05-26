---
layout: post
title: "Understanding Independence and Bayes’ Rule"
date: 2025-05-16
categories: [statistics, beginner]
tags: [independence, bayes, conditional, tree-diagram, posterior, prior, likelihood]
math: true
---

How can we tell if two events are independent?  
What does it mean to update our beliefs when new data comes in?  
This post unpacks these ideas — and ends with a walkthrough of **Bayes’ Rule**.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/union-conditional/">Making Sense of Union, Tables, and Conditional Thinking</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/Probabilities/">Probability Distributions & Cumulative Thinking</a></p>
</div>

---

## 🔗 <span style="color:#1E90FF;">What Is Independence?</span>

Two events are **independent** when the occurrence of one **doesn’t affect** the probability of the other.

### 📌 Mathematically:

Any of the following implies independence:

\\[
P(A \mid B) = P(A)
\\]
\\[
P(B \mid A) = P(B)
\\]
\\[
P(A \cap B) = P(A) \cdot P(B)
\\]

If **any** of these holds, the events are independent.

---

## 🔄 <span style="color:#FFA500;">Independence vs Disjoint</span>

| Concept             | Description                                           |
|---------------------|-------------------------------------------------------|
| **Disjoint (Mutually Exclusive)** | Events can’t both happen. \\( P(A \cap B) = 0 \\) |
| **Independent**     | One event doesn’t affect the other’s probability       |

### ✅ Key Insight:
- If A and B are **disjoint**, then \\( P(A \cap B) = 0 \\)
- But that contradicts \\( P(A) \cdot P(B) > 0 \\) — so:
> **Disjoint events are always dependent.**  
> **Independent events are never disjoint (unless one has probability 0).**

---

## 🧪 <span style="color:#20B2AA;">Example: Email Spam Detection</span>

Suppose:
- 40% of all emails are spam → \\( P(S) = 0.4 \\)
- 80% of spam emails contain the word “free” → \\( P(F \mid S) = 0.8 \\)
- 10% of non-spam emails contain “free” → \\( P(F \mid \bar{S}) = 0.1 \\)

---

## 🌳 <span style="color:#228B22;">Build a Decision Tree</span>


![Bayes Decision Tree](/assets/images/bayes_decision_tree.png)
*Figure: Tree diagram showing all outcomes for Spam vs Free*


We can calculate all joint probabilities:

- \\( P(S \cap F) = 0.4 \cdot 0.8 = 0.32 \\)  
- \\( P(\bar{S} \cap F) = 0.6 \cdot 0.1 = 0.06 \\)  
- \\( P(F) = 0.32 + 0.06 = 0.38 \\)

---

## 📘 <span style="color:#8A2BE2;">Bayes' Theorem</span>

Now, we want:

> If I see “free” in an email, what’s the probability it’s spam?

### 📌 Formula:
\\[
P(S \mid F) = \frac{P(S \cap F)}{P(F)} = \frac{0.32}{0.38} \approx 0.842
\\]

---

## 🧠 <span style="color:#9370DB;">Understanding Bayes' Rule: Components</span>

| Term             | Meaning                                                              |
|------------------|----------------------------------------------------------------------|
| **Prior**        | What you believe before seeing the evidence → \\( P(S) = 0.4 \\)     |
| **Likelihood**   | Probability of the evidence given the hypothesis → \\( P(F \mid S) \\) |
| **Evidence**     | Total probability of seeing “free” → \\( P(F) = 0.38 \\)             |
| **Posterior**    | Updated belief → \\( P(S \mid F) = 0.842 \\)                         |

---

## 🧠 Bayes’ Theorem in Action: Two Real-World Examples

---

### 📚 Example 1: Student Cheating Detection

A teacher knows that only **2% of students** cheat on exams.

She uses a plagiarism detector that:
- Correctly identifies cheaters 90% of the time  
- Wrongly flags innocent students 5% of the time

Now, a student gets flagged. What are the chances they actually cheated?

Let:
- \\( C \\): student cheated
- \\( P \\): student flagged

We know:
- \\( P(C) = 0.02 \\),  \\( P(\bar{C}) = 0.98 \\)  
- \\( P(P \mid C) = 0.90 \\)  
- \\( P(P \mid \bar{C}) = 0.05 \\)

---

### ✏️ Bayes' Theorem:

\\[
P(C \mid P) = \frac{P(P \mid C) \cdot P(C)}{P(P \mid C) \cdot P(C) + P(P \mid \bar{C}) \cdot P(\bar{C})}
\\]

#### 🔍 Interpretation:
- **Numerator** = Likelihood × Prior = \\( 0.90 \cdot 0.02 = 0.018 \\)  
  → This is the **joint probability** of being a cheater **and** being flagged
- **Denominator** = Total probability of being flagged  
  → Includes both cheaters and non-cheaters who were flagged:
\\[
= 0.018 + (0.05 \cdot 0.98) = 0.018 + 0.049 = 0.067
\\]

### ✅ Final Answer:
\\[
P(C \mid P) = \frac{0.018}{0.067} \approx 0.268
\\]

Even if flagged, there's only a **~26.8% chance** the student actually cheated.

![Bayes Pie Chart](/assets/images/bayes_pie_chart.png)
*Figure: True vs False Positives that make up the total evidence (P(Flagged))*


---

### 💊 Example 2: Random Drug Testing at Work

A company screens employees for a rare performance-enhancing drug.

- Only **1 in 1,000** uses it → \\( P(D) = 0.001 \\)
- The test is **99% accurate**:
  - \\( P(+ \mid D) = 0.99 \\)  
  - \\( P(+ \mid \bar{D}) = 0.01 \\)

An employee tests positive. What's the probability they actually use the drug?

---

### ✏️ Bayes' Theorem:

\\[
P(D \mid +) = \frac{P(+ \mid D) \cdot P(D)}{P(+ \mid D) \cdot P(D) + P(+ \mid \bar{D}) \cdot P(\bar{D})}
\\]

#### 🔍 Interpretation:
- **Numerator** = Likelihood × Prior = \\( 0.99 \cdot 0.001 = 0.00099 \\)  
  → This is the **joint probability** of actually using the drug and testing positive
- **Denominator** = Total probability of testing positive:
\\[
= 0.00099 + (0.01 \cdot 0.999) = 0.00099 + 0.00999 = 0.01098
\\]

### ✅ Final Answer:
\\[
P(D \mid +) = \frac{0.00099}{0.01098} \approx 0.09
\\]

Despite a positive result, there's only a **~9% chance** the employee actually uses the drug — because the condition is rare, and **false positives dominate** the denominator.

---

<details class="border rounded p-3 bg-light my-4">
  <summary class="fw-bold text-primary">🧠 Level Up: Mastering Bayes — What’s Really Going On?</summary>
  <div class="mt-2">

  <p>Bayes’ Theorem might look like a formula — but it’s actually a way of <strong>reversing conditional logic</strong>.</p>

  <ul>
    <li>🎯 The <strong>numerator</strong> is the probability that <em>both the hypothesis and evidence</em> are true (joint probability).</li>
    <li>🧪 The <strong>denominator</strong> is the <em>total probability</em> of the observed evidence — from all possible sources.</li>
  </ul>

  <p>So Bayes’ Theorem simply asks:</p>
  <blockquote class="blockquote">
    If this result just happened, how likely was it caused by what I suspected?
  </blockquote>

  <p>🧠 You’re updating your belief (the prior) based on what you just saw (the evidence), and how likely that evidence is under each possible explanation (likelihood).</p>

  <p><strong>Bayes is not just math — it’s decision logic under uncertainty.</strong></p>

  </div>
</details>


---

{% include quiz/Bayes.html %}

---

![Bayes Formula Flow](/assets/images/bayes_formula_flow.png)
*Figure: Flow of belief update — from prior and likelihood to posterior*

---

## 🧠 Summary

| Concept             | Meaning                                             |
|---------------------|-----------------------------------------------------|
| Independence        | One event does not affect the other                 |
| Disjoint            | Events can’t happen together                        |
| Joint from Marginal | Only possible if events are independent             |
| Bayes' Rule         | Updates belief with new data                        |
| Prior               | Initial belief                                      |
| Likelihood          | How likely the data is under a hypothesis           |
| Posterior           | Updated probability                                 |
| Evidence            | Total probability of the observed condition         |

---

## ✅ Up Next

Next, we’ll dive into **probability distributions** and how cumulative distributions help us model real-world events over time.

Stay tuned!

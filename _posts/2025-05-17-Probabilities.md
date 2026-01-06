---
layout: post
title: "What Are Random Variables and How Do We Visualize Their Distributions?"
date: 2025-05-17
categories: [statistics,Descriptive statistics, beginner]
tags: [random-variable, pmf, pdf, cdf, discrete, continuous, quantile]
math: true
description: Learn how to understand and visualize random variables using PMF, PDF, and CDF. Covers discrete vs continuous distributions with real examples and intuitive plots.

---

What’s the difference between **a PMF, PDF, and CDF** — and how do they relate to **random variables?**
In this post, we’ll break down the key types of random variables (discrete vs continuous), show you how to visualize them, and explain how these concepts power real-world applications in statistics and machine learning.
---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/Bayes-_Rule/">Understanding Independence and Bayes’ Rule</a></p>
  <p>🔜 <strong>Next:</strong><a href="/posts/random-var-mean/"> Summary Statistics of Probability Distributions</a></p>
</div>

---

## 🎲 <span style="color:#1E90FF;">What Is a Random Variable?</span>

A **random variable** is a numerical outcome of a random phenomenon.

It can take different values depending on the situation — like the result of a die roll, the temperature in your city, or a person’s height.

---

## 🧱 <span style="color:#FFA500;">Types of Random Variables</span>

| Type           | Description                                                 | Examples                        |
| -------------- | ----------------------------------------------------------- | ------------------------------- |
| **Discrete**   | Takes a countable number of values                          | # of calls/day, die roll result |
| **Continuous** | Takes any value within an interval (infinite possibilities) | Height, temperature, weight     |

---

## 📊 <span style="color:#20B2AA;">How Do We Work With Random Variables?</span>

We use **probability distributions** to describe how likely each outcome is.

A probability distribution can be expressed as:
- A **table**
- A **graph**
- An **equation**

Depending on the variable type, we use:

| Type           | Distribution Function                  |
| -------------- | -------------------------------------- |
| **Discrete**   | **Probability Mass Function (PMF)**    |
| **Continuous** | **Probability Density Function (PDF)** |

---

### 🔍 Visual: PMF (Discrete Distribution)

![PMF Plot](/assets/images/pmf_plot.png)

Each bar shows the probability of an exact outcome.

---

### 🔍 Visual: PDF (Continuous Distribution)

![PDF Plot](/assets/images/pdf_plot.png)

The **area under the curve** (not the height) represents probability.  
You can’t directly say \\( P(X = 5) \\); it’s always \\( P(a \le X \le b) \\).

---

## ⚖️ <span style="color:#8A2BE2;">Why Are Discrete Probabilities Simpler?</span>

With discrete random variables, calculating probabilities is straightforward — you can just **add up the values**:

> \\( P(X = 2 \text{ or } X = 3) = P(X = 2) + P(X = 3) \\)

In contrast, with **continuous variables**, you need to integrate the area under the curve — which often requires formulas or software.

---

## 📈 <span style="color:#228B22;">Cumulative Distribution Function (CDF)</span>

The **Cumulative Distribution Function** answers:
> What is the probability that \\( X \\) is less than or equal to some value?

We can compute CDFs for **both** discrete and continuous variables.

---

### 🧪 Example: CDF (Discrete)

| x   | P(X = x) | P(X ≤ x) |
| --- | -------- | -------- |
| 1   | 0.1      | 0.1      |
| 2   | 0.3      | 0.4      |
| 3   | 0.2      | 0.6      |
| 4   | 0.25     | 0.85     |
| 5   | 0.15     | 1.0      |

![CDF Discrete](/assets/images/cdf_discrete.png)

Each step adds the probability from the previous value.

---

### 📊 Example: CDF (Continuous)

![CDF Continuous](/assets/images/cdf_continuous.png)

This curve shows **P(X ≤ x)** for every point — and it **always increases**.

---

## 📉 <span style="color:#FF69B4;">Distribution vs Cumulative: Visual Comparison</span>

| View          | What It Shows                                |
| ------------- | -------------------------------------------- |
| **PDF / PMF** | Probability of individual values (or areas)  |
| **CDF**       | Cumulative probability up to a certain point |

#### 🎨 Visual Comparison

**PDF → Use the area under curve to find probability**  
**CDF → Read probability directly from the graph**

---

## 📌 Key Properties of CDF

- Always increases (never decreases)
- Final value = 1
- You can find \\( x \\) for a given probability — or the other way around

---

## 🎯 <span style="color:#9370DB;">What Is a Quantile?</span>

A **quantile** tells us the value at a certain cumulative probability.

- The **median** is the 0.5 quantile → 50% of values lie below
- The **0.9 quantile** means 90% of values are below that point

### 🔍 Visual Example

![Quantile Concept](/assets/images/cdf_continuous.png)

> If the 90th percentile is 8.1, then \\( P(X \le 8.1) = 0.90 \\)

---
## 🤖 Why It Matters for Machine Learning

In machine learning, understanding random variables and their distributions is essential for:

- Modeling prediction uncertainty (e.g., probabilistic classifiers)
- Evaluating models (e.g., CDFs in ROC analysis)
- Data generation (e.g., sampling from PDFs or PMFs)
- Feature engineering (quantile normalization, log transformations)

Mastering these basics helps you build better models with interpretable results.

---

<details class="level-up-box">
    <summary class="level-up-title">🧠 Level Up: Why CDFs Are Powerful</summary>
<div class="level-up-content">
CDFs help you <b>answer questions in reverse</b>:
<li> “What’s the probability of X being below a threshold?” (➡️ read from CDF) </li>
<li> <span class="katex">“What value corresponds to 75% of cases?” (➡️ find the x-value for \( P(X) = 0.75 \))</span></li>

You can even <b>invert</b> the function to get values back from probabilities.

CDFs are especially useful in:

<li> Risk modeling</li>
<li> Threshold setting</li>
<li> Statistical simulations</li>
<li> Machine learning (quantile regression)</li>

  </div>
</details>

---
<details class="custom-box custom-best">
  <summary><strong>✅ Best Practices</strong></summary>
  <ul>
    <li>Use CDFs when comparing distributions or setting thresholds.</li>
    <li>Choose PMF for count data and PDF for continuous measurements.</li>
    <li>Use visualizations to detect skewness or outliers in distributions.</li>
    <li>Verify the total probability sums to 1 in your PMF/PDF.</li>
  </ul>
</details>

---

<details class="custom-box custom-warning">
  <summary><strong>⚠️ Common Pitfalls</strong></summary>
  <ul>
    <li>❌ Misinterpreting PDF height as probability — area matters.</li>
    <li>❌ Forgetting that continuous variables can't have P(X = a) > 0.</li>
    <li>❌ Confusing quantiles with raw values or assuming symmetry.</li>
    <li>❌ Using PMF formulas on continuous data or vice versa.</li>
  </ul>
</details>

---

{% include quiz/cummulative-prob.html %}

---
## ✅ Summary

| Concept         | Description                                    |
| --------------- | ---------------------------------------------- |
| Random Variable | Represents numeric outcome of a random event   |
| Discrete        | Countable outcomes (use PMF)                   |
| Continuous      | Infinite outcomes (use PDF)                    |
| PMF / PDF       | Describe probability distribution              |
| CDF             | Accumulated probability up to x                |
| Quantile        | Inverse of CDF — get x for a given probability |

---
## 🔜 Up Next

In the next post, we’ll explore **summary statistics** like:
- Mean
- Variance
- Standard deviation
- Expected value

These help us describe **how a probability distribution behaves**.

Stay tuned!

---
## 📺 Explore the Channel

<div style="max-width: 400px; margin: 30px auto; border: 1px solid #ccc; border-radius: 12px; padding: 16px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); text-align: center; font-family: sans-serif;">
  
  <img src="../assets/images/Hoda-Osama-Ai.png" alt="Hoda Osama AI Channel" style="width: 100%; border-radius: 8px;">

  <h3 style="margin-top: 16px; color: #333;">🎥 Hoda Osama AI</h3>
  <p style="color: #555;">Learn statistics and machine learning concepts step by step with visuals and real examples.</p>
  
  <a href="https://www.youtube.com/@Hoda_Osama_AI" target="_blank" rel="noopener noreferrer">
    <button style="margin-top: 12px; padding: 10px 20px; font-size: 16px; background-color: #FF0000; color: white; border: none; border-radius: 6px; cursor: pointer;">
      🔔 Subscribe on YouTube
    </button>
  </a>
</div>
---
## 💬 <span style="color:#4B0082;"> Got a Question? </span>

Leave a comment or open an issue on GitHub — I love connecting with other learners and builders. 🔁

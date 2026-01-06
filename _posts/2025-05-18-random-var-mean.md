---
layout: post
title: "Mean, Variance, and Standard Deviation of Random Variables"
date: 2025-05-18
categories: [statistics,Descriptive statistics, beginner]
tags: [mean, variance, stddev, random-variable, discrete, continuous]
math: true
---

How do we summarize a random variable with a single number?  
What happens to the mean and variance if we shift or scale the variable?  
This post explains the **mean**, **variance**, and **standard deviation** for both discrete and continuous random variables — with concrete examples.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/Probabilities/">What Are Random Variables and How Do We Visualize Their Distributions?</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/normal-distr/">Introduction to the Normal Distribution</a></p>
</div>

---

## 📏 <span style="color:#1E90FF;">What Is the Mean of a Random Variable?</span>

The **mean** (or expected value) of a random variable \( X \) is its **probability-weighted average** of all possible values.

---

### 🧮 <span style="color:#FFA500;"> Mean of a Discrete Random Variable </span>

\\[
\\mu_X = E(X) = \\sum_i x_i P(x_i)
\\]

This means each value \\( x_i \\) is weighted by its probability \\( P(x_i) \\).

#### Example:

| \\(x_i\\)    | 1   | 2   | 3   | 4   |
| ------------ | --- | --- | --- | --- |
| \\(P(x_i)\\) | 0.1 | 0.3 | 0.4 | 0.2 |

Calculate:

\\[
E(X) = 1 \\times 0.1 + 2 \\times 0.3 + 3 \\times 0.4 + 4 \\times 0.2 = 0.1 + 0.6 + 1.2 + 0.8 = 2.7
\\]

---

![Mean of Discrete Random Variable Light](/assets/images/discrete_random_var_mean_light.png)

---

### 📐<span style="color:#228B22; font-weight:bold;">  Mean of a Continuous Random Variable </span>

\\[
\\mu_X = E(X) = \\int_{-\\infty}^{\\infty} x f(x) \\, dx
\\]

Where \\( f(x) \\) is the probability density function (PDF).

#### Example:

If

\\[
f(x) = \\frac{1}{2} \\quad \\text{for } 0 \\leq x \\leq 2, \\quad 0 \\text{ otherwise}
\\]

Then

\\[
E(X) = \int_0^2 x \times \frac{1}{2} \, dx = \frac{1}{2} \int_0^2 x \, dx = \frac{1}{2} \times \left[ \frac{x^2}{2} \right]_0^2 = \frac{1}{2} \times 2 = 1
\\]

---

![Mean of a Continuous Random Variable](/assets/images/continuous_random_var_mean.png)

---

## 🔄 <span style="color:#FFA500;">Mean Under Linear Transformations</span>

If we transform \\( X \\) as:

\\[
Y = a + bX
\\]

then

\\[
E(Y) = a + b E(X)
\\]

---

#### <span style="color:#FFA500; font-weight:bold;"> Example (Using discrete mean above): </span>

\\[
E(Y) = 3 + 2 \times 2.7 = 3 + 5.4 = 8.4
\\]

---

![Mean of a Continuous Random Variable](/assets/images/linear_transformation_mean.png)

---

## 📊 <span style="color:#8A2BE2;">What Is Variance?</span>

Variance measures the **spread** or **deviation** of values around the mean:

\\[
\text{Var}(X) = E[(X - \mu)^2]
\\]

---

### 🧮 Variance for Discrete Random Variable

\\[
\text{Var}(X) = \sum_i (x_i - \mu)^2 P(x_i)
\\]

Using the discrete example above (\\( \\mu = 2.7 \\)):

\\[
\text{Var}(X) = (1 - 2.7)^2 \times 0.1 + (2 - 2.7)^2 \times 0.3 + (3 - 2.7)^2 \times 0.4 + (4 - 2.7)^2 \times 0.2
\\]

\\[
= (2.89)(0.1) + (0.49)(0.3) + (0.09)(0.4) + (1.69)(0.2)
\\]

\\[
= 0.289 + 0.147 + 0.036 + 0.338
\\]

\\[
= 0.81
\\]


---

![Mean of a Continuous Random Variable](/assets/images/discrete_variance_contributions.png)

---

### 📐 Variance for Continuous Random Variable

\\[
\text{Var}(X) = \int_{-\infty}^\infty (x - \mu)^2 f(x) \, dx
\\]

For the continuous example above (\\( \\mu=1 \\)):

\\[
\text{Var}(X) = \int_0^2 (x - 1)^2 \times \frac{1}{2} \, dx = \frac{1}{2} \int_0^2 (x^2 - 2x + 1) \, dx
\\]

Calculate:

\\[
= \frac{1}{2} \left[ \frac{x^3}{3} - x^2 + x \right]_0^2 = \frac{1}{2} \left( \frac{8}{3} - 4 + 2 \right) = \frac{1}{2} \times \frac{2}{3} = \frac{1}{3} \approx 0.333
\\]

---

## 🔄 <span style="color:#20B2AA;">Variance Under Linear Transformations</span>

For \\( Y = a + bX \\), variance changes as:

\\[
\text{Var}(Y) = b^2 \text{Var}(X)
\\]

*Adding or subtracting a constant \\( a \\) does not affect variance.*

---

### ✏️ Proof Sketch:

\\[
\text{Var}(Y) = E[(Y - E[Y])^2]
\\]

\\[
= E[(a + bX - (a + bE[X]))^2]
\\]

\\[
= E[(b(X - E[X]))^2]
\\]

\\[
= b^2 E[(X - E[X])^2]
\\]

\\[
= b^2 \text{Var}(X)
\\]


---

### Example:

Using previous discrete variance \( 0.81 \):

\\[
\text{Var}(Y) = 2^2 \times 0.81 = 4 \times 0.81 = 3.24
\\]

---

## 📏 <span style="color:#9370DB;">Standard Deviation and Scaling</span>

Standard deviation \\( \sigma \\) is the square root of variance:

\\[
\sigma_X = \sqrt{\text{Var}(X)}
\\]

For \\( Y = a + bX \\):

\\[
\sigma_Y = \sqrt{\text{Var}(Y)} = \sqrt{b^2 \text{Var}(X)} = |b| \sigma_X
\\]

---

### Example (continued):

\\[
\sigma_X = \sqrt{0.81} = 0.9
\\]

\\[
\sigma_Y = 2 \times 0.9 = 1.8
\\]

---

## 🔢 <span style="color:#FF4500;">Variance of Sum and Difference</span>

For any two variables \\( X \\) and \\( Y \\):

\\[
\text{Var}(X \pm Y) = \text{Var}(X) + \text{Var}(Y) \pm 2\,\text{Cov}(X, Y)
\\]

---
## 🤖 Why It Matters for Machine Learning
  <div class="mt-2">
    <p>Understanding <strong>expected value</strong> and <strong>variance</strong> is foundational to many machine learning algorithms:</p>
    <ul>
      <li>📊 <strong>Feature Scaling:</strong> When features are transformed (e.g., using <em>standardization</em> or <em>min-max scaling</em>), you're applying <em>linear transformations</em> — and knowing how these affect mean and variance helps you avoid introducing bias.</li>
      <li>🧠 <strong>Loss Functions:</strong> Common losses like <code>MSE</code> rely on variance concepts — minimizing variance between predicted and actual values improves model performance.</li>
      <li>📈 <strong>Model Interpretation:</strong> Many models assume data has constant variance (homoscedasticity). Violating this can lead to poor generalization.</li>
    </ul>
    <p class="mt-3">💡 Mastering these statistical fundamentals makes it easier to debug models, improve feature engineering, and better understand algorithm behavior under the hood.</p>
  </div>


---
<details class="level-up-box">
  <summary class="level-up-title">🧠 Level Up: Understanding Variance Properties</summary>
<div class="level-up-content">

<li> Adding a constant \( a \) to a random variable shifts the mean but leaves variance unchanged.  </li>
<li> Multiplying by \( b \) scales the variance by \( b^2 \).  </li>
<li> Standard deviation scales by \( |b| \) — the absolute value of the multiplier.  </li>
<li> Variance of sums depends on covariance — independent variables have zero covariance, so variances add.</li>

  </div>
</details>

---
<details class="custom-box custom-best">
  <summary><strong>✅ Best Practices for Working with Random Variable Metrics</strong></summary>
  <ul>
    <li>Always check whether your variable is <strong>discrete or continuous</strong> before choosing formulas.</li>
    <li>Use <strong>linear transformation rules</strong> to simplify calculations and scaling checks.</li>
    <li>Understand that <strong>standard deviation</strong> is more interpretable in the context of units.</li>
    <li>Apply variance rules carefully when dealing with <strong>sums of variables</strong>.</li>
  </ul>
</details>
---
<details class="custom-box custom-warning">
  <summary><strong>⚠️ Common Pitfalls to Avoid</strong></summary>
  <ul>
    <li>❌ Confusing the formula for variance between <strong>sample vs. population</strong>.</li>
    <li>❌ Forgetting to square the scaling factor when applying transformations to variance.</li>
    <li>❌ Assuming that adding constants affects the variance (it doesn’t).</li>
    <li>❌ Neglecting <strong>covariance</strong> when computing variance of sums.</li>
  </ul>
</details>

---
{% include quiz/random-var-mean.html %}

---

## ✅ Summary

| Concept                   | Formula / Description                                                            |
| ------------------------- | -------------------------------------------------------------------------------- |
| Mean (Discrete)           | \\( \mu = \sum x_i P(x_i) \\)                                                    |
| Mean (Continuous)         | \\( \mu = \int x f(x) dx \\)                                                     |
| Variance (Discrete)       | \\( \sigma^2 = \sum (x_i - \mu)^2 P(x_i) \\)                                     |
| Variance (Continuous)     | \\( \sigma^2 = \int (x - \mu)^2 f(x) dx \\)                                      |
| Linear Transform Mean     | \\( E(a + bX) = a + b E(X) \\)                                                   |
| Linear Transform Variance | \\( \text{Var}(a + bX) = b^2 \text{Var}(X) \\)                                   |
| Variance of Sum/Diff      | \\( \text{Var}(X \pm Y) = \text{Var}(X) + \text{Var}(Y) \pm 2\text{Cov}(X,Y) \\) |
| Std Deviation             | \\( \sigma = \sqrt{\text{Var}(X)} \\)                                            |

---
## 🔜 Up Next

Next, we’ll explore the **Normal Distribution** — a fundamental continuous distribution that appears everywhere in statistics and data science.

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


---
layout: post
title: "Mean, Variance, and Standard Deviation of Random Variables"
date: 2025-05-18
categories: [statistics, beginner]
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

| \\(x_i\\) | 1   | 2   | 3   | 4   |
|---------|-----|-----|-----|-----|
| \\(P(x_i)\\) | 0.1 | 0.3 | 0.4 | 0.2 |

Calculate:

\\[
E(X) = 1 \\times 0.1 + 2 \\times 0.3 + 3 \\times 0.4 + 4 \\times 0.2 = 0.1 + 0.6 + 1.2 + 0.8 = 2.7
\\]

---

![Mean of Discrete Random Variable Light](/assets/images/discrete_random_var_mean_light.png)

---

### 📐 Mean of a Continuous Random Variable

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

#### Example (Using discrete mean above):

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

<details class="border rounded p-3 bg-light my-4">
  <summary class="fw-bold text-primary">🧠 Level Up: Understanding Variance Properties</summary>
  <div class="mt-2">

<li> Adding a constant \( a \) to a random variable shifts the mean but leaves variance unchanged.  </li>
<li> Multiplying by \( b \) scales the variance by \( b^2 \).  </li>
<li> Standard deviation scales by \( |b| \) — the absolute value of the multiplier.  </li>
<li> Variance of sums depends on covariance — independent variables have zero covariance, so variances add.</li>

  </div>
</details>

---

{% include quiz/random-var-mean.html %}

---

## ✅ Summary

| Concept                 | Formula / Description                                 |
|-------------------------|-----------------------------------------------------|
| Mean (Discrete)          | \\( \mu = \sum x_i P(x_i) \\)                          |
| Mean (Continuous)        | \\( \mu = \int x f(x) dx \\)                           |
| Variance (Discrete)      | \\( \sigma^2 = \sum (x_i - \mu)^2 P(x_i) \\)          |
| Variance (Continuous)    | \\( \sigma^2 = \int (x - \mu)^2 f(x) dx \\)           |
| Linear Transform Mean    | \\( E(a + bX) = a + b E(X) \\)                         |
| Linear Transform Variance| \\( \text{Var}(a + bX) = b^2 \text{Var}(X) \\)        |
| Variance of Sum/Diff     | \\( \text{Var}(X \pm Y) = \text{Var}(X) + \text{Var}(Y) \pm 2\text{Cov}(X,Y) \\) |
| Std Deviation            | \\( \sigma = \sqrt{\text{Var}(X)} \\)                  |

---

## 🔜 Up Next

Next, we’ll explore the **Normal Distribution** — a fundamental continuous distribution that appears everywhere in statistics and data science.

Stay tuned!

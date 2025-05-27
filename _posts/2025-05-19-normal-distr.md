---
layout: post
title: "Understanding Normal Distribution"
date: 2025-05-19
categories: [statistics, beginner]
tags: [normal distribution, gaussian, probability, statistics]
math: true
---

## 📌 <span style="color:#20B2AA;"> What is Normal Distribution (Gaussian Distribution)? </span>

The **normal distribution** (or **Gaussian distribution**) is a type of continuous probability distribution for a real-valued random variable. It describes how many natural phenomena and errors in measurements are distributed. The graph is symmetric and bell-shaped.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/random-var-mean/">Mean, Variance, and Standard Deviation of Random Variables</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/z-distribution/">Z Distribution</a></p>
</div>

---

## 📐 <span style="color:#1E90FF;"> The Probability Density Function (PDF) for Normal Distribution </span>

The equation for the PDF of a normal distribution is:

\\[
f(x) = \frac{1}{\sigma \sqrt{2\pi}} \exp \left( -\frac{(x - \mu)^2}{2\sigma^2} \right)
\\]

Where:
- \\( \mu \\) is the **mean** (location parameter) of the distribution, which defines where the peak of the bell curve is located.
- \\( \sigma \\) is the **standard deviation** (shape parameter), which controls the width of the bell curve.
- \\( \\exp \\) is the exponential function, describing how particles or phenomena distribute themselves in nature (e.g., diffusion).

This equation connects the statistical world to real-world distributions.

---

## 📊 <span style="color:#FF6347;"> Understanding the Equation </span>

This equation is an **exponential function** and, after standardization, it describes how the values are distributed symmetrically around the mean.

- The area under the curve represents the total probability, and the sum of all probabilities equals 1.
- The variable \\( x \\) can take any value from \\( -\infty \\) to \\( +\infty \\), meaning the distribution extends infinitely in both directions.

---

## 🔄 Important Characteristics of Normal Distribution

- **\\( \mu \\)** describes the **location** of the distribution, i.e., where the center of the bell curve lies.
- **\\( \sigma \\)** defines the **shape** of the distribution, i.e., how spread out the values are around the mean.
- The probability for any given range can be found using the **cumulative distribution function (CDF)**.

---

## 🧮<span style="color:#1E90FF;">  Example of Normal Distribution </span>

For any normal distribution:
- **68%** of values lie between \\( \mu - \sigma \\) and \\( \mu + \sigma \\).
- **95%** of values lie between \\( \mu - 2\sigma \\) and \\( \mu + 2\sigma \\).
- **99.7%** of values lie between \\( \mu - 3\sigma \\) and \\( \mu + 3\sigma \\).

### 📈<span style="color:#20B2AA;"> Visualizing the 68%, 95%, and 99.7% Rule </span>

Here’s a visual showing the **68%**, **95%**, and **99.7%** areas under the curve:

![Normal Distribution - Empirical Rule](./assets/images/normal_distribution_empirical_rule.png)

---

## 📝 <span style="color:#1E90FF;">How to Calculate Probabilities Using Normal Distribution</span>

To calculate the probability that a variable \\( X \\) lies within a specific range:
- We use the **Cumulative Distribution Function (CDF)**, which gives the area under the curve from \\( -\infty \\) to a specified \\( x \\).

---

<details class="border rounded p-3 bg-light my-4">
  <summary class="fw-bold text-primary">🧠 Level Up: Understanding the Normal Distribution in Detail</summary>
  <div class="mt-2">
    <ul>
      <li>The <b>normal distribution</b> is foundational in statistics. It is used in hypothesis testing, confidence intervals, and in many natural and social sciences.</li>
      <li><b>The 68-95-99.7 rule</b>: This empirical rule highlights the percentage of data that falls within 1, 2, and 3 standard deviations from the mean.</li>
      <li>The <b>central limit theorem</b> suggests that, regardless of the original distribution of data, the sampling distribution of the sample mean will approximate a normal distribution as the sample size increases.</li>
      <li>In practice, many natural phenomena and errors in measurement follow a normal distribution because of the <b>law of large numbers</b>.</li>
    </ul>
  </div>
</details>

---

{% include quiz/normal-distr.html %}

---

## 📏 <span style="color:#FFA500;"> Summary of Key Points </span>

- The **normal distribution** is symmetric and bell-shaped.
- The **mean** \\( \mu \\) determines the location of the peak.
- The **standard deviation** \\( \sigma \\) controls the spread.
- **68%** of values lie within one standard deviation (\\( \mu \pm \sigma \\)).
- **95%** of values lie within two standard deviations (\\( \mu \pm 2\sigma \\)).
- **99.7%** of values lie within three standard deviations (\\( \mu \pm 3\sigma \\)).

---

## 🔜 Up Next

Next, we’ll explore the **Z-Distribution** — a standardized version of the normal distribution that is used to calculate probabilities and percentiles.

Stay tuned!

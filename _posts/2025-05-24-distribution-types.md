---
layout: post
title: "Population, Sample, and Sampling Distributions Explained"
date: 2025-05-24
categories: [statistics, beginner]
tags: [population-distribution, sample-distribution, sampling-distribution, standardization]
math: true
---

## 🎯 <span style="color:#228B22; font-weight:bold;"> Population Distribution </span>

The **population distribution** describes the values of a variable for **all members** of a population.

- Mean: \\( \mu \\) (population mean)
- Standard deviation: \\( \sigma \\) (population standard deviation)

### Example:

Suppose the heights of all adults in a town are normally distributed with:

\\[
\mu = 170 \text{ cm}, \quad \sigma = 10 \text{ cm}
\\]

To find the probability that a randomly selected adult is taller than 180 cm, convert the score to a Z-score:

\\[
Z = \frac{180 - 170}{10} = 1
\\]

Then look up \\( P(Z > 1) \\) in the standard normal table (approximately 0.1587).

---

## 🔍 <span style="color:#1E90FF; font-weight:bold;"> Sample Distribution </span>

The **sample distribution** is the distribution of observed data values in a particular sample.

- Mean: \\( \bar{x} \\) (sample mean)
- Standard deviation: \\( s \\) (sample standard deviation)

### Example:

In a sample of 30 adults, you measure their heights and calculate:

\\[
\bar{x} = 168 \text{ cm}, \quad s = 11 \text{ cm}
\\]

To find the probability a randomly selected person in this sample is shorter than 160 cm:

\\[
Z = \frac{160 - 168}{11} \approx -0.73
\\]

Look up \\( P(Z < -0.73) \\) in the Z-table (about 0.2327).

---

## 📊 <span style="color:#FFA500; font-weight:bold;"> Sampling Distribution of the Sample Mean </span>

The **sampling distribution of the sample mean** is a **theoretical distribution** of all possible sample means from samples of size \\( n \\).

- Mean of sampling distribution: \\( \mu_{\bar{x}} = \mu \\)
- Standard error: \\( \sigma_{\bar{x}} = \frac{\sigma}{\sqrt{n}} \\)

### Important:

- It is always approximately **normal**, regardless of the population distribution (by CLT).
- We standardize using Z-scores to calculate probabilities about sample means.

### Example:

From the previous population:

\\[
\mu = 170, \quad \sigma = 10, \quad n=25
\\]

The standard error is:

\\[
\sigma_{\bar{x}} = \frac{10}{\sqrt{25}} = 2
\\]

To find the probability that the sample mean is greater than 174 cm:

\\[
Z = \frac{174 - 170}{2} = 2
\\]

Look up \\( P(Z > 2) \\) (about 0.0228).

---
![Clear Educational Diagram](/assets/images/distributions.png)

---

<details class="border rounded p-3 bg-light my-4">
  <summary class="fw-bold text-primary">🧠 Level Up: Deeper Insights into Sampling Distributions</summary>
  <div class="mt-2" style="line-height:1.5; font-size: 0.95rem;">
    <ul>
      <li>The Central Limit Theorem explains why sampling distributions tend to normality even when populations are skewed.</li>
      <li>Sampling distributions can be used to calculate confidence intervals and conduct hypothesis tests.</li>
      <li>Understanding the shape and variability of sampling distributions is critical for accurate statistical inference.</li>
      <li>Advanced techniques like bootstrapping allow estimation of sampling distributions without relying on CLT assumptions.</li>
    </ul>
  </div>
</details>

---
{% include quiz/distr-types.html %}


---

## ✅ <span style="color:#228B22; font-weight:bold;">Summary</span>

| <span style="color:#1E90FF; font-weight:bold;">Concept</span>                  | <span style="color:#1E90FF; font-weight:bold;">Description</span>                           |
|----------------------------|----------------------------------------------------------|
| <span style="color:#228B22;">Population Distribution</span>  | Distribution of all members in the population                                     |
| <span style="color:#DA70D6;">Sample Distribution</span>      | Distribution of data in a single sample                                          |
| <span style="color:#FFA500;">Sampling Distribution</span>    | Theoretical distribution of sample means from many samples                        |
| <span style="color:#8A2BE2;">Mean of Sampling Distribution</span> | Equals the population mean \\( \mu \\)                                              |
| <span style="color:#DC143C;">Standard Error</span>            | \\( \sigma_{\bar{x}} = \frac{\sigma}{\sqrt{n}} \\), variability of sample means     |
| <span style="color:#4682B4;">Standardization (Z-score)</span>| Converting values to standard normal scores for probability calculations          |

---

## 🔜 Up Next

In the next post, we’ll cover **The Sampling Distribution of the Sample Proportion** — essential for working with categorical data and proportions.

Stay curious! 📈

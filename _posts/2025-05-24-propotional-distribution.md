---
layout: post
title: "Sampling Distribution of the Sample Proportion"
date: 2025-05-24
categories: [statistics, beginner]
tags: [sampling-distribution, sample-proportion, population-proportion]
math: true
---

## 🎯 <span style="color:#228B22; font-weight:bold;"> The Sampling Distribution of the Sample Proportion </span>

In a **population**, the **proportion** is the number of successful outcomes over the total number of cases. This proportion is denoted by \\( \beta \\).

For a **sample**, the proportion is represented by \\( p \\), which is an estimate of \\( \beta \\) (population proportion). As the sample size increases, \\( p \\) gets closer to \\( \beta \\).

- **Number of samples** = \\( N \\)
- **Sample proportion** = \\( p \\)

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/distribution-types/" style="color:#FF6F61;">Population, Sample, and Sampling Distributions Explained</a></p>
</div>

---

## 🔍 <span style="color:#1E90FF; font-weight:bold;"> Example: Proportion of Voters Supporting a Candidate </span>

Imagine you're conducting a poll to determine the proportion of voters supporting a political candidate in a city. Out of a sample of 1000 people:

- 600 people say they support the candidate, so the sample proportion \\( p = \frac{600}{1000} = 0.6 \\).

If you repeat this polling process many times, the **sample proportions** will vary. The more samples you take, the closer \\( p \\) will get to the\\( \beta \), which is the true support rate in the city.

![Sampling Distribution of Proportion](/assets/images/clean_sampling_distribution_proportion.png)

---

## 📊 <span style="color:#FFA500; font-weight:bold;"> Key Properties of the Sampling Distribution of the Sample Proportion </span>

- As the number of samples approaches infinity, the **sample proportion \\( p \\)** will approximate the **population proportion \\( \beta \\)**.
- The **mean** of the sampling distribution of the sample proportion is \\( \mu_p = \mu \\) (the population proportion).
- The sampling distribution is **approximately normal** if:
  - \\( n \times \beta \geq 15 \\)
  - \\( n \times (1 - \beta) \geq 15 \\)
  
This is because we are working with **binary categorical data**, where the outcomes are either "success" or "failure."

---

## 🔎 <span style="color:#2E8B57; font-weight:bold;"> Conditions for Normality </span>

- The **sampling distribution** of the sample proportion will be **approximately bell-shaped** if:
  - \\( n \times \beta \geq 15 \\)
  - \\( n \times (1 - \beta) \geq 15 \\)

Where:
- \\( n \\) = sample size
- \\( \beta \\) = population proportion (success rate)

This ensures that the data behaves like a normal distribution and we can use standard statistical tools like Z-scores.

---

## 📏 <span style="color:#8A2BE2; font-weight:bold;"> Standard Deviation of the Sample Proportion </span>

The standard deviation (also called the **standard error**) of the sample proportion is given by the formula:

\\[
\sigma_p = \sqrt{\frac{\beta(1 - \beta)}{n}}
\\]

Where:
- \\( \beta \\) = population proportion
- \\( n \\) = sample size

### Example:
Let’s assume a population proportion of \\( \beta = 0.6 \\) (60% of people support a candidate), and you take a sample of size \\( n = 1000 \\).

The standard error is:

\\[
\sigma_p = \sqrt{\frac{0.6(1 - 0.6)}{1000}} = \sqrt{\frac{0.24}{1000}} = 0.0155
\\]

This means the sample proportion will vary by about 0.0155 from the true population proportion on average.

---

## ⚖️ <span style="color:#DC143C; font-weight:bold;"> Calculating Proportions for Binary Categorical Variables </span>

When dealing with binary categorical variables (like success/failure, yes/no), **we don't need to calculate the mean or standard deviation** using traditional methods. Instead, we compute the **proportion \\( \beta \\)** for the population and \\( p \\) for the sample.

- **Population Proportion** \\( \beta \\)
- **Sample Proportion** \\( p \\)
- **Standard Deviation** of the sample proportion \\( \sigma_p \\)

### Example:

- Population: 60% support the candidate (\\( \beta = 0.6 \\))
- Sample: 550 out of 1000 support the candidate (\\( p = 0.55 \\))

Use the formula to find the standard error for further analysis.

---
<details class="level-up-box">
  <summary class="level-up-title">🧠 Level Up: Advanced Insights on Sampling Proportions</summary>
   <div class="level-up-content">
    <ul>
      <li>The <b>Central Limit Theorem</b> ensures that as the sample size increases, the sampling distribution of the sample proportion becomes approximately normal, allowing for easier statistical inference.</li>
      <li>When <b>sample size</b> \( n \) is large enough (usually \( n \geq 30 \)) and both \( n\beta \geq 15 \) and \( n(1-\beta) \geq 15 \) hold, the sampling distribution of the sample proportion will follow a normal distribution.</li>
      <li>To improve accuracy, <b>confidence intervals</b> and <b>hypothesis tests</b> can be applied to sample proportions, leveraging the normality assumption from the CLT.</li>
      <li>If the sample size is small or the conditions for normality aren’t met, other techniques like <b>binomial approximation</b> or <b>bootstrapping</b> can be used for more reliable results.</li>
    </ul>
  </div>
</details>

---
<details class="custom-box custom-best">
  <summary><strong>✅ Best Practices for Proportional Sampling</strong></summary>
  <ul>
    <li>Ensure your sample size is large enough so that <code>n × β ≥ 15</code> and <code>n × (1 - β) ≥ 15</code>.</li>
    <li>Use random and representative sampling to reduce bias in estimating <code>p</code>.</li>
    <li>Report a confidence interval with your sample proportion for better interpretation.</li>
    <li>Verify that your variable is binary (success/failure) before applying this model.</li>
  </ul>
</details>

---
<details class="custom-box custom-warning">
  <summary><strong>⚠️ Common Pitfalls to Avoid</strong></summary>
  <ul>
    <li>❌ Applying the normal approximation when <code>n × β</code> or <code>n × (1 - β)</code> is less than 15.</li>
    <li>❌ Misinterpreting <code>p</code> as a fixed value — it's a random variable.</li>
    <li>❌ Forgetting that standard deviation decreases with larger samples.</li>
    <li>❌ Confusing the population proportion <code>β</code> with the sample proportion <code>p</code>.</li>
  </ul>
</details>


---

{% include quiz/propotion-distr.html %}

---
## ✅ <span style="color:#228B22; font-weight:bold;">Summary</span>

| <span style="color:#1E90FF; font-weight:bold;">Concept</span>                  | <span style="color:#1E90FF; font-weight:bold;">Description</span>                           |
|----------------------------|----------------------------------------------------------|
| <span style="color:#228B22;">Population Proportion (\\( \beta \\))</span>  | Proportion of successful outcomes in the population.                                     |
| <span style="color:#DA70D6;">Sample Proportion (\\( p \\))</span>      | Proportion of successful outcomes in a sample.                                          |
| <span style="color:#FFA500;">Sampling Distribution</span>    | Theoretical distribution of sample proportions from many samples                        |
| <span style="color:#8A2BE2;">Mean of Sampling Distribution</span> | Equals the population proportion \\( \mu_p = \mu \\)                                              |
| <span style="color:#DC143C;">Standard Error (\\( \sigma_p \\))</span>            | \\( \sigma_p = \sqrt{\frac{\beta(1 - \beta)}{n}} \\), variability of sample proportions     |
| <span style="color:#4682B4;">Conditions for Normality</span> | \\( n \times \beta \geq 15 \\) and \\( n \times (1 - \beta) \geq 15 \\) for bell-shaped curve. |

---
## 💬 Got a question or suggestion?

Leave a comment below — I’d love to hear your thoughts or help if something was unclear.

---

## 🔜 Up Next

In the next post, we’ll explore **The Sampling Distribution of the Sample Mean** in more detail — how sample averages behave and how to apply them in statistical procedures.

Stay curious! 📈

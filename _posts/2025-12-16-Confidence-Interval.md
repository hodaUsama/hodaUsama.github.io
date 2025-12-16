---
layout: post
title: "Confidence Interval for a Known Population Standard Deviation"
date: 2025-12-16
categories: [statistics, Inferential Statistics, beginner]
tags: [confidence-interval, z-distribution, population-mean, statistics-for-ml]
math: true
description: Learn how to calculate a confidence interval when the population standard deviation is known using a real-world example on teen screen time.
---

## 🎯 <span style="color:#2E8B57;">Goal: Estimating a Population Mean with Known Standard Deviation</span>

In statistics, estimating the **true population mean (\\( \\mu \\))** using a sample mean (\\( \\bar{x} \\)) is a core task in inferential analysis.

This post explains how to calculate a **Confidence Interval** when the **population standard deviation (\\( \sigma \\)) is known** — a scenario where we use the **Z-distribution** instead of the T-distribution.

---

## 📱 <span style="color:#C0392B;">Real-World Case: Teenagers' Daily Screen Time</span>

Imagine you're analyzing national survey data on **teenagers' daily screen time** (phones, laptops, TV).

A previous nationwide health report tells us the **standard deviation** of screen time across the full population of teens is **\\( \sigma = 1.5 \\) hours**.

You're working with a **random sample of 60 teenagers**, and you find that:

- **Sample Mean**: \\( \bar{x} = 5.2 \\) hours/day  
- **Known Population SD**: \\( \sigma = 1.5 \\) hours  
- **Sample Size**: \\( n = 60 \\)  
- **Confidence Level**: 95% (Z = 1.96)

---

## 📊 <span style="color:#1E90FF;">Step-by-Step: Building the Confidence Interval</span>

### 🔹 Step 1: Calculate the Standard Error

\\[
SE = \frac{\sigma}{\sqrt{n}} = \frac{1.5}{\sqrt{60}} \approx 0.1936
\\]

---

### 🔹 Step 2: Calculate the Margin of Error

\\[
ME = Z \times SE = 1.96 \times 0.1936 \approx 0.3794
\\]

---

### 🔹 Step 3: Construct the Confidence Interval

\\[
\bar{x} \pm ME = 5.2 \pm 0.3794
\\]

- **Lower Bound**: \\( 5.2 - 0.3794 = 4.82 \\)  
- **Upper Bound**: \\( 5.2 + 0.3794 = 5.58 \\)

✅ **Conclusion**: We are **95% confident** that the **true average screen time among all teenagers** is **between 4.82 and 5.58 hours per day**.

---

![A Visual Guide to Confidence Intervals](/assets/images/ConfIInfo.png)

---

## 🧠 <span style="color:#D35400;">Level Up: Why This Matters for Machine Learning</span>

In ML, you're often making predictions on **unseen populations**. Whether it’s user behavior, healthcare diagnostics, or marketing trends — understanding **confidence intervals** helps model generalization.

- 🔍 **Precision vs Confidence**: A **wider interval** gives more confidence but less precision. A **narrower interval** is more precise but riskier.
- 🎯 If you want a **narrower range**, increase the **sample size** to reduce standard error.

---

## 🐍 <span style="color:#8A2BE2;">Python in Practice: CI with Known Standard Deviation</span>

```python
import numpy as np
import scipy.stats as stats

# Given data
sample_mean = 5.2
sigma = 1.5
n = 60
z = 1.96

# Standard Error
se = sigma / np.sqrt(n)

# Margin of Error
me = z * se

# Confidence Interval
ci_lower = sample_mean - me
ci_upper = sample_mean + me

print(f"95% CI: ({ci_lower:.2f}, {ci_upper:.2f})")
```

---

## 📏 <span style="color:#DC143C;">Quick Reference: Steps to Calculate</span>

1. ✅ **Collect your data**  
   - Sample size \\( n \\)  
   - Sample mean \\( \bar{x} \\)  
   - Known population standard deviation \\( \sigma \\)

2. ✅ **Choose your confidence level**  
   - Common choices:  
     - 90% → \\( Z = 1.645 \\)  
     - 95% → \\( Z = 1.96 \\)  
     - 99% → \\( Z = 2.576 \\)

3. ✅ **Calculate the Standard Error (SE)**  
   \\[
   SE = \frac{\sigma}{\sqrt{n}}
   \\]

4. ✅ **Calculate the Margin of Error (ME)**  
   \\[
   ME = Z \times SE
   \\]

5. ✅ **Construct the Confidence Interval**  
   \\[
   \bar{x} \pm ME
   \\]  
   - Lower bound: \\( \bar{x} - ME \\)  
   - Upper bound: \\( \bar{x} + ME \\)

---

## ✅ <span style="color:#1E90FF;">Summary Table</span>

| <strong>Component</strong>   | <strong>Value</strong> |
| ---------------------------- | ---------------------- |
| Sample Mean \\( \bar{x} \\)  | 5.2 hours              |
| Population SD \\( \sigma \\) | 1.5 hours              |
| Sample Size \\( n \\)        | 60                     |
| Z-Score (95%)                | 1.96                   |
| Standard Error (SE)          | 0.1936                 |
| Margin of Error (ME)         | 0.3794                 |
| Confidence Interval          | (4.82, 5.58) hours     |

---
---

<details class="custom-box custom-best">
  <summary><strong>✅ Best Practices for Confidence Intervals with Known σ</strong></summary>
  <ul>
    <li><strong>Know Your σ:</strong> This method only applies if the population standard deviation is already known from prior studies or reliable data.</li>
    <li><strong>Use a Large Enough Sample:</strong> While the Z-distribution works with any sample size here, larger samples reduce the standard error and tighten the interval.</li>
    <li><strong>Pick the Right Confidence Level:</strong> Choose your level (90%, 95%, or 99%) based on how much uncertainty you're willing to tolerate.</li>
    <li><strong>Report the Full Interval:</strong> Don’t just state the sample mean — always give the range (e.g., 5.2 ± 0.38 or [4.82, 5.58]).</li>
    <li><strong>Communicate Confidence Clearly:</strong> Explain what the interval means in plain language — it’s about method reliability, not a probability for one interval.</li>
  </ul>
</details>

---

<details class="custom-box custom-warning">
  <summary><strong>⚠ Common Pitfalls to Avoid</strong></summary>
  <ul>
    <li><strong>Using Z when σ is Unknown:</strong> If σ is estimated from the sample, you should use the T-distribution instead of Z.</li>
    <li><strong>Skipping the Square Root of n:</strong> Forgetting to apply the square root in the standard error formula leads to major errors.</li>
    <li><strong>Thinking "95% Confidence" = 95% Chance:</strong> That’s incorrect — confidence refers to the long-run success rate of the method, not a single estimate.</li>
    <li><strong>Assuming the Mean is Fixed:</strong> The sample mean 
    
    \[      
      ( \bar{x} )\  
    \] 
    
    changes with each sample — it’s not the true 
    
    \[
       ( \mu )\
    \]
    
    </li>
    <li><strong>Not Increasing n for Precision:</strong> Want a narrower interval? Increase the sample size — that reduces SE and tightens your estimate.</li>
  </ul>
</details>

---

<details class="level-up-box">
  <summary class="level-up-title">🧠 Level Up: Z vs T Confidence Intervals</summary>
  <div class="level-up-content">
    <p>There are two main ways to estimate a confidence interval for a mean:</p>
    <ul>
      <li>🧠 <strong>Z-Interval:</strong> Use when the population standard deviation (σ) is <strong>known</strong> — typically from historical or scientific sources.</li>
      <li>🧠 <strong>T-Interval:</strong> Use when σ is <strong>unknown</strong> and you estimate it using the sample standard deviation (s). This is much more common in real-world applications.</li>
    </ul>
    <p>Knowing when to use Z vs T is a foundational skill in statistics and machine learning evaluations.</p>
  </div>
</details>

---

<h2 id="quiz" class="mt-5">📌 Try It Yourself: Confidence Interval with Known σ</h2>

<p><strong>Q1:</strong> When should you use a Z-distribution instead of a T-distribution for confidence intervals?</p>
<details class="my-2">
  <summary><strong>💡 Show Answer</strong></summary>
  <p>When the population standard deviation (σ) is known.</p>
</details>

<p><strong>Q2:</strong> What formula is used to compute the standard error when σ is known?</p>
<details class="my-2">
  <summary><strong>💡 Show Answer</strong></summary>
  <p> 

  \[ 
    \( \text{SE} = \frac{\sigma}{\sqrt{n}} )\
    \]
  </p>
</details>

<p><strong>Q3:</strong> Why does increasing the sample size reduce the width of a confidence interval?</p>
<details class="my-2">
  <summary><strong>💡 Show Answer</strong></summary>
  <p>Because it decreases the standard error, making the margin of error smaller.</p>
</details>

<p><strong>Q4:</strong> If a study reports a 95% confidence interval of [4.82, 5.58], what does this mean?</p>
<details class="my-2">
  <summary><strong>💡 Show Answer</strong></summary>
  <p>It means that if the study were repeated many times, 95% of the calculated intervals would contain the true population mean.</p>
</details>

<p><strong>Q5:</strong> You calculate 

\[
  ( \bar{x} = 5.2 )\, ( \sigma = 1.5 )\, ( n = 60 )\
\]
  , and want a 95% confidence level. What’s your margin of error?</p>
<details class="my-2">
  <summary><strong>💡 Show Answer</strong></summary>
  <p>

  \[
     ( \SE = 1.5 / \sqrt{60} = 0.1936 )\
  \], so ME = 1.96 × 0.1936 = 0.3794</p>
</details>

---


## 🔜 <span style="color:#FFA500;">What’s Next?</span>

Now that you’ve mastered how to calculate a confidence interval with a known \\( \sigma \\), our next post will dive into **how to estimate the population mean when the population standard deviation is <em>unknown</em>** — using the **T-distribution**.

Stay tuned as we continue building your statistical intuition for data science and ML. 🎓📊

---

## 💬 Got a Question?

I’d love to hear your thoughts! Drop your questions, corrections, or topic suggestions below.

---

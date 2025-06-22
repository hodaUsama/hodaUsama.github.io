---
layout: post
title: "Z-Score: Comparing Values Using Standardization"
date: 2025-05-08
categories: [statistics, beginner]
tags: [z-score, standardization, variability, distribution, outliers]
math: true
description: "Understand z-scores and standardization — how far a value is from the mean, and why it's a powerful tool in comparing values across distributions and machine learning tasks."

---

Have you ever scored 90 on a test and wondered: *Is that impressive or just average?*  
To answer that, you need more than just the number — you need to know how it compares to others. That’s exactly what a **Z-score** helps you do.

A **Z-score** tells you how far a value is from the mean in terms of standard deviations. It’s one of the most useful tools in statistics and machine learning for comparing values across different distributions, detecting outliers, and standardizing data for models.

In this post, you’ll learn what Z-scores are, how to calculate and interpret them, and how they’re used in real-world analysis.


---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/variance-standard-deviation/">Measuring Variability: Variance and Standard Deviation</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/full-case-study/">Real Example: Putting It All Together</a></p>
</div>

---

## 🎯 <span style="color:#1E90FF;">What is a Z-Score?</span>

A **Z-score** (or standard score) tells you:

> ❓ “How many standard deviations is this value away from the mean?”

It answers:
- Is this value **above or below average**?
- Is it **unusual or common** in this distribution?

---


## 🤖 Why Z-Scores Matter in Machine Learning

Z-scores are used to:
- **Standardize features** (essential for models like KNN, SVM, logistic regression)
- **Detect outliers** in high-dimensional data
- **Compare different variables** on the same scale
- Improve **feature scaling** and **model convergence**

Z-scores make raw values comparable across features and distributions.

---

## 🧮 <span style="color:#FFA500;">Z-Score Formula</span>

\\[
z = \frac{x - \bar{x}}{\sigma}
\\]

This formula transforms a raw score \\( x \\) into a standardized score:

- The numerator \\( x - \bar{x} \\) tells us how far the value is from the mean  
- The denominator \\( \sigma \\) scales this difference using standard deviation  
- The result is a unit-free number (z-score) showing its relative position

Where:
- \\( x \\): the observation  
- \\( \bar{x} \\): the mean  
- \\( \sigma \\): the standard deviation

---

## 📊 <span style="color:#228B22;">Example: One Observation</span>

Suppose:
- Mean = 70  
- Standard Deviation = 10  
- Observation = 85

Then:

\\[
z = \frac{85 - 70}{10} = 1.5
\\]

🟢 The value is **1.5 standard deviations above** the mean.

Now try:

\\[
z = \frac{60 - 70}{10} = -1
\\]

🔵 This one is **1 standard deviation below** the mean.

---

## 📈 <span style="color:#9370DB;">How to Interpret Z-Scores</span>

- **Positive z-score** → Above the mean  
- **Negative z-score** → Below the mean  
- **z = 0** → Exactly the mean

Z-scores show where a value lies **on the distribution curve**.

📌 When the distribution is **skewed**:
- Right-skewed → Large z-scores occur more often in the tail  
- Left-skewed → Negative z-scores dominate the lower tail

---

## 📉 <span style="color:#20B2AA;">Empirical Rules and Z-Score Ranges</span>

There’s a general understanding of how much data falls in certain z-score ranges:

| Z-Score Range | Approx. % of Data |
|---------------|-------------------|
| -1 to +1      | ~68%              |
| -2 to +2      | ~75%              |
| -3 to +3      | ~89%              |

✅ So most values (especially in bell-shaped distributions) lie between -2 and +2.

---
## 🖼️ Visual Insight: Z-Scores and the Normal Distribution

The Z-score works best with **normally distributed data**. Here's how the values are typically spread:

![Normal distribution curve labeled with z-scores from -3 to +3, showing the 68-95-99.7 rule for standard deviation spread.](/assets/images/zscore_distribution.png)

- ~68% of values fall between z = -1 and +1  
- ~95% fall between z = -2 and +2  
- ~99.7% fall between z = -3 and +3  

> ✅ Use this to visually estimate how common or rare a value is based on its Z-score.

---

## 🔁 <span style="color:#FF6347;">Z-Score Always Balances</span>

If you compute z-scores for a full dataset, their **sum is always zero**:

\\[
\sum z = 0
\\]

That’s because the deviations above and below the mean **cancel out**.

---

## 🧪 <span style="color:#F06500;">Multiple Z-Scores from a Dataset</span>

Let’s say we have a dataset of exam scores:  
{70, 80, 90}

**Step 1** — Find the mean and standard deviation:  
- Mean = \\( \bar{x} = 80 \\)  
- Standard deviation =  
  \\[
  \sigma = \sqrt{\frac{(70-80)^2 + (80-80)^2 + (90-80)^2}{3}} = \sqrt{66.67} \approx 8.16
  \\]

**Step 2** — Compute z-scores for each value:

\\[
z_{70} = \frac{70 - 80}{8.16} \approx -1.22
\\]

\\[
z_{80} = \frac{80 - 80}{8.16} = 0
\\]

\\[
z_{90} = \frac{90 - 80}{8.16} \approx 1.22
\\]




These scores tell us:
- 70 is below average  
- 80 is exactly the average  
- 90 is above average

✅ The sum of these z-scores ≈ 0, confirming the rule.

---

## ⚖️ <span style="color:#1E90FF;">Comparing Across Distributions</span>

Let’s say we have two distributions:

### Test A:
- Mean = 60, SD = 5  
- Observation = 70  
\\[
z = \frac{70 - 60}{5} = 2
\\]

### Test B:
- Mean = 85, SD = 10  
- Observation = 90  
\\[
z = \frac{90 - 85}{10} = 0.5
\\]

📌 Although 90 is numerically higher, it is **less exceptional** in Test B than 70 is in Test A.

---

## 🌍 <span style="color:#20B2AA;">This is Called Standardization</span>

**Standardization** means:
> Expressing a value in terms of **how far it is from the mean**, using the standard deviation.

It lets us:
- Compare scores from different tests
- Identify outliers
- Normalize data for machine learning

---

<details class="level-up-box">
  <summary class="level-up-title">🧠 Level Up: How Z-Scores Power Real Analysis</summary>
  <div class="level-up-content">
    <p>Z-scores are useful not just for detecting outliers or comparing scores, but also in **statistical inference** and **ML pipelines**. Here's how they're used in real-world applications:</p>
    <ul>
      <li>🎯 <strong>Probability:</strong> Z-scores help us estimate how likely a value is in a normal distribution — using z-tables</li>
      <li>📏 <strong>Confidence Intervals:</strong> Z-scores define the range of values we expect sample means to fall within</li>
      <li>🚨 <strong>Outlier Detection:</strong> Observations with <code>|z| > 2</code> or <code>|z| > 3</code> are often flagged as potential outliers</li>
      <li>🔄 <strong>Standardization:</strong> Machine learning models often require data to be normalized using z-scores</li>
    </ul>
    <p class="mb-0">You’ll see these ideas come to life as we explore probability and inference in upcoming posts.</p>
  </div>
</details>
---
{% include quiz/zscore.html %}

---

## 🧠 Summary

| Concept           | What It Means                                | Practical Use                         |
|-------------------|-----------------------------------------------|----------------------------------------|
| Z-score           | Distance from mean in standard deviations     | Normalization, outlier detection       |
| Positive z        | Above average                                 | High-performing observation            |
| Negative z        | Below average                                 | Underperformance or anomaly            |
| z = 0             | Exactly average                               | Benchmark reference point              |
| Sum of all z      | Zero in a complete dataset                    | Confirms correct standardization       |

---

💬 **Have a question or want to compare z-scores from your own dataset?**  
Drop it in the comments — happy to help!

---

## ✅ Up Next

Next, we’ll walk through a **real-life example** that uses everything we’ve learned:
- Mean
- Median
- Standard deviation
- Z-scores  
And how to interpret and compare them together.

Stay tuned!

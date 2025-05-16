---
layout: post
title: "Z-Score: Comparing Values Using Standardization"
date: 2025-05-08
categories: [statistics, beginner]
tags: [z-score, standardization, variability, distribution, outliers]
math: true
---

What if you had **one number** and wanted to know whether it’s *common* or *exceptional*?  
For example, is a score of 90 on a test considered average — or much higher than typical?

That’s where the **Z-score** comes in.

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

<details class="border rounded p-3 bg-light my-4">
  <summary class="fw-bold text-primary">🧠 Level Up: How Z-Scores Power Real Analysis</summary>
  <div class="mt-2">
    <p>Z-scores are more than just a tool for comparing test scores. They're the foundation for some of the most powerful techniques in statistics and machine learning:</p>
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

| Concept           | What It Means                                |
|-------------------|-----------------------------------------------|
| Z-score           | # of standard deviations from the mean        |
| Positive z        | Above average                                 |
| Negative z        | Below average                                 |
| z = 0             | Exactly the mean                              |
| Sum of all z      | Always equals 0 in a full dataset             |
| Use case          | Comparing values across distributions         |

---

## ✅ Up Next

Next, we’ll walk through a **real-life example** that uses everything we’ve learned:
- Mean
- Median
- Standard deviation
- Z-scores  
And how to interpret and compare them together.

Stay tuned!

---
layout: post
title: "Z-Score: Comparing Values Using Standardization"
date: 2025-01-08
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

{% include quiz/zscore.html %}


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

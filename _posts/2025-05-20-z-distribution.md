---
layout: post
title: "Understanding Z-Distribution and Using the Z-Table"
date: 2025-05-20
categories: [statistics, beginner]
tags: [z-distribution, standard normal, z-table, statistics]
math: true
---

## 📌 <span style="color:#228B22; font-weight:bold;"> What is Z-Distribution? </span>

The **Z-distribution** (or **standard normal distribution**) is a special case of the normal distribution with:

- Mean \\( \mu = 0 \\)
- Standard deviation \\( \sigma = 1 \\)

It is used to standardize different normal distributions to a common scale.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/normal-distr/" style="color:#FF6F61;">Understanding Normal Distribution</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/binomial-distribution/" style="color:#1E90FF;">Understanding Binomial Distribution</a></p>
</div>

---

## 🔢 <span style="color:#FFA500; font-weight:bold;">Why do we use Z-Distribution?</span>

If you want to find the probability or the space far from the mean by any value (like <span style="color:#D2691E;">1.3</span>), the Z-distribution helps by converting your values into a standardized form.

---

## 🔄 <span style="color:#1E90FF; font-weight:bold;"> Converting Between X and Z </span>

To work with any normal distribution, you first convert values \\( X \\) to their corresponding Z-scores:

\\[
Z = \frac{X - \mu}{\sigma}
\\]

And vice versa:

\\[
X = Z \times \sigma + \mu
\\]

---

## 📊 <span style="color:#8A2BE2; font-weight:bold;"> Understanding the Cumulative Z-Table </span>

The **Z-table** (or standard normal table) shows the cumulative probability for the standard normal distribution \\( Z \\).

- It gives the probability that a standard normal variable \\( Z \\) is **less than or equal to** a given value.
- In other words, it shows the area under the curve **to the left** of a Z-score.
- Values in the table range from 0 to 1 because they represent probabilities.

### How to Read the Z-Table

1. Find the **row** corresponding to the first two digits and the first decimal place of your Z-score.
2. Find the **column** corresponding to the second decimal place of your Z-score.
3. The value where the row and column intersect is the cumulative probability.

For example, to find the cumulative probability for \\( Z = 1.23 \\):
- Look at the row for <span style="color:#D2691E;">1.2</span>
- Look at the column for <span style="color:#D2691E;">0.03</span>
- The table value at this intersection is approximately <span style="color:#FF4500; font-weight:bold;">0.8907</span>

This means \\( P(Z \leq 1.23) = 0.8907 \\).

---

## 🧮 <span style="color:#2E8B57; font-weight:bold;"> Example: Using the Z-Table </span>

Suppose you want to find the probability that a standard normal variable \\( Z \\) is less than <span style="color:#D2691E;">1.23</span>.

- Locate <span style="color:#D2691E;">1.2</span> in the rows.
- Locate <span style="color:#D2691E;">0.03</span> in the columns.
- The value in the table is <span style="color:#FF4500; font-weight:bold;">0.8907</span>.

Thus, \\( P(Z \leq 1.23) = 0.8907 \\), meaning there is an **89.07% chance** that \\( Z \\) is less than or equal to 1.23.

---

## 🔄 <span style="color:#1E90FF; font-weight:bold;"> Summary of Using the Z-Table with Any Normal Distribution </span>

- First, convert your \\( X \\) value to a Z-score using:

\\[
Z = \frac{X - \mu}{\sigma}
\\]

- Then, use the Z-table to find the cumulative probability for that Z.
- If you want the probability between two values, find the cumulative probabilities for both and subtract the smaller from the larger.

---

## 📊 Visual Aid: Sample Z-Table (Partial)

| Z     | .00  | .01  | .02  | .03  | .04  |
|-------|-------|-------|-------|-------|-------|
| 1.2   | 0.8849 | 0.8869 | 0.8888 | <span style="color:#FF4500; font-weight:bold;">0.8907</span> | 0.8925 |
| 1.3   | 0.9032 | 0.9049 | 0.9066 | 0.9082 | 0.9099 |

*The value for Z=1.23 is highlighted.*

---

## 🧮  <span style="color:#8A2BE2; font-weight:bold;"> Example: Finding Probability Between Two Values </span>

Suppose \\( X \\) is normally distributed with mean \\( \\mu = 3 \\) and standard deviation \\( \sigma = 1 \\). We want to find the probability that \\( X \\) lies between <span style="color:#D2691E;">2</span> and <span style="color:#D2691E;">5</span>.

### Step 1: Convert \\( X \\) values to Z-scores

\\[
Z = \\frac{X - \\mu}{\\sigma}
\\]

Calculate:

 \\[
Z_1 = \\frac{2 - 3}{1} = -1
 \\]

\\[
Z_2 = \\frac{5 - 3}{1} = 2
\\]

### Step 2: Find cumulative probabilities using the Z-table

- The cumulative probability for \\( Z_2 = 2 \\) is approximately <span style="color:#FF4500; font-weight:bold;">0.9772</span>.
- The cumulative probability for \\( Z_1 = -1 \\) is approximately <span style="color:#FF4500; font-weight:bold;">0.1587</span>.

### Step 3: Subtract to get the probability between the two values
\\[
P(2 < X < 5) = P(Z < 2) - P(Z < -1) = 
\\]
<span style="color:#FF4500; font-weight:bold;">0.9772 - 0.1587 = 0.8185</span>


So, there is an approximately **81.85%** chance that \\( X \\) lies between 2 and 5.

---

### Visuals

Below are shaded regions representing these cumulative probabilities:

- Area below \\( X = 5 \\):

- Area below \\( X = 2 \\):

![Region below 2 and 5](./assets/images/region_below_5.png)

---

## 🔟 Example: 10th Percentile Duration

To find the 10th percentile, find the Z-score corresponding to 0.10 cumulative probability in the Z-table, then convert it back to \\( X \\):

\\[
X = Z_{0.10} \times \sigma + \mu
\\]

---

## 🔄 <span style="color:#228B22; font-weight:bold;"> Why Conversion Is Useful Beyond Normal Distributions </span>

Converting \\( X \\) to \\( Z \\) can be applied to various data types and distributions, not just normal ones. It standardizes data for easier comparison and probability calculations.

---

<details class="border rounded p-3 bg-light my-4">
  <summary class="fw-bold text-primary">🧠 Level Up: Deep Dive into Z-Distribution</summary>
  <div class="mt-2" style="line-height:1.5; font-size: 0.95rem;">
    <ul>
      <li>The Z-distribution is a powerful tool for standardizing and comparing data across different normal distributions.</li>
      <li>It plays a key role in hypothesis testing, confidence interval calculation, and many inferential statistics methods.</li>
      <li>The cumulative distribution function (CDF) and its inverse (quantile function) allow us to compute probabilities and critical values.</li>
      <li>Learning to interpret Z-scores helps in identifying outliers and understanding data spread relative to the mean.</li>
      <li>Remember, the Z-table provides cumulative probabilities from the far left up to any Z-score, but you can also calculate tail probabilities for ranges beyond.</li>
    </ul>
  </div>
</details>

---


{% include quiz/z-distribution.html %}

---


## ✅ <span style="color:#228B22; font-weight:bold;">Summary</span>

| Concept                      | Description                                                     |
|------------------------------|-----------------------------------------------------------------|
| Z-Distribution               | Standard normal distribution with mean \\( \mu=0 \\), \\( \sigma=1 \\) |
| Z-Score                     | Measures how many standard deviations a value is from the mean: \\( Z = \\frac{X - \\mu}{\\sigma} \\) |
| Cumulative Z-Table          | Gives the probability \\( P(Z \leq z) \\), area under the curve to the left of \\( z \\) |
| Finding Probability Between Two Values | Convert \\( X \\) values to Z-scores, look up cumulative probabilities, subtract to find the probability between |
| Percentiles                 | Use Z-scores from the cumulative table and convert back to \\( X \\) values for interpretation |


---

## 🔜 Up Next

Next, we’ll explore the **Binomial Distribution** — a fundamental discrete distribution used to model the number of successes in a fixed number of independent trials.

Stay tuned!


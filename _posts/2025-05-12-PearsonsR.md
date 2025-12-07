---
layout: post
title: "Pearson’s r: Measuring the Strength and Direction of Linear Relationships"
date: 2025-05-12
categories: [statistics,Descriptive statistics, beginner]
tags: [pearsons-r, correlation, linear-relationship, scatter-plot, data-analysis]
math: true
description: Learn how Pearson’s r measures the strength and direction of linear relationships between variables. Includes formula breakdown, Python code, and machine learning relevance.

---
How strongly are two variables related — and in what direction? That’s exactly what **Pearson’s correlation coefficient (r)** helps us measure. 

In this post, you’ll learn what Pearson’s r is, how to calculate it, when to use it, and how it fits into data science and machine learning workflows. We’ll break it down with formulas, visualizations, and Python code so you can apply it confidently in your own projects.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/correlation-contingency-scatter/">Correlation Between Variables: Contingency Tables and Scatter Plots</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/Regression/">Regression: Predicting Relationships Between Variables</a></p>
</div>

---
## 🎯 **Types of Correlation**

There are four main types of correlation you may encounter in data:

1. **Strong Positive Linear Relationship**  
   - As one variable increases, the other increases in a **perfect straight line**.
   
2. **Weak Positive Linear Relationship**  
   - The variables increase together, but not in a perfect linear fashion.
   
3. **Strong Negative Linear Relationship**  
   - As one variable increases, the other decreases in a **perfect straight line**.

4. **Perfect Negative Linear Relationship**  
   - A perfect inverse relationship, where every increase in one variable exactly corresponds to a decrease in the other.

However, **not all relationships are linear**. Many datasets show **curves** or **non-linear relationships**, where Pearson’s r would not be applicable.

---

**Visualizing the Types of Correlation and Linear vs Non-Linear Relationships:**

![Correlation and Relationship Types](/assets/images/PearsonsR.png)

---

## 📊 **Why Scatter Plots Alone Aren’t Enough**

A **scatter plot** helps visualize the relationship between two variables, but it **doesn't quantify** how strong or weak the correlation is.  

The scatter plot might show a **weak** or **strong** relationship, but it doesn't give you a precise measurement. For that, we use **Pearson’s r**, which **quantifies** both the strength and direction of the relationship.

### 🧮 **The Equation for Pearson’s r**

Pearson’s r is calculated as:

\\[
r = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum (x_i - \bar{x})^2 \sum (y_i - \bar{y})^2}}
\\]

Where:
- \\( x_i \\) = data points of variable X
- \\( y_i \\) = data points of variable Y
- \\( \bar{x} \\) = mean of variable X
- \\( \bar{y} \\) = mean of variable Y

---

### 📈 **How Pearson’s r Works**

Pearson’s r produces a value between **-1** and **+1**:

- **r = +1** → **Perfect positive correlation**
- **r = -1** → **Perfect negative correlation**
- **r = 0** → **No correlation**
- **0 < r < 1** → **Positive relationship** (but not perfect)
- **-1 < r < 0** → **Negative relationship** (but not perfect)

#### **Interpretation**:
- **Strength**: The closer Pearson’s r is to **+1** or **-1**, the **stronger** the relationship.
- **Direction**: 
  - **Positive** (+) = as one variable increases, the other increases
  - **Negative** (-) = as one variable increases, the other decreases

---
## 🤖 Why Pearson’s r Matters in Machine Learning

Pearson’s r is more than just a statistic — it's a critical tool in feature selection and exploratory data analysis (EDA) in machine learning:

- ✅ Helps detect **linear relationships** between features and target variables.
- 📉 Can reveal **redundant features** (multicollinearity) that affect model stability.
- 🔍 Commonly used in **correlation matrices** for dimensionality reduction or preprocessing.

Understanding correlation guides better **feature engineering**, a key step for improving model performance.

---
## 📉 **Visualizing Pearson’s r: How the Data Points Collect Around the Line**

Let’s consider how the points align along the line. A **strong correlation** means the data points are tightly grouped along a straight line.

- **Perfect Correlation**: Data points lie exactly along the line.
- **Weak Correlation**: Data points are spread out, but still follow the general trend.
- **No Correlation**: Data points are scattered randomly.

---

## 🧪 **Example Calculation**

Let’s walk through a small example:

Data:

| X   | Y   |
| --- | --- |
| 1   | 3   |
| 2   | 4   |
| 3   | 6   |
| 4   | 8   |
| 5   | 10  |

Now calculate Pearson’s r:

1. Calculate the **means**:
   - \\( \bar{x} = 3 \\)
   - \\( \bar{y} = 6.2 \\)

2. Calculate the **numerator** of the formula:

\\[
\sum (x_i - \bar{x})(y_i - \bar{y}) = (1-3)(3-6.2) + (2-3)(4-6.2) + (3-3)(6-6.2) + (4-3)(8-6.2) + (5-3)(10-6.2)
\\]

\\[
= 4.4 + 2.2 + 0 + 2.2 + 2.4 = 11.2
\\]

3. Calculate the **denominator** of the formula (the squared deviations for both variables):

\\[
\sum (x_i - \bar{x})^2 = (1 - 3)^2 + (2 - 3)^2 + (3 - 3)^2 + (4 - 3)^2 + (5 - 3)^2 = 4 + 1 + 0 + 1 + 4 = 10
\\]

\\[
\sum (y_i - \bar{y})^2 = (3 - 6.2)^2 + (4 - 6.2)^2 + (6 - 6.2)^2 + (8 - 6.2)^2 + (10 - 6.2)^2 = 10.24 + 4.84 + 0.04 + 3.24 + 14.44 = 32.8
\\]

4. Now calculate Pearson’s r:

\\[
r = \frac{11.2}{\sqrt{10 \times 32.8}} = \frac{11.2}{\sqrt{328}} = \frac{11.2}{18.1} \approx 0.62
\\]

This means the correlation is **moderately strong positive**, but **not perfect**.

---

### 🧑‍💻 **Python Code for Pearson’s r**

You can also calculate Pearson’s r using Python's `numpy`:

```python
import numpy as np

# Data
x = np.array([1, 2, 3, 4, 5])
y = np.array([3, 4, 6, 8, 10])

# Calculate Pearson's r
r = np.corrcoef(x, y)[0, 1]
print("Pearson's r:", r)

```
---

<details class="level-up-box">
<summary class="level-up-title">
🧠 Level Up: When Not to Use Pearson’s r</summary> <div class="level-up-content"> <p>Pearson’s r assumes a <b>linear relationship</b> between two variables. But what if the data forms a <b>curve</b> ? </p> <ul> <li>📊 If your data is <b> non-linear </b>, Pearson’s r won’t give you an accurate measure of correlation. The relationship might look like a U-shape or exponential curve, which Pearson’s r can’t capture.</li> <li>🔄 For <b> non-linear relationships </b>, try using <b> Spearman’s rank correlation </b>, which assesses monotonic relationships (whether increasing or decreasing).</li> <li>🎯 Always visualize the data first with a scatter plot to check if the relationship is linear before calculating Pearson’s r.</li> </ul> <p>Understanding when Pearson’s r applies — and when it doesn’t — is key to reliable data analysis.</p> </div> </details>

---
<details class="custom-box custom-best">
  <summary><strong>✅ Best Practices for Using Pearson’s r</strong></summary>
  <ul>
    <li>Always plot a <strong>scatter plot first</strong> to verify linearity.</li>
    <li>Use Pearson’s r for <strong>continuous, quantitative variables</strong>.</li>
    <li>Report both the <strong>r-value and a visual</strong> for context.</li>
  </ul>
</details>
---
<details class="custom-box custom-warning">
  <summary><strong>⚠️ Common Pitfalls</strong></summary>
  <ul>
    <li>❌ Using Pearson’s r on <strong>non-linear relationships</strong>.</li>
    <li>❌ Assuming correlation = causation — r only shows association.</li>
    <li>❌ Using it on <strong>ordinal or categorical data</strong>.</li>
  </ul>
</details>

---
{% include quiz/pearsons-r.html %}

---

## 🔁 <span style="color:#1E90FF;">Summary</span>

| Relationship Type | Pearson’s r Interpretation |
| ----------------- | -------------------------- |
| Strong Positive   | \( r = +1 \)               |
| Weak Positive     | \( 0 < r < 1 \)            |
| Strong Negative   | \( r = -1 \)               |
| No Correlation    | \( r = 0 \)                |

---
## 💬 Got a question or suggestion?

Leave a comment below — I’d love to hear your thoughts or help if something was unclear.

---
## 🎯 Up Next: Regression - Predicting Relationships Between Variables

In our upcoming post, we will delve into **regression analysis**, which goes beyond correlation to help us **predict** the value of one variable based on another. 

### Key points we will cover:
1. **What is regression?**
2. **Linear regression equation** and its components
3. **How to interpret the regression line** in a scatter plot
4. **How regression helps us predict future values**

Stay tuned as we explore this essential technique that forms the backbone of predictive modeling and machine learning!

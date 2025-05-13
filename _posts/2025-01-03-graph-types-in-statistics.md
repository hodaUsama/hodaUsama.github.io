---
layout: post
title: "Choosing the Right Graph: How to Visualize Your Data in Statistics"
date: 2025-01-03
categories: [statistics, beginner]
tags: [graphs, data-types, histogram, pie-chart, bar-chart]
---
When you collect data, your next big step is to understand it — and the best way to do that is to **visualize it**.

But not every graph works for every type of data.

In this post, we’ll explore:
- How to choose a graph based on your <span style="color:#1E90FF;"><strong>data type</strong></span>
- The difference between <span style="color:#32CD32;">bar charts, pie charts, and histograms</span>
- The different <span style="color:#FF8C00;">shapes of histograms</span> (and what they tell us)

---
---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/cases-variables-frequency-table/">Descriptive vs Inferential Statistics</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/frequency-tables-python/">Choosing the Right Graph: How to Visualize Your Data</a></p>
</div>

---
## 📋 <span style="color:#1E90FF;">1. Categorical Data: Nominal and Ordinal</span>

**Categorical data** includes labels, names, or categories.

There are two types:

- <strong>Nominal</strong>: No order (e.g., eye color, favorite food)  
- <strong>Ordinal</strong>: Ordered categories (e.g., rating from poor to excellent)

### 🔹 Best graphs for categorical data:

### <span style="color:#32CD32;">Bar Chart</span>
- Each category is a separate bar  
- Bar height = frequency  
- Bars are <strong>separated</strong> (not touching)

### <span style="color:#20B2AA;">Pie Chart</span>
- Shows parts of a whole  
- Best when you want to show percentages or proportions

💡 <span style="color:#FF6347;">Tip:</span> Bar charts are usually <strong>easier to read</strong> than pie charts — especially with many categories.

---

## 📊 <span style="color:#228B22;">2. Quantitative Data: Interval and Ratio</span>

**Quantitative data** is numerical, like height, age, or test scores.

This includes:
- <strong>Interval</strong>: No true zero (e.g., temperature in °C)
- <strong>Ratio</strong>: Has a true zero (e.g., weight, age)

### 🔸 Best graph for quantitative data:

### <span style="color:#FF8C00;">Histogram</span>
- Bins or intervals group data (e.g., ages 10–19, 20–29, etc.)
- Bars are <strong>connected</strong> to show continuous data

---

## 🧠 <span style="color:#FF6347;">3. Types of Histogram Shapes</span>

Histograms don’t just show data — their <strong>shapes</strong> tell a story.

### 📈 Bell-Shaped (Normal)
- Most data is in the center
- Few values at the extremes
- Example: IQ scores, height

### 🔄 Skewed Right (Positive Skew)
- Long tail on the right
- Most values are low
- Example: Income (most people earn little, few earn a lot)

### 🔃 Skewed Left (Negative Skew)
- Long tail on the left
- Most values are high
- Example: Age of retirement (most people retire around 60–65)

### ⛰️ Bimodal (Two Peaks)
- Two distinct groups in the data
- Example: Test scores from two different classes

---

## 🖼️ Visual Guide to Histogram Shapes

![Histogram Shapes](assets/images/histogram_shapes.png)

---
{% include quiz/graph-types.html %}

---

## 🧾 Summary Table

| <span style="color:#1E90FF;">Data Type</span>     | <span style="color:#228B22;">Graph Type</span>     | Use When…                            |
|------------------|--------------------|--------------------------------------|
| Nominal          | Bar, Pie           | Categories with no order             |
| Ordinal          | Bar                | Ordered categories                   |
| Interval/Ratio   | Histogram          | Numeric data (continuous)            |

---

## ✅ Up Next

We’ll build on this and create <strong>frequency tables</strong> — the building blocks behind many of these graphs!


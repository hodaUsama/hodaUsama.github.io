---
layout: post
title: "How to Build Frequency Tables in Python (With Charts)"
date: 2025-05-04
categories: [statistics,Descriptive statistics, beginner]
tags: [frequency-table, python, bar-chart, histogram]
description: "Learn how to create frequency tables in Python for both categorical and numerical data using Counter, pandas, and numpy — and visualize them with bar charts and histograms."

---
Before building a machine learning model or exploring data in Python, you need to understand how your data is distributed. This guide walks you through creating frequency tables for both categorical and continuous data — and visualizing them using bar charts and histograms with Python libraries like pandas, numpy, and matplotlib.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/graph-types-in-statistics/">Choosing the Right Graph: How to Visualize Your Data</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/central-tendency/">Measuring the Center: Mean, Median, and Mode Explained</a></p>
</div>

---
👉 <strong>Understand your data.</strong>

That’s where <span style="color:#1E90FF;"><strong>frequency tables</strong></span> come in — they help you summarize your raw data and reveal hidden patterns. In this post, you’ll learn how to create frequency tables in Python and visualize them with charts.

We’ll cover:

✔️ What frequency tables are  
✔️ Why they matter  
✔️ How to build them for both categorical and numerical data  
✔️ How to plot them with bar charts and histograms

---

## 📊 <span style="color:#1E90FF;">What is a Frequency Table?</span>

A frequency table shows how often each value appears in your data. It’s a way to take messy raw numbers and turn them into something readable — a summary that helps you spot patterns fast.

🟡 Imagine you asked 20 people about their <strong>favorite fruit</strong>. Here's the data:

```python
fruits = ['apple', 'banana', 'apple', 'orange', 'banana', 'banana',
          'apple', 'banana', 'orange', 'apple', 'banana', 'banana',
          'orange', 'apple', 'apple', 'banana', 'banana', 'apple',
          'orange', 'banana']
```

We want to know: how many chose each fruit?

---

## 🔢 <span style="color:#228B22;">Step 1: Count Frequencies for Categorical Data</span>

```python
from collections import Counter

fruit_counts = Counter(fruits)
print(fruit_counts)
```

📌 Output:
```
Counter({'banana': 9, 'apple': 7, 'orange': 4})
```

🎯 This is your frequency table. It tells you that:
- 9 people chose banana 🍌  
- 7 people chose apple 🍎  
- 4 people chose orange 🍊

---
### 🐼 Alternative: Using pandas for frequency tables

If your data is in a pandas DataFrame, you can use `value_counts()` for one way tables and `pd.crosstab()` for two way tables.

```python
import pandas as pd

df = pd.DataFrame({'fruit': fruits})

# One way frequency table
print(df['fruit'].value_counts())
```
Example output:

```python
banana    9
apple     7
orange    4
Name: fruit, dtype: int64
```
### 🔄 Two-Way Frequency Tables (Contingency Tables)

```python
df = pd.DataFrame({
    'fruit': ['apple', 'banana', 'apple', 'orange', 'banana', 'banana'],
    'color': ['red', 'yellow', 'green', 'orange', 'yellow', 'green']
})

table = pd.crosstab(df['fruit'], df['color'])
print(table)
```

Example output:

```python
color   green  orange  red  yellow
fruit                            
apple       1       0    1       0
banana      1       0    0       2
orange      0       1    0       0

```

### 📈 Relative and cumulative frequency

So far we counted how many times each value appears. You can also look at:

- **Relative frequency** - the proportion or percentage of the total  
- **Cumulative frequency** - the running total as you move through ordered values

Using pandas, relative frequency is easy:

```python
import pandas as pd

df = pd.DataFrame({'fruit': fruits})

freq = df['fruit'].value_counts()
rel_freq = df['fruit'].value_counts(normalize=True)

print("Frequency:")
print(freq)
print("\nRelative frequency:")
print(rel_freq)

```
Example output:

```python
Frequency:
banana    9
apple     7
orange    4
Name: fruit, dtype: int64

Relative frequency:
banana    0.45
apple     0.35
orange    0.20
Name: fruit, dtype: float64

```
For ordered numerical data, you can also compute cumulative frequency:
```python
scores = pd.Series([85, 90, 85, 88, 92, 85, 90])

freq = scores.value_counts().sort_index()
cum_freq = freq.cumsum()

print("Frequency:")
print(freq)
print("\nCumulative frequency:")
print(cum_freq)


```


## 📊 <span style="color:#FFA500;">Step 2: Visualize It with a Bar Chart</span>

```python
import matplotlib.pyplot as plt

plt.bar(fruit_counts.keys(), fruit_counts.values(), color='skyblue', edgecolor='black')
plt.title("Favorite Fruit Survey")
plt.xlabel("Fruit")
plt.ylabel("Frequency")
plt.show()
```

🧠 This simple chart helps you immediately see which fruit is most popular — **bar charts** are perfect for categorical data.

---

## 📏 <span style="color:#20B2AA;">Step 3: Frequency Table for Numerical Data</span>

What if your data is continuous? Like **heights** or **ages**?

Let’s simulate 50 students’ heights:

```python
import numpy as np

heights = np.random.normal(loc=165, scale=10, size=50)
bins = [140, 150, 160, 170, 180, 190]
```

Now create a frequency table using intervals:

```python
counts, bin_edges = np.histogram(heights, bins=bins)

for i in range(len(counts)):
    print(f"{int(bin_edges[i])}–{int(bin_edges[i+1])}: {counts[i]}")
```

📌 Output (varies by run):
```
140–150: 2
150–160: 6
160–170: 21
170–180: 15
180–190: 6
```

This means:
- Most students are in the 160–170 cm range  
- Very few are shorter than 150 or taller than 180

---

## 📉 <span style="color:#9370DB;">Step 4: Plot It with a Histogram</span>


```python
plt.hist(heights, bins=bins, color='lightgreen', edgecolor='black')
plt.title("Height Distribution")
plt.xlabel("Height (cm)")
plt.ylabel("Frequency")
plt.show()
```

Unlike bar charts, <strong>histograms</strong> have connected bars — they’re designed for continuous data.
![Frequency Table Charts](assets/images/frequency_table_charts.png)

---
> **Tip:**  
> For discrete numerical data (like test scores), you can also use `value_counts()` to create a frequency table:

 ```python
import pandas as pd
scores = [85, 90, 85, 88, 92, 85, 90]
pd.Series(scores).value_counts().sort_index()
 ```

> **Histogram Best Practices:**  
> - Always label your x-axis and y-axis clearly, including units (e.g., "Height (cm)").  
> - Use a consistent y-axis scale when comparing multiple histograms.  
> - Start the y-axis at zero unless there is a strong reason not to, and indicate clearly if you do otherwise.

---

## 🧠 <span style="color:#FF6347;">Why Frequency Tables Matter</span>

- They help you <strong>understand distributions</strong> at a glance.  
- Let you <strong>detect outliers, rare categories, or unexpected values</strong>.  
- Support <strong>data preparation for machine learning</strong>, for example:
  - Choosing how to encode categorical variables.  
  - Deciding how to group continuous values into bins.  
  - Detecting strong class imbalance before training a classifier.  

Frequency tables are also a first step toward more advanced tools such as descriptive statistics, histograms, box plots, and probability distributions.

---
<details class="custom-box custom-best">
  <summary><strong>✅ Best practices for frequency tables and histograms</strong></summary>

  <ul>
    <li>
      <strong>Start with simple counts.</strong>
      Build a basic frequency table to see which categories or values are common and which are rare before doing more complex analysis.
    </li>
    <li>
      <strong>Sort tables in a meaningful way.</strong>
      For categorical data, sort by category or by frequency depending on what you want to highlight. For numeric values, sort by value to match the natural order.
    </li>
    <li>
      <strong>Use relative frequency when comparing groups.</strong>
      Convert counts to proportions or percentages when sample sizes differ between groups or datasets.
    </li>
    <li>
      <strong>Choose bins thoughtfully for numerical data.</strong>
      Pick bin edges that are easy to interpret and that match the scale of the data, rather than relying only on automatic binning.
    </li>
    <li>
      <strong>Combine tables with visualizations.</strong>
      Use bar charts and histograms alongside frequency tables so that patterns are visible both numerically and visually.
    </li>
  </ul>
</details>


---
<details class="custom-box custom-warning">
  <summary><strong>⚠️ Common pitfalls with frequency tables and histograms</strong></summary>

  <ul>
    <li>
      <strong>Using too many or too few bins.</strong>
      Very few bins can hide important structure, while too many bins can create noisy patterns that are hard to interpret.
    </li>
    <li>
      <strong>Ignoring missing values.</strong>
      If you do not handle missing values explicitly, frequency tables and histograms can give a misleading picture of the data.
    </li>
    <li>
      <strong>Not sorting numerical frequencies.</strong>
      For ordered or numeric data, leaving the index unsorted can make tables and bar charts harder to read.
    </li>
    <li>
      <strong>Mixing up bar charts and histograms.</strong>
      Bar charts are for categories, histograms are for continuous intervals. Using the wrong one can confuse the message.
    </li>
    <li>
      <strong>Reading counts without context.</strong>
      Large counts or bars can look impressive, but always interpret them relative to the total sample size and to other categories.
    </li>
  </ul>
</details>

---

<details class="level-up-box">
  <summary class="level-up-title">🧠 Level Up: Leveraging Frequency Tables for Deeper Data Insights</summary>
 <div class="level-up-content">
    <p>Frequency tables are more than simple counts — they’re powerful tools for exploring and preparing data:</p>
    <ul>
      <li>🔢 For <strong>categorical data</strong>, frequency tables reveal the distribution and highlight dominant categories.</li>
      <li>📊 For <strong>numerical data</strong>, grouping values into intervals in frequency tables helps uncover patterns and anomalies.</li>
      <li>🧑‍💻 Building frequency tables programmatically (e.g., with Python’s <code>pandas</code>) enables scalable and reproducible analysis.</li>
      <li>🎨 Visualizing frequency tables with bar charts or histograms bridges raw numbers to intuitive understanding.</li>
    </ul>
    <p>Mastering frequency tables will improve your data wrangling and make your visualizations more meaningful.</p>
  </div>
</details>

---

{% include quiz/frequency-tables.html %}

---
## ✅ Summary

| Task                      | Tool                |
| ------------------------- | ------------------- |
| Count categories          | `Counter()`         |
| Visualize categories      | Bar chart           |
| Group continuous data     | `numpy.histogram()` |
| Visualize continuous data | Histogram           |

---

## 🚀 Coming Next

In the next post, we’ll take this frequency data and calculate powerful summary statistics like:

- <strong>Mean</strong>  
- <strong>Median</strong>  
- <strong>Standard deviation</strong>

Stay tuned!

---
## 📺 Explore the Channel

<div style="max-width: 400px; margin: 30px auto; border: 1px solid #ccc; border-radius: 12px; padding: 16px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); text-align: center; font-family: sans-serif;">
  
  <img src="../assets/images/Hoda-Osama-Ai.png" alt="Hoda Osama AI Channel" style="width: 100%; border-radius: 8px;">

  <h3 style="margin-top: 16px; color: #333;">🎥 Hoda Osama AI</h3>
  <p style="color: #555;">Learn statistics and machine learning concepts step by step with visuals and real examples.</p>
  
  <a href="https://www.youtube.com/@Hoda_Osama_AI" target="_blank" rel="noopener noreferrer">
    <button style="margin-top: 12px; padding: 10px 20px; font-size: 16px; background-color: #FF0000; color: white; border: none; border-radius: 6px; cursor: pointer;">
      🔔 Subscribe on YouTube
    </button>
  </a>
</div>
---
## 💬 <span style="color:#4B0082;"> Got a Question? </span>

Leave a comment or open an issue on GitHub — I love connecting with other learners and builders. 🔁


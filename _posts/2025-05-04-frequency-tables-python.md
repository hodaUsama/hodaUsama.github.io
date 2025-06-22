---
layout: post
title: "How to Build Frequency Tables in Python (With Charts)"
date: 2025-05-04
categories: [statistics, beginner]
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

### 🐼 Alternative: Using pandas for Frequency Tables

If your data is in a pandas DataFrame (which is common in real projects), you can use `value_counts()` for one column or `pd.crosstab()` for two-way tables:


```python
import pandas as pd

df = pd.DataFrame({'fruit': fruits})

```
One-way frequency table
```python
print(df['fruit'].value_counts())
```
Two-way frequency table (example with another variable)

```python
df['color'] = ['red', 'yellow', ...] # Add another column if you have one
print(pd.crosstab(df['fruit'], df['color']))
undefined

```
### 🔄 Two-Way Frequency Tables (Contingency Tables)

To examine the relationship between two categorical variables, use `pd.crosstab()`:
```python
Example: Suppose you have 'fruit' and 'color' columns
df = pd.DataFrame({
'fruit': ['apple', 'banana', 'apple', 'orange', 'banana', 'banana'],
'color': ['red', 'yellow', 'green', 'orange', 'yellow', 'green']
})
print(pd.crosstab(df['fruit'], df['color']))
undefined
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



## 🧠 <span style="color:#FF6347;">Why Frequency Tables Matter</span>

- They help you <strong>understand distributions</strong> at a glance  
- Let you <strong>detect outliers</strong> or unexpected values  
- Help in preparing datasets for machine learning (e.g., binning or encoding)

They’re also a first step toward more advanced tools: descriptive statistics, histograms, boxplots, and beyond.

---
## ⚠️ Common Pitfalls 
 - Forgetting to sort frequency tables by value or category.  
 - Using too many or too few bins in histograms, which can hide patterns or create noise.  
 - Not handling missing values before counting frequencies.

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

| Task                             | Tool                |
|----------------------------------|---------------------|
| Count categories                 | `Counter()`         |
| Visualize categories             | Bar chart           |
| Group continuous data            | `numpy.histogram()` |
| Visualize continuous data        | Histogram           |

---
💬 **Got a question or suggestion?**  
Feel free to leave a comment in the section below — I’d love to hear your thoughts or help with your dataset!

---

## 🚀 Coming Next

In the next post, we’ll take this frequency data and calculate powerful summary statistics like:

- <strong>Mean</strong>  
- <strong>Median</strong>  
- <strong>Standard deviation</strong>

Stay tuned!

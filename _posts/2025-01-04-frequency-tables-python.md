---
layout: post
title: "How to Build Frequency Tables in Python (With Charts)"
date: 2025-01-04
categories: [statistics, beginner]
tags: [frequency-table, python, bar-chart, histogram]
---
Before you build a machine learning model or even run a single analysis, there's one thing you must do first:
---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/graph-types-in-statistics/">Descriptive vs Inferential Statistics</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/frequency-tables-python/">Choosing the Right Graph: How to Visualize Your Data</a></p>
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

## 🧠 <span style="color:#FF6347;">Why Frequency Tables Matter</span>

- They help you <strong>understand distributions</strong> at a glance  
- Let you <strong>detect outliers</strong> or unexpected values  
- Help in preparing datasets for machine learning (e.g., binning or encoding)

They’re also a first step toward more advanced tools: descriptive statistics, histograms, boxplots, and beyond.

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

## 🚀 Coming Next

In the next post, we’ll take this frequency data and calculate powerful summary statistics like:

- <strong>Mean</strong>  
- <strong>Median</strong>  
- <strong>Standard deviation</strong>

Stay tuned!

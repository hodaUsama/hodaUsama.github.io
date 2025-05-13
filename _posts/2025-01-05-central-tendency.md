---
layout: post
title: "Measuring the Center: Mean, Median, and Mode Explained"
date: 2025-01-05
categories: [statistics, beginner]
tags: [central-tendency, mean, median, mode, outliers, measurement-levels]
---

Before we jump into how data spreads, let’s understand how to find the **center** of it.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/frequency-tables-python/">How to Build Frequency Tables in Python</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/dispersion-range-iqr-boxplot/">Measures of Dispersion: Range, IQR, and Box Plot</a></p>
</div>

---

## 🎯 <span style="color:#1E90FF;">What is Central Tendency?</span>

Central tendency describes the **"middle" or typical value** in a dataset. The three main measures are:

- <strong style="color:#FF6347;">Mode</strong>
- <strong style="color:#FFA500;">Median</strong>
- <strong style="color:#228B22;">Mean</strong>

Each one tells us something slightly different.

---

## 🧮 <span style="color:#FF6347;">Mode</span>

- The **most frequent value** in a dataset
- Works with **any type of variable**
- Especially useful for **nominal (categorical)** data

💡 Example:
If most students choose “Math” as their favorite subject, then:
> Mode = "Math"

🛑 You can't calculate a **mean** or **median** for categories like “Math” or “History” — but you can find the mode.

---

## 🧭 <span style="color:#FFA500;">Median</span>

- The **middle value** when data is sorted
- Best used when data is **skewed or has outliers**
- Only works with **ordinal, interval, or ratio** variables

💡 Example:
For ages: [16, 17, 18, 40, 90]  
> Median = 18

✅ Median is **not affected by extreme values** — that's why it's preferred when there are outliers.

---

## ➕ <span style="color:#228B22;">Mean</span>

- The **arithmetic average**
- Add up all values, divide by the count
- Works well with **interval and ratio** variables

💡 Example:
Scores = [80, 85, 90]  
> Mean = (80 + 85 + 90) / 3 = 85

🛑 Not ideal when there are **outliers** — they can distort the average.

---

## 🖼️ Visual Comparison

Here’s a quick visual to help you compare the three measures:

![Central Tendency Illustration](/assets/images/MeasureMentOFCentralTendency.png)

- **Mode** = Most frequent
- **Median** = Middle value
- **Mean** = Balances all data values

---

## 📌 <span style="color:#9370DB;">Choosing the Right Measure</span>

| Measurement Level | Mode | Median | Mean |
|-------------------|------|--------|------|
| Nominal           | ✅   | ❌     | ❌   |
| Ordinal           | ✅   | ✅     | ❌   |
| Interval/Ratio    | ✅   | ✅     | ✅   |

⚠️ **Outliers** = values that are much higher or lower than the rest  
👉 When outliers exist, **median** is often more reliable than mean.

---
{% include quiz/central-tendency.html %}
---
## 🔁 <span style="color:#1E90FF;">Summary</span>

| Measure | Best For | Sensitive to Outliers? |
|---------|----------|------------------------|
| Mode    | Nominal, any variable | ❌ No     |
| Median  | Skewed/Ordinal data   | ❌ No     |
| Mean    | Symmetrical data only | ✅ Yes    |

---

## ✅ Up Next

In the next post, we’ll talk about how **spread out** your data is.  
That’s called **Measures of Dispersion** — including **Range**, **Interquartile Range**, and the **Box Plot**.

Stay curious!

---
layout: post
title: "Understanding Dispersion: Range, IQR, and the Box Plot"
date: 2025-01-06
categories: [statistics, beginner]
tags: [dispersion, range, IQR, boxplot, quartiles, outliers]

---

Now that we’ve learned how to measure the **center** of data, let’s talk about how data **spreads out** — that’s called **dispersion**.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/central-tendency/">Measuring the Center: Mean, Median, and Mode Explained</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/variance-standard-deviation/">Measuring Variability: Variance and Standard Deviation</a></p>
</div>

---

## 📏 <span style="color:#1E90FF;">Range: A Simple Start</span>

- **Range** = Largest value − Smallest value
- Gives a basic idea of **spread**
- But it’s **not reliable** for measuring variability if there are **outliers**

💡 Example:
If data = [5, 6, 6, 7, 95] → Range = 95 − 5 = 90  
🛑 That huge gap is because of **one extreme value** (an outlier)

---

## 📦 <span style="color:#FFA500;">Interquartile Range (IQR)</span>

To handle outliers, we use the **IQR**, which is based on **quartiles**:

| Quartile | Meaning |
|----------|---------|
| Q1       | 25% of data is below this point |
| Q2       | 50% (median)                    |
| Q3       | 75% of data is below this point |

### 🧮 Formula:
**IQR = Q3 − Q1**

- IQR focuses on the **middle 50%** of the data
- It removes the influence of **extreme values**

---

## 📊 <span style="color:#20B2AA;">Box Plot: Best of Both Worlds</span>

A **box plot** shows:
- The **minimum** and **maximum** values
- **Q1, Q2 (median), and Q3**
- Any **outliers**

It’s one of the best visual tools to understand:
- Center
- Spread
- Skewness
- Outliers

---

## 🖼️ Visual: Anatomy of a Box Plot

![Box Plot Diagram](/assets/images/boxplot1.png)

- Each 25% is shown as a section
- The box spans from Q1 to Q3
- The line in the middle is the **median (Q2)**
- Points outside are **outliers**

---

## 🎯 Why Not Just Use the Mean?

While **central tendency** is important, it’s not enough.  
We need to know how **spread out** the data is — especially when comparing groups.

🧠 The **box plot** helps you see both center and variability.

---

{% include quiz/dispersion-boxplot.html %}


## 🔁 <span style="color:#1E90FF;">Summary</span>

| Measure | What it tells us       | Sensitive to outliers? |
|---------|------------------------|-------------------------|
| Range   | Max − Min              | ✅ Yes                  |
| IQR     | Spread of middle 50%   | ❌ No                   |
| Box Plot | Visual of quartiles & outliers | ❌ No         |

---

## ✅ Up Next

Next, we’ll go deeper into **numeric measures** of variability:  
- **Variance**
- **Standard Deviation**

And we’ll learn how to calculate and visualize them!

Stay tuned.

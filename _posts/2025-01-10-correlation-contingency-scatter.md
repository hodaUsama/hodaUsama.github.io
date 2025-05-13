---
layout: post
title: "Correlation Between Variables: Contingency Tables and Scatter Plots"
date: 2025-01-10
categories: [statistics, beginner]
tags: [correlation, contingency-table, scatter-plot, categorical, quantitative]
math: true
---

To understand the relationship between two variables, we use **correlation**.

But how we analyze that relationship depends on the type of data we’re working with — **categorical or quantitative**.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/full-case-study/">A Real-World Statistics Example</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/full-case-study/">Understanding Pearson's R</a></p>
</div>

---

## 🎓 Real-Life Case: Study Habits and Exam Performance

Imagine a high school counselor wants to investigate the relationship between **how often students study** and whether they **pass or fail a weekly quiz**.

She surveys 30 students and records two things:
- 📚 Study Time Category: Rarely, Sometimes, Often
- ✅ Quiz Result: Pass or Fail

---

## 🧮 Step 1: The Contingency Table

This type of table is used for **categorical variables**. It shows how often combinations of categories occur.

| Study Frequency \ Quiz Result | Pass | Fail | Total |
|-------------------------------|------|------|-------|
| Rarely                        | 3    | 7    | 10    |
| Sometimes                     | 6    | 4    | 10    |
| Often                         | 9    | 1    | 10    |
| **Total**                     | 18   | 12   | 30    |

---

## 🔁 Step 2: Conditional Proportions

The raw counts don't tell the full story. So we calculate the **percentage** of each outcome within each group.

For example:
- Among students who study **Rarely**, 3/10 passed = **30%**
- Among those who study **Often**, 9/10 passed = **90%**

| Study Frequency | % Passed | % Failed |
|-----------------|----------|----------|
| Rarely          | 30%      | 70%      |
| Sometimes       | 60%      | 40%      |
| Often           | 90%      | 10%      |

✅ These are **conditional proportions** — percentages **within each row**.

---

## 📊 Step 3: Understanding Proportions — Quick Summary

We use **conditional proportions** to look *within groups*, and **marginal proportions** to summarize a variable *on its own*.

- Conditional example:  
  Among those who study Rarely → 3/10 passed = **30%**
- Marginal example:  
  Overall pass rate → 18/30 = **60%**

📚 Want a full breakdown with examples, visual tables, and when to use each?  
👉 [Read: Conditional vs. Marginal Proportions →](/posts/conditional-vs-marginal/)


---

## 🔍 Step 4: Interpreting the Categorical Correlation

The more a student studies, the more likely they are to pass.  
We can see a **positive association** in the conditional proportions:
- Rarely study → low pass rate
- Often study → high pass rate

➡️ But contingency tables don’t **quantify** correlation — they only show patterns.

---

## 🔄 Step 5: Let’s Make It Quantitative

Now let’s **change the scenario**:

The counselor asks students for their **exact number of study hours per week** and records their **quiz scores out of 100**.

Here’s a sample:

| Hours Studied | Quiz Score |
|---------------|------------|
| 2             | 50         |
| 3             | 55         |
| 5             | 65         |
| 7             | 70         |
| 8             | 76         |
| 10            | 85         |
| 12            | 92         |

---

## 📈 Step 6: Scatter Plot

This type of plot is perfect for **quantitative variables**.  
It helps us visually assess correlation:

- Each point = one student  
- X-axis: Hours studied  
- Y-axis: Quiz score

![Scatter Plot – Study Hours vs Quiz Score](/assets/images/scatter_study_scores.png)


You’ll notice: the more hours students study, the higher their scores.  
This is a **strong positive relationship**.

---

{% include quiz/case-study.html %}

## ✅ Conclusion

| Type of Data        | Tool to Use          | Example                     |
|---------------------|----------------------|-----------------------------|
| Categorical (Nominal/Ordinal) | Contingency Table     | Study Frequency vs Pass/Fail |
| Quantitative         | Scatter Plot          | Hours Studied vs Quiz Score |

🧠 Choose the right tool based on your variable types.

---

## 🔜 Up Next

Next, we’ll calculate the **Pearson correlation coefficient (r)** — a number that tells us **how strong** a linear relationship really is.

---
layout: post
title: "Correlation Between Variables: Contingency Tables and Scatter Plots"
date: 2025-05-10
categories: [statistics,Descriptive statistics, beginner]
tags: [correlation, contingency-table, scatter-plot, categorical, quantitative]
math: true
description: Learn how to analyze relationships between variables using correlation techniques like contingency tables and scatter plots, based on whether your data is categorical or quantitative.

---

Understanding how two variables relate is a core step in data analysis — and that's where **correlation** comes in.

But choosing the right correlation method depends on your data type: are your variables **categorical** or **quantitative**? In this post, we’ll break down the key approaches — from contingency tables to scatter plots — so you can analyze relationships with confidence.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/full-case-study/">A Real-World Statistics Example</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/PearsonsR/">Understanding Pearson's R</a></p>
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
| ----------------------------- | ---- | ---- | ----- |
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
| --------------- | -------- | -------- |
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
| ------------- | ---------- |
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

![Scatter plot showing positive correlation](/assets/images/scatter_study_scores.png)


You’ll notice: the more hours students study, the higher their scores.  
This is a **strong positive relationship**.

---

<details class="custom-box custom-best">
  <summary><strong>✅ Best Practices When Exploring Variable Relationships</strong></summary>
  <ul>
    <li>Start with <strong>simple visuals</strong> like scatter plots or tables before jumping into modeling.</li>
    <li>Use <strong>scatter plots</strong> to spot linear or curved patterns between numeric variables.</li>
    <li>For <strong>categorical data</strong>, contingency tables show how categories relate.</li>
    <li>Always ask: “Can this help my model make better predictions?”</li>
    <li>Use a <strong>correlation metric</strong> (like Pearson’s r) for numerical comparisons.</li>
  </ul>
</details>


---

<details class="custom-box custom-warning">
  <summary><strong>⚠ Common Pitfalls to Avoid</strong></summary>
  <ul>
    <li><strong>Assuming correlation means causation</strong> — just because two variables move together doesn’t mean one causes the other.</li>
    <li><strong>Ignoring outliers</strong> — one extreme value can distort your scatter plot or correlation result.</li>
    <li><strong>Overlooking non-linear patterns</strong> — not all relationships are straight lines. Try other visuals or transformations.</li>
    <li><strong>Using the wrong chart</strong> — don’t use a scatter plot for categorical data; use a contingency table instead.</li>
    <li><strong>Forgetting to check variable types</strong> — always know what kind of data you're working with before analyzing relationships.</li>
  </ul>
</details>

---

<details class="level-up-box">
  <summary class="level-up-title">🧠 Level Up: Choosing the Right Correlation Approach Based on Data Types</summary>
  <div class="level-up-content">
    <p>Correlation analysis isn’t one-size-fits-all — the type of variables determines the best method:</p>
    <ul>
      <li>📊 For two <strong>quantitative variables</strong>, measures like <em>Pearson's r</em> capture linear relationships.</li>
      <li>📋 For two <strong>categorical variables</strong>, <em>contingency tables</em> and tests like <em>Chi-square</em> help assess association.</li>
      <li>🔄 For mixed variable types, specialized methods like <em>point-biserial correlation</em> or <em>ANOVA</em> are used.</li>
    </ul>
    <p>Understanding your data types ensures you pick the most powerful and appropriate analysis technique.</p>
  </div>
</details>
---

{% include quiz/case-study.html %}

---

## 🤖 Why It Matters in Machine Learning

In machine learning, understanding **relationships between variables** helps you:

- 📊 Choose the right features for your model (feature selection).
- 📉 Detect multicollinearity — too much correlation between features can hurt model accuracy.
- 🧪 Engineer new features based on strong associations (e.g., combining study time and pass rate).
- 📈 Pick the right models — strong linear correlation? Consider regression. Categorical outcomes? Try classification.

Learning how to interpret contingency tables and scatter plots builds your **EDA skills**, a core part of every data science pipeline.


---

## ✅ Conclusion

| Type of Data                  | Tool to Use       | Example                      |
| ----------------------------- | ----------------- | ---------------------------- |
| Categorical (Nominal/Ordinal) | Contingency Table | Study Frequency vs Pass/Fail |
| Quantitative                  | Scatter Plot      | Hours Studied vs Quiz Score  |

🧠 Choose the right tool based on your variable types.

---
## 🔜 Up Next

Next, we’ll calculate the **Pearson correlation coefficient (r)** — a number that tells us **how strong** a linear relationship really is.

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

---
layout: post
title: "From Raw Data to Insight: Cases, Variables, and Frequency Tables"
date: 2025-05-02
categories: [statistics, beginner]
tags: [cases, variables, frequency-table, data-matrix, measurement-levels]
---

Before you can do any kind of data analysis — even before you calculate a single average — you need to understand what kind of **data** you're working with.

Let’s start from the very beginning.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/descriptive-vs-inferential">Descriptive vs Inferential Statistics</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/graph-types-in-statistics/">Choosing the Right Graph: How to Visualize Your Data</a></p>
</div>

---

## 👤 <span style="color:#1E90FF;">What Are Cases?</span>

**Cases** are the <strong>things you're studying</strong>.  
Think of them as <strong>rows</strong> in your data table — each row is a case.

| Case (row) | Student Name | Age | Grade | Favorite Subject |
|------------|--------------|-----|-------|------------------|
| 1          | Mariam       | 17  | 88    | Math             |
| 2          | Youssef      | 16  | 75    | Science          |

🟦 In this example, each <strong>student</strong> is a case.

---

## 🧬 <span style="color:#228B22;">What Are Variables?</span>

**Variables** are the <strong>characteristics</strong> you're measuring.  
They appear as <strong>columns</strong> in your data.

In the table above:
- <code>Age</code>, <code>Grade</code>, and <code>Favorite Subject</code> are all variables.

### 🔄 <span style="color:#FFA500;">Variable vs. Constant</span>
- A <strong>variable</strong> changes from case to case  
- A <strong>constant</strong> stays the same

💡 Example:
If all students are from <em>the same school</em>, then "School" is a <strong>constant</strong> — no need to analyze it.

---

## 🎯 <span style="color:#20B2AA;">Levels of Measurement</span>

Not all variables are created equal. They differ by <strong>what kind of values</strong> they hold.

| Level              | Description                              | Example            |
|--------------------|------------------------------------------|--------------------|
| Nominal            | Categories with no order                 | Favorite Subject   |
| Ordinal            | Categories with order                    | Satisfaction (Low/Med/High) |
| Interval           | Numbers, but no true zero                | Temperature (°C)   |
| Ratio              | Numbers with true zero (can divide)      | Age, Grade         |

📌 <span style="color:#FF6347;">Why it matters</span>: Some statistical methods only work for certain levels!

---

## 🧱 <span style="color:#9370DB;">The Data Matrix</span>

A <strong>data matrix</strong> is simply a big table:  
- Rows = <strong>cases</strong>  
- Columns = <strong>variables</strong>

🧩 It looks like a spreadsheet — great for analysis but hard to show here.  
Often, datasets are <em>too large</em> to present in full on a website or paper.

That’s why we use a simpler summary:

---

## 📊 <span style="color:#FF8C00;">The Frequency Table</span>

A <strong>frequency table</strong> tells us how often something appears in our data.

Let’s say you collected <strong>heights</strong> of 50 students.

You can group them into <strong>intervals</strong> like this:

| Height Range (cm) | Frequency |
|-------------------|-----------|
| 140–149           | 3         |
| 150–159           | 10        |
| 160–169           | 20        |
| 170–179           | 12        |
| 180–189           | 5         |

🎯 This helps us <span style="color:#FF6347;"><strong>see patterns</strong></span> — like more students being in the 160s.

🧠 For <strong>continuous data</strong> like height or age, this method is perfect.

---

## 🖼️ Diagram: Frequency Table vs Raw Data

![Frequency Table Animation](assets/images/frequency_table_demo.gif)

---
<details class="border rounded p-3 bg-light my-4">
  <summary class="fw-bold text-primary">🧠 Level Up: The Importance of Data Types and Structure in Machine Learning</summary>
  <div class="mt-2">
    <p>Understanding your data’s structure is crucial before any analysis or modeling:</p>
    <ul>
      <li>📋 <strong>Cases</strong> represent individual units of observation — like rows in a spreadsheet.</li>
      <li>📊 <strong>Variables</strong> describe characteristics or features of those cases — like columns.</li>
      <li>🔢 Recognizing whether variables are <em>categorical</em> or <em>quantitative</em> guides how you summarize, visualize, and model your data.</li>
      <li>📈 Properly structured data helps prevent errors and ensures meaningful machine learning outcomes.</li>
    </ul>
    <p>Getting these basics right is the foundation of all successful data science work.</p>
  </div>
</details>


---
{% include quiz/cases-variables-frequency.html %}
---

## 🔁 <span style="color:#1E90FF;">Summary</span>

| Concept             | Meaning                                      |
|---------------------|----------------------------------------------|
| <span style="color:#1E90FF;">Case</span>                | One item/person we study                     |
| <span style="color:#228B22;">Variable</span>            | A feature that varies across cases           |
| Constant            | A value that doesn’t change                  |
| <span style="color:#20B2AA;">Levels of Measurement</span> | Tells us how to handle the data            |
| <span style="color:#9370DB;">Data Matrix</span>         | A full table of all cases and variables      |
| <span style="color:#FF8C00;">Frequency Table</span>     | A summary of how often values appear         |

---

## ✅ Up Next

In the next post, we’ll <strong>build and visualize frequency tables using Python</strong>  
- With code and charts  
- For both categorical and continuous data

Stay tuned!

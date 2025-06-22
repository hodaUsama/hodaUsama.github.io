---
layout: post
title: "From Raw Data to Insight: Cases, Variables, and Frequency Tables"
date: 2025-05-02
categories: [statistics, beginner]
tags: [cases, variables, frequency-table, data-matrix, measurement-levels, machine-learning]
description: "Learn how to organize raw data using cases, variables, data matrices, and frequency tables — the essential building blocks for data analysis and machine learning."
---

Understanding the structure of your data is the first step in any data analysis or machine learning project. Before you calculate averages or build models, you need to know what your data represents — including its **cases, variables,** and measurement levels.
In this beginner-friendly guide, you’ll learn how to organize raw data using data matrices and frequency tables — two essential tools for clean, structured, and insightful analysis.

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

## 🤖 How Is This Related to Machine Learning?

Understanding cases, variables, and frequency tables is essential for any machine learning project:

- **Cases** are the data points your model will learn from (e.g., each row in your dataset could be a customer, an image, or a transaction).
- **Variables** are the features (columns) that describe each case. These features are what the model uses to find patterns and make predictions.
- **Levels of measurement** determine how you preprocess variables: categorical variables may need encoding (like one-hot encoding), while numerical variables might need normalization.
- **Frequency tables** help you explore and understand the distribution of your data, spot class imbalance in classification problems, and detect outliers or errors before modeling.

> In short, before you build a machine learning model, you must first organize, describe, and understand your data using these basic statistical tools. This ensures your model is built on a solid foundation and can learn meaningful patterns.

---

<details class="level-up-box">
  <summary class="level-up-title">🧠 Level Up: The Importance of Data Types and Structure in Machine Learning</summary>
  <div class="level-up-content">
    <p>Understanding your data’s structure is crucial before any analysis or modeling:</p>
    <ul>
      <li>📋 <strong>Cases</strong> represent individual units of observation — like rows in a spreadsheet.</li>
      <li>📊 <strong>Variables</strong> describe characteristics or features of those cases — like columns.</li>
      <li>🔢 Recognizing whether variables are <em>categorical</em> or <em>quantitative</em> guides how you summarize, visualize, and model your data.</li>
      <li>📈 Properly structured data helps prevent errors and ensures meaningful machine learning outcomes.</li>
      <li>⚠️ <strong>Common Pitfall:</strong> Mixing variable types without proper encoding can cause ML models to perform poorly.</li>
    </ul>
    <p>Getting these basics right is the foundation of all successful data science work.</p>
  </div>
</details>

---

## 🧪 Hands-On Practice

Try creating a frequency table yourself!  
- Use any small dataset (e.g., your favorite movies, sports stats, or a sample from Kaggle).  
- Group a continuous variable into intervals and count frequencies.  
- Share your results or questions in the comments or GitHub repo.

 💻 **Challenge yourself**: Open the interactive notebook and create your own frequency tables! 

[Open in Colab](https://colab.research.google.com/drive/1MZ0aB1KjMhOilCSEkdhCN0szJAb7fwX_?usp=sharing){:target="_blank"}

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
💬 **Got a question or suggestion?**  
Feel free to leave a comment in the section below — I’d love to hear your thoughts or help with your dataset!

---

## ✅ Up Next

In the next post, we’ll <strong>build and visualize frequency tables using Python</strong>  
- With code and charts  
- For both categorical and continuous data

💬 Have a dataset you’re working with? Share it in the comments or GitHub — let’s explore it together!

Stay tuned!

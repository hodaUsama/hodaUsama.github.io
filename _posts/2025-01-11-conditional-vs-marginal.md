---
layout: post
title: "Conditional vs. Marginal Proportions: What’s the Difference?"
date: 2025-01-11
categories: [statistics, beginner,concepts]
tags: [proportions, conditional, marginal, contingency-table, categorical]
math: true
---

Have you ever looked at a data table and wondered:

> ❓ *What’s the difference between marginal and conditional proportions?*  
> ❓ *When do I use each one?*

You’re not alone! These two terms come up a lot in **categorical data analysis**, especially when working with **contingency tables**.

Let’s break it all down with examples and visuals.

---

## 🧮 Let’s Start with a Contingency Table

A school counselor surveys students about their study habits and quiz results.

Here’s a visual of the full table — with highlights to show how conditional and marginal proportions work:

![Conditional vs Marginal Table](/assets/images/conditional-vs-marginal-table.png)

<details class="my-4">
  <summary style="font-weight:600; font-size:1rem; color:#1E90FF; padding:0.5em; background:#f8f9fa; border:1px solid #ddd; border-radius:6px; display:inline-block; cursor:pointer;">
    📋 Click to View: Full Study Frequency × Quiz Result Table
  </summary>

  <div class="table-responsive mt-3">
    <table class="table table-bordered table-sm">
      <thead class="table-light">
        <tr>
          <th>Study Frequency \\ Quiz Result</th>
          <th>Pass</th>
          <th>Fail</th>
          <th>Total</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Rarely</td>
          <td>3</td>
          <td>7</td>
          <td>10</td>
        </tr>
        <tr>
          <td>Sometimes</td>
          <td>6</td>
          <td>4</td>
          <td>10</td>
        </tr>
        <tr>
          <td>Often</td>
          <td>9</td>
          <td>1</td>
          <td>10</td>
        </tr>
        <tr class="table-light">
          <th>Total</th>
          <th>18</th>
          <th>12</th>
          <th>30</th>
        </tr>
      </tbody>
    </table>
  </div>
</details>

This table summarizes the relationship between two **categorical variables**:
- How often students study (Rarely, Sometimes, Often)
- Whether they passed or failed a quiz

---

## 🔁 <span style="color:#FFA500;">Conditional Proportions</span>

A **conditional proportion** asks:

> “**Given** that we’re in a certain group, what percent have a specific outcome?”

It’s about looking **within each row** (or column) to compare outcomes **relative to that group’s total**.

### 💡 Example:
- Among students who studied *Rarely*:  
  \\[
  P(\text{Pass} \mid \text{Rarely}) = \frac{3}{10} = 30\%
  \\]

- Among those who studied *Often*:  
  \\[
  P(\text{Pass} \mid \text{Often}) = \frac{9}{10} = 90\%
  \\]

| Study Frequency | % Passed | % Failed |
|-----------------|----------|----------|
| Rarely          | 30%      | 70%      |
| Sometimes       | 60%      | 40%      |
| Often           | 90%      | 10%      |

🧠 **Why it matters:**  
Conditional proportions reveal **associations between variables**.  
Here, we clearly see a trend: studying more = higher pass rate.

---

## 📊 <span style="color:#9370DB;">Marginal Proportions</span>

A **marginal proportion** answers:

> “What percent of the entire dataset falls into this category?”

It’s calculated using the **totals** in the margins of the table — hence the name.

### 💡 Examples:
- Proportion of all students who passed:  
  \\[
  P(\text{Pass}) = \frac{18}{30} = 60\%
  \\]

- Proportion who studied *Often*:  
  \\[
  P(\text{Often}) = \frac{10}{30} = 33.3\%
  \\]

🧠 **Why it matters:**  
Marginal proportions describe **each variable individually**.  
They help answer: "What percent of students passed overall?" or "How many students studied Often?"

---

## 🧩 <span style="color:#20B2AA;">Putting It All Together</span>

Here’s a comparison to clarify:

| Type                   | What It Tells You                                      | Formula                          |
|------------------------|--------------------------------------------------------|----------------------------------|
| **Marginal Proportion**   | Overall percent for a single category                   | Row/Column Total ÷ Grand Total   |
| **Conditional Proportion** | Outcome percent within a specific group (adds to 100%) | Cell ÷ Row Total (or Column)     |

✅ Use **marginals** for summarizing one variable  
✅ Use **conditionals** to **compare groups** and spot patterns

---

## 🚫 Common Mistakes

- Confusing marginal % (overall) with conditional % (within group)
- Forgetting that conditional proportions **always add to 100%** across the row/column
- Assuming patterns in conditionals **prove causation** (they don’t!)

---
{% include quiz/conditional-vs-marginal.html %}

---
## 🧠 Summary

| Term                  | Meaning                                               | Use Case                          |
|-----------------------|-------------------------------------------------------|-----------------------------------|
| **Marginal Proportion**  | Overall frequency of one category                    | "What % of all students passed?"  |
| **Conditional Proportion** | % of outcome **within a specific group**            | "What % of Rarely students passed?" |

---

## 🔗 Related Posts

- 📊 [Explore how we used conditional proportions in a real study →](/posts/correlation-contingency-scatter/)
- 📈 [Next: Pearson’s r — quantifying correlation for numeric data →](/posts/correlation-contingency-scatter/)

---

## ✅ TL;DR: Quick Recap

🟪 **Marginal Proportion** = Total % across **everyone**  
👉 Example: What % of all students passed?

🟦 **Conditional Proportion** = % **within a specific group**  
👉 Example: What % of students who studied *Rarely* passed?

---

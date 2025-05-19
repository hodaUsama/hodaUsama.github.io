---
layout: post
title: "Regression: Predicting Relationships Between Variables with the Best Fit Line"
date: 2025-05-13
categories: [statistics, beginner]
tags: [regression, linear-regression, residuals, r-squared, prediction]
math: true
---

In our last post, we explored **Pearson’s r**, which measures the strength and direction of a linear relationship between two variables. Now, we take the next step: **using regression** to model and predict relationships with a best-fitting line.

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Statistics" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/PearsonsR/">Pearson’s r It quantifies the strength and direction of a linear relationship</a></p>
  <p>🔜 <strong>Next:</strong> <a href="/posts/Randomness/">Mastering Randomness</a></p>
</div>

---

## 🎯 <span style="color:#1E90FF;"> A Creative Case Study: Predicting Exam Scores from Study Hours</span>

Imagine you collect data on students’ **hours studied** and their corresponding **exam scores**. You plot these points on a scatter plot and calculate Pearson’s r:

\[
r = 0.93
\]

This indicates a strong positive linear relationship: generally, more study hours relate to higher exam scores.

---

## 📊 <span style="color:#228B22;">Drawing the Regression Line & Understanding Residuals</span>

We want to draw a **regression line** through the scatter plot that best fits the data and allows us to **predict exam scores** based on study hours.

But how do we know which line fits best?

- For each data point, calculate the **vertical distance** to the regression line — this distance is called a **residual**.

- **Positive residuals** are distances where points lie **above** the regression line.

- **Negative residuals** are distances where points lie **below** the regression line.


  ![Scatter Plot with Regression Line & Residuals](/assets/images/regression-scatter-residuals.svg)
  <p style="font-size:0.9em;">*Visualizing residuals: distances from data points to regression line*</p>


---

## 🧮 <span style="color:#FFA500;"> Minimizing Residuals: Ordinary Least Squares (OLS) </span>

We want the regression line that **minimizes the sum of squared residuals** (RSS):

\\[
RSS = \sum (y_i - \hat{y}_i)^2
\\]

- We **square residuals** because positive and negative residuals would otherwise cancel out (sum of residuals = 0).

- Squaring also penalizes larger errors more heavily.

This method is called **Ordinary Least Squares (OLS)** — the most common technique for fitting regression lines.

  ![Visualizing Sum of Squared Residuals](/assets/images/regression-squared-residuals.svg)
  <p style="font-size:0.9em;">*Squares representing residuals and how RSS is calculated*</p>

---

## 📈 <span style="color:#20B2AA;"> The Regression Equation </span>

The regression line predicts values of \\( y \\) (dependent variable) from \\( x \\) (independent variable) as:

\\[
\hat{y} = a + b x
\\]

Where:  
- \\( \hat{y} \\) = predicted value of \\( y \\)  
- \\( a \\) = intercept (value of \\( y \) when \( x = 0 \\))  
- \\( b \\) = slope (change in \\( y \\) for one unit increase in \\( x \\))  

---

## 🧮 <span style="color:#FF6347;"> Calculating the Regression Coefficients </span>

Using the data, we calculate:

\\[
b = r \times \frac{s_y}{s_x}
\\]

\\[
a = \bar{y} - b \bar{x}
\\]

Where:  
- \\( r \\) = Pearson’s correlation coefficient between \\( x \\) and \\( y \\)  
- \\( s_y \\) = standard deviation of \\( y \\)  
- \\( s_x \\) = standard deviation of \\( x \\)  
- \\( \bar{y} \\) = mean of \\( y \\)  
- \\( \bar{x} \\) = mean of \\( x \\)

---

## ✅  <span style="color:#9370DB;"> Why Is This the Best Fitting Line?</span>

- Because it **minimizes the sum of squared residuals** (errors), no other line has less total squared distance from the points.

- It’s the line with the smallest prediction error on the observed data.

---

## 📊 <span style="color:#FF8C00;"> Assessing the Fit: \\( R^2 \\) (Coefficient of Determination) </span>

The statistic \\( R^2 \\) measures how well the regression line predicts \\( y \\):

\\[
R^2 = r^2
\\]

- \\( r \\) gives the **direction and strength** of the linear relationship.

- \\( R^2 \\) tells **how much better the regression line predicts \\( y \\) compared to simply using the mean of \\( y \\)**.

- \\( R^2 \\) also represents **the proportion of variance in \\( y \\) explained by \\( x \\)**.

---



  ![Comparison of High vs Low R-squared]( /assets/images/regression-r-squared-comparison.svg )
  <p style="font-size:0.9em;">*Comparing high and low \( R^2 \) values: High \( R^2 \) shows a good fit, Low \( R^2 \) shows a poor fit*</p>


---

## ⚠️ Important Tips

- **Correlation is NOT causation.** A strong relationship doesn’t prove one variable causes the other.

- **Outliers can distort** regression results. Always visualize your data and consider the effect of outliers before trusting the model.

---
{% include quiz/regression.html %}

## 🔁 <span style="color:#1E90FF;">Summary</span>

| Concept                           | Meaning                                                                                  |
|---------------------------------|------------------------------------------------------------------------------------------|
| <span style="color:#1E90FF;">Residual</span>                 | The vertical distance between an observed data point and the regression line             |
| <span style="color:#228B22;">Sum of Squared Residuals (RSS)</span> | The total of squared residuals minimized in ordinary least squares regression            |
| <span style="color:#20B2AA;">Regression Equation</span>      | \\( \hat{y} = a + b x \\); predicts \\( y \\) from \\( x \\)                                  |
| <span style="color:#9370DB;">Slope (\\(b\\))</span>            | Change in predicted \\( y \\) for a one unit increase in \\( x \\)                           |
| <span style="color:#FF8C00;">Intercept (\\(a\\))</span>        | Predicted value of \\( y \\) when \\( x = 0 \\)                                             |
| <span style="color:#1E90FF;">Pearson’s \\( r \\)</span>        | Correlation coefficient showing strength and direction of linear relationship            |
| <span style="color:#228B22;">Coefficient of Determination (\\(R^2\\))</span> | Proportion of variance in \\( y \\) explained by \\( x \\) via the regression model          |

---

## ✅ Up Next

In the next post, we’ll dive into <strong>Randomness and Probability</strong>  
- Understanding randomness in data and processes  
- Key probability concepts and rules  
- How probability helps us make sense of uncertainty  
- Practical examples to build your intuition

Stay tuned!



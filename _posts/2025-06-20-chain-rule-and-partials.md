---

layout: post
title: "🔗 Chain Rule, Implicit Differentiation, and Partial Derivatives (Calculus for ML)"
date: 2025-06-20
categories: [calculus, intermediate]
tags: [chain-rule, partial-derivatives, implicit-differentiation, calculus, machine-learning]
description: "Understand the Chain Rule, Implicit Differentiation, and Partial Derivatives with simple examples. Learn how to differentiate composite and multivariable functions step by step — a must for machine learning."
math: true

---

Before diving into neural networks or complex optimization, it's critical to master three powerful tools in calculus: the **Chain Rule**, **Implicit Differentiation**, and **Partial Derivatives**.

In this post, you'll learn:
- How to apply the **chain rule** to composite functions
- How **implicit differentiation** builds on the chain rule
- How to **differentiate multivariable functions** with respect to one variable (partial differentiation)

---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Calculus" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/what-is-gradient/" style="color:#FF6F61;">Understanding Gradients and Partial Derivatives (Multivariable Calculus for Machine Learning)</a></p> 
   <p>🔜 <strong>Next:</strong> <a href="/posts/jacobian-calculus/" style="color:#1E90FF;">Understanding the Jacobian – A Beginner’s Guide with 2D & 3D Examples</a></p>
</div>

---

## 🔗 <span style="color:#1E90FF;">What is the Chain Rule?</span>

The **chain rule** allows us to differentiate **composite functions**, i.e., functions inside other functions.

Let’s say:

\\[
f(x) = h(p(x)) = \sin(x^2)
\\]

We treat the outer function \\( h(u) = \sin(u) \\), and the inner \\( p(x) = x^2 \\).

Using the chain rule:

\\[
f'(x) = h'(p(x)) \cdot p'(x)
= \cos(x^2) \cdot 2x
\\]

✅ So, the derivative of \\( \sin(x^2) \\) is \\( 2x \cdot \cos(x^2) \\)

---

### 🧮 Python: Symbolic Chain Rule

```python
import sympy as sp

x = sp.symbols('x')
f = sp.sin(x**2)
dfdx = sp.diff(f, x)
dfdx = 2*x*cos(x**2)
```

---
![Plot showing sin(x²) and its derivative 2x·cos(x²) — a visual demonstration of the Chain Rule in action.](/assets/images/chain_rule_plot.png)

---

## 🧠 <span style="color:#FF8C00;">Another Chain Rule Example (Step-by-Step)</span>

Let’s find the derivative of:

\\[
f(x) = \ln(3x^2 + 1)
\\]

This function has **a function inside a function**, which is exactly when we use the **chain rule**.

---

### 🔹 Step 1: Identify the Inner and Outer Functions

We rewrite the function as:

\\[
f(x) = h(p(x))
\\]

Where:
- The **inner function** is: \\( p(x) = 3x^2 + 1 \\)
- The **outer function** is: \\( h(u) = \ln(u) \\), with \\( u = p(x) \\)

---

### 🔹 Step 2: Differentiate Each Part

- \\( h'(u) = \frac{1}{u} \\) → this is the derivative of \\( \ln(u) \\)
- \\( p'(x) = \frac{d}{dx}(3x^2 + 1) = 6x \\)

Now apply the **chain rule**:

\\[
f'(x) = h'(p(x)) \cdot p'(x) = \frac{1}{3x^2 + 1} \cdot 6x
\\]

---

### ✅ Final Answer

\\[
f'(x) = \frac{6x}{3x^2 + 1}
\\]

---

### 💡 Why This Matters

When differentiating logarithmic, trigonometric, or exponential functions **wrapped around polynomials**, the chain rule is your go-to tool. You treat the “outside” and “inside” layers separately, then multiply the results.

---

## 🔁 <span style="color:#9370DB;">Implicit Differentiation</span>

Sometimes, functions are not written in the form \\( y = f(x) \\). Instead, **x and y are mixed together** in one equation. In that case, we can't isolate y easily — so we use **implicit differentiation**.

---

### 📘 Example: A Circle

Take the equation of a circle:

\\[
x^2 + y^2 = 25
\\]

This defines a relationship between x and y, but y is not explicitly solved.

---

### 🧠 Step 1: Differentiate both sides **with respect to x**

Apply \\( \frac{d}{dx} \\) to each term:

\\[
\frac{d}{dx}(x^2) + \frac{d}{dx}(y^2) = \frac{d}{dx}(25)
\\]

- \\( \frac{d}{dx}(x^2) = 2x \\)
- \\( \frac{d}{dx}(25) = 0 \\) (constants have zero slope)
- \\( \frac{d}{dx}(y^2) = 2y \cdot \frac{dy}{dx} \\) ← this uses the **chain rule**, because y is treated as a function of x

So the full result becomes:

\\[
2x + 2y \cdot \frac{dy}{dx} = 0
\\]

---

### ✍️ Step 2: Solve for \\( \frac{dy}{dx} \\)

Subtract \\( 2x \\) from both sides:

\\[
2y \cdot \frac{dy}{dx} = -2x
\\]

Divide both sides by \\( 2y \\):

\\[
\frac{dy}{dx} = \frac{-x}{y}
\\]

---

### 💡 Interpretation:

Even though we didn’t solve for y directly, we found the slope of the curve **at any point (x, y)** on the circle. This is powerful — we differentiated without rearranging!

---

🔗 This method is essential when:
- y appears in powers or multiplied with x
- You have to find \\( \frac{dy}{dx} \\) but can't isolate y
- You're working with geometric shapes, constraint equations, or system-level models in ML


---
![A plot of the circle x² + y² = 25, showing the implicit relationship between x and y.](/assets/images/implicit_circle.png)

---

## 🔀 <span style="color:#32CD32;">Partial Derivatives</span>

When a function depends on more than one variable (e.g., \\( f(x, y, z) \\)), we can differentiate with respect to one, treating the others as **constants**.

Let:

\\[
f(x, y, z) = \sin(x) \cdot e^{yz^2}
\\]

### 🔹 Differentiate with respect to \\( x \\):

Only \\( \sin(x) \\) is affected:

\\[
\frac{\partial f}{\partial x} = \cos(x) \cdot e^{yz^2}
\\]

✅ Here, \\( y \\) and \\( z \\) are treated as constants.



### 🔹 Differentiate with respect to \( y \):

\\[
\frac{\partial f}{\partial y} = \sin(x) \cdot e^{yz^2} \cdot z^2
\\]

Chain rule applied to the exponent!

---

### 🔹 Differentiate with respect to \\( z \\):

\\[
\frac{\partial f}{\partial z} = \sin(x) \cdot e^{yz^2} \cdot 2yz
\\]


---


### 🧮 Python: Symbolic Partial Derivatives

```python
import sympy as sp

x, y, z = sp.symbols('x y z')
f = sp.sin(x) * sp.exp(y * z**2)

df_dx = sp.diff(f, x)
df_dy = sp.diff(f, y)
df_dz = sp.diff(f, z)

df_dx, df_dy, df_dz

```
Output:


```python
(exp(y*z**2)*cos(x),
 z**2*exp(y*z**2)*sin(x),
 2*y*z*exp(y*z**2)*sin(x))

```
This confirms our analytical work.


## ✅ 3. Visualizing f(x, y) = sin(x) · e^y in 3D


![3D surface plot of f(x, y) = sin(x) · eʸ ...](/assets/images/partial_surface_3d.png)`

---

### 📊 Python: 3D Surface Plot

```python
import numpy as np
import matplotlib.pyplot as plt

X, Y = np.meshgrid(np.linspace(-2*np.pi, 2*np.pi, 100), np.linspace(-2, 2, 100))
Z = np.sin(X) * np.exp(Y)

fig = plt.figure(figsize=(8, 6))
ax = fig.add_subplot(111, projection='3d')
ax.plot_surface(X, Y, Z, cmap='viridis')
ax.set_title(r'$f(x, y) = \sin(x) \cdot e^y$')
ax.set_xlabel('x')
ax.set_ylabel('y')
ax.set_zlabel('f(x, y)')
plt.show()

```

### 🤖 Relevance to Machine Learning

Understanding these differentiation tools is essential for anyone working in machine learning:

- 🧮 **Chain Rule** powers **backpropagation** in neural networks. Each layer’s gradient is computed by chaining derivatives through the layers — exactly as taught by the chain rule.
- ⚙️ **Partial Derivatives** form the backbone of **gradient-based optimization**. In functions with multiple variables (e.g., model weights), we compute partials to know how each parameter affects the loss.
- ❓ **Implicit Differentiation** appears in **constrained optimization** and in tools like Lagrange Multipliers, often used when variables can't be expressed directly.
- 📉 These techniques together allow models to **learn**, **update weights**, and **minimize error** during training.

In short: these aren’t just abstract math tricks — they’re the mathematical gears that drive intelligent systems.

---
<details class="level-up-box">
  <summary class="level-up-title"><strong>🚀 Level Up</strong></summary>
    <div class="level-up-content">
  <ul>
    <li>💡 The <strong>Chain Rule</strong> extends naturally to multiple nested layers — this is the foundation of backpropagation in neural networks.</li>
    <li>🔁 <strong>Implicit Differentiation</strong> is especially useful in constraint optimization problems where you can’t isolate a variable.</li>
    <li>🌐 <strong>Partial Derivatives</strong> are essential for working with functions of many variables — you'll see them in gradient vectors, Jacobians, and Hessians.</li>
    <li>📊 In <strong>machine learning</strong>, partial derivatives guide how each weight is updated during training.</li>
    <li>🧠 Want to go deeper? Explore the <strong>Total Derivative</strong> and <strong>Directional Derivatives</strong> for full control over multivariate calculus.</li>
  </ul>
    </div>
</details>

---
<details class="custom-box custom-best">
  <summary><strong>✅ Best Practices</strong></summary>
  <ul>
    <li>🔍 <strong>Break down complex expressions</strong> into inner and outer layers to apply the chain rule step by step.</li>
    <li>🧠 <strong>Label your inner and outer functions clearly</strong> — this reduces mistakes and makes your process transparent.</li>
    <li>📐 Use <strong>implicit differentiation</strong> when a function defines x and y together — especially useful for constraint problems.</li>
    <li>🧮 In <strong>partial differentiation</strong>, freeze all variables you're not differentiating with respect to — treat them like constants.</li>
    <li>📊 <strong>Simplify before and after differentiating</strong> — it helps reduce errors and makes the final expression cleaner.</li>
    <li>📈 <strong>Check your results visually</strong> when possible using a graphing tool to confirm slope behavior matches intuition.</li>
  </ul>
</details>


---

<details class="custom-box custom-warning">
  <summary><strong>⚠️ Common Pitfalls</strong></summary>
  <ul>
    <li>❌ <strong>Forgetting to multiply by the derivative of the inner function</strong> when using the chain rule — the #1 mistake!</li>
    <li>❌ <strong>Applying the power rule directly to composite expressions</strong> without unpacking layers first.</li>
    <li>❌ <strong>Misusing implicit differentiation</strong> by forgetting to apply the chain rule to y terms.</li>
    <li>❌ <strong>In partial differentiation</strong>, accidentally differentiating with respect to more than one variable at once.</li>
    <li>❌ <strong>Confusing constant functions with constant coefficients</strong> — constants like 7 are different from terms like 7x.</li>
  </ul>
</details>


---


## 📌 <span style="color:#9370DB;">Try It Yourself</span>

Test your understanding with these practice problems. Each one focuses on a key technique: chain rule, implicit differentiation, or partial derivatives.

---

<details>
<summary>📊 <strong>Chain Rule:</strong> What is 

 \( \frac{d}{dx} \sin(5x^2) \)
?</summary>

This is a composite function: \( \sin(u) \) where \( u = 5x^2 \)
<br>
 🧠 Step-by-step:
- Outer: \( \frac{d}{du} \sin(u) = \cos(u) \)
- Inner: \( \frac{d}{dx}(5x^2) = 10x \)

### ✅ Final Answer:
\[
\frac{d}{dx} \\sin(5x^2) = \\cos(5x^2) \\cdot 10x
\]
</details>

---

<details>
<summary>📊 <strong>Implicit Differentiation:</strong> Given \( x^2 + xy + y^2 = 7 \), find \( \frac{dy}{dx} \)</summary>

Differentiate both sides with respect to \( x \):
<br>
 🧠 Step-by-step:
- \( \frac{d}{dx}(x^2) = 2x \)
- \( \frac{d}{dx}(xy) = x \cdot \frac{dy}{dx} + y \) ← product rule!
- \( \frac{d}{dx}(y^2) = 2y \cdot \frac{dy}{dx} \)
- \( \frac{d}{dx}(7) = 0 \)

Putting it together:

\[
2x + x \cdot \frac{dy}{dx} + y + 2y \cdot \frac{dy}{dx} = 0
\]

Group \( \frac{dy}{dx} \) terms:

\[
(x + 2y)\frac{dy}{dx} = -(2x + y)
\]

### ✅ Final Answer:
\[
\frac{dy}{dx} = \frac{-(2x + y)}{x + 2y}
\]
</details>

---

## 🔁 <span style="color:#228B22;">Summary: What You Learned</span>

| 🧠 Concept                    | 📌 Description                                                                      |
| ---------------------------- | ---------------------------------------------------------------------------------- |
| **Chain Rule**               | Differentiates composite functions by chaining outer and inner derivatives.        |
| **Implicit Differentiation** | Differentiates equations where y is not isolated, using the chain rule on y terms. |
| **Partial Derivative**       | Differentiates multivariable functions with respect to one variable at a time.     |
| **Backpropagation**          | Uses chain rule to compute gradients layer by layer in neural networks.            |
| **Gradient Vector**          | A vector of partial derivatives used in optimization and ML training.              |
| **Derivative of sin(x²)**    | \\( \\frac{d}{dx}\\sin(x^2) = 2x \\cdot \\cos(x^2) \\)                             |
| **∂f/∂x of f(x, y, z)**      | \\( \\frac{\\partial}{\\partial x}(\\sin(x)e^{yz^2}) = \\cos(x)e^{yz^2} \\)        |

---

## 🧭 <span style="color:#9370DB;">Next Up</span>

Now that you’ve learned how to compute partial derivatives, you're ready to tackle the next building block in multivariable calculus: the **Jacobian Matrix**.

In the next post, we’ll explore:
- What the **Jacobian** is and how it's constructed
- Why it’s essential for **transformations**, **coordinate changes**, and **machine learning gradients**
- Step-by-step examples for both scalar and vector-valued functions

Stay curious — you're one layer closer to mastering the math behind modern ML models.

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


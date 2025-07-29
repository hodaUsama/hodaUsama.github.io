---
layout: post
title: "⚙️ Optimization in Machine Learning: From Gradient Descent to Newton’s Method"
description: "Understand the core optimization techniques used in training machine learning models, including gradient descent, Newton’s method, learning rates, and loss surfaces."
tags: ["optimization", "gradient-descent", "hessian", "machine-learning", "training"]
date: 2025-06-23
categories: [calculus, beginner]
toc: true
math: true
---
---

## ⚙️ What Is Optimization in ML?

Optimization is the core process that drives learning in machine learning models.  
It’s how we find the best parameters — like weights in a neural network — that reduce error as much as possible.

Imagine you're hiking through a mountainous landscape: the goal is to reach the lowest valley.  
This landscape represents the **loss surface**, and optimization algorithms guide your steps to find that minimum.

---
---

<div class="series-nav">
  <p>📚 <strong>This post is part of the "Intro to Calculus" series</strong></p>
  <p>🔙 <strong>Previously:</strong> <a href="/posts/hessien-optimization/" style="color:#FF6F61;">What is the Hessian? Understanding Curvature and Optimization in Machine Learning</a></p> 
</div>

---

---

## 🎯 Loss Functions

A **loss function** measures how far off a model’s predictions are from actual labels.

Examples:
- Mean Squared Error: \\( L = \frac{1}{n}\sum (y_i - \hat{y}_i)^2 \\)
- Cross-Entropy for classification

We want to **minimize** the loss by adjusting parameters.

---

## 🔽 Gradient Descent (First-Order)

Gradient descent uses the **gradient** (first derivative) to take steps in the direction of steepest decrease.

Update rule:
\\[
\theta_{\text{next}} = \theta - \eta \cdot \nabla L(\theta)
\\]

- \\( \eta \\): learning rate (step size)
- \\( \nabla L(\theta) \\): gradient of the loss function

Too large \\( \eta \\) → overshooting; too small → slow convergence.

---

## 📉 Python: Gradient Descent Demo

```python
import numpy as np
import matplotlib.pyplot as plt

# Loss function and derivative
f = lambda x: x**2
df = lambda x: 2*x

x_vals = [2.0]  # starting point
lr = 0.1

for _ in range(10):
    x_new = x_vals[-1] - lr * df(x_vals[-1])
    x_vals.append(x_new)

# Plot
x = np.linspace(-2, 2, 100)
y = f(x)
plt.plot(x, y)
plt.scatter(x_vals, [f(x) for x in x_vals], color='red')
plt.title("Gradient Descent on f(x) = x²")
plt.xlabel("x")
plt.ylabel("f(x)")
plt.show()
```
---
### 📊 Visual: Gradient Descent Steps on a Curve

This plot shows how gradient descent iteratively steps toward the minimum on \( f(x) = x^2 \):

![Gradient descent path showing red dots moving toward the bottom of a parabola](/assets/images/gradient_descent_path.png "Gradient Descent on $f(x) = x^2$")


---

## 🧠 Newton’s Method (Second-Order)

Newton's method uses the **Hessian** to adjust step size based on curvature:

\\[
\theta_{\text{next}} = \theta - H^{-1} \nabla L(\theta)
\\]

Where:
- \\( H \\): Hessian matrix (second derivatives)
- More accurate near optima, but requires expensive matrix inversion.

---

## 🧪 Python: Newton’s Method Symbolic (2D)

```python
import sympy as sp

x, y = sp.symbols('x y')
f = x**2 + y**2

# Gradient
grad = sp.Matrix([sp.diff(f, var) for var in (x, y)])
# Hessian
H = sp.hessian(f, (x, y))

# Newton step
theta = sp.Matrix([x, y])
theta_next = theta - H.inv() * grad
sp.simplify(theta_next)
```
---

### 🖼️ Visual: Newton’s Method and Curvature

This 3D surface shows how Newton’s Method uses curvature to jump directly to the bottom:

- Red arrow = gradient direction
- Blue point = Newton’s update lands at the minimum

![3D surface of $f(x, y) = x^2 + y^2$ with gradient and Newton step arrow](/assets/images/newton_method_surface.png "Newton’s Method on $f(x, y) = x^2 + y^2$")


---

## ⚖️ Comparing First- and Second-Order Methods

| Method            | Uses            | Pros                        | Cons                        |
|------------------|------------------|------------------------------|-----------------------------|
| Gradient Descent | First derivative | Simple, scalable             | Slower convergence          |
| Newton's Method  | Second derivative| Faster near minimum          | Expensive (Hessian inverse) |

---
## 🤖 Relevance to Machine Learning

Optimization is the engine behind how machine learning models learn. Whether it’s a simple linear model or a deep neural network, optimization determines how the model improves its predictions over time.

<ul>
  <li>
    <b>Model Training</b>: Algorithms like gradient descent adjust weights to minimize loss functions — it's how models learn from data.
  </li>
  <li>
    <b>Neural Networks</b>: Every training step in deep learning is an optimization update, typically using stochastic gradient descent or its variants.
  </li>
  <li>
    <b>Convex vs. Non-Convex Loss</b>: Optimization challenges differ depending on whether the loss surface is smooth and convex (easy) or full of local minima/saddles (hard).
  </li>
  <li>
    <b>Learning Rate Tuning</b>: Choosing the right learning rate is essential — too small and the model learns slowly, too large and it may diverge.
  </li>
  <li>
    <b>Advanced Optimizers</b>: Algorithms like Adam, RMSProp, and L-BFGS use momentum, adaptive learning rates, or curvature approximations to improve training.
  </li>
  <li>
    <b>Batch Training</b>: Optimization behaves differently when using mini-batches, full batches, or stochastic updates.
  </li>
  <li>
    <b>Loss Surface Geometry</b>: Understanding optimization gives insight into why some models get stuck in saddle points, overshoot, or fail to converge.
  </li>
</ul>

---
<details class="level-up-box">
<summary class="level-up-title">🧠 Level Up</summary>
<div class="level-up-content">
<ul>
  <li>🧭 <b>Optimization = Learning</b>: Every ML model “learns” by minimizing a loss function — optimization is the engine behind it.</li>
  <li>🚀 <b>Gradient Descent</b>: First-order methods are simple and scale well, making them the default in most neural networks.</li>
  <li>🔁 <b>Learning Rate Tuning</b>: Adjusting the learning rate can mean the difference between convergence and failure — even for the same algorithm.</li>
  <li>🔺 <b>Newton’s Method</b>: Second-order updates use curvature to move faster near minima — especially in low-dimensional or convex problems.</li>
  <li>🧠 <b>Adaptive Methods</b>: Optimizers like Adam and RMSProp approximate curvature and adjust step sizes automatically per parameter.</li>
</ul>
</div>
</details>

---

<details class="custom-box custom-best">
<summary><strong>✅ Best Practices</strong></summary>

<ul>
  <li>🧠 <b>Understand the loss surface</b>: Visualizing or analyzing loss curvature helps choose the right optimizer and learning rate.</li>
  <li>🔢 <b>Start with simple functions</b>: Practice gradient descent and Newton’s method on 1D and 2D functions to build intuition.</li>
  <li>📉 <b>Tune the learning rate</b>: Test multiple values — even the best optimizer fails with a poor step size.</li>
  <li>🔁 <b>Compare first and second-order updates</b>: Understand when Newton’s method outperforms basic gradient descent (e.g., near optima).</li>
  <li>⚙️ <b>Use auto-diff tools</b>: Frameworks like TensorFlow and PyTorch compute gradients and Hessians efficiently and correctly.</li>
</ul>
</details>

---

<details class="custom-box custom-warning">
<summary><strong>⚠️ Common Pitfalls</strong></summary>

<ul>
  <li>❌ <b>Choosing a bad learning rate</b>: Too large and you overshoot; too small and training stalls.</li>
  <li>❌ <b>Ignoring convergence behavior</b>: Watch for oscillation, divergence, or vanishing updates.</li>
  <li>❌ <b>Over-relying on Newton’s method</b>: It's powerful, but impractical for high-dimensional models due to Hessian computation.</li>
  <li>❌ <b>Misinterpreting gradient direction</b>: The gradient shows steepest increase — you must subtract it to minimize loss.</li>
  <li>❌ <b>Confusing global vs. local minima</b>: Optimization finds local minima — that doesn’t always mean it’s the best possible model.</li>
</ul>
</details>

---

## 📌 <span style="color:#9370DB;">Try It Yourself</span>

<details>
<summary>📊 <strong>Gradient Descent Step:</strong> What’s the next value of \( x \) if we start at \( x = 2 \) on \( f(x) = x^2 \) with learning rate 0.1?</summary>

🧠 Step-by-step:<br>
- Gradient: \( f'(x) = 2x \), so at \( x = 2 \), \( f'(2) = 4 \)<br>
- Update rule: \( x_{\text{next}} = x - \eta \cdot f'(x) = 2 - 0.1 \cdot 4 = 1.6 \)

✅ Final Answer:
\[
x_{\text{next}} = 1.6
\]
</details>

---

<details>
<summary>📊 <strong>Newton’s Method Step:</strong> On \( f(x) = x^2 \), what is the Newton update from \( x = 2 \)?</summary>

🧠 Step-by-step:<br>
- Gradient: \( f'(x) = 2x \), so \( f'(2) = 4 \)<br>
- Hessian (2nd derivative): \( f''(x) = 2 \)<br>
- Newton update: \( x_{\text{next}} = x - \frac{f'(x)}{f''(x)} = 2 - \frac{4}{2} = 0 \)

✅ Final Answer:
\[
x_{\text{next}} = 0
\]
</details>

---

<details>
<summary>📊 <strong>Compare Steps:</strong> Which method moves more aggressively from \( x = 2 \) on \( f(x) = x^2 \)?</summary>

🧠 Answer:<br>
- Gradient Descent took \( x \rightarrow 1.6 \)<br>
- Newton’s Method took \( x \rightarrow 0 \)<br>

✅ Newton's Method is more aggressive and goes straight to the minimum in this case.
</details>

---

## 🔁 <span style="color:#228B22;">Summary: What You Learned</span>

| 🧠 Concept             | 📌 Description                                                                 |
|------------------------|-------------------------------------------------------------------------------|
| **Loss Function**      | Measures model error — optimization tries to minimize it                      |
| **Gradient Descent**   | First-order method that uses slope to step toward minima                      |
| **Learning Rate**      | Controls step size — critical for convergence                                 |
| **Newton’s Method**    | Uses both gradient and Hessian for curvature-aware optimization               |
| **Hessian Matrix**     | Matrix of second derivatives — shows local curvature                          |
| **Convex vs Non-Convex** | Optimization behavior changes based on loss surface shape                   |
| **Optimizer Behavior** | Different optimizers converge at different speeds and directions              |
| **Python Tools**       | Libraries like NumPy and SymPy can simulate and visualize optimization steps  |

---

## 💬 <span style="color:#4B0082;">Got a question or suggestion?</span>

Leave a comment below — I’d love to hear your thoughts or help if something was unclear.


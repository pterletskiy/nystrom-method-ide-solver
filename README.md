# Numerical Methods for Integro-Differential Equations (IDEs) 🧮

This repository implements the **Nyström Method** to solve linear and nonlinear boundary value problems (BVP) involving Integro-Differential Equations. This work was developed for the **Numerical Methods in Finance** course, part of the **MSc in Mathematical Finance at ISEG (Lisbon School of Economics & Management)**.

## 📌 Problem Statement

We aim to determine a function $y \in C^2[a, b]$ that satisfies the general integro-differential equation:

$$y''(x) + \alpha(x)y'(x) + \beta(x)y(x) + \int_a^b K(x,t)y(t) \ dt = f(x), x \in ]a,b[$$

with boundary conditions:
$$y(a) = y(b) = 0$$

---

## 🛠️ Methodology (Personal Contribution - Parts A & B)

I was primarily responsible for the implementation of the linear solver and the subsequent convergence analysis.

### 1. Linear Solver Implementation (Part A)
Developed a modular Python solver that discretizes the domain and approximates the IDE using:
* **Finite Differences:** Central, Forward, and Backward schemes for $y'(x)$ and $y''(x)$.
* **Quadrature Rules:** Implementation of the Trapezoidal rule (and others) to approximate the integral term.
* **Linear System Construction:** The discretized equation is transformed into a system of linear equations $Ay = B$, solved using efficient matrix inversion techniques.

### 2. Convergence Analysis (Part B)
To validate the model, I performed a rigorous error analysis using an exact solution $y(x) = \sin(\pi x)$.
* **Order of Convergence:** Verified the relationship between grid size $h$ and the global error.
* **Scheme Comparison:** Evaluated how different finite difference schemes (Central vs. One-sided) impact the accuracy and stability of the Nyström method.

![Convergence Analysis](images/convergence_plot.png)
*Figure: Error decay for different numerical schemes.*

---

## 🧪 Advanced Applications (Parts C & D)
In collaboration with group members, the project was extended to handle:
* **Nonlinear Kernels:** Solving equations where $K$ depends on $y(t)$, i.e., $K(x, t, y(t))$.
* **Newton's Method:** Implementing iterative solvers for the resulting nonlinear systems.

$$y''(x) + \int_0^1 \frac{e^{x + t}}{1 + y(t)^2} y(t) \, dt = x$$

---

## 💻 Tech Stack
* **Python:** Main language.
* **NumPy:** Linear algebra and matrix operations.
* **Matplotlib:** Numerical solution visualization and convergence plotting.
* **LaTeX:** For mathematical documentation.

---

## 📂 Project Structure
* `NMF_Project.ipynb`: Full implementation, from linear solvers to nonlinear Newton iterations.
* `Project-Assignment.pdf`: Formal description of the numerical problems.
* `images/`: Plots showing numerical solutions and convergence rates.

---
**Authors:** [Petr Terletskiy](https://www.linkedin.com/in/petr-terletskiy/) (Lead on Parts A & B), Rodrigo Jesus, Tiago Monteiro.  
**Context:** Master's in Mathematical Finance (ISEG - 2024/25)

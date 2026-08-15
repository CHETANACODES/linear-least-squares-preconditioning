# linear-least-squares-preconditioning
# Computational Methods for Solving Linear Least-Squares Problems

### Analysis, Optimization, and Numerical Stability

**Author:** Chetana Pandey  
**Degree:** MSc Mathematics  
**Institution:** Mahatma Gandhi Kashi Vidyapith, Varanasi, India  
**Year:** 2026

---

## Overview

This repository contains the research document and computational implementation for a study on numerical methods for solving linear least-squares problems.

The project presents a comparative computational analysis of four gradient-based optimization approaches:

1. Standard Gradient Descent
2. Diagonal Scaling Preconditioning
3. Iterative Preconditioning
4. SVD-Based Preconditioning

The primary objective is to investigate how different optimization and preconditioning strategies affect:

- Convergence behaviour
- Numerical accuracy
- Numerical stability
- Computational efficiency
- Iteration complexity
- The influence of matrix conditioning

All methods are implemented and evaluated under consistent experimental conditions using Python and standard scientific-computing libraries.

---

## Research Motivation

Linear least-squares problems arise throughout scientific computing, engineering, data analysis, statistics, and machine learning.

Given a matrix \(A \in \mathbb{R}^{m \times n}\) and a vector \(b \in \mathbb{R}^{m}\), the linear least-squares problem seeks a vector \(x\) satisfying

\[
\min_x \|Ax-b\|_2^2.
\]

Although the problem is mathematically well understood, the numerical performance of iterative optimization methods can depend strongly on the conditioning and spectral properties of the underlying system.

This project investigates whether preconditioning techniques can improve the computational behaviour of gradient-based optimization while maintaining numerical accuracy and stability.

---

## Research Objectives

The main objectives of this study are:

- To formulate linear least-squares problems as optimization problems.
- To implement standard Gradient Descent for least-squares optimization.
- To implement Diagonal Scaling Preconditioning.
- To implement Iterative Preconditioning.
- To implement SVD-Based Preconditioning.
- To compare the convergence behaviour of the methods.
- To evaluate numerical accuracy using residual norms and relative errors.
- To compare computational efficiency using iteration counts and execution time.
- To examine the role of matrix conditioning in optimization performance.
- To establish a reproducible computational framework for comparing optimization methods.

---

## Methods Compared

### 1. Standard Gradient Descent

The least-squares objective can be written as

\[
f(x)=\frac{1}{2}\|Ax-b\|_2^2.
\]

Its gradient is

\[
\nabla f(x)=A^T(Ax-b).
\]

The standard gradient-descent iteration is

\[
x_{k+1}=x_k-\alpha \nabla f(x_k),
\]

where \(\alpha\) denotes the step size.

---

### 2. Diagonal Scaling Preconditioning

Diagonal scaling modifies the optimization process using a diagonal preconditioning matrix.

The objective is to improve the numerical behaviour of the iterative method by appropriately scaling the problem.

The method is evaluated in terms of:

- convergence speed,
- residual accuracy,
- relative error,
- and computational cost.

---

### 3. Iterative Preconditioning

The iterative preconditioning approach modifies the optimization process using an iterative transformation intended to improve convergence characteristics.

Its performance is compared against both the baseline gradient method and the other preconditioning strategies.

---

### 4. SVD-Based Preconditioning

Singular Value Decomposition provides a spectral representation of the system:

\[
A = U\Sigma V^T.
\]

The singular values provide information about the numerical structure and conditioning of the least-squares problem.

The SVD-based approach uses this information to construct a preconditioned optimization framework.

---

## Experimental Framework

All four methods are evaluated under identical experimental conditions.

The comparison uses:

- A common synthetic least-squares problem
- Identical initialization
- Consistent stopping criteria
- Common numerical precision
- Common evaluation metrics

The principal evaluation metrics are:

### Convergence

The number of iterations required to satisfy the prescribed stopping criterion.

### Residual Norm

\[
\|Ax-b\|_2
\]

which measures the quality of the computed least-squares solution.

### Relative Error

The relative error between the computed solution and the known solution vector.

### Execution Time

The computational time required for each optimization method to converge.

---

## Computational Environment

The implementation was developed using:

- **Python**
- **NumPy**
- **SciPy**
- **Matplotlib**
- **Google Colaboratory**

The computational framework is designed to be reproducible and extensible.

---

## Results

The experimental evaluation showed that all four methods successfully converged to the least-squares solution for the benchmark problem.

The computed solutions achieved:

- Residual norms on the order of \(10^{-7}\)
- Relative errors on the order of \(10^{-8}\)

### Convergence Performance

For the benchmark problem, the observed iteration counts were:

| Method | Iterations | Execution Time (s) |
|---|---:|---:|
| Standard Gradient Descent | 111 | 0.004270 |
| Diagonal Scaling Preconditioning | **103** | 0.004583 |
| Iterative Preconditioning | 131 | 0.035883 |
| SVD-Based Preconditioning | 918 | 0.110100 |

Under the experimental conditions considered, **Diagonal Scaling Preconditioning achieved the most favourable overall convergence behaviour**.

It required the fewest iterations while maintaining an execution time comparable to standard Gradient Descent.

---

## Numerical Accuracy

The residual norms obtained from all four methods were approximately of order

\[
10^{-7},
\]

while the relative errors were approximately of order

\[
10^{-8}.
\]

For the benchmark problem, Diagonal Scaling Preconditioning achieved:

\[
\text{Residual Norm}
=
8.96357748\times10^{-7}
\]

and

\[
\text{Relative Error}
=
1.87022756\times10^{-8}.
\]

These results indicate that all four methods produced accurate numerical solutions under the selected experimental conditions.

---

## Conditioning

The benchmark least-squares problem used in the experiment had a condition number of approximately

\[
\kappa \approx 2.73.
\]

This indicates that the selected problem was relatively well-conditioned.

Consequently, the potential benefits of more sophisticated preconditioning techniques were naturally limited in this experiment.

This is an important qualification of the results: the observed performance should not be interpreted as evidence that diagonal scaling is universally superior to SVD-based or other advanced preconditioning techniques.

Instead, the results suggest that the effectiveness of a preconditioning strategy depends strongly on the characteristics of the underlying optimization problem.

---

## Key Findings

The main observations from the computational experiments are:

1. All four optimization methods successfully converged to the least-squares solution.

2. Diagonal Scaling Preconditioning required the fewest iterations for the benchmark problem.

3. Diagonal Scaling Preconditioning achieved the smallest residual norm and relative error among the evaluated methods.

4. Standard Gradient Descent also demonstrated strong performance on the selected problem.

5. Iterative Preconditioning converged successfully but required additional computational effort.

6. SVD-Based Preconditioning required substantially more iterations and computational time under the experimental conditions.

7. The benchmark problem was relatively well-conditioned, with a condition number of approximately \(2.73\).

8. The results demonstrate that the computational advantage of a preconditioning technique depends on the characteristics of the underlying problem.

---

## Research Limitations

Several limitations of the present study should be acknowledged.

### 1. Benchmark Problem

The experiments were conducted using a synthetic least-squares problem with a relatively low condition number.

Therefore, the results do not fully characterize the behaviour of the methods on highly ill-conditioned systems.

### 2. Problem Scale

The current study focuses on a centralized least-squares problem.

Large-scale sparse systems and distributed optimization problems were outside the scope of the present investigation.

### 3. Number of Algorithms

Only four representative optimization approaches were evaluated.

Many other optimization and preconditioning techniques remain to be investigated.

### 4. Experimental Scope

The conclusions are specific to the experimental configuration and benchmark considered in this study.

Different problem structures may produce substantially different performance characteristics.

---

## Future Research Directions

The results provide several natural directions for further investigation.

### Highly Ill-Conditioned Problems

Future experiments can investigate least-squares systems with significantly larger condition numbers in order to examine the effectiveness of different preconditioning strategies under more demanding numerical conditions.

### Large-Scale Sparse Systems

The framework can be extended to large-scale sparse matrices arising from scientific and engineering applications.

This would allow investigation of:

- scalability,
- memory requirements,
- computational complexity,
- numerical robustness,
- and convergence behaviour.

### Nonlinear Least-Squares Problems

The methodology can be extended from linear least-squares problems to nonlinear least-squares optimization.

### Additional Optimization Methods

Future comparisons may include:

- Conjugate Gradient methods
- Quasi-Newton methods
- Stochastic optimization
- Adaptive gradient methods
- Randomized preconditioning
- Other modern first-order optimization methods

### Scientific and Machine Learning Applications

The computational framework can also be extended to real-world datasets and optimization problems arising in scientific computing and machine learning.

---

## Reproducibility

The project is intended to provide a reproducible computational framework.

The experiments use:

- common initialization,
- consistent stopping criteria,
- identical evaluation metrics,
- and a common computational environment.

The implementation is provided so that the experiments can be reproduced and extended to additional optimization methods and benchmark problems.

---

## Repository Structure

```text
linear-least-squares-preconditioning/
│
├── README.md
│
├── research/
│   └── research_proposal.pdf
│
├── notebooks/
│   └── experiments.ipynb
│
├── src/
│   ├── gradient_descent.py
│   ├── diagonal_preconditioning.py
│   ├── iterative_preconditioning.py
│   └── svd_preconditioning.py
│
├── results/
│   ├── convergence/
│   ├── accuracy/
│   └── performance/
│
└── figures/
    ├── convergence_plots/
    └── comparison_plots/

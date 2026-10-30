# Week 01: Financial Mathematics, Stochastic Foundations & Numerical Analysis

This repository implements and verifies the fundamental building blocks of financial engineering—stochastic processes, mathematical statistics derivations, Monte Carlo simulations, and numerical root-finding algorithms—using Python.

---

## 📌 Key Topics & Methodologies

### 1. Time Value of Money & Compounding Conventions
* Calculation of future values under simple interest, discrete compounding (annual, quarterly, monthly), and continuous compounding conventions.

### 2. Probability Distributions & Rare Event Approximations
* Comparative accuracy analysis between the exact Binomial distribution and the Poisson approximation ($\lambda = np$) for rare event modeling.

### 3. Distributional Convolutions & Moment-Generating Functions (MGF)
* Given the hierarchical Gaussian model $Y \sim N(\mu, \sigma^2)$ and $(X \mid Y = y) \sim N(y, \nu^2)$:
  * Analytical derivation of the marginal distribution $X \sim N(\mu, \sigma^2 + \nu^2)$ via the Law of Total Probability and completing the square in Gaussian convolution integrals.
  * Closed-form derivation via the Law of Iterated Expectations and MGF uniqueness theorem, validated against numerical simulation across 200,000 trials.

### 4. Random Walk Models & Stopping Time Probabilities
* Discrete random walk modeling of asset price paths: $S_{10} = S_0 + \sum_{i=1}^{10} W_i$.
* Computation of the non-parametric upper bound using **Chebyshev's Inequality** ($P \le 0.4000$).
* Analytical evaluation under the **Exact Gaussian Distribution** ($P = 0.0569$) and convergence verification via **10,000-path Monte Carlo simulation** ($\approx 0.0531$).

### 5. Numerical Root-Finding for Internal Rate of Return (IRR)
* Numerical estimation of polynomial roots for $f(\lambda) = -1 + \lambda + \lambda^2 = 0$ with a precision threshold of $\text{Tolerance} = 10^{-6}$:
  * **Newton-Raphson Method**: Converged in 4 iterations (quadratic convergence rate).
  * **Bisection Method**: Converged in 19 iterations (linear convergence rate).
  * Benchmarking execution runtime using `timeit` and visualizing error decay dynamics on a log scale.

### 6. Geometric Probability & Brainteasers
* Analytical proof that $N$ randomly distributed points on a circle lie within a semicircle with probability $P_N = \frac{N}{2^{N-1}}$.
* Numerical verification using a maximum consecutive gap condition ($\text{Max Gap} \ge 0.5$) evaluated over 200,000 Monte Carlo trials.

---

## 🛠 Tech Stack
* **Language**: Python 3
* **Libraries**: `numpy`, `scipy.stats`, `matplotlib`, `timeit`

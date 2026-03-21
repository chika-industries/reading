## Summary of Chapter 5: Level 2: Subexponentials and Power Laws

This chapter moves beyond finite-moment distributions to examine "true fat tails"—the subexponential and power law classes. It establishes the critical boundary between Mediocristan and Extremistan and explores the distinctive properties of power laws.

### 5.0.1 Revisiting the Rankings

The chapter begins by reviewing the hierarchy of distributions introduced in Chapter 3:

1. **Compact support** (Bernoulli, Binomial)
2. **Thin tails** (Gaussian)
3. **Conventional tails** (higher kurtosis than Gaussian but rapid CLT convergence)
4. **Starter Fat Tails** (lognormal)
5. **Subexponential** (borderline)
6. **Supercubic** (α > 3)
7. **Infinite Variance** (α < 2)
8. **Undefined First Moment** (α ≤ 1)
9. **"Fuhgetaboutdit"**

### 5.0.2 What is a Borderline Probability Distribution?

**Subexponentiality** is the mathematical definition of the boundary. For a subexponential distribution:

$$\lim_{x\to\infty} \frac{1-F^{*2}(x)}{1-F(x)} = 2$$

where $F^{*2}$ is the distribution of the sum of two independent copies. This means the probability that the sum exceeds a large value x is twice the probability that either one separately exceeds x. For large x, the sum is dominated by the maximum—the other contributes negligibly.

More generally, for n variables:
- $\lim_{x\to\infty} \frac{P(S_n > x)}{P(X > x)} = n$
- $\lim_{x\to\infty} \frac{P(S_n > x)}{P(M_n > x)} = 1$

Thus the sum has the same magnitude as the largest observation—tails play the dominant role.

Subexponential distributions have **no exponential moments**: $\int_0^\infty e^{\epsilon x} dF(x) = +\infty$ for any $\epsilon > 0$.

**The Lindy Effect**: For thin-tailed distributions, $\lim_{K\to\infty} \frac{1}{K}E(X|X>K) = 1$ (characteristic scale exists). For fat-tailed regular variation, this limit exceeds 1 (no characteristic scale).

### 5.0.3 Let Us Invent a Distribution

The chapter constructs a borderline distribution using the hyperbolic tangent: 
$$\overline{F}^\kappa(x) = \frac{1}{2}(1 - \tanh(\kappa x))$$

This distribution has kurtosis 21/5—slightly fatter than Gaussian but at the cusp of subexponentiality. It demonstrates how little it takes to cross from Gaussian to subexponential properties.

### 5.1 Level 3: Scalability and Power Laws

**Scalability**: For scale-free distributions, $\frac{P(X > nK)}{P(X > K)}$ depends on n, not K. These lack a characteristic scale and have Paretian tails: $P(X > x) = Cx^{-\alpha}$ for large x.

**Regular Variation Class $\mathfrak{P}$**:
$$\mathfrak{P} = \{X: \mathbb{P}(X > x) \sim L(x)x^{-\alpha}\}$$
where $L(x)$ is slowly varying ($\lim_{x\to\infty} \frac{L(tx)}{L(x)} = 1$).

Only scalable distributions have "true" fat tails—others eventually turn Gaussian under summation. The tail exponent $\alpha$ is asymptotic; we may never fully reach it, observing only intermediate versions.

### 5.1.2 Grey Swans

**Grey Swans**: Large deviations consistent with power law properties but that would be Black Swans to those stuck in thin-tailed frameworks. Figure 5.3 shows the British pound's Brexit jump—consistent with power law expectations despite appearing extreme to Gaussian-trained eyes.

The Student T is used as a convenient proxy for symmetric power laws because the center matters little for decision-making. The lower the exponent, the less the center plays a role.

### 5.2 Some Properties of Power Laws

**Property 1: Tail exponent of a sum**
For weighted sum $S_n = \sum w_i X_i$ with positive weights, $\alpha_s = \min(\alpha_i)$. Adding a single summand with undefined moments makes the total sum's corresponding moment undefined.

**Principle: Power Laws + Thin Tails = Power Laws**
Mixing power law and thin-tailed variables always results in power laws.

**Property 2: Transformations**
If X has tail exponent $\alpha$, then $X^p$ has tail exponent $\alpha/p$. A convex transformation thickens the tail—variance of a finite-variance variable with $\alpha < 4$ will be infinite.

### 5.3 Bell Shaped vs. Non-Bell Shaped Power Laws

The fatter the tails, the less the "body" matters. But for power laws with thinner tails, the slowly varying function (non-power law zone) plays a role. Figure 5.6 compares a double Pareto distribution (angular, double-convex) to a Student T (bell-shaped, semi-concave) with the same tail exponent—showing how central shape can differ despite identical tail behavior.

### 5.4 Interpolative Powers of Power Laws: An Example

**Jobless Claims during COVID-19**: Figure 5.7 shows what looked like an "unexpected" 30-standard-deviation jump. But Figure 5.8 (Zipf plot) reveals the data was always power law distributed—the jump was entirely consistent with the tail exponent. Only thin-tailed thinking made it surprising.

### 5.5 Super-Fat Tails: The Log-Pareto Distribution

The log-Pareto is the Paretian analog of the lognormal:
- If $X \sim \text{Pareto}(L,\alpha)$, then $e^X \sim \text{Log-Pareto}(L,\alpha)$
- PDF: $f(x) = \frac{\alpha L^\alpha \log^{-\alpha-1}(x)}{x}$, $x \geq e^L$
- Survival: $S(x) = L^\alpha \log^{-\alpha}(x)$

While a regular power law has asymptotic slope $-\alpha$ on log-log plot, the log-Pareto's slope approaches 0—yet no moments exist regardless of $\alpha$. Figure 5.9 compares the two.

### 5.6 Pseudo-Stochastic Volatility: An Investigation

A power law with constant scale can masquerade as a heteroskedastic (stochastic volatility) process. Figure 5.10 shows running realized volatility for Student T returns—it *looks* like stochastic volatility, but the scale is actually constant.

The distribution of squared returns from a Student T becomes a power law with tail exponent $\alpha/2$, explaining why volatility-of-volatility measures are unstable and why econometric reliance on heteroskedasticity is flawed—the variance of variance lacks structure.

**Key Takeaways:**
- Subexponentiality is the true boundary between thin and fat tails
- Power laws are defined by scalability—no characteristic scale
- The tail exponent determines moment existence and is preserved under summation
- Convex transformations thicken tails (variance of variance is fatter-tailed than variance)
- What looks like stochastic volatility may just be a constant-scale power law
- The lognormal sits at a strange boundary—behaving like thin tails at low variance, fat tails at high variance
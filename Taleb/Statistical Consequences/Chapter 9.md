## Summary of Chapter 9: Extreme Values and Hidden Tails

This chapter introduces extreme value theory (EVT) and applies it to the problem of "hidden tails"—the part of the distribution beyond the maximum observed in any finite sample. It formalizes the Lucretius fallacy: the fool believes the tallest river he's seen is the tallest river that exists.

### 9.1 Preliminary Introduction to EVT

**The Maximum Distribution**: For i.i.d. variables with CDF \(F(x)\), the distribution of the maximum \(M_n = \max(X_1, ..., X_n)\) is exact:
$$\mathbb{P}(M_n \leq x) = F(x)^n$$

While this exact form is usable for computation, the asymptotic structure (as \(n \to \infty\) and \(x \to x^*\), the distribution's endpoint) is more useful for general theory.

**The Fisher-Tippett-Gnedenko Theorem**: If there exist norming constants \(a_n > 0\) and \(b_n \in \mathbb{R}\) such that:
$$\mathbb{P}\left(\frac{M_n - b_n}{a_n} \leq x\right) \xrightarrow{n\to\infty} G(x)$$
then \(G(x)\) belongs to one of three families:

1. **Gumbel (Type 1, \(\xi = 0\))**: \(G(x) = \exp(-\exp(-(x - b_n)/a_n))\)
   - For distributions with exponential tails (normal, exponential, gamma)

2. **Fréchet (Type 2, \(\xi = 1/\alpha > 0\))**: \(G(x) = \exp(-(x/a_n)^{-\alpha})\) for \(x > 0\)
   - For distributions with power law tails (Pareto, Student t, Cauchy)
   - \(\alpha\) is the same tail exponent from the underlying distribution

3. **Weibull (Type 3, \(\xi = -1/\alpha < 0\))**: \(G(x) = \exp(-(-x/a_n)^{\alpha})\) for \(x < 0\)
   - For distributions with finite right endpoints (bounded distributions)

### 9.1.1 How Any Power Law Tail Leads to Fréchet

For a Pareto distribution with CDF \(F(x) = 1 - (L/x)^\alpha\), the exact PDF of the maximum is:
$$\psi(x) = \frac{\alpha n (L/x)^\alpha (1 - (L/x)^\alpha)^{n-1}}{x}$$

The Fréchet PDF is:
$$\phi(x) = \alpha \beta^\alpha x^{-\alpha-1} e^{-\beta^\alpha x^{-\alpha}}$$

For large \(x\), these converge when \(\beta = L n^{1/\alpha}\). This shows that the tail exponent \(\alpha\) is preserved—the maximum has the same tail exponent as the underlying variables.

**Property**: The tail exponent of the maximum of i.i.d. random variables equals the tail exponent of the variables themselves.

### 9.1.2 Gaussian Case

Unlike power laws, the Gaussian converges to its extreme value distribution (Gumbel) with "extreme slowness." Fisher and Tippett noted this in 1928. The norming constants are more complicated, and the approximation is poor in the tails (Figures 9.3 and 9.4). For practical work, it's better to use the exact distribution of the maximum from the Gaussian CDF:
$$\frac{\partial F^{(s)}(K)}{\partial K} = \frac{e^{-K^2/2} 2^{\frac{1}{2}-n} n \,\text{erfc}\left(-\frac{K}{\sqrt{2}}\right)^{n-1}}{\sqrt{\pi}}$$

### 9.1.3 The Pickands-Balkema-de Haan Theorem

This theorem concerns the conditional distribution of exceedances above a high threshold \(u\). Define:
$$F_u(y) = \mathbb{P}(X - u \leq y | X > u) = \frac{F(u + y) - F(u)}{1 - F(u)}$$

As \(u \to x^*\) (the distribution's endpoint), \(F_u(y)\) converges to the **Generalized Pareto Distribution (GPD)**:
$$G_{\xi,\sigma}(x) = \begin{cases} 1 - (1 + \xi x/\sigma)^{-1/\xi} & \xi \neq 0 \\ 1 - \exp(-x/\sigma) & \xi = 0 \end{cases}$$

- \(\xi > 0\): Pareto distribution (power law tails)
- \(\xi = 0\): Exponential distribution
- \(\xi = -1\): Uniform distribution

This theorem allows inference about tail behavior by focusing on exceedances above a threshold, without specifying the entire distribution.

### 9.2 The Invisible Tail for a Power Law

**The Hidden Moment**: Let \(K_n\) be the maximum observed in a sample of size \(n\). The \(p\)-th moment can be decomposed into:
$$\mathbb{E}(X^p) = \underbrace{\int_L^{K_n} x^p \phi(x) dx}_{\text{observed}} + \underbrace{\int_{K_n}^\infty x^p \phi(x) dx}_{\text{hidden}}$$

The hidden part represents the contribution from values larger than anything yet seen.

**Distribution of the Hidden Moment**: For a Pareto distribution with scale \(L\) and tail exponent \(\alpha\), the hidden \(p\)-th moment (for \(p > \alpha\)) has density:
$$g_{n,p,\alpha}(z) = n L^{\frac{ap}{p-a}} \left(z - \frac{pz}{\alpha}\right)^{\frac{p}{a-p}} \exp\left(n\left(-L^{\frac{ap}{p-a}}\right)\left(z - \frac{pz}{\alpha}\right)^{-\frac{p}{a-a}}\right)$$

The expectation of the hidden \(p\)-th moment is:
$$\mathbb{E}(\mu_{K,p}) = \frac{\alpha(L^p - L^\alpha K^{p-\alpha})}{\alpha - p}$$

For the survival function (\(p=0\)), the distribution is simply exponential:
$$g_{n,0,\alpha}(z) = n e^{-nz}$$

This is remarkable: **the distribution of exceedance probabilities for an empirical distribution does not depend on the fatness of the tails**—only on sample size \(n\).

**Practical Implications**: Figures 9.7-9.9 show the proportion of the mean that lies beyond the maximum observation. For \(\alpha\) close to 1, the hidden mean can be several times larger than the observed mean. This means that even with exhaustive historical data, the true mean may be much larger than the sample mean.

### 9.2.1 Comparison with the Normal Distribution

For a Gaussian, the expected invisible tail (for \(p=0\)) is approximately \(1/n\):
$$\int_0^\infty \frac{e^{-K^2/2} 2^{-n-\frac{1}{2}} n \,\Gamma\left(\frac{1}{2}, \frac{K^2}{\sqrt{2}}\right) \left(\text{erf}\left(\frac{K}{\sqrt{2}}\right) + 1\right)^{n-1}}{\pi} dK = \frac{1 - 2^{-n}}{n+1}$$

This decays much faster than for power laws, where the hidden tail can be substantial even for large \(n\).

### 9.3 Appendix: The Empirical Distribution is Not Empirical

This section drives home a critical point: while the empirical distribution function converges uniformly (Glivenko-Cantelli theorem) and its fluctuations are Gaussian (Donsker's theorem), these results concern **probabilities**, not **payoffs**.

**The Critical Distinction**:
- For probabilities: The error around the empirical distribution shrinks as \(1/\sqrt{n}\), regardless of the underlying distribution.
- For payoffs (expected values): The error depends critically on the tail behavior.

**The Result**: For U.S. stock market data, using the empirical distribution (rather than extrapolating the tail) underestimates tail risk by a factor of **5 to 70 times** (Figure 9.11). This is because:
1. The empirical distribution assigns zero probability to values beyond the observed maximum
2. Under fat tails, the probability of exceeding the observed maximum is not negligible
3. The payoff conditional on exceeding the maximum can be much larger than any observed value

**The Lucretius Fallacy in Practice**: The paper by Goetzmann, Kim, and Shiller (Figure 9.10) exemplifies this error. They survey investors about crash probabilities and compare their answers to the "base rate" from historical data—missing that the historical data itself underestimates the true probability of extremes.

### Key Takeaways

1. **Extreme value theory provides the tools to extrapolate beyond observed maxima**. The Fréchet distribution is the natural limit for power law tails.

2. **The tail exponent is preserved under maximization**. The maximum has the same tail exponent as the underlying variables.

3. **There is always a "hidden tail" beyond the observed maximum**. For power laws, this hidden part can dominate the mean, even for large samples.

4. **The empirical distribution is dangerously misleading for fat tails**. While it works well for probabilities (the chance of exceeding a threshold), it fails catastrophically for payoffs (the expected value conditional on exceedance).

5. **The Lucretius fallacy is not just philosophical—it's quantitative**. Using past maxima as a guide to future extremes underestimates risk by orders of magnitude.

**For investors and risk managers**: Any risk assessment based solely on historical data (without tail extrapolation) is systematically underestimating tail risk. The "empirical" approach is not empirical enough—it ignores the part of the distribution that hasn't shown up yet but inevitably will.
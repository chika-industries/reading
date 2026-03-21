## Summary of Chapter 19: Meta-Distribution of P-Values and P-Hacking

This chapter tackles one of the most fundamental issues in modern science: the reliability of p-values. Taleb derives the exact distribution of p-values across repeated experiments and shows that they are so unstable that most "statistically significant" results are essentially meaningless.

### 19.1 The Problem

**The Setup**: Scientists use p-values to determine if a result is "statistically significant." The standard threshold is p < 0.05. But what does this actually mean?

**The Question**: If you knew the "true" p-value (the probability you'd get by averaging over infinite experiments), what would the distribution of p-values look like across actual experiments? The answer is shocking.

**The Main Result**: The distribution of p-values is extremely skewed and volatile, regardless of sample size. Figure 19.1 shows this—even with large samples, p-values vary enormously across repetitions of the same experiment.

### 19.1 Proofs and Derivations

**Proposition 19.1**: For a one-tailed p-value from a paired t-test (unknown variance) with median value p_M, the distribution across identical copies of the experiment is:

$$\phi(p; p_M) = \begin{cases} \phi(p; p_M)_L & p < 0.5 \\ \phi(p; p_M)_H & p > 0.5 \end{cases}$$

The exact formula (equation 19.1) is complicated, involving inverse beta functions, but the behavior is what matters.

**Proposition 19.2**: For large n (the Gaussian limit), the distribution simplifies to:
$$\lim_{n\to\infty} \phi(p; p_M) = e^{-\text{erfc}^{-1}(2p_M)(\text{erfc}^{-1}(2p_M)-2\text{erfc}^{-1}(2p))}$$

The CDF is:
$$\Phi(k; p_M) = \frac{1}{2}\text{erfc}\left(\text{erf}^{-1}(1-2k) - \text{erf}^{-1}(1-2p_M)\right)$$

**What This Means**: Even in the large-sample limit, p-values are not stable. They follow a distribution that depends only on the median p-value p_M.

### The Devastating Implication

**Figure 19.2** shows the distribution of p-values when the true (median) p-value is 0.11:
- **53% of experiments will show p < 0.05** (statistically significant)
- **25% of experiments will show p < 0.01** (highly significant)

Yet the true p-value is 0.11—not significant by conventional standards. More than half of experiments will produce "significant" results from pure randomness.

**Figure 19.3** shows distributions for different p_M:
- When p_M = 0.5, the distribution is uniform—all p-values equally likely
- When p_M is small, the distribution is extremely right-skewed

**For a "true" p-value of 0.05** (borderline significant):
- 75% of experiments will show p < 0.05
- 60% of experiments with true p = 0.12 will show p < 0.05

This means: **a p-value of 0.05 in a single study tells you almost nothing**. The true p-value could easily be 0.12 (not significant) or 0.02 (highly significant).

### 19.2 Distribution of Minimum P-Value (P-Hacking)

**Proposition 19.3**: If you run m experiments and take the minimum p-value (common p-hacking practice), the distribution is:

$$\phi_m(p; p_M) = m e^{\text{erfc}^{-1}(2p_M)(2\text{erfc}^{-1}(2p)-\text{erfc}^{-1}(2p_M))} \left(1 - \frac{1}{2}\text{erfc}\left(\text{erfc}^{-1}(2p) - \text{erfc}^{-1}(2p_M)\right)\right)^{m-1}$$

**Figure 19.4** shows the expected minimum p-value as a function of m (number of trials). With just 5-10 trials, the minimum p-value plunges toward zero—even if nothing is real.

### 19.3 Inverse Power of Test

**Proposition 19.4**: The "power" of a test (probability of detecting a real effect) is similarly unstable. Uncertainty about parameters makes power calculations systematically optimistic.

### 19.4 Application and Conclusion

**The Bottom Line**:

1. **A p-value of 0.05 is meaningless**. To get what people *think* they're getting from p < 0.05, you need p < 0.005 or lower.

2. **The replication crisis is mathematically inevitable**. If true effects are modest (p_M ≈ 0.1-0.2), then by chance alone, many studies will show "significant" results that won't replicate. The Open Science project's finding that only 30-40% of psychology studies replicate is exactly what this math predicts.

3. **P-hacking is devastating**. Running just a few experiments and reporting the lowest p-value guarantees "significant" results regardless of truth.

4. **Power calculations are similarly biased**. Standard power analysis ignores the uncertainty in the underlying parameters, making studies seem more powerful than they really are.

### What This Means for Investors

This chapter might seem academic, but its implications for investment research are profound:

**1. Don't trust "statistically significant" factor research**

Hundreds of academic papers have found "significant" factors that predict stock returns (size, value, momentum, profitability, etc.). This chapter says: with true p_M around 0.1-0.2, more than half of these "discoveries" are expected to be false positives by pure chance.

**2. The replication crisis in finance is predictable**

Just as psychology studies failed to replicate, many "proven" factors will fail out-of-sample. The anomaly zoo is mostly statistical noise.

**3. Backtests are worse than you think**

When you backtest a strategy, you're implicitly running many experiments (different parameter choices, different time periods, different filters). The minimum p-value across these experiments is almost guaranteed to be "significant" even if the strategy has no edge.

**4. The threshold for "real" should be much lower**

If a study reports p = 0.05, assume it's noise. If it reports p = 0.001, it might be real—but even then, there's a chance it's a fluke. The only convincing evidence is:
- Multiple independent replications
- With p < 0.01 each
- And a strong theoretical basis

**5. The more people look, the more false positives**

With thousands of quants and academics mining the same data, the number of "discovered" factors is guaranteed to explode. Most are spurious correlations that will disappear.

**6. Meta-analyses are also biased**

If the underlying studies are biased (and they are), averaging them doesn't fix the problem. The meta-distribution of p-values means meta-analyses will overestimate true effects.

**7. For your own research**

If you're testing investment ideas:
- Pre-register your hypotheses (don't data-mine)
- Use much higher thresholds (p < 0.001, not 0.05)
- Adjust for multiple testing (if you try 20 ideas, one will look significant by chance)
- Require out-of-sample validation
- Be skeptical of your own "discoveries"

### A Concrete Example

Suppose 1,000 researchers each test whether a randomly chosen stock characteristic predicts returns. With no real effects, by chance alone:
- 50 will find p < 0.05
- 10 will find p < 0.01
- 1 will find p < 0.001

These 61 "discoveries" will be published. Journals will fill with "proven" factors. Investors will read about them. Hedge funds will try to trade them. All from pure noise.

This isn't a hypothetical—it's exactly what happened in finance. The "factor zoo" has hundreds of claimed predictors, most of which are almost certainly spurious.

### The Bottom Line

This chapter is a devastating critique of the entire enterprise of statistical significance testing. The p-value is not a reliable measure of evidence. The distribution of p-values across experiments is so wide that a single p < 0.05 result is essentially uninformative.

For investors, the lesson is simple: **be deeply skeptical of any claim that rests on p < 0.05**. The bar for "evidence" in quantitative finance should be much, much higher. Most published research is noise. Most backtested strategies are data-mined artifacts. Most "proven" factors will fail.

As Taleb puts it: "From a probabilistic standpoint, neither a p-value of .05 nor a 'power' at .9 appear to make the slightest sense." If you're making investment decisions based on such flimsy evidence, you're not investing—you're gambling.
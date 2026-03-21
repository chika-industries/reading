## Summary of Chapter 8: How Much Data Do You Need? An Operational Metric for Fat-Tailedness

This chapter introduces a practical, operational metric (the **kappa metric**, \(\kappa\)) to answer a deceptively simple question: "How much data do you need to make meaningful statements about a given dataset?" It bridges the gap between asymptotic theory (what happens as \(n \to \infty\)) and the real world where \(n\) is always finite.

### 8.1 Introduction and Definitions

**The Problem**: Conventional measures of fat-tailedness—the tail index \(\alpha\) for power laws and kurtosis for finite-moment distributions—fail to allow comparisons across different distribution classes. How can you compare:
- A sum of 100 Student T variables with 3 degrees of freedom to a Lévy-stable distribution?
- A Pareto distribution with \(\alpha = 2.1\) (finite variance) to a Gaussian?
- A lognormal with high variance to a power law?

Existing metrics don't provide answers. The kappa metric fills this gap by measuring **how much additional data helps stabilize the observed mean**.

**The Intuition**: Figure 8.1 shows what \(\kappa\) measures: how the mean absolute deviation of the sum \(S_n = X_1 + ... + X_n\) grows as sample size increases. For a Gaussian, it grows like \(\sqrt{n}\); for fatter tails, it grows faster, meaning you need more data to achieve the same stability.

### 8.2 The Metric

**Definition**: Let \(X_1, ..., X_n\) be i.i.d. with finite mean, \(S_n\) the partial sum, and \(\mathbb{M}(n) = \mathbb{E}(|S_n - \mathbb{E}(S_n)|)\) the expected mean absolute deviation from the mean. Define \(\kappa\) by:

$$\frac{\mathbb{M}(n)}{\mathbb{M}(n_0)} = \left(\frac{n}{n_0}\right)^{\frac{1}{2-\kappa_{n_0,n}}}$$

Solving for \(\kappa\):

$$\kappa(n_0,n) = 2 - \frac{\log(n) - \log(n_0)}{\log\left(\frac{\mathbb{M}(n)}{\mathbb{M}(n_0)}\right)}$$

**Properties**:
- \(\kappa \in [0,1]\) (can be negative in bimodal cases, but not for unimodal distributions)
- \(\kappa = 0\) for the Gaussian (maximally thin-tailed)
- \(\kappa = 1\) for a Cauchy or any distribution without a finite mean
- Higher \(\kappa\) means slower convergence of the law of large numbers

**Why Mean Absolute Deviation?** MAD is used instead of standard deviation because it remains well-defined even when variance is infinite. Under power laws, the second moment is unstable and uninformative; MAD is far more robust.

### 8.3 Stable Basin of Convergence as Benchmark

For stable distributions with index \(\tilde{\alpha} \geq 1\), a beautiful simplification occurs:
$$\mathbb{M}(n) = n^{1/\tilde{\alpha}} \mathbb{M}(1)$$
and consequently:
$$\kappa_{(n_0,n)} = 2 - \tilde{\alpha}$$

This means:
- For Gaussian (\(\tilde{\alpha}=2\)): \(\kappa = 0\)
- For Cauchy (\(\tilde{\alpha}=1\)): \(\kappa = 1\)
- For stable distributions, \(\kappa\) is constant regardless of \(n\)

The preasymptotic question becomes: how does \(\kappa_n\) converge to \(2 - \tilde{\alpha}\), and at what rate?

**Practical Significance**: Any \(\kappa > 0.15\) indicates a high degree of unreliability for "normal approximation" confidence intervals. Most research in fat-tailed domains should be viewed with skepticism.

### 8.4 Technical Consequences

**Sample Size Requirements**: To achieve the same reduction in mean absolute error as a Gaussian sample of size \(n_g\), a fat-tailed distribution requires:

$$n_v \approx n_g^{-\frac{1}{\kappa_1 - 1}}$$

Examples:
- Student T with 3 degrees of freedom (\(\alpha=3\)): requires 120 observations to match Gaussian with 30 (4× more data)
- Pareto with same \(\alpha=3\): requires 543 observations to match Gaussian with 30 (18× more data)
- Pareto "80/20" (\(\alpha \approx 1.14\)): requires \(>10^9\) more observations than Gaussian

This shows that **finiteness of variance is not an indication of thin-tailed behavior** for practical purposes.

**Asymmetric Distributions**: A one-tailed Pareto is "fatter" than a symmetric power law with the same exponent. This matters because the stable distribution (which is symmetric in the limit) is rarely observed in practice—real data is often one-tailed.

**Convergence of Student T to Gaussian**: For the cubic Student T (\(\alpha=3\)), \(\kappa\) converges to 0 at rate \(1/\log(n)\)—excruciatingly slow. Even with \(10^6\) observations, the behavior is not Gaussian. This confirms Mandelbrot's intuition that the cubic acts like a power law in the tails.

**The Lognormal Paradox**: The lognormal behaves like a Gaussian at low variance (\(\sigma\) small) and like a power law at high variance (\(\sigma\) large). As \(\sigma \to \infty\), \(\kappa \to 1\). This explains why debates about whether wealth is lognormal or Pareto are practically irrelevant—with high variance, they're indistinguishable for statistical purposes.

### 8.5 Conclusion and Consequences

**Portfolio Construction**: The question "how much data do you need?" translates directly to "how many securities do you need?" for diversification. Markowitz optimization only works for \(\kappa\) near 0. For a Pareto close to 80/20, you need \(10^9\) more securities than Gaussian-based theory suggests. The simple \(1/n\) heuristic (equal weighting) outperforms Markowitz optimization under fat tails—what behavioral economists call a "bias" is actually rational.

**Statistical Inference**: The kappa metric provides guidance on sample sufficiency for forecasting. For example, determining whether climate conditions "have changed" requires vastly different sample sizes depending on the fat-tailedness of the data.

### 8.6 Appendix: Derivations and Proofs

**Cubic Student T (\(\alpha=3\))**: The mean absolute deviation for n summands is:
$$\mathbb{M}(n) = \frac{2\sqrt{3}}{\pi}(e^n n^{-n}\Gamma(n+1,n) - 1)$$
where \(\Gamma(.,.)\) is the incomplete gamma function. This yields \(\kappa_{1,n} = 2 - \frac{\log(n)}{\log(e^n n^{-n}\Gamma(n+1,n) - 1)}\), which converges to 0 as \(1/\log(n)\).

**Lognormal Sums**: The lognormal does not have a closed-form characteristic function, but its cumulants show that:
- As \(\sigma \to 0\), \(\kappa \to 0\) (Gaussian behavior)
- As \(\sigma \to \infty\), \(\kappa \to 1\) (power law behavior)
- For intermediate \(\sigma\), the Pearson IV distribution provides a good approximation

**Exponential**: The exponential distribution sits at the cusp of subexponentiality. Its \(\kappa\) converges to 0 slowly: \(\lim_{n\to\infty} \log(n)\kappa_{1,n} = 4 - 2\log(2\pi)\).

**Negative Kappa**: Occurs in bimodal distributions where the means are separated by several standard deviations (e.g., a mixture of two Gaussians with different means). These have thinner tails than the Gaussian and negative excess kurtosis.

**Key Takeaways:**
- The kappa metric provides a practical way to compare fat-tailedness across distributions
- Finite variance does not imply fast convergence—the cubic Student T requires \(10^6\) observations to approach Gaussianity
- The lognormal is a chameleon: thin-tailed at low variance, fat-tailed at high variance
- Sample size requirements for fat-tailed data are often orders of magnitude larger than intuition suggests
- Portfolio diversification requires far more securities than Markowitz theory indicates
- The \(1/n\) heuristic is not a bias but a rational response to fat tails
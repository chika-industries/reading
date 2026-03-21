## Summary of Chapter 7: Limit Distributions, A Consolidation

This chapter provides a comprehensive overview of limit theorems (law of large numbers and central limit theorem) with a focus on preasymptotic behavior—what happens when the number of summands is large but not infinite. It establishes the foundation for understanding how different distributions converge (or fail to converge) to their limiting forms.

### 7.1 Refresher: The Weak and Strong LLN

**Weak Law of Large Numbers**: The sample average \(\overline{X}_n\) converges in probability to the expected value \(\mu\). For any \(\epsilon > 0\):
$$\lim_{n\to\infty} \mathbb{P}(|\overline{X}_n - \mu| > \epsilon) = 0$$

**Strong Law of Large Numbers**: The sample average converges almost surely to \(\mu\):
$$\mathbb{P}\left(\lim_{n\to\infty}\overline{X}_n = \mu\right) = 1$$

Finiteness of variance is not necessary for the LLN to hold—only finite mean is required. The assumptions can be relaxed: non-identical distributions are allowed under certain conditions (finite second moments, weak dependence), but the i.i.d. case with finite mean is sufficient.

### 7.2 Central Limit in Action

**Generalized Central Limit Theorem (GCLT)**:
$$\frac{S_n - a_n}{b_n} \xrightarrow{D} X_s$$
where \(X_s\) follows a stable distribution \(S(\alpha_s, \beta, \mu, \sigma)\). The stable distribution is characterized by its characteristic function:
$$\chi(t) = e^{(i\mu t - |t\sigma|^{\alpha_s}(1 - i\beta \tan(\frac{\pi\alpha_s}{2})\text{sgn}(t)))} \quad (\alpha_s \neq 1)$$

The stable class includes the Gaussian (\(\alpha_s = 2\)), Cauchy (\(\alpha_s = 1\)), and Lévy (\(\alpha_s = 1/2\)) distributions. Stable distributions are "stable under summation": summing copies yields the same distribution family.

**LLN for Stable Distributions**: For \(1 < \alpha_s \leq 2\), the characteristic function converges to that of a Dirac delta at \(\mu\):
$$\lim_{n\to\infty} \chi(t/n)^n = e^{i\mu t}$$

### 7.3 Speed of Convergence of CLT: Visual Explorations

The chapter examines four cases to illustrate how convergence speed varies dramatically across distributions:

**Fast Convergence: The Uniform Distribution**
- With just n=3 summands, the distribution is already nearly bell-shaped
- The uniform sum distribution has an explicit piecewise polynomial form

**Semi-Slow Convergence: The Exponential**
- Sum of exponentials follows a gamma distribution
- Convergence is slower than uniform due to skewness
- Requires symmetry to approach Gaussian

**The Slow Pareto**
- For Pareto with \(\alpha = 2\) (finite variance), convergence is extremely slow
- Figure 7.5 shows that even with n=1000, the distribution retains its skewness
- The characteristic function involves the exponential integral and is computationally intensive

**The Half-Cubic Pareto (\(\alpha = 3/2\))**
- Despite finite variance, convergence to Gaussian is agonizingly slow
- Figure 7.7 shows that even with n=10,000, the distribution is still visibly non-Gaussian
- This distribution never becomes symmetric in any practical sample size

**Norming Constants**: For Pareto distributions with \(1 < \alpha_p < 2\), the norming constants are:
$$a_n = n\mathbb{E}(X)$$
$$b_n = \pi n^{1/\alpha_p}\left(2\sin\left(\frac{\pi\alpha_p}{2}\right)\Gamma(\alpha_p)\right)^{-1/\alpha_p}(c+d)^{1/\alpha_p}$$

For \(\alpha_p = 2\) (finite variance), \(b_n = \sqrt{c+d}\sqrt{n\log n}\)

### 7.4 Cumulants and Convergence

The excess cumulants provide a metric for convergence to Gaussianity. For the p-th cumulant:
$$K_n^p \triangleq \frac{(-i)^p \partial^p \log(\chi(\omega)^n)}{(-\partial^2 \log(\chi(\omega)^n))^2}$$

For distributions outside the power law class, \(K_n^p \to 0\) for all \(p > 2\) at rate \(N^{p-2}\). Table 7.1 shows the speed of convergence for various distributions:
- Poisson: \(K^{(4)} \propto 1/n\)
- Exponential: \(K^{(4)} \propto 3\lambda^2/n\)
- Gamma: \(K^{(4)} \propto 3/n\)
- Two-state stochastic volatility: \(K^{(4)} \propto 3(1-p)/pn\)

However, empirical evidence (Figure 10.2) shows that financial data does not exhibit this convergence—kurtosis does not drop with aggregation, indicating they are not in the Gaussian basin.

### 7.5 Technical Refresher: Traditional Versions of CLT

**Lindeberg-Lévy CLT**: For i.i.d. variables with finite variance \(\sigma^2\):
$$\sqrt{n}(\overline{X}_n - \mu) \xrightarrow{D} N(0, \sigma^2)$$

**Lyapunov's CLT**: For independent (not necessarily identically distributed) variables, if for some \(\delta > 0\):
$$\lim_{n\to\infty} \frac{1}{s_n^{2+\delta}} \sum_{i=1}^n \mathbb{E}(|X_i - \mu_i|^{2+\delta}) = 0$$
then \(\frac{1}{s_n}\sum (X_i - \mu_i) \xrightarrow{D} N(0,1)\)

**Lindeberg's Condition**: For all \(\epsilon > 0\):
$$\lim_{n\to\infty} \frac{1}{s_n^2} \sum_{i=1}^n \mathbb{E}\left[(X_i - \mu_i)^2 \cdot \mathbf{1}_{\{|X_i - \mu_i| > \epsilon s_n\}}\right] = 0$$
This condition is both sufficient and necessary under certain regularity conditions.

### 7.6 The Law of Large Numbers for Higher Moments

**Testing for Infinite Moments**: A visual test for fat-tailedness examines whether higher moments converge under the LLN. For a power law with exponent \(\alpha\), moments of order \(p > \alpha\) do not exist and will show occasional jumps in the cumulative average.

**MS Plot (Maximum-to-Sum)**: This diagnostic plots the contribution of the maximum observation to the total sum as n increases. If \(\mathbb{E}(X^p) < \infty\), then \(M_n^p / S_n^p \xrightarrow{a.s.} 0\). Figure 7.9 shows MS plots for the S&P 500—the fourth moment never converges, indicating it is infinite.

Table 7.2 presents kurtosis values for various financial securities at different aggregation levels (daily, 10-day, 66-day). The maximum quartic contribution (share of kurtosis from a single observation) ranges from 2% to 94%—demonstrating extreme instability.

### 7.7 Mean Deviation for a Stable Distribution

For stable distributions with finite mean (\(1 < \alpha_s \leq 2\)), the mean absolute deviation can be computed via the Hilbert transform of the characteristic function. The result is:

$$\mathbb{E}|X|_{(\alpha_s,\beta,\sigma,0)} = \frac{\sigma_s}{2\pi}\Gamma\left(\frac{\alpha_s - 1}{\alpha_s}\right)\left((1 + i\beta\tan(\frac{\pi\alpha_s}{2}))^{1/\alpha_s} + (1 - i\beta\tan(\frac{\pi\alpha_s}{2}))^{1/\alpha_s}\right)$$

This provides a way to measure dispersion in L¹ norm even when variance is infinite.

**Key Takeaways:**
- Convergence to the Gaussian is not universal—it can be excruciatingly slow
- The half-cubic Pareto (\(\alpha=1.5\)) remains non-Gaussian even at n=10,000
- Higher moments provide diagnostics: if kurtosis doesn't drop with aggregation, the distribution is not in the Gaussian basin
- MS plots reveal whether moments exist
- Mean absolute deviation is a robust dispersion measure even when variance is infinite
- The stable distribution family generalizes the CLT to fat-tailed cases



## Summary of Chapter 6: Thick Tails in Higher Dimensions

This chapter extends the analysis of fat tails from univariate to multivariate settings, revealing how higher dimensions amplify the challenges and introduce new phenomena that undermine standard statistical tools.

### 6.1 Thick Tails in Higher Dimension, Finite Moments

Using the same variance-preserving heuristic as in Chapter 4, the chapter shows how stochastic volatility in a multivariate Gaussian produces fatter tails. The joint distribution becomes a mixture of two Gaussians with different covariance matrices. The effect is analogous to the univariate case: a higher peak (more density near the center) and fatter tails (Figure 6.1). This concentration in the center is a hallmark of thick tails even in higher dimensions.

### 6.2 Joint Fat-Tailedness and Ellipticality of Distributions

**Elliptical distributions** are defined by a characteristic function of the form $\phi(t) = \exp(it'\mu)\Psi(t\Sigma t')$, meaning the distribution depends on a single covariance matrix $\Sigma$. Under ellipticity, all linear combinations are characterized solely by location and scale—a property crucial for portfolio theory. However, real-world returns are **not elliptical** due to stochastic correlations and covariances (Figure 6.3). This loss of ellipticity invalidates much of modern finance, including mean-variance optimization and the concept of diversification.

### 6.3 Multivariate Student T

The multivariate Student t distribution is a common model for symmetric power laws. Its PDF for a bivariate case with correlation $\rho$ is given. A crucial point: even when $\rho = 0$, the variables are **not independent** (unlike the Gaussian). Independence requires the joint density to factor into the product of marginals, which fails for thick-tailed elliptical distributions. This demonstrates that uncorrelatedness does not imply independence under fat tails.

### 6.4 Fat Tails and Mutual Information

Mutual information is a more powerful measure of dependence than correlation. For a bivariate Student t with correlation $\rho$ and tail exponent $\alpha$, mutual information is:
$$ \mathbb{I}_\alpha(X,Y) = -\frac{1}{2}\log(1-\rho^2) + \lambda_\alpha $$
where $\lambda_\alpha \to 0$ as $\alpha \to \infty$ (Gaussian limit). The extra term $\lambda_\alpha$ captures nonlinear dependence that correlation misses. Mutual information can detect dependencies even when correlation is zero.

### 6.5 Fat Tails and Random Matrices

The eigenvalues of random matrices follow the Wigner semicircle distribution for thin-tailed data with finite moments. Under fat tails, the distribution of eigenvalues changes: for power law tails with exponent $\alpha$, the fourth moment may not exist, and the limiting spectral distribution deviates from the semicircle. This affects principal component analysis (PCA), making it unreliable (as seen in Figure 3.26).

### 6.6 Correlation and Undefined Variance

A paradox: even when variances are infinite (so covariance is undefined), the **correlation coefficient** (sample Pearson correlation) remains bounded between -1 and 1 and can be computed. However, its sampling distribution is extremely heavy-tailed and converges very slowly. Figure 6.10 shows the distribution of sample correlation for a bivariate Cauchy—it is bimodal and extremely spread out, making it practically useless for inference. Thus, while correlation exists in principle, it is not a reliable statistic under fat tails.

### 6.7 Fat Tailed Residuals in Linear Regression Models

When regressing a thin-tailed variable (e.g., IQ) on a fat-tailed one (e.g., income), the residuals are fat-tailed. The coefficient of determination $R^2$ is then biased upward and converges to its true value extremely slowly. For infinite variance residuals, the expected $R^2$ tends to zero, but finite samples can show high values (Figure 6.13 shows an example with Cauchy residuals giving $R^2 = 0.985$ in a small sample). This invalidates many studies that use linear regression with fat-tailed data, particularly in social sciences.

**Key insight**: When a fat-tailed variable is regressed against a thin-tailed one, $R^2$ is systematically inflated and requires astronomical sample sizes to converge. Nonlinear transformations (e.g., taking logs) can help only if the transformation is exact—otherwise errors persist.

### Conclusion

Higher dimensions compound the problems of fat tails:
- Elliptical distributions are too restrictive; real data exhibit stochastic correlations.
- Uncorrelatedness ≠ independence.
- Correlation exists but is uninformative due to noise.
- Mutual information is a better dependence measure.
- PCA and factor analysis produce spurious factors.
- Regression $R^2$ is biased and misleading.

The chapter underscores that standard multivariate methods fail under fat tails, and more robust approaches (e.g., based on tail dependence or mutual information) are needed.
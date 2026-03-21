## Summary of Chapter 4: Univariate Fat Tails, Level 1, Finite Moments

This chapter begins the technical exploration of fat tails by focusing on the entry-level case: distributions where all moments remain finite. It builds intuition through simple heuristics and examines why standard deviation is a problematic metric.

### 4.1 A Simple Heuristic to Create Mildly Fat Tails

The chapter opens with a reminder about Jensen's inequality and convexity: tail probabilities are convex to the scale (standard deviation) of a distribution. This allows fattening tails by "stochasticizing" the variance—making it random while preserving the mean.

**Variance-Preserving Heuristic**: 
- Mix two Gaussians: N(0, σ√(1-a)) with probability 1/2 and N(0, σ√(1+a)) with probability 1/2
- This preserves the second moment (variance) but increases kurtosis to 3(a²+1)
- The parameter a acts like "volatility of volatility"

**Limitation**: This simple method can only double kurtosis, so it's mainly pedagogical.

**Improved Skewed Variance Heuristic**:
- Mix Gaussians with probabilities p and (1-p) and different variances
- Can achieve much higher kurtosis (up to 3000 with p=1/1000)
- Approximates lognormal stochastic volatility

**Gamma Variance**: Using gamma distribution for variance yields closed-form solutions with Bessel functions, allowing analytical tractability.

### 4.2 Does Stochastic Volatility Generate Power Laws?

The answer depends on what is stochasticized:
- Stochasticizing σ or σ² (with lognormal or gamma) → not power laws
- Stochasticizing 1/σ or 1/σ² → can produce power laws

Table 4.1 and 4.2 show transformations and moment conditions for different stochastic volatility specifications.

### 4.3 The Body, The Shoulders, and The Tails

**Where do the tails start?** The tails begin at the level of convexity to the scale parameter. For a Gaussian, stochasticizing σ creates:

- **Inner tunnel** (high peak): where density increases
- **Shoulders**: where density decreases (intermediate events become less likely)
- **Outer tails**: where density increases again

The crossover points for a Gaussian are at approximately -2.13σ, -0.66σ, 0.66σ, and 2.13σ. The tails proper start beyond ±2.13σ.

For a Student T with α=3, crossovers are at ±√(4-√13)s and ±√(4+√13)s ≈ ±1.3s and ±2.7s.

**Key insight**: Fat tails manifest with higher peaks (more concentration around the center), narrower shoulders, and fatter tails—a point frequently misunderstood.

### 4.4 Fat Tails, Mean Deviation, and the Rising Norms

**The Common Error**: People routinely confuse standard deviation (STD) with mean absolute deviation (MAD). In a famous study, investment professionals given MAD=1% wrongly answered that STD=1%, when the correct Gaussian value is ~1.25%. Under fat tails, the ratio STD/MAD increases dramatically—from ~1.25 for Gaussian to arbitrarily large values.

**Example**: For a distribution with 10⁶ observations of -1 and one observation of 10⁶, MAD=2 but STD=1000—a ratio of 500.

**The Fisher-Eddington Dispute**: In 1920, Fisher argued STD is 12% more "efficient" than MAD for Gaussian data, settling the matter in favor of STD. But this efficiency reverses with the slightest contamination—a minute presence of outliers makes MAD 5 times more efficient.

**Power Mean Inequality**: For any 1 ≤ p < q, the Lp norm is less than or equal to the Lq norm. As spread increases, higher moments explode. For a flat distribution {1,1}, all norms equal 1. Perturb to {1/2, 3/2} and norms rise: L₁=1, L₂≈1.12, L₃≈1.19, L₄≈1.26.

**Why retire standard deviation?** 
1. MAD is more accurate in-sample and less volatile
2. People intuitively think in MAD but equations use STD
3. MAD exists whenever the mean exists; STD requires finite second moment
4. Infinite variance models were dismissed because economists conflated them with infinite MAD

### 4.5 Visualizing the Effect of Rising p on Iso-Norms

Figures 4.13-4.15 show how the unit ball expands as the norm increases from L₁ to L∞. For dimension d=2, L₁ occupies half the square; L∞ occupies all of it. For d=3, L₁ occupies only 1/6 of the cube. The ratio of higher to lower moments increases with dimensionality—a hint at the curse of dimensionality and model error.

**Key Takeaways:**
- Fat tails mean higher peaks, narrower shoulders, and fatter tails—not just "more outliers"
- Standard deviation is a fragile metric that fails under fat tails
- The ratio STD/MAD is a simple diagnostic for fat-tailedness
- Mean absolute deviation should replace standard deviation in most applications
- The "tails" typically start around 2-3 standard deviations from the mean

The chapter concludes with references to further reading on subexponentiality, extreme value distributions, and stable distributions.
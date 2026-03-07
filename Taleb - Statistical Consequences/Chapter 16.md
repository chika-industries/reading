## Summary of Chapter 16: On the Tail Risk of Violent Conflict (with P. Cirillo)

This chapter applies the statistical machinery developed throughout the book to a real-world problem: understanding the risk of violent conflicts and wars. While the topic may seem removed from investing, the lessons are directly applicable to any domain with fat tails—including financial markets.

### 16.1 Introduction/Summary

**The "Long Peace" Debate**: Steven Pinker and others have argued that violence has declined over time—that we're living in the most peaceful era in human history. This claim rests on statistical analysis of conflict data.

**The Problem**: Violence data is:
- Fat-tailed (extreme events dominate)
- Incomplete (many conflicts unrecorded)
- Unreliable (estimates vary widely)
- Bounded (casualties can't exceed world population)

Standard statistical methods fail on all counts.

**The Core Finding**: When properly analyzed using extreme value theory and methods that account for boundedness, the data shows no evidence of declining violence. The "long peace" is likely a statistical illusion.

### 16.2 Summary Statistical Discussion

**The Results**:

1. **Paretian tails**: Conflict casualties follow a power law with tail exponent α ≈ 0.53 (using log-rescaled data). This means:
   - The mean is undefined in the unbounded case
   - Extreme events dominate all statistical properties
   - The difference between a "large" war and a "huge" war is scale-invariant

2. **Memorylessness**: The time between major conflicts (>50,000 casualties) follows an exponential distribution—no trend, no clustering, no "learning." The probability of a major war next year is the same regardless of how long it's been since the last one.

3. **Underestimated mean**: Table 16.1 shows that the true statistical mean (using MLE methods) is **3-4 times larger** than the sample mean. For conflicts >10,000 casualties:

| Threshold | Sample Mean | ML Mean | Ratio |
|-----------|-------------|---------|-------|
| 10K | 9.1M | 31.1M | 3.43 |
| 25K | 9.8M | 36.2M | 3.69 |
| 50K | 11.2M | 41.1M | 3.67 |
| 100K | 13.4M | 47.4M | 3.53 |
| 200K | 16.6M | 63.1M | 3.79 |
| 500K | 24.8M | 82.6M | 3.31 |

The "journalistic" average—just averaging observed conflicts—underestimates the true expected casualties by a factor of 3-4.

### 16.3 Methodological Discussion

**The Log Transformation**: Since casualties can't exceed world population, the data is bounded. The chapter uses the same smooth transformation from Chapter 15:

$$Z = L - H \log\left(\frac{H - Y}{H - L}\right)$$

This removes the upper bound while preserving tail behavior, allowing standard EVT methods.

**Dealing with Unreliable Data**: Historical casualty estimates vary wildly. The chapter uses Monte Carlo methods:
- For each conflict with lower/upper bounds, draw uniformly between them
- Run thousands of simulations
- The tail exponent α is robust to this uncertainty (Figure 16.1 shows the distribution across 100,000 simulations)

**Missing Events**: By jackknifing (randomly removing up to 30% of events) and checking parameter stability, they show the tail estimates are robust. Missing small/medium conflicts doesn't affect the tail—missing a large one would, but large ones are precisely the ones recorded.

### 16.4 Data Analysis

**Figures 16.3 and 16.4** show conflict casualties over time:
- Raw data: appears to show increase (population growth)
- Rescaled data (adjusting for world population): appears to show decrease
- Both are misleading—they focus on means, not tails

**Peaks Over Threshold**: Using EVT with threshold u = 50,000 casualties, Table 16.4 gives the GPD parameters:

| Data Type | ξ | β |
|-----------|-----|-----|
| Raw Data | 1.59 | 3.63 |
| Naive Rescaling | 1.87 | 14.33 |
| Log-rescaling | 1.87 | 14.33 |

ξ > 1 means **no moments exist**—the distribution is extremely fat-tailed.

**Inter-arrival Times**: Tables 16.2 and 16.3 show average waiting times between large conflicts:

For events >10 million casualties (actual estimates):
- Average wait: 102 years
- Mean absolute deviation: 144 years

For rescaled data:
- Average wait for 50M+ events: 68 years
- MAD: 79 years

**The implication**: 70 years without a world war is *nothing*. It's completely consistent with the distribution having no trend. Claiming "peace" after 70 years is like flipping a coin 70 times, getting 70 heads, and declaring the coin has changed.

### 16.5 Additional Robustness and Reliability Tests

**Bootstrap Analysis**: Figures 16.11-16.13 show the distribution of ξ across 100,000 bootstrap samples:
- Raw data: ξ centered around 1.6, always >1
- Rescaled data: ξ centered around 1.9, always >1

The fat-tailedness is robust to sampling variation.

**Perturbation Across Bounds**: Figures 16.14-16.16 show p-values, sample means, and MLE means across 100,000 combinations of high/low estimates. The results are stable—the tail exponent doesn't change much with different historical estimates.

### 16.6 Conclusion: Is the World More Unsafe Than It Seems?

**The Answer**: Yes. Violence is systematically underestimated by naive methods that:
- Focus on sample means rather than tail estimates
- Ignore the stochastic nature of inter-arrival times
- Treat bounded data as unbounded
- Fail to account for the hidden tail

**Key Points**:

1. **A large event wouldn't change the statistical picture**. If a war with 3× the mean casualties occurred, it wouldn't require re-estimating the parameters—it would be entirely consistent with the existing distribution.

2. **The waiting time is memoryless**. You can't say "we haven't had a world war in 70 years, so we're due" or "so we're safe." The probability is the same every year.

3. **The true mean is 3-4× larger than the sample mean**. Any analysis using historical averages is underestimating risk by a factor of 3-4.

4. **Survivorship bias cuts the other way**. The fact that we're here to study history means the world was *less* violent than it could have been. Adding this bias would increase estimated risk further.

### What This Means for Investors

This chapter is a masterclass in how to think about **any risk with fat tails**. The lessons transfer directly to financial markets:

**1. Sample means are useless for fat-tailed risks**

The average return of the S&P 500 over 100 years is not a reliable estimate of the true mean. The "shadow mean" could be significantly different. Historical averages are not "robust"—they're systematically biased.

**2. "This time is different" cuts both ways**

Pinker claimed violence declined based on 70 years of data. The same mistake is made in markets: "We haven't had a crash in 10 years, so we're safer" (wrong) or "We haven't had a crash in 10 years, so we're due" (also wrong). Memoryless processes don't work that way.

**3. Waiting times are uninformative about trends**

If a crash happens every 10 years on average, going 20 years without one is not evidence that crashes have been "solved." It's just a 13.5% probability event (e^(-20/10)). The same logic applies to the "long peace"—70 years without a world war is a 0.5% event under exponential waiting times, but that doesn't prove the distribution changed.

**4. The hidden tail is always there**

Just as the true mean of conflict casualties is 3-4× the sample mean, the true expected drawdown of the S&P 500 is larger than any historical drawdown. The 2008 crash wasn't the worst possible—it was just the worst so far.

**5. Robustness checks matter**

The chapter's methodology—bootstrapping, perturbing estimates, jackknifing—shows how to test whether your conclusions are driven by a few data points. For the S&P 500, the 1987 crash drives most of the kurtosis. Remove it and your risk estimates change dramatically. That's a sign your estimates aren't robust.

**6. Policy implications**

If you're a pension fund manager or a central banker, using historical averages to set risk limits is dangerous. The true risk is larger than the data suggests. The "long peace" in markets (low volatility periods) is just as illusory as the long peace in geopolitics.

### The Bottom Line for Investors

This chapter is a warning: **if you're using historical averages to estimate risk, you're systematically underestimating it**. The bias isn't random—it's always downward. The true mean is larger (for positive risks) or more negative (for negative risks) than your sample suggests.

The correct response isn't to give up on risk management—it's to:
1. Use extreme value theory, not sample moments
2. Account for boundedness through appropriate transformations
3. Test robustness by perturbing your data
4. Recognize that long periods without extreme events prove nothing

As Taleb puts it: "To make a scientific pronouncement about the drop in the incidence of wars of a certain magnitude, wait three times as long as the mean inter-arrival times. For large wars such as WW1 and WW2, wait 300 years. It is what it is."
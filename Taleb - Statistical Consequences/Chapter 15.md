## Summary of Chapter 15: Shadow Moments of Apparently Infinite-Mean Phenomena

This chapter (co-authored with P. Cirillo) introduces a powerful concept called the "shadow mean"—the true statistical mean of a process that, based on available data, appears to have an infinite mean. This is directly relevant to investors because it explains why historical averages can be dangerously misleading.

### 15.1 Introduction

**The Problem**: Some phenomena appear to have infinite mean based on observed data—the sample mean keeps jumping, never settling down. But in reality, these phenomena have a finite upper bound (the world's population for wars, total market capitalization for stocks, etc.). The data hasn't yet revealed the bound, so we mistakenly think the mean doesn't exist.

**Figure 15.1** illustrates this: you observe data up to some maximum M, but the true upper bound H is much larger and unseen. The "apparent tail" (what you see) and the "real tail" (what exists) are indistinguishable until you get close to H.

### 15.2 The Dual Distribution

**The Insight**: Instead of truncating the distribution (which creates an artificial "cliff" at H), apply a smooth transformation that removes the upper bound:

$$Z = \phi(Y) = L - H \log\left(\frac{H - Y}{H - L}\right)$$

This transformation:
- Maps the bounded variable Y (in [L, H]) to an unbounded variable Z (in [L, ∞))
- Is smooth (no cliffs or discontinuities)
- Preserves the tail behavior: for large H, Z ≈ Y until you approach H

Now Z can be modeled using standard extreme value theory (like the Generalized Pareto Distribution) without worrying about the bound.

### 15.3 Back to Y: The Shadow Mean

After fitting the tail of Z using EVT, you transform back to Y to get the "shadow mean"—the true expected value that accounts for the unseen part of the distribution.

**The Result**: For a Pareto-like tail with exponent α, the conditional mean above a threshold L* is:

$$E[Y | Y > L^*] = (H - L^*) e^{\frac{\alpha\sigma}{H}} \left(\frac{\alpha\sigma}{H}\right)^\alpha \Gamma\left(1-\alpha, \frac{\alpha\sigma}{H}\right) + L^*$$

This looks complicated, but the key point is: **the true mean can be dramatically larger than the sample mean**.

**Table 15.1** (from Chapter 16) shows this for conflict data. For conflicts with >10,000 casualties:
- Sample mean: 9.1 million
- Shadow mean (MLE): 31.1 million
- Ratio: 3.43× larger

This pattern holds across different thresholds—the true mean is consistently 3-4× larger than what you'd naively calculate from historical data.

### 15.4 Comparison to Other Methods

The chapter compares three ways to handle bounded fat-tailed data:

1. **Hard truncation**: Set an endpoint H and normalize. Creates an artificial cliff—density drops to zero abruptly.

2. **Absorbing barrier**: Compress all mass above H into a Dirac delta at H. Also creates a cliff.

3. **Smooth transformation (this chapter)**: No cliff, gradual approach to H.

Figure 15.3 shows the ratio of smooth to truncated expectations. For α < 1, the smooth transformation gives much higher expectations—sometimes 2-3× higher.

### 15.5 Applications

This method applies to many real-world phenomena relevant to investors:

**Operational Risk**: A firm's losses are bounded by its capitalization, but extreme losses can still be huge. The shadow mean tells you the true expected loss.

**Reinsurance Contracts**: Almost all have caps, but multiple contracts on the same risk can aggregate to large exposures. Shadow moments capture this.

**Credit Risk**: Loans have finite maximum loss (the loan amount), but portfolios of loans have complex tail behavior.

**City Size**: Cities follow Zipf's law (power law), but no city can exceed world population. Shadow moments adjust for this bound.

**Company Size**: Sales are bounded by global GDP, but the tail of the distribution is still fat. The true expected size of the largest companies is larger than historical data suggests.

**Earthquakes, Floods, etc.**: Natural catastrophes have physical upper bounds, but historical data hasn't seen them.

### What This Means for Investors

**1. Historical averages systematically underestimate true expected values**

If you're using historical average returns of the S&P 500 to forecast the future, you're likely underestimating the true mean. The "shadow mean" could be significantly higher—or lower, depending on the bound.

**2. This cuts both ways**

For positively skewed variables (like stock returns over long periods), the shadow mean is *higher* than the sample mean. The unseen right tail (once-in-a-century bull markets) contributes more than history shows.

For negatively skewed variables (like drawdowns), the shadow mean is *more negative* than the sample mean. The unseen left tail (once-in-a-century crashes) is worse than anything in the record.

**3. Bounds matter, even if you can't see them**

The fact that stock markets have no absolute upper bound (in theory) but do have a practical upper bound (global wealth) means the true distribution is bounded but the bound is so high you'll never see it. This chapter's method handles that.

**4. For retirement planning, this is crucial**

If you're using historical return data to run Monte Carlo simulations for retirement, you're implicitly assuming the future will look like the past. But the shadow mean says: even if the underlying process is unchanged, the *true* expected return over your remaining lifetime is different from the historical average, because you haven't seen the full distribution.

**5. For risk management, it's even more crucial**

Value at Risk (VaR) and Expected Shortfall (ES) based on historical data are systematically biased. The true ES (expected loss given a crash) is larger than any historical crash suggests. This chapter provides a way to estimate it.

**6. The "Pareto 80/20" rule is even more extreme**

If the true mean is 3-4× larger than the sample mean for conflict data, similar logic applies to wealth concentration. The oft-cited "top 1% owns 50%" might actually be "top 1% owns 70-80%" once you account for the unseen tail. This aligns with Chapter 14's point that measured inequality is systematically too low.

### A Concrete Example for S&P 500 Investors

Imagine you have 100 years of S&P 500 returns. The maximum annual return is, say, +50% (1933). The minimum is -40% (1931). Based on this, you might think returns are bounded between -40% and +50%.

But in reality, the distribution is unbounded above (in theory) and bounded below only by -100%. The "shadow mean" approach says:

1. Transform returns using the log function (already common in finance)
2. Fit the tail of log returns using EVT
3. Transform back to get the true expected return, accounting for the possibility of returns larger than any seen historically

The result: your historical average might be 10%, but the shadow mean could be 12% or 8%, depending on the tail behavior. The point isn't that it's always higher—it's that the historical average is not the right number.

### The Bottom Line

This chapter gives investors a framework for thinking about **what you don't know**. The data you have is just a sample from a distribution that extends beyond your experience. The true mean of that distribution—the "shadow mean"—can be estimated using extreme value theory and smooth transformations, but it will never equal the sample mean.

For long-term investors, this means:
- Don't treat historical averages as gospel
- The future will eventually reveal outcomes outside your experience
- Prudent planning accounts for this uncertainty
- The "shadow" is real, even if you can't see it yet
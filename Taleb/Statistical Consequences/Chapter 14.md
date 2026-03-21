## Summary of Chapter 14: On the Super-Additivity and Estimation Biases of Quantile Contributions

This chapter (co-authored with R. Douady) tackles another seemingly technical topic that has huge implications for how we understand inequality—and by extension, how we interpret any "top x% owns y%" statistics that appear constantly in financial media.

### 14.1 Introduction

**The 80/20 Rule**: Vilfredo Pareto noticed that 80% of Italy's land belonged to 20% of the population. This self-similarity means the top 1% should own about 53% of wealth. But here's the problem: **the measured share of the top 1% is systematically biased downward** when calculated the usual way.

**The Core Problem**: For fat-tailed variables (wealth, income, company sizes, market caps), the in-sample quantile contribution—what you calculate from your data—is a biased estimator of the true value. It's always too low.

### 14.2 Estimation for Unmixed Pareto-Tailed Distributions

**Definition**: The quantile contribution κ_q is the share of the total held by the top q%:
$$\kappa_q = \frac{q E[X | X > h(q)]}{E[X]}$$

The natural estimator is just: take your sample, find the top q%, sum their wealth, divide by total wealth.

**The Bias**: Table 14.1 shows the problem for α = 1.1 (similar to wealth distribution):

| Sample Size | Estimated κ (mean) | True κ = 0.658 |
|-------------|-------------------|----------------|
| 1,000 | 0.405 | -0.253 bias |
| 10,000 | 0.486 | -0.172 bias |
| 100,000 | 0.539 | -0.119 bias |
| 1,000,000 | 0.581 | -0.077 bias |
| 10,000,000 | 0.592 | -0.066 bias |
| 100,000,000 | 0.607 | -0.051 bias |

Even with **100 million observations**, the estimated top 1% share is still 5% below the true value. For smaller samples (like most surveys), the bias is enormous.

**Why?** The estimator is **concave** in large observations. When a new billionaire appears in your sample, the measured top 1% share increases, but less than it should. The concavity means you're systematically truncating the contribution of the very largest values.

### 14.3 An Inequality About Aggregating Inequality

**The Super-Additivity Result**: This is the killer insight. If you measure inequality in subgroups and average them, you get a **lower** number than if you measure inequality in the combined group.

$$\kappa_q(\text{combined}) > \text{average of } \kappa_q(\text{subgroups})$$

**In plain English**: Europe as a whole will appear more unequal than the average inequality of European countries. The US as a whole will appear more unequal than the average of states. The world as a whole will appear more unequal than the average of countries.

This means:
- You can't compare inequality across different-sized units
- A country with a larger population will naturally show higher measured inequality, all else equal
- "Rising inequality" over time might just reflect larger sample sizes or better data collection

### 14.4 Mixed Distributions for the Tail Exponent

**The Convexity Effect**: κ_q is a **convex function** of the tail exponent α. By Jensen's inequality:
$$\kappa_q(\text{average } \alpha) < \text{average of } \kappa_q(\alpha)$$

If there's uncertainty about the true α (and there always is), the estimated κ_q is biased downward. The more uncertainty, the larger the bias.

**Example**: If α is estimated at 1.5 but could be 1.2 or 1.8 with equal probability, the true κ_q is higher than if α were exactly 1.5 with certainty. Uncertainty about the tails makes inequality worse than your "best estimate" suggests.

### 14.5 A Larger Total Sum is Accompanied by Increases in κ̂_q

**The Correlation**: The estimated top share κ̂_q is positively correlated with the total sum S. When wealth increases, it's almost always because the rich got richer, not because everyone got richer equally.

Figure 14.5 shows this: as total wealth increases, the measured top share increases. This means:
- Economic growth naturally increases measured inequality
- You can't have growth without rising κ̂_q, unless the poor grow faster than the rich
- Comparing inequality across different levels of development is meaningless without adjustment

### 14.6 Conclusion and Proper Estimation of Concentration

**The Central Mistakes**:

1. **Using "robust" methods on fat-tailed data**: They're not robust—they're biased.
2. **Comparing inequality across time or space without adjustment**: Sample size effects dominate.
3. **Believing year-on-year changes in κ̂_q reflect real changes**: They might just be sampling noise.

**The Piketty Connection**: This chapter is a direct statistical critique of Thomas Piketty's work on rising inequality. If κ̂_q is biased upward with sample size and total wealth, then:
- As economies grow, measured inequality automatically rises
- As data collection improves, measured inequality automatically rises
- The "rise" might be entirely statistical, not real

**How to Measure Concentration Properly**:

1. **Use tail-based methods**: Estimate α, then derive κ_q from α. This is less biased and aggregates properly.
2. **Account for uncertainty**: Use the lower bound of α's confidence interval, not the point estimate.
3. **Don't trust naive quantile contributions**: They're systematically too low and the bias varies with sample size.

### What This Means for Investors

**1. Be skeptical of "top 1% owns X%" headlines**
- These numbers come from surveys with limited sample sizes
- The true number is almost certainly higher
- Year-to-year changes are likely noise, not signal

**2. Understand that market concentration measures have the same bias**
- "Top 10 stocks in the S&P 500 now account for 30% of market cap"
- This number is biased downward relative to the true concentration of the underlying economic activity
- As the market grows, measured concentration will naturally rise

**3. The "rising inequality" narrative may be statistically artefactual**
- Better data collection = higher measured inequality
- Economic growth = higher measured inequality
- Larger population = higher measured inequality
- The real trend is much harder to discern

**4. For portfolio construction, focus on tail exponents, not point estimates**
- If you're worried about concentration risk, estimate α
- Lower α means more concentration risk, regardless of what the current top 10 holdings look like
- The true concentration is always higher than the measured concentration

**5. When comparing markets or economies, adjust for size**
- The US will always look more concentrated than Switzerland, simply because it's bigger
- This doesn't mean the US economy is structurally more unequal
- It's a statistical artifact

### The Big Picture

This chapter, like the previous one, shows that **standard statistics break down under fat tails, and the breakdown is systematic and predictable**. The bias isn't random—it's always downward. You always underestimate concentration. You always underestimate inequality. You always think things are more equal than they really are.

For investors, this means:
- The risks you worry about (market concentration, wealth inequality, tail events) are worse than the data suggest
- The comforting statistics that say "things aren't that bad" are systematically biased
- Prudence means assuming the true concentration is higher than measured

The chapter ends with a pointed critique of Piketty and Pinker: both made claims about trends in inequality and violence using methods that, under fat tails, are guaranteed to produce biased results. The "decline of violence" and "rise of inequality" might both be statistical illusions—artifacts of using the wrong tools on the wrong data.
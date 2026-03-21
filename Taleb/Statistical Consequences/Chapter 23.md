## Summary of Chapter 23: Option Pricing Under Power Laws: A Robust Heuristic

This chapter (co-authored with the Universa team) provides a practical, robust method for pricing options when the underlying follows a power law distribution—which is to say, for all real-world assets. Unlike Black-Scholes, which requires knowing volatility and assumes thin tails, this method requires only the tail exponent α and one anchor option price.

### 23.1 Introduction

**The Karamata Point**: For a power law distribution, there comes a point beyond which the slowly varying function L(x) becomes effectively constant. This is the "Karamata constant" (Figure 23.1). Beyond this point, the distribution follows the strong Pareto law:
$$P(X > x) = l x^{-\alpha}$$

This is the region where the tail is "pure" power law—no more slowly varying complications.

**The Key Insight**: Once you're in the Karamata region, option prices have a simple closed form. All the complexity of the distribution below the threshold is captured in a single constant (l), which can be backed out from one observable option price.

### 23.2 Call Pricing Beyond the Karamata Constant

**First Approach: S is in the Regular Variation Class**

If the underlying price S itself has survival function in the regular variation class, then for all strikes K > l and α > 1:
$$C(K) = \frac{K^{1-\alpha} l^\alpha}{\alpha - 1}$$

This is remarkably simple. The option price is proportional to K^{1-\alpha}.

**Result 1: Relative Pricing**
For any two strikes K₁, K₂ ≥ l:
$$C(K₂) = \left(\frac{K₂}{K₁}\right)^{1-\alpha} C(K₁)$$

**This is the key practical result**. If you know the price of one tail option (say, the 10% out-of-the-money call) and you know α, you can price all further-out options by simple scaling. No volatility, no drift, no complicated models—just the tail exponent.

**The constant l disappears** in the ratio. You don't need to know it. The anchor option price contains all the information about the distribution below the Karamata point.

### 23.2.2 Second Approach: Geometric Returns in Regular Variation Class

More realistically, returns (S - S₀)/S₀ follow a power law, not the price itself. For this case:

$$C(K, S_0) = \frac{(l S_0)^\alpha (K - S_0)^{1-\alpha}}{\alpha - 1}$$

**Result 2: Relative Pricing**
For K₁, K₂ ≥ (1 + l)S₀:
$$C(K₂) = \left(\frac{K₂ - S_0}{K₁ - S_0}\right)^{1-\alpha} C(K₁)$$

Again, the scaling is simple—now in terms of moneyness (K - S₀) rather than absolute strike.

**Figure 23.5** shows the intuition on a log-log plot:
- Black-Scholes: curved, accelerating downward
- Power law: straight line with slope 1-α
- Lower α (fatter tails) = flatter slope = higher tail option prices

### 23.3 Put Pricing

For puts (left tail), the formula is more complicated because of the boundary at zero, but the same principle applies. Equation 23.7 gives the relative pricing relationship.

**The Key Point**: Put options in the left tail also follow a power law scaling, though with an adjustment for the fact that prices can't go below zero.

### 23.4 Arbitrage Boundaries

The power law scaling must be consistent with no-arbitrage conditions. In particular, the call spread condition (butterfly non-negativity) puts a lower bound on α:

$$\alpha \geq \frac{1}{-\log(K - S_0) + \log(l) + \log(S_0)} \times \text{[complicated expression]}$$

In practice, this means that for a given anchor option price and strike, not all α are possible—there's a consistency condition that must hold.

### 23.5 Comments

**The Key Comparison**:

**Figure 23.2** shows three option pricing curves:
- **Black-Scholes (constant volatility)** : curved, thin-tailed
- **Smile (stochastic volatility)** : curved but with fatter tails
- **Power law**: straight line on log-log plot, determined solely by α

**Figure 23.3** applies this to S&P 500 options:
- Market prices (blue) closely follow a power law
- The implied α from market prices is around 2.75
- This is consistent with the tail exponent estimated from historical returns

**Figure 23.4** shows the same in implied volatility terms. The power law model (blue) matches the market's volatility smile (red) remarkably well.

**The Controversial Implication**: Many academic papers claim that out-of-the-money options are "overpriced" because they're expensive relative to Black-Scholes with constant volatility. But this chapter shows: **they're not overpriced—Black-Scholes is misspecified**. When you use the correct (power law) model, option prices are exactly where they should be.

### What This Means for Investors

**1. Option prices are simpler than you think**

Once you're in the tail (beyond about 2-3 standard deviations), option prices follow a simple power law scaling. If you know the tail exponent α and one price, you know all prices. No complex models needed.

**2. The tail exponent α is the only thing that matters**

For tail options, all the complexity of the "body" of the distribution (volatility, drift, etc.) is captured in the anchor price. The relative prices are determined solely by α. This is why estimating α is so important—it's the key to understanding tail risk.

**3. The S&P 500's tail exponent is stable**

Figure 23.3 shows that market prices imply α ≈ 2.75, and this has been relatively stable over time. This means the relative cost of tail protection (e.g., 20% out-of-the-money puts vs. 10% out-of-the-money puts) is predictable.

**4. "Overpriced" tail options are a myth**

Academic studies claiming tail options are overpriced are using the wrong benchmark. Relative to Black-Scholes (which assumes thin tails), they look expensive. Relative to the correct power law model, they're fairly priced. The market knows what it's doing.

**5. For hedging, this is useful**

If you want to hedge tail risk, you can use this scaling to determine how much protection to buy. If the 10% out-of-the-money put costs $X, the 20% out-of-the-money put should cost approximately $X × (20/10)^{1-α}. With α ≈ 2.75, 1-α = -1.75, so (2)^{-1.75} ≈ 0.3. The 20% put should cost about 30% of the 10% put.

**6. For selling options, this is a warning**

If you're selling out-of-the-money options, you need to charge prices consistent with this scaling. If you use Black-Scholes, you'll underprice tail options and get crushed when the tail shows up. This is exactly what happened to LTCM and many others.

**7. The volatility smile is not a mystery**

The smile exists because the distribution is power law, not lognormal. Once you accept this, the smile is exactly what you'd expect. No need for stochastic volatility, jumps, or other complications—just a straight line on a log-log plot.

**8. For long-term investors, this is empowering**

You can now think about tail risk in a simple, robust way. The cost of protecting against a 30% crash relative to a 20% crash is determined by α. If you know α, you know the relative prices. No black box required.

### A Concrete Example

Suppose the S&P 500 is at 4000, and the 4400 call (10% out-of-the-money) costs $50. With α = 2.75, what should the 4800 call (20% out-of-the-money) cost?

Using the formula:
$$C(4800) = C(4400) \times \left(\frac{4800 - 4000}{4400 - 4000}\right)^{1-2.75} = 50 \times \left(\frac{800}{400}\right)^{-1.75} = 50 \times 2^{-1.75} = 50 \times 0.3 = 15$$

The 20% out-of-the-money call should cost about $15. If the market is pricing it at $25, that's a relative mispricing—either the 10% call is too cheap, the 20% call is too expensive, or your α estimate is wrong.

### The Bottom Line

This chapter provides a simple, robust framework for thinking about option prices in the tail. The key insights:

1. **In the tail, options follow a power law**
2. **The tail exponent α determines relative prices**
3. **One anchor price gives you all tail prices**
4. **The volatility smile is natural, not a puzzle**
5. **Claims of "overpriced" tail options are based on wrong models**

For investors, this means:
- You can understand tail option pricing without complex models
- You can detect relative mispricings
- You can hedge tail risk more efficiently
- You can avoid being fooled by academic studies using the wrong benchmark

As Taleb puts it: "The proposed methods allow us to approach such claims with more realism." The market isn't irrational—your model is just wrong.
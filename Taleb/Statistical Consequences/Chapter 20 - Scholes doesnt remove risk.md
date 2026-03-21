## Summary of Chapter 20: Financial Theory's Failures with Option Pricing

This chapter marks a shift into the practical world of finance, where Taleb applies the fat-tail framework to one of the most celebrated achievements of modern economics: the Black-Scholes-Merton option pricing model. His verdict is damning—the model's core assumptions are so divorced from reality that it's essentially useless for actual risk management.

### 20.1 Bachelier, Not Black-Scholes

**The Two Competing Paradigms**:

1. **Bachelier (1900)** : Options priced by actuarial expectation—just take the expected payoff under the real-world distribution. Simple, robust, works with any distribution.

2. **Black-Scholes-Merton (1973)** : Options priced by dynamic hedging—continuously trade the underlying to eliminate risk, making the option "redundant." Requires extremely idealized assumptions.

**The Irony**: Bachelier's approach is closer to how traders actually think and have thought for centuries. Black-Scholes is a theoretical construct that works only in a fantasy world.

### 20.1.1 Distortion from Idealization

**The Black-Scholes Requirements**:
- Frictionless markets (no transaction costs)
- No price impact from trading
- Known probability distribution (Gaussian with fixed parameters)
- Continuous trading
- No jumps (scalable discontinuities)

**The Mathematical Problem**: The Black-Scholes hedging argument relies on a Taylor expansion where all terms higher than second order disappear. In a power law world, **higher moments don't disappear—they explode**.

The hedged portfolio's change is:
$$\Delta \pi = -\frac{\partial C}{\partial t}\Delta t - \frac{1}{2}\frac{\partial^2 C}{\partial S^2}\Delta S^2 + O(\Delta S^3)$$

For a power law with α < 3, the cubic term doesn't vanish—it matters. For α < 2, the quadratic term itself is unstable. The whole construction falls apart.

### 20.1.2 The Actual Replication Process

**The Dynamic Hedging Integral**: To replicate a call option, you'd need to execute:
$$\lim_{\Delta t \to 0} \sum_{i=1}^{n=T/\Delta t} \frac{\partial C}{\partial S}\bigg|_{S=S_{t+(i-1)\Delta t}} (S_{t+i\Delta t} - S_{t+(i-1)\Delta t})$$

This is supposed to converge to the option payoff. In a Gaussian world, it does (by Ito's lemma). In a fat-tailed world, **it doesn't converge at all**.

### 20.1.3 Failure: How Hedging Errors Can Be Prohibitive

**Figures 20.1-20.3** tell the story:

- **Figure 20.1**: Hedging errors for an option portfolio under a Student T distribution with α = 3 (finite variance, but fat tails). The errors don't shrink—they persist. The distribution of errors has infinite variance, so they never converge.

- **Figure 20.2**: For comparison, hedging errors in the idealized Black-Scholes world. They shrink nicely toward zero.

- **Figure 20.3**: Add the 1987 crash to the simulation. The hedging errors explode. One event wipes out years of "risk-free" hedging.

**The Conclusion**: In a power law world, dynamic hedging removes no risk. The errors are large, persistent, and potentially catastrophic. The entire Black-Scholes apparatus is a dangerous illusion.

### What This Means for Investors and Traders

**1. "Risk-free" hedging is a myth**

The promise of Black-Scholes was that you could eliminate risk by dynamic hedging. Under fat tails, this is mathematically impossible. Hedging errors don't average out—they accumulate and can blow up.

**2. Option sellers are taking massive hidden risk**

When you sell an option and hedge it dynamically using Black-Scholes, you're not hedged. You're exposed to the very tail events the model ignores. The 1987 crash blew up many "properly hedged" option portfolios.

**3. The 1987 crash wasn't a surprise—it was inevitable**

Under a power law with α ≈ 3, a 20-standard-deviation move is not a once-in-a-universe event. It's expected to happen eventually. The fact that models treated it as impossible meant hedges failed exactly when needed most.

**4. Bachelier's approach is more robust**

Pricing by expectation (under the real-world distribution) doesn't require dynamic hedging. It works for any distribution with finite mean—including power laws. It's simpler, more transparent, and doesn't create false confidence.

**5. The volatility smile is a confession**

Traders don't use Black-Scholes with a single volatility. They use different volatilities for different strikes—the "volatility smile." This is an implicit admission that the model is wrong. They're just using it as a translation tool, not a pricing model.

**6. For long-term investors, this matters**

If you're using options to hedge your portfolio (e.g., buying puts for crash protection), you need to understand that the Black-Scholes prices you see are based on a flawed model. The "fair price" under fat tails is higher than Black-Scholes suggests—especially for out-of-the-money puts.

**7. The LTCM blowup was predictable**

Long-Term Capital Management used Black-Scholes-style models and dynamic hedging. When the Russian default hit, their hedges failed, and they lost everything. This wasn't bad luck—it was mathematical inevitability under fat tails.

**8. The alternative exists**

The chapter hints at what's coming in subsequent chapters: option pricing can be done using power law assumptions. If you know the tail exponent α, you can price options robustly without dynamic hedging. This is the subject of Chapter 23.

### The Deeper Point

This chapter isn't just about option pricing—it's about the **hubris of mathematical modeling** in finance. Black and Scholes created an elegant theory that seemed to solve a practical problem. But elegance isn't truth. Their model works in a world that doesn't exist—continuous, frictionless, Gaussian. In the real world of fat tails, jumps, and uncertainty, it's not just wrong; it's dangerous.

**The tragedy**: Generations of traders, risk managers, and regulators were taught that Black-Scholes was the way to price and hedge options. Billions of dollars were risked based on this fantasy. And when the fat tails showed up, the models failed exactly when they were needed most.

As Taleb puts it: "In short: dynamic hedging in a power law world removes no risk."

For investors, the lesson is simple: **be deeply skeptical of any model that claims to eliminate risk**. In a fat-tailed world, risk can be managed, but it can't be eliminated. Anyone who tells you otherwise is selling something—or hasn't read Chapter 20.
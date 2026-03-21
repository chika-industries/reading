## Summary of Chapter 21: Unique Option Pricing Measure (No Dynamic Hedging/Complete Markets)

This short but powerful chapter provides the mathematical foundation for why options can be priced without dynamic hedging or complete markets—contradicting the standard Black-Scholes narrative. Taleb shows that Put-Call Parity alone is sufficient to force options to be priced at the forward price, making the entire dynamic hedging apparatus unnecessary.

### 21.1 Background

**The Puzzle**: The Black-Scholes argument is that options can be priced by dynamic hedging because they're "redundant"—their payoff can be replicated by continuously trading the underlying. But:
1. Dynamic hedging isn't operationally feasible
2. It fails mathematically under fat tails
3. Traders priced options for centuries before Black-Scholes
4. Options trade on assets that don't allow dynamic replication

**The Question**: How can options be priced without dynamic hedging?

**The Answer**: Put-Call Parity is enough.

### 21.2 Proof

**The Setup**:
- Define C(K) as a European call with strike K
- Define P(K) as a European put with same strike
- Let F be the forward price of the underlying (the price you could lock in today for delivery at expiration)

**Lemma 21.1**: There exist unique probability measures for calls and puts such that:
$$C = \int_{\Omega} f_C d\mu_1$$
$$P = \int_{\Omega} f_P d\mu_2$$
where $f_C$ and $f_P$ are the payoff functions.

**Lemma 21.2**: The probability measures for puts and calls are the same ($\mu_1 = \mu_2$). This follows from Put-Call Parity and taking limits across strikes.

**Lemma 21.3**: Puts and calls must be priced at the same as the risk-neutral measure $\mu_Q$ as the tradable forward.

**The Key Insight**: Put-Call Parity says:
$$C(K) - P(K) + K = F$$

This holds for all strikes K. By taking derivatives with respect to K, you recover the probability distribution:
$$\frac{\partial C}{\partial K} = -P(S > K)$$
$$\frac{\partial P}{\partial K} = P(S < K)$$

The forward price F pins down the mean of this distribution. **That's it**. No dynamic hedging required. No complete markets. No continuous trading. Just arbitrage relationships between contemporaneous prices.

### 21.3 Case Where the Forward is Not Risk Neutral

Even if the forward price embeds a risk premium (i.e., F ≠ S₀eʳᵗ due to financing constraints or regulatory issues), the same logic applies. Options will be priced using a measure whose mean is that forward price. The "risk-neutral" measure is just the measure that lines up with the observable forward.

### 21.4 Comment

**The Key Comparison**:

| | Black-Scholes Merton | Put-Call Parity with Spreading |
|---|---|---|
| **Type** | Continuous rebalancing | Interpolative static hedge |
| **Limit** | Law of large numbers in time | Law of large numbers across strikes |
| **Market Assumptions** | No gaps, no jumps; ability to borrow/lend at all dates | Gaps and jumps acceptable; ability to borrow/lend for single forward date |
| **Probability Distribution** | Requires all moments finite | Requires only finite first moment (infinite variance OK) |
| **Market Completeness** | Required | Not required |
| **Realism** | Low | High |
| **Convergence** | Uncertain; one large jump changes everything | Robust |

**The Crucial Point**: Dynamic hedging tries to average over time (continuous trading). Put-Call parity averages over states (across strikes). Time averaging fails under fat tails because one jump can ruin everything. State averaging is robust because the probabilities across strikes must sum to one, regardless of how fat the tails are.

**For Practitioners**: This explains why traders have always focused on the relationship between strikes (volatility smile, skew) rather than dynamic hedging. The information is in the cross-section, not the time series.

### What This Means for Investors

**1. Option prices are valid even if markets are incomplete**

You don't need complete markets or dynamic hedging to have meaningful option prices. Put-Call Parity and no-arbitrage across strikes are enough. This means options are not "redundant securities"—they provide information that can't be derived from the underlying alone.

**2. The forward price is the key**

Whatever you think about future returns, the forward price (the price at which you can lock in delivery today) determines the mean of the pricing distribution. If you disagree with the forward, you can arb it. But for pricing options, the forward is the anchor.

**3. Fat tails are not a problem for pricing**

Black-Scholes requires all moments finite. This approach only requires finite first moment (the mean). Power laws with α > 1 are fine. You can price options on assets with infinite variance—something Black-Scholes can't handle.

**4. The volatility smile is natural**

Different strikes give different implied volatilities not because the model is wrong, but because the distribution isn't lognormal. The smile is just the market's way of expressing the true fat-tailed distribution. No need for stochastic volatility models—just use the actual distribution implied by Put-Call Parity.

**5. For long-term investors, this is liberating**

You don't need to believe in dynamic hedging or complete markets to use options. You just need to believe that Put-Call Parity holds (it's an arbitrage relationship) and that options across strikes are consistently priced. This is much weaker and more realistic.

**6. The information is in the cross-section**

To understand what the market thinks about tail risk, look at out-of-the-money option prices relative to at-the-money. The ratio tells you the implied tail exponent. This is robust information—it doesn't depend on a model of how volatility evolves over time.

**7. Dynamic hedging is optional**

You can hedge options if you want, but it's not required for pricing. The price is determined by supply, demand, and arbitrage across strikes—not by a continuous-time replication argument. This matches how actual options markets work.

### The Bottom Line

This chapter demolishes the myth that Black-Scholes "solved" the option pricing problem. Options were priced correctly for centuries before Black-Scholes, using simple arbitrage relationships. The Black-Scholes dynamic hedging argument is a theoretical curiosity, not a practical necessity.

For investors, the key takeaways are:
- Option prices contain real information about tail risk
- This information is accessible through simple no-arbitrage relationships
- You don't need to believe in continuous trading or complete markets
- The forward price is the anchor—everything else follows
- Fat tails are not a barrier to pricing; they're just another input

As Taleb puts it: "We have replaced the complexity and intractability of dynamic hedging with a simple, more benign interpolation problem." Option pricing isn't rocket science—it's just arbitrage.
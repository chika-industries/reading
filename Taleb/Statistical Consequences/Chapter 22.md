## Summary of Chapter 22: Option Traders Never Use the Black-Scholes-Merton Formula

This chapter (co-authored with Espen Haug) is a historical and practical takedown of one of the most persistent myths in finance: that the Black-Scholes-Merton model is what option traders actually use. Taleb and Haug show that traders used sophisticated heuristics long before Black-Scholes, and continue to use methods that are far more robust than the academic model.

### 22.1 Breaking the Chain of Transmission

**The Core Argument**: Option trading is a craft (*techne*), not a science (*episteme*). Knowledge passes from trader to trader through practice, not through academic papers. The academic finance establishment has systematically ignored this practical knowledge, creating a false narrative that theory precedes practice.

**The Result**: Generations of traders, risk managers, and regulators have been taught that Black-Scholes is how options work. This is historically false and practically dangerous.

### 22.2 Introduction/Summary

**The Two Myths**:

1. **Myth 1**: We had to wait for Black-Scholes-Merton to price options and manage option books.
   - **Reality**: Options were actively traded for centuries before 1973, with sophisticated pricing and hedging methods.

2. **Myth 2**: Traders today use the Black-Scholes-Merton formula.
   - **Reality**: Traders use heuristics that are closer to Bachelier and Thorp, and they adapt the formula in ways that contradict its core assumptions.

### 22.3 Myth 1: Traders Did Not Price Options Before BSM

**Historical Evidence**:

- **1600s**: Joseph De La Vega describes active option trading in Amsterdam, including put-call parity concepts.
- **1870s**: Active equity options markets in New York and London, with traders sophisticated enough to price for tail events.
- **1902**: Leonard Higgins publishes "The Put-and-Call," describing put-call parity in detail.
- **1904**: S.A. Nelson publishes "The ABC of Options and Arbitrage," showing:
  - Complete understanding of put-call parity
  - Delta hedging (sell a call, buy half the stock—since at-the-money options have ~50% delta)
  - Arbitrage between London and New York markets
  - The ability to convert puts into calls and vice versa

**Nelson (1904)** writes:
> "Sellers of options in London as a result of long experience, if they sell a Call, straightway buy half the stock against which the Call is sold; or if a Put is sold, they sell half the stock immediately."

This is **delta hedging**, fully understood and practiced 70 years before Black-Scholes.

**Bronzin (1908)** : Derives several option pricing formulas, including one very similar to Black-Scholes, using arbitrage principles and put-call parity.

**Thorp and Kassouf (1967)** : Publish "Beat the Market," showing market-neutral delta hedging for warrants and options. Thorp had the Black-Scholes formula programmed and running before Black and Scholes published.

**The Put-Call Parity Chain**:
- Higgins (1902) described it
- Nelson (1904) expanded it
- Deutsch (1910) described it
- Reinach (1961) described it in detail
- Stoll (1969) is credited in academic literature as the discoverer—60+ years after practitioners had been using it

### 22.4 Methods and Derivations

**The Bachelier-Thorp Formula**: The actual formula traders use (and used) is:
$$C = e^{-rT} \int_K^\infty (S_T - K) f(S_T) dS_T$$

That's it. Expected value under the real distribution, discounted. No dynamic hedging required. No assumption of lognormality. Any distribution works.

**Delta Hedging as Risk Management, Not Pricing**: Traders used delta hedging to reduce risk, not to derive prices. The delta came from the pricing formula, not the other way around.

### 22.5 Myth 2: Traders Today Use Black-Scholes

**What Traders Actually Do**:

1. **Prices come from supply and demand, not models**. A trader's price is determined by inventory, competition, and arbitrage relationships—not a theoretical valuation.

2. **The "volatility smile" is a confession**. Traders don't use one volatility. They use different volatilities for different strikes. This is a direct contradiction of the Black-Scholes model, which assumes constant volatility.

3. **Put-call parity is the real constraint**. As shown in Chapter 21, put-call parity forces consistency across strikes and with the forward. This is what traders actually enforce.

4. **Options are hedged with other options**. The robust way to manage option risk is to offset with other options, not to dynamically hedge with the underlying. This is what "converters" did in the early 1900s.

**The Irony**: The Black-Scholes formula is used as a **translation tool**, not a pricing model. Traders quote prices in "implied volatility" because it's a convenient language, not because they believe in the model. As one trader put it: "We use Black-Scholes to communicate, not to think."

### 22.6 On the Mathematical Impossibility of Dynamic Hedging

**The Fatal Flaw**: Dynamic hedging assumes all moments of the distribution exist. For power laws, they don't.

In a Taylor expansion of the hedged portfolio, terms of order ΔS³ and higher don't disappear. For α < 3, the cubic term matters. For α < 2, even the quadratic term is unstable.

**The Replication Integral**:
$$\lim_{\Delta t \to 0} \sum_{i=1}^{n} \frac{\partial C}{\partial S}\bigg|_{S_{t+(i-1)\Delta t}} (S_{t+i\Delta t} - S_{t+(i-1)\Delta t})$$

This is supposed to converge to the option payoff. Under fat tails, **it doesn't converge at all**. The errors are large, persistent, and potentially infinite in variance.

**Merton's (1976) Admission**: Even Merton acknowledged that dynamic hedging fails in the presence of jumps, but suggested that if jumps are uncorrelated with the market, you can still use Bachelier-style expectation pricing. This is an implicit admission that the dynamic hedging argument is not general.

### 22.6.1 The (Confusing) Robustness of the Gaussian

**Why Black-Scholes survived**: You can express any distribution in terms of Gaussian by varying σ across strikes—the "volatility surface." This doesn't mean the Gaussian is correct; it means it's a flexible enough function to fit anything if you add enough parameters.

**But**: This flexibility is **inconsistent with Black-Scholes theory**. If the model were true, σ would be constant. The fact that traders use a different σ for every strike proves they don't believe the model.

### 22.6.2 Order Flow and Options

**The Real Driver of Option Prices**: Supply and demand. If more people want to buy out-of-the-money puts, their price goes up. Market makers don't "manufacture" them through dynamic hedging—they adjust their prices to balance inventory.

**The Implied Distribution**: The set of option prices across strikes implies a probability distribution (via the Breeden-Litzenberger result). This is a consistency condition, not a theory of where prices come from.

### 22.6.3 Bachelier-Thorp

**The Correct Attribution**: The formula should be called **Bachelier-Thorp**, not Black-Scholes-Merton. Bachelier derived it by expectation in 1900. Thorp had it running on computers before 1973. Black, Scholes, and Merton provided a (flawed) theoretical justification after the fact.

### What This Means for Investors

**1. The "genius of Black-Scholes" is a myth**

The formula wasn't discovered by Black and Scholes—it was already known and used. Their contribution was a theoretical argument that turned out to be both unnecessary and wrong under fat tails. The real genius was the practitioners who figured out how to price and hedge options through centuries of trial and error.

**2. Option prices contain real information**

The options market isn't just gambling—it's a sophisticated information aggregation mechanism. The prices across strikes tell you what market participants collectively believe about tail risk. This information is accessible through simple no-arbitrage relationships.

**3. Be skeptical of "model prices"**

When your broker or a trading desk gives you an option price "from the model," they're using Black-Scholes as a translation tool, not as truth. The real price is determined by supply and demand. The "model" is just a language for quoting.

**4. Dynamic hedging is not a free lunch**

You cannot eliminate risk by continuously trading. Under fat tails, the hedging errors are large and persistent. Anyone claiming to offer "risk-free" arbitrage through dynamic hedging is either naive or dishonest.

**5. The volatility smile is your friend**

The fact that out-of-the-money options have higher implied volatility tells you something important: the market knows the distribution has fat tails. Use this information. Don't assume it's a "mispricing" to be arbitraged away.

**6. History matters**

The options market worked for centuries before 1973. The idea that Black-Scholes "created" modern options trading is ahistorical nonsense. Traders were doing sophisticated things long before academics showed up.

**7. For long-term investors, options are useful**

Options can hedge tail risk, generate income, or express views on volatility. But use them with humility. The models are guides, not truth. And remember: the people who actually trade options for a living don't believe the models either.

### The Bottom Line

This chapter is a powerful reminder that **practice precedes theory**. The academics didn't invent option pricing—they just provided a (flawed) justification for what practitioners already knew. The real knowledge resides in the trading community, passed down through generations of experience.

For investors, the lesson is: **trust markets, not models**. The options market prices tail risk every day. Those prices reflect real supply and demand, real fears and hopes, real information about the future. The models are just translations. The prices are the truth.

As Taleb puts it: "We call the equation Bachelier-Thorp. We were using it all along and gave it the wrong name, after the wrong method and with attribution to the wrong persons."
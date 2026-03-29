
## 🔁 Section 3 Summary: Modified Petersburg Game – The Growth Stock Analogy

Durand modifies the original Petersburg game to make it **directly analogous to valuing a growth stock**.

### The Modified Game:
- Peter tosses a coin repeatedly until a head appears.
- Instead of a single lump sum, Peter pays Paul a **series of dividends**:
  - If the first toss is a tail, Paul receives **D** ducats.
  - If the second toss is also a tail, he receives an additional **D(1+g)** ducats.
  - If the third toss is a tail, another **D(1+g)^2**, and so on.
- The game stops when a head appears.
- Probability of a tail on any toss = \( \frac{1}{1+i} \)  
  Probability of a head = \( \frac{i}{1+i} \)

### Expected Present Value (Paul’s expectation):

\[
E = \frac{D}{1+i} + \frac{D(1+g)}{(1+i)^2} + \frac{D(1+g)^2}{(1+i)^3} + \dots
\]

This is **arithmetically identical** to the standard discounted cash flow (DCF) formula for a stock that pays an initial dividend \( D \), which grows at a constant rate \( g \), discounted at a constant rate \( i \).

### Summation (Actuarial formula):
- Sum of first \( n \) terms:
\[
S_n = D \cdot \frac{1 - \frac{(1+g)^n}{(1+i)^n}}{i - g} \quad (i \neq g)
\]
- Sum to infinity (if \( i > g \)):
\[
S_\infty = \frac{D}{i - g}
\]
- If \( g \geq i \), the infinite sum **diverges to infinity** – just like the original Petersburg paradox.

### Key Insight:
The modified game shows that **perpetual growth stocks with \( g \geq i \)** are mathematically equivalent to a Petersburg game with infinite expected value. Yet no rational investor would pay an infinite price. This sets up the next sections: why investors won’t pay the full theoretical value, and how various adjustments (utility, finite horizons, risk) resolve the paradox in practice.

Durand notes that J. B. Williams (1938) had already derived the same formula \( D/(i-g) \) for valuing retained earnings, but with the crucial warning that it only works when \( i > g \).


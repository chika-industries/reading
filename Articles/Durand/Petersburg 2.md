

## 🎲 Section 2 Summary: The Petersburg Paradox (Original Formulation)

Durand presents the classic Petersburg Paradox as introduced by Daniel Bernoulli in 1738.

### The Game:
- Peter tosses a fair coin repeatedly until it lands **heads**.
- Paul receives:
  - **1 ducat** if heads appears on the **first** toss.
  - **2 ducats** if heads appears on the **second** toss.
  - **4 ducats** on the third toss.
  - **8 ducats** on the fourth toss, and so on – **doubling** each time.

### Probability and Payout Table:

| Heads on toss # | Probability | Payout (ducats) |
|----------------|-------------|----------------|
| 1              | 1/2         | 1              |
| 2              | 1/4         | 2              |
| 3              | 1/8         | 4              |
| 4              | 1/16        | 8              |
| ...            | ...         | ...            |
| n              | (1/2)^n     | 2^(n-1)        |

### Mathematical Expectation:

\[
E = \sum_{n=1}^{\infty} \left(\frac{1}{2}\right)^n \times 2^{n-1}
   = \sum_{n=1}^{\infty} \frac{1}{2} 
   = \infty
\]

Thus, the **expected value is infinite**.

### The Paradox:
Even though the mathematical expectation is infinite, **no rational person would pay more than a small finite amount** (e.g., a few ducats) to play. This contradiction reveals that pure expected value fails to capture real-world decision-making.

### Key Insight for Growth Stocks:
The paradox arises from the combination of **exponentially growing payoffs** and **geometrically decaying probabilities**. Durand notes that this is **structurally identical** to the problem of valuing a growth stock with a constant growth rate \( g \) and a constant discount rate \( i \) when \( g \geq i \). In both cases, naive discounting or expectation yields infinity – yet markets and people assign finite values.

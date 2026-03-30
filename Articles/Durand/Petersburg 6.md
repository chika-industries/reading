
## ⏳ Section 6 Summary: The Problem of Remote Dividends

Durand introduces a new difficulty in valuing growth stocks that did not arise in the original Petersburg Paradox: the **remoteness** of large dividend payments.

### Conventional discounting vs. reality:
- Standard theory says a dividend \( n \) years hence is worth \( \frac{D_n}{(1+i)^n} \).
- For ordinary bonds or preferred stocks, dividends far in the future are negligible when discounted.
- For a growth stock with \( g \geq i \), remote dividends (e.g., 10,000 years out) are **not negligible** – they can be astronomically large in present value terms.

### Practical limits on valuation horizon:

| Type of investor | Practical horizon |
|------------------|------------------|
| Individual without heirs | Dividends beyond life expectancy are useless. They could sell the stock, but that still requires a market price based on someone else’s horizon. |
| Individual with heirs | May look several generations ahead, but uncertainty about unborn offspring limits planning. |
| Life insurance company / pension fund | Obligations can extend 150–200 years (e.g., a whole life policy on a 21‑year‑old). These institutions need to match long‑duration liabilities with long‑duration assets. |

### Duration as a measure:
- **Duration** = weighted average time to receive cash flows (Macaulay duration).
- For a perpetuity: \( \text{Duration} = \frac{1+i}{i} \). At \( i = 3\% \), duration ≈ 34 years.
- For a growth stock (series (1) with \( i > g \)), duration = \( \frac{1+i}{i-g} \).
- If \( g = 5\% \), \( i = 6\% \), duration ≈ 100 years.
- As \( g \) approaches \( i \), duration → ∞.
- If \( g \geq i \), duration is infinite (like present value).

### Use of growth stocks in institutional portfolios:
- British actuaries developed **immunization** techniques: matching the duration of assets and liabilities minimizes interest‑rate risk.
- Pension funds with young workers may have liability durations exceeding 40 years – longer than perpetuities can match.
- Growth stocks offer a solution: their duration can be much longer than that of perpetuities, allowing better asset‑liability matching.
- However, extremely long durations (e.g., 1,000+ years) become impractical. An infinite duration implies waiting forever for a substantial return – which no rational investor, even one concerned with distant bequests, would accept.

### Clendenin & Van Cleave’s solution:
- Increase the discount rate for more remote dividends (e.g., 4% for first 20 years, 6% for next 20, 8% for next 20, then zero).
- This renders very remote dividends negligible and ensures a finite present value.
- While a 60‑year cutoff might suit an aging individual, it would not satisfy institutions with longer horizons. But even for them, a 600‑year cutoff is effectively infinite.

### Key conclusion of Section 6:
The problem of remote dividends is that traditional discounting can give enormous weight to payments thousands of years in the future. Because investors (individual or institutional) have finite horizons, these remote dividends should be heavily discounted or disregarded. Growth stocks’ long durations can be useful for matching liabilities, but beyond a point, the remoteness itself makes the valuation implausible.


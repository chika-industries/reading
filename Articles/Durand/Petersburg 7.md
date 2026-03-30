
## 📋 Section 7 Summary: Summary and Implications for Security Appraisal in General

Durand concludes by drawing together the various reasons an investor (Paul) would not pay the full theoretical value of a growth stock, and extends the implications to all securities.

### Recap of reasons to scale down growth stock valuations:

1. **Finite growth horizon** – growth eventually slows or ceases (Williams’ logistic curve).
2. **Diminishing marginal utility** – large remote dividends have less subjective value (Cramer, Bernoulli).
3. **Risk of ruin / diversification** – an investor with finite resources cannot commit too much to a single risky stock (Whitworth).
4. **Remoteness of dividends** – very distant payments are practically worthless, so they can be heavily discounted or ignored (Clendenin & Van Cleave).

Investors might use any combination of these adjustments.

### The problem of precision:

Durand notes that having **many possible adjustments** is itself a problem – there is no single, objective way to arrive at a precise valuation. Cramer’s two utility functions gave very different answers; Bernoulli’s gave another; Williams’ logistic model adds its own forecasting difficulties.

### Williams’ logistic growth formula (as presented):

For a stock with constant growth \( g \) for \( n \) years, then tapering off exponentially to a terminal level, the valuation is:

\[
V = D\left[\frac{(1+g)^n - (1+i)^n}{(g-i)(1+i)^n} + \frac{(2g + i + 2gi)(1+g)^n}{i(g + i + gi)(1+i)^n}\right]
\]

Even if the structure is accepted, the formula is extremely sensitive to small errors in \( g \), \( i \), and \( n \), especially when \( n \) is large and \( g \) is close to \( i \).

### Sensitivity illustration (Table 2):

Durand reproduces an abridged table from Clendenin & Van Cleave showing the present value of 60 dividend payments (initial $1.00, discount rate 5%) under different growth assumptions:

| Growth period (years) | PV if growth = 5% | PV if growth = 4% |
|-----------------------|-------------------|-------------------|
| 0                     | $18.93            | $18.93            |
| 10                    | $28.00            | $26.00            |
| 20                    | $37.00            | $32.00            |
| 30                    | $45.00            | $37.00            |
| 40                    | $52.00            | $41.00            |
| 50                    | $57.00            | $44.00            |
| 60                    | $60.00            | $45.00            |

Small differences in growth rate or growth period produce large differences in value – underscoring the difficulty of relying on such models.

### Implications for all securities:

- Even conventional bonds and preferred stocks require adjustments for **term to maturity**.
- The common practice of using a **single discount rate** for all bonds is an oversimplification; a bond’s duration should influence the rate.
- One could instead use a series of discount rates \( i_1, i_2, \dots, i_n \) that vary with the timing of each coupon or principal payment.

### Final moral:

Conventional discount formulas are **rough approximations** – acceptable for high‑grade, short‑term bonds, but increasingly hazardous as quality deteriorates or duration lengthens. Growth stocks represent the **extreme case**: longest duration, greatest sensitivity, and the most difficult to value.

Durand ends with a sobering thought: the Petersburg Paradox has resisted a unique, universally accepted solution for over 200 years, despite being tackled by great minds. The growth‑stock problem offers **no great hope of a satisfactory solution** either.


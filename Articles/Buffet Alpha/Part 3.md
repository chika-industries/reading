
### Part 3 Summary: Decomposing Returns – Public Stocks vs. Private Companies

The authors separate Berkshire Hathaway’s performance into two components:
- **Publicly traded stocks** – a measure of Buffett’s stock‑picking ability.
- **Privately held companies** – may also capture his skill as a CEO/manager.

#### Methodology

1. **Public stock portfolio**  
   - Using Berkshire’s 13F filings (1980–2017), the authors collect all common stock holdings at each quarter‑end.  
   - They assume no changes between filings and compute monthly returns weighted by Berkshire’s dollar holdings.  
   - The portfolio is rebalanced monthly to keep weights constant.

2. **Private holdings**  
   - Not directly observable. The market value of private holdings is inferred as a residual from the balance sheet:  

\[
\text{Private}^{MV} = \text{TA}^{MV} - \text{Public}^{MV} - \text{Cash}^{MV}
\]

   - The return of private holdings is then backed out using a formula (Equation 1 in the paper) that isolates the private component from changes in public stocks, liabilities, and equity.

3. **Decomposition of Berkshire’s excess return**  
   - Berkshire’s equity excess return is a **leveraged weighted average** of public and private excess returns:

\[
r_{t+1}^{\text{Equity}} - r_{t+1}^f = L_t \left[ w_t (r_{t+1}^{\text{Private}} - r_{t+1}^f) + (1 - w_t)(r_{t+1}^{\text{Public}} - r_{t+1}^f) \right]
\]

   - Where \( w_t = \frac{\text{Private}^{MV}}{\text{Private}^{MV} + \text{Public}^{MV}} \) (average = 65% private, 35% public over 1980–2017).  
   - Berkshire’s reliance on private companies grew from <20% in early 1980s to >78% by 2017.

#### Key findings (Table 2)

- **Public stocks** (Buffett’s stock picks) performed very well:
  - Average excess return: 12.0% (vs. market 7.5%)
  - Sharpe ratio: 0.74 (vs. market 0.49)
  - Information ratio: 0.51

- **Private holdings** also outperformed the market:
  - Average excess return: 9.3%
  - Sharpe ratio: 0.45

- **The public portfolio had a higher Sharpe ratio than the private portfolio.**  
  This suggests that Buffett’s skill comes **more from stock selection than from his managerial influence** on acquired companies.

- Berkshire’s overall stock return (18.6% excess, Sharpe 0.79) is higher than both components because of **leverage** (1.7×) and **diversification benefits** between public and private holdings.

#### Caveats
- The estimated private returns are noisy, especially in early years, because they depend on the market’s valuation of Buffett himself.  
- The analysis focuses on 1984–2017 for private returns to reduce outliers.

#### Conclusion of Part 3
Buffett’s public stock picks are the strongest part of his performance. His ability to buy the right stocks matters more than his role as a manager of private companies – though the private side still adds value and provides cheap leverage through insurance float.

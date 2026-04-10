### Part 5 Summary: A Systematic Buffett Strategy

The authors ask: *If Buffett’s success comes from leverage + exposure to BAB, QMJ, HML, etc., can we replicate his performance with a systematic (rule‑based) portfolio?*

#### Construction of the systematic Buffett‑style portfolio

1. **Estimate Buffett’s market exposure**  
   - Run a univariate regression of Berkshire’s excess returns on the market (MKT) to get \(\beta^{\text{Buffett}}\).

2. **Estimate Buffett’s active stock‑selection tilts**  
   - Run a regression of Berkshire’s **beta‑adjusted returns** (\(r - r^f - \beta^{\text{Buffett}} \text{MKT}\)) on the six factors (MKT, SMB, HML, UMD, BAB, QMJ).  
   - The coefficients (excluding alpha and error) define the active tilt portfolio return:  

\[
r_t^A = m \cdot \text{MKT}_t + s \cdot \text{SMB}_t + h \cdot \text{HML}_t + u \cdot \text{UMD}_t + b \cdot \text{BAB}_t + q \cdot \text{QMJ}_t
\]

3. **Rescale to match Berkshire’s idiosyncratic volatility**  
   - Multiply \(r_t^A\) by \(\frac{\sigma_I}{\sigma_A}\) (where \(\sigma_I\) = Berkshire’s idiosyncratic volatility) to simulate leverage and avoid attenuation bias.

4. **Add back market exposure and risk‑free rate**  

\[
r_t^{\text{Buffett style}} = r_t^f + \beta^{\text{Buffett}} \text{MKT}_t + r_t^{\text{Active}}
\]

The result is a diversified, long‑short portfolio that matches Berkshire’s beta, total volatility, idiosyncratic volatility, and factor tilts.

#### Performance results (Table 2, Figure 3, Table 5)

- **The systematic Buffett‑style portfolio performs comparably to Berkshire Hathaway itself.**  
  - For the public stock portfolio (cleanest comparison), the systematic version has a **correlation of 73%** with Buffett’s actual public stocks (explaining 53% of variance).  
  - Correlations with overall Berkshire stock (48%) and private holdings (26%) are lower but still substantial.

- **Table 5** shows:
  - When regressing Berkshire on the systematic portfolio, the alpha is **not significant** (i.e., the systematic portfolio explains Buffett’s returns).  
  - When regressing the systematic portfolio on Berkshire, the alpha is **large and significant** – meaning the systematic portfolio has extra diversification benefits (it holds many more stocks).

- **Long‑only, unleveraged version** (holding top 50 stocks based on active tilts) also performs well, though less spectacularly than the long‑short leveraged version.

- **Implementable (out‑of‑sample) version** (Appendix C) – using only information up to month \(t\) to form portfolios for month \(t+1\) – yields similar results, confirming robustness.

#### Figure 3 (cumulative returns)
- Shows that the systematic Buffett‑style portfolio tracks Berkshire’s actual returns closely over time, and both far outperform a leveraged market portfolio.

#### Important caveats
- The systematic portfolios **do not account for transaction costs, taxes, or implementation frictions**.  
- They also benefit from hindsight in the full‑sample version (though the out‑of‑sample version addresses this).  
- Therefore, the apparent outperformance should be discounted – the main insight is **high covariation**, not that the systematic strategy beats Buffett after costs.

#### Conclusion of Part 5
> “If one had applied leverage to a portfolio of safe, high‑quality, value stocks consistently over this time period, one would have achieved a remarkable return, as Buffett did.”

Buffett’s genius was recognizing this early, securing cheap leverage, and sticking to the strategy through drawdowns.

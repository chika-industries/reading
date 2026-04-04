## 📖 Summary of Segment 5: Cases A, B, C – Maximum Entropy Distributions under Tail Constraints

Now we get to the **core math** of the paper. But don’t worry – I’ll keep it visual and intuitive, with just enough formulas to see what’s going on.

### The setup (reminder)

We know only:
- Left tail: \( P(X \leq K) = \epsilon \) and \( E[X \mid X \leq K] = \nu_{-} \)
- One extra constraint (to make the right tail finite)

We then find the **maximum entropy distribution** \( f_{MEE}(x) \). It will have two pieces:

\[
f_{MEE}(x) = \epsilon \cdot f_{-}(x) + (1-\epsilon) \cdot f_{+}(x)
\]

- \( f_{-}(x) \) for \( x \leq K \) – **exponential** (determined entirely by \( K \) and \( \nu_{-} \))
- \( f_{+}(x) \) for \( x > K \) – shape depends on the **extra constraint**

---

## Case A: Constrain the global mean \( E[X] = \mu \)

This is equivalent to fixing the **expected return above K**:  
Let \( \nu_{+} = E[X \mid X > K] \), then \( \epsilon \nu_{-} + (1-\epsilon)\nu_{+} = \mu \).

**Resulting max entropy distribution**:

- \( f_{-}(x) = \frac{1}{K - \nu_{-}} \exp\left(-\frac{K - x}{K - \nu_{-}}\right) \) for \( x \leq K \)  
  (exponential rising toward \( K \), highest just before stop-loss)

- \( f_{+}(x) = \frac{1}{\nu_{+} - K} \exp\left(-\frac{x - K}{\nu_{+} - K}\right) \) for \( x > K \)  
  (exponential decaying to the right)

**Shape**: Both sides are **exponential**. The right tail is **light** – it decays faster than any power law. This is like a “double exponential” distribution with a kink at \( K \).

**What it means for a value investor**:
- If you believe returns above K are **not fat-tailed** (e.g., typical “efficient market” view), this is your max entropy model.
- But exponential tails mean **very large gains are exponentially rare**. That’s not Buffett or Taleb – that’s more like a diversified index fund with a stop-loss.
- The paper shows that as you repeat this strategy over time (multi-period naive), the average return converges to a Gaussian (central limit theorem). So Case A is **not** where you get massive asymmetric upside.

---

## Case B: Constrain the absolute mean \( E[|X|] = \mu \)

This is useful if you care about **both positive and negative deviations** equally (like a mean absolute deviation constraint). The math is similar but now \( f_{+}(x) \) involves \( |x| \) instead of \( x \).

**Result**: Still exponential tails on both sides, but symmetric in shape if \( \nu_{-} \) and \( \nu_{+} \) are symmetric. Not very interesting for value investors who care about upside asymmetry.

---

## Case C: Constrain a power-law tail – **the fat-tailed case**

This is the **most relevant** for you.  
Instead of fixing the mean, they fix:

\[
E[\log(1 + |X|) \mid X > K] = A
\]

Why? Because for a power-law distribution \( f_{+}(x) \propto (1+x)^{-(1+\alpha)} \), the expected log is related to \( 1/\alpha \). By fixing \( A \), you fix the tail exponent \( \alpha \).

**Resulting max entropy distribution**:

- \( f_{-}(x) \) is the same exponential on the left (still controlled by stop-loss)
- \( f_{+}(x) = \frac{1}{C(\alpha)} (1 + x)^{-(1+\alpha)} \) for \( x \geq K \)

where \( C(\alpha) \) is a normalizing constant. The right tail decays as a **power law** – much slower than exponential. This means **extreme gains are much more likely** than in Case A.

**Shape**: See Figures 5 and 6 in the paper (I described them earlier). As \( \alpha \) gets smaller (e.g., \( \alpha = 1 \) or 2), the tail gets fatter. As \( \alpha \) grows, it approaches exponential.

**What it means for a value investor**:
- This is the **Buffett-Taleb** case: you have no idea how high the upside can go, so you allow for power-law gains (multi-baggers).
- The constraint \( E[\log(1+|X|) \mid X > K] = A \) is like saying: “I expect a certain log return on my upside bets, but I don’t constrain the mean (which might be infinite if \( \alpha \leq 1 \)).”
- This matches the idea of **asymmetric bets**: limited downside (via stop-loss or margin of safety), unlimited upside (power law).

---

## The multi-period comment (important)

They briefly note:

- **Case A** (exponential tails): Over many periods, the **average return** converges to a Gaussian (Central Limit Theorem) and then to a **Dirac delta** – meaning no uncertainty left, just the mean. So exponential tails become predictable in the long run.
- **Case C** (power-law tails): Convergence to Gaussian **only happens if \( \alpha \geq 2 \)**. If \( \alpha < 2 \), the variance is infinite, and the average does **not** become Gaussian – it stays fat-tailed. That means **uncertainty never disappears**, even with many periods.

> 🧠 *For a value investor*: This is profound. If your upside bets have power-law tails (true deep value or venture capital), you cannot average away the risk – the fat tail persists. That’s why you need the barbell: cash on the side to survive long enough for the power-law payoff to arrive.

---

## ✅ Summary table for Cases A, B, C

| Case | Extra constraint | Right tail shape | Multi-period behavior | Value investing fit |
|------|----------------|------------------|----------------------|---------------------|
| A | Global mean \( E[X] = \mu \) | Exponential (light) | Converges to Gaussian → Dirac | Not good – limits upside |
| B | Absolute mean \( E[|X|] = \mu \) | Exponential (symmetric) | Similar to A | Not asymmetric |
| C | \( E[\log(1+|X|) \mid X>K] = A \) | Power law (fat) | Stays fat-tailed if \( \alpha < 2 \) | **Excellent** – matches Buffett/Taleb |

---

## Final takeaway for you

> **If you are a value investor who holds concentrated bets with a margin of safety (left-tail protection) and expects rare, large upside (power law), then Case C is your maximum entropy model. It justifies the barbell: cash + fat-tailed bets. Exponential tails (Case A) are for those who believe in efficient markets and diversification – not for you.**


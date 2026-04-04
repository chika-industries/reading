## 📖 Summary of Segment 3: Revisiting Mean-Variance & Gaussian Case

### What this section does

The authors now **connect** their tail-risk constraints to the traditional Gaussian (normal distribution) world of Modern Portfolio Theory. They show: *if you falsely assume returns are normal*, then imposing tail constraints (VaR and expected shortfall) **determines the mean and variance completely** – leaving no freedom for optimization. This reveals a “no free lunch” trade-off.

### Setting up the normal case

Let portfolio return \( X \) be normally distributed with mean \( \mu \) and variance \( \sigma^2 \).  
You impose:

1. **Tail probability**: \( P(X \leq K) = \epsilon \)   (e.g., 1% chance of losing more than \( K \))
2. **Expected shortfall**: \( E[X \mid X \leq K] = \nu_{-} \)   (average loss if you’re in that tail)

In a normal distribution, \( \mu \) and \( \sigma \) are the only parameters. Two equations, two unknowns → **unique solution**.

### The math (simplified for a biophysicist)

Let \( \eta(\epsilon) \) = the \(\epsilon\)-quantile of the standard normal (e.g., for \(\epsilon = 0.05\), \( \eta \approx -1.645\)).  
Also define a special function \( B(\epsilon) \) (ugly but just a number from the normal distribution; for small \(\epsilon\), \( B \approx -1 \)).

From the two constraints, they derive:

\[
\mu = \frac{\nu_{-} + K \cdot B(\epsilon)}{1 + B(\epsilon)}, \quad
\sigma = \frac{K - \nu_{-}}{\eta(\epsilon) \cdot (1 + B(\epsilon))}
\]

**What does this mean?**  
Once you pick your tail parameters \( K, \epsilon, \nu_{-} \), the mean \( \mu \) and volatility \( \sigma \) are **forced** – no trade-off, no optimization. You cannot independently choose a higher expected return without changing the tail constraints.

### The “no free lunch” inequality

For a positive expected return (\( \mu > 0 \)), you need:

\[
|\nu_{-}| > K \cdot B(\epsilon)
\]

Since \( B(\epsilon) < -1 \) and tends to -1 as \( \epsilon \to 0 \), this says: **to have a positive average return, your expected shortfall \( \nu_{-} \) must be sufficiently large in magnitude (i.e., you must accept a bad enough average loss in the tail)**.  
In plain English: you cannot clip the left tail too tightly and still expect a positive return – the market demands a risk premium.

### The mixture of two normals (a more realistic model)

Because real returns have fatter tails than a single normal, they introduce a **mixture**:

\[
f(x) = \lambda \cdot N(\mu_1, \sigma_1^2) + (1-\lambda) \cdot N(\mu_2, \sigma_2^2)
\]

A simple case: set \( \lambda = \epsilon \), \( \mu_1 = \nu_{-} \) (the left-tail mean), and then \( \mu_2 \) is forced by the overall mean. If you make \( \sigma_1 \) and \( \sigma_2 \) very small, the distribution becomes **two spikes**: one at the loss level \( \nu_{-} \) (with probability \( \epsilon \)) and one at a higher return (with probability \( 1-\epsilon \)).

> 🧠 *For a value investor*: This is the **barbell in probability space** – a small chance of a known loss, a large chance of a known gain. No messy middle.

### Dynamic stop-loss comment

They briefly mention: a hard stop-loss at level \( K \) (selling when price hits \( K \)) creates an **absorbing barrier**. The resulting distribution has no mass below \( K \) – it’s like a Dirac delta at \( K \) for the stopped loss. This introduces positive skewness (because the left tail is cut off).

### Key takeaways for you as a value investor

1. **If you believe returns are normal, tail constraints lock in mean and variance** – you can’t beat the trade-off.  
2. **The “no free lunch”** means: to expect a positive return, you must accept a sufficiently bad average loss when the tail event happens.  
3. **Mixture of two normals** shows the barbell explicitly: a small probability of a loss, a large probability of a gain, almost no middle.  
4. **Stop-losses** change the distribution shape – they don’t just cap losses, they introduce asymmetry (skewness) that standard MPT ignores.

### Bottom line

> **If you control the left tail (via VaR, shortfall, or stop-loss), the traditional mean-variance optimization becomes irrelevant – the tail constraints alone determine the distribution’s parameters under normality. In reality, returns aren’t normal, so the solution is a barbell: two point masses (loss / gain) instead of a bell curve.**

Would you like me to continue with **Segment 4** (Maximum Entropy Setup), where they drop normality entirely and maximize entropy subject only to tail constraints?


## 🔁 Reminder: What is entropy here?

In thermodynamics, you learned:

- **Boltzmann entropy** \( S = k \log \Omega \) – measures the number of microscopic states \(\Omega\) consistent with macroscopic constraints (energy, volume, etc.).
- **Second law**: systems evolve toward the macrostate with the **highest entropy** given constraints.

In **information theory** (Shannon) and **statistical inference** (Jaynes), the idea is identical but generalized:

- **Shannon entropy** (for a continuous distribution \( f(x) \)) is:
  \[
  H = -\int f(x) \log f(x) \, dx
  \]
- **Maximum entropy principle** (Jaynes): When you only know a few facts (e.g., mean, variance, tail probabilities), the **most honest, least biased** distribution is the one that maximizes \( H \) subject to those facts.  
  Why? Because any other distribution would assume **extra information you don’t actually have** – i.e., hidden biases.

👉 In thermodynamics: Nature maximizes entropy given energy constraints.  
👉 Here: We **choose** the distribution that maximizes entropy given tail-risk constraints. It’s the **most unpredictable** distribution consistent with what we know (and we know very little – only the left tail).

> 🧠 *For you*: Think of it like this – you know your stop-loss and your average loss in a crash. You know **nothing** else about returns. The maximum entropy distribution is the one that spreads probability as evenly as possible (in log space) subject to those hard facts. No hidden Gaussian assumptions, no hidden correlations.

---

## 📖 Summary of Segment 4: Maximum Entropy Setup

### What this section does

Now they **drop the normality assumption entirely**. They say:  
We only know:
1. Tail probability \( P(X \leq K) = \epsilon \)
2. Expected shortfall \( E[X \mid X \leq K] = \nu_{-} \)
3. Possibly one more constraint (like overall mean or absolute mean)

Everything else is **unknown**. So we model \( X \) with the **maximum entropy distribution** consistent with these constraints.

### Why not just use any distribution?

Without a principle like maximum entropy, you could arbitrarily choose a distribution that fits the constraints – but that would smuggle in hidden assumptions. Max entropy is the **honest** choice: it assumes the least possible structure beyond the constraints.

### The technical problem

They define:
- \( \Omega_{var}(\theta) \) = set of all probability densities \( f \) satisfying the tail constraints (with \( \theta = (K, \epsilon, \nu_{-}) \)).
- This set is **convex** (if two densities satisfy constraints, so does their average).

But – **crucial point** – the tail constraints alone **do not** yield a finite maximum entropy distribution. Why? Because for \( x > K \) (the non-tail region), you could spread probability out to infinity (making entropy arbitrarily large). You need **at least one more constraint** to pin down the right tail.

### The additional constraints they consider

They then introduce **three cases** (A, B, C) – each adds one extra constraint to make the problem well-posed:

- **Case A**: Fix the global mean \( E[X] = \mu \) (or equivalently, fix \( E[X \mid X > K] = \nu_{+} \))
- **Case B**: Fix the absolute mean \( E[|X|] = \mu \)
- **Case C**: Fix a power-law tail behavior (fat tails) via \( E[\log(1+|X|) \mid X > K] = A \)

### The form of the maximum entropy solution

For **Case A**, the max entropy density splits into two pieces:

\[
f_{MEE}(x) = \epsilon \cdot f_{-}(x) + (1-\epsilon) \cdot f_{+}(x)
\]

where:
- \( f_{-}(x) \) for \( x \leq K \) is an **exponential** (decaying away from \( K \))
- \( f_{+}(x) \) for \( x > K \) is also an exponential (decaying to the right)

They show that \( f_{-}(x) \) has the form:

\[
f_{-}(x) = \frac{1}{K - \nu_{-}} \exp\left(-\frac{K - x}{K - \nu_{-}}\right), \quad x \leq K
\]

Wait – careful: reading the paper, they write:  
\( f_{-}(x) = \frac{1}{K - \nu_{-}} \exp\left(-\frac{K - x}{K - \nu_{-}}\right) \) for \( x \leq K \).  
This is an **exponential rising as \( x \) increases toward \( K \)**? Actually let me re-check: The exponent is \( -\frac{K - x}{K - \nu_{-}} \). If \( x < K \), then \( K - x > 0 \), so the exponent is negative, and as \( x \to K \), exponent → 0, so \( f_{-} \) is highest at \( x = K \). That makes sense: near the stop-loss, probability accumulates.

Similarly, \( f_{+}(x) \) for \( x > K \) is another exponential (decaying to the right).

### The key insight for a value investor

The maximum entropy distribution under tail constraints + mean constraint is **not a bell curve**. It has:
- A **sharp cut-off or exponential left tail** (determined by \( K \) and \( \nu_{-} \))
- An **exponential right tail** (unless you choose Case C with power law)

But more importantly: **The portfolio’s composition (which stocks) almost disappears from the problem**. Only the **aggregate tail parameters** matter. This is radical:  
> You don’t need to pick “efficient” stocks. You just need to control the portfolio’s total loss, then take maximum uncertainty (i.e., asymmetric bets) on the upside.

### Why no wiggle room on the left

The left side (\( x \leq K \)) is **fully determined** by \( K \) and \( \nu_{-} \). There’s no freedom. The only freedom is on the right side (\( x > K \)), and even that is forced to be exponential (maximum entropy) unless you add a power-law constraint.

---

## ✅ Takeaway from Segment 4

> **When you only know your tail loss limits (VaR + expected shortfall), the most honest model for your portfolio return is a maximum entropy distribution. This distribution has an exponential left tail fixed by your stop-loss and average crash loss, and an exponential right tail (unless you specify fat tails). The individual assets you hold become almost irrelevant – only the aggregate tail matters. This justifies the barbell: control the left, maximize uncertainty on the right.**

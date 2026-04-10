Excellent. Let's continue our walk. We now have the Lorentz transformation equations in hand. They are the tool. Now Einstein shows us what they *mean* for physical objects and clocks.

**The transformation we have (setting \(a=1\)):**

\[
\tau = \beta \left( t - \frac{v x}{c^2} \right), \quad
\xi = \beta (x - v t), \quad
\eta = y, \quad
\zeta = z
\]

where \(\beta = \frac{1}{\sqrt{1 - v^2/c^2}}\).

Now he asks two simple questions that reveal everything.

### Step 12: Length Contraction (The moving rod)

**The question:** How long is a moving rod?

**The setup:** A rod of length \(l\) is at rest in the moving system \(k\). It lies along the \(\xi\)-axis. So its ends have coordinates \(\xi = 0\) and \(\xi = l\) in \(k\).

**How do we measure its length from the stationary system \(K\)?** Einstein is very careful. He says: an observer in \(K\) must measure the positions of the *two ends* **at the same time \(t\)** in \(K\). Why? Because if you measure one end now and the other end later, the rod will have moved, and you'll get a nonsense number.

So set \(t = 0\) for convenience. From the transformation:

\[
\xi = \beta (x - v \cdot 0) = \beta x \quad \Rightarrow \quad x = \frac{\xi}{\beta}
\]

Thus:
- The left end (\(\xi = 0\)) is at \(x = 0\).
- The right end (\(\xi = l\)) is at \(x = l / \beta\).

So the length in \(K\) is:

\[
\text{Length in } K = \frac{l}{\beta} = l \sqrt{1 - \frac{v^2}{c^2}}
\]

**The result:** The moving rod is **shorter** than its rest length \(l\). It contracts in the direction of motion by the factor \(\sqrt{1 - v^2/c^2}\).

**Einstein's comment:** This is not an illusion. It is a real, physical contraction that follows directly from our definition of simultaneity. Different observers, using their own synchronized clocks, will measure different lengths for the same rod.

**What about the perpendicular directions?** For \(y\) and \(z\), we have \(\eta = y\). So no contraction sideways. That makes sense: motion is along \(x\), so only the \(x\)-direction is affected.

### Step 13: Time Dilation (The moving clock)

**The question:** How fast does a moving clock tick?

**The setup:** A clock is at rest in the moving system \(k\), placed at the origin \(\xi = 0\). In \(k\), it ticks every second (\(\tau = 0, 1, 2, \ldots\)).

**From \(K\)'s perspective:** Using the transformation, for \(\xi = 0\):

\[
\tau = \beta \left( t - \frac{v x}{c^2} \right)
\]

But if the clock is at the origin of \(k\), its position in \(K\) is \(x = v t\) (since it moves with the system). Substitute \(x = v t\):

\[
\tau = \beta \left( t - \frac{v \cdot v t}{c^2} \right) = \beta \left( t - \frac{v^2}{c^2} t \right) = \beta t \left(1 - \frac{v^2}{c^2}\right)
\]

But \(\beta = 1 / \sqrt{1 - v^2/c^2}\). So:

\[
\tau = \frac{1}{\sqrt{1 - v^2/c^2}} \cdot \left(1 - \frac{v^2}{c^2}\right) t = t \sqrt{1 - \frac{v^2}{c^2}}
\]

Or, solving for \(t\):

\[
t = \frac{\tau}{\sqrt{1 - v^2/c^2}} = \beta \tau
\]

**The result:** When the moving clock shows \(\tau = 1\) second, the stationary clock shows \(t = \beta\) seconds, which is **longer** than 1 second. The moving clock runs slow. For example, if \(v = 0.866c\), then \(\beta = 2\), and the moving clock ticks once for every two seconds of stationary time.

**Einstein's words (paraphrased):** "A clock placed at the equator must run slower than an identical clock at the pole." This is a direct, testable prediction.

### Step 14: The Famous "Traveling Clock" Thought Experiment

Einstein then draws a striking conclusion. He imagines two synchronous clocks at point \(A\) in the stationary system. One stays at \(A\). The other is taken on a journey along a closed curve (say, around the block) and returns to \(A\). The moving clock will have recorded **less time** than the stationary one.

**Why?** Because during the journey, the moving clock was not always in an inertial frame (it had to accelerate to turn around), but the effect accumulates. The formula for the time difference, to a first approximation, is \(\Delta t \approx \frac{1}{2} \frac{v^2}{c^2} \times \text{(travel time)}\).

**Modern version (twin paradox):** One twin travels at high speed and returns younger than the other. Einstein saw this implication in 1905.

**Takeaway for Einstein's mind:** He is not afraid to follow the logic to its seemingly absurd conclusions. If the postulates are right, these effects are real. And they have been confirmed countless times (muon decay, atomic clocks on airplanes, GPS satellites).

### Step 15: Velocity Addition (The new rule)

Before ending the kinematics section, he asks: How do velocities add? In Newton's world, if you walk forward on a moving train, your speed relative to the ground is (walking speed + train speed). In relativity, it's different.

**The derivation (briefly):** A point moves in \(k\) with constant velocities \(w_\xi, w_\eta, w_\zeta\). Use the transformation to find its velocities \(u_x, u_y, u_z\) in \(K\). The result for motion along the \(x\)-axis only:

\[
u = \frac{v + w}{1 + \frac{v w}{c^2}}
\]

**What this means:** No matter how you add velocities, you can never exceed \(c\). If \(v = 0.9c\) and \(w = 0.9c\), then \(u = (1.8c) / (1 + 0.81) = 1.8c / 1.81 \approx 0.9945c\). Always less than \(c\).

If \(w = c\), then \(u = (v + c)/(1 + v/c) = c(v/c + 1)/(1 + v/c) = c\). So light speed is the same for all observers – consistent with the second postulate.

**Einstein's comment:** This shows that \(c\) plays the role of an infinite velocity in the old mechanics. Nothing can go faster than light.

---

### Summary of Kinematics (what we've covered):

1. **Relativity of simultaneity** – "now" is not universal.
2. **Lorentz transformation** – the rule for converting coordinates.
3. **Length contraction** – moving objects shrink in the direction of motion.
4. **Time dilation** – moving clocks run slow.
5. **Velocity addition** – speeds add in a way that keeps light speed as the limit.

All of this from two simple postulates and a careful definition of synchronism.

### What's next in the paper:

Now Einstein turns to **electrodynamics**. He will show that Maxwell's equations, which were the source of the original "asymmetry," are actually perfectly covariant under the Lorentz transformation. The electric and magnetic fields are not separate things – they mix together when you change reference frames. The magnet-and-conductor problem disappears: in both cases, the physics is the same, just seen from different angles.

He will also derive the **Doppler effect** for light (the formula for how frequency changes when source and observer move), and the **aberration of light** (the apparent shift in direction of starlight due to Earth's motion).

Shall we walk through that next? Or would you like to pause and reflect on the kinematics we've done? Either way, I'm here at your pace.
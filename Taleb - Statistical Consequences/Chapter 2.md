## Summary of Chapter 2: Glossary, Definitions, and Notations

This chapter serves as a comprehensive reference guide, establishing the precise terminology and mathematical notations used throughout the book. Rather than a narrative chapter, it functions as a "catalogue raisonné" of concepts that will be deployed in subsequent discussions.

### Section 2.1: General Notations and Frequently Used Symbols

The chapter opens with standard mathematical notations:
- **P**, **E**, **V** for probability, expectation, and variance operators
- **M** for mean absolute deviation
- **φ(.)** and **f(.)** for probability density functions
- **F(.)** for cumulative distribution functions, **\overline{F}(.)** for survival functions
- Convergence notations: **→ᴰ** (distribution), **→ᴾ** (probability), **→ᵃ⋅ˢ** (almost sure)
- Key distributions: **N(μ,σ)** (Gaussian), **L(.)** (Lognormal), **S(α,β,μ,σ)** (stable distribution)
- The power law class **𝔓** and subexponential class **𝔖**

### Section 2.2: Catalogue Raisonné of General & Idiosyncratic Concepts

This substantial section defines the core conceptual framework:

**Foundational Statistical Concepts** (2.2.1-2.2.5)
- **Power Law Class (𝔓)**: Defined by survival function ℙ(X > x) = L(x)x^{-α} with slowly varying function L(x). The "Karamata point" marks where L(x) becomes constant.
- **Law of Large Numbers**: Both weak and strong forms, noting finiteness of variance is unnecessary.
- **Central Limit Theorem**: Standard Lindeberg-Lévy version and its generalizations.
- **Law of Medium Numbers (Preasymptotics)**: The book's central focus—behavior for finite n, not just asymptotics.
- **Kappa Metric (κ)**: A novel measure in [0,1] gauging preasymptotic behavior (0 for Gaussian, 1 for Cauchy/undefined mean).

**Distribution Classes and Properties** (2.2.6-2.2.12)
- **Elliptical Distribution**: Requires single covariance matrix; regime-switching violates ellipticity.
- **Stable (Lévy stable) Distribution**: Generalization of CLT with tail index α ∈ (0,2].
- **Subexponentiality**: The boundary between Mediocristan and Extremistan—where the sum is dominated by the maximum.
- **Student T**: Used as convenient two-tailed power law proxy (Cauchy at α=1, Gaussian as α→∞).

**Epistemological and Critical Concepts** (2.2.13-2.2.25)
- **Citation Ring & Rent Seeking**: Circular academic self-referentiality and conflicts of interest in research.
- **Pseudo-empiricism (Pinker Problem)**: Making inferences using metrics that don't apply to fat-tailed variables.
- **Skin in the Game**: Filtering mechanism forcing operators to bear consequences of failures.
- **Wittgenstein's Ruler**: Using the table to measure the ruler—a large deviation (e.g., "six sigma") indicates the distribution is power law, not that a rare event occurred.
- **Black Swans**: Observer-dependent events outside what can be modeled, with large consequences. Fat tails make them worse but aren't the cause.

**Technical and Measurement Concepts** (2.2.26-2.2.31)
- **Empirical Distribution is Not Empirical**: Censored on [x_min, x_max], carrying huge consequences for fat tails.
- **Hidden Tail & Shadow Moment**: Moments above the maximum observation; "plug-in" estimation via maximum likelihood rather than direct sample measurement.
- **Tail Dependence**: Upper/lower tail dependence indices between variables.
- **Metaprobability**: Stochasticizing parameters to check robustness.
- **Dynamic Hedging**: Replication of option payoffs—shown to be impossible in fat-tailed environments due to preasymptotic properties.

The chapter establishes that moving from thin to fat tails isn't merely changing distribution names but requires fundamental rethinking of statistical tools and decision frameworks.
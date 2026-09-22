# Lecture 01: Probability 101 Foundations for Statistical Learning

Probability provides the mathematical framework to quantify uncertainty. In statistical learning, we treat data observations as realizations of random variables.

## 1. Axioms of Probability
Let $\Omega$ be the sample space (all possible outcomes) and $A$ be an event within that space. The probability $P(A)$ must satisfy Kolmogorov's Axioms:

1. **Non-negativity**: $P(A) \ge 0$ for any event $A$.
2. **Normalization**: $P(\Omega) = 1$ (the probability of the entire sample space is certain).
3. **Additivity**: For any mutually exclusive (disjoint) events $A$ and $B$:  $$P(A \cup B) = P(A) + P(B)$$

---

## 2. Conditional Probability & Independence
Conditional probability updates our beliefs about an event $A$ given that another event $B$ has already occurred.

$$ P(A | B) = \frac{P(A \cap B)}{P(B)} \quad \text{where } P(B) > 0 $$

### Statistical Independence:
Two random events $A$ and $B$ are completely independent if and only if knowing $B$ happened gives zero information about $A$: 
$ P(A | B) = P(A) \iff P(A \cap B) = P(A) \cdot P(B) $

---

## 3. Bayes' Theorem
Bayes' Theorem allows us to invert conditional probabilities. This forms the bedrock of Bayesian statistics and classification models (like Naive Bayes or Logistic Regression metrics):

$$ P(A | B) = \frac{P(B | A) \cdot P(A)}{P(B)} $$

Where:
* $P(A|B)$ is the **Posterior** probability.
* $P(B|A)$ is the **Likelihood** of seeing the evidence given the hypothesis.
* $P(A)$ is the **Prior** probability of the hypothesis.
* $P(B)$ is the **Marginal** probability of the evidence, often expanded using the Law of Total Probability:  

  $$ P(B) = \sum_{i} P(B | A_i) \cdot P(A_i) $$

---

## 4. Expected Value and Variance
For a continuous random variable $X$ with a probability density function (pdf) $f(x)$:

### Expected Value (The Mean $\mu$):
$$ \mathbb{E}[X] = \int_{-\infty}^{\infty} x \cdot f(x) \, dx $$

### Variance ($\sigma^2$ - The Spread):
$$ \text{Var}(X) = \mathbb{E}[(X - \mathbb{E}[X])^2] = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 $$

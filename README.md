# 🎯 Rejection Sampling Method

This notebook illustrates the **Rejection Sampling Method**, a fundamental technique in probabilistic simulations used to sample from complex distributions by leveraging a simpler proposal distribution.

---

## 🧠 Core Idea

Rejection sampling allows us to generate random samples from a target distribution `f(x)` by:

1. Drawing samples from a **proposal distribution** `g(x)`, which is easy to sample from.
2. Accepting or rejecting samples based on a condition using a known bound `M` such that:

   ```
   f(x) <= M * g(x)
   ```

This method is powerful when **direct sampling from `f(x)` is difficult**, but evaluating `f(x)` is feasible.

---

## 📌 Implementation Steps

- Define the **target density function** `f(x)` (e.g., a truncated normal).
- Choose a **proposal distribution** `g(x)` that is:
  - Easy to sample from,
  - Covers the support of `f(x)`.
- Compute or choose an upper bound `M` such that `f(x) ≤ M g(x)` for all `x`.
- Loop:
  - Sample `x ~ g(x)` and `u ~ U(0, 1)`
  - Accept `x` if `u ≤ f(x) / (M * g(x))`

---

## 📊 Visuals

The notebook includes plots that:

- Compare the target and proposal distributions.
- Show the accepted vs rejected samples.
- Display the empirical histogram vs the true density.

---

## ✅ Applications

- Bayesian Inference
- Simulating rare events
- Graphical models and probabilistic programming

---

## 📚 Summary

Rejection sampling is a versatile method for **simulating from intractable distributions**. It is especially useful when exact sampling is impossible, but function evaluation is accessible. Though sometimes inefficient, it serves as a **baseline technique** in Monte Carlo methods.
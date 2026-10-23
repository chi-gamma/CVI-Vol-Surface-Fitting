# Convex Volatility Interpolation

This project implements **Convex Volatility Interpolation (CVI)**, a model-free, arbitrage-constrained volatility surface fitting methodology introduced by Deschâtres [1].

CVI parameterizes **implied variance** using equivalent cubic spline and B-spline representations, fitting the surface through **quadratic programming (QP) with linear constraints**. Its cubic-spline parameters describe ATM variance, ATM skew, and variance convexity at selected knots, providing an intuitive representation of smile shape.

Unlike approaches that calibrate individual maturity slices independently, CVI **fits all expiries simultaneously**, incorporating strike- and maturity-related constraints within a unified optimization framework. Its flexible spline representation can capture complex volatility smiles, including **W-shaped structures** that are difficult to represent using fixed-parameter models such as standard SVI.

A central challenge is the treatment of **butterfly arbitrage**. Although butterfly-arbitrage constraints are linear in option price space, they are nonlinear and nonconvex in implied variance space. CVI addresses this through **iterative linearization**, solving an initial QP followed by one or more QPs with butterfly-arbitrage constraints linearized around the preceding solution.

---

## Key Requirements for a Good Volatility Surface Fitter

A robust volatility surface fitter should satisfy the following:

1. **Market Consistency:**  
   Accurately fit market bid and ask quotes while avoiding overfitting.

2. **Arbitrage-Free:**  
   Enforce constraints designed to prevent static arbitrage, even if market quotes are not. This includes:
   - No **calendar spread arbitrage**
   - No **butterfly arbitrage**, including outside listed strikes and in the tails

3. **Intuitive Parameterization:**  
   Model parameters should be interpretable, so their impact on risk and hedging is straightforward.

4. **Stable and Fast Calibration:**  
   The fitting algorithm should converge reliably and be efficient for practical use.

---
## 📊 Results
### Volatility Smile Calibration

The figure below compares market bid and ask implied volatility quotes with the fitted CVI volatility smile. The fitted smile remains smooth while lying within the market bid-ask spread. The lower panel shows the corresponding risk-neutral probability density implied by the fitted volatility smile.

![Volatility Smile](https://github.com/user-attachments/assets/e894e894-834f-4a99-a27b-74aefe72c62a)

**Figure 1.** Market bid and ask volatility quotes together with the fitted Convex Volatility Interpolation smile. The corresponding risk-neutral probability density implied by the fitted smile is shown below.

### Implied Volatility Surface

The figure below illustrates the arbitrage-free implied volatility surface produced by the Convex Volatility Interpolation methodology across option tenor and log-forward moneyness.

<img width="623" height="590" alt="CVI implied volatility surface" src="https://github.com/user-attachments/assets/2850bdad-5da2-4aca-a715-3cea10f53097" />

**Figure 2.** Arbitrage-free implied volatility surface generated using the Convex Volatility Interpolation methodology.

---

## References

[1] Deschâtres, F. (2026). Convex Volatility Interpolation. Risk, Cutting Edge, February 27, 2026. Available at SSRN.
Available at SSRN: [https://ssrn.com/abstract=4831218](https://ssrn.com/abstract=4831218) or [http://dx.doi.org/10.2139/ssrn.4831218](http://dx.doi.org/10.2139/ssrn.4831218)

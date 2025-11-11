# Convex Volatility Interpolation

This project implements **Convex Volatility Interpolation (CVI)** — a model-free method for fitting a volatility surface introduced in [1]. The CVI method demonstrates how to fit a volatility surface while **preventing arbitrage**.  

CVI uses a **dual parameterization** in cubic spline and B-spline spaces, calibrated via **quadratic programming (QP) with linear constraints**. It places no restrictions on the number of parameters, allowing it to flexibly fit any volatility surface observed in the market.

---

## Key Requirements for a Good Volatility Surface Fitter

A robust CVI implementation should satisfy the following:

1. **Market Consistency:**  
   Accurately fit market bid and ask quotes while avoiding overfitting.

2. **Arbitrage-Free:**  
   Ensure the surface is arbitrage-free in strike and time, even if market quotes are not. This includes:
   - No **calendar spread arbitrage**
   - No **butterfly arbitrage**, including outside listed strikes and in the tails

3. **Intuitive Parameterization:**  
   Model parameters should be interpretable, so their impact on risk and hedging is straightforward.

4. **Stable and Fast Calibration:**  
   The fitting algorithm should converge reliably and be efficient for practical use.

---

![Volatility Smile](https://github.com/user-attachments/assets/e894e894-834f-4a99-a27b-74aefe72c62a)

---

## References

[1] Deschâtres, F. (2024). *Convex Volatility Interpolation.*  
Available at SSRN: [https://ssrn.com/abstract=4831218](https://ssrn.com/abstract=4831218) or [http://dx.doi.org/10.2139/ssrn.4831218](http://dx.doi.org/10.2139/ssrn.4831218)

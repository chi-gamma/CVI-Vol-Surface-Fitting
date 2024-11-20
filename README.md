# Convex Volatility Interpolation

This project implements the Convex Volatility Interpolation method for fitting a volatility surface introduced in [1], showing how to fit a volatility surface while preventing arbitrage.
The (CVI) method for fitting a volatility surface uses a dual parameterization in cubic spline and B-spline spaces calibrated using quadratic programming (QP) with linear constraints. 
This method has no restrictions on the number of parameters, and is able to fit any volatility surface.

![vol smile](https://github.com/user-attachments/assets/e894e894-834f-4a99-a27b-74aefe72c62a)


## References
<a id="1">[1]</a> 
Deschâtres, F. (2024). 
Convex Volatility Interpolation.
Available at SSRN: https://ssrn.com/abstract=4831218 or http://dx.doi.org/10.2139/ssrn.4831218

# Convex Volatility Interpolation

This project implements the Convex Volatility Interpolation, a model-free method for fitting a volatility surface introduced in [1], showing how to fit a volatility surface while preventing arbitrage.
The (CVI) method for fitting a volatility surface uses a dual parameterization in cubic spline and B-spline spaces calibrated using quadratic programming (QP) with linear constraints. 
This method has no restrictions on the number of parameters, and is able to fit any volatility surface.

The requirements of a good volatility surface fitter are assumed to be the following:
-  It should accurately fit the market bids and asks in a consistent manner to prevent overfitting.
-  It should be arbitrage free in strike and time, without assuming that the market bids and asks are
      themselves arbitrage free. There should be no calendar spread or butterfly arbitrage, including outside
      of the listed strikes, in the tails.
-  The parameterization should be intuitive. The relationship between risks managed and the parameters should be straightforward.
-  The calibration should be stable and fast.

![vol smile](https://github.com/user-attachments/assets/e894e894-834f-4a99-a27b-74aefe72c62a)


## References
<a id="1">[1]</a> 
Deschâtres, F. (2024). 
Convex Volatility Interpolation.
Available at SSRN: https://ssrn.com/abstract=4831218 or http://dx.doi.org/10.2139/ssrn.4831218

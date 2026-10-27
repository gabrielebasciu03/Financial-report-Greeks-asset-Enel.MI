# Financial-report-Greeks-asset-Enel.MI
Option Greeks and Implied Volatility Surfaces: Enel S.p.A. (ENEL.MI). Black-Scholes Greeks in Excel/VBA: theoretical surfaces, implied volatility skew from Refinitiv option chains, and a comparison of estimated vs. Refinitiv Greeks.
## Overview

This project studies the sensitivities of European options, the Greeks, in three stages: theory, market data and reconciliation with a professional data provider. It was built in Excel with VBA functions implementing the closed-form Black-Scholes formulas, and it is Report 5 of the A.Y. 2025-2026 coursework.

**Part 1: Theoretical Greeks.** 
Delta, Gamma, Theta, Vega and Rho are computed for calls and puts (K = 100, r = 1%, σ = 20%) over S ∈ [60, 140] and τ ∈ [0.1, 5] years, and plotted as 3D surfaces. Delta turns into a near-step function around the strike at short maturities. Gamma peaks sharply at-the-money and decays for long maturities and deep ITM/OTM options. Theta is most negative for short-dated ATM options. A volatility-shock analysis (σ = 10%, 20%, 30%) shows that Gamma, Vega and Theta deform non-linearly, while Delta and Rho stay comparatively stable. Put Greeks mirror call Greeks, consistent with put-call parity.

**Part 2: Enel implied volatility surface.** 
Call and put chains from Refinitiv (strikes 8.4 to 12.5, maturities from 2 to 610 days) are inverted numerically through Black-Scholes to extract implied volatility. Both surfaces show a negative skew, with higher IV at low strikes, steeper at short maturities and flatter at long ones. This points to downside-risk pricing rather than a symmetric smile. Vega and Rho surfaces built from the market data are qualitatively consistent with theory but noisy, because of data gaps and illiquid strikes.

**Part 3: Theoretical vs. empirical Greeks.** 
For an ATM Enel call (S = 9.79, K = 10, maturity 19/06/2026, σ_imp = 23.214%), Black-Scholes estimates are compared with Refinitiv's values. Rho, Theta and Vega match closely once time is expressed in years and the rate is converted to continuous compounding. Delta is reasonably close, while Gamma shows the largest gap. A flat-volatility model is least reliable for second-order sensitivities, which depend heavily on the smile.

**Tech:** 
derivatives pricing, VBA, numerical IV inversion, volatility-surface analysis, hedging intuition, data-quality assessment.

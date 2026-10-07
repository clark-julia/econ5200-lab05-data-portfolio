# econ5200-lab05-data-portfolio
# Diagnosing a Flawed Risk Model: VaR, Expected Shortfall & Monte Carlo

## Objective
I diagnosed a junior analyst's normal-distribution VaR model and showed how much tail risk it misses compared with historical and fat-tailed methods.

## Methodology
- Reviewed the analyst's model, which assumes normally distributed returns, and compared its 99% VaR against historical VaR on the same portfolio.
- Computed VaR and Expected Shortfall under three methods: historical, normal, and Student-t (fitted degrees of freedom = 4.58).
- Ran Monte Carlo simulation and cut the standard error using antithetic variates.
- Used a `risk_metrics.py` module (`calculate_var`, `calculate_es`, `mc_var`) and ran its self-tests to confirm the functions behaved as expected.
- Had an AI write a VaR backtest, revised my prompt once, and checked the result against my own count of breaches.

## Key Findings
- At 99%, the normal model understated historical VaR by 12.7%, which is $40,393 on the portfolio.
- Antithetic variates reduced the Monte Carlo standard error by 1.26x.
- The normal 99% VaR was breached on 1.71% of days, not the 1% a 99% VaR promises. My own count matched the AI's backtest.

# eth_mempool_transaction_congestion
1. Objective:< br/>
Simple research onto whether real-time mempool congestion on Ethereum can predict short-horizon ETH volatility.

2. Data Pipeline:< br/>
Query using Ethereum Mempool data in DuneSQL (flashbot mempool dumpster) and fetched using dune-client and REST API. 

3. Hypothesis:< br/>
H1: “A spike in the 90-percentile gas bid raises the next-5-minute realised ETH volatility.”

4. Methods:< br/>
Created and analysed HAC-robust OLS model with scatter and overlay plots for visual sanity.

5. Results:< br/>
| Metric        | Value         |
| ------------- | ------------- |
| p-value       | 0.35          |
| R^2           | 0.001         |
| Durbin-Watson | 0.30          |

6. Conclusion:
No statistical evidence: gas-z explains <0.1 % of forward vol; residuals highly autocorrelated.

7. Future Work:
- Add more historical data; Dune Analytics has fixed limit on number of data to fetch into the local server in free version account, so need alternative approach
- Explore various regresion models like multivariate AR / GARCH-X models to handle price and volume data
- Test other parameters including percentile, lags.
- Test other data-preprocessing methods
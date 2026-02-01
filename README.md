# Quantum-Alpha-Nexus (QAN)


**Harnessing Quantum-inspired Optimisation for Liquidity-Aware Execution on WEEX.**

---

## Project Overview

**Quantum Alpha Nexus (QAN)** is an advanced automated trading framework developed for the **WEEX AI Automated Trading Hackathon**. The project tackles the "curse of dimensionality" in high-frequency trading (HFT)—the massive computational challenge of real-time portfolio rebalancing and risk management across a vast universe of digital assets.

By integrating the **CoinGecko API** for deep market intelligence with quantum algorithms (QAOA and VQE), QAN identifies the "Efficient Frontier" of assets—minimising risk and maximising returns—with a speed and precision unattainable by standard classical solvers.

---

## Architecture


### 1. Market Intelligence Layer: CoinGecko API
* **Dynamic Filtering:** Scans the WEEX tradable universe to filter assets based on real-time liquidity and volume-to-market-cap ratios to eliminate high-slippage risks.
* **Volatility Calibration:** Retrieves historical price data to calculate realised volatility, which directly modulates the algorithm's risk-aversion parameters.

### 2. Quantum Optimisation Engine: `qiskit-finance`
* **Problem Formulation:** Maps the Mean-Variance Optimization (MVO) problem into a **Quadratic Unconstrained Binary Optimization (QUBO)** model.
* **Quantum Solvers:** Employs the **Quantum Approximate Optimization Algorithm (QAOA)** and **Variational Quantum Eigensolver (VQE)** to explore billions of portfolio combinations in parallel. 
* **Constraint Injection:** Encodes sophisticated trading rules (e.g., sector diversity, max allocation per asset) as penalty terms within the Ising Hamiltonian.

### 3. Execution Layer: (WEEX API)
* **Precision Entry:** Automatically deploys capital on the WEEX exchange according to the weights ($w$) optimized by the quantum layer.
* **Adaptive Safety:** Dynamically adjusts bid-ask spreads and stop-loss triggers based on the real-time volatility metrics provided by the intelligence layer.

---

## Mathematical Models and Quantum Logic

### The Objective Function
The core logic resides in a modified **Markowitz Mean-Variance Model**:

$$\min_{w} \left( q \cdot w^T \Sigma w - \mu^T w \right)$$

* **$w$ (Weights):** The optimized allocation of capital across the selected asset universe.
* **$\Sigma$ (Covariance Matrix):** A measure of asset correlation derived from CoinGecko data.
* **$\mu$ (Expected Returns):** Predicted performance based on historical trends.
* **$q$ (Risk Aversion):** A tunable parameter scaling the trade-off between risk and reward.

### The Quantum Edge
To solve this on quantum hardware or simulators, we translate the MVO into a **QUBO** format. The system seeks the **Ground State** (the configuration with the lowest physical energy), which represents the absolute mathematical optimum for the portfolio.


## Advantages of QAN

1.  **Combinatorial Speedup:** QAOA utilises quantum interference to amplify optimal portfolio configurations, outperforming classical search which is originally an NP-hard problem, and classical solutions are usually brute-force. 
2.  **Slippage Protection:** Integrated CoinGecko liquidity filters ensure the bot only targets assets with sufficient depth, protecting the 1,000 USDT starting capital.
3.  **Institutional Rigor:** By utilising `qiskit-finance`, QAN implements financial mathematics which in the future, can be scaled as necessary.



---

**Built for the WEEX Alpha Awakens Hackathon | Imperial College London**

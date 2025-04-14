# 🧠 Quantum RSI Executor  
**Validated, Optimized, and Production-Ready Quantum-Enhanced RSI Strategy**  
License: MIT  

---

## 📌 Overview

**Quantum RSI Executor** is a modular, signal-agnostic, and volatility-calibrated trading engine that combines classical technical indicators with quantum-inspired correction logic and conditional risk assessment.  
It transforms traditional RSI into a probabilistically enhanced decision metric suitable for high-frequency, low-latency, and institutional-scale trading systems.

---

## 🚀 Key Features

- ✅ Classical RSI with exponential smoothing  
- 🧬 Quantum Bitstring Correction (QBC) — real-time signal modulation  
- 📉 Risk Estimation via CVaR (Conditional Value at Risk)  
- 💡 Adaptive Position Sizing using dynamic ATR-based scaling  
- 🧠 Integrated plotting and visualization for diagnostics  
- ⚙️ Modular design — pluggable into larger algorithmic stacks  

---

## 🧪 Core Components

| Component                | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| `compute_rsi()`          | Calculates RSI using smoothed average gains and losses                      |
| `apply_quantum_correction()` | Modulates RSI with normalized quantum bitstring input                |
| `compute_quantum_risk()` | Simulates returns to estimate CVaR via Gaussian sampling                    |
| `compute_position_size()`| Allocates capital using ATR-based risk units                                |
| `analyze()`              | Main pipeline: computes metrics, visualizes results, and returns trade info |

---

## 🧮 Core Formulas

**RSI:**  
\[
RSI_t = 100 - \frac{100}{1 + \frac{AvgGain_t}{AvgLoss_t}}
\]  

**Quantum RSI:**  
\[
RSI_{quantum} = RSI_t \cdot \left( \frac{int(bitstring)}{2^n - 1} \right)
\]  

**CVaR (α = 0.05):**  
\[
CVaR = \frac{1}{\alpha N} \sum_{i=1}^{\alpha N} r_i \quad \text{where } r_i \in \text{sorted(returns)}
\]  

---

## 📈 Sample Usage

```python
from quantum_rsi_executor import QuantumRSIExecutor
import numpy as np

prices = np.cumsum(np.random.randn(100) + 0.5) + 100
executor = QuantumRSIExecutor()
results = executor.analyze(prices, bitstring="110101")

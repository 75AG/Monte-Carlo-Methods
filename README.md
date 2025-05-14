# Monte-Carlo-Methods
 Monte Carlo Simulation of Economic Resistance Constant (μₑ)
# Monte Carlo Simulation of Economic Resistance Constant (μₑ)

This repository contains the Python implementation of the Monte Carlo simulation used in the research paper:

**"Analyzing Stagflation Using a Fluid Dynamics Model: Toward Deriving an Economic Resistance Constant"**

---

## 📌 Description

This project uses a fluid dynamics analogy to model macroeconomic stagflation. Specifically, we use Monte Carlo methods to simulate 10,000 scenarios and estimate an economic resistance constant, denoted as μₑ, which reflects the economy’s resistance to growth under inflationary constraints such as taxation and interest rates.

---

## 🔬 Methodology

The simulation is based on a modified form of Newton’s law of viscosity:

Where:
- `P`: Liquidity (analogous to pressure)
- `v`: Economic growth rate
- `Q`: Economic output
- `τ`: Tax rate
- `r`: Interest rate

The simulation:
- Randomly samples P, v, Q, τ, r from uniform distributions
- Applies transformations:
  - `v_effective = v * exp(-r)`
  - `Q_effective = Q * (1 - τ)`
- Calculates μₑ for each scenario
- Aggregates statistics (mean, median, standard deviation)

---

## 📂 Files



## 📊 Example Output

- Mean μₑ: ~5.77  
- Median μₑ: ~2.62  
- Std Dev μₑ: ~11.23  
- Typical clustering: μₑ ≈ 2.5–3

---

## ▶️ How to Run

1. Clone the repository:
```bash
git clone https://github.com/your-username/economic-resistance-montecarlo.git
cd economic-resistance-montecarlo



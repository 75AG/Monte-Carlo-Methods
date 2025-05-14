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
import numpy as np
import matplotlib.pyplot as plt

# Number of simulation trials
num_trials = 10000

# Generate random variables using uniform distributions
P = np.random.uniform(100, 1000, num_trials)       # Monetary liquidity (pressure)
v = np.random.uniform(0.1, 2.0, num_trials)        # Growth rate (velocity)
Q = np.random.uniform(10, 500, num_trials)         # Economic output
tau = np.random.uniform(0.05, 0.5, num_trials)     # Tax rate
r = np.random.uniform(0.01, 0.2, num_trials)       # Interest rate

# Apply adjustments for interest rate and taxes
v_effective = v * np.exp(-r)
Q_effective = Q * (1 - tau)

# Compute economic resistance constant μₑ
mu_e = (P * v_effective) / Q_effective

# Display statistics
mean_mu_e = np.mean(mu_e)
median_mu_e = np.median(mu_e)
std_mu_e = np.std(mu_e)

print(f"Mean μₑ: {mean_mu_e:.2f}")
print(f"Median μₑ: {median_mu_e:.2f}")
print(f"Standard Deviation: {std_mu_e:.2f}")

# Plot histogram of μₑ
plt.figure(figsize=(10, 6))
plt.hist(mu_e, bins=100, color='skyblue', edgecolor='black', density=True)
plt.title("Distribution of Economic Resistance Constant μₑ")
plt.xlabel("μₑ")
plt.ylabel("Probability Density")
plt.grid(True)
plt.show()




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



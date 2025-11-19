## PORTFOLIO-PIPELINE-REP.-BY-A.B.
A complete portfolio optimization pipeline using Pyomo, IPOPT, and automated return analysis.

## Overview

This repository contains a fully structured portfolio optimization project designed to:

Download historical stock prices

Compute daily, log, and monthly returns

Build return/covariance/correlation matrices

Generate an efficient frontier

Solve quadratic optimization models using IPOPT

Visualize allocation behavior as target returns increase

Automatically stop when the portfolio becomes fully concentrated

The project is built as a clean Python package, following the same organizational style used in high-quality data-science codebases 

## Repository Structure

PORTFOLIO-PIPELINE-REP.-BY-A.B./
│
├── main.py                        # Entry point to run the full project
├── requirements.txt               # All required Python dependencies
├── README.md                      # This documentation
│
├── src/
│   └── unified_portfolio.py       # Core portfolio optimization engine (Pyomo + IPOPT)
│
└── Unified Portfolio Code A.B..ipynb   # Original notebook (reference only)

## Installation & Setup

## 1. Clone the repository
```python
git clone https://github.com/atesboyaci-alt/PORTFOLIO-PIPELINE-REP.-BY-A.B..git
cd PORTFOLIO-PIPELINE-REP.-BY-A.B.
```
## 2. Install dependencies
```python
pip install -r requirements.txt

```

## 3. Run the full project
```python
python main.py
```

## IMPORTANT — Replace the Placeholder Ticker List

Inside src/unified_portfolio.py, replace:

tickers = ["AAPL", "MSFT", "GOOGL"]

with the actual assignment list:
```python
tickers = ["AXP","AFL","BAC","COIN","BA","CAT","DAL", "FDX", "GD", "DD","PKG","LYB","IP","LIN"]
```

## What IPOPT Does in This Project

IPOPT (Interior Point OPTimizer) solves nonlinear constrained optimization problems.
In this project, IPOPT computes the minimum-variance portfolio for a required return target.

## Optimization Model
min 𝑥⊤Σ𝑥

Subject to;

i∑​xi​=1
i∑​xi​μi​ ≥ target return
xi​ ≥ 0

## IPOPT’s Role

Efficiently solves quadratic programs

Ensures valid, feasible allocations

Handles constraints cleanly and quickly

Allows sweeping return targets in small increments

Stops when the portfolio becomes fully concentrated (only 1 asset at weight ≈ 1)

This is what makes the adaptive frontier generation possible.

## Running in Google Colab

This repository includes automatic Colab detection.

If the code is run inside Google Colab:

Installs idaes-pse

Downloads IPOPT binaries

Adds ./bin to PATH

Runs identically to local execution

No manual setup required.

## Author

Ates Boyaci
Portfolio Optimization Pipeline — Fall 2025



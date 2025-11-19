WOMACK-STOCKS-REP.-BY-A.B.
REPOSITORY STRUCTURE

WOMACK-STOCKS-REP.-BY-A.B./
│
├── main.py — Entry point to run the full project
├── requirements.txt — Python dependencies
├── README.md — Project documentation
│
├── src/
│ └── unified_portfolio.py — Core portfolio optimization module
│
└── Unified Portfolio Code A.B..ipynb — Original notebook (reference only)

CLONE THE REPOSITORY
git clone https://github.com/atesboyaci-alt/WOMACK-STOCKS-REP.-BY-A.B..git

cd WOMACK-STOCKS-REP.-BY-A.B.

INSTALL DEPENDENCIES
pip install -r requirements.txt

RUN THE PROJECT
python main.py

PLEASE REPLACE THE PLACEHOLDER INSIDE unified_portfolio.py
tickers = ["AAPL", "MSFT", "GOOGL"]
WITH YOUR REAL WOMACK STOCK LIST:

tickers = ["AXP", "AFL", "BAC", "COIN", "BA", "CAT",
"DAL", "FDX", "GD", "DD", "PKG", "LYB",
"IP", "LIN"]

WHAT IPOPT DOES IN THIS PROJECT
IPOPT (“Interior Point OPTimizer”) is a nonlinear optimization solver used to compute portfolio weights that:
• Satisfy the required return
• Minimize portfolio variance
• Respect weight constraints
• Allocate 100% of the budget

In this project, Pyomo sends IPOPT a quadratic optimization model:

Minimize: xᵀ Σ x
Subject to: Σ x_i = 1
Σ x_i * μ_i ≥ target_return
x_i ≥ 0

IPOPT:
• Finds the optimal weights for each target return
• Stops when the portfolio becomes fully concentrated
• Ensures mathematically correct solutions

This solver enables fast, accurate frontier generation even with large ticker sets.

RUNNING IN GOOGLE COLAB
This project contains built-in Colab detection. If run inside Colab, it automatically:
• Installs idaes-pse
• Downloads IPOPT solver binaries
• Adds ./bin to PATH
• Runs exactly like a local machine
No manual configuration required.

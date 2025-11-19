PORTFOLIO-PIPELINE-REP.-BY-A.B.

This repository implements a unified portfolio optimization pipeline that retrieves historical stock data, computes return metrics, constructs covariance and correlation matrices, and generates an efficient frontier using Pyomo and IPOPT. The project follows a clean and modular Python structure consistent with course standards.

REPOSITORY STRUCTURE

PORTFOLIO-PIPELINE-REP.-BY-A.B./
|
|-- main.py # Entry point for the full pipeline
|-- requirements.txt # Required Python packages
|-- README.md # Project documentation
|
|-- src/
| |-- unified_portfolio.py # Core optimization and analysis module
|
|-- Unified Portfolio Code A.B..ipynb # Original notebook (reference only)

CLONE THE REPOSITORY

git clone https://github.com/atesboyaci-alt/PORTFOLIO-PIPELINE-REP.-BY-A.B..git

cd PORTFOLIO-PIPELINE-REP.-BY-A.B.

INSTALL DEPENDENCIES

pip install -r requirements.txt

RUN THE PIPELINE

python main.py

Running the pipeline performs the following:

Downloads historical prices for selected tickers

Computes daily, log, and monthly return series

Constructs covariance and correlation matrices

Generates diagnostic visualizations

Builds and solves a portfolio optimization model using Pyomo and IPOPT

Traces the efficient frontier over increasing required returns

Produces allocation profiles across the risk spectrum

TICKER CONFIGURATION

Inside src/unified_portfolio.py, update the base ticker list. Replace:

tickers = ["AAPL", "MSFT", "GOOGL"]

with the Womack stock list:

tickers = ["AXP", "AFL", "BAC", "COIN", "BA", "CAT",
"DAL", "FDX", "GD", "DD", "PKG", "LYB",
"IP", "LIN"]

OPTIMIZATION MODEL DETAILS

The optimization model seeks the minimum-variance portfolio that satisfies a required expected return. IPOPT is used as the nonlinear solver.

Objective:

Minimize xᵀ Σ x

Subject to:

Σ x_i = 1
Σ x_i * μ_i ≥ target_return
x_i ≥ 0

IPOPT provides:

Feasible optimal weights for each return level

Portfolio variance and standard deviation values

A full set of frontier points for visualization

Automatic termination when a fully concentrated portfolio is reached

The model is solved iteratively across increasing target returns to construct the efficient frontier.

GOOGLE COLAB EXECUTION

The script includes automatic handling for Colab environments:

Installs idaes-pse

Retrieves IPOPT binaries

Updates PATH to include solver executables

Ensures Pyomo and IPOPT run without local installation

No additional configuration is required when using Colab.

AUTHOR

Ates Boyaci
Portfolio Pipeline Project — Fall 2025
Instructor: Prof. Wanik

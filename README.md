# Portfolio Optimization with Python

[![Python Version](https://img.shields.io/badge/python-3.7%2B-blue)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)
[![Finance](https://img.shields.io/badge/domain-Quantitative%20Finance-orange)](https://)

A comprehensive Python library for portfolio optimization and risk analysis. This project implements modern portfolio theory and optimization techniques to help build optimal investment portfolios that maximize returns for a given level of risk.

## 📊 Project Overview

Portfolio optimization is the process of selecting the best portfolio of financial assets according to some objective, typically maximizing expected return for a given amount of risk. This library provides:

- **Risk-Adjusted Return Optimization**: Find the optimal asset allocation that provides the best return for your risk tolerance
- **Multiple Optimization Methods**: Both mathematical optimization formulas and Monte Carlo simulations
- **Comprehensive Risk Analysis**: Calculate key risk metrics including volatility, Value at Risk (VaR), and more
- **Data Flexibility**: Compatible with multiple data sources including Yahoo Finance, Nasdaq, and brokerage APIs

## 🚀 Key Features

- **Modern Portfolio Theory (Markowitz) Implementation**
- **Monte Carlo Simulation for portfolio optimization**
- **Risk metrics calculation** (Volatility, VaR, Sharpe Ratio)
- **Multiple data source support** (Yahoo Finance, Nasdaq, Alpha Vantage, etc.)
- **Efficient Frontier visualization**
- **Portfolio performance analysis and backtesting**

## 🛠 Installation

### Prerequisites

- Python 3.7+
- pip package manager

### Clone and Install
    - Clone the repository
    git clone https://github.com/yourusername/portfolio-optimization.git

    - Navigate to the project directory
    cd portfolio-optimization
    
    - Install in editable mode (allows modifications and use in other scripts)
    pip install -e .

The -e flag installs the package in editable mode, meaning you can modify the code and see changes reflected across all your scripts that use this library.


## 📦 Dependencies

The project relies on these key Python libraries:

**numpy** - Numerical computations and linear algebra

**pandas** - Data manipulation and analysis

**scipy** - Scientific computing and optimization algorithms

**matplotlib** - Data visualization and plotting

**scikit-learn** - Data preprocessing and standardization

**pathlib** - Cross-platform file path handling

All dependencies are automatically installed with the package installation.

## 💻 Usage

### Basic Setup

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from scipy import optimize
from sklearn import preprocessing
import portfolio_optimization as po

#### Set pandas display options for better data frame visualization
pd.set_option('display.max_columns', None)
pd.set_option('display.expand_frame_repr', False)

## Getting Started

### Load your price data (example with Nasdaq data)
from portfolio_optimization.data_sources import nasdaq

### Initialize portfolio optimizer
optimizer = po.PortfolioOptimizer()

### Add assets and their price data
optimizer.add_asset('AAPL', apple_prices)
optimizer.add_asset('TSLA', tesla_prices)
optimizer.add_asset('MSFT', microsoft_prices)

### Run optimization for target risk level
optimal_weights = optimizer.optimize_for_risk(target_risk=0.15)

### Analyze results
optimizer.plot_efficient_frontier()
optimizer.calculate_portfolio_metrics()

## Data Sources

The library supports multiple data sources:

### Using Yahoo Finance
from portfolio_optimization.data_sources import yahoo_finance

### Using Nasdaq
from portfolio_optimization.data_sources import nasdaq

### Using Alpha Vantage  
from portfolio_optimization.data_sources import alpha_vantage

### Custom data (CSV, Excel, etc.)
prices = pd.read_csv('your_price_data.csv')


## 🎯 Portfolio Optimization Methods

1. Mathematical Optimization
Uses SciPy's optimization algorithms to find the exact optimal portfolio weights mathematically.

2. Monte Carlo Simulation
Runs thousands of random portfolio combinations to find the best risk-return profiles.

3. Risk-Adjusted Return Optimization
Maximizes returns for a given level of risk tolerance specified by the user.

## 📈 Example: Building an Optimal Portfolio

### Define your risk tolerance (standard deviation)
risk_tolerance = 0.18  # 18% annual volatility

### Get optimal portfolio weights
weights = optimizer.optimize_for_risk(risk_tolerance)

print("Optimal Portfolio Allocation:")
for stock, weight in weights.items():
    print(f"{stock}: {weight:.2%}")

### Calculate expected portfolio metrics
metrics = optimizer.calculate_metrics(weights)
print(f"Expected Return: {metrics['return']:.2%}")
print(f"Expected Risk: {metrics['risk']:.2%}")
print(f"Sharpe Ratio: {metrics['sharpe']:.2f}")

## 🏗 Project Structure
```
portfolio-optimization/
├── src/
│   └── portfolio_optimization/
│    ├── __init__.py
│    ├── optimizer.py          - Main optimization engine
│    ├── risk_metrics.py       - Risk calculation functions
│    ├── data_sources/         - Data source integrations
│        └── visualization.py     - Plotting and charting
├── examples/                     - Usage examples and tutorials
├── tests/                        - Test suite
├── requirements.txt              - Project dependencies
└── setup.py                      - Package configuration
```

## 🤝 Contributing

Contributions are welcome! This project is particularly useful for:

Finance students working on portfolio management projects

Wealth management professionals looking to automate portfolio construction

Quantitative analysts developing investment strategies

Python developers interested in financial applications

Feel free to fork the repository and submit pull requests for any improvements.

## 📝 License


This project is open source and available under the MIT License.



# RL-Based Portfolio Optimization using PPO and ARIMA

## Project Overview

This project presents a Reinforcement Learning-based approach for portfolio optimization using Proximal Policy Optimization (PPO) combined with the ARIMA time-series forecasting model.

The main objective of the project is to dynamically allocate investments between selected stocks based on historical market data and predicted price information.

The project uses historical stock market data of Reliance Industries and Tata Consultancy Services (TCS).

ARIMA is used to generate predicted stock price information, while the PPO reinforcement learning agent learns an investment allocation strategy by interacting with a custom stock market environment.

The performance of the reinforcement learning model is compared with an equal-weight baseline portfolio.

## Problem Statement

Traditional portfolio allocation strategies often use fixed investment rules and may not adapt effectively to changing market conditions.

The objective of this project is to develop an intelligent portfolio optimization system that dynamically adjusts asset allocation using reinforcement learning.

The system aims to study whether a PPO-based reinforcement learning agent, enhanced with ARIMA-generated predictive features, can perform better than a simple equal-weight baseline strategy.

## Technologies Used

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Matplotlib
- Gymnasium
- Stable-Baselines3
- Proximal Policy Optimization (PPO)
- ARIMA
- Statsmodels
- Git
- GitHub

## Dataset

The project uses historical stock price datasets for:

- Reliance Industries
- Tata Consultancy Services (TCS)

The datasets are stored in CSV format.

The stock data includes attributes such as:

- Date
- Open Price
- High Price
- Low Price
- Previous Close
- Last Traded Price
- Other historical market information

For portfolio optimization, the relevant stock price information is extracted, cleaned, and converted into numerical format.

## Project Methodology

The project follows the pipeline:

Stock Market Data → Data Preprocessing → ARIMA Forecasting → Custom Gymnasium Environment → PPO Agent Training → Portfolio Evaluation → Baseline Comparison

### 1. Data Collection

Historical stock market data for Reliance Industries and TCS is collected and stored in CSV format.

### 2. Data Preprocessing

The datasets are cleaned and processed before model training.

The preprocessing steps include:

- Loading CSV datasets
- Extracting relevant stock price information
- Converting values into numerical format
- Handling missing values
- Preparing the final dataset

### 3. ARIMA Forecasting

The ARIMA time-series model is used to generate predicted stock price information.

The ARIMA-generated prediction is added as an additional feature to the state representation of the reinforcement learning environment.

In simple terms:

ARIMA predicts, and PPO decides.

### 4. Custom Reinforcement Learning Environment

A custom portfolio environment is developed using Gymnasium.

The reinforcement learning problem consists of:

- Agent: PPO model
- Environment: Simulated stock market environment
- State: Current stock market information and ARIMA-generated predictive feature
- Action: Portfolio allocation decisions
- Reward: Portfolio performance based on investment returns

### 5. PPO Model

Proximal Policy Optimization (PPO) is used as the reinforcement learning algorithm.

PPO is suitable for this project because portfolio allocation can be represented using a continuous action space.

The PPO agent interacts with the environment and learns an investment allocation policy through reward-based training.

### 6. Baseline Strategy

An equal-weight portfolio strategy is used as the baseline.

In the baseline strategy:

- 50% of the investment is allocated to Reliance
- 50% of the investment is allocated to TCS

The baseline does not learn or dynamically modify its allocation strategy.

The PPO model is compared with this baseline to evaluate whether reinforcement learning provides improved portfolio decision-making.

## Performance Metrics

The model is evaluated using:

### Portfolio Growth

Portfolio growth represents how the value of the investment changes over the evaluation period.

### Sharpe Ratio

The Sharpe Ratio is used to evaluate risk-adjusted returns.

A higher Sharpe Ratio generally indicates better returns relative to the level of risk taken.

### Annualized Return

Annualized return estimates portfolio performance on a yearly basis.

## RL vs Baseline

The main comparison performed in this project is:

PPO Reinforcement Learning Agent vs Equal-Weight Baseline Portfolio

The baseline maintains fixed portfolio allocation, whereas the PPO agent learns a dynamic allocation strategy through interaction with the environment.

## Project Structure

- `RL_Portfolio_Optimization.ipynb` - Main project implementation
- Reliance CSV Dataset - Historical Reliance stock data
- TCS CSV Dataset - Historical TCS stock data
- Design Document - Project design and methodology
- Project Presentation - Project presentation slides
- `.gitignore` - Files excluded from Git tracking
- `README.md` - Project documentation

## Limitations

The current implementation has several limitations:

- The project uses a limited historical dataset
- Only two stocks are considered
- Transaction costs are not included
- Slippage is not modeled
- The system does not currently operate using real-time market data
- Historical performance does not guarantee future market performance

## Future Scope

The project can be further improved by:

- Using larger historical datasets
- Adding more stocks and financial assets
- Including transaction costs and slippage
- Implementing explicit risk constraints
- Comparing ARIMA with LSTM and Transformer-based forecasting models
- Performing hyperparameter optimization
- Implementing proper train, validation, and test datasets
- Integrating real-time stock market data
- Developing a portfolio management dashboard

## Conclusion

This project demonstrates the application of reinforcement learning to portfolio optimization.

ARIMA is used to generate predictive time-series information, while the PPO agent learns dynamic portfolio allocation decisions through interaction with a custom Gymnasium environment.

The project evaluates the reinforcement learning approach by comparing its portfolio performance with an equal-weight baseline strategy using financial performance metrics.

This implementation serves as a research and educational prototype for studying the application of reinforcement learning and time-series forecasting in financial portfolio optimization.
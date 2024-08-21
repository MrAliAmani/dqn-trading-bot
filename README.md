# TradingBot_Q-Learning_DQN

This repository contains the implementation of trading bots using Q-learning and Deep Q-learning Networks (DQNs).

## Project Overview

The project focuses on developing and comparing different reinforcement learning agents to trade stocks. It includes both Q-learning and various DQN models, each with different architectures and features.

## Project Structure

- **agents/**: Contains code for training and executing the different RL agents.
- **environment/**: A customized trading environment based on the AnyTrading Gym environment.
- **examples/**: Jupyter notebooks demonstrating the usage of the environments.
- **graphs/**: Graphs and charts from experiments.
- **scratch/**: Miscellaneous notebooks and scratch work.
- **utils/**: Utility scripts for data collection, saving, and plotting.

## DQN Agents

- **DQN1**: Initial attempt, unsuccessful in learning.
- **DQN2**: DQN2 uses a CNN to extract features from the entire observation space and approximate the Q values. It employs a target network and replay buffer. It sucks, most likely because it doesn't use one-hot vectors to encode past positions.
- **DQN3**: DQN3 is like DQN2 but with a teeny tiny NN that uses precomputed features: a 200 day and 50 day moving average. Like DQN2 it also sucks because I hadn't figured out that you have to use one-hot vectors to encode agents' past positions.
- **DQN4**: DQN4 finally figures out that you need to one-hot the position history. Duh. This uses a large feedforward neural network and finally produces some resemblance of profit.
- **DQN5**: DQN5 is like DQN4 but uses a small neural network and precomputed features: 200-day moving average, 50-day moving average, and current position, one-hotted.
- **DQN6**: DQN6 is like DQN4 but uses a CNN for function approximation over the entire observation space.

## Q-Learning Agents

- **Q_learning_stocks.py**: Initial Q-Learning agent.
- **Q_learning_singleunits.py**: Single-unit trader with adjustable hyperparameters.
- **Q_learning_multiunits.py**: Multi-unit trader with customizable buy/sell strategies.

## Installation

Clone the repository:

```bash
git clone https://github.com/MrAliAmani/dqn-trading-bot.git
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Usage
Run a specific DQN agent:

```bash
python run_dqn4_agent.py
```

Run a Q-learning agent:

```bash
python Q_learning_singleunits.py
```

## Feedback

If you have any feedback, please reach out to me at *<aliamani019@gmail.com>*.

## Authors

[@AliAmani](https://github.com/MrAliAmani)

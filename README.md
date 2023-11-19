# Deep-Reinforcement
Deep-Reinforcement-Stock-Trading
This project intends to leverage deep reinforcement learning in portfolio management. The framework structure is inspired by Q-Trader. The reward for agents is the net unrealized (meaning the stocks are still in portfolio and not cashed out yet) profit evaluated at each action step. For inaction at each step, a negtive penalty is added to the portfolio as the missed opportunity to invest in "risk-free" Treasury bonds. A lot of new features and improvements are made in the training and evaluation pipelines. All evaluation metrics and visualizations are built from scratch.

Key assumptions and limitations of the current framework:

trading has no impact on the market
only single stock type is supported
only 3 basic actions: buy, hold, sell (no short selling or other complex actions)
the agent performs only 1 action for portfolio reallocation at the end of each trade day
all reallocations can be finished at the closing prices
no missing data in price history
no transaction cost
Key challenges of the current framework:

implementing algorithms from scratch with a thorough understanding of their pros and cons
building a reliable reward mechanism (learning tends to be stationary/stuck in local optima quite often)
ensuring the framework is scalable and extensible
Currently, the state is defined as the normalized adjacent daily stock price differences for n days plus [stock_price, balance, num_holding].

In the future, we plan to add other state-of-the-art deep reinforcement learning algorithms, such as Proximal Policy Optimization (PPO), to the framework and increase the complexity to the state in each algorithm by constructing more complex price tensors etc. with a wider range of deep learning approaches, such as convolutional neural networks or attention mechanism. In addition, we plan to integrate better pipelines for high quality data source, e.g. from vendors like Quandl; and backtesting, e.g. zipline.

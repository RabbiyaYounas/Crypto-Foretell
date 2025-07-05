# Crypto-Foretell

Crypto Foretell is a hybrid Transformer-based architecture developed for cryptocurrency price forecasting. It introduces a dual-branch structure that models both long-term and short-term temporal dependencies using Auto-Correlation and Self-Attention + LSTM, respectively. The outputs are fused using a Bayesian Model Averaging (BMA) strategy.

**Model Architecture Overview**
The model is composed of three core components:

**1. Auto-Correlation Branch (Long-Term Trend Modeling)**
This branch is responsible for capturing long-range dependencies and cyclical patterns in the time series data.

**Key Components:**

AutocorrelationLayer: Identifies seasonal or repeating patterns.

EmbeddingLayer: Projects raw input into higher-dimensional space.

FeedForwardBlock: Applies non-linear transformations.

PositionalEncoding: Injects temporal order into input features.

This branch excels in learning overall market trends and low-frequency signals.

**2. Self-Attention + LSTM Branch (Short-Term Dynamics)**
This branch captures short-term volatility and recent fluctuations.

**Key Components:**

MultiHeadSelfAttention: Focuses on relevant nearby time steps.

LSTMBlock: Sequentially processes attention outputs to preserve local temporal structure.

FeedForwardBlock: Applies transformations for feature refinement.

ResidualConnections: Maintains gradient flow and improves learning stability.

This module is optimized for highly dynamic and volatile patterns in price series.

**3. Bayesian Model Averaging (Fusion Mechanism)**
This module combines the outputs of both branches to generate a robust final prediction.

**Fusion Strategy:**

Dynamically computes weights for each branch based on validation behavior.

Balances between long-term and short-term features.

Final output is an ensemble prediction derived from learned weights.

**How to Use**
This repository includes the model architecture only. Training, evaluation, and dataset scripts are not provided.

**To use:**

Clone the repository.

Explore autocorr_branch/ and attention_lstm_branch/ for model components.

Integrate modules into your own PyTorch training pipeline.

Customize fusion logic via fusion/.



**Contact**
For questions or collaboration, contact:

Rabbiya Younas: younas.rabbiya@yu.ac.kr

Hafiz Muhammad Raza ur Rehman: m.razaurrehman@gmail.com

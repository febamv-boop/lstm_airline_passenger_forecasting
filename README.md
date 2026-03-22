#### International Airline Passenger Forecasting
An end-to-end Time Series forecasting project using LSTMs (Long Short-Term Memory) to predict monthly passenger traffic. This project demonstrates
advanced data preprocessing techniques like Log Transformation and Min-Max Scaling to handle non-stationary data.

#### Project Overview
Predicting airline traffic is a classic time-series challenge due to its strong upward trend and multiplicative seasonality 
(the "wobble" gets bigger as the numbers grow).
This model achieves:
Training R2: 0.95
Testing R2: 0.72
Training MAPE: 5.18%
Testing MAPE: 6.95% (Highly Accurate)

#### Technical Workflow

#### 1. Data Preprocessing
To help the LSTM learn effectively, the data underwent a specific transformation pipeline:
Log Transformation: Applied to stabilize the variance and convert multiplicative seasonality into additive.
Min-Max Scaling: Normalized data to a [0,1] range for optimal neural network convergence.
Sliding Window: Created a look-back period of 12 months to capture the full annual cycle.

#### 2. Model Architecture
Built using Keras/TensorFlow:
Input Layer: Sequential input for 12-month time steps.
LSTM Layer: 32 units with L2 Regularization to prevent overfitting.
Dropout: 30% to improve generalization.
Dense Layers: ReLU activation for non-linearity followed by a single output neuron

#### 3. Evaluation Strategy
Metrics were calculated by reversing the transformations in the exact opposite order:
Inverse Scaling (Back to Log values)
Exponential Function (Back to real passenger counts)

#### Results
MAE for train: 11.75  ;  MAE for test: 32.44;
RMSE for train:15.28  ;  RMSE for test  41.10;
MAPE for train: 5.18% ;  MAPE for test  6.95%;
R2Score for train: 0.951 ;  R2Score for test   0.7178

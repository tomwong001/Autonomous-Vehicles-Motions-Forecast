
# Autonomous Vehicle Motion Prediction
This repository contains the report for the final project report of CSE 151B, where we built deep learning models to forecast the motion of autonomous vehicles based on observed data. The project team consists of Annie Fan, Yunyi Huang, Zixin Ma, and Zhenjian Wang.

Project Overview
In this project, we developed predictive models to forecast the positions of autonomous vehicles (AVs) over the next 6 seconds based on their motion data from the previous 5 seconds. The ability to predict future trajectories is crucial for enhancing the safety and efficiency of AVs. By accurately forecasting their motion, AVs can make better decisions in real time, reducing the likelihood of accidents caused by misjudgments.

Key Features:
Time-series data: Vehicle motion data sampled at 10Hz, consisting of X and Y coordinates. 

Input: 5 seconds of previous vehicle positions (50 time steps).

Output: Predicted positions for the next 6 seconds (60 time steps).

Techniques: Feature engineering (e.g., velocity, distance), deep learning models (Linear Regression, LSTM, MLP), data normalization.


Data
The dataset consists of vehicle motion data from multiple cities, including:

Austin

Miami

Pittsburgh

Dearborn

Washington DC

Palo Alto

Each city's dataset contains X and Y coordinates representing vehicle positions over time, along with derived features such as velocity and distance.


Data Splits:

Training set length: 203,816 samples.

Testing set length: 29,843 samples.

Each data point includes:

Input: 50 time steps (X, Y positions).

Output: 60 time steps (future X, Y positions).


Feature Engineering:

City: One-hot encoding of cities.

Velocity: Euclidean distance between consecutive points divided by time.

Distance: Euclidean distance between two points.


Models
We explored several models to predict future vehicle positions:

Linear Regression Model:

Input features: Position, velocity, distance, city information.

Hidden layers: 2048 → 4096 → 2048 dimensions.

Output: Predicted positions for the next 6 seconds.

Loss function: Mean Squared Error (MSE).


LSTM + MLP Model:

Input: X, Y positions over the previous 5 seconds.

Architecture: LSTM with 1 recurrent layer, followed by MLP layers.

Output: 60 time steps of predicted X, Y positions.

Activation function: Leaky ReLU.

Loss function: MSE.



Results
Key Results:

Our best-performing model was the LSTM + MLP model, which achieved:

Public score: 17.32344

Private score: 17.33729


Feature engineering, especially data normalization and adding velocity/distance, significantly improved model performance.


Model Performance:

Linear Model with Position, Velocity, and Distance: Training loss = 24.2054, Validation loss = 24.3439.

LSTM + MLP: Training loss = 13.7089, Validation loss = 18.8053.
Future Work
To improve our models further, we plan to:

Explore more advanced data preprocessing techniques such as data rotation.
Implement ensemble learning to combine the strengths of different models.
Experiment with Seq2Seq and Transformer architectures for better sequential prediction.

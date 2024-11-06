Explanation of the Code:

Data Preprocessing:
--------------------------------
We load the traffic flow data from a CSV file.
We normalize the data using MinMaxScaler to bring the values between 0 and 1, which is essential for deep learning models.
We create sequences of data (historical traffic flow) to use as input for the models. For example, if seq_length=48, the model will use the past 48 time steps to predict the next time step.

Model Development:
-------------------------------
We create two models: an LSTM and a GRU.
Both models have two recurrent layers, each followed by a Dropout layer to reduce overfitting, and a dense output layer.
The models are compiled using the Adam optimizer and the mean squared error loss function, suitable for regression tasks.

Training the Models:
--------------------------------------
We train both the LSTM and GRU models for 10 epochs with a batch size of 32.

Model Evaluation:
--------------------------------
After training, we predict the traffic flow for the test set and calculate the RMSE (Root Mean Squared Error) for both models.

Visualization:
--------------------------------------------------------
We plot the predicted traffic flow against the actual traffic flow for both the LSTM and GRU models.
We also visualize the training loss for both models over the epochs.

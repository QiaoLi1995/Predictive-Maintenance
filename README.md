# Deep Convolutional Neural Network for Remaining Useful Life Prediction 
This is an example repo that illustrates the concept of predictive maintainance through remaining useful life estimation. A deep convolution neural network is trained using a subset of the [C-MAPSS](https://ti.arc.nasa.gov/tech/dash/groups/pcoe/prognostic-data-repository/) dataset. This implementation utilized a threshold approach (called piecewise linear RUL) to define the engine pre-degradation cycle (R_early) when the engine is assumed to operate in a normal state. This implementation also uses selected sensor readings, as opposed to other implementation that used the whole dataset for model training. 

## Dataset
The dataset (Train_data.csv) is a cleaned version of train_FD001 subset in the C-MAPSS dataset. The test dataset (Test_engine_21.csv) is a subset of the C-MAPSS dataset containing engine number 21 sensor readings. Data cleaning is done by removing features that does not provide useful (and non-i.i.d) information from the dataset. This is done to move the implementation closer to real-world scenario.


## Model
The RUL estimator has 4 convolutional hidden layers with varying filters and a kernel size of 3. It also uses a Globalmaxpooling layer and dropout layers stacked as shown in the notebook. The output is a single-unit Dense layer. Relu activation is used on all convolutional layers while the fully connected layer and the output activation is linear. 

## Usage
You may load the model checkpoint and predict the RUL directly or preprocess and train a new model using the codes in the CMAPSS data cleaner and the steps shown in the notebook.

## Links:
1. O. Heimes, "Recurrent neural networks for remaining useful life estimation", International Conference on Prognostics and Health Management, pp. 1-6, 2008.
2. Li X, et al., "Remaining useful life estimation in prognostics using deep convolution neural networks" Reliability Engineering and System Safety pp.1-11, 2018. 

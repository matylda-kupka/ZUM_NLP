# ZUM_NLP
The dataset was downloaded from Kaggle. Dataset consists of tweets from twitter related to Corona Virus pandemic. Labels were assigned manually in the raw data set. 
The set consists of 6 columns:
- user name (coded, for privacy reasons)
- screen name
- location
- date of the tweet
- contents of the post (so tweet itself)
- sentiment assigned

There are 5 possible classes in this data set: Extremely Positive, Positive, Neutral, Negative, Extremely Negative. 

The CNN model consists of the following layers: 
- Embedding layer, which converts input data into dense vectors
- Conv1D layer which adds 1D convolutional layer to the model. Convolutional layers are essential for capturing local patterns in the input data
- MaxPooling layer, which reduces the dimensionality of the feature maps while retaining important information
- Flattening layer, which transforms the multi-dimensional output of the previous layers into a flat vector. This is necessary when transitioning from convolutional layers to fully connected layers.
- Dense layer, with 64 neurons and ReLU actiavtion function. This layer is intended to capture global patterns in the data.
- output layer with softmax function, as this problem deals with multi-class classification

Second model is LSTM model, which consists of the following:
- Embedding layer, used to convert integer-encoded vocabulary indices into dense vectors of fixed size
- LSTM layer. LSTM is a type of recurrent neural network (RNN) that is well-suited for sequence data like text. The parameter `128` specifies the number of LSTM units (or memory cells) in the layer.
- Dense layer, with activation softmax

 Both models are compiled with the following parameters:
- optimizer='adam': Adam is an optimization algorithm that adapts the learning rate during training
- loss='sparse_categorical_crossentropy': This is the loss function used for multi-class classification problems
- metrics=['accuracy']:accuracy will be monitored during training

In order to use the file, simply replace the "test_sententce" at the end of the code with your sentence and run the code. Result will be the prediction of the sentiment, as per above mentioned 5 classes.

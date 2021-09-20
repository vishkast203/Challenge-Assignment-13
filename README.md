# Challenge-Assignment-13
Neural Networks
Executive Summary: The Risk Management Team had requested help to create a model that predicts whether applicants will be successful if funded by Alphabet Soup. A CSV file containing a variety of information about each business, including whether or not it ultimately became successful was provided. The inital model run showed a 73%  accuracy rate that proved that there was more room to finesse the model to improve the accuracy.

Programs & Tools: The machine learning & Nueural Network models were run using Pandas, tensroFLow & Keras ru on Python Version 3.8. 

Steps: A dataframe was created by reading the csv file provided. The dataframe showed many columns of datatypes 'Object' as shown below:
EIN                        int64
NAME                      object
APPLICATION_TYPE          object
AFFILIATION               object
CLASSIFICATION            object
USE_CASE                  object
ORGANIZATION              object
STATUS                     int64
INCOME_AMT                object
SPECIAL_CONSIDERATIONS    object
ASK_AMT                    int64
IS_SUCCESSFUL              int64
dtype: object

The EIN &  NAME columns were dropped as they had no relevance to the binary calssification models being employed. 
Next a list of categorical variables was created as follows:
['APPLICATION_TYPE',
 'AFFILIATION',
 'CLASSIFICATION',
 'USE_CASE',
 'ORGANIZATION',
 'INCOME_AMT',
 'SPECIAL_CONSIDERATIONS']

The OneHotEncoder was initiated & Encode the categorcal variables using OneHotEncoder & a fully numerical DataFrame with the encoded variables was created. Next a  Numerical DF was cretaed to concat with the encoded dataframe. The final resultwas a fully numerical encoded_numerical_df that was used for the Neural Network Analysis.

Next the the target set y using the 'IS_SUCCESSFUL' column. All oither columns were allocated to X. We then split the features & targets into training & testing datasets. The StdScalar instance was initated & the model was scaled & fit the training dataset. 

Using the Tensor FLow & Keras models the number of input features & hidden latyers were defined &  the initial sequential model results were as follows:
Model: "sequential_15"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
dense_32 (Dense)             (None, 58)                6786      
_________________________________________________________________
dense_33 (Dense)             (None, 29)                1711      
_________________________________________________________________
dense_34 (Dense)             (None, 58)                1740      
_________________________________________________________________
dense_35 (Dense)             (None, 1)                 59        
=================================================================
Total params: 10,296
Trainable params: 10,296
Non-trainable params: 0

We then evaluated the model the model loss and accuracy metrics using the evaluate method and the test data. 
The model was then compiled as follows:
268/268 - 0s - loss: 0.5517 - accuracy: 0.7300
Loss: 0.551679253578186, Accuracy: 0.7300291657447815

Finally the inital resultys were saved to an HDF5 file & named the file AlphabetSOup H5. The next steps were to add additional hidden layers to improve th emodel accuracy. THis is still Work in Progress.


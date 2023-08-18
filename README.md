# Deep Learning Challenge

# Report

## Alphabet Soup Funding Success Prediction - Deep Learning Model Performance Report

## Overview of the Analysis:
The purpose of this analysis is to develop a deep learning model that can predict whether applicants receiving funding from Alphabet Soup will be successful in their ventures. The model is trained on a dataset containing information about more than    34,000 organizations that have received funding. The goal is to create a binary classifier that accurately predicts the success of the funding recipients based on various features.


## Results:

### Data Preprocessing:

. Target Variable: IS_SUCCESSFUL (Binary variable indicating 
  funding success)
. Features: All columns except for IS_SUCCESSFUL were used as 
  features for the  
  model.
. Removed Variables: EIN, NAME, SPECIAL_CONSIDERATIONS, and 
  STATUS were removed from   
  the final optimizedmodel as they are neither targets nor relevant features. By 
  focusing on the most relevant features, the model's performance is more likely to  
  improve as it learns meaningful patterns in the data. 

### Compiling, Training, and Evaluating the Model:

. Optimized Neural Network Architecture:
      . Input Layer: Number of features = 43 (determined by the 
        number of columns in   
        the preprocessed dataset)
      . Hidden Layer 1: 80 neurons, LeakyReLU activation function
      . Hidden Layer 2: 30 neurons, LeakyReLU activation function
      . Hidden Layer 3: 10 neurons, ReLU activation function
      . Hidden Layer 4: 5 neurons, ReLU activation function
      . Output Layer: 1 neuron, sigmoid activation function (for 
        binary classification)

I used additional layers to allow the model to learn complex and hierarchical representations of the data, potentially improving its ability to capture intricate patterns and relationships. 

I used Leaky ReLU to helps mitigate the vanishing gradient problem and allows some degree of gradient flow even for negative inputs.

I used ReLU activation since its a common choice for hidden layers due to its simplicity and effectiveness.

Sigmoid activation is used on the output because it is suitable for binary classification tasks, where the output represents the probability of the positive class (funding success).

The model did not reach the target performance of 75%. Even after optimization the model did not go above 73% as seen below. 

. Model Compilation:
      . Loss Function: Binary Cross-Entropy
      . Optimizer: Adam
      . Metrics: Accuracy

. Model Training:
      . Epochs: 100
      . Training Data: Scaled and preprocessed features from the training set

. Model Evaluation:
      . Loss: 0.559
      . Accuracy: 72.6%

To optimize performance I did the following:
	
        - Removed Variables EIN, NAME, SPECIAL_CONSIDERATIONS,   
          and STATUS
    	- Increased the Neural Network Architecture with 2       
          additional hidden layers and increased the nuerons to increase commplexity.
	    - I added LeakyReLU to the ReLu and Sigmoid             
          activation functions.
	

### Summary:

The optimized deep learning model achieved an accuracy of 72.6% on the test data, indicating its fair ability to predict funding success with moderate accuracy. While this performance could be acceptable, there is more room for improvement. 

Considering the nature of the problem and the features available, I suggest trying a Gradient Boosting model, like XGBoost. These models could perform better at dealing with organized data and handling the different categories that exist in this dataset. XGBoost works by putting together a bunch of decision trees, which helps it understand tricky details and connections in the data. This might make the predictions even better.


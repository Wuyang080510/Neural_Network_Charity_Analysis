# Neural_Network_Charity_Analysis
Use Pandas and Scikit-Learn to preprocess dataset, and create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

## Project Overview
Alphabet Soup is a non-profit foundation that support organizations that protect environment, improve people’s well-being, and unify the world. However, not all the organizations funded by the Alphabet Soup use the fund in an impactful way. In this project I will help Alphabet Soup to find out if the foundation’s money is used effectively by the organizations funded by Alphabet Soup. I would use features in the provided dataset to create a binary classifier to predict if the organizations funded by Alphabet Soup will be successful. This model will help Alphabet Soup to decide which organization is worth to donate to and which are high risk applicants. 

### The Dataset
The dataset for this analysis is a CSV file containing more than 34,000 organizations that have received fundings from Alphabet Soup over the years. 
The metadata is as following:

•	EIN and NAME—Identification columns

-	APPLICATION_TYPE—Alphabet Soup application type

-	AFFILIATION—Affiliated sector of industry

-	CLASSIFICATION—Government organization classification

-	USE_CASE—Use case for funding

-	ORGANIZATION—Organization type

-	STATUS—Active status

-   INCOME_AMT—Income classification

-	SPECIAL_CONSIDERATIONS—Special consideration for application

-	ASK_AMT—Funding amount requested

-	IS_SUCCESSFUL—Was the money used effectively

## Results

### Data Preprocessing
The final goal of this project is predicting if the organization funded by Alphabet Soup will be successful. Therefore, the IS_SUCCESSFUL column is the target for my neural network model. 

APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATION, AND ASK_AMT columns all have impact to the effectiveness of the funding. The data under these columns are considered as features for my model. 

EIN and NAME columns are identification columns. They do not offer any insight into the funding success result. Therefore, these two columns should be removed. 

## Compiling, Training, and Evaluation the Model
Fund Effectiveness Prediction Model Configuration:

-	hidden_nodes_layer1: 80 neurons, ReLU activation function

-	hidden_nodes_layer2: 20 neurons, ReLU activation function

-	Output Layer: 1 neuron, Sigmoid activation function

The target for the model is 75%. For the first try, the best accuracy the model could produce for the training dataset was 74.04%. The accuracy score for the test dataset was 72.7%.

### Model Optimization
-	Dropped the STATUS and SPECIAL_CONSIDERATION columns. More than 90% of the data in each of these two columns are the same. They do not add any power to the model’s prediction effect. 
-	Grouped the values in the ASK_AMT column, as most of the funding amounts equal $5000. The amount differs from $5000 were grouped into “other” category.
-	Added one more hidden layer with 40 neurons.
-	Use Tanh as an activation function 
With all the above attempts taken, the training dataset achieved an accuracy of 74.14%. The accuracy for the test dataset kept the same at 72.7%.

## Summary
The best result delivered by the model is the combination of ReLU, Tanh, and Sigmoid. Next, we could use a random forest tree classifier to generate a prediction model to compare with the neural network model I created in this project to identify if it has a better prediction power for the Alphabet Soup funding dataset. 

<br>

> Note: The accuracy for the solution is designed to be lower than 75%.
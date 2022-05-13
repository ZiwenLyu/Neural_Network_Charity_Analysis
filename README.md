# Neural_Network_Charity_Analysis

## Overview of the analysis: Explain the purpose of this analysis.

This project is to predict whether organization applicants will effectively utilize funds and succeed if funded by Alphabet Soup. The data is from Alphabet Soup’s business team, containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. I will adopt and train a neural network model to make predictions for Alphabet Soup.

## Results

### Data Preprocessing

- Target: "IS_SUCCESSFUL" is considered as target here. It is a binary type data: 0 means not successful, and 1 means successful.
- Features: "APPLICATION_TYPE": Alphabet Soup application type, "AFFILIATION": Affiliated sector of industry, "CLASSIFICATION": Government organization classification, "USE_CASE": Use case for funding, "ORGANIZATION": Organization type, "STATUS": Active status, "INCOME_AMT": Income classification, "SPECIAL_CONSIDERATIONS": Special consideration for application, "ASK_AMT": Funding amount requested.
- Neither targets nor features: "EIN" and "NAME" are identification of each organization and sshould be removed from the input data.
- Label features: For each categorical column with more than 10 unique values("CLASSIFICATION" and ""), I binned "rare" categorical variables together in a new column "other" to reduce feature dimensions, and then adopted one-hot encoding to label every categorical column.

### Compiling, Training, and Evaluating the Model

- I used two hidden layers at first and then added one more hidden layer to increase the accuracy. Usually the number of neurons in the input layer should be the number of features. Since there are over 40 features and 30,000 rows, I chose 40 neurons at first. And as the number of hidden neurons should be 2/3 the size of the input layer, plus the size of the output layer. For the first layer I chose 100 neurons, 80 neurons for the second layers, and 40 neurons for the thrid layer, and used ReLU activation functions for each layer. Because the output prediction is binary, so the output layer I use the sigmoid activation function. 
- Were you able to achieve the target model performance?
- What steps did you take to try and increase model performance?

## Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

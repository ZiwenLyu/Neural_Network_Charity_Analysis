# Neural_Network_Charity_Analysis

## Overview of the analysis: Explain the purpose of this analysis.

This project is to predict whether organization applicants will effectively utilize funds and succeed if funded by Alphabet Soup. The data is from Alphabet Soup’s business team, containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. I will adopt and train a neural network model to make predictions for Alphabet Soup.

## Results

### Data Preprocessing

- Target: "IS_SUCCESSFUL" is considered as target here. It is a binary type data: 0 means not successful, and 1 means successful.
- Features: "APPLICATION_TYPE": Alphabet Soup application type, "AFFILIATION": Affiliated sector of industry, "CLASSIFICATION": Government organization classification, "USE_CASE": Use case for funding, "ORGANIZATION": Organization type, "STATUS": Active status, "INCOME_AMT": Income classification, "SPECIAL_CONSIDERATIONS": Special consideration for application, "ASK_AMT": Funding amount requested.
- Neither targets nor features: "EIN" and "NAME" are identification of each organization and sshould be removed from the input data.
- Label features: For each categorical column with more than 10 unique values("CLASSIFICATION" and "APPLICATION_TYPE"), I binned "rare" categorical variables together in a new column "other" to reduce feature dimensions, and then adopted one-hot encoding to label every categorical column.
![bucket1](https://github.com/ZiwenLyu/Neural_Network_Charity_Analysis/blob/main/screenshots/bucket2-1.png)
![bucket2](https://github.com/ZiwenLyu/Neural_Network_Charity_Analysis/blob/main/screenshots/bucket2-2.png)

### Compiling, Training, and Evaluating the Model

- I used two hidden layers at first. Usually the number of neurons in the input layer should be the number of features, and the number of hidden neurons should be 2/3 the size of the input layer, plus the size of the output layer. Since there are over 40 features and 30,000 rows, I chose 40 neurons for the input layer, 28 neurons for the hidden layer, and used ReLU activation functions. Because the output prediction is binary, so the output layer I use the sigmoid activation function. 
As the fig shows, the total number of parameters are 2,937.

![parameters1](https://github.com/ZiwenLyu/Neural_Network_Charity_Analysis/blob/main/screenshots/screenshot2.png)

- The target accuracy is 75%. But the result is 72.7%.

![accuracy1](https://github.com/ZiwenLyu/Neural_Network_Charity_Analysis/blob/main/screenshots/screenshot2-1.png)

- In order to improve the accuracy, I increased one hidden layer and added more neurons, so the total number of parameteres rise to 8,691. Also, I reduced the rare occurences in bins. To better train the model, numbers of epochs are added to 300. The accuracy result is only slightly improved to 72.8%.

![parameters2](https://github.com/ZiwenLyu/Neural_Network_Charity_Analysis/blob/main/screenshots/screenshot1.png)
![accuracy2](https://github.com/ZiwenLyu/Neural_Network_Charity_Analysis/blob/main/screenshots/screenshot1-1.png)

## Summary: 

Overall, the nerual network model performs 72.8% accurately for this project. Since the features and size of this data is very limited, the nerual network prones to overfit. Other supervised classification models could solve the problem better, such as the random forest which requires less data to run.

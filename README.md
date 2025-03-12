# deep-learning-challenge

## Kevin Khov

### Neural Network Model Report

#### Overview:
The purpose of this analysis was to assist the nonprofit organization, Alphabet Soup, in selecting potential funding applicants that are most likely to be successful with their ventures. In order to do this, a neural network model was created to learn from a dataset of previous organizations that have been funded by Alphabet Soup that includes information such as their current active status, their income amount, the funding amount requested, and if they were successful or not. The goal was to create a model that would have at least 75% accuracy in predicting this.

#### Results:
- Data Preprocessing
  - Target Variable: IS_SUCCESSFUL (to determine if the oragnization was successful after receiving funding from Alphabet Soup)
  - Feature Variables: APPLICATION_TYPE, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, ASK_AMT
  - Removed Variables: EIN, NAME, APPLICATION_TYPE < 500 count, CLASSICATION < 1000 counts
 
- Compiling, Training, and Evaluating the Model
  - For the initial neural network model, a total of 3 layers were used (2 hidden layers). A total of 2 hidden layers were chosen to account for the possible complexity of learning the model has to go through. The first hidden layer had 80 neurons, the second hidden layer had 30 neurons, and the output layer had 1 neuron. These numbers were chosen to prevent possible overfitting or underfitting of the model. Each hidden layer used the ReLu activation function and the output layer used the Sigmoid activation function. The ReLu function helps the model learn complex patterns and the Sigmoid function is used since the target variable is binary (0 or 1).
 
  - This initial model did not reach the target model performance, only have an accuracy of 72.41%.
![image](https://github.com/user-attachments/assets/78fc9462-761e-43e9-8647-0931946337a8)

  - First, an additional hidden layer was added with number of neurons at 10, which increased the accuracy of the model to 72.55%. Second, the number of neurons in each hidden layer was increased to 128, 64 and 32, which increased the accuracy of the model to 72.65%. Lastly, the number of epochs was increased to 500, which decreased the accuracy back to 72.54%.
    - First Change:
![image](https://github.com/user-attachments/assets/9de4bccd-294d-4e31-86c2-0b38af4b0ddb)
    - Second Change:
![image](https://github.com/user-attachments/assets/0048f184-8105-4ba7-863c-20cdf6371ea5)
    - Third Change:
![image](https://github.com/user-attachments/assets/0edfb213-a4a6-4bbc-b59c-d25d88cfd4fc)


#### Summary:
Overall, the model did perform well in predicting whether an organization would succeed if it were to receive funding from Alphabet Soup, but not well enough to achieve the target accuracy goal of 75%. After taking steps to optimize the model by adding a hidden layer, increasing the number of neurons in each hidden layer, and increasing the number of epochs, the maximum accuracy achieved was 72.65%. While this was an increase in accuracy from the initial neural network model, further adjustments need to be made to the model in order to reach the desired 75% accuracy. Increasing the number of epochs to 500 may have caused overfitting, which caused the overall accuracy to slightly decrease. Another model that may be considered to help solve this problem is Random Forest model, which can account for multiple variables in a decision tree-like model. Since there are many variables that may contribute to a organization being successful with funding, such as income amount and ask amount, having a model that effectively takes these into account may improve the overall accuracy of the model.

The initial neural network model can be found in the file "AlphabetSoupCharity.ipynb". Subsequent neural network models can be found in the following files: "AlphabetSoupCharity_Optimization1.ipynb" (added hidden layer to model), "AlphabetSoupCharity_Optimization2.ipynb" (increased number of neurons in each hidden layer), and "AlphabetSoupCharity_Optimization3.ipynb" (increased number of epochs). The HDF5 files for each model can be found in the "HDF5 Files" folder under their corresponding model names.

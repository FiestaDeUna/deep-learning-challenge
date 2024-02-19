# deep-learning-challenge

Analysis Overview: 

ABC Charities is a crowdfunding charity organization. nThe purpose of this analysis is to build a deep learning model that can predict with at least 75% accuracy, which crowdfunding campaigns hosted by ABC will be succeesful in their fundraising goals.  

The model is trained off of a dataset with the following features: 


EIN: Identifier
NAME: Name or organization 
APPLICATION_TYPE: type of Alphabet Soup application 
AFFILIATION: Sector of industry 
CLASSIFICATION: Classification of organization 
USE_CASE: Usage for funding 
ORGANIZATION: Type of organization 
STATUS: Active or inactive 
INCOME_AMT:  income bins 
SPECIAL_CONSIDERATIONS: yes or no 
ASK_AMT: Amount requested 
IS_SUCCESSFUL: Was the fundraiser successful (target variable) 

Process in code: 

Step One: Preprocessing the data 
*Drop non-feature columns (EIN, NAME) with pd.drop()
*Identify any columns that have more than 10 unique values for potential binning with value_counts()
*Bin all application types with less than 500 applications into an “Other” category  
*Bin all classification types with less than 800 applications into an “Other” category 
![](Images/classification_forloop.png) 
*Convert all categorical data into numeric values with pd.get_dummies 
*Separate target variable (“IS_SUCCESSFUL”) from other features 
*Split the data data into training and testing sets with test_train_split 
*Scale the data with StandardScaler 


Step Two: Complete, Train, and Evaluate the Model 
1. Define the model with tf.keras.model. 
2. Choose the amount of hidden layers and activation nodes per level; determine activation function per level 
![](Images/Initial_build.png) 
3. Compile and train the model 
4. Evaluate the model
![](Images/compile_train.png) 
Initial Accuracy: 72.83% 
![](Images/initial_model_accuracy) 

Step Three: Optimize the Model 
1. Increase the number of activation nodes from 90 to 100 in the first hidden layer 
2. Increase the number of activation nodes from 25 to 30 in the second hidden layer 
3. Evaluate the model 
         Optimization 1 Accuracy: 73.11% 
4. Change the initial activation function to LeakyReLu and add a third hidden layer; increase epochs from 50 to 75 
5. Evaluate the model: 
        Optimization 2 Accuracy: 72.71 %

Reccomendation: Optimization 1 is the preferred model; though it does not reach the target accuracy of 75%, it achieved the best accuracy level while mainting a light processing load. 




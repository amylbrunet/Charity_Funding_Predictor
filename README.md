# Charity_Funding_Predictor

## Overview
The purpose of this analysis is to create an algorithm for the non-profit foundation, Alphabet Soup, to predict whether or not applicants for funding will be successful. The foundation provided a dataset of more than 34,000 organizations that have received funding over the years to allow capturing of metadata to perform the predictive analysis. Using machine learning and neural networks, features in the dataset were used to create a binary classifier that is capable of predicting whether applicants will be successful if funded by the foundation.

## Results
* Data Preprocessing

  * Target variable: IS_SUCCESSFUL
  
  * Feature variables: APPLICATION_TYPE, AFFLIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMOUNT, SPECIAL_CONSIDERATIONS, ASK_AMT
  
  * Removed variables: in 1st attempt, the EIN and NAME columns were removed because they were not necessary identifiers for the analysis. In 2nd and 3rd attempts to optimize, only the EIN column was removed to allow NAME to be included as a feature variable in an attempt to improve accuracy of the model.

* Compiling, Training, and Evaluating the Model

  * In the initial training of the model, I included 2 hidden layers, the first with 80 neurons, and the second with 30. I chose to start with 2 hidden layers to allow for processing of the complex data but to keep computation time low. I used the “relu” activation for the first and second layers, and for the output layer I used the “sigmoid” activation. Relu was used for first two layers because it is a simple acitivation function but is good for performance, and sigmoid was used for output because it provides a probability output value between 0 and 1 for the IS_SUCCESSFUL column.

![image](https://user-images.githubusercontent.com/89691802/154480659-f0fbff2f-adca-4a12-9b4a-59dcba76cd1d.png)


  * In my first attempt, I was not able to achieve target performance. The accuracy of my initial model was 72%, and the target was 75%.

![image](https://user-images.githubusercontent.com/89691802/154480758-71a233f5-34b4-4f28-893d-688fddc7de8a.png)


  * In my following attempts, I was able to achieve target performance. My final attempt at optimization is listed below. It took me three attempts to optimize performance. In my first attempt, I went back to preprocessing and decided to keep the NAME column as a feature variable. I created bins for names that had value counts under 200. Doing this increased target performance to 74%. I then went back and changed the cutoff value of the name value counts to under 100, and this did not change the target performance, keeping it as 74%. Finally, I kept the cutoff value for the name column at under 100 and then I added a third hidden layer of 10 neurons and an activation of ‘relu’, and this increased by target performance to 75%.

![image](https://user-images.githubusercontent.com/89691802/154480855-f89d632c-3c25-44e2-851b-ce738407949d.png)


## Summary
In conclusion, this predictive analysis was successful at reaching a target of 75% accuracy using machine learning and neural networks. Although optimization attempts of this model were successful at increasing accuracy, additional optimization models could be used to further improve performance. Instead of using neural networks, a Random Forest Classifier could be used because it is optimal for binary classification models. Random Forest has faster performance than neural networks and the problem of overfitting can be avoided. 

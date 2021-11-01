# Neural_Network_Charity_Analysis

## Overview of the analysis
To create a binary classifier DeepLearning Neural Network Model that is capable of predicting whether applicants will be successful if funded by Alphabet Soup, goal to have a model with a 75% or better accuracy score.

### Results
- Data Preprocessing
  - Variable considered the target in model: "IS_SUCCESFUL", as the goal is to predict based on features if funding was used effectively which is categorized under the column IS_SUCCESSFUL
  - Variables considered to be the features in the model: APPLICATION_TYPE AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT were all used as features. 
  - Variables neither targets nor features, and removed from the input: "EID" & "NAME" are not features as they are both identification columns. However, in the 3rd optimization model ran, I pulled "STATUS" out from being a feature, as without know more than was explained on this dataset, I do not see how the active or in-active status of funding would matter in predicting success. 
- Compiling, Training, and Evaluating the Model
  - Neurons, layers, and activation functions used in neural network model, and why:
    - The initial model - followed given params first dense layer had 80 neurons and second had 30 both used 'relu', output layer had 1. Model results in following image.
    
    ![image](https://github.com/trosie3/Neural_Network_Charity_Analysis/blob/main/Resources/images/origmodel.png)
    - The first optimization model - I increased the neurons from 80 to 85 and from 30 to 50, left functions the same. Thought process here was perhaps a few more neurons could bump the model to higher accuracy as the initial model’s accuracy was already near 73%. Model results in following image.
    
    ![image](https://github.com/trosie3/Neural_Network_Charity_Analysis/blob/main/Resources/images/optmodel1.png)
    - The second optimization model - I added two additional hidden layers both with 30 neurons and tried running 10 more epochs, and with all hidden layers kept 'relu'. Thought process here was perhaps more hidden layers were needed and just a few more epochs since the previous model barely increased in accuracy from the original. However this model barely preformed better than the original and not as well as the first optimization model. Model results in following image.
    
    ![image](https://github.com/trosie3/Neural_Network_Charity_Analysis/blob/main/Resources/images/optmodel2.png)
    - The third optimization model - I kept the second model params but changed the input data thinking better data and more layers would be the key. In this model I removed the "STATUS" feature, as it was the only data I felt confident enough to remove as I could not think of a correlation of active vs inactive that might matter on the success of the funding given. There may have been more 'noisy data' to drop here but given the definitions I had on the columns I could not be sure what might be redundant or unneeded data. This did produce the model with the highest accuracy score. Model results in following image.
    
    ![image](https://github.com/trosie3/Neural_Network_Charity_Analysis/blob/main/Resources/images/optmodel3.png)
  
  - Target model performance: I was not able to achieve the 75% accuracy score with any of the models and adjustments I made. My final model got closest with a 73.1% accuracy but even that was only a marginal increase from the original model.
  - Steps to try and increase model performance: I attempted slight tweaks in each model ranging from adding neaurons and layers to adjusting input data, as noted in more detail above in each model's description.

## Summary: 
Overall there were slight improvements in each model either in accuracy, reduction of loss or both. The first optimization model had the lowest loss of all models, the third optimization model had the best accuracy of all the models, the second optimization model had slightly better accuracy than the original model but has a higher loss matrix. If aiming for least lost, and higher accuracy the first optimization model is probably the best to go with. 

Given the 75% accuracy goal was not met further analysis and model testing should be done. Perhaps, using the first optimization model with the tweaked data used in the third model would lead to better accuracy and loss scores. Knowing more about the data would also make it easier to know what data was 'noisy' but the vague definitions given made that hard to access. 

Another way to imporve accuracy would be to try a completely different machine learning model. Given the data as it is, and the aim of a binary prediction result either a RandomForests, or SVM model might be a better to use on this data as both tend to have higher accuracy than the nerual network models used, and both are slightly more interpretable.


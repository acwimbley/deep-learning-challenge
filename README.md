# deep-learning-challenge

The notebooks were copied directly from colab into the github repository. There were 4 notebooks total, the original and 3 additional for each change in the model.  Below is the analysis.


Challenge 21 - Analysis
Overview of the analysis: 
The purpose of this project was to create a model for Alphabet Soup to use to select applicants who will have over a 75% success rate if they were funded.
Results
Data Preprocessing
•	What variable(s) are the target(s) for your model?
o	The target variable in this model is the column “Is Successful”
•	What variable(s) are the features for your model?
o	The featured variables include the columns: Application_Type, Affiliation, Classification, Use_Case, Organization, Status, Income_Amount, Special_Considerations, and Ask_Amount
•	What variable(s) should be removed from the input data because they are neither targets nor features?
o	The columns removed because they were unnecessary were the EIN and NAME 
Additional steps taken in the preprocessing of the data included determining the unique values of the feature columns. Those with more than 10 unique values were then considered for creating bins and a cutoff value.  For Application type, the cutoff value was 500 and for Classification the cutoff was 1000.
The categorical data was then converted to numeric using the pd.get.dummies function.  As a result of this function, the total number of columns increased to 43.  For the final steps, the data was split into train and test data and then scaled. 
Compiling, Training, and Evaluating the Model
How many neurons, layers, and activation functions did you select for your neural network model, and why?
•	Several train and test sessions were executed on the Sequential model. The models were compiled, trained and summarized as follows:
•	Model 1 – AlphabetSoupCharity (Original)
o	Relu was used as the activation except for the output which was Sigmoid and 100 Epochs.  The shape of the layers were 80, 30, 1 respectively.
o	Train Accuracy = .7378 or 74% and the Test Accuracy = .7261 or 73%
•	Model 2 – AlphabetSoupCharity_Optimization
o	Tanh was the activation for the first and second layer as Sigmoid remained for the output.  This was the only change.
o	Train Accuracy = .7405or 74% and the Test Accuracy = .7280 or 73%
•	Model 3 – AlphabetSoupCharity_Optimization2
o	Added a third layer using Relu as the activation for all except the output which remained Sigmoid. The units for each layer were 80, 60, 40 and 1 respectively.  The epochs was increased to 120.
o	Train Accuracy = .7410 or 74% and the Test Accuracy = .7301 or 73%
•	Model 4 – AlphabetSoupCharity_Optimization3
o	Relu and Tanh were used as the activation respectively for the first and second layer as Sigmoid remained for the output.  The epoch was changed to 50
o	Train Accuracy = .7375 or 74% and the Test Accuracy = .7289 or 73%

•	Were you able to achieve the target model’s performance?
o	 I was striving for an accuracy rate in the test data of 75% or above.  I was not able to achieve that.
•	What steps did you take in your attempts to increase model performance?
o	The changes I attempted were small changes to monitor the changes except for the last model in which I increased the number of layers by 1 and increased the epochs to 120
3.	Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.
•	There was a slightly better performance in the AlphabetSoupCharity_Optimization2 model in which I added a third layer, adjusted the units and increased the epochs.  
•	This model seems to be on the right track on probably reaching the desired level of accuracy.
•	Further training and testing is necessary to make a recommendation of a better model.

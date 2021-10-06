# deep_learning_challenge
deep_learning_challenge homework
1. Overview of the analysis: Explain the purpose of this analysis.

The purpose of this analysis is to create and run deep learning algorithm to predict whether applicants for funding will be successful or not. The analysis is based on the dataset of Alphabet Soup, containing data for more than 34000 organizations. 

2. Results: Using bulleted lists and images to support your answers, address the following questions.

    2.1 Data Preprocessing

- Model target: the data on whether the funding had been successful or not was considered as a target for the model
- Features: the following columns were identified as features of the model: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT
- Columns EIN and Name were considered irrelevant for the model and therefore were removed form the initial dataset. 

Furthermore, to optimize the model, the features that have had more than 10 unique values (e.g. Classification and Application Type)  were further analysed and smaller values were grouped/binned.

Text values were also transformed into numerical values using dummies. The model was then split into test and training sets and scaled. 

2.2 Compiling, Training, and Evaluating the Model

- How many neurons, layers, and activation functions did you select for your neural network model, and why?
An initial model was run with 100 epochs and included 2 hidden layers:
        * 1st hidden layer with 4 neurons and
        * 2nd hidden layer with 2 neurons. 
- Were you able to achieve the target model performance?
The test model accuracy was 0.72 while the training accuracy was 0.73, which was slightly less than the target of 0.75

- What steps did you take to try and increase model performance?
to improve the performance of the model the following changes were made:
       * in the 1st Attempt: I increased the No of neurons in layer 1 from 4 to 6, and in layer 2 from 2 to 4. Hidden layer function  = relu. This did not improve the performance of the model and the test accuracy was 0.724
       * in the 2nd Attempt: I kept the same number of neurons as in the 1st attempt  in layer 1 and 2,  plus I added a 3rd layer with 2 neurons. Hidden layer function  = relu. This did not improve the test accuracy (0.726);
       * in the 3rd attempt: I configured layer 1 = 70 neurons, layer 2 = 30 neurons, and increased epochs from 100 to 200 , Hidden layer function  = relu. The test accuracy remained at the level of 0.724
       * 4th attempt - changed function to Tanh, keep layer 1 = 4 neurons, and in layer 2 = 2 neurons, 100 epochs. test accuracy remained the same.

3. Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

Overall the model produced good results when comparing test and training accuracy score: there is a little difference between the two. However It did not manage to achieve the desired target of accuracy = 0.75, even after adjusting the number of layers, neurons and epochs. this  suggests that other optimization approaches may be considered. For example determining and dropping some of the less relevant features from the model could produce a better performance. 

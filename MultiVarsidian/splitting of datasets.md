## Splitting of Satadets

#### Problem Motivation and Assumptions

Why do we need to split the dataset into training, test and validation? In a single setence, it is to solve the model structure selection problem and estimate the performance of the estimator in real life. Selecting model structure is a critical and fundamental problem in data analysis. So far we have assumed that the model structure is known and we are finding parameters for it. Now we also need to find which model structure most faithfully models the observation which is the dataset. So, the workflow follows roughly this structure

1. Determine a model structure 
2. Estimate parameters
3. Estimate the performance in real life

For each of these tasks we will need to split the dataset somehow. We will need a training set for estimating parameters and a test set to estimate the performance in real life. Further we will need a split which is for choosing the model structure. This is usually done in the training set by splitting it into one more set called validation. In practice this is done through [[cross validation]].

#### How to do this in practice
Choosing the correct split is subtle and important. There is room for error, and the results will vary drastically depending on how one splits. At any rate, we shall leave the test set as "witheld data". This is data that the estimator will not see before we have a structure and a set of parameters and want to estimate how they perform in the real world. 

**Splitting according to application:**
In general there is the consideration of what we need our model to do. If the goal will be to forecast temporal signals, that is a model which generalizes on unseen domain for the data, we will have to leave out some big part of the data at some point. This will ensure that the PI in real life is tested on extrapolation, which is what the model will do. Otherwise if we are estimating the features of a mountain or processing some image/audio data for the purpose of making a model which handles this data to achieve some processing results, we might consider the "every 3rd sample" strategy.

![[multivar_test_train_1.png]]

![[multivar_test_train_2.png]]

**Splitting of temporal/dynamic data:**
When estimating in connection to dynamical systems and system identification, we have to consider that the training set needs to a) cover well all the operating areas in parameter space which the system is expected to work at while b) not choose the same areas as for testing since then we will be overfitting our PI to similar operating ranges as the test. Consideration a) ensures that many possible input-output relations are seen and thus we have good grounds in the training set to determine both model structure (through further split into validation or CV) and parameters while consideration b) ensures that the test set provides a meaningful test for our estimated model.

![[multivar_train_test_dynamical.png]]

#### Properties of good set splits
In general also the test, train, validation sets should have the following properties:

1) Independent of each other (consideration b) in the paragraph on dynamical systems)
2) Follow similar probability distributions. This connects to the concepts of [[ergodicity]], [[heteroschedasticity]] and [[stationarity]]

 

# Indian_Premier_League_Predictions
Predicting the winner for Indian Premier League (IPL) Competition and Matches based on Historical Data

## Instructions
The codes are under src folder. Exploration.ipynb and Exploration_2.ipynb provides exploration of the data. Winner_Prediction.ipynb and Winner_Prediction.py corresponds to the execution code. 

## Objectives
Originally the problem was listed on Kaggle with objective only one objective (#1 listed below). However, we extended the problem to the following multiple objectives: 
    1. Predict winner of any given match (of any season) even before the match has started.
    2. Predict the winner of any given match when the first inning is finished and before the start of the second inning
    3. Predict who will win the 9th season final before the match has begun
    4. Predict who will win the 9th season final before the match has begun
    5. Predict the winner of the finals of 9th season based on over-by-over (i.e. at any given state of the match)
    
## Approaches

Problem 1: Predict winner of any given match before the match has started
Obtained the match and team level features such as season, city, date, team names, toss winner, etc. While the label is the winner of the match. Portion of the data is used to predict the winenr of the matches in test data.

Problem 2: Predict the winner of any given match when the first inning is finished
Obtained match, team level and between match features such as runs scored by the first team and the wickets taken by the second team. The label is the same: winning team

Problem 3: Predict who will win the 9th season final before the match has begun
Same as Problem 1, however entire dataset has been used to predict the winner of the final match of last season.

Problem 4: Predict who will win the 9th season final before the match has begun
Same as Problem 2, however entire dataset has been used to predict the winner of the final match of last season.

Problem 5: Predict the winner of the finals of 9th season based on over-by-over
Probability of winning the match is obtained over-by-over by providing match and team level information along with match progress over-by-over by adding features like: runs and wickets scored per over, inning wickets and scores, etc. and other match level features like: runs scored in the last over, wickets taken the last over, target, remaining target, run-rate, required run-rate, difference between run-rate and required run-rate, etc. The target label is 1 for the team which won and 0 for the team which lost. All of these features are used to predict the probability of winning the match, i.e. class label=0. The data for all the matches has been used to predict the winner of the last season's finals over-by-over. 

## Results

### Problem 1 

Name: Gradient Boosting
Accuracy score:  0.655172413793
Name: Naive Bayes
Accuracy score:  0.0689655172414
Name: SVM
Accuracy score:  0.344827586207
Name: Logistic Regression
Accuracy score:  0.655172413793
Name: Nearest Neighbors using Centroid
Accuracy score:  0.51724137931
Name: K-nearest Neighbors
Accuracy score:  0.48275862069
Name: Ensemble
Accuracy score:  0.51724137931


Overall Accuracy of prediction before match: 
0.655172413793
Overall, Gradient Boosting using XGB gives the best performance.

### Problem 2
Accuracy of prediction post first innings: 
0.620689655172

### Problem 3
Accuracy = 0, i.e. model predicted the loosing team as the winner before the match

### Problem 4
Accuracy = 1, i.e model correctly predicted the winner after the first inning for the same setup as #3

### Problem 5
Probability of any finalist team winning the match is predicted over-by-over. The model is able to capture the winning/loosing probability when wickets are lost, or high runs are scored in an over, i.e model is able to capture all the local intricacies of the match based on the performance of a team. Overall, the model did well and predicted the correct winner.

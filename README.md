![image](https://github.com/user-attachments/assets/362f9f1c-c5f7-4cbc-9416-e2cf087f7cde)
# Statistical Anaylsis in Chess
This repository goes over a variaty of statistical methods to gain a deeper understanding of Chess

# Overview
- *Statistical Goals*: With predictive modeling not being the main goal of my project, I had 3 goals that I would be trying to complete. The goals were:
  - Determine how accurate the elo rating is for chess
  - Determine the significance to playing white vs black
  - Find the probabilty of winning based off the differnce in elo rating
  
There are many statistical methods that can be used, in this project, I used Logistic Regression, and One-sample t-test. For the first goal, we had a coefficient of 0.00455(for every point increase in the elo gap, the odds of winning increase by this amount) with an AUCof .693, so the elo gap is better than guessing. For determinig the signigicane of white vs black using the t-test, we got a p-value of 0.97941 at a 95% confidence interval. 
- *Predictive Goals*: The goal was to predict the amount of elo a person would win or lose each game. The data was seperated to show a differnce between white and black players and Gradient Boosting was the model of choice. The model was able to accuratly predict the amount a Elo Differnce of a player 68.4% of the time. The probabilty of winning based off the differnce in elo rating suprisingly varied widely.

# Summary 

- ## Data
  -Csv file that consists of chess games and features. Some features include:
    -Event type, Results, EloRatings, as well as white and black players
  - File consists of 6,256,184 rows and 15 columns
  - Used an 80-20 split between training and testing
    
- ## Preprocessing
  - There was a small proportion of null values, this resulted in the easy removal of missing values.
  - Very small proportion of games lost due to abandonment and rule infractions, therefore they were removed.
  - Got rid of a list of unnecesarry columns such as PlayerName, ECO,and AN(All moveswithin given game).
  - Normalized necesarry columns to get ready for modeling.
 
- ## Visualization
This is a histogram showing the distribution of the elo among white players, it's important to look at graphs like these to get a better understanding of the data. For example, this graphs shows the distribution is normal for the elo ratings of those who play white.
  ![image](https://github.com/user-attachments/assets/6777e149-5764-47ec-be94-1f3ea7f76712)

When looking for important features, I used this graph to determine that seperating between white and black players could be an important item to look at
  ![image](https://github.com/user-attachments/assets/3270a8bd-e09a-4cbb-98a6-0aee31396ccc)

Trying to get some final understanding, this graph gave some insight on the probability of winning based on differnce in elo.
![image](https://github.com/user-attachments/assets/9623104c-9eba-441f-a829-09cca02f43fa)
This graph is interesting, most of it makes sense, but on the far right things get funky. This can most likely be explained by those who cheat, or smurf(really good players that play at an elo rating much lower than their true skill), causing the sudden drop.

## Problem Formulation
- With different goals, I had different inputs and outputs, however, in general, the elo of each player, event type, results, and cause of termination, was used to get results. Linear regression was used test the predictive power of elo, as well as to find the odds of winning based off the Elogap between players, seperated into white and black. The one sample t-test was used to see if playing white or black had a significant difference. In regards to predictive modeling, linear regression was used as a baseline,and XGBoost and Gradient Boosting was used due to the potential complexity of the prediction. Originally, only 100,000 rows were used to create the model. With this, hypertuning was used. Hypertuning with XGboost seemed to produce worse and worse results, likely due to the complexity of the model. However, gradient boosting proved to be a bit better after some tuning. 
  
## Training
-Software: Juypter Notebook

## Perfomance

## Conclusions

## Future Plans

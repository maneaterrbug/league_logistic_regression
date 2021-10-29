# Predicting the Win
Matt Ryan

## Abstract

Here we attempt to develop a model that can semi-accurately predict probability of a professional League of Legends e-sport team to win a game based on the a game's current state 15 minutes into the game. Ultimately, the hope here is that this tool can be used by the League of Legends broadcast team to enhance game discussion and viewer experience.

## Design

League of Legends is one of the most popular video games in the world, with a reported monthly active player-base of ~115 million players as of 2020 and a peak concurrent player-count in Sept. 2021 of over 2 million players. As an e-sport, League of Legends has shown immense growth over the past decade, with the 2020 League of Legends World Championship finals reaching a peak concurrent viewership of 49.5 million viewers. Therefore, with traditional sportscast level viewership, we want traditional sportscast level professionalism. To strengthen the analytics tools available to the casting team and enhance the overall viewing experience, we want to design an application to be referenced by e-sports casters during games that predicts the probability that a team will win a game based on the current in-game conditions.


## Data

The data used here was found on [Oracle's Elixir](https://oracleselixir.com/tools/downloads), and encompasses 11,604 professional games played in 2021. Because each game represents 12 data points (one for each team respectively, and one for each of the 5 players on each team), totaling 138,528 data points. The set also encompassed 122 features. 

## Algorithms

*EDA*

First, in order to for the data to reflect solely the winning and losing teams' performances per game, we aggregated individual player KDA records and assigned them to 5 new fields per team. Then, because many of the features available to us report statistics only available at the end of a game, they are not of much use to us. Therefore, we selected for a handful features that report on performance at 15 minutes into a game, including a field (csat15mins) that was calculated using linear regression.

*Modeling*

We used SKlearn.LogisticRegression() trained using a train-test split of 80-20. Of our 80% training set, we performed grid cross-validation among 10 subsets and with a grid composed of C (model complexity) values ranging from 1 to 100. Ultimately, it was determined by comparing F1 scores that the model performed the  strongest with a C-value of 16, receiving an F1 score of 0.76. Finally, with our hyperparameters tuned, we trained the model on the train set.

*Assessing Results*

Our model, when applied to the test set, ultimately predicted values with an accuracy score of 0.756 (using sklearn.metrics.accuracy_score). We assessed many different scores:
* Accuracy score = 0.756
* F1 Score = 0.759
* Precision = 0.761
* Recall = 0.753



## Tools
- Excel for initial evaluation of csv file
- Pandas and numpy for processing and manipulation of data
- SKLearn for modeling and model assessment
- matplotlib and Seaborn for visualization


## Communication

We are confident this model can be use on professional e-sports broadcasts to enhance the caster analysis and level of discussion. With our level of accuracy, we feel the probability predictions are accurate enough to carry weight when referenced, but still inaccurate enough to allow for open discussion/interpretation of predictions on the broadcast. Going forward, we believe this model can be enhanced to allow for predictions of gamestates earlier in the game. In addition, there is potential to apply the model to the entire playerbase and use insights to inform the developers' game balance decisions.

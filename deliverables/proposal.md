* With the League of Legends World 2021 Championship already underway, we are looking to answer the question: can we use past regional league and World's game performances of professional League e-sports teams **and** their players/roles to predict the probability of a team winning a game based on the current game-state?
	* Because we are simply wishing to predict the probability of a team winning a game based on its current game-state, we believe using logistic regression to be a good approach
* Esports fans and analysts can benefit from this modelling in that it can give them more information with which to make predictions
	* Potentially Riot (developer of League of Legends) broadcast team have contracted me to be able to have some analytics to reference during live casting of pro games
	* This modelling could also be beneficial to the Riot balance team; they could use insights derived from the modelling to inform balance decisions going forward (ie some feature is too impactful or not impactful enough and should be balanced accordingly).

### Data Descriptions:

* I will be using the Match Data datasets by year as found on [Oracle's Elixir](https://oracleselixir.com/tools/downloads)
	* the main focus for this project will be examining the 2021 Match Data csv file, though it might be interesting to compare modeling results from 2021 data against the 2020 dataset to see if time (or "meta") plays a role at all
* An individual sample unit would be a game from one team's perspective, with associated features being the performances of the individual players of the team, the numbers/times of objectives on the map taken, the amount of gold each team has, etc.

* the target variable will be the game result, which is in the form of either a 1 or 0 with 1 denoting a win and 0 denoting a loss, and we will attempt predict a probability as opposed to a "hard" value of win or loss

### Tools

* numpy and Pandas for data processing and manipulation
* seaborn and matplotlib for visualization
* sklearn for modelling and model evaluation
* SQLite for storing and high-level exploration of data

### MVP Goal

* the goal minimum viable product would be an initial logistic regression model and a brief evaluation of its performance on the test set

![](../resources/worlds2019.png)




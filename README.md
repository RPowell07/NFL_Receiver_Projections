# Projecting NFL Receiving Stats for Upcoming Season
Capstone Project for General Assembly Data Science Immersive Course; Rick Powell

## Project Statement:
Create models to predict Yardage, Receptions, and Touchdowns for NFL Wide Receivers, Runningbacks and Tight Ends, which can be used by Fantasy Football GMs to make educated roster decisions.

## Background
Every year, 32 NFL teams compete over 17 games and post-season in the hopes of winning the Super Bowl. In addition to watching football,  millions of people now play Fantasy Football each year, constructing rosters of NFL players to compete for their own league titles.

Projecting NFL players statistics can be used in many different situations, whether it's trying to predict a contract for a free agent player, or in the case of this project, can be used to determine which player to draft in fantasy football. Being able to make accurate predictions will help make an informed decision and improve outcomes, whether that's not overpaying or underpaying for a player, or winning a fantasy football draft.

This project aims to create models to predict passing yards, receptions and touchdowns for all passcatching positions (wide receiver, tight end, and runningback) for the upcoming 2022 NFL season.


### Libraries Used
All data cleaning and modeling was run in Python using the following libraries:
Pandas, numpy, scikit learn, matplotlib, seaborn


## Notebooks
* [`01_draft_results.ipynb`](./code/01_draft_results.ipynb): Notebook combining all draft datasets between 2001 and 2022.
* [`02_debut_year.ipynb`](./code/02_debut_year.ipynb): Notebook combining all debut datasets between 2001 and 2021.
* [`03_rookies.ipynb`](./code/03_rookies.ipynb): Notebook combining rookie statistics between 2018 and 2021.
* [`04_receiving_stats.ipynb`](./code/04_receiving_stats.ipynb): Notebook to merge and clean data for data analysis and modeling.
* [`05_data_analysis.ipynb`](./code/05_data_analysis.ipynb): Notebook for exploratory data analysis, images.
* [`06_modeling_yards.ipynb`](./code/06_modeling_yards.ipynb): Notebook to build a model to predict yards.
* [`07_modeling_receptions.ipynb`](./code/07_modeling_receptions.ipynb): Notebook to build a model to predict receptions.
* [`08_modeling_TDs.ipynb`](./code/08_modeling_TDs.ipynb): Notebook to build a model to predict touchdowns.
* [`09_predictions.ipynb`](./code/09_predictions.ipynb): Notebook to run our models to make predictions for the 2022 season.


## Data 
Data was pulled from Pro-Football Reference ([source](https://www.pro-football-reference.com/)).
* [`2018-2021_receiving.csv`](./data/2018-2021_receiving.csv): Dataset of Wide Receivers, Tight Ends and Running Backs who caught passes between 2018 and 2021.
* [`draft_final.csv`](./data/draft_final.csv): Dataset of all players who were drafted between 2001 and 2022.
* [`debut_final.csv`](./data/debut_final.csv): Dataset of all players who began their careers between 2001 and 2021.
* [`rookie_stats.csv`](./data/rookie_stats.csv): Dataset of average statistics for rookies based on position and round drafted.
* [`receiving_train.csv`](./data/receiving_train.csv): Dataset of players from 2018 through 2020 to train our model.
* [`receiving_test.csv`](./data/receiving_test.csv): Dataset of players from 2021 to test our model.


## Data Dictionary

| Feature | Type  | Description |
|------|------|--------|
| Tm | categorical | What team a player played for that season |
| Age | int | Age of the player during that season |
| G | int | Games played by a player during a specific season |
| GS | int | Games started by a player during a specific season |
| Tgt | int | Number of times a player was targeted on a passing play |
| Rec | int | Number of times a player caught a pass |
| Yds | float | Receiving yards for a player during a specific season |
| TD | int | Touchdowns scored by a player during a specific season |
| 1D | int | First Downs earned by a player during a specfic season |
| YBC | float | Yards gained before a player catches a pass |
| YBC/R | float | Average Yards gained before a player catches a pass per every pass caught |
| YAC | float | Yards gained before a player catches a pass |
| YAC/R | float | Average Yards gained after a player catches a pass per every pass caught |
| ADOT | float | Average Depth of Target when a player is thrown the ball |
| BrkTkl | int | Number of times a player broke a tackle |
| Rec/Br | float | Number of receptions for every broken tackle |
| Drop | int | Number of times a player dropped a catchable pass |
| Drop% | float | Percent of total targets that were dropped by a player |
| Int | int | Passes intercepted by the other team intended for the player |
| Rat | float | Passer Rating of Quarterbacks when targeting a player |
| ProBowl | categorical | Player was voted to attend the Pro-Bowl |
| AllPro | categorical | Player was voted to 1st team All-Pro |
| Year | categorical | Specific season the stats were pulled for |
| Rnd | categorical | What round a player was drafted in (Undrafted = 8) |
| Pick | categorical | What pick a player was drafted (Undrafted = 260) |
| Pos | categorical | What postion a player plays (WR, TE, RB) |
| YrsPlayed | int | Number of years between when a player was drafted and current year |
| X_-1_year | n/a | The listed stat above (represented by X) for the previous year |
| X_-2_year | n/a | The listed stat above (represented by X) for two years prior |
| X_target | n/a | The listed stat above (represented by X) from the following year, used for modeling |


## Conclusions

I created 3 individual models: one for yardage, one for receptions, and one for touchdowns. Using these models, I am able to build out player projections for the upcoming season. 

For my final Yardage model, I used the Linear Regression Model. On our training set, the model had a training score of .579, and a testing score of .533. I chose this model because it was not as overfit as many of our other models, but it also gave us a decent testing score compared to many of our other models. 

I also used a Linear Regression Model for the final Receptions model. On our training set, we had a training score of .542, and a testing score of .474, I chose this model because it had a relatively high testing score, but also did not appear too overfit.

Finally, for my final Touchdown model, I used the Stacking Model that combined RandomForest, GradientBoost, AdaBoost, and Lasso models and then fed those results into a Linear Regression model. On our training set, we had a training score of .332, and a testing score of .314. I chose this model because all of our touchdown models had relatively low testing scores, but this model did not appear to be overfit and was around the same level of scores as the rest of the models. 

Overall, my testing scores weren't too high, but it makes some sense. Due to the time restraints of the project, there are a number of factors I had to cut that could vastly improve my model. I believe Quarterback play would have a large impact on passing statistics, as that influences who gets targeted, and the quality of the pass. Which defenses a player plays against over the course of a season, not all teams play each other and therefore some schedules are easier than other. Also, I'd want to look at college stats to better predict rookie stats that I filled in based on draft round and position.

Finally, I wanted to include my top 5 receivers for the upcoming 2022 season. The full list of predictions will be in the data folder listed as `predictions.csv`.

My Top 5 Receivers for 2022 (sorted by receptions)

|Player | Receptions |Yards |Touchdowns |	
|------|------|--------|--------|
|Cooper Kupp	|116.0	|1365.0	|9.0|
|Davante Adams	|107.0	|1240.0	|8.0|
|Justin Jefferson	|100.0	|1359.0	|8.0|
|Stefon Diggs	|85.0	|1089.0	|7.0|
|Chris Godwin	|84.0	|972.0	|5.0|

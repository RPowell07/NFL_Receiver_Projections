# Projecting NFL Receiver Stats for Upcoming Season
Capstone Project for General Assembly Data Science Immersive Course

## Project Statement:
Create a model to predict Receptions, Yardage, and Touchdowns for Wide Receivers, Runningbacks and Tight Ends, which can be used by both NFL GMs or Fantasy Football GMs to make roster decisions.

## Background
Projecting players statistics can be used in many different situations, whether it's trying to predict a contract for a free agent player, to trying to determine which player to draft in fantasy football. Being able to make accurate predictions will help make an informed decision improve outcomes, whether that's not overpaying or underpaying for a player, or winning a fantasy football draft.

This project aims to create a model for predicting passing yards, receptions and touchdowns for all passcatching positions (wide receiver, tight end, and runningback).


## Notebooks
* [`draft_year.ipynb`](./code/draft_year.ipynb): Notebook combining all draft datasets between 2001 and 2022.
* [`debut_year.ipynb`](./code/debut_year.ipynb): Notebook combining all debut datasets between 2001 and 2021.
* [`rookies.ipynb`](./code/rookies.ipynb): Notebook combining rookie statistics between 2018 and 2021.
* [`receiving_stats.ipynb`](./code/receiving_stats.ipynb): Notebook to merge and clean data for data analysis and modeling.
* [`data_analysis.ipynb`](./code/data_analysis.ipynb): Notebook for exploratory data analysis, images.
* [`modeling_yards.ipynb`](./code/modeling_yards.ipynb): Notebook to build a model to predict yards.
* [`modeling_TDs.ipynb`](./code/modeling_TDs.ipynb): Notebook to build a model to predict touchdowns.
* [`modeling_receptions.ipynb`](./code/modeling_receptions.ipynb): Notebook to build a model to predict receptions.
* [`predictions.ipynb`](./code/predictions.ipynb): Notebook to run our models to make predictions for the 2022 season.


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


### Libraries Used
Pandas, numpy, sci-kit learn, seaborn, matplotlib

## Conclusions



Additional pieces that would improve my model:
Quarterback play. Heavily impacts players who have to catch their passes.
Defenses, every year, teams play new teams
Looking at college stats to predict rookie stats
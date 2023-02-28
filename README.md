# dk_dff_rosterizer
DraftKings DFF Roster Optimizer

The capability to model future individual player performance and optimize the overall expected points total of a composed Daily Fantasy Football roster is integral to a DFF Manager’s success. While several commercial products and Daily Fantasy Game Websites themselves offer suggested lineups to “optimize” a Manager’s roster, it is unknown whether the supplied data is skewed in favor of the gaming host. DK DFF Rosterizer is an automated roster optimizer using Ridge-Regression analysis and Integer Programming Optimization as an alternative to the projections supplied by DraftKings.

Install the required modules and run from any location to generate an optimized roster for DFF in 2020

- A video detailing our idea, methods and findings:<br>
<a href="http://www.youtube.com/watch?feature=player_embedded&v=zoqKWcT-wMo" 
   target="_blank"><img src="https://img.youtube.com/vi/zoqKWcT-wMo/0.jpg" 
alt="Presentation" width="240" height="180" border="10" /></a>

- The slidedeck in the video can be found [here][1].

- A technical report based on our findings can be found [here][2].

## Goal
Major fantasy football platforms provide player point projections. One can optimize over these projections and get an ostensibly 'optimal' lineup. We sought out to also model player performances as well. We reason that past performances, in particular a player's most recent games, can be used to predict future performance.

## Data Collection
We scrape historical fantasy football player salaries from <footballdiehards.com>
Historical player statistics for the last 30 years are scraped from <stathead.com> and compiled into batches of weeks.

## Modeling
We'd like to avoid excessive weight given to recent performances so decided on a Ridge Regression model. We found in our model selection steps that it outperformed simple linear and LASSO models.

## Feature Creation
We compared different modeling approaches:
- Predicting fantasy points
- Predicting individual stats
- Incorporate player positions
- A rolling window: look at past 4-8 games to predict next game
We found that predicting stats, including positions and increasing the window size led to the best results.

## Integer Program & Optimization
Given salaries and projected performances, we can formulate an integer program with the necessary player and salary constraints.
We model outputs to optimize over the predicted player performances and with standard branch and bound methods can find an optimal solution.

## Evaluation
There are between 30-100 players available per position and on the order of 10^23 possible lineups. It is also difficult to predict performances and thus we recognize it is infeasible to find the global optimum.
Thus we seek to beat our benchmarks: commercial predictions from experts such as DraftKings and FantasyPros.

## Results
We compared the our model's optimal team against the optimal team based on DraftKings predictive performance models.
Across the 2020 NFL season through Week 14, we found that for a window size between 3-6 games our model beat DK ~75% of the time.
When using a 7 game window, for weeks 11-14, we outperformed DK each time.

## Improvements
In a future iteration we would seek to improve our feature engineering, model selection and game selection.
We would seek to incorporate opponent defense statistics, weather as well as a team's general offensive competence.
A ridge regression model is rather restrictive and so a neural network would likely constitute a better model.
We were focused on predicting pure fantasy points. However the model  may be altered to account for different competition formats such as 50/50 or GPP, a larger opponent pool or the payout where we may want to aim for a riskier but potentially higher performing team.


[1]: https://github.com/ssalim5/dk_dff_rosterizer/blob/master/Slideshow.pdf
[2]: https://github.com/ssalim5/dk_dff_rosterizer/blob/master/Technical%20Report.pdf

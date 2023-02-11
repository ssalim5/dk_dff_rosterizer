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

## Methodology
- Data Collection
We scrape historical fantasy football player salaries from <footballdiehards.com>
Historical player statistics for the last 30 years are scraped from <stathead.com> and compiled into batches of weeks.

-Modeling

-Optimization

-Evaluation

## Feature Creation

## Integer Program

## Results




[1]: https://github.com/ssalim5/dk_dff_rosterizer/blob/master/Slideshow.pdf
[2]: https://github.com/ssalim5/dk_dff_rosterizer/blob/master/Technical%20Report.pdf

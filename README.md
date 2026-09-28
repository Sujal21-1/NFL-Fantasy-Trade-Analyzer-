
# NFL Fantasy Football Trade Analyzer

A fantasy football trade analyzer that uses NFL player data to compare player value, recent performance, consistency, and upcoming matchups.

## Overview

This project builds a data-driven framework for evaluating fantasy football trades using NFL player statistics and schedule data from NFLverse.

The analyzer calculates a **Trade Value Score** based on:

* PPR points per game
* Recent performance
* Scoring consistency
* Upcoming matchup difficulty

Users can compare individual players or multiple players on each side of a proposed trade.

## Features

* Cleaned and analyzed NFL player statistics
* Aggregated weekly data into player-season metrics
* Calculated PPR production and usage metrics
* Measured recent player performance
* Evaluated weekly scoring consistency
* Calculated upcoming matchup scores
* Created a weighted Trade Value Score
* Built a trade evaluation function
* Created interactive Plotly visualizations

## Trade Value Score

The current scoring framework uses:

| Metric             | Weight |
| ------------------ | -----: |
| Production         |    45% |
| Recent Performance |    25% |
| Consistency        |    15% |
| Matchup            |    15% |

The score is designed as a transparent analytical framework rather than a guaranteed prediction of future fantasy performance.

## Visualizations

The notebook includes interactive visualizations for:

1. Top players by Trade Value Score
2. Season production vs. recent performance
3. Player-to-player trade comparisons

## Tech Stack

* **Python**
* **Pandas**
* **NumPy**
* **Plotly**
* **Scikit-learn**
* **NFLverse / nflreadpy**

## Data

NFL player statistics and schedule data are sourced from [NFLverse](https://github.com/nflverse) and accessed through `nflreadpy`.

## Project Structure

```text
nfl-fantasy-trade-analyzer/
│
├── NFL_Fantasy_Trade_Analyzer.ipynb
└── README.md
```

## Limitations

The current version uses analyst-defined scoring weights and does not directly account for factors such as injuries, depth-chart changes, league-specific settings, or player projections.

Future versions could incorporate these factors and validate the Trade Value Score against future fantasy performance.

## Conclusion

This project demonstrates how Python, data preparation, feature engineering, statistical analysis, and interactive visualization can be combined to build a practical fantasy football analytics tool.

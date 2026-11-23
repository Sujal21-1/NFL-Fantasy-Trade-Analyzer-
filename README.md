# NFL Fantasy Football Analytics & Trade Analyzer

A Python-based fantasy football analytics project that combines NFL player statistics, exploratory data analysis, machine learning, player valuation, and interactive trade evaluation to support PPR fantasy football decisions.

## Project Overview

This project uses historical NFL player data from NFLverse to analyze fantasy football performance and develop a data-driven player valuation and trade evaluation system.

The project follows an end-to-end analytics workflow, transforming raw weekly NFL statistics into player performance insights, machine learning predictions, and interactive fantasy football tools.

## Key Features

- **NFL Data Collection & Preparation:** Retrieved and cleaned weekly NFL player statistics using `nflreadpy`.
- **Exploratory Data Analysis:** Examined fantasy production, player consistency, workload, and efficiency across positions.
- **Feature Engineering:** Developed historical performance features, including previous-game PPR and rolling three-game averages.
- **Machine Learning:** Compared Linear Regression and Random Forest models against a previous-game baseline.
- **Player Projections:** Generated next-appearance PPR estimates using the selected machine learning model.
- **Player Valuation:** Created position-relative player rankings using projected production, historical performance, and consistency.
- **Interactive Plotly Visualizations:** Built interactive charts to explore player rankings, projections, and performance.
- **Trade Analyzer:** Evaluates multi-player trade packages using projected PPR, historical production, and scoring consistency.
- **Starting Lineup Impact:** Compares projected starting lineup performance before and after a proposed trade, accounting for roster composition, positional needs, and FLEX positions.

## Machine Learning Results

Three prediction approaches were evaluated using a chronological training and testing split.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Previous-Game Baseline | 5.807 | 8.209 | -0.003 |
| Linear Regression | **4.788** | **6.391** | **0.392** |
| Random Forest | 4.847 | 6.511 | 0.369 |

Linear Regression achieved the lowest Mean Absolute Error, reducing prediction error by approximately 17.6% compared with the previous-game baseline.

The model uses historical player performance features to estimate PPR points for a player's next recorded appearance.

## Player Valuation Methodology

Players are evaluated using three position-relative components:

- **Projected Performance (50%):** Predicted next-game PPR.
- **Historical Performance (30%):** Average historical PPR production.
- **Consistency (20%):** Week-to-week scoring consistency, with lower variability receiving a higher score.

The resulting Player Value Score is scaled from 0 to 100.

Scores are calculated relative to other players at the same position, rather than representing universal fantasy football market values.

## Interactive Dashboard

The project includes Plotly visualizations for exploring:

- Player valuation rankings by position.
- Historical average PPR versus projected PPR.
- Player performance comparisons.
- Position-level production and consistency.

## Trade Analyzer

The interactive trade analyzer supports multiple players on both sides of a proposed trade.

It evaluates:

- Total projected PPR gained or lost.
- Historical average PPR.
- Player scoring consistency.
- Position-by-position roster changes.
- Starting lineup performance before and after a trade.
- Positional needs and roster depth.

The analyzer provides a recommendation based primarily on the projected change in starting lineup PPR.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly
- Scikit-learn
- nflreadpy
- NFLverse
- Google Colab

## Data Sources

Historical NFL weekly player statistics were retrieved from NFLverse using the `nflreadpy` Python package.

The analysis covers the 2022–2026 seasons included in the dataset.

## Limitations

- Machine learning predictions are estimates and do not guarantee future fantasy performance.
- Predictions target a player's next recorded appearance, which may not correspond to the next calendar week.
- Injuries, depth-chart changes, and confirmed player availability are not directly incorporated into the model.
- Player valuation weights and trade recommendation thresholds are analyst-defined.
- Position-relative valuation scores should not be interpreted as direct comparisons of market value across positions.
- Starting lineup evaluations depend on user-provided roster and league lineup settings.

## Future Improvements

- Incorporate injury and depth-chart information.
- Add matchup-adjusted player projections.
- Expand league-specific roster and scoring configurations.
- Evaluate historical trade recommendations against actual future outcomes.
- Improve projections with additional usage and situational features.

## Conclusion

This project demonstrates how Python, data preparation, exploratory analysis, machine learning, and interactive visualization can be combined to build a practical sports analytics application.

By connecting player projections and historical performance to roster-level trade evaluation, the project turns NFL statistics into actionable fantasy football insights.


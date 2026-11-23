# NFL Fantasy Football Analytics & Trade Analyzer

A Python-based fantasy football analytics project that combines NFL player statistics, exploratory data analysis, machine learning, player valuation, and interactive trade evaluation to support PPR fantasy football decisions.

## Project Overview

This project uses historical NFL player statistics from NFLverse to analyze fantasy football performance and develop a data-driven player valuation and trade evaluation system.

The goal is to transform raw NFL statistics into meaningful insights that help evaluate player performance, project future production, and make better fantasy football trade decisions.

## Dashboard Preview

### Player Rankings by Position

Explore the top 10 players at each position using position-relative player valuation scores.

![Player Rankings by Position](Player%20rankings%20by%20position%20dashboard.png)

### NFL Fantasy Football Player Valuation Dashboard

An interactive dashboard featuring player rankings, historical versus projected PPR, average projected production, and weekly scoring consistency.

![Player Valuation Dashboard](Player%20valuation%20dashboard.png)

## Key Features

- **NFL Data Collection:** Retrieved weekly NFL player statistics using `nflreadpy`.
- **Data Cleaning:** Prepared player statistics across the 2022–2026 seasons.
- **Exploratory Data Analysis:** Analyzed fantasy production, player consistency, workload, and efficiency.
- **Feature Engineering:** Created previous-game performance and rolling three-game averages.
- **Machine Learning:** Compared Linear Regression and Random Forest against a previous-game baseline.
- **Player Projections:** Estimated PPR points for players' next recorded appearances.
- **Player Valuation:** Developed position-relative rankings using projected performance, historical production, and consistency.
- **Interactive Visualizations:** Built Plotly dashboards to explore player rankings and performance.
- **Trade Analyzer:** Evaluates multi-player trade packages using projected PPR, historical production, and consistency.
- **Starting Lineup Impact:** Compares projected lineup performance before and after a proposed trade, including positional needs and FLEX positions.

## Machine Learning Results

Three prediction approaches were evaluated using a chronological training and testing split.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Previous-Game Baseline | 5.807 | 8.209 | -0.003 |
| Linear Regression | **4.788** | **6.391** | **0.392** |
| Random Forest | 4.847 | 6.511 | 0.369 |

Linear Regression achieved the lowest Mean Absolute Error, reducing prediction error by approximately 17.6% compared with the previous-game baseline.

## Player Valuation Methodology

The Player Value Score combines three position-relative components:

- **Projected Performance (50%):** Predicted next-game PPR.
- **Historical Performance (30%):** Average historical PPR production.
- **Consistency (20%):** Week-to-week scoring consistency, rewarding lower scoring variability.

The resulting score is scaled from 0 to 100. Players are evaluated relative to others at the same position.

## Trade Analyzer

The interactive trade analyzer supports multiple players on both sides of a proposed trade.

It evaluates:

- Total projected PPR gained or lost.
- Historical average PPR.
- Player scoring consistency.
- Position-by-position roster changes.
- Starting lineup performance before and after a trade.
- Positional needs and roster composition.
- Multiple FLEX positions based on league lineup settings.

The analyzer provides a recommendation based primarily on the projected change in starting lineup PPR.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Plotly
- Matplotlib
- Seaborn
- nflreadpy
- NFLverse
- Google Colab

## Data Sources

Historical NFL weekly player statistics were retrieved from NFLverse using the `nflreadpy` Python package.

The analysis covers the 2022–2026 seasons included in the dataset.

## Limitations

- Machine learning predictions are estimates and do not guarantee future fantasy performance.
- Predictions target a player's next recorded appearance, which may not correspond to the next calendar week.
- Injuries, depth-chart changes, and confirmed player availability are not directly incorporated.
- Player valuation weights and trade recommendation thresholds are analyst-defined.
- Position-relative scores should not be interpreted as direct market values across positions.
- Starting lineup evaluations depend on user-provided roster and league lineup settings.

## Future Improvements

- Incorporate injury and depth-chart information.
- Add matchup-adjusted player projections.
- Expand league-specific roster configurations.
- Evaluate historical trade recommendations against actual future outcomes.
- Improve projections with additional usage and situational features.

## Conclusion

This project demonstrates how Python, data analytics, machine learning, and interactive visualization can be combined to build a practical sports analytics application.

By connecting player projections and historical performance to roster-level trade evaluation, the project transforms NFL statistics into actionable fantasy football insights.

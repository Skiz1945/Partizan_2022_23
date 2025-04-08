## Overview

What drives a team to greatness in Europe’s fiercest basketball league? This project unravels Partizan Mozzart Bet Belgrade’s 2022/23 EuroLeague season, transforming raw stats from `euroleague_box_score.csv`, filtered into `partizan_2022_raw.csv` and refined as `partizan_2022_cleaned.csv`, into a playbook of insights. Using multiple Jupyter notebooks, I combined data cleaning, validation, and cutting-edge analytics to decode player efficiency, team dynamics, and game-changing trends.

As a basketball enthusiast with a passion for data, I use Python to showcase players like Lessort and Leday, forecast scoring streaks, and analyze the effects of player absences. Whether you’re deeply rooted in the game, fascinated by data, or a bit of both, this analysis provides an in-depth look at Partizan’s statistics and offers insights into the future of sports analytics.

## Objectives

This analysis begins with Partizan-specific raw data (`partizan_2022_raw.csv`), extracted from the broader `euroleague_box_score.csv`, and advances through cleaning, validation, and sophisticated analytics to deliver actionable insights into player and team performance. Key objectives include:

- **Data Cleaning:** Transform raw Partizan data into a reliable, analysis-ready format (`partizan_2022_cleaned.csv`).
- **Data Validation:** Ensure the cleaned dataset’s consistency and accuracy.
- **Efficiency Metrics:** Assess player efficiency across multiple dimensions.
- **Plus/Minus Analysis:** Measure players’ on-court impact in regular season and playoffs.
- **Consistency Analysis:** Evaluate player reliability and scoring patterns.
- **Trend Analysis Over Time:** Monitor performance trends across regular season and playoff rounds.
- **Home vs. Away Performance:** Analyze home-court advantage effects on player and team stats.
- **Player Role Clustering:** Group players by style using K-Means clustering.
- **Predictive Modeling:** Forecast player performance with regression models.
- **Key Player Absences:** Examine impacts of top players’ absences on team dynamics.

The cleaned dataset (`partizan_2022_cleaned.csv`), stored alongside the notebooks, underpins all analyses, offering a multidimensional view of Partizan’s season for strategic insights, roster optimization, and coaching decisions.

## Project Structure

### Cleaning Data
- **File:** `2.cleaning_data.ipynb`
- **Description:** Cleans the raw dataset (`partizan_2022_raw.csv`) by handling missing values, standardizing formats, removing duplicates, and dropping irrelevant columns. Saves the cleaned data as `partizan_2022_cleaned.csv`.
- **Key Steps:** Converts `minutes` to `total_seconds`, standardizes player names (e.g., "LEDAY, ZACH" → "Leday Zach"), ensures data consistency, and exports the cleaned dataset.

### Data Validation
- **File:** `3.data_validation.ipynb`
- **Description:** Validates the cleaned dataset (`partizan_2022_cleaned.csv`) by checking consistency between player sums and team totals, verifying internal metrics, and confirming complex calculations like PIR.
- **Key Steps:** Compares points and assists, explains rebound/turnover discrepancies (e.g., 135 unassigned rebounds), validates field goals and PIR, and ensures per-game consistency.

### Efficiency Metrics
- **File:** `4.efficiency_metrics.ipynb`
- **Description:** Analyzes player performance using six efficiency metrics (TS%, PP32, AST/TO, USG%, PPP, REB%) to identify top performers and strategic insights.
- **Key Steps:** Calculates metrics like True Shooting (e.g., Lessort 0.721) and Usage Rate (e.g., Punter 13.64%), ranks players, and highlights key contributors like Lessort, Punter, and Exum.

### Plus/Minus Analysis
- **File:** `5.plus_minus.ipynb`
- **Description:** Evaluates player impact via plus/minus, comparing regular season and playoff performance, with visualizations to highlight trends.
- **Key Steps:** Computes average plus/minus (e.g., Avramovic 3.67), analyzes playoff shifts (e.g., Smailagic +3.36), and plots top performers’ trends.

### Consistency Analysis
- **File:** `6.consistency_analysis.ipynb`
- **Description:** Assesses player reliability using standard deviation (points, PIR, plus/minus) and autocorrelation (scoring streaks) for players with ≥10 games.
- **Key Steps:** Identifies consistent performers (e.g., Vukcevic, points SD 2.23) and top scorers (e.g., Punter, 16.08 mean), analyzes streakiness (e.g., Trifunovic 0.27 autocorr).

### Trend Analysis
- **File:** `7.trend_analysis_over_time.ipynb`
- **Description:** Tracks player performance trends (points, valuation, plus/minus) across regular season and playoffs, with statistical tests and visualizations.
- **Key Steps:** Calculates phase-wise changes (e.g., Punter +9.82 valuation), tests significance (e.g., Punter p=0.2786), plots trends for top players.

### Home vs. Away Performance
- **File:** `8.home_vs_away.ipynb`
- **Description:** Compares player and team performance at home vs. away, analyzing points, valuation, plus/minus, and defense, with statistical tests and visualizations.
- **Key Steps:** Identifies home boosts (e.g., Madar +6.95 valuation), finds significant plus/minus advantage (4.27-point swing, p=0.0182), notes non-significant points (p=0.3298) and defense (p=0.8220) differences.

### Clustering Analysis of Player Roles
- **File:** `9.clustering_with_k_means.ipynb`
- **Description:** Applies K-Means clustering to group players by per-minute stats (points, rebounds, assists, steals, blocks), identifying roles like “All-Around Bigs,” “Scoring Playmakers,” and “Defensive Specialists” using PCA and silhouette score.
- **Key Steps:** Clusters 12 players into 3 groups (e.g., Lessort in “Bigs,” Punter in “Playmakers”), visualizes with PCA, and validates with silhouette score (0.29), suggesting moderate separation with some overlap (e.g., Papapetrou’s hybrid role).

### Predictive Modeling for Player Performance
- **File:** `10.predictive_modeling.ipynb`
- **Description:** Forecasts points scored using Linear Regression (R²=0.36, RMSE=5.41) and Random Forest (R²=0.29, RMSE=5.70), with player-specific models for Punter (R²=0.61, RMSE=3.59) and Lessort (R²=-0.27, RMSE=4.24).
- **Key Steps:** Uses features like playing time, prior points, and game context; Linear Regression excels generally, Punter’s model improves accuracy, while Lessort’s underperforms due to matchup dependency.

### Impact of Key Player Absences on Team and Individual Performance
- **File:** `11.impact_of_absences.ipynb`
- **Description:** Examines effects of absences of top-five players by playing time (Leday, Lessort, Punter, Exum, Nunnally) on team points/valuation and Zach Leday’s stats across 39 games.
- **Key Steps:** Finds team points drop (e.g., Exum’s absence: -28.16) and Leday’s scoring rises (e.g., Punter absent: 20.00 vs. 10.97), highlighting his adaptability.

## What I Learned

This project sharpened my analytical game:

- **Python Proficiency:** Leveled up with Pandas for data wrangling, Seaborn/Matplotlib for visualization, and Scikit-learn for clustering and predictive modeling.
- **Sports Data Nuances:** Tackled the complexities of basketball stats, like reconciling team vs. player rebounds (e.g., 135 unassigned rebounds) and handling absences.
- **Performance Metrics:** Mastered efficiency metrics (e.g., TS%, USG%) and their practical insights, plus predictive modeling (e.g., Linear Regression’s R²=0.36) for strategic applications.

## Challenges I Faced

Hurdles I navigated during the project:

- **Data Quirks:** Unraveling unassigned stats (e.g., 135 team rebounds) required deep dives into game logs and validation checks.
- **Modeling Limits:** Predicting player performance proved tricky (e.g., Lessort’s R²=-0.27), highlighting matchup-driven variability.
- **Metric Selection:** Balancing relevant stats (e.g., TS%, USG%) with simplicity meant trimming complexity without losing insight.

## Conclusion

This analysis of Partizan’s 2022/23 EuroLeague season uncovered strengths (e.g., Lessort’s efficiency, Leday’s adaptability) and areas for growth (e.g., depth during absences). It lays a foundation for future exploration—like incorporating opponent stats or lineup synergies—while offering a data-driven playbook for basketball and analytics enthusiasts.

## Tools I Used

I built this project with a Python-centric data science stack:

- **Python:** The backbone of my analysis, leveraging:
  - **Pandas:** Data wrangling and manipulation.
  - **NumPy:** Numerical computations.
  - **Matplotlib & Seaborn:** Visualization of trends and insights.
  - **Scikit-learn:** Clustering and predictive modeling.
  - **SciPy:** Statistical tests and analysis.
- **Jupyter Notebooks:** Interactive environment for coding, notes, and visuals.
- **Visual Studio Code:** Efficient script development and execution.
- **Git & GitHub:** Version control and project sharing.

## Getting Started

- **Requirements:** Python 3.11, pandas, matplotlib, seaborn, scipy, numpy, scikit-learn
- **Data:** Raw data in `data/partizan_2022_raw.csv`; cleaned data in `partizan_2022_cleaned.csv`
- **Run:** Open notebooks in Jupyter to explore the analysis.

## Notes
- Detailed findings are in the notebooks.
- Contact milandjkc1ds@gmail.com for questions.
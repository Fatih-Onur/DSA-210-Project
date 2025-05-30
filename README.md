# FOOTBALL TEAMS EXPENDITURE TO SUCCESS - DSA_210_project

## Project Overview

This project investigates how English Premier League teams' transfer market activities—such as transfer expenditures, player acquisitions and departures, and financial returns—correlate with their on-field performance measured by league standings and points. Using data sourced from Transfermarkt, the study will employ exploratory data analysis and statistical modeling across multiple seasons to uncover trends and assess the impact of financial investments.

The main goal is to find out whether spending big money on new star players really helps a team's short-term success. If it helps, how much it helps and which factors are most crucial along the transfer window. This investigation can be done with every football league and every season as long as we have meaningful data on it. However, I will be studying the English Premier League since it is the most valuable and most watched league across the world (also the league with the most money spent).

---

## Objectives

1. **Analyze Spending vs. Success:**  
   Investigate the correlation between total transfer expenditure and team performance, measured by league standings and points.

2. **Evaluate Spending Efficiency:**  
   Assess how efficiently teams spend by comparing money spent per new player with performance improvements.

3. **Measure Net Transfer Impact:**  
   Examine the relationship between net profit or loss in the transfer market and a team’s ability to maintain or improve its league position.

4. **Assess Squad Stability vs. Performance:**  
   Analyze how player turnover (new signings vs. departures) affects team consistency and success.

5. **Compare Financial Strategies:**  
   Identify different spending strategies (big spenders vs. budget-conscious teams) and their effectiveness in achieving better results.

---

## Motivation

This project reflects and combines two of my passions: football and finance. In this project, I investigate the financial and sporting decisions of major organizations and examine whether "a bag of money can score a goal".

In summary, I want to find out how a team's market value and their spending on transfers impact their success.

---

## Dataset

The dataset for this project consists of 10 years of English Premier League team spending and success data through these factors:

- **Total spending on transfers:** How much did every team spend throughout both short term (1 year) and long term (10 years) periods.
- **Total spending on wages:** Total money that clubs spend on transfers.
- **Total income from transfers:** Total money that went into club revenue from transfers.
- **Number of new players:** Number of players that joined the club either as a free transfer, on loan, by fee, or end of loan from another club.
- **Number of players sent:** Number of players that left the club either as a free transfer, on loan, or by fee.
- **Net profit from transfers:** Net profit/loss after all the transfers.
- **League standing:** Each team's league standing in every year.
- **Points obtained:** Each team's points at the end of every season.
- **Number of trophies:** How many trophies that club won during this period.
- **Fee per player:** Average fee per player.
- **Teams’ estimated market value:** Sum of players' estimated market values in a club.

New data can be used and this list can be extended. However, it should be sufficient for this analysis.

---

## Data Collection

I collected data from the following sources:

- **Transfermarkt:** Spending, earning, market value, and number of transfer data.  
  Link: [Transfermarkt Premier League Transfer Spending](https://www.transfermarkt.com/premier-league/einnahmenausgaben/wettbewerb/GB1)

- **Premier League & UEFA:** Performance data (points, standings, trophies).  
  Links:  
  - [Premier League Tables](https://www.premierleague.com/tables)  
  - [UEFA Club Rankings](https://www.uefa.com/nationalassociations/uefarankings/club/?year=2025)  
    *(Filter by country as England)*

---

## Data Exploration and EDA

<span style="color:blue">After collecting and merging the data, I performed extensive exploratory data analysis (EDA) to better understand the structure and trends.</span>  
- I examined the **distribution of spending and income** for each team, as well as overall league spending trends over the years.  
- I analyzed the **relationship between spending and league performance**, checking for linear or non-linear patterns.  
- I visualized the impact of **net profit/loss** and the number of player arrivals/departures on seasonal performance.  
- Throughout the EDA, I used **scatter plots, correlation matrices, and boxplots** to highlight the most important features and remove redundancies (such as overlapping variables like “Balance” and “+/-”).

This helped shape a more refined feature set for the next modeling phase.

---

## Machine Learning Modeling

<span style="color:blue">After cleaning and reducing the dataset, I moved on to predictive modeling to estimate each team's next season's point total.</span>  
- I started with **Linear Regression** as a baseline model to identify linear relationships and benchmark performance.  
- I then evaluated **K-Nearest Neighbors (KNN)** by testing different k values to capture local data patterns.  
- Next, I implemented a **Decision Tree Regressor**, though it was prone to overfitting without parameter tuning.  
- To address this, I tested **Random Forest Regressor**, an ensemble of decision trees that balances bias and variance well.  
- Finally, I experimented with **XGBoost Regressor**, but it did not outperform the simpler models for this dataset.

Throughout this process, I tracked key metrics for each model:
- **R² Score** to measure how much variance in next season's points the model could explain.  
- **MSE** and **RMSE** to capture the average magnitude of prediction errors.

The **Linear Regression** and **Random Forest** models achieved the best performance, each explaining over 72% of the variance and predicting next-season points with an average error of about 9 points.  
Meanwhile, KNN showed decent performance at k=15, and XGBoost underperformed due to possible overfitting.

---

## Conclusion

This project demonstrated that a thoughtful balance of data cleaning, feature selection, and model choice is key for building robust predictive models.  
Despite testing more advanced algorithms like XGBoost, the simpler and more interpretable models (like Linear Regression and Random Forest) provided the best trade-off between accuracy and generalizability.

This journey provided valuable insights not only into football finances but also into the power of machine learning to reveal meaningful patterns in real-world data.


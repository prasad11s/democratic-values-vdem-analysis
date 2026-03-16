# Analyzing Democratic Values and Political Ideologies Across Six Countries

## Overview

This project examines how populism, anti-elitism, and people-centrism influence democratic values including respect for political opponents, gender equality, minority rights, and political pluralism across Australia, China, Germany, India, the United Kingdom, and the United States.

Using the V-Dem V-Party dataset covering 1970 to 2020, the study applies both frequentist and Bayesian statistical techniques to uncover how political parties promote or hinder democratic norms across 50 years of political history.

## Research Questions

1. How does the level of populism influence a party's respect for political opponents across different countries?
2. Is there a significant difference in gender equality ideology among political parties across India, the U.S., and Germany?
3. Do countries with higher support for minority rights also exhibit higher political pluralism?
4. Do political parties with stronger anti-elitism views tend to show greater support for people-centric policies, and does this relationship vary across countries?

## Key Findings

- **Populism and Political Tolerance:** Higher populism is associated with lower respect for political opponents (β = −1.31, p < 0.001), with the sharpest declines observed in the U.S. and Germany. India shows a divergent positive association, suggesting different populist dynamics.
- **Gender Equality Ideology:** Germany leads significantly, while India lags behind by 2.5 points (p < 0.001). The model explains 42% of variance across the three countries analyzed.
- **Minority Rights and Pluralism:** The relationship is positive overall but context dependent. China shows the strongest linkage (interaction β = 0.77, p = 0.043), while other countries exhibit weaker effects.
- **Anti-Elitism and People-Centrism:** Anti-elitism strongly predicts people-centric narratives (β = 0.38, p < 0.001), particularly in the UK and India, while Germany shows a negative interaction.

## Visualizations

### Populism vs. Respect for Political Opponents
![Populism vs Respect](figures/populism_vs_respect_opponents.png)

### Gender Equality Ideology by Country
![Gender Equality Boxplot](figures/boxplot_gender_equality_by_country.png)

### Populism Trends Over Time (1970 to 2020)
![Populism Trends](figures/populism_trends_over_time.png)

## Visualizations

The analysis includes the following visual explorations:

- Time series trends of populism scores across countries (1970 to 2020)
- Scatterplots with linear fits: Populism vs. Respect for Opponents, Populism vs. Minority Rights, Gender Equality vs. Political Pluralism, People-Centrism vs. Respect for Opponents
- Boxplots comparing distributions of populism, political pluralism, gender equality, respect for opponents, and minority rights across all six countries

## Methods

| Approach | Tools | Application |
|----------|-------|-------------|
| Frequentist Regression | `lm()` | Linear models with interaction terms for all four research questions |
| Bayesian Regression | `stan_glm()` via `rstanarm` | Posterior estimation with informative priors, credible intervals, and convergence diagnostics |
| ANOVA | `lm()` with categorical predictors | Cross-country comparison of gender equality ideology |
| Exploratory Data Analysis | `ggplot2`, `dplyr` | Summary statistics, scatterplots, boxplots, and time series visualizations |

All Bayesian models achieved strong convergence (Rhat = 1.0) with effective sample sizes exceeding 3,000 for all parameters.

## Model Performance

| Research Question | Model | R² | Key Predictor Significance |
|-------------------|-------|-----|---------------------------|
| RQ1: Populism → Respect for Opponents | Interaction model | 0.83 | p < 0.001 |
| RQ2: Gender Equality across Countries | ANOVA style | 0.42 | p < 0.001 |
| RQ3: Minority Rights → Political Pluralism | Interaction model | 0.90 | p = 0.043 (China interaction) |
| RQ4: Anti-Elitism → People-Centrism | Interaction model | 0.76 | p < 0.001 |

## Dataset

- **Source:** V-Dem V-Party Dataset, Version 2.0 (2023), Varieties of Democracy Project
- **URL:** [https://www.v-dem.net](https://www.v-dem.net)
- **Scope:** 305 party-level observations across 6 countries, 12 variables after cleaning
- **Time Period:** 1970 to 2020
- The cleaned dataset (`cleaned_vparty_model_data.xlsx`) is included in this repository

## Repository Structure

```
├── Final_Democracy.Rmd             # R Markdown source with full analysis code
├── Report.pdf                      # Written project report with findings
├── cleaned_vparty_model_data.xlsx  # Cleaned dataset (305 observations, 12 variables)
├── variable_descriptions.txt       # Descriptions of all variables used
├── figures/                        # All visualizations generated from the analysis
│   ├── populism_vs_respect_opponents.png
│   ├── populism_vs_minority_rights.png
│   ├── gender_equality_vs_political_pluralism.png
│   ├── people_centrism_vs_respect_opponents.png
│   ├── boxplot_populism_by_country.png
│   ├── boxplot_political_pluralism_by_country.png
│   ├── boxplot_gender_equality_by_country.png
│   ├── boxplot_respect_opponents_by_country.png
│   ├── boxplot_minority_rights_by_country.png
│   ├── populism_trends_over_time.png
│   └── gender_equality_trends_over_time.png
└── README.md
```

## Tech Stack

**Language:** R

**Key Libraries:** tidyverse, ggplot2, dplyr, rstanarm, janitor

**Statistical Methods:** Linear Regression, Bayesian Regression (Stan), ANOVA, Interaction Models

## Course Context

This project was completed as the final project for **IST 686: Quantitative Reasoning for Data Science** at Syracuse University (Spring 2025), under Professor Dilmore.

## Author

**Prasad Shimpi**
MS Applied Data Science, Syracuse University
[LinkedIn](https://www.linkedin.com/in/prasadshimpi/) | [GitHub](https://github.com/prasad11s)

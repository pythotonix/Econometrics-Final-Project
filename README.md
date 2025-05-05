# Econometrics Final Project: Analyzing Factors Affecting Cafe Check Amount

## Overview

This project explores consumer behavior in a local café in Lviv, aiming to uncover the key factors that influence customer spending. Through exploratory data analysis (EDA) and binary logistic regression modeling, we identify how different menu categories, time-based variables, and customer characteristics impact the total check amount — ultimately leading to practical, data-driven recommendations for menu design, promotion strategy, and procurement planning.

Final report: [`final_report_econometrics.pdf`](./final_report_econometrics.pdf)

---

## Objectives

- Understand how **time of day**, **day of week**, and **month** influence customer spending and category preferences.
- Identify which **dish categories are frequently ordered together**.
- Model how dish categories and contextual factors influence the **likelihood of ordering a main course**.
- Recommend **combo offers and promotion strategies** based on empirical findings.

---

## Data Description

The dataset consists of **in-cafe transaction records** over a full year with the following structure:
- `opened`, `closed`: Order start and end times
- `guest_count`, `profit`, `paid`, `discount`: Order-level metadata
- One-hot encoded dish category flags (`main_course`, `salad`, `soup`, etc.)
- Temporal context (`morning`, `lunch`, `evening`, `day_of_week`, `weekend`)

All analyses focus only on **non-delivery orders** to ensure consistency and interpretability.

---

## Project Structure

| File                          | Description                                                                 |
|-------------------------------|-----------------------------------------------------------------------------|
| `eda.ipynb`                   | Initial EDA on spending patterns, category frequency, and guest profiles    |
| `menu_categorization.ipynb`   | Preprocessing and combining food categories into macro-groups               |
| `category_EDA_in_cafe.ipynb`  | Time-based visualizations of category popularity and profit                 |
| `profitable_eda.ipynb`        | Analysis of weighted and raw profit per category, including seasonality     |
| `main_course_model.ipynb`     | Logistic regression to predict likelihood of ordering a main course         |
| `final_report_econometrics.pdf` | Full report containing methodology, figures, results, and recommendations |

---

## Key Results

### Exploratory Data Analysis
- **Main courses** dominate profit and frequency, especially during **lunch and dinner**.
- **Hot drinks and soups** peak in the **morning**, while **alcohol and cold drinks** are preferred in the **evening/weekend**.
- Categories like **salads** and **starters** often co-occur with **grill items**, suggesting complementary or substitutive behavior.

### Logistic Regression Findings
- **Guest count**, **salad**, and **soup** significantly increase the odds of ordering a **main course**.
- **Grill items**, especially when paired with **salad**, reduce that likelihood.
- **Alcohol alone** decreases main course selection, but combined with **starters**, the probability increases.
- **Soup in the evening** strongly boosts main course choice.

---

## Recommendations

| Combo                             | Time              | Business Goal                              |
|----------------------------------|-------------------|---------------------------------------------|
| Starter + Main + Cold Drink      | Lunch             | Upsell high-margin sides with mains         |
| Salad + Grill                    | Lunch             | Balance meal and increase ticket size       |
| Soup + Main                      | Evening           | Nudge undecided customers to full meal      |
| Main + Cold Drink                | Evening           | Leverage demand spikes with simple pairing  |
| Alcohol + Starter                | Evening (Weekend) | Trigger celebratory/full-meal orders        |

More in [Section 6.2 of the Report](./final_report_econometrics.pdf).

---

## Authors

- **Sofiia Bazylevych**
- **Solomiia Shopiak**
- **Tetiana Shvets**

Ukrainian Catholic University – Business Analytics Program  
Econometrics Final Project (2025)

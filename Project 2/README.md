# Project 2 - Ames Housing Data and Kaggle Challenge
---

### Overview:
Project 2 covers:
- Background
- Outside Research
- Data Overview
- Summary Table on the features I keep
- Conclusion (Summary Table)
- Business Recommendations

## Background & Problem Statement

As a data analyst working under a real estate company, I am tasked to develop a model to predict the selling price of a given home in Ames, Iowa. My employer hopes to use this information to further educate the property agents on how to utilise these information to upsell a house in Ames. The agents can also use this information to advice their sellers on a reasonable price to sell their house in Ames.

This project aims to explore the top predictors of selling price of a given home in Ames, Iowa.

## Outside Research

Based on a post on the 'ByCarrier' blog, we can understand more on the most common features of a 'Perfect' house. Some of the features are outdoor areas and garage. To have such features, the house would need to have big spaces. We must also consider how functional is our 'Dream' house. Is it able to address our current needs, will it be able to address our future needs? We have to be more practical when buying a house. One can understand more from the blogpost ([*source*](https://bycarrier.com/blog/custom-homes/features-perfect-house/)).

## Data Overview

The Ames housing train data set contains 2051 entries with 81 features, representing characteristics of houses sold between 2006 - 2010. 

The features can also be classified into the following types:

- Numerical (Example: General Living Area)
- Categorical (Example: Neighborhood)

## Summary Table on the features I keep

| **Feature**       | **Type**      | **Reason for keeping feature**              |
|-------------------|---------------|---------------------------------------------|
| **Overall Qual**  | _numerical_   | Correlation score is 80%                    |
| **Gr Liv Area**   | _numerical_   | Correlation score is 72%                    |
| **Total Bmst SF** | _numerical_   | Correlation score is 67%                    |
| **Garage Area**   | _numerical_   | Correlation score is 66%                    |
| **1st Flr SF**    | _numerical_   | Correlation score is 65%                    |
| **Garage Cars**   | _numerical_   | Correlation score is 65%                    |
| **Condition 1**   | _categorical_ | Their notches in the boxplot do not overlap |
| **Condition 2**   | _categorical_ | Their notches in the boxplot do not overlap |
| **Exter Qual**    | _categorical_ | Their notches in the boxplot do not overlap |
| **Exter Cond**    | _categorical_ | Their notches in the boxplot do not overlap |
| **Foundation**    | _categorical_ | Their notches in the boxplot do not overlap |
| **Bsmt Qual**     | _categorical_ | Their notches in the boxplot do not overlap |
| **Bsmt Cond**     | _categorical_ | Their notches in the boxplot do not overlap |
| **Kitchen Qual**  | _categorical_ | Their notches in the boxplot do not overlap |
| **Functional**    | _categorical_ | Their notches in the boxplot do not overlap |
| **Garage Finish** | _categorical_ | Their notches in the boxplot do not overlap |

## Conclusion (Summary Table)

| **Types of Model**    | **Cross_val_score** | **Train** | **Test** | **Alpha** | **The Model I chose** |
|-----------------------|---------------------|-----------|----------|-----------|-----------------------|
| **Linear Regression** | -6.34               | 0.8772    | 0.8876   | NA        | No                    |
| **Lasso**             | 0.8646              | 0.8768    | 0.8876   | 80        | Yes                   |
| **Ridge**             | 0.8644              | 0.8770    | 0.8878   | 10        | No                    |

## Business Recommendations

| **Top Features (from Lasso Model)** |
|-------------------------------------|
| _Gr Liv Area_                       |
| _Total Bmst SF_                     |
| _Overall Qual_                      |
| _Functional_Type_                   |
| _Garage Area_                       |

Now that we know what the top predictors are, we would have a unique selling point. These information would give us an edge over our competitors.

Firstly, we can further upsell the property. We can go straight to the point of explaining how is this the dream house that each customer is looking for. We can also be more persuasive when trying to seal the deal. This would help to make the buyers be able to have a smooth and exciting experience while looking for their dream house.

Secondly, as property agents, one would handle buyers and sellers. Knowing the features of the house would be able to aid us in coming up with a reasonable price range so that we can help our sellers sell their houses as fast as possible. We would also be able to manage their expectations. 

Our aim is to satisfy the needs of all customers. With the top predictors, we would be able to provide a efficient and fun experience for both buyers and sellers.

**References:**

10 common features of a “Perfect” house. (n.d.). By Carrier. https://bycarrier.com/blog/custom-homes/features-perfect-house/
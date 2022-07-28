<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 3 - Web APIs & NLP
---

## Problem Statement

As part of the marketing team for ClassPass, we are tasked to increase awareness for 'Pilates'. Hence, the stakeholders have instructed our team to conduct a NLP research on 'Pilates' and another similar exercise, 'Yoga' using reddit. As we will be using Search Engines to publish our advertisements, this research aims to come out with a classification model for a more effective advertising campaigns for 'Pilates'. Beside the classification model, this reserach will also address the following:

- Provide a general sentiment analysis on 'Yoga' and 'Pilates'.

### Overview:
Project 3 covers:
- (Part 1)
  - Background
  - Outside Research
  - Data Collection
- (Part 2)
  - Data Cleaning
  - Pre-Processing & EDA
  - Sentiment Analysis
- (Part 3)
  - Modeling
  - Conclusion (Summary Table)
  - Business Recommendations
  - Further Analysis

## Background

Based on the 'ClassPass Comeback Report: Fitness and Beauty Trends 2021' we found out that Yoga and Pilates are both in the top 10 classes being booked. Yoga is ranked second while Pilates is ranked fourth. One can read more on it from ClassPass blog ([*source*](https://classpass.com/blog/2021-comeback-fitness-trends/)).

We were also able to understand that 'Yoga is growing a loyal following.' Newcomers are most likely to book a yoga class first. Livestream yoga is the only digital class type in the top 10 most booked classes and appointments. In-studio yoga has climbed to the second most popular class type since studios have reopened. It’s likely that the at-home yoga spike produced some new students, and that both new and seasoned yogis are excited to practice with a community again.

Pilates is ranked fourth as people expressed that it can be hard to fit a Pilates reformer (an equipment used when practicing Pilates) into their house. Hence 2/3 of our members are saying that access to equipment is one of the top reason for heading back to classes for Pilates.

## Outside Research

Yoga and Pilates are often compared as they have many similarities but the two are inherently very different forms of exercise. They are both low-impact exercise and are able to offer connection to the body and relief stress while developing flexibility, strength, control and endurance. One can understand more from the article from Harpers Bazaar ([*source*](https://www.harpersbazaar.com/uk/beauty/fitness-wellbeing/a25626354/yoga-vs-pilates/)).

But the biggest difference between the two is the emphasis on the spiritual side in Yoga classes. Yoga is an integrated health management system using breath, movement and meditation to unite mind, body and spirit. Also there are different types of Yoga like 'Hatha Yoga', 'Power Yoga', 'Hot Yoga' and many more.

While Pilates is a physical system that uses very specific targeted exercises to improve strength, flexibility and posture with particular focus on the core. Pilates are mainly split into 'Mat Pilates' or 'Classical Pilates'.

Pilates have been on an upwards trend in terms of popularity and accessibility. Pilates was invented by Joseph Pilates more than a century ago. Due to covid, gyms were closed and we were all confined to our homes. Thanks to social media being the driving force behind the recent resurgence of the low-impact workout, awareness for Pilates was increased. As we had to look for new ways to work out that involved minimal equipment that are generally accessible and easy to follow with just a mat and a resistance band while watching online videos. One can understand more from the article from Body and Soul ([*source*](https://www.bodyandsoul.com.au/fitness/training-tips/why-is-pilates-everywhere-now-and-what-did-covid-have-to-do-with-it/news-story/49ece150142fad14048bdb6608b44581)).

## Sentiment Analysis Summary Table

| **Subreddit** | **Positive Sentiment** | **Neutral Sentiment** | **Negative Sentiment** |
|---------------|------------------------|-----------------------|------------------------|
| Yoga          | 79.31%                 | 4.87%                 | 15.82%                 |
| Pilates       | 81.02%                 | 6.33%                 | 12.65%                 |

Yoga and pilates sentiments are pretty similar. Based on our findings from our dataset, pilates's positive sentiment was higher than yoga's positive sentiment by 2%. Pilate's negative sentiment is lower than yoga's negative sentiment by 2%.

From this, we can see that the public's opinion and sentiment towards pilates are better than yoga. Hence, we are high likely able to increase pilates awareness.

## Conclusion (Summary Table)

| # | **Vectorizer**  | **Model**                 | **Best Score** | **Best Train** | **Test Score (Accuracy)** | **Test Score (Sensitivity)** | **Best Parameters**                                                                        |
|---|-----------------|---------------------------|----------------|----------------|---------------------------|------------------------------|--------------------------------------------------------------------------------------------|
| 1 | CountVectorizer | _Logistic Regression_     | 0.8432         | 0.9993         | 0.8004                    | 0.8032                       | cvec__max_df: 0.85 cvec__max_features: 5000 cvec__min_df: 3 cvec__ngram_range: (1, 2)      |
| 2 | TfidfVectorizer | _Logistic Regression_     | 0.8674         | 0.9549         | 0.8347                    | 0.8193                       | tvec__max_df: 0.8 tvec__max_features: 2500 tvec__min_df: 3 tvec__ngram_range: (1, 2)       |
| 3 | CountVectorizer | _Multinomial Naïve Bayes_ | 0.8560         | 0.9280         | **0.8488**                    | 0.8594                       | cvec__max_df: 0.85 cvec__max_features: 2500 cvec__min_df: 3 cvec__ngram_range: (1, 2)      |
| 4 | TfidfVectorizer | _Multinomial Naïve Bayes_ | 0.8587         | 0.9408         | 0.8387                    | 0.8514                       | tvec__max_df: 0.8 tvec__max_features: 2500 tvec__min_df: 3 tvec__ngram_range: (1, 2)       |
| 5 | CountVectorizer | _Random Forest_           | 0.8486         | 0.9785         | 0.8246                    | 0.8153                       | rf__max_depth: None rf__min_samples_leaf: 2 rf__min_samples_split: 5 rf__n_estimators: 150 |
| 6 | TfidfVectorizer | _Random Forest_           | 0.8378         | 0.9549         | 0.8105                    | 0.8112                       | rf__max_depth: None rf__min_samples_leaf: 4 rf__min_samples_split: 2 rf__n_estimators: 200 |

### Model Selection: Multinomial Naïve Bayes with Count Vectorizer

## Business Recommendations

Our baseline accuracy score is 0.503 and every model have outperformed it. In order to increase our awareness for pilates, our marketing efforts must be able to differentiate between yoga and pilates. Hence, the focus is on getting as many correct predictions as possible. The Multinomial Naïve Bayes with CountVectorizer has the best predictive performance on the classification problem. Through the research we were able to address some other problems such as identifying the top common words and even performed sentiment analysis. The marketing team and the stakeholders would then be able to perform a more data-driven approach in handling the marketing campaigns for pilates.

## Further Analysis

For future steps, we can analyse pilates with other exercises offered by ClassPass. As yoga and pilates are similar, the scores attained were all 0.8 (in terms of accuracy). Hence, should try to compare pilates with exercises that is not yoga to see whether will the models perform better.

We can also understand more on the trend of pilates over the years more in-depth so as to understand what are the features of pilates that attracts people to start learning and practicing it. Once we have such informations, we would be able to further improve our awareness campaigns.

### References

https://www.bodyandsoul.com.au/fitness/training-tips/why-is-pilates-everywhere-now-and-what-did-covid-have-to-do-with-it/news-story/49ece150142fad14048bdb6608b44581

Fitness and beauty trends 2021. (2021, July 28). ClassPass Blog. https://classpass.com/blog/2021-comeback-fitness-trends/

The key differences between yoga and Pilates. (2021, March 16). Harper's BAZAAR. https://www.harpersbazaar.com/uk/beauty/fitness-wellbeing/a25626354/yoga-vs-pilates/
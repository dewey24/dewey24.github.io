---
title: <br/><br/><br/>Machine Learning Evaluation Metrics<br/><br/><br/>
date: "14 Oct 2021"
show_date: true
layout: single
classes: wide
author_profile: true
header:
  overlay_image: /assets/images/walle.jpeg
  #overlay_color: "#333"
  show_overlay_excerpt: false
  #teaser: /assets/images/experiments.jpeg
tags:
- "Machine Learning"
- "Deep Learning"
- Analytics
- AI
toc: true
---

_________________________________________________________________________________________________________________________________________________________________________________

## _**CLASSIFICATION METRICS**_

1. Accuracy = (TP + TN) / (TP + FP + TN + FN)
2. Error = (FP + FN) / (TP + FP + TN + FN)
3. Precision +ve = TP / (TP + FP)
4. Recall +ve = TP / (TP + FN)
5. Precision -ve = TN / (TN + FN)
6. Recall -ve = TN / (TN + FP)
7. F-measure = 2 x Precision x Recall / (Precision + Recall)
8. Receiver Operating Characterstic = Plot True Postive Rate (TP / P) versus False Positive Rate (FP / N) for different cutoff values
9. Area Under Curve (Area Under ROC Curve)
10. Cumulative Response Curve = % of Postives Targeted VERSUS % of Test Instances (decreasing by score)
11. Lift Curve =  (% of Postives Targeted / % of Positives Targeted by a Random Classifier) VERSUS % of Test Instances (decreasing by score)
12. Profit Curves (or Cost Aware Lift Curves) = Expected Value Maximization

_________________________________________________________________________________________________________________________________________________________________________________

## _**REGRESSION METRICS**_

1. Error = \|Actual_i - Prediction_i\|
2. [MAPE](https://en.wikipedia.org/wiki/Mean_absolute_percentage_error) = AVERAGE {Error_i / Actual_i}
3. [wMAPE](https://en.wikipedia.org/wiki/Mean_absolute_percentage_error#WMAPE) = SUM {Error_i} / SUM {Actual_i}
* Most commonly the absolute percent errors are weighted by the actuals 
4. MAE = AVERAGE {Error_i}
5. P90 WE = {0.9 x Underbias + 0.1 X Overbias} / Actuals

_________________________________________________________________________________________________________________________________________________________________________________

## _**RANKING METRICS**_

1. Precision at top-K - % of relevant items among top-K recommendations
2. Mean Average Precision (MAP) - Avg. precision across different levels of recall
3. Normalized Discounted Cumulative Gain
* The premise of DCG is that highly relevant documents appearing lower in a search result list should be penalized as the graded relevance value is reduced logarithmically proportional to the position of the result.
* Normalization - since result lists vary in length depending on the query
4. Receiver Operating Characterstic = Plot True Postive Rate (TP / P) versus False Positive Rate (FP / N) for different cutoff values

_________________________________________________________________________________________________________________________________________________________________________________

## _**RECOMMENDER SYSTEMS METRICS**_

1. Offline Evaluation Metrics - Classification Metrics; Regression Metrics; Ranking Metrics
2. Online Evaluation Metrics - A/B Tests to measure increase in CTR (Click Trough Rate) or Sales

_________________________________________________________________________________________________________________________________________________________________________________

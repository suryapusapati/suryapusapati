---
title: "How to evaluate an ML model performance?"
tags:
style: fill
color: primary
description: List of Performance Metrics in Machine Learning.
# external_url: 
---

# List of Performance Metrics
For any Machine Learning model, we need metrics to rank the model in terms of performance or to compare it with other trained ML methods. Every ML task can be divided into either *Regression* or *Classification* problem. From my literature, I have created a comprehensive list of metrics I came across.

## Regression or Time-series problem:
> *NOTE: Error is sometimes also referred to as loss.*
* Mean Error (ME)
	* Mean Squared Error (MSE)
	* Root Mean Squared Error (RMSE)
	* Normalised RMSE (NRMSE)

* Absolute Error
	* Mean Absolute Error (MAE)
	* Mean Absolute Scaled Error (MASE)
	* Median Relative Absolute Error (MdRAE)

* Percentage Error
	* Mean Percentage Error (MPE)
	* Mean Absolute Percentage Error (MAPE)
	* Mean Squared Percentage Error (MSPE)
	* Root-Mean Squared Percentage Error (RMSPE)
	* Weighed Absolute Percentage Error (WAPE)
	* Weighted MAPE (WMAPE)
	* Symmetric MAPE (sMAPE)

* Relative Error
	* Root Mean Squared Relative Error (RMSRE)
	* Geometric Mean Relative Absolute Error (GMRAE)

* R-squared (Coefficient of determination) (R2)
* Explained variance score

## Classification problem:
* Classification Accuracy
* Recall
* Precision
* F1
* Kappa
* MCC
* Logarithmic Loss
* Area Under ROC Curve (AU-ROC)
* Confusion Matrix
* Classification Report

## If I missed out something, feel free to rise an [issue](https://github.com/suryapusapati/suryapusapati/issues) in GitHub. Hereon I will keep on improving the post with new metrics.

Ⓒ Surya Pusapati 2022
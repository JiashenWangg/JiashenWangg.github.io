---
layout: page
title: Loan Default Classification (SBA Loans)
description: A predictive modeling framework for U.S. Small Business Administration (SBA) loans to identify default risk at origination

img: 
importance: 3
category: Data Science
---
## Project Overview

This project develops a predictive modeling framework for U.S. Small Business Administration (SBA) loans to identify default risk at origination. The objective is to classify loans as Paid in Full (PIF) or Charged Off (CHGOFF), with a primary focus on minimizing costly missed defaults under significant class imbalance. The analysis emphasizes aligning model evaluation with real-world credit risk priorities, where false negatives (missed defaults) carry substantially higher financial impact than false positives.

## Market & Data Overview

The analysis is based on a large-scale SBA loan-level dataset comprising approximately 900,000 observations across 27 raw variables, refined into a modeling dataset of ~857,000 loans with 17 structured features. The target variable, MIS_Status, distinguishes between non-default (PIF) and default (CHGOFF) outcomes.

The dataset captures borrower characteristics, loan terms, institutional factors, and geographic indicators, providing a comprehensive view of credit risk drivers across the U.S. small business lending market.

## Modeling Strategy

Feature engineering focuses on economically meaningful transformations. The final feature set includes a balanced mix of numerical and categorical predictors designed to capture both borrower risk and institutional context.

<div class="row justify-content-sm-center">
    <!-- LEFT: text (8/12) -->
    <div class="col-sm-8 mt-3 mt-md-0">
        <p>
            A unified modeling framework is implemented using scikit-learn pipelines to ensure consistent preprocessing and fair model comparison. The dataset is split into training (80%) and testing (20%) sets using stratified sampling to preserve class distribution. Multiple model classes are evaluated to capture different aspects of the bias–variance tradeoff:
        </p>
        <ul>
            <li>Logistic Regression serves as an interpretable baseline</li>
            <li>Random Forest captures nonlinear relationships via bagging</li>
            <li>AdaBoost sequentially improves weak learners</li>
            <li>XGBoost leverages gradient boosting with regularization for high-performance prediction</li>
        </ul>
    </div>
    <!-- RIGHT: image (4/12) -->
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/loan_pipeline.png" title="Example Pipeline" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
            End-to-end modeling pipeline from data preprocessing to model evaluation.
        </div>
    </div>
    
</div>

Model evaluation prioritizes recall for the default class (CHGOFF), alongside precision, F1-score, and ROC-AUC, reflecting the asymmetric cost structure of credit risk decisions. Among all models, XGBoost delivers the strongest performance. Compared to baseline models, XGBoost significantly reduces false negatives, directly addressing the primary business objective of minimizing missed defaults while maintaining strong overall discrimination.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/loan_rocauc.png" title="ROC-AUC Curve" class="img-fluid rounded z-depth-1" style="height:250px;" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/loan_confusion.png" title="Confusion Matrix" class="img-fluid rounded z-depth-1" style="height:250px;" %}
    </div>
</div>
<div class="caption">
    On the left, ROC-AUC curve of XGBoost model; on the right, confusion matrix
</div>

## Risk Drivers & Model Insights

Feature importance analysis highlights several key determinants of loan default risk:

- Loan term as a proxy for exposure duration
- Disbursement timing, indicating operational and liquidity factors
- Bank identity, reflecting institutional underwriting quality
- SBA guarantee share, capturing risk allocation structure
- Geographic classification (urban vs. rural), indicating macroeconomic context

These drivers are consistent with established credit risk intuition, reinforcing the model’s interpretability and practical relevance.
---
layout: page
title: Detecting Horse Cardiac Arrhythmia with ECG Data
description: The study focuses on developing methods to detect cardiac arrhythmia in horses using ECG data.
img: 
importance: 1
category: Data Science
related_publications: false
---

## Project Overview

This project was conducted in collaboration with [Dr. Katharyn Mitchell](https://equine.cornell.edu/people/katharyn-mitchell) from [Cornell University College of Veterinary Science](https://www.vet.cornell.edu/), under the guidance of [Dr. Ron Yurko](https://www.stat.cmu.edu/~ryurko/). Part of it was created as the capstone project for the [Spring 2024 section of 36-490 Undergraduate Research](https://www.stat.cmu.edu/capstoneresearch/spring2024/) at Carnegie Mellon University.

The study focuses on developing scalable and interpretable methods to detect cardiac arrhythmia in horses using electrocardiogram (ECG) data. Leveraging over 500,000 RR interval observations collected across multiple physiological phases, we combine statistical techniques, time-series analysis, and machine learning models to identify abnormal heart rhythms. This work contributes to veterinary medicine by enabling earlier diagnosis and data-driven decision support for cardiac conditions in equine populations.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Horse_Poster.png" title="Project Poster" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Poster presented for the Spring 2024 section of 36-490 Undergraduate Research at Meeting of the Minds Conference
</div>

## Study Abstract

Cardiac arrhythmia detection from ECG signals is a critical yet time-intensive task, particularly in veterinary contexts where continuous monitoring data is abundant but underutilized. Using the Cornell Equine ECG dataset, this study investigates whether patterns in RR intervals and derived heart rate variability features can reliably distinguish between normal and arrhythmic states.

The dataset includes recordings from 13 horses across 24-hour monitoring periods, spanning multiple physiological phases such as pre-injection baseline, severe symptom onset, and recovery. We organize features into interpretable groups capturing short-term variability, long-term structure, and temporal dynamics.

Our approach integrates multiple stages of analysis. First, we apply statistical feature engineering and unsupervised learning methods—including Principal Component Analysis (PCA), Gaussian Mixture Models, and hierarchical clustering—to explore underlying structure and identify phase separability. Next, we model temporal dynamics using Functional PCA to capture how cardiac behavior evolves over time. Finally, we implement supervised classification models, including logistic regression, Lasso regularization, and Linear Discriminant Analysis, combined with domain-specific feature extraction from Poincaré plots and time-series signals.

Using a rigorous Leave-One-Horse-Out cross-validation framework, our best-performing model achieves an AUC of 0.92 and high sensitivity in detecting arrhythmic events. Key findings highlight that increased short-term variability (SD1, coefficient of variation) is strongly associated with arrhythmia, while long-term stability (SD2) indicates normal cardiac function.

This project demonstrates that combining domain-informed feature engineering with interpreable statistical models can outperform more complex approaches in small-sample, high-noise biomedical settings. The resulting pipeline—from raw ECG signals to validated predictions—provides a scalable and clinically meaningful framework for early detection and monitoring of cardiac abnormalities in horses.

## Methods

**Stage 1**: Feature Engineering & Unsupervised Learning
We performed domain-informed preprocessing, including outlier removal using thresholding, ARIMA residual filtering, and delta-RR constraints. From cleaned signals, we extracted summary statistics (mean, variance) and Poincaré-based features (SD1, SD2). Dimensionality reduction was conducted via PCA, followed by clustering using Gaussian Mixture Models and hierarchical clustering to explore latent structure.

**Stage 2**: Functional Time-Series Modeling
To capture temporal dynamics, RR sequences were standardized and resampled into fixed-length vectors. Functional PCA (FPCA) was applied to model continuous-time variation and identify dominant temporal patterns. Principal component loadings were analyzed to interpret physiological changes over time.

**Stage 3**: Supervised Classification
The problem was reformulated as a binary classification task (baseline vs arrhythmia). Time series were segmented into short windows to increase sample size. Features included statistical summaries and nonlinear measures (SD1, SD2, SD1/SD2, entropy, coefficient of variation). Models included Logistic Regression, Lasso-regularized Logistic Regression, and Linear Discriminant Analysis, evaluated using Leave-One-Horse-Out cross-validation to ensure generalization.

## Results

Unsupervised methods revealed clear separation between baseline and post-symptom states, with PCA capturing key variability structure. FPCA identified critical time windows and temporal patterns associated with arrhythmia onset and recovery. The best supervised model (Lasso Logistic Regression) achieved an AUC of 0.92 with high sensitivity. Key predictive features included increased short-term variability (SD1, CV) for arrhythmia and higher long-term stability (SD2) for normal rhythm.
---
layout: page
title: Warehouse Work Queue Time Prediction
description: Combines statistical modeling and machine learning to enable proactive workforce planning and operational optimization
img: 
importance: 2
category: capstone
---

## Project Overview

This project was conducted as part of the capstone project for the [Master of Science in Applied Data Science (MADS)](https://www.cmu.edu/dietrich/statistics-datascience/academics/mads/index.html) program at Carnegie Mellon University, in collaboration with [Lucas Systems](https://www.lucasware.com/). The project focuses on developing predictive models for warehouse operations. The objective is to estimate the expected completion time of work queues using large-scale execution data collected from real warehouse environments. By leveraging over 100 million task-level records across multiple facilities operating under a shared voice-directed system (Jennifer), this project combines statistical modeling and machine learning to enable proactive workforce planning and operational optimization.

## Background

Accurately predicting how long a sequence of warehouse tasks will take is critical for staffing decisions, workload balancing, and operational efficiency. However, this problem is challenging due to heterogeneity across warehouses, including differences in layouts, product characteristics, and workflows. Traditional rule-based approaches often fail to capture these complexities or generalize across environments.

This project addresses these challenges by integrating multiple data sources—including activity logs, product attributes, spatial layouts, and distance matrices—to build a unified modeling framework. By transforming raw execution data into structured features that capture both operational and spatial dynamics, the project aims to provide accurate and interpretable predictions of queue completion time before work begins.

## Methods

The modeling pipeline begins with large-scale data engineering across multiple relational datasets. Task-level activity logs are first sorted chronologically per worker, and task durations are computed using timestamp differences. Data is then cleaned by removing assignment initialization events and filtering out unrealistic time gaps caused by breaks or interruptions. The activity data is enriched through joins with product and location tables, enabling the incorporation of handling difficulty (e.g., weight, volume) and spatial structure (aisle, bay, level).

Feature engineering plays a central role in the analysis. Key features include travel distance between consecutive tasks (derived from precomputed distance matrices), categorical encodings of work types, and log-transformed variables to address strong right-skewness in task duration. Exploratory analysis reveals that travel distance, work type (WorkCode), and spatial attributes are among the strongest drivers of task time variability.

Multiple modeling approaches are implemented to balance predictive performance and interpretability. Linear regression serves as a baseline to quantify marginal effects of operational factors. Regularized regression methods such as LASSO and ElasticNet are applied for feature selection and robustness in the presence of correlated predictors. Tree-based models, including decision trees, capture nonlinear interactions and provide feature importance insights. Neural networks are explored for flexibility but are primarily used as benchmarks due to their limited interpretability in operational settings.

## Implications

This project demonstrates that combining structured feature engineering with interpretable statistical models can effectively predict warehouse task completion time at scale. The resulting system enables managers to forecast workload duration before execution, optimize staffing levels, and identify operational bottlenecks such as inefficient layouts or high-cost task types.

Beyond prediction accuracy, a key contribution of this work is its emphasis on interpretability and generalization. By identifying core drivers such as travel distance, product handling complexity, and workflow structure, the models provide actionable insights that can be applied across different warehouse environments. This positions the framework as a scalable decision-support tool for improving efficiency, reducing operational costs, and enabling data-driven workforce planning in modern logistics systems.
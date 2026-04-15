---
layout: page
title: Formula 1 Press Conferences NLP
description: Investigates how Formula 1 drivers differ in communication style and whether language alone can reliably identify individual speakers

img: 
importance: 5
category: Data Science
---
## Project Overview

This project investigates linguistic patterns in official FIA Formula 1 press-conference transcripts (2022–2025) to understand how drivers differ in communication style and whether language alone can reliably identify individual speakers. Using natural language processing (NLP) and statistical modeling techniques, the study explores stylistic variation, media presence, and speaker classification within a large corpus of professional sports interviews. The analysis integrates descriptive statistics, unsupervised learning, and regularized classification models to uncover both interpretable linguistic patterns and predictive signals.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/f1_conference.jpg" title="Press Conference" class="img-fluid rounded z-depth-1" style="height:200px;"%}
    </div>
</div>
<div class="caption">
    Example picutre of FIA Formula 1 press-conference, from Formula 1 News - 2024 Monaco GP Post-Race Press Conference
</div>

## LLM Application
Building on the core analysis of linguistic patterns and speaker classification, I developed an end-to-end NLP application that operationalizes these insights into an interactive tool. The system analyzes Formula 1 press conference transcripts and predicts whether the speaker is Max Verstappen using a stylometric classification model. The workflow begins with collecting and preprocessing unstructured text data, followed by feature extraction using linguistic signals such as part-of-speech distributions, keyword indicators, and pronoun usage. A trained LASSO logistic regression model then produces a probabilistic prediction based on these features.

To enhance interpretability, I integrated a generative AI layer using an LLM, which translates structured model outputs into clear, natural-language explanations grounded in the underlying linguistic patterns. The system is deployed through a lightweight interface that allows users to input custom text and receive both predictions and explanations in real time. The screenshot below shows the final user interface and example output of the application.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/f1_llm.jpg" title="LLM Application Demo" class="img-fluid rounded z-depth-1" style="height:200px;"%}
    </div>
</div>
<div class="caption">
    Application interface displaying transcript input, prediction results, and LLM explanation
</div>

## Corpus and Data Description

The dataset consists of official FIA Formula 1 press-conference transcripts sourced from Formula1.com, covering four seasons (2022–2025). Each document corresponds to a single driver’s responses within a press conference and is filtered to include only transcripts with at least 200 tokens to ensure sufficient linguistic content.

The final corpus contains 1,048 documents and approximately 947,000 tokens. Each document is labeled with contextual metadata, including driver, team, season, Grand Prix, and press-conference type. This structured dataset enables both cross-sectional and temporal analysis of linguistic behavior across drivers and competitive contexts.

## Analytical Framework

The study is organized around three primary analytical components. First, media presence is quantified through token volume, aggregated by driver and season, to examine how communication exposure correlates with competitive performance and visibility. This analysis focuses on the most prominent drivers to capture meaningful variation in media engagement.

Second, linguistic style is characterized using part-of-speech (POS) distributions extracted via UDPipe. Transcripts are aggregated at the driver level, and POS proportions are normalized to control for differences in speech length. Hierarchical clustering (Ward’s D2) and Principal Component Analysis (PCA) are applied to identify stylistic groupings and latent dimensions of variation across drivers.

Third, a supervised classification task is formulated to distinguish whether a transcript was spoken by Max Verstappen. The dataset is split chronologically to preserve temporal structure, with training data from 2022–2024 and a fully held-out test set from 2025. A LASSO-regularized logistic regression model is trained using a rich feature set, including lexical metrics, keyword indicators, pronoun usage, and POS distributions, enabling both predictive performance and feature interpretability.

<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/f1_pca.jpg" title="PCA Biplot" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/f1_clustering.png" title="Dendrogram" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, PCA biplot of drivers by POS features; On the right, hierarchical clusters dendrogram of drives (5 clusters)
</div>

## Key Findings

The analysis reveals that token volume closely tracks competitive relevance, with higher-performing drivers receiving greater media exposure. Stylometric analysis based on POS distributions uncovers meaningful groupings, including clusters of rookie drivers, linguistic similarities among Spanish-speaking drivers, and shared stylistic patterns among recent world champions.

The speaker classification model achieves strong performance, with 87.9% validation accuracy and 85.8% accuracy on the held-out 2025 test set. Key linguistic indicators associated with Max Verstappen include greater use of evaluative and outcome-focused language, shorter average word length, and reduced reliance on particles and descriptive modifiers.

## Implications

This project demonstrates that linguistic features alone can provide meaningful signals for both exploratory analysis and predictive modeling in real-world text data. By combining interpretable statistical methods with NLP techniques, the study highlights how communication style reflects both individual identity and broader contextual factors such as performance and experience.

Beyond the Formula 1 domain, this framework can be extended to authorship attribution, behavioral profiling, and media analysis in other settings. The results illustrate the value of integrating stylometric analysis with machine learning to extract actionable insights from large-scale textual data.
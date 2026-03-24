---
layout: page
title: E-Commerce Database and Dashboard Design
description: This project delivers a scalable system for monitoring business performance and generating actionable insights for the admin team.

img: 
importance: 4
category: Visualization and Analytics
---

## Project Overview

This project was developed for [LUXRUG](https://www.amazon.com/stores/Luxrug/page/B7BECA18-0B22-4580-865B-A6FEBAC94BF9?lp_asin=B0DBYYVZMX&ref_=ast_bln&store_ref=bl_ast_dp_brandlogo_sto), an early-stage e-commerce brand specializing in rug sales on Amazon. As the company launched in October 2024, the project focuses on building a data infrastructure and interactive analytics dashboard to support data-driven decision-making from limited but rapidly growing data. By combining data engineering, database design, and interactive visualization, this project delivers a scalable system for monitoring business performance and generating actionable insights for the admin team.

As a newly established Amazon seller, LUXRUG faced challenges in tracking performance metrics and understanding revenue trends due to fragmented and evolving data sources. Raw data exports from Amazon Seller Central—including sales, returns, and customer reviews—require significant preprocessing before they can be used for analysis.

This project addresses these challenges by designing a centralized data pipeline and an intuitive dashboard tailored to key user needs. Through direct communication with stakeholders, core user stories were identified, focusing on revenue tracking, product performance, and operational monitoring. The goal is to transform raw transactional data into a structured, accessible system that enables timely and informed business decisions.

## Analytical Approach & Data Infrastructure

The project begins with building a robust data foundation through structured data engineering and database design. A normalized relational schema is developed to integrate sales, returns, and review data, ensuring consistency, scalability, and long-term usability. Historical datasets are cleaned, standardized, and loaded into the system with careful handling of timestamps, currency formats, and categorical variables.

To support ongoing operations, an automated daily update pipeline is implemented to ingest new data from Amazon Seller Central. This pipeline ensures data integrity through deduplication and incremental updates, maintaining a continuously synchronized and reliable database.

On top of this infrastructure, an interactive dashboard is developed using R Shiny with a strong focus on user-centric design. Initial lo-fi prototypes are created based on stakeholder requirements to guide development. The final product features dynamic filtering, time-series analysis, and KPI tracking, enabling users to explore revenue patterns, monitor product performance, and identify trends or anomalies in real time.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/luxrug-screenshot.png" title="Screenshot of Dashboard" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Interactive dashboard, showcasing key features and sales metrics
</div>

## Implications

This project establishes a complete analytics workflow—from raw data ingestion to interactive visualization—for a growing e-commerce business. The dashboard enables LUXRUG to track revenue performance, evaluate product-level trends, and respond quickly to operational changes such as returns or shifts in demand.

Beyond immediate insights, the system provides a scalable foundation for future analytics initiatives, including customer segmentation, A/B testing, and marketing optimization. By transforming fragmented data into a structured and interactive decision-support tool, this project empowers the company to make more informed strategic decisions and scale efficiently in a competitive e-commerce environment.
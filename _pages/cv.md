---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* Ph.D in Computer Science, Télécom SudParis, 2028 (expected)
* Masters in Data Science and Computing, [SSSIHL](https://www.sssihl.edu.in/), 2024
* Bachelors in Computer Applications, [SSSIHL](https://www.sssihl.edu.in/), 2021

<!-- Work experience
======
* Spring 2024: Academic Pages Collaborator
  * GitHub University
  * Duties includes: Updates and improvements to template
  * Supervisor: The Users
 -->
  
Skills
======
* Machine Learning and Data Science
  * Speech and Language Technologies (Focus on Low Resource Languages)
  * Natural Language Processing (Transformers, Word Embeddings, Text Classification)
  * Time Series Analysis and Forecasting
  * Visual Language Modelling 
  * Data Visualization and EDA
* Computer Science
  * Python (NumPy, Pandas, Matplotlib, Scikit-learn, PyTorch, Transformers)
  * C/C++ (Memory Management, Pointers, Data Structures)
  * SQL (Queries, Joins, Normalization)
  * LaTeX (Document Preparation, Beamer)
* Mathematics and Statistics
  * Multivariate Statistical Analysis
  * Linear Algebra
  * Stochastic Processes
  * Optimization Techniques

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
<!-- Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul> -->
  
Other Activities
======
* Currently helping a team of 2 undergraduate students at [HUST](https://ai4life.hust.edu.vn/) for their research projects on VLM on Medical Data.
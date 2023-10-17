---
layout: page
title: Research
permalink: /projects/
description: A growing collection of my projects.
nav: true
nav_order: 2
display_categories: [work, fun]
horizontal: false
---
**Current**

* **3D Paired CT Partition and Semantic Mask Generation**, *Oct. 2022- present*
    * A Yang Lab, Imperial College London
    * Ongoing


    Current challenges demand paired image and mask generation due to the scarcity of large, labelled datasets required for training AI models for accurate diagnosis, prognosis, and treatment planning. I hypothesize that a latent representation that can be reconstructed to an image in the pixel space can also be projected back into the corresponding semantic map of that image, which makes it possible to generate paired images and masks at the same time. This project is a part of my master thesis at Imperial.

**Past Projects**

* **A FSMIL Model for PET/CT Lymphoma Analysis**, *Sep. 2021 - Jun. 2022*
    *  Key Laboratory of Intelligent Computing in Medical Image, Northeastern University
    *  [*CMPB*]()


    The application of deep learning models in lymphoma subtype prediction is limited due to the difficulty in collecting large patient cohorts for each subtype and expert annotations, given the lower incidence of NHL compared to other cancers and the limited availability of advanced imaging technologies such as PET/CT. Radiomics is a popular methodology for lymphoma analysis characterized by its standardized workflow. However, its effectiveness heavily relies on the accuracy of manual ROI selection, a labour-intensive process with reproducibility issues. This issue arises from the wide distribution of non-Hodgkin lymph nodes across multiple human body parts and the intratumoral heterogeneity between involved sites. The practical impossibility of performing a biopsy on each lymph node and the subjective judgment involved in ROI acquisition often lead to inconsistencies and the inclusion of regions with irrelevant or misleading labels in the set of ROIs, which can undermine the model's accuracy and reliability. This issue is more pronounced in studies with smaller sample sizes.

    After conducting a literature review to understand the background, I proposed a bag-level few-shot learning method to overcome the unique challenges of lymphoma subtype prediction: data scarcity and complexities of manual ROI selection. This study is a preliminary exploration of the AI-enabled and non-invasive solution to lymphoma analysis. A future direction is to generalize the current framework to new datasets, including other lymphoma subtypes and benign lesions such as lymph node tuberculosis, the reactive hyperplasia of the lymph node, and lymphadenitis.

* **MIL for Lung CT COVID-19 Indentification**, *Sep 2020 - Aug 2021*
    *  Key Laboratory of Intelligent Computing in Medical Image, Northeastern University
    *  [*CMPB*](https://www.sciencedirect.com/science/article/pii/S0169260721004806)


    Given the global spread of the novel coronavirus disease 2019 (COVID-19), there is an urgent need for a method to accurately differentiate COVID-19 from community-acquired pneumonia (CAP). The challenge lies in the spatial uncertainty and morphological diversity of COVID-19 lesions in the lungs, coupled with their subtle differences from CAP, making differential diagnosis challenging.

    To address this, I introduced a multiple instance learning (MIL) model. I also compared the model's performance to that of a radiologist with 16 years of experience. The radiologist achieved an accuracy of 66.80%, which aligns with the previously reported range of 60–83%. In contrast, the model exhibited an accuracy of 95.9%, highlighting the potential of the proposed method to enhance the differentiation of COVID-19 from CAP.

* **MIL for Lung CT COPD Identification**, *2020*
    * Key Laboratory of Intelligent Computing in Medical Image, Northeastern University
    * [*Phys Med Biol*](https://pubmed.ncbi.nlm.nih.gov/32235077/)


    I built and compared the performance of three machine learning models in the classification task. After dimension reduction through principle component analysis (PCA), features are input into three MIL methods: Citation k-Nearest-Neighbor (Citation-KNN), multiple instance support vector machine, and expectation-maximization diverse density.


<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>

---
layout: default
title: SATIN Public Leaderboard
---

# SATIN Tasks
<p>The SATIN metadataset is designed to evaluate the capabilities of modern machine learning models on a broad range of remote sensing (RS) image classification tasks. The creators of this benchmark intend for it to be primarily used for evaluating vision-language (VL) models in a zero- or low-shot classification setting. They also aim for it to be a living benchmark that undergoes incremental improvements and expansions over time.</p>

<h2>The tasks in SATIN are as follows:</h2>

<ol>
    <li><strong>Land Cover:</strong> This task involves classifying images based on the biophysical surface characteristics of the Earth, such as vegetation type or the presence of artificial structures. Examples of broad land cover classes include forest, grassland, water, and building. Some datasets used for this task are SAT-4, SAT-6, and NaSC-TG2.</li>
    <li><strong>Land Use:</strong> This task focuses on classifying images based on the economic and social functions of the areas depicted. Land use classes provide more granularity than land cover categories, with labels such as residential, industrial, parking lot, church, storage tank, and water. Datasets used for this task include WHU-RS19, RSSCN7, RSC11, and EuroSAT.</li>
    <li><strong>Hierarchical Land Use:</strong> This task evaluates the ability to classify land use across different levels of granularity. Images are annotated with different labels depending on the hierarchical level. For instance, an image of a bridge could be labeled as transportation area → highway land → bridge. Datasets used for this task include MillionAID and RSI-CB256.</li>
    <li><strong>Complex Scenes:</strong> This task involves classifying images with large fields of view that can capture multiple land use categories. These images may contain one or more land use labels. Datasets used for this task include UCM Land Use, AID, MLRSNet, and MultiScene.</li>
    <li><strong>Rare Scenes:</strong> This task focuses on classifying imagery into rare and specialized categories that fall outside land cover and land use, such as hurricane damage, wind turbines, crop varieties, or aerosol classes. Each image is annotated with a single category label. Datasets used for this task include AWTP, Post Hurricane, SISI, Canadian Cropland, and USTC-SmokeRS.</li>
    <li><strong>False Colour Scenes:</strong> This task involves classifying images that are not in true-color RGB format but instead map near-infrared, red, and green bands to red, green, and blue channels. The imagery in these datasets is labeled with a single land use or land cover class. Datasets used for this task include BC Scenes and BCS Scenes.</li>
</ol>

<div class="dataset-web-container">
  <img src="{{ site.baseurl }}/assets/images/Datasets_Overview.svg" alt="SATIN datasets web">
</div>

<p>The evaluation metrics for SATIN are based on accuracy, measured at three levels: per dataset, per task, and overall. For most datasets, a single ground-truth label is given per image, and the dataset accuracy score is calculated as the fraction of correct predictions. For images with multiple ground-truth labels, the Jaccard Index is used to calculate image classification accuracy, and the dataset accuracy is the arithmetic mean of image accuracies. For images with hierarchical labels, image classification accuracy is determined as the arithmetic mean of prediction accuracies at each level, and the dataset accuracy is the arithmetic mean of image accuracies.

Macro-average metrics are used to track progress across tasks and the overall SATIN metric. The geometric mean of dataset accuracy scores is used for each task, and the geometric mean across datasets is used as the overall SATIN metric.
</p>

---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
# layout: home
layout: default
title: SATIN - A Remote Sensing Imagery Benchmark
permalink: /
---

<!-- Logo and Text -->
<div style="display: flex; align-items: center; justify-content: center;">
  <img href="{{ site.baseurl }}" class="large-logo" src="{{ site.baseurl }}/assets/images/gold_logo_transparent.png" alt="Large Logo" style="margin-right: 15px;" />
  <div>
  <p class="satin-title" style="margin: 0;">SATIN</p>
  <p class="satin-subtitle-text">
    <span class="satin-subtitle-uc" style="margin: 0;">SAT</span><span class="satin-subtitle-lc" style="margin: 0;">ellite </span>
    <span class="satin-subtitle-uc" style="margin: 0;">I</span><span class="satin-subtitle-lc" style="margin: 0;">mage</span><span class="satin-subtitle-uc" style="margin: 0;">N</span><span class="satin-subtitle-lc" style="margin: 0;">et</span>
  </p>
  </div>
</div>
<br>


<div class="small-logos-container" style="display: flex; justify-content: center; margin-top: 10px;">
  <a href="https://caml-lab.com/">
    <img class="small-logo" src="{{ site.baseurl }}/assets/images/caml_logo.png" alt="Small Logo 1" />
  </a>
  <a href="https://caml-lab.com/">
    <img class="small-logo" src="{{ site.baseurl }}/assets/images/cam_logo.svg" alt="Small Logo 1" />
  </a>
  <a href="https://visailab.github.io/index.html">
    <img class="small-logo" src="{{ site.baseurl }}/assets/images/vail_logo.png" alt="Small Logo 1" />
  </a>
  <a href="https://visailab.github.io/index.html">
    <img class="small-logo" src="{{ site.baseurl }}/assets/images/hku_logo.png" alt="Small Logo 2" />
  </a>
</div>
<!-- Institution Logos
<div class="logo-container">
  <a href="https://caml-lab.com/">
    <img class="small-logo" src="{{ site.baseurl }}/assets/images/caml_logo.png" alt="Small Logo 1" />
  </a>
  <a href="https://visailab.github.io/index.html">
    <img class="small-logo" src="{{ site.baseurl }}/assets/images/vail_logo.png" alt="Small Logo 1" />
  </a>
  <a href="https://caml-lab.com/">
    <img class="small-logo" src="{{ site.baseurl }}/assets/images/cam_logo.svg" alt="Small Logo 1" />
  </a>
  <a href="https://visailab.github.io/index.html">
    <img class="small-logo" src="{{ site.baseurl }}/assets/images/hku_logo.png" alt="Small Logo 2" />
  </a>
</div>
-->
<br>

#  SATIN: A Multi-Task Remote Sensing Metadataset
<div style="text-align: justify;">

  <p>The Satellite ImageNet (SATIN) metadataset is a comprehensive collection of resources designed to train, evaluate, and analyze vision-language (VL) models for classifying satellite and aerial imagery. SATIN consists of:</p>
  <ol>
    <li>A metadataset curated from 27 existing remote sensing datasets, spanning a wide range of tasks, resolutions, fields of view, and geographic areas. These datasets are organized into six distinct tasks, featuring over 250 distinct class labels, and imagery resolutions spanning five orders of magnitude.</li>
    <li>A zero-shot transfer classification approach, which enables the evaluation of VL models across various tasks and datasets without the need for fixed category labels. This makes it possible to test a single VL model across different tasks, addressing the challenges of image diversity, label hierarchies, and scene complexity in remote sensing classification.</li>
    <li>A streamlined benchmark, leveraging platforms like Hugging Face Datasets, to provide a seamless experience for hosting, downloading, and evaluating models and datasets with minimal friction.</li>
    <li>A public leaderboard for tracking the performance of VL models on the SATIN benchmark, promoting research and development in the remote sensing domain.</li>
  </ol>
  <p>The format of the SATIN metadataset is designed to be model-agnostic, allowing any VL model capable of processing satellite and aerial imagery to participate. The ultimate goal of SATIN is to drive research and progress in the development of robust and accurate models for interpreting remote sensing imagery, with potential applications in land-use planning, natural resource management, food security, and environmental risk management.</p>



</div>


<div class="button-row" style="display: flex; justify-content: center; margin-top: 20px;">
  <a href="{{ site.paper_link }}" class="button">Read the paper</a>
  <a href="{{ site.github_link }}" class="button">Look at the code</a>
  <a href="{{ site.huggingface_link }}" class="button">Download the data</a>
  <a href="{{ site.baseurl }}/_pages/tasks" class="button">Explore the tasks</a>
  <a href="{{ site.baseurl }}/_pages/leaderboard" class="button">Check out the leaderboard</a>
</div>
<!--<div class="button-row" style="display: flex; justify-content: center; margin-top: 20px;">
  <a href="{{ site.baseurl }}/_pages/tasks" class="button">Explore the tasks</a>
  <a href="{{ site.baseurl }}/_pages/leaderboard" class="button">Check out the leaderboard</a>
</div>-->

<!--
## Citation
If you have used our benchmark or have found our work useful in your research, please cite our paper:

```bibtex
@article{roberts2023satin,
  title        = {SATIN: A Multi-Task Metadataset for Classifying Satellite Imagery using Vision-Language Models},
  author       = {Jonathan Roberts, Kai Han and Samuel Albanie},
  year         = {2023},
  journal      = {arXiv preprint arXiv:INSERT_NUM}
}
```
-->


## Any questions?
If you have any questions or feedback about our work, please [contact us](mailto:jdr53@cam.ac.uk).

---
layout: page
permalink: /publications/
title: publications
description: ""
nav: true
nav_order: 1
display_categories: ["Publications", "Master thesis", "Bachelor thesis"]
horizontal: false
---

<!-- pages/publications.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  
  {%- if category == "Publications" -%}
    
  {%- endif -%}
  
  {%- if category == "Master thesis" -%}
  
    <li class="masthead__menu-item">
      <a href="https://github.com/NiekMooij/NiekMooij.github.io/tree/main/assets/pdf/NiekMooijMasterThesisGeneratingMaximalIndependentSetsUsingLotkaVolterraDynamics.pdf">M.N. Mooij. "Generating Maximal Independent Sets Using Lotka-Volterra Dynamics”. Master thesis. Utrecht University, 2022.</a>
    </li>

  {%- endif -%}
  
  {%- if category == "Bachelor thesis" -%}

    <li class="masthead__menu-item">
      <a href="https://github.com/NiekMooij/NiekMooij.github.io/tree/main/assets/pdf/NiekMooijBachelorThesisEntropyAndOptionPricing.pdf">M.N. Mooij. "Entropy and Option Pricing”. Bachelor thesis. Utrecht University, 2019.</a>
    </li>
    
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

 


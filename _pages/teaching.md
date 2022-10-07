---
layout: page
permalink: /teaching/
title: teaching
description: Courses I am teaching now (and have taught in the past)
nav: true
nav_order: 5
display_categories: [current, past]
horizontal: false
---

<!-- pages/teaching.md -->
<div class="teaching">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized teaching -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_teaching = site.teaching | where: "category", category -%}
  {%- assign sorted_teaching = categorized_teaching | sort: "importance" %}
  <!-- Generate cards for each project -->
  {%- for project in sorted_teaching -%}
      {% include teaching.html %}
  {%- endfor %}
  </div>
{%- endif -%}
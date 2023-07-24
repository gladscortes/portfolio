---
layout: page
title: Projects
permalink: /
display_categories: [Power BI, SQL, Excel, R]
---

<div style="margin-bottom:4rem;">
        <p>
            I am a data analyst based in the Philippines.
        </p>
  </div>

<!-- pages/projects.md -->
<div class="projects">

  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {% assign categorized_projects = site.posts | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.html %}
    {% endfor %}
  </div>
  {% endfor %}

</div>

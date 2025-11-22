---
layout: default
title: Projects
---

<section class="projects-page">
  <h1 class="page-title">Research Projects</h1>
  <p class="page-subtitle">
    Selected research projects of the Neuro-Symbolic Artificial Intelligence (NSAI) Lab,
    including ongoing and completed work on neural-symbolic learning and
    knowledge-augmented intelligent systems.
  </p>

  {% assign projs = site.projectpage | sort: "start_year" | reverse %}

  <div class="project-grid project-grid-page">
    {% for proj in projs %}
      <article class="project-card project-card-page">
        <h2 class="project-title">
          <a href="{{ proj.url | relative_url }}">{{ proj.title }}</a>
        </h2>

        {% if proj.short_desc %}
        <p class="project-short">{{ proj.short_desc }}</p>
        {% endif %}

        <p class="project-meta-line">
          {% if proj.pi %}
            <span class="project-meta-label">PI:</span> {{ proj.pi }}
          {% endif %}
          {% if proj.start_year or proj.end_year or proj.status %}
            <span class="project-meta-sep">·</span>
          {% endif %}
          {% if proj.start_year or proj.end_year %}
            <span class="project-meta-label">Duration:</span>
            {% if proj.start_year %}{{ proj.start_year }}{% endif %}
            {% if proj.end_year %}–{{ proj.end_year }}{% endif %}
          {% endif %}
          {% if proj.status %}
            <span class="project-meta-sep">·</span>
            <span class="project-status">{{ proj.status }}</span>
          {% endif %}
        </p>

        {% if proj.tags %}
        <p class="project-tags">
          {% for t in proj.tags %}
            <span class="project-tag">{{ t }}</span>
          {% endfor %}
        </p>
        {% endif %}

        <p class="project-more-link">
          <a href="{{ proj.url | relative_url }}" class="btn-link">View project details →</a>
        </p>
      </article>
    {% endfor %}
  </div>
</section>

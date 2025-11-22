---
layout: default
title: People
---

<section class="people-page">
  <h1 class="page-title">People</h1>

  {% for group in site.data.people %}
    <h2 class="people-role">{{ group.role }}</h2>

    <div class="people-grid">
      {% for m in group.members %}
        <div class="people-card">

          {% assign img = m.img | default: "" %}
          {% if img == "" %}
            {% assign final_img = "/assets/img/people/default.png" %}
          {% else %}
            {% assign final_img = "/assets/img/people/" | append: img %}
          {% endif %}

          <div class="people-photo">
            <img src="{{ final_img | relative_url }}">
          </div>

          <div class="people-info">
            <p class="people-name">{{ m.name }}</p>

            {% if m.email %}
            <p class="people-email">{{ m.email }}</p>
            {% endif %}

            {% if m.interests %}
            <ul class="people-interests">
              {% for it in m.interests %}
                <li>{{ it }}</li>
              {% endfor %}
            </ul>
            {% endif %}

          </div>
        </div>
      {% endfor %}
    </div>
  {% endfor %}
</section>

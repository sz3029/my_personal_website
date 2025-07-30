---
title: Work Experience
layout: single # Or 'home', 'archive', or a custom layout you create
permalink: /work-experience/
author_profile: true # Optional: to show your author profile sidebar
---

<!-- <h1 class="page__title">My Work Experience</h1> -->
{% assign timeline_entries = site.data.timeline | sort: 'start_date' | reverse %}
{% for entry in timeline_entries %}
  <div class="timeline-item">
    <h2>{{ entry.title }} at {{ entry.company }}</h2>
    <p class="timeline-dates">{{ entry.start_date }} &ndash; {{ entry.end_date }}</p>
    <p class="timeline-location"><i class="fas fa-location-dot"></i> {{ entry.location }}</p>
    <div class="timeline-description">
      {{ entry.description | markdownify }}
    </div>
    {% if entry.achievements %}
      <ul class="timeline-achievements">
        {% for achievement in entry.achievements %}
          <li>{{ achievement }}</li>
        {% endfor %}
      </ul>
    {% endif %}
  </div>
{% endfor %}
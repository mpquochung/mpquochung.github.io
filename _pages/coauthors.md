---
layout: page
permalink: /coauthors/
title: Co-authors
description: The researchers I have had the pleasure of learning from and working with. As of updated in August 2026.
nav: true
nav_order: 3
---

<p class="coauthors-intro">
  One soul cannot be the whole world, and I am deeply grateful to every co-author whose ideas, dedication, and collaboration have shaped the work we accomplished together. Onward we go!
</p>

{% assign coauthors = site.data.collaborators | where: 'group', 'coauthor' %}
{% assign advisors = site.data.collaborators | where: 'group', 'advisor' %}

<section class="collaborator-section" aria-labelledby="advisors-heading">
  <div class="collaborator-section__heading">
    <p>Mentors and supervisors</p>
    <h2 id="advisors-heading">Advisors</h2>
  </div>
  <div class="coauthor-grid">
    {% for author in advisors %}
      {% include coauthor-card.liquid author=author %}
    {% endfor %}
  </div>
</section>

<section class="collaborator-section" aria-labelledby="coauthors-heading">
  <div class="collaborator-section__heading">
    <p>Research collaborators</p>
    <h2 id="coauthors-heading">Co-authors</h2>
  </div>
  {% if coauthors.size > 0 %}
    <div class="coauthor-grid">
      {% for author in coauthors %}
        {% include coauthor-card.liquid author=author %}
      {% endfor %}
    </div>
  {% else %}
    <p class="collaborator-section__empty">Co-author profiles are coming soon.</p>
  {% endif %}
</section>

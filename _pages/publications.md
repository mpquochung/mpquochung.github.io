---
layout: page
permalink: /publications/
title: Publications
description: Working on some cool things, Stay tuned.
nav: true
nav_order: 2
---

## Conference Papers

<div class="publications">
  {% bibliography --group_by none --query @inproceedings %}
</div>

## Journal Articles

<div class="publications">
  {% bibliography --group_by none --query @article %}
</div>

## arXiv Preprints

<div class="publications">
  {% bibliography --group_by none --query @misc %}
</div>


<style>
  .publications .publication-extra {
    display: none;
  }

  .post article > h2 {
    margin-top: 2rem;
    padding-bottom: 0.5rem;
    border-bottom: 1px solid var(--global-divider-color);
  }

  .post article > h2:first-of-type {
    margin-top: 0;
  }

  .publication-toggle {
    margin: 0.25rem 0 1.75rem;
    padding: 0;
    color: var(--global-theme-color);
    font-weight: 600;
    text-decoration: underline;
    text-underline-offset: 0.2em;
    background: transparent;
    border: 0;
    cursor: pointer;
  }

  .publication-toggle:hover,
  .publication-toggle:focus {
    color: var(--global-hover-color);
  }
</style>

<script>
  document.addEventListener("DOMContentLoaded", () => {
    document.querySelectorAll(".post article > .publications").forEach((publicationList) => {
      const entries = Array.from(publicationList.querySelectorAll("ol.bibliography > li"));
      if (entries.length <= 3) return;

      entries.slice(3).forEach((entry) => entry.classList.add("publication-extra"));

      const toggle = document.createElement("button");
      toggle.type = "button";
      toggle.className = "publication-toggle";
      toggle.textContent = "Show more";
      toggle.setAttribute("aria-expanded", "false");

      toggle.addEventListener("click", () => {
        const expanded = toggle.getAttribute("aria-expanded") === "true";
        entries.slice(3).forEach((entry) => entry.classList.toggle("publication-extra", expanded));
        toggle.textContent = expanded ? "Show more" : "Show less";
        toggle.setAttribute("aria-expanded", String(!expanded));
      });

      publicationList.after(toggle);
    });
  });
</script>

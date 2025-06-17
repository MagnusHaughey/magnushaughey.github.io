---
layout: page
title: Publications
permalink: /publications/
order: 3
---

{% assign sorted_publications = site.publications | sort: "year" | reverse %}
<div class="publications-list">
  {% for publication in sorted_publications %}
    <div class="publication">
        <img class="publication-image" src="{{ publication.image }}" alt="Publication Image">
        <div class="publication-details">
            <h3 class="publication-title">{{ publication.title }}</h3>
            {% assign highlighted_authors = publication.authors | replace: "Magnus Haughey", "<strong>Magnus Haughey</strong>" %}
            <p class="publication-authors">{{ highlighted_authors | markdownify }}</p>
            <p class="publication-journal">{{ publication.journal }}, {{ publication.year }}</p>
            <p class="publication-doi">
                DOI: <a href="{{ publication.doi }}" target="_blank">{{ publication.doi }}</a>
            </p>
        </div>
    </div>
  {% endfor %}
</div>

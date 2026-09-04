---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

<p class="publication-legend"><sup>*</sup> Equal contribution; <sup>†</sup> Corresponding author.</p>

<section class="publication-section" aria-labelledby="published-work">
  <h2 id="published-work">Publications</h2>
  {% assign publication_years = site.data.publications.publications | group_by: "year" %}
  {% for year in publication_years %}
    <h3 class="pub-year">{{ year.name }}</h3>
    <div class="publication-list">
      {% for item in year.items %}
        {% include publication-entry.html item=item %}
      {% endfor %}
    </div>
  {% endfor %}
</section>

<section class="publication-section publication-section--preprints" aria-labelledby="preprint-work">
  <h2 id="preprint-work">Preprints</h2>
  {% assign preprint_years = site.data.publications.preprints | group_by: "year" %}
  {% for year in preprint_years %}
    <h3 class="pub-year">{{ year.name }}</h3>
    <div class="publication-list">
      {% for item in year.items %}
        {% include publication-entry.html item=item %}
      {% endfor %}
    </div>
  {% endfor %}
</section>

{% if site.data.publications.books and site.data.publications.books != empty %}
<section class="book-section" aria-labelledby="books">
  <h2 id="books">Book</h2>
  <ul class="book-list">
    {% for book in site.data.publications.books %}
      <li><strong>{{ book.authors }}</strong>，《{{ book.title }}》，{{ book.publisher }}，{{ book.year }}。</li>
    {% endfor %}
  </ul>
</section>
{% endif %}

<p class="source-note">更完整的历史成果清单可参见<a href="https://ssds.sufe.edu.cn/99/eb/c715a236011/page.htm">上海财经大学教师主页</a>。</p>

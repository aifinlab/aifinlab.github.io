---
layout: archive
title: "Teaching"
permalink: /teaching/
author_profile: true
---

<p class="page-intro">课程按授课时间倒序列出。课程编号、学期和教学对象以学校正式教学安排为准。</p>

{% if site.data.teaching.courses and site.data.teaching.courses != empty %}
<div class="course-list">
  {% assign teaching_terms = site.data.teaching.courses | map: "term" | uniq | sort | reverse %}
  {% for term in teaching_terms %}
    <section class="teaching-term" aria-labelledby="term-{{ term | slugify }}">
      <h2 id="term-{{ term | slugify }}">{{ term }}</h2>
      <ul>
        {% assign term_courses = site.data.teaching.courses | where: "term", term %}
        {% for course in term_courses %}
          {% include teaching-entry.html course=course %}
        {% endfor %}
      </ul>
    </section>
  {% endfor %}
</div>
{% else %}
<p class="content-pending">课程信息核验后更新。</p>
{% endif %}

<section class="teaching-awards-section" aria-labelledby="teaching-awards">
  <h2 id="teaching-awards">Selected Teaching Awards</h2>
  {% if site.data.teaching.awards and site.data.teaching.awards != empty %}
  <ul class="teaching-awards">
    {% for award in site.data.teaching.awards %}
      <li><strong>{{ award.title }}</strong>{% if award.organization %}，{{ award.organization }}{% endif %}{% if award.year %}，{{ award.year }}{% endif %}{% if award.description %}。{{ award.description }}{% endif %}。</li>
    {% endfor %}
  </ul>
  {% else %}
  <p class="content-pending">教学获奖信息核验后更新。</p>
  {% endif %}
</section>

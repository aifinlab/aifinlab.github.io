---
layout: archive
title: "Lab Members"
permalink: /lab-members/
author_profile: true
---

<p class="page-intro">AIFin Lab 聚焦 AI + 金融投资大模型研究，团队覆盖金融语料、模型训练、多模态评测、金融智能体、安全风控、量化研究和工程平台。</p>

## Director / 实验室负责人

{% include featured-person.html person=site.data.people.supervisor %}

## Team / 团队成员

{% assign lab_has_members = false %}
{% for group in site.data.people.lab_groups %}
  {% if group.members and group.members != empty %}
    {% assign lab_has_members = true %}
    <section class="people-group" aria-labelledby="lab-{{ group.key }}">
      <h3 id="lab-{{ group.key }}">{{ group.title }}</h3>
      <div class="people-grid">
        {% for person in group.members %}
          {% include member-card.html person=person %}
        {% endfor %}
      </div>
    </section>
  {% endif %}
{% endfor %}

{% unless lab_has_members %}
<p class="content-pending">教师、研究人员、行政运营、工程及学生成员资料将在获得本人确认后发布。</p>
{% endunless %}

<p class="source-note">开源项目与团队协作信息请参见 <a href="https://github.com/aifinlab">AIFin Lab on GitHub</a>。</p>

---
layout: archive
title: "Supervision"
permalink: /supervision/
author_profile: true
---

## Supervisor / 导师

{% include featured-person.html person=site.data.people.supervisor %}

## Current Students & Alumni / 在读学生与毕业生

<div class="supervision-directory">
{% assign supervision_has_members = false %}
{% for group in site.data.people.supervision_groups %}
  {% if group.members and group.members != empty %}
    {% assign supervision_has_members = true %}
    <section class="people-group" aria-labelledby="supervision-{{ group.key }}">
      <h3 id="supervision-{{ group.key }}">{{ group.title }}</h3>
      <div class="people-grid">
        {% for person in group.members %}
          {% include supervision-person.html person=person group=group %}
        {% endfor %}
      </div>
    </section>
  {% endif %}
{% endfor %}

{% unless supervision_has_members %}
<p class="content-pending">学生名单与个人资料将在获得成员确认后发布。</p>
{% endunless %}
</div>



<h2>Student Awards</h2>

{% if site.data.supervision.awards and site.data.supervision.awards != empty %}
<table class="supervision-awards">
  <thead>
    <tr>
      <th scope="col">序号</th>
      <th scope="col">奖项名称</th>
      <th scope="col">奖励年度</th>
    </tr>
  </thead>
  <tbody>
    {% for award in site.data.supervision.awards %}
    <tr>
      <td>{{ forloop.index }}</td>
      <td><strong>{{ award.title }}</strong></td>
      <td>{{ award.year }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>
{% endif %}

<h2>Prospective Students & Interns</h2>

<div class="notice-box">

<p>欢迎博士生、硕士生和研究实习生联系。申请邮件建议包含：个人简历、成绩或专业背景、感兴趣的研究方向、可投入时间，以及能代表你能力的论文、代码或项目链接。</p>

<ul>
  <li>Email: <a href="mailto:zhang.liwen@mail.shufe.edu.cn">zhang.liwen@mail.shufe.edu.cn</a></li>
  <li>Subject suggestion: <code>[Application] Name + Program/Role + Research Direction</code></li>
  <li>招生名额、学位要求与录取流程以上海财经大学当年官方政策为准。</li>
</ul>

</div>

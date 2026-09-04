---
layout: archive
title: "Talks"
permalink: /talks/
author_profile: true
---

<p class="page-intro">报告内容主要围绕金融大模型、金融 AI 评测、智能体、统计建模与量化投资展开。</p>

{% assign academic = site.data.talks.academic %}
<section class="talk-section" aria-labelledby="academic-talks">
  <h2 id="academic-talks">{{ academic.title }}</h2>
  <ul class="talk-list">
    {% for talk in academic.items %}
      {% include talk-entry.html talk=talk %}
    {% endfor %}
  </ul>
</section>

{% assign industry = site.data.talks.industry %}
<section class="talk-section" aria-labelledby="industry-talks">
  <h2 id="industry-talks">{{ industry.title }}</h2>
  <ul class="talk-list">
    {% for talk in industry.items %}
      {% include talk-entry.html talk=talk %}
    {% endfor %}
  </ul>
</section>

<p class="source-note">完整历史报告清单可参见<a href="https://ssds.sufe.edu.cn/99/eb/c715a236011/page.htm">上海财经大学教师主页</a>。</p>

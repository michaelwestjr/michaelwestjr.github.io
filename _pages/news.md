---
layout: page
permalink: /news/
title: news
description:
nav: true
nav_order: 3
---

{% assign sorted_news = site.news | sort: "date" | reverse %}

<p>
  <strong>browse by year:</strong>
  <a href="{{ '/news/2025/' | relative_url }}">2025</a> ·
  <a href="{{ '/news/2024/' | relative_url }}">2024</a> ·
  <a href="{{ '/news/2023/' | relative_url }}">2023</a> ·
  <a href="{{ '/news/2022/' | relative_url }}">2022</a> ·
  <a href="{{ '/news/2021/' | relative_url }}">2021</a> ·
  <a href="{{ '/news/2020/' | relative_url }}">2020</a> ·
  <a href="{{ '/news/2019/' | relative_url }}">2019</a>
</p>


<h2>latest</h2>
<hr>

{% for news in sorted_news limit:5 %}
  <h3>{{ news.title }}</h3>
  <p><em>{{ news.date | date: "%B %d, %Y" }}</em></p>
  {{ news.content }}
  <hr>
{% endfor %}

<p>
  <a href="{{ '/news/2025/' | relative_url }}">See all 2025 news →</a>
</p>
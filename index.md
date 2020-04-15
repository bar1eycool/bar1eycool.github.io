---
title: Home
---

## Hi

This is my blog.

<!--- iterate categories --->

## Categories
{% for category in site.categories %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in category[1] %}
      <li>{{ post.date | date: "%Y/%m/%d"}} - <a href="{{ post.url }}">{{ post.title }}</a></li>
      <p style="text-align: left;">{{ post.excerpt }} </p>
    {% endfor %}
  </ul>
{% endfor %}

<!--- * [First post]({% post_url /2020/2020-04-12-first-post %}) --->
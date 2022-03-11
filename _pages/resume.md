---
layout: resume
permalink: /resume/
title: Resume
---

<div class="resume">
  {% for category in site.categories %}
    <div class="archive-group">
      {% capture category_name %}{{ category | first }}{% endcapture %}
      <div id="#{{ category_name | slugize }}"></div>
      <p></p>
      <h1 class="page">{{ category_name }}</h1>
      <a name="{{ category_name | slugize }}"></a>
        {% for experience in site.posts %}
          {% if experience.categories[0] == category_name %}
            <article class="resume">
              <a href="{{ site.baseurl }}{{ post.url }}">
                <h2>{{ experience.title }}</h2>
                <h3>{{ experience.subtitle }}</h3>
                <h4>{{ experience.startdate }} - {{ experience.enddate }}</h4>
              </a>
              <div>
                {{ experience.excerpt }}
              </div>
              <a href="{{ site.baseurl }}{{ experience.url }}" class="read-more">Read More</a>
            </article>
          {%endif%}
        {% endfor %}
    </div>
  {% endfor %}
</div>

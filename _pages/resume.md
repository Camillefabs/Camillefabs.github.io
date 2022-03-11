---
layout: resume
permalink: /resume/
title: Resume
---
<a href="../_pages/resume/Camille_Fabo_Resume_2022.pdf" class="button alt" download>DOWNLOAD PDF</a>

<div class="resume">
  {% for category in site.categories %}
    <div class="archive-group">
      {% capture category_name %}{{ category | first }}{% endcapture %}
      <div id="#{{ category_name | slugize }}"></div>
      <h1 class="page">{{ category_name }}</h1>
      <a name="{{ category_name | slugize }}"></a>
        {% for experience in site.posts %}
          {% if experience.categories[0] == category_name %}
            <article class="resume">
                <a href="{{ site.baseurl }}{{ post.url }}">
                  <h2>{{ experience.title }}</h2>
                </a>
                <h3>{{ experience.subtitle }}</h3>
                <h4>{{ experience.location }} [{{ experience.startdate }} - {{ experience.enddate }}]</h4>
                <div>{{ experience.excerpt }}</div>
            </article>
          {%endif%}
        {% endfor %}
    </div>
  {% endfor %}
</div>
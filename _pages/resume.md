---
layout: resume
permalink: /resume/
title: Resume
---
<a href="../_pages/resume/Camille_Fabo_Resume_2022.pdf" class="button alt" download>DOWNLOAD PDF</a>

<div class="resume">
  <!-- defining categories for resume -->
  {% assign categories = "EDUCATION|PROFESSIONAL EXPERIENCES|TEACHING EXPERIENCE|VOLUNTEERING" | split: "|" %}

  {% for category in categories %}
    <div class="archive-group">
      <div id="#{{ category | slugize }}"></div>
      <h1 class="page">{{ category }}</h1>
      <a name="{{ category | slugize }}"></a>
        {% assign sorted_experiences = site.experiences | sort: 'date' | reverse %}
        {% for experience in sorted_experiences %}
          {% if experience.category == category %}
            <article class="resume">
                <a href="{{ experience.website}}" target="_blank">
                <h2>{{ experience.title }}</h2>
                <h3>{{ experience.subtitle }}</h3>
                </a>
                <h4>{{ experience.location }} [{{ experience.startdate }} - {{ experience.enddate }}]</h4>
                <div>{{ experience.excerpt }}</div>
            </article>
          {%endif%}
        {% endfor %}
    </div>
  {% endfor %}
</div>

---
layout: page
permalink: /resume/
title: My Resume
---
<div style="text-align: center;">
  <button>
    <a href="../_pages/resume/Camille_Fabo_Resume_2022.pdf" download class="button"> DOWNLOAD PDF </a>
  </button>
</div>

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
                  <a href="{{ experience.website}}" {% if experience.website !="" %}target="_blank"{%endif%} style="margin-bottom: -5%; font-size: 1em;">
                    <div style= "display:inline-block;margin-right:10px;">
                      <h2>{{ experience.title }}</h2>
                    </div>
                  </a> 
                    <div style= "display: inline-block; float: right; margin-top: .5%;">
                    <h4> [{{ experience.startdate }} - {{ experience.enddate }}]</h4>
                  </div>
                <h3>{{ experience.subtitle }}</h3>
                <h4>{{ experience.location }}</h4>
                <div>
                  <p>{{ experience.excerpt }}</p>
                </div>
            </article>
          {%endif%}
        {% endfor %}
    </div>
  {% endfor %}
</div>

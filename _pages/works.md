---
layout: default
title: Works
permalink: /works/
---

<div class="posts">
    {% for post in site.posts %}
      <article class="post">
        <a href="{{ site.baseurl }}{{ post.url }}">
          <h1>{{ post.title }}</h1>
  
          <div>
            <p class="post_date">{{ post.date | date: "%B %e, %Y" }}</p>
          </div>
        </a>
        <div class="entry">
          {{ post.excerpt }}
        </div>
  
        <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
      </article>
    {% endfor %}
  
    <!-- pagination -->
    {% if site.total_pages > 1 %}
    <div class="pagination">
      {% if site.previous_page %}
        <a href="{{ site.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&laquo; Prev</a>
      {% else %}
        <span>&laquo; Prev</span>
      {% endif %}
  
      {% for page in (1..site.total_pages) %}
        {% if page == site.page %}
          <span class="webjeda">{{ page }}</span>
        {% elsif page == 1 %}
          <a href="{{ '/' | prepend: site.baseurl | replace: '//', '/' }}">{{ page }}</a>
        {% else %}
          <a href="{{ site.paginate_path | prepend: site.baseurl | replace: '//', '/' | replace: ':num', page }}">{{ page }}</a>
        {% endif %}
      {% endfor %}
  
      {% if site.next_page %}
        <a href="{{ site.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Next &raquo;</a>
      {% else %}
        <span>Next &raquo;</span>
      {% endif %}
    </div>
    {% endif %}
  </div>
  
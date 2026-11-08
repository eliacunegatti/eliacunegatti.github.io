---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

{% if site.publication_category %}
{% for category in site.publication_category %}
{% assign category_posts = site.publications | where: "category", category[0] | sort: "date" | reverse %}
<section class="publication-category">
  <h2 class="publication-category__title">{{ category[1].title }}</h2>
  <div class="publication-list">
  {% for post in category_posts %}
    <article class="publication-item">
      <span class="publication-item__year">{{ post.date | date: "%Y" }}</span>
      <div class="publication-item__content">
        <h3>{{ post.title }}</h3>
        <div class="publication-item__authors">{{ post.authors | markdownify }}</div>
        <p class="publication-item__venue">{{ post.venue }}</p>
      </div>
      <div class="publication-item__links">
        {% if post.paperurl %}<a href="{{ post.paperurl }}" target="_blank" rel="noopener">Paper ↗</a>{% endif %}
        {% if post.codeurl %}<a href="{{ post.codeurl }}" target="_blank" rel="noopener">Code ↗</a>{% endif %}
      </div>
    </article>
  {% endfor %}
  </div>
</section>
{% endfor %}
{% else %}
{% for post in site.publications reversed %}
#### {{ post.title }}
**Authors:** {{ post.authors }}  
**Venue:** {{ post.venue }}  
{% if post.paperurl %} 
<a href="{{ post.paperurl }}" target="_blank">Full Text</a>  
{% endif %}
{% if post.extra %} 
<a href="{{ post.extra }}" target="_blank">Full Text</a>  
{% endif %}
{% endfor %}
{% endif %}

<p class="publication-thanks">Great research is a team sport — kudos to all my co-authors.</p>

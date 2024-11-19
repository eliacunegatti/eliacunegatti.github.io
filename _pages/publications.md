---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

<!-- Render publications with categories if defined -->
{% if site.publication_category %}
{% for category in site.publication_category %}
## {{ category[1].title }}
---
{% for post in site.publications reversed %}
{% if post.category != category[0] %}
{% continue %}
{% endif %}
**{{post.title}}**<br>
{{ post.authors }}  
{{ post.venue }}  
<a href="{{ post.paperurl }}" target="_blank">Paper</a> {% if post.codeurl %}- <a href="{{ post.codeurl }}" target="_blank">Code</a>{% endif %}

{% endfor %}
{% endfor %}
{% else %}
<!-- Render all publications if no categories are defined -->
{% for post in site.publications reversed %}
#### {{ post.title }}
**Authors:** {{ post.authors }}  
**Venue:** {{ post.venue }}  
{% if post.paperurl %} 
<a href="{{ post.paperurl }}" target="_blank">Full Text</a>  
{% endif %}
{% endfor %}
{% endif %}


<hr style="border: 1px solid black;">

*Kudos to all the co-authors!!* 🎉👌🏻 
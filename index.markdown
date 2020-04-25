---
layout: homepage
---

{% assign current_date =  site.time | date: '%F' | date: '%s' %}

{{current_date}}

second 




{% assign posts = site.posts | sort: date | reverse  %}

# 432000


<ul>
  {% for post in posts %}
    <li>
        {% assign post_date = post.date | date: '%F' | date: '%s' %}  
        {% assign k = current_date | minus: post_date %}
        {{k}}
        {% if k <= 432000 and k > 0 %}
            {{ 'New'}}
        {% else %}
            {{' Not New '}}
        {% endif %}
      <a href="{{ post.url }}">{{ post.title }} - {{post.date }} - {{post.order}}</a>
    </li>
  {% endfor %}
</ul>
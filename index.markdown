---
layout: homepage
---

{:.container-fluid}
<div>
{:.row}
<div>
{:.col-md-6}
<div>
title
</div>
{:.col-md-6}
<div>
ad space
</div>
</div>
</div>

{% assign current_date = site.time | date : "%F" | date : "%s" %}



<div class="d-flex">

{% for post in site.posts %}
{% raw %}

[
<div class="card" style="width: 18rem;">
  <img class="card-img-top" src="..." alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
</a>
][1]

<a href="#">
<div>Hey</div>
</a>

<a href="f">
{:.card .card-width}
<div  style="width: 18rem;">


![{{post.title}}]({{post.postImg}} "{{post.title}}"){:.card-img-top}

{:.card-body}
<div>

{:.card-title .text-truncate}
##### {{post.title}}

{:.card-text}
{{post.postDes}}
</div>
</div>

</a>

{% endraw %}
    {% assign post_date = post.date | date : "%F" | date : "%s" %}
    {% assign date_difference =  current_date  | minus: post_date %}
    {% if date_difference <= 432000 and date_difference >= 0 %}
        {{"new post"}}
    {% else %}
        {{"old post"}}
    {% endif %}




    {{post.title}}
{% endfor %}

</div>


[1]: http://stackoverflow.com
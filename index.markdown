---
layout: homepage
---

{% assign current_date = site.time | date : "%F" | date : "%s" %}



<div class="d-flex justify-content-center flex-wrap">

{% for post in site.posts %}

{:.card .card-width .ml-2 .mr-2 .mb-2}
<div style="width: 18rem;">


![{{post.title}}]({{post.postImg}} "{{post.title}}"){:.card-img-top .img-responsive}

{:.card-body}
<div>

{:.card-title .text-truncate}
##### {{post.title}}

{:.card-text .text-truncate}
{{post.postDes}}

[Visit Post]({{post.url}}){:.btn .btn-primary}


</div>
<div style="position:absolute;right:0">
{% assign post_date = post.date | date : "%F" | date : "%s" %}
{% assign date_difference =  current_date  | minus: post_date %}
{% if date_difference <= 432000 and date_difference >= 0 %}
{:.badge .badge-danger}
<span>new post</span>
{% endif %}
</div>
</div>






{% endfor %}

</div>



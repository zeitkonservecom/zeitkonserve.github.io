---
title: Zeitkonserve.com
---

<ul class="posts t">
{% for post in site.posts  limit:400 %}
<div class="post" style="margin-bottom:40px">
    <a href="{{ BASE_PATH }}{{ post.url }}"><h3>{{ post.title }}<br /></h3></a>
	<i>{{ post.date | date_to_string }}<br /></i>
        {{ post.content }}
            <a href="{{ post.url }}">Read more...</a>
</div>
{% endfor %}
</ul>

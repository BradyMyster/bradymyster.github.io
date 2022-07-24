---
layout: page
lang: en
title: Blog
originalTitle: Blog
---

{% assign posts = site.posts | where: "lang", page.lang %}
{% for p in posts  %}
<ul class="posts">
   <li>
        <img src="{{site.url}}/assets/images/{{p.image}}" width="{{p.imageWidth}}" height="{{p.imageHeight}}" /><br/>
        <span class="post-title">{{p.title}}</span>
        <p>{{ p.date | date: "%B" }}{{ p.date | date: "%d" | plus:'0' }}, {{ p.date | date: "%Y" }}</p>
        <p>{{p.excerpt | remove: '<p>' | remove: '</p>' }}</p>
        {% if p.external %}
            <a href="{{ p.externalUrl }}" target="_blank">{{site.data.translations[page.lang].readMore}}</a>
        {% else %}
            <a href="{{ p.url }}">{{site.data.translations[page.lang].readMore}}</a>
        {% endif %}
   </li>
<ul>
{% endfor %}
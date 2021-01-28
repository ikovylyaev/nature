---
layout: places
title: места
permalink: /places/
---

<div class="row row-cols-1 row-cols-sm-2 row-cols-md-4 g-5" style='margin-bottom: 50px;'>
        {% for post in site.posts %}
            <a class='col' href='{{site.url}}/{{post.url}}' style='margin-bottom: 0px;'>
                <img src='{{ site.url }}/photos/{{ post.number }}/title.jpg' alt='{{ post.title }} - {{ site.title }}' style='width: 100%;'>
                <h3 style='margin: 0px;'>{{post.title}}</h3>
                <p style='margin: 0px;'>{{post.region}}</p>
            </a>
        {% endfor %}
    </div>
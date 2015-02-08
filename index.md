---
layout: page
title: Learn by doing!
tagline: (or at least writing about it)
---

    
    author :
      name : {{site.author.name}}
      email : {{site.author.email}}
      github : {{site.author.github}}
      twitter : {{site.author.twitter}}

The theme should reference these variables above (if I've updated the .md file correctly).
    
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

## Thanks to the many people involved in Jekyll / Github for making this so easy


---
layout: journal
pagination:
  data: collections
  size: 1
  alias: tag
permalink: /tags/{{ tag | slug }}/
eleventyComputed:
  title: "{{ tag }}"
---

{% for article in collections[tag] %}

<div class="py-4 sm:py-10">
  <p>
    <h2 class="text-2xl sm:text-4xl font-bold"><a href="{{ article.url }}">{{ article.data.title }}</a></h2>
  </p>
  <em><time datetime="{{ article.date | dateIso }}">{{ article.date | dateReadable }}</time></em>
  <div>{{ article.templateContent }}</div>
    <span><a href="{{ article.url }}">Read More</a></span>
  </p>
</div>
{% endfor %}

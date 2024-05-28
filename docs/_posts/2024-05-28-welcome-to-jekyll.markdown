---
layout: post
title:  "Alles Guddes fir däi Gebuertsdag :)"
date:   2024-06-02 06:57:42 -0400
categories: 
---

<h1>{{ page.title }}</h1>

<p></p>

{% assign count = 0 %}
{% assign align = "left" %}
{% for gallery in site.data.galleries.overview %}
{% if count == 0 %}<div class="row">{% endif %}
  <div class="half-width gallery-preview {{ align }}">
    <h1>{{ gallery.title }}</h1>
    <a href="{{ site.url }}{{ site.baseurl }}/photography/{{ gallery.directory }}.html">
      <img alt="{{ gallery.title }}" src="{{ site.url }}{{ site.baseurl }}/assets/photography/{% if gallery.picture_path %}{{ gallery.picture_path }}{% else %}{{ gallery.directory }}{% endif %}/{{ gallery.preview.thumbnail }}" />
    </a>
  </div>
{% if count == 1 %}</div>{% endif %}
{% assign count = count | plus: 1 %}
{% assign align = "right" %}
{% if count >= 2 %}
{% assign align = "left" %}
{% assign count = 0 %}
{% endif %}
{% endfor %}

{% if count != 1 %}
</div>
{% endif %}

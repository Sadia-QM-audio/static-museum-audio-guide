---
layout: master
permalink: /ar/
type:
title: Lusail Museum

# Note that below the 'for my_page in pages' and 'if my_page.title'... should be on the same line to remove whitespace between li elements.
---

<div class="home">

  <!---
  <p>{{ site.index_page_text }}</p>
  --->


  <p dir="rtl" lang="ar"> اختر اللغة:
    <button class="language-button" onclick="window.location.href='{{ baseurl }}'">English</button>
    <button class="language-button">العربية</button>
  </p>

                 
  <p dir="rtl" lang="ar">حدد توقف دليل صوتي للبدء.</p>

  <ul class="post-list">
    {% assign pages = site.pages | sort: 'page_rank' %}
    {% for my_page in pages %}{% if (my_page.section_title != null) and my_page.type == 'stop' %}<li>
        <a class="post-link" href="{{ my_page.url | prepend: site.baseurl }}" style="background-image: url('{{ site.baseurl }}{{ site.headphones_icon_color }}');">
          <span class="post-item">{{ my_page.stop_id }}</span>
        </a>
      </li>{% endif %}{% endfor %}
  </ul>

<!--

For reference: This is a list of all the stops and titles in this audio guide

{% assign pages = site.pages | sort: 'page_rank' %}
    {% for my_page in pages %}{% if (my_page.section_title != null) and my_page.type == 'stop' %}
Stop #: {{ my_page.stop_id }}
Section Title: {{ my_page.section_title }}
Title: {{ my_page.title }}
      {% endif %}{% endfor %}

-->
  
<!--
  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>
-->
</div>

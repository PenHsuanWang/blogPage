---
title: "高山百岳 行程圖文紀錄 archive by date"
layout: archive
permalink: /categories/mt-note-photo-100peaks_date/
author_profile: true

sidebar:
  nav: "main"

header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: https://1.bp.blogspot.com/-6ObULrUCMuo/Xirf8EBhe6I/AAAAAAAA8Ig/9h-_sjEHJRsNPuLP_3Ltxgsf9Rhtf7lqACKgBGAsYHg/s1600/_MG_3538.JPG
  actions:
    - label: "<i class='fab fa-instagram'></i> Follow"
      url: "https://www.instagram.com/benwang.photo"
    - label: "<i class='fab fa-github'></i> Info"

---

<a href="/categories/mt-note-photo-100peaks_tag/" class="btn btn--primary">標籤分類</a>

<ul class="taxonomy__index">
	{% assign postsInYear = site.categories.mt-note-photo-100peaks | reverse | group_by_exp: 'post', 'post.date | date: "%Y"' %}
	{% for year in postsInYear %}
	  <li>
		<a href="#{{ year.name}}">
		  <strong>{{ year.name}}</strong><span calss="taxonomy__count">{{ year.items | size }}</span>
		</a>
	  </li>
	{% endfor %}
</ul>

{% assign postsByYear = site.categories.mt-note-photo-100peaks | reverse | group_by_exp: 'post', 'post.date | date: "%Y"' %}
{% for year in postsByYear %}
  <section id="{{ year.name }}" class="taxomony__section">
    <h2 class="archive__subtitle">{{ year.name }}</h2>
	<div class = "entries-{{ page.entries_layout | default: 'list'}}">
	  {% for post in year.items %}
	    {% include archive-single.html type=page.entries_layout %}
	  {% endfor %}
	</div>
	<a href="#page-title" class="back-to-top">{{ site.data.ui-text[site.locale].back_to_top | default: 'Back to Top' }}
	&uarr;</a>
  </section>
{% endfor %}

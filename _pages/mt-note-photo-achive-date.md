---
title: "登山圖文記錄 sort by Tag"
permalink: /mt-note-photo/date/
layout: tags-mt-note-photo

collection: mt-note-photo

author_profile: true
---

<ul class="taxonomy__index">
	{% assign postsInYear = site.mt-note-photo | group_by_exp: 'post', 'post.date | date: "%Y"' %}
	{% for year in postsInYear %}
	  <li>
		<a href="#{{ year.name}}">
		  <strong>{{ year.name}}</strong>> <span calss="taxonomy__count">{{ year.items | size }}</span>>
		</a>
	  </li>
	{% endfor %}
</ul>

{% assign postsByYear = site.mt-note-photo | group_by_exp: 'post', 'post.date | date: "%Y"' %}
{% for year in postsByYear %}
  <section id="{{ year.name }}" class="taxomony__section">
    <h2 class="archive__subtitle">{{ year.name }}</h2>
	<div class = "entries-{{ page.entries_layout | default: 'list'}}">
	  {% for post in year.items %}
	    {% include archive-single.html tpye=page.entries_layout %}
	  {% endfor %}
	</div>
	<a href="#page-title" class="back-to-top">{{ site.data.ui-text[site.locale].back_to_top | default: 'Back to Top' }}
	&uarr;</a>
  </section>
{% endfor %}


<a href="/mt-note-photo/" class="btn btn--danger">回上層</a>
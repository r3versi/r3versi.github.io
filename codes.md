---
layout: default
title: Esercizi
permalink: /codes/
menu: true
---

<ul class="post-list">
	{% for code in site.codes %}
		<li>
			<span class="post-meta">{{ code.date | date: "%b %-d, %Y" }}</span>

			<h2>
				<a class="post-link" href="{{ code.url | relative_url }}">{{ code.title | escape }}</a>
			</h2>
			{{ code.excerpt | escape }}
		</li>
	{% endfor %}
</ul>
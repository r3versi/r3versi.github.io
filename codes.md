---
layout: default
title: Codici
permalink: /codes/
---

<ul class="post-list">
	{% for code in site.codes %}
		<li>
			<span class="post-meta">{{ code.date | date: "%b %-d, %Y" }}</span>

			<h2>
				<a class="post-link" href="{{ code.url | relative_url }}">{{ code.title | escape }}</a>
			</h2>
		</li>
	{% endfor %}
</ul>
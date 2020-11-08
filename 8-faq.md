---
layout: default
title: FAQ
description: FAQ
css-add: accordion
---

**FAQ**. Это список наиболее часто задаваемых вопросов.

<section class="faq">
	{% for item in site.faq %}
	  <button class="accordion">{{ item.description }}</button>
	  <div class="panel">
	    {{ item.content | markdownify }}
	  </div>
	{% endfor %}
</section>

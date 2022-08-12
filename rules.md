---
layout: main
title: Ammonite Rules
---

<div id="icon"><img src="assets/ammonite.png"></div>
<h1 class="center">Ammonite Rules</h1>
{% assign rules_i = 0 %}
{% for section in site.data.rules %}
<section id="{{ section.name | slugify }}">
    <h2><a href="#{{ section.name | slugify }}">#</a> {{ section.name }}</h2>
    {% if section.rules %}
    <ol class="rules_segment">
      {% for rule in section.rules %}{% assign rules_i = rules_i | plus: 1 %}
      <li class="rules_rule" value="{{ rules_i }}" id="{{ rules_i }}">
        <div class="rule_num"><a href="#{{ rules_i }}">#{{ rules_i }}</a></div>
        <div class="rule_text">{{ rule | markdownify | remove: "<p>" | remove: "</p>"  }}</div>
      </li>
      {% endfor %}
    </ol>
    {% endif %}
    {{ section.text | markdownify }}
</section>
{% unless forloop.last %}<hr>{% endunless %}
{% endfor%}
<div class="gutter"></div>

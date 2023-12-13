---
title: BitD Philly | Player Characters
layout: default
---

# Player Characters

<div class="pic_list">
    {% for char in site.data.world.pcs %}
    <p>
        {% if char.picture %}
        <img src="{{ site.baseurl }}/assets/img/world/characters/pcs/{{ char.picture }}">
        {% else %}
        <img src="{{ site.baseurl }}/assets/img/world/characters/pcs/default.jpg">
        {% endif %}
        <b>{{char.alias}}</b><br>
        {{char.name}}<br>
        {{char.playbook}}
        <hr>
        {{char.short_desc}}
    </p>
    {% endfor %}
</div>
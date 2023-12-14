---
title: BitD Philly | Player Characters
layout: default
---

# Player Characters

<!-- <div class="pic_list">
    {% assign chars = site.data.world.pcs | sort: 'alias' %}
    {% for char in chars %}
    <p>
        {% if char.picture %}
        <img src="{{ site.baseurl }}/assets/img/world/characters/pcs/{{ char.picture }}">
        {% else %}
        <img src="{{ site.baseurl }}/assets/img/world/characters/pcs/default.jpg">
        {% endif %}
        {% if char.alias %}
        <b>{{char.alias}}</b><br>
        {{char.name}}<br>
        {% else %}
        <b>{{char.name}}</b><br>
        {% endif %}
        {{char.playbook}}
        <hr>
        {{char.short_desc}}
    </p>
    {% endfor %}
</div> -->

<div class="pic_list">
    {% for char in site.player_characters %}
    <p>
        <a href="{{char.url}}">
            <img src="{{ site.baseurl}}/{{char.img_root| append: char.picture}}">
        </a>
        {% if char.alias %}
            <b>{{char.alias}}</b><br>
            {{char.name}}<br>
        {% else %}
            <b>{{char.name}}</b><br>
        {% endif %}
        {{char.playbook}}
        <hr>
        {{char.excerpt}}
    </p>
    {% endfor %}
</div>
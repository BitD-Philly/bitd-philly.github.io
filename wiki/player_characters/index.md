---
title: BitD Philly | Player Characters
layout: default
---

# Player Characters

<div class="pic_list">
    {% for char in site.player_characters %}
    <p>
        <a href="{{char.url}}">
            <img src="{{ site.baseurl}}/{{char.img_root| append: char.picture}}">
        </a>
        {% if char.alias %}
            <b>{{char.alias}}</b><br>
            {{char.full-name}}<br>
        {% else %}
            <b>{{char.full-name}}</b><br>
        {% endif %}
        {{char.playbook}}
        <hr>
        {{char.excerpt}}
    </p>
    {% endfor %}
</div>
---
layout: default
title: Wiki
---
# Wiki

Welcome to the Nameless wiki! The aim of this wiki is to provide a living record of the people, places, and events of our crew's city of Duskvol and beyond.

<h2>Featured Player Characters</h2>

This rough-and-tumble crew has a large cast of unique and interesting characters. [See All Player Characters »](player_characters)
{% assign some_pcs = site.player_characters | sample: 2 %}
<ul class="wiki_list">
{% for pc in some_pcs %}
<li>
<a href="{{pc.url}}"><img src="/{{pc.img_root | append: pc.picture}}"></a>
<p>
<h3>{{pc.full-name}}</h3>
<b>{{pc.playbook}}</b></p>
<p>
{{pc.excerpt | default: pc.desc}}</p>
<p style="float:right;clear:right;margin-top:0">
<a href="{{pc.url}}">Read more »</a></p>
</li>
{%endfor%}
</ul>

## Featured NPCs
Friends, allies, enemies, and more! [See all NPCs »](npcs)
<ul class="wiki_list">
{% assign some_npcs = site.npcs | sample: 2 %}
{% for npc in some_npcs %}
<li>
<p>
<h3>{{npc.full-name}}</h3>
{{npc.excerpt}}</p>
<p style="float:right;clear:right;margin-top:0">
<a href="{{npc.url}}">Read more » </a>
</p>
</li>
{%endfor%}
</ul>

## Featured Factions
Associations, enterprises, and coalitions, criminal or otherwise. [See all factions »](factions)
<ul class="wiki_list" >
{% assign some_factions = site.factions | sample: 2 %}
{% for faction in some_factions %}
<li>
<p>
<h3>{{faction.full-name}}</h3>
{{faction.excerpt}}</p>
<p style="float:right;clear:right;margin-top:0">
<a href="{{faction.url}}">Read more »</a>
</p>
</li>
{%endfor%}
</ul>

## Featured Locations
Criminal haunts and lucrative locales! [See all locations »](locations)
<ul class="wiki_list" >
{% assign some_locations = site.locations | sample: 2 %}
{% for loc in some_locations %}
<li>
<p>
<h3>{{loc.full-name}}</h3>
{{loc.excerpt}}</p>
<p style="float:right;clear:right;margin-top:0">
<a href="{{loc.url}}">Read more »</a>
</p>
</li>
{%endfor%}
</ul>

## Contribute

Play in our game and want to contribute to the wiki? [Click here](contribute) to get started!


## Legal Notice

Materials in this wiki are inspired by the published Duskwall/Shattered Isles setting, but are in many ways unique to our game. Wiki contents that share similarities with official published places and characters should be thought of as transformative (fan) work based on the original setting, and should not be used in place of published material. 

Please support the official release!
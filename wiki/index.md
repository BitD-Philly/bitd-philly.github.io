---
layout: default
---
# Wiki

Welcome to the Nameless wiki! The aim of this wiki is to provide a living record of the people, places, and events of our crew's city of Duskvol and beyond.

<style>

.wiki_list {
	margin: 0 auto;
    padding: 0;
	list-style: none;
    font-size: 0.9em;
    width:100%;
}
.wiki_list li {
	margin: 0em 1em;
    display: inline-block;
    clear:both;
    vertical-align:top;
    width:25em;
	text-align: left;
	border-width: 1px 1px 2px 1px;
	padding: 2px 5px;
}

.wiki_list li img {
	float: left;
	clear: left;
	padding: 2px!important;
    border: 1px solid #ccc;
	margin-right: 10px;
    width: 120px;
}

.wiki_list li h3 {
    margin-bottom: 0.2em;
}
</style>


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
{{pc.excerpt}}</p>
<p style="float:right;clear:right;margin-top:0">
<a href="{{pc.url}}">Read more »</a></p>
</li>
{%endfor%}
</ul>

## Featured NPCs
Friends, allies, enemies, and more! [See all NPCs »](npcs)
<ul class="wiki_list">
{% assign some_npcs = site.npcs | sample: 3 %}
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
{% assign some_factions = site.factions | sample: 3 %}
{% for faction in some_factions %}
<li>
<p>
<h3>{{faction.full-name}}</h3>
{{faction.excerpt}}</p>
<p style="float:right;clear:right;margin-top:0">
<a href="{{faction.url}}">Read more » </a>
</p>
</li>
{%endfor%}
</ul>

## Featured Locations
Criminal haunts and lucrative locales! [See all locations »](locations)
<ul class="wiki_list" >
{% assign some_locations = site.locations | sample: 3 %}
{% for loc in some_locations %}
<li>
<p>
<h3>{{loc.full-name}}</h3>
{{loc.excerpt}}</p>
<p style="float:right;clear:right;margin-top:0">
<a href="{{loc.url}}">Read more » </a>
</p>
</li>
{%endfor%}
</ul>


## Contribute

Play in our game and want to contribute to the wiki? Check out [this Discord thread](https://discord.com/channels/1022641517170540574/1023043651925979246/1185264034472267898) to get started!


## Legal Notice

This work is based on [Blades in the Dark](http://www.bladesinthedark.com/), product of One Seven Design, developed and authored by John Harper, and licensed for our use under the [Creative Commons Attribution 3.0 Unported license](http://creativecommons.org/licenses/by/3.0/).

Materials in this wiki are inspired by the published Duskwall/Shattered Isles setting, but are in many ways unique to our game. Wiki contents that share similarities with official published places and characters should be thought of as transformative (fan) work based on the original setting, and should not be used in place of official material. 

Please support the official release!
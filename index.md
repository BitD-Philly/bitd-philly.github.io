---
layout: default
title: home
---
{% assign latest-recap = site.posts | where: "tags","session-recap" | sort: date | last%}

# Welcome, scoundrel!

<img class="imgleft" src="{{site.baseurl}}/assets/img/V-SEA-W_logo.png" alt="V-Sea-W logo, flanked by knives. the caption reads the schmeek shall inherit the earth." width=90>

This is the website for [the Nameless](/gang/), a gang of thieves and sneaks who prowl the streets of [Duskvol](/wiki/duskvol) by lamplight-- nabbing the valuables of the rich and powerful, fighting ghosts and automatons, and running such illicit ventures as the city's [premier wrestling ring](/wiki/v-sea-w) -- all under the watchful eyes of the [Immortal Emperor](/wiki/npcs#the-immortal-emperor) and his servants.

<div style="clear:both"></div>

Welcome to the world of Blades in the Dark, a top role playing game developed by John Harper. Our gang plays biweekly and our games are run by GM Ted Gold.

The purpose of this website is to create a centralized place for the gang to be able to access important information quickly-- as a pocket reference to [characters](/wiki/player_characters) and other [gangs](/wiki/factions), as well as keep track of some of the simulationist aspects of the game, as on the [gang page](/gang/).

### Latest Session

**[{{latest-recap.title}} »]({{latest-recap.url | replace: "recap.html",""}})**  
*{{latest-recap.date | date: "%B %-d, %Y"}}*

{{latest-recap.excerpt}} 

### Explore

<center>
<a class="button" href="/gang/">Check Crew Stats »</a>
<a class="button" href="/story/">Read The Story »</a>
<a class="button" href="/wiki/locations">Explore the Map »</a>
</center>
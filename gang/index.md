---
layout: default
title: Gang
---

# The Nameless

{% assign gang-stats = site.data.gang.stats.stats %}
{% assign gang-counters = site.data.gang.stats.counters %}
{% assign gang-finances = site.data.gang.stats.finances %}
<!-- {{ gang-counters}} -->

<!-- Rep/Turf Counter -->
{% include clock.html 
    label="Rep" fill=gang-counters.reputation 
    label2="Turf" fill2="2" 
    max="12" group="6" 
    align="center"%}


{% include clock.html 
    label="Vault" fill=gang-finances.vault group=4 align="center" %}


{% include clock.html label="Heat" fill=gang-counters.heat group=5 align="center" %}
{% include clock.html label="Wanted Level" fill=gang-counters.wanted-level align="center"%}


# Upgrades

{% include clock.html label="Crew XP" fill=gang-counters.xp group=5 align="right"%}
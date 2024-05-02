---
title: Gang
stylesheet: gang
---
<!-- retrieve data from stats file -->
{% assign gang = site.data.gang.stats %}
{% assign details = site.data.gang.details%}
{% assign cohorts = site.data.gang.cohorts | sort: "class" %}
{% assign upgrade-types = "lair,training,quality" | split: ","%}

{% assign featured-faction-list = site.data.gang.featured-factions | join: ":" | append: ":" | prepend: ":"%}

<!-- Calculations -->
{% assign n-turf = gang.stats.claims | where: "is-turf",true | size %}
{% assign roman_numerals = "0,I,II,III,IV,V,VI" | split: "," %}

# The Nameless
<div style="display:inline-block;max-width:45%;min-width: 20em;vertical-align:top;text-align:left;" markdown="1">

The Nameless are crew of `{{gang.type}}` with a reputation as `{{gang.reputation}}`, headquartered at `{{gang.lair}}` in the Six Towers district of Duskvol.

<h2>Current Stats</h2>

The Nameless are currently `Tier {{roman_numerals[gang.stats.tier]}}` with `{{gang.stats.hold}}` hold.

<!-- Rep/Turf Counter -->
{% include clock.html 
    label="Rep" fill=gang.stats.rep 
    label2="Turf" fill2=n-turf 
    max="12" group="6" 
    align="center" css="margin-bottom: 3em"%}

{% include clock.html label="Heat" fill=gang.counters.heat group=3 align="center" %}
{% include clock.html label="Wanted Level" fill=gang.counters.wanted-level align="center" css="margin-bottom: 3em"%}

<!-- XP Counter -->
{% include clock.html 
    label="Crew XP" fill=gang.counters.xp 
    group=5 align="center" css="margin-bottom: 3em;"%}


<!-- Vault Counter -->
{% include clock.html 
    label="Vault" fill=gang.counters.vault 
    group=4 align="center" %}
</div>

<!-- Faction List -->
<table class="factions" style="display:inline-block;min-width: 20em;width: 45%;">
{% for faction_classification in site.data.world.factions._index %}

{% assign faction_group = site.data.world.factions[faction_classification] | sort: "tier" | reverse %}
<tr class="title">
<th colspan=4>{{faction_classification | replace: "-"," "}}</th>
</tr>
{% if forloop.first %}
<tr class="title">
<td>Name</td> <td>Tier</td> <td>Hold</td> <td>Status</td>
</tr>
{% endif %}
{% for faction in faction_group %}
{% assign match = faction.id | append: ":" | prepend: ":" %}
{% assign format-flags = "" %}

{% if featured-faction-list contains match %}

{% unless faction.hold %}
{% assign format-flags = format-flags | append: "strike"%}
{%endunless%}

{% if faction.collection %}
{% assign faction-link = "/wiki/" | append: faction.id%}
{% else %}
{% assign faction-link = "/wiki/factions#"| append: faction.id%}
{%endif%}

<tr class="{{format-flags}}">
<td><a href="{{faction-link}}">{{faction.name}}</a></td>
<td>{{roman_numerals[faction.tier]}}</td>
<td>{% if faction.hold == "S"%}strong{%elsif faction.hold=="W"%}weak{%endif%}</td>
<td class="s{{faction.status | replace: '-','m'}}">{%if faction.status >= 0%}+{%endif%}{{ faction.status }}</td>
</tr>
{% endif %}
{% endfor %}
{% endfor %}
</table>

<div style="clear:both;"></div>

# Advancements

<!-- Asset Table of (1) abilities, (2) claims, (3) upgrades -->
<table class="perks">
<tr>
<th>Abilities</th>
<th>Source</th>
<th>Effect</th>
</tr>

<!-- Asset Table: Abilities -->
{% for ability in gang.abilities %}

{% if ability.name == "veteran" %}
{% assign name = ability.vet-name | replace: "-"," "%}
{% assign source = ability.source %}
{% assign effects = ability.effects %}
{% else %}
{% assign name = ability.name | replace: "-"," "%}
{% assign source = "shadows" %}
{% assign effects = details.abilities | where: "name",ability.name | map: "effects" | last%}
{% endif %}

<tr>
<td>{{name}}</td>
<td>{{source}}</td>
<td>{% for effect in effects %}
{{effect | markdownify}}
{%endfor%}
</td>
</tr>
{% endfor %}


<tr>
<th>Claims & Turf</th>
<th>Source</th>
<th>Effect</th>
</tr>
<!-- Asset table: Claims & Turf -->
{% for claim in gang.claims %}

{% if claim.effects %}
{% assign effects = claim.effects %}
{% else %}
{% assign effects = details.claims | where: "name", claim.name | map: "effects" | last %}
{% endif%}

{%if claim.source == "shadows" %}
{% assign source = claim.source %}
{% assign source-link = nil %}

{% else %}
{% assign source-name = claim.source | split: ":" | last | replace: "-"," "%}
{% assign source-link = "/wiki/"|append: claim.source | replace: ":","#" %}
{% assign source = "["|append: source-name | append: "](" | append: source-link | append: ")" %}
{%endif%}

<tr>
<td>{{claim.name | replace: "-"," "}}</td>
<td>{{source |markdownify}}</td>
<td>
{% for effect in effects %}
{{effect | markdownify}}
{%endfor%}
</td>
</tr>
{%endfor%}

<tr>
<th>Upgrades</th>
<th>Source</th>
<th>Effect</th>
</tr>
<!-- Asset table: Upgrades -->
{% for type in upgrade-types %}
{% for item in gang.upgrades[type] %}

{% assign effects = site.data.gang.upgrades-details[type] | where: "name",item | map: "effects" | last %}
{% if type=="training" %}
{% assign name = item | replace: "-"," "| append: " training" %}
{%elsif type=="quality" %}
{% assign name = "quality "| append: item | replace: "-"," "%}
{% else %}
{% assign name = item | replace: "-", " "%}
{%endif%}
<tr>
<td>{{name}}</td>
<td>{{type}}</td>
<td>
{% for effect in effects %}
{{effect | markdownify}}
{%endfor%}
</td>

</tr>
{%endfor%}

{%endfor%}
</table>


# Cohorts

<table class="perks">
{% if cohorts %}
{% assign health-status = "Destroyed;Broken;Impaired (-1d);Weakened (-1 effect);Healthy"| split: ";"%}
<tr>
<th>Name</th>
<th>Class</th>
<th>Status</th>
<th>Types</th>
<th>Quality</th>
<th>Edges</th>
<th>Flaws</th>
</tr>
{% for cohort in cohorts %}
{% if cohort.class=="expert"%}
{% assign quality = gang.stats.tier | plus: 1 %}
{% elsif cohort.class=="gang"%}
{% assign quality = gang.stats.tier %}
{% endif %}

{% assign health = cohort.health | slice: 0| plus: 0%}

<tr>
<td>{{cohort.name}}</td>
<td>{{cohort.class}}</td>
<td>{{health-status[health]}}</td>
<td>{% for type in cohort.types %}
{{type | markdownify }}
{%endfor%}</td>
<td>{{roman_numerals[quality]}}</td>
<td>{% for edge in cohort.edges %}
{{edge | markdownify}}
{%endfor%}</td>
<td>{% for flaw in cohort.flaws %}
{{flaw | markdownify}}
{%endfor%}</td>
</tr>
{% endfor %}

{%endif%}

</table>
---
# site data (required)
# This data in this header is used to reference this organization across the entire website. 
name: The Billhooks
faction_category: underworld

#optional
leader: Erin
picture:
---
{% assign faction_id = page.name | slugify: "latin" %}
{% assign faction_group = site.data.world.factions[page.faction_category] %}
 
{% for faction in faction_group %}
{% if faction.id == faction_id %}
{{faction.name}}
{% endif %}
{% endfor %}

You can link to other wiki pages like this:`[link text](link-target)`, where `link text` is the text that is written on the page and `link-target` is the name of the page you are linking to.

**Note that valid links lowercase and spaces must be replaced with dashes (-).**

Examples:
* [Duskvol](duskvol)
* The [Seventh Tower Consortium](seventh-tower-consortium)

You can also link to sub-headers on any page by using a # after the `link-text`. For example, linking to Cruncho's backstory would look like this:

`Due to Cruncho's [personal history](cruncho#backstory) with football, he was able to...` -->
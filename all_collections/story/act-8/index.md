---
title: "Act VIII: Under Scrutiny"
act-id: "act-8"
permalink: /story/act-8/index:output_ext
category: acts
excerpt: In which the Nameless attempt to out-maneuver Render's forces.
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories",page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.content}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}
---
title: "Act VII: Render"
act-id: "act-7"
permalink: /story/act-7/index:output_ext
category: acts
excerpt: In which the Nameless prepare for Render's arrival in Duskvol.
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories",page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.excerpt}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}
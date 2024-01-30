---
title: "Act I: Starting Out, Spirit Wardens, and Scurlock"
act-id: "act-1"
permalink: /story/act-1/index:output_ext
category: acts
excerpt: In which the Nameless steal a clockwork head, survive a bespoke house of horrors, accidentally kill an important man, and pick a fight with some ex-cops.
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories",page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.content}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}

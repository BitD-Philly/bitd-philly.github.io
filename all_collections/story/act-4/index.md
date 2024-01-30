---
title: "Act IV: The Ironworks Debacle"
act-id: "act-4"
permalink: /story/act-4/index:output_ext
category: acts
excerpt: In which the Nameless cause a looming energy shortage, lose track of a certain ancient vampire, and kill a demon.
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories",page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.content}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}
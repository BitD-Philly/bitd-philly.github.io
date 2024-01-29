---
title: "Act 4: The Ironworks Debacle"
act-id: "act-4-the-ironworks-debacle"
permalink: /story/act-4-the-ironworks-debacle/index:output_ext
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
---
title: "Act VI: The War of Sevens"
act-id: "act-6"
permalink: /story/act-6/index:output_ext
category: acts
excerpt: In which the Nameless defend Six Towers against corporate interests.
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories",page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.content}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}
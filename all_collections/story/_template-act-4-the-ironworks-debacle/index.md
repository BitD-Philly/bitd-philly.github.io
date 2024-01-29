---
title: "Act X: Title Of Act"
act-id: "act-X-title-of-act"
permalink: /story/act-x-title-of-act/index:output_ext
category: acts
excerpt: Short description of major themes/events of the act
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories",page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.content}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}

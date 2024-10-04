---
title: "Act IX: The New Regime"
act-id: "act-9"
permalink: /story/act-9/index:output_ext
category: acts
excerpt: In which the Nameless navigate a political landscape utterly changed by Render's takeover.
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories",page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.content}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}
---
title: "Act III: Consolidation"
act-id: "act-3"
permalink: /story/act-3/index:output_ext
category: acts
excerpt: In which the Nameless make allies and enemies from the high halls of academia to the sunken streets of Crow's Foot.
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories", page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.content}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}

---
title: "Act 3: Consolidation"
act-id: "act-3-consolidation"
permalink: /story/act-3-consolidation/index:output_ext
category: acts
excerpt: In which the Nameless make allies and enemies within the high halls of academia and the sunken streets of Crow's Foot.
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories",page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.content}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}

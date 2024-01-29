---
title: "Act V: Gentrifiers & Gates"
act-id: "act-5"
permalink: /story/act-5/index:output_ext
category: acts
excerpt: In which the Nameless make shady business deals, stage a power failure, re-decapitate a robot, and fulfill a fake child's dying wish. 
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories",page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.content}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}
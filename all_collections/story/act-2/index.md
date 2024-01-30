---
title: "Act II: The War for Six Towers"
act-id: "act-2"
permalink: /story/act-2/index:output_ext
category: acts
excerpt: In which the Nameless fight a brutal war with the Gray Cloaks and establish a premier wrestling venue.
---
# {{page.title}}

{{page.excerpt}}

{% assign act_sessions = site.posts |where: "tags","session-recap" | where: "categories",page.act-id | sort: "date" %}
{% for session in act_sessions %}
## [{{session.title}}]({{session.url | replace: "recap","index"}})
{{session.content}}
[Read more »]({{session.url | replace: "recap","index"}})
{%endfor%}

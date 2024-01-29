---
title: The Story of the Nameless
permalink: /story/
---

# The Story

{% assign acts = site.pages | where: "category","acts" | sort: "act-id"%}

{% for act in acts %}
## [{{act.title}}]({{act.url}})
{{ act.excerpt }}

{% assign sessions = site.posts | where: "categories", act.act-id | where: "tags","session-recap" | sort: "date"%}
{%for session in sessions %}
1. [{{session.title}} »]({{session.url | replace: "recap","index"}})
{%endfor%}
{%endfor%}
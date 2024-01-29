{% assign posts = site.posts | where: "categories", page.date | sort: "date"%}
{{includes.date}}

{% for post in posts %}
{%if post.tags contains "session-recap"%}
{{post.content}}
{% elsif post.tags contains "fluff" %}
{% unless post.title == ""%}
# {{post.title}}
{%endunless%}
{{post.content}}

{% endif %}
{%endfor%}
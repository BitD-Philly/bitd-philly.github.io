{% assign folder_name = page.date | date: "%Y-%m-%d"%}
{% assign posts = site.posts | where: "categories", folder_name | sort: "date"%}

{% for post in posts %}
{% assign post_name = post.url | replace: ".html", "" | split: "/" | last %}


{% if post_name =="index" %}
{%continue%}
{%elsif post.tags contains "session-recap"%}
{{post.content}}
{% elsif post.tags contains "fluff" %}
{% unless post.title == ""%}
# {{post.title}}
{%endunless%}
{{post.content}}
{% endif %}

{%endfor%}
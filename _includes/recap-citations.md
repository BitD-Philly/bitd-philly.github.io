# Citations
{% assign recaps = site.posts | where: "tags","session-recap" | reverse%}

{% for recap in recaps%}
{% assign ref = recap.title | replace: "'", ""| replace: ".","" | replace: "ç","c" | slugify: latin %}
[^{{ref}}]: *{{recap.title}}*. <{{recap.url | replace: "recap.html","" | absolute_url}}>
{%endfor%}
# Citations
{% assign recaps = site.posts | where: "tags","session-recap" | reverse%}

{% for recap in recaps%}
{% assign ref = recap.title | replace: "'", ""| replace: ".","" | slugify %}
[^{{ref}}]: *{{recap.title}}*. <{{site.url}}{{recap.url | replace: "recap.html",""}}>
{%endfor%}
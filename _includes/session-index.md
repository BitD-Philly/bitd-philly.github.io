{% assign roman_numerals = "0,I,II,III,IV,V,VI,VII,VIII,XIV,X" | split: "," %}

{% assign folder_name = page.date | date: "%Y-%m-%d"%}
{% assign act-number = page.categories[1] | split: "-" | last| plus: 0%}
{% assign session_number = 1 %}

{% assign act-recaps = site.posts | where: "categories",page.categories[1] | where: "tags","session-recap" | sort: "date"%}


{% assign posts = site.posts | where: "categories", folder_name | sort: "date"%}


{% for recap in act-recaps %}

{% if recap.date == page.date and forloop.last == false %}
    {% assign next-session = act-recaps[forloop.index]%}
    {% assign title = recap.title %}

{% elsif recap.date < page.date %}
    {% assign session_number = session_number | plus: 1 %}
    {% assign previous-session = recap %}

{% elsif forloop.last == true%}
    {%unless next-session %}
        {% assign next-act = act-number | plus: 1 | prepend: "act-"%}
        {% assign next-session = site.posts | where: "categories",next-act | where: "tags","session-recap" | sort: date | first%}
    {%endunless%}
    {%unless previous-session%}
        {% assign previous-act = act-number | minus: 1 | prepend: "act-"%}
        {% assign previous-session = site.posts | where: "categories",previous-act | where: "tags","session-recap" | sort: date | last%}
    {%endunless%}
    {% unless title %}
        {% assign title=recap.title %}
    {%endunless%}
{%endif%}
{%endfor%}

# {{title}}

<div class="session_header">
Act {{roman_numerals[act-number]}} -- Session {{session_number}}<br>
{{page.date | date_to_string: "ordinal","US"}}
<br>
<a href="{{previous-session.url|replace: 'recap','index'}}">« Back</a> • 
<a href="{{next-session.url|replace: 'recap','index'}}">Next »</a>
</div>



{% for post in posts %}
{% assign post_name = post.url | replace: ".html", "" | split: "/" | last %}


{% if post_name =="index" %}
{%continue%}
{% elsif post.tags contains "session-recap"%}
{% if forloop.first == false %}
# Session Recap
{%endif%}
{{post.content}}
{% elsif post.tags contains "fluff" %}
{% unless post.title == ""%}
# {{post.title}}
{%endunless%}
{{post.content}}
{% endif %}

{%endfor%}
---
---
{% assign payout_dates = site.data.gang.stash %}
{% assign stash = 0 %}
{% for date in payout_dates%}
{% assign stash = stash| plus: date.stash%}
If you joined the Nameless before `{{date.date| date: "%B %e, %Y"}}`, then you have earned `{{stash}}` stash.
{%endfor%}
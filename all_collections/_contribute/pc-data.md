---
layout: docs
title: PC Metadata
---
# Player Character Metadata 

PC wiki pages can be found in the "player_characters" collection, located at the path `/all_collections/_player_characters`. When adding a new character page, make a copy of the `_template.md` file located in the directory.

## Required Front Matter

| Field | Data type| Description |
|-|-|-|
| full-name | string | full name of the character |
| playbook |  string | Name of the character's playbook |
| player | string | First name of the player |

## Optional Front Matter

| Field | Data type | Description |
|-|-|-|
| pronouns | string | Preferred pronouns of the character |
| alias | string | one or more aliases the character uses, separated by commas. |
| prefers-alias | bool | default: empty. If `true`, the character's alias (or first listed alias) will be used in metadata-generated site content.|
| status | string | status of characteer; values: left blank, `dead`, `missing`, `in hiding`, `incarcerated`, or `incapacitated`. If left blank, site will default to displaying "active". |
| desc | string | 1-2 sentence description of character. |
| picture | string | file location of the picture associated with the PC. (Contact site admin to set this up!) |

## Example Front Matter
### PC with alias and picture
Example front matter for a PC with a preferred alias and a picture:

{% highlight markdown %}
---
# This data in this header is used to reference your character across the entire website. 
# required
full-name: Rosie Woodward 
playbook: Hound
player: Vinnie
last_update: 12 December 2023

# optional
alias: Sizzle
prefers-alias: true
pronouns: she/her
desc: "Mysterious gunslinger, pistol enthusiast. Has a hawk. Never comfortable."
picture: Sizzle.png
---
{%endhighlight%}

### PC that is presumed dead
Example front matter for a PC that is presumed dead and prefers their name over their alias:

{% highlight markdown %}
---
# This data in this header is used to reference your character across the entire website. 
# required
full-name: Orianna Helker
player: Parker
playbook: Whisper
last_updated: 15 December 2023

# This data in this header is used to reference your character across the entire website. 
# required
alias: Affect
prefers-alias: 
pronouns: She/They
status: Presumed dead
desc: A former steelworker who developed a fascination with the ghost field after witnessing vampires massacre her union mates. Now a manifestation of Vazara.
picture: Orianna.png
---
{% endhighlight %}

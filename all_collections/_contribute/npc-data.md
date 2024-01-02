---
layout: docs
---

# NPC Metadata Structure

<div id="toc" markdown="1">
<b>Contents</b>
* TOC
{: toc}
</div>


This page outlines the metadata for NPC stubs and wiki pages in the `_npcs` collection.

# NPC Stubs

A "stub" is the base unit for a data entry for any non-player character or other world entity. It must contain the character's name and unique `w-id` ("world id").

Characters without wiki pages should have an `excerpt` key with a 1-2 sentence description. Characters with wiki pages should state the collection name the wiki page is a part of.

The data for npc stubs is located in the `_data/world/characters/` folder.

<div style="clear:both;"></div>

## Stub Data Structure

| Field | Required | Data type| Description |
|-|-|-|-|
| name | Required | string | display name of the character |
| w-id   | Required | string | unique identifier used as the wiki URL. Usually the character's name, but lowercase and with dashes instead of spaces (e.g., Lord Scurlock's `w-id` is `lord-scurlock`.) |
| collection | Optional | string | The collection the character's wiki page belongs to, if the stub has been expanded into a dedicated wiki page. |
| excerpt | Optional | string | 1-2 sentence description of character, *only if* the character does not have a wiki page.|

## Example Stubs

### Standalone NPC Stub

{% highlight markdown %}
- name: Caleb Hollow
  w-id: caleb-hollow
  excerpt: Reconciled ghost and confidence man. Will do anything for a day as a vampire.
{% endhighlight %}

### NPC Stub with wiki page

{% highlight markdown %}
- name: Lord Scurlock
  w-id: lord-scurlock
  collection: npcs
{% endhighlight %}

# Wiki Pages
NPC wiki pages can be found in the "npcs" collection, located at the path `/all_collections/_npcs`. When adding a new npc page, make a copy of the `_template.md` file located in the directory.

Note: characters that have dedicated wiki pages still retain their stub data. The stub is updated to re-direct to the primary wiki page through the use of the `collection` and `w-id` keys.

## Required Front Matter 

The text in between the lines of three dashes (---) at the top of the wiki page is called *front matter*. For NPCs, the front matter uses the following fields.

| Field | Required | Data type| Description |
|-|-|-|-|
| full-name | Required | string | The full known name (not alias) of the npc. |
| w-id | Required | string | Matches the npc's stub `w-id`, used for filtering and page generation. |
| char-type | Required | string | Type of npc, as defined by which .yml file the stub is listed in (e.g., `criminals`, `nobles-and-notables`, etc.)    |
| faction-type | Required^\* | string | Only required if the `w-id` is also listed as a `faction` stub (e.g., Lugos, Lord Scurlock). This declares the type of faction, as defined by which .yml file the stub is listed in.  |
| last_updated | Required | DD Month YYYY | Date the wiki page was last updated. |

## Optional Front Matter 

| Field | Required? | Data type| Description |
|-|-|-|-|
| alias | No | string | One or more aliases the character uses, separated by commas. List primary alias first.
| prefers-alias | No | bool | Set to `true` if the npc is better known by their primary alias than their full name, otherwise leave blank. |
|pronouns| No | string | the npc's preferred pronouns |
| status | No | string | status of the npc. if left blank, will default to `active`. Other options include `missing`, `incapacitated`, `hiding`, `dead`, `retired`, `presumed dead`, `incarcerated`, etc. |
| factions |    No | string | factions the npc is associated with, but does not share a `w-id` with. Format as `faction-type:faction-name` and separate with commas.|
| picture | No | string | the filename of the npc image in the `img_root` folder associated with the `_npcs` collection. Contact site admin (Parker or Vinnie) to set up a picture. |
| desc | No | string | 1-2 sentence description of the npc. |

## Front Matter Examples

### NPC with faction id

An example of front matter for an `npc` whose `w-id` is also associated with a faction:

{% highlight markdown %}
---
# required
# This data in this header is used to reference this character across the entire website. 
full-name: Lord Scurlock
w-id: lord-scurlock
char-type: spooks-and-supernaturals
faction-type:   underworld
desc:        A dangerous vampire with powerful connections. Ancient and immutable.
last_updated: 17 Dec 2023

#optional
pronouns:       He/Him
status:         missing/presumed dead 
---
{% endhighlight %}

### NPC with alias
An example of front matter for an `npc` with multiple `aliases`:

{% highlight markdown %}
---
# required
# This data in this header is used to reference this character across the entire website. 
full-name: Elia Wickham
w-id: elia-wickham
char-type: spooks-and-supernaturals
last_updated: 17 Dec 2023

#optional
alias:          Old Wickham, Young Hamwick
pronouns:       any
status:         active
desc:        A pre-calamity ghost of a shadow witch, who has become "contagious" to those who interact with her spirit essence. Middling comedic actor.
---
{% endhighlight %}

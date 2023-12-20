---
permalink: /wiki/npcs/docs
---

# NPC Metadata Structure

These do not need to be in order! (but it's nice if they are)

Characters are at the top level of the data hierarchy. Character data points to factions and locations, and faction/location data does not point back to characters.

## Stubs

Stubs are the base unit for a data entry for a character. It contains the character's name and unique `w-id` ("world id"). Characters without wiki pages should have an `excerpt` key with a 1-2 sentence description.

The data for npc stubs is located in the `_data/world/characters/` folder.

### Data Structure
| Field | Required | Data type| Description |
|-|-|-|-|
| name | Required | string | display name of the character |
| id   | Required | string | unique identifier used as the wiki URL. Usually the character's name, but lowercase and with dashes instead of spaces (e.g., Lord Scurlock's `id` is `lord-scurlock`.) |
| collection | Optional | string | The collection the character's wiki page belongs to, if the stub has been expanded into a dedicated wiki page. |
| excerpt | Optional | string | 1-2 sentence description of character, *only if* the character does not have a wiki page.|

### Example Entry (no dedicated wiki page)
{% highlight markdown %}
- name: Caleb Hollow
  id: caleb-hollow
  excerpt: Reconciled ghost and confidence man. Will do anything for a day as a vampire.
{% endhighlight %}

### Example Entry (dedicated wiki page)
{% highlight markdown %}
- name: Lord Scurlock
  id: lord-scurlock
  collection: npcs
{% endhighlight %}

## Pages
NPC pages can be found in the "npcs" collection, located at the path `/all_collections/_npcs`. When adding a new npc page, make a copy of the `_template.md` file located in the directory.

### Data Structure

Note: characters that have dedicated wiki pages still retain their stub data so the stubs can re-direct to the primary wiki page through the use of the `collection` and `id` keys.

### Required Values
| Field | Required | Data type| Description |
|-|-|-|-|
| full-name | Required | string | The full known name (not alias) of the npc. |
| w-id | Required | string | Matches the npc's stub `id`, used for filtering and page generation. |
| char-type | Required | string | Type of npc, as defined by which .yml file the stub is listed in (e.g., `criminals`, `nobles-and-notables`, etc.)    |
| faction-type | Required^\* | string | Only required if the `w-id` is also listed as a `faction` stub (e.g., Lugos, Lord Scurlock). This declares the type of faction, as defined by which .yml file the stub is listed in.  |
| excerpt | Required | string | 1-2 sentence description of the npc. |
| last_updated | Required | DD Month YYYY | Date the wiki page was last updated. |

### Optional Values
| Field | Required? | Data type| Description |
|-|-|-|-|
| alias | No | string | One or more aliases the character uses, separated by commas. List primary alias first.
| prefers-alias | No | bool | Set to `true` if the npc is better known by their primary alias than their full name, otherwise leave blank. |
|pronouns| No | string | the npc's preferred pronouns |
| status | No | string | status of the npc. if left blank, will default to `active`. Other options include `missing`, `incapacitated`, `hiding`, `dead`, `retired`, `presumed dead`, `incarcerated`, etc. |
| factions |    No | string | factions the npc is associated with, but does not share a `w-id` with. Format as `faction-type:faction-name` and separate with commas.|
| is-cohort | No | bool | set to `true` if the npc is a cohort of the Nameless, otherwise leave blank. |
| picture | No | string | the filename of the npc image in the `img_root` folder associated with the `_npcs` collection. Contact site admin (Parker or Vinnie) to set up a picture. |

### Example wiki headers

An example of an `npc` whose `w-id` is also associated with a faction.

```
# required
# This data in this header is used to reference this character across the entire website. 
full-name: Lord Scurlock
w-id: lord-scurlock
char-type: spooks-and-supernaturals
faction-type:   underworld
excerpt:        A dangerous vampire with powerful connections. Ancient and immutable.
last_updated: 17 Dec 2023

#optional
pronouns:       He/Him
status:         missing/presumed dead 
picture:        # contact site admin (Parker or Vinnie) to set up a picture.
```

An example of an `npc` with multiple `aliases`
```
# required
# This data in this header is used to reference this character across the entire website. 
full-name: Elia Wickham
w-id: elia-wickham
char-type: spooks-and-supernaturals
last_updated: 17 Dec 2023

#optional
pronouns: Any?
alias:          Old Wickham, Young Hamwick
prefers-alias:  # Set to "true" if your character uses their alias instead of their name; otherwise, leave blank.
pronouns:       any
status:         active
excerpt:        A pre-calamity ghost of a shadow witch, who has become "contagious" to those who interact with her spirit essence. Middling comedic actor.
picture:        # contact site admin (Parker or Vinnie) to set up a picture.
```

# NPC Metadata Structure

These do not need to be in order! (but it's nice if they are)

Characters are at the top level of the data hierarchy. Character data points to factions and locations, and faction/location data does not point back to characters.

| Field | Required | Data type| Description |
|-|-|-|-|
| name | Required | string | display name of the character |
| id   | Required | string | unique identifier used as the wiki URL |
| has-page| Optional | bool | default: empty. Set to `true` if the character has a dedicated wiki page. |
| excerpt | Optional | string | 1-2 sentence description of character. |
| alias | Optional | string | one or more aliases the character uses, separated by commas. |
| prefers-alias | Optional | bool | default: empty. Will use the character's alias in metadata-generated site content.|
| status | Optional | string | status of characteer; values: left blank, `dead`, `missing`, `in hiding`, `incarcerated`, or `incapacitated`. If left blank, site will default to displaying "active". |
| location | Optional | string | one or more location ids the character is associated with, starting with the current location, separated by commas. Will default to "duskvol" in metadata-generated content if left blank. |
| faction | Optional | string | one or more faction ids the character is associated with, separated by commas. |
| rival | Optional | string | one or more player characters this npc is a rival to, separated by commas. |
| friend | Optional | string | one or more player characters this npc is a friend to, separated by commas. |
|-|-|-|-|
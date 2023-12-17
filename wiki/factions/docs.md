# Factions Metadata Structure

These do not need to be in order! (but it's nice if they are)

Factions are at the second level of the data hierarchy.

| Field | Required | Data type| Description |
|-|-|-|-|
| name | Required | string | display name of the faction |
| id   | Required | string | unique identifier used as the wiki URL |
| tier | Required | int | Tier of the faction. Must be a number; leave empty if faction has been dismantled.|
| hold | Required | string | "S" for strong, "W" for weak. Leave empty if faction has been dismantled. |
| status | Required | int | Status of relations with the Nameless. Number between -3 and 3. Leave empty of faction has been dismantled. |
| has-page| Optional | bool | default: empty. Set to `true` if the faction has a dedicated wiki page. |
| excerpt | Optional | string | 1-2 sentence description of faction. |
| location | Optional | string | one or more location ids the faction is associated with, starting with the current location, separated by commas. Will default to "duskvol" in metadata-generated content if left blank. |
|-|-|-|-|
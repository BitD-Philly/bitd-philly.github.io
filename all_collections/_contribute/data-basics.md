---
---
# Intro to Stubs and Pages

<div id="toc" markdown="1">
<b>Contents</b>
* TOC
{: toc}
</div>

Once you've gotten comfortable editing existing wiki pages, you might be interested in adding new things to the wiki. This page goes over the basics of how the wiki data is organized and the processes for adding new entities to the wiki!

<div style="clear:both;"></div>

# Stubs and Pages

Our version of Duskvol has all sorts of interesting people, places, and things, but not every entity has enough information to need its own dedicated wiki page. So, in order to keep the website files relatively neat, we start small when adding new things and scale them up as needed.

We accomplish this through the use of **stubs** and **pages**.

## Stubs
A ***stub*** is the minimum data associated with an entity in the Nameless Wiki.

Stubs are very small -- usually just the entity's name, a unique *world id*, or `w-id`, and maybe a short description or some associated game data. All wiki stubs are stored in the Github repo's `_data/world/` folder in .yml files, which you can find at <https://github.com/BitD-Philly/bitd-philly.github.io/tree/content/_data/world>.

For example, this is a stub for the NPC "Lugos", which is stored with other similar npc stubs in the `characters/spooks-and-supernaturals.yml` [file](https://github.com/BitD-Philly/bitd-philly.github.io/tree/content/_data/world):

```
- name: Lugos
  w-id: lugos
  excerpt: Remorseless clockwork robotic assassin. Massacre fetishist. Decapitated currently.
```

This is the stub for the Dimmer Sisters faction, located in the `factions/underworld.yml` file:
```
- name: The Dimmer Sisters
  id: the-dimmer-sisters
  tier: 2
  hold: S
  status: 0
  excerpt: Ancient gang of witches with a subterranean temple hideout and a large body chock-full of ghosts.
  ```

The data from these stubs is used to build the landing pages on the wiki, such as the [NPC](/wiki/npcs) or [faction](/wiki/factions) pages -- which means adding a new stub to a data file will automatically add the entity into the landing page without any extra work.

Different types of stubs have different data requirements; when adding a new stub, make sure to refer to the appropriate metadata documentation -- for instance, the [NPC Metadata reference page](npc-data).

## Pages

A ***page*** is a dedicated webpage for a given entity in the Nameless wiki.

Pages can (obviously) contain much more information and have a lot more flexibility than stubs, but they are more time-intensive to create, so only a subset of stubs will end up with wiki pages.

Pages are stored in *collections*, located in the Github Repo's `all_collections` folder. Only some collections are wiki collections: as of Jan 1, 2024, the wiki collections are `_player_characters`, `_npcs`, `_factions`, and `_locations`.

Wiki pages all start with a header called *front matter*, which is text situated between two lines of three dashes each. This metadata is used to build the entity's wiki page layout and other related pages across the site. Each collection has different requirements for front matter, so make sure to check the appropriate metadata documentation when creating a new page, such as the [NPC Metadata reference page](npc-data).

Here is some example front matter for a player character page:

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
status: active
desc: Mysterious gunslinger, pistol enthusiast. Has a hawk. Never comfortable.
picture: Sizzle.png
---
{%endhighlight%}

Note that all non-player-character wiki pages retain their original stubs, which are updated to redirect to the page's collection. The stub and the page can be cross-referenced using the `w-id`, which doubles as the URL of the page.

# Promoting a Stub to a Page

-- coming soon! --
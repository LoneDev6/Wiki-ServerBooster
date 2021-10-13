---
description: config_entity_limiter.yml
---

# 🐖 Entity limiter

{% hint style="info" %}
This configuration helps **reducing enity counter **in the server to **avoid lag**.\
This is an alternative to stacking plugins as they alter gameplay stacking entities into a single one.\
\
ServerBooster lowers down server lag just limiting entity groups without alterating the gameplay.
{% endhint %}

(Description of the option is in gray)

```yaml
#language of the messages (in lang_limiter folder)
lang: en
# Radius in blocks to check for mobs
radius: 56 
# ticks for a farm animal to grow up
growth_ticks: -1 
# dev option
relative_age: false 
# shows message in console when an entity spawn is denied
debug: false 

age-limiter-enabled: false
breeding-limiter-enabled: false
# enable limits by sheep colors (can make lag)
sheep-color-check: false 
# farm animal breeding cooldown in ticks (-1 to disable)
breeding_ticks: -1 
# will block also plugin spawned mobs. Please enable this at your own risk
force-spawn-deny: true 
# enabling this should boost performance of mob removal on spawn
cancel-event-instead-of-remove-entity: true 
# ignore every rule for these entity types
spawn-whitelist:
  types:
    - ARMOR_STAND
    - ITEM_FRAME
    - DROPPED_ITEM
    - PAINTING
# which worlds do you want these options to be applied
worlds:
  - world
  - world_nether
  - world_the_end

# this is the default setting for mobs that are not in the "limites" list
defaults:
  # Enable age limiting and remove the mob after a number of ticks. 
  # (e.g. 18000 for 15 minutes) Set -1 to ignore the age.
  age: -1
  # The maximum number of a mob type to be allowed to spawn in a 
  # "view distance" defined by radius. Set -1 to ignore radius.
  radius_max: 10 
  # The maximum number of a mob type to be allowed to spawn in a single chunk.
  # Set -1 to ignore max entities of this type in chunk.
  chunk_max: 5 
  # If set to a value other than -1, the number of mobs to not be removed 
  # on chunk unload.
  # Set -1 to avoid deleting excess entities on chunk unload.
  cull: 5 
```

### Example entityies limits

```yaml
limits:
  # limits zombie villagers: 
  # Only 15 can spawn in a radius of 56 blocks (radius is set on the top of this page).
  # Only 4 can spawn in the same chunk.
  # Only 10 will remain on chunk unload. Others will be removed.
  zombie_villager:
    radius_max: 15
    chunk_max: 4
    cull: 10
  # limits enderman:
  # Only 7 can spawn in a radius of 56 blocks (radius is set on the top of this page).
  # Only 4 can spawn in the same chunk.
  # No enderman will remain on chunk unload. They all will be removed.
  enderman:
    radius_max: 7
    chunk_max: 4
    cull: 0
```

{% hint style="warning" %}
To avoid entities from being removed (like enderman farms entities and similar) you have to **rename **the **entities **using a [nametag](https://minecraft.gamepedia.com/Name_Tag).

There are some methods to avoid entity removal:

* **rename **the entities using nametag
* put the entity on a **vehicle **(**minecart**, **boat**)
* make the entity **Invulnerable **(NBT tag)
* **tame **the entity (only **dog**, **cat**...)
* entity has an **item equipped **(armor, item in hand)
* is a [Guardian ](https://minecraft.gamepedia.com/Guardian)or [Elder Guardian](https://minecraft.gamepedia.com/Elder_Guardian)
{% endhint %}




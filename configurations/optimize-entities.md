---
description: config_optimize_entities.yml
---

# Optimize entities

{% hint style="info" %}
This config allows you to:

* override and optimize spigot.yml and bukkit.yml configurations in a single place
* limit entities AI to avoid useless CPU processing
{% endhint %}

\(Description of the option is in gray\)

```yaml
### Override bukkit.yml and spigot.yml configs
# ALL THESE SETTINGS ARE SPIGOT.yml SETTINGS. Search online about a good explaination. 
# ServerBooster just overrides these values ignoring the spigot.yml values
# https://www.spigotmc.org/wiki/spigot-configuration/
# https://bukkit.gamepedia.com/Bukkit.yml

override_spigot_bukkit_configs: true
mob-spawn-range: 3
entity-activation-range:
  tick-inactive-villagers: false
  animals: 16
  monsters: 16
  raiders: 25
  misc: 2
ticks-per:
  animal-spawns: 70
  monster-spawns: 6
spawn-limits:
  monsters: 7
  animals: 2
  water-animals: 1
  ambient: 1

######################################################################################################
# Special functions only available on Spigot 1.14+, won't be activated if 
# server version is below 1.14
######################################################################################################
#Log when the plugin untrack entities
log-to-console: false
log-detailed: false
log-tps:
  enabled: false
  interval: 1200

# DO NOT ENABLE. Can cause excessive amount of mobs spawned: 
# Disable tick for untracked entities (experimental, use at your own risk).
# Minecraft won't see these entities anymore until they are unfrozen 
# by the plugin, so the server will spawn more entities
# thinking there is no entitity.
disable-tick-for-untracked-entities: false
#disable ai for untracked entities
disable-ai-for-untracked-entities: true

trigger-options:
  # If set to true: optimization takes place every "untrack-ticks" 
  # also if tps is not below value specified in "when-tps-below"
  always:
    enabled: true
    # How many ticks between untrack process
    # The untrack process will check for untracked entities by players 
    # but still by the server, and untrack them.
    untrack-ticks: 600
  when-tps-below:
    enabled: true
    # if tps are not below this value, the task will not perform the untrack
    # and it will wait for the next run
    value: 18.5
    # How many ticks between untrack process
    # The untrack process will check for untracked entities by players 
    # but still by the server, and untrack them.
    untrack-ticks: 450


#frecuency in ticks to check untracked entities
#It will check for players traking entities and will track it again 
#(this is to prevent invisible entities)
check-untracked-entities-frequency: 35

#Distance in blocks to check for players near untracked entities
tracking-range: 35

#Entities with these properties will be ignored from optimization. 
#You should leave this as default
ignore:
  custom-named: false
  invulnerable: false
  drops: true
  itemframes: true
  armorstands: true
  villagers: false

#which worlds do you want these options to be applied
worlds:
  - world
  - world_nether
  - world_the_end
```


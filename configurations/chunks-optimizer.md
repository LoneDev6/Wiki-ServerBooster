---
description: chunks_optimizer.yml
---

# Chunks optimizer

{% hint style="info" %}
This config allows to optimize how chunks are managed in Minecraft.  
What you can do:

* **detect chunks** with **lagging** mechanics \(redstone machines, 0 tick machines, water or lava lagging the server, plugins listening to high frequency block updates\)
* **lower down chunks packets** sending **frequency** to players if the server TPS is low or if the player ping is high \(to avoid player losing connection if they have slow internet\)
* **unload chunks** from **RAM** when players are not around them, to avoid high RAM usage, low TPS and crash
{% endhint %}

\(Description of the option is in gray\)

```yaml
slow-down-chunk-packets:
  # slow down chunks packets sending when TPS is below this value
  when-tps-below:
    enabled: true
    value: 19
  # slow down chunks packets sending when player ping is below this value
  when-high-player-ping:
    enabled: true
    value: 150
  # only in these worlds
  worlds:
    - world
    - world_nether
    - world_the_end
block-physics-lag-detector:
  enabled: true
  # detect chunks lagging only when TPS is below this value
  low-tps: 18
  lag:
  # notify lag only after these ticks (example 950000) to avoid message spam
    warning-threshold: 950000
  # notify online OP players
    notify-op: true
  # enable this to cancel the lagging event (to block the lagging machine for example)
    cancel-event: false
  # only in these worlds
  worlds:
    - world
    - world_nether
    - world_the_end
unload-chunks:
  enabled: true
  # unload chunks with no players only after some ticks (example 6000)
  interval-ticks: 6000
  log:
    # log the unload event in console
    unload: true
  # only in these worlds
  worlds:
    - world
    - world_nether
    - world_the_end
```


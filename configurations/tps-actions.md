---
description: config_tps.yml
---

# 🏃 TPS actions

{% hint style="info" %}
This config allows you to execute commands when a low TPS value is reached.

You can create as many as groups you want. Also commands are unlimited.

You can use these placeholders in commands: {tps}
{% endhint %}

This config is just an example, it's not really useful to remove items on the ground:

```yaml
tps-commands:
  enabled: false
  commands:
    group_1:
      tps: 16
      delay_ticks: 36000
      list:
        command_1:
          command: "broadcast Server is lagging ({tps} tps). Please be patient. "
          delay_ticks: 0
        command_2:
          command: "broadcast Removing entities on the ground in 60 seconds..."
          delay_ticks: 20
        command_3:
          command: "minecraft:kill @e[type=item]"
          delay_ticks: 1200
```

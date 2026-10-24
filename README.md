# MBM Mod (Fabric, Minecraft 1.21.11, client-side)

Open the menu with **Right Shift**. The menu is black with the MBM logo; every entry is a clickable toggle.

## Features

- **Player Activity** - scans for fully grown kelp, vines and amethyst buds/clusters ("shards") and
  draws a **green box** around the nearest 150. Scanning skips empty chunk sections and is capped at
  about 2 ms per tick, so it does not lag.
- **Tunneler** - bot that digs a 1-wide tunnel in the direction you were facing (snapped to N/S/E/W),
  picks the best pickaxe in your hotbar, keeps itself centered, and stops on liquid, bedrock or low
  health. The menu has a height toggle (2 = walkable, 1 = crawl-size).
- **Freecam** - detached camera. W/A/S/D fly, Space up, Left Shift down, Left Ctrl for speed. Your
  player stands still. Turn it off in the menu (or Right Shift, then click Freecam).
- **Chest / Hopper / Dispenser / Crafter ESP** - separate toggles, boxes visible through walls
  (chest = orange, hopper = gray, dispenser = blue, crafter = purple). Trapped chests count as chests.

## Build

Needs JDK 21. The easiest way is to open this folder in IntelliJ IDEA (it sets up Gradle for you) and
run the `build` task. From a terminal, with Gradle 8.14 or newer installed:

```
gradle build
```

(Or run `gradle wrapper --gradle-version 8.14.3` once to create `gradlew`, then use `./gradlew build`.)

The jar is `build/libs/mbm-mod-1.0.0.jar` (not the `-sources` one). Put it in your `mods` folder next to
Fabric API for 1.21.11 (Fabric Loader 0.18.1 or newer).

If Gradle cannot resolve a version in `gradle.properties`, copy the current values for 1.21.11 from
https://fabricmc.net/develop/ .

## Notes

- Boxes are drawn as a 2D overlay projected from the camera, which is why they show through walls and
  cost almost nothing. They use your FOV setting, so they can drift slightly while sprint FOV
  effects are active.
- Many servers forbid automation, freecam and ESP. Check the rules before using it online.

# Project Apocalyptic

A single-player, top-down pixel-art zombie-apocalypse survival game for the browser.

## Current build

**Prototype 0.4 — Living World & Settlement Survival Overhaul.** The game is a self-contained HTML5 Canvas project. Open `index.html` in a modern browser or serve the folder with a static HTTP server. No build step or external dependencies are required.

## Controls

| Input | Action |
| --- | --- |
| WASD / Arrow keys | Move |
| Shift | Sprint |
| Mouse | Aim |
| Left click | Fire |
| Space | Melee attack |
| E | Interact with nearby settlement objects, scavenge, enter/search a building, or exit an interior |
| R | Reload |
| I | Open / close inventory |
| Settlement panel | Build defenses, storage, generator, rain barrel, farm plot, campfire, and bedroll; craft and manage supplies |
| Escape | Pause / resume |

## Implemented systems

- Large scrollable county map, road network, environmental details, buildings, vegetation, and loot.
- Dedicated transparent SVG sprite sheets for the survivor and walkers, with four directional rows and four animation frames per direction.
- Directional sprite rendering, walking cycles, weapon recoil, and melee swing animation.
- Enterable building interiors with floorboards, distinct furniture arrangements for residences, clinics, shops, gas stations, and warehouses, a searchable container, and an explicit marked exit interaction.
- Inventory with item icons and stack counts; usable bandages, food, and water, plus ammunition magazines that replenish reserve ammo.
- Equipment slots for weapon, clothing, and backpack, with basic loadout switching.
- Inventory and equipment loadout persisted in local saves alongside player progress and searched-world state.
- Walker perception, sound investigation, pursuit, searching, group alerting, and corrected flank-target reset when a walker reacquires direct sight.
- Horde migration events and flanking/encirclement approach targets around the player.
- Pistol combat, melee, ammunition, hit particles, and synthesized browser audio effects.
- Dynamic clear, overcast, rain, and fog weather states with screen-space rain/fog rendering.
- Hunger and thirst drain over time; starvation and dehydration damage health. Eat canned/cooked food and drink bottled or collected water.
- Settlement construction: barricades, fences, gates, snares, storage crates, generators, rain barrels, farm plots, campfires, bedrolls, work tables, and chairs.
- Defenses block movement and have durability; alerted walkers can converge on and break barricades, fences, and gates.
- Storage containers allow one-item-at-a-time depositing and withdrawal. Generator fuel powers a larger nearby night-visibility radius.
- Rain barrels collect water during storms. Farm plots grow crops over time, faster in rain, and can be harvested.
- Crafting for planks, prepared meals, and snare materials; campfires heat canned food or cook raw meat.
- Clickable abandoned belongings provide short environmental-story fragments; blood pools and trails mark disturbing scenes.
- Time-shifting building shadows, tree shadows, ambient darkness, and reduced night visibility. Walkers see farther and move faster at night.
- Settlement objects, fuel/water/storage state, farming progress, belongings, blood marks, hunger, and thirst persist in local saves.

## Current limitations

This is an actively evolving prototype. The sprite sheets are dedicated pixel-art SVG atlases generated for the game, not hand-painted high-resolution raster sheets. Interiors currently use a shared room layout with a searchable container rather than unique floor plans for each building. Equipment slots and item effects are a foundation for deeper gear statistics, durability, clothing protection, and capacity rules. The backpack slot remains a placeholder rather than a capacity system. Storage interaction currently moves one item per interaction. Farming is an abstract growth timer rather than a full soil, crop-rotation, and irrigation simulation. Rainwater is collected but purification is not yet implemented. Generator power is represented by a local night-visibility radius rather than a full electrical grid. Audio is synthesized through Web Audio rather than recorded asset files. Hordes use lightweight migration and surround-target steering rather than full navigation meshes or persistent off-screen simulation.

## Project direction

- Detailed pixel-art presentation and animation
- Large interconnected open world
- Single-player survival, scavenging, weapons, crafting, and settlements
- Believable walkers and dynamic hordes
- Persistent player and world progression

The project is an original zombie-survival game inspired by the atmosphere and survival tension of the genre.

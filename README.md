# Project Apocalyptic

A single-player, top-down pixel-art zombie-apocalypse survival game for the browser.

## Current build

**Prototype 0.4 — Living World & Settlement Survival Overhaul.** The game is a self-contained HTML5 Canvas project. Open `index.html` in a modern browser or serve the folder with a static HTTP server. No build step or external dependencies are required.

## Controls

| Input | Action |
| --- | --- |
| WASD / Arrow keys | Move |
| Shift | Sprint |
| Mouse / pointer | Aim |
| Touch / pointer | Tap to fire or inspect nearby evidence; use keyboard movement on supported devices |
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
- Hunger and thirst drain over time; starvation and dehydration damage health. Eat canned/cooked food and drink bottled water or boiled rainwater.
- Settlement construction: barricades, fences, gates, snares, storage crates, generators, rain barrels, farm plots, campfires, bedrolls, work tables, and chairs.
- Defenses block movement and have durability; alerted walkers can converge on and break barricades, fences, and gates.
- Storage containers allow one-item-at-a-time depositing and withdrawal. Generator fuel powers a larger nearby night-visibility radius.
- Rain barrels collect untreated rainwater during storms. Use a campfire to boil it before drinking. Farm plots grow crops over time, faster in rain, and can be harvested.
- Crafting for planks, prepared meals, and usable snare kits. Planks are required for wooden construction; campfires boil rainwater, heat canned food, and cook raw meat.
- Expanded field crafting: water filters, first-aid kits, reinforced backpacks, rain ponchos, and handmade spears with distinct melee reach/damage. Backpack, poncho, spear, filter, and medical kit equipment can be equipped or used from the pack.
- County power-grid deterioration: municipal power fades over the opening stretch of the outbreak, town lighting fails, and fueled generators become the dependable source of powered safehouse light.
- Handheld radio with battery-powered frequency scans, survivor distress calls, emergency warnings, evacuation rumors, power-grid alerts, and environmental lore.
- Dynamic county events: supply drops, vehicle crashes, spreading fires that attract walkers, and survivor distress beacons. Event locations persist and can be investigated for rewards.
- Five-tier safehouse progression at a work table. Upgrades consume increasingly scarce materials, improve shelter defenses, and reduce ongoing hunger/thirst drain.
- Expanded county districts with a dense forest, farm fields, suburban streets, rural settlements, and industrial blocks.
- Clickable abandoned belongings provide short environmental-story fragments; blood pools and trails mark disturbing scenes.
- Time-shifting building shadows, tree shadows, ambient darkness, and reduced night visibility. Walkers see farther and move faster at night.
- Settlement objects, fuel/water/storage state, farming progress, belongings, blood marks, hunger, and thirst persist in local saves.

## Current limitations

This is an actively evolving prototype. The sprite sheets are dedicated pixel-art SVG atlases generated for the game, not hand-painted high-resolution raster sheets. Interiors currently use a shared room layout with a searchable container rather than unique floor plans for each building. Equipment slots and item effects are a foundation for deeper gear statistics, durability, clothing protection, and capacity rules. The field backpack can be equipped and increases reserve-ammunition carrying capacity; a full weight-based inventory capacity model remains future work. Storage interaction currently moves one item per interaction. Farming is an abstract growth timer rather than a full soil, crop-rotation, and irrigation simulation. Rainwater boiling is implemented at campfires; more advanced filtration and water-source simulation remain future work. The electrical grid now deteriorates over time and powers selected town districts before failing; generators provide local backup light. This is still a lightweight regional simulation rather than a building-by-building utility network. Audio is synthesized through Web Audio rather than recorded asset files. Hordes use lightweight migration and surround-target steering rather than full navigation meshes or persistent off-screen simulation.

## Project direction

- Detailed pixel-art presentation and animation
- Large interconnected open world
- Single-player survival, scavenging, weapons, crafting, and settlements
- Believable walkers and dynamic hordes
- Persistent player and world progression

The project is an original zombie-survival game inspired by the atmosphere and survival tension of the genre.


## Deploy to Vercel

This repository is configured as a **static site**. The game runs directly in the browser; there is no Node.js build, package installation, or server runtime required.

1. Push the repository to GitHub.
2. In Vercel, choose **Add New → Project** and import `relaymann/projectapocalyptic`.
3. Keep the project root set to the repository root.
4. Use the **Other** framework preset. The repository's `vercel.json` sets the output directory to `.` (the repository root).
5. Leave the build command empty, then deploy.

Vercel will serve `index.html` at the project URL and publish the `assets/` directory alongside it. Future commits pushed to the connected `main` branch will trigger deployments automatically. You can also deploy from the Vercel dashboard after importing the project.

The game currently stores progress in the browser's local storage, so saves are local to the browser/device and are not automatically shared between devices.

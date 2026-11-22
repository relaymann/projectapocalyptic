# Project Apocalyptic

A single-player, top-down pixel-art zombie-apocalypse survival game for the browser.

## Current build

**Prototype 0.5 — Powered Safehouse & Food Preservation Overhaul.** The game is a self-contained HTML5 Canvas project. Open `index.html` in a modern browser or serve the folder with a static HTTP server. No build step or external dependencies are required.

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
- Settlement construction: barricades, fences, gates, snares, storage crates, generators, rain barrels, farm plots, campfires, bedrolls, work tables, chairs, solar panels, battery banks, wiring junctions, pumps, pipe sections, refrigerators, pantries, watch posts, spike barriers, irrigation nodes, and drying racks.
- Defenses block movement and have durability; alerted walkers can converge on and break barricades, fences, and gates.
- Storage containers, refrigerators, and pantries support item-by-item food storage and withdrawal. Powered refrigerators preserve stored perishables; pantries slow spoilage, while unpowered refrigeration no longer protects stored food.
- Electrical utility network: generators, solar panels, battery banks, wire junctions, and connected loads. Wire junctions form a proximity-linked network; solar charges connected batteries during daylight, while powered pumps, refrigerators, and irrigation consume battery charge.
- Water utility network: rain barrels, pipe junctions, pumps, and irrigation. Rain refills barrels; connected powered pumps transfer rainwater into a cistern, and the player can collect pumped water. Irrigation consumes stored pump water to improve nearby crop growth.
- Defensive spike barriers can be armed and damage walkers; watch posts and elevated guard towers extend the survivor's early-warning radius. Reinforced walls and gates have higher durability and can be attacked and breached by walkers.
- Enterable buildings now have powered interior lighting, an indoor water tap, a refrigerator, and a persistent storage room. Taps require a powered pump connected through pipe junctions; refrigerators require a working electrical source and spoil food when unpowered.
- Exterior building windows glow when the building has power. Buildable floodlights illuminate larger areas when connected to an active power source.
- New settlement construction: reinforced walls, reinforced gates, guard towers, floodlights, and larger storage lockers.
- Expanded agriculture produces fresh produce. Salt-cured food and drying racks provide longer-lasting rations.
- Rain barrels collect untreated rainwater during storms. Powered pumps draw from nearby barrels through direct connections or pipe sections and accumulate water for collection. Campfires still boil untreated rainwater before drinking.
- Safehouse electrical network: solar panels generate daytime power and charge nearby battery banks; batteries can supply local appliances after dark. Wiring junctions extend the connection radius, while grid power and fueled generators remain additional sources. Refrigerators require power and slow carried-food spoilage; pantry and refrigerator containers also store food.
- Food and agriculture: rain and powered irrigation accelerate crop growth, fertilizer boosts a planted plot, and harvests yield fresh produce. Fresh produce, cooked meals, and raw meat can spoil over time; powered refrigeration delays spoilage. Drying racks gradually turn raw meat into preserved food, and the preserve-food action converts raw meat or fresh produce into a longer-lasting ration.
- Defensive and observation upgrades: armed spike barriers damage walkers that cross them, while watch posts expand the nearby-walker warning radius. Snare traps remain available as a separate reusable defense.
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
- Settlement electrical control console: a master breaker disconnects safehouse circuits, and every building has an independently switchable interior/exterior light circuit. The live management dashboard reports estimated electrical demand, grid/local source status, battery charge, total water reserves, stored food, and defensive integrity.
- Buildable 100-unit water storage tanks with visible fill gauges. Tanks transfer water from connected powered pumps through the pipe network, can supply connected building taps, and preserve their levels in saves.

## Current limitations

This is an actively evolving prototype. The sprite sheets are dedicated pixel-art SVG atlases generated for the game, not hand-painted high-resolution raster sheets. Interiors currently use a shared room layout with a searchable container rather than unique floor plans for each building. Equipment slots and item effects are a foundation for deeper gear statistics, durability, clothing protection, and capacity rules. The field backpack can be equipped and increases reserve-ammunition carrying capacity; a full weight-based inventory capacity model remains future work. Storage interaction currently moves one item per interaction. Farming remains an abstract crop-growth model rather than a full soil, crop-rotation, and seasonal simulation. Plumbing and electrical wiring use proximity-based connection ranges rather than a tile-by-tile pipe/wire construction editor. Solar generation, battery charge, pumps, refrigeration, irrigation, and generator/grid power are simulated locally, not as a full electrical engineering model. Food spoilage uses a simplified timer and item stacks rather than per-item freshness tracking. Watch posts expand the HUD warning radius rather than providing a staffed lookout or binocular interface. Spike barriers are simple one-use damage obstacles. Audio is synthesized through Web Audio rather than recorded asset files. Hordes use lightweight migration and surround-target steering rather than full navigation meshes or persistent off-screen simulation.

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

# Project Apocalyptic

A single-player, top-down pixel-art zombie-apocalypse survival game for the browser.

## Current build

**Prototype 0.2** is a self-contained HTML5 Canvas game. No build step or external dependencies are required.

### Run locally

Open `index.html` in a modern desktop browser, or serve this folder with any static HTTP server.

### Controls

| Input | Action |
| --- | --- |
| WASD / Arrow keys | Move |
| Shift | Sprint |
| Mouse | Aim |
| Left click | Fire |
| Space | Melee attack |
| E | Scavenge nearby loot or buildings |
| R | Reload |
| Escape | Pause / resume |

### Implemented systems

- Large, scrollable county map with layered grass, road markings, environmental debris, vegetation, and detailed building exteriors
- Animated top-down pixel-character and walker movement cycles
- Player movement, aiming, sprinting, health, stamina, combat, and reloads
- Walkers with field-of-view vision checks and building line-of-sight obstruction
- Hearing-based sound investigation for gunshots, sprinting footsteps, and nearby activity
- Walker states for wandering, investigating, searching last-known locations, and pursuing
- Nearby walkers can be alerted and drawn toward disturbances
- Basic steering recovery when walkers encounter obstacles
- Ammunition, scavenging, searchable buildings, medical supplies, and local save data
- Day/night lighting and player-centered visibility

### Current limitations

This is an evolving gameplay prototype, not the finished game. Character art is currently rendered from custom pixel primitives rather than imported sprite-sheet assets. Building interiors, a full inventory/equipment UI, crafting, vehicles, survivor NPCs, advanced navigation/pathfinding, audio assets, and robust save slots remain planned.

## Project direction

- Detailed pixel-art presentation
- Large interconnected open world
- Single-player first
- Survival, scavenging, weapons, crafting and settlements
- Believable walkers and dynamic hordes
- Persistent player and world progression

The project is an original zombie-survival game inspired by the atmosphere and survival tension of the genre.

# 🎮 Dungeon Gunner

Dungeon Gunner is a 2D top-down dungeon shooter built in **Unity**. The player selects a character, explores procedurally generated dungeon levels, clears enemy rooms, collects chest rewards, manages weapons and ammo, and fights boss encounters to progress through the run.

The project focuses on a complete gameplay loop rather than a single isolated prototype: procedural dungeon generation, room-based combat, character selection, weapons, enemies, chests, score, high scores, minimap support, audio, VFX, and UI are all connected into one playable structure.

<p align="center">
  <a href="https://qanht.itch.io/dungeon-gunner">
    <img src="https://img.shields.io/badge/🎮_Play_on_itch.io-Dungeon_Gunner-fa5c5c?style=for-the-badge&logo=itchdotio&logoColor=white" />
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active%20Development-brightgreen" />
  <img src="https://img.shields.io/badge/Unity-6000.3.10f1-blue" />
  <img src="https://img.shields.io/badge/License-MIT-green" />
</p>

---

## Overview

Designers author room templates, room node graphs, enemy pools, chest reward tables, weapons, ammo, music, and character data as ScriptableObjects and prefabs. At runtime the game selects a room graph, places compatible room templates without overlap, connects matching doorways, and activates combat encounters as the player enters rooms — assembling a complete, variable run from authored content.

## Gameplay

- Choose from multiple playable characters such as The Thief, The Scientist, and The General.
- Explore dungeon layouts assembled from authored room templates and room node graphs.
- Fight through locked combat rooms where doors open only after all enemies are defeated.
- Use mouse aiming, projectile weapons, reload timing, and dodge rolling during combat.
- Collect health, ammo, and weapon rewards from chests.
- Build score through enemy kills and an accuracy-based multiplier.
- Progress across multiple dungeon levels and reach boss encounters after regular rooms are cleared.

## Core Features

- Procedural dungeon generation using room templates, room node graphs, doorway matching, bounds checking, and layout retries.
- Data-driven gameplay using ScriptableObjects for players, movement, enemies, weapons, ammo, rooms, dungeon levels, music, sound effects, and VFX.
- Event-driven character architecture for movement, aiming, firing, reloading, health, destruction, score, and UI updates.
- A* enemy pathfinding using room tilemap collision data, preferred path tiles, and dynamic movable obstacles.
- Weapon and ammo system with clip ammo, reserve ammo, reloads, fire rate, precharge, projectile spread, burst spawning, trails, hit effects, and ammo patterns.
- Room encounter system with enemy spawn tables, level-specific enemy counts, spawn intervals, concurrent enemy limits, battle music, and room-clear events.
- Object pooling for projectiles, weapon effects, ammo hit effects, and sound effects.
- UI systems for character selection, health, weapon status, ammo, score, pause menu, high scores, minimap, and dungeon overview map.

## Technical Highlights

- Unity 6000.3.10f1
- 2D Tilemap-based dungeon rooms
- Universal Render Pipeline
- Cinemachine camera support
- ScriptableObject-based content authoring
- Custom room node graph workflow with a custom editor
- Component-based actor design
- Global and local event systems
- Object pooling
- A* pathfinding
- High score persistence

## Controls

| Input | Action |
| --- | --- |
| WASD / Arrow keys | Move |
| Mouse | Aim |
| Left mouse button | Fire |
| Right mouse button while moving | Roll |
| Mouse wheel / number keys | Switch weapon |
| R | Reload |
| E | Interact / use item |
| Tab | Dungeon overview map |
| Escape | Pause |

## Main Systems

| System | Description |
| --- | --- |
| Dungeon Generation | Builds each level from a random room graph and compatible room template pool. |
| Room Combat | Locks rooms during enemy encounters and unlocks them after all spawned enemies are defeated. |
| Player | Handles character data, health, movement, rolling, aiming, weapon inventory, and interactions. |
| Enemies | Supports materialization, A* chase movement, ranged weapon AI, line-of-sight checks, health, and score rewards. |
| Weapons | Uses reusable runtime weapon state backed by ScriptableObject weapon and ammo definitions. |
| Chests | Spawns rewards on room entry or after combat, including health, ammo, and weapons. |
| Scoring | Event-driven score and accuracy multiplier, clamped and persisted as high scores on win or loss. |
| Audio & VFX | Data-driven music, sound effects, and particle effects played through pooled objects. |
| UI | Displays player health, weapon status, ammo, score multiplier, menus, high scores, minimap, and dungeon overview. |

## Project Structure

| Folder | Purpose |
| --- | --- |
| `Assets/Scripts` | Main gameplay, systems, UI, tools, and architecture code. |
| `Assets/Prefabs` | Player, enemy, dungeon, UI, ammo, weapon, sound, chest, and environment prefabs. |
| `Assets/ScriptableObjectAssets` | Data assets for players, enemies, weapons, rooms, levels, sounds, and dungeon graphs. |
| `Assets/Scenes` | Main menu, gameplay, character selector, instructions, and high score scenes. |
| `DOCs` | Additional GDD and codebase architecture documentation. |

Within `Assets/Scripts`, code is organized by system, including: `AStar`, `Chests`, `Dungeon`, `DungeonMap`, `Effects`, `Enemies`, `Environment`, `GameManager`, `Health`, `Minimap`, `Movement`, `NodeGraph`, `Player`, `PoolManager`, `Sounds`, `StaticEvents`, `UI`, `Utilities`, and `Weapons`.

## Documentation

More detailed project documentation is included in:

- `DOCs/Game_Design_Document.md`
- `DOCs/Codebase_Architecture_And_Refactoring_Guide.md`

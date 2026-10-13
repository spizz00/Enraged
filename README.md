# Enraged

A fast 2D precision platformer made for the UM Game Jam. Climb to the chest as fast as you can, but every hit scrambles your controls, and too many hits send you into a berserk rage.

Link to itch.io: https://spizz00.itch.io/enraged

## About
Reach the victory chest in the shortest time you can and post your score to the global leaderboard.

Built in **Unity** with C# during the UM Game Jam 2026.
Team of 3 | 48 Hours

## Features
- Responsive platformer movement: coyote time, jump buffering, variable jump height, wall slide, wall jump, dash with cooldown, and drop-through platforms
- **Control scrambling:** getting hit randomly swaps two of your control bindings for a few seconds
- **Rage meter:** each hit fills the meter, and a full meter triggers a timed berserk state
- Enemy variety: patrolling and chasing ground enemies, flying enemies with line-of-sight detection, and wall crawlers
- Run timer and **global leaderboard** (Unity Gaming Services)
- Pause menu, main menu, and victory screen

## Technical Notes
**Player controller** (`PlayerController.cs`)
- Uses coyote time and a jump buffer so jumps feel forgiving, with extra gravity on the way down for a snappier arc.
- Wall slide and wall jump use raycasts against a wall layer; dash and drop-through are coroutines.

**Damage and rage system** (`DamageSystem.cs`, `ControlRandomizer.cs`)
- State flags for scrambled, berserk, and cooldown states decide when the player can be hit.
- `ControlRandomizer` keeps an action dictionary and swaps two entries at random, then routes input through it.

**Enemy AI** (`GroundEnemy.cs`, `FlyingEnemy.cs`, `WallCrawler.cs`)
- Ground enemies patrol, turn at platform edges, flip when stuck, and chase within a vision radius.
- Flying enemies chase only when a raycast confirms line of sight.

**Leaderboard** (`GlobalLeaderboard.cs`)
- Anonymous sign-in with Unity Gaming Services, and async score submission and loading. If the network fails, the game still shows the menu buttons.

## Tech
- Unity [version], C#
- Unity Input System, Unity Gaming Services (Authentication, Leaderboards)
- Git / GitHub

## Controls
| Action | Key |
|---|---|
| Move | [WASD] |
| Jump | [Space] |
| Dash | [Left Shift] |
| Drop down | [S] |
| Pause | [Esc] |

## Credits
[Art, music, and sound effects, and where they came from.]

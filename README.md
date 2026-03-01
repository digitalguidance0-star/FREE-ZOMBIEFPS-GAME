# ☠ NACHT DER UNTOTEN — ZOMBIE ASSAULT

> *"Classified // Black Ops // Eyes Only"*

A fully self-contained, browser-based first-person zombie wave survival shooter built entirely in a single HTML file using **Three.js (r128)** and the **Web Audio API**. No build tools. No dependencies beyond a CDN script tag. Just open and play.

---

## 🎮 Overview

**Nacht Der Untoten: Zombie Assault** is an immersive, feature-rich FPS survival game inspired by classic wave-based zombie modes. Fight through endless waves of increasingly dangerous undead across a procedurally-lit, atmospheric bunker environment. Every system — from the 3D renderer to the audio engine to the HUD — is hand-coded *BY AI*  and contained in one file.

---

## ✨ Feature Highlights

### 🔫 Combat Systems
- **4 Weapons** — M1919 LMG, STG-44 Assault Rifle, PTRS-41 Anti-Tank Rifle, Ithaca 37 Shotgun
- **Hitscan ballistics** with pellet spread, recoil, and bullet travel tracers
- **Headshot detection** with damage multipliers per weapon
- **ADS (Aim Down Sights)** with per-weapon zoom levels and tighter spread
- **Melee Knife** (`F`) — instant close-range kill option
- **Frag Grenades** (`G`) with physics arc, cook timer, and area explosion
- **Weapon Upgrade System** — every 5 waves, choose from 3 randomized weapon enhancements (Stopping Power, Extended Mag, Rapid Fire, Barrel Rifling, Sleight of Hand, Grip Tape, FMJ Rounds)

### 🧟 Enemy AI
- **4 Zombie Types:** Grunt, Runner, Brute, Crawler — each with unique stats, speed, and attack patterns
- **Lunge attacks** on close approach
- **Flanking AI** (Wave 6+) — zombies actively circle and flank the player
- **Pack Rush** (Wave 9+) — surrounding zombies coordinate simultaneous attacks
- **Rage Mode** — zombies below 25% HP enter a frenzied state with boosted speed and attack rate
- **Elite Mutations** — random spawns include Juggernauts (3× HP, tankier) and Sprinters (toxic-green, fast)
- **Phantom Stalker** — rare cloaked enemy visible only when close or taking damage

### 🌊 Wave System
- **Infinite continuous rounds** — no cap, waves scale indefinitely
- Zombie count grows each wave; spawn rate accelerates
- **Horde Events** every 4 waves — double spawn rate, boosted zombie speed, dramatic screen effects
- Wave-clear bonuses and grenade/ammo resupply between rounds
- Between-wave countdown shortens as rounds progress (tension maintained)

### 🗺️ Map & Environment
- Fully 3D bunker with textured brick walls, aged floorboards, and darkened ceiling
- Procedural wall/floor/ceiling textures generated via Canvas API (no external images)
- Sandbag fortifications, ammo crates, wooden debris, structural pillars
- **4 spawn portals** at map corners with animated particle FX
- **3 Environmental Hazard Zones** — burning ground that damages both zombies and players
- **Explosive Barrels** — shoot to trigger massive chain-damage explosions
- Dynamic flickering lanterns and atmospheric point lights
- Exponential fog (`THREE.FogExp2`) for depth and dread

### 🎧 Procedural Audio (Web Audio API)
- **No audio files** — all sounds are synthesized in real time:
  - Gunshots (per-weapon tonal profile)
  - Zombie groans (proximity-based, type-specific bandpass noise)
  - Footsteps (player movement-triggered)
  - Heartbeat (critical health)
  - Reload clicks (multi-stage metallic clank)
  - Grenade pulls, explosions, ambient drone
  - Horde roar event
- Dynamic ambient threat track that intensifies with wave number

### 🧰 Tactical Abilities & Gadgets

| Key | Ability | Cooldown |
|-----|---------|----------|
| `X` | **Stim Shot** — +40 HP, 40% speed boost, 6s | 45s |
| `F` | **Phase Dash** — 8m forward blink teleport | 5s |
| `G` | **Gravity Grenade** — black hole singularity | 15s |
| `Y` | **Grappling Hook** — physics-based pull traversal | — |
| `Z` | **Deployable Barricade** — nano-shield wall | 30s |
| `X` | **Repulsor Blast** — shockwave knockback | 12s |
| `J` | **C4 Explosive** — throw + remote detonate | — |
| `T` | **Teleport Beacon** — throw + warp to disc | — |
| `5` | **Sentry Turret** — auto-targeting gun drone | 30s |
| `6` | **Proximity Mine** — stick to floor, auto-detonates | 15s |
| `U` | **Combat Drone** — hovering laser companion | — |
| `B` | **Bio-Scanner** — X-ray enemy highlight through walls | — |
| `L` | **Tactical Flashlight** — spotlight on/off | — |
| `H` | **Tactical Ping** — world-space marker with distance | — |

### 🎨 HUD & Visual Systems
- **Dynamic Compass** ribbon at top of screen with threat blip markers
- **Threat Meter** (vertical sidebar) — intensity based on nearby enemy count
- **Proximity Threat Vignette** — directional red edge glow showing enemy positions
- **Tactical Visor** — canvas-based brackets drawn around enemies with distance + health bars
- **Kill Chain UI** — combo multiplier with decay timer (Double Kill → Legendary)
- **Cinematic Kill System** — letterbox bars, freeze-frame flash, chromatic aberration on kills
- **Blood Visor** — procedural droplets on camera lens when taking damage
- **Damage Number Popups** — floating numerals above hit targets; special HEADSHOT label
- **Zombie Health Bars** — live HP bars floating above each enemy
- **EKG Monitor** — heartbeat waveform appears at critical health
- **Reload Arc** — circular progress ring around crosshair during reloads
- **Directional Hit Arrows** — show which direction damage came from
- **Wave-Incoming Pulse** — border flash on new wave start
- **Night Cycle HUD** — blood moon tracker, wave number, corner skull decorations, color temperature shifting
- **Film Grain** — animated noise layer that intensifies during combat
- **CRT Overlay** — scanlines, chromatic aberration, vignette for retro-tactical aesthetic
- **Helmet HUD** — curved visor border overlay for immersion
- **Atmospheric Rain** — CSS rain layer + procedural visor water droplets
- **Kill Streak Announcer** — impact text (DOUBLE KILL, RAMPAGE, GODLIKE)
- **Reactive Combat HUD** — glitch + RGB channel split on HUD elements when firing/taking damage
- **Minimap** — top-left radar with player position, enemy dots, and wall geometry
- **Controls Reference Panel** — live key-highlight sidebar (toggle with `TAB`)

### 👾 Special Mechanics
- **Perk Bottle Drops** — 15% chance on kill to drop a collectible perk:
  - *Speed Cola* — ROF +50%
  - *Juggernog* — HP ×2 (200 max)
  - *Double Tap* — Damage ×2
  - *Quick Revive* — Regen ×3
- **Last Stand** — when HP hits 0, enter a 15s downed state; kill an enemy to revive with 50 HP
- **Voltaic Arc (Chain Lightning)** — headshot kills arc electricity to up to 3 nearby enemies
- **Soul Harvester Companion** — orbiting orb collects zombie souls; 10 souls triggers a shockwave kill
- **Nano Swarm Defense** — passive orbiting particle drones that damage close enemies
- **Vampiric Aura** — passive life drain on nearby enemies, heals player
- **Gravity Singularity** — rare 2% drop from kills; black hole that pulls and crushes nearby enemies
- **Power-Up Drops** (3% kill chance): NUKE (kill all), INSTA-KILL (15s), INFINITE AMMO (15s)
- **Tactical Lean** (`Q`/`E`) — left/right lean with camera tilt and position offset
- **Sprint-Slide System** — hold `SHIFT` + crouch while sprinting to slide
- **Dynamic Dismemberment** — heavy hits or kills remove zombie limbs/heads with blood fountains
- **Persistent High Score Board** — top 5 scores saved to `localStorage` across sessions

---

## 🕹️ Controls

### Movement
| Key | Action |
|-----|--------|
| `W A S D` | Move |
| `SHIFT` | Sprint |
| `SPACE` | Jump |
| `CTRL` | Crouch / Slide (while sprinting) |
| `Q` / `E` | Lean Left / Right |

### Combat
| Key | Action |
|-----|--------|
| `LMB` | Fire |
| `RMB` | Aim Down Sights (ADS) |
| `R` | Reload |
| `F` | Knife / Phase Dash |
| `G` | Throw Grenade / Gravity Grenade |
| `V` | Melee Kick |
| `X` | Stim Shot / Repulsor Blast |
| `1–4` | Switch Weapon |

### Tactical
| Key | Action |
|-----|--------|
| `5` | Deploy Sentry Turret |
| `6` | Throw Proximity Mine |
| `J` | Place / Detonate C4 |
| `Y` | Fire / Release Grappling Hook |
| `Z` | Deploy Barricade |
| `T` | Throw / Warp to Teleport Beacon |
| `U` | Summon Combat Drone |
| `B` | Toggle Bio-Scanner |
| `L` | Toggle Flashlight |
| `H` | Ping Location |
| `TAB` | Toggle Controls Panel |

### System
| Key | Action |
|-----|--------|
| `ESC` | Pause / Unpause |

---

## 🚀 Getting Started

1. **Download** `nacht_der_untoten.html`
2. **Open** it in any modern browser (Chrome, Firefox, Edge, Safari)
3. Click **DEPLOY** on the main menu
4. Click the canvas to lock the mouse pointer
5. Survive

> ⚠️ **No server required.** Works as a local file (`file://`). No installs, no build steps.

### Browser Compatibility
| Browser | Status |
|---------|--------|
| Chrome 90+ | ✅ Full support |
| Firefox 88+ | ✅ Full support |
| Edge 90+ | ✅ Full support |
| Safari 15+ | ✅ Full support |
| Mobile | ⚠️ Not designed for touch |

---

## 🏗️ Technical Architecture

### Rendering
- **Three.js r128** via CDN — scene graph, geometries, materials, shadows
- **Dual-scene rendering** — main game world + weapon view-model (separate camera, depth-cleared)
- **Procedural textures** — all wall, floor, ceiling, and prop textures are canvas-generated at runtime
- **PCF Soft Shadow Maps** — dynamic shadows from point lights
- **Reinhard tone mapping** — cinematic exposure control

### Game Systems
- **Entity-Component pattern** — `player` object with `update(dt)`, Zombie class with `update(dt)`
- **Fixed-step physics** — gravity, jump, collision resolution against AABB map objects
- **Hitscan raycasting** — step-marched ray against AABB wall list and zombie bounding boxes
- **Object pooling** — bullet meshes recycled via `BULLET_POOL` array
- **Particle system** — unified `bloodParticles` array with gravity, bounce, and fade

### Audio
- **Web Audio API** — `AudioContext`, `OscillatorNode`, `BiquadFilterNode`, `BufferSourceNode`
- All sounds synthesized procedurally (noise buffers, bandpass filters, LFOs, gain envelopes)
- Lazy-initialized on first user interaction

### Data Persistence
- `localStorage` — high score board (`ironwolf_scores_v1` key, top 5 entries)

### File Size
- Single `.html` file
- ~2,800+ lines of inline JavaScript
- Zero external assets beyond the Three.js CDN script

---

## 🧱 Code Structure

```
nacht_der_untoten.html
│
├── CSS Styles (HUD, menus, overlays, animations)
├── HTML Structure (menu, HUD elements, canvases)
│
└── JavaScript
    ├── Engine Bootstrap        (renderer, scene, camera, resize)
    ├── Procedural Textures     (canvas-generated wall/floor/ceil)
    ├── Materials               (M.wall, M.floor, M.zombie, etc.)
    ├── Map Builder             (walls, sandbags, pillars, props)
    ├── Lighting                (ambient, point lights, flicker system)
    ├── Player Object           (movement, shooting, health, weapons)
    ├── View Model              (weapon mesh + muzzle flash)
    ├── Bullet & Hitscan        (ray march, hit detection)
    ├── Impact / Blood FX       (particle system, blood decals)
    ├── Grenades                (physics, explosion, shrapnel)
    ├── Zombie Class            (AI states, mesh, animation)
    ├── Wave System             (spawn scheduling, scaling, horde events)
    ├── Camera Shake            (trauma-based)
    ├── Input System            (keyboard, mouse, pointer lock)
    ├── HUD Helpers             (health, ammo, streak, killfeed)
    ├── Minimap                 (canvas render, radar)
    ├── Game Loop               (requestAnimationFrame, dt)
    │
    ├── UPGRADES (Additive modules, no base code modification)
    │   ├── Sprint-Slide System
    │   ├── Advanced Tactical HUD (compass, EKG, reload arc, hit arrows)
    │   ├── Procedural Audio Threat System
    │   ├── Perk Bottle Drop System
    │   ├── Threat Meter + Kill Rings
    │   ├── Spawn Portal FX
    │   ├── Tactical Lean System
    │   ├── Cinematic Kill Freeze-Frame
    │   ├── Persistent High Score Board
    │   ├── Weapon Upgrade System
    │   ├── Night Cycle HUD Skin
    │   ├── Zombie Horde Roar Event
    │   ├── Dynamic Crosshair
    │   ├── Wave-Clear Polling Fix
    │   ├── Controls Reference Panel
    │   ├── Kill Chain Multiplier UI
    │   ├── Environmental Hazard Zones
    │   ├── Definitive Zombie Melee Fix
    │   ├── Damage Number Popups + Health Bars
    │   ├── Zombie Aggression Escalation AI
    │   ├── Proximity Threat Pulse HUD
    │   ├── Zombie Rage Mode
    │   ├── Voltaic Arc (Chain Lightning)
    │   ├── Blood Visor
    │   ├── Dynamic Dismemberment
    │   ├── Last Stand (Second Wind)
    │   ├── Reactive Combat HUD
    │   ├── Soul Harvester Companion
    │   ├── Sentry Turret
    │   ├── Tactical Visor (Target Locking)
    │   ├── Gravity Singularity Drop
    │   ├── Adrenaline Injector (Stim)
    │   ├── CRT Overlay
    │   ├── Phantom Stalker AI
    │   ├── Proximity Mines
    │   ├── Helmet HUD Overlay
    │   ├── Elite Mutations (Juggernaut / Sprinter)
    │   ├── Explosive Barrels
    │   ├── Screen Shake System
    │   ├── Tactical Power-Ups (Nuke, Insta-Kill, Inf-Ammo)
    │   ├── Dynamic Reactive Crosshair (Canvas)
    │   ├── Phase Dash (Blink)
    │   ├── Grappling Hook
    │   ├── Atmospheric Rain & Visor
    │   ├── Bio-Scanner (X-Ray)
    │   ├── Gravity Singularity Grenade
    │   ├── Nano-Swarm Defense
    │   ├── Deployable Barricade
    │   ├── Kill Streak Announcer
    │   ├── Vampiric Aura
    │   ├── Melee Kick
    │   ├── Tactical Compass
    │   ├── Tactical Flashlight
    │   ├── Repulsor Blast
    │   ├── Critical Health Vignette
    │   ├── Tactical Ping System
    │   ├── Remote Explosive (C4)
    │   ├── Low Ammo Warning
    │   ├── Dynamic Day/Night Cycle
    │   ├── Combat Drone
    │   ├── Dynamic Hitmarkers
    │   └── Teleport Beacon
    │
    └── Game Flow (startGame, pauseGame, showGameOver, returnMenu)
```

---

## 📊 Enemy Reference

| Type | HP | Speed | Damage | Notes |
|------|----|-------|--------|-------|
| Grunt | 150 | 2.2 | 15 | Standard zombie |
| Runner | 80 | 4.5 | 15 | Fast, fragile |
| Brute | 400 | 2.0 | 35 | Large, tank |
| Crawler | 50 | 1.5 | 5 | Low profile, difficult to hit |

All base HP is multiplied by `waveScaling = 1 + (wave - 1) × 0.12`.

---

## 🔧 Weapon Reference

| Weapon | Damage | Mag | Fire Rate | Type | Notes |
|--------|--------|-----|-----------|------|-------|
| M1919 LMG | 18 | 100 | 80ms | Auto | Drum magazine, bipod |
| STG-44 | 28 | 30 | 110ms | Auto | Balanced all-rounder |
| PTRS-41 | 120 | 5 | 900ms | Semi | 5× zoom, 3.5× headshot |
| Ithaca 37 | 18×8 | 8 | 600ms | Semi | 8 pellets per shot |

---

## 📁 Files

```
FreeZombieFPSGame.html    Main game file (everything)
README.md                 This document
LICENSE                   MIT License
```

---

## 🙏 Credits & Dependencies

- **[Three.js r128](https://threejs.org/)** — 3D rendering engine (CDN, MIT License)
- All other code, art, audio, and design by **®TSCreates + ChatGPT, Claude, Gemini Pro**

---

## 📜 License

This project is licensed under the **MIT License** — see [LICENSE](./LICENSE) for full terms.

---

*"They just keep coming."*

**®TSCreates** — All systems nominal.
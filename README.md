# Charvik Adventures

A single-file HTML5 platformer. 8 chapters, animal wardens, 11 spirit powers, 3 playable explorers — no build step, no assets, no dependencies except Google Fonts.

**Play it:** open `game.html` in any modern browser (desktop or phone). Everything (art, audio, level data) is generated in the file itself.

## Controls

| Action | Keyboard | Touch |
|---|---|---|
| Move | `←` `→` or `A` `D` | D-pad (left) |
| Jump / Spirit Wings | `Space` `W` `↑` (tap again mid-air) | Jump button |
| Fireball | `J` or `X` (hold to auto-fire) | Power button |
| Wind Dash | `K` or `C` | Power button |
| Titan Shield | `L` or `V` | Power button |
| Spirit Slam | `S` or `↓` in mid-air | Slam button |
| Spirit Shop (at torches) | `E` | Shop button |
| Pause | `P` / `Esc` | Pause icon |

## Chapters & wardens

1. **Sunset Cove** — Crab King · *Tide pools* — reward: Wind Dash
2. **Whispering Jungle** — Jungle Tiger · *Ruined clearing* — Spirit Slam
3. **Echo Caverns** — Cave Wolf · *Stalactite den* — Spirit Light
4. **Frostpeak** — Frost Dragon · *Frozen spire* — Frost Dash
5. **Murkfen Swamp** — Murk Elephant · *Sunken temple* — Spirit Siphon
6. **Skyreach Temples** — Storm Roc · *Sky bridge* — Sky Glide
7. **Ember Forge** — Magma Bear · *Magma vault* — Magma Ward
8. **Shadow Rift** — Shadow Charvik · *Void sanctum* — Awakened Form

Each chapter gives one power from a mid-level stone totem and one from its warden. Progress (unlocked chapters, powers, per-chapter ranks) is saved in `localStorage`.

**Test keys** (island map): `U` unlocks all chapters, `I` awakens all powers.

## Run locally

```bash
python -m http.server 8026
# then open http://127.0.0.1:8026/game.html
```

or just double-click `game.html`.

## Files

- `game.html` — the whole game
- `index.html` — redirect, so a static host serves the game at the site root
- `game.html.txt` — early snapshot of the first prototype (kept for reference)

## License

Personal project — do what you like with it.

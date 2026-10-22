# Charvik Adventures

A browser platformer in one HTML file. 8 chapters, 8 animal wardens, 11 spirit powers, 3 playable explorers — no build step, no framework. Level art and audio are generated in code; each warden is a photoreal cut-out taken from its own painting, standing in front of a blurred, darkened version of that lair.

**Play online:** https://devtripathix.github.io/charvik-adventures/

**Play locally:** open `game.html` in any modern browser (desktop or phone), or serve the folder (see below) so the `assets/` images load.

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

Touch controls appear automatically on coarse-pointer devices.

## Chapters & wardens

| # | Chapter | Warden | Lair | Reward |
|---|---|---|---|---|
| 1 | Sunset Cove | Crab King | The Barnacle Trench — storm coast, shipwrecks | Wind Dash |
| 2 | Whispering Jungle | Jungle Tiger | The Canopy Charnel — ironwood basin, god rays | Spirit Slam |
| 3 | Echo Caverns | Cave Wolf | The Den of Howls — limestone amphitheatre | Spirit Light |
| 4 | Frostpeak | Frost Dragon | The Rime-Spire Caldera — blue ice, crevasses | Frost Dash |
| 5 | Murkfen Swamp | Murk Elephant | The Sunken Riverbed — mangrove, mud flats | Spirit Siphon |
| 6 | Viper's Hollow | Poisonous Snake | The Toxic Cenote — venom pools, glowing spores | Sky Glide |
| 7 | Ember Forge | Magma Bear | The Basalt Crucible — lava channels, embers | Magma Ward |
| 8 | Sunken Megalopolis | Godzilla | The Drowned City — flood, neon, radioactive lightning | Awakened Form |

Every warden has its own vulnerability rhythm (shell-breach, flank, alpha, skull, dorsal plates, coils) and its own attack set: charges, pounces, wing gusts, water jets, venom spit, atomic breath, shockwaves.

Each chapter gives one power from a mid-level stone totem and one from its warden. Progress (unlocked chapters, powers, per-chapter ranks) is saved in `localStorage`.

**Test keys** (island map): `U` unlocks all chapters, `I` awakens all powers.

## Warden lairs & sound

- **Photoreal wardens.** Each animal was cut out of its painting (u2net matting), trimmed to solid alpha and shipped as WebP with transparency. In game the cut-out breathes, bobs, leans into a charge, squashes on a pounce and flashes white when hit — with a soft rim glow so dark coats (wolf, godzilla) read against dark lairs.
- **Each animal fights its own way.** Pincer snaps, pounce + claw flurry, pack howl, frost volley, trunk wave, venom arc, quake slam, atomic breath — on separate cooldowns from the charge/pounce state machine, so they no longer just stomp.
- **Lair furniture.** The arena floor is lined with that chapter's wreckage: ship ribs and foam, buttress roots and bones, skull piles and stalagmites, ice shards, mud mounds and reeds, altar stones and venom pools, obsidian and lava cracks, collapsed concrete and rebar.
- Entering an arena raises a title card with the warden's portrait.
- Jungle, swamp and cenote chapters run a procedural ambience bed — cicada drones, canopy bird calls, dripping water.
- The city chapter adds rainfall, distance thunder and lightning flashes.
- Boss music drops a minor-key percussion layer that speeds up as the warden loses health; each fight opens with a roar stinger.

## Run locally

```bash
cd "Charvik adv"
python -m http.server 8026
# then open http://127.0.0.1:8026/game.html
```

On a phone on the same Wi-Fi, bind to all interfaces and open `http://<your-lan-ip>:8027/game.html`:

```bash
python -m http.server 8027 --bind 0.0.0.0
```

## Files

- `game.html` — the whole game (code, level data, canvas art, procedural audio)
- `assets/boss_*.jpg` — the eight warden lair paintings (1280×720), used as blurred arena vistas and card art
- `assets/cut/*.webp` — the eight warden cut-outs used as the in-game sprites (transparent)
- `index.html` — redirect, so a static host serves the game at the site root
- `game.html.txt` — early snapshot of the first prototype (kept for reference)

## License

Personal project — do what you like with it.

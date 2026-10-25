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

- **Two-pose 2D characters.** Each warden has an idle pose and a generated attack pose (image-to-image from its own painting, then matted to transparent WebP). The game cross-fades between them, adds squash/lean/bob and a white hit flash, so a pounce actually changes silhouette instead of sliding one still around.
- **Each animal fights its own way.** Pincer snaps, pounce + claw flurry, pack howl that summons two cubs at half health, frost volleys + dive + landing slam, trunk wave, venom arc, quake slam with falling rocks, atomic breath — on separate cooldowns from the charge/pounce state machine.
- **Per-chapter scenery.** Dense canopy with buttress-rooted trunks, a river band and bones on the bank (jungle); sea stacks and a wrecked hull (cove); columns and a moon shaft (caverns); ice spires over a lava rift (frostpeak); mangrove roots over stagnant water (swamp, cenote); lava falls and obsidian (forge); flooded towers and neon (city). Ground has strata and grit so the cut-away earth no longer reads as a flat slab.
- **Lair furniture.** Arena floors carry that chapter's wreckage — ship ribs, bones, skull piles, ice shards, reeds, altar stones with venom pools, obsidian, rebar.
- Jungle/swamp/cenote ambience: cicada drones, canopy bird calls and a low humid-air bed, ducked but still present during fights.
- The city chapter adds rainfall, distant thunder and lightning flashes.
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
- `assets/cut/*.webp` — warden sprites: `name.webp` idle, `name_atk.webp` attack pose (transparent)
- `index.html` — redirect, so a static host serves the game at the site root
- `game.html.txt` — early snapshot of the first prototype (kept for reference)

## License

Personal project — do what you like with it.

# Sofle Choc Pro BT - ZMK Config

## Project overview

ZMK firmware configuration for a Keebart Sofle Choc Pro BT split keyboard with Dvorak layout.

- **Board:** Keebart Sofle Choc Pro BT (nRF52840)
- **Firmware:** ZMK v0.3
- **Layout:** Dvorak with homerow mods, thumb cluster modifiers, and combos
- **Display:** Nice!view (custom shield: `nice_view_disp`)
- **Build:** GitHub Actions on push, produces .uf2 files

## Key files

- `config/sofle_choc_pro.keymap` — keymap and behaviors
- `config/sofle_choc_pro.conf` — user config (applies to both halves)
- `boards/arm/sofle_choc_pro/` — custom board definition
- `boards/shields/nice_view_disp/` — custom Nice!view display shield
- `build.yaml` — GitHub Actions build matrix

## Rules

- **Always update `README.md`** when changing the keymap, layers, combos, behaviors, or thumb cluster layout. The README contains visual layer maps and feature documentation that must stay in sync with the actual keymap.
- No physical reset button on this board — the NAV layer has `&bootloader` and `&sys_reset` on the top-left keys for flashing.

# Sofle Choc Pro BT - Dvorak Layout

Custom ZMK firmware configuration for the **Sofle Choc Pro BT** split keyboard with a Dvorak layout inspired by the [yal.cc Sofle keymap](https://yal.cc/sofle-keymap/), featuring dedicated modifier keys, thumb cluster arrows, a nav toggle layer, and a numpad with mirrored keys for gaming.

## Layers

| # | Name   | Activation              | Purpose                                |
|---|--------|-------------------------|----------------------------------------|
| 0 | Base   | Default                 | Dvorak with Tab/Ctrl and arrows        |
| 1 | Alt    | Hold ALT (left thumb)   | F-keys left, navigation right          |
| 2 | Nav    | Toggle from ALT layer   | Persistent nav block on right hand     |
| 3 | Num    | Hold NUM (right thumb)  | Numpad right, mirrored Dvorak left     |
| 4 | Adjust | Hold ALT + NUM together | RGB, Bluetooth, power, bootloader      |

---

## Layer 0: Base (Dvorak)

Tab doubles as LCtrl on hold. `=` doubles as RCtrl on hold. Arrow keys on the right thumb cluster. Enter doubles as NUM layer on hold.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│   `   │   1   │   2   │   3   │   4   │   5   │                 │   6   │   7   │   8   │   9   │   0   │ BSPC  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│TAB/CTL│   '   │   ,   │   .   │   P   │   Y   │                 │   F   │   G   │   C   │   R   │   L   │   /   │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│ LSFT  │   A   │   O   │   E   │   U   │   I   │                 │   D   │   H   │   T   │   N   │   S   │ =/CTL │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │   ;   │   Q   │   J   │   K   │   X   │ MUTE  │ │ PLAY  │   B   │   M   │   W   │   V   │   Z   │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │  GUI  │  ALT  │ SPACE │MO ALT │ENT/NUM│ │MO NUM │   -   │   \   │  LEFT │ RIGHT │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

**Encoders:** Left = Scroll Down/Up | Right = Volume Down/Up

---

## Layer 1: Alt (hold ALT)

F-keys on the left, navigation and media on the right. Left home row has explicit modifiers for Shift+Arrow text selection. Toggle NAV layer from left thumb.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│  ESC  │  F1   │  F2   │  F3   │  F4   │  F5   │                 │  F6   │  F7   │  F8   │  F9   │  F10  │ BSPC  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│CAPSWRD│  F11  │  F12  │       │ PSCR  │       │                 │       │ HOME  │  UP   │  END  │  DEL  │ PG UP │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │  GUI  │  SFT  │  CTL  │  ALT  │       │                 │       │ LEFT  │ DOWN  │ RIGHT │       │ PG DN │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │       │       │ │       │       │       │       │ PREV  │ NEXT  │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │ SPACE │  INS  │TG NAV │ >>>>> │ ENTER │ │       │       │       │       │ PAUSE │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

**Encoders:** Both = Volume Down/Up

---

## Layer 2: Nav Toggle (toggle from ALT)

Activated by pressing TG NAV on the ALT layer. Only overwrites the right-side letter keys with a nav block — left side and symbols pass through to base. Press TG NAV on right thumb to deactivate.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│       │       │       │       │       │       │                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │       │                 │ PG UP │ HOME  │  UP   │  END  │       │  DEL  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │       │                 │ PG DN │ LEFT  │ DOWN  │ RIGHT │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │       │       │ │       │       │       │       │       │       │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │       │       │       │       │ │       │       │       │       │TG NAV │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

Blank = transparent (falls through to base layer).

---

## Layer 3: Numpad (hold NUM)

Right side is a full numpad. Left side mirrors the right-hand Dvorak keys for one-handed gaming (right hand on mouse).

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│   [   │   6   │   7   │   8   │   9   │   0   │                 │NUM LK │   /   │   *   │   (   │   )   │ BSPC  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│ BSPC  │   F   │   G   │   C   │   R   │   L   │                 │ SPACE │  KP7  │  KP8  │  KP9  │       │  DEL  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│   =   │   D   │   H   │   T   │   N   │   S   │                 │   +   │  KP4  │  KP5  │  KP6  │   -   │   =   │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│   ]   │   B   │   M   │   W   │   V   │   Z   │       │ │       │       │  KP1  │  KP2  │  KP3  │KP ENT │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │   -   │   \   │   /   │  ESC  │ ENTER │ │ ENTER │  KP0  │       │   ,   │       │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

**Encoders:** Left = Arrow Left/Right | Right = Volume Down/Up

---

## Layer 4: Adjust (hold ALT + NUM)

Activated by holding both ALT and NUM simultaneously. Bluetooth pairing, RGB underglow controls, power management, and flashing.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│ BOOT  │ BT 1  │ BT 2  │ BT 3  │ BT 4  │ BT 5  │                 │       │       │       │       │       │ RESET │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│EP TOG │RGB HU-│RGB HU+│RGB SA-│RGB SA+│RGB EFF│                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │RGB BR-│RGB BR+│       │       │       │                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│BT CLR │       │       │       │       │STUDIO │RGB TOG│ │       │       │       │       │       │       │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │       │       │       │       │ │       │       │       │       │       │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

---

## Features

### Modifier Keys

- **Tab/Ctrl:** Hold Tab for LCtrl, tap for Tab
- **=/Ctrl:** Hold `=` for RCtrl, tap for `=`
- **Enter/NUM:** Hold Enter for NUM layer, tap for Enter
- **ALT layer home row:** Explicit GUI, Shift, Ctrl, Alt for modifier combos (e.g., Shift+Arrow for text selection)

### Thumb Cluster

| Left Thumb         | Right Thumb        |
|--------------------|--------------------|
| GUI                | MO NUM             |
| ALT                | `-`                |
| Space              | `\`                |
| MO ALT (layer)     | Left Arrow         |
| Enter / NUM (hold) | Right Arrow        |

### Nav Toggle

Activated from the ALT layer (hold ALT, press TG NAV on left thumb). Provides a persistent nav block on the right hand so you can navigate without holding a layer key. Press TG NAV on the right thumb to deactivate.

### Numpad Mirror

The NUM layer mirrors right-hand Dvorak keys onto the left side for one-handed gaming — your left hand gets access to F, G, C, R, L, D, H, T, N, S, etc. while your right hand stays on the mouse.

### Caps Word

Activated from the ALT layer (top-left key). Auto-capitalizes all letters until you press space, enter, or a non-alphanumeric key. Keeps `_` and `-` active for typing `SNAKE_CASE_CONSTANTS` and `HYPHENATED-WORDS`.

### Encoders

| Layer  | Left Encoder       | Right Encoder      |
|--------|--------------------|--------------------|
| Base   | Scroll Down/Up     | Volume Down/Up     |
| Alt    | Volume Down/Up     | Volume Down/Up     |
| Nav    | Volume Down/Up     | Volume Down/Up     |
| Num    | Arrow Left/Right   | Volume Down/Up     |
| Adjust | Volume Down/Up     | Volume Down/Up     |

---

## Hardware

- **Board:** Sofle Choc Pro BT (nRF52840)
- **Switches:** Kailh Choc v1
- **Display:** Nice!view (rotated 180)
- **Firmware:** ZMK v0.3
- **Features:** RGB underglow, Bluetooth 5.0, USB-C, encoders, ZMK Studio

## Building

Firmware is built automatically via GitHub Actions on push. Download the `.uf2` files from the Actions artifacts and flash to each half.

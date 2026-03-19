# Sofle Choc Pro BT - Dvorak Layout

Custom ZMK firmware configuration for the **Sofle Choc Pro BT** split keyboard with a Dvorak layout featuring homerow mods, thumb cluster modifiers, combos, and Caps Word.

## Layers

| # | Name     | Activation                | Purpose                          |
|---|----------|---------------------------|----------------------------------|
| 0 | Base     | Default                   | Dvorak + homerow & thumb mods    |
| 1 | Symbols  | Hold SYM (right thumb)    | Programming symbols and brackets |
| 2 | Nav      | Hold NAV (left thumb)     | Arrows, system nav, clipboard    |
| 3 | Function | Hold FUN (right thumb)    | F-key grid + system keys         |
| 4 | Adjust   | Hold NAV + FUN together   | RGB, Bluetooth, power            |

---

## Layer 0: Base (Dvorak)

Homerow mods shown as `tap/hold`. Thumb cluster has Ctrl on both sides, Space/Enter double as Shift when held.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│   `   │   1   │   2   │   3   │   4   │   5   │                 │   6   │   7   │   8   │   9   │   0   │   `   │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│  ESC  │   '   │   ,   │   .   │   P   │   Y   │                 │   F   │   G   │   C   │   R   │   L   │ BSPC  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│  TAB  │ A/GUI │ O/ALT │ E/CTL │ U/SFT │   I   │                 │   D   │ H/SFT │ T/CTL │ N/ALT │ S/GUI │   -   │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │   ;   │   Q   │   J   │   K   │   X   │ MUTE  │ │ PLAY  │   B   │   M   │   W   │   V   │   Z   │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │  ALT  │  CTL  │  NAV  │ BSPC  │SPC/SFT│ │ENT/SFT│  SYM  │  FUN  │  CTL  │  ALT  │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

**Encoders:** Left = Volume Up/Down | Right = Prev/Next Track

---

## Layer 1: Symbols (hold SYM)

Brackets grouped on right hand: `[ ]` top, `{ }` home, `( )` bottom.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│   ~   │   !   │   @   │   #   │   $   │   %   │                 │   ^   │   &   │   *   │   (   │   )   │   ~   │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │   `   │   <   │   >   │   "   │   '   │                 │   &   │   :   │   [   │   ]   │   %   │  DEL  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │   !   │   -   │   +   │   =   │   #   │                 │   |   │   ;   │   {   │   }   │   @   │   \   │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │   ^   │   /   │   *   │   ~   │   $   │       │ │       │   _   │   ?   │   (   │   )   │   !   │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │       │       │       │       │ │       │ >>>>> │       │       │       │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

`>>>>>` = held layer key. Blank = transparent (falls through to base layer).

---

## Layer 2: Navigation (hold NAV)

System navigation with arrows, page controls, and clipboard shortcuts. Left home row has explicit modifiers for Shift+Arrow text selection. Top-left corner has bootloader, studio unlock, and reset keys.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│ BOOT  │STUDIO │       │       │       │       │                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│ RESET │       │       │       │       │       │                 │ HOME  │ PG DN │ PG UP │  END  │       │  DEL  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │  GUI  │  ALT  │  CTL  │  SFT  │       │                 │   <-  │   v   │   ^   │  ->   │       │ BSPC  │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │ UNDO  │  CUT  │ COPY  │ PASTE │       │       │ │       │       │       │       │       │       │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │       │ >>>>> │       │       │ │       │       │       │       │       │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

---

## Layer 3: Function (hold FUN)

F-keys in a 3x3 grid on the left hand. Right home row has explicit modifiers for combos like Shift+F5.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│       │       │       │       │       │       │                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │  F12  │  F7   │  F8   │  F9   │ PSCR  │                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │  F11  │  F4   │  F5   │  F6   │ SLCK  │                 │       │  SFT  │  CTL  │  ALT  │  GUI  │       │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │  F10  │  F1   │  F2   │  F3   │ PAUSE │       │ │       │       │       │       │       │       │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │       │       │       │       │ │       │       │ >>>>> │       │       │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

---

## Layer 4: Adjust (hold NAV + FUN)

Activated by holding both NAV and FUN simultaneously. Bluetooth pairing, RGB underglow controls, and power management.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│BT CLR │ BT 1  │ BT 2  │ BT 3  │ BT 4  │ BT 5  │                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│EP TOG │RGB HU-│RGB HU+│RGB SA-│RGB SA+│RGB EFF│                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │RGB BR-│RGB BR+│       │       │       │                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │STUDIO │RGB TOG│ │       │       │       │       │       │       │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │       │       │       │       │ │       │       │       │       │       │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

---

## Features

### Homerow Mods (GACS)

Hold a home row key to activate a modifier, tap for the letter. Mirrored on both halves.

| Left Hand | Right Hand |
|-----------|------------|
| A = GUI   | S = GUI    |
| O = Alt   | N = Alt    |
| E = Ctrl  | T = Ctrl   |
| U = Shift | H = Shift  |

**Anti-misfire settings:** `tapping-term-ms = 280`, `require-prior-idle-ms = 150` (typing within 150ms always produces letters), `quick-tap-ms = 200`, opposite-hand-only triggering.

### Thumb Cluster

| Left Thumb           | Right Thumb          |
|----------------------|----------------------|
| ALT                  | ENTER / hold = Shift |
| CTRL                 | SYM (layer)          |
| NAV (layer)          | FUN (layer)          |
| Backspace            | CTRL                 |
| SPACE / hold = Shift | ALT                  |

### Combos

Press two adjacent keys simultaneously (within 60ms) on the base layer:

| Keys    | Output    | Position               |
|---------|-----------|------------------------|
| U + I   | Escape    | Left home row          |
| H + T   | Caps Word | Right home row         |
| , + .   | Backspace | Left top row           |
| Q + J   | Tab       | Left bottom row        |
| M + W   | Enter     | Right bottom row       |
| ; + Q   | Paste     | Left bottom row        |
| J + K   | Copy      | Left bottom row        |
| K + X   | Cut       | Left bottom row        |

### Caps Word

Activated via the H+T combo. Auto-capitalizes all letters until you press space, enter, or a non-alphanumeric key. Keeps `_` and `-` active for typing `SNAKE_CASE_CONSTANTS` and `HYPHENATED-WORDS`.

### Encoders

| Layer    | Left Encoder     | Right Encoder     |
|----------|------------------|-------------------|
| All      | Volume Down/Up   | Prev/Next Track   |

---

## Hardware

- **Board:** Sofle Choc Pro BT (nRF52840)
- **Switches:** Kailh Choc v1
- **Display:** Nice!view (rotated 180)
- **Firmware:** ZMK v0.3
- **Features:** RGB underglow, Bluetooth 5.0, USB-C, encoders, ZMK Studio

## Building

Firmware is built automatically via GitHub Actions on push. Download the `.uf2` files from the Actions artifacts and flash to each half.

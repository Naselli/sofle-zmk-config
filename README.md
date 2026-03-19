# Sofle Choc Pro BT - Dvorak Layout

Custom ZMK firmware configuration for the **Sofle Choc Pro BT** split keyboard with a Dvorak layout featuring thumb cluster modifiers, combos, and Caps Word.

## Layers

| # | Name     | Activation                | Purpose                          |
|---|----------|---------------------------|----------------------------------|
| 0 | Base     | Default                   | Dvorak + thumb cluster mods      |
| 1 | Symbols  | Hold SYM (right thumb)    | Programming symbols and brackets |
| 2 | Numbers  | Hold NUM (left thumb)     | Right-hand numpad + F-keys       |
| 3 | Nav      | Hold NAV (left thumb)     | Arrows, system nav, clipboard    |
| 4 | Function | Hold FUN (right thumb)    | F-key grid + system keys         |
| 5 | Adjust   | Hold NAV + FUN together   | RGB, Bluetooth, power            |

---

## Layer 0: Base (Dvorak)

Modifiers are on the thumb cluster. Space and Enter double as Shift when held.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│   `   │   1   │   2   │   3   │   4   │   5   │                 │   6   │   7   │   8   │   9   │   0   │   `   │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│  ESC  │   '   │   ,   │   .   │   P   │   Y   │                 │   F   │   G   │   C   │   R   │   L   │ BSPC  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│  TAB  │   A   │   O   │   E   │   U   │   I   │                 │   D   │   H   │   T   │   N   │   S   │   -   │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │   ;   │   Q   │   J   │   K   │   X   │ MUTE  │ │ PLAY  │   B   │   M   │   W   │   V   │   Z   │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │  GUI  │  ALT  │  NAV  │  NUM  │SPC/SFT│ │ENT/SFT│  SYM  │  FUN  │  ALT  │  CTL  │
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

## Layer 2: Numbers (hold NUM)

Right-hand numpad layout with arithmetic operators.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│  F12  │  F1   │  F2   │  F3   │  F4   │  F5   │                 │  F6   │  F7   │  F8   │  F9   │  F10  │  F11  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │       │                 │   -   │   7   │   8   │   9   │   /   │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │       │                 │   +   │   4   │   5   │   6   │   *   │       │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │       │       │ │       │   .   │   1   │   2   │   3   │   0   │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │       │       │ >>>>> │       │ │       │       │       │       │       │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

---

## Layer 3: Navigation (hold NAV)

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

## Layer 4: Function (hold FUN)

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

## Layer 5: Adjust (hold NAV + FUN)

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

### Thumb Cluster Modifiers

Modifiers live on the thumb keys instead of the home row for a cleaner typing experience.

| Left Thumb           | Right Thumb          |
|----------------------|----------------------|
| GUI                  | ENTER / hold = Shift |
| ALT                  | SYM (layer)          |
| NAV (layer)          | FUN (layer)          |
| NUM (layer)          | RALT                 |
| SPACE / hold = Shift | RCTRL                |

### Combos

Press two adjacent keys simultaneously (within 60ms) on the base layer:

| Keys    | Output    | Position               |
|---------|-----------|------------------------|
| U + I   | Escape    | Left home row          |
| H + T   | Caps Word | Right home row         |
| , + .   | Backspace | Left top row           |
| Q + J   | Tab       | Left bottom row        |
| M + W   | Enter     | Right bottom row       |

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

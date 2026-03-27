# Sofle Choc Pro BT - Dvorak Layout

Custom ZMK firmware configuration for the **Sofle Choc Pro BT** split keyboard with a beginner-friendly Dvorak layout featuring homerow mods and clean layer organization.

## Layers

| # | Name     | Activation              | Purpose                          |
|---|----------|-------------------------|----------------------------------|
| 0 | Base     | Default                 | Dvorak + homerow mods            |
| 1 | Nav      | Hold NAV (left thumb)   | Arrows, Home/End, clipboard      |
| 2 | Symbols  | Hold SYM (right thumb)  | Programming symbols and brackets |
| 3 | Function | Hold FUN (right thumb)  | F-key grid + system keys         |
| 4 | Adjust   | Hold NAV + FUN together | RGB, Bluetooth, power            |
| 5 | Game     | Toggle from Adjust      | Plain QWERTY, no hold-tap        |
| 6 | Numpad   | Hold NUM (left thumb)   | Right-hand numpad                |

---

## Layer 0: Base (Dvorak)

Homerow mods on the home row (hold for modifier, tap for letter). `=` in the Dvorak top-right position. Windows key on bottom-left, Caps Word on bottom-right.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│   `   │   1   │   2   │   3   │   4   │   5   │                 │   6   │   7   │   8   │   9   │   0   │   =   │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│  TAB  │   '   │   ,   │   .   │   P   │   Y   │                 │   F   │   G   │   C   │   R   │   L   │   /   │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│  ESC  │   A   │ O/ALT │ E/CTL │ U/SFT │   I   │                 │   D   │ H/SFT │ T/CTL │ N/ALT │   S   │   -   │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│  GUI  │   ;   │   Q   │   J   │   K   │   X   │ MUTE  │ │ NEXT  │   B   │   M   │   W   │   V   │   Z   │CAPSWRD│
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │CP/PST │  NUM  │  NAV  │  DEL  │ SPACE │ │ ENTER │ BSPC  │  SYM  │  FUN  │  ALT  │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

**Encoders:** Left = Volume Down/Up | Right = Prev/Next Track

---

## Layer 1: Navigation (hold NAV)

Arrow keys and page navigation on the right. Explicit modifiers on the left home row for Shift+Arrow text selection. Clipboard shortcuts on the left bottom row. Top-left has bootloader and reset for flashing.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│ BOOT  │STUDIO │       │       │       │       │                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│ RESET │       │       │       │       │       │                 │ HOME  │ PG DN │ PG UP │  END  │       │  DEL  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │  GUI  │  ALT  │  CTL  │  SFT  │       │                 │  LEFT │ DOWN  │  UP   │ RIGHT │       │ BSPC  │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │ UNDO  │  CUT  │ COPY  │ PASTE │       │       │ │       │  INS  │       │       │       │       │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │       │ >>>>> │       │       │ │       │       │       │       │       │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

---

## Layer 2: Symbols (hold SYM)

Brackets grouped on the right hand: `[ ]` top, `{ }` home, `( )` bottom. Operators and common symbols on the left.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│   ~   │   !   │   @   │   #   │   $   │   %   │                 │   ^   │   &   │   *   │   (   │   )   │  DEL  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │   `   │   <   │   >   │   "   │   '   │                 │   &   │   :   │   [   │   ]   │   %   │   \   │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │   !   │   -   │   +   │   =   │   #   │                 │   |   │   ;   │   {   │   }   │   @   │   _   │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │   ^   │   /   │   *   │   ~   │   $   │       │ │       │   \   │   ?   │   (   │   )   │   !   │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │       │       │       │       │ │       │       │ >>>>> │       │       │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

---

## Layer 3: Function (hold FUN)

F-keys on the top row matching their number positions (F1 above 1, etc.), with F11/F12 on the outer keys. Right home row has explicit modifiers for combos like Shift+F5.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│  F11  │  F1   │  F2   │  F3   │  F4   │  F5   │                 │  F6   │  F7   │  F8   │  F9   │  F10  │  F12  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │ PSCR  │                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │ SLCK  │                 │       │  SFT  │  CTL  │  ALT  │  GUI  │       │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │ PAUSE │       │ │       │       │       │       │       │       │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │       │       │       │       │ │       │       │       │ >>>>> │       │
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

## Layer 5: Game (toggle from Adjust)

Plain QWERTY layout with all hold-tap behaviors removed — no homerow mods, no mod-tap Space/Enter. Every key is a simple keypress for reliable gaming input. Toggle on from the Adjust layer (top-right), toggle off with bottom-right key.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│   `   │   1   │   2   │   3   │   4   │   5   │                 │   6   │   7   │   8   │   9   │   0   │   =   │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│  TAB  │   Q   │   W   │   E   │   R   │   T   │                 │   Y   │   U   │   I   │   O   │   P   │   \   │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│ CAPS  │   A   │   S   │   D   │   F   │   G   │                 │   H   │   J   │   K   │   L   │   ;   │   '   │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│ SHIFT │   Z   │   X   │   C   │   V   │   B   │ MUTE  │ │ NEXT  │   N   │   M   │   ,   │   .   │   /   │ GAME  │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │  ESC  │  ALT  │  CTL  │  ALT  │ SPACE │ │ SHIFT │ BSPC  │ ENTER │  FUN  │  ALT  │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

---

## Layer 6: Numpad (hold NUM)

Right-hand numpad layout with arithmetic operators. Left home row has explicit modifiers for combos like Ctrl+numpad keys.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│       │       │       │       │       │       │                 │NUMLOCK│  KP7  │  KP8  │  KP9  │  KP-  │  KP/  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │       │                 │       │  KP4  │  KP5  │  KP6  │  KP+  │  KP*  │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │  GUI  │  ALT  │  CTL  │  SFT  │       │                 │       │  KP1  │  KP2  │  KP3  │  KP=  │ BSPC  │
├───────┼───────┼───────┼───────┼───────┼───────┼───────╮ ╭───────┼───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │       │       │ │       │       │  KP0  │  KP0  │  KP.  │KP ENT │       │
╰───────┴───────┼───────┼───────┼───────┼───────┼───────┤ ├───────┼───────┼───────┼───────┼───────┼───────┴───────╯
                │       │ >>>>> │       │       │       │ │       │       │       │       │       │
                ╰───────┴───────┴───────┴───────┴───────╯ ╰───────┴───────┴───────┴───────┴───────╯
```

---

## Features

### Homerow Mods (GACS)

Hold a home row key to activate a modifier, tap for the letter. Mirrored on both halves. Uses opposite-hand-only triggering to prevent misfires.

| Left Hand | Right Hand |
|-----------|------------|
| O = Alt   | N = Alt    |
| E = Ctrl  | T = Ctrl   |
| U = Shift | H = Shift  |

**Anti-misfire settings:** `tapping-term-ms = 280`, `require-prior-idle-ms = 150` (typing within 150ms always produces letters), `quick-tap-ms = 175`, opposite-hand-only triggering.

### Thumb Cluster

Delete on left thumb, Backspace on right thumb. Shift is handled entirely by homerow mods.

| Left Thumb (outer→inner) | Right Thumb (inner→outer) |
|--------------------------|---------------------------|
| Copy / Shift=Paste       | Enter                     |
| NUM (layer)              | Bspc                      |
| NAV (layer)              | SYM (layer)               |
| Delete                   | FUN (layer)               |
| Space                    | ALT                       |

### Caps Word

Activated by tapping Space and Enter simultaneously. Auto-capitalizes all letters until you press space, enter, or a non-alphanumeric key. Keeps `_` and `-` active for typing `SNAKE_CASE_CONSTANTS` and `HYPHENATED-WORDS`.

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

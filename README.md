# Sofle Choc Pro BT - Dvorak Layout

Custom ZMK firmware configuration for the **Sofle Choc Pro BT** split keyboard with a Dvorak layout featuring homerow mods, combos, Caps Word, tap-dance, and sticky keys.

## Layers

| # | Name     | Activation                | Purpose                          |
|---|----------|---------------------------|----------------------------------|
| 0 | Base     | Default                   | Dvorak + GACS homerow mods       |
| 1 | Symbols  | Hold SYM (right thumb)    | Programming symbols and brackets |
| 2 | Numbers  | Hold NUM (left thumb)     | Right-hand numpad + F-keys       |
| 3 | Nav      | Hold NAV (left thumb)     | Arrows, system nav, clipboard    |
| 4 | Function | Hold FUN (right thumb)    | F-key grid + system keys         |
| 5 | Adjust   | Hold NAV + FUN together   | RGB, Bluetooth, power            |

---

## Layer 0: Base (Dvorak)

Homerow mods shown as `tap/hold`. Tap for the letter, hold for the modifier.

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
                │ (enc) │STICKY │  NAV  │  NUM  │ SPACE │ │ ENTER │  SYM  │  FUN  │STICKY │ (enc) │
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

System navigation with arrows, page controls, and clipboard shortcuts. Left home row has explicit modifiers for Shift+Arrow text selection.

```
╭───────┬───────┬───────┬───────┬───────┬───────╮                 ╭───────┬───────┬───────┬───────┬───────┬───────╮
│       │       │       │       │       │       │                 │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤                 ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │       │       │       │       │       │                 │ HOME  │ PG DN │ PG UP │  END  │       │  DEL  │
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

### Homerow Mods (GACS)

Hold a home row key to activate a modifier, tap for the letter. Modifiers are arranged **GUI, Alt, Ctrl, Shift** from pinky to index finger, mirrored on both halves.

| Left Hand | Right Hand |
|-----------|------------|
| A = GUI   | S = GUI    |
| O = Alt   | N = Alt    |
| E = Ctrl  | T = Ctrl   |
| U = Shift | H = Shift  |

**Anti-misfire protections:**
- `balanced` flavor -- modifier activates when another key is pressed while holding
- `quick-tap-ms = 175` -- rapid double-taps always register as letters
- Opposite-hand-only triggering -- holding A and pressing O won't activate GUI, only cross-hand presses trigger mods
- `hold-while-undecided` -- responsive modifier feel

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

Activated via the H+T combo or double-tap left STICKY key. Auto-capitalizes all letters until you press space, enter, or a non-alphanumeric key. Keeps `_` and `-` active for typing `SNAKE_CASE_CONSTANTS` and `HYPHENATED-WORDS`.

### Tap-Dance (STICKY keys)

The two STICKY keys in the thumb cluster support single and double tap:

| Key          | Single Tap      | Double Tap      |
|--------------|-----------------|-----------------|
| Left STICKY  | One-shot Shift  | Caps Word       |
| Right STICKY | One-shot Ctrl   | One-shot Alt    |

**One-shot** means: tap the sticky key, then press your next key -- the modifier applies to just that one keypress. You can chain them: tap Sticky-Shift, tap Sticky-Ctrl, press a key = Ctrl+Shift+key.

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

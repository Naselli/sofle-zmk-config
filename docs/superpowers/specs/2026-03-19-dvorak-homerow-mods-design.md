# Sofle Choc Pro BT — Dvorak Layout with Homerow Mods

**Date:** 2026-03-19
**Board:** Sofle Choc Pro BT (nRF52840, 60 keys, 2 encoders, RGB underglow, Nice!view display)
**ZMK Version:** v0.3 (pinned in west.yml)
**Approach:** Community Standard (Approach A) — 5 layers + 1 conditional adjust layer

## Overview

A complete Dvorak keyboard configuration featuring GACS homerow mods, combos, Caps Word, tap-dance, and sticky keys. Designed for mixed programming and writing use. Snappy modifier timings with anti-misfire protections.

## Position Map Reference

From `sofle_choc_pro-layouts.dtsi`:

```
Row 0:  0  1  2  3  4  5        6  7  8  9 10 11
Row 1: 12 13 14 15 16 17       18 19 20 21 22 23
Row 2: 24 25 26 27 28 29       30 31 32 33 34 35
Row 3: 36 37 38 39 40 41 42 43 44 45 46 47 48 49
Row 4:       50 51 52 53 54 55 56 57 58 59
```

- Left hand: positions 0-5, 12-17, 24-29, 36-42, 50-54
- Right hand: positions 6-11, 18-23, 30-35, 43-49, 55-59
- Positions 42/43 are encoder press keys
- Positions 54/55 are the innermost thumb keys (Space/Enter)

## Layers

| # | Name     | Activation              | Purpose                          |
|---|----------|-------------------------|----------------------------------|
| 0 | Base     | Default                 | Dvorak + homerow mods            |
| 1 | Symbols  | Hold SYM (right thumb)  | Programming symbols and brackets |
| 2 | Numbers  | Hold NUM (left thumb)   | Numpad + F-keys                  |
| 3 | Nav      | Hold NAV (left thumb)   | Arrows, system nav, clipboard    |
| 4 | Function | Hold FUN (right thumb)  | F-key grid + system keys         |
| 5 | Adjust   | Conditional: NAV + FUN  | RGB controls, ext power, BT     |

## Layer 0: Base (Dvorak)

```
Pos:  0      1      2      3      4      5                  6      7      8      9     10     11
      `      1      2      3      4      5                  6      7      8      9      0      `

Pos: 12     13     14     15     16     17                 18     19     20     21     22     23
     ESC    '      ,      .      P      Y                  F      G      C      R      L     BSPC

Pos: 24     25     26     27     28     29                 30     31     32     33     34     35
     TAB   A/GUI  O/ALT  E/CTL  U/SFT   I                  D    H/SFT  T/CTL  N/ALT  S/GUI   -

Pos: 36     37     38     39     40     41     42     43   44     45     46     47     48     49
     none    ;      Q      J      K      X    MUTE  PLAY   B      M      W      V      Z    none

Pos:        50     51     52     53     54     55     56   57     58     59
           (enc)  STICKY  NAV    NUM   SPACE  ENTER  SYM   FUN  STICKY (enc)
```

### Key Notes

- Positions 36 and 49 (outermost bottom row) are `&none` — these are hard to reach on a Choc Pro and are intentionally dead.
- Position 50/59 are encoder rotation bindings (not physical keys in the matrix for tapping).
- `&studio_unlock` is placed on Layer 5 (Adjust) for ZMK Studio access.

### Homerow Mod Configuration

- **Order:** GACS (GUI, Alt, Ctrl, Shift) — pinkies to index fingers
- **Left hand:** A/GUI (pos 25), O/ALT (pos 26), E/CTRL (pos 27), U/SHIFT (pos 28)
- **Right hand:** H/SHIFT (pos 31), T/CTRL (pos 32), N/ALT (pos 33), S/GUI (pos 34)
- **I (pos 29) and D (pos 30) are unmodified** — high-frequency Dvorak letters, mods would cause misfires

### Homerow Mod Timings

| Parameter              | Value      | Purpose                                                    |
|------------------------|------------|------------------------------------------------------------|
| tapping-term-ms        | 200        | Snappy activation                                          |
| quick-tap-ms           | 175        | Repeat tap within 175ms always registers as tap            |
| flavor                 | balanced   | Activates when another key is pressed while holding        |
| hold-while-undecided   | yes        | Immediately apply hold behavior while deciding (responsive)|
| hold-trigger-on-release| yes        | Resolve hold-tap when trigger key is released              |

**Note on ZMK v0.3 compatibility:** `require-prior-idle-ms` is NOT available in ZMK v0.3. The `quick-tap-ms` property combined with `hold-trigger-key-positions` (opposite-hand-only triggering) provides sufficient misfire protection. If the project upgrades to ZMK main branch in the future, `require-prior-idle-ms = 125` should be added.

### Hold-Trigger Key Positions

Left-hand homerow mods trigger only when a right-hand key is pressed (and vice versa). This prevents misfires from same-hand rolls.

- **Left mods (HML)** at positions 25-28: trigger on right-hand positions `6 7 8 9 10 11 18 19 20 21 22 23 30 31 32 33 34 35 43 44 45 46 47 48 49 55 56 57 58 59`
- **Right mods (HMR)** at positions 31-34: trigger on left-hand positions `0 1 2 3 4 5 12 13 14 15 16 17 24 25 26 27 28 29 36 37 38 39 40 41 42 50 51 52 53 54`

### Thumb Cluster Detail

| Position (L/R) | Left                          | Right                         |
|----------------|-------------------------------|-------------------------------|
| 50 / 59        | Encoder (vol up/dn)           | Encoder (prev/next)           |
| 51 / 58        | Tap-dance: 1x=sk(SHIFT), 2x=caps_word | Tap-dance: 1x=sk(CTRL), 2x=sk(ALT) |
| 52 / 57        | &mo 3 (NAV)                   | &mo 4 (FUN)                   |
| 53 / 56        | &mo 2 (NUM)                   | &mo 1 (SYM)                   |
| 54 / 55        | &kp SPACE                     | &kp ENTER                     |

All layer keys use `&mo` (momentary layer, no tap output).

## Layer 1: Symbols

Activated by holding SYM (pos 56, right thumb). Symbols on left hand, brackets grouped on right.

```
Pos:  0      1      2      3      4      5                  6      7      8      9     10     11
      ~      !      @      #      $      %                  ^      &      *      (      )      ~

Pos: 12     13     14     15     16     17                 18     19     20     21     22     23
     ___     `      <      >      "      '                  &      :      [      ]      %     DEL

Pos: 24     25     26     27     28     29                 30     31     32     33     34     35
     ___     !      -      +      =      #                  |      ;      {      }      @      \

Pos: 36     37     38     39     40     41     42     43   44     45     46     47     48     49
     ___     ^      /      *      ~      $    ___    ___    _      ?      (      )      !    ___

Pos:        50     51     52     53     54     55     56   57     58     59
           ___    ___    ___    ___    ___    ___    >>>   ___    ___    ___
```

### Design Notes

- Brackets grouped on right hand: `[ ]` top, `{ }` home, `( )` bottom — same fingers, different rows
- Operators on left home: `-` `+` `=` on middle three fingers
- `< >` on left top for generics/HTML
- `|` and `\` on right home for shell/code
- `_` on right bottom for snake_case
- `>>>` indicates the held layer key (SYM)

## Layer 2: Numbers

Activated by holding NUM (pos 53, left thumb). Numpad on right hand.

```
Pos:  0      1      2      3      4      5                  6      7      8      9     10     11
     F12     F1     F2     F3     F4     F5                 F6     F7     F8     F9    F10    F11

Pos: 12     13     14     15     16     17                 18     19     20     21     22     23
     ___    ___    ___    ___    ___    ___                  -      7      8      9      /    ___

Pos: 24     25     26     27     28     29                 30     31     32     33     34     35
     ___    ___    ___    ___    ___    ___                  +      4      5      6      *    ___

Pos: 36     37     38     39     40     41     42     43   44     45     46     47     48     49
     ___    ___    ___    ___    ___    ___    ___    ___    .      1      2      3      0    ___

Pos:        50     51     52     53     54     55     56   57     58     59
           ___    ___    ___    >>>   ___    ___    ___   ___    ___    ___
```

### Design Notes

- Numpad layout on right hand (standard calculator arrangement)
- Arithmetic operators alongside: `/` `*` top right, `-` `+` home left
- F-keys on top row: F1-F5 left, F6-F10 right, F11/F12 on edges
- Left hand free for homerow mod combos (Ctrl+number, etc.)

## Layer 3: Navigation

Activated by holding NAV (pos 52, left thumb). System navigation — Vim handles in-editor movement.

```
Pos:  0      1      2      3      4      5                  6      7      8      9     10     11
     ___    ___    ___    ___    ___    ___                 ___    ___    ___    ___    ___    ___

Pos: 12     13     14     15     16     17                 18     19     20     21     22     23
     ___    ___    ___    ___    ___    ___                HOME  PG_DN  PG_UP   END   ___    DEL

Pos: 24     25     26     27     28     29                 30     31     32     33     34     35
     ___    GUI    ALT    CTL    SFT    ___                LEFT   DOWN    UP   RIGHT  ___   BSPC

Pos: 36     37     38     39     40     41     42     43   44     45     46     47     48     49
     ___    UNDO   CUT   COPY  PASTE   ___    ___    ___  ___    ___    ___    ___    ___    ___

Pos:        50     51     52     53     54     55     56   57     58     59
           ___    ___    >>>   ___    ___    ___    ___   ___    ___    ___
```

### Design Notes

- Arrow keys on right home row (positions 30-33)
- Home/End/PgUp/PgDn on right top row
- Explicit modifiers on left home row (positions 25-28) for Shift+Arrow text selection etc.
- Clipboard shortcuts (OS-level keycodes) on left bottom row (positions 37-40)
- BT controls moved to Adjust layer only (requires NAV+FUN held) — prevents accidental BT switching
- Del (pos 23) and Bspc (pos 35) on right side

## Layer 4: Function

Activated by holding FUN (pos 57, right thumb). F-key grid and system keys.

```
Pos:  0      1      2      3      4      5                  6      7      8      9     10     11
     ___    ___    ___    ___    ___    ___                 ___    ___    ___    ___    ___    ___

Pos: 12     13     14     15     16     17                 18     19     20     21     22     23
     ___    F12    F7     F8     F9    PSCR                ___    ___    ___    ___    ___    ___

Pos: 24     25     26     27     28     29                 30     31     32     33     34     35
     ___    F11    F4     F5     F6    SLCK                ___    SFT    CTL    ALT    GUI    ___

Pos: 36     37     38     39     40     41     42     43   44     45     46     47     48     49
     ___    F10    F1     F2     F3   PAUSE   ___    ___  ___    ___    ___    ___    ___    ___

Pos:        50     51     52     53     54     55     56   57     58     59
           ___    ___    ___    ___    ___    ___    ___   >>>   ___    ___
```

### Design Notes

- F-keys in 3x3 grid on left hand: F1-F3 bottom, F4-F6 middle, F7-F9 top, F10-F12 on pinkies
- Mirrors numpad layout rotated — easy to remember
- Print Screen, Scroll Lock, Pause on index column
- Right home row has explicit modifiers (positions 31-34) for Shift+F5, Ctrl+F5 combos

## Layer 5: Adjust (Conditional)

Activated when both NAV (layer 3) and FUN (layer 4) are held simultaneously. ZMK conditional layer: `if-layers = <3 4>; then-layer = <5>;`

```
Pos:  0      1      2      3      4      5                  6      7      8      9     10     11
     BTCLR  BT1    BT2    BT3    BT4    BT5               none   none   none   none   none   none

Pos: 12     13     14     15     16     17                 18     19     20     21     22     23
     EP_TOG HUD    HUI    SAD    SAI    EFF               none   none   none   none   none   none

Pos: 24     25     26     27     28     29                 30     31     32     33     34     35
     none   BRD    BRI    none   none   none              none   none   none   none   none   none

Pos: 36     37     38     39     40     41     42     43   44     45     46     47     48     49
     none   none   none   none   none STUDIO RGB_TOG none none   none   none   none   none   none

Pos:        50     51     52     53     54     55     56   57     58     59
           none   none   none   none   none   none   none none   none   none
```

### Design Notes

- RGB underglow: hue (HUD/HUI), saturation (SAD/SAI), brightness (BRD/BRI), effects (EFF)
- External power toggle (EP_TOG)
- Bluetooth: clear + 5 device slots — only accessible via two-thumb hold for safety
- RGB toggle on encoder position (42)
- `&studio_unlock` at position 41 for ZMK Studio access
- All other keys are `&none` (dead) — this is intentional for a settings layer

## Behavior Definitions

### Homerow Mods (4 behaviors needed)

Two behaviors for left-hand mods, two for right-hand:

```
HML: left-hand homerow mod (for GUI, ALT, CTRL on A, O, E)
  compatible: zmk,behavior-hold-tap
  flavor: balanced
  tapping-term-ms: 200
  quick-tap-ms: 175
  hold-while-undecided: yes
  hold-trigger-on-release: yes
  hold-trigger-key-positions: <right-hand positions>

HMShiftL: left-hand shift (for U)
  Same as HML but flavor: balanced (shift benefits from hold-while-undecided)

HMR: right-hand homerow mod (for ALT, CTRL, GUI on N, T, S)
  Same as HML but hold-trigger-key-positions: <left-hand positions>

HMShiftR: right-hand shift (for H)
  Same as HMR but flavor: balanced
```

Note: Separate shift behaviors allow future tuning (e.g., different tapping-term for shift vs other mods) without affecting other homerow mods.

### Tap-Dance (2 behaviors)

```
td_sticky_left:
  compatible: zmk,behavior-tap-dance
  tapping-term-ms: 200
  bindings: <&sk LSHFT>, <&caps_word>

td_sticky_right:
  compatible: zmk,behavior-tap-dance
  tapping-term-ms: 200
  bindings: <&sk LCTRL>, <&sk LALT>
```

### Caps Word

```
caps_word:
  compatible: zmk,behavior-caps-word
  continue-list: <UNDERSCORE MINUS BACKSPACE DELETE>
```

Custom `continue-list` to keep `-` and `_` active (default `&caps_word` does NOT continue on `-`). Also continues on BACKSPACE and DELETE for correcting typos without deactivating.

### Sticky Keys

Uses built-in `&sk` behavior. Default ZMK settings:
- Timeout: 1000ms
- Release behavior: releases on next keypress
- Chainable by default (tap multiple sticky keys before the final keypress)

## Combos

All on base layer (layer 0). Numeric positions provided for unambiguous implementation.

| Name      | Positions | Keys  | Output      | Timeout |
|-----------|-----------|-------|-------------|---------|
| Escape    | 28 29     | U + I | &kp ESC     | 60ms    |
| Caps Word | 31 32     | H + T | &caps_word  | 60ms    |
| Backspace | 14 15     | , + . | &kp BSPC    | 60ms    |
| Tab       | 38 39     | Q + J | &kp TAB     | 60ms    |
| Enter     | 45 46     | M + W | &kp ENTER   | 60ms    |

**Combo timeout set to 60ms** (must press both keys within this window). Tight enough to prevent accidental triggers during normal typing, loose enough to be reliably triggered.

**Known risk:** Words containing "ui" (ruin, fruit, suit) require U followed by I. The 60ms combo window and opposite-hand hold-trigger on U's homerow mod should prevent most false triggers. If misfires occur, increase timeout or switch to a different combo pair.

## Encoder Bindings

| Layer    | Left Encoder       | Right Encoder       |
|----------|--------------------|---------------------|
| Base     | Vol Down / Vol Up  | Prev / Next Track   |
| All others | Vol Down / Vol Up | Prev / Next Track  |

Encoders use the same bindings across all layers for consistency.

## Required Includes

```c
#include <behaviors.dtsi>
#include <behaviors/caps_word.dtsi>
#include <dt-bindings/zmk/bt.h>
#include <dt-bindings/zmk/ext_power.h>
#include <dt-bindings/zmk/keys.h>
#include <dt-bindings/zmk/rgb.h>
```

Note: Verify that `behaviors/caps_word.dtsi` is available in ZMK v0.3. If not, define caps_word behavior inline in the keymap.

## Hardware Config

No changes to `sofle_choc_pro.conf`. All existing board defconfig settings remain unchanged:

- ZMK Studio enabled
- RGB underglow (max brightness 20, hue 200, sat 98)
- BLE experimental connection
- Nice!view display rotated 180
- Deep sleep enabled
- Encoders enabled

## Future Improvements

When upgrading from ZMK v0.3 to main branch:
- Add `require-prior-idle-ms = 125` to all homerow mod behaviors for additional misfire protection
- Consider `global-quick-tap-ms` if available in the newer version

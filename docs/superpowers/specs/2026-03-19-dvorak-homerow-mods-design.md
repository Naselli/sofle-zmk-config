# Sofle Choc Pro BT — Dvorak Layout with Homerow Mods

**Date:** 2026-03-19
**Board:** Sofle Choc Pro BT (nRF52840, 60 keys, 2 encoders, RGB underglow, Nice!view display)
**Approach:** Community Standard (Approach A) — 5 layers with dedicated purposes

## Overview

A complete Dvorak keyboard configuration featuring GACS homerow mods, combos, Caps Word, tap-dance, and sticky keys. Designed for mixed programming and writing use. Snappy modifier timings with anti-misfire protections.

## Layers

| # | Name     | Activation              | Purpose                          |
|---|----------|-------------------------|----------------------------------|
| 0 | Base     | Default                 | Dvorak + homerow mods            |
| 1 | Symbols  | Hold SYM (right thumb)  | Programming symbols and brackets |
| 2 | Numbers  | Hold NUM (left thumb)   | Numpad + F-keys                  |
| 3 | Nav      | Hold NAV (left thumb)   | Arrows, system nav, clipboard, BT |
| 4 | Function | Hold FUN (right thumb)  | F-key grid + media               |
| 5 | Adjust   | Conditional: NAV + FUN  | RGB controls, ext power, BT     |

## Layer 0: Base (Dvorak)

```
 `      1      2      3      4      5                  6      7      8      9      0      `
ESC    '      ,      .      P      Y                  F      G      C      R      L     BSPC
TAB   A(GUI) O(ALT) E(CTL) U(SFT)  I                  D    H(SFT) T(CTL) N(ALT) S(GUI)  -
       ;      Q      J      K      X    MUTE  PLAY    B      M      W      V      Z
             ENC    STICKY  NAV   NUM   SPACE  ENTER  SYM    FUN   STICKY  ENC
```

### Homerow Mod Configuration

- **Order:** GACS (GUI, Alt, Ctrl, Shift) — pinkies to index fingers
- **Left hand:** A(GUI), O(ALT), E(CTRL), U(SHIFT)
- **Right hand:** H(SHIFT), T(CTRL), N(ALT), S(GUI)
- **I and D are unmodified** — high-frequency Dvorak letters, mods would cause misfires

### Homerow Mod Timings

| Parameter              | Value | Purpose                                                    |
|------------------------|-------|------------------------------------------------------------|
| tapping-term-ms        | 200   | Snappy activation                                          |
| quick-tap-ms           | 175   | Repeat tap within 175ms always registers as tap            |
| require-prior-idle-ms  | 125   | Mod only activates if paused 125ms before — prevents rolls |
| flavor                 | balanced | Activates when another key is pressed while holding      |

### Hold-Trigger Key Positions

Left-hand homerow mods (A, O, E, U) trigger only when a right-hand key is pressed (and vice versa). This prevents misfires from same-hand rolls.

- **Left mods (HML):** trigger on right-hand positions (6-11, 18-23, 30-35, 43-49, 55-59)
- **Right mods (HMR):** trigger on left-hand positions (0-5, 12-17, 24-29, 36-42, 50-54)

### Thumb Cluster

| Position | Left                     | Right                    |
|----------|--------------------------|--------------------------|
| Outer    | Encoder (vol up/dn)      | Encoder (prev/next)      |
| 1        | Sticky (tap-dance)       | FUN (hold) / -           |
| 2        | NAV (hold) / -           | SYM (hold) / -           |
| 3        | NUM (hold) / -           | Sticky (tap-dance)       |
| Inner    | Space                    | Enter                    |

## Layer 1: Symbols

Activated by holding SYM (right thumb). Symbols on left hand, brackets grouped on right.

```
 ~      !      @      #      $      %                  ^      &      *      (      )      ~
       `      <      >      "      '                  &      :      [      ]      %     DEL
       !      -      +      =      #                  |      ;      {      }      @      \
       ^      /      *      ~      $    ___    ___    _      ?      (      )      !
              ___    ___    ___    ___   ___    ___   >>>    ___    ___    ___
```

### Design Notes

- Brackets grouped on right hand: `[ ]` top, `{ }` home, `( )` bottom — same fingers, different rows
- Operators on left home: `-` `+` `=` on middle three fingers
- `< >` on left top for generics/HTML
- `|` and `\` on right home for shell/code
- `_` on right bottom for snake_case

## Layer 2: Numbers

Activated by holding NUM (left thumb). Numpad on right hand.

```
F12    F1     F2     F3     F4     F5                  F6     F7     F8     F9    F10    F11
       ___    ___    ___    ___    ___                  -      7      8      9      /    ___
       ___    ___    ___    ___    ___                  +      4      5      6      *    ___
       ___    ___    ___    ___    ___  ___    ___      .      1      2      3      0
              ___    ___    ___   >>>   ___    ___    ___    ___    ___    ___
```

### Design Notes

- Numpad layout on right hand (standard calculator arrangement)
- Arithmetic operators alongside: `/` `*` top, `-` `+` home
- F-keys on top row: F1-F5 left, F6-F10 right, F11/F12 on edges
- Left hand free for homerow mod combos (Ctrl+number, etc.)

## Layer 3: Navigation

Activated by holding NAV (left thumb). System navigation — Vim handles in-editor movement.

```
BTCLR  BT1    BT2    BT3    BT4    BT5                ___    ___    ___    ___    ___    ___
       ___    ___    ___    ___    ___                 HOME  PG_DN  PG_UP   END   ___    DEL
       GUI    ALT    CTL    SFT    ___                 LEFT   DOWN    UP   RIGHT  ___   BSPC
       UNDO   CUT   COPY  PASTE   ___  ___    ___     ___    ___    ___    ___    ___
              ___    ___   >>>    ___   ___    ___    ___    ___    ___    ___
```

### Design Notes

- Arrow keys on right home row
- Home/End/PgUp/PgDn on right top row
- Explicit modifiers on left home row for Shift+Arrow text selection etc.
- Clipboard shortcuts (OS-level keycodes) on left bottom row
- Bluetooth controls on top row (clear + 5 device slots)
- Del and Bspc on right side

## Layer 4: Function

Activated by holding FUN (right thumb). F-key grid and system keys.

```
       ___    ___    ___    ___    ___                 ___    ___    ___    ___    ___    ___
       F12    F7     F8     F9    PSCR                 ___    ___    ___    ___    ___    ___
       F11    F4     F5     F6   SLCK                  ___    SFT    CTL    ALT    GUI    ___
       F10    F1     F2     F3   PAUSE ___    ___      ___    ___    ___    ___    ___
              ___    ___    ___   ___   ___    ___    ___    >>>    ___    ___
```

### Design Notes

- F-keys in 3x3 grid on left hand: F1-F3 bottom, F4-F6 middle, F7-F9 top, F10-F12 on pinkies
- Mirrors numpad layout rotated — easy to remember
- Print Screen, Scroll Lock, Pause on index column
- Right home row has explicit modifiers for Shift+F5, Ctrl+F5 combos

## Layer 5: Adjust (Conditional)

Activated when both NAV and FUN are held simultaneously.

```
BTCLR  BT1    BT2    BT3    BT4    BT5                ___    ___    ___    ___    ___    ___
EP_TOG HUD    HUI    SAD    SAI   EFF                  ___    ___    ___    ___    ___    ___
       BRD    BRI    ___    ___    ___                  ___    ___    ___    ___    ___    ___
       ___    ___    ___    ___    ___  RGB_TOG  ___    ___    ___    ___    ___    ___
              ___    ___    ___    ___   ___    ___    ___    ___    ___    ___
```

### Design Notes

- RGB underglow: hue, saturation, brightness, effects
- External power toggle
- Bluetooth device switching
- RGB toggle on left encoder position

## Combos

All on base layer, using adjacent key pairs:

| Name      | Keys  | Output    | Position                    |
|-----------|-------|-----------|-----------------------------|
| Escape    | U + I | ESC       | Left index + middle         |
| Caps Word | H + T | Caps Word | Right index + middle        |
| Backspace | , + . | BSPC      | Left top row adjacent       |
| Tab       | Q + J | TAB       | Left bottom row adjacent    |
| Enter     | M + W | ENTER     | Right bottom row adjacent   |

**Combo timeout:** 50ms (must press both keys within this window)

## Caps Word

- Activated via H + T combo
- Auto-capitalizes all letters
- Deactivates on: space, enter, or any non-alphanumeric key
- Keeps `_` and `-` active (for SNAKE_CASE_CONSTANTS)
- No manual toggle-off needed

## Tap-Dance

On the two STICKY keys in the thumb cluster:

### Left Sticky Key

| Taps | Output          |
|------|-----------------|
| 1    | One-shot Shift  |
| 2    | Caps Word       |

### Right Sticky Key

| Taps | Output          |
|------|-----------------|
| 1    | One-shot Ctrl   |
| 2    | One-shot Alt    |

**Tap-dance timeout:** 200ms between taps

## Sticky Keys (One-Shot) Behavior

- Timeout: 1000ms (if no follow-up key pressed, modifier expires)
- Hold behavior: acts as regular modifier when held instead of tapped
- Chainable: tap Sticky-Shift, tap Sticky-Ctrl, press key = Ctrl+Shift+key

## Encoder Bindings

| Layer    | Left Encoder     | Right Encoder     |
|----------|------------------|-------------------|
| Base     | Vol Down / Up    | Prev / Next Track |
| Symbols  | Vol Down / Up    | Prev / Next Track |
| Numbers  | Vol Down / Up    | Prev / Next Track |
| Nav      | Vol Down / Up    | Prev / Next Track |
| Function | Vol Down / Up    | Prev / Next Track |

## Hardware Config

No changes to `sofle_choc_pro.conf` beyond enabling mouse emulation removal (already commented out). All existing board defconfig settings remain unchanged:

- ZMK Studio enabled
- RGB underglow (max brightness 20, hue 200, sat 98)
- BLE experimental connection
- Nice!view display rotated 180
- Deep sleep enabled
- Encoders enabled

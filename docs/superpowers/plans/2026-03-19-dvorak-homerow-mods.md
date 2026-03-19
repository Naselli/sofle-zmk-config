# Dvorak Homerow Mods Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Rewrite the Sofle Choc Pro BT keymap with GACS homerow mods, 5 layers + conditional adjust, combos, Caps Word, tap-dance, and sticky keys.

**Architecture:** Single-file keymap (`config/sofle_choc_pro.keymap`) containing all behaviors, combos, conditional layers, and 6 layer definitions. No config file changes needed.

**Tech Stack:** ZMK v0.3, devicetree syntax, nRF52840

**Spec:** `docs/superpowers/specs/2026-03-19-dvorak-homerow-mods-design.md`

---

### Task 1: Rewrite includes and layer defines

**Files:**
- Modify: `config/sofle_choc_pro.keymap:1-16`

- [ ] **Step 1: Replace includes and defines**

Replace the entire top section (lines 1-16) with:

```dts
/*
 * Copyright (c) 2020 The ZMK Contributors
 *
 * SPDX-License-Identifier: MIT
 */

#include <behaviors.dtsi>
#include <behaviors/caps_word.dtsi>
#include <dt-bindings/zmk/bt.h>
#include <dt-bindings/zmk/ext_power.h>
#include <dt-bindings/zmk/keys.h>
#include <dt-bindings/zmk/rgb.h>

#define BASE 0
#define SYM 1
#define NUM 2
#define NAV 3
#define FUN 4
#define ADJUST 5
```

- [ ] **Step 2: Commit**

```bash
git add config/sofle_choc_pro.keymap
git commit -m "update layer defines for new 6-layer layout"
```

---

### Task 2: Rewrite behaviors block

**Files:**
- Modify: `config/sofle_choc_pro.keymap:18-80` (the `/ {` block opening and behaviors)

- [ ] **Step 1: Replace the entire behaviors block**

Replace from `/ {` through the closing `};` of behaviors (lines 18-80) with:

```dts
/ {
    behaviors {
        HML: HML {
            compatible = "zmk,behavior-hold-tap";
            label = "HML";
            bindings = <&kp>, <&kp>;
            #binding-cells = <2>;
            tapping-term-ms = <200>;
            quick-tap-ms = <175>;
            flavor = "balanced";
            hold-while-undecided;
            hold-trigger-on-release;
            hold-trigger-key-positions = <6 7 8 9 10 11 18 19 20 21 22 23 30 31 32 33 34 35 43 44 45 46 47 48 49 55 56 57 58 59>;
        };

        HMR: HMR {
            compatible = "zmk,behavior-hold-tap";
            label = "HMR";
            bindings = <&kp>, <&kp>;
            #binding-cells = <2>;
            tapping-term-ms = <200>;
            quick-tap-ms = <175>;
            flavor = "balanced";
            hold-while-undecided;
            hold-trigger-on-release;
            hold-trigger-key-positions = <0 1 2 3 4 5 12 13 14 15 16 17 24 25 26 27 28 29 36 37 38 39 40 41 42 50 51 52 53 54>;
        };

        HMShiftL: HMShiftL {
            compatible = "zmk,behavior-hold-tap";
            label = "HMSHIFTL";
            bindings = <&kp>, <&kp>;
            #binding-cells = <2>;
            tapping-term-ms = <200>;
            quick-tap-ms = <175>;
            flavor = "balanced";
            hold-while-undecided;
            hold-trigger-on-release;
            hold-trigger-key-positions = <6 7 8 9 10 11 18 19 20 21 22 23 30 31 32 33 34 35 43 44 45 46 47 48 49 55 56 57 58 59>;
        };

        HMShiftR: HMShiftR {
            compatible = "zmk,behavior-hold-tap";
            label = "HMSHIFTR";
            bindings = <&kp>, <&kp>;
            #binding-cells = <2>;
            tapping-term-ms = <200>;
            quick-tap-ms = <175>;
            flavor = "balanced";
            hold-while-undecided;
            hold-trigger-on-release;
            hold-trigger-key-positions = <0 1 2 3 4 5 12 13 14 15 16 17 24 25 26 27 28 29 36 37 38 39 40 41 42 50 51 52 53 54>;
        };

        td_sticky_left: td_sticky_left {
            compatible = "zmk,behavior-tap-dance";
            label = "TD_STICKY_LEFT";
            #binding-cells = <0>;
            tapping-term-ms = <200>;
            bindings = <&sk LSHFT>, <&caps_word>;
        };

        td_sticky_right: td_sticky_right {
            compatible = "zmk,behavior-tap-dance";
            label = "TD_STICKY_RIGHT";
            #binding-cells = <0>;
            tapping-term-ms = <200>;
            bindings = <&sk LCTRL>, <&sk LALT>;
        };
    };

    /* Custom caps_word with continue-list for SNAKE_CASE and hyphenated-words */
    &caps_word {
        continue-list = <UNDERSCORE MINUS BACKSPACE DELETE>;
    };
```

Note: Do NOT close the `/ {` block yet — combos and keymap follow.

Note on `caps_word.dtsi`: If this include does not exist in ZMK v0.3, remove the `#include <behaviors/caps_word.dtsi>` line and instead define the behavior inline inside the `behaviors {}` block:
```dts
        caps_word: caps_word {
            compatible = "zmk,behavior-caps-word";
            label = "CAPS_WORD";
            #binding-cells = <0>;
            continue-list = <UNDERSCORE MINUS BACKSPACE DELETE>;
        };
```
And remove the `&caps_word { ... };` override block outside behaviors.

- [ ] **Step 2: Commit**

```bash
git add config/sofle_choc_pro.keymap
git commit -m "rewrite behaviors: GACS homerow mods, tap-dance, balanced flavor"
```

---

### Task 3: Add combos and conditional layers

**Files:**
- Modify: `config/sofle_choc_pro.keymap` (insert after behaviors block, before keymap block)

- [ ] **Step 1: Add combos and conditional layer blocks**

Insert after the behaviors closing `};` and before the `keymap {` block:

```dts
    combos {
        compatible = "zmk,combos";

        combo_esc {
            timeout-ms = <60>;
            key-positions = <28 29>;
            bindings = <&kp ESC>;
            layers = <BASE>;
        };

        combo_caps_word {
            timeout-ms = <60>;
            key-positions = <31 32>;
            bindings = <&caps_word>;
            layers = <BASE>;
        };

        combo_bspc {
            timeout-ms = <60>;
            key-positions = <14 15>;
            bindings = <&kp BSPC>;
            layers = <BASE>;
        };

        combo_tab {
            timeout-ms = <60>;
            key-positions = <38 39>;
            bindings = <&kp TAB>;
            layers = <BASE>;
        };

        combo_enter {
            timeout-ms = <60>;
            key-positions = <45 46>;
            bindings = <&kp ENTER>;
            layers = <BASE>;
        };
    };

    conditional_layers {
        compatible = "zmk,conditional-layers";

        adjust_layer {
            if-layers = <NAV FUN>;
            then-layer = <ADJUST>;
        };
    };
```

- [ ] **Step 2: Commit**

```bash
git add config/sofle_choc_pro.keymap
git commit -m "add combos (esc, caps word, bspc, tab, enter) and conditional adjust layer"
```

---

### Task 4: Write the Base layer

**Files:**
- Modify: `config/sofle_choc_pro.keymap` (replace keymap block)

- [ ] **Step 1: Replace the keymap block with all 6 layers**

Start by writing the Base layer. Replace the entire `keymap { ... }` block (from `keymap {` to the final `};` before the closing `};` of the root `/` block) with:

```dts
    keymap {
        compatible = "zmk,keymap";

        base_layer {
            display-name = "dvorak";
            bindings = <
&kp GRAVE      &kp N1          &kp N2         &kp N3          &kp N4           &kp N5                              &kp N6       &kp N7          &kp N8         &kp N9         &kp N0           &kp GRAVE
&kp ESC        &kp SQT         &kp COMMA      &kp PERIOD      &kp P            &kp Y                               &kp F        &kp G           &kp C          &kp R          &kp L            &kp BSPC
&kp TAB        &HML LGUI A     &HML LALT O    &HML LCTRL E    &HMShiftL LSHFT U &kp I                              &kp D        &HMShiftR RSHFT H &HMR RCTRL T &HMR RALT N    &HMR RGUI S      &kp MINUS
&none          &kp SEMICOLON   &kp Q          &kp J           &kp K            &kp X  &kp C_MUTE    &kp C_PLAY     &kp B        &kp M           &kp W          &kp V          &kp Z            &none
                               &none          &td_sticky_left  &mo NAV          &mo NUM &kp SPACE    &kp ENTER      &mo SYM      &mo FUN         &td_sticky_right &none
            >;
            sensor-bindings = <&inc_dec_kp C_VOL_DN C_VOL_UP &inc_dec_kp C_PREV C_NEXT>;
        };
```

Note: Positions 36/49 are `&none`. Position 50/59 are `&none` (encoder rotation is handled by sensor-bindings, not key bindings).

- [ ] **Step 2: Commit**

```bash
git add config/sofle_choc_pro.keymap
git commit -m "add base dvorak layer with GACS homerow mods and tap-dance thumbs"
```

---

### Task 5: Write the Symbols layer

**Files:**
- Modify: `config/sofle_choc_pro.keymap` (add after base_layer)

- [ ] **Step 1: Add symbols layer**

Add immediately after the base layer's closing `};`:

```dts
        sym_layer {
            display-name = "symbols";
            bindings = <
&kp TILDE      &kp EXCL        &kp AT         &kp HASH        &kp DLLR         &kp PRCNT                           &kp CARET    &kp AMPS        &kp ASTRK      &kp LPAR       &kp RPAR         &kp TILDE
&trans         &kp GRAVE       &kp LT         &kp GT          &kp DQT          &kp SQT                             &kp AMPS     &kp COLON       &kp LBKT       &kp RBKT       &kp PRCNT        &kp DEL
&trans         &kp EXCL        &kp MINUS      &kp PLUS        &kp EQUAL        &kp HASH                            &kp PIPE     &kp SEMI        &kp LBRC       &kp RBRC       &kp AT           &kp BSLH
&trans         &kp CARET       &kp FSLH       &kp ASTRK       &kp TILDE        &kp DLLR  &trans        &trans      &kp UNDER    &kp QMARK       &kp LPAR       &kp RPAR       &kp EXCL         &trans
                               &trans         &trans          &trans           &trans    &trans        &trans      &trans       &trans          &trans         &trans
            >;
            sensor-bindings = <&inc_dec_kp C_VOL_DN C_VOL_UP &inc_dec_kp C_PREV C_NEXT>;
        };
```

- [ ] **Step 2: Commit**

```bash
git add config/sofle_choc_pro.keymap
git commit -m "add symbols layer with grouped brackets and programming operators"
```

---

### Task 6: Write the Numbers layer

**Files:**
- Modify: `config/sofle_choc_pro.keymap` (add after sym_layer)

- [ ] **Step 1: Add numbers layer**

```dts
        num_layer {
            display-name = "numbers";
            bindings = <
&kp F12        &kp F1          &kp F2         &kp F3          &kp F4           &kp F5                              &kp F6       &kp F7          &kp F8         &kp F9         &kp F10          &kp F11
&trans         &trans          &trans         &trans          &trans           &trans                              &kp MINUS    &kp N7          &kp N8         &kp N9         &kp FSLH         &trans
&trans         &trans          &trans         &trans          &trans           &trans                              &kp PLUS     &kp N4          &kp N5         &kp N6         &kp ASTRK        &trans
&trans         &trans          &trans         &trans          &trans           &trans    &trans        &trans      &kp DOT      &kp N1          &kp N2         &kp N3         &kp N0           &trans
                               &trans         &trans          &trans           &trans    &trans        &trans      &trans       &trans          &trans         &trans
            >;
            sensor-bindings = <&inc_dec_kp C_VOL_DN C_VOL_UP &inc_dec_kp C_PREV C_NEXT>;
        };
```

- [ ] **Step 2: Commit**

```bash
git add config/sofle_choc_pro.keymap
git commit -m "add numbers layer with right-hand numpad and F-keys"
```

---

### Task 7: Write the Navigation layer

**Files:**
- Modify: `config/sofle_choc_pro.keymap` (add after num_layer)

- [ ] **Step 1: Add navigation layer**

```dts
        nav_layer {
            display-name = "nav";
            bindings = <
&trans         &trans          &trans         &trans          &trans           &trans                              &trans       &trans          &trans         &trans         &trans           &trans
&trans         &trans          &trans         &trans          &trans           &trans                              &kp HOME     &kp PG_DN       &kp PG_UP      &kp END        &trans           &kp DEL
&trans         &kp LGUI        &kp LALT       &kp LCTRL       &kp LSHFT        &trans                              &kp LEFT     &kp DOWN        &kp UP         &kp RIGHT      &trans           &kp BSPC
&trans         &kp K_UNDO      &kp K_CUT      &kp K_COPY      &kp K_PASTE      &trans    &trans        &trans      &trans       &trans          &trans         &trans         &trans           &trans
                               &trans         &trans          &trans           &trans    &trans        &trans      &trans       &trans          &trans         &trans
            >;
            sensor-bindings = <&inc_dec_kp C_VOL_DN C_VOL_UP &inc_dec_kp C_PREV C_NEXT>;
        };
```

- [ ] **Step 2: Commit**

```bash
git add config/sofle_choc_pro.keymap
git commit -m "add navigation layer with arrows, clipboard, and system nav"
```

---

### Task 8: Write the Function layer

**Files:**
- Modify: `config/sofle_choc_pro.keymap` (add after nav_layer)

- [ ] **Step 1: Add function layer**

```dts
        fun_layer {
            display-name = "function";
            bindings = <
&trans         &trans          &trans         &trans          &trans           &trans                              &trans       &trans          &trans         &trans         &trans           &trans
&trans         &kp F12         &kp F7         &kp F8          &kp F9           &kp PSCRN                           &trans       &trans          &trans         &trans         &trans           &trans
&trans         &kp F11         &kp F4         &kp F5          &kp F6           &kp SLCK                            &trans       &kp RSHFT       &kp RCTRL      &kp RALT       &kp RGUI         &trans
&trans         &kp F10         &kp F1         &kp F2          &kp F3           &kp PAUSE_BREAK &trans    &trans    &trans       &trans          &trans         &trans         &trans           &trans
                               &trans         &trans          &trans           &trans    &trans        &trans      &trans       &trans          &trans         &trans
            >;
            sensor-bindings = <&inc_dec_kp C_VOL_DN C_VOL_UP &inc_dec_kp C_PREV C_NEXT>;
        };
```

- [ ] **Step 2: Commit**

```bash
git add config/sofle_choc_pro.keymap
git commit -m "add function layer with F-key grid and explicit right-hand modifiers"
```

---

### Task 9: Write the Adjust layer and close the file

**Files:**
- Modify: `config/sofle_choc_pro.keymap` (add after fun_layer, close all blocks)

- [ ] **Step 1: Add adjust layer and close all blocks**

```dts
        adjust_layer {
            display-name = "adjust";
            bindings = <
&bt BT_CLR         &bt BT_SEL 0     &bt BT_SEL 1     &bt BT_SEL 2     &bt BT_SEL 3     &bt BT_SEL 4                             &none  &none  &none  &none  &none  &none
&ext_power EP_TOG  &rgb_ug RGB_HUD  &rgb_ug RGB_HUI  &rgb_ug RGB_SAD  &rgb_ug RGB_SAI  &rgb_ug RGB_EFF  &none                          &none  &none  &none  &none  &none
&none              &rgb_ug RGB_BRD  &rgb_ug RGB_BRI  &none            &none            &none            &none                          &none  &none  &none  &none  &none
&none              &none            &none            &none            &none            &studio_unlock   &rgb_ug RGB_TOG  &none  &none  &none  &none  &none  &none  &none
                                    &none            &none            &none            &none            &none            &none  &none  &none  &none  &none
            >;
        };
    };
};
```

- [ ] **Step 2: Verify the file is syntactically complete**

Run: Check that all `{` have matching `}` and the file ends with `};` closing the root `/ {` block. The structure should be:

```
/ {
    behaviors { ... };
    combos { ... };
    conditional_layers { ... };
    keymap {
        base_layer { ... };
        sym_layer { ... };
        num_layer { ... };
        nav_layer { ... };
        fun_layer { ... };
        adjust_layer { ... };
    };
};
```

- [ ] **Step 3: Commit**

```bash
git add config/sofle_choc_pro.keymap
git commit -m "add adjust layer with RGB, BT, studio unlock — keymap complete"
```

---

### Task 10: Final verification

**Files:**
- Read: `config/sofle_choc_pro.keymap` (full file)

- [ ] **Step 1: Read the entire keymap and verify**

Read `config/sofle_choc_pro.keymap` and verify:
- 6 layers defined (base, sym, num, nav, fun, adjust)
- All layers have exactly 60 bindings (12+12+12+14+10 = 60 per layer, matching the position map)
- Homerow mods on positions 25-28 (left) and 31-34 (right) in base layer
- Combos reference correct positions (28+29, 31+32, 14+15, 38+39, 45+46)
- Conditional layer activates on layers 3+4 → layer 5
- `&studio_unlock` present on adjust layer
- All `&trans` in non-base layers fall through correctly
- Encoder sensor-bindings present on all layers that need them

- [ ] **Step 2: Count bindings per layer**

For each layer, count the number of binding entries. The Sofle Choc Pro has 60 keys. Each layer must have exactly 60 bindings. Row counts: 12 + 12 + 12 + 14 + 10 = 60.

- [ ] **Step 3: Final commit if any fixes were needed**

```bash
git add config/sofle_choc_pro.keymap
git commit -m "fix: correct any issues found during verification"
```

Only commit if changes were made.

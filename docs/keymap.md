# Toucan keymap

The layout combines `../zmk-config/config/keyball44.keymap` with the newer
`corne-v4-layout.vil` export. The shield keymap is the source of truth;
`config/toucan.keymap` includes it so both build paths use the same layout.

## Physical mapping

The Toucan has three rows of six keys per hand and three thumbs per hand.
The Corne export's seventh-column center switches are extra keys, not part
of those six-key rows. Its right-hand matrix rows are reversed when mapped
to the Toucan's left-to-right binding order.

Thumbs, from left to right across the keyboard:

| Position | Tap | Hold |
| --- | --- | --- |
| Left outer | Command | Command |
| Left middle | AERO + Command | AERO + Command |
| Left inner | Space | NUM |
| Right inner | Backspace | MOVE |
| Right middle | Right Command | Right Command |
| Right outer | Right Option | Right Option |

The left-middle thumb reproduces the Vial export's `0x5068` binding:
`LM(3, MOD_LGUI)`. Command and AERO are active only while it is held.

## Layers

| Index | Name | Access |
| --- | --- | --- |
| 0 | QWERTY | Default |
| 1 | NUM | Hold Space |
| 2 | SYM | Hold F or J |
| 3 | AERO | Hold the left-middle thumb |
| 4 | MOUSE | Touch trackpad; NUM + hold Backspace; AERO + hold Space |
| 5 | MOVE | Hold Backspace |
| 6 | ACC | Hold S or L |
| 7 | ACCS | Hold A+S or L+semicolon together |
| 8 | EXTRA | Hold Space+Backspace together (within 50 ms) |
| 9 | SYS | NUM + hold Right Option; EXTRA + hold Right Option |

Mod-taps and layer-taps retain Keyball's balanced 200 ms tapping term and
150 ms quick-tap setting. Escape doubles as Control, A and semicolon as
Shift, D and K as Option, and both bottom pinky keys as Enter/Shift.

NUM, SYM, AERO, and MOVE use the newer Corne mappings. S and L retain
Keyball's accent-layer holds. SYM also provides the Corne's direct accents:
Q = à, W = è, E = é, R = ê, and C = ç. Both dedicated accent layers retain
all nine Keyball accents, including their uppercase variants. Accent
macros assume a macOS keyboard input source supporting Option dead keys.

SYM keeps the Control+A tmux prefix macros on A/S/D/F/G, T (Space), and Z.
MOVE places F1–F10 on the top row, F11/F12 on D/F, arrows on H/J/K/L, and
Home/Page Down/Page Up/End on N/M/comma/dot.

## Extra Corne center keys

Hold the two inner thumbs together, then press the indicated key. These
bindings preserve the extra center switches without shifting the ordinary
T/Y or G/H columns.

| EXTRA key | Original center switch | Action |
| --- | --- | --- |
| T | Left top center | Control+grave |
| G | Left home center | Control+G |
| Y | Right top center | Disabled, as in the export |
| H | Right home center | Control+Option+Command+Space |
| R | MOVE left top center | Volume up |
| F | MOVE left home center | Volume down |
| J | MOVE right home center | Mute |

The media keys sit one column over from T/G/H, keeping the Corne's
top/home-row arrangement. The thumbs have no media bindings.
Right Option in EXTRA momentarily opens SYS.

## Trackpad and mouse

MOUSE remains layer 4, matching the Toucan trackpad's touch processor.
It combines the Corne's E/D/F middle/right/left clicks and H/J/K/L cursor
movement with its N/M/comma/dot wheel directions (left/up/down/right).
The Toucan's six thumb clicks remain middle/left/right, left/right/middle.
Other keys fall through to the active typing layers.

The existing trackpad gestures remain configured in `toucan.dtsi`,
including motion-to-scroll while NUM or SYM is held. Trackball-specific
SCROLL/SNIPE layers from Keyball are replaced by the Toucan trackpad and
the keyboard mouse controls.

## System controls

SYS provides Bluetooth profiles 0–4 on Q/W/E/R/T, clear-current-profile on
Backspace, next/previous profile on J/K, Studio unlock on Z, and bootloader
entry on either bottom pinky key.

After flashing, an existing ZMK Studio saved keymap may override firmware
defaults. Reset the saved keymap in Studio to load this layout if needed.

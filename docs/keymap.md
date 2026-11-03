# Toucan keymap

`boards/shields/toucan/toucan.keymap` defines the Toucan layout.
`config/toucan.keymap` is a relative symlink to that file.
The build matrix points `ZMK_CONFIG` at the checkout's `config/` directory,
where the symlink resolves to the shield keymap. Firmware builds use the
upstream reusable workflow.

## Physical mapping

The Toucan has three rows of six keys per hand and three thumbs per hand.

Thumbs, from left to right across the keyboard:

| Position | Tap | Hold |
| --- | --- | --- |
| Left outer | Command | Command |
| Left middle | AERO + Command | AERO + Command |
| Left inner | Space | NUM |
| Right inner | Backspace | MOVE |
| Right middle | Right Command | Right Command |
| Right outer | Right Option | Right Option |

The left-middle thumb activates Command and AERO only while it is held.

## Layers

| Index | Name | Access |
| --- | --- | --- |
| 0 | BASE | Default |
| 1 | NUM | Hold Space |
| 2 | SYM | Hold F or J |
| 3 | AERO | Hold the left-middle thumb |
| 4 | MOUSE | Touch trackpad; NUM + hold Backspace; AERO + hold Space |
| 5 | MOVE | Hold Backspace |
| 6 | ACC | Hold S or L |
| 7 | ACCS | Hold A+S or L+semicolon together |
| 8 | EXTRA | Hold Space+Backspace together (within 50 ms) |
| 9 | SYS | NUM + hold Right Option; EXTRA + hold Right Option |

Mod-taps and layer-taps use a balanced 200 ms tapping term and
150 ms quick-tap setting. Escape doubles as Control, A and semicolon as
Shift, D and K as Option, and both bottom pinky keys as Enter/Shift.

Hold S or L to access ACC. SYM also provides direct accents:
Q = à, W = è, E = é, R = ê, and C = ç. The dedicated accent layers provide
é, è, à, ù, ê, â, ô, î, and ç, including their uppercase variants. Accent
macros assume a macOS keyboard input source supporting Option dead keys.

SYM keeps the Control+A tmux prefix macros on A/S/D/F/G, T (Space), and Z.
MOVE places F1–F10 on the top row, F11/F12 on D/F, arrows on H/J/K/L, and
Home/Page Down/Page Up/End on N/M/comma/dot.

## Extra shortcuts and media controls

Hold the two inner thumbs together, then press the indicated key.

| EXTRA key | Action |
| --- | --- |
| T | Control+grave |
| G | Control+G |
| Y | Disabled |
| H | Control+Option+Command+Space |
| R | Volume up |
| F | Volume down |
| J | Mute |

Volume up/down are vertically aligned on R/F, with mute on J.
The thumbs have no media bindings.
Right Option in EXTRA momentarily opens SYS.

## Trackpad and mouse

MOUSE is layer 4, matching the Toucan trackpad's touch processor.
E/D/F provide middle/right/left clicks, H/J/K/L move the cursor, and
N/M/comma/dot scroll left/up/down/right.
The six thumb clicks are middle/left/right, left/right/middle.
Other keys fall through to the active typing layers.

Trackpad gestures are configured in `toucan.dtsi`, including
motion-to-scroll while NUM or SYM is held.

## System controls

SYS provides Bluetooth profiles 0–4 on Q/W/E/R/T, clear-current-profile on
Backspace, next/previous profile on J/K, Studio unlock on Z, and bootloader
entry on either bottom pinky key.

After flashing, an existing ZMK Studio saved keymap may override firmware
defaults. Reset the saved keymap in Studio to load this layout if needed.

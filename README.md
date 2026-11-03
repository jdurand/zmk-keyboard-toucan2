# ZMK config for beekeeb Toucan2 Keyboard

[The beekeeb Toucan2 Keyboard](https://beekeeb.com/introducing-toucan2/) is a
wireless split 42-key column-stagger keyboard with a display and a trackpad,
and an aggressive stagger on the pinky columns.

# Customizations

- **Keymap**: [config/toucan.keymap](config/toucan.keymap)
- **Layers and shortcuts**: [keymap guide](docs/keymap.md)
- **General configs**: [left config][left-conf] and [right config][right-conf]
- **Swipe shortcuts**: the `swipe_button_mapper` node in [toucan.dtsi][dtsi]
- **Invert scroll / trackpad settings**: the `tps43_trackpad` node in the
  [right overlay][right-overlay]

[left-conf]: boards/shields/toucan/toucan_left.conf
[right-conf]: boards/shields/toucan/toucan_right.conf
[dtsi]: boards/shields/toucan/toucan.dtsi
[right-overlay]: boards/shields/toucan/toucan_right.overlay

# License

The code in this repo is available under the MIT license.

The included shield nice_view_gem is modified from
https://github.com/M165437/nice-view-gem licensed under the MIT License.

The linked trackpad module is based on
https://github.com/geeksville/zmk_driver_azoteq

ZMK code snippets are taken from the ZMK documentation under the MIT license.

The embedded font QuinqueFive is designed by GGBotNet, licensed under the
SIL Open Font License, Version 1.1.

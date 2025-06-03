# Keychron Q7 ANSI Custom Keymap with Home Row Mods

This repository contains a custom QMK keymap for the Keychron Q7 ANSI keyboard, featuring home row mods for enhanced typing efficiency.

## Features

- **Home Row Mods**: Modifier keys (Ctrl, Shift, Alt, GUI) integrated into the home row keys (A, S, D, F, J, K, L, ;)
- **Multiple Layers**:
  - MAC_BASE: Default layer for macOS
  - WIN_BASE: Windows/Linux compatible layer
  - Function layers (FN1, FN2, FN3) for media controls, RGB lighting, and function keys
  - GAMING layer with standard key positions (no home row mods)
- **RGB Lighting Controls**: Comprehensive controls for RGB lighting effects
- **Gaming Toggle**: Easily switch to a gaming-optimized layout without home row mods
- **Adjusted Tapping Term**: Optimized for home row mods to reduce accidental modifier activations

## Home Row Mods Layout

The home row mods are configured as follows:

### Left Hand
- A: GUI (Command/Windows)
- S: Alt (Option)
- D: Shift
- F: Control

### Right Hand
- J: Control
- K: Shift
- L: Alt (Option)
- ; (Semicolon): GUI (Command/Windows)

## Layer Switching

- FN3: Accessed by holding the key to the right of Right Control in MAC_BASE layer
- FN2: Accessed by holding the key to the right of Right Control in WIN_BASE layer
- FN3: Accessed by holding the rightmost key in the bottom row
- GAMING: Toggle on/off by pressing H while in FN3 layer (position of GAMING_TOG key)

## Gaming Mode

The dedicated gaming layer disables home row mods for a traditional typing experience, which is often preferred for gaming where holding keys is common. 

### How to Enter/Exit Gaming Mode
- **Enter Gaming Mode**: Press FN3 + H
- **Exit Gaming Mode**: Press FN3 + H (while in gaming mode)

## Tapping Term Configuration

This keymap uses an extended tapping term to make home row mods more comfortable to use. The tapping term is set in the parent directory's `config.h` file:

```c
#define TAPPING_TERM 300
```

The tapping term defines how long a key needs to be held (in milliseconds) before it registers as a hold action rather than a tap. A higher value like 300ms makes it less likely to accidentally trigger modifiers during normal typing.

If you find yourself accidentally triggering modifiers while typing, you might want to increase this value further. If the modifiers feel sluggish to activate, you might want to decrease it.

## Compilation and Flashing

1. Set up your QMK environment following the [QMK Setup Guide](https://docs.qmk.fm/#/newbs_getting_started)
2. Compile the firmware:
   ```
   qmk compile -kb keychron/q7/ansi -km my_keymap
   ```
3. Flash the firmware:
   ```
   qmk flash -kb keychron/q7/ansi -km my_keymap
   ```

## Customization

To customize this keymap, modify the `keymap.c` file according to your preferences. See the [QMK Keycodes Reference](https://docs.qmk.fm/#/keycodes) for available keycodes.

## Notes on Home Row Mods

Home row mods work by sending modifier keys when held, and regular alphanumeric keys when tapped. This allows you to keep your fingers on the home row while accessing modifiers, reducing hand movement and potentially increasing typing efficiency.

For optimal usage:
- Adjust to the new layout gradually
- You may need to slightly adjust your typing style to avoid accidental modifier activations
- Consider adjusting the TAPPING_TERM value if you experience issues 
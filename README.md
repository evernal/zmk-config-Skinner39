![](https://web-api.textin.com/ocr_image/external/a8fbeec7ad58d1c1.jpg)

## Recent Changes (zmk-update branch)

This branch updates the Skinner39 configuration to be compatible with the latest ZMK firmware and introduces several significant improvements:

### Major Updates

- **ZMK Main Migration**: Migrated to ZMK main branch with Zephyr 4.1 and Hardware Model v2 (HWMv2) board structure
- **Board Structure Modernization**: Restructured board files to the new `boards/FindKBtokyoJP/skinner39/` HWMv2 format
- **Driver Update**: Switched from badjeff's PMW3610 driver to the Zephyr upstream implementation for better compatibility
- **Miryoku Keymap**: Ported Miryoku-style keymap from the ck-keymap branch for improved ergonomic layout

### Bluetooth Performance Optimization

Bluetooth settings have been tuned for improved trackball responsiveness:

- **Lower latency**: 7.5ms connection intervals for faster input response
- **Extended range**: +8dBm TX power for better wireless connectivity
- **Faster radio**: 2M PHY mode for higher throughput and reduced lag
- **Larger buffers**: Increased ACL and L2CAP buffer sizes for smoother trackball data transmission

### Trackball & Input Improvements

- **Trackball cursor direction**: Cursor now moves correctly in all directions
- **Slower scrolling**: Scroll mode is slower for finer control
- **Homerow mods more reliable**: Holding a homerow key (e.g., holding "f" for Shift) is less likely to misfire as a tap during fast typing
- **Device naming**: Left and right halves show distinct names (`Skinner39_Left` / `Skinner39_Right`) in USB and Bluetooth device lists

### Trackball Modes

The trackball supports multiple modes via layer switching:

- **Layer 5 (Scroll mode)**: Trackball acts as a scroll wheel with Y-axis inversion for natural scrolling direction
- **Layer 6 (Snipe mode)**: Trackball sensitivity reduced for precision cursor control

---

## Skinner39

Skinner39 is a wireless split keyboard with OLED displays, inspired by Yawkee's Keyball. As a fan of Blade Runner 2049, this keyboard was designed with imagery from the movie's futuristic, dystopian cityscapes and flying cars as inspiration. Assembly guide available here: https://aeolian-melon-437.notion.site/Skinner39-1a14484f44ee80c3916ad98ebab79145

## Product Details

- Fully wireless (MS88SF2)
- ZMK Studio & ZMK firmware support
- OLED display equipped
- Low-profile and high-profile compatible*1
- Supports 34mm & 25mm trackballs with dedicated case
- 3D printed case with adjustable trackball position
- Rear reset button and Bluetooth ON/OFF switch
- Ultra-thin lithium battery*2
- Magnetic tenting function

## Package Contents

- Assembled left and right set (39 keys total)
- MS88SF2 module
- 2 pre-soldered PCBs*3
- Main case
- Top plate
- 25mm/34mm trackball case (with ceramic support ball)
- 25mm/34mm trackball
- Low-power trackball sensor
- Power switch
- Diodes
- 2 types of screws
- Spacers
- Rubber feet

## Important Notes

*1 Compatible with Choc v1, Choc v2, and MX switches. However, when using Choc V1, you need to purchase dedicated keycaps or 3D print custom keycaps.

*2 Lithium-ion batteries require careful handling for safety. We cannot be held responsible for any accidents or damage resulting from improper handling. For detailed battery safety information, please visit:

https://www.baj.r.jp/battery/safety/safety16.html

*3 Sockets for Choc V1, V2, and MX switches are pre-installed. If you want to use both low-profile and high-profile switches, please purchase the corresponding cases and plates separately.

## Setup Guide

Skinner39 Configuration Instructions

- The left hand is the main unit
- USB connection should be made to the left hand
- Note: The keyboard will not function if only the right hand is connected to the PC
- Select [Skinner39] from your PC's Bluetooth device list to connect
- Once connected, both OLEDs will display the "Wi-Fi" icon and connection device "number"

## If Bluetooth Connection Fails

1. Press the [bt_clr] key and [2] key simultaneously, then try to reconnect wirelessly
2. If connection still fails, press the reset button (round button on the back of the case) once to reset
3. After resetting, press the [bt_clr] key and [2] key again to establish wireless connection

<!-- 0 symbol_layer |SYM --- 1 Skp 6kp 6kp 6kp 6kp 6kp 5kp Skp 2 ! @ # &#36; % Y U 1 O P 3 6bt 6bt 6bt Strons 6kp Skp 6kp 4 BT_CLR BT_SEL O BT_SEL 1 BT_SEL 2 H J K 5kp Skp L ; (BT_CLR)Clear profile 5 Strons Gtrans Gtrans Gtrons Strans Skp Skp 6kp Skp 6kp 6 N M , / + Strans Gtrons Strons 6kp 1 Gtrans Strans Strans 6kp  -->
![](https://web-api.textin.com/ocr_image/external/9f48b8ead660bd21.jpg)

## If You Make Configuration Errors

1. Fork again from ZMK GitHub Actions and download the firmware
2. Connect both keyboard halves via USB
3. Press the reset button, and a device called "keyball" will appear on your PC
4. Paste the reset file into Keyball
5. Reset is complete
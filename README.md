# cy83rd3ck — Hardware

Hardware design files for the cy83rd3ck physical device (handheld music sequencer/groovebox).

## Status: Breadboard validation phase
Core electronics on order (CM4 + CM4IO Board, Teensy 4.1, Waveshare 4" 800x480 DSI touch display,
prototyping supplies). Next step is validating CM4 ↔ Teensy ↔ display ↔ input wiring on a breadboard
before moving to enclosure printing and PCB design.

## Files
- `cy83rd3ck_hardware_concept.pdf` — full concept doc: front-panel diagram (94.6 x 151.51 x 20.3mm),
  side-section depth stack, Bill of Materials, PCB floorplan (front/back), and OpenSCAD source listing.
- `cy83rd3ck_hardware_concept.html` — same content, HTML source (for editing diagrams).
- `cy83rd3ck_pcb_floorplan.pdf` — standalone PCB floorplan (front-facing + back-side concept layout, not routed).
- `cy83rd3ck_front_panel.scad` — OpenSCAD source for the front panel shell (cutouts for screens,
  buttons, sliders, keyboard, speakers). Open in [OpenSCAD](https://openscad.org) to view/render/export STL.

## Key specs
- Enclosure: 94.6 x 151.51 x 20.3mm, SLA resin prototype
- Compute: Raspberry Pi CM4 (CM4108016, 8GB/16GB/Wireless) + CM4IO Board
- MIDI/IO controller: Teensy 4.1
- Screen 1 (main): 4" 800x480 capacitive touch DSI, ~87x52.5mm active area (Waveshare 4-DSI-TOUCH-A, SKU 34354)
- Screen 2: 3.12" SSD1322 mono OLED
- Screen 3: 2.3" 128x32 OLED
- Audio: WM8960 codec, 2x 16mm BeStar speakers
- Power: LP523450 LiPo (1000mAh) + IP5306 charge/boost, USB-C
- Keyboard: 1 octave FSR-based, donor Raimy 37-key toy keyboard

## Links
- Software (browser app): https://happyfaceemoji.github.io/cy83rd3ck
- Ko-fi (prototype fundraiser): https://ko-fi.com/happyfaceemoji

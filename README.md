# Ethan IR Receiver Remaster

![IR Remote Kit](https://github.com/paulwang999/ethan-ir-receiver-remaster/blob/main/1.jpg?raw=true)

A redesigned MakerBit-style IR remote extension for **micro:bit**.  
Supports the 21-key remote shown above — ideal for classroom projects and servo control.



IR Remote Extension (ethan-ir-new_remote)

A redesigned and educational MakeCode extension for the micro:bit that adds an improved IR remote controller layout and servo-control demo, based on the original MakerBit IR receiver blocks.

This version is optimized for beginners, classroom use, and modern MakeCode compatibility.

🔧 Overview of Modifications
1. Custom Remote Layout

The button grid now matches the actual 21-key Keyestudio / common remote layout:

1 2 3
4 5 6
7 8 9
* 0 #
[ ] ↑ [ ]
◀  OK  ▶
[ ] ↓ [ ]


Added blank placeholders to preserve the real physical shape on the MakeCode grid picker.

Moved the "any" button to the last row so it no longer disturbs the remote’s layout but is still available for debugging or universal event handling.

2. Removed MakerBit background dependency

The original MakerBit extension used the background.schedule() API, which isn’t available when running as a standalone project or new extension.

Replaced all calls to background.schedule() with control.runInBackground(), which is part of the core MakeCode runtime and works on all boards.

3. Added Reliable Repeat / Release Handling

Implemented a simple background loop using basic.pause(20) to check for IR repeat timeout.

This ensures correct “Pressed / Released” events without relying on MakerBit’s custom thread scheduler.

4. Improved Compatibility and Stability

Fully compatible with micro:bit V1, V2, and V3.

Avoids conflicts with P0 (speaker pin on V2).

Uses only MakeCode core APIs — no external dependencies.

5. Educational Enhancements

Code comments and block labels rewritten for clarity.

All functions kept under a single MakerBit category for familiarity.

Servo demo examples included to help students quickly see real movement feedback from IR input.



💡 Why These Changes Matter
Problem in Original MakerBit	Solution in This Version
Layout didn’t match real remote → confusing for beginners	Re-arranged buttons and added placeholders to reflect the actual remote
background.schedule missing in MakeCode projects	Replaced with safe control.runInBackground
Events sometimes repeated or stuck	Added repeat timeout loop
Not compatible with MakeCode offline / local test	All logic self-contained, no dependencies
“any” key cluttered the layout	Moved to last line; optional use only
🧠 Educational Purpose

This project was rebuilt for classroom STEM workshops to help children learn:

Event handling (on IR button … pressed)

Hardware control (servo movement, LED indicators)

Microcontroller wiring (signal, power, ground, common-ground principle)

Debugging with MakeCode blocks and serial monitor

🧩 Files
File	Description
infrared-receiver.ts	Main implementation with updated logic
pxt.json	Extension configuration
README.md	Documentation (this file)
LICENSE	MIT license (recommended for education)
icon.png	Optional extension icon
⚙️ How to Use / Import

Upload this repository to GitHub (public).

In MakeCode, open Advanced → Extensions.

Paste your GitHub link,

Wait for it to load — the category MakerBit will appear.

Drag your custom IR and servo blocks into your program!

🪄 License

MIT License — free to use, remix, and share for educational purposes.
Created by paul wang and ethan wang to help kids learn micro:bit robotics and IR control.


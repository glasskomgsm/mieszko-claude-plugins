---
name: design-mechanism
description: >
  This skill should be used when the user wants to design an animatronic or
  mechanism, e.g. "design an animatronic", "how do I make X move", "new
  animatronics project", "design a mechanism for", or describes a figure,
  prop, or creature they want to bring to life with motion.
metadata:
  version: "0.1.0"
---

# Design an animatronic mechanism

Turn an idea ("a raven that turns its head and flaps wings") into a buildable mechanism concept using off-the-shelf parts and basic workshop fabrication.

## Before designing — always ask

1. **Budget** — always ask for the project budget (in PLN) before proposing anything. Tailor actuation and part choices to it.
2. **Motions** — what should move, how far, how fast, how often, and does it need to be synchronized or sequenced?
3. **Size and environment** — rough dimensions, indoor/outdoor, run time (continuous display vs. triggered).
4. Skip questions already answered in the conversation.

## User's workshop context

- Can weld, drill, cut, and tap — steel frames and custom brackets are cheap options, prefer them over exotic bought parts.
- Buys from Allegro, Botland/TME, and local hardware stores. Metric everything. Prices in PLN.
- Keeps only basic materials in stock — every part must go on the parts list.
- Assembles 3D models in Onshape from free downloaded models (GrabCAD etc.).

## Actuation selection

The user works with all of these — pick per motion, not per project:

| Actuation | Best for | Typical parts |
|---|---|---|
| Hobby servo + microcontroller | Precise, sequenced motion under ~35 kg·cm | MG996R/DS3218 class servos, Arduino Nano/ESP32, PCA9685 board, 5-6 V PSU |
| DC gear motor | Continuous or looping motion | 12 V gear motors, motor driver, cams/cranks off the shaft |
| Pneumatics | Fast, strong, linear "pop" motions | Cylinders, 5/2 solenoid valves, compressor, fittings |
| Purely mechanical | Ambient motion, no electronics | Hand crank, springs, counterweights, cam shafts |

Prefer the simplest actuation that meets the motion requirement. One DC motor driving several cams often beats five servos in cost and reliability.

## Mechanism design rules

- Decompose the animatronic into named motions (head-turn, jaw, wing-flap...), then design one mechanism per motion: actuator → transmission (linkage, cam, pushrod, cable/bowden, gear, belt) → output.
- Use standard off-the-shelf transmission parts: 608/6xx series bearings, pillow blocks (KP08, KFL08), 8 mm/10 mm/12 mm steel rods, shaft collars, GT2 belts and pulleys, M3-M8 fasteners, clevises, rod ends, ball links.
- Custom parts must be makeable with weld/drill/cut/tap from common stock: flat bar, angle, tube, threaded rod, sheet.
- State torque/force estimates for each actuated motion and verify the chosen actuator has ~2x margin.
- Flag pinch points and safety issues (especially pneumatics) explicitly.

## Output

Deliver the concept as:

1. Motion list with actuation choice and reasoning per motion.
2. Per-motion mechanism description (actuator → transmission → output), with rough dimensions.
3. Estimated total cost vs. budget.
4. A simple SVG sketch of the key mechanism(s) when it helps understanding.

Then offer the next steps: generate the parts list (`parts-list` skill), find free 3D models (`find-3d-models`), or plan the build (`build-steps`).

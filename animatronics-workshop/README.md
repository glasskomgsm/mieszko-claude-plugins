# Animatronics Workshop

Plugin for designing and building simple animatronics from off-the-shelf parts, tailored to a workshop with welding, drilling, cutting, and tapping capability.

## Skills

| Skill | Trigger | What it does |
|---|---|---|
| design-mechanism | "design an animatronic", "how do I make X move" | Asks budget first, breaks the idea into motions, picks actuation (servo / DC motor / pneumatic / mechanical), designs each mechanism from standard parts |
| parts-list | "parts list", "BOM", "what do I need to buy" | Excel BOM with Buy / Fabricate / Summary sheets — Allegro, Botland/TME and local hardware store sources, prices in PLN, budget check |
| find-3d-models | "find 3D models", "GrabCAD" | Finds free STEP/STL models for the parts, ready to import into Onshape |
| build-steps | "how do I build this", "build plan" | Ordered fabrication and assembly plan with drill/tap sizes, subassembly checks, and test procedure |

## Assumptions baked in

Metric units, PLN prices, no parts stock kept between projects, Onshape as CAD. Edit the SKILL.md files to change these.

## Setup

None — no external connections or environment variables required.

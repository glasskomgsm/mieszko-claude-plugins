---
name: find-3d-models
description: >
  This skill should be used when the user asks to "find 3D models", "find
  CAD files", mentions GrabCAD, or wants downloadable models of bearings,
  motors, servos, or other parts to assemble a project in Onshape.
metadata:
  version: "0.1.0"
---

# Find free 3D models for project parts

Locate free, downloadable 3D models of off-the-shelf parts so the user can assemble the whole project in Onshape.

## Sources, in order of preference

1. **Manufacturer/supplier CAD** — exact geometry: SKF/bearing makers, servo makers, TME product pages (many include 3D models), pneumatics makers (Festo/SMC have CAD portals).
2. **GrabCAD** (grabcad.com/library) — largest community library; most standard parts (608 bearings, MG996R servo, KP08 pillow block, NEMA17...) exist there.
3. **Traceparts / 3DContentCentral** — standard industrial components.
4. **Printables / Thingiverse** — hobby parts and brackets (STL only — mention the limitation).

## Workflow

1. Take the parts list from the conversation (or the BOM file); if none exists, ask which parts need models.
2. For each part, web-search for a matching free model, e.g. "GrabCAD 608 bearing", "MG996R servo STEP".
3. Verify the model matches the actual spec (size, mounting holes) — say when a model is "close but check dimensions".
4. Prefer STEP format — it imports cleanly into Onshape. Note when only STL is available (fine for visual reference, poor for mating).

## Output

A table in chat: part → model name → format → direct link → note (exact match / verify dimensions / STL only). Mark parts with no good free model — for simple ones (spacers, plates, custom brackets), offer to describe the geometry so the user can sketch them in Onshape in minutes.

Do not download files on the user's behalf unless asked — links let the user grab them with their own GrabCAD account.

## Onshape tips to include when relevant

- Import STEP via the + button → Import; each part lands as its own Part Studio.
- Use mate connectors on bearing bores and shaft ends for fast assembly.
- Keep downloaded parts in one folder/document per project.

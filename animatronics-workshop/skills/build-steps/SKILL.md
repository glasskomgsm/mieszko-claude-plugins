---
name: build-steps
description: >
  This skill should be used when the user asks "how do I build this", "in
  what order do I assemble", "build plan", "fabrication steps", or is ready
  to start making and assembling an animatronics project.
metadata:
  version: "0.1.0"
---

# Plan fabrication and assembly

Produce an ordered, workshop-ready build plan for an animatronics project.

## Inputs

Use the mechanism design and parts list from the conversation. If missing, ask for a short project description. Confirm all parts are on hand or note which steps are blocked by missing parts.

## Plan structure

**Phase 1 — Fabrication.** One step per custom part: material, cut dimensions with tolerance hints, drill sizes (state tap-drill sizes explicitly, e.g. M5 → 4.2 mm), tap sizes, weld joints. Order steps so that parts needing fit-up against bought parts (bearing seats, motor mounts) are made after those parts arrive.

**Phase 2 — Subassemblies.** Group by mechanism (one per motion). For each: parts involved, assembly order, what to check before moving on (shaft spins freely, no slop in linkage, servo horn centered at neutral).

**Phase 3 — Integration.** Mount subassemblies to the frame, route cables/hoses with slack at moving joints, wire electronics last.

**Phase 4 — Test and tune.** Power each motion separately at low speed first; set servo end-stops in software before mechanical limits; check current draw; run 15-minute soak test and re-check fasteners.

## Rules

- Number every step; keep each step one action.
- Flag steps where a mistake is expensive or unsafe (welding near finished parts, pneumatic first pressurization) with a warning line.
- Note where threadlocker, lubrication, or loctite-free serviceable joints are wanted.
- End with a short commissioning checklist.

Deliver the plan in chat by default; offer a PDF version for the workshop bench.

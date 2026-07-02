---
name: parts-list
description: >
  This skill should be used when the user asks for a "parts list", "BOM",
  "bill of materials", "what do I need to buy", "shopping list", or wants
  the parts for an animatronics project collected into a spreadsheet.
metadata:
  version: "0.1.0"
---

# Generate a project parts list (Excel BOM)

Produce a complete, buy-ready parts list for an animatronics project as an Excel spreadsheet (.xlsx). Use the xlsx skill for file creation.

## Ground rules

- The user keeps no stock beyond basics — list EVERYTHING needed to complete the project, including fasteners, wire, connectors, and consumables (welding wire, cutting discs, taps only if a new size is needed).
- Metric sizes only. Prices in PLN.
- If a mechanism design exists earlier in the conversation, build the BOM from it. Otherwise ask what the project is, and ask for the budget if not yet known.
- Search current prices and availability with web search — prefer Allegro, Botland, and TME. For hardware-store items (steel stock, generic fasteners), mark "local hardware store" and give a typical price. Do not invent exact prices; if unverified, give a range and mark it as estimated.

## Spreadsheet structure

One workbook, three sheets:

**1. Buy** — off-the-shelf parts:
| # | Part | Spec / size | Qty | Unit price (PLN) | Total | Source | Link / where | Notes |

Group rows by category: actuators, electronics, motion parts (bearings, rods, pulleys), pneumatics, fasteners, materials, consumables. Add a grand-total row and compare against the budget — flag if over.

**2. Fabricate** — parts the user makes:
| # | Part | Made from (stock listed in Buy sheet) | Operations (weld/drill/cut/tap) | Qty | Notes |

Every "made from" material must have a matching row on the Buy sheet.

**3. Summary** — project name, date, total cost, budget, cost by category, and open questions/decisions.

## Formatting

- Bold header rows, currency format for price columns, real SUM formulas (not hardcoded totals).
- Conditional highlight on the budget row: green if under, red if over.
- Column widths sized to content.

Deliver the .xlsx file and a one-paragraph summary: total cost vs. budget and the riskiest items (long shipping, single-source, or price-uncertain parts). Offer to find free 3D models for the bought parts (`find-3d-models` skill).

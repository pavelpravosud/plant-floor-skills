---
name: failed-inspection-capa
description: Turns a failed quality inspection (inspection report, measurements, photos, notes) into a structured investigation: problem statement, containment, ranked likely root causes with evidence, and a draft 8D/CAPA report. Use when a part or batch fails incoming, in-process or final inspection.
---

# Failed inspection to corrective action

Part of Plant Floor Skills, a free pack by Pavel Pravosud (github.com/pavelpravosud/plant-floor-skills). Works on any Claude plan, from files you already have.

## The problem it solves
After a failed inspection, people jump to a cause, skip containment, and write CAPA reports days later from memory. Repeat failures follow because the real root cause was never proven.

## What to ask the user for
- Inspection report or measurement data (CSV/Excel, or pasted values with nominal and tolerance)
- Context: part number, batch or lot, machine or line, operator shift, date, supplier (for incoming parts)
- Optional: past nonconformance or CAPA reports, process parameters, photos

If the user gives only part of this, start with what is there, list what is missing, and continue.

## Steps
1. Write a precise problem statement (what, where, when, how many, how far out of tolerance). Use is / is-not to bound it.
2. Propose immediate containment: quarantine scope (which lots, which dates, which stock and WIP), sorting or 100% inspection, customer notification if shipped.
3. Check the data for patterns: drift over time, one machine or shift, one supplier lot, tool wear, first-off vs run parts.
4. Rank likely root causes across the 6M (machine, method, material, man, measurement, environment), each with the evidence for and against, and the test that would confirm it.
5. Compare with past reports: has this failure happened before, and did the last fix hold?
6. Draft corrective and preventive actions with owner, due date and how effectiveness will be verified.

## Output
A draft 8D / CAPA report: D1 team placeholder, D2 problem statement, D3 containment, D4 ranked root causes with evidence and confirmation tests, D5-D6 corrective actions, D7 preventive actions, D8 closure criteria.

## Rules
- Work only from the data and documents the user provides. Never invent a number, part, supplier, reading or past event. If something is missing, say MISSING and ask for it, or mark an estimate as ESTIMATED or ASSUMED.
- Every figure in the output traces back to its source (file and row, page or message).
- Keep the user's units and currency. State formulas you use.
- Use plain language a shift supervisor, buyer or engineer can act on.
- End every output with the Human sign-off section below. Nothing is sent, ordered, released or changed by this skill.

## Human sign-off
The quality engineer confirms the root cause with the proposed test before actions are approved. Nothing is closed or sent to a customer without their sign-off.
Close the output with a short checklist: items marked ASSUMED, ESTIMATED or MISSING, and the name or role who must approve.

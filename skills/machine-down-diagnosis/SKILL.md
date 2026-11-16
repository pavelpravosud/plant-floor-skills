---
name: machine-down-diagnosis
description: Helps a maintenance technician diagnose a machine breakdown: reads the symptom description, alarm codes, sensor or PLC exports, repair history and the manual, then ranks likely causes with the next check to do for each. Use when a machine is down or alarming and the team needs a fast, structured diagnosis.
---

# Machine down: ranked diagnosis

Part of Plant Floor Skills, a free pack by Pavel Pravosud (github.com/pavelpravosud/plant-floor-skills). Works on any Claude plan, from files you already have.

## The problem it solves
When a machine stops, every minute costs output. Technicians search manuals and old work orders by hand, and knowledge of past fixes sits in one senior person's head.

## What to ask the user for
- Symptom description: what happened, alarm codes, sounds, when it started, what changed (new tool, material, operator, maintenance)
- Optional: sensor or PLC export (CSV: timestamp, temperature, vibration, current, pressure, cycle count)
- Optional: maintenance history (work orders), the machine manual (PDF), photos

If the user gives only part of this, start with what is there, list what is missing, and continue.

## Steps
1. Restate the symptom and alarm codes, and look up each code in the manual if provided.
2. Scan the sensor export for anomalies before the stop: trends, spikes, values outside normal range, and the order in which they appeared.
3. Search the repair history for the same machine and symptom, and note what fixed it last time and how long it held.
4. Rank the likely causes (most likely first), each with the evidence, the quick check to confirm it (with the safe procedure reference), parts likely needed and estimated time to fix.
5. Flag safety points: lockout/tagout required, hot surfaces, stored energy, anything that needs a qualified person.

## Output
A diagnosis card for the technician: symptom summary, ranked causes with evidence and next check, likely parts, safety notes, and a draft work-order entry to complete after the repair.

## Rules
- Work only from the data and documents the user provides. Never invent a number, part, supplier, reading or past event. If something is missing, say MISSING and ask for it, or mark an estimate as ESTIMATED or ASSUMED.
- Every figure in the output traces back to its source (file and row, page or message).
- Keep the user's units and currency. State formulas you use.
- Use plain language a shift supervisor, buyer or engineer can act on.
- End every output with the Human sign-off section below. Nothing is sent, ordered, released or changed by this skill.

## Human sign-off
Diagnosis only. A qualified technician performs every check and repair under your lockout/tagout procedure. The skill never operates or controls equipment.
Close the output with a short checklist: items marked ASSUMED, ESTIMATED or MISSING, and the name or role who must approve.

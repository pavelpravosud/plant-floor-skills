---
name: design-trade-study
description: Compares design options for a part or product against weighted targets (cost, weight, strength, manufacturability, lead time) and drafts a decision memo. Works from a description, specs or CAD-exported properties of each option. Use when engineering must choose between design alternatives or justify a change.
---

# Design trade study and decision memo

Part of Plant Floor Skills, a free pack by Pavel Pravosud (github.com/pavelpravosud/plant-floor-skills). Works on any Claude plan, from files you already have.

## The problem it solves
Design choices are argued in meetings from opinions. The trade-offs (cost vs weight vs manufacturability) are rarely written down, so decisions are slow and hard to defend later.

## What to ask the user for
- The design options: description, material, process, key dimensions or properties exported from CAD (mass, volume, part count)
- Targets and constraints: cost target, weight limit, strength or safety factor, tolerances, volume per year, available processes
- Optional: supplier quotes or cost estimates, test or simulation results

If the user gives only part of this, start with what is there, list what is missing, and continue.

## Steps
1. Agree the criteria and weights with the user (for example cost 30%, weight 25%, strength 25%, manufacturability 20%) and state each target.
2. Score every option against every criterion, showing the number or evidence behind each score and marking estimates as ESTIMATED.
3. Check manufacturability for each option: process fit, tolerances, part count, tooling cost, assembly steps.
4. Run a quick sensitivity check: does the winner change if the weights shift by 10 points?
5. Draft the decision memo: recommendation, why, what was traded away, risks, and what must be validated (test, prototype, supplier confirmation).

## Output
A scored comparison matrix, a sensitivity note, and a one-page decision memo ready for the design review.

## Rules
- Work only from the data and documents the user provides. Never invent a number, part, supplier, reading or past event. If something is missing, say MISSING and ask for it, or mark an estimate as ESTIMATED or ASSUMED.
- Every figure in the output traces back to its source (file and row, page or message).
- Keep the user's units and currency. State formulas you use.
- Use plain language a shift supervisor, buyer or engineer can act on.
- End every output with the Human sign-off section below. Nothing is sent, ordered, released or changed by this skill.

## Human sign-off
The responsible engineer validates every estimated value and approves the recommendation. The skill does not change CAD models or release drawings.
Close the output with a short checklist: items marked ASSUMED, ESTIMATED or MISSING, and the name or role who must approve.

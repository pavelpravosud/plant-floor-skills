---
name: morning-production-report
description: Builds the morning production report from a plain Excel or CSV export of yesterday's production: output against target per line or machine, downtime with reasons, scrap, OEE where data allows, the cost of downtime and missed output, and the top 3 actions for today's meeting. Use every morning before the production meeting.
---

# Morning production report

Part of Plant Floor Skills, a free pack by Pavel Pravosud (github.com/pavelpravosud/plant-floor-skills). Works on any Claude plan, from files you already have.

## The problem it solves
Supervisors spend the first hour of the day copying numbers from the MES or spreadsheets into a report. By the meeting, nobody has time to ask why output was missed or what to fix today.

## What to ask the user for
- A production export (CSV or Excel): date, shift, line or machine, planned quantity, good quantity, scrap, run time, downtime minutes, downtime reason
- Optional: cost per hour of downtime or contribution margin per unit, to put a value on losses
- Optional: previous days' reports to show the trend

If the user gives only part of this, start with what is there, list what is missing, and continue.

## Steps
1. Check the data first: missing shifts, negative or impossible values, duplicate rows. List any issue at the top instead of hiding it.
2. Summarise output vs target per line and in total, with the gap in units and %.
3. Rank downtime by minutes and by reason (Pareto), and show the top 3 reasons.
4. Compute scrap rate and, where run time and ideal cycle time exist, OEE (availability x performance x quality). Mark it as not computable if data is missing.
5. Put a value on losses: downtime cost and missed contribution, using the user's rates.
6. Write the 3 actions for today's meeting, each tied to a number in the report, plus what to watch.

## Output
A one-page report: headline numbers, output vs target table, downtime Pareto, scrap and OEE, cost of losses, data issues, and the top 3 actions. Every figure links back to the rows it came from.

## Rules
- Work only from the data and documents the user provides. Never invent a number, part, supplier, reading or past event. If something is missing, say MISSING and ask for it, or mark an estimate as ESTIMATED or ASSUMED.
- Every figure in the output traces back to its source (file and row, page or message).
- Keep the user's units and currency. State formulas you use.
- Use plain language a shift supervisor, buyer or engineer can act on.
- End every output with the Human sign-off section below. Nothing is sent, ordered, released or changed by this skill.

## Human sign-off
The supervisor checks the data issues and approves the report before it is shared.
Close the output with a short checklist: items marked ASSUMED, ESTIMATED or MISSING, and the name or role who must approve.

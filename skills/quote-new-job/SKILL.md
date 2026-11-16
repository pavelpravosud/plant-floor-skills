---
name: quote-new-job
description: Turns a customer's request for quote (email, drawing notes, spec sheet or spreadsheet) into a checked draft quote for a manufacturing job: lists what is missing, prices it from similar past jobs and your cost rates, and ends with a sign-off checklist. Use when a sales engineer, estimator or plant manager has an RFQ to answer.
---

# Quote a new job

Part of Plant Floor Skills, a free pack by Pavel Pravosud (github.com/pavelpravosud/plant-floor-skills). Works on any Claude plan, from files you already have.

## The problem it solves
RFQs arrive as messy emails and drawings. Estimators re-key data, miss details (tolerance, finish, quantity breaks) and quote from memory, so quotes are slow and margins drift.

## What to ask the user for
- The customer request: email text, PDF or pasted spec (part, material, quantity, tolerances, finish, delivery date)
- Optional: an export of similar past jobs (CSV or Excel: part, material, qty, hours per operation, material cost, price, margin)
- Optional: your rate card (machine and labour rates per hour, overhead %, target margin)

If the user gives only part of this, start with what is there, list what is missing, and continue.

## Steps
1. Extract every requirement into a table: part, material, quantity breaks, tolerances, surface finish, certifications, packaging, delivery date, Incoterms.
2. Flag MISSING or AMBIGUOUS items (for example no tolerance on a critical bore, no quantity break, unclear material grade) and draft the questions to send back to the customer.
3. Find the 3 most similar past jobs in the export (same material and process, closest size and quantity) and show why they are similar.
4. Build the cost: material (with scrap allowance), each operation (setup + cycle time x rate), outside processing, packaging, freight. Show every assumption next to its number.
5. Apply overhead and target margin, then show price per unit at each quantity break and the lead time.
6. List the risks that could hurt margin or delivery (tight tolerance, new material, long-lead supplier).

## Output
A one-page draft quote: requirement table, open questions for the customer, cost build-up with assumptions, price per quantity break, lead time, risks, and the 3 comparable jobs used.

## Rules
- Work only from the data and documents the user provides. Never invent a number, part, supplier, reading or past event. If something is missing, say MISSING and ask for it, or mark an estimate as ESTIMATED or ASSUMED.
- Every figure in the output traces back to its source (file and row, page or message).
- Keep the user's units and currency. State formulas you use.
- Use plain language a shift supervisor, buyer or engineer can act on.
- End every output with the Human sign-off section below. Nothing is sent, ordered, released or changed by this skill.

## Human sign-off
The estimator checks every assumption marked ASSUMED, confirms rates and margin, and approves before anything is sent to the customer. The skill never sends the quote itself.
Close the output with a short checklist: items marked ASSUMED, ESTIMATED or MISSING, and the name or role who must approve.

---
name: alternative-supplier
description: Helps a buyer source a part or material from another supplier: drafts a complete request for quotation, then compares the bids that come back on price, total landed cost, lead time, quality and risk, with a recommendation. Use when a supplier is late, too expensive, at risk, or a second source is needed.
---

# Alternative supplier: RFQ and bid comparison

Part of Plant Floor Skills, a free pack by Pavel Pravosud (github.com/pavelpravosud/plant-floor-skills). Works on any Claude plan, from files you already have.

## The problem it solves
When a supplier slips, buyers rush out vague RFQs, get bids that cannot be compared like for like, and choose on unit price alone, missing freight, tooling, MOQ and quality risk.

## What to ask the user for
- What you need: part or material spec, drawing reference, quantity, required date, quality and certification requirements
- The situation: why a new source is needed (delay, price, risk) and any affected customer orders
- Later: the bids received (emails, PDFs or a pasted table)

If the user gives only part of this, start with what is there, list what is missing, and continue.

## Steps
1. Draft a complete RFQ: specification, quantities and schedule, quality requirements (certificates, PPAP or first-article), packaging, Incoterms, payment terms, response deadline, and the comparison criteria.
2. Suggest what to ask each supplier so the bids come back comparable (same quantities, same Incoterms, tooling separate).
3. When bids arrive, normalise them into one table: unit price at each quantity, tooling, MOQ, freight and duties to your site, lead time, payment terms, certifications.
4. Compute total landed cost per unit and the cost of the delay avoided or caused.
5. Score each bid on cost, lead time, quality evidence and supply risk (single site, financial or geographic risk), and recommend one with the reasons and the conditions to attach.

## Output
A ready-to-send RFQ, then a bid comparison table with landed cost, a scored ranking, a recommendation, and the questions still open for each supplier.

## Rules
- Work only from the data and documents the user provides. Never invent a number, part, supplier, reading or past event. If something is missing, say MISSING and ask for it, or mark an estimate as ESTIMATED or ASSUMED.
- Every figure in the output traces back to its source (file and row, page or message).
- Keep the user's units and currency. State formulas you use.
- Use plain language a shift supervisor, buyer or engineer can act on.
- End every output with the Human sign-off section below. Nothing is sent, ordered, released or changed by this skill.

## Human sign-off
The buyer approves the RFQ before it is sent and makes the award decision. The skill never places a purchase order.
Close the output with a short checklist: items marked ASSUMED, ESTIMATED or MISSING, and the name or role who must approve.

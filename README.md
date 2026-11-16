# Plant Floor Skills (free Claude skills for manufacturing)

Six free Claude skills for the jobs that eat a plant team's day: quoting, quality, maintenance, sourcing, design decisions and the morning report.

**Why this pack is different:** it works on **any Claude plan, including Free**. You need no Enterprise licence and no system connectors. Each skill works from the files you already have: emails, PDFs, drawings notes, and Excel or CSV exports from your ERP, MES or spreadsheets.

By [Pavel Pravosud](https://github.com/pavelpravosud). MIT licence. Independent work, inspired by the manufacturing workflows Anthropic announced on 12 Nov 2026; not affiliated with or copied from Anthropic's Claude for Manufacturing plugin.

## The six skills: what each one solves

### 1. Quote a new job (`quote-new-job`)
- **Problem:** RFQs arrive as messy emails and drawings. Estimators re-key data, miss details and quote from memory, so quotes are slow and margins drift.
- **When:** a customer sends a request for quote, or you need to re-quote a repeat part.
- **Who and where:** sales engineers, estimators, owners of job shops and contract manufacturers, at the desk with the RFQ email open.
- **What you get:** a one-page draft quote with every requirement extracted, the questions to send back to the customer, a cost build-up from your own past jobs and rates, price per quantity break, lead time and margin risks.
- **Benefit:** faster quotes, fewer missed requirements, and margins based on real past jobs instead of memory.

### 2. Failed inspection to corrective action (`failed-inspection-capa`)
- **Problem:** after a failed inspection, people jump to a cause, skip containment and write the CAPA report days later from memory, so the same failure comes back.
- **When:** a part or batch fails incoming, in-process or final inspection, or a customer complaint arrives.
- **Who and where:** quality engineers and quality managers, at the inspection bench or in the quality office.
- **What you get:** a precise problem statement, containment scope, likely root causes ranked across the 6M with evidence and the test that would confirm each, and a draft 8D / CAPA report.
- **Benefit:** containment the same day, root causes proven rather than guessed, and audit-ready reports in minutes.

### 3. Machine down: ranked diagnosis (`machine-down-diagnosis`)
- **Problem:** when a machine stops, every minute costs output. Technicians dig through manuals and old work orders, and the knowledge of past fixes sits in one senior person's head.
- **When:** a machine is down, alarming or behaving strangely.
- **Who and where:** maintenance technicians and maintenance leads, at the machine on a tablet or laptop.
- **What you get:** a diagnosis card with likely causes ranked by evidence (alarm codes, sensor export, repair history, manual), the next safe check for each, likely parts, safety notes and a draft work-order entry.
- **Benefit:** shorter downtime, junior technicians working with senior-level structure, and every fix recorded for next time. Diagnosis only: the skill never operates equipment.

### 4. Alternative supplier: RFQ and bid comparison (`alternative-supplier`)
- **Problem:** when a supplier slips, buyers rush out vague RFQs, get bids that cannot be compared and choose on unit price alone, missing freight, tooling, MOQ and quality risk.
- **When:** a supplier is late, too expensive or at risk, or you need a second source.
- **Who and where:** buyers and purchasing managers, at the desk.
- **What you get:** a complete, ready-to-send RFQ, then a like-for-like bid table with total landed cost, a scored ranking and a recommendation with conditions.
- **Benefit:** a new source in days instead of weeks, decisions on total cost and risk, and a paper trail for the award.

### 5. Design trade study and decision memo (`design-trade-study`)
- **Problem:** design choices are argued in meetings from opinions, and the trade-offs are rarely written down, so decisions are slow and hard to defend later.
- **When:** engineering must choose between design options, or justify a design change.
- **Who and where:** design and manufacturing engineers, before a design review.
- **What you get:** a weighted scoring matrix (cost, weight, strength, manufacturability, lead time), a sensitivity check and a one-page decision memo.
- **Benefit:** faster design reviews, decisions anyone can trace, and manufacturability checked before tooling money is spent.

### 6. Morning production report (`morning-production-report`)
- **Problem:** supervisors spend the first hour of the day copying numbers into a report, so nobody has time to ask why output was missed or what to fix today.
- **When:** every morning, before the production meeting.
- **Who and where:** production supervisors, plant managers and operations leads, from yesterday's MES or spreadsheet export.
- **What you get:** output vs target per line, downtime Pareto, scrap and OEE where data allows, the cost of downtime and missed output, data issues flagged, and the top 3 actions for today.
- **Benefit:** the report in two minutes instead of an hour, and a meeting about actions instead of numbers. Try it with `examples/sample_production_export.csv`.

## Built-in safeguards (all six skills)
- Works only from your data. Never invents numbers; anything missing is marked MISSING, ESTIMATED or ASSUMED.
- Every figure traces back to its source file and row.
- Every output ends with a human sign-off checklist. The skills draft; your people approve. Nothing is sent, ordered, released or changed by a skill.

## Install (any Claude plan, about 2 minutes)
1. In Claude, go to **Settings > Capabilities** and turn on **Code execution and file creation** (on Team or Enterprise, an owner enables skills for the organisation).
2. Download the ZIP of the skill you want from the [`download`](download) folder. Each skill is its own ZIP. Use these ZIPs, not GitHub's green Code button (Claude rejects that ZIP because of its folder name).
3. In Claude, go to **Customize > Skills**, click **+**, then **Create skill > Upload a skill**, and pick the ZIP.
4. Start a chat and ask, for example: *"Build this morning's production report from the attached export"* or *"Turn this RFQ into a draft quote"*, and attach your files.

## Licence
MIT. Use, adapt and share freely. If it helps your team, a star on the repo and a follow on LinkedIn are welcome.

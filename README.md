# Project Migration Command Center

An interactive, single-page dashboard that walks through a business project migration (offshoring, onshoring or reshoring) from start to finish: phases, pre-move checks, formulas, KPIs, RAG tracking and RACI.

**Live demo:** [https://project-migration-cc-ashutosh.netlify.app/](https://project-migration-cc-ashutosh.netlify.app/)

---

## Table of contents

1. [What this is](#what-this-is)
2. [Why it exists](#why-it-exists)
3. [Key terms](#key-terms)
4. [Features by tab](#features-by-tab)
5. [The 8-phase plan](#the-8-phase-plan)
6. [Go-live gate criteria](#go-live-gate-criteria)
7. [Pre-move checklist](#pre-move-checklist)
8. [Formula reference](#formula-reference)
9. [KPI dashboard and RAG logic](#kpi-dashboard-and-rag-logic)
10. [RACI rules](#raci-rules)
11. [How to use it](#how-to-use-it)
12. [Run locally](#run-locally)
13. [Deploy to Netlify](#deploy-to-netlify)
14. [Customize it](#customize-it)
15. [Tech stack and design notes](#tech-stack-and-design-notes)
16. [Limitations](#limitations)
17. [Author and credits](#author-and-credits)

---

## What this is

A self-contained HTML file (HTML, CSS and vanilla JavaScript in one file, no build step, no dependencies) that gives a project team a single place to plan and monitor a migration. It covers the full lifecycle in phases, from the first assessment to steady state.

## Why it exists

When work moves from one location to another (for example from the USA to India, or back), the move itself is rarely what fails. What fails is the small stuff nobody checked: who owns what, whether service levels hold, whether quality stays the same, and whether compliance is intact. This dashboard puts those checks, the maths behind them, and the governance tools in one place.

Typical examples: claims processing, MIS reporting, finance operations, IT support.

## Key terms

| Term | Meaning |
| --- | --- |
| Offshoring | Moving work to a lower-cost country such as India |
| Onshoring | Moving work to the home country or a higher-cost region |
| Reshoring / backshoring | Returning work that was previously moved away |
| SLA | Service Level Agreement, the agreed service target |
| FTE | Full-Time Equivalent, a unit of staffing capacity |
| AHT | Average Handle Time per item |
| TAT | Turnaround Time |
| KT | Knowledge Transfer |
| RAG | Red / Amber / Green status |
| RACI | Responsible, Accountable, Consulted, Informed |
| RAID | Risks, Assumptions, Issues, Dependencies |
| FPY | First Pass Yield |
| SOP | Standard Operating Procedure |

## Features by tab

| Tab | What it gives you |
| --- | --- |
| **Overview** | Definitions, live summary cards (phases, timeline, checklist progress, RAG counts), a timeline bar, and a short how-to |
| **Phase Roadmap** | 8 expandable phase cards with duration, output, key activities, exit gate and focus areas, plus tickable go-live gate criteria |
| **Pre-Move Checklist** | 7 check areas with tick boxes and an overall progress bar |
| **Formula Lab** | 18 live calculators for SLA, FTE, quality, people, financial and transition metrics |
| **KPI Dashboard** | 14 KPIs with targets, tolerances and direction; type in actuals and the RAG colour updates automatically |
| **RAG Tracker** | Editable tracker with 11 columns, pre-seeded with one row per phase, and an add-row button |
| **RACI** | Clickable matrix of 9 activities by 8 roles with automatic validation |
| **Practical Tips** | Six field-tested tips for running the programme |

## The 8-phase plan

| Phase | Typical duration | Key output |
| --- | --- | --- |
| 1. Assess and business case | 4–6 weeks | Approved scope and case |
| 2. Design and blueprint | 4–6 weeks | Target operating model, SOPs, controls |
| 3. Build and hire | 6–10 weeks | Team hired, access and tools ready |
| 4. Knowledge transfer and shadowing | 8–12 weeks | KT sign-off, shadowing completed |
| 5. Reverse KT and assisted run | 4–6 weeks | Offshore team handles work with onshore backup |
| 6. Parallel run | 4–8 weeks | Output and quality variance measured |
| 7. Go-live and hypercare | 4–6 weeks | Stable SLAs with daily monitoring |
| 8. Steady state and decommission | Ongoing | BAU handover, onshore exit |

Phases 1–7 add up to roughly **34–54 weeks**. Phase 8 is ongoing.

## Go-live gate criteria

- Parallel-run output variance under 2%
- SLA met for 3 consecutive weeks
- Accuracy at or above target (for example 98%)
- 100% of critical project KT signed off
- Controls tested and evidence captured
- Escalation matrix and contact list live

## Pre-move checklist

1. **Project selection:** volume, peaks and AHT; rule-based vs judgment-heavy work; automation potential (automate first); dependencies on onshore people, systems and decisions.
2. **Business case:** fully loaded cost per FTE; total offshore cost including transition, dual running, travel, attrition and management overhead; net savings, one-time cost and payback; risk-adjusted ramp-up at 60–80% productivity.
3. **Regulatory and compliance:** data privacy and cross-border rules (GDPR, US state rules, RBI/IRDAI, client clauses); data residency, access controls and PII masking; audit trail, SOX or internal controls, regulator notice; licensing for the performing entity.
4. **People:** attrition risk and retention incentives; knowledge transfer plan and owners; labour law obligations (notice, severance, consultation); shift design and time-zone overlap.
5. **Technology and access:** systems inventory and licences; VPN/SSO and provisioning lead times; data flows, transfers and dependent reports; tool readiness (Power BI, RPA, ticketing).
6. **Project readiness:** SOPs documented and version-controlled; project maps, decision trees and exceptions; escalation matrix and control points; baseline KPIs from the current state.
7. **Governance:** steering committee; RAID log; change control; go/no-go criteria at each gate.

## Formula reference

**SLA and service**

- SLA compliance % = (Items within SLA ÷ Total completed) × 100
- Breach % = 100 − SLA compliance %
- Average TAT = Σ(Completion − Start) ÷ Items
- Throughput = Items completed ÷ Period
- Backlog ageing = Open items grouped by age (0–1 day, 2–5 days, 5+ days)

**FTE and capacity**

- Productive hours per FTE = (Working days − Leave − Holidays − Training) × Hours per day × Utilization %
- Shrinkage % = (Leave + Training + Meetings + Absence) ÷ Paid hours × 100
- FTE required = (Annual volume × AHT in hours) ÷ Productive hours per FTE
- Add a 10–15% buffer for attrition and ramp-up

*Worked example:* 120,000 transactions × 0.25 hr = 30,000 hours. Productive hours per FTE = 219 days × 8 × 80% = 1,401.6. FTE required = 21.4, so plan for 22, or about 24–25 with buffer.

**Quality**

- Accuracy % = (Error-free items ÷ Items checked) × 100
- First Pass Yield = Right first time ÷ Total items
- Rework % = Reworked items ÷ Total items

**People**

- Attrition % (annualized) = (Leavers ÷ Average headcount) × (12 ÷ months in period) × 100
- Utilization % = Productive time ÷ Available time

**Financial**

- Cost per transaction = Total operating cost ÷ Volume
- Savings % = (Onshore cost − Total offshore cost) ÷ Onshore cost × 100
- Payback period (months) = One-time transition cost ÷ Monthly net savings

**Transition**

- KT completion % = Modules signed off ÷ Total modules
- Parallel-run variance % = |New output − Old output| ÷ Old output × 100
- Defect leakage = Errors found after go-live ÷ Total items processed

## KPI dashboard and RAG logic

| Category | KPIs | Example target |
| --- | --- | --- |
| Service | SLA %, TAT, backlog | SLA ≥ 95% |
| Quality | Accuracy, FPY, audit findings | Accuracy ≥ 98% |
| Productivity | Items per FTE, utilization | At or above baseline |
| People | Attrition, training completion | Attrition under 15% |
| Financial | Cost per transaction, savings realized | Within 5% of plan |
| Transition | KT %, milestones on time, variance | 100% critical KT |

**RAG thresholds** (agree these before you start, so everyone reads the colours the same way):

- **Green:** actual meets or beats target
- **Amber:** within tolerance (for example 2 percentage points or 5% of target)
- **Red:** outside tolerance, or a milestone is missed with no recovery plan

For "lower is better" metrics (attrition, TAT, backlog, breach rate, cost), the logic is reversed. The dashboard handles this per KPI.

**RAG Tracker columns:** Workstream, Milestone, Owner, Due date, % complete, RAG, Trend (↑ → ↓), Issue / risk, Mitigation, Next action, Last updated.

## RACI rules

- Exactly **one A** (Accountable) per row
- At least **one R** (Responsible) per row
- Everyone else is C (Consulted) or I (Informed)
- Click a cell to cycle **R → A → C → I → A/R → –**
- The Check column shows **OK** or flags the problem (for example "2 A" or "No R")

Default roles: Sponsor, Programme manager, Onshore SME, Offshore lead, HR, Legal/Compliance, IT, Quality/Risk.

## How to use it

1. Open the live demo and read the **Overview**.
2. Walk the **Phase Roadmap** phase by phase and note the exit gate for each.
3. Tick items in the **Pre-Move Checklist** as your team confirms them.
4. Test your own numbers in the **Formula Lab**.
5. Enter actuals in the **KPI Dashboard** and watch the RAG colours update.
6. Maintain the **RAG Tracker** weekly and use it in your steering review.
7. Assign roles in the **RACI** tab and fix any row flagged red.

**Working rhythm that suits this plan**

- Measure the baseline before any change. If you don't know today's SLA and accuracy, you can't prove the move worked.
- Run a weekly steering review with a one-page dashboard: SLA, quality, RAG, top 5 risks, decisions needed.
- Plan for the dip: expect a temporary fall in productivity and quality in the first 2–3 months.
- Automate before you move wherever work is rule-based and high-volume.
- Never skip a go/no-go gate.

## Run locally

No installation needed.

```bash
# Option 1: just open the file
open Project_Migration_Command_Center.html      # macOS
start Project_Migration_Command_Center.html     # Windows

# Option 2: serve it locally
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to Netlify

1. Put `index.html` (the dashboard file, renamed) in a folder.
2. Go to Netlify, choose **Add new site → Deploy manually**, and drag the folder in.
3. Optionally change the site name under **Site configuration → Change site name**.

Or connect a Git repository and set the publish directory to the folder containing `index.html`. No build command is needed.

The current deployment is at **[https://project-migration-cc-ashutosh.netlify.app/](https://project-migration-cc-ashutosh.netlify.app/)**

## Customize it

Everything is data-driven, so most changes mean editing a list near the top of the `<script>` block:

| What to change | Variable |
| --- | --- |
| Phases, durations, activities, exit gates | `PH` |
| Go-live gate criteria | `GATE` |
| Checklist areas and items | `CK` |
| Formula calculators and default inputs | `CAL` |
| KPI names, targets, direction, tolerance, sample actuals | `KP` |
| RAG tracker starting rows | `RAGR` |
| RACI roles and default assignments | `ROLES`, `RACI` |
| Colours and dark mode | CSS variables on `:root` |

## Tech stack and design notes

- Plain HTML, CSS and vanilla JavaScript in a single file
- No frameworks, no external requests, no tracking
- Responsive layout with horizontally scrolling tables on small screens
- Automatic light and dark mode through CSS variables
- Tab bar uses a single delegated click listener and ARIA roles; the URL hash (`#1` to `#8`) opens a specific tab

## Limitations

- **Sample data:** all numbers in the Formula Lab, KPI Dashboard and RAG Tracker are illustrative. Replace them with your own baseline before using it for decisions.
- **No saving:** entries live in the browser session only and reset on refresh. For a persistent version, add `localStorage` or export to Excel or Power BI.
- **Planning aid, not advice:** durations and thresholds are typical starting points. Legal, labour and data-privacy requirements must be confirmed with your own legal and compliance teams.

## Author and credits

Created by **Ashutosh Mishra** (Ash), with design and code assistance from Claude (Anthropic).

If you are hiring for reporting, automation, Power BI or RPA roles, or would like to discuss migration reporting, feel free to connect on LinkedIn.

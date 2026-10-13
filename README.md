# Faculty Affairs Operations Platform

A single-file web platform for Faculty Affairs operations at Harvard FAS.

Built by Narissara Khomkhai. Demonstration build with synthesized sample data
where real data is unavailable. Every figure is labelled by source.

---

## What this is

A working tool for the Dean for Faculty Affairs and Planning, the Senior
Associate Deans, and their staff.

It is not a dashboard. It is not a reporting system. It is a **playbook**
with a dashboard attached — built around the office's actual structure:
who decides what, who produces evidence, and who carries which portfolio.

The organising principle is simple: **the handbook is the product**. Every
other view — the control tower, the dashboard, the forecast lab, the
analytics console — exists in service of executing the handbook well.

---

## The three seats

The office has three people who each carry a distinct portfolio. The
platform is built around **who decides what**, not around features.

### Dean for Faculty Affairs and Planning

**Decides:** tenure and promotion cases, leaves and sabbaticals, the
faculty workforce plan, crisis and governance response.

**Sees:** the Dean's dashboard, the control tower, the handbook playbook,
the workforce forecast, the composition and equity views.

### Senior Associate Dean — faculty data and appointments

**Carries:** non-ladder and visiting faculty, Title IX and professional
conduct, data and information systems, the Faculty Appointments Office.

**Sees:** the cockpit filtered to that remit, the handbook playbook with
chapters 9b, 11 and 13 called out, the conduct tracker, the data lineage
tab.

### Senior Associate Dean — research and recruitment

**Carries:** research appointments, faculty outside activities and
conflict of commitment, tenure-track recruitment and retention, TA policy.

**Sees:** the outside-activity tracker, the research appointments view,
the search workflow, the TA/TF tab.

**Why the seats differ.** The office page is explicit about who carries
what. The platform encodes that structure: a seat that does not carry
faculty data does not see workforce indicators. That is not a limitation;
it is the office structure reflected in software.

---

## Five design principles

### 1. Provenance before everything

Every figure carries a label:

| Layer | Meaning | Colour |
|---|---|---|
| REAL | FAS faculty extract or published FAS report | green |
| MODEL | Forecast or calculation; not a count | purple |
| SAMPLE | Synthesized for demonstration | orange |
| DOCUMENT | Text from a handbook or policy page | grey |
| ASSUMPTION | An input you can change | orange |
| USER | Entered in this browser | blue |

A sample figure next to a real one, without a label, is a figure that will
eventually mislead someone. The provenance discipline is the single most
important design decision in this build.

### 2. Check first, then decide

The control tower opens with six readiness gates:

1. Is the evidence current enough to plan from?
2. Do the published and extracted totals agree?
3. Do hires and exits explain the movement?
4. Does the aggregate hide a unit under pressure?
5. Has a passed date been mistaken for a done one?
6. Can this hold real case data yet?

A Dean's office acting on an August 2024 extract in the 2026–27 cycle is
making a dated decision. The platform refuses to hide that.

### 3. One seat at a time

The platform opens with "Who is working?" — one seat per person. Each seat
sees only what that office decides, owes and must chase. A shared
dashboard that shows everything to everyone is a dashboard nobody trusts.

### 4. The handbook is the product

The playbook tab is the heart of the platform. Ten governed processes,
each with:

- numbered steps in order
- the responsible party for each step
- the documents each step produces
- the lead time
- the published deadline
- the rules that catch people out

### 5. Name the gaps

Where the data does not exist — course coverage, teaching load, budget
lines — the platform says so. It does not estimate. It does not
interpolate. It shows a card that says "Not connected" and names the
source that would fill it.

---

## What is covered

| Capability | Data layer |
|---|---|
| Faculty headcount and composition | REAL |
| Ladder forecast to 2030–31 | MODEL |
| Division-level teaching capacity | REAL |
| Non-ladder teaching corps | MODEL + published |
| Leave and coverage | REAL |
| Tenure-track pipeline | REAL |
| Handbook playbook, 10 processes | DOCUMENT |
| Published academic calendar 2026–27 | DOCUMENT |
| Control tower, six readiness gates | MIXED |
| Analytics console, four capabilities × six domains | MIXED |
| Forecast lab with backtest and 80% bands | MODEL |
| Email engine, drafts built from the handbook record | DOCUMENT |
| Contacts directory, 2026–27 | DOCUMENT |

### The four analytics capabilities

Applied across six domains:

- **Descriptive** — what happened
- **Diagnostic** — why it happened
- **Predictive** — what is likely next
- **Prescriptive** — what to do about it

Domains: academic operations · faculty affairs and talent · workforce
planning · academic programmes and capacity · finance and resource
planning · portfolio and governance.

---

## What is not covered (named gaps)

Where a feed does not exist, the platform says so rather than inventing a
number. These are the gaps a Dean will see named on the dashboard.

| Gap | Source to connect |
|---|---|
| Course coverage by term | my.harvard / SIS |
| Section fill and enrollment | SIS |
| Teaching load per faculty member | SIS + faculty roster |
| TF and TA allocation | GSAS / FAS TF records |
| PhD admissions and yield | GSAS |
| Space and scheduling | FAS Registrar |
| Curriculum and programme review | FAS Registrar |
| Budget vs actual by division | FAS Finance |
| Position control: authorised, filled, frozen | Aurora |
| Funding source per hire | FAS Finance |
| Live case status by process | Aurora / Appointments Office log |

The gaps are themselves a finding. The platform says, in effect: *here are
the questions a Dean needs to answer that we cannot yet feed.*

---

## Running it

Open the HTML file in a browser.

- No install
- No server
- No build step
- No data leaves the browser

Everything runs client-side. State that persists (KPI thresholds, decision
log entries, planner assumptions) is saved in the browser's local storage
and is per-device.

---

## Repository structure

```
.
├── README.md
├── index.html          # the platform, single file
└── docs/
    ├── design.md       # design decisions and rationale
    ├── data.md         # provenance, sources, refresh cadence
    └── gaps.md         # the named gaps and their source systems
```

---

## Data sources and credits

**Workforce figures.** FAS faculty extract of 13 August 2024, and
published FAS reports (Annual Report 2024 Faculty Trends; FAS faculty
meeting, December 2025; Harvard OIRA Fact Book, Fall 2025).

**Handbook.** FAS Appointment and Promotion Handbook, chapters and
subsections read 6 October 2026.

**Deadlines.** Chapter 2H, AY 2026–27, checked 7 October 2026.

**Contacts.** FAS Contact Information by Topic 2026–27, and the FAS
Office for Faculty Affairs page.

**Sample content.** Where figures are synthesized for demonstration, they
carry the SAMPLE label. They are not Harvard data and must not be quoted.

---

## Status

Demonstration build. Not a system of record. Not an institutional
approval. Every real decision still runs through the office's own
processes.

---

## Licence

MIT

---

## Credits

Created by Narissara Khomkhai.

Platform design, data model, and interface. Built with a single HTML
file, vanilla JavaScript, and the FAS faculty extract as its evidence base.

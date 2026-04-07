# AI After-Action Workflow

## Purpose

This document defines a lightweight reporting workflow for Campaign Juniper Spear 2026 that preserves the original OJS staff-product model while reducing manual rewrite work.

The goal is not to let AI decide campaign canon. The goal is to use AI to turn raw after-action material into draft staff documents that campaign leadership can approve and carry forward into the next mission.

## Why this workflow exists

The original OJS material shows a clear pattern:

- mission orders and phase documents were prepared in advance
- post-mission reports were written after key operations
- those reports appear to have been used to justify the next operational step

The strongest examples are in `OJS Original Documents/(01) Reports`, including:

- `OPSUM - OJS - M2`
- `OPSUM - OJS - M4`
- `OPSUM - OJS - M6`
- `OPSUM - OJS - M8`
- `Intel Package OP JS II Dealbreaker`

That means the real bridge between missions was not the raw forum AAR by itself. The bridge was the curated staff product that converted player activity into approved campaign state.

## Operating principle

AI should update campaign state first, then draft human-readable documents from that state.

The approval chain should be:

1. collect raw mission material
2. extract structured facts
3. update a draft campaign ledger
4. generate draft reporting products
5. approve or reject disputed items
6. publish approved outputs and carry the ledger forward

## Required inputs

Each mission should have one intake packet built from as many of the following as are available:

- forum AARs
- mission-end staff summary
- Zeus or GM notes
- casualty summary
- logistics or ammunition summary
- screenshots or annotated overlays
- optional comms transcript
- optional mission timeline

Use [`docs/templates/mission-intake-template.md`](templates/mission-intake-template.md) for the intake packet.

## Canon workflow

### Step 1: Build the mission intake packet

Moderators or campaign staff consolidate all available post-mission material into a single structured intake.

### Step 2: Extract the campaign fact sheet

AI converts the intake packet into a normalized record covering:

- mission result
- objectives completed, partially completed, or failed
- friendly and enemy casualties
- key leaders captured, killed, or escaped
- materiel destroyed or recovered
- intelligence recovered
- civilian impact
- major decisions, deviations, and surprises
- unresolved threats
- continuity hooks for the next mission

Use [`docs/templates/campaign-fact-sheet-template.md`](templates/campaign-fact-sheet-template.md).

### Step 3: Update the campaign ledger

The campaign ledger is the machine-readable canon source for the running operation. AI should propose changes to it before drafting narrative documents.

The ledger should track at minimum:

- mission status by episode
- current enemy network status
- known locations and denied areas
- named friendly, hostile, and civilian actors
- recovered or missing intelligence
- logistics and force degradation
- unresolved story threads
- pending opportunities and risks

Use [`docs/templates/campaign-ledger-template.json`](templates/campaign-ledger-template.json).

### Step 4: Generate draft outputs

Once the draft ledger update exists, AI can generate multiple outputs from the same approved fact base:

- community-facing AAR summary
- OPSUM for operational outcome
- INTSUM or INTREP for exploitable intelligence
- optional SITREP for a shorter command update
- next-mission handoff for the planner writing the next OPORD or FRAGORD

Use these templates:

- [`docs/templates/opsum-template.md`](templates/opsum-template.md)
- [`docs/templates/intel-annex-template.md`](templates/intel-annex-template.md)
- [`docs/templates/next-mission-handoff-template.md`](templates/next-mission-handoff-template.md)

### Step 5: Human approval

Campaign leadership must approve:

- disputed or weakly supported facts
- what becomes canon
- what remains rumor, assessment, or unresolved reporting
- how player success or failure affects the next mission

AI may draft recommendations, but it must not make final canon decisions on its own.

### Step 6: Publish and hand off

After approval:

- publish the approved reporting products
- save the approved campaign ledger state
- hand the next-mission package to the mission planner

## Output set

### Community-facing output

Use a short narrative AAR for forums or public recap posts. This should be readable and dramatic, but it should not be the canonical source of campaign truth.

### Staff-facing output

The authoritative reporting set should stay closer to the original OJS pattern:

- OPSUM for mission outcome
- intel annex for exploitation and follow-on analysis
- handoff brief for the next mission planner

## Data handling rules

- mark uncertain claims as disputed, unverified, or assessed
- separate observed facts from inferred conclusions
- record source references for important claims
- prefer omission over invention when evidence is thin
- keep every published draft traceable to the mission intake packet

## Suggested implementation order

1. use the templates in this repository manually for one mission
2. refine the sections that campaign staff actually use
3. adopt the ledger as the campaign canon source
4. later, add scripting or automation only after the manual workflow is stable

## Success criteria

The workflow is working if it produces:

- one intake packet per mission
- one approved fact sheet per mission
- one updated ledger per mission
- one approved staff reporting set per mission
- one clean handoff into the next planning cycle

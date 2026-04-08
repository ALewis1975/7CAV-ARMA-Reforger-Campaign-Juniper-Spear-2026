# Campaign process plan draft

## Purpose

This document turns the repository's existing continuity workflow into a 7CAV campaign operating model.

It is an organizational and staff-process plan, not a live-mission automation design.

## Operating model

The campaign should run on two layers:

1. **Reforger mission runtime** for deterministic scenario execution, player interaction, and mission-end export.
2. **GitHub continuity layer** for campaign state, review, staffing products, and approved canon updates.

Under this model:

- AI supports staff work before and after missions.
- AI does not drive minute-to-minute tactical control during live play.
- GitHub pull requests are the approval gate for canon updates.
- The approved campaign ledger remains the source of truth for follow-on orders.

## Core workflow

### 1. Pre-mission planning

Before each mission:

- build or update the mission briefing from approved campaign state
- prepare a controller packet from the approved OPORD or FRAGO
- issue a short controller pace card
- assign campaign staff roles for the event

Use these templates:

- [`docs/templates/controller-packet-template.md`](templates/controller-packet-template.md)
- [`docs/templates/controller-pace-card-template.md`](templates/controller-pace-card-template.md)
- [`docs/templates/mission-briefing-slides-template.md`](templates/mission-briefing-slides-template.md)

### 2. Live mission execution

During the mission:

- keep mission logic deterministic and mission-focused
- use controllers to preserve intent, pacing, and consequences
- avoid turning the mission into a run-and-gun acceleration loop
- record major events, controller interventions, and deviations for later review

### 3. Post-mission intake

After each event:

- compile one mission intake packet
- attach forum AAR material, GM notes, casualty and logistics summaries, screenshots, and optional transcripts
- identify what is observed fact, what is assessed, and what is disputed

Use [`docs/templates/mission-intake-template.md`](templates/mission-intake-template.md).

### 4. AI-assisted synthesis

Once the intake packet is ready:

- draft a normalized campaign fact sheet
- draft mission-log and state-delta outputs
- draft staff-facing reporting products
- draft the public forum AAR in BBCode

AI should always update the ledger draft before it writes narrative follow-on products.

Use:

- [`docs/templates/campaign-fact-sheet-template.md`](templates/campaign-fact-sheet-template.md)
- [`docs/templates/campaign-ledger-template.json`](templates/campaign-ledger-template.json)
- [`docs/templates/opsum-template.md`](templates/opsum-template.md)
- [`docs/templates/intel-annex-template.md`](templates/intel-annex-template.md)
- [`docs/templates/next-mission-handoff-template.md`](templates/next-mission-handoff-template.md)
- [`docs/templates/forum-aar-template.md`](templates/forum-aar-template.md)

### 5. Review and canon approval

Campaign staff should review:

- proposed ledger updates
- disputed or weakly supported facts
- named-actor status changes
- civilian-impact updates
- WMD-related findings
- any change that alters the next mission baseline

Merge approval in GitHub is the canon decision point.

### 6. Publish and hand off

After approval:

- save the approved ledger state
- publish approved staff and community outputs
- hand the next-mission package to the planner
- carry forward unresolved risks, staffing gaps, and continuity threads

## Controller support model

The campaign should control pace before the mission, not improvise it during the mission.

Each mission should produce a controller packet that includes:

- commander's intent
- desired tempo and friction model
- escalation rules
- failure conditions and fail-forward guidance
- branch triggers and sequel boundaries
- explicit "do not accelerate" rules
- likely player friction points and how to let them play out

Each mission should also issue a short pace card for controllers that answers:

- when to slow the mission down
- when to allow friction to breathe
- when to inject pressure
- when not to improvise new escalation

Post-mission review should compare actual controller actions against the controller packet and log drift as a review item.

## Staff billets and training model

To reduce the burden on scarce officers and controllers, split campaign work into smaller billets:

- mission commander
- controller or GM
- AAR curator
- continuity officer *(AI agent)*
- intel and order drafter *(AI agent)*

Each billet should have:

- a short purpose statement
- a pre-mission checklist
- an execution checklist where applicable
- a post-mission checklist
- defined handoff outputs

See [`docs/staff-role-playbooks.md`](staff-role-playbooks.md).

## Continuity and persistence model

To survive volunteer turnover and long time gaps:

- keep campaign history, named actors, unresolved threads, logistics state, and pending review items in GitHub
- review changes by pull request so state transitions stay visible
- use Issues or a Project board for open storylines, staffing gaps, continuity risks, and pending staff decisions
- require each mission to publish the same standard output set

The minimum output set per mission should be:

- intake packet
- fact sheet
- mission-log export
- state-delta export
- forum AAR draft
- OPSUM
- intel annex when needed
- next-mission handoff
- mission briefing slide outline for the follow-on event

## Console-player considerations

Campaign process should assume mixed PC and console participation.

That means:

- avoid dependence on player-side mod workflows
- keep player tasks, role expectations, and briefing outputs concise
- favor staff-side GitHub tooling over in-game data entry requirements
- design AAR collection so console players still feed the same intake packet through staff-curated summaries and forum posts
- keep command-and-control products readable in short-form briefing formats

## GitHub-native operating model

Recommended platform use:

- **Discussions** for planning debates, adaptation concepts, and staffing conversations
- **Issues** for mission tasks, staffing shortages, open continuity questions, controller lessons learned, and unresolved risks
- **Pull requests** for ledger updates, mission output review, and canon approval
- **Templates** for intake, reporting, handoff, briefing, and controller-support products
- **Actions later** for validation, reminders, or file generation only after the manual workflow is stable

## Minimum viable AI use

### Pre-mission

- draft controller packet
- draft controller pace card
- draft briefing slides
- draft concise intel summary

### Post-mission

- normalize AAR inputs
- extract structured facts
- draft ledger updates
- draft BBCode forum AAR
- draft OPSUM, intel annex, and next-mission handoff

### Between missions

- summarize trends across AARs
- identify recurring controller issues
- surface continuity risks
- propose enemy adaptation options for staff approval

## Governance rules

- AI drafts; humans approve.
- Do not let AI adjudicate live tactical outcomes as canon on its own.
- Separate observed facts from assessed conclusions.
- Mark weak evidence as disputed, unverified, or assessed.
- Require explicit human review for named-actor status changes, civilian-impact changes, WMD-related findings, and next-mission baseline changes.
- Prefer omission over invention.

## Rollout sequence

1. Run one full mission through the existing manual loop.
2. Prove intake to ledger draft to approved PR to next-mission handoff.
3. Refine only the sections staff actually use.
4. Formalize billets, checklists, and controller products.
5. Add selective GitHub automation only after the manual process is stable.

## Success criteria

The process is working when it:

- preserves mission tempo and intent without ad hoc controller escalation
- reduces manual rewrite work for AARs and follow-on orders
- keeps canon traceable to reviewed source packets
- allows staff turnover without losing campaign continuity
- supports mixed PC and console participation without changing the core workflow

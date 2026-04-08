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

### Phase III - Initial Conduct

#### Operational concept

Task Force Iron Vanguard executes the coastal and urban break-in that establishes operational momentum and strips Umar of his littoral shield. This phase covers the first campaign mission block and should end with proof that the network has displaced inland.

#### Mission line

| Mission | Working title | Campaign role | Primary form | Task unit |
| --- | --- | --- | --- | --- |
| M1 | Tripwire | Ranger recon and HUMINT along the littoral to map the smuggling network before the main raid | Special reconnaissance / HUMINT patrol | Ranger platoon attachment |
| M2 | Dealbreaker | Raid a coastal facilitator node and recover manifests, radios, and route intelligence | Coastal raid | 1-7 CAV (reinforced) |
| M3 | Stranglehold | Establish checkpoints and observation posts to control population movement and screen displaced persons | Checkpoint and security operation | HQ / support elements with host-nation security |
| M4 | Deliverance | Recover isolated personnel and preserve momentum on the urban fringe | Personnel recovery | 1-7 CAV (reinforced) |
| M5 | Open Hands | Medical outreach in a civilian area affected by the fighting, collecting local intelligence while providing care | MEDCAP / civil-military operation | Medical section with security element |
| M6 | Thunder and Lightning | Seize a military complex and route junction to break the urban defensive belt | Mechanized deliberate attack | 1-7 CAV (reinforced) |
| M7 | Iron Council | HQ staff exercise and wargame for the inland exploitation phase, synthesizing M1-M6 intelligence | Planning and wargaming exercise | Task Force Iron Vanguard HQ |
| M8 | Window Shopping | Cordon and clear a market or industrial district and confirm inland escape | Urban cordon and assault | 1-7 CAV (reinforced) |

#### Tasks by major element

| Element | Phase III tasks |
| --- | --- |
| Task Force Iron Vanguard HQ | Sequence M1-M8 for cumulative intelligence gain and tempo preservation; lead M7 planning exercise |
| 1-7 CAV (reinforced) | Conduct the main raid, rescue, breakthrough, and urban assault actions |
| Air assault company attachment | Provide blocking positions, rooftop or compound seizure, and rapid repositioning |
| Ranger platoon attachment | Support HVT capture windows and sensitive-site exploitation |
| 2-12 ARS-equivalent screen | Seal reinforcement lanes and monitor retreat routes out of the city |
| 2-227 AVN-equivalent detachment | Lift QRF elements, support CASEVAC, and extend operational reach |
| 7-17 CAV-equivalent detachment | Escort aviation and suppress technical-mounted counterattacks |
| Host-nation security forces | Hold cordons, secure detainees, assume control of cleared facilities |
| Urban police / gendarmerie | Restore checkpoint and crowd-control posture after key objectives are seized |

---

### Phase IV - Exploitation

#### Operational concept

With the enemy forced out of exposed coastal and urban nodes, the campaign transitions to inland pursuit, network reduction, WMD recovery, and sanctuary isolation. This is the decisive phase for collapsing Umar's ability to preserve his network and sanctuary system.

#### Mission line

| Mission | Working title | Campaign role | Primary form | Task unit |
| --- | --- | --- | --- | --- |
| M10 | Pursuit opener | Locate retreat corridors, caches, and first interior logistics hubs | Wide-area sweep | 1-7 CAV (reinforced) |
| M11 | Eagle Eye | Aviation reconnaissance over interior approach corridors to locate retreat routes, camp activity, and convoy patterns | Aerial reconnaissance / ISR mission | 7-17 CAV-equivalent detachment (attack reconnaissance) or 2-227 AVN-equivalent detachment (aerial observation) |
| M12 | Camp strike | Raid or air assault a rural complex tied to WMD transit | Air assault or raid | 1-7 CAV (reinforced) |
| M13 | Pathfinder | Deep reconnaissance sweep across a second interior sector, hunting for WMD transit indicators and sanctuary approach routes | Deep reconnaissance sweep | Aviation / ISR element |
| M14 | Interdiction strike | Hit a convoy, depot, or crossing point moving Umar support personnel | Interdiction attack | 1-7 CAV (reinforced) |
| M15 | Iron Road | Armored route clearance and security along interior supply lines, securing the logistics backbone for exploitation missions | Route reconnaissance and security | 2-12 ARS-equivalent screen or armor element |
| M16 | WMD recovery | Secure a hardened site containing stockpiles, precursors, or technical records | Deliberate objective seizure | 1-7 CAV (reinforced) |
| M17 | Anvil | Armored engagement against the enemy's captured heavy-weapons group, destroying the last conventional threat before the sanctuary assault | Armored meeting engagement | Armor / mechanized element |
| M18 | Final encirclement | Encircle and assault Umar's sanctuary or border stronghold | Multi-axis final assault | 1-7 CAV (reinforced) |

#### Tasks by major element

| Element | Phase IV tasks |
| --- | --- |
| Joint Task Force Juniper HQ | Retask campaign priority toward sanctuary reduction and WMD-site exploitation |
| Task Force Iron Vanguard HQ | Maintain pressure across multiple lanes without losing the main effort |
| 1-7 CAV (reinforced) | Execute the decisive sweep, raid, seizure, and final assault actions |
| Air assault company attachment | Conduct vertical envelopment, pursuit blocks, and retreat denial |
| Ranger platoon attachment | Support sensitive-site exploitation and sanctuary breach shaping |
| 2-12 ARS-equivalent screen | Fix or track retreating packets and identify breakout attempts |
| 115 BSB-equivalent support node | Sustain distributed operations across long lines and support contamination-control requirements |
| 2-227 AVN-equivalent detachment | CASEVAC, resupply, raid support, and rapid repositioning |
| 7-17 CAV-equivalent detachment | Armed reconnaissance, convoy disruption, and overwatch during final isolation |
| Border guard regiment and regional forces | Support frontier containment and deny external reinforcement or escape |

---

### Phase V - Stability

#### Operational concept

After the destruction of Umar's sanctuary network, campaign activity shifts to securing recovered sites, processing detainees and evidence, transferring terrain to partner control, and preserving freedom of action against residual cells.

#### Forces required by function or capability

- Site security and exploitation
- Detainee handling and consequence management
- Route security and fixed-site handoff
- Civil affairs, information, and legitimacy support

#### Tasks by major element

| Element | Phase V tasks |
| --- | --- |
| Joint Task Force Juniper HQ | Direct transition priorities, theater messaging, and follow-on security framework |
| Task Force Iron Vanguard HQ | Consolidate gains, support handoff, and maintain reserve combat power against spoilers |
| 1-7 CAV (reinforced) | Secure decisive sites until host-nation forces can assume control |
| 115 BSB-equivalent support node | Support site exploitation, sustainment, recovery, and medical operations |
| Host-nation security forces | Assume control of cleared compounds, districts, depots, and detainee sites |
| Urban police / gendarmerie | Re-establish civil control and checkpoint presence |
| Local intelligence bureau | Exploit captured media and detainees into residual-network targeting |
| Regional stabilization mission | Secure relief corridors and reinforce legitimacy in sensitive zones |

### Secondary mission design concept

The campaign follows a dual-track mission structure drawn from the original OJS schedule. Even-numbered missions (M2, M4, M6, M8, M10, M12, M14, M16, M18) are **primary missions** run by the main maneuver force at platoon or company scale. Odd-numbered missions (M1, M3, M5, M7, M11, M13, M15, M17) are **secondary missions** designed for HQ and specialized task-force elements.

#### Secondary mission characteristics

- **Smaller scale:** section to platoon playable force
- **Specialized task units:** Ranger platoon, aviation detachment, armor/reconnaissance screen, medical section, support elements, or HQ staff
- **Condition-setting role:** each secondary mission shapes the next primary mission by providing reconnaissance, security, sustainment, planning, or civil engagement
- **Shorter duration:** designed for focused one- to two-hour sessions
- **Canon contribution:** secondary mission outcomes feed the campaign continuity workflow and may upgrade or degrade conditions for the following primary mission

#### Secondary mission sequencing

Secondary missions run between primary missions in campaign chronology. Each secondary mission sits immediately before the primary mission it supports:

- M1 → shapes M2 (Ranger recon feeds the coastal raid)
- M3 → shapes M4 (checkpoint intelligence feeds the personnel recovery)
- M5 → shapes M6 (civil engagement and medical intel feeds the breakthrough plan)
- M7 → shapes M8 (exploitation planning feeds the cordon-and-assault)
- M11 → shapes M12 (aerial recon feeds the camp strike)
- M13 → shapes M14 (deep recon feeds the interdiction strike)
- M15 → shapes M16 (route security feeds the WMD-site seizure)
- M17 → shapes M18 (armor engagement clears the way for the final assault)

A secondary mission that fails or is skipped should degrade conditions for the next primary mission (harder start, less intelligence, degraded support) rather than block the campaign sequence.

### Information and civil effects guidance

- Undermine enemy freedom of movement and confidence in sanctuary.
- Increase civilian willingness to avoid, report, or abandon enemy-controlled nodes.
- Counter enemy intimidation, propaganda, and coercion.
- Preserve the legitimacy of friendly and partner operations by minimizing unnecessary destruction and maintaining disciplined site control.

### Coordinating instructions

- Every mission must reinforce the coast-city-interior-sanctuary campaign spine.
- Mission outcomes should alter conditions, not replace the sequence.
- Use fail-forward logic instead of hard resets wherever possible.
- Recovered documents, detainees, media, and site evidence should feed the campaign continuity workflow.
- The next mission handoff must state what was confirmed, what remains unresolved, and which route, site, or person becomes the next focal point.

## 7. Sustainment

- Sustainment should remain mobile, expeditionary, and visibly constrained.
- CASEVAC planning is mandatory in littoral and interior operations.
- WMD-linked objectives require contamination-control, isolation, and controlled exploitation procedures.
- Distribution, vehicle recovery, and casualty support must keep pace with dispersed maneuver rather than rely on static rear-area abundance.

## 8. Command and signal

- Campaign command remains battalion-led in the playable space with higher headquarters shaping the wider theater.
- Command posts, logistics hubs, aviation support zones, and holding areas should shift as operations move inland.
- Debriefs, OPSUMs, AARs, and handoff products should use repository templates so campaign canon stays traceable across sessions.

## Planning end state for this draft

This campaign plan is intended to serve as the campaign-level planning baseline that sits above individual OPORDs and below the broader adaptation guidance. It should be used as the narrative and operational template for future mission briefs, continuity updates, and campaign-state decisions.
- preserves mission tempo and intent without ad hoc controller escalation
- reduces manual rewrite work for AARs and follow-on orders
- keeps canon traceable to reviewed source packets
- allows staff turnover without losing campaign continuity
- supports mixed PC and console participation without changing the core workflow

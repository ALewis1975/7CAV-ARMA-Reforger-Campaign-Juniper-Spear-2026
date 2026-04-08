# 7CAV ARMA Reforger Campaign Juniper Spear 2026

This repository is the planning and documentation workspace for a modern **ARMA Reforger** adaptation of **Operation Juniper Spear**.

The project is currently focused on turning the original campaign into a **Reforger-first, combined-arms campaign framework** rather than doing a literal one-to-one recreation of Mogadishu.

## What this repo currently contains

This is a **documentation-first repository**. It currently holds campaign design drafts, workflow guidance, templates, and preserved original source material.

It does **not** currently contain a finished playable campaign release in this repository root.

## What players should expect

The current campaign direction keeps the original Juniper Spear arc while adapting it for a fictional Horn-of-Africa-inspired theater built around:

- coastal raids and lodgment operations
- helicopter insertion, extraction, and CASEVAC
- urban cordon-and-assault fighting
- mechanized and mounted maneuver
- inland pursuit, interdiction, and final sanctuary reduction

The intended campaign flow is:

1. seize the littoral foothold
2. break the enemy's urban network
3. pursue the force inland
4. secure WMD-related sites
5. finish with a final HVT encirclement

## Mission plan

The current mission plan is summarized below from the [campaign plan draft](docs/campaign-plan-draft.md).

### Phase III - Initial Conduct

| Mission | Working title | Campaign role |
| --- | --- | --- |
| M1 | Tripwire | Ranger recon and HUMINT along the littoral to map the smuggling network before the main raid |
| M2 | Dealbreaker | Raid a coastal facilitator node and recover manifests, radios, and route intelligence |
| M3 | Stranglehold | Establish checkpoints and observation posts to control population movement and screen displaced persons |
| M4 | Deliverance | Recover isolated personnel and preserve momentum on the urban fringe |
| M5 | Open Hands | Medical outreach in a civilian area affected by the fighting, collecting local intelligence while providing care |
| M6 | Thunder and Lightning | Seize a military complex and route junction to break the urban defensive belt |
| M7 | Iron Council | HQ staff exercise and wargame for the inland exploitation phase, synthesizing M1-M6 intelligence |
| M8 | Window Shopping | Cordon and clear a market or industrial district and confirm inland escape |

### Phase IV - Exploitation

| Mission | Working title | Campaign role |
| --- | --- | --- |
| M10 | Pursuit opener | Locate retreat corridors, caches, and first interior logistics hubs |
| M11 | Eagle Eye | Aviation reconnaissance over interior approach corridors to locate retreat routes, camp activity, and convoy patterns |
| M12 | Camp strike | Raid or air assault a rural complex tied to WMD transit |
| M13 | Pathfinder | Deep reconnaissance sweep across a second interior sector, hunting for WMD transit indicators and sanctuary approach routes |
| M14 | Interdiction strike | Hit a convoy, depot, or crossing point moving Umar support personnel |
| M15 | Iron Road | Armored route clearance and security along interior supply lines, securing the logistics backbone for exploitation missions |
| M16 | WMD recovery | Secure a hardened site containing stockpiles, precursors, or technical records |
| M17 | Anvil | Armored engagement against the enemy's captured heavy-weapons group, destroying the last conventional threat before the sanctuary assault |
| M18 | Final encirclement | Encircle and assault Umar's sanctuary or border stronghold |

Odd-numbered missions are secondary shaping missions and even-numbered missions are primary main-effort missions. See [`docs/campaign-plan-draft.md`](docs/campaign-plan-draft.md) for the full phase structure, task-unit breakdown, and sequencing details.

## What developers, mission makers, and staff should read first

- [Reforger-first adaptation guide](docs/reforger-first-adaptation.md) - overall campaign direction, design pillars, and mission-line adaptation
- [Campaign plan draft](docs/campaign-plan-draft.md) - campaign-level plan built from the original OJS campaign-plan structure and current Juniper Spear 2026 lore
- [Campaign WARNO draft](docs/campaign-warno-draft.md) - campaign-level operational framing and phase structure
- [Campaign ORBAT draft](docs/campaign-orbat-draft.md) - friendly, partner, and hostile force structure
- [AI after-action workflow](docs/ai-after-action-workflow.md) - recommended campaign reporting and canon-update workflow
- [Campaign state and event reference](docs/campaign-state-and-events.md) - minimum ledger schema, event vocabulary, and M2 continuity-loop standard
- [Staff role playbooks](docs/staff-role-playbooks.md) - lightweight billet definitions and handoff checklists for campaign execution

## Repository layout

### Current adaptation workspace

The active design material lives under [`docs/`](docs/):

- [`docs/reforger-first-adaptation.md`](docs/reforger-first-adaptation.md)
- [`docs/campaign-plan-draft.md`](docs/campaign-plan-draft.md)
- [`docs/campaign-warno-draft.md`](docs/campaign-warno-draft.md)
- [`docs/campaign-orbat-draft.md`](docs/campaign-orbat-draft.md)
- [`docs/ai-after-action-workflow.md`](docs/ai-after-action-workflow.md)
- [`docs/campaign-state-and-events.md`](docs/campaign-state-and-events.md)
- [`docs/staff-role-playbooks.md`](docs/staff-role-playbooks.md)

Templates for campaign planning and reporting live under [`docs/templates/`](docs/templates/):

- [`docs/templates/mission-intake-template.md`](docs/templates/mission-intake-template.md)
- [`docs/templates/controller-packet-template.md`](docs/templates/controller-packet-template.md)
- [`docs/templates/controller-pace-card-template.md`](docs/templates/controller-pace-card-template.md)
- [`docs/templates/forum-aar-template.md`](docs/templates/forum-aar-template.md)
- [`docs/templates/campaign-fact-sheet-template.md`](docs/templates/campaign-fact-sheet-template.md)
- [`docs/templates/opsum-template.md`](docs/templates/opsum-template.md)
- [`docs/templates/intel-annex-template.md`](docs/templates/intel-annex-template.md)
- [`docs/templates/next-mission-handoff-template.md`](docs/templates/next-mission-handoff-template.md)
- [`docs/templates/mission-briefing-slides-template.md`](docs/templates/mission-briefing-slides-template.md)
- [`docs/templates/campaign-ledger-template.json`](docs/templates/campaign-ledger-template.json)

### 7CAV working documents

[`7CAV Docs/`](7CAV%20Docs) is available for 7CAV-specific working documents and supporting reference material that should remain separate from the core adaptation guidance in `docs/`.

That directory also holds a sample 7CAV OPORD PDF that can be used as a reference when building Google Slides mission briefings and PDF briefing exports.

### Original source archive

[`OJS Original Documents/`](OJS%20Original%20Documents) preserves the original Juniper Spear campaign material, including draft planning documents, phase documents, reports, overlays, and reference products that the adaptation is based on.

## Recommended use

### If you are a player

- use this repository to understand the campaign's intended setting and structure
- expect the current material to be planning documentation, not a finished mission pack
- read the adaptation guide if you want the big-picture direction

### If you are building or running the campaign

- use the adaptation guide, WARNO, and ORBAT as the current design baseline
- use the campaign process plan and staff role playbooks to assign billets, keep tempo discipline, and preserve continuity between events
- use the templates in `docs/templates/` to standardize planning, controller packets, BBCode forum outputs, PDF-ready staff products, and Google Slides briefing products
- use the AI workflow document only as a drafting and staff-support process, not as an automatic canon authority
- preserve traceability back to source documents when locking campaign decisions

## Project status

Current repository status:

- campaign setting reframed into the fictional **Hadir Littoral** and **Daryan Interior**
- original campaign-plan structure now adapted into a current Reforger-first draft campaign plan
- mission line mapped from the original source into a Reforger-first campaign structure
- reporting and continuity templates prepared for campaign operations
- campaign state schema and event vocabulary locked for the first continuity loop
- original OJS material preserved for reference

## License

This repository is distributed under the terms of the [GNU General Public License v3.0](LICENSE).

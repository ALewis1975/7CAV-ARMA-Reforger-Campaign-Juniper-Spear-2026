# Campaign state and event reference

## Purpose

This document locks the minimum campaign-state shape and event vocabulary for the Reforger-native Juniper Spear continuity loop.

It exists so mission makers, campaign staff, and any later automation all mutate the same campaign truth model instead of inventing incompatible formats.

## Design rules

1. Keep the campaign ledger as the canonical source of approved state.
2. Treat mission logs and state deltas as proposals until reviewed.
3. Separate observed events from assessed conclusions.
4. Require human review for canon changes that alter named actors, civilian impact, WMD findings, or the next mission baseline.
5. Favor a small stable vocabulary over a large speculative schema.

## Minimum canonical state

The campaign ledger should always preserve these domains:

- campaign metadata
- current phase and active mission focus
- friendly readiness and sustainment
- enemy-network posture
- intelligence confirmed and intelligence pending exploitation
- civilian impact and political friction
- named actors
- mission history
- pending review items

### Reference shape

The reference shape below shows a pre-approval M2 baseline.

```json
{
  "campaign": {
    "name": "Campaign Juniper Spear 2026",
    "version": 1,
    "phase": "I",
    "currentMissionId": "M2",
    "lastApprovedMission": null,
    "lastUpdated": "YYYY-MM-DDTHH:MM:SSZ"
  },
  "friendly": {
    "personnelReady": 34,
    "criticalCasualties": 2,
    "vehiclesOperational": ["RHIB-1", "MRZR-2"],
    "vehiclesDamaged": [],
    "sustainment": "green",
    "notes": []
  },
  "enemyNetwork": {
    "coastalCellIntegrity": 0.55,
    "urbanCellIntegrity": 0.8,
    "interiorCellIntegrity": 1.0,
    "alertLevel": "elevated",
    "knownRoutes": ["Jetty-3", "North Causeway"],
    "notes": []
  },
  "intel": {
    "confirmed": ["Broker linked to Umar", "Manifest fragment recovered"],
    "leads": ["Warehouse near airfield", "Call sign NEMESIS"],
    "evidenceRecovered": [
      {
        "type": "document",
        "summary": "",
        "sourceMissionId": "M2",
        "confidence": "high"
      }
    ]
  },
  "civil": {
    "collateralIncidents": 1,
    "localCooperation": "uncertain",
    "roeConcerns": []
  },
  "namedActors": {
    "AhmadUmar": {
      "status": "at_large",
      "lastKnownRegion": "urban fringe",
      "confidence": "medium",
      "notes": []
    }
  },
  "missionHistory": [],
  "pendingReview": {
    "stateDeltas": [],
    "disputedFacts": []
  }
}
```

## Mission event vocabulary

Mission logs should use a controlled vocabulary so later reporting stays consistent.

| Event type | Use when | Typical payload |
| --- | --- | --- |
| `mission.started` | The scenario officially begins | mission ID, start time, commander |
| `insertion.completed` | Main force reaches the intended start point | method, location, time |
| `objective.updated` | An objective changes state | objective name, new status, notes |
| `contact.major` | A major engagement materially changes the mission | location, enemy type, outcome |
| `casualty.recorded` | Friendly, hostile, or civilian casualties must be logged | side, count, severity, location |
| `vehicle.status.changed` | A mission-critical vehicle is damaged, disabled, recovered, or lost | vehicle ID, status, cause |
| `detainee.captured` | A detainee or POW enters campaign handling | identity, affiliation, location |
| `evidence.recovered` | Documents, electronics, media, or technical material are seized | type, summary, confidence |
| `site.exploited` | A compound, crash site, cache, or WMD-linked site is exploited | location, findings, follow-on need |
| `roe.incident` | ROE, civilian harm, or media-sensitive events occur | category, description, review flag |
| `gm.inject` | Staff or controller notes need to become part of the record | note text, source, time |
| `exfil.completed` | Main force completes extraction | method, location, time |
| `mission.ended` | The scenario officially ends | result, end time, summary |

## Review gates

These changes should always require explicit approval before becoming canon:

- named actor captured, killed, confirmed present, or confirmed absent
- discovery, recovery, or destruction of WMD-related material
- civilian casualty or collateral-damage updates
- mission failure or partial success that changes the next mission's assumptions
- force-availability changes that remove major friendly assets

These changes can usually be drafted automatically and then reviewed as part of normal approval:

- objective completion status
- ordinary casualty totals
- vehicle damage and recovery
- recovered documents, radios, and route indicators
- timeline reconstruction

## M2 vertical-slice standard

The first vertical slice should prove the complete continuity loop for **M2 - Dealbreaker**.

At minimum, M2 should demonstrate:

- one approved mission brief generated from current campaign state
- one mission log using the locked event vocabulary
- one proposed state delta tied to the mission result
- one drafted AAR or OPSUM package
- one drafted next-mission FRAGO or handoff
- one human approval step that updates canon for M4

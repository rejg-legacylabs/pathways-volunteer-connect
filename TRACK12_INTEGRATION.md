# Track 12 Integration — Pathways VolunteerConnect

## Overview

All volunteers must complete **Track 12: Volunteer Orientation** in Pathways Hub OS before being cleared to interact with HOH Foundation residents.

Track 12 is built in Pathways Hub OS (also owned by REJG Legacy Labs LLC).

## Track 12 Curriculum (7 Classes)

| Class | Title |
|---|---|
| 12.01 | Welcome to HOH — Mission, Population, and Your Role |
| 12.02 | Trauma-Informed Volunteering |
| 12.03 | Confidentiality, HIPAA Basics, and Resident Privacy |
| 12.04 | Boundaries, Conduct, and Professional Expectations |
| 12.05 | Safety Protocols and Incident Reporting |
| 12.06 | Your Service Area — Mentor, Driver, Trades, Meals |
| 12.07 | Volunteer Certification Complete — What's Next |

## Scheduling Gate Logic

A volunteer record must meet ALL three conditions before they can be assigned to a shift:

```javascript
const canSchedule = (
  volunteer.background_check_status === 'cleared' &&
  volunteer.track12_completed === true &&
  volunteer.waiver_signed === true
);
```

If any condition is false, the volunteer portal shows a prominent banner explaining what is needed.

## Status Tracking

The `track12_completed` field on the Volunteer entity:
- Default: `false`
- Set to `true` by HOH coordinator after confirming completion
- Future: API integration with Pathways Hub OS LMS for automatic sync

## Volunteer Portal Flow

```
Volunteer submits intake form
        ↓
Account created (status: pending)
        ↓
Complete waiver (waiver_signed: true)
        ↓
Background check submitted (status: pending → cleared)
        ↓
Complete Track 12 in Pathways Hub OS (track12_completed: true)
        ↓
Coordinator activates volunteer (status: active)
        ↓
Volunteer can be scheduled for shifts ✅
```

## Pathways Hub OS Connection

- Platform: Pathways Hub OS (REJG Legacy Labs)
- Track 12 hosted in Pathways Hub OS learning environment
- Volunteers access via link in VolunteerConnect dashboard
- Completion confirmed manually by HOH coordinator (v1) or via API (future)
- Canva folder: `Track 12 — Volunteer Orientation` (FAHKclNX3Yc)

# Pathways VolunteerConnect

**IP Owner:** REJG Legacy Labs LLC 
**Licensed to:** Headquarters of Hope Foundation (Intercompany MSA) 
**Base44 App ID:** `6a1117ff13888870642b4227` 
**Base44 Editor:** https://app.base44.com/apps/6a1117ff13888870642b4227/editor/preview 
**GitHub:** github.com/rejg-legacylabs/pathways-volunteer-connect

---

## Overview

Pathways VolunteerConnect is a multi-tenant volunteer management platform built and owned by **REJG Legacy Labs LLC**. It is licensed to Headquarters of Hope Foundation and partner nonprofits for volunteer recruitment, onboarding, scheduling, and management.

This platform is part of the **Pathways Hub OS ecosystem** — the IP portfolio of REJG Legacy Labs LLC.

---

## License Structure

```
REJG Legacy Labs LLC  (Owner / Developer)
        │
        │  Intercompany Software License (MSA)
        ▼
Headquarters of Hope Foundation  (Primary Licensee)
        │
        │  Network Agreement
        ▼
Partner Nonprofits  (Sub-Users)
SAFE Alliance · CommUnity Care · LifeWorks · Austin Recovery Network · etc.
```

| Asset | Owner |
|---|---|
| Source code | REJG Legacy Labs LLC |
| Database schema and entities | REJG Legacy Labs LLC |
| Brand: Pathways VolunteerConnect | REJG Legacy Labs LLC |
| Platform design and UX | REJG Legacy Labs LLC |

---

## Architecture

**Three Roles:**
- `admin` — HOH Foundation super admin (full platform access, all orgs, all volunteers)
- `org_admin` — Partner nonprofit coordinators (own roster + shared pool view)
- `volunteer` — Individual volunteer portal (profile, hours, schedule, certs)

**Multi-Tenant Shared Pool:** Volunteers register once and can serve multiple organizations. Partner nonprofits plug in and access the shared pool while managing their own rosters.

---

## Key Features

- Public volunteer intake form and landing page
- Background check status tracking (clears/blocks scheduling)
- Track 12 completion tracking (Pathways Hub OS Volunteer Orientation — 7 classes)
- Shared volunteer pool across all partner organizations
- Volunteer-to-opportunity skills matching
- Shift scheduling and attendance tracking
- Hours logging and approval workflow
- Milestone badges: 25 / 50 / 100 / 250 / 500 hours
- Org coordinator dashboards per entity
- Platform-wide master admin analytics dashboard
- Document storage: waivers, background check auth, ID uploads
- Announcements and communications per org or platform-wide

---

## Scheduling Gates

A volunteer **cannot** be assigned to a shift until ALL three are true:

```
background_check_status = "cleared"
track12_completed = true
waiver_signed = true
```

---

## Track 12 Integration

All volunteers must complete **Track 12: Volunteer Orientation** (7 classes) in Pathways Hub OS before being cleared for resident interaction. See `TRACK12_INTEGRATION.md` for full details.

---

## Revenue Model (REJG Legacy Labs)

Pathways VolunteerConnect is SaaS-licensable to Texas transitional housing and reentry nonprofits as part of the Pathways Hub OS ecosystem.

- **HOH Foundation:** Internal use (covered under MSA)
- **External nonprofits:** Monthly SaaS licensing fee
- **White-label:** Available for large networks

---

## HIPAA and Compliance

- Volunteers do **NOT** have access to resident records
- Background check data is status-only — no raw sensitive data stored
- PII restricted to secured entities only
- Volunteer waivers stored in Document entity
- HIPAA separation maintained between volunteer and resident data layers

---

## Contact

| Entity | Role | Email | Phone |
|---|---|---|---|
| REJG Legacy Labs | IP Owner / Developer | contact@rejglegacylabs.com | — |
| HOH Foundation | Primary Licensee | info@headquartersofhope.org | 737-255-8355 |
| RE Jones Global | Parent Company | info@rejonesglobal.com | 737-999-0256 |

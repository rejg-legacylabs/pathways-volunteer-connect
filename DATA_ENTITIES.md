# Data Entities — Pathways VolunteerConnect

## Entity Overview

All entities are stored in the Base44 backend (App ID: `6a1117ff13888870642b4227`).

---

## 1. Organization

| Field | Type | Notes |
|---|---|---|
| name | string | Org display name |
| type | enum | nonprofit, faith, gov |
| address, city, state | string | Location |
| phone, email, website | string | Contact info |
| status | enum | active, pending, inactive |
| HOH_partner | boolean | Is part of HOH network |
| contact_person | string | Primary coordinator name |
| contact_email | string | Coordinator email |
| approved_at | date | When HOH approved org |
| description | text | Org mission/description |
| volunteer_count | number | Auto-calculated |

## 2. Volunteer

| Field | Type | Notes |
|---|---|---|
| first_name, last_name | string | |
| email, phone | string | |
| address, city, zip | string | |
| status | enum | pending, active, inactive, suspended |
| background_check_status | enum | not_submitted, pending, cleared, failed |
| background_check_date | date | When cleared |
| skills | array | mentor, driver, trades_plumber, trades_electrician, trades_carpenter, meal_provider, admin, counselor, legal, medical, other |
| availability | array | weekday_mornings, weekday_afternoons, weekday_evenings, weekends |
| languages | array | Languages spoken |
| emergency_contact_name | string | |
| emergency_contact_phone | string | |
| shirt_size | string | For volunteer gear |
| bio | text | About the volunteer |
| total_hours | number | Lifetime hours |
| milestone_badge | enum | none, 25hrs, 50hrs, 100hrs, 250hrs, 500hrs |
| waiver_signed | boolean | |
| waiver_date | date | |
| track12_completed | boolean | Pathways Hub OS Track 12 |
| track12_date | date | |
| notes | text | Internal coordinator notes |

## 3. VolunteerOrgLink

| Field | Type | Notes |
|---|---|---|
| volunteer_id | string | Reference to Volunteer |
| org_id | string | Reference to Organization |
| status | enum | active, inactive |
| joined_date | date | |
| role_at_org | string | Their specific role |
| approved_by | string | Coordinator who approved |
| hours_with_org | number | Hours logged with this org |

## 4. Opportunity

| Field | Type | Notes |
|---|---|---|
| title | string | Opportunity name |
| org_id, org_name | string | Which org posted |
| description | text | Details |
| skills_needed | array | Required skills |
| date_needed | date | |
| start_time, end_time | time | |
| location | string | |
| volunteers_needed | number | Target count |
| volunteers_confirmed | number | Confirmed count |
| status | enum | open, filled, cancelled, completed |
| created_by | string | Coordinator |

## 5. Shift

| Field | Type | Notes |
|---|---|---|
| volunteer_id, volunteer_name | string | |
| opportunity_id | string | |
| org_id, org_name | string | |
| date | date | |
| start_time, end_time | time | |
| status | enum | scheduled, completed, no_show, cancelled |
| hours_logged | number | |
| approved | boolean | |
| approved_by | string | |
| notes | text | |

## 6. HoursLog

| Field | Type | Notes |
|---|---|---|
| volunteer_id, volunteer_name | string | |
| org_id, org_name | string | |
| date | date | |
| hours | number | |
| activity_description | text | |
| status | enum | pending, approved, rejected |
| submitted_at | datetime | |
| reviewed_by | string | |
| notes | text | |

## 7. Document

| Field | Type | Notes |
|---|---|---|
| volunteer_id | string | |
| type | enum | waiver, background_check, id, other |
| filename | string | |
| uploaded_at | datetime | |
| status | enum | pending, approved, rejected |

## 8. Announcement

| Field | Type | Notes |
|---|---|---|
| org_id | string | null = platform-wide |
| title | string | |
| message | text | |
| priority | enum | normal, urgent |
| created_by | string | |
| expires_at | date | |

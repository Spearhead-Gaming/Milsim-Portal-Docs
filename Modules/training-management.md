# 🎓 User Training Management – Feature Specification

This module tracks individual member progress toward required trainings, allows leadership to manage qualifications, and provides automated feedback when training milestones are completed.

---

## ✅ Core Features

### 1. Admin-Defined Training Criteria
- Admins create and manage training requirements:
  - `Title`
  - `Description`
  - `Training Type` (Core / Optional / Unit-specific)
  - `Required for`: Rank, Unit, or Role
  - `Visible to`: Public, Leadership-only
- Attachments allowed: Briefing documents, SOPs, etc.

---

### 2. User Progress Tracking
- Users can view their:
  - Completed Trainings
  - Pending / Incomplete Requirements
  - Progress toward unit/rank-specific training goals
- Optional: Show percentage completed

---

### 3. Training Completion
- Trainings can be marked as complete by:
  - Admins
  - Squad Leads (for team members only)
  - Automatically (via event attendance sync)
- Metadata stored:
  - `Completed By` (instructor or auto)
  - `Date Completed`
  - `Notes` (optional remarks)

---

### 4. Achievements & Notifications
- Auto-notify user via:
  - Web dashboard banner
  - Discord DM (optional)
- Notify Squad Leads of training milestones
- Optional: Create digital certificate or badge (visual award)

---

### 5. Role-Based Access Control (RBAC)

| Role           | Permissions                                             |
|----------------|---------------------------------------------------------|
| Admin          | Create/manage training criteria, mark completion for anyone |
| CO/XO          | Full access to unit-wide training status                |
| Squad Lead     | Can mark training complete for their squad              |
| Team Lead      | View team training status                               |
| Regular User   | View personal training progress only                    |

---

### 6. Filtering & Reporting
- View training by:
  - Individual
  - Unit
  - Training type (core, advanced, etc.)
- Generate reports:
  - Who is missing required training?
  - Which trainings are most/least completed?
- Export to CSV or PDF

---

### 7. Integration with Events
- Events can optionally fulfill trainings:
  - Admin tags event with `Fulfills: [Training Name]`
  - After event, attendees are auto-marked as completed
- Manual override allowed for edge cases

---

### 8. Edge Cases & Policy Rules
- [ ] Allow re-certification (repeat training after expiration?)
- [ ] Show expired or outdated trainings
- [ ] Versioning of training (v1, v2 — preserve history)
- [ ] Prevent self-certification (unless explicitly allowed)

---

### 9. Future Enhancements
- In-portal quizzes or training modules
- Auto-promote rank on training completion
- Link with Discord roles to unlock channels
- Export training history to certificate-style PDF

---

## 📌 Status
Planning phase ✅  
Next step: Define training schema, event-training linking logic, and instructor workflows.
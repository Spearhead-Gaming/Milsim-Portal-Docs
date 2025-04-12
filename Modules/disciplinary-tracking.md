# ⚖️ Member Disciplinary Tracking – Feature Specification

This module provides a centralized, transparent system for logging, reviewing, and managing disciplinary actions within the community. It promotes accountability and ensures consistent enforcement of community standards.

---

## ✅ Core Features

### 1. Incident Logging
- Admins and designated leadership can file disciplinary entries with:
  - `User Involved`
  - `Date of Incident`
  - `Reported By`
  - `Summary of Incident`
  - `Action Taken` (Warning, Probation, Removal, etc.)
  - `Evidence` (optional file upload or link)
- Optional fields:
  - Tags (e.g., "Attendance", "Behavior", "Insubordination")

---

### 2. Review & Escalation
- Incidents can be flagged for review by higher leadership
- CO/XO may:
  - Escalate to full board
  - Overturn/revise the logged action
  - Assign further action (e.g., mandatory retraining)
- Visibility rules enforced per rank (see RBAC below)

---

### 3. User Visibility
- Users can view their own disciplinary history only
- Display includes:
  - Total incidents
  - Most recent incident
  - Actions taken
  - Current disciplinary status (e.g., Probation)

---

### 4. Admin & Leadership Dashboards
- Filter incidents by:
  - Date range
  - Type of action
  - Unit or reporting leader
  - Severity or tags
- View charts/stats on disciplinary trends
- Export filtered incident logs (CSV/PDF)

---

### 5. Notifications & Logging
- Notify:
  - CO/XO when an incident is filed
  - Reporting party when incident is reviewed or closed
- Log actions in Discord admin log channel
- DM to user when a disciplinary action is added (optional toggle)

---

### 6. Role-Based Access Control (RBAC)

| Role           | Permissions                                               |
|----------------|-----------------------------------------------------------|
| Admin          | Full access to all logs, actions, and stats               |
| CO/XO          | View all reports, overturn decisions, assign actions      |
| Squad Lead     | File reports on team members, view team infractions       |
| Team Lead      | View team member discipline summaries (no detail)         |
| Regular User   | View own record only                                      |

---

### 7. Edge Cases & Rules
- [ ] Limit incident editing to Admins only
- [ ] Show if an incident is related to a failed RSVP/attendance threshold
- [ ] Multi-user incidents (e.g., group behavior violations)
- [ ] Clear indication if an incident has been appealed or overturned

---

### 8. Future Enhancements
- Appeals process (user-requested re-evaluation)
- Automatic flags:
  - 3+ missed events without LOA
  - Abnormal behavior detected (chat flags, Discord data)
- Probation system:
  - Track if user is under watch
  - Require acknowledgment or retraining

---

## 📌 Status
Planning phase ✅  
Next step: Design incident schema, role-based view logic, and Discord logging integration.
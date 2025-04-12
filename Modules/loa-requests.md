# 📝 Leave of Absence (LOA) Requests – Feature Specification

This module manages Leave of Absence requests submitted by community members. It automates approval workflows, tracks LOA history, and integrates with Discord to manage user roles and visibility within the unit.

---

## ✅ Core Features

### 1. LOA Request Submission
- Users can submit LOA requests through the portal.
- Required fields:
  - `Start Date`
  - `End Date`
  - `Reason for Leave`
- Optional: Allow future editing or cancellation before approval.

---

### 2. LOA Approval Workflow
- Admins, Squad Leads, or designated leadership can:
  - Approve
  - Reject
  - Request more information
- Upon approval:
  - User status updated to **On Leave**
  - Discord roles are automatically updated
- Upon rejection:
  - User notified with rejection reason

---

### 3. Role & Status Management
- On LOA Approval:
  - Replace "Active" role with "On Leave" on Discord
  - Prevent RSVP to events (optional)
  - Mark user as unavailable in dashboards
- On LOA End:
  - Auto-switch roles back (via cron job or manual trigger)
  - Notify user that they’ve returned to Active status

---

### 4. History & Tracking
- Each user has a LOA history record:
  - Past LOAs (dates, reasons, approval status)
  - Status changes (Active → LOA → Active)
- Admins can view LOA status on user profile
- Display LOA info in leadership dashboards

---

### 5. Notifications & Discord Integration
- DM sent to user when LOA is approved or rejected
- Leadership channel notifications for new LOA requests
- Auto-log actions (approved/rejected LOAs) in admin log channel

---

### 6. Role-Based Access Control (RBAC)

| Role           | Permissions                                               |
|----------------|-----------------------------------------------------------|
| Admin          | Full control over all LOA requests                        |
| CO/XO          | Approve/reject any LOA request, update status manually    |
| Squad Lead     | Approve LOAs for their squad only                         |
| Team Lead      | View LOA status of team members                           |
| Regular User   | Submit LOA, view personal history                         |

---

### 7. Edge Cases & Rules
- [ ] Prevent overlapping LOA dates
- [ ] Minimum and maximum LOA duration enforcement
- [ ] Auto-extension logic if user hasn’t returned?
- [ ] Notify squad lead if LOA is nearing expiration
- [ ] LOA overrides RSVP or attendance penalties

---

### 8. Future Enhancements
- Auto-reminders to user 24h before return date
- Flag long-term LOA users for leadership review
- Track LOA reasons by category for analytics
- In-app calendar to display who is on LOA

---

## 📌 Status
Planning phase ✅  
Next step: Finalize LOA schema, approval routing logic, and Discord role automation.
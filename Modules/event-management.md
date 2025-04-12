# 📅 Event Management & Attendance Tracking – Feature Specification

This module is responsible for scheduling, announcing, and tracking attendance for events in the Arma 3 Milsim Community Portal. It supports both in-app RSVP handling and full Discord integration for community engagement and automation.

---

## ✅ Core Features

### 1. Event Creation & Editing
- Create events with the following fields:
  - `Title`
  - `Description` (optional Markdown support)
  - `Start / End Time` (stored in UTC, displayed in local time)
  - `Associated Deployment`
  - `Event Type`: `Training`, `Operation`, `Meeting`, `Other`
  - `Max Participants` (optional)
  - `Visibility`: Public, Unit-only, Leadership-only
  - Toggle for:
    - Discord Announcement
    - Discord Scheduled Event Creation

**Future Enhancements:**
- Required Training to Attend
- File Attachments (briefing docs, etc.)

---

### 2. RSVP System
- RSVP options: ✅ Attending, 🟡 Maybe, ❌ Not Attending
- RSVP allowed up until event start time
- Users can change RSVP before start
- RSVP updates reflected in real-time (WebSocket support)

**Automation:**
- Discord button responses sync with portal DB
- RSVP auto-triggers “Interested” on Discord scheduled events
- Confirmation DM sent on RSVP

---

### 3. Attendance & Check-In
- Admins can mark users as:
  - `Attended`
  - `No-show`
  - `Excused`
- Tracks:
  - RSVP’d but did not attend
  - Attended but did not RSVP
- Optional attendance notes (late, excused, etc.)
- (Planned) QR code or Discord command-based live check-in

---

### 4. Attendance Dashboard & Summary
- Dashboard filters:
  - Deployment
  - Event Type
  - Date Range
  - Unit/User
- RSVP stats per event
- Export attendance to CSV/XLS
- Attendance trends over time
- Absentee reports for leaders

---

### 5. Reminders & Notifications
- Automated DMs for RSVP’d users:
  - 24 hours before
  - 1 hour before
- Notify Squad Lead if team member hasn’t RSVP’d by 12h out
- Auto-notify users with multiple missed events
- DM & Discord pings if RSVP deadline missed

---

### 6. Discord Bot Integration
- Create Discord embed with RSVP buttons (✅ 🟡 ❌)
- Auto-create Discord Scheduled Event
- Slash commands:
  - `/event_list`
  - `/event_attendance_check`
  - `/event_remove_user`
- Admin-only slash command control via role permissions
- Private log channel for event actions

---

### 7. Role-Based Access Control (RBAC)

| Role           | Permissions                                             |
|----------------|---------------------------------------------------------|
| Admin          | Full event creation, attendance management              |
| CO/XO          | Manage all events tied to all deployments               |
| Squad Lead     | Create training events, view team RSVP/attendance       |
| Team Lead      | View attendance data for their own unit/team            |
| Regular User   | RSVP to events, view their own attendance history       |

---

### 8. Edge Cases & Policy Handling
- Users who RSVP then go on LOA before event = auto-invalidated?
- Deleted Discord event sync → flag in UI?
- Duplicate event prevention logic (by title/time overlap)
- Admins can override RSVP lockout after deadline
- Users flagged for frequent:
  - “No RSVP”
  - “RSVP’d but No-show”

---

## 📌 Status
Planning phase ✅  
Next step: Finalize schemas, flow diagrams, and wireframes before implementation.
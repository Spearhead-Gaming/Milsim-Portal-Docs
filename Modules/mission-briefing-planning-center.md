# 📋 Mission Briefing & Planning Center – Full Feature Specification

This module allows creation and management of pre-operation briefings. It standardizes mission planning documentation and ensures all roles have access to relevant tactical information.

---

## 🎯 Purpose & Goals
- Standardize format for OPORDs and training briefs
- Link mission information to calendar events
- Assign squad/team objectives and planning assets

---

## 👤 Roles

| Role       | Permissions                                   |
|------------|-----------------------------------------------|
| Admin      | Full access                                   |
| S3 Staff   | Can create/edit all briefings                 |
| CO/XO      | Can view/edit briefings within their scope    |
| Squad Lead | View/annotate squad-relevant briefings        |
| Team Lead  | View briefings only                           |
| User       | RSVP-based access to public briefings         |

---

## 📋 Core Features
- Briefing types: OPORD, FRAGO, SITREP
- Customizable fields: objectives, enemy intel, comms, ROE
- Attachments: PDFs, maps, voice messages
- RSVP-only or leadership-only visibility
- QR code for Discord embeds

---

## 🗃️ Schema
Collection: `briefings`  
Fields: eventId, deploymentId, situation, objectives, attachments, tasking, visibility

---

## 🌐 API
- `POST /api/briefings` – Create
- `GET /api/briefings/:eventId` – View by event
- `PUT /api/briefings/:id` – Edit
- `DELETE /api/briefings/:id` – Delete

---

## 🔁 Integration
- Linked to Events module
- Tasking displays in Unit chain views
- Discord embed announcement command

---

## 📌 Status
Planning complete ✅  
Next: Form builder and template designer

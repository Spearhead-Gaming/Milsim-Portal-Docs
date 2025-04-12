# 🛠️ Operation Builder & Mission Library – Full Feature Specification

This module centralizes storage of mission templates used across campaigns. Operations can be linked to events, deployments, and reused through a cloning tool.

---

## 🎯 Purpose
- Build structured operation templates with key metadata
- Attach mission files and version history
- Assign to deployments or events
- Track reuse across campaigns

---

## 👤 Role Access

| Role       | Permissions                               |
|------------|-------------------------------------------|
| Admin      | All operations + delete                   |
| S3 Staff   | Full creation/editing and file handling   |
| CO/XO      | View and approve                          |
| Squad Lead | View basic info on approved operations    |

---

## 📋 Features
- Metadata: Title, Map, Type, Version, Tags
- File upload: .pbo, .zip, docs
- Mission linking: assigned campaign and event
- Reuse log: when/where used, version
- Filtering: terrain, tags, author, time period

---

## 🗃️ Schema
Collection: `operations`  
Fields: title, map, type, missionFileUrl, version, usedInEvents[], tags, createdBy

---

## API
- `GET /api/operations` – List/search
- `POST /api/operations` – Create
- `PUT /api/operations/:id` – Edit
- `POST /api/operations/:id/clone` – Reuse template

---

## 🚀 Future Additions
- Visual previews (map, image, PDF)
- Tag by training focus
- Usage statistics

---

## 📌 Status
Planning complete ✅  
Next: Build library grid/list views and file upload logic

# 🧠 Intel & Threat Board – Full Feature Specification

This module functions as an immersive intelligence and threat-tracking system. It is designed to support mission planning, campaign immersion, and strategic awareness by consolidating relevant operational data and enemy profiles in a central hub.

---

## 🎯 Purpose & Goals
- Document and centralize faction/enemy data
- Organize in-universe intelligence for campaigns and ops
- Link mission intel to deployments and events
- Provide accessible map-based threat visualization

---

## 👤 User Roles & Permissions

| Role       | Permissions                                                |
|------------|------------------------------------------------------------|
| Admin      | Full CRUD for all intel entries and threat actor profiles |
| S3 Staff   | Create/edit intel entries and update AO assessments       |
| CO/XO      | View and comment; create entries during active ops        |
| Squad Lead | View and annotate assigned intel regions                  |
| User       | View-only (if access granted per event or AO)             |

---

## 📋 Core Feature Breakdown

### 1. Threat Actor Profiles
- Faction name & alias
- Description, structure, and doctrine
- AO presence (regions/maps where active)
- Equipment loadout (estimated)
- Associated operations (linked history)

### 2. Intel Entries
- Types:
  - HUMINT (Human Intelligence)
  - SIGINT (Signals Intelligence)
  - IMINT (Imagery)
  - OSINT (Open Source)
- Fields:
  - Source (unit, drone, informant, etc.)
  - Description / summary
  - Confidence level (low/med/high)
  - Location (grid/map reference)
  - Attachments (images, documents)
  - Tags (e.g. vehicle, sabotage, logistics)

### 3. Visual Threat Board
- Filter by region, operation, tag, confidence
- Map overlay mode
- Timeline/history mode to see progression
- Pin drop for AO markers with legend

---

## 🗃️ Database Schema (Mongoose-style)

### `intelEntries`
```ts
{
  _id: ObjectId,
  type: 'HUMINT' | 'SIGINT' | 'IMINT' | 'OSINT',
  source: string,
  summary: string,
  confidence: 'Low' | 'Medium' | 'High',
  location: string,
  regionMap: string,
  threatActorId?: ObjectId,
  tags: string[],
  attachments: [string],
  createdBy: ObjectId,
  createdAt: Date
}
```

### `threatActors`
```ts
{
  _id: ObjectId,
  name: string,
  alias?: string,
  description: string,
  aoPresence: string[],
  equipment: string[],
  operations: [ObjectId],
  lastUpdated: Date
}
```

---

## 🌐 API Endpoints
- `POST /api/intel` → Create intel
- `GET /api/intel` → List/filter
- `GET /api/intel/:id` → View single intel
- `POST /api/threat-actors` → Create actor
- `GET /api/threat-actors` → Browse actors

---

## 🖥️ UI Components
- **IntelBoard.tsx** – Region/map overlay view
- **IntelEntryForm.tsx** – Create intel entry
- **ThreatProfileCard.tsx** – View/edit threat actor
- **IntelTimeline.tsx** – Time-based filter and analysis view

---

## 🔁 Integration
- Briefing Center: auto-import key intel by tag/region
- Event Planner: pre-load relevant intel for planning dashboard
- Discord webhook (intel-pings or updates)

---

## ⚠️ Edge Cases & Rules
- Entries require at least 1 confidence level
- Auto-flag outdated intel >60 days old
- Cross-reference entry sources by tag for verification

---

## 🚀 Future Enhancements
- GeoJSON / custom map tiles for live mapping
- Unit-tagged AO tracking
- Custom user dashboard feed for new intel
- Auto-translation or classified view modes

---

## 📌 Status
Planning complete ✅  
Next step: Build form schema, AO visualization, and briefing integration hooks.

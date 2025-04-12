# 🪖 Unit Structure Management – Feature Specification

This module allows administrators to create and manage a hierarchical military structure composed of **Units**, **Squads**, and **Teams**, and assign users to their positions within the organization. It serves as a foundation for permissions, training tracking, attendance reporting, and Discord role syncing.

---

## ✅ Core Features

### 1. Unit Hierarchy Creation
- Create top-level **Units** (e.g., “Alpha Company”)
- Under each Unit:
  - Add **Squads**
  - Under Squads, add **Teams**
- Each layer includes:
  - `Name`
  - `Callsign` (optional)
  - `Description`
  - `Assigned Leadership Roles` (CO, XO, Squad Lead, Team Lead)

---

### 2. User Assignment & Profile Integration
- Assign users to:
  - `Unit`
  - `Squad` (within a unit)
  - `Team` (within a squad)
- View assignments on user profile
- Roles and permissions dynamically tied to user’s structure level

---

### 3. Leadership Management
- Set leadership per layer:
  - `Unit CO / XO`
  - `Squad Lead`
  - `Team Lead`
- Automatically apply Discord leadership roles
- Used for access control across the portal

---

### 4. Unit Dashboard
- Visual breakdown of structure (tree view or nested table)
- Stats per structure:
  - Member count
  - Leadership chain
  - Training completion %
  - Active LOAs
  - Recent attendance
- Navigation links to manage unit-specific data

---

### 5. Admin Tools
- Create, rename, merge, archive Units/Squads/Teams
- Reassign members across units
- View inactive squads/teams or low population warnings
- Bulk assignment support

---

## 🔁 Integration Points

| Module             | How It Integrates                                 |
|--------------------|---------------------------------------------------|
| **Events**         | Filter by unit/squad/team for attendance summaries |
| **Training**       | Track training progress per squad/team             |
| **LOA**            | Show who’s on leave within a specific structure    |
| **Disciplinary**   | Filter incidents by structure                      |
| **Resources**      | Assign guides/manuals to specific unit levels      |
| **Permissions**    | Scope access based on leadership assignments       |

---

## 🗃️ Suggested Schema

### `units`
```ts
{
  _id: ObjectId,
  name: string,
  callsign?: string,
  description?: string,
  squads: [ObjectId],
  leadership: {
    co: ObjectId,
    xo: ObjectId
  }
}
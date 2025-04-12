# 🧩 Milsim Operation Modlist Management – Feature Specification

This module allows leadership and S3 staff to manage, organize, and distribute modlists for operations. It ensures all players have the correct mods, synced through Steam Workshop or Arma 3 Launcher integration.

---

## ✅ Core Features

### 1. Modlist Creation & Management
- Create named modlists for:
  - Operations
  - Training
  - Persistent campaigns
- Each modlist includes:
  - `Title`
  - `Description`
  - `Tags` (e.g., “Main Deployment”, “Optional”, “Training”)
  - `Steam Workshop URLs` or `Mod IDs`
  - `Order/priority` field for load sequence

---

### 2. Sync & Download Tools
- Export options:
  - `.html` file for Arma 3 Launcher import
  - Raw `.json`/`.txt` for A3Sync or CLI loaders
- Optional:
  - One-click copy link
  - QR code for quick download (via mobile)

---

### 3. User Interaction
- Users can:
  - View assigned modlists
  - Download or sync with one click
  - Mark modlist as “synced” (checkbox or toggle)
- Optional: Track user mod sync completion (future)

---

### 4. Discord Integration
- Notify relevant channels on:
  - New modlist added
  - Modlist updated (with changelog message)
- Slash commands (admin only):
  - `/modlist_post [operation name]`
  - `/modlist_update_notice`

---

### 5. Version Control & Update Logs
- Each modlist supports:
  - Version tagging (e.g., `v1.0`, `v1.1`)
  - Changelog notes per update
  - History of changes (viewable by admins/S3 staff)
- Revert to previous version (admin only)

---

### 6. Role-Based Access Control (RBAC)

| Role       | Permissions                                          |
|------------|------------------------------------------------------|
| Admin      | Create/edit/delete all modlists                      |
| S3 Staff   | Full modlist management + version control            |
| CO/XO      | View and share modlists                              |
| Squad Lead | View and share modlists                              |
| Regular User | View and sync assigned modlists only              |

---

### 7. Edge Cases & Compatibility
- [ ] Detect invalid Steam links or duplicates
- [ ] Warn users if modlist is outdated or changed
- [ ] Allow private/internal mod links with secure access
- [ ] Set expiration date or archive status for outdated modlists

---

### 8. Future Enhancements
- Automatic Steam Workshop validation & mod icon display
- Arma 3 Launcher integration (via `.html` launcher import file)
- In-portal mod manager (compare installed vs required mods)
- Notifications if users are missing required mods (optional agent)

---

## 📌 Status
Planning phase ✅  
Next step: Define modlist schema, export formats, and Steam link validation.
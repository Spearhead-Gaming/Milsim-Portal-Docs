# 🖥️ Server Management Portal – Feature Specification

This module provides a centralized control panel for managing Arma 3 game servers. It allows leadership and S3 staff to monitor server status, perform basic operations, and schedule recurring tasks like restarts or backups.

---

## ✅ Core Features

### 1. Server Status Monitoring
- Display real-time server information:
  - `Online / Offline` state
  - `Current Player Count`
  - `Max Players`
  - `Current Mission File`
  - `Server IP and Port`
- Auto-refresh or WebSocket-based live updates

---

### 2. Remote Server Actions
- Authorized users can trigger:
  - `Restart Server`
  - `Stop Server`
  - `Start Server`
  - `Force Update Mods`
- Logs actions performed (by who, when, and what action)

---

### 3. Scheduled Task Management
- Schedule the following recurring tasks:
  - Automatic server restarts (daily/weekly)
  - Mod updates (via workshop or external sync)
  - Backup tasks (config files, mission data)
- Cron-style or calendar-based scheduling
- View upcoming and completed tasks

---

### 4. Discord Integration & Notifications
- Log server restarts, stops, or updates to an S3 staff Discord channel
- Optional DM or @mention if the server goes offline unexpectedly
- Manual command support via Discord bot (optional):
  - `/server_status`
  - `/server_restart`
  - `/server_update_mods`

---

### 5. Role-Based Access Control (RBAC)

| Role       | Permissions                                                    |
|------------|----------------------------------------------------------------|
| Admin      | Full control of all server features                            |
| S3 Staff   | Can perform restarts, stop/start, manage scheduled tasks       |
| CO/XO      | Can view status and logs                                       |
| Squad Lead | View status only                                               |
| Regular User | No access unless explicitly granted (view-only toggle?)      |

---

### 6. Audit Log
- Every server action is logged with:
  - User who performed the action
  - Timestamp
  - Action Type
- Filterable audit history page (view by date, user, action)

---

### 7. Edge Cases & Fail-Safes
- [ ] Prevent restart if users are online (confirm override)
- [ ] Backup before shutdown (optional toggle)
- [ ] Allow scheduled restarts to be skipped if active users detected
- [ ] Health check pings to validate true offline status

---

### 8. Future Enhancements
- Mod/version mismatch detection
- One-click mission rotation
- Real-time player viewer with connected users
- Map rotation scheduling
- Mobile-friendly quick action panel

---

## 📌 Status
Planning phase ✅  
Next step: Define server control API integration (with RCON, SSH, or service layer), task scheduler, and permission structure.
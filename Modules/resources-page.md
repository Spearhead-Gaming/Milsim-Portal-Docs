# 📚 Resources Page – Feature Specification

This module provides a centralized hub for guides, manuals, reference materials, and links relevant to the community. It helps members find important information quickly and ensures materials are kept up to date with role-based edit permissions.

---

## ✅ Core Features

### 1. Categorized Resource Listings
- Resources organized into categories such as:
  - Training Manuals
  - SOPs (Standard Operating Procedures)
  - Server Setup Guides
  - Unit Policies
  - Useful External Tools
- Each resource contains:
  - `Title`
  - `Description`
  - `Link` (internal or external)
  - `Category`
  - `Tags` (optional)
  - `Last Updated` date

---

### 2. Resource Management Interface
- Admin UI for:
  - Adding new resources
  - Editing title, description, link, or category
  - Reordering resources in each category
  - Deleting outdated or irrelevant resources

**Optional Enhancements:**
- Attachments (e.g., upload a PDF/manual instead of a link)
- Markdown-supported descriptions or embedded previews

---

### 3. Permissions & Access Control
- Users:
  - Can view and use resources
  - Can suggest new resources (optional)
- Leadership (Team Lead+):
  - Can edit or update resources in their assigned category
- Admins:
  - Full access to manage all resources and categories

---

### 4. Navigation & UI
- Clean, searchable interface
- Filter by:
  - Category
  - Tags
  - Keyword
- Option to favorite/star resources for quick access
- Mobile responsive layout for quick in-game referencing

---

### 5. Audit Logging & Notifications
- Track who added/edited/deleted each resource
- Optional log to Discord admin channel
- Notification to leadership when critical documents (e.g., SOP) are changed

---

### 6. Role-Based Access Control (RBAC)

| Role           | Permissions                                                 |
|----------------|-------------------------------------------------------------|
| Admin          | Create/edit/delete all resources and categories             |
| CO/XO          | Edit core SOPs and training categories                      |
| Squad Lead     | Add/update training and team-specific resources             |
| Team Lead      | View all, update relevant training links                    |
| Regular User   | View all public resources                                   |

---

### 7. Edge Cases & Policy Rules
- [ ] Handle broken links (auto-check or user report)
- [ ] Prevent duplicate titles in the same category
- [ ] Archive deprecated documents instead of deletion (optional)
- [ ] Versioning support for SOPs or training guides

---

### 8. Future Enhancements
- User-submitted resource suggestions (approval queue)
- In-portal PDF viewer for uploaded resources
- Resource download analytics (track usage)
- Unit-specific resources (visible only to assigned unit)

---

## 📌 Status
Planning phase ✅  
Next step: Define resource schema, edit form components, and RBAC enforcement.
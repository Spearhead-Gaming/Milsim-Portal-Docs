# 🌐 Public Community Hub – Full Feature Specification

The Public Community Hub serves as the front-facing website for the Milsim organization. It provides general public information, promotes recruitment, showcases operations, and delivers access to modlists and schedules for potential and current members.

---

## 🎯 Purpose & Goals
- Act as a landing page for recruitment and community visibility
- Offer new users an introduction to the unit’s identity, values, and activity
- Provide access to events, modlists, and guides without needing to log in
- Sync dynamically with internal portal content when permitted

---

## 👤 Audience & Permissions

| User Type         | Access Scope                                                  |
|------------------|---------------------------------------------------------------|
| Anonymous Visitor | Public content, recruitment, modlist, gallery, contact form  |
| Registered User   | Redirected to full portal dashboard (after login)            |
| Admin             | Edit static content, images, media uploads, layout structure |

---

## 📋 Core Feature Breakdown

### 1. Landing Page
- Unit banner with mission statement and visual branding
- Intro section with video or image carousel
- “Why Join Us?” with bullet reasons and icons
- “What We Do” with links to major modules (ops, training, comms)

### 2. Recruitment Information
- Requirements list (age, schedule, equipment, Discord)
- How to Apply → button linking to internal application module
- Recruiter Discord tag and optional contact form

### 3. Public Event Schedule
- Display next 3–5 public ops/trainings
- Integrated with `/api/events/public`
- Shows: title, time (with user-local timezone), and tags

### 4. Public Modlist Viewer
- View current operation modlist
- Include: Steam collection, Arma 3 Launcher export file, guide
- Optional: Troubleshooting tips and setup help

### 5. Media Highlights
- Most recent gallery items from AAR/Media module (curated)
- YouTube embeds for recent uploads
- Carousel and filter by operation tag (optional)

---

## 🗃️ Suggested Page Routes
- `/` – Landing page
- `/join` – Recruitment info
- `/events` – Public ops calendar
- `/mods` – Current modlist with links
- `/media` – Highlights and AAR snippets

---

## 🌐 API Dependencies
- `GET /api/events/public`
- `GET /api/modlist/latest`
- `GET /api/media/public`

---

## 🖥️ Frontend Components
- **HeroBanner.tsx** – Large intro image with CTA
- **EventCard.tsx** – Upcoming public operation
- **RecruitmentPanel.tsx** – Join us guide and Discord link
- **ModlistViewer.tsx** – Current modpack with links
- **MediaCarousel.tsx** – Screenshots, YouTube previews

---

## ⚠️ Rules & Policies
- Only curated content should be public (controlled by Admin toggle)
- Event/Modlist/Media API calls must filter by `public: true`
- Contact form spam protection (reCAPTCHA or rate limit)

---

## 🚀 Future Enhancements
- Live Discord widget with activity feed
- SEO optimization for recruitment keywords
- Server status widget (e.g. A3Sync or GameTracker)
- Internationalization (EN, FR, DE, etc.)

---

## 📌 Status
Planning complete ✅  
Next step: Build landing page structure and connect dynamic routes to public-facing APIs.

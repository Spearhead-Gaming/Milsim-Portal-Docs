# 📝 Recruitment & Application Tracker – Full Feature Specification

This module streamlines the intake, review, and onboarding of new applicants into the Milsim community. It ensures consistent evaluation, assigns leadership to manage candidates, and integrates Discord for automated onboarding and communication.

---

## 🎯 Purpose & Goals
- Enable structured recruitment with transparent application processing
- Automate role assignments and Discord onboarding steps
- Track candidate progress from application to full unit integration
- Maintain a searchable log of applicant history

---

## 👤 User Roles & Permissions

| Role       | Permissions                                                                 |
|------------|-----------------------------------------------------------------------------|
| Admin      | Full access to application form config, reviewer assignment, status updates |
| CO/XO      | Review/approve all applications, assign recruiters                          |
| Recruiter  | View and manage assigned applications, submit review notes                  |
| User       | Submit one application, view own progress/status                            |

---

## 📋 Core Feature Breakdown

### 1. Application Form
- Customizable form builder (admin-only)
- Required fields: Discord Tag, Steam Profile, Age, Time Zone, Experience, Availability, Motivation
- Optional fields: Referral, custom inputs
- Discord OAuth2 login required to submit
- CAPTCHA protection

### 2. Review Queue & Moderation
- Dashboard for admin and recruiters
- Sort/filter by status, reviewer, date
- Actions: assign reviewer, add notes, approve/reject, archive

### 3. Onboarding Tracker
- Track modlist sync, training, Discord verification
- Visual checklist and timeline
- Recruiter assigned for follow-up

---

## 🗃️ Schemas
See in-app database: `applications`, `onboardingTrackers`

---

## 🔁 Integration Points
- Discord DM on approval/rejection
- Auto-assign Discord “Candidate” role
- Link to training and unit assignment

---

## 🚀 Future Enhancements
- Auto-close inactive applications
- Candidate status analytics
- Cross-module eligibility checks

---

## 📌 Status
Planning phase ✅  
Next: UI form creation, review dashboard, and role-sync integration

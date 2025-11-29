# SignLMS – Sign Language Learning Management System

> **Note:** This repository only contains a project README and a demo video of the website UI and core flows.  
> The full source code is kept private because this is a sponsored academic project and uses private API keys, tokens, and other confidential configuration.

---

## 📁 Repository Contents

- `README.md` – Project overview, architecture, features, and tech stack.
- `demo/SignLMS-demo.mp4` – Screen recording of the live system showing:
  - Teacher portal (dashboard, assignments, quizzes, classes, students)
  - Student portal (dashboard, assignments, quizzes)
  - Key user journeys (login, assignment creation, quiz creation, submission flows)

The application code, `.env` files, API keys, Firebase configuration, and deployment scripts are **not** included in this repository.

---

## 🔒 Confidentiality & Sponsorship

- This project is developed as a **sponsored academic/industry project**.
- The codebase contains:
  - Private API keys, tokens, and secrets (e.g., Firebase, database credentials, email providers).
  - Institution‑specific logic, data structures, and flows.
  - Integration details with third‑party services used by the sponsor.

Because of this:

- The complete source code is stored in a **private repository** and cannot be publicly disclosed.
- Any reuse, redistribution, or modification of the full system requires explicit permission from the sponsor and supervising faculty.

This public-facing README and demo video are provided **only** to document the project for review and evaluation purposes.

---

## 🎯 Project Overview

**SignLMS** is a web-based Learning Management System focused on **sign language education**.  
It allows teachers to manage classes, assignments, and quizzes, and allows students to learn, submit work, and track their progress in sign language courses.

Key goals:

- Support structured sign language teaching in schools/colleges.
- Make it easy for teachers to assign practice (including sign video assignments and quizzes).
- Give students a clean, mobile-friendly portal to keep track of tasks and assessments.

---

## 👥 User Roles

1. **Admin**
   - Manages teachers and students.
   - Oversees classes and global settings.

2. **Teacher**
   - Manages their classes and enrolled students.
   - Creates assignments and quizzes.
   - Reviews submissions and monitors progress.

3. **Student**
   - Views enrolled classes and upcoming work.
   - Submits assignments and attempts quizzes.
   - Tracks grades and completion status.

---

## ✨ Main Features (as shown in demo)

### Teacher Portal

- **Dashboard**
  - Summary cards for:
    - Total students
    - Total classes
    - Assignments created
    - Quizzes created
  - Quick refresh to pull latest stats.

- **Students Management**
  - Add single student with email + password.
  - Bulk upload students via CSV (auto‑generates passwords and downloads credentials file).
  - View list of students (name, email, status, created date).
  - Delete students (removes from Firebase Auth + database).

- **Assignments & Quizzes**
  - Tabbed interface: **Assignments** | **Quizzes**.
  - Assignments:
    - Create assignment with title, description, due date, class selection.
    - Cards show title, description, due date, status (active/closed), created date.
    - Delete assignments.
  - Quizzes:
    - List of quizzes with title, description, question count, total points, time limit, and status.
    - Delete quizzes.
    - Demo shows how quizzes appear similarly to assignments for teachers.

- **Classes**
  - View classes created for the teacher with:
    - Class name, subject, grade, section.
  - Used when assigning work to the correct group of students.

### Student Portal

- **Dashboard**
  - Overview of active classes and upcoming assignments/quizzes.
  - Simple, student-friendly layout.

- **Assignments & Quizzes**
  - View upcoming and past assignments.
  - Attempt quizzes with:
    - Question list
    - Points per question
    - Timer (if configured)
  - See completion and basic feedback.

---

## 🧱 Technology Stack

### Frontend

- **React** (with hooks)
- **TypeScript**
- **React Router** for routing
- **Tailwind CSS / utility‑class styling**
- **Lucide React** icons
- Custom API client wrapper for HTTP calls

### Backend

- **Node.js** + **Express.js**
- **TypeScript**
- **MongoDB** with **Mongoose**
- **Firebase Authentication** (email/password)
- **JWT** for session handling (on top of Firebase UID)
- RESTful API layered with:
  - Controllers (business logic)
  - Models (Mongoose schemas)
  - Middleware (auth, role checks, validation)

### Other

- Environment-based configuration using `.env` files.
- Secure handling of secrets (never hard-coded in code, only in env/config).
- Deployed using standard Node/React deployment flow (demo shows running app).

---

## 🧩 High-Level Architecture

- **Frontend** (Teacher & Student portals)
  - Communicates only with the backend via REST APIs.
  - Manages UI state (dashboard stats, assignments, quizzes, modals).

- **Backend API**
  - Authenticates users via Firebase tokens.
  - Uses role-based access:
    - `/api/teacher/*` for teacher actions.
    - `/api/student/*` for student actions.
  - Exposes endpoints for:
    - Teachers: dashboard stats, classes, students, assignments, quizzes.
    - Students: assignments, quizzes, submissions.

- **Database (MongoDB)**
  - Collections for:
    - Users
    - Classes
    - Assignments
    - Quizzes
    - Submissions / attempts
  - References between teachers, classes, and students.

---

## 🚫 Source Code & Secrets

The full codebase is intentionally excluded from this public repository because:

- It contains **private API keys and tokens** (Firebase, database, email/notification services, etc.).
- It is part of a **sponsored institutional project**, not an open‑source product.
- Some logic and content is tailored specifically for the sponsoring institution.

If you are a reviewer/teacher:

- Please refer to:
  - This README for technical and functional overview.
  - The demo video for a walkthrough of all main flows.

If full source review is needed:

- Access can be provided separately via a private repository or local machine demonstration, as per sponsor/institution policy.

---

## 👨‍🎓 Credits

- **Developers:** Aditya Chakre, Tauheed Khan, Shruti Konde, Shaikh Javeriya
- **Project Type:** Sponsored academic project  
- **Institution:** Maharashtra Institute of Technology  
- **Guide / Instructor:** Ms. Supriya Gaikwad

---

## 📅 Status

- **Version:** 2.0  
- **Last Updated:** November 2025  
- **Visibility:** Documentation + demo only (code private)


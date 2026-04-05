You are a senior technical writer. Create a clear, professional README for this project.

Project name:
Advanced Online Examination and Proctoring System

Stack:
- Frontend: React + Vite
- Backend: Node.js + Express + MongoDB

Known features:
- Separate student and teacher register/login pages
- 3 departments and 5 subjects per department
- Teacher can create exams with auto-generated default 10 MCQ questions (4 options each)
- Live camera monitoring for students during exam
- Automatic exam termination + alert when multiple faces are detected
- Teacher dashboard includes:
  - exam conduct controls (start/terminate)
  - student data list
  - malpractice list
  - right/wrong question analytics per student
- Student dashboard shows percentage-only results
- Separate student result portal login to view detailed right/wrong question report

Admin panel (from frontend/src/pages/Admin.jsx):
- Sections: Reports, Users, Catalog, Announcements, Exams, Settings
- Reports: summary for last 30 days (users, exams, results avg %, violations)
- Users: create user, edit user, toggle active/disabled, reset password
- Bulk import users from CSV: header = name,email,password,role,department,rollNumber,phoneNumber,active
- Export users CSV
- Catalog: JSON mapping of dept -> subjects[]
- Announcements: send to all or per department
- Exams: approve exams, terminate sessions
- Settings: JSON key-value config editor

Routes:
- Student auth: /auth/student
- Teacher auth: /auth/teacher
- Student dashboard: /student
- Student result detail portal: /student/result-access
- Teacher dashboard: /teacher

Backend setup:
1. cd backend
2. copy .env.example .env
3. Set values in .env:
   - MONGO_URI
   - JWT_SECRET
   - ADMIN_REGISTER_CODE (optional; enables Admin Register)
   - TEACHER_REGISTER_CODE (optional but recommended)
   - PORT (frontend expects http://localhost:5001 by default)
4. npm install
5. npm run dev

Frontend setup:
1. cd frontend
2. copy .env.example .env and set VITE_API_URL if needed
3. npm install
4. npm run dev

One-command dev (Windows / PowerShell):
- Start both backend + frontend: powershell -ExecutionPolicy Bypass -File .\dev.ps1
- Stop ports 5001 + 5173: powershell -ExecutionPolicy Bypass -File .\stop.ps1

Output requirements:
- Use GitHub-flavored Markdown
- Keep sections concise and scannable
- Do not invent features not listed
- Include these sections (and only these, unless something is clearly missing):
  1. Overview
  2. Key Features
  3. Tech Stack
  4. Admin Panel Highlights
  5. Routes
  6. Setup (Backend + Frontend)
  7. Environment Variables
  8. One-Command Dev
  9. Project Structure (high level, mention /frontend and /backend)
  10. Notes / Limitations (only if implied by given info)

Tone:
- Clear, professional, project-ready

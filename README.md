# AI-Powered Smart Recruitment System

A complete internship portfolio project that streamlines recruitment with resume analysis, ATS scoring, skill extraction, job matching, recruiter analytics, candidate dashboards, and AI-style interview question generation.

## Project Overview

Recruiters spend a lot of time reading resumes manually, comparing skills with job descriptions, and preparing interview questions. This project automates those steps with a full-stack web application.

The local demo works without external AI keys. The code is structured so Gemini or OpenAI can be added later in `server/controllers/aiController.js`.

## Features

- Candidate registration and login
- Recruiter/admin login flow
- Resume upload and text analysis
- Resume parser for name, email, phone, education, skills, experience, projects, and certifications
- ATS score, grammar score, formatting score, and resume score
- Missing keyword and skill gap report
- Job listing, search, filtering, and job detail pages
- Resume-to-job matching percentage
- Personalized interview question generation
- Candidate dashboard with recommendations and application status
- Recruiter dashboard with statistics, candidate ranking, skill distribution, and CSV export
- Dark mode
- Express API routes matching the project guide

## Tech Stack

Frontend:

- React.js
- React Router
- Axios
- Lucide React icons
- Responsive CSS

Backend:

- Node.js
- Express.js
- JWT
- bcrypt
- Multer
- Mongoose-ready models

Database:

- MongoDB Atlas ready through `MONGODB_URI`
- In-memory demo data when MongoDB is not configured

AI:

- Local AI-style scoring and question generation
- Gemini/OpenAI key placeholders in `.env`

## Architecture

```text
Client React UI
  -> Resume analysis utilities
  -> Job matching utilities
  -> Dashboards and reports

Express API
  -> Auth routes
  -> Resume upload routes
  -> AI analysis routes
  -> Job management routes
  -> MongoDB-ready models
```

## Folder Structure

```text
AI-Recruitment-System/
├── client/
│   ├── public/
│   ├── assets/
│   ├── components/
│   ├── pages/
│   ├── services/
│   ├── context/
│   ├── hooks/
│   ├── utils/
│   ├── src/
│   ├── App.jsx
│   ├── main.jsx
│   ├── styles.css
│   └── index.html
├── server/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── uploads/
│   ├── utils/
│   └── server.js
├── README.md
├── package.json
└── .env
```

## Installation

```bash
npm install
npm run dev
```

Open the client:

```text
http://127.0.0.1:5173
```

Run the backend API separately:

```bash
npm run server
```

Backend health check:

```text
http://127.0.0.1:5000/api/health
```

## Environment Variables

```env
PORT=5000
CLIENT_URL=http://127.0.0.1:5173
JWT_SECRET=replace-this-with-a-long-secret
MONGODB_URI=
GEMINI_API_KEY=
OPENAI_API_KEY=
VITE_API_URL=http://127.0.0.1:5000/api
```

## API Documentation

Authentication:

- `POST /register`
- `POST /login`
- `GET /profile`
- `POST /api/auth/forgot-password`

Resume:

- `POST /uploadResume`
- `GET /resume`
- `DELETE /resume`

Jobs:

- `GET /jobs`
- `GET /jobs/:id`
- `POST /job`
- `PUT /job/:id`
- `PATCH /job/:id/close`
- `DELETE /job/:id`

AI:

- `POST /resume-analysis`
- `POST /job-matching`
- `POST /generate-interview`

## Demo Logins

Candidate:

```text
candidate@example.com
password123
```

Recruiter:

```text
recruiter@example.com
password123
```

## Resume Description

Developed a full-stack AI recruitment platform that streamlines hiring by analyzing resumes, extracting candidate skills, matching applicants with job descriptions, calculating ATS compatibility scores, and generating personalized interview questions. Built authentication-ready backend routes, recruiter and candidate dashboards, resume upload support, and deployment-ready project documentation using React.js, Node.js, Express.js, and MongoDB-ready models.

## Future Enhancements

- Connect MongoDB Atlas for persistent users, resumes, jobs, and applications
- Replace local scoring with Gemini or OpenAI prompts
- Add Cloudinary file storage
- Add email notifications with Nodemailer
- Add admin analytics and user management
- Add pagination for large candidate and job datasets
- Add profile photos and resume download
- Deploy frontend to Vercel and backend to Render



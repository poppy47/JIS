# ⚖️ Judiciary Information System (JIS)

A full-stack web application to digitize and manage court operations — including case registration, hearing scheduling, and role-based access for judges, lawyers, and registrars.

---

## 🚀 Tech Stack

**Frontend**
- React 18, React Router v6
- Bootstrap 5, MDB React UI Kit, styled-components

**Backend**
- Node.js, Express 4
- MongoDB (Mongoose 7)

---

## ✨ Features

- **Role-based access control** — separate dashboards for Judge, Lawyer, and Registrar
- **Case management** — register, update, and search cases by CIN (Case Identification Number)
- **Hearing scheduler** — schedule court dates with location and description
- **User management** — signup, login, update, and delete court personnel
- **Lawyer validation** — automatically validates that assigned judge and lawyers exist before filing a case
- **Payment page** — for lawyers to access case details

---

## 🗂️ Project Structure

```
judicary_information/
├── backend/               # Node.js + Express REST API
│   ├── models/            # Mongoose schemas (User, Case, Schedule)
│   ├── Functions/         # CRUD helper functions
│   ├── modules/           # OOP role classes (User, Judge, Lawyer, Registrar)
│   ├── database/          # MongoDB connection
│   └── index.js           # Entry point, all API routes
│
├── frontend/              # React SPA
│   ├── src/
│   │   ├── components/    # All page components
│   │   ├── css/           # Stylesheets
│   │   └── App.js         # Routes & role-based rendering
│   └── public/
│
└── Documents/             # SRS, DFD, UML diagrams (class, use-case, sequence, etc.)
```

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/Signup` | Register a new user |
| `POST` | `/Login` | Authenticate user |
| `GET` | `/users/:userName` | Get user by username |
| `PUT` | `/update/:userName` | Update user details |
| `DELETE` | `/delete/:userName` | Delete a user |
| `POST` | `/registrar/addcase` | File a new case |
| `POST` | `/registrar/getdetails` | Fetch case by CIN |
| `PUT` | `/registrar/updatecase` | Update case information |
| `POST` | `/registrar/schedulecase/:cin` | Schedule a hearing |

---

## ⚙️ Getting Started

### Prerequisites
- Node.js v16+
- MongoDB (running locally on port `27017`)

### Run the backend
```bash
cd backend
npm install
node index.js
# Runs on http://localhost:5000
```

### Run the frontend
```bash
cd frontend
npm install
npm start
# Runs on http://localhost:3000
```

### Create your first user
Use the `/Signup` endpoint or the signup page. Set `userType` to one of: `registrar`, `judge`, or `lawyer`.

---

## 👤 User Roles

| Role | Permissions |
|------|-------------|
| **Registrar** | Add, update, schedule cases; manage users |
| **Judge** | View assigned cases and schedules |
| **Lawyer** | Browse cases, view schedules, make payments |

---

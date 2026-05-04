#  SmartTractor Health Monitoring Sys

A full-stack final year B.Tech CSE project for monitoring tractor health in real time using simulated IoT sensor data, predictive maintenance logic, and a modern SaaS-style dashboard.

## Features

- Modern React + Tailwind frontend with landing page, auth pages, dashboard, profile, and history logs
- JWT authentication with role-based users: `Admin` and `Farmer`
- Node.js + Express backend with MongoDB integration
- Real-time-like tractor telemetry simulation using a background sensor engine
- Data visualization for temperature, fuel, oil, battery, and engine load
- AI-inspired maintenance suggestions and failure-risk scoring
- Alerts panel with acknowledge action
- PDF report download endpoint
- Forgot password demo flow
- Responsive light/dark themed interface

## Project Structure

```text
Smart Tractor Health Monitoring System/
|-- backend/
|   |-- src/
|   |   |-- config/
|   |   |-- controllers/
|   |   |-- middleware/
|   |   |-- models/
|   |   |-- routes/
|   |   |-- services/
|   |   `-- utils/
|   |-- .env.example
|   |-- package.json
|   `-- server.js
|-- frontend/
|   |-- src/
|   |   |-- components/
|   |   |-- context/
|   |   |-- lib/
|   |   `-- pages/
|   |-- .env.example
|   |-- package.json
|   |-- tailwind.config.js
|   `-- vite.config.js
`-- README.md
```

## Tech Stack

- Frontend: React, Vite, Tailwind CSS, Recharts, Framer Motion
- Backend: Node.js, Express.js, MongoDB, Mongoose, JWT, bcrypt
- Report Generation: PDFKit

## Setup Instructions

### 1. Backend setup

```bash
cd backend
npm install
copy .env.example .env
```

Update `.env` if needed:

```env
PORT=5000
MONGODB_URI=mongodb://127.0.0.1:27017/smart-tractor-health
JWT_SECRET=change_this_secret
CLIENT_URL=http://localhost:5173
SIMULATION_INTERVAL_MS=5000
```

Start the backend:

```bash
npm run dev
```

### 2. Frontend setup

Open a second terminal:

```bash
cd frontend
npm install
copy .env.example .env
```

Frontend `.env`:

```env
VITE_API_URL=http://localhost:5000/api
```

Start the frontend:

```bash
npm run dev
```

### 3. Demo login

- Email: `admin@tractorai.com`
- Password: `Admin@123`

## Main Modules Explained

### Frontend

- `LandingPage.jsx`: project introduction and feature highlights
- `LoginPage.jsx` and `RegisterPage.jsx`: authentication UI with validation
- `DashboardPage.jsx`: KPI cards, charts, AI insights, and alert center
- `HistoryPage.jsx`: tractor sensor history logs
- `ProfilePage.jsx`: editable user profile and tractor details
- `ThemeContext.jsx`: dark/light mode support

### Backend

- `authController.js`: registration, login, forgot password, reset password
- `sensorController.js`: dashboard data, telemetry history, alerts
- `simulationService.js`: generates live telemetry every few seconds
- `insightService.js`: calculates risk score and maintenance suggestions
- `reportController.js`: generates downloadable PDF report

## API Overview

- `POST /api/auth/register`
- `POST /api/auth/login`
- `POST /api/auth/forgot-password`
- `POST /api/auth/reset-password`
- `GET /api/sensors/dashboard`
- `GET /api/sensors/history`
- `GET /api/sensors/alerts`
- `PATCH /api/sensors/alerts/:id/acknowledge`
- `GET /api/users/profile`
- `PUT /api/users/profile`
- `GET /api/reports/download`

## Future Improvements

- Replace simulation with Arduino/ESP32 sensor input
- Add Socket.IO for true live push updates
- Add email-based password reset and OTP verification
- Add multiple tractor management for enterprise farms
- Deploy frontend on Vercel and backend on Render/Railway

## Notes

- The AI feature uses a rule-based predictive engine, suitable for academic demonstration and easy future replacement with a trained ML model.
- The project structure is beginner-friendly and presentation-ready for viva/demo use.

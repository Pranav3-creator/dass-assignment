# DASS_Assignment
The Hackathon Management System is a full-stack web application designed to manage hackathon-related activities including:

User authentication (Register/Login)

Team creation and management

Discussion forum

QR-based attendance tracking

Real-time team chat

The system is built using a modern MERN-style stack with real-time communication support via Socket.io and is fully deployed in production.

 Tech Stack
Frontend

React (Vite)

Axios

React Router

Socket.io Client

Hosted on Vercel

Backend

Node.js

Express.js

MongoDB (Database)

Mongoose

Socket.io

JWT Authentication

Hosted on Render

 Features Implemented
 User Authentication

Register with:

Name

Email

Password

Roll Number

Secure login with JWT

Token stored in localStorage

Protected routes using middleware

 Team Registration

Create a team

View list of teams

Join team chat

Teams stored in MongoDB

 Discussion Forum

Post discussions

View discussion threads

Persisted in database

 QR-Based Attendance

Generate QR code (Admin side)

Scan / Mark attendance

Attendance stored in database

Prevents duplicate marking

 Real-Time Team Chat

Built using Socket.io

Join team-specific chat rooms

Messages update instantly

Messages stored in MongoDB

Works in deployed production

 Project Structure
root/
│
├── backend/
│   ├── config/
│   ├── middleware/
│   ├── routes/
│   ├── socket/
│   ├── server.js
│
├── frontend/
│   ├── src/
│   │   ├── api/
│   │   ├── pages/
│   │   ├── components/
│   │   └── main.jsx
│
└── README.md
 Authentication Flow

User registers → Data saved in MongoDB

User logs in → JWT token generated

Token stored in localStorage

Axios interceptor attaches token to API requests

Backend verifies token before protected routes

Deployment Details
 Frontend Deployment

Platform: Vercel

Built using Vite

Environment variables configured:

VITE_API

VITE_SOCKET

 Backend Deployment

Platform: Render

Express server running

CORS configured for:

localhost (development)

Vercel domain (production)

 Production URLs

Frontend:

https://<your-vercel-domain>.vercel.app

Backend:

https://<your-render-backend>.onrender.com
 Environment Variables
Frontend (Vercel)
VITE_API=https://your-backend.onrender.com/api
VITE_SOCKET=https://your-backend.onrender.com
Backend (Render)
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
 How to Run Locally
Clone Repository
git clone <repo-url>
cd project-folder
 Backend Setup
cd backend
npm install
npm run dev

Server runs on:

http://localhost:5000
 Frontend Setup
cd frontend
npm install
npm run dev

Frontend runs on:

http://localhost:5173
 API Endpoints
Authentication

POST /api/auth/reg

POST /api/auth/login

Team

GET /api/team

POST /api/team

Forum

GET /api/forum

POST /api/forum

Attendance

POST /api/att

GET /api/att

Chat

GET /api/chat/:teamId

 Design Decisions

Used JWT for stateless authentication.

Used Axios interceptor for automatic token attachment.

Used Socket.io rooms for team-specific chat.

Separated frontend and backend for scalable deployment.

Used environment variables for secure configuration.

Configured CORS properly for production deployment.

 Challenges Faced

CORS issues after deployment

Environment variables not updating in Vercel

Socket.io connection to localhost in production

Permission denied during Vercel build

 Solutions

Updated backend CORS origin list

Set correct VITE_API and VITE_SOCKET

Redeployed frontend

Configured correct root directory in Vercel

 Functional Modules Summary
Module	Status
Authentication	 Completed
Team Registration	 Completed
Discussion Forum	 Completed
QR Attendance	 Completed
Real-Time Chat	 Completed
Production Deployment	 Completed
Future Improvements

Role-based access control (Admin/User)

Better UI/UX styling

Chat message timestamps

Image/file sharing in chat

Attendance analytics dashboard

Pagination for forum posts

 Conclusion

The Hackathon Management System successfully implements:

Full-stack architecture

Authentication & authorization

Real-time communication

Database persistence

Production deployment

Secure configuration management

The application demonstrates understanding of:

REST APIs

JWT authentication

WebSocket communication

Environment-based configuration

Full deployment workflow

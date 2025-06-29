# TO-DO-TASK-APPLICATION# Todo Task Management Web Application

This is a full-stack Todo Task Management web app built for the Katomaran Hackathon. It enables users to sign in via social login, manage personal tasks, share tasks, and get real-time updates.

## Features

- Social login with Google (OAuth 2.0)
- Task CRUD operations (Create, Read, Update, Delete)
- Share tasks with other users via email/username
- Real-time updates using WebSockets
- Pagination, sorting, and filtering of tasks (e.g., by priority, due date)
- Responsive design (mobile + desktop)
- Toast notifications for actions (create, update, delete)
- Error boundaries + basic offline support

## Tech Stack

- **Frontend**: React (Hosted on Vercel / Netlify)
- **Backend**: Node.js + Express (Hosted on Render / Railway)
- **Database**: MongoDB Atlas (NoSQL)
- **Real-time**: WebSockets (via Socket.io)
- **Auth**: Google OAuth 2.0 + JWT

## Architecture Diagram

+-----------------------+          +---------------------------+       +--------------------------+
|  React Frontend (Vercel|  <--->   |  Node.js Backend (Render / | <-->  | Database (MongoDB Atlas / |
|  / Netlify / Firebase) | WebSocket|  Express API Server)       | REST  | Supabase / Neon etc.)     |
+-----------------------+          +---------------------------+       +--------------------------+
         |                                      |                                   
         | OAuth 2.0 Login (Google/GitHub)      |                                   
         +------------------------------------->|                                   
         | <----------------------------------- | (JWT Token)                       
         |                                      |                                   
         | <----------------------------------->| Real-time updates                 
         |                                      | <-------------------------------> 
         |                                      | (WebSocket / SSE)                


## Assumptions

- Only Google OAuth is implemented for simplicity, though the spec mentioned GitHub/Facebook as options.
- Real-time updates use WebSocket via Socket.io rather than SSE.
- Email invitations for sharing tasks are simulated — no real email sending implemented (uses username lookup).



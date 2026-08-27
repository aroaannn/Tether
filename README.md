# Tether

A full-stack social media application where users can connect, share posts and stories, discover people, and chat in real time.

<p align="center">

[<img src="https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black" height="22">](https://react.dev/)
[<img src="https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white" height="22">](https://vite.dev/)
[<img src="https://img.shields.io/badge/Redux-764ABC?style=flat&logo=redux&logoColor=white" height="22">](https://redux-toolkit.js.org/)
[<img src="https://img.shields.io/badge/Tailwind-06B6D4?style=flat&logo=tailwindcss&logoColor=white" height="22">](https://tailwindcss.com/)
[<img src="https://img.shields.io/badge/Node.js-339933?style=flat&logo=nodedotjs&logoColor=white" height="22">](https://nodejs.org/)
[<img src="https://img.shields.io/badge/Express-000000?style=flat&logo=express&logoColor=white" height="22">](https://expressjs.com/)
[<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white" height="22">](https://www.mongodb.com/)
[<img src="https://img.shields.io/badge/Clerk-6C47FF?style=flat&logo=clerk&logoColor=white" height="22">](https://clerk.com/)

</p>

##  Features

*  User authentication with Clerk
*  User profiles and profile customization
*  Follow and connection system
*  Create and like posts
*  24-hour disappearing stories
*  Real-time one-to-one messaging
*  Image uploads and media handling
*  Notifications and background jobs
*  Email notifications

##  Tech Stack

**Frontend**

* React + Vite
* Redux Toolkit
* React Router
* Tailwind CSS
* Clerk
* Axios

**Backend**

* Node.js
* Express.js
* MongoDB + Mongoose
* Clerk
* Multer
* ImageKit
* Inngest
* Nodemailer

---

##  System Architecture

```mermaid
flowchart LR
    A[User] --> B[React + Vite]
    B --> C[Redux Toolkit]
    B --> D[Express API]

    D --> E[Clerk Auth]
    D --> F[Controllers]
    F --> G[(MongoDB)]

    F --> H[ImageKit]
    D --> I[Inngest]
    I --> J[Nodemailer]

    D -. Real-time .-> B
```

### Application Flow

```mermaid
flowchart TD
    A[User Login] --> B[Clerk Authentication]
    B --> C[React Application]
    C --> D[Express API]
    D --> E[Authentication Middleware]
    E --> F[Controllers]
    F --> G[(MongoDB)]

    C --> H[Create Post / Story]
    H --> D

    C --> I[Send Message]
    I --> D
    D --> J[SSE]
    J --> C
```

---

##  Project Structure

```text
Tether/
├── client/          # React frontend
│   └── src/
│       ├── components/
│       ├── features/
│       ├── pages/
│       ├── api/
│       └── App.jsx
│
├── server/          # Express backend
│   ├── configs/
│   ├── controllers/
│   ├── middlewares/
│   ├── models/
│   ├── routes/
│   ├── inngest/
│   └── server.js
│
└── README.md
```

---

##  Installation

### 1. Clone the repository

```bash
git clone https://github.com/aroaannn/Tether.git
cd Tether
```

### 2. Setup Backend

```bash
cd server
npm install
```

Create `server/.env`:

```env
PORT=4000
MONGODB_URI=your_mongodb_uri
CLERK_SECRET_KEY=your_clerk_secret_key
IMAGEKIT_PUBLIC_KEY=your_imagekit_public_key
IMAGEKIT_PRIVATE_KEY=your_imagekit_private_key
IMAGEKIT_URL_ENDPOINT=your_imagekit_url
INNGEST_EVENT_KEY=your_inngest_event_key
INNGEST_SIGNING_KEY=your_inngest_signing_key
```

Run the server:

```bash
npm run server
```

### 3. Setup Frontend

Open another terminal:

```bash
cd client
npm install
```

Create `client/.env`:

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_BASEURL=http://localhost:4000
```

Run the frontend:

```bash
npm run dev
```

---

##  Real-Time Messaging

Tether uses **Server-Sent Events (SSE)** for real-time messaging.

```text
User A
   ↓
React Client
   ↓
Express API
   ↓
MongoDB
   ↓
SSE Connection
   ↓
React Client
   ↓
User B
```

This allows new messages to be pushed to connected users without repeatedly refreshing or polling the server.

---

##  Future Improvements

* Group chats
* Comments and post sharing
* Push notifications
* Typing indicators
* Online/offline status
* Advanced search

---

##  Author

**Aroan Victor**


# JWT Authentication + Notes CRUD Application

A full-stack Notes Management application built using **React**, **Node.js**, **Express**, **MongoDB Atlas**, **JWT Authentication**, and **bcrypt.js**.

The application allows users to register, log in securely using JSON Web Tokens (JWT), and perform Create, Read, Update, and Delete (CRUD) operations on their personal notes.

---

# Features

## User Authentication
- User Registration
- User Login
- Password Hashing using bcrypt.js
- JWT Token Authentication
- Protected API Routes
- Secure Logout

---

## Notes Management

Authenticated users can:

- Create Notes
- View Their Own Notes
- Edit Notes
- Delete Notes

Each user's notes are private and cannot be accessed by other users.

---

# Technologies Used

## Frontend

- React.js
- React Hooks
- CSS
- Fetch API

---

## Backend

- Node.js
- Express.js
- MongoDB Atlas
- Mongoose
- JSON Web Token (JWT)
- bcrypt.js
- dotenv
- CORS

---

# Project Structure

```
project/
│
├── client/
│   ├── src/
│   │   ├── App.jsx
│   │   ├── App.css
│   │   └── main.jsx
│
├── server/
│   ├── index.js
│   ├── .env
│   ├── package.json
│
└── README.md
```

---

# Installation

## Step 1

Clone the repository

```bash
git clone https://github.com/yourusername/jwt-notes-app.git
```

---

## Step 2

Navigate to backend

```bash
cd server
```

Install dependencies

```bash
npm install
```

---

## Step 3

Create a `.env` file

```env
PORT=5000

MONGO_URI=your_mongodb_atlas_connection_string

JWT_SECRET=your_secret_key
```

Example

```env
PORT=5000

MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/notesdb

JWT_SECRET=mysecret123
```

---

## Step 4

Run Backend

```bash
npm start
```

or

```bash
node index.js
```

Backend runs at

```
http://localhost:5000
```

---

## Step 5

Open another terminal

Navigate to frontend

```bash
cd client
```

Install dependencies

```bash
npm install
```

Run React application

```bash
npm run dev
```

Frontend runs at

```
http://localhost:5173
```

---

# API Endpoints

## Register

```
POST /register
```

Body

```json
{
    "username":"john",
    "password":"123456"
}
```

Response

```json
{
    "message":"Account created! You can now log in."
}
```

---

## Login

```
POST /login
```

Body

```json
{
    "username":"john",
    "password":"123456"
}
```

Response

```json
{
    "token":"JWT_TOKEN"
}
```

---

## Get Notes

```
GET /notes
```

Headers

```
Authorization: Bearer JWT_TOKEN
```

---

## Create Note

```
POST /notes
```

Headers

```
Authorization: Bearer JWT_TOKEN
```

Body

```json
{
    "text":"My first note"
}
```

---

## Update Note

```
PUT /notes/:id
```

Headers

```
Authorization: Bearer JWT_TOKEN
```

Body

```json
{
    "text":"Updated note"
}
```

---

## Delete Note

```
DELETE /notes/:id
```

Headers

```
Authorization: Bearer JWT_TOKEN
```

---

# Database Collections

## Users Collection

```json
{
    "_id":"",
    "username":"john",
    "password":"hashed_password"
}
```

---

## Notes Collection

```json
{
    "_id":"",
    "username":"john",
    "text":"Sample Note",
    "createdAt":"",
    "updatedAt":""
}
```

---

# Security Features

- Passwords are encrypted using bcrypt.js.
- JWT Authentication secures all protected routes.
- User-specific authorization ensures users can only access their own notes.
- MongoDB Atlas securely stores application data.
- Environment variables protect sensitive credentials.

---

# Workflow

```
User Registration
        │
        ▼
Password Hashing
        │
        ▼
Store User in MongoDB
        │
        ▼
User Login
        │
        ▼
JWT Token Generated
        │
        ▼
Frontend Stores Token
        │
        ▼
Protected CRUD Operations
```

---

# Future Enhancements

- Forgot Password
- Reset Password via Email
- Search Notes
- Categories/Tags
- Rich Text Editor
- Dark Mode
- User Profile
- Image Attachments
- Pagination
- Refresh Tokens
- Docker Deployment

---

# Dependencies

Backend

```json
{
  "bcryptjs": "^2.x",
  "cors": "^2.x",
  "dotenv": "^16.x",
  "express": "^4.x",
  "jsonwebtoken": "^9.x",
  "mongoose": "^8.x"
}
```

Frontend

```json
{
  "react": "^19.x",
  "react-dom": "^19.x",
  "vite": "^7.x"
}
```

---

# Author

**Tejas**

Bachelor of Computer Applications (BCA)

---

# License

This project is developed for educational and learning purposes.

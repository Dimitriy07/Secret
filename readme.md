# 🔐 Secure Authentication App with Node.js, Express, and MongoDB

## 📌 Overview

This application demonstrates secure user authentication using **Node.js**, **Express**, **MongoDB**, and **Passport.js**. It supports:

- Local authentication with **username and password**
- **Google OAuth 2.0** authentication
- **Session-based authentication** for persistent login
- **Secure password storage** with `passport-local-mongoose`

## 🚀 Technologies Used

- **Node.js**
- **Express.js**
- **MongoDB + Mongoose**
- **EJS (Embedded JavaScript Templates)**
- **Passport.js (local + Google OAuth)**
- **dotenv** for environment variable management

## 📂 Project Setup

### 1️⃣ Install Dependencies

```sh
npm install express body-parser ejs mongoose passport passport-local passport-local-mongoose express-session dotenv passport-google-oauth20 mongoose-findorcreate
```

### 2️⃣ Create a `.env` File

Inside the project directory, create a `.env` file and add your Google API credentials:

```env
CLIENT_ID=your-google-client-id
CLIENT_SECRET=your-google-client-secret
```

### 3️⃣ Run MongoDB Locally

Ensure MongoDB is running locally on port `27017`. If using a cloud database, update the connection string in `mongoose.connect()`.

### 4️⃣ Start the Server

```sh
node app.js
```

Server runs on **http://localhost:3000**.

## 🔑 Security Features

### 1️⃣ **Environment Variables for Secrets**

- Stores sensitive information (`CLIENT_ID`, `CLIENT_SECRET`) in `.env` instead of hardcoding them.
- Uses `dotenv` to load environment variables.

### 2️⃣ **Session-Based Authentication**

- Uses `express-session` for session management.
- Ensures users stay logged in between page reloads.

### 3️⃣ **Secure Password Storage**

- `passport-local-mongoose` automatically hashes and salts passwords before storing them.

### 4️⃣ **OAuth 2.0 Authentication with Google**

- Users can sign in using Google credentials securely.

### 5️⃣ **Logout and Session Management**

- Implements a secure logout route (`/logout`) to destroy user sessions.

## 🔄 Routes

| Route                  | Method | Description                        |
| ---------------------- | ------ | ---------------------------------- |
| `/`                    | GET    | Home page                          |
| `/register`            | GET    | Registration form                  |
| `/register`            | POST   | Registers a new user               |
| `/login`               | GET    | Login form                         |
| `/login`               | POST   | Authenticates user                 |
| `/logout`              | GET    | Logs out user                      |
| `/secrets`             | GET    | Displays secrets (protected route) |
| `/submit`              | GET    | Submit secret (requires login)     |
| `/auth/google`         | GET    | Initiates Google OAuth login       |
| `/auth/google/secrets` | GET    | Google OAuth callback              |

## 🛠 Future Enhancements

- ✅ Implement **JWT authentication** for API-based authentication.
- ✅ Add **password reset functionality**.
- ✅ Improve error handling and validation.

---

💡 **Built with security in mind!** If you found this useful, ⭐ the repo! Happy coding! 🚀

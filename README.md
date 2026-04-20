# Overview

Multi Messenger Application is a full-stack system that provides a centralized platform for sending messages across multiple communication services. The project consists of a Spring Boot backend and a frontend interface (React-based) that allows users to interact with the system.

The backend processes user requests, identifies the selected platform, retrieves the mapped platform account from the database, and sends the message using external APIs such as Telegram and Discord. The frontend provides a user-friendly interface for login and message sending.

# Features
1.Centralized full-stack messaging system
2.User-friendly frontend interface for interaction
3.REST API for authentication and message sending
4.Telegram message delivery using Telegram Bot API
5.Discord message delivery using JDA
6.MySQL-based storage for user-platform mappings
7.Modular backend architecture (controller, service, repository, model)
8.Frontend-backend API integration using HTTP requests
9.Scalable design for adding platforms like Slack and WhatsApp

# Technologies Used
Backend
Java 17
Spring Boot
Spring Web MVC
Spring Data JPA
MySQL
H2 Database
JDA (Java Discord API)
Maven
Frontend
React
HTML
CSS
JavaScript
Axios (for API calls)

# Project Structure

multi-messenger-project/
```text
│
├── backend/
│   └── src/main/java/com/project/multimessenger
│       │
│       ├── controller
│       │   ├── AuthController.java
│       │   └── MessageController.java
│       │
│       ├── dto
│       │   ├── LoginRequest.java
│       │   └── MessageRequest.java
│       │
│       ├── model
│       │   ├── Platform.java
│       │   ├── User.java
│       │   └── UserPlatformAccount.java
│       │
│       ├── repository
│       │   ├── PlatformRepository.java
│       │   ├── UserRepository.java
│       │   └── UserPlatformAccountRepository.java
│       │
│       ├── service
│       │   ├── DiscordService.java
│       │   ├── MessageService.java
│       │   └── UserService.java
│       │
│       └── MultimessengerApplication.java
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── App.jsx
│   │   └── main.jsx
│   │
│   └── package.json

# How the Project Works
User interacts with the frontend interface
Frontend sends API request to backend
Backend receives and processes the request
Backend checks the selected platform
It looks up the platform in the platforms table
It finds the user’s mapped platform account in the user_platform_accounts table
Based on the platform:
Sends the message using Telegram Bot API
Sends the message using Discord JDA
Backend returns response to frontend
Frontend displays success or error message to user

---

# Installation Instructions

## Prerequisites

# Backend

* Java 17
* Maven
* MySQL

### Frontend

* Node.js
* npm

## Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/multi-messenger-project.git
cd multi-messenger-project
```


## Step 2: Backend Setup

### Navigate to backend folder

```bash
cd backend
```


### Add API Tokens

```properties
telegram.bot.token=your_telegram_token
discord.bot.token=your_discord_token
```

### Create Database

Run this in MySQL:

```sql
CREATE DATABASE multimessenger;
```

### Run Backend

```bash
mvn spring-boot:run
```

Backend will start at:

```text
http://localhost:8080
```

---

## Step 3: Frontend Setup

### Navigate to frontend folder

```bash
cd ../frontend
```

### Install Dependencies

```bash
npm install
```

### Start Frontend

```bash
npm run dev
```

Frontend will run at:

```text
http://localhost:5173
```

---

## Step 4: Verify Application

### Test Backend

Open browser or Postman:

```http
GET http://localhost:8080/message/test
```

Expected output:

```text
Backend is working
```

---

## Step 5: Insert Sample Data

### Insert Platforms

```sql
INSERT INTO platforms (platform_name) VALUES ('Telegram');
INSERT INTO platforms (platform_name) VALUES ('Discord');
INSERT INTO platforms (platform_name) VALUES ('Slack');
INSERT INTO platforms (platform_name) VALUES ('WhatsApp');
```

### Insert User

```sql
INSERT INTO users (full_name, email, phone, created_at)
VALUES ('Test User', 'test@example.com', '9999999999', NOW());
```

## Step 6: Test APIs

### Login

```http
POST http://localhost:8080/auth/login
```

Body:

```json
{
  "email": "admin",
  "password": "1234"
}
```



### Send Message

```http
POST http://localhost:8080/message/send
```

Body:

```json
{
  "userId": 1,
  "platform": "Telegram",
  "message": "Hello from Multi Messenger"
}



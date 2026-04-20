Overview

Multi Messenger Project is a full-stack messaging application that provides a single interface for sending messages through multiple communication platforms. The system consists of:

a Spring Boot backend for API handling, business logic, database access, and third-party platform integration
a React frontend for user login and message sending

The project currently supports:

Telegram
Discord

The following platforms are included for future extension:

Slack
WhatsApp

This project is useful for demonstrating full-stack development, REST APIs, database integration, external API usage, and platform-based message routing.

Project Structure
multi-messenger-project/
│
├── backend/
│   ├── src/
│   ├── pom.xml
│   ├── mvnw
│   └── mvnw.cmd
│
├── frontend/
│   ├── src/
│   ├── package.json
│   ├── vite.config.js
│   └── index.html
│
└── README.md

Tech Stack
Frontend
React
Vite
JavaScript
Fetch API
Backend
Java 17
Spring Boot
Spring Web MVC
Spring Data JPA
Maven
MySQL
JDA (Discord integration)
Telegram Bot API
Features
User login interface
Send messages using one unified dashboard
Platform selection for message delivery
Backend validation of request data
Telegram integration
Discord integration
Database-based platform and user account mapping
Extensible design for adding more platforms
How It Works
User opens the frontend and logs in.
After login, the dashboard appears.
User enters:
message text
user ID
target platform
Frontend sends the request to the backend.
Backend validates the request.
Backend checks:
whether the platform exists in the database
whether the user has a mapped account for that platform
Based on the selected platform:
Telegram message is sent through Telegram Bot API
Discord message is sent through Discord bot integration
Response is returned to the frontend.

Installation Instructions

Make sure the following are installed on your system:
Java 17
Node.js (version 18 or above)
MySQL Server
Maven (or use the provided Maven wrapper)
Git
Any IDE (VS Code, IntelliJ, Eclipse)

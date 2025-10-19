# 01Blog - Student Learning Platform

A fullstack social blogging platform where students share their learning experiences, discoveries, and progress. Built with Spring Boot and Angular.

## Features

### Core Features
- User authentication with role-based access (student/admin)
- Public user profiles ("blocks") displaying all posts
- Create, edit, and delete posts with media (images/videos)
- Like and comment on posts in real-time
- Subscribe to other users and receive notifications
- Report inappropriate content or users

### Admin Features
- Moderation dashboard for users, posts, and reports
- Ban/delete users and remove posts
- View and manage user reports
- Basic analytics on posts and reported users

## Tech Stack

- **Backend:** Spring Boot, Spring Security, JWT, JPA/Hibernate, PostgreSQL
- **Frontend:** Angular, Angular Material, Bootstrap
- **Database:** PostgreSQL
- **Storage:** File system or AWS S3

## Prerequisites

- Java 11+
- Node.js 16+
- PostgreSQL 12+
- Git

## Quick Start

### Backend Setup

```bash
cd backend
# Configure application.properties with database credentials
mvn clean install
mvn spring-boot:run
```

Backend runs on `http://localhost:8080`

### Frontend Setup

```bash
cd frontend
npm install
ng serve
```

Frontend runs on `http://localhost:4200`

## Project Structure

```
01blog/
├── backend/
│   ├── src/main/java/
│   │   ├── config/        # Security, JWT config
│   │   ├── controller/    # REST endpoints
│   │   ├── service/       # Business logic
│   │   ├── repository/    # Database access
│   │   └── entity/        # JPA entities
│   └── resources/
│       └── application.properties
├── frontend/
│   ├── src/app/
│   │   ├── components/    # UI components
│   │   ├── services/      # API communication
│   │   └── models/        # TypeScript interfaces
│   └── index.html
└── README.md
```

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/auth/register` | POST | User registration |
| `/api/auth/login` | POST | User login |
| `/api/posts` | GET/POST | Retrieve or create posts |
| `/api/posts/{id}` | PUT/DELETE | Update or delete post |
| `/api/users/{id}` | GET | View user profile |
| `/api/users/{id}/subscribe` | POST/DELETE | Subscribe/unsubscribe |
| `/api/posts/{id}/comments` | POST | Add comment |
| `/api/comments/{id}` | DELETE | Delete comment |
| `/api/reports` | POST | Submit report |
| `/api/admin/reports` | GET | View reports (admin only) |
| `/api/admin/users` | GET | View all users (admin only) |
| `/api/admin/users/{id}` | DELETE | Delete user (admin only) |
| `/api/admin/posts/{id}` | DELETE | Delete post (admin only) |

## Authentication

Uses JWT tokens for stateless authentication. Include token in request headers:

```
Authorization: Bearer <token>
```

Role-based access control protects admin endpoints.

## File Upload

Media uploads are stored securely using either the file system or AWS S3 with preview generation.

## Running Tests

### Backend Tests
```bash
mvn test
```

### Frontend Tests
```bash
ng test
```

## Deployment

Refer to individual backend/frontend deployment guides for production setup.

## License

Educational Project - Learning Purposes Only
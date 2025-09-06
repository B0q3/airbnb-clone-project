# Airbnb Clone Project

## Overview

This project is a full-stack clone of the Airbnb platform. It aims to replicate the core features of Airbnb, such as user registration, property listings, booking functionality, reviews, and payments. The project is designed to deepen our understanding of full-stack development using modern tools and best practices.

### Project Goals

- Build a scalable and modular full-stack web application.
- Implement real-world features like user authentication, property listings, and bookings.
- Gain hands-on experience with backend, frontend, and database technologies.
- Practice version control and team collaboration using Git and GitHub.

### Tech Stack

- **Backend**: Django
- **API**: GraphQL
- **Database**: PostgreSQL
- **Frontend**: React
- **DevOps**: Docker, GitHub Actions

## Team Roles

### 1. Backend Developer
Responsible for developing the server-side logic, APIs, and integrating the database. Works primarily with Django and GraphQL to build robust and secure endpoints.

### 2. Frontend Developer
Designs and implements the user interface using React. Ensures the application is responsive, accessible, and communicates properly with the backend APIs.

### 3. Database Administrator (DBA)
Designs and manages the PostgreSQL database schema. Ensures data integrity, optimizes queries, and handles backups and migrations.

### 4. DevOps Engineer
Handles deployment, environment configuration, and CI/CD pipelines using tools like Docker and GitHub Actions. Ensures reliability and scalability of the system.

### 5. Project Manager
Coordinates the development process, tracks progress, and ensures the project stays on schedule. Manages communication among team members and stakeholders.

## Technology Stack

### 1. Django
A high-level Python web framework used for building the backend logic and APIs of the application. Django helps manage user authentication, request handling, and database interaction securely and efficiently.

### 2. GraphQL
A flexible API query language used in place of traditional REST APIs. It allows the frontend to request exactly the data it needs, improving performance and reducing over-fetching.

### 3. PostgreSQL
A powerful open-source relational database system used to store all structured data, including users, listings, bookings, reviews, and payments.

### 4. React
A JavaScript library for building dynamic and interactive user interfaces. It connects to the backend via GraphQL and renders components based on user actions and data.

### 5. Docker
A containerization tool used to package the application and its dependencies into portable containers, ensuring consistent environments across development and production.

### 6. GitHub Actions
A CI/CD tool integrated with GitHub that automates testing, building, and deployment pipelines to streamline development workflows and maintain code quality.

## Database Design

### 🧑 Users
Fields:
- `id` (UUID)
- `name`
- `email`
- `password`
- `role` (guest or host)

Description:
Each user can act as a guest or a host. Hosts can create property listings, while guests can book properties.

---

### 🏠 Properties
Fields:
- `id` (UUID)
- `title`
- `description`
- `location`
- `price_per_night`
- `host_id` (Foreign Key → Users)

Description:
A property belongs to a host (user). A host can have multiple properties listed.

---

### 📅 Bookings
Fields:
- `id` (UUID)
- `user_id` (Foreign Key → Users)
- `property_id` (Foreign Key → Properties)
- `check_in_date`
- `check_out_date`

Description:
Each booking is made by a guest for a specific property and includes check-in and check-out dates.

---

### ⭐ Reviews
Fields:
- `id` (UUID)
- `user_id` (Foreign Key → Users)
- `property_id` (Foreign Key → Properties)
- `rating` (1–5)
- `comment`

Description:
Guests can leave a review for a property they booked. Each review is linked to both the user and the property.

---

### 💳 Payments
Fields:
- `id` (UUID)
- `booking_id` (Foreign Key → Bookings)
- `amount`
- `status` (e.g., pending, completed)
- `payment_date`

Description:
Each payment is associated with a booking and includes details like amount and status.

---

### 🔗 Entity Relationships Summary
- A **User** can have many **Properties** (if host)
- A **Property** can have many **Bookings**
- A **Booking** is linked to one **User** and one **Property**
- A **Booking** has one **Payment**
- A **User** can leave multiple **Reviews** for different **Properties**

## Feature Breakdown

### 1. User Management
Allows users to register, log in, and manage their profiles. This feature handles authentication and authorization, ensuring secure access to user-specific data.

### 2. Property Management
Hosts can create, update, and delete property listings with details like location, pricing, and amenities. This enables the core functionality of displaying available properties for booking.

### 3. Booking System
Enables guests to book properties by selecting dates and confirming availability. The system manages booking statuses, cancellations, and date conflicts to maintain accurate schedules.

### 4. Review and Rating System
Guests can leave reviews and ratings on properties they have stayed at. This feedback helps future users make informed decisions and promotes trust within the platform.

### 5. Payment Processing
Handles secure payment transactions for bookings, including tracking payment statuses and histories. This ensures smooth financial operations between guests and hosts.

### 6. Notifications
Sends email or in-app notifications for booking confirmations, payment updates, and review requests. This keeps users informed and engaged throughout their interaction with the platform.

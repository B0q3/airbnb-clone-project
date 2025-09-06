# Airbnb Clone Project

## Project Overview
The Airbnb Clone Project is a full-stack application simulating a booking platform like Airbnb. The goal is to develop a scalable backend using Django, PostgreSQL, and GraphQL, focusing on security, database design, and CI/CD pipeline automation.

## Team Roles
- **Backend Developer:** Develops APIs, handles business logic, and integrates with databases.
- **Database Administrator:** Designs and maintains the database structure ensuring data integrity and performance.
- **Frontend Developer:** Builds the user interface and interacts with backend services.
- **QA Engineer:** Tests the application to ensure it meets requirements and is free of bugs.
- **DevOps Engineer:** Sets up CI/CD pipelines, deployment automation, and manages infrastructure.

## Technology Stack
- **Django:** Web framework used to build the backend APIs.
- **PostgreSQL:** Relational database system to store user, booking, and property data.
- **GraphQL:** Query language used to fetch and manipulate data efficiently.
- **Docker:** Containerizes the application for consistent environments.
- **GitHub Actions:** Automates testing and deployment pipelines.

## Database Design
### Entities and Fields:
- **Users:** user_id, username, email, password, role  
- **Properties:** property_id, owner_id (User), title, description, price, location  
- **Bookings:** booking_id, user_id, property_id, start_date, end_date, status  
- **Reviews:** review_id, user_id, property_id, rating, comment, date  
- **Payments:** payment_id, booking_id, amount, payment_date, payment_method  

### Relationships:
- A User can own multiple Properties.
- A User can make multiple Bookings.
- Each Booking is linked to one Property.
- Users can leave multiple Reviews for Properties.
- Each Payment corresponds to one Booking.

## Feature Breakdown
- **User Management:** Allows users to register, login, and manage their profiles.
- **Property Management:** Owners can list, update, and remove properties.
- **Booking System:** Users can search for properties, book stays, and manage bookings.
- **Review System:** Users can leave feedback and ratings for properties.
- **Payment Processing:** Secure payment handling for bookings.

## API Security
- **Authentication:** Users must log in to access protected endpoints using JWT tokens.
- **Authorization:** Role-based access control ensures users can only perform allowed actions.
- **Rate Limiting:** Protects APIs from abuse by limiting the number of requests per time window.
- Security protects sensitive data like user information and payment details.

## CI/CD Pipeline
Continuous Integration and Continuous Deployment (CI/CD) automate building, testing, and deploying the project to ensure rapid and reliable releases. Tools such as GitHub Actions run tests on every commit, and Docker ensures consistent deployment environments.

---


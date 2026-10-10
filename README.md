# Car Rental Web Platform

A full-stack car rental web application built using **Spring Boot, React.js, MySQL, and JWT authentication**. The platform simplifies the car rental process by connecting customers, rental agencies, and administrators through a secure, responsive, and user-friendly interface.

The application enables customers to search and book vehicles, agencies to manage car listings and rental requests, and administrators to oversee users, agencies, and platform activities.

## Table of Contents

- [Features](#features)
- [User Roles](#user-roles)
- [Technology Stack](#technology-stack)
- [System Requirements](#system-requirements)
- [Project Structure](#project-structure)
- [Installation and Setup](#installation-and-setup)
- [Database Configuration](#database-configuration)
- [Application URLs](#application-urls)
- [Deployment](#deployment)

## Features

- User authentication and authorization using JWT.
- Role-based access control for customers, agencies, and administrators.
- Car listing management with support for multiple images.
- Search and filtering by brand, category, model, and price.
- Rental booking with date, location, and driver preferences.
- Automatic availability checks to help prevent double bookings.
- Rental request approval and rejection by agencies.
- Booking status tracking and rental history.
- Vehicle ratings and customer feedback.
- Document submission and verification for customers and agencies.
- Administrative dashboard for managing users, agencies, feedback, and platform statistics.
- Responsive user interface for desktop and mobile devices.

## User Roles

### 1. Customer

Customers can:

- Register, log in, and manage their accounts.
- Browse, search, and filter available vehicles.
- View car details, images, pricing, and ratings.
- Create rental bookings by specifying dates and preferences.
- Track booking status and view rental history.
- Rate vehicles after completing rentals.
- Submit identity documents for verification.

### 2. Agency

Agencies can:

- Register and submit documents for verification.
- Add, update, and delete car listings.
- Upload up to four images for each vehicle.
- Manage vehicle details and availability.
- View incoming rental requests.
- Approve or reject rental bookings.
- Track booking statuses and rental history.

### 3. Administrator

Administrators can:

- Manage customer and agency accounts.
- Verify or suspend user accounts.
- Review agency verification requests and submitted documents.
- Monitor rental activity and platform statistics.
- Manage customer feedback and related responses.

## Technology Stack

| Layer | Technology |
|---|---|
| Frontend | React.js |
| Styling | Tailwind CSS |
| Build Tool | Vite |
| Backend | Java, Spring Boot |
| Database | MySQL |
| Authentication | JSON Web Tokens (JWT) |
| Build Management | Maven |
| Frontend Deployment | Netlify |
| Backend Deployment | Render |

## System Requirements

### Functional Requirements

- Support three user roles: Customer, Agency, and Administrator.
- Provide vehicle listing, searching, and filtering functionality.
- Support rental booking creation and status management.
- Provide role-specific dashboards and permissions.
- Support document verification and customer feedback.
- Provide a responsive user interface.

### Non-Functional Requirements

- Secure authentication and role-based authorization.
- Encrypted password storage.
- HTTPS for secure communication in production.
- Efficient database queries and appropriate indexing.
- Responsive performance across different screen sizes.
- Architecture that can be optimized and scaled as usage increases.

## Project Structure

```text
car-rental/
├── backend/
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       │   └── com/
│   │       │       └── rental/
│   │       │           ├── controller/
│   │       │           ├── service/
│   │       │           ├── entity/
│   │       │           └── repository/
│   │       └── resources/
│   │           └── schema.sql
│   └── pom.xml
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── routes/
│   │   └── api/
│   └── package.json
│
└── README.md
```

## Installation and Setup

### Prerequisites

Make sure the following tools are installed:

- Java Development Kit (JDK)
- Maven
- Node.js and npm
- MySQL Server
- Git

### 1. Clone the Repository

```bash
git clone <repository-url>
cd car-rental
```

Replace `<repository-url>` with your GitHub repository URL.

### 2. Configure the Database

Create a MySQL database named `car_rental`.

```sql
CREATE DATABASE car_rental;
```

Import the database schema from `backend/src/main/resources/schema.sql`, if provided.

Configure your database connection settings in the Spring Boot application configuration file. Set the database URL, username, and password using your local configuration or environment variables.

### 3. Run the Backend

Navigate to the backend directory:

```bash
cd backend
```

Build the application:

```bash
./mvnw clean install
```

Start the Spring Boot server:

```bash
./mvnw spring-boot:run
```

On Windows, use `mvnw.cmd` instead of `./mvnw` when required.

The backend runs at:

`http://localhost:8000`

Ensure that the configured Spring Boot server port is `8000`; otherwise, use the port specified in your configuration.

### 4. Run the Frontend

Open a new terminal and navigate to the frontend directory:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The frontend runs at:

`http://localhost:5173`

Ensure that the frontend API configuration points to the correct backend URL.

## Database Configuration

The application uses MySQL for storing application data, including:

- User and agency information.
- Vehicle listings and details.
- Rental orders and booking statuses.
- Ratings and customer feedback.
- Verification and related application records.

Configure the database connection using the appropriate Spring Boot properties. Avoid committing database credentials, JWT secrets, or other sensitive configuration values to version control.

## Application URLs

| Component | URL |
|---|---|
| Frontend | `http://localhost:5173` |
| Backend | `http://localhost:8000` |
| Database | MySQL server configured locally |

## Deployment

The application is deployed using the following services:

- **Frontend:** Netlify
- **Backend:** Render
- **Database:** MySQL

For production deployment, configure the frontend to communicate with the deployed backend URL. Set database credentials and JWT secrets through environment variables, enable HTTPS, and configure appropriate CORS policies.

## Future Enhancements

- Online payment integration.
- Email and SMS booking notifications.
- Advanced analytics and reporting.
- Map-based vehicle discovery.
- Automated booking reminders.
- Improved monitoring, caching, and performance optimization.
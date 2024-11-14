# Airline Management System

A comprehensive Airline Management System designed using microservices architecture, enabling efficient handling of various airline operations such as user authentication, flight bookings, flight searches, and automated notifications. This system ensures scalability, maintainability, and flexibility by decomposing functionalities into separate, independently deployable services. Built with Node.js and Express,seamless database interactions using Sequelize ORM with MySQL, and reliable message queuing through RabbitMQ.

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
- [Microservices](#microservices)

## Overview

The Airline Management System is a feature-rich application developed to streamline and automate various aspects of airline operations. By leveraging a microservices-based architecture, each core functionality is encapsulated within its own service, promoting better organization, easier scalability, and simplified maintenance. The system encompasses user management, flight booking processes, comprehensive flight search capabilities, and automated email notifications for reminders and confirmations. This modular approach not only enhances the system's robustness but also facilitates continuous integration and deployment, ensuring that updates and new features can be rolled out with minimal downtime and maximum efficiency.

## Architecture

```
┌─────────────┐     ┌─────────────┐
│  API        │     │   Auth      │
│  Gateway    │────▶│   Service   │
└─────────────┘     └─────────────┘
      │
      │            ┌─────────────┐
      └───────────▶│  Booking    │
      │            │  Service    │
      │            └─────────────┘
      │
      │            ┌─────────────┐
      └───────────▶│  Flights    │
      │            │  Service    │
      │            └─────────────┘
      │
      │            ┌─────────────┐
      └───────────▶│  Reminder   │
                   │  Service    │
                   └─────────────┘
```

## Tech Stack

- **Node.js**: JavaScript runtime environment for building scalable server-side applications.
- **Express.js**: Fast, unopinionated, minimalist web framework for Node.js.
- **Sequelize ORM**: Promise-based Node.js ORM for Postgres, MySQL, MariaDB, SQLite, and Microsoft SQL Server, facilitating easy database interactions.
- **MySQL**: Open-source relational database management system for efficient data storage and retrieval.
- **RabbitMQ**: Robust message broker for handling asynchronous communication between services.
- **JSON Web Tokens (JWT)**: Secure method for transmitting information between parties as a JSON object, utilized for authentication.
- **dotenv**: Module to load environment variables from a `.env` file into `process.env`.
- **Morgan**: HTTP request logger middleware for Node.js.
- **Nodemon**: Utility that monitors for changes in the source code and automatically restarts the server.

## Prerequisites

- **Node.js** (v14 or higher)
- **MySQL** (v8 or higher)
- **RabbitMQ**
- **Git**

## Setup Instructions

Each microservice has its own detailed setup instructions. Click on the links below to view the setup guide for each service:

- [Auth Service](https://github.com/amansharma999/Auth_Service)
- [Booking Service](https://github.com/amansharma999/AirTicketBookingService)
- [Flights and Search Service](https://github.com/amansharma999/FlightsAndSearchService)
- [Reminder Service](https://github.com/amansharma999/ReminderService)
- [API Gateway](https://github.com/amansharma999/API_Gateway)

## Microservices

### Auth Service
- Handles user authentication and authorization.
- Manages user roles and permissions.
- Provides JWT token generation and validation.
- Handles user registration and login.

### Booking Service  
- Manages flight bookings.
- Handles booking creation and cancellation.
- Maintains booking history.
- Integrates with the Reminder Service for notifications.

### Flights and Search Service
- Manages the flights database.
- Provides flight search functionality.
- Handles flight CRUD operations.
- Maintains data for cities and airports.

### Reminder Service
- Handles email notifications.
- Manages booking reminders.
- Processes queue-based notifications.
- Integrates with external email service.

### API Gateway
- Routes requests to appropriate services.
- Handles request validation.
- Manages service discovery.
- Implements rate limiting.

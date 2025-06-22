# Airbnb-clone-project
The backend for the Airbnb Clone project is a robust and scalable application for managing user interactions, property listings, bookings, and payments. It supports various functionalities, ensuring a smooth experience for users and hosts. The project is built using Django, Django REST Framework, PostgreSQL, GraphQL, Celery, Redis, and Docker.

**Project Goals**
- Implement a secure system for user registration, authentication, and profile management.
- Develop features for property listing creation, updates, and retrieval.
- Create a booking mechanism for users to reserve properties and manage booking details.
- Integrate a payment system to handle transactions and record payment details.
- Allow users to leave reviews and ratings for properties.
- Ensure efficient data retrieval and storage through database optimizations.

## Team Roles
- **Backend software Developer**: Responsible for implementing software API endpoints, devising app architecture and database schemas, and implementing business logic.
- **Quality Assurance Engineer**: Ensures the application performs according to requirements, with no defects. Thoroughly tests all backend functionalities and ensures they meet quality standards.
- **Test Automation Engineer**: Writes automated test scripts that help determine which parts of the application are suitable for automation.
- **DevOps Engineer**: Facilitates deployment, monitoring, and scaling of backend services. Builds continuous integration and continuous delivery (CI/CD) pipelines for fast delivery.
- **Database Administrator**: Manages database design, indexing, and optimizations.

## Technology Stack
- **Django**: A high-level Python web framework used for building the RESTful API.
- **Django Rest framework**: Extends Django specifically for building RESTful APIs. It provides powerful tools for serialization, authentication, permissions, and API documentation. 
- **PostgreSQL**: A powerful open-source relational database management system that supports both SQL and NoSQL data storage features.
- **GraphQL**: Single endpoint query language and runtime for APIs. It allows for flexible and efficient querying of data.
- **Celery**: For handling asynchronous tasks such as sending notifications or processing payments.
- **Redis**: Serves as a cache and message broker. Used for caching and session management.
- **Docker**: Containerization tool for consistent development and deployment environments.
- **CI/CD Pipelines**: Automated pipelines for testing and deploying code changes.

## Database Design
- **Users** - A user can either be a guest or a host. All types of users have the following common fields: *user_id*, *user_name*, *user_type*, *email*, *password*.
  
- **Properties** - A property belongs to a host. Key property fields include the following: *property_id*, *host_id*, *property_type*, *property_description*, *property_status*.
  
- **Bookings** - A booking belongs to a guest and is made for a property owned by a host. Key booking fields include the following: *booking_id*, *property_id*, *guest_id*, *host_id*, *booking_status*.
  
- **Reviews** - A review is made by a guest(reviewer) for a particular property that belongs to a host(reviewee). Review entities have the following common fields: *review_id*, *reviewer_id*, *review*, *rating*, *property_id*.
  
- **Payments** - A payment is made by a guest(payer) for a booking they made. Payment entities have the following common fields: *payment_id*, *payer_id*, *booking_id*, *payment_type*, *amount*.

## Feature Breakdown
- #### User Management
Enables users to create accounts, log in securely, and manage their profiles with comprehensive verification systems. It establishes trust and safety within the platform by ensuring user identities are validated, reducing fraud, and increasing booking confidence.

- #### Property Management
Hosts can create detailed property listings with property type, description, pricing, and availability. This feature serves as the core inventory management system for all property listings.

- #### Booking System
Provides instant booking capabilities with real-time availability checking, pricing, and immediate confirmation for eligible properties. Guests can also update their bookings, including check-in and check-out details.

- #### Payment Processing
A comprehensive payment system that handles secure transactions and multiple payment methods, and automated host payouts. This feature ensures financial security for both parties by holding payments until successful check-in and providing dispute resolution mechanisms.

- #### Review System
Allows guests to review and rate properties with a star rating and written feedback. It also allows guests to manage their reviews and hosts to review their guests.

## API Security
Security is crucial for user data protection, payments, and overall system stability. Firstly, the platform will collect personal and sensitive user information, so a data breach could result in identity theft. Additionally, property and booking information reveal users' travel plans, home addresses, and absence periods, making security breaches potentially dangerous for personal safety. Therefore, protecting this data is essential for maintaining user trust and complying with privacy regulations. Secondly, payment security is fundamental to platform viability since users must trust the system with their financial information and significant transaction amounts. A comprehensive payment security ensures transaction integrity and prevents financial fraud. To ensure that the application is well-secured, here are some security measures that will be implemented:

#### Authentication & Identity Management
- OAuth 2.0 integration to allow social login with Google, Facebook, Apple for secure third-party authentication.
- Password Security: minimum complexity requirements, and breach detection.
- Session Management: Secure session handling with automatic logout, concurrent session limits, and suspicious activity detection

#### Authorization & Access Control
- Role-Based Access Control (RBAC): Distinct permissions for guests, hosts, admins etc.
- Resource-Level Permissions: Fine-grained access control ensuring users can only access their bookings, properties, and data.
- Data Segregation: Tenant isolation ensuring user data is properly compartmentalized.

#### Rate Limiting
- API Rate Limiting: Redis-based rate limiting with different tiers for authenticated vs. anonymous users
- Progressive Rate Limiting: Increasing delays for repeated failed attempts (login, password reset, booking)
- Endpoint-Specific Limits: Different rate limits for search, booking, payment, and messaging endpoints

#### Data Encryption & Protection
- Encryption at rest, encryption in transit and database encryption

#### Payment Security
- Tokenization: Credit card tokenization to avoid storing sensitive payment data
- 3D Secure Authentication: Enhanced cardholder verification for online transactions
- Secure Payment Processing: End-to-end encryption for payment flows with minimal data exposure

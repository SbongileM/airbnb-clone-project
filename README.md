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
- **Users** - A user can either be a guest or a host. All types of users have the following common fields:
  -*user_id* 
  -*user_name*
  -*user_type*
  -*email*
  -*password*
  
- **Properties** - A property belongs to a host. Key property fields include the following:
  -*property_id*
  -*host_id*
  -*property_type*
  -*property_description*
  -*property_status*
  
- **Bookings** - A booking belongs to a guest and is made for a property owned by a host. Key booking fields include the following:
  -*booking_id*
  -*property_id*
  -*guest_id*
  -*host_id*
  -*booking_status*
  
- **Reviews** - A review is made by a guest(reviewer) for a particular property that belongs to a host(reviewee). Review entities have the following common fields:
  -*review_id*
  -*reviewer_id*
  -*reviewee_ide*
  -*rating*
  -*property_id*
  
- **Payments** - A payment is made by a guest(payer) for a booking they made. Payment entities have the following common fields:
  -*payment_id*
  -*payer_id*
  -*booking_id*
  -*payment_type*
  -*amount*

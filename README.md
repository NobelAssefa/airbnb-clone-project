# airbnb-clone-project
 **Objective**
The backend for the Airbnb Clone project is designed to provide a robust and scalable foundation for managing user interactions, property listings, bookings, and payments. This backend will support various functionalities required to mimic the core features of Airbnb, ensuring a smooth experience for users and hosts.

**Project Goals**
User Management: Implement a secure system for user registration, authentication, and profile management.
Property Management: Develop features for property listing creation, updates, and retrieval.
Booking System: Create a booking mechanism for users to reserve properties and manage booking details.
Payment Processing: Integrate a payment system to handle transactions and record payment details.
Review System: Allow users to leave reviews and ratings for properties.
Data Optimization: Ensure efficient data retrieval and storage through database optimizations.


**Technology Stack**
Django: A high-level Python web framework used for building the RESTful API.
Django REST Framework: Provides tools for creating and managing RESTful APIs.
PostgreSQL: A powerful relational database used for data storage.
GraphQL: Allows for flexible and efficient querying of data.
Celery: For handling asynchronous tasks such as sending notifications or processing payments.
Redis: Used for caching and session management.
Docker: Containerization tool for consistent development and deployment environments.
CI/CD Pipelines: Automated pipelines for testing and deploying code changes.

**Team Roles**
Backend Developer: Responsible for implementing API endpoints, database schemas, and business logic.
Database Administrator: Manages database design, indexing, and optimizations.
DevOps Engineer: Handles deployment, monitoring, and scaling of the backend services.
QA Engineer: Ensures the backend functionalities are thoroughly tested and meet quality standards.



**Database Design**
1. User -
     Fields: id (Unique identifier), name (Full name of the user),email (User's email address),role (e.g., guest or host), createdAt (Account creation date)
     Relationships:
A user can own multiple properties (if host).
A user can make multiple bookings (if guest).
A user can write multiple reviews.
A user can make multiple payments.

3. Property
  Represents a listing created by a host.
    Fields: id (Unique identifier), title (Name of the property), description (Details about the property),location (Address or coordinates), pricePerNight (Cost per night)
   Relationships: 
A property belongs to a user (the host).
A property can have multiple bookings.
A property can have multiple reviews.

5. Booking
    Represents a reservation by a guest.
    Fields:id (Unique identifier),userId (The guest who made the booking),propertyId (The property being booked),startDate (Check-in date),endDate (Check-out date)
    Relationships:

A booking belongs to a user (guest).
A booking belongs to a property.
A booking can have one payment.


4. Review
    Represents feedback left by a guest after a stay.
    Fields: id (Unique identifier),userId (Who wrote the review),propertyId (Which property was reviewed),rating (e.g., 1–5 stars),comment (Optional text feedback)
    Relationships:
A review belongs to a user.
A review belongs to a property.

5.  Payment
    Represents payment for a booking.
    Fields:id (Unique identifier),bookingId (Related booking),amount (Total cost),paymentDate (When the payment was made),status (e.g., pending, completed, failed)

    Relationships:
A payment belongs to a booking.
A payment indirectly belongs to a user (via booking).


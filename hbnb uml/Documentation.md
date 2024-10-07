# HBnB Evolution - Technical Documentation

## Overview
This document outlines the **technical architecture and design** of the HBnB Evolution application, a simplified version of an AirBnB-like system. It includes high-level architecture, detailed class diagrams for business logic, and sequence diagrams to represent key API calls. The documentation serves as a blueprint for the implementation of the application.

## Project Description
**HBnB Evolution** allows users to perform four main operations:

1. **User Management**:
   - Users can register, update their profiles, and be identified as regular users or administrators.
2. **Place Management**:
   - Users can list properties they own, including details like name, description, price, and location. Properties can also have associated amenities.
3. **Review Management**:
   - Users can leave reviews on places they have visited, providing a rating and a comment.
4. **Amenity Management**:
   - Amenities can be created, updated, deleted, and associated with places.

Each entity in the system (User, Place, Review, Amenity) will have a unique identifier and track creation and update timestamps.

## Architecture Overview
The application follows a **three-layered architecture**:

- **Presentation Layer**: API and services that manage interactions with the users.
- **Business Logic Layer**: Models that represent the core entities (User, Place, Review, Amenity) and handle business logic.
- **Persistence Layer**: Manages data storage and retrieval from the database.

The **Facade Pattern** is used to simplify communication between these layers, ensuring that each layer interacts via a unified interface.

## Diagrams

### 1. High-Level Package Diagram
The high-level package diagram illustrates the three-layered architecture and the communication pathways between layers using the **Facade Pattern**. The main components include:

- **Presentation Layer**: Exposes APIs and services.
- **Business Logic Layer**: Contains the core models (User, Place, Review, Amenity).
- **Persistence Layer**: Handles database interactions.

### 2. Class Diagram for Business Logic Layer
The detailed class diagram focuses on the core entities in the Business Logic layer:
- **User**: Attributes include first name, last name, email, and password.
- **Place**: Attributes include title, description, price, latitude, and longitude.
- **Review**: Each review includes a rating and comment and is linked to a user and a place.
- **Amenity**: Amenities have a name and description and can be associated with places.

The diagram highlights relationships between these entities, such as associations between places and amenities.

### 3. Sequence Diagrams for API Calls
The following sequence diagrams show how different API calls are handled across the application layers:

1. **User Registration**: Flow of user registration from the API to the database.
2. **Place Creation**: Process of creating a new place listing.
3. **Review Submission**: Steps involved in submitting a review for a place.
4. **Fetching a List of Places**: Sequence of operations for retrieving places based on user criteria.

Each diagram illustrates interactions between the Presentation, Business Logic, and Persistence layers.

## How to Use This Documentation
This technical documentation is designed to guide the implementation of HBnB Evolution. The diagrams provide a clear representation of the system's structure and behavior, which will be critical during the development phase. The **Facade Pattern** simplifies layer interactions, making the architecture both flexible and maintainable.

## Conclusion
The provided diagrams and explanations give a comprehensive overview of the HBnB Evolution application's architecture. This documentation serves as a foundation for building a robust, scalable system that aligns with the business requirements.


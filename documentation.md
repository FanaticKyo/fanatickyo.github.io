# Mining Management System Documentation

This document provides a comprehensive overview of the Mining Management System, its architecture, and its features. It is intended for outside stakeholders who need to understand the system's capabilities.

## 1. System Architecture

The Mining Management System is a monolithic application built with the Django web framework. It follows a modular architecture, with each major feature encapsulated in its own Django app. This modular design allows for clear separation of concerns and makes the system easier to maintain and extend.

The system uses a PostgreSQL database with PostGIS for spatial data support. The backend is powered by Python and Django, while the frontend is built with a mix of HTML, CSS, and JavaScript, including libraries like Leaflet for interactive maps.

The following is a list of the core applications and their functionalities:

- **`project`**: The central application for managing mining projects.
- **`user`**: Handles user authentication and management.
- **`tms`**: The Tenement Management System, for managing mining tenements.
- **`lms`**: The Land Management System, for managing land parcels and owners.
- **`knowledgebase`**: A comprehensive knowledge base for storing and managing mining-related information.
- **`project_management`**: A project management tool with a Kanban-style board for tracking tasks.
- **`geodesk_gis`**: Provides GIS functionalities, including map visualization and data processing.
- **`interactive_map`**: Offers interactive maps for visualizing spatial data.
- **`notification`**: A system for sending notifications to users.
- **`website`**: The public-facing website with information about the system and subscription plans.

## 2. Core Features

### 2.1. Project Management (`project` and `project_management`)

The system provides robust project management capabilities, allowing users to:

- **Create and manage projects**: Each project has a name, owner, country, state, purpose, and locality.
- **Manage project members**: Users can be added to projects with different permission levels (Read, Write, Admin, Owner).
- **Track tasks with a Kanban board**: The `project_management` app provides a Kanban board with columns, tasks, labels, and assignees.
- **Organize work with subtasks and checklists**: Tasks can be broken down into subtasks and checklist items for better organization.
- **Store project-related files**: The system allows for the storage and management of project-specific files.

### 2.2. User Management (`user`)

The system has a custom user model with the following features:

- **Email-based authentication**: Users log in with their email and password.
- **User profiles**: Each user has a profile with their first name, last name, and company.
- **Role-based access control**: The system uses Django's built-in permission system, extended with object-level permissions, to control access to different features and data.

### 2.3. Tenement Management System (`tms`)

The Tenement Management System (TMS) is a important feature for managing mining tenements. It allows users to:

- **Track tenement information**: The system stores detailed information about each tenement, including its permit state, type, number, status, and key dates (lodged, granted, expiry).
- **Manage tenement holders**: It keeps track of tenement holders and their share percentages.
- **Handle environmental authorities**: The system can store information about environmental authorities associated with tenements.
- **Manage work programs**: Users can create and manage work programs for each tenement, including disciplines, activities, estimated expenditures, and actual costs.
- **Track tenement tasks**: The system includes a task management feature for tenements, allowing users to assign tasks, set due dates, and track their completion.

### 2.4. Land Management System (`lms`)

The Land Management System (LMS) is designed to manage land parcels and their owners. Its key features include:

- **Parcel management**: The system stores detailed information about each land parcel, including its lot and plan number, tenure, area, and geometry.
- **Owner management**: It allows for the management of land owners, including their personal details, contact information, and relationships with parcels.
- **Notes and correspondence**: Users can add notes and store correspondence with landowners.
- **Tasks and reminders**: The system provides a task management feature for landowners, with due dates, priorities, and reminders.
- **History tracking**: The LMS keeps a history of all changes made to land parcel and owner information.

### 2.5. Knowledge Base (`knowledgebase`)

The Knowledge Base is a powerful tool for storing and managing a wide range of mining-related information. It has a hierarchical structure that allows for detailed organization of knowledge:

- **Mines, Orebodies, Domains, and Blocks**: The hierarchy starts with a `Mine`, which can have multiple `Orebodies`. Each `Orebody` can have multiple `Domains`, and each `Domain` can have multiple `Blocks`.
- **Entries**: Knowledge is stored in `Entries`, which are linked to a specific `Block`. Each entry has a title, content, author, and tags.
- **Versioning**: The system keeps a history of all changes made to an entry, allowing users to view and revert to previous versions.
- **Attachments and Spatial Data**: Users can attach files and spatial data (e.g., Shapefiles, GeoJSON) to entries.
- **Comments and Templates**: The system supports comments on entries and allows for the creation of entry templates.

### 2.6. GIS and Interactive Maps (`geodesk_gis` and `interactive_map`)

The system provides a range of GIS and mapping functionalities:

- **Map visualization**: Users can visualize spatial data on interactive maps.
- **Layer management**: The interactive map supports multiple layers, including tenements, parcels, and other spatial data.
- **Data processing**: The `geodesk_gis` app provides tools for processing and analyzing spatial data.

### 2.7. Website and Subscriptions (`website`)

The public-facing website provides information about the Mining Management System and allows users to subscribe to different plans. The `website` app includes models for:

- **Contact messages**: Storing messages sent through the contact form.
- **Subscriptions**: Managing user subscriptions.
- **Stripe integration**: The system is integrated with Stripe for handling payments and subscriptions.
- **Credit management**: The website includes a credit system where users can purchase and use credits for certain features.

## 3. Conclusion

The Mining Management System is a comprehensive and powerful platform for managing all aspects of a mining operation. Its modular architecture, rich feature set, and robust data model make it a valuable tool for any mining company. This document provides a high-level overview of the system's capabilities. For more detailed information, please refer to the source code and the individual application documentation.

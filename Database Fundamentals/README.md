# Project: Designing a Database for a Real Estate Platform

This project, developed for the **Database Fundamentals (31271)** course, documents the end-to-end process of designing and implementing a relational database for a real estate platform. Inspired by commercial websites like `realestate.com.au`, the goal was to model a robust system for managing property listings, users, and their interactions.

The project was executed in three distinct stages, moving from high-level business concepts to a functional, queryable database.

---

## Stage 1: Database Design Case Study

The initial phase involved a case study to understand the core business requirements of a real estate platform. The primary objective was to define the scope of the database by identifying key functions, data needs, and the rules governing them.

This involved:
*   **Analyzing Business Functions**: Identifying essential services such as user registration, property searching, submitting rental applications, and scheduling property inspections.
*   **Defining Data Requirements**: Listing the specific pieces of information (attributes) that needed to be stored for each entity, such as a property's address and price, or a user's name and contact details.
*   **Establishing Business Rules**: Creating rules to ensure data consistency and integrity. For example, a rule stating that "a property listing must be associated with a valid agent."

---

## Stage 2: Conceptual Data Modeling (ERD)

With a clear understanding of the requirements, the next step was to create an Entity-Relationship Diagram (ERD). The ERD serves as a high-level, visual blueprint of the database, illustrating the different entities and the logical relationships between them. This conceptual model is crucial for ensuring the database design is logical and addresses all business rules before implementation begins.

Our ERD captures the core entities—`User`, `Property`, `Agent`, `Agency`—and the various interactions between them, such as how a `User` **submits** an `Application` or an `Agent` **manages** a `Listing`.

➡️ **[View the full Entity-Relationship Diagram (ERD)](./erd.PNG)**

---

## Stage 3: Functional Database Implementation

The final stage involved translating the conceptual ERD into a functional, relational database using PostgreSQL. This required writing a SQL script to perform all the necessary data definition and data manipulation tasks.

The implementation focused on creating three key tables from the ERD: `User`, `Listing`, and the associative entity `Application`, which connects them. The script handles:
1.  **Table Creation**: Defining the structure for each table and its columns.
2.  **Constraint Enforcement**: Using Primary and Foreign Keys to enforce the relationships defined in the ERD and ensure data integrity.
3.  **Data Population**: Inserting realistic sample data to simulate a live environment.
4.  **Data Querying**: Writing `SELECT` queries with `JOIN`s, `GROUP BY` clauses, and subqueries to retrieve meaningful information and test the database's functionality.

The complete SQL script includes table definitions, `INSERT` statements for sample data, and a series of queries to demonstrate the database in action.

➡️ **[View the full PostgreSQL Script (PartD.sql)](./PartD.sql)**

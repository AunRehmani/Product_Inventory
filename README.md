# Product Inventory Management System

A Java and Maven-based application for managing product inventory records, database persistence, and barcode-related service operations.

## Overview

`Product_inventory` is structured under the `org.example` package with a layered layout that separates the entry point, domain model, database connection/access layer, and service layer.

## Project Structure

```text
Product_inventory/
├── .mvn/                                   # Maven wrapper configuration & properties
├── src/
│   ├── main/
│   │   ├── java/org/example/
│   │   │   ├── services/
│   │   │   │   ├── barcode_service.java    # Barcode-related service logic
│   │   │   │   └── Product_service.java    # Product inventory business logic
│   │   │   ├── db_connection.java          # Database connection setup & handling
│   │   │   ├── Main.java                   # Application entry point
│   │   │   ├── Product_DAO.java            # Data Access Object for database operations
│   │   │   └── Product.java                # Product model / entity class
│   │   └── resources/                      # Configuration & application resource files
│   └── test/
│       └── java/                           # Unit and integration tests
├── .gitignore                              # Git ignore rules
└── pom.xml                                 # Maven build configuration & dependencies



**Core Components:**
Main.java: Entry point that initializes and coordinates application workflows.

Product.java: Defines the product entity, fields, and accessors.

db_connection.java: Manages database connection configuration and connection lifecycle.

Product_DAO.java: Data Access Object handling database queries and CRUD persistence for products.

services/Product_service.java: Implements business logic and coordinates product operations.

services/barcode_service.java: Handles barcode-related operations (generation, lookup, or validation).

pom.xml: Declares Maven build plugins, compiler target settings, and project dependencies.

**Core Dependencies & Requirements:**

Runtime & Build Tools
Java Development Kit (JDK): Required to compile and run the Java source code (match the Java version configured in pom.xml).

Apache Maven: Used for dependency management, compilation, testing, and packaging (you can also use the Maven wrapper in .mvn/).

Relational Database: Configured via db_connection.java and/or files in src/main/resources/.

Typical Java / Maven Dependencies
Depending on what is declared in your pom.xml, a setup with db_connection.java, Product_DAO.java, and barcode_service.java typically relies on:

JDBC Driver (e.g., MySQL Connector/J, PostgreSQL JDBC Driver, or SQLite JDBC) for connecting db_connection.java to your database.

Testing Framework (e.g., JUnit 5) for tests under src/test/java/.

Barcode Library (if external barcode generation/decoding libraries are used in barcode_service.java, alongside standard Java libraries).

Maven Build & Execution Plugins (such as maven-compiler-plugin, maven-surefire-plugin, or exec-maven-plugin).

Check pom.xml for the exact <dependencies> and <properties> blocks used in this repository.


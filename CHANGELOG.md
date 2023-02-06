# Spring Security, JWT, Authentication, and Authorization

## Getting Started

#### Create a new Spring Boot Project

Use Spring Inilializr (https://start.spring.io/) to set up project:
- Set to Maven project, Java, Spring Boot 3.0.2, Jar, Java 17. 
- Added dependencies
	+ Spring Web
	+ Spring Security
	+ Spring Data JPA
	+ PostgreSQL Driver
	+ Lombok

Open the project in your IDE  
PostgreSQL will be used as the database for this project.  
Start by configuring the datasource  

#### Create Database in PostgreSQL/PGAdmin
Open PGAdmin, log in, create a new database  
> named this one `jwt_security`

#### Set up application properties
Renaming application.properties to application.yml  

**Why .yml/.yaml?**  
>YAML is popular because it is optimized for data serialization, formatted dumping, configuration files, log files, and internet messaging and filtering. Since YAML works in concurrence with any programming language, it is often used to write configuration files.

Ignore the dashes. They're for showing the necessary indentation. Indentation with .yml files is **CRITICAL**  
`spring:`  
`--datasource:`  
`----url: jdbc:postgresql://localhost:5432/jwt_security`  
`----username: postgres`  
`----password: postgres1`  
`----driver-class-name: org.postgresql.Driver`  
`--jpa:`  
`----hibernate:`  
`------ddl-auto: create-drop`  
`----show-sql: true`  
`----properties:`  
`------hibernate:`  
`--------format_sql: true`  
`----database: postgresql`  
`----database-platform: org.hibernate.dialect.PostgreSQLDialect`  

After configuring this file and establishing the database, run the Spring Application.
At `http://localhost:8080/` I'm taken to /login and greeted with a generic login page. No credentials are set, however the server is persisting, and checking in Postman returns a 401 - Unauthorized.  
At this point we've got our beginnings

----

# Hotel Management

A Java Swing desktop database project for managing hotels, rooms, employees, customers, roles, and work assignments. Forms support inserting, updating, removing, and displaying records.

## Stack

- Java 11 and Swing, with NetBeans-generated forms.
- MySQL through JDBC.
- Maven project with a local NetBeans `AbsoluteLayout` dependency.
- Bundled MySQL Connector/J and `rs2xml.jar` for displaying query results in tables.

## Local setup

Use a disposable local database, not production data.

1. Install JDK 11, Maven or a compatible Java IDE, and a MySQL server.
2. Create an empty database named `manage_hotel` and import [`manage_hotel.sql`](manage_hotel.sql). Review the SQL before importing; it includes schema and sample data.
3. Set local database credentials in every `DriverManager.getConnection` call in `Hotel_Mangment.java` and `com/tables.java`. The source uses placeholder username/password strings and `jdbc:mysql://localhost/manage_hotel`. Never commit real credentials.
4. Make the bundled `mysql-connector-java-8.0.27.jar` and `rs2xml.jar` available on the compile/runtime classpath. The POM declares only `AbsoluteLayout`, so Maven alone does not provide all required libraries.
5. Run the `Hotel_Mangment` main class in a graphical desktop session.

The bundled layout library is under `lib/unknown/binary/AbsoluteLayout/SNAPSHOT/`. NetBeans can be used to inspect the `.form` files alongside the Java source.

## Project layout

- [`src/main/java/Hotel_Mangment.java`](src/main/java/Hotel_Mangment.java): main window and database actions.
- [`src/main/java/com/tables.java`](src/main/java/com/tables.java): query results displayed in a Swing table.
- [`pom.xml`](pom.xml): Java version and local dependency configuration.
- [`manage_hotel.sql`](manage_hotel.sql): database schema and seed records.

This is a learning project with hardcoded connection configuration and direct record deletion. Back up data before experimenting. Build and database compatibility with current tooling have not been verified.

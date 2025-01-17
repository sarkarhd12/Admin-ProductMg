# Admin-ProductMg


Product Management API
Overview

This project is a Spring Boot-based RESTful API for managing products. It supports CRUD operations, image upload, and search functionality.
Features

    Create, Read, Update, and Delete (CRUD) products.
    Upload and retrieve product images.
    Search products by name, description, brand, or category.
    Integration with MySQL database.

Technologies Used

    Java
    Spring Boot
    Spring Data JPA
    MySQL
    Maven

Prerequisites

    Java 11 or higher
    Maven
    MySQL

Setup and Installation
1. Clone the Repository

bash

git clone  (https://github.com/sarkarhd12/Admin-ProductMg.git)
Admin-ProductMg.git
cd Admin-ProductMg

2. Configure MySQL Database

Create a MySQL database and update the application.properties file with your database configuration:

properties

spring.datasource.url=jdbc:mysql://localhost:3306/your_database_name?useSSL=false
spring.datasource.username=your_database_username
spring.datasource.password=your_database_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL5Dialect

3. Build the Project

bash

mvn clean install

4. Run the Application

bash

mvn spring-boot:run

The application will start on http://localhost:8080.
API Endpoints
Get All Products

    URL: /api/products
    Method: GET
    Response: List of products

Get Product by ID

    URL: /api/product/{id}
    Method: GET
    Path Variables:
        id: The ID of the product to retrieve.
    Response: Product object

Add a Product

    URL: /api/product
    Method: POST
    Request Parts:
        product: JSON object of the product
        imageFile: Multipart file of the product image
    Response: Created product object

Get Product Image by Product ID

    URL: /api/product/{productId}/image
    Method: GET
    Path Variables:
        productId: The ID of the product whose image to retrieve.
    Response: Byte array of the image

Update a Product

    URL: /api/product/{id}
    Method: PUT
    Path Variables:
        id: The ID of the product to update.
    Request Parts:
        product: JSON object of the updated product
        imageFile: Multipart file of the updated product image
    Response: Status message

Delete a Product

    URL: /api/product/{id}
    Method: DELETE
    Path Variables:
        id: The ID of the product to delete.
    Response: Status message

Search Products

    URL: /api/products/search
    Method: GET
    Request Parameters:
        keyword: The search keyword.
    Response: List of products matching the keyword
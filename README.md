Microservices Architecture: Admin and Main Services
This project demonstrates a microservices-based architecture consisting of two independent services: Admin and Main. Both services communicate using RabbitMQ for asynchronous messaging.

Overview
Admin Service:

Built with Django and Docker.
Uses MySQL as the database.
Manages products and tracks the likes received for each product.
Main Service:

Built with Flask and Docker.
Uses MySQL as the database.
Tracks users and the products they have liked.
Features
Admin Service:
CRUD operations for managing products.
Publishes messages to RabbitMQ when a product is created, updated, or deleted.
Keeps track of the number of likes each product receives.
Main Service:
Tracks user information.
Allows users to like products.
Publishes messages to RabbitMQ when a product is liked.
Prevents duplicate likes by a single user for the same product.
Architecture
Key Components:
Admin Service: Manages product details and communicates with the Main Service using RabbitMQ.
Main Service: Manages user-product interactions and responds to messages from the Admin Service.
RabbitMQ: Facilitates communication between the two services by enabling asynchronous message exchange.
Communication Flow:
Admin publishes events (e.g., product created) to RabbitMQ.
Main consumes these events to update its records.
Main publishes events (e.g., product liked) to RabbitMQ, and Admin consumes these events to update product statistics.




Technologies Used
Admin Service: Django, MySQL, Docker.
Main Service: Flask, MySQL, Docker.
Communication: RabbitMQ for message exchange.

# Spotify-microservices-app
Spotify a music app is deployed as a microservice on docker.
# Steps to deploy spotify on docker 
Clone the repository using command :git clone  https://github.com/Amna-Zafar02/microservices-app.git
cd path/to/repo
Run docker-compose up --build
Open the given localhost port to play the spotify.
To stop container : docker-compose sown


**1. Frontend
Description: Serves the client-side application using Nginx.
Build Context: ./frontend
Port Mapping:
Host: 8080 → Container: 80
Access: http://localhost:8080

**2. Backend
Description: Handles server-side logic (e.g., API endpoints).
Build Context: ./backend
Port Mapping:
Host: 5001 → Container: 5000
Dependencies: Starts after the database service.
Access: http://localhost:5001


**3. Database
Description: MySQL database for storing application data.
Build Context: ./database
Port Mapping:
Host: 3306 → Container: 3306
Environment Variables:
MYSQL_ROOT_PASSWORD: Password for the root user.
MYSQL_DATABASE: Name of the initial database.
MYSQL_USER: Application's database user.
MYSQL_PASSWORD: Password for the database user.


**Network
Name: app-network
Type: Bridge
Purpose: Allows communication between all services.
How to Use
Start the application:
docker-compose up --build

**Access the services:
Frontend: http://localhost:8080
Backend: http://localhost:5001
Database: Use any SQL client to connect at localhost:3306.

**Stop the application:
docker-compose down

# Summary
The frontend, backend, and database services are connected through the app-network.
Each service is mapped to a port on the host machine for local access.
Configuration and dependencies are managed via Docker Compose for easy setup and deployment.

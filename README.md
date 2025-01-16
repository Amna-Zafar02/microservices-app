# Spotify-microservices-app
Spotify a music app is deployed as a microservice on docker.
# Steps to deploy spotify on docker 
1.Clone the repository using command :git clone  https://github.com/Amna-Zafar02/microservices-app.git
2.cd path/to/repo
3.Run docker-compose up --build
4.pen the given localhost port to play the spotify.
5.To stop container : docker-compose sown


**1. Frontend
1.Description: Serves the client-side application using Nginx.
2.Build Context: ./frontend
3.Port Mapping:
4.Host: 8080 → Container: 80
5.Access: http://localhost:8080

**2. Backend
1.Description: Handles server-side logic (e.g., API endpoints).
2.Build Context: ./backend
3.Port Mapping:
4.Host: 5001 → Container: 5000
5.Dependencies: Starts after the database service.
6.Access: http://localhost:5001


**3. Database
1.Description: MySQL database for storing application data.
2.Build Context: ./database
3.Port Mapping:
4.Host: 3306 → Container: 3306
5.Environment Variables:
6.MYSQL_ROOT_PASSWORD: Password for the root user.
7.MYSQL_DATABASE: Name of the initial database.
8.MYSQL_USER: Application's database user.
9.MYSQL_PASSWORD: Password for the database user.


**Network
1.Name: app-network
2.Type: Bridge
3.Purpose: Allows communication between all services.

**How to Use
**Start the application:
docker-compose up --build

**Access the services:
1.Frontend: http://localhost:8080
2.Backend: http://localhost:5001
3.Database: Use any SQL client to connect at localhost:3306.

**Stop the application:
docker-compose down

# Summary
The frontend, backend, and database services are connected through the app-network.
Each service is mapped to a port on the host machine for local access.
Configuration and dependencies are managed via Docker Compose for easy setup and deployment.

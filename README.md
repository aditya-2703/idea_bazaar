# Project Overview

This repository contains a collection of microservices built using Spring Boot, designed to create a robust and scalable platform for managing users, projects, resources, payments, and third-party integrations. Each service operates independently, allowing for flexibility and ease of maintenance.

## Table of Contents

- [Architecture](#architecture)
- [Microservices](#microservices)
  - [User  Service](#user-service)
  - [Project Service](#project-service)
  - [Resource Service](#resource-service)
  - [Payment Service](#payment-service)
  - [ThirdParty Service](#thirdparty-service)
- [Workflow](#workflow)
- [Dependencies](#dependencies)
- [Database Structure](#database-structure)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Architecture

The architecture of the system is based on a microservices approach, where each service is responsible for a specific domain. The services communicate with each other through APIs, and an API Gateway acts as a single entry point for client requests.

![Architecture Diagram](https://github.com/user-attachments/assets/2aed3991-429e-4b74-a8d3-080da2cf8b26)
</br>
![flow](https://github.com/user-attachments/assets/518f63d2-2960-4551-8e29-22266375d868)



### [User Service](https://github.com/aditya-2703/UserServiceApi)

**Functionality:**
- User registration and login
- User profile update
- Bookmarking projects
- Getting user details

**Components:**
- User API
- User Business Logic
- User Repository
- User Bookmarks

**Database:**
- Users table
- User Saved Projects table
- Bookmarks table

### [Project Service](https://github.com/aditya-2703/ProjectServiceApi)

**Functionality:**
- Create, update, and delete projects
- Link resources to projects
- Search projects
- Fetch repositories from Git service

**Components:**
- Project API
- Project Business Logic
- Project Repository
- Project Resources

**Database:**
- Projects table
- Project Resources table

### [Resource Service](https://github.com/aditya-2703/ProjectServiceApi)

**Functionality:**
- Create, update, and delete resources
- Validate resource URLs
- Search resources
- Tag resources

**Components:**
- Resource API
- Resource Business Logic
- Resource Repository
- Resource Cache (Redis)

**Database:**
- Resources table

### [Payment Service](https://github.com/aditya-2703/ProjectServiceApi)

**Functionality:**
- Initiate payments
- Verify payments
- Refund payments
- Payment history
- Payment status

**Components:**
- Payment API
- Payment Business Logic
- Payment Repository

**Database:**
- Payments table

### [ThirdParty Service](https://github.com/aditya-2703/ProjectServiceApi)

**Functionality:**
- Fetch repositories from a third-party service (e.g., GitHub)

**Components:**
- ThirdParty API
- ThirdParty Business Logic
- ThirdParty Repository
- ThirdParty Resources

**Database:**
- ThirdParty table
- ThirdParty Resources table

## Workflow

1. **Client Interaction:** Users interact with the application through web or mobile clients.
2. **API Gateway:** The API Gateway routes requests to the appropriate microservice based on the requested functionality.
3. **Service Processing:** Each microservice processes the request and interacts with its database.
4. **Data Persistence:** Microservices store and retrieve data from their respective databases.
5. **Response Generation:** After processing, microservices generate responses and send them back to the API Gateway.
6. **Response Delivery:** The API Gateway forwards the processed response back to the client.

## Dependencies

- Spring Boot
- Spring Data JPA
- Spring Security
- Redis (for caching in Resource Service)
- Microservices (for inter-service communication)
- External APIs (e.g., GitHub API for ThirdParty Service)

## Database Structure

![Database Structure Diagram](https://github.com/user-attachments/assets/8c6ccf0a-3dcc-4670-927b-e43878a10694)

## Usage

1. **Clone the Repository:**
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Set Up Environment:**
   - Create a `.env` file in each microservice directory and configure the necessary environment variables.

3. **Install Dependencies:**
   ```bash
   ./mvnw clean install
   ```

4. **Run the Services:**
   - Start each microservice individually or use a container orchestration tool like Docker or Kubernetes for deployment.
   ```bash
   ./mvnw spring-boot:run
   ```

5. **Access the API:**
   - Use tools like Postman or curl to interact with the API endpoints exposed by the API Gateway.

## Contributing

Contributions are welcome! Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

---

This README provides a comprehensive overview of the project, its architecture, and how to use it. It serves as a guide for developers and users to understand the system's functionality and structure.

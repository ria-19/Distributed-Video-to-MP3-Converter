## Distributed Video To MP3 Converter - Microservice Architecture

**Overview:**
This project implements a video-to-MP3 conversion service using a microservice architecture. The system leverages Docker and Kubernetes for containerization and deployment.

**Key Features:**

* **Microservice Architecture:** Decouples components for scalability and maintainability.
* **Asynchronous Processing:** Utilizes RabbitMQ for efficient message queuing and parallel processing.
* **Data Persistence:** Stores video and MP3 files in MongoDB for easy retrieval.
* **Notification System:** Sends email notifications to users upon conversion completion.

<img width="1411" alt="Screenshot 2024-08-31 at 3 45 51 PM" src="https://github.com/user-attachments/assets/c58710a9-0950-4365-9e18-329e09919102">

**Workflow:**

1. **User Upload:** A user uploads a video to the API Gateway.
2. **Video Storage:** The API Gateway stores the video in MongoDB and sends a message to the RabbitMQ queue.
3. **Conversion Process:** The video-to-MP3 service consumes the message, fetches the video from MongoDB, converts it to MP3, and stores the result in MongoDB.
4. **Notification:** The notification service consumes a message from the queue, sends an email notification to the user, and provides a unique ID for download.
5. **Download:** The user uses the unique ID and their JWT to request the MP3 file from the API Gateway, which retrieves it from MongoDB and serves it to the client.

**Deployment:**

* **Docker:** Containerizes each microservice for portability and isolation.
* **Kubernetes:** Manages the deployment and scaling of the microservices on a cluster.

**Dependencies:**

* **Programming Language:** Python
* **Frameworks:** Flask
* **Database:** MongoDB, MySQL
* **Message Queue:** RabbitMQ
* **Other:** Docker, Kubernetes

**Further implementation todo:**

* Error handling and logging mechanisms for monitoring and troubleshooting.
* Explore caching strategies to improve performance for frequently accessed resources.
* Implementing security measures to protect user data and prevent unauthorized access.


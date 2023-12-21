Part 2: Microservices Architecture

============ Q1: Define what is a Microservices architecture and how does it differ from a Monolithic application. ============

A monolithic application is built as a single unified unit while a microservices architecture is a collection of smaller, independently deployable services
A Microservices architecture is an approach to software development where a large application is broken down into small, independent services that communicate with each other through lightweight protocols.


============ Q2: Compare Microservices and Monolithic architectures by listing their respective pros and cons. ============

---------------------------------------------- Monolithic architectures : ----------------------------------------------
**Pros :**
- Simple to develop 
    IDEs are oriented around developing a single application
- Easy to test
    Just need to launch the one application
- Can be simple to deploy
    Just have to copy the deployment unit to a server

**Cons :**
- Becomes unmanageable for complex applications
    • Difficult to maintain and to understand

    • Difficult to scale and ensure high
availability
    • Obstacle to frequent deployments
    • Difficult to try and adopt new technologies

---------------------------------------------- Microservices architectures : ----------------------------------------------
**Pros :**

- Scalability Ease:
    • Microservices allow for independent scalability. Specific services can be scaled without impacting the entire application.

- Independent Deployment:**
    • Microservices can be deployed independently, facilitating frequent updates without disrupting the entire system.

- Technological Flexibility:**
    • Each microservice can be developed with different technologies, making it easier to adopt new technologies without affecting the entire application.

- Complexity Management:**
    • Microservices are easier to understand and maintain, as each service has a specific responsibility.

- Resilience:**
    • In the event of a failure in one microservice, others continue to function, ensuring better overall resilience.

**Cons :**

- Communication Complexity:**
    • Communication between microservices can introduce complexity, requiring careful management of remote calls and protocols.

- Initial Development Complexity:**
     • The initial setup of a Microservices architecture can be more complex than developing a monolithic application.

- Complex Integration Testing:**
    • Integration testing can be more complex due to the need to test interactions between multiple microservices.

- Data Consistency Management:**
    • Maintaining data consistency across different microservices can be challenging, requiring careful handling of transactions.

- Cost of Microservices Management:**
    • Managing a large number of microservices can lead to higher operational costs, requiring appropriate infrastructure and tools.


============ Q3: In a Micoservices architecture, explain how should the application besplit and why. ============

**Bounded:**
   - A micro service must offer an interface that is uniform and is designed to support
service composition through contracts

**Complete but Minimal:**
    • A micro service must be functionally complete , with a well defined contract, trying to
avoid inter services dependencies
    • A micro service must only contain highly cohesive entities

**Resilient:**
    • A micro service must fail without impacting other services in the same application

**Elastic:**
    • A micro service must be able to scale up or down independently of other services in
the same application

WHY :
    • "One feature is one change in one micro service and therefore one deployment" 
    • Micro services are intended to be developed & tested / be deployed & updated / be operated / Scale & fail ALL independently!


============ Q4: Briefly explain the CAP theorem and its relevance to distributed systems and Microservices. ============

The CAP theorem means : Consistency, Availability, Partition Tolerance

**Consistency :** All nodes in the system see the same data at the same time.

**Availability :** Every request to the system receives a response, without guarantee that it contains the most recent version of the information.

**Partition Tolerance :** The system continues to operate despite arbitrary partitioning (communication breakdowns) between nodes, which may cause some nodes to be unreachable by others.

how does this relate to Microservices and distributed systems?

- Microservices and CAP Theorem:
  - In a Microservices architecture, where services communicate over a network, the CAP theorem is highly relevant. Microservices often prioritize partition tolerance due to the distributed nature of the architecture.

- Trade-offs:
  - Microservices often face trade-offs between consistency and availability. Different microservices might make different choices based on the specific requirements of their functionality.

- Data Management:
  - The CAP theorem influences how microservices handle data consistency across the system. Some services might choose eventual consistency (A) over strong consistency (C) to ensure high availability.

- Resilience and Partitioning:
  - Microservices must be designed to be resilient to network partitions. This means that even if some parts of the system are temporarily unreachable, the overall system should continue to function.

============ Q5: What consequences on the architecture ? ============

- Consistency and Availability Trade-off: Architectures face a trade-off between ensuring data consistency and maintaining system availability during network partitions.

- Data Management Challenges: Techniques like data replication and partitioning are employed, introducing complexities in synchronization and conflict resolution for distributed systems.

- Eventual Consistency Principle: Many distributed systems, including Microservices, prioritize eventual consistency, allowing the system to converge to a consistent state over time.

- Emphasis on Fault Tolerance: Architectures must prioritize fault tolerance, asynchronous communication, and monitoring to ensure resilience and recovery in the face of failures.

============ Q6: Provide an example of how microservices can enhance scalability in a cloud environment. ============

The use of containers to deploy independent services in a cloud environment is an example of how microservices can enhance scalability. These autonomous services can be easily scaled automatically in response to growing demand.

============ Q7: What is statelessness and why is it important in microservices architecture ? ============

Statelessness means that no client data is stored on the server between requests, and session state is stored on the clien.
Each request from clients contains all the information necessary to process the request by the server.
In microservices architectures, it is crucial for scalability and resilience, as it enables requests to be handled by any instance of the service.

============ Q8: What purposes does an API Gateway serve ? ============

API Gateway acts as a "front door" for applications to access data, business logic, or functionality from your backend services, such as workloads running on Amazon Elastic Compute Cloud (Amazon EC2), code running on AWS Lambda, any web application, or real-time communication applications.

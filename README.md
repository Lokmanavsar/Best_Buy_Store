# Building a Cloud-Native App for Best Buy
## Updated Application Architecture

![Best Buy architecture diagram](assets/Best_Buy.png)

## Application and Architecture Explanation

Welcome to the Best Buy application.
The Best Buy application is a microservices-based, containerized architecture that can be deployed to a Kubernetes cluster. The design emphasizes polyglot programming, event-driven communication, and integration with AI services to enhance functionality. Here's a breakdown of how the application works: 

### 1.Store Front (Vue):
* Acts as the customer-facing interface.
*Users can browse products, place orders, and interact with the platform.

### 2.Store Admin (Vue):
* Provides store administrators with a management interface for order tracking and product catalog management.

### 3.Order Service (Node):
* Manages customer orders, including their creation and updates.
* Communicates asynchronously via Azure Service Bus for seamless order processing.

### 4.Product Service (Rust):
* Handles product-related functionalities such as catalog updates and inventory management.
* Works in conjunction with the Order Service and Store Front to provide up-to-date product data.

### 5.Makeline Service (Go):
* Coordinates the fulfillment pipeline, ensuring orders are processed and tracked efficiently.
* Updates the Order Database (MongoDB) and interacts with other microservices for real-time processing.

### 6.AI Service (Python):
* Uses OpenAI's GPT-4 model to generate product descriptions, improving the content quality of the storefront.
* Integrates with the DALL-E model to generate product images for a visually engaging user experience.

### 7.Order Database (MongoDB):
* Serves as the primary data store for orders, maintaining a scalable and efficient backend for order-related data.

### 8.Azure Service Bus:
* Acts as the backbone for event-driven communication between microservices, ensuring reliability and decoupled interactions.

## Deployment Instructions
Step-by-step instructions to deploy the application in a Kubernetes cluster.

## Table of Microservice Repositories
A table listing each microservice repository and its GitHub link.


| Service | Github Repo |
| --- | --- | --- |
| `store-front-Best_Buy` | [store-front-Best_Buy](https://github.com/Lokmanavsar/store-front-Best_Buy.git) |
| `store-admin` | Web app used by store employees to view orders in queue and manage products (Vue.js) | [store-admin-L8](https://github.com/ramymohamed10/store-admin-L8) |
| `order-service` | This service is used for placing orders (Javascript) | [order-service-L8](https://github.com/ramymohamed10/order-service-L8) |
| `product-service` | This service is used to perform CRUD operations on products (Rust) | [product-service-L8](https://github.com/ramymohamed10/product-service-L8) |
| `makeline-service` | This service handles processing orders from the queue and completing them (Golang) | [makeline-service-L8](https://github.com/ramymohamed10/makeline-service-L8) |
| `ai-service` | Optional service for adding generative text and graphics creation (Python) | [ai-service-L8](https://github.com/ramymohamed10/ai-service-L8) |
| `rabbitmq` | RabbitMQ for an order queue | [rabbitmq](https://github.com/docker-library/rabbitmq) |
| `mongodb` | MongoDB instance for persisted data | [mongodb](https://github.com/docker-library/mongo) |
| `virtual-customer` | Simulates order creation on a scheduled basis (Rust) | [virtual-customer-L8](https://github.com/ramymohamed10/virtual-customer-L8) |
| `virtual-worker` | Simulates order completion on a scheduled basis (Rust) | [virtual-worker-L8](https://github.com/ramymohamed10/virtual-worker-L8) |


![Logical Application Architecture Diagram](assets/Algonquin%20Pet%20Store%20On%20Steroids.png)

## Run the app on Azure Kubernetes Service (AKS)

You can use the kubernetes YAML files provided in the [Deployment Files](./Deployment%20Files/) folder to deploy the app to an AKS cluster.




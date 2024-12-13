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


| Service               | Repository Link     |
|-----------------------|---------------------|
| `store-front-Best_Buy`           | [store-front-best-buy](https://github.com/Lokmanavsar/store-front-Best_Buy.git)   |
| `order-service-Best_Buy`         | [order-service-Best_Buy](https://github.com/Lokmanavsar/order-service-Best_Buy.git)   |
| `product-service-Best_Buy`       | [product-service-Best_Buy](https://github.com/Lokmanavsar/product-service-Best_Buy.git)   |
| `store-admin-Best_Buy`           | [store-admin-Best_Buy](https://github.com/Lokmanavsar/store-admin-Best_Buy.git)   |
| `makeline-service-Best_Buy`      | [makeline-service-Best_Buy](https://github.com/Lokmanavsar/makeline-service-Best_Buy.git)   |
| `ai-service-Best_Buy`            | [ai-service-Best_Buy](https://github.com/Lokmanavsar/ai-service-Best_Buy.git)   |


![Logical Application Architecture Diagram](assets/Algonquin%20Pet%20Store%20On%20Steroids.png)

## Run the app on Azure Kubernetes Service (AKS)

You can use the kubernetes YAML files provided in the [Deployment Files](./Deployment%20Files/) folder to deploy the app to an AKS cluster.




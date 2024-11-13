# Algonquin Pet Store (On Steroids)
Welcome to the Algonquin Pet Store (On Steroids) application.

This sample demo app consists of a group of containerized microservices that can be easily deployed into a Kubernetes cluster. This is meant to show a realistic scenario using a polyglot architecture, event-driven design, and common open source back-end services (eg - RabbitMQ, MongoDB). The application also leverages OpenAI's models to generate product descriptions and images. This can be done using either [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/overview) or [OpenAI](https://openai.com/).

This application is inspired by Azure Kubernetes Service (AKS) quickstart demo [Azure Kubernetes Service (AKS) Docs](https://learn.microsoft.com/en-us/azure/aks/).

> [!NOTE]
> This is not meant to be an example of perfect code to be used in production, but more about showing a realistic application running in kubernetes. 

## Architecture

The application has the following services: 

| Service | Description |
| --- | --- |
| `store-front` | Web app for customers to place orders (Vue.js) |
| `store-admin` | Web app used by store employees to view orders in queue and manage products (Vue.js) | 
| `order-service` | This service is used for placing orders (Javascript) |
| `product-service` | This service is used to perform CRUD operations on products (Rust) |
| `makeline-service` | This service handles processing orders from the queue and completing them (Golang) |
| `ai-service` | Optional service for adding generative text and graphics creation (Python) |
| `rabbitmq` | RabbitMQ for an order queue |
| `mongodb` | MongoDB instance for persisted data |
| `virtual-customer` | Simulates order creation on a scheduled basis (Rust) |
| `virtual-worker` | Simulates order completion on a scheduled basis (Rust) |


![Logical Application Architecture Diagram](assets/Algonquin%20Pet%20Store%20On%20Steroids.png)

## Run the app on Azure Kubernetes Service (AKS)

You can use the kubernetes YAML files provided in the Deployment Files folder to deploy the app to an AKS cluster.




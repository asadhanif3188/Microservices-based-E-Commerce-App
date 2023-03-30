# Microservices based E-Commerce App - Deployed on Kubernetes

In this demo application, we are going to deploy a **microservices** based **E-Commerce** web application with **11** microservices on Kubernetes.

Application credit to [Google Cloud Platform](https://github.com/GoogleCloudPlatform/microservices-demo).

## Description 
**Online Boutique** is a cloud-native microservices demo application. Online Boutique consists of a 11-tier microservices application. The application is a web-based e-commerce app where users can browse items, add them to the cart, and purchase them.

**Google uses this application to demonstrate use of technologies like Kubernetes/GKE, Istio, Stackdriver, gRPC and OpenCensus**. This application works on any Kubernetes cluster, as well as Google Kubernetes Engine. It’s easy to deploy with little to no configuration.

## Architecture
Online Boutique is composed of 11 microservices written in different languages that talk to each other over gRPC.

![App Architecture](images/architecture-diagram.png)

## Microservices Detail

| Microservice | Language | Working on Port | Env. Variables | Description                    |
|--------------|----------|-----------|--------------|--------------------| 
| frontend     | Go       |8080       |     | Exposes an HTTP server to serve the website. Does not require signup/login and generates session IDs for all users automatically.|
| cartservice  | C#       |8080       |     | Stores the items in the user's shopping cart in Redis and retrieves it. |
| productcatalogservice  | Go       |8080       |     | Provides the list of products from a JSON file and ability to search products and get individual products. |
| currencyservice  | Nodejs       |8080       |     | Converts one money amount to another currency. Uses real values fetched from European Central Bank. It's the highest QPS service. |

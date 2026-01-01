Microservices-based digital payment system with Kafka-driven transaction processing and idempotent wallets.

📌 Overview

This project is a distributed digital payment system inspired by real-world platforms like PayPal.
It is designed to address core backend and system design challenges such as:

High-throughput transaction processing
Fault isolation using microservices
Reliable and consistent wallet updates
Handling retries, failures, and duplicate requests
Real-time event-driven workflows

The system is built using Spring Boot microservices and follows an event-driven architecture with Apache Kafka to ensure scalability and reliability.

🏗 Architecture

The system is decomposed into independent microservices, each with a clear responsibility:

Client
  |
  |--> User Service
  |--> Transaction Service ---> Kafka ---> Reward Service
  |                               |
  |                               ---> Wallet Service

Key Design Principles

Loose coupling via Kafka-based asynchronous communication
Fault isolation between services
Exactly-once wallet updates using idempotency
Scalable and resilient backend design

🔧 Microservices Breakdown

👤 User Microservice

Manages user registration and profile information
Exposes REST APIs for user-related operations

💸 Transaction Microservice

Handles payment initiation and transaction lifecycle
Publishes transaction events to Kafka
Acts as the core payment orchestration service

💰 Wallet Microservice

Maintains user wallet balances
Implements idempotent APIs to prevent:
Double debits
Duplicate transaction processing
Ensures exactly-once balance updates

🎁 Reward Microservice

Consumes transaction events from Kafka
Calculates and distributes rewards in real time
Decoupled from core payment flow to avoid latency

⚙️ Key Features

✅ Microservices-based architecture using Spring Boot
✅ Event-driven communication with Apache Kafka
✅ Idempotent wallet operations for consistency
✅ Real-time reward processing
✅ API rate limiting to handle traffic spikes and abuse
✅ RESTful APIs with clean service separation

🛠 Tech Stack

Language: Java
Framework: Spring Boot
Architecture: Microservices, Event-Driven Design
Messaging: Apache Kafka
Databases: MySQL / PostgreSQL
Security & Reliability: Idempotency, Rate Limiting
Tools: Git, Postman

# Architecture

## Overview

The bookstore application is built as a set of loosely coupled microservices communicating over HTTP and an event bus. Each service owns its own data store and exposes a well-defined API.

## Service boundaries

| Service       | Responsibility                     | Data store  |
|---------------|-------------------------------------|------------|
| Catalog       | Books, authors, categories          | PostgreSQL |
| Order         | Carts, orders, payments             | PostgreSQL |
| Notification  | Emails, push notifications          | Redis      |

## Communication patterns

- **Synchronous**: REST API calls between services for real-time queries (e.g., order service fetches book details from catalog).
- **Asynchronous**: Event bus (NATS) for decoupled workflows (e.g., order placed triggers notification).

## Deployment

Services are containerized and deployed to Kubernetes. Each service has its own Helm chart under `deploy/`.

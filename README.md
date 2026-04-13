# Test Repo

A sample repository used to test the fullsend runner. It contains a small microservice architecture for a bookstore application.

## Architecture

The application follows a layered architecture with three main services:

- **Catalog Service**: Manages the book inventory, handles CRUD operations for books, authors, and categories.
- **Order Service**: Processes customer orders, manages shopping carts, and handles checkout workflows.
- **Notification Service**: Sends email and push notifications for order confirmations, shipping updates, and promotional campaigns.

## Getting started

```bash
# Install dependencies
make install

# Run tests
make test

# Start the development server
make dev
```

## API overview

All services expose REST APIs documented in their respective directories. The API gateway routes requests to the appropriate service based on the URL prefix.

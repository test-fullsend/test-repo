# Catalog Service

Manages the book inventory for the bookstore.

## Endpoints

- `GET /api/books` — List all books (supports pagination and filtering)
- `GET /api/books/:id` — Get a single book by ID
- `POST /api/books` — Create a new book (admin only)
- `PUT /api/books/:id` — Update a book (admin only)
- `DELETE /api/books/:id` — Delete a book (admin only)
- `GET /api/authors` — List all authors
- `GET /api/categories` — List all categories

## Data model

A book has: title, author, ISBN, price, category, description, stock count, and publication date.

## Search

Full-text search is supported via PostgreSQL's `tsvector` indexing on title, author name, and description fields.

# Order Service

Handles shopping carts, order processing, and payment integration.

## Endpoints

- `POST /api/cart` — Create a new cart
- `POST /api/cart/:id/items` — Add item to cart
- `DELETE /api/cart/:id/items/:itemId` — Remove item from cart
- `POST /api/orders` — Place an order (converts cart to order)
- `GET /api/orders/:id` — Get order status
- `GET /api/orders` — List orders for the authenticated user

## Order lifecycle

1. Customer adds items to cart
2. Customer initiates checkout
3. Order service validates stock with catalog service
4. Payment is processed via Stripe integration
5. Order confirmed event is published to the event bus
6. Notification service picks up the event and sends confirmation email

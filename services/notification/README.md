# Notification Service

Sends transactional and promotional notifications to customers.

## Channels

- **Email**: Order confirmations, shipping updates, password resets (via SendGrid)
- **Push**: Mobile push notifications for order status changes (via Firebase Cloud Messaging)

## Event subscriptions

The service listens to the following events on the NATS event bus:

- `order.placed` — Sends order confirmation email
- `order.shipped` — Sends shipping notification with tracking link
- `order.delivered` — Sends delivery confirmation
- `user.registered` — Sends welcome email

## Rate limiting

Notifications are rate-limited per user to prevent spam. The rate limiter uses Redis with a sliding window algorithm.

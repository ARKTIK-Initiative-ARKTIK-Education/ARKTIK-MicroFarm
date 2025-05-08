# API Overview
<img src="../../../assets/ARKTIK%20Logo.png" alt="ARKTIK Logo" width="200">


This folder contains the RESTful API endpoints powering e-commerce, subscription management, dashboards, and integration with external services.

## Directory Structure

```
src/api/
├── controllers/      # Route handlers for each resource
├── models/           # Database schemas and validation
├── routes/           # Express (or Fastify) route definitions
├── services/         # Business logic and external integrations
└── utils/            # Helpers, error handling, and middleware
```

## Key Endpoints

### Products & Orders

* `POST /api/orders` — Create a new kit order
* `GET /api/orders/:id` — Retrieve order details
* `GET /api/catalog` — List available kits and pricing tiers

### Subscriptions

* `POST /api/subscriptions` — Subscribe to AI analytics (Basic, Pro, Enterprise)
* `GET /api/subscriptions/:userId` — Get user subscription status
* `PUT /api/subscriptions/:id` — Upgrade/downgrade subscription plan
* `DELETE /api/subscriptions/:id` — Cancel a subscription

### Billing & Payments

* `POST /api/payments` — Process payments via Stripe (card, ACH)
* `POST /api/stripe/webhook` — Handle Stripe event callbacks for invoices and charges

### Dashboard Data

* `GET /api/dashboard/:farmId/sensors` — Retrieve live sensor readings (moisture, pH, temperature)
* `GET /api/dashboard/:farmId/alerts` — List recent AI-generated recommendations and alerts

### User & Authentication

* `POST /api/auth/register` — New user registration
* `POST /api/auth/login` — User authentication and JWT issuance
* `GET /api/users/:id` — Fetch user profile and stored-value balance

## Services & Integrations

* **StripeService** — Handles wallet funding, subscription billing, and invoicing
* **MailService** — Sends transactional emails (order confirmations, alerts)
* **AnalyticsService** — Interfaces with AI analysis engine for recommendations

## Getting Started

1. Install dependencies: `npm install` or `yarn install`
2. Configure environment variables in `.env` (see `sample.env`)
3. Start development server: `npm run dev`
4. Run tests: `npm test`

*For detailed implementation guidelines, refer to comments in each subdirectory.*

# System Integration Patterns for UK SMEs

A practical guide to common system integration scenarios facing UK small and medium enterprises. For bespoke integration and automation support, visit [ajairu.dev](https://ajairu.dev).

## Why integration matters

Most UK SMEs run 5 to 15 different software systems: accounting, CRM, e-commerce, inventory, payroll, marketing, customer support, and more. When these systems do not talk to each other, you get manual data entry, errors, delays, and wasted hours. Integration fixes this.

The right integration pattern depends on your systems, your budget, your technical capability, and how real-time your data needs to be.

---

## Pattern 1: Point-to-point API integration

**What it is:** System A calls the API of System B directly, sending or receiving data.

**When to use:**
- You have two or three systems that need to share data
- Both systems have well-documented APIs
- You need real-time or near-real-time data sync
- You have a developer or technical partner who can maintain the connection

**Pros:** Fast, direct, no intermediary. Full control over what data moves and when.
**Cons:** Does not scale. Connecting 5 systems point-to-point means 20 connections. Each connection needs maintenance.

**Example:** Your e-commerce platform (Shopify) sends order data to your accounting software (Xero) via its API every time an order is placed.

## Pattern 2: Middleware / iPaaS (Integration Platform as a Service)

**What it is:** A middleware platform sits between your systems and orchestrates data flow. It connects to each system once and routes data between them.

**When to use:**
- You have 4 or more systems to integrate
- You want a visual, low-code way to manage integrations
- Your team is not heavily technical
- You need to integrate with many SaaS products

**Common platforms for UK SMEs:**
- Zapier (simple, wide range of connectors)
- Make (formerly Integromat, more powerful, visual builder)
- n8n (open-source, self-hostable, good for cost-conscious SMEs)
- Microsoft Power Automate (if you are in the Microsoft ecosystem)

**Pros:** Scales to many systems. Non-technical team members can build flows. Reduces maintenance burden.
**Cons:** Monthly cost. Vendor lock-in. Complex logic can be hard to debug. May not support niche or legacy systems.

**Example:** A new customer in your CRM triggers a welcome email in your marketing tool, creates a project in your project management tool, and logs a record in your accounting system, all through a middleware platform.

## Pattern 3: Webhook-driven event integration

**What it is:** System A sends an HTTP request (webhook) to System B (or a middleware) when something happens. No polling required.

**When to use:**
- You need to react to events in real time
- The source system supports webhooks
- You have a server or serverless function to receive the webhook
- You want to avoid polling for changes

**Pros:** Real-time. Efficient (no polling). Event-driven architecture.
**Cons:** Requires a publicly accessible endpoint to receive webhooks. Need to handle retries and failures. Webhook delivery is not guaranteed by all providers.

**Example:** Your payment provider (Stripe) sends a webhook to your application when a payment fails, triggering an automated email to the customer and a task in your support system.

## Pattern 4: Scheduled batch synchronisation

**What it is:** A scheduled job (cron, scheduled task) runs at intervals, pulls data from one system, transforms it, and pushes it to another.

**When to use:**
- Real-time sync is not needed (daily or hourly is fine)
- APIs have rate limits that prevent constant polling
- You need to process data in bulk (e.g. end-of-day reconciliation)
- You want a simple, predictable, auditable process

**Pros:** Simple. Predictable. Easy to audit. Handles bulk processing well. Resilient to temporary outages.
**Cons:** Not real-time. Data can be stale between runs. Need to handle failures and retries.

**Example:** Every night at 2am, a script pulls the day's sales from your e-commerce platform, formats them, and imports them into your accounting software.

## Pattern 5: Shared database / data warehouse

**What it is:** Multiple systems read from and/or write to a shared database or data warehouse. Data is centralised and each system accesses what it needs.

**When to use:**
- You need a single source of truth across multiple systems
- You need reporting and analytics across all your data
- You have data volume that APIs cannot handle efficiently
- You want to decouple systems from each other

**Common tools:**
- PostgreSQL (open-source, powerful, widely supported)
- Google BigQuery (for analytics-heavy use cases)
- Microsoft SQL Server (if in the Microsoft ecosystem)
- Airtable or Notion (for lightweight, non-technical teams)

**Pros:** Single source of truth. Great for reporting. Decouples systems.
**Cons:** More complex to set up. Requires database expertise. Schema changes affect all connected systems.

**Example:** Your CRM, e-commerce platform, and accounting software all sync their data into a central PostgreSQL database. Your reporting dashboard pulls from this single source, giving you a unified view of the business.

## Pattern 6: Message queue / event bus

**What it is:** Systems publish events to a message queue. Other systems subscribe to the events they care about. The queue handles delivery, retries, and ordering.

**When to use:**
- You have many systems that need to react to the same events
- You need reliable delivery with retries
- You are building an event-driven architecture
- You need to decouple producers from consumers

**Common tools:**
- RabbitMQ (open-source, widely used)
- Apache Kafka (high throughput, more complex)
- Amazon SQS / SNS (if on AWS)
- Redis (lightweight, good for simpler setups)

**Pros:** Reliable. Scalable. Decoupled. Handles failures gracefully.
**Cons:** More complex to set up and maintain. Requires development expertise. Overkill for simple integrations.

**Example:** When an order is placed, an event is published to the queue. The inventory system, accounting system, fulfilment system, and notification system each consume the event independently.

---

## Choosing the right pattern

| If you have... | And you need... | Consider... |
|----------------|-----------------|-------------|
| 2-3 systems | Direct, real-time sync | Point-to-point API |
| 4+ systems | Centralised management | Middleware / iPaaS |
| Event-driven needs | Real-time reactions | Webhooks |
| Bulk data, no real-time need | Daily sync | Scheduled batch |
| Many systems, reporting needs | Single source of truth | Shared database |
| Many systems, reliable delivery | Event-driven architecture | Message queue |

## Common integration challenges for UK SMEs

### Legacy systems with no API
Many UK SMEs run systems that predate modern APIs. Options: use file-based integration (CSV import/export), screen scraping (fragile but sometimes necessary), or plan a migration to a modern system.

### Rate limits
SaaS APIs often limit how many requests you can make per minute. Batch where possible, cache where appropriate, and respect rate limits to avoid being blocked.

### Data format mismatches
System A calls it "customer", System B calls it "client", System C uses a different ID format. Plan for data transformation in every integration. Document your field mappings.

### Authentication complexity
Different systems use different auth methods (API keys, OAuth, basic auth). Standardise where possible and store credentials securely, never in code.

### Error handling and monitoring
Integrations fail. Network issues, API changes, data format changes. Every integration needs error handling, logging, and alerting. If you do not know an integration is broken, you will find out from a customer.

### GDPR and data sovereignty
When data moves between systems, especially through cloud middleware, you need to consider where the data is processed and whether it complies with UK GDPR. Check data processing agreements with your middleware providers.

## A practical starting point

If you are new to integration, start here:

1. **Map your systems.** List every software tool your business uses and what data each one holds.
2. **Identify the biggest pain.** Where is the most manual data entry happening? That is your first integration target.
3. **Check for APIs.** Do the two systems involved have APIs? If yes, you are in business.
4. **Start small.** Use a middleware tool like Zapier or n8n for your first integration. Get a win, then expand.
5. **Document everything.** Field mappings, schedules, error handling. Future you will thank present you.

## Next steps

- For bespoke integration development, visit [ajairu.dev](https://ajairu.dev)
- Use the [Software Audit Template](software-audit-template.md) to assess your existing systems
- Use the [Build vs Buy Calculator](build-vs-buy-calculator.md) to evaluate integration tools

## Disclaimer

This guide is provided as general guidance, not professional advice. For integration support tailored to your specific systems and requirements, contact [ajairu.dev](https://ajairu.dev).
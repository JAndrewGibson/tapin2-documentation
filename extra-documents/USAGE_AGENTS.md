# Tapin2 API Usage Guide for AI Agents

This document provides essential context and technical constraints for AI agents tasked with integrating or interacting with the Tapin2 API.

## API Overview
The Tapin2 API is a REST-based service providing venue, event, product, and order management. It uses multiple versions (`v1`, `v2`, `v3`, `v4`) depending on the specific feature set.

## 🔑 Authentication
All requests require a `Key` header:
- **Header**: `Key`
- **Value**: `Key={TAPIN2_API_KEY}`

## ⚠️ Critical Technical Constraints

### 1. Timezone Discrepancy
AI agents MUST handle timezones differently depending on the controller type:
- **Events/Schedules**: Returned in **Local Venue Time** (e.g., `04/30/2026 8:00 AM`).
- **Orders/Financials**: Returned in **UTC** (e.g., `2026-04-30T18:45:00Z`).
- **Resolution**: Cross-reference the `venue.timeZoneInfo` object to localize order timestamps for end-users.

### 2. Sandbox Blocked Endpoints
The following operations are known to fail in the sandbox environment and should be handled gracefully:
- **Category Creation**: `POST /Category` (Returns 500).
- **Cart Operations**: `POST /cart/add`, `remove`, `updatequantity` (Returns 500).
- **Legacy Reports**: `v1/reports/*` (Returns 500).

Refer to [known-issues.md](known-issues.md) for a full list of deficiencies.

## 📦 Core Data Models
Refer to the following structured models for response parsing:
- [EventType](../models/event_type.md): Pricing and categorization for events.
- [Product](../models/product.md): Item metadata and pricing.
- [Order/Item](../models/item.md): Transaction and line-item details.
- [Modifier](../models/modifier.md): Flattened (v4) or nested (v2) product options.
- [Venue](../models/venue.md): Top-level venue configuration and metadata.
- [Location](../models/location.md): Physical service areas (stands, bars, etc.).

## 🛠️ Best Practices
- **Large Payloads**: Product and Order arrays can be massive. Always use `count` or `limit` parameters when exploring.
- **Sanitization**: When generating examples or logs, always replace real Venue IDs and Product IDs with placeholders (e.g., `VENUE_ID_1`).
- **Order Verification**: Always verify an order's status (`isPaidInFull`) before confirming fulfillment.

---
- [METHODOLOGY.md](METHODOLOGY.md): Explanation of the verification and sanitization process.
- [known-issues.md](known-issues.md): Full list of API caveats and deficiencies.

[← Back to Main Registry](../README.md)

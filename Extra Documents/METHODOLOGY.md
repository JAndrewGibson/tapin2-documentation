---
layout: default
title: Methodology
---

# Methodology

This document outlines the testing and verification process used to ensure the accuracy of the Tapin2 API documentation. Given that the official documentation is frequently incomplete or incorrect, I rely on a systematic exploratory approach.

## Verification Process

### 1. Exploratory Probing
Every endpoint is tested against live sandbox environments using various venue types to capture structural variance:
- **Suite-based Venues**: Used to verify tab-based workflows, packages, and complex product components.
- **Concessions-based Venues**: Used to verify standard, flat-rate concession behavior.

### 2. Schema Discovery
Since sample responses in official docs are often incorrect, I generate schemas based on live JSON responses. I perform:
- **Null-Value Analysis**: Repeated calls across different events/venues to identify optional fields.
- **Data Type Validation**: Confirming whether fields are consistent (e.g., ensuring IDs are consistently integers vs. strings).
- **Component Deep-Dives**: For complex objects like "Combos" or "Packages," I map out the nested structures that differ from standard products.

### 3. Versioning Strategy
I explicitly test different version headers (`v1` through `v4`) and `{version}` placeholders to determine:
- Feature parity between versions.
- Deprecation status.
- Structural changes in responses.

### 4. Safety & State Integrity
For any state-modifying endpoints (`PUT`, `POST` on orders, etc.), the following rules apply:
- **Pre-Approval**: No state-modifying call is made without explicit user consent.
- **Isolated Testing**: Tests are performed only on specific items or venues designated by the user as "safe for modification."

### 5. Sanitization & Anonymization
To ensure security and privacy, all documented responses undergo a sanitization process:
- **Identifier Masking**: Real Venue IDs, Product IDs, and Event IDs are replaced with generic placeholders (e.g., `VENUE_ID_1`).
- **PII Removal**: Customer names, emails, and physical addresses are scrubbed and replaced with "Example Name" or "123 Example Way."
- **Internal Reference Scrubbing**: Proprietary internal IDs and ERP reference strings are replaced with generic identifiers or `null`.

## Documentation Quality Standards
- **Real Examples**: All examples are derived from live API responses, not extrapolated from official documentation.
- **Granular Detail**: Each endpoint is documented in its own file to prevent information bleed between versions or similar-looking endpoints.
- **Model-Driven Structure**: Complex objects link to shared schemas in the `models/` directory for consistency across the documentation suite.

---
[← Back to Main Registry](../README.md)

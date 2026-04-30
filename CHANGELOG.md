# Changelog

All notable changes to this documentation project will be noted here.

## [1.1.0] - 2026-04-30

### Documentation & Probing
- **Category POST**: Documented `{version}/Category`. Identified a consistent `500 Internal Server Error` (`NullReferenceException` in `SubmitIntegrationsAsync`) likely due to POS synchronization failures in the sandbox.
- **Event Search**: Documented `POST v2/events/{minDate}/{maxDate}`. Confirmed this functions as a search tool requiring a `venueId` payload rather than an event creation tool.
- **Unprinted Orders**: Verified and documented `v2/venues/{venueId}/orders/unprinted`. Successfully captured the full response structure including nested discount and fee objects using a live test order.
- **Cart Management**: Probed `POST v2/cart/add`, `remove`, and `updatequantity`. Identified a `500 Internal Server Error` (`ArgumentNullException`) in the `OrderingCutOff` logic, even when valid event and location contexts are provided.
- **Orders (Small)**: Documented `GET v4/venues/{venueId}/events/{eventId}/orders/small`. Verified the flattened response structure and confirmed it includes simplified item and modifier data.
- **Order Item Bump**: Documented and verified `POST v4/venues/{id}/orders/{id}/items/{id}/bump`. Confirmed successful fulfillment progression with a `true` response.
- **Error Logging**: Documented and verified `POST v2/venues/{venueId}/error`. Confirmed `204 No Content` success status for client-side telemetry reporting.
- **Project Progress**: Achieved **100% Documentation Progress** across all 34 identified endpoints.

### Findings & Caveats
- **Timezone Discrepancy**: Identified a critical architectural inconsistency where Event endpoints return localized venue time (PST) while Order-related endpoints return timestamps in **UTC**.
- **Sanitization**: Performed a site-wide audit and sanitization of sensitive data. All real IDs (`venueId`, `productId`, `eventId`) and team names have been replaced with generic placeholders in example responses.
- **Deficiency Tracking**: Formalized the tracking of blocked endpoints, distinguishing between backend 500 errors (Blocked) and 404/Empty responses (Incomplete/Unverified).

### UI & Polish
- **Cross-Referencing**: Implemented a "Related Endpoints" section across major documentation pages to improve discoverability.
- **Enhanced Models**: Added `Venue` and `Location` shared models to complete the core data schema suite.
- **Methodology Expansion**: Updated [METHODOLOGY.md](METHODOLOGY.md) with formal sanitization and model-driven documentation standards.
- **Agentic Usage**: Created [USAGE_AGENTS.md](USAGE_AGENTS.md) as a downloadable context provider for external AI agents.
- **Model Linking**: Replicated the behavior of the original Tapin2 help system by creating a `models/` directory for shared structures (Product, EventType, Item, etc.) and linking the "Type" column in documentation tables to these models.
- **Help Link Precision**: Corrected "Original Documentation" links to point to the specific route-based URLs on the Tapin2 help site rather than the generic landing page.
- **Known Issues Guide**: Created [known_issues.md](known_issues.md) (renamed from `BLOCKED.md`) as a comprehensive guide to sandbox deficiencies and caveats.
- **README Redesign**: Overhauled the main registry with:
    - A clear **Status Legend** for Documented, Blocked, and Planned states.
    - Improved visual hierarchy using folder icons (📂) for expandable categories.
    - Removal of progress percentages for a cleaner, production-ready presentation.
    - Direct integration of a "View Known Issues" badge.
- **Bulk Linking**: Systematically added [🔗 View Original Documentation](https://api.tapin2.co/help) links to all 34 endpoint documentation files.
- **Support Integration**: Added official **support@tapin2.co** contact information across all relevant help guides.

## [1.0.0] - 2026-04-29
### Added
- Dark mode support added to GitHub Pages site via Jekyll midnight theme.
- Initial project structure and categorization established.
- Changelog created to track iterative probing progress.

## [0.1.0] - 2026-04-29
### Added
- Initial endpoint documentation for Categories, Events, Locations, Products, and Venues.
- [METHODOLOGY.md](METHODOLOGY.md) created to explain the live verification and sanitization process.
- Initial "Known Deficiencies" section added to the README.
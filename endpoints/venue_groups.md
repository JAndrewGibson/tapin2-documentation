# Venue Group IDs

Retrieve the list of venue identifiers associated with a specific venue group.

- **Endpoint**: `v2/venuegroups/{groupId}/venueids`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Status: Known Deficiency

This endpoint currently returns a `404 Not Found` error in the sandbox environment. Venue groups are used for organizations managing multiple physical sites (e.g., an entire university campus or multiple stadiums). 

---
[← Back to Endpoint Registry](../README.md)

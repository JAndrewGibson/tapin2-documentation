# Tapin2 API Documentation

This repository serves as the primary, complete source of documentation for the Tapin2 API.

## Project Goal

The objective is to provide exhaustive documentation for every endpoint in the Tapin2 ecosystem, filling the gaps found in the [existing lackluster documentation](https://api.tapin2.co/help).

Beyond documenting known endpoints, this project includes exploratory efforts to discover and verify additional, undocumented endpoints and parameters.

**[View the API Endpoint Registry](endpoints/README.md)**

## Repository Structure

- `agents.md`: Essential context for AI agents working on this repo (venue IDs, auth patterns).
- `METHODOLOGY.md`: Detailed explanation of our API verification and documentation process.
- `endpoints/`: (To be created) Detailed documentation per endpoint category.
- `discovery/`: (To be created) Logs and findings from API exploration.

## Setup & Usage

### Authentication
Requests require a `Key` header:
`Key={TAPIN2_API_KEY}`

Create a `.env` file in the root directory:
```env
TAPIN2_API_KEY=your_key_here
```

### Exploratory Calling
Scripts for discovery and verification will be housed in the `scripts/` directory (future implementation).

## Key Venue Types
- **Suites**: Suite-based service including tabs and packages.
- **Concessions**: Standard physical concession stand service.

## Known Deficiencies & Limitations

- **Translations (`v2/venues/{venueId}/translations`)**: Currently returns an empty object `{}` for all tested venues. The mechanism for populating these strings is currently unverified.
- **Suite-based Event Data**: Current event calls for suite-based venues frequently return `null` outside of specific preorder windows.
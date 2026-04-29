# Documentation Planned

This endpoint has been identified but is not yet fully documented in this repository.

## How to Contribute
I'm systematically probing the Tapin2 API to verify responses against live sandbox data. If you have experience with this endpoint or have sample JSON responses (sanitized), please feel free to:
1. Probe the endpoint using the sample script below.
2. Create a new documentation file in the `endpoints/` directory using our standard schema.
3. Update the main `README.md` registry.

### Sample Verification Script
You can use the following Python snippet to probe undocumented endpoints. Ensure you have your `TAPIN2_API_KEY` and `VENUE_ID` ready.

```python
import requests
import json

# Configuration
API_KEY = "YOUR_API_KEY"
VENUE_ID = "YOUR_VENUE_ID"
ENDPOINT = "v2/venues/{venueId}/example" # Update this

url = f"https://api.tapin2.co/{ENDPOINT.replace('{venueId}', VENUE_ID)}"
headers = {"Key": API_KEY, "Content-Type": "application/json"}

print(f"Calling: {url}")
response = requests.get(url, headers=headers)

if response.status_code == 200:
    print(json.dumps(response.json(), indent=4))
else:
    print(f"Error {response.status_code}: {response.text}")
```

## Documentation Requirements
- Use the **Full Structure** rule: do not omit fields for brevity.
- Sanitize all data (use "Example Venue", "Product ABC", etc.).
- Include a link back to the registry.

---
[← Back to Endpoint Registry](../README.md)

# Venue Sections

Retrieve a list of seating sections and their groups for a specific event.

- **Endpoint**: `v2/venues/{venueId}/events/{eventId}/sections`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `eventId` | Integer | Path | The unique identifier for the event. |

## Response Structure

Returns an array of section objects.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the section. |
| `title` | String | Name of the section (e.g., "101", "305"). |
| `group` | Object | The seating group this section belongs to. |
| `rowTitle` | String | Custom title for rows in this section (often empty). |
| `numberTitle` | String | Custom title for seat numbers in this section (often empty). |

### Seating Group Object

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | ID of the seating group. |
| `title` | String | Name of the group (e.g., "Lower Bowl", "Club Seats"). |

## Example Response (Sanitized)

```json
[
    {
        "id": 1001,
        "title": "101",
        "group": {
            "id": 10,
            "title": "Example Seating Group"
        },
        "rowTitle": "",
        "numberTitle": ""
    },
    {
        "id": 1002,
        "title": "102",
        "group": {
            "id": 10,
            "title": "Example Seating Group"
        }
    }
]
```

## Venue-Specific Notes

- **Data Slicing**: Some venues have hundreds of sections. This endpoint is useful for building seat selection or delivery location pickers.
- **Groupings**: Sections are logically grouped (e.g., by level or ticket type) to simplify UI display.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-events-eventId-sections)

[← Back to Endpoint Registry](../README.md)

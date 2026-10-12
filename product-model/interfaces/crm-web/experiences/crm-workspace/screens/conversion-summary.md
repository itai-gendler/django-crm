---
{
  "entities": [
    {
      "entity": "request",
      "shows": [
        "Receipt date",
        "Source",
        "Subsequent",
        "Country"
      ]
    },
    {
      "entity": "deal",
      "shows": [
        "Stage",
        "Closing reason"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/request.py"
    }
  ]
}
---

# Conversion summary

Request/Deal conversion and stage criteria.

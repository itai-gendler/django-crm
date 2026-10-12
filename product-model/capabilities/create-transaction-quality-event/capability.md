---
{
  "availability": [
    {
      "place": "crm-web::crm-workspace"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "quality/models/transaction_quality.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "quality/site/transactionqualityeventadmin.py"
    }
  ]
}
---

# Create transaction quality event

Retain a distinct Transaction quality event with supplied information and source defaults.

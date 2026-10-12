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
      "target": "crm/utils/rates_loader.py"
    }
  ]
}
---

# Refresh exchange rates

Refresh enabled conversion information on its configured schedule. Provider failures do not establish fresh rates.

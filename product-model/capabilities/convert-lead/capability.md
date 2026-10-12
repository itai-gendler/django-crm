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
      "target": "crm/site/leadadmin.py"
    }
  ],
  "domain": "leads"
}
---

# Convert lead

The conversion resolves or creates the Company and Contact person, rewires related records and removes the source Lead.

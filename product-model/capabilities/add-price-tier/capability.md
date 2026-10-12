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
      "target": "crm/site/productadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/tieredpricinginline.py"
    }
  ],
  "domain": "products"
}
---

# Add price tier

Missing tiers are generated from category rules when present, otherwise department rules. Existing names are skipped and nonbase calculation uses the retained nonzero base price.

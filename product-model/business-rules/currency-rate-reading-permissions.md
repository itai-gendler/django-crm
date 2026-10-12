---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "currency-rate",
      "effect": "reads"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/payment.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Currency rate reading permissions

Reads retained rates in permitted payment/pricing/report presentation.

Historical-rate lookup follows the actual initiating payment, pricing or report path. Native parent access uses its actual requesting User and native operation/proxy permission where called; helper paths preserve their own staff-only checks. The calculation performs no independent Currency rate model-view check.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "currency",
      "effect": "reads"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/payment.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/currencyadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    },
    {
      "unattended": true
    }
  ]
}
---

# Currency reading permissions

Reads Currency information in permitted pricing/financial presentation.

Currency lookup in native pricing, payment and financial projections follows the actual initiating User’s parent native operation or report-proxy checks. Staff helpers use their actual wrapper, without a separately invented Currency model-view check. Unattended lookup follows the corresponding capture or refresh dispatch; the conversion-refresh Testing gate does not prohibit monthly report capture solely because Testing is enabled.

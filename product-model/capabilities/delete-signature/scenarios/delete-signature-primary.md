---
{
  "kind": "primary",
  "routes": {
    "main": "Delete signature"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Signature and invoke delete.",
      "entities": [
        {
          "entity": "signature",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::signature-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Remove the selected Signature.",
      "entities": [
        {
          "entity": "signature",
          "effect": "removes"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::signature-record"
        }
      },
      "actor": "sales-manager"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/signatureadmin.py"
    }
  ]
}
---

# Delete signature

## Trigger

Sales manager invokes Delete signature.

## Outcome

Remove the selected Signature.

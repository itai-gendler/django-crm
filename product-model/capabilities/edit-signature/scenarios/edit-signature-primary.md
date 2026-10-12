---
{
  "kind": "primary",
  "routes": {
    "main": "Edit signature"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Signature and invoke edit.",
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
      "text": "The selected Signature retains the submitted Name, Content, Type, Default. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "signature",
          "effect": "changes",
          "facts": [
            "Name",
            "Content",
            "Type",
            "Default",
            "Department"
          ]
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

# Edit signature

## Trigger

Sales manager invokes Edit signature.

## Outcome

The selected Signature retains the submitted Name, Content, Type, Default. Read-only fields retain their previous values and invalid form input returns field errors.

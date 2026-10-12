---
{
  "kind": "primary",
  "routes": {
    "main": "Create signature"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Save the named signing content and default choice.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::signature-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct Signature is retained with Name, Content, Type, Default. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
      "entities": [
        {
          "entity": "signature",
          "effect": "creates",
          "facts": [
            "Name",
            "Content",
            "Type",
            "Default",
            "Owner",
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

# Create signature

## Trigger

Sales manager invokes Create signature.

## Outcome

A distinct Signature is retained with Name, Content, Type, Default. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

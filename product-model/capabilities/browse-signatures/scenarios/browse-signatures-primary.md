---
{
  "kind": "primary",
  "routes": {
    "main": "Browse signatures"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Signature and invoke browse.",
      "entities": [
        {
          "entity": "signature",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::signature-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "Present the source-defined Signature selection, search/filter results and summary facts.",
      "entities": [
        {
          "entity": "signature",
          "effect": "reads",
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
          "place": "crm-web::crm-workspace::signature-browser"
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

# Browse signatures

## Trigger

Sales manager invokes Browse signatures.

## Outcome

Present the source-defined Signature selection, search/filter results and summary facts.

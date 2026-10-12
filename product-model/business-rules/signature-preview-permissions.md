---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "signature",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/signature_previews.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/signatureadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Signature preview permissions

Reads Signature preview; logged-in handler, no owner recheck.

The handler requires a logged-in requesting account. It resolves the selected signature without an additional native signature View or owner comparison.

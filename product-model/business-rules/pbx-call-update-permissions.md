---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "contact-person",
      "effect": "changes",
      "facts": [
        "Last contact"
      ],
      "contexts": [
        {
          "place": "zadarma-notifications"
        }
      ]
    },
    {
      "type": "entity",
      "id": "lead",
      "effect": "changes",
      "facts": [
        "Last contact"
      ],
      "contexts": [
        {
          "place": "zadarma-notifications"
        }
      ]
    },
    {
      "type": "entity",
      "id": "activity-log",
      "effect": "changes",
      "facts": [
        "Entries"
      ],
      "contexts": [
        {
          "place": "zadarma-notifications"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "voip/views/voipwebhook.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/contactadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/leadadmin.py"
    }
  ],
  "permits": [
    {
      "actors": [
        "zadarma-pbx"
      ]
    }
  ]
}
---

# Pbx call update permissions

Changes matched Contact/Lead last-contact and Deal workflow facts through supported PBX events; Zadarma actor. Provider identity validation is separate.

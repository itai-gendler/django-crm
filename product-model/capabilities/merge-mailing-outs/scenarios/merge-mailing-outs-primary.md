---
{
  "kind": "primary",
  "routes": {
    "main": "Merge mailing outs"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Invoke the offered merge control with the stated input.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "reads",
          "facts": [],
          "as": "first-original"
        },
        {
          "entity": "mailing-out",
          "effect": "reads",
          "facts": [],
          "as": "second-original"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "A new compatible Mailing Out retains deduplicated pending recipient IDs and the source counts and recipient results; selected originals are removed and the new record opens.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "creates",
          "facts": [
            "Name",
            "Message",
            "Recipient type",
            "Status",
            "Pending recipients",
            "Successful recipients",
            "Failed recipients",
            "Recipient count",
            "Successful count",
            "Failed count",
            "Daily count",
            "Sending date",
            "Report",
            "Email account",
            "Owner",
            "Department",
            "Created",
            "Updated",
            "Modified by"
          ],
          "as": "merged-campaign"
        },
        {
          "entity": "mailing-out",
          "effect": "removes",
          "as": "first-original"
        },
        {
          "entity": "mailing-out",
          "effect": "removes",
          "as": "second-original"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-browser"
        }
      },
      "actor": "sales-manager"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/mailingoutadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/admin_actions.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/utils/sendmassmail.py"
    }
  ]
}
---

# Merge mailing outs

## Trigger

Sales manager invokes Merge mailing outs.

## Outcome

A new compatible Mailing Out retains deduplicated pending recipient IDs and the source counts/history; selected originals are removed and the new record opens.

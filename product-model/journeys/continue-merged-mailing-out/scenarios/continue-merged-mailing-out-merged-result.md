---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
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
      },
      "capability": "merge-mailing-outs"
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
      "actor": "sales-manager",
      "capability": "merge-mailing-outs"
    },
    {
      "kind": "product",
      "actor": "sales-manager",
      "capability": "merge-mailing-outs",
      "text": "The Product opens the created campaign editor for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-browser"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Mailing Out and invoke edit.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "reads",
          "facts": [],
          "as": "merged-campaign"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      },
      "capability": "edit-mailing-out"
    },
    {
      "kind": "product",
      "text": "The Product saves: selected Mailing Out retains the submitted Message, Status, Report. Source-defined read-only links and attribution remain unchanged.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "changes",
          "facts": [
            "Message",
            "Status",
            "Report"
          ],
          "as": "merged-campaign"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      },
      "actor": "sales-manager",
      "capability": "edit-mailing-out"
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

# Continue merged mailing out — merged result

## Trigger

The sales manager starts by invoke the offered merge control with the stated input.

## Outcome

The selected Mailing Out retains the submitted Message, Status, Report. Source-defined read-only links and attribution remain unchanged.

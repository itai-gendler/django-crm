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
      "text": "Submit the eligible newsletter audience selection.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
        }
      },
      "capability": "create-mailing-out"
    },
    {
      "kind": "product",
      "text": "A paused Mailing Out is retained from the eligible selected Company audience, with its message, recipient type and queues, then opens for editing.",
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
          ]
        },
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
        }
      },
      "actor": "sales-manager",
      "capability": "create-mailing-out"
    },
    {
      "kind": "product",
      "actor": "sales-manager",
      "capability": "create-mailing-out",
      "text": "The Product opens the created campaign editor for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
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
          "facts": []
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
          ]
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

# Prepare mailing out — selected company

## Trigger

The sales manager starts by submit the eligible newsletter audience selection.

## Outcome

The selected Mailing Out retains the submitted Message, Status, Report. Source-defined read-only links and attribution remain unchanged.

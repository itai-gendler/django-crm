---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The filtered Contact person selection is passed to campaign creation with its actual owner filter.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        }
      ],
      "capability": "create-mailing-out",
      "actor": "sales-manager"
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Submit the eligible newsletter audience selection.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
        }
      },
      "capability": "create-mailing-out"
    },
    {
      "kind": "product",
      "text": "The campaign uses the filtered Contact selection and actual owner filter.",
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
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
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
          "place": "crm-web::crm-workspace"
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

# Prepare mailing out — filtered contact

## Trigger

The sales manager starts by submit the eligible newsletter audience selection.

## Outcome

The selected Mailing Out retains the submitted Message, Status, Report. Source-defined read-only links and attribution remain unchanged.

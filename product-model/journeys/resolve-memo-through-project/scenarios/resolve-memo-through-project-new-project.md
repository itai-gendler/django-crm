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
      "actor": "co-worker",
      "text": "Submit the selected unlinked Memo using its work creation button.",
      "entities": [
        {
          "entity": "memo",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::memo-record"
        }
      },
      "capability": "edit-memo"
    },
    {
      "kind": "product",
      "text": "The Product saves the submitted office content and addressee before opening the work creation form.",
      "entities": [
        {
          "entity": "memo",
          "effect": "changes",
          "facts": [
            "Name",
            "Description",
            "Conclusion",
            "Recipient",
            "Updated",
            "Modified by"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::memo-record"
        }
      },
      "actor": "co-worker",
      "capability": "edit-memo"
    },
    {
      "kind": "product",
      "actor": "co-worker",
      "capability": "edit-memo",
      "text": "The Product opens the prefilled work Add form for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::memo-record"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Save work content, dates and responsible people.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::project-record"
        }
      },
      "capability": "create-project"
    },
    {
      "kind": "product",
      "text": "New work links to its Memo with the observed review/resolution/file effects.",
      "entities": [
        {
          "entity": "project",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Note",
            "Priority",
            "Stage",
            "Active",
            "Start date",
            "Due date",
            "Closing date",
            "Next step",
            "Next step date",
            "Reminder",
            "Owner",
            "Co-owner",
            "Department",
            "Responsible people",
            "Subscribers",
            "Tags",
            "Created",
            "Updated",
            "Modified by"
          ]
        },
        {
          "entity": "file",
          "effect": "creates",
          "facts": [
            "Filename",
            "Media location",
            "Attached subject",
            "Attached to Deal"
          ],
          "with": "project"
        },
        {
          "entity": "memo",
          "effect": "changes",
          "facts": [
            "Stage",
            "Review date",
            "Conclusion",
            "Project"
          ]
        },
        {
          "entity": "resolution",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::project-record"
        }
      },
      "actor": "co-worker",
      "capability": "create-project"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/memoadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/projectadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    }
  ]
}
---

# Resolve memo through project — new project

## Trigger

The co worker starts by select Memo and invoke edit.

## Outcome

New work links to its Memo with the observed review/resolution/file effects.

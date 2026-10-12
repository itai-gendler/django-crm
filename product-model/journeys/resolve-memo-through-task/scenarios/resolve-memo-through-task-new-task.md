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
      "text": "The Product opens the prefilled child-work Add form for the next action.",
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
      "text": "Save work content, stage, dates and responsible people.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      },
      "capability": "create-task"
    },
    {
      "kind": "product",
      "text": "New work links to its Memo with the observed review/resolution/file effects.",
      "entities": [
        {
          "entity": "task",
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
            "Completion token",
            "Hide main task",
            "Owner",
            "Co-owner",
            "Department",
            "Responsible people",
            "Subscribers",
            "Tags",
            "Parent task",
            "Project",
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
          "with": "task"
        },
        {
          "entity": "memo",
          "effect": "changes",
          "facts": [
            "Stage",
            "Review date",
            "Conclusion",
            "Task"
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
          "place": "crm-web::crm-workspace::task-record"
        }
      },
      "actor": "co-worker",
      "capability": "create-task"
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
      "target": "tasks/site/taskadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/forms.py"
    }
  ]
}
---

# Resolve memo through task — new task

## Trigger

The co worker starts by select Memo and invoke edit.

## Outcome

New work links to its Memo with the observed review/resolution/file effects.

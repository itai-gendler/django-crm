---
{
  "kind": "primary",
  "routes": {
    "main": "Create project — from memo"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected unreviewed Memo is used to prefill new linked work.",
      "entities": [
        {
          "entity": "memo",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "co-worker"
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
      }
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
      "actor": "co-worker"
    }
  ],
  "references": [
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

# Create project — from memo

## Trigger

Co worker invokes Create project.

## Outcome

New work links to its Memo with the observed review/resolution/file effects.

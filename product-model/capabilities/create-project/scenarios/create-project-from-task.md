---
{
  "kind": "primary",
  "routes": {
    "main": "Create project — from task"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The Add form receives content, subscriber defaults and attachment choices from the selected Task.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Note",
            "Responsible people"
          ]
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
      "text": "A distinct Project retains the submitted content and participant choices prefilled from the source Task; the creation path adds no persistent link back to that source.",
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
          "entity": "task",
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

# Create project — from task

## Trigger

Co worker invokes Create project.

## Outcome

A distinct Project retains the submitted content and participant choices prefilled from the source Task; the creation path adds no persistent link back to that source.

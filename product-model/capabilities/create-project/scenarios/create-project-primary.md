---
{
  "kind": "primary",
  "routes": {
    "main": "Create project"
  },
  "steps": [
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
      "text": "A distinct Project is retained with the submitted Name, Description, Note, Priority, due date, stage and responsible people. Start date comes from its retained default. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
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

# Create project

## Trigger

Co worker invokes Create project.

## Outcome

A distinct Project is retained with the submitted Name, Description, Note, Priority, due date, stage and responsible people. Start date comes from its retained default. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

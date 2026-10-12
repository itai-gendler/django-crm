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
      "actor": "department-head",
      "text": "Submit the current Task form using its creation submit button.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      },
      "capability": "edit-task"
    },
    {
      "kind": "product",
      "text": "The Product saves the current Task before redirecting to the associated work Add form.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Name",
            "Description",
            "Note",
            "Due date",
            "Priority",
            "Stage",
            "Active",
            "Updated",
            "Modified by"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      },
      "actor": "department-head",
      "capability": "edit-task"
    },
    {
      "kind": "product",
      "actor": "department-head",
      "capability": "edit-task",
      "text": "The successful parent save opens the work Add form with copied content, participant defaults and selectable attachments.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "department-head",
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
      "actor": "department-head",
      "capability": "create-project"
    }
  ],
  "references": [
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/projectadmin.py"
    }
  ]
}
---

# Create project from task — department head

## Trigger

The department head starts by submit the current Task form using its creation submit button.

## Outcome

A distinct Project is created from copied source content; this path does not convert or relink the source work.

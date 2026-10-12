---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/task.py"
    }
  ],
  "domain": "tasks",
  "relations": [
    {
      "entity": "task",
      "verb": "has subtask",
      "cardinality": "one-to-many"
    },
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    },
    {
      "entity": "activity-log",
      "verb": "has workflow",
      "cardinality": "one-to-one"
    }
  ]
}
---

# Task

Work content, priority, active/closed stage, dates/follow-up, reminder flag, completion token, hide-main choice and workflow; owner/co-owner, responsible people, subscribers, tags, parent Task, Project and Files

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Description** — Retained descriptive content.
- **Note** — Additional retained notes on the assigned work.
- **Priority** — Selected work priority.
- **Stage** — The selected configured processing stage.
- **Active** — Whether this record remains active.
- **Start date** — Retained start date; current work fieldsets provide no editable start-date input.
- **Due date** — Date by which the assigned work is due.
- **Closing date** — Date recorded by the implemented closure branch.
- **Next step** — The retained follow-up action.
- **Next step date** — The retained follow-up date.
- **Reminder** — Whether the subject carries an active reminder indication.
- **Completion token** — The retained token used to find this Task through notification links; recipient binding, expiry and single use are not established.
- **Hide main task** — Whether this participant has chosen to hide the related main work from their ordinary list.
- **Owner** — The account responsible for this record.
- **Co-owner** — The additional account sharing responsibility.
- **Department** — The organizational scope retained on this record.
- **Responsible people** — People assigned the work; this is distinct from owner/co-owner and subscribers.
- **Subscribers** — People retained to follow changes and receive the implemented notices.
- **Tags** — Selected retained classification membership.
- **Parent task** — Reference to the main work to which this subtask belongs.
- **Project** — Reference to the related project.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.
- **Responsible count** — The number of retained responsible people, evaluated from that membership when applying work controls.

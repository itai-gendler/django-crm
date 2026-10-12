---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "deal"
    },
    {
      "type": "entity",
      "id": "task"
    },
    {
      "type": "entity",
      "id": "project"
    },
    {
      "type": "entity",
      "id": "memo"
    },
    {
      "type": "entity",
      "id": "email"
    },
    {
      "type": "entity",
      "id": "history"
    },
    {
      "type": "entity",
      "id": "activity-log"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/deal.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/task.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/project.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/memo.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/crmemail.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/taskbase.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/memoadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/taskadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/projectadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/send_email.py"
    }
  ]
}
---

# Activity recording

Subject Activity log entries and History are automatic recording consequences, not independently authorized Step mutations. Task creation records the account supplied to its native save; subtask creation also records on its parent, and Project-linked Task creation records on the Project. Task stage/completion and follow-up branches record the observed next step and account attribution; sole-responsible follow-up edited by another account appends that account. Child follow-up records on the parent; child stage/completion records the implemented parent entry. Automatic parent closure records that closure after exact eligibility/set checks. Project creation and follow-up/stage processing record at their inspected save points; Memo processing retains the source note/review entries. Deal stage, close and follow-up operations record at their actual branches. Normal Email sending records its success in linked Deal workflow before the final Sent save; no independent Deal-edit authorization is called. Native admin saves/removals produce their History entries where the framework invokes recording. Source-supplied attribution is retained, including the internally selected User in public completion; it is not caller identity proof.

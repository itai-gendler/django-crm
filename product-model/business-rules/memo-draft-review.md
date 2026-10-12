---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "memo"
    },
    {
      "type": "entity",
      "id": "user-profile"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/memo.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/memoadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/userprofileadmin.py"
    }
  ]
}
---

# Memo draft review

Draft/notified/stage/review changes preserve notice suppression, release and review branches.

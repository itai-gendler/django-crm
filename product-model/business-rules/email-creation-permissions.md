---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::email-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/crmemail.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/create_email.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/reply_email.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Email creation permissions

Native Add uses the initiating active staff account's effective crm.add_crmemail permission. The linked-email GET only prepares Add and does not persist correspondence; saving that form uses native Add. The Deal attachment-selection POST, reply and forward helpers save drafts under their actual staff wrapper without independently checking Email Add or source-object model access. Native Email Add does not become staff-only merely because helper creation is staff-only. Automatic import follows its inspected configured queue consumer, not a human native Add. The account evaluated is the actual initiating request account; direct and assigned Group permissions and native superuser handling apply where native permission is called.

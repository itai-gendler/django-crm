---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email"
    },
    {
      "type": "entity",
      "id": "email-account"
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
      "target": "massmail/models/email_account.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/send_email.py"
    }
  ]
}
---

# Email sending outcomes

Sending resolves the main EmailAccount by Email.owner, which can differ from the initiating account. Missing subject, missing content or the lone <br> body returns the saved draft with an error before SMTP; missing owner's main account has its own error. Addresses are parsed, and the message is assembled before the send try block. Normal processing calls SMTP first, assigns Sent in memory, records a success notice and linked Deal workflow, then persists Sent and redirects to the Email browser. Authentication, connect/data/header/recipient/disconnect/sender errors and ValueError caught in that block return to the draft without the final Sent save. A failure after an external attempt can leave delivery uncertain; the failure response is no delivery proof. Uncaught construction/save failures have no invented graceful response. Linked Deal workflow saving invokes no independent direct Deal-edit check. Accepted processing does not prove recipient delivery.

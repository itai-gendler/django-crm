---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "mailing-out"
    },
    {
      "type": "entity",
      "id": "email-account"
    },
    {
      "type": "entity",
      "id": "newsletter-recipient"
    },
    {
      "type": "entity",
      "id": "mailing-settings"
    },
    {
      "type": "entity",
      "id": "product-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/mailing_out.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/email_account.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/unsubscribes.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "settings/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "webcrm/settings.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/mailingoutadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/utils/sendmassmail.py"
    }
  ]
}
---

# Campaign delivery

Actual schedule, account rotation, counters, recipient failures and disabled-account effects retained; Done may retain failure history.

The unattended sender requires Mailing enabled and Testing false and reads the canonical settings row. It processes Active and Active but Error queues and takes at most one campaign per owner in a pass. Business-time scheduling uses its start/end window and the implemented Friday/Saturday/Sunday exclusion. Enabled mass-mail accounts belong to the campaign owner; same-day accounts are skipped only when their count is greater than the configured threshold. New sending days reset daily counts. Registration routing is maintained for the actual recipient/account selection. Normal sending moves a recipient to the successful list and increments account and campaign counters. Account authentication/sender failure disables mass mailing on that account, retains account/campaign diagnostics and leaves that recipient for later processing; recipient-level failure moves its identifier to the failed list and marks the campaign Active but Error. Empty pending queues can become Done while failed-recipient information remains. No durable retry, recipient delivery or exactly-once guarantee follows from those status transitions.

---
{
  "scope": "Named commercial, work, correspondence, campaign, intake, reporting and supporting operations at commit 873806c982d52c28476c24c01d1a5a224e812302.",
  "method": "Static read-only source inspection and documentation leads.",
  "covered": [
    {
      "description": "CRM routing, native-site access, language and session-scope code",
      "paths": [
        "webcrm/urls.py",
        "webcrm/settings.py",
        "common/site/",
        "common/utils/usermiddleware.py",
        "crm/site/crmmodeladmin.py",
        "crm/utils/clarify_permission.py",
        "common/utils/admin_redirect_middleware.py"
      ]
    },
    {
      "description": "Request, counterparty and Deal model/form/handler operations",
      "paths": [
        "crm/models/",
        "crm/forms/",
        "crm/site/",
        "crm/views/",
        "crm/utils/create_form_request.py",
        "crm/utils/create_objects.py"
      ]
    },
    {
      "description": "Output pricing calculation and its browser behavior",
      "paths": [
        "crm/views/product_price_info.py",
        "crm/static/crm/js/outputinline.js"
      ]
    },
    {
      "description": "Task, Project, Memo, assignment and notification completion code",
      "paths": [
        "tasks/models/",
        "tasks/site/",
        "tasks/forms.py",
        "tasks/views/",
        "tasks/urls.py",
        "common/utils/email_to_participants.py",
        "common/templatetags/util.py",
        "tests/utils/helpers.py"
      ]
    },
    {
      "description": "Correspondence send, administration flags, IMAP import and inquiry-linkage code",
      "paths": [
        "crm/utils/send_email.py",
        "crm/utils/import_emails.py",
        "crm/utils/restore_imap_emails.py",
        "crm/utils/create_email_request.py",
        "common/views/select_emails_import.py",
        "common/views/select_email_account.py",
        "crm/apps.py",
        "crm/admin.py"
      ]
    },
    {
      "description": "Campaign, recipient-routing, reusable-message and signature operations",
      "paths": [
        "massmail/models/",
        "massmail/site/",
        "massmail/admin_actions.py",
        "massmail/views/",
        "massmail/utils/sendmassmail.py"
      ]
    },
    {
      "description": "Common profile, attachment, reminder and displayed-history operations",
      "paths": [
        "common/models.py",
        "common/admin.py",
        "common/site/userprofileadmin.py",
        "common/site/reminderadmin.py",
        "common/forms/",
        "common/utils/reminders_sender.py",
        "common/utils/remind_me.py",
        "common/utils/get_file_links.py"
      ]
    },
    {
      "description": "Chat audience, author and unread-status code",
      "paths": [
        "chat/models.py",
        "chat/site/",
        "chat/forms/"
      ]
    },
    {
      "description": "Financial and commercial report projections and snapshot capture code",
      "paths": [
        "analytics/models.py",
        "analytics/site/",
        "analytics/utils/"
      ]
    },
    {
      "description": "Quality event and weight presentation code",
      "paths": [
        "quality/models/",
        "quality/site/"
      ]
    },
    {
      "description": "PBX notification, callback and conversion refresh code",
      "paths": [
        "voip/models.py",
        "voip/urls.py",
        "voip/views/",
        "voip/backends/zadarmabackend.py",
        "crm/utils/rates_loader.py"
      ]
    },
    {
      "description": "Effective settings and intake suppression usage",
      "paths": [
        "settings/models.py",
        "crm/utils/helpers.py"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Deployment, container and CI machinery",
      "paths": [
        ".github/"
      ]
    },
    {
      "description": "Packaging, setup and ordinary test cases; tests/utils/helpers.py is separately inspected as production-used synthetic-client behavior.",
      "paths": [
        "requirements.txt",
        "tests/"
      ]
    },
    {
      "description": "Migration execution mechanisms",
      "paths": [
        "crm/migrations/",
        "tasks/migrations/",
        "common/migrations/",
        "massmail/migrations/"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "Full native user, permission and configuration administration",
      "paths": [
        "common/admin.py",
        "settings/admin.py",
        "crm/site/",
        "massmail/site/",
        "voip/admin.py"
      ]
    },
    {
      "description": "Complete credential, OAuth, remote-mailbox operations and restoration variants",
      "paths": [
        "massmail/",
        "common/views/select_emails_import.py",
        "crm/utils/restore_imap_emails.py"
      ]
    },
    {
      "description": "User transfer, department copying, diagnostics and City consolidation",
      "paths": [
        "common/",
        "crm/views/delete_duplicate_object.py"
      ]
    },
    {
      "description": "Mailing image uploads, ancillary result views and arbitrary related-subject combinations",
      "paths": [
        "massmail/views/",
        "common/views/"
      ]
    },
    {
      "description": "Help and translation-service operations",
      "paths": [
        "help/",
        "crm/utils/"
      ]
    },
    {
      "description": "Inherited framework operations and deletion/navigation variants beyond the named operations",
      "paths": [
        "common/site/",
        "crm/site/",
        "tasks/site/"
      ]
    },
    {
      "description": "Additional role-specific achieved handoff runs",
      "paths": [
        "tasks/site/",
        "crm/views/",
        "massmail/views/",
        "chat/site/"
      ]
    },
    {
      "description": "Deployment media-serving transport and byte-delivery authorization",
      "paths": [
        "webcrm/urls.py",
        "common/utils/get_file_links.py"
      ]
    }
  ],
  "limitations": [
    {
      "description": "Anonymous import and callback branches lack a fully established successful contract",
      "paths": [
        "crm/site/crmadminsite.py",
        "voip/views/callback.py"
      ]
    },
    {
      "description": "Shipped role configuration does not establish deployed memberships or direct grants",
      "paths": [
        "common/fixtures/groups.json",
        "common/utils/usermiddleware.py"
      ]
    },
    {
      "description": "Asynchronous and external-service branches do not establish durable retry or delivery guarantees",
      "paths": [
        "crm/utils/import_emails.py",
        "massmail/utils/sendmassmail.py",
        "common/utils/reminders_sender.py",
        "voip/backends/zadarmabackend.py"
      ]
    },
    {
      "description": "Public completion uses input-selected User and synthetic native posts without established caller binding, expiry or single-use enforcement",
      "paths": [
        "tasks/views/task_completed.py",
        "tasks/views/create_completed_subtask.py"
      ]
    },
    {
      "description": "Deployment media-byte authorization is not established by advertised links",
      "paths": [
        "common/utils/get_file_links.py",
        "webcrm/urls.py"
      ]
    },
    {
      "description": "Report criteria and conversion scopes differ between the inspected projections",
      "paths": [
        "analytics/site/",
        "analytics/utils/"
      ]
    },
    {
      "description": "Canonical sender settings usage does not establish uniqueness or complete administration of extra rows",
      "paths": [
        "settings/models.py",
        "common/utils/reminders_sender.py",
        "massmail/utils/sendmassmail.py"
      ]
    }
  ]
}
---

# Coverage

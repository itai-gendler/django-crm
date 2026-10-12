---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "product-price-tier",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::product-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/productadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/tieredpricinginline.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmstackedinline.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Product price tier creation permissions

Ordinary manual inline Add never authorizes Tier creation: the inline Add check is false for everyone, including Superuser. Generation dispatched by the Product save control creates missing tiers only after the initiating account's native Product save. Existing Product generation requires effective crm.change_product and access through ProductAdmin's actual queryset; generation after native Add requires effective crm.add_product. The actual initiating User's direct permissions, assigned Group permissions and native superuser handling supply effective permission. Generation performs no independent add_productpricetier check. This dispatch grants no manual inline Add. ProductAdmin derives from plain ModelAdmin and applies no CRM owner/co-owner clarification. Its queryset uses selected department first, otherwise Superoperator's assigned department Groups, otherwise is unfiltered. Product Modified by and update time are saved before tier generation; missing department is supplied from the current selected department. Category rules take precedence over department rules; missing base rule, missing base tier and existing zero base price have separate outcomes.

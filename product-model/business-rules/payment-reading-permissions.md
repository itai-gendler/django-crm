---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "payment",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::payment-record"
        },
        {
          "place": "crm-web::crm-workspace::payment-browser"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/payment.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/paymentadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/paymentinline.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Payment reading permissions

Native Add uses the configured model add permission. Inline creation uses Payment change permission and Deal clarification. Reading uses the actual Payment queryset and object-view checks. Editing additionally requires manager ownership/co-ownership and matching operator department when those roles apply. Removal has the manager restriction but no corresponding operator department check

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

PaymentAdmin uses plain ModelAdmin lookup: Superoperator restricts first to Deal departments represented by its assigned Groups; otherwise a selected department restricts unless the account is Accountant; otherwise the base queryset is used. Native view uses effective View or Change. Native Change/Delete check the corresponding effective permission first. Change rejects Manager outside Deal owner/co-owner and rejects Operator outside its current department; Delete has the Manager restriction without the Operator comparison. These overlapping flags are tested as implemented, without a broader privileged-role override. Inline Add/Change/Delete instead follow PaymentInline’s change permission and parent Deal clarification. Automatic removal of nonreceived entries after unsuccessful Deal closure follows that initiating save, not a separate payment-delete check.

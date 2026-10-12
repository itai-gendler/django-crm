---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webcrm/settings.py"
    }
  ],
  "singleton": true
}
---

# Product settings

Effective operating configuration used by mapped behavior: testing/debug and feature gates, exchange-rate schedule, VAT and relevant configured defaults

## Information kept

- **Testing** — The effective testing switch read by sender and startup guards.
- **Debug** — The effective debug switch read by the reminder sender.
- **Mailing enabled** — The effective mailing gate required by unattended delivery.
- **Exchange rate schedule** — Effective schedule and update configuration consulted by automatic conversion refresh.
- **VAT** — The effective VAT display/calculation configuration.
- **Configured defaults** — Effective defaults consulted by mapped handlers, including language, timezone and feature choices.

## Intent

This is the effective operating configuration read by mapped behavior.

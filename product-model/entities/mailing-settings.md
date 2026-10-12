---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "settings/models.py"
    }
  ],
  "singleton": true
}
---

# Mailing settings

Effective canonical settings: daily account limit, business-time choice/start/end and unsubscribe destination

## Information kept

- **Daily account limit** — The configured sending threshold, checked by the source with today_count greater than the threshold.
- **Business time** — Whether the sender applies its configured hours and Friday/Saturday/Sunday exclusion.
- **Business start** — Configured start of the business-time sending window.
- **Business end** — Configured end of the business-time sending window.
- **Unsubscribe destination** — The configured destination of known and unknown unsubscribe outcomes.

## Intent

This is the canonical settings instance read by the corresponding sender. Extra settings rows and their administration are not represented as additional effective instances.

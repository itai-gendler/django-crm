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

# Reminder settings

Effective canonical reminder check interval

## Information kept

- **Check interval** — The canonical sender’s check interval in seconds; fallback creates 300 unless configured otherwise.

## Intent

This is the canonical settings instance read by the corresponding sender. Extra settings rows and their administration are not represented as additional effective instances.

---
{
  "type": "webhook",
  "actors": [
    "zadarma-pbx"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webcrm/urls.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "voip/views/voipwebhook.py"
    }
  ]
}
---

# Zadarma notifications

The provider challenge and call-end notification contract.

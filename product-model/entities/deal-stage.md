---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/others.py"
    }
  ]
}
---

# Deal stage

Name/order, department and default/success/conditional-success/shipment choices

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Order** — Configured order of presentation.
- **Department** — The organizational scope retained on this record.
- **Default** — Marks the corresponding configured default choice.
- **Second default** — Marks the stage used by the commercial default-stage advancement.
- **Successful** — Marks the configured successful outcome used by commercial closure.
- **Conditionally successful** — Marks a stage that also sets the retained commercial win timestamp.
- **Goods shipped** — Marks the commercial stage selected by configured shipment handling.

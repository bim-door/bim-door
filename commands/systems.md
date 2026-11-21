# UNION commands: Systems

1 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## Mechanical Control Device

A UNION command on the Systems tab, Mechanical panel. It asks: "Click a wall face, or click to place free, for the mechanical control device".

### Press it

- Tab: Systems
- Panel: Mechanical
- Kind: tool
- Ribbon: Building Services > Mechanical

Worked example: press **Mechanical Control Device** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Mechanical Control Device · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Mechanical Control Device' on Systems's Mechanical panel: the tool 'Mechanical Control Device' stands | keys: Escape (tool Mechanical Control Device -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Tag on Placement | yesno | false |  | all |
| Type | choice | Thermostat | Thermostat, CO2 Sensor, Humidistat | all |

Played in these jobs:

- [3068. Draw a 6 x 4 m office, place a space in it and put a thermostat on the wall beside the door position.](../examples/building-services.md)

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

# UNION commands: Tools

1 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## modify-trim

A UNION command on the Tools tab, Adjust panel.

### Press it

- Tab: Tools
- Panel: Adjust
- Kind: action
- Ribbon: Modify > Edit

Worked example: press **modify-trim** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:modify-trim · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'modify-trim' on Modify's Edit panel (through its fold) (through its parent 'Trim/Extend''s arrow, the row 'Trim/Extend Selection'; the press stood 56 ms (the menu stood at 19 ms; its row ran 17 ms; it made 0 child widgets native)): the tool 'modify-trim' stands | keys: Escape (tool modify-trim -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Mode | choice | By Selection | By Selection, Corner, Single, Multiple | all |

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

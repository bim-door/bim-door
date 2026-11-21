# UNION commands: External

4 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## IFC Property Sets

A UNION command on the External tab, Imports panel. Also known as ifc-psets.

### ifc-psets

- Tab: External
- Panel: Imports
- Kind: action
- Ribbon: Insert > Import

Worked example: press **IFC Property Sets** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:ifc-psets · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'ifc-psets' on Insert's Import panel (through its parent 'Import''s arrow, the row 'IFC Property Sets'; the press stood 62 ms (the menu stood at 17 ms; its row ran 45 ms; the window's first paint at 45 ms in union_shell::ShellDialogWindow, dialog 'Browse IFC'; the dialog stood 1098 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Browse' opened and stood; closed by the player | inside the modal 'Browse' | keys: Escape (no tool, dialog 'Browse' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Scope | choice | all | all, selection | all |
| Property Sets | choice | all | all, psets, qtos | all |

## ifc-assemblies

A UNION command on the External tab, Imports panel.

### Press it

- Tab: External
- Panel: Imports
- Kind: action
- Ribbon: Insert > Import

Worked example: press **ifc-assemblies** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:ifc-assemblies · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'ifc-assemblies' on Insert's Import panel (through its parent 'Import''s arrow, the row 'IFC Assemblies'; the press stood 431 ms (the menu stood at 369 ms; its row ran 62 ms; the window's first paint at 62 ms in union_shell::ShellDialogWindow, dialog 'IFC Assemblies'; the dialog stood 1082 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'IFC Assemblies' opened and stood; closed by the player | inside the modal 'IFC Assemblies' | keys: Escape (no tool, dialog 'IFC Assemblies' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Keep Whole Body | yesno | true |  | all |
| Nest | yesno | true |  | all |

## ifc-classes

A UNION command on the External tab, Imports panel.

### Press it

- Tab: External
- Panel: Imports
- Kind: action
- Ribbon: Insert > Import

Worked example: press **ifc-classes** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:ifc-classes · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'ifc-classes' on Insert's Import panel (through its parent 'Import''s arrow, the row 'IFC Classifications'; the press stood 437 ms (the menu stood at 17 ms; its row ran 419 ms; it made 0 child widgets native)): it refused in words: cannot proceed: no IFC file is named

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Scope | choice |  | All, View, Selection | all |
| Source | text |  |  | all |

## ifc-types

A UNION command on the External tab, Imports panel.

### Press it

- Tab: External
- Panel: Imports
- Kind: action
- Ribbon: Insert > Import

Worked example: press **ifc-types** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:ifc-types · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'ifc-types' on Insert's Import panel (through its parent 'Import''s arrow, the row 'IFC Types'; the press stood 809 ms (the menu stood at 350 ms; its row ran 457 ms; it made 0 child widgets native)): it refused in words: cannot proceed: no IFC file is chosen

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Bind Sections | yesno | true |  | all |
| IFC File | text |  |  | all |

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

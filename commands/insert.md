# UNION commands: Insert

13 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## Copy/Monitor

A UNION command on the Insert tab, Link panel.

### Press it

- Tab: Insert
- Panel: Link
- Kind: action
- Ribbon: Insert > Link

Worked example: press **Copy/Monitor** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:Copy/Monitor · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Copy/Monitor' on Insert's Link panel (the window's first paint at 86 ms in union_shell::ShellDialogWindow, dialog 'Browse IFC'): the dialog 'Copy/Monitor' opened and stood; closed by the player | inside the modal 'Copy/Monitor' | keys: Escape (no tool, dialog 'Copy/Monitor' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Detail Library

A UNION command on the Insert tab, Load from Library panel.

### Press it

- Tab: Insert
- Panel: Load from Library
- Kind: dialog
- Ribbon: Detailing > Detail

Worked example: press **Detail Library** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Library · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Detail Library' on Annotate's Detail panel (through its fold) (the window's first paint at 128 ms in union_shell::ShellDialogWindow, dialog 'Detail Library'): the dialog 'Detail Library' opened and stood; closed by the player | inside the modal 'Detail Library' | keys: Escape (no tool, dialog 'Detail Library' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## IFC Materials

A UNION command on the Insert tab, Import panel. Also known as ifc-materials.

### ifc-materials-dialog

- Tab: Insert
- Panel: Import
- Ribbon: Insert > Import

Worked example: press **IFC Materials** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:ifc-materials-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'ifc-materials-dialog' on Insert's Import panel (through its parent 'Import''s arrow, the row 'IFC Materials'; the press stood 505 ms (the menu stood at 423 ms; its row ran 82 ms; the window's first paint at 82 ms in union_shell::ShellDialogWindow, dialog 'IFC Materials'; the dialog stood 1201 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'IFC Materials' opened and stood; closed by the player | inside the modal 'IFC Materials' | keys: Escape (no tool, dialog 'IFC Materials' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## IFC Openings

A UNION command on the Insert tab, Import panel.

### ifc-openings-dialog

- Tab: Insert
- Panel: Import
- Ribbon: Insert > Import

Worked example: press **IFC Openings** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:ifc-openings-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'ifc-openings-dialog' on Insert's Import panel (through its parent 'Import''s arrow, the row 'IFC Openings'; the press stood 89 ms (the menu stood at 24 ms; its row ran 65 ms; the window's first paint at 65 ms in union_shell::ShellDialogWindow, dialog 'IFC Openings'; the dialog stood 1094 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'IFC Openings' opened and stood; closed by the player | inside the modal 'IFC Openings' | keys: Escape (no tool, dialog 'IFC Openings' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Insert 2D Elements from File

A UNION command on the Insert tab, Load from Library panel.

### Press it

- Tab: Insert
- Panel: Load from Library
- Kind: action
- Ribbon: Insert > Load from Library

Worked example: press **Insert 2D Elements from File** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:Insert 2D Elements from File · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Insert 2D Elements from File' on Insert's Load from Library panel (the window's first paint at 63 ms in union_shell::ShellDialogWindow, dialog 'Browse IFC'): the dialog 'Insert 2D Elements from File' opened and stood; closed by the player | inside the modal 'Insert 2D Elements from File' | keys: Escape (no tool, dialog 'Insert 2D Elements from File' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Insert Views from File

A UNION command on the Insert tab, Load from Library panel.

### Press it

- Tab: Insert
- Panel: Load from Library
- Ribbon: Insert > Load from Library

Worked example: press **Insert Views from File** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:Insert Views from File · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Insert Views from File' on Insert's Load from Library panel (the window's first paint at 63 ms in union_shell::ShellDialogWindow, dialog 'Browse IFC'): the dialog 'Browse' opened and stood; closed by the player | inside the modal 'Browse' | keys: Escape (no tool, dialog 'Browse' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Links Manager

A UNION command on the Insert tab, Link panel. Also known as Manage Links.

### Manage Links

- Tab: Insert
- Panel: Link
- Kind: dialog
- Ribbon: Manage > Manage Project

Worked example: press **Links Manager** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:Manage Links · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Manage Links' on Manage's Manage Project panel (the window's first paint at 255 ms in union_shell::ShellDialogWindow, dialog 'Links Manager'): the dialog 'Links Manager' opened and stood; closed by the player | inside the modal 'Links Manager' | keys: Escape (no tool, dialog 'Links Manager' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Load Block

A UNION command on the Insert tab, Load from Library panel. Also known as Load Family.

### Load Family

- Tab: Insert
- Panel: Load from Library
- Kind: dialog
- Ribbon: Insert > Load from Library

Worked example: press **Load Block** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:Load Family · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Load Family' on Insert's Load from Library panel (the window's first paint at 343 ms in union_shell::ShellDialogWindow, dialog 'Load Block'): the dialog 'Load Block' opened and stood; closed by the player | inside the modal 'Load Block' | keys: Escape (no tool, dialog 'Load Block' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## New Block

A UNION command on the Insert tab, Load from Library panel.

### Press it

- Tab: Insert
- Panel: Load from Library
- Ribbon: Insert > Load from Library

Worked example: press **New Block** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:New Block · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'New Block' on Insert's Load from Library panel (the window's first paint at 9 ms in QDialog#BlockEditorWindow, dialog 'Block Editor'): the command 'New Block' ran | keys: Escape (no tool, dialog 'Block Editor · New Generic Model' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## New Block › Casework

A UNION command on the Insert tab, Load from Library panel.

### Press it

- Tab: Insert
- Panel: Load from Library
- Ribbon: Insert > Load from Library > New Block

Worked example: press **New Block › Casework** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:New Block › Casework · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'New Block › Casework' on Insert's Load from Library panel (through its parent 'New Block''s arrow, the row 'Casework'; the press stood 713 ms (the menu stood at 320 ms; its row ran 379 ms; the window's first paint at 16 ms in QDialog#BlockEditorWindow, dialog 'Block Editor'; it made 0 child widgets native)): the command 'New Block › Casework' ran | keys: Escape (no tool, dialog 'Block Editor · New Casework' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## New Block › Furniture

A UNION command on the Insert tab, Load from Library panel.

### Press it

- Tab: Insert
- Panel: Load from Library
- Ribbon: Insert > Load from Library > New Block

Worked example: press **New Block › Furniture** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:New Block › Furniture · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'New Block › Furniture' on Insert's Load from Library panel (through its parent 'New Block''s arrow, the row 'Furniture'; the press stood 754 ms (the menu stood at 343 ms; its row ran 396 ms; the window's first paint at 16 ms in QDialog#BlockEditorWindow, dialog 'Block Editor'; it made 0 child widgets native)): the command 'New Block › Furniture' ran | keys: Escape (no tool, dialog 'Block Editor · New Furniture' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## New Block › Generic Model

A UNION command on the Insert tab, Load from Library panel.

### Press it

- Tab: Insert
- Panel: Load from Library
- Ribbon: Insert > Load from Library > New Block

Worked example: press **New Block › Generic Model** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:New Block › Generic Model · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'New Block › Generic Model' on Insert's Load from Library panel (through its parent 'New Block''s arrow, the row 'Generic Model'; the press stood 448 ms (the menu stood at 11 ms; its row ran 426 ms; the window's first paint at 11 ms in QDialog#BlockEditorWindow, dialog 'Block Editor'; it made 0 child widgets native)): the command 'New Block › Generic Model' ran | keys: Escape (no tool, dialog 'Block Editor · New Generic Model' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Project Files

A UNION command on the Insert tab, Link panel. Also known as Manage Project.

### Press it

- Tab: Insert
- Panel: Link
- Kind: dialog
- Ribbon: Insert > Link

Worked example: press **Project Files** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:Project Files · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Project Files' on Insert's Link panel (through its parent 'Manage Links''s arrow, the row 'Project Files'; the press stood 374 ms (the menu stood at 341 ms; its row ran 33 ms; the window's first paint at 33 ms in QDialog; the dialog stood 1054 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Project Files' opened and stood; closed by the player | inside the modal 'Project Files' | keys: Escape (no tool, dialog 'Project Files' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

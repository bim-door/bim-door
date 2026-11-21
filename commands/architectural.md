# UNION commands: Architectural

6 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## Area and Volume Computations

A UNION command on the Architectural tab, Room & Area panel.

### area-computations

- Tab: Architectural
- Panel: Room & Area
- Ribbon: Architectural > Room & Area

Worked example: press **Area and Volume Computations** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:area-computations · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'area-computations' on Architecture's Room & Area panel (through its fold) (the window's first paint at 201 ms in union_shell::ShellDialogWindow, dialog 'Area and Volume Computations'): the dialog 'Area and Volume Computations' opened and stood; closed by the player | inside the modal 'Area and Volume Computations' | keys: Escape (no tool, dialog 'Area and Volume Computations' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Ceiling Settings

A UNION command on the Architectural tab, Build panel.

### draw-ceiling-dialog

- Tab: Architectural
- Panel: Build
- Ribbon: Architectural > Build

Worked example: press **Ceiling Settings** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:draw-ceiling-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'draw-ceiling-dialog' on Architecture's Build panel (through its parent 'draw-ceiling''s arrow, the row 'Ceiling Settings'; the press stood 511 ms (the menu stood at 406 ms; its row ran 105 ms; the window's first paint at 105 ms in union_shell::ShellDialogWindow, dialog 'Ceiling'; the dialog stood 1149 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Ceiling' opened and stood; closed by the player | inside the modal 'Ceiling' | keys: Escape (no tool, dialog 'Ceiling' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Component

A UNION command on the Architectural tab, Build panel.

### Press it

- Tab: Architectural
- Panel: Build
- Ribbon: Architectural > Build

Worked example: press **Component** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Component · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Component' on Architecture's Build panel: the tool 'Component' stands | keys: Escape (tool Component -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Ramp Settings

A UNION command on the Architectural tab, Circulation panel.

### draw-ramp-settings

- Tab: Architectural
- Panel: Circulation
- Ribbon: Architectural > Circulation

Worked example: press **Ramp Settings** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:draw-ramp-settings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'draw-ramp-settings' on Architecture's Circulation panel (through its parent 'draw-ramp''s arrow, the row 'Ramp Settings'; the press stood 419 ms (the menu stood at 327 ms; its row ran 92 ms; the window's first paint at 92 ms in union_shell::ShellDialogWindow, dialog 'Ramp'; the dialog stood 1088 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Ramp' opened and stood; closed by the player | inside the modal 'Ramp' | keys: Escape (no tool, dialog 'Ramp' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Stair Settings

A UNION command on the Architectural tab, Circulation panel.

### draw-stair-settings

- Tab: Architectural
- Panel: Circulation
- Ribbon: Architectural > Circulation

Worked example: press **Stair Settings** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:draw-stair-settings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'draw-stair-settings' on Architecture's Circulation panel (through its parent 'draw-stair''s arrow, the row 'Stair Settings'; the press stood 1494 ms (the menu stood at 1349 ms; its row ran 145 ms; the window's first paint at 145 ms in union_shell::ShellDialogWindow, dialog 'Stair'; the dialog stood 3349 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Stair' opened and stood; closed by the player | inside the modal 'Stair' | keys: Escape (no tool, dialog 'Stair' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Vertical

A UNION command on the Architectural tab, Opening panel.

### Press it

- Tab: Architectural
- Panel: Opening
- Ribbon: Architectural > Opening

Worked example: press **Vertical** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Vertical · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Vertical' on Architecture's Opening panel (through its fold): the command 'Vertical' ran; status 'Click one corner of the shaft footprint' | keys: Escape (tool Shaft -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

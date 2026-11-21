# UNION commands: Detailing

22 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## annotate-autodim

A UNION command on the Detailing tab, Dimensions panel.

### Press it

- Tab: Detailing
- Panel: Dimensions
- Kind: action
- Ribbon: Detailing > Dimension

Worked example: press **annotate-autodim** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:annotate-autodim · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'annotate-autodim' on Annotate's Dimension panel: the command 'annotate-autodim' ran; status 'Dimension All: nothing to dimension on Ground (no grid, exterior wall run or opening)' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Grids | yesno | true |  | all |
| Offset | length | 1500 |  | all |
| Openings | yesno | true |  | all |
| Walls | yesno | true |  | all |

## Arc

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Start-End-Radius Arc

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Arc** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Start-End-Radius Arc · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Detail Line › Start-End-Radius Arc' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Arc'; the press stood 41 ms (the menu stood at 17 ms; its row ran 9 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Arc works in a plan, section or elevation view

## Arc, Center and Ends

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Center-ends Arc

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Arc, Center and Ends** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Center-ends Arc · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Detail Line › Center-ends Arc' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Arc, Center and Ends'; the press stood 34 ms (the menu stood at 16 ms; its row ran 6 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Arc, Center and Ends works in a plan, section or elevation view

## Arc, Fillet

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Fillet Arc

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Arc, Fillet** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Fillet Arc · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Detail Line › Fillet Arc' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Arc, Fillet'; the press stood 50 ms (the menu stood at 24 ms; its row ran 10 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Arc, Fillet works in a plan, section or elevation view

## Arc, Tangent End

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Tangent End Arc

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Arc, Tangent End** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Tangent End Arc · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Detail Line › Tangent End Arc' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Arc, Tangent End'; the press stood 75 ms (the menu stood at 36 ms; its row ran 16 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Arc, Tangent End works in a plan, section or elevation view

## Automatic Dimensions

A UNION command on the Detailing tab, Dimension panel.

### annotate-autodim-dialog

- Tab: Detailing
- Panel: Dimension
- Ribbon: Detailing > Dimension

Worked example: press **Automatic Dimensions** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:annotate-autodim-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'annotate-autodim-dialog' on Annotate's Dimension panel: it refused in words: cannot proceed: automatic dimensions are placed on a plan view; the view shown is @3d

## Circle

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Circle

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Circle** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Circle · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Detail Line › Circle' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Circle'; the press stood 50 ms (the menu stood at 28 ms; its row ran 9 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Circle works in a plan, section or elevation view

## Cloud Revision

A UNION command on the Detailing tab, Detail panel.

### annotate-revision-dialog

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail

Worked example: press **Cloud Revision** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:annotate-revision-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'annotate-revision-dialog' on Annotate's Detail panel (through its fold) (the window's first paint at 99 ms in union_shell::ShellDialogWindow, dialog 'Cloud Revision'): the dialog 'Cloud Revision' opened and stood; closed by the player | inside the modal 'Cloud Revision' | keys: Escape (no tool, dialog 'Cloud Revision' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Count

A UNION command on the Detailing tab, Detail panel.

### Press it

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail

Worked example: press **Count** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Count · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Count' on Annotate's Detail panel (through its fold) (the window's first paint at 152 ms in union_shell::ShellDialogWindow, dialog 'Count'): the dialog 'Count' opened and stood; closed by the player | inside the modal 'Count' | keys: Escape (no tool, dialog 'Count' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Ellipse

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Ellipse

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Ellipse** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Ellipse · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Detail Line › Ellipse' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Ellipse'; the press stood 109 ms (the menu stood at 24 ms; its row ran 61 ms; it made 0 child widgets native)): the command 'Detail Line › Ellipse' ran; status 'Click to start the detail line' | keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Elliptical Arc

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Partial Ellipse

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Elliptical Arc** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Partial Ellipse · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Detail Line › Partial Ellipse' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Elliptical Arc'; the press stood 127 ms (the menu stood at 34 ms; its row ran 70 ms; it made 0 child widgets native)): the command 'Detail Line › Partial Ellipse' ran; status 'Click one end of the axis' | keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Join Lines

A UNION command on the Detailing tab, Detail panel.

### Press it

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail

Worked example: press **Join Lines** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Join Lines · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Join Lines' on Annotate's Detail panel (through its fold): the tool 'Join Lines' stands | keys: Escape (tool Join Lines -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Line

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Line

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Line** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Line · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Detail Line › Line' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Line'; the press stood 435 ms (the menu stood at 12 ms; its row ran 422 ms; it made 0 child widgets native)): the command 'Detail Line › Line' ran; status 'Click to start the detail line' | keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [5010. Detail a 1200 square pad footing at 1:20 with the column stub, bottom bars as dots and a cogged bar, and the pad dimensions.](../examples/annotation-details-and-materials.md)

## Loaded Tags

A UNION command on the Detailing tab, Tag panel.

### Press it

- Tab: Detailing
- Panel: Tag
- Ribbon: Detailing > Tag

Worked example: press **Loaded Tags** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Loaded Tags · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Loaded Tags' on Annotate's Tag panel (through its fold) (the window's first paint at 245 ms in union_shell::ShellDialogWindow, dialog 'Loaded Tags'): the dialog 'Loaded Tags' opened and stood; closed by the player | inside the modal 'Loaded Tags' | keys: Escape (no tool, dialog 'Loaded Tags' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Match Properties

A UNION command on the Detailing tab, Detail panel.

### Press it

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail

Worked example: press **Match Properties** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Match Properties · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Match Properties' on Annotate's Detail panel (through its fold): the tool 'Match Properties' stands | keys: Escape (tool Match Properties -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Pick Lines

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Pick Lines

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Pick Lines** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Pick Lines · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Detail Line › Pick Lines' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Pick Lines'; the press stood 198 ms (the menu stood at 12 ms; its row ran 174 ms; it made 0 child widgets native)): the command 'Detail Line › Pick Lines' ran; status 'Click a Grid or Wall line to pick' | keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Polygon

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Inscribed Polygon

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Polygon** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Inscribed Polygon · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Detail Line › Inscribed Polygon' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Polygon'; the press stood 50 ms (the menu stood at 20 ms; its row ran 8 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Polygon works in a plan, section or elevation view

## Polygon, Circumscribed

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Circumscribed Polygon

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Polygon, Circumscribed** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Circumscribed Polygon · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Detail Line › Circumscribed Polygon' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Polygon, Circumscribed'; the press stood 57 ms (the menu stood at 22 ms; its row ran 16 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Polygon, Circumscribed works in a plan, section or elevation view

## Rectangle

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Rectangle

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Rectangle** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Rectangle · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Detail Line › Rectangle' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Rectangle'; the press stood 58 ms (the menu stood at 30 ms; its row ran 11 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Rectangle works in a plan, section or elevation view

Played in these jobs:

- [5050. Lay out a switchboard front at 1:10: the cabinet, three breaker rows as rectangles and a label strip.](../examples/annotation-details-and-materials.md)

## Region › Filled Region

A UNION command on the Detailing tab, Detail panel.

### Press it

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Region

Worked example: press **Region › Filled Region** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Region › Filled Region · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Region › Filled Region' on Annotate's Detail panel (through its fold) (through its parent 'Region''s arrow, the row 'Filled Region'; the press stood 414 ms (the menu stood at 20 ms; its row ran 392 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Region › Filled Region works in a plan, section or elevation view

## Region › Masking Region

A UNION command on the Detailing tab, Detail panel.

### Press it

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Region

Worked example: press **Region › Masking Region** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Region › Masking Region · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Region › Masking Region' on Annotate's Detail panel (through its fold) (through its parent 'Region''s arrow, the row 'Masking Region'; the press stood 50 ms (the menu stood at 20 ms; its row ran 11 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Region › Masking Region works in a plan, section or elevation view

## Spline

A UNION command on the Detailing tab, Detail panel.

### Detail Line › Spline

- Tab: Detailing
- Panel: Detail
- Ribbon: Detailing > Detail > Detail Line

Worked example: press **Spline** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line › Spline · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Detail Line › Spline' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Spline'; the press stood 56 ms (the menu stood at 21 ms; its row ran 12 ms; it made 0 child widgets native)): the command 'Detail Line › Spline' ran; status 'Click the first point of the spline' | keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

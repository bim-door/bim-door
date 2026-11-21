# UNION commands: View

30 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## 2D View

A UNION command on the View tab, Create panel. Also known as Drafting View.

### Drafting View

- Tab: View
- Panel: Create
- Kind: tool
- Ribbon: Views > Create

Worked example: press **2D View** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Drafting View · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Drafting View' on View's Create panel (the window's first paint at 63 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player | inside the modal 'New Drafting View' | keys: Escape (no tool, dialog 'New Drafting View' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Scale | choice | 50 |  | all |

Played in these jobs:

- [4047. Start a 1:10 drafting view called Gutter Detail, open a sheet for it and place it.](../examples/views-sheets-and-schedules.md)
- [5009. Give me a 1:10 slab edge detail with a rebate for the brick, a drip groove, a rebate hatch and the slab depth noted.](../examples/annotation-details-and-materials.md)
- [5010. Detail a 1200 square pad footing at 1:20 with the column stub, bottom bars as dots and a cogged bar, and the pad dimensions.](../examples/annotation-details-and-materials.md)
- [5024. Draw a 100 mm pipe and a 50 mm riser in section at 1:5 and give each a diameter or radius dimension.](../examples/annotation-details-and-materials.md)
- [5040. Detail a 600 by 300 concrete beam section at 1:10: stirrup, three top and three bottom bars as circles, and the cover noted.](../examples/annotation-details-and-materials.md)
- [5047. Draw an externally lagged round duct section at 1:5: the duct wall, 50 mm lagging all round and a foil jacket.](../examples/annotation-details-and-materials.md)
- [5049. Sketch a hex nut in plan, a washer circle and a curved cable run in a drafting view to show our bolted joint symbol.](../examples/annotation-details-and-materials.md)
- [5050. Lay out a switchboard front at 1:10: the cabinet, three breaker rows as rectangles and a label strip.](../examples/annotation-details-and-materials.md)
- [5064. Draw the pipe clip fixing a 50 mm pipe to a concrete soffit at 1:5, with the anchor and the clip spacing noted.](../examples/annotation-details-and-materials.md)
- [5067. Draw a 20 mm conduit and a socket box in a stud wall at 1:5 with the stud, the lining and the box depth.](../examples/annotation-details-and-materials.md)

## Area Boundary

A UNION command on the View tab, Create panel. It asks: "Click to start the area boundary".

### Press it

- Tab: View
- Panel: Create
- Kind: tool
- Ribbon: Architectural > Room & Area
- Draw modes: Line, Pick Lines

Worked example: press **Area Boundary** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Area Boundary · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Area Boundary' on Architecture's Room & Area panel (through its fold): the tool 'Area Boundary' stands | keys: Escape (tool Area Boundary -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Apply Area Rules | yesno | true |  | Pick Lines |
| Offset | length | 0 |  | Pick Lines |

## Border

A UNION command on the View tab, Sheet Composition panel. Also known as Title Block.

### Title Block

- Tab: View
- Panel: Sheet Composition
- Kind: tool
- Ribbon: Views > Sheet Composition

Worked example: press **Border** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Title Block · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Title Block' on View's Sheet Composition panel (through its fold): it refused in words: cannot proceed: Title Block works in a plan, section or elevation view

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Size | choice | A1 | A0, A1, A2, A3, A4, ANSI_B, ANSI_C, ANSI_D, ANSI_E, ARCH_C, ARCH_D, ARCH_E, ARCH_E1 | all |

## Camera

A UNION command on the View tab, Create panel.

### 3D View › Camera

- Tab: View
- Panel: Create
- Kind: tool
- Ribbon: Views > Create > 3D View

Worked example: press **Camera** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:3D View › Camera · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed '3D View › Camera' on View's Create panel (through its parent '3D View''s arrow, the row 'Camera'; the press stood 794 ms (the menu stood at 336 ms; its row ran 457 ms; it made 0 child widgets native)): the tool '3D View › Camera' stands | keys: Escape (tool 3D View › Camera -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| From | level | Level 1 |  | all |
| Offset | length | 1750 |  | all |
| Perspective | yesno | true |  | all |
| Scale | number | 100 |  | all |

## Cascade

A UNION command on the View tab, Windows panel. Also known as Cascade Windows.

### Cascade Windows

- Tab: View
- Panel: Windows
- Kind: action
- Ribbon: Views > Windows

Worked example: press **Cascade** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Cascade Windows · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Cascade Windows' on View's Windows panel (through its fold): the command 'Cascade Windows' ran; status 'Cascade: 2 windows stepped, @3d in front -- click a window to bring it forward' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Copy View

A UNION command on the View tab, Create panel. Also known as Duplicate View.

### Duplicate View

- Tab: View
- Panel: Create
- Kind: action
- Ribbon: Views > Create

Worked example: press **Copy View** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Duplicate View · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Duplicate View' on View's Create panel: the command 'Duplicate View' ran; status 'Ground Copy 1 made' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Cut Shape

A UNION command on the View tab, Graphics panel. Also known as Cut Profile. It asks: "Click an element, then sketch the cut profile".

### Cut Profile

- Tab: View
- Panel: Graphics
- Kind: tool
- Ribbon: Views > Graphics
- Draw modes: Line

Worked example: press **Cut Shape** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Cut Profile · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Cut Profile' on View's Graphics panel (through its fold): the tool 'Cut Profile' stands | keys: Escape (tool Cut Profile -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Drawing

A UNION command on the View tab, Sheet Composition panel. Also known as Sheet.

### Sheet

- Tab: View
- Panel: Sheet Composition
- Kind: tool
- Ribbon: Views > Sheet Composition

Worked example: press **Drawing** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Sheet · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Sheet' on View's Sheet Composition panel (through its fold) (the window's first paint at 364 ms in union_shell::ShellDialogWindow, dialog 'New Sheet'): the dialog 'New Sheet' opened and stood; closed by the player | inside the modal 'New Sheet' | keys: Escape (no tool, dialog 'New Sheet' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [4047. Start a 1:10 drafting view called Gutter Detail, open a sheet for it and place it.](../examples/views-sheets-and-schedules.md)

## Elevation

A UNION command on the View tab, Create panel. It asks: "Click to place the elevation marker".

### Press it

- Tab: View
- Panel: Create
- Kind: tool
- Ribbon: Views > Create

Worked example: press **Elevation** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Elevation · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Elevation' on View's Create panel: the tool 'Elevation' stands | keys: Escape (tool Elevation -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Direction | choice | Nearest Wall | Nearest Wall, North, East, South, West | all |

Played in these jobs:

- [4046. Put a section line and an elevation marker on the Ground plan of my 8 by 6 m house.](../examples/views-sheets-and-schedules.md)

### Elevation › Elevation

- Tab: View
- Panel: Create
- Kind: tool
- Ribbon: Views > Create > Elevation

Worked example: press **Elevation** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Elevation › Elevation · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Elevation › Elevation' on View's Create panel (through its parent 'Elevation''s arrow, the row 'Elevation'; the press stood 907 ms (the menu stood at 401 ms; its row ran 503 ms; it made 0 child widgets native)): the tool 'Elevation › Elevation' stands | keys: Escape (tool Elevation › Elevation -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Enlargement

A UNION command on the View tab, Create panel. Also known as Callout. It asks: "Click to draw the enlargement, or sketch it".

### Callout

- Tab: View
- Panel: Create
- Kind: tool
- Ribbon: Views > Create
- Works in views: drafting, plan, section_or_elevation, sheet_or_schedule
- Draw modes: Rectangle, Sketch

Worked example: press **Enlargement** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Callout · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Callout' on View's Create panel: the tool 'Callout' stands | keys: Escape (tool Callout -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Refer to | choice |  |  | all |
| Type | choice | Enlargement | Enlargement, Detail, Wall Section, View Reference | all |

## Extent Box

A UNION command on the View tab, Create panel. Also known as Scope Box. It asks: "Click two corners of the extent box".

### Scope Box

- Tab: View
- Panel: Create
- Kind: tool
- Ribbon: Setout > Datum
- Draw modes: Rectangle

Worked example: press **Extent Box** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Setout:Scope Box · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Scope Box' on Setout's Datum panel: the tool 'Scope Box' stands | keys: Escape (tool Scope Box -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Height | length | 3000 |  | all |
| Name | text |  |  | all |

## Filters

A UNION command on the View tab, Graphics panel.

### Press it

- Tab: View
- Panel: Graphics
- Kind: action
- Ribbon: Views > Graphics

Worked example: press **Filters** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Filters · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Filters' on View's Graphics panel (through its fold) (the window's first paint at 432 ms in union_shell::ShellDialogWindow, dialog 'Filters'): the dialog 'Filters' opened and stood; closed by the player | inside the modal 'Filters' | keys: Escape (no tool, dialog 'Filters' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Hidden Lines Off

A UNION command on the View tab, Graphics panel. Also known as Remove Hidden Lines. It asks: "Click an element to hide the hidden lines".

### Hidden Lines › Hidden Lines Off

- Tab: View
- Panel: Graphics
- Kind: tool
- Ribbon: Views > Graphics > Hidden Lines

Worked example: press **Hidden Lines Off** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Hidden Lines › Hidden Lines Off · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Hidden Lines › Hidden Lines Off' on View's Graphics panel (through its fold) (through its parent 'Hidden Lines''s arrow, the row 'Hidden Lines Off'; the press stood 468 ms (the menu stood at 16 ms; its row ran 451 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Select an element first to remove its hidden lines

## Hidden Lines On

A UNION command on the View tab, Graphics panel. Also known as Show Hidden Lines. It asks: "Click an element to show the hidden lines".

### Hidden Lines

- Tab: View
- Panel: Graphics
- Kind: tool
- Ribbon: Views > Graphics

Worked example: press **Hidden Lines On** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Hidden Lines · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Hidden Lines' on View's Graphics panel (through its fold): it refused in words: cannot proceed: Select an element first to show its hidden lines

## Layout Grid

A UNION command on the View tab, Sheet Composition panel. Also known as Guide Grid. It asks: "Click anywhere to place the layout grid".

### Guide Grid

- Tab: View
- Panel: Sheet Composition
- Kind: tool
- Ribbon: Views > Sheet Composition

Worked example: press **Layout Grid** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Guide Grid · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Guide Grid' on View's Sheet Composition panel (through its fold): it refused in words: cannot proceed: no sheet is open

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Spacing | length | 50 |  | all |

## Legends

A UNION command on the View tab, Create panel.

### Press it

- Tab: View
- Panel: Create
- Kind: action
- Ribbon: Views > Legends

Worked example: press **Legends** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Legends · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Legends' on View's Legend Views panel (through its fold) (the window's first paint at 85 ms in union_shell::ShellDialogWindow, dialog 'New Legend View'): the dialog 'New Legend View' opened and stood; closed by the player | inside the modal 'New Legend View' | keys: Escape (no tool, dialog 'New Legend View' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Matchline

A UNION command on the View tab, Sheet Composition panel. It asks: "Click the start and end of the matchline".

### Press it

- Tab: View
- Panel: Sheet Composition
- Kind: tool
- Ribbon: Views > Sheet Composition
- Draw modes: Line

Worked example: press **Matchline** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Matchline · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Matchline' on View's Sheet Composition panel (through its fold): the tool 'Matchline' stands | keys: Escape (tool Matchline -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Model View

A UNION command on the View tab, Create panel. Also known as 3D View.

### 3D View

- Tab: View
- Panel: Create
- Kind: action
- Ribbon: Views > Create

Worked example: press **Model View** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:3D View · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed '3D View' on View's Create panel: the command '3D View' ran; status 'Opened the 3D view {3D}' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [4030. Show my 6 by 4 m shed in the 3D view as a realistic picture without edge lines.](../examples/views-sheets-and-schedules.md)

## Placed View

A UNION command on the View tab, Sheet Composition panel. Also known as Viewport. It asks: "Click on the sheet to place the view".

### View/Viewport

- Tab: View
- Panel: Sheet Composition
- Kind: tool
- Ribbon: Views > Sheet Composition

Worked example: press **Placed View** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Viewport · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Viewport' on View's Sheet Composition panel (through its fold) (the window's first paint at 80 ms in union_shell::ShellDialogWindow, dialog 'Place View'): the dialog 'Views' opened and stood; closed by the player | inside the modal 'Views' | keys: Escape (no tool, dialog 'Views' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [4047. Start a 1:10 drafting view called Gutter Detail, open a sheet for it and place it.](../examples/views-sheets-and-schedules.md)

## Plans

A UNION command on the View tab, Create panel. Also known as Plan Views.

### Plan Views

- Tab: View
- Panel: Create
- Kind: action
- Ribbon: Views > Create

Worked example: press **Plans** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Plan Views · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Plan Views' on View's Create panel (the window's first paint at 114 ms in union_shell::ShellDialogWindow, dialog 'New Plan'): the dialog 'New Plan' opened and stood; closed by the player | inside the modal 'New Plan' | keys: Escape (no tool, dialog 'New Plan' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Levels | text |  |  | all |

## Revisions

A UNION command on the View tab, Sheet Composition panel.

### Press it

- Tab: View
- Panel: Sheet Composition
- Kind: dialog
- Ribbon: Detailing > Detail

Worked example: press **Revisions** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Revisions · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Revisions' on Annotate's Detail panel (through its fold) (the window's first paint at 78 ms in union_shell::ShellDialogWindow, dialog 'Revisions'): the dialog 'Revisions' opened and stood; closed by the player | inside the modal 'Revisions' | keys: Escape (no tool, dialog 'Revisions' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Schedules

A UNION command on the View tab, Create panel.

### Press it

- Tab: View
- Panel: Create
- Kind: tool
- Ribbon: Views > Schedules

Worked example: press **Schedules** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Schedules · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Schedules' on View's Schedule Views panel (through its fold) (the window's first paint at 106 ms in QDialog#SchedulesWindow): the command 'Schedules' ran | keys: Escape (no tool, dialog 'Schedules' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Section

A UNION command on the View tab, Create panel. It asks: "Click the section head".

### Press it

- Tab: View
- Panel: Create
- Kind: tool
- Ribbon: Views > Create
- Draw modes: Line

Worked example: press **Section** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Section · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Section' on View's Create panel: the tool 'Section' stands | keys: Escape (tool Section -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Refer to | choice |  |  | all |
| Type | choice |  |  | all |
| View Depth | length | 0 |  | all |

Played in these jobs:

- [4046. Put a section line and an elevation marker on the Ground plan of my 8 by 6 m house.](../examples/views-sheets-and-schedules.md)

## Switch

A UNION command on the View tab, Windows panel. Also known as Switch Windows.

### Press it

- Tab: View
- Panel: Windows
- Kind: action
- Ribbon: Views > Windows

Worked example: press **Switch** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Switch · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Switch' on View's Windows panel (through its fold): the command 'Switch' ran; status 'Open views: Ground (active), {3D} -- click a view's tab to switch to it' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Tabs

A UNION command on the View tab, Windows panel. Also known as Tab Views.

### Tab Views

- Tab: View
- Panel: Windows
- Kind: action
- Ribbon: Views > Windows

Worked example: press **Tabs** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Tab Views · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Tab Views' on View's Windows panel (through its fold): the command 'Tab Views' ran; status 'Tab Views: 2 open views stand as tabs -- Ground, {3D}' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Thin Lines

A UNION command on the View tab, Graphics panel.

### Press it

- Tab: View
- Panel: Graphics
- Kind: tool
- Ribbon: Views > Graphics

Worked example: press **Thin Lines** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Thin Lines · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Thin Lines' on View's Graphics panel (through its fold): the command 'Thin Lines' ran; status 'Thin lines on' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Tile

A UNION command on the View tab, Windows panel. Also known as Tile Views.

### Tile Views

- Tab: View
- Panel: Windows
- Kind: action
- Ribbon: Views > Windows

Worked example: press **Tile** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Tile Views · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Tile Views' on View's Windows panel (through its fold): the command 'Tile Views' ran; status 'Tile Views: only Ground is open -- open another view to tile it' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## View Presets

A UNION command on the View tab, Graphics panel. Also known as View Templates.

### View Templates

- Tab: View
- Panel: Graphics
- Kind: tool
- Ribbon: Views > Graphics

Worked example: press **View Presets** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:View Templates · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'View Templates' on View's Graphics panel (through its fold) (the window's first paint at 166 ms in union_shell::ShellDialogWindow, dialog 'View Presets'): the dialog 'View Templates' opened and stood; closed by the player | inside the modal 'View Templates' | keys: Escape (no tool, dialog 'View Templates' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Visibility

A UNION command on the View tab, Graphics panel. Also known as Visibility/Graphics.

### Visibility/Graphics

- Tab: View
- Panel: Graphics
- Kind: action
- Ribbon: Views > Graphics

Worked example: press **Visibility** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Visibility/Graphics · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Visibility/Graphics' on View's Graphics panel (through its fold) (the window's first paint at 23 ms in QDialog#VisibilityGraphicsDialog): the dialog 'Visibility/Graphic Overrides for Floor Plan: Ground' opened and stood; closed by the player | inside the modal 'Visibility/Graphic Overrides for Floor Plan: Ground' | keys: Escape (no tool, dialog 'Visibility/Graphic Overrides for Floor Plan: Ground' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Walkthrough

A UNION command on the View tab, Create panel. It asks: "Click to place a key frame, Enter to finish".

### 3D View › Walkthrough

- Tab: View
- Panel: Create
- Kind: tool
- Ribbon: Views > Create > 3D View

Worked example: press **Walkthrough** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:3D View › Walkthrough · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed '3D View › Walkthrough' on View's Create panel (through its parent '3D View''s arrow, the row 'Walkthrough'; the press stood 891 ms (the menu stood at 435 ms; its row ran 455 ms; it made 0 child widgets native)): the tool '3D View › Walkthrough' stands | keys: Escape (tool 3D View › Walkthrough -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

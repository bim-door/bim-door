# UNION commands: Views

59 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## 3D View › Default 3D View

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > 3D View

Worked example: press **3D View › Default 3D View** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:3D View › Default 3D View · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed '3D View › Default 3D View' on View's Create panel (through its parent '3D View''s arrow, the row 'Default 3D View'; the press stood 871 ms (the menu stood at 400 ms; its row ran 469 ms; it made 0 child widgets native)): the command '3D View › Default 3D View' ran; status 'Opened the 3D view {3D}' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Area Schedule

A UNION command on the Views tab, Schedules panel.

### views-areas-schedule

- Tab: Views
- Panel: Schedules
- Ribbon: Views > Schedules

Worked example: press **Area Schedule** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:views-areas-schedule · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'views-areas-schedule' on View's Schedule Views panel (through its fold) (the window's first paint at 64 ms in QDialog#SchedulesWindow): the command 'views-areas-schedule' ran; status 'Areas made' | keys: Escape (no tool, dialog 'Schedules' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Automatic Sections Settings

A UNION command on the Views tab, Create panel.

### views-autosections-dialog

- Tab: Views
- Panel: Create
- Ribbon: Views > Create

Worked example: press **Automatic Sections Settings** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:views-autosections-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'views-autosections-dialog' on View's Create panel (the window's first paint at 49 ms in union_shell::ShellDialogWindow, dialog 'views-autosections'): the dialog 'Automatic Sections Settings' opened and stood; closed by the player | inside the modal 'Automatic Sections Settings' | keys: Escape (no tool, dialog 'Automatic Sections Settings' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [4044. Make the sections and elevations for every grid line of my 8 by 6 m building in one go.](../examples/views-sheets-and-schedules.md)

## Callout › Rectangle

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Callout

Worked example: press **Callout › Rectangle** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Callout › Rectangle · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Callout › Rectangle' on View's Create panel (through its parent 'Callout''s arrow, the row 'Rectangle'; the press stood 748 ms (the menu stood at 354 ms; its row ran 391 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Callout › Rectangle works in a plan, section or elevation view

Played in these jobs:

- [4045. Draw an enlargement callout around the entrance of my 8 by 6 m house.](../examples/views-sheets-and-schedules.md)

## Callout › Sketch

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Callout

Worked example: press **Callout › Sketch** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Callout › Sketch · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Callout › Sketch' on View's Create panel (through its parent 'Callout''s arrow, the row 'Sketch'; the press stood 430 ms (the menu stood at 16 ms; its row ran 412 ms; it made 0 child widgets native)): it refused in words: cannot proceed: Callout › Sketch works in a plan, section or elevation view

## Close Inactive Views

A UNION command on the Views tab, Windows panel.

### Press it

- Tab: Views
- Panel: Windows
- Ribbon: Views > Windows

Worked example: press **Close Inactive Views** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Close Inactive Views · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Close Inactive Views' on View's Windows panel (through its fold): the command 'Close Inactive Views' ran; status 'Closed 1 inactive view(s)' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Colour Fill › Colour Key

A UNION command on the Views tab, Graphics panel.

### Press it

- Tab: Views
- Panel: Graphics
- Ribbon: Views > Graphics > Colour Fill

Worked example: press **Colour Fill › Colour Key** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Colour Fill › Colour Key · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Colour Fill › Colour Key' on View's Graphics panel (through its fold) (through its parent 'views-colourfill''s arrow, the row 'Colour Key'; the press stood 45 ms (the menu stood at 21 ms; its row ran 6 ms; it made 0 child widgets native)): it refused in words: cannot proceed: colour fill is set on a plan view; the view shown is @3d

## Display Options

A UNION command on the Views tab, Graphics panel.

### Press it

- Tab: Views
- Panel: Graphics
- Ribbon: Views > Graphics

Worked example: press **Display Options** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Display Options · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Display Options' on View's Graphics panel (through its fold) (the window's first paint at 147 ms in union_shell::ShellDialogWindow, dialog 'Display Options'): the dialog 'Display Options' opened and stood; closed by the player | inside the modal 'Display Options' | keys: Escape (no tool, dialog 'Display Options' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [4030. Show my 6 by 4 m shed in the 3D view as a realistic picture without edge lines.](../examples/views-sheets-and-schedules.md)

## Duplicate View › Duplicate

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Duplicate View

Worked example: press **Duplicate View › Duplicate** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Duplicate View › Duplicate · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Duplicate View › Duplicate' on View's Create panel (through its parent 'Duplicate View''s arrow, the row 'Duplicate'; the press stood 854 ms (the menu stood at 393 ms; its row ran 460 ms; it made 0 child widgets native)): the command 'Duplicate View › Duplicate' ran; status 'Ground Copy 1 Copy 1 made' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [4029. Duplicate the Ground plan for the structural engineer and hide the furniture and dimensions on the copy.](../examples/views-sheets-and-schedules.md)
- [4082. Duplicate the Ground plan and put the copy on a sheet for the electrician.](../examples/views-sheets-and-schedules.md)

## Duplicate View › Duplicate as Dependent

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Duplicate View

Worked example: press **Duplicate View › Duplicate as Dependent** with the view **Ground Copy 1 Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Duplicate View › Duplicate as Dependent · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Duplicate View › Duplicate as Dependent' on View's Create panel (through its parent 'Duplicate View''s arrow, the row 'Duplicate as Dependent'; the press stood 538 ms (the menu stood at 17 ms; its row ran 518 ms; it made 0 child widgets native)): the command 'Duplicate View › Duplicate as Dependent' ran; status 'Ground Copy 1 Copy 1 (dependent) made' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Duplicate View › Duplicate with Detailing

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Duplicate View

Worked example: press **Duplicate View › Duplicate with Detailing** with the view **Ground Copy 1 Copy 1 (dependent)** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Duplicate View › Duplicate with Detailing · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Duplicate View › Duplicate with Detailing' on View's Create panel (through its parent 'Duplicate View''s arrow, the row 'Duplicate with Detailing'; the press stood 639 ms (the menu stood at 20 ms; its row ran 617 ms; it made 0 child widgets native)): the command 'Duplicate View › Duplicate with Detailing' ran; status 'Ground Copy 1 Copy 1 (dependent) Copy 1 made' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Elevation › Framing Elevation

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Elevation

Worked example: press **Elevation › Framing Elevation** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Elevation › Framing Elevation · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Elevation › Framing Elevation' on View's Create panel (through its parent 'Elevation''s arrow, the row 'Framing Elevation'; the press stood 591 ms (the menu stood at 26 ms; its row ran 563 ms; it made 0 child widgets native)): the tool 'Elevation › Framing Elevation' stands | keys: Escape (tool Elevation › Framing Elevation -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Entourage

A UNION command on the Views tab, Render panel. Also known as render-entourage. It asks: "Click a point to place the entourage".

### Render › Entourage

- Tab: Views
- Panel: Render
- Kind: tool
- Ribbon: Views > Render > Render

Worked example: press **Entourage** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Entourage · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render › Entourage' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Entourage'; the press stood 220 ms (the menu stood at 24 ms; its row ran 172 ms; it made 0 child widgets native)): the tool 'render-entourage' stands | keys: Escape (tool render-entourage -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Kind | choice | Person | Person, Tree, Car | all |
| Next Seed | yesno | true |  | all |
| Rotation | angle | 0 |  | all |
| Seed | number | 1 |  | all |
| Variant | choice |  | , adult, child, cyclist, columnar, spreading, conifer, hatch, saloon | all |

## Legends › Keynote Legend

A UNION command on the Views tab, Legends panel.

### Press it

- Tab: Views
- Panel: Legends
- Ribbon: Views > Legends > Legends

Worked example: press **Legends › Keynote Legend** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Legends › Keynote Legend · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Legends › Keynote Legend' on View's Legend Views panel (through its fold) (through its parent 'Legends''s arrow, the row 'Keynote Legend'; the press stood 78 ms (the menu stood at 24 ms; its row ran 54 ms; the window's first paint at 54 ms in union_shell::ShellDialogWindow, dialog 'New Keynote Legend'; the dialog stood 712 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Keynote Legend' opened and stood; closed by the player | inside the modal 'New Keynote Legend' | keys: Escape (no tool, dialog 'New Keynote Legend' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Legends › Legend

A UNION command on the Views tab, Legends panel.

### Press it

- Tab: Views
- Panel: Legends
- Ribbon: Views > Legends > Legends

Worked example: press **Legends › Legend** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Legends › Legend · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Legends › Legend' on View's Legend Views panel (through its fold) (through its parent 'Legends''s arrow, the row 'Legend'; the press stood 246 ms (the menu stood at 12 ms; its row ran 234 ms; the window's first paint at 234 ms in union_shell::ShellDialogWindow, dialog 'New Legend View'; the dialog stood 981 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Legend View' opened and stood; closed by the player | inside the modal 'New Legend View' | keys: Escape (no tool, dialog 'New Legend View' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Plan Views › Area Plan

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Plan Views

Worked example: press **Plan Views › Area Plan** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Plan Views › Area Plan · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Plan Views › Area Plan' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Area Plan'; the press stood 880 ms (the menu stood at 633 ms; its row ran 247 ms; the window's first paint at 247 ms in union_shell::ShellDialogWindow, dialog 'Area Plans'; the dialog stood 1197 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Area Plans' opened and stood; closed by the player | inside the modal 'Area Plans' | keys: Escape (no tool, dialog 'Area Plans' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Plan Views › Floor Plan

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Plan Views

Worked example: press **Plan Views › Floor Plan** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Plan Views › Floor Plan · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Plan Views › Floor Plan' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Floor Plan'; the press stood 234 ms (the menu stood at 29 ms; its row ran 205 ms; the window's first paint at 205 ms in union_shell::ShellDialogWindow, dialog 'New Plan'; the dialog stood 1165 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Plan' opened and stood; closed by the player | inside the modal 'New Plan' | keys: Escape (no tool, dialog 'New Plan' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [2020. Roof the 8 x 5 m cottage with a gable roof: slope the long sides, leave the gable ends upright, 400 overhang, sitting on the wall tops.](../examples/architecture.md)
- [2021. Give the 6 x 4 m studio a single-pitch roof that falls to the south wall, drawn on an eaves plan.](../examples/architecture.md)
- [2022. Sketch the roof of the 9 x 6 m machinery shed from its outline on an eaves plan and finish it.](../examples/architecture.md)
- [2023. Roof the 8 x 5 m community room flat with an extensive green roof, 300 overhang, and run a fascia round all four edges.](../examples/architecture.md)
- [2024. Roof the 10 x 6 m house with a 30 degree hip roof and put a fascia and a gutter on its south eave.](../examples/architecture.md)
- [2060. Roof the 12 x 6 m workshop with a gable roof and hang a gutter on each long eave.](../examples/architecture.md)

## Plan Views › Plan Region

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Plan Views

Worked example: press **Plan Views › Plan Region** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Plan Views › Plan Region · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Plan Views › Plan Region' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Plan Region'; the press stood 557 ms (the menu stood at 27 ms; its row ran 528 ms; it made 0 child widgets native)): the tool 'Plan Views › Plan Region' stands | keys: Escape (tool Plan Views › Plan Region -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Plan Views › Reflected Ceiling Plan

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Plan Views

Worked example: press **Plan Views › Reflected Ceiling Plan** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Plan Views › Reflected Ceiling Plan · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Plan Views › Reflected Ceiling Plan' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Reflected Ceiling Plan'; the press stood 130 ms (the menu stood at 24 ms; its row ran 106 ms; the window's first paint at 106 ms in union_shell::ShellDialogWindow, dialog 'New Plan'; the dialog stood 1194 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Plan' opened and stood; closed by the player | inside the modal 'New Plan' | keys: Escape (no tool, dialog 'New Plan' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Plan Views › Structural Plan

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create > Plan Views

Worked example: press **Plan Views › Structural Plan** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Plan Views › Structural Plan · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Plan Views › Structural Plan' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Structural Plan'; the press stood 113 ms (the menu stood at 35 ms; its row ran 78 ms; the window's first paint at 78 ms in union_shell::ShellDialogWindow, dialog 'New Plan'; the dialog stood 1147 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Plan' opened and stood; closed by the player | inside the modal 'New Plan' | keys: Escape (no tool, dialog 'New Plan' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Refresh renders

A UNION command on the Views tab, Sheet Composition panel.

### sheets-render-refresh

- Tab: Views
- Panel: Sheet Composition
- Ribbon: Views > Sheet Composition

Worked example: press **Refresh renders** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:sheets-render-refresh · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'sheets-render-refresh' on View's Sheet Composition panel (through its fold): the command 'sheets-render-refresh' ran; status 'Nothing to refresh' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Render

A UNION command on the Views tab, Render panel.

### Press it

- Tab: Views
- Panel: Render
- Ribbon: Views > Render

Worked example: press **Render** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render' on View's Render panel (through its fold): the command 'render-view' ran; status 'Render: the document carries no 3D scene (no mesh rows to draw)' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Render › Entourage Settings

A UNION command on the Views tab, Render panel.

### Press it

- Tab: Views
- Panel: Render
- Ribbon: Views > Render > Render

Worked example: press **Render › Entourage Settings** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Entourage Settings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render › Entourage Settings' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Entourage Settings'; the press stood 174 ms (the menu stood at 33 ms; its row ran 141 ms; the window's first paint at 141 ms in union_shell::ShellDialogWindow, dialog 'Entourage'; the dialog stood 712 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Entourage' opened and stood; closed by the player | inside the modal 'Entourage' | keys: Escape (no tool, dialog 'Entourage' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Render › Night Lighting

A UNION command on the Views tab, Render panel.

### Press it

- Tab: Views
- Panel: Render
- Ribbon: Views > Render > Render

Worked example: press **Render › Night Lighting** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Night Lighting · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render › Night Lighting' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Night Lighting'; the press stood 68 ms (the menu stood at 10 ms; its row ran 58 ms; the window's first paint at 58 ms in union_shell::ShellDialogWindow, dialog 'Night Lighting'; the dialog stood 866 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Night Lighting' opened and stood; closed by the player | inside the modal 'Night Lighting' | keys: Escape (no tool, dialog 'Night Lighting' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Render › Render Textures

A UNION command on the Views tab, Render panel.

### Press it

- Tab: Views
- Panel: Render
- Ribbon: Views > Render > Render

Worked example: press **Render › Render Textures** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Render Textures · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render › Render Textures' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Render Textures'; the press stood 125 ms (the menu stood at 25 ms; its row ran 100 ms; the window's first paint at 100 ms in union_shell::ShellDialogWindow, dialog 'Render Textures'; the dialog stood 708 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Render Textures' opened and stood; closed by the player | inside the modal 'Render Textures' | keys: Escape (no tool, dialog 'Render Textures' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Render › Sun Hours

A UNION command on the Views tab, Render panel.

### Press it

- Tab: Views
- Panel: Render
- Ribbon: Views > Render > Render

Worked example: press **Render › Sun Hours** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Sun Hours · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Render › Sun Hours' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Sun Hours'; the press stood 48 ms (the menu stood at 24 ms; its row ran 6 ms; it made 0 child widgets native)): it refused in words: cannot proceed: the document holds no windows to study

## Render › Sun Study

A UNION command on the Views tab, Render panel.

### Press it

- Tab: Views
- Panel: Render
- Ribbon: Views > Render > Render

Worked example: press **Render › Sun Study** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Sun Study · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render › Sun Study' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Sun Study'; the press stood 228 ms (the menu stood at 25 ms; its row ran 203 ms; the window's first paint at 203 ms in union_shell::ShellDialogWindow, dialog 'Sun Study'; the dialog stood 816 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Sun Study' opened and stood; closed by the player | inside the modal 'Sun Study' | keys: Escape (no tool, dialog 'Sun Study' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Render Lights

A UNION command on the Views tab, Render panel. Also known as render-lights.

### Render › Render Lights

- Tab: Views
- Panel: Render
- Kind: action
- Ribbon: Views > Render > Render

Worked example: press **Render Lights** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Render Lights · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render › Render Lights' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Render Lights'; the press stood 622 ms (the menu stood at 14 ms; its row ran 588 ms; it made 0 child widgets native)): the command 'render-lights' ran; status 'Render Lights: night on, exposure 1.20 -- no lights placed yet' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Exposure | number | 1.2 |  | all |
| Night | yesno | true |  | all |

## Render Queue

A UNION command on the Views tab, Render panel. Also known as render-queue.

### Render › Render Queue

- Tab: Views
- Panel: Render
- Kind: action
- Ribbon: Views > Render > Render

Worked example: press **Render Queue** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Render Queue · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render › Render Queue' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Render Queue'; the press stood 656 ms (the menu stood at 22 ms; its row ran 610 ms; it made 0 child widgets native)): the command 'render-queue' ran; status 'Render Queue 0' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Height | number | 1080 |  | all |
| Style | choice |  | Wireframe, Hidden Line, Shaded, Consistent Colors, Realistic, White Model, X-Ray, traced | all |
| Width | number | 1920 |  | all |

## Render Settings

A UNION command on the Views tab, Render panel.

### Press it

- Tab: Views
- Panel: Render
- Ribbon: Views > Render

Worked example: press **Render Settings** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render Settings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render Settings' on View's Render panel (through its fold): the command 'Render Settings' ran; status 'Render Settings shown' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## render-panorama

A UNION command on the Views tab, Render panel.

### Render › Render Panorama

- Tab: Views
- Panel: Render
- Kind: action
- Ribbon: Views > Render > Render

Worked example: press **render-panorama** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Render Panorama · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render › Render Panorama' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Render Panorama'; the press stood 157 ms (the menu stood at 16 ms; its row ran 141 ms; the window's first paint at 141 ms in union_shell::ShellDialogWindow, dialog 'Render Panorama'; the dialog stood 965 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Render Panorama' opened and stood; closed by the player | inside the modal 'Render Panorama' | keys: Escape (no tool, dialog 'Render Panorama' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Eye | choice | view | view, selection, point, box | all |
| Width | number | 4096 |  | all |

## render-print

A UNION command on the Views tab, Render panel.

### Render › Print Render

- Tab: Views
- Panel: Render
- Kind: action
- Ribbon: Views > Render > Render

Worked example: press **render-print** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Print Render · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Render › Print Render' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Print Render'; the press stood 34 ms (the menu stood at 16 ms; its row ran 5 ms; it made 0 child widgets native)): it refused in words: cannot proceed: the document has no saved meshes to render (--write-meshes stores them)

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| DPI | choice |  | 150, 300 | all |
| Orientation | choice |  | Landscape, Portrait | all |
| Paper | choice |  | A0, A1, A2, A3, A4, ANSI_B, ANSI_C, ANSI_D, ANSI_E, ARCH_C, ARCH_D, ARCH_E, ARCH_E1, Letter, Tabloid | all |
| Style | choice |  | Shaded, Hidden Line | all |

## render-sun

A UNION command on the Views tab, Render panel.

### Render › True Sun Shadows

- Tab: Views
- Panel: Render
- Kind: action
- Ribbon: Views > Render > Render

Worked example: press **render-sun** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › True Sun Shadows · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render › True Sun Shadows' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'True Sun Shadows'; the press stood 689 ms (the menu stood at 20 ms; its row ran 665 ms; it made 0 child widgets native)): the command 'render-sun' ran | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Date | text |  |  | all |
| Ground Shadows | yesno | true |  | all |
| Time | text |  |  | all |

## render-textures

A UNION command on the Views tab, Render panel.

### Render › Procedural Textures

- Tab: Views
- Panel: Render
- Kind: action
- Ribbon: Views > Render > Render

Worked example: press **render-textures** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Render › Procedural Textures · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Render › Procedural Textures' on View's Render panel (through its fold) (through its parent 'Render''s arrow, the row 'Procedural Textures'; the press stood 2333 ms (the menu stood at 24 ms; its row ran 2282 ms; it made 0 child widgets native)): the command 'render-textures' ran; status 'Procedural Textures: 6 ready at 1024 px for all textures (brick, concrete, timber, steel, glass, plaster)' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Size | choice | 1024 | 256, 512, 1024, 2048 | all |
| Texture | choice | all | all, brick, concrete, timber, steel, glass, plaster | all |

## Schedules › Graphical Column Schedule

A UNION command on the Views tab, Schedules panel.

### Press it

- Tab: Views
- Panel: Schedules
- Ribbon: Views > Schedules > Schedules

Worked example: press **Schedules › Graphical Column Schedule** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Schedules › Graphical Column Schedule · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Schedules › Graphical Column Schedule' on View's Schedule Views panel (through its fold) (through its parent 'Schedules''s arrow, the row 'Graphical Column Schedule'; the press stood 155 ms (the menu stood at 27 ms; its row ran 104 ms; the window's first paint at 43 ms in QDialog#SchedulesWindow; it made 0 child widgets native)): the command 'Schedules › Graphical Column Schedule' ran; status 'Graphical Column Schedule made' | keys: Escape (no tool, dialog 'Schedules' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Schedules › Graphical Wall Schedule

A UNION command on the Views tab, Schedules panel.

### Press it

- Tab: Views
- Panel: Schedules
- Ribbon: Views > Schedules > Schedules

Worked example: press **Schedules › Graphical Wall Schedule** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Schedules › Graphical Wall Schedule · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Schedules › Graphical Wall Schedule' on View's Schedule Views panel (through its fold) (through its parent 'Schedules''s arrow, the row 'Graphical Wall Schedule'; the press stood 89 ms (the menu stood at 28 ms; its row ran 39 ms; the window's first paint at 38 ms in QDialog#SchedulesWindow; it made 0 child widgets native)): the command 'Schedules › Graphical Wall Schedule' ran; status 'Graphical Wall Schedule made' | keys: Escape (no tool, dialog 'Schedules' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Schedules › Material Takeoff

A UNION command on the Views tab, Schedules panel.

### Press it

- Tab: Views
- Panel: Schedules
- Ribbon: Views > Schedules > Schedules

Worked example: press **Schedules › Material Takeoff** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Schedules › Material Takeoff · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Schedules › Material Takeoff' on View's Schedule Views panel (through its fold) (through its parent 'Schedules''s arrow, the row 'Material Takeoff'; the press stood 71 ms (the menu stood at 23 ms; its row ran 25 ms; the window's first paint at 27 ms in QDialog#SchedulesWindow; it made 0 child widgets native)): the command 'Schedules › Material Takeoff' ran | keys: Escape (no tool, dialog 'Schedules' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Schedules › Note Block

A UNION command on the Views tab, Schedules panel.

### Press it

- Tab: Views
- Panel: Schedules
- Ribbon: Views > Schedules > Schedules

Worked example: press **Schedules › Note Block** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Schedules › Note Block · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Schedules › Note Block' on View's Schedule Views panel (through its fold) (through its parent 'Schedules''s arrow, the row 'Note Block'; the press stood 115 ms (the menu stood at 45 ms; its row ran 41 ms; the window's first paint at 47 ms in QDialog#SchedulesWindow; it made 0 child widgets native)): the command 'Schedules › Note Block' ran; status 'Note Block made' | keys: Escape (no tool, dialog 'Schedules' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Schedules › Schedule/Quantities

A UNION command on the Views tab, Schedules panel.

### Press it

- Tab: Views
- Panel: Schedules
- Ribbon: Views > Schedules > Schedules

Worked example: press **Schedules › Schedule/Quantities** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Schedules › Schedule/Quantities · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Schedules › Schedule/Quantities' on View's Schedule Views panel (through its fold) (through its parent 'Schedules''s arrow, the row 'Schedule/Quantities'; the press stood 428 ms (the menu stood at 23 ms; its row ran 398 ms; the window's first paint at 11 ms in QDialog#SchedulesWindow; it made 0 child widgets native)): the command 'Schedules › Schedule/Quantities' ran | keys: Escape (no tool, dialog 'Schedules' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Schedules › Sheet List

A UNION command on the Views tab, Schedules panel.

### Press it

- Tab: Views
- Panel: Schedules
- Ribbon: Views > Schedules > Schedules

Worked example: press **Schedules › Sheet List** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Schedules › Sheet List · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Schedules › Sheet List' on View's Schedule Views panel (through its fold) (through its parent 'Schedules''s arrow, the row 'Sheet List'; the press stood 161 ms (the menu stood at 20 ms; its row ran 120 ms; the window's first paint at 208 ms in QDialog#SchedulesWindow; it made 0 child widgets native)): the command 'Schedules › Sheet List' ran; status 'Sheet List made' | keys: Escape (no tool, dialog 'Schedules' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [4034. Open three sheets for the issue and give me the sheet list schedule.](../examples/views-sheets-and-schedules.md)

## Schedules › Steel Take-off

A UNION command on the Views tab, Schedules panel.

### Press it

- Tab: Views
- Panel: Schedules
- Ribbon: Views > Schedules > Schedules

Worked example: press **Schedules › Steel Take-off** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Schedules › Steel Take-off · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Schedules › Steel Take-off' on View's Schedule Views panel (through its fold) (through its parent 'Schedules''s arrow, the row 'Steel Take-off'; the press stood 82 ms (the menu stood at 24 ms; its row ran 32 ms; the window's first paint at 44 ms in QDialog#SchedulesWindow; it made 0 child widgets native)): the command 'Schedules › Steel Take-off' ran; status 'Steel Take-off made' | keys: Escape (no tool, dialog 'Schedules' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Schedules › View List

A UNION command on the Views tab, Schedules panel.

### Press it

- Tab: Views
- Panel: Schedules
- Ribbon: Views > Schedules > Schedules

Worked example: press **Schedules › View List** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Schedules › View List · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Schedules › View List' on View's Schedule Views panel (through its fold) (through its parent 'Schedules''s arrow, the row 'View List'; the press stood 313 ms (the menu stood at 39 ms; its row ran 183 ms; the window's first paint at 113 ms in QDialog#SchedulesWindow; it made 0 child widgets native)): the command 'Schedules › View List' ran; status 'View List made' | keys: Escape (no tool, dialog 'Schedules' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Sheet Renders

A UNION command on the Views tab, Sheet Composition panel.

### sheets-render-settings

- Tab: Views
- Panel: Sheet Composition
- Ribbon: Views > Sheet Composition

Worked example: press **Sheet Renders** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:sheets-render-settings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'sheets-render-settings' on View's Sheet Composition panel (through its fold) (the window's first paint at 581 ms in union_shell::ShellDialogWindow, dialog 'Sheet Renders'): the dialog 'Sheet Renders' opened and stood; closed by the player | inside the modal 'Sheet Renders' | keys: Escape (no tool, dialog 'Sheet Renders' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## sheets-render

A UNION command on the Views tab, Drawings panel.

### Press it

- Tab: Views
- Panel: Drawings
- Kind: action
- Ribbon: Views > Sheet Composition

Worked example: press **sheets-render** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:sheets-render · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'sheets-render' on View's Sheet Composition panel (through its fold): it refused in words: cannot proceed: Open a sheet first

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Style | choice |  |  | all |
| View | choice |  |  | all |
| Width | length | 120 |  | all |

## Silhouette Edges

A UNION command on the Views tab, Graphics panel.

### views-silhouette-dialog

- Tab: Views
- Panel: Graphics
- Ribbon: Views > Graphics

Worked example: press **Silhouette Edges** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:views-silhouette-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'views-silhouette-dialog' on View's Graphics panel (through its fold) (through its parent 'Display Options''s arrow, the row 'Silhouette Edges'; the press stood 284 ms (the menu stood at 30 ms; its row ran 254 ms; the window's first paint at 254 ms in union_shell::ShellDialogWindow, dialog 'Silhouette Edges'; the dialog stood 1274 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Silhouette Edges' opened and stood; closed by the player | inside the modal 'Silhouette Edges' | keys: Escape (no tool, dialog 'Silhouette Edges' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## User Interface

A UNION command on the Views tab, Windows panel.

### Press it

- Tab: Views
- Panel: Windows
- Ribbon: Views > Windows

Worked example: press **User Interface** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:User Interface · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'User Interface' on View's Windows panel (through its fold): its menu opened (closed) | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## User Interface › Browser Organization

A UNION command on the Views tab, Windows panel.

### Press it

- Tab: Views
- Panel: Windows
- Ribbon: Views > Windows > User Interface

Worked example: press **User Interface › Browser Organization** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:User Interface › Browser Organization · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'User Interface › Browser Organization' on View's Windows panel (through its fold) (through its parent 'User Interface''s arrow, the row 'Browser Organization'; the press stood 149 ms (the menu stood at 13 ms; its row ran 136 ms; the window's first paint at 136 ms in union_shell::ShellDialogWindow, dialog 'Browser Organization Properties'; the dialog stood 860 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Browser Organization Properties' opened and stood; closed by the player | inside the modal 'Browser Organization Properties' | keys: Escape (no tool, dialog 'Browser Organization Properties' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## User Interface › Keyboard Shortcuts

A UNION command on the Views tab, Windows panel.

### Press it

- Tab: Views
- Panel: Windows
- Ribbon: Views > Windows > User Interface

Worked example: press **User Interface › Keyboard Shortcuts** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:User Interface › Keyboard Shortcuts · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'User Interface › Keyboard Shortcuts' on View's Windows panel (through its fold) (through its parent 'User Interface''s arrow, the row 'Keyboard Shortcuts'; the press stood 134 ms (the menu stood at 18 ms; its row ran 116 ms; the window's first paint at 116 ms in union_shell::ShellDialogWindow, dialog 'Shortcuts'; the dialog stood 730 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Shortcuts' opened and stood; closed by the player | inside the modal 'Shortcuts' | keys: Escape (no tool, dialog 'Shortcuts' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## User Interface › Project Browser

A UNION command on the Views tab, Windows panel.

### Press it

- Tab: Views
- Panel: Windows
- Ribbon: Views > Windows > User Interface

Worked example: press **User Interface › Project Browser** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:User Interface › Project Browser · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'User Interface › Project Browser' on View's Windows panel (through its fold) (through its parent 'User Interface''s arrow, the row 'Project Browser'; the press stood 38 ms (the menu stood at 22 ms; its row ran 4 ms; it made 0 child widgets native)): the command 'User Interface › Project Browser' ran; status 'Project Tree hidden' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## User Interface › System Browser

A UNION command on the Views tab, Windows panel.

### Press it

- Tab: Views
- Panel: Windows
- Ribbon: Views > Windows > User Interface

Worked example: press **User Interface › System Browser** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:User Interface › System Browser · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'User Interface › System Browser' on View's Windows panel (through its fold) (through its parent 'User Interface''s arrow, the row 'System Browser'; the press stood 66 ms (the menu stood at 20 ms; its row ran 29 ms; it made 0 child widgets native)): the command 'User Interface › System Browser' ran; status 'System Browser shown' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## View Filters

A UNION command on the Views tab, Display panel. Also known as view-filters.

### view-filters

- Tab: Views
- Panel: Display
- Kind: action
- Ribbon: Views > Graphics

Worked example: press **View Filters** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:view-filters · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'view-filters' on View's Graphics panel (through its fold): it refused in words: cannot proceed: nothing is selected

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Halftone | yesno | false |  | all |
| Line Colour | text |  |  | all |
| Line Pattern | text |  |  | all |
| Line Weight | number | 0 |  | all |
| Name | text |  |  | all |
| Operator | choice | equals | equals, does not equal, is greater than, is greater than or equal to, is less than, is less than or equal to, contains, does not contain, begins with, ends with, has a value, has no value | all |
| Parameter | text | Type |  | all |
| Value | text |  |  | all |
| Visible | yesno | true |  | all |

## View Templates › Manage View Templates

A UNION command on the Views tab, Graphics panel.

### Press it

- Tab: Views
- Panel: Graphics
- Ribbon: Views > Graphics > View Templates

Worked example: press **View Templates › Manage View Templates** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:View Templates › Manage View Templates · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'View Templates › Manage View Templates' on View's Graphics panel (through its fold) (through its parent 'View Templates''s arrow, the row 'Manage View Templates'; the press stood 234 ms (the menu stood at 13 ms; its row ran 221 ms; the window's first paint at 221 ms in union_shell::ShellDialogWindow, dialog 'View Presets'; the dialog stood 1005 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'View Templates' opened and stood; closed by the player | inside the modal 'View Templates' | keys: Escape (no tool, dialog 'View Templates' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## View Templates › Sync Templates

A UNION command on the Views tab, Graphics panel.

### View Templates › View Preset Sync

- Tab: Views
- Panel: Graphics
- Ribbon: Views > Graphics > View Templates

Worked example: press **View Templates › Sync Templates** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:View Templates › View Preset Sync · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'View Templates › View Preset Sync' on View's Graphics panel (through its fold) (through its parent 'View Templates''s arrow, the row 'Sync Templates'; the press stood 110 ms (the menu stood at 16 ms; its row ran 94 ms; the window's first paint at 94 ms in union_shell::ShellDialogWindow, dialog 'View Preset Sync'; the dialog stood 876 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'View Preset Sync' opened and stood; closed by the player | inside the modal 'View Preset Sync' | keys: Escape (no tool, dialog 'View Preset Sync' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## views-areas

A UNION command on the Views tab, New View panel.

### Press it

- Tab: Views
- Panel: New View
- Kind: action
- Ribbon: Views > Create

Worked example: press **views-areas** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:views-areas · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'views-areas' on View's Create panel (the window's first paint at 36 ms in QMessageBox): the dialog 'Area Plan' opened and stood; closed by the player | inside the modal 'Area Plan' | keys: Escape (no tool, dialog 'Area Plan' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Area Scheme | choice | Gross Building | Gross Building, Rentable | all |
| Level | level |  |  | all |

## views-autosections

A UNION command on the Views tab, New View panel.

### Press it

- Tab: Views
- Panel: New View
- Kind: action
- Ribbon: Views > Create

Worked example: press **views-autosections** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:views-autosections · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'views-autosections' on View's Create panel: the command 'views-autosections' ran; status 'Made 0 sections, 0 elevations and 0 sheets; 1 skipped' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Elevations | yesno | true |  | all |
| Grids | text | all |  | all |
| Plan | level |  |  | all |
| Sections | yesno | true |  | all |
| Sheets | yesno | true |  | all |

## views-colourfill

A UNION command on the Views tab, Display panel.

### Press it

- Tab: Views
- Panel: Display
- Kind: action
- Ribbon: Views > Graphics

Worked example: press **views-colourfill** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:views-colourfill · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'views-colourfill' on View's Graphics panel (through its fold): it refused in words: cannot proceed: colour fill is set on a plan view; the view shown is @3d

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Colour By | choice |  |  | all |
| Placement | choice |  | Top Left, Top Right, Bottom Left, Bottom Right | all |
| Ranges | text |  |  | all |
| Value | text |  |  | all |

## views-legend

A UNION command on the Views tab, New View panel.

### Press it

- Tab: Views
- Panel: New View
- Kind: action
- Ribbon: Views > Legends

Worked example: press **views-legend** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:views-legend · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'views-legend' on View's Legend Views panel (through its fold) (the window's first paint at 720 ms in union_shell::ShellDialogWindow, dialog 'views-legend'): the dialog 'Legends' opened and stood; closed by the player | inside the modal 'Legends' | keys: Escape (no tool, dialog 'Legends' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Line Styles | yesno | false |  | all |
| Name | text |  |  | all |

## view-templates

A UNION command on the Views tab, Display panel.

### View Templates › Template Chooser

- Tab: Views
- Panel: Display
- Kind: action
- Ribbon: Views > Graphics > View Templates

Worked example: press **view-templates** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:View Templates › Template Chooser · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'View Templates › Template Chooser' on View's Graphics panel (through its fold) (through its parent 'View Templates''s arrow, the row 'Template Chooser'; the press stood 184 ms (the menu stood at 15 ms; its row ran 169 ms; the window's first paint at 169 ms in union_shell::ShellDialogWindow, dialog 'View Presets'; the dialog stood 860 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'View Templates' opened and stood; closed by the player | inside the modal 'View Templates' | keys: Escape (no tool, dialog 'View Templates' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Action | choice | manage | create, apply, sync, detach, manage | all |
| Name | text |  |  | all |
| Views | choice | current | current, open, sheet | all |

## Zoom to Selection

A UNION command on the Views tab, Create panel.

### Press it

- Tab: Views
- Panel: Create
- Ribbon: Views > Create

Worked example: press **Zoom to Selection** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:Zoom to Selection · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Zoom to Selection' on View's Create panel: it refused in words: cannot proceed: nothing is selected

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

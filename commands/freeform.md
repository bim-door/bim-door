# UNION commands: Freeform

21 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## Building Pad

A UNION command on the Freeform tab, Site panel. Also known as draw-topo-pad. It asks: "Sketch the loop, then Finish".

### draw-topo-pad

- Tab: Freeform
- Panel: Site
- Kind: tool
- Ribbon: Freeform > Site
- Draw modes: Line, Rectangle, Circle, Pick Lines

Worked example: press **Building Pad** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:draw-topo-pad · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'draw-topo-pad' on Massing & Site's Site panel (through its fold): it refused in words: cannot proceed: the model has no Topography -- draw or import one first

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Level | level |  |  | all |
| Offset | length | 0 |  | all |

## CITYJSON

A UNION command on the Freeform tab, Site panel.

### Press it

- Tab: Freeform
- Panel: Site
- Kind: action
- Ribbon: Freeform > Site

Worked example: press **CITYJSON** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:CITYJSON · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'CITYJSON' on Massing & Site's Site panel (through its fold) (the window's first paint at 56 ms in union_shell::ShellDialogWindow, dialog 'Browse IFC'): the dialog 'Import CITYJSON' opened and stood; closed by the player | inside the modal 'Import CITYJSON' | keys: Escape (no tool, dialog 'Import CITYJSON' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Buildings | choice | Mass | Mass, Generic Models, Site, Skip | all |
| Furniture | choice | Entourage | Entourage, Site, Skip | all |
| LOD | choice | Highest | Highest, 0, 1, 2, 3 | all |
| Terrain | choice | Site | Site, Generic Models, Skip | all |
| Vegetation | choice | Planting | Planting, Site, Skip | all |

## Convert to Toposolid

A UNION command on the Freeform tab, Site panel.

### Press it

- Tab: Freeform
- Panel: Site
- Kind: action
- Ribbon: Freeform > Site

Worked example: press **Convert to Toposolid** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Convert to Toposolid · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Convert to Toposolid' on Massing & Site's Site panel (through its fold) (through its parent 'Toposolid''s arrow, the row 'Convert to Toposolid'; the press stood 162 ms (the menu stood at 39 ms; its row ran 102 ms; it made 0 child widgets native)): it refused in words: cannot proceed: the model holds no Topography to convert

## Curtain System

A UNION command on the Freeform tab, Model by Face panel. It asks: "Click a vertical mass face in the plan to place a curtain system on it".

### Press it

- Tab: Freeform
- Panel: Model by Face
- Kind: tool
- Ribbon: Freeform > Model by Face

Worked example: press **Curtain System** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Curtain System · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Curtain System' on Massing & Site's Model by Face panel: the command 'Curtain System' ran; status 'Click to start the wall' | keys: Escape (tool Wall -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Floor by Face

A UNION command on the Freeform tab, Model by Face panel. It asks: "Select a mass, then press Floor by Face: a floor goes on each level the mass cuts".

### Press it

- Tab: Freeform
- Panel: Model by Face
- Kind: tool
- Ribbon: Freeform > Model by Face

Worked example: press **Floor by Face** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Floor by Face · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Floor by Face' on Massing & Site's Model by Face panel: the tool 'Floor by Face' stands | keys: Escape (tool Floor by Face -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Form Panels

A UNION command on the Freeform tab, Form panel. Also known as form-panels. It asks: "Click the surface to divide it into panels".

### form-panels

- Tab: Freeform
- Panel: Form
- Kind: tool
- Ribbon: Freeform > Form

Worked example: press **Form Panels** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:form-panels · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'form-panels' on Massing & Site's Form panel: the command 'form-panels' ran; status 'Click the surface to divide it into panels' | keys: Escape (tool Form Panels -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Inset | length | 20 |  | all |
| Max Warp | length | 20 |  | all |
| Pattern | choice | rect | rect, diamond, hex | all |
| U | number | 12 |  | all |
| U Grid | yesno | true |  | all |
| V | number | 20 |  | all |
| V Grid | yesno | true |  | all |

Played in these jobs:

- [6052. Loft the shell through three section curves and divide it into hexagonal panels.](../examples/change-modify-and-freeform.md)

## Form Panels Settings

A UNION command on the Freeform tab, Form panel.

### form-panels-dialog

- Tab: Freeform
- Panel: Form
- Ribbon: Freeform > Form

Worked example: press **Form Panels Settings** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:form-panels-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'form-panels-dialog' on Massing & Site's Form panel (the window's first paint at 38 ms in union_shell::ShellDialogWindow, dialog 'Form Panels'): the dialog 'Form Panels' opened and stood; closed by the player | inside the modal 'Form Panels' | keys: Escape (no tool, dialog 'Form Panels' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## GEOJSON

A UNION command on the Freeform tab, Site panel.

### Press it

- Tab: Freeform
- Panel: Site
- Kind: action
- Ribbon: Freeform > Site

Worked example: press **GEOJSON** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:GEOJSON · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'GEOJSON' on Massing & Site's Site panel (through its fold) (the window's first paint at 78 ms in union_shell::ShellDialogWindow, dialog 'Browse IFC'): the dialog 'Import GEOJSON' opened and stood; closed by the player | inside the modal 'Import GEOJSON' | keys: Escape (no tool, dialog 'Import GEOJSON' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Default Height | length | 3000 |  | all |
| Needs Location | yesno | true |  | all |
| Origin | choice | project | project, first coordinate | all |
| Storey Height | length | 3000 |  | all |

## Graded Region

A UNION command on the Freeform tab, Site panel.

### draw-topo-graded

- Tab: Freeform
- Panel: Site
- Ribbon: Freeform > Site

Worked example: press **Graded Region** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:draw-topo-graded · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'draw-topo-graded' on Massing & Site's Site panel (through its fold): it refused in words: cannot proceed: select one Toposurface or Toposolid to grade

## Label Contours

A UNION command on the Freeform tab, Site panel. It asks: "Click two points across the contours".

### Press it

- Tab: Freeform
- Panel: Site
- Kind: tool
- Ribbon: Freeform > Site

Worked example: press **Label Contours** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Label Contours · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Label Contours' on Massing & Site's Site panel (through its fold): the tool 'Label Contours' stands | keys: Escape (tool Label Contours -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## LANDXML

A UNION command on the Freeform tab, Site panel.

### Press it

- Tab: Freeform
- Panel: Site
- Kind: action
- Ribbon: Freeform > Site

Worked example: press **LANDXML** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:LANDXML · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'LANDXML' on Massing & Site's Site panel (through its fold) (the window's first paint at 197 ms in union_shell::ShellDialogWindow, dialog 'LandXML Import'): the dialog 'LandXML Import' opened and stood; closed by the player | inside the modal 'LandXML Import' | keys: Escape (no tool, dialog 'LandXML Import' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Category | choice | Topography | Topography, Toposolid | all |
| Contour Interval | length | 500 |  | all |

## Property Line

A UNION command on the Freeform tab, Site panel. It asks: "Sketch the property line, then Finish".

### Press it

- Tab: Freeform
- Panel: Site
- Kind: tool
- Ribbon: Freeform > Site

Worked example: press **Property Line** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Property Line · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Property Line' on Massing & Site's Site panel (through its fold): it refused in words: cannot proceed: Property Line works in a plan view

## Property Line Distances

A UNION command on the Freeform tab, Site panel.

### Press it

- Tab: Freeform
- Panel: Site
- Kind: action
- Ribbon: Freeform > Site

Worked example: press **Property Line Distances** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Property Line Distances · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Property Line Distances' on Massing & Site's Site panel (through its fold) (through its parent 'Property Line''s arrow, the row 'Distances and Bearings'; the press stood 107 ms (the menu stood at 18 ms; its row ran 89 ms; the window's first paint at 89 ms in union_shell::ShellDialogWindow, dialog 'Property Line Distances'; the dialog stood 883 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Property Line Distances and Bearings' opened and stood; closed by the player | inside the modal 'Property Line Distances and Bearings' | keys: Escape (no tool, dialog 'Property Line Distances and Bearings' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Reference Point

A UNION command on the Freeform tab, Form panel. It asks: "Click to place a reference point".

### Press it

- Tab: Freeform
- Panel: Form
- Kind: tool
- Ribbon: Freeform > Form

Worked example: press **Reference Point** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Reference Point · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Reference Point' on Massing & Site's Form panel: the tool 'Reference Point' stands | keys: Escape (tool Reference Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset From Level | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |
| Show Reference Planes | yesno | false |  | all |

## Roof by Face

A UNION command on the Freeform tab, Model by Face panel. It asks: "Select a mass, then press Roof by Face, or click a mass top face: a roof goes on it".

### Press it

- Tab: Freeform
- Panel: Model by Face
- Kind: tool
- Ribbon: Freeform > Model by Face

Worked example: press **Roof by Face** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Roof by Face · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Roof by Face' on Massing & Site's Model by Face panel: the tool 'Roof by Face' stands | keys: Escape (tool Roof by Face -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Show Mass

A UNION command on the Freeform tab, Form panel.

### Press it

- Tab: Freeform
- Panel: Form
- Ribbon: Freeform > Form

Worked example: press **Show Mass** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Show Mass · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Show Mass' on Massing & Site's Form panel: the command 'Show Mass' ran; status 'masses hidden in Ground' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Sub-Divide

A UNION command on the Freeform tab, Site panel. It asks: "Sketch the region inside a Toposolid, then press Enter".

### Press it

- Tab: Freeform
- Panel: Site
- Kind: tool
- Ribbon: Freeform > Site

Worked example: press **Sub-Divide** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Sub-Divide · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Sub-Divide' on Massing & Site's Site panel (through its fold): the tool 'Sub-Divide' stands | keys: Escape (tool Sub-Divide -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Topography Settings

A UNION command on the Freeform tab, Site panel.

### draw-topo-settings

- Tab: Freeform
- Panel: Site
- Ribbon: Freeform > Site

Worked example: press **Topography Settings** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:draw-topo-settings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'draw-topo-settings' on Massing & Site's Site panel (through its fold) (the window's first paint at 67 ms in union_shell::ShellDialogWindow, dialog 'Topography Settings'): the dialog 'Topography Settings' opened and stood; closed by the player | inside the modal 'Topography Settings' | keys: Escape (no tool, dialog 'Topography Settings' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Toposolid

A UNION command on the Freeform tab, Site panel. It asks: "Sketch the boundary, close it, add points, then press Enter".

### Press it

- Tab: Freeform
- Panel: Site
- Kind: tool
- Ribbon: Freeform > Site

Worked example: press **Toposolid** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Toposolid · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Toposolid' on Massing & Site's Site panel (through its fold): the tool 'Toposolid' stands | keys: Escape (tool Toposolid -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Elevation | length | 0 |  | all |

## Toposurface

A UNION command on the Freeform tab, Site panel. Also known as draw-topo. It asks: "Click points to sketch the toposurface".

### draw-topo

- Tab: Freeform
- Panel: Site
- Kind: tool
- Ribbon: Freeform > Site

Worked example: press **Toposurface** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:draw-topo · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'draw-topo' on Massing & Site's Site panel (through its fold): the command 'draw-topo' ran; status 'Click points to sketch the toposurface' | keys: Escape (tool Toposurface -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Contour interval | length | 500 |  | all |
| Elevation | length | 0 |  | all |
| Major every | number | 5 |  | all |
| Points file | text |  |  | all |

## Wall by Face

A UNION command on the Freeform tab, Model by Face panel. It asks: "Click a vertical mass face in the plan to place a wall on it".

### Press it

- Tab: Freeform
- Panel: Model by Face
- Kind: tool
- Ribbon: Freeform > Model by Face

Worked example: press **Wall by Face** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Wall by Face · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall by Face' on Massing & Site's Model by Face panel: the command 'Wall by Face' ran; status 'Click to start the wall' | keys: Escape (tool Wall -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

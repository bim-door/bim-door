# UNION commands: Annotate

38 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## 2D Block

A UNION command on the Annotate tab, Detail panel. Also known as Component (detail). It asks: "Click to place the detail component".

### Component (detail)

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail

Worked example: press **2D Block** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Component · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Component' on Annotate's Detail panel (through its fold): the command 'Component (detail)' ran; status 'Click to place the detail component' | keys: Escape (tool 2D Block -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Block | text |  |  | all |
| Length | length | 1000 |  | all |
| Rotation | length | 0 |  | all |
| View | choice | End | End, Side | all |

## 2D Group

A UNION command on the Annotate tab, Detail panel. Also known as Detail Group. It asks: "Click to place the detail group".

### Detail Group

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail

Worked example: press **2D Group** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Group · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Detail Group' on Annotate's Detail panel (through its fold): the tool 'Detail Group' stands | keys: Escape (tool Detail Group -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## 2D Line

A UNION command on the Annotate tab, Detail panel. Also known as Detail Line.

### Detail Line

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail

Worked example: press **2D Line** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Detail Line · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands | keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [5009. Give me a 1:10 slab edge detail with a rebate for the brick, a drip groove, a rebate hatch and the slab depth noted.](../examples/annotation-details-and-materials.md)
- [5010. Detail a 1200 square pad footing at 1:20 with the column stub, bottom bars as dots and a cogged bar, and the pad dimensions.](../examples/annotation-details-and-materials.md)
- [5024. Draw a 100 mm pipe and a 50 mm riser in section at 1:5 and give each a diameter or radius dimension.](../examples/annotation-details-and-materials.md)
- [5040. Detail a 600 by 300 concrete beam section at 1:10: stirrup, three top and three bottom bars as circles, and the cover noted.](../examples/annotation-details-and-materials.md)
- [5047. Draw an externally lagged round duct section at 1:5: the duct wall, 50 mm lagging all round and a foil jacket.](../examples/annotation-details-and-materials.md)
- [5049. Sketch a hex nut in plan, a washer circle and a curved cable run in a drafting view to show our bolted joint symbol.](../examples/annotation-details-and-materials.md)
- [5064. Draw the pipe clip fixing a 50 mm pipe to a concrete soffit at 1:5, with the anchor and the clip spacing noted.](../examples/annotation-details-and-materials.md)
- [5067. Draw a 20 mm conduit and a socket box in a stud wall at 1:5 with the stud, the lining and the box depth.](../examples/annotation-details-and-materials.md)

## Aligned

A UNION command on the Annotate tab, Dimension panel. It asks: "Click a reference".

### Press it

- Tab: Annotate
- Panel: Dimension
- Kind: tool
- Ribbon: Detailing > Dimension

Worked example: press **Aligned** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Aligned · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Aligned' on Annotate's Dimension panel: it refused in words: cannot proceed: Aligned works in a plan, section or elevation view

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Intersecting Grids | yesno | false |  | Auto Dimension Options |
| Intersecting Walls | yesno | true |  | Auto Dimension Options |
| Openings | choice | Centers | Centers, Widths | Auto Dimension Options |
| Pick | choice | Individual References | Individual References, Entire Walls, Options... | all |
| Prefer | choice | Wall Centerlines | Wall Centerlines, Wall Faces | all |

Played in these jobs:

- [5013. Dimension the outside of our 6 by 4 m site office: both long walls and both short walls.](../examples/annotation-details-and-materials.md)

## Angular

A UNION command on the Annotate tab, Dimension panel. It asks: "Click a reference".

### Press it

- Tab: Annotate
- Panel: Dimension
- Kind: tool
- Ribbon: Detailing > Dimension

Worked example: press **Angular** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Angular · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Angular' on Annotate's Dimension panel: it refused in words: cannot proceed: Angular works in a plan, section or elevation view

## Any Tag

A UNION command on the Annotate tab, Tag panel. Also known as Multi-Category.

### Multi-Category

- Tab: Annotate
- Panel: Tag
- Kind: tool
- Ribbon: Detailing > Tag

Worked example: press **Any Tag** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Multi-Category · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Multi-Category' on Annotate's Tag panel (through its fold): it refused in words: cannot proceed: lock this 3D view (View Control Bar) before placing a Multi-Category in it

## Arc Length

A UNION command on the Annotate tab, Dimension panel. It asks: "Click an arc to dimension the length".

### Press it

- Tab: Annotate
- Panel: Dimension
- Kind: tool
- Ribbon: Detailing > Dimension

Worked example: press **Arc Length** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Arc Length · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Arc Length' on Annotate's Dimension panel: it refused in words: cannot proceed: Arc Length works in a plan, section or elevation view

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Snap to Wall Faces | yesno | true |  | all |

## Area Tag

A UNION command on the Annotate tab, Tag panel. It asks: "Click an area to tag it".

### Press it

- Tab: Annotate
- Panel: Tag
- Kind: tool
- Ribbon: Architectural > Room & Area

Worked example: press **Area Tag** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Area Tag · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Area Tag' on Architecture's Room & Area panel (through its fold): it refused in words: cannot proceed: Area Tag works in a plan, section or elevation view

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Leader | yesno | false |  | all |
| Orientation | choice | Horizontal | Horizontal, Vertical | all |

## Center Mark

A UNION command on the Annotate tab, Detail panel. It asks: "Click a circle or arc to show its center mark".

### Press it

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail

Worked example: press **Center Mark** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Center Mark · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Center Mark' on Annotate's Detail panel (through its fold): it refused in words: cannot proceed: Center Mark works in a plan, section or elevation view

## Centerline

A UNION command on the Annotate tab, Detail panel. It asks: "Click the first line, then the second: a centerline is drawn midway between them".

### Press it

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail

Worked example: press **Centerline** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Centerline · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Centerline' on Annotate's Detail panel (through its fold): it refused in words: cannot proceed: Centerline works in a plan, section or elevation view

## Chamfer

A UNION command on the Annotate tab, Detail panel. It asks: "Click the first line or arc".

### Press it

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail

Worked example: press **Chamfer** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Chamfer · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Chamfer' on Annotate's Detail panel (through its fold): it refused in words: cannot proceed: Chamfer works in a plan, section or elevation view

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Angle | angle | 0 |  | all |
| Distance 1 | length | 0 |  | all |
| Distance 2 | length | 0 |  | all |
| Length | length | 0 |  | all |
| Method | choice | distance | distance, angle | all |
| Polyline | yesno | false |  | all |
| Trim | yesno | true |  | all |

## Cloud

A UNION command on the Annotate tab, Detail panel. Also known as Revision Cloud. It asks: "Sketch the cloud boundary, then Finish".

### Annotate/Revision Cloud

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail
- Draw modes: Line, Rectangle

Worked example: press **Cloud** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Revision Cloud · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Revision Cloud' on Annotate's Detail panel (through its fold): it refused in words: cannot proceed: Revision Cloud works in a plan, section or elevation view

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Revision | choice |  |  | all |

## Datum Feature

A UNION command on the Annotate tab, Symbol panel. It asks: "Click the feature to place the datum symbol".

### Press it

- Tab: Annotate
- Panel: Symbol
- Kind: tool
- Ribbon: Detailing > Symbol

Worked example: press **Datum Feature** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Datum Feature · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Datum Feature' on Annotate's Symbol panel (through its fold): the tool 'Datum Feature' stands | keys: Escape (tool Datum Feature -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Datum | text | A |  | all |
| Rotation | angle | 0 |  | all |

## Diameter

A UNION command on the Annotate tab, Dimension panel. It asks: "Click an arc to dimension the diameter".

### Press it

- Tab: Annotate
- Panel: Dimension
- Kind: tool
- Ribbon: Detailing > Dimension

Worked example: press **Diameter** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Diameter · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Diameter' on Annotate's Dimension panel: the tool 'Diameter' stands | keys: Escape (tool Diameter -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [5024. Draw a 100 mm pipe and a 50 mm riser in section at 1:5 and give each a diameter or radius dimension.](../examples/annotation-details-and-materials.md)
- [5047. Draw an externally lagged round duct section at 1:5: the duct wall, 50 mm lagging all round and a foil jacket.](../examples/annotation-details-and-materials.md)
- [5064. Draw the pipe clip fixing a 50 mm pipe to a concrete soffit at 1:5, with the anchor and the clip spacing noted.](../examples/annotation-details-and-materials.md)

## Feature Control Frame

A UNION command on the Annotate tab, Symbol panel. It asks: "Click to place the feature control frame".

### Press it

- Tab: Annotate
- Panel: Symbol
- Kind: tool
- Ribbon: Detailing > Symbol

Worked example: press **Feature Control Frame** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Feature Control Frame · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Feature Control Frame' on Annotate's Symbol panel (through its fold): the tool 'Feature Control Frame' stands | keys: Escape (tool Feature Control Frame -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Characteristic | choice | Position | Straightness, Flatness, Circularity, Cylindricity, Profile of a Line, Profile of a Surface, Parallelism, Perpendicularity, Angularity, Position, Concentricity, Symmetry, Circular Run-out, Total Run-out | all |
| Datum 1 | text |  |  | all |
| Datum 2 | text |  |  | all |
| Datum 3 | text |  |  | all |
| Modifier | choice | None | None, M, L, P, F, T, U | all |
| Rotation | angle | 0 |  | all |
| Tolerance | text | 0.1 |  | all |
| Zone | choice | None | None, Diameter, Spherical Diameter | all |

## Fillet

A UNION command on the Annotate tab, Detail panel. It asks: "Click the first line or arc".

### Press it

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail

Worked example: press **Fillet** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Fillet · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Fillet' on Annotate's Detail panel (through its fold): the tool 'Fillet' stands | keys: Escape (tool Fillet -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Polyline | yesno | false |  | all |
| Radius | length | 0 |  | all |
| Trim | yesno | true |  | all |

## Find

A UNION command on the Annotate tab, Text panel. Also known as Find/Replace.

### Find/Replace

- Tab: Annotate
- Panel: Text
- Kind: tool
- Ribbon: Detailing > Text

Worked example: press **Find** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Find/Replace · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Find/Replace' on Annotate's Text panel (through its fold) (the window's first paint at 158 ms in union_shell::ShellDialogWindow, dialog 'Find/Replace'): the dialog 'Find/Replace' opened and stood; closed by the player | inside the modal 'Find/Replace' | keys: Escape (no tool, dialog 'Find/Replace' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Hatch

A UNION command on the Annotate tab, Detail panel. Also known as Region.

### Region

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail

Worked example: press **Hatch** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Region · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Region' on Annotate's Detail panel (through its fold): the tool 'Region' stands | keys: Escape (tool Region -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Insulation

A UNION command on the Annotate tab, Detail panel. It asks: "Click the start and end of the insulation".

### Press it

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail
- Draw modes: Line

Worked example: press **Insulation** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Insulation · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Insulation' on Annotate's Detail panel (through its fold): the tool 'Insulation' stands | keys: Escape (tool Insulation -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Bulge to Width Ratio (1/x) | number | 2 |  | all |
| Chain | yesno | true |  | all |
| Placement | choice | Centre | Centre, Near, Far | all |
| Width | length | 50 |  | all |

## Keynote

A UNION command on the Annotate tab, Tag panel. It asks: "Click an element to place the keynote".

### Press it

- Tab: Annotate
- Panel: Tag
- Kind: tool
- Ribbon: Detailing > Tag

Worked example: press **Keynote** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Keynote · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Keynote' on Annotate's Tag panel (through its fold): the tool 'Keynote' stands | keys: Escape (tool Keynote -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Display | choice | Text | Text, Key | all |
| Mode | choice | Element Keynote | Element Keynote, Material Keynote, User Keynote | all |

## Legend Component

A UNION command on the Annotate tab, Detail panel. It asks: "Click in the Legend view to place the component".

### Press it

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail

Worked example: press **Legend Component** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Legend Component · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Legend Component' on Annotate's Detail panel (through its fold) (through its parent 'Component''s arrow, the row 'Legend Component'; the press stood 107 ms (the menu stood at 10 ms; its row ran 84 ms; it made 0 child widgets native)): it refused in words: cannot proceed: a Legend Component is placed in a Legend view; open or make one

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Type | choice |  |  | all |
| View | choice | plan | plan | all |

## Linear

A UNION command on the Annotate tab, Dimension panel. It asks: "Click a reference".

### Press it

- Tab: Annotate
- Panel: Dimension
- Kind: tool
- Ribbon: Detailing > Dimension

Worked example: press **Linear** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Linear · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Linear' on Annotate's Dimension panel: the tool 'Linear' stands | keys: Escape (tool Linear -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Axis | choice |  | , Horizontal, Vertical | all |

Played in these jobs:

- [5025. Dimension the three outer legs of an L-shaped shed with linear dimensions.](../examples/annotation-details-and-materials.md)

## Material Tag

A UNION command on the Annotate tab, Tag panel. It asks: "Click an element to tag the material".

### Press it

- Tab: Annotate
- Panel: Tag
- Kind: tool
- Ribbon: Detailing > Tag

Worked example: press **Material Tag** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Material Tag · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Material Tag' on Annotate's Tag panel (through its fold): the tool 'Material Tag' stands | keys: Escape (tool Material Tag -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Leader | yesno | false |  | all |
| Text | choice | Name | Name, Description | all |
| Orientation | choice | Horizontal | Horizontal, Vertical | all |

Played in these jobs:

- [5019. Tag the material on the east and west walls of the store.](../examples/annotation-details-and-materials.md)

## Radial

A UNION command on the Annotate tab, Dimension panel. It asks: "Click an arc to dimension the radius".

### Press it

- Tab: Annotate
- Panel: Dimension
- Kind: tool
- Ribbon: Detailing > Dimension

Worked example: press **Radial** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Radial · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Radial' on Annotate's Dimension panel: it refused in words: cannot proceed: Radial works in a plan, section or elevation view

Played in these jobs:

- [5024. Draw a 100 mm pipe and a 50 mm riser in section at 1:5 and give each a diameter or radius dimension.](../examples/annotation-details-and-materials.md)

## Repeating Detail Component

A UNION command on the Annotate tab, Detail panel. It asks: "Click the start and end of the repeating detail".

### Press it

- Tab: Annotate
- Panel: Detail
- Kind: tool
- Ribbon: Detailing > Detail

Worked example: press **Repeating Detail Component** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Repeating Detail Component · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Repeating Detail Component' on Annotate's Detail panel (through its fold): the tool 'Repeating Detail Component' stands | keys: Escape (tool Repeating Detail Component -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Block | choice | bolt_shop | bar_callout, bar_cog, bar_hook, bar_lap, bar_mark, bar_stirrup, benchmark, bolt_shop, bolt_site, bracing_cross, bracing_single, break_line, break_line_cylindrical, break_line_zigzag, camber_mark, cantilever_mark, centre_line_mark, coordinate_target, datum_mark, level_target, moment_connection, reduced_level_mark, setout_point, shear_connection, slope_mark, span_mark, splice_mark, step_line, support_fixed, support_guided, support_hinge, support_pin, support_roller, support_spring, weld_all_round, weld_backing, weld_butt, weld_convex, weld_fillet, weld_flush, weld_plug, weld_reference, weld_seam, weld_site, weld_spot | all |
| Layout | choice | Fixed Distance | Fixed Distance, Fill Available Space, Maximum Spacing | all |
| Spacing | length | 500 |  | all |

## Save to Detail Library

A UNION command on the Annotate tab, Detail panel.

### Press it

- Tab: Annotate
- Panel: Detail
- Kind: dialog
- Ribbon: Detailing > Detail

Worked example: press **Save to Detail Library** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Save to Detail Library · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Save to Detail Library' on Annotate's Detail panel (through its fold): it refused in words: cannot proceed: nothing is selected to save to the detail library

## Span Direction

A UNION command on the Annotate tab, Symbol panel. It asks: "Click a floor to place its span direction".

### Press it

- Tab: Annotate
- Panel: Symbol
- Kind: tool
- Ribbon: Detailing > Symbol

Worked example: press **Span Direction** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Span Direction · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Span Direction' on Annotate's Symbol panel (through its fold): the tool 'Span Direction' stands | keys: Escape (tool Span Direction -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Spelling

A UNION command on the Annotate tab, Text panel.

### Press it

- Tab: Annotate
- Panel: Text
- Kind: tool
- Ribbon: Detailing > Text

Worked example: press **Spelling** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Spelling · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Spelling' on Annotate's Text panel (through its fold): the command 'Spelling' ran; status 'The spelling check is complete.' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Spot Coordinate

A UNION command on the Annotate tab, Dimension panel. It asks: "Click a point to place a spot coordinate".

### Press it

- Tab: Annotate
- Panel: Dimension
- Kind: tool
- Ribbon: Detailing > Dimension

Worked example: press **Spot Coordinate** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Spot Coordinate · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Spot Coordinate' on Annotate's Dimension panel: the tool 'Spot Coordinate' stands | keys: Escape (tool Spot Coordinate -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Leader | yesno | false |  | all |
| Rotate with host | yesno | false |  | all |
| Shoulder | yesno | true |  | all |

## Spot Fall

A UNION command on the Annotate tab, Dimension panel. Also known as Spot Slope. It asks: "Click the start of the edge".

### Spot Slope

- Tab: Annotate
- Panel: Dimension
- Kind: tool
- Ribbon: Detailing > Dimension

Worked example: press **Spot Fall** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Spot Slope · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Spot Slope' on Annotate's Dimension panel: the tool 'Spot Slope' stands | keys: Escape (tool Spot Slope -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset from Reference | length | 0 |  | all |
| Slope Representation | choice | Arrow | Arrow, Triangle | all |

## Spot Level

A UNION command on the Annotate tab, Dimension panel. Also known as Spot Elevation. It asks: "Click an element to place a spot elevation".

### Spot Elevation

- Tab: Annotate
- Panel: Dimension
- Kind: tool
- Ribbon: Detailing > Dimension

Worked example: press **Spot Level** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Spot Elevation · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Spot Elevation' on Annotate's Dimension panel: the tool 'Spot Elevation' stands | keys: Escape (tool Spot Elevation -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Display Elevations | choice | Actual Elevation | Actual Elevation, Top and Bottom | all |
| Leader | yesno | false |  | all |
| Relative Base | yesno | false |  | all |
| Rotate with host | yesno | false |  | all |
| Shoulder | yesno | true |  | all |

Played in these jobs:

- [5018. Mark spot elevations on the north and south walls of the plant room.](../examples/annotation-details-and-materials.md)

## Surface Texture

A UNION command on the Annotate tab, Symbol panel. It asks: "Click to place the surface texture symbol".

### Press it

- Tab: Annotate
- Panel: Symbol
- Kind: tool
- Ribbon: Detailing > Symbol

Worked example: press **Surface Texture** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Surface Texture · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Surface Texture' on Annotate's Symbol panel (through its fold): the tool 'Surface Texture' stands | keys: Escape (tool Surface Texture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Allowance | text |  |  | all |
| Lay | text |  |  | all |
| Method | text |  |  | all |
| Material Removal | choice | Any | Any, Required, Prohibited | all |
| Rotation | angle | 0 |  | all |
| Roughness | text | Ra 3.2 |  | all |

## Symbol

A UNION command on the Annotate tab, Symbol panel. It asks: "Click to place the symbol".

### Press it

- Tab: Annotate
- Panel: Symbol
- Kind: tool
- Ribbon: Detailing > Symbol

Worked example: press **Symbol** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Symbol · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Symbol' on Annotate's Symbol panel (through its fold): the tool 'Symbol' stands | keys: Escape (tool Symbol -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Rotation | length | 0 |  | all |
| Symbol | choice | North Arrow | North Arrow, Scale Bar | all |

Played in these jobs:

- [5017. Put a north arrow and a scale bar beside the building on the Ground plan.](../examples/annotation-details-and-materials.md)

## Table

A UNION command on the Annotate tab, Text panel. It asks: "Click the insertion point of the table".

### Press it

- Tab: Annotate
- Panel: Text
- Kind: tool
- Ribbon: Detailing > Text

Worked example: press **Table** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Table · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Table' on Annotate's Text panel (through its fold): the tool 'Table' stands | keys: Escape (tool Table -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Columns | number | 4 |  | all |
| Rows | number | 3 |  | all |

## Tag

A UNION command on the Annotate tab, Tag panel. Also known as Tag by Category.

### Tag by Category

- Tab: Annotate
- Panel: Tag
- Kind: tool
- Ribbon: Detailing > Tag

Worked example: press **Tag** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Tag by Category · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Tag by Category' on Annotate's Tag panel (through its fold): the tool 'Tag by Category' stands | keys: Escape (tool Tag by Category -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [5015. Put two doors in the site office and tag both of them.](../examples/annotation-details-and-materials.md)
- [5052. Tag the corner column and the first beam on the Level 1 structural plan.](../examples/annotation-details-and-materials.md)
- [5053. Run a supply duct with one air terminal on it and tag the duct.](../examples/annotation-details-and-materials.md)
- [5055. Run a 100 mm sewer pipe along the corridor wall and tag it.](../examples/annotation-details-and-materials.md)

## Tag All

A UNION command on the Annotate tab, Tag panel. It asks: "Click to tag every element in the view".

### Press it

- Tab: Annotate
- Panel: Tag
- Kind: tool
- Ribbon: Detailing > Tag

Worked example: press **Tag All** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Tag All · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Tag All' on Annotate's Tag panel (through its fold): the tool 'Tag All' stands | keys: Escape (tool Tag All -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Avoid Overlap | yesno | false |  | all |

## Text

A UNION command on the Annotate tab, Text panel. It asks: "Click to place the text".

### Press it

- Tab: Annotate
- Panel: Text
- Kind: tool
- Ribbon: Detailing > Text

Worked example: press **Text** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:Text · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Text' on Annotate's Text panel (through its fold): the tool 'Text' stands | keys: Escape (tool Text -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Height | length | 0 |  | all |
| Leader | yesno | false |  | all |
| List | choice | None | None, Bulleted, Numbered | all |
| Scale | choice | 100 |  | all |
| Type | choice | 3.5mm Arial | 3.5mm Arial, 2.5mm Arial, 5mm Arial Bold | all |

Played in these jobs:

- [5020. Add a note with a leader to the east wall of the workshop that reads "FIRE WALL".](../examples/annotation-details-and-materials.md)
- [5054. Put a note on the plant room plan pointing at the south wall: "120/120/120 FIRE RATED WALL".](../examples/annotation-details-and-materials.md)

## View Reference

A UNION command on the Annotate tab, Tag panel. It asks: "Choose the view in Refer to, then click to place the reference".

### Press it

- Tab: Annotate
- Panel: Tag
- Kind: tool
- Ribbon: Detailing > Tag

Worked example: press **View Reference** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Annotate:View Reference · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'View Reference' on Annotate's Tag panel (through its fold) (through its parent 'Tag by Category''s arrow, the row 'View Reference'; the press stood 262 ms (the menu stood at 16 ms; its row ran 233 ms; it made 0 child widgets native)): the command 'View Reference' ran; status 'Click to draw the enlargement, or sketch it' | keys: Escape (tool Callout -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

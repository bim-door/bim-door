# 7. Materials, textures and the material node graph


In this part: UNION has file materials, a shipped library of 67 photographic texture sets, and a node graph on each material that keeps one. Make a material with an op line, set it one key a line, and put it on an element by its own route.

A file material holds a colour, a texture set, a repeat size, a turn, roughness, metal, bump, see-through and glow. A texture set is a folder of photographs with its own graph. The graph is a set of ALBATROSS Material cards kept with the material. Textures are photographs and show their own colours; nine sets take their colour from the material. All of it shows in the Realistic view; a new template's 3D view opens in Hidden, so set Realistic before judging a material (last piece).

The pieces:
- Make a file material and set its keys: the op lines, all 33 keys (nine reach the Realistic view), reading back.
- The 67 texture sets by name and kind, and the nine that take their colour from `render_colour`.
- Put a material on things: layers of wall, floor and roof types, blocks, doors, windows, Forms, structural members.
- The material node graph: where a graph lives, the 19 Material cards, the door's reach.
- What reads wrong and the fix: pale and grey, relief on flat paint.

Look it up:

    get_guide {"part":"reference > Dialogs > Display Options"}
    albatross_place {"kind":"zzz"}

## Make a file material and set its keys (texture, texture_size, render_colour, glow ...)

A file material is named. Make it, then set one key a line. Send the lines in `ops_run` (one undo step). A value that holds a space is written in double quotes.

A plain material:

    op:add material name="X"

A material from a shipped texture set, with that set's ready-made graph:

    op:add material library=<set> name="X"

One key:

    op:set material name="X" key=<k> value=<v>

The nine keys that reach the Realistic view: `texture`, `texture_size` (mm), `texture_rotation`, `render_colour`, `roughness`, `metallic`, `bump`, `transparency`, `glow`.

| key | sets | values |
|---|---|---|
| `texture` | the photograph set | a set name from the next piece |
| `texture_size` | size of one repeat, mm | a number in mm |
| `texture_rotation` | the turn of the texture | |
| `render_colour` | colour of a plain material; colour of the nine brightness-only sets | `#f4f1ea`, `#7E9AAE`, `#ffffff` |
| `roughness` | rough or glossy | 0.05 (glass), 0.3 (brushed stainless), 0.85 (precast; board blocks) |
| `metallic` | how metal the surface is | 0.9 (brushed stainless) |
| `bump` | bump of the surface | |
| `transparency` | see-through level, 0 to 1 | 0.6 (glass) |
| `glow` | lifts a pale material in shade | 0.2 to 0.45 (last piece) |

A material keeps 33 keys in all. The other 24, grouped by kind, are listed in UNION's answer to a wrong key (below):
- Relief: `relief_depth`, `relief_shadow`, `height_gain`.
- For drawings: `shading_colour` (`#7E9AAE` in the glass call below), `cut_pattern`, `surface_pattern`, `surface_pattern_angle`, `surface_pattern_follows`.
- Physical: `density`, `elastic_modulus`, `poisson_ratio`, `yield_strength`, `rigidity_modulus`, `tensile_strength`, `compressive_strength`, `thermal_expansion`, `heat_conductivity`.
- Description: `description`, `material_class`, `material_keynote`, `material_mark`, `material_comments`, `manufacturer`, `cost`.

A whole call, glass:

    ops_run {"name":"Glass","lines":["op:add material name=\"Facade Glass\"","op:set material name=\"Facade Glass\" key=render_colour value=#7E9AAE","op:set material name=\"Facade Glass\" key=shading_colour value=#7E9AAE","op:set material name=\"Facade Glass\" key=transparency value=0.6","op:set material name=\"Facade Glass\" key=roughness value=0.05"]}

Brushed stainless, the same shape, with `metallic` 0.9 and `roughness` 0.3:

    ops_run {"name":"Stainless","lines":["op:add material name=\"Stainless Steel Brushed\"","op:set material name=\"Stainless Steel Brushed\" key=render_colour value=#B9BEC4","op:set material name=\"Stainless Steel Brushed\" key=shading_colour value=#B9BEC4","op:set material name=\"Stainless Steel Brushed\" key=metallic value=0.9","op:set material name=\"Stainless Steel Brushed\" key=roughness value=0.3"]}

A wrong key lists all 33 keys the material keeps. The call:

    op:set material name="Play White" key=zzz value=1

UNION's answer, exactly:

    cannot proceed: a material keeps no 'zzz' (its keys: density, elastic_modulus, poisson_ratio, yield_strength, rigidity_modulus, tensile_strength, compressive_strength, thermal_expansion, heat_conductivity, render_colour, texture, texture_size, texture_rotation, roughness, metallic, bump, transparency, glow, relief_depth, relief_shadow, height_gain, cut_pattern, surface_pattern, shading_colour, surface_pattern_angle, surface_pattern_follows, description, material_class, material_keynote, material_mark, material_comments, manufacturer, cost)

UNION's own words for a set name it does not hold:

    cannot proceed: the library holds no texture set named 'zinc_standing_seam'; nothing was written

Reading back. Keep your own list of what you set. `element_get` on an element shows the name its `Material` row holds, not the material's keys. The saved file carries the materials and the Display Options.

## The 67 texture sets by name (photographs; nine take their colour from render_colour)

Write a name exactly, lower case with underscores, as `library=<set>` or as `key=texture value=<set>`. The names below are grouped by kind of surface; a `*` marks the nine whose entry says `"grain": "luminance"`.

| kind of surface | sets |
|---|---|
| Concrete (5) | `concrete_smooth`, `concrete_board_formed`, `concrete_polished`, `concrete_rough`, `precast_panel`* |
| Brick, block, stone (8) | `brick_red`, `brick_white`, `brick_grey`*, `brick_cream`*, `brick_paver`, `blockwork`, `stone_sandstone`, `stone_granite` |
| Render, plaster, boards (5) | `render_white`, `render_grey`, `plaster_painted`, `plasterboard_painted`, `fibre_cement` |
| Roof tiles (2) | `roof_tile_terracotta`, `roof_tile_concrete`* |
| Timber (8) | `timber_oak`, `timber_floor_strip`, `timber_pine`, `timber_cladding`, `plywood`, `clt_panel`, `timber_herringbone`, `timber_floor_wide` |
| Metal (14) | `steel_brushed`, `steel_painted`, `steel_galvanised`, `steel_rusted`, `steel_plate_painted`*, `steel_sheet_worn`*, `aluminium_panel`, `zinc_cladding`, `corten`, `copper`, `metal_deck`, `box_profile`*, `corrugated`, `grating` |
| Floors and panels inside (6) | `tiles_ceramic`, `tiles_terrazzo`, `tile_floor_large`, `carpet_grey`, `vinyl_floor`, `acoustic_panel` |
| Hard paving (3) | `paving_stone`*, `asphalt`, `gravel` |
| Grass, ground, rock (16) | `lawn_mown`*, `grass`, `grass_dense`, `grass_rough`, `soil`, `bark_mulch`, `moss`, `sand`, `forest_ground`, `rock_cliff_grey`, `rock_cliff_dark`, `rock_mountain`, `rocks_ground`, `rock_mossy`, `riverbed_pebbles`, `river_bank_mud` |

The 58 sets without a `*` show their own photographed colours. `render_colour` does not change them: `brick_red` looked the same at white, #B4B4B4 and blue, on blocks.

The nine with a `*` draw brightness and take their colour from `render_colour`: `lawn_mown`, `roof_tile_concrete`, `paving_stone`, `box_profile`, `precast_panel`, `brick_grey`, `brick_cream`, `steel_plate_painted`, `steel_sheet_worn`. `op:add material library=lawn_mown` is grey, because the colour input of its graph is white. Give it a colour:

    op:set material name="X" key=render_colour value=<#rrggbb>

## Put a material on things: wall, floor and roof layers, blocks, doors, windows, Forms, structural members

**Wall, floor, roof: the layers of the type.** Duplicate a layered type, then set each layer's material. `types_list` reads each type's layers first (layer 1 is the exterior side):

    types_list {"category":"Walls"}
    type_duplicate {"category":"Walls","type":"Exterior Glazing","name":"Glass Facade"}
    type_set {"category":"Walls","type":"Glass Facade","key":"Layer 1 Material","value":"Facade Glass"}

`type_duplicate` answers the name the copy got (a name already held is numbered, "<source> 2") and its `layers`; use that name in `type_set`.

    type_set {"category":"Walls","type":"Generic 200mm","key":"Layer 1 Material","value":"Play White"}

UNION's answer lists the type's layers with the material now set:

    {"category":"Walls","id":"3043cea2-...","key":"Layer 1 Material","layers":[{"function":"Structure","layer":1,"material":"Play White","thickness":200}],"type":"Generic 200mm","value":"Play White"}

The key is `Layer <number> Material`: the number counts from 1, exterior side first. To move a wall already drawn onto another type, change its type with `@type`. Send the name of your duplicated type as the value; the call as played used a type of the template:

    param_set {"ids":["<wall id>"],"key":"@type","value":"Block 190 Core-filled"}

UNION's answer was `{"changed":1,"elements":1}`, and `element_get` then read the new type. `op:set id=<id> key=Type value=...` is refused (`A Roof has no parameter 'Type'`).

Set EVERY layer. A wall, floor or roof type draws the material of its STRUCTURE layer in the Realistic view, so a finish on another layer alone does not show. "Concrete Slab 200 + Tile" is Ceramic 10 over Concrete 200: send one `type_set` per layer.

**Block, door, window: the element's Material row**:

    op:set id=<id,id,...> key=Material value="<file material>"

It worked on block categories, doors and windows. On a Structural Framing block the row was refused: give the member's type its material instead (below). A block draws ONE texture for the whole element; each part's colour still comes from its material word (part 8, Blocks). With no Material set, a block takes its category's default finish: Furniture and Doors draw a grey wood grain over every part, so white doors, pictures and fabric look like dirty timber. Choose by the block:
- painted or manufactured: a plain file material, `render_colour` `#ffffff`, `glow` `0.2`;
- timber pieces: a timber set;
- roof tile blocks: `roof_tile_concrete` (one of the nine: give it a `render_colour`);
- board blocks: a timber floor set with `roughness` `0.85`.

A file material's name in a block type's material parameter draws a pale timber; that parameter takes the fixed words (part 8, Blocks).

**A Form** (a freeform surface; part 9):

    ops_run {"name":"materials","lines":["op:add material name=\"Play White\"","op:set material name=\"Play White\" key=render_colour value=#f4f1ea","op:set material name=\"Play White\" key=glow value=0.2","op:add material library=copper name=\"Play Copper\"","op:set id=<form id> key=Material value=\"Play White\""]}

A Form takes the element `Material` row; `element_get` then shows `"Material":"Play White"`. A plain colour material showed in the Realistic view. Look at the picture before you say what a Form shows. Blocks, doors and windows take a texture through their `Material` row (above).

**A structural member: its type.** A beam type takes key `Material` (the call is also in the Two Towers set):

    type_set {"category":"Structural Framing","type":"323.9x10CHS","family":"Circular Hollow Section - Hot-Finished","key":"Material","value":"Stainless Steel Brushed"}

## The material node graph: where a graph lives, the Material cards, what the door reaches

**Where a graph lives.** Each of the 67 sets has a `graph.albatross.json` beside its images (colour, normal, roughness). `op:add material library=<set>` gives the new material that set's graph.

**The 19 Material cards of ALBATROSS.** UNION's own list, in its answer to a card kind it does not hold: AO Map, Base Colour Map, Cut Pattern, Dirt, Edge Wear, Flatten Normal, Height Map, Material Output, Moss and Stain, Multiply Map, Normal Map, Pattern Colour, Real-World Size, Relief, Rock Scatter, Roughness Map, Shading Colour, Surface Pattern, Wetness.

**What the door reaches.** The tools place, set, wire and read these cards on the ALBATROSS canvas (part 10, ALBATROSS). `albatross_place` and `albatross_graph` open the ALBATROSS window when it is closed.

Placing and wiring Material cards, a Material Output among them, worked.

## What reads wrong and the fix: pale and grey, relief on flat paint

**Flat grey, or no material at all.** The 3D view is in Hidden (a new template's view opens so). Set the style, with the 3D view in front:

    steps_run {"steps":["ribbon:View:Display Options · picks — · keys — · fields Display Options: Style=Realistic; Show Edges=no; Silhouette Edges=no; Shadows=yes; Soft Shadows=yes; Backdrop=Sky; OK= · expect —"]}

Part 6 (See your work) holds the pictures.

**A lawn or roof tile that is grey.** One of the nine brightness-only sets: set `render_colour` (the texture sets piece).

**Pale materials go grey on faces away from the sun.** `glow` 0.2 to 0.45 keeps them pale:

    op:set material name="Play White" key=glow value=0.2

**Relief on flat paint reads as dirt**. Paint is a plain file material with no `texture` key, `render_colour` `#ffffff`, `glow` `0.2`. Do not set `bump` or a Relief card on painted materials.

**A lawn or ground part is buried.** The landscape pad stands at the lowest level whose name is like "Ground": name the lowest site level so.

**A block shows pale timber.** Its material parameter holds a file material's name: put the file material on the element's `Material` row instead (the placing piece).

Look it up:

    get_guide {"part":"reference"}
    get_guide {"part":"reference > Dialogs > Display Options"}

`get_guide` with part `reference` lists the reference: Commands, Dialogs, Ops grammar; the Display Options call answers that dialog's fields.

Look it up:

    params_schema {"category":"<category>"}

`params_schema` lists the rows of a category. `types_list {"category":"Walls"}` reads the wall types. A wrong card kind is answered with the card kinds by group; a wrong key is answered with the 33 keys a material keeps.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

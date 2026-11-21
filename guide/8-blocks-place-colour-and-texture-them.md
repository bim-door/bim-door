# 8. Blocks: place, colour and texture them


A block is a library family: furniture, casework, fixtures, lights, plants, people, cars, steel sections, doors, windows, equipment, and the build-ups of walls, floors, roofs and ceilings. You can place any of them, change their types and parameters, give a placed block a photographic texture, and set the colour of each of its parts.

In this part:
- Find a block (`library_list`) and place it (the `op:place block` line with every key, rotation, lifting, ceiling-hung blocks, doors and windows by `op:add door` and `op:add window`).
- Types and parameters of a block: `types_list`, `type_duplicate`, `type_set`, instance parameters.
- Texture and colour: one texture per element from its `Material` row, what a block shows with none, the played remedies, and the 67 material words for block parts with their colours.
- The category rule, doors and windows.

Look it up: `library_list {"category":"Furniture","limit":5}`.

## Find a block: library_list and its arguments

`library_list` lists the Block Database's block names of one category, including blocks that serve it. It reads no model. `category` is required: `library_list {}` answers `library.list needs a category`. Optional: `limit`, `after`.

List one category:

    library_list {"category":"Furniture","limit":5}

UNION's answer: `{"category":"Furniture","count":5,"more":true,"names":["Armchair","Banquette Booth","Bar Stool","Bed - Bunk","Bed - Double"],"next":5,"total":204}`. Send `next` as `after` while `more` is true:

    library_list {"category":"Furniture","limit":50,"after":50}

A wrong word in a call lists the valid ones: UNION's refusals name their fix and list the valid words.

## Place a block: op:place block, rotation, level, ceiling host, doors and windows

The line:

    op:place block family="<family>" at=(x,y) type="<type>" level="Ground" rotation=90 host=<id>

`family` and `at` are required. `type`, `level`, `rotation` (degrees) and `host` (an element id) are optional. A value that holds a space is quoted. `family` is a Block Database block name; the block loads into the model when it is not there. A played line, a tube section placed on the ground level:

    ops_run {"lines":["op:place block family=\"Circular Hollow Section - Hot-Finished\" type=323.9x10CHS at=(0,-20000) level=Ground"]}

The form for a free-standing block, many lines to a call:

    op:place block family="<family>" at=(4200,3100) level="Ground" rotation=90 type="<type>"

- `made` in the answer is the block's id. Keep `ops_run` batches to 25 to 35 lines on a large model.
- To raise a placed block, move it with `op:move`, by (dx,dy,dz) in mm:

        op:move id=<made id> by=(0,0,1500)

- Repeat an element: `op:array id=<seed> count=5 step=(8400,0,0)` leaves the seed and makes 4 copies; their ids are in `made`. It was used on columns and beams.
- A block whose category is not one of UNION's categories answers with words that include `load it first`. See the category rule in the piece "The category rule, doors and windows".

A ceiling-hung block (its file says host ceiling) takes the ceiling's id in `host=`; the line is `op:place block ... host=<ceiling id>`:

    op:place block family="<family>" at=(4200,3100) level="Ground" rotation=0 type="<type>" host=<ceiling id>

Read the ceiling ids first (the rows come under `rows`):

    elements_query {"category":"Ceilings","fields":["id","type"],"limit":100}

Doors and windows. A door or window block goes into a wall with `op:add door` or `op:add window`, which cuts the opening. `place block ... host=<wall id>` answered ok with no note and cut no opening: the element read back as a BlockInstance where a real door reads Door.

    op:add door wall=<wall id> offset=1200 sill=0 type="<door type>" flip=no hand=no

`wall` is required; give exactly one of `at` (a point near the wall's line) or `offset` (mm from the wall's start to the centre of the opening). `sill`, `type`, `flip` and `hand` are optional. `type` is a Doors or Windows type the model holds. Played lines:

    op:add door wall=<south wall id> at=(2000,0)
    op:add window wall=<wall id> at=(65100,8400) sill=900 type="1800 x 1800"

- `hand=yes` was written to put the hinge at the wall's end and `flip=yes` to swing the leaf the other way. Look at a plan or a picture before you tell the person which way a door opens.
- A family new to the model is loaded by one placement with `host=<wall id>`; after that `op:add door ... type=` takes its types. Delete the stray block with `op:delete id=<made id>`; for a tube section the type stayed.
- For a door or window of its own hand or size, `type_duplicate` its type first (next piece) and add with the copy.

## Types and parameters of a block: types_list, type_duplicate, type_set, instance parameters

A type holds the values every block placed on it shares. `types_list` reads the types the model holds. A family in a model holds the types that were placed. To put a type in the file, place the block once, then delete the element; for a tube section the type stayed:

    op:delete id=<made id>

Copy a type, then change the copy. `type_duplicate` carries the original's parameters:

    type_duplicate {"category":"Walls","type":"Exterior Glazing","name":"Blue-grey glass"}

The played shape, on a wall type:

    type_set {"category":"Walls","type":"Blue-grey glass","key":"Vertical Spacing","value":2100}

`type_set` of a block type's material parameter takes one of the 67 words (next but one piece). The reply says `unchanged:true` when the type already held the value. A wall type's layer takes a file material by the key `Layer 1 Material`: part 7 (Materials) has the call.

Door heights were set on the types (`Height` 2400, frames `Paint - White`). A door type's `Glazed` set true draws the whole leaf as glass: set it false when the leaf is solid.

Instance parameters belong to one placed block (a Length on a skirting run, a Mark). Write them after placing:

    op:set id=<made id> key=Length value=2400

`param_set {"ids":["<door id>"],"key":"Mark","value":"D1"}` set Mark on one element and answered `{changed:1, elements:1}`.

A key that begins with `@` is an element column. On a wall, to a type the model holds:

    param_set {"ids":["<wall id>"],"key":"@type","value":"Block 190 Core-filled"}

UNION answered `{"changed":1,"elements":1}` and `element_get` then read the new type and family. The same call on a roof was played with the same answer. `op:set id=<id> key=Type value=<type>` is refused: `A Roof has no parameter 'Type'`.

For Doors and Windows, `params_schema {"category":"Doors"}` answers its identity rows and `open:true`: the list is not closed, and `param_set` sets a further parameter by name. Read one element's parameter names with `element_get {"id":"<id>"}`.

Look it up: `params_schema {}` lists the categories that carry rows; `params_schema {"category":"Doors"}`; `element_get` on a placed block.

## Texture and colour of a block: the Material row, the default finish, the played remedies

A block draws ONE texture for the whole element. That texture is the file material on the element's own `Material` row. Each part also takes the colour of its material word (next piece).

Make a plain file material, then set the row on every block that should use it. The lines are the played shapes of `op:add material`, `op:set material` and `op:set id=<ids> key=Material`:

    ops_run {"name":"Block material","lines":["op:add material name=\"Blk Plain\"","op:set material name=\"Blk Plain\" key=render_colour value=#ffffff","op:set material name=\"Blk Plain\" key=glow value=0.2","op:set id=<id>,<id> key=Material value=\"Blk Plain\""]}

- `id=` takes several ids, separated by commas with no space.
- The row worked on block categories, doors and windows. On a Structural Framing block the row was refused. Give the member's type its material instead, a file material or one of the 67 words. The call is Two Towers prompt 12: `type_set {"category":"Structural Framing","type":"323.9x10CHS","family":"Circular Hollow Section - Hot-Finished","key":"Material","value":"Stainless Steel Brushed"}`
- With no `Material` set, a block takes its category's default finish. Furniture and Doors draw a grey wood grain over every part, so white doors, pictures and fabric look like dirty timber.
- A texture set is a photograph and shows its own colours. Nine sets draw brightness and take their colour from `render_colour`: lawn_mown, roof_tile_concrete, paving_stone, box_profile, precast_panel, brick_grey, brick_cream, steel_plate_painted, steel_sheet_worn. Part 7 (Materials) lists the 67 sets and the keys `texture`, `texture_size`, `texture_rotation`, `render_colour`, `roughness`, `metallic`, `bump`, `transparency`, `glow`.

Remedies played on one house, 548 blocks plus 29 doors and 113 windows:

| Block | File material to set on the Material row |
|---|---|
| Painted or manufactured pieces, doors, windows, trim, pictures | plain: `render_colour #ffffff`, `glow 0.2` |
| Timber pieces | `texture timber_oak`, `render_colour #ffffff`, `glow 0.1` |
| Roof tile blocks | `texture roof_tile_concrete`, `render_colour #ffffff`, `texture_size 1800` |
| Board blocks (floorboards, decking) | `texture timber_floor_strip` (floorboards) or `timber_floor_wide` (deck boards), `render_colour #ffffff`, `roughness 0.85` |

Each key is one line: `op:set material name="Blk Timber" key=texture value=timber_oak`.

- Pale materials go grey on faces away from the sun; `glow` 0.2 to 0.45 keeps them pale.
- A block material PARAMETER (Bedding, Top Material) holds a word. A project material name there draws as timber. Set it on the type: `type_set {"category":"Furniture","type":"<type>","family":"<family>","key":"<material parameter>","value":"Paint - White"}`.
- Timber words carry a wood grain: leave them off cloth. Brick and stone words carry their own pattern. Brown words draw orange in sunlight.

## The 67 material words for block parts, with their colours

Every material parameter of every block type must hold one of these words. The hex is the word's colour. Another name draws as timber. Words as UNION's table prints them:

- Whites: Paint - White F3F3F0 (matt) | Melamine EDEBE4 (satin joinery) | Laminate D9D4C7 (cream) | Plasterboard E9E6DF | Porcelain F4F5F3 (gloss) | Vitreous China F1F4F6 (gloss) | Ceramic ECEAE4 (tile) | Enamel F0F0EC | Acrylic EFEFEB | Plastic - White F0EFEB | Render DBD4C5 (cream, rough) | Limestone D8CDB4 (cream stone) | Car Paint - White F1F2F0 (gloss)
- Greys: Paint - Grey 8C8C8C | Fabric 7D8790 (mid grey-blue cloth) | Upholstery 5F6A74 (dark slate cloth) | Geotextile 5D6064 (dark neutral) | Membrane 3F4A52 (very dark slate) | Stone A39C91 | Granite 8B8681 | Concrete B8B1A4 | Fibre Cement BEB9AF | Aluminium C3C8CC | Steel 778B98 | Galvanised Steel A7B3BA | Stainless Steel C9D0D5 | Chrome DCE1E5 | Cast Iron 55595D | Car Paint - Silver B4B9BD
- Blacks: Paint - Black 282828 | Plastic - Black 2B2B2B | Rubber 222222 | Tyre 1C1C1D | Car Paint - Black 1A1B1D (gloss, piano) | PE 34363A
- Timbers: Timber - Softwood DDBB82 (light pine) | Plywood D9BD8B | CLT D8B27A | Glulam D4A45E | LVL CC9A57 | OSB C8A15C | Veneer B98E5A (mid oak) | Timber - Hardwood A9814C (mid brown) | PSL B47A45 (red-brown) | Hardboard 6E4F33 (dark walnut) | Bark 5B4636
- Warm: Leather 6B4430 (brown) | Rammed Earth B88A62 (terracotta-tan) | Sandstone CFAF7E (beige) | Clay Brick A75D40 (brick red) | Soil 7A6049 | Copper B87333 | Brass C9A640 | Insulation E3CF86 (yellow batts) | Mineral Wool D6BE78
- Colours: Paint - Red B93A2E | Car Paint - Red A8211C | Paint - Green 1F8A4D | Foliage 4F7A3A (plants) | Car Paint - Blue 1F3F7A
- Glass and light: Glass BCD5DA | Tinted Glass 6B8288 | Mirror CED7DB | Glass Block C3D9DC | Lens - Clear DCE8EC | Lens - Opal F8F8F5 (glows a little) | LED Emitter FFF1C9 (glows)

That is 13 + 16 + 6 + 11 + 9 + 5 + 7 = 67 words (counted from the table).

Choose the nearest word for each surface:

| Surface | Word |
|---|---|
| white paint | Paint - White |
| white joinery | Melamine |
| grey paint | Paint - Grey |
| blue-grey | Steel |
| charcoal | Geotextile or Membrane |
| cream | Laminate, Render or Limestone |
| black | Paint - Black or Plastic - Black |
| gloss black | Car Paint - Black |
| dark timber | Hardboard |
| red-brown timber | PSL |
| mid timber | Timber - Hardwood or Veneer |
| light timber | Timber - Softwood, Plywood or Glulam |
| brass, chrome, stainless | Brass, Chrome, Stainless Steel |
| zinc, galvanised | Galvanised Steel |
| glass, frosted glass | Glass, Glass Block |
| white china, white tile | Vitreous China or Porcelain, Ceramic |
| grey stone | Granite or Stone |
| terracotta | Rammed Earth or Clay Brick |
| leaves, bark, soil | Foliage (some Paint - Green), Bark, Soil |
| lamp glow | LED Emitter or Lens - Opal |

Set a type's word with `type_set` (piece "Types and parameters of a block"); the reply says `unchanged:true` when the type already held it, and a refused key lists the type's parameters.

## The category rule, doors and windows

The category rule. A block's `category` must be one of UNION's categories, or placing answers with words that include `load it first`. Names that answered `load it first` in play: Floor Finishes, Lighting, Equipment, Columns, Site.

Doors and windows are hosted blocks. A door block's `Glazed` set true draws the whole leaf as glass.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

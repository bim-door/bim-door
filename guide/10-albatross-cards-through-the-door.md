# 10. ALBATROSS: cards through the door


ALBATROSS is UNION's node graph: a canvas of cards joined by wires. A card is a small function with named inputs and outputs (its ports) and settings. An agent draws a graph with `albatross_place`, `albatross_set`, `albatross_wire` and `albatross_graph`. Some cards (28 kinds, in the Structural, Services and Model groups) write elements into the model when their `run` setting turns true: `Brace between Points` was played. The rest compute: numbers, lists, points, curves, surfaces, material maps.

In this part:
- The card tools: exact arguments, the shape of each answer, the rule for an unknown kind, a first graph, a picture of the graph.
- The card kinds by group: every kind by exact name, writers marked.
- Cards that write the model: the `run` setting, a writer's inputs, other routes to the same elements.
- A gridshell: the played recipe, 560 tubes, and a canopy graph. Then curves, surfaces and material graphs by cards, and where a material's graph is stored.

Look it up: `albatross_place {"kind":"zz no such card"}` lists every kind by group; `albatross_graph {}` lists the cards on the canvas.
Then: `view_image {"window":"albatross"}` pictures the graph; `get_guide {"part":"guide > 7. Materials"}` for materials.

## The card tools: place, set, wire, read, read one card, delete

`albatross_place` opens the ALBATROSS window when it is closed. A card is named by its `card` id from the place answer, for example `node-f3508b`, or by its drawn title. When two cards share a title, UNION takes the first. Name a card by its id.

**Place** a card:

    albatross_place {"kind":"<kind>","at":[<x>,<y>],"inputs":{"<port or setting>":<value>}}

`kind` is a library kind in any case. `at` is optional, in canvas pixels; the canvas steps the card clear of its neighbours. `inputs` is optional and sets ports and settings as `albatross_set` does. Answer: `{card, kind, title, ports:{inputs, outputs}, settings, set, refused, answer, state, messages?}`. Read `ports` and `settings` there and never guess a port name. `set` holds each input that took, read back; `refused` lists each input refused, with its words; the card stands. Both are always there, {} and [] when empty. An Expression whose formula does not parse answers `refused` and no card is placed. One canvas undo record.

`answer` is the card's answer in words. `state` is `rest`, `warning` or `error`; `messages` lists the card's own lines when `state` is `warning`. A card asking for an input is not at fault: an unwired Expression answers `cannot proceed: an Expression names an input not wired: 'x'` (state `error`) and an unwired Polyline `cannot proceed: Polyline needs its 'points' input` (state `warning`).

**An unknown kind lists the library's kinds**:

    albatross_place {"kind":"zz no such card"}

Answer: `cannot proceed: the Albatross library has no card kind 'zz no such card'. Kinds by group: Model: Beam, Brace, Column, ...` and every kind of every group, about 3 KB. Nothing is placed.

**Set** one input or setting:

    albatross_set {"card":"<card id>","input":"<port or setting>","value":<value>}

Answer: `{card, input, readBack, note?, answer, state, messages?}`. `note` says the input is wired, so the wire's value is used and the value set waits. An input the card does not carry, or a value it refuses, answers `refused` in the canvas's words; a Boolean's `state` takes `true`, `false` or the words "true" and "false". `Data Output` and `Data Input` refuse to write or read a file while UNION AI is working: the files are the person's.

**Wire** an output into an input:

    albatross_wire {"from":"<card id>","output":"<output name>","to":"<card id>","input":"<input name>"}

`output` is optional and defaults to the first output of `from`. A new wire replaces the wire already into that input (`replaced`); the same wire again answers `unchanged` true. The answer carries the `to` card's `ports`, `answer` and `state`, and `messages` if any. A cycle, or a Material pin joined to a pin of another type, is refused in the canvas's words. Any other wire stands, and the `to` card says in `answer` and `state` whether it can use the value. A card or port that is not there answers `not_found` or `refused` and names the ports it has.

**Read** the graph:

    albatross_graph {"limit":200}

Answer: `{total, count, cards:[{card, kind, title, ports:{inputs, outputs}, inputs, cut?, settings, enabled?, answer, state, messages?}], wires:[{from, output, to, input}], more, next?, stale?}`. `limit` is at most 1000; `after` is an offset. An `inputs` value over 300 characters is cut with ...; `cut` names the inputs cut. `wires` are those into the cards of the page. `enabled` is false for a disabled card only. `stale` says why the answers are not those of the graph as it stands: read again. With no window open the call opens it with the model's stored graph and no other card. The window already holds one Boolean card that is not yours.

**A first graph**: a Series (the numbers), an Expression on them, a Point from the result and a Polyline through the points. Keep the `card` id from each place answer as <S>, <E>, <P>, <L>.

    albatross_place {"kind":"series","inputs":{"count":4}}
    albatross_place {"kind":"Expression","inputs":{"expression":"x*2"}}
    albatross_place {"kind":"Point"}
    albatross_place {"kind":"Polyline"}
    albatross_wire {"from":"<S>","to":"<E>","input":"x"}
    albatross_wire {"from":"<E>","to":"<P>","input":"x"}
    albatross_wire {"from":"<P>","to":"<L>","input":"points"}
    albatross_graph {}

Ports: Series in `start`, `step`, `count`, out `numbers`; Expression in `x`, out `value`; Point in `x`, `y`, `z`, out `point`; Polyline in `points`, out `polyline`. The Series answers `[4] 0, 1, 2, 3`. When all is wired the Polyline's state is `rest`, and `albatross_graph` lists five cards and three wires. Change the count:

    albatross_set {"card":"<S>","input":"count","value":6}

**A picture of the graph**. With the ALBATROSS window open and in front, `view_image` with no `window` returns the graph, not the model. Name the window:

    view_image {"window":"albatross"}
    view_image {"window":"main"}

## The card kinds by group

UNION's own list, from the answer of `albatross_place {"kind":"zzz"}`: every group and kind, typed in any case. `*` marks the 28 cards that write elements into the model when `run` turns true (next piece). Ports of a kind are read from the place answer. Each line: the names.

- Model (21): `Beam`, `Brace`, `Column`, `Deconstruct Element`, `Filter Elements`, `Floor`, `Foundation`, `Get Parameter`, `Grid`, `Level`, `Model Pipeline`, `Move Elements`*, `Opening`, `Roof`, `Schedule from Elements`*, `Selected Elements`, `Services Run`, `Set Parameter`*, `Sheet`, `View`, `Wall`.
- Data (3): `Boolean`, `Number`, `Text`.
- Maths (25): `Addition`, `Cos`, `Division`, `Domain`, `Expression`, `Multiplication`, `Range`, `Round`, `Series`, `Sin`, `Subtraction`, `Tan`, `Average`, `Bounds`, `Construct Domain`, `Deconstruct Domain`, `Equality`, `Gate And`, `Gate Not`, `Gate Or`, `Larger Than`, `Mass Addition`, `Random`, `Remap Numbers`, `Smaller Than`.
- Sets (46): `List Length`, `Reverse`, `Clean Tree`, `Concatenate`, `Create Set`, `Cull`, `Cull Index`, `Cull Pattern`, `Dispatch`, `Duplicate Data`, `Entwine`, `Explode Tree`, `Flatten`, `Format`, `Graft`, `Insert Items`, `Key/Value Search`, `List Item`, `Member Index`, `Merge`, `Null Item`, `Partition`, `Path Mapper`, `Repeat Data`, `Replace Items`, `Replace Nulls`, `Set Difference`, `Set Intersection`, `Set Union`, `Shift`, `Shift Paths`, `Sort`, `Split List`, `Stream Filter`, `Stream Gate`, `Sub List`, `Text Case`, `Text Join`, `Text Length`, `Text Replace`, `Text Split`, `Tree Branch`, `Tree Item`, `Tree Statistics`, `Trim Tree`, `Weave`.
- Vector (28): `Array`, `Distance`, `Move`, `Point`, `Vector`, `Amplitude`, `Angle`, `Bounding Box`, `Closest Point`, `Construct Plane`, `Cross Product`, `Cull Duplicates`, `Deconstruct`, `Deconstruct Plane`, `Deconstruct Vector`, `Dot Product`, `Mirror`, `Plane`, `Populate 2D`, `Rotate`, `Scale`, `Sort Points`, `Unit Vector`, `Vector 2Pt`, `Vector Length`, `XY Plane`, `XZ Plane`, `YZ Plane`.
- Curve (20): `Length`, `Line`, `Polyline`, `Arc`, `Arc 3Pt`, `Circle`, `Curve`, `Curve Closest Point`, `Divide`, `End Points`, `Evaluate`, `Explode`, `Extend`, `Join`, `Offset`, `Point In Curve`, `Point On Curve`, `Polygon`, `Rectangle`, `Shatter`.
- Surface (8): `Area`, `Boundary`, `Extrude`, `Loft`, `Surface Divide`, `Surface Evaluate`, `Surface Offset`, `Surface Points`.
- Intersect (3): `Curve with Curve`, `Curve with Plane`, `Solid with Plane`.
- Structural (15): `Beam along Line`*, `Brace between Points`*, `Column at Point`*, `Floor from Loop`*, `Grid from Line`*, `Level from Number`*, `Opening at Point`*, `Pad at Point`*, `Raft from Loop`*, `Section by Name`, `Space from Loop`*, `Stair between Levels`*, `Strip along Curve`*, `Truss between Points`*, `Wall along Curve`*.
- Material (19): `AO Map`, `Base Colour Map`, `Cut Pattern`, `Dirt`, `Edge Wear`, `Flatten Normal`, `Height Map`, `Material Output`, `Moss and Stain`, `Multiply Map`, `Normal Map`, `Pattern Colour`, `Real-World Size`, `Relief`, `Rock Scatter`, `Roughness Map`, `Shading Colour`, `Surface Pattern`, `Wetness`.
- Services (12): `Board at Point`*, `Circuit from Devices`*, `Device at Point`*, `Duct along Polyline`*, `Fitting at Corner`*, `Fixture at Point`*, `Pipe along Polyline`*, `Riser between Levels`*, `Size from Number`, `Sprinkler at Point`*, `Terminal at Point`*, `Tray along Polyline`*.
- Params (23): `Boolean Toggle`, `Button`, `Cluster`, `Colour Swatch`, `Control Knob`, `Curve Param`, `Data Dam`, `Data Input`, `Data Output`, `Data Recorder`, `Digit Scroller`, `Gradient`, `Graph Mapper`, `Line Param`, `MD Slider`, `Panel`, `Param Viewer`, `Point Param`, `Relay`, `Scribble`, `Timer`, `Value List`, `Vector Param`.
- Display (4): `Colour Hue`, `Colour RGB`, `Custom Preview`, `Split ARGB`.

Everyday word to group: column, beam, wall, floor, slab, grid, level, stair, footing, truss, brace go to Structural; duct, pipe, sprinkler, socket, switchboard, cable tray, luminaire go to Services; formula, sequence, random, average to Maths; list, tree, text, unique to Sets; point, vector, plane, rotate to Vector; spline, polyline, arc, offset, divide to Curve; loft, extrude, surface area to Surface; slider, toggle, note, colour picker to Params; texture, normal map, roughness, weathering to Material. A kind not found by a word: send the wrong kind above and read the list.

## Cards that write the model

A writer card makes elements in the model when its `run` turns true. They are in the Structural, Services and Model groups and marked `*` in the previous piece.

**The run rule.** A writer card writes only when its `run` setting goes from false to true; played with the Brace:

    albatross_set {"card":"<card id>","input":"run","value":true}

The answer says what was made, for example `created N braces`; the made elements stand in their category (the Brace: Structural Framing; check with `document_info {"categories":true}`). Played with the Brace: the write is one Undo entry named `Add-in: albatross.set`. One Undo takes the whole write back and one Redo brings it back. The step that does it:

    steps_run {"steps":["qa:Undo · picks — · keys — · fields — · expect —"]}

After an Undo the card still reads `run` true: set `run` false, then true, to write again. `run` true again on unchanged cards answers `unchanged: 1 element already written` and adds nothing. Without `run` true a writer only previews. Cards read `level` as a level NAME; empty means the lowest level. A point that carries a z stands at that height.

**Structural writers**; input names:
- `Brace between Points`: start, end, type, run.

**Other routes to the same elements**: the `Roof` command (part 3); Forms by `Freeform Curve`, `Loft`, `Sweep` and `Revolve` (part 9). A writer card's `run` is the door's write. A `Tower` card is not among the kinds UNION lists.

## A gridshell: a lattice of tubes round a form

The card `Brace between Points` writes one steel member from a start point to an end point when its setting `run` is true, so a gridshell is a Series that counts the members, Expressions that turn the count into two points each, and one Brace card. Played, a lattice of 14 rows by 40 round, 560 members. N is the number round, M the rows, H the height, `c` the member's number.
1. Put the tube section in the file once:

        ops_run {"lines":["op:place block family=\"Circular Hollow Section - Hot-Finished\" type=323.9x10CHS at=(0,-20000) level=Ground"]}

   then `op:delete id=<the made id>`; the type stays and the Brace can use it.
2. `albatross_place` every card first, then wire (an Expression placed before its names are wired answers `cannot proceed`: expected). Cards: a Series (`start` 0, `step` 1, `count` N*M), and Expressions. `ts`, `zs` and the rest below are YOUR labels for what each holds, not names the door knows: keep each place reply's `card` id under its label and wire by that id, never by the title "Expression" (eight share it). Played with N 40, M 14, H 51200 (all 12 place calls: Two Towers Prompt 8):

        albatross_place {"kind":"Series","at":[40,150],"inputs":{"start":0,"step":1,"count":560}}

   - `ts` t at the member's start: `6.283185307179586*(c % N)/N`; `te` at its end: `6.283185307179586*((c % N) + 1)/N` (grammar `+ - * / // % **`, brackets, `sin cos tan sqrt exp floor ceil fabs pow atan2 hypot` and more; `min`, `max`, a condition and `pi` are not among them).
   - `zs` start height: `H*((c // N) + ((c % N) + (c // N)) % 2)/M`; `ze` end height: `H*((c // N) + 1 - ((c % N) + (c // N)) % 2)/M`. Neighbouring members rise and fall in turn, so they close into diamonds.
   - `xs`, `ys`, `xe`, `ye`: centre plus radius times `cos(t)` or `sin(t)`; the radius may depend on `z`, so wire `zs` (and `ze`) into them too. A plan that swells and flares, played: `R(t,z) = pow(pow(fabs(cos(t)/a),6) + pow(fabs(sin(t)/b),6), -0.16666666666666666) + 1500*(1 + sin(2*t + 4.71238898*z/28800)) + 2500*pow(1 - z/H, 3)` (a rounded rectangle of semi-axes a and b, a wave of 0 to 3,000 mm, a flare of 2,500 mm at the ground); it closes in over a roof when the first term is multiplied by `sqrt(1 - 0.55*pow(((z - roof) + fabs(z - roof))/(2*(H - roof)), 2))` (`roof` is the roof level's elevation in mm; played: H 51,200, roof 43,200).
   - The centre is the plan's middle and a, b are half the plan's x and y extents plus the clearance you want: the played plan is 33,600 by 25,200 (centre 16,800, 12,600) with a 22,400 and b 17,700, which is +5,600 and +5,100; the wave adds 0 to 3,000 mm and the flare 0 at the top. Check the smallest gap to the facade by arithmetic before the bake.
   - two `Point` cards `ps` and `pe`, and the `Brace between Points`.
3. Wire (`output` is `numbers` for the Series, `value` for an Expression, `point` for a Point): `c` into `ts`, `te`, `zs`, `ze`; `ts` into `xs` and `ys` input `t`; `te` into `xe` and `ye`; `zs` into `xs`, `ys` and `ps` input `z`; `ze` into `xe`, `ye` and `pe` input `z`; `xs`, `ys` into `ps` inputs `x`, `y`; `xe`, `ye` into `pe`; `ps` into the Brace input `start`, `pe` into `end`. Wires answer `cannot proceed` or `refused` until the last one: expected.
4. Set the section, then run:

        albatross_set {"card":"<brace>","input":"type","value":"323.9x10CHS"}
        albatross_set {"card":"<brace>","input":"run","value":true}

   The answer says `created N braces` and the members stand in Structural Framing (`document_info {"categories":true}`). To picture the shell: part 6 (See your work); on a large model: part 12 (Large models) first.
5. After a bake: one `qa:Undo` took back the whole bake (684 members, named `Add-in: albatross.set`) and one `qa:Redo` brought it back. Leave `run` true: changing a Point-side card moves the answers and not the braces. `run` true again on unchanged cards answered `unchanged: 1 element already written` and added nothing. After a `qa:Undo` of a bake the card still reads `run` true and says the same while the model holds none: set `run` false, then true.
6. Several shells (a skin round each building, columns that flare into a canopy) are the same recipe once each, with the card set placed again (a graph of 12 cards and 20 wires per shell); an Expression's variable is an input of the same name, so wire each one; the window's own Boolean card is not yours.

**A second played graph: a canopy of 70 members**. Two Towers Prompt 11: a patch of braces over two parameters, s along (7 divisions) and t across (10 rows). It is 14 cards (a Series, ten Expressions, two Points, one Brace) and 22 wires, placed first and wired by id as above, with s and t as the Expression inputs. Its Series counts 70.

- `ss` `(c % 7)/7`; `se` `((c % 7) + 1)/7`; `ts` and `te` use `c // 7` and `c % 7` as in step 2 over 10 rows.
- `ys` and `ye` `4400 + 24800*t`; `zs` and `ze` `28800 + 3000*sin(3.141592653589793*s) + 1200*sin(3.141592653589793*s)*(1 - cos(18.84955592153876*t))/2`. `xs` and `xe` are long formulas in s and t.
- All its calls, with the `xs` and `xe` formulas:

        get_guide {"part":"Two Towers > Prompt 11"}

## Curves, surfaces and material graphs by cards

Forms in the model, smooth and freeform, come from the commands `Freeform Curve`, `Loft`, `Sweep` and `Revolve`: part 9 (Forms, freeform curves and surfaces).

**Where a material's graph is stored.** The tools place, set and wire Material cards. One route through the door: `op:add material library=<set> name="X"` attaches a shipped texture set's ready-made graph. The 67 sets and their keys: part 7 (Materials).

Textures are photographs: the map cards bring a set's own images, and the nine sets marked `"grain": "luminance"` take their colour from `render_colour` (part 7).

Look it up: `albatross_place {"kind":"zz no such card"}` for the kinds; the ports of a card are in its own place answer; `albatross_graph {}` for what a graph holds; `get_guide {"part":"guide > 7. Materials"}` for materials.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

# UNION MCP BIM Server

The MCP server built into UNION, a BIM and CAD drafting program, and how an AI agent uses it to model a building and make its drawings: the guide, every command, the one-line ops, and 449 real drafting jobs with their exact calls and UNION's answers, played on UNION 1.0.0-beta.2.

UNION models a building and makes its drawings: plans, sections, elevations, details, schedules and sheets, for structural, mechanical, electrical and architectural offices. An AI works in it through calls: `ops_run` (one line per element, for example `op:add wall from=(0,0) to=(6000,0) level=Ground`), `steps_run` (any ribbon press, dialog or pick, in UNION's step language), `commands_run`, reads of every element, type and schedule, and pictures of any view. Each call answers green or red in UNION's own words, with the counts it changed.

## Contents

- [guide/](guide/README.md): the work loop and every part of the guide.
- [commands/](commands/README.md): 499 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.
- [ops.md](ops.md): the 54 one-line op kinds and their keys.
- [examples/](examples/README.md): 449 drafting jobs, request, calls and result, every line played green; all of them in [examples/jobs.jsonl](examples/jobs.jsonl).
- [guide/two-towers.md](guide/two-towers.md): 15 prompts that draw two steel towers, a gridshell and a drawing set.
- [llms.txt](llms.txt) and [llms-full.txt](llms-full.txt): the map, and everything in one file.
- The same 449 jobs as a dataset: [huggingface.co/datasets/bimdoor/drafting-jobs](https://huggingface.co/datasets/bimdoor/drafting-jobs).

## Reading a job

- The person opens a new project from a template; through the MCP server, New is the person's own press.
- `ops_run {"lines":[...]}`: one line per element. Units are millimetres.
- `steps_run {"steps":[...]}`: `<control> · picks <points> · keys <keys> · fields <Dialog: Field=value> · expect <what must show>`.
- UNION's answer to each line, then UNION's count of the model after the last line.

## A Revit alternative an AI can drive

UNION is building information modelling (BIM) and CAD drafting software for structural, mechanical, electrical and architectural offices, and an alternative to Autodesk Revit and AutoCAD for drawings. Its tools work the way a Revit user expects: levels, grids, walls, floors, roofs, stairs, structural columns and framing, ducts, pipes and cable trays, views, sections, elevations, sheets and schedules. Its MCP server gives an AI agent every one of them.

Search words: UNION MCP BIM Server, BIM MCP server, MCP server for BIM, building information modeling MCP, Revit MCP, Revit alternative, Autodesk Revit alternative, AutoCAD alternative, AI BIM, AI CAD drafting, AEC MCP server, MCP for architecture and engineering drawings.

Revit, AutoCAD and Autodesk are trademarks of Autodesk, Inc. UNION is not affiliated with or endorsed by Autodesk.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

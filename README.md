# BIM door: how an AI drives UNION

How an AI drives UNION, a BIM and drafting program, through its MCP door: the guide, every command, the one-line ops, and 449 real drafting jobs with their exact calls and UNION's answers.

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

- The person opens a new project from a template; on the AI door, New is the person's own press.
- `ops_run {"lines":[...]}`: one line per element. Units are millimetres.
- `steps_run {"steps":[...]}`: `<control> · picks <points> · keys <keys> · fields <Dialog: Field=value> · expect <what must show>`.
- UNION's answer to each line, then UNION's count of the model after the last line.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

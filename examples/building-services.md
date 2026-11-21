# UNION examples: Building services

99 drafting jobs, each the request in plain words, the exact calls an AI sends to UNION, and UNION's answer to each, played green on UNION 1.0.0-beta.2.

## 3001. Run a 600 x 250 supply duct 12 m down the corridor at 2700 mm and put four diffusers on it.

- Starts from: a new Mechanical project
- Ends with: One 600 x 250 supply duct, 12 m long at 2700 mm, with four air terminals on it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(12000,0) level=\"Level 1\" width=600 height=250 elevation=2700 system=\"Supply Air\"",
  "op:add terminal at=(1500,0) level=\"Level 1\"",
  "op:add terminal at=(4500,0) level=\"Level 1\"",
  "op:add terminal at=(7500,0) level=\"Level 1\"",
  "op:add terminal at=(10500,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(12000,0) level="Level 1" width=600 height=250 elevation=2700 system="Supply Air"` | green: op:add duct made=duct-4957bd24e7d6c2a7,system-0e862b4bebf0e8ee changed= ms=7 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(1500,0) level="Level 1"` | green: op:add terminal made=terminal-6383ab51522e593f changed=system-0e862b4bebf0e8ee ms=3 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(4500,0) level="Level 1"` | green: op:add terminal made=terminal-3130a3a9843718d0 changed=system-0e862b4bebf0e8ee ms=2 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(7500,0) level="Level 1"` | green: op:add terminal made=terminal-82399d2a322aaa8c changed=system-0e862b4bebf0e8ee ms=3 Check "Air Terminals +1": Air Terminals 2 -> 3 (+1, expected +1) |
| `op:add terminal at=(10500,0) level="Level 1"` | green: op:add terminal made=terminal-6859ede6733fa9ce changed=system-0e862b4bebf0e8ee ms=3 Check "Air Terminals +1": Air Terminals 3 -> 4 (+1, expected +1) |

### The result

The model holds: Air Terminals 4,Duct Systems 1,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3002. Draw a supply duct and a return duct side by side along a 20 m corridor, with a diffuser every 5 m on the supply and a grille every 5 m on the return.

- Starts from: a new Mechanical project
- Ends with: A 20 m supply duct and a 20 m return duct 900 mm apart, each with four air terminals.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(20000,0) level=\"Level 1\" width=500 height=250 elevation=2700 system=\"Supply Air\"",
  "op:add duct from=(0,900) to=(20000,900) level=\"Level 1\" width=500 height=250 elevation=2700 system=\"Return Air\"",
  "op:add terminal at=(2500,0) level=\"Level 1\"",
  "op:add terminal at=(7500,0) level=\"Level 1\"",
  "op:add terminal at=(12500,0) level=\"Level 1\"",
  "op:add terminal at=(17500,0) level=\"Level 1\"",
  "op:add terminal at=(2500,900) level=\"Level 1\"",
  "op:add terminal at=(7500,900) level=\"Level 1\"",
  "op:add terminal at=(12500,900) level=\"Level 1\"",
  "op:add terminal at=(17500,900) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(20000,0) level="Level 1" width=500 height=250 elevation=2700 system="Supply Air"` | green: op:add duct made=duct-72131ac0d3442984,system-e3b047f99252a55b changed= ms=5 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(0,900) to=(20000,900) level="Level 1" width=500 height=250 elevation=2700 system="Return Air"` | green: op:add duct made=duct-c00b7d9668b39844,system-8d3b56f46d476a9a changed= ms=4 Check "Ducts +1 and Duct Systems +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Systems 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(2500,0) level="Level 1"` | green: op:add terminal made=terminal-31bd5214aee48796 changed=system-e3b047f99252a55b ms=2 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(7500,0) level="Level 1"` | green: op:add terminal made=terminal-eb63b4c968fa5ef2 changed=system-e3b047f99252a55b ms=49 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(12500,0) level="Level 1"` | green: op:add terminal made=terminal-d63eae6471c575f3 changed=system-e3b047f99252a55b ms=3 Check "Air Terminals +1": Air Terminals 2 -> 3 (+1, expected +1) |
| `op:add terminal at=(17500,0) level="Level 1"` | green: op:add terminal made=terminal-dbf22b1c3c60dfa5 changed=system-e3b047f99252a55b ms=3 Check "Air Terminals +1": Air Terminals 3 -> 4 (+1, expected +1) |
| `op:add terminal at=(2500,900) level="Level 1"` | green: op:add terminal made=terminal-fd5291676e243b39 changed=system-8d3b56f46d476a9a ms=2 Check "Air Terminals +1": Air Terminals 4 -> 5 (+1, expected +1) |
| `op:add terminal at=(7500,900) level="Level 1"` | green: op:add terminal made=terminal-be1490bd78f0856a changed=system-8d3b56f46d476a9a ms=4 Check "Air Terminals +1": Air Terminals 5 -> 6 (+1, expected +1) |
| `op:add terminal at=(12500,900) level="Level 1"` | green: op:add terminal made=terminal-f58ec15bb6627199 changed=system-8d3b56f46d476a9a ms=3 Check "Air Terminals +1": Air Terminals 6 -> 7 (+1, expected +1) |
| `op:add terminal at=(17500,900) level="Level 1"` | green: op:add terminal made=terminal-7879149f20d26158 changed=system-8d3b56f46d476a9a ms=3 Check "Air Terminals +1": Air Terminals 7 -> 8 (+1, expected +1) |

### The result

The model holds: Air Terminals 8,Duct Systems 2,Ducts 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3003. Put an air handling unit at the end of the corridor and run its supply and return ducts down the corridor between the corridor walls.

- Starts from: a new Mechanical project
- Ends with: Two corridor walls 20 m long, an air handling unit, and a supply and a return duct along the corridor.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,-800) to=(20000,-800) level=\"Level 1\"",
  "op:add wall from=(0,1700) to=(20000,1700) level=\"Level 1\"",
  "op:add equipment at=(-1500,450) level=\"Level 1\" elevation=0",
  "op:add duct from=(0,0) to=(20000,0) level=\"Level 1\" width=500 height=250 elevation=2700 system=\"Supply Air\"",
  "op:add duct from=(0,900) to=(20000,900) level=\"Level 1\" width=500 height=250 elevation=2700 system=\"Return Air\"",
  "op:add terminal at=(10000,0) level=\"Level 1\"",
  "op:add terminal at=(10000,900) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,-800) to=(20000,-800) level="Level 1"` | green: op:add wall made=wall-5d0b1c7bd960e993 changed= ms=73 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(0,1700) to=(20000,1700) level="Level 1"` | green: op:add wall made=wall-a00a88f704669066 changed= ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add equipment at=(-1500,450) level="Level 1" elevation=0` | green: op:add equipment made=equipment-371f491fe37f4d4c changed= ms=3 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add duct from=(0,0) to=(20000,0) level="Level 1" width=500 height=250 elevation=2700 system="Supply Air"` | green: op:add duct made=duct-b3c7c299af687794,system-3754e978c2b3976d changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(0,900) to=(20000,900) level="Level 1" width=500 height=250 elevation=2700 system="Return Air"` | green: op:add duct made=duct-2a8d05c4a250abb4,system-d0d635d3f879ecfb changed= ms=3 Check "Ducts +1 and Duct Systems +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Systems 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(10000,0) level="Level 1"` | green: op:add terminal made=terminal-2964c70f496a43c6 changed=system-3754e978c2b3976d ms=2 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(10000,900) level="Level 1"` | green: op:add terminal made=terminal-c100f09f11103b04 changed=system-d0d635d3f879ecfb ms=2 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |

### The result

The model holds: Air Terminals 2,Duct Systems 2,Ducts 2,Levels 2,Mechanical Equipment 1,Walls 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3004. Run a 300 mm round exhaust duct 9 m from the toilet block to the exhaust fan and put the fan at the end of it.

- Starts from: a new Mechanical project
- Ends with: A 300 mm round exhaust duct 9 m long at 2800 mm with a fan beyond its end.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(9000,0) level=\"Level 1\" diameter=300 elevation=2800 system=\"Exhaust Air\"",
  "op:add equipment at=(9600,0) level=\"Level 1\" elevation=2800"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(9000,0) level="Level 1" diameter=300 elevation=2800 system="Exhaust Air"` | green: op:add duct made=duct-596abffd6effbc21,system-87122f720f1484fa changed= ms=5 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add equipment at=(9600,0) level="Level 1" elevation=2800` | green: op:add equipment made=equipment-e2bb3ef4e4eb023d changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |

### The result

The model holds: Duct Systems 1,Ducts 1,Levels 2,Mechanical Equipment 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3005. Draw a 12 m main supply duct 800 x 300 with two 400 x 250 branches going north at 4 m and 8 m, each ending in a diffuser.

- Starts from: a new Mechanical project
- Ends with: An 800 x 300 main split by two branches, with a diffuser at the end of each branch.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(12000,0) level=\"Level 1\" width=800 height=300 elevation=2700",
  "op:add duct from=(4000,0) to=(4000,5000) level=\"Level 1\" width=400 height=250 elevation=2700",
  "op:add duct from=(8000,0) to=(8000,5000) level=\"Level 1\" width=400 height=250 elevation=2700",
  "op:add terminal at=(4000,4500) level=\"Level 1\"",
  "op:add terminal at=(8000,4500) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(12000,0) level="Level 1" width=800 height=300 elevation=2700` | green: op:add duct made=duct-9655587c3e9da2a5,system-7853c180dcc4c544 changed= ms=7 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(4000,0) to=(4000,5000) level="Level 1" width=400 height=250 elevation=2700` | green: op:add duct made=duct-eaaa828521cdd9ab,duct-9655587c3e9da2a5,duct-9b7e7dd4bb1c59fd,fitting-8d6de4216157ebe5,system-081de6183dd82b75 changed=system-7853c180dcc4c544 ms=3 Check "Ducts +2 and Duct Fittings +1": Ducts 1 -> 3 (+2, expected +2); [green] Duct Fittings 0 -> 1 (+1, expected +1) |
| `op:add duct from=(8000,0) to=(8000,5000) level="Level 1" width=400 height=250 elevation=2700` | green: op:add duct made=duct-3fec3f97ac4e3fa9,duct-9b7e7dd4bb1c59fd,duct-32f1c9153c6b1b6e,fitting-3a7d9affca24287f,system-5772da85079e247f changed=system-081de6183dd82b75 ms=3 Check "Ducts +2 and Duct Fittings +1": Ducts 3 -> 5 (+2, expected +2); [green] Duct Fittings 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(4000,4500) level="Level 1"` | green: op:add terminal made=terminal-b28a1a2746baf46d changed=system-5772da85079e247f ms=3 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(8000,4500) level="Level 1"` | green: op:add terminal made=terminal-de76fc3b7bfbe725 changed=system-5772da85079e247f ms=4 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |

### The result

The model holds: Air Terminals 2,Duct Fittings 2,Duct Systems 1,Ducts 5,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3006. Draw an 18 m supply duct that steps down in size every 6 m: 800 x 300, then 600 x 300, then 400 x 250.

- Starts from: a new Mechanical project
- Ends with: Three joined duct lengths of 800 x 300, 600 x 300 and 400 x 250 in one run.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(6000,0) level=\"Level 1\" width=800 height=300 elevation=2700",
  "op:add duct from=(6000,0) to=(12000,0) level=\"Level 1\" width=600 height=300 elevation=2700",
  "op:add duct from=(12000,0) to=(18000,0) level=\"Level 1\" width=400 height=250 elevation=2700"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(6000,0) level="Level 1" width=800 height=300 elevation=2700` | green: op:add duct made=duct-b5ad47bd4e2d1f15,system-2226e405c5dc2ae8 changed= ms=77 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(6000,0) to=(12000,0) level="Level 1" width=600 height=300 elevation=2700` | green: op:add duct made=duct-aef567e1608f36eb,fitting-5d09dce55ef81f97,system-d8e69f1092e48c8a changed=system-2226e405c5dc2ae8 ms=3 Check "Ducts +1": Ducts 1 -> 2 (+1, expected +1) |
| `op:add duct from=(12000,0) to=(18000,0) level="Level 1" width=400 height=250 elevation=2700` | green: op:add duct made=duct-32f6511e9e63899d,fitting-c35551d3ff80b020,system-ab8c9ca05fb49041 changed=system-d8e69f1092e48c8a ms=85 Check "Ducts +1": Ducts 2 -> 3 (+1, expected +1) |

### The result

The model holds: Duct Fittings 2,Duct Systems 1,Ducts 3,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3007. Run a 500 x 250 supply duct 8 m east, turn it north for 5 m with an elbow, and end it with a diffuser.

- Starts from: a new Mechanical project
- Ends with: An L-shaped 500 x 250 duct with an elbow at the turn and a diffuser near its end.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(8000,0) level=\"Level 1\" width=500 height=250 elevation=2700",
  "op:add duct from=(8000,0) to=(8000,5000) level=\"Level 1\" width=500 height=250 elevation=2700",
  "op:add terminal at=(8000,4500) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(8000,0) level="Level 1" width=500 height=250 elevation=2700` | green: op:add duct made=duct-adc49d323603a483,system-8910af67f928d3ba changed= ms=6 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(8000,0) to=(8000,5000) level="Level 1" width=500 height=250 elevation=2700` | green: op:add duct made=duct-7d6b0dca0159398c,fitting-a27c50ad412943c6,system-5c04542264f91c50 changed=system-8910af67f928d3ba ms=4 Check "Ducts +1 and Duct Fittings +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Fittings 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(8000,4500) level="Level 1"` | green: op:add terminal made=terminal-ae32d8ba5daa4dde changed=system-5c04542264f91c50 ms=5 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |

### The result

The model holds: Air Terminals 1,Duct Fittings 1,Duct Systems 1,Ducts 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3008. Draw a 10 m return air duct 600 x 300 at 2600 mm and put three return grilles on it.

- Starts from: a new Mechanical project
- Ends with: A return air duct with three air terminals on it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(10000,0) level=\"Level 1\" width=600 height=300 elevation=2600 system=\"Return Air\"",
  "op:add terminal at=(2000,0) level=\"Level 1\"",
  "op:add terminal at=(5000,0) level=\"Level 1\"",
  "op:add terminal at=(8000,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(10000,0) level="Level 1" width=600 height=300 elevation=2600 system="Return Air"` | green: op:add duct made=duct-0d824943661efd34,system-3f156862fe9e8536 changed= ms=6 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(2000,0) level="Level 1"` | green: op:add terminal made=terminal-7d2beb4ef9e76dd4 changed=system-3f156862fe9e8536 ms=3 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(5000,0) level="Level 1"` | green: op:add terminal made=terminal-6643bca142b96fd3 changed=system-3f156862fe9e8536 ms=391 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(8000,0) level="Level 1"` | green: op:add terminal made=terminal-3cdc4d280822e9e1 changed=system-3f156862fe9e8536 ms=2 Check "Air Terminals +1": Air Terminals 2 -> 3 (+1, expected +1) |

### The result

The model holds: Air Terminals 3,Duct Systems 1,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3009. Run a 500 x 400 kitchen exhaust duct 6 m long at 3000 mm and put the exhaust fan at its end.

- Starts from: a new Mechanical project
- Ends with: A 500 x 400 exhaust duct 6 m long at 3000 mm and a fan at its end.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(6000,0) level=\"Level 1\" width=500 height=400 elevation=3000 system=\"Exhaust Air\"",
  "op:add equipment at=(6600,0) level=\"Level 1\" elevation=3000"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(6000,0) level="Level 1" width=500 height=400 elevation=3000 system="Exhaust Air"` | green: op:add duct made=duct-2a7a3ac63d513c87,system-880287e128b0fc3c changed= ms=6 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add equipment at=(6600,0) level="Level 1" elevation=3000` | green: op:add equipment made=equipment-437e8084b53ebef0 changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |

### The result

The model holds: Duct Systems 1,Ducts 1,Levels 2,Mechanical Equipment 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3010. Run a 500 x 250 supply duct along the same line on both floors, with a diffuser on each.

- Starts from: a new Mechanical project
- Ends with: A supply duct and a diffuser on Level 1 and the same on Level 2.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(10000,0) level=\"Level 1\" width=500 height=250 elevation=2700",
  "op:add terminal at=(5000,0) level=\"Level 1\"",
  "op:add duct from=(0,0) to=(10000,0) level=\"Level 2\" width=500 height=250 elevation=2700",
  "op:add terminal at=(5000,0) level=\"Level 2\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(10000,0) level="Level 1" width=500 height=250 elevation=2700` | green: op:add duct made=duct-34c36764c706ea2f,system-6a831a00bbebbfd0 changed= ms=5 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(5000,0) level="Level 1"` | green: op:add terminal made=terminal-f77f6130940de081 changed=system-6a831a00bbebbfd0 ms=3 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add duct from=(0,0) to=(10000,0) level="Level 2" width=500 height=250 elevation=2700` | green: op:add duct made=duct-2b19b7d4c6f08f6b,system-04c2da43ca932eae changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Systems 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(5000,0) level="Level 2"` | green: op:add terminal made=terminal-be26254fe04b4159 changed=system-04c2da43ca932eae ms=2 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |

### The result

The model holds: Air Terminals 2,Duct Systems 2,Ducts 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3011. Lay out the supply air for an office floor: a 12 m main with four branches at 2 m, 5 m, 8 m and 11 m, each ending in a diffuser.

- Starts from: a new Mechanical project
- Ends with: A 12 m supply main with four 4 m branches and four diffusers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(12000,0) level=\"Level 1\" width=700 height=300 elevation=2700 system=\"Supply Air\"",
  "op:add duct from=(2000,0) to=(2000,4000) level=\"Level 1\" width=300 height=200 elevation=2700",
  "op:add duct from=(5000,0) to=(5000,4000) level=\"Level 1\" width=300 height=200 elevation=2700",
  "op:add duct from=(8000,0) to=(8000,4000) level=\"Level 1\" width=300 height=200 elevation=2700",
  "op:add duct from=(11000,0) to=(11000,4000) level=\"Level 1\" width=300 height=200 elevation=2700",
  "op:add terminal at=(2000,3500) level=\"Level 1\"",
  "op:add terminal at=(5000,3500) level=\"Level 1\"",
  "op:add terminal at=(8000,3500) level=\"Level 1\"",
  "op:add terminal at=(11000,3500) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(12000,0) level="Level 1" width=700 height=300 elevation=2700 system="Supply Air"` | green: op:add duct made=duct-de7a8c003b1b8a15,system-ccd2fe711aa14de9 changed= ms=6 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(2000,0) to=(2000,4000) level="Level 1" width=300 height=200 elevation=2700` | green: op:add duct made=duct-3cc28f41b81370d9,duct-de7a8c003b1b8a15,duct-90099201a140b6a7,fitting-ef2685d5d0354958,system-980b22820ceef71e changed=system-ccd2fe711aa14de9 ms=4 Check "Ducts +2 and Duct Fittings +1": Ducts 1 -> 3 (+2, expected +2); [green] Duct Fittings 0 -> 1 (+1, expected +1) |
| `op:add duct from=(5000,0) to=(5000,4000) level="Level 1" width=300 height=200 elevation=2700` | green: op:add duct made=duct-2abf18870275c3b2,duct-90099201a140b6a7,duct-d591c76fc4a2b1f8,fitting-0d8e21e9544424aa,system-db90da9ab321b055 changed=system-980b22820ceef71e ms=3 Check "Ducts +2 and Duct Fittings +1": Ducts 3 -> 5 (+2, expected +2); [green] Duct Fittings 1 -> 2 (+1, expected +1) |
| `op:add duct from=(8000,0) to=(8000,4000) level="Level 1" width=300 height=200 elevation=2700` | green: op:add duct made=duct-0259e1faa67d0e60,duct-d591c76fc4a2b1f8,duct-7230112b263a2275,fitting-8e98cfc1163ad33c,system-fbdf9d17ab6c4aa6 changed=system-db90da9ab321b055 ms=4 Check "Ducts +2 and Duct Fittings +1": Ducts 5 -> 7 (+2, expected +2); [green] Duct Fittings 2 -> 3 (+1, expected +1) |
| `op:add duct from=(11000,0) to=(11000,4000) level="Level 1" width=300 height=200 elevation=2700` | green: op:add duct made=duct-56133617c0943eb8,duct-7230112b263a2275,duct-0d965c7cb975b1c8,fitting-1aa6c7167124cd61,system-570f2e881f6a66ca changed=system-fbdf9d17ab6c4aa6 ms=22 Check "Ducts +2 and Duct Fittings +1": Ducts 7 -> 9 (+2, expected +2); [green] Duct Fittings 3 -> 4 (+1, expected +1) |
| `op:add terminal at=(2000,3500) level="Level 1"` | green: op:add terminal made=terminal-fe79340afa84a4a3 changed=system-570f2e881f6a66ca ms=4 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(5000,3500) level="Level 1"` | green: op:add terminal made=terminal-8735ae038fa900ad changed=system-570f2e881f6a66ca ms=3 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(8000,3500) level="Level 1"` | green: op:add terminal made=terminal-abdcce65030a2b44 changed=system-570f2e881f6a66ca ms=3 Check "Air Terminals +1": Air Terminals 2 -> 3 (+1, expected +1) |
| `op:add terminal at=(11000,3500) level="Level 1"` | green: op:add terminal made=terminal-d2d2af37507a87dc changed=system-570f2e881f6a66ca ms=49 Check "Air Terminals +1": Air Terminals 3 -> 4 (+1, expected +1) |

### The result

The model holds: Air Terminals 4,Duct Fittings 4,Duct Systems 1,Ducts 9,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3012. Draw an 8 x 6 m plant room with two air handling units in it and run a supply and a return duct out of the east side.

- Starts from: a new Mechanical project
- Ends with: Four plant room walls, two air handling units, and a supply and a return duct leaving east.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=\"Level 1\"",
  "op:add wall from=(8000,0) to=(8000,6000) level=\"Level 1\"",
  "op:add wall from=(8000,6000) to=(0,6000) level=\"Level 1\"",
  "op:add wall from=(0,6000) to=(0,0) level=\"Level 1\"",
  "op:add equipment at=(2000,3000) level=\"Level 1\" elevation=0",
  "op:add equipment at=(5000,3000) level=\"Level 1\" elevation=0",
  "op:add duct from=(6200,2500) to=(14000,2500) level=\"Level 1\" width=600 height=300 elevation=2700 system=\"Supply Air\"",
  "op:add duct from=(6200,3500) to=(14000,3500) level=\"Level 1\" width=600 height=300 elevation=2700 system=\"Return Air\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level="Level 1"` | green: op:add wall made=wall-4ae9fb0a97f1506e changed= ms=5 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level="Level 1"` | green: op:add wall made=wall-c8bdb4602decf7a4 changed=wall-4ae9fb0a97f1506e ms=215 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level="Level 1"` | green: op:add wall made=wall-6ffc12802dc4a2ea changed=wall-c8bdb4602decf7a4 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level="Level 1"` | green: op:add wall made=wall-0e8f9add3d2361fe changed=wall-6ffc12802dc4a2ea,wall-4ae9fb0a97f1506e ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add equipment at=(2000,3000) level="Level 1" elevation=0` | green: op:add equipment made=equipment-ce8ee0ee8e8f07f9 changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add equipment at=(5000,3000) level="Level 1" elevation=0` | green: op:add equipment made=equipment-657d2be683c5d16c changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 1 -> 2 (+1, expected +1) |
| `op:add duct from=(6200,2500) to=(14000,2500) level="Level 1" width=600 height=300 elevation=2700 system="Supply Air"` | green: op:add duct made=duct-0a1a821bcd755b24,system-8b64522a54198271 changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(6200,3500) to=(14000,3500) level="Level 1" width=600 height=300 elevation=2700 system="Return Air"` | green: op:add duct made=duct-cfc0a72c546faae9,system-c51b4837cce83418 changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Systems 1 -> 2 (+1, expected +1) |

### The result

The model holds: Duct Systems 2,Ducts 2,Levels 2,Mechanical Equipment 2,Walls 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3013. Lay a supply duct, a return duct and a 300 mm round exhaust duct side by side along a 15 m corridor, each on its own system.

- Starts from: a new Mechanical project
- Ends with: Three parallel ducts, supply, return and exhaust, each in its own duct system.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(15000,0) level=\"Level 1\" width=600 height=300 elevation=2800 system=\"Supply Air\"",
  "op:add duct from=(0,1000) to=(15000,1000) level=\"Level 1\" width=600 height=300 elevation=2800 system=\"Return Air\"",
  "op:add duct from=(0,2000) to=(15000,2000) level=\"Level 1\" diameter=300 elevation=2600 system=\"Exhaust Air\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(15000,0) level="Level 1" width=600 height=300 elevation=2800 system="Supply Air"` | green: op:add duct made=duct-392f3b735aa079b0,system-b8d9c42176c22974 changed= ms=4 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(0,1000) to=(15000,1000) level="Level 1" width=600 height=300 elevation=2800 system="Return Air"` | green: op:add duct made=duct-3c3bb2492dd8878a,system-ae449b924fe28631 changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Systems 1 -> 2 (+1, expected +1) |
| `op:add duct from=(0,2000) to=(15000,2000) level="Level 1" diameter=300 elevation=2600 system="Exhaust Air"` | green: op:add duct made=duct-b4cde0120928b488,system-af9507dac0fb7e31 changed= ms=2 Check "Ducts +1 and Duct Systems = 3": Ducts 2 -> 3 (+1, expected +1); [green] Duct Systems = 3 (expected 3) |

### The result

The model holds: Duct Systems 3,Ducts 3,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3014. Draw a 400 x 200 supply duct, take it back, then bring it back again.

- Starts from: a new Mechanical project
- Ends with: One 400 x 200 supply duct, drawn, undone and redone.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(6000,0) level=\"Level 1\" width=400 height=200 elevation=2600"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(6000,0) level="Level 1" width=400 height=200 elevation=2600` | green: op:add duct made=duct-c0bf3a26134df675,system-2da27d7df7ef1e4d changed= ms=4 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "qa:Undo · picks — · keys — · fields — · expect Ducts -1 and Duct Systems -1",
  "qa:Redo · picks — · keys — · fields — · expect Ducts +1 and Duct Systems +1"
]}
```

| Line | UNION answered |
|---|---|
| `qa:Undo · picks — · keys — · fields — · expect Ducts -1 and Duct Systems -1` | green: QToolButton pressed; a command ran Check "Ducts -1 and Duct Systems -1": Ducts 1 -> 0 (-1, expected -1); [green] Duct Systems 1 -> 0 (-1, expected -1) |
| `qa:Redo · picks — · keys — · fields — · expect Ducts +1 and Duct Systems +1` | green: QToolButton pressed; a command ran Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |

### The result

The model holds: Duct Systems 1,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3015. Draw a 6 m supply duct with three diffusers, then copy the whole run 3 m north for the next room.

- Starts from: a new Mechanical project
- Ends with: Two identical 6 m supply ducts 3 m apart, each carrying three diffusers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(6000,0) level=\"Level 1\" width=500 height=250 elevation=2700",
  "op:add terminal at=(1000,0) level=\"Level 1\"",
  "op:add terminal at=(3000,0) level=\"Level 1\"",
  "op:add terminal at=(5000,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(6000,0) level="Level 1" width=500 height=250 elevation=2700` | green: op:add duct made=duct-c6fed8a239e5c95a,system-861bdb4281afa737 changed= ms=6 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(1000,0) level="Level 1"` | green: op:add terminal made=terminal-b1a2ea749cc96814 changed=system-861bdb4281afa737 ms=2 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(3000,0) level="Level 1"` | green: op:add terminal made=terminal-c6ea4d9c3a481851 changed=system-861bdb4281afa737 ms=3 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(5000,0) level="Level 1"` | green: op:add terminal made=terminal-08594fb457bdbf97 changed=system-861bdb4281afa737 ms=3 Check "Air Terminals +1": Air Terminals 2 -> 3 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (5500,0) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Copy · picks (0,0) (0,3000) · keys Return · fields — · expect Ducts +1 and Air Terminals +3"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (5500,0) · keys — · fields — · expect 1 selected` | green: select: (5500,0) mm at px (750.4,427.0) on the plan view; picked 'duct-c6fed8a239e5c95a'; selected 0 -> 1 [duct-c6fed8a239e5c95a] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (duct-c6fed8a239e5c95a) (expected exactly 1) |
| `ribbon:Modify:Copy · picks (0,0) (0,3000) · keys Return · fields — · expect Ducts +1 and Air Terminals +3` | green: pressed 'Copy' on Modify's Modify panel (through its fold): the tool 'Copy' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (0,3000) mm at px (648.0,371.2) on the plan view \| presses to the tool 2 (the tool ended on the press), selection changed \| keys: Return (no tool -> tool Copy, nothing standing to end) Check "Ducts +1 and Air Terminals +3": Ducts 1 -> 2 (+1, expected +1); [green] Air Terminals 3 -> 6 (+3, expected +3) |

### The result

The model holds: Air Terminals 6,Duct Systems 1,Ducts 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3016. Draw two supply ducts 2 m apart, then delete the lower one because it was drawn in the wrong place.

- Starts from: a new Mechanical project
- Ends with: One 6 m supply duct left at y = 2000.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(6000,0) level=\"Level 1\" width=500 height=250 elevation=2700",
  "op:add duct from=(0,2000) to=(6000,2000) level=\"Level 1\" width=500 height=250 elevation=2700"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(6000,0) level="Level 1" width=500 height=250 elevation=2700` | green: op:add duct made=duct-28343ea6b934d231,system-7b94ab16c274bbb5 changed= ms=5 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(0,2000) to=(6000,2000) level="Level 1" width=500 height=250 elevation=2700` | green: op:add duct made=duct-5734324809b01080,system-eb0b4267729ee68b changed= ms=4 Check "Ducts +1 and Duct Systems +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Systems 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (3000,0) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Ducts -1"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (3000,0) · keys — · fields — · expect 1 selected` | green: select: (3000,0) mm at px (703.8,427.0) on the plan view; picked 'duct-28343ea6b934d231'; selected 0 -> 1 [duct-28343ea6b934d231] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (duct-28343ea6b934d231) (expected exactly 1) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Ducts -1` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Ducts -1": Ducts 2 -> 1 (-1, expected -1) |

### The result

The model holds: Duct Systems 1,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3017. Draw a 5 m branch duct 400 x 250 and place a duct accessory in it at 2 m.

- Starts from: a new Mechanical project
- Ends with: A 400 x 250 branch duct split by a duct accessory at 2 m.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(5000,0) level=\"Level 1\" width=400 height=250 elevation=2700"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(5000,0) level="Level 1" width=400 height=250 elevation=2700` | green: op:add duct made=duct-eb0cf589bea77cd8,system-27e1dc4707411a8f changed= ms=77 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Duct Accessory · picks (2000,0) · keys Escape Escape · fields — · expect Duct Accessories +1 and Ducts +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Duct Accessory · picks (2000,0) · keys Escape Escape · fields — · expect Duct Accessories +1 and Ducts +1` | green: pressed 'Duct Accessory' on Systems's HVAC panel: the tool 'Duct Accessory' stands \| picks: (2000,0) mm at px (685.2,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Duct Accessory -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Duct Accessories +1 and Ducts +1": Duct Accessories 0 -> 1 (+1, expected +1); [green] Ducts 1 -> 2 (+1, expected +1) |

### The result

The model holds: Duct Accessories 1,Duct Systems 1,Ducts 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3018. Run a 6 m supply duct and connect a flexible duct from its end to a diffuser 1.5 m away.

- Starts from: a new Mechanical project
- Ends with: A 6 m supply duct, a flexible duct leaving its end and a diffuser at the flexible duct's end.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(6000,0) level=\"Level 1\" width=400 height=250 elevation=2700"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(6000,0) level="Level 1" width=400 height=250 elevation=2700` | green: op:add duct made=duct-8528c4e1441c136f,system-1366c70debcc2350 changed= ms=5 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Flex Duct · picks (6000,0) (7500,1200) · keys Escape Escape · fields — · expect Flex Ducts +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Flex Duct · picks (6000,0) (7500,1200) · keys Escape Escape · fields — · expect Flex Ducts +1` | green: pressed 'Flex Duct' on Systems's HVAC panel: the tool 'Flex Duct' stands \| picks: (6000,0) mm at px (759.7,427.0) on the plan view \| (7500,1200) mm at px (787.6,404.7) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Flex Duct -> tool Flex Duct, 'Flex Duct' still stands (the key went to union_shell::Viewport)); Escape (tool Flex Duct -> no tool) Check "Flex Ducts +1": Flex Ducts 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add terminal at=(7500,1200) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add terminal at=(7500,1200) level="Level 1"` | green: op:add terminal made=terminal-86857063da2d9bd7 changed= ms=2 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |

### The result

The model holds: Air Terminals 1,Duct Systems 2,Ducts 1,Flex Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3019. Draw three supply ducts of different sizes and make a duct schedule listing mark, type, width and height.

- Starts from: a new Mechanical project
- Ends with: Three ducts of 800 x 300, 500 x 250 and 300 x 200 and a Duct Schedule listing them.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(8000,0) level=\"Level 1\" width=800 height=300 elevation=2700",
  "op:add duct from=(0,1500) to=(8000,1500) level=\"Level 1\" width=500 height=250 elevation=2700",
  "op:add duct from=(0,3000) to=(8000,3000) level=\"Level 1\" width=300 height=200 elevation=2700",
  "op:add schedule category=Ducts fields=Mark,Type,Width,Height name=\"Duct Schedule\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(8000,0) level="Level 1" width=800 height=300 elevation=2700` | green: op:add duct made=duct-56c559faf255c2ef,system-17365d1be7785abd changed= ms=59 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(0,1500) to=(8000,1500) level="Level 1" width=500 height=250 elevation=2700` | green: op:add duct made=duct-ceffa64951cc3a74,system-3aff091e8d27ed95 changed= ms=1 Check "Ducts +1 and Duct Systems +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Systems 1 -> 2 (+1, expected +1) |
| `op:add duct from=(0,3000) to=(8000,3000) level="Level 1" width=300 height=200 elevation=2700` | green: op:add duct made=duct-575453fccbbb704b,system-88dab161cfc9a2e2 changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 2 -> 3 (+1, expected +1); [green] Duct Systems 2 -> 3 (+1, expected +1) |
| `op:add schedule category=Ducts fields=Mark,Type,Width,Height name="Duct Schedule"` | green: op:add schedule made=eb6d307c03364d13b444322625356528 changed= ms=70 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Duct Systems 3,Ducts 3,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 3020. Put four diffusers on a supply duct and make a schedule of the air terminals by type with a count.

- Starts from: a new Mechanical project
- Ends with: A supply duct with four diffusers and a schedule of the air terminals by type.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(12000,0) level=\"Level 1\" width=600 height=250 elevation=2700",
  "op:add terminal at=(2000,0) level=\"Level 1\"",
  "op:add terminal at=(5000,0) level=\"Level 1\"",
  "op:add terminal at=(8000,0) level=\"Level 1\"",
  "op:add terminal at=(11000,0) level=\"Level 1\"",
  "op:add schedule category=\"Air Terminals\" fields=Type,Count name=\"Diffuser Schedule\" itemize=no"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(12000,0) level="Level 1" width=600 height=250 elevation=2700` | green: op:add duct made=duct-8ea62d4c35d6e372,system-5b9ff2d1d031ea0a changed= ms=5 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(2000,0) level="Level 1"` | green: op:add terminal made=terminal-223a5d0cb75abc1e changed=system-5b9ff2d1d031ea0a ms=2 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(5000,0) level="Level 1"` | green: op:add terminal made=terminal-dcbbdb5b505b0022 changed=system-5b9ff2d1d031ea0a ms=2 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(8000,0) level="Level 1"` | green: op:add terminal made=terminal-d4536bfc1f1a75ba changed=system-5b9ff2d1d031ea0a ms=2 Check "Air Terminals +1": Air Terminals 2 -> 3 (+1, expected +1) |
| `op:add terminal at=(11000,0) level="Level 1"` | green: op:add terminal made=terminal-d7125d0467684eb3 changed=system-5b9ff2d1d031ea0a ms=2 Check "Air Terminals +1": Air Terminals 3 -> 4 (+1, expected +1) |
| `op:add schedule category="Air Terminals" fields=Type,Count name="Diffuser Schedule" itemize=no` | green: op:add schedule made=5c715ff19a42481182b8e9ddaad689ba changed= ms=172 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Air Terminals 4,Duct Systems 1,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 3021. Place an air handling unit, a fan coil unit and an exhaust fan and schedule the mechanical equipment with mark and type.

- Starts from: a new Mechanical project
- Ends with: Three pieces of mechanical equipment and an Equipment Schedule listing them.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add equipment at=(0,0) level=\"Level 1\" elevation=0",
  "op:add equipment at=(3000,0) level=\"Level 1\" elevation=0",
  "op:add equipment at=(6000,0) level=\"Level 1\" elevation=2800",
  "op:add schedule category=\"Mechanical Equipment\" fields=Mark,Type name=\"Equipment Schedule\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add equipment at=(0,0) level="Level 1" elevation=0` | green: op:add equipment made=equipment-a8840c1a233aecac changed= ms=4 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add equipment at=(3000,0) level="Level 1" elevation=0` | green: op:add equipment made=equipment-2e3b0c966083e860 changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 1 -> 2 (+1, expected +1) |
| `op:add equipment at=(6000,0) level="Level 1" elevation=2800` | green: op:add equipment made=equipment-9c2c7e61f6c237e2 changed= ms=1 Check "Mechanical Equipment +1": Mechanical Equipment 2 -> 3 (+1, expected +1) |
| `op:add schedule category="Mechanical Equipment" fields=Mark,Type name="Equipment Schedule"` | green: op:add schedule made=ba616b507be2462caf78db5ac08af5fe changed= ms=296 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Mechanical Equipment 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 3022. Show the supply and the return duct on the plan and drop a duct legend beside them.

- Starts from: a new Mechanical project
- Ends with: A supply duct, a return duct and a duct legend on the plan.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(8000,0) level=\"Level 1\" width=500 height=250 elevation=2700 system=\"Supply Air\"",
  "op:add duct from=(0,1200) to=(8000,1200) level=\"Level 1\" width=500 height=250 elevation=2700 system=\"Return Air\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(8000,0) level="Level 1" width=500 height=250 elevation=2700 system="Supply Air"` | green: op:add duct made=duct-6286a00ade4fe62c,system-793ceb588c9184e6 changed= ms=5 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(0,1200) to=(8000,1200) level="Level 1" width=500 height=250 elevation=2700 system="Return Air"` | green: op:add duct made=duct-6aa915f8fbf62b37,system-d8737b8f4f34ec02 changed= ms=3 Check "Ducts +1 and Duct Systems +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Systems 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Duct Legend · picks (10000,0) · keys Escape Escape · fields — · expect Duct Legends +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Duct Legend · picks (10000,0) · keys Escape Escape · fields — · expect Duct Legends +1` | green: pressed 'Duct Legend' on Systems's Check Systems panel (through its fold): the tool 'Duct Legend' stands \| picks: (10000,0) mm at px (834.1,427.0) on the plan view \| presses to the tool 1 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Duct Legends +1": Duct Legends 0 -> 1 (+1, expected +1) |

### The result

The model holds: Duct Legends 1,Duct Systems 2,Ducts 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3023. Draw a supply duct with two diffusers and run the duct system check.

- Starts from: a new Mechanical project
- Ends with: A supply duct with two diffusers and the Check Duct Systems report run on it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(8000,0) level=\"Level 1\" width=500 height=250 elevation=2700",
  "op:add terminal at=(2500,0) level=\"Level 1\"",
  "op:add terminal at=(5500,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(8000,0) level="Level 1" width=500 height=250 elevation=2700` | green: op:add duct made=duct-c16738a1deef4f99,system-065170421694d4f4 changed= ms=7 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(2500,0) level="Level 1"` | green: op:add terminal made=terminal-7e351121f04322b7 changed=system-065170421694d4f4 ms=4 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(5500,0) level="Level 1"` | green: op:add terminal made=terminal-7ec3d5b6321de13a changed=system-065170421694d4f4 ms=3 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Check Duct Systems · picks — · keys — · fields — · expect status: Check Duct Systems"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Check Duct Systems · picks — · keys — · fields — · expect status: Check Duct Systems` | green: pressed 'Check Duct Systems' on Systems's Check Systems panel (through its fold) (the window's first paint at 31 ms in QDialog#servicesCheckReport:Check Duct Systems): the command 'Check Duct Systems' ran; status 'Check Duct Systems: 2 found -- selected' Check "status: Check Duct Systems": status 'Check Duct Systems' read; now 'Check Duct Systems: 2 found -- selected', since the step began 'Check Duct Systems: 2 found -- selected' |

### The result

The model holds: Air Terminals 2,Duct Systems 1,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3024. Use the Duct tool to draw a 500 x 250 supply duct at 2700 mm and a diffuser on it.

- Starts from: a new Mechanical project
- Ends with: A 500 x 250 supply duct at 2700 mm and a diffuser on it, drawn with the Duct tool.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Duct · picks (1000,1000) (7000,1000) · keys Escape Escape · fields Options Strip: Width=500; Height=250; Middle Elevation=2700; System Type=Supply Air · expect Ducts +1 and Duct Systems +1",
  "ribbon:Systems:Air Terminal · picks (4000,1000) · keys Escape Escape · fields — · expect Air Terminals +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Duct · picks (1000,1000) (7000,1000) · keys Escape Escape · fields Options Strip: Width=500; Height=250; Middle Elevation=2700; System Type=Supply Air · expect Ducts +1 and Duct Systems +1` | green: pressed 'Duct' on Systems's HVAC panel: the tool 'Duct' stands \| fields: Width=500 reads '500 mm'; Height=250 reads '250 mm'; Middle Elevation=2700 reads '2700 mm'; System Type=Supply Air reads 'Supply Air' \| picks: (1000,1000) mm at px (666.6,408.4) on the plan view \| (7000,1000) mm at px (778.3,408.4) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Duct -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Air Terminal · picks (4000,1000) · keys Escape Escape · fields — · expect Air Terminals +1` | green: pressed 'Air Terminal' on Systems's HVAC panel: the command 'Air Terminal' ran; status 'Click a face to place the air terminal' \| picks: (4000,1000) mm at px (722.4,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Diffuser -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |

### The result

The model holds: Air Terminals 1,Duct Systems 1,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3025. Draw a supply duct and a return duct with the Duct tool, 2 m apart, each with a diffuser.

- Starts from: a new Mechanical project
- Ends with: A supply duct and a return duct, 2 m apart, with an air terminal on each.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Duct · picks (1000,1000) (6000,1000) · keys Escape Escape · fields Options Strip: Width=400; Height=200; Middle Elevation=2700; System Type=Supply Air · expect Ducts +1 and Duct Systems +1",
  "ribbon:Systems:Air Terminal · picks (3500,1000) · keys Escape Escape · fields — · expect Air Terminals +1",
  "ribbon:Systems:Duct · picks (1000,3000) (6000,3000) · keys Escape Escape · fields Options Strip: Width=400; Height=200; Middle Elevation=2700; System Type=Return Air · expect Ducts +1 and Duct Systems +1",
  "ribbon:Systems:Air Terminal · picks (3500,3000) · keys Escape Escape · fields — · expect Air Terminals +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Duct · picks (1000,1000) (6000,1000) · keys Escape Escape · fields Options Strip: Width=400; Height=200; Middle Elevation=2700; System Type=Supply Air · expect Ducts +1 and Duct Systems +1` | green: pressed 'Duct' on Systems's HVAC panel: the tool 'Duct' stands \| fields: Width=400 reads '400 mm'; Height=200 reads '200 mm'; Middle Elevation=2700 reads '2700 mm'; System Type=Supply Air reads 'Supply Air' \| picks: (1000,1000) mm at px (666.6,408.4) on the plan view \| (6000,1000) mm at px (759.7,408.4) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Duct -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Air Terminal · picks (3500,1000) · keys Escape Escape · fields — · expect Air Terminals +1` | green: pressed 'Air Terminal' on Systems's HVAC panel: the command 'Air Terminal' ran; status 'Click a face to place the air terminal' \| picks: (3500,1000) mm at px (713.1,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Diffuser -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Duct · picks (1000,3000) (6000,3000) · keys Escape Escape · fields Options Strip: Width=400; Height=200; Middle Elevation=2700; System Type=Return Air · expect Ducts +1 and Duct Systems +1` | green: pressed 'Duct' on Systems's HVAC panel: the tool 'Duct' stands \| fields: Width=400 reads '400 mm'; Height=200 reads '200 mm'; Middle Elevation=2700 reads '2700 mm'; System Type=Return Air reads 'Return Air' \| picks: (1000,3000) mm at px (666.6,371.2) on the plan view \| (6000,3000) mm at px (759.7,371.2) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Duct -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Ducts +1 and Duct Systems +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Systems 1 -> 2 (+1, expected +1) |
| `ribbon:Systems:Air Terminal · picks (3500,3000) · keys Escape Escape · fields — · expect Air Terminals +1` | green: pressed 'Air Terminal' on Systems's HVAC panel: the command 'Air Terminal' ran; status 'Click a face to place the air terminal' \| picks: (3500,3000) mm at px (713.1,371.2) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Diffuser -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |

### The result

The model holds: Air Terminals 2,Duct Systems 2,Ducts 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3026. Set two air handling units on the roof plant deck and run a 600 x 300 exhaust duct between them.

- Starts from: a new Mechanical project
- Ends with: Two pieces of mechanical equipment and an exhaust duct, all on Level 2.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add equipment at=(0,0) level=\"Level 2\" elevation=0",
  "op:add equipment at=(8000,0) level=\"Level 2\" elevation=0",
  "op:add duct from=(1200,0) to=(6800,0) level=\"Level 2\" width=600 height=300 elevation=1200 system=\"Exhaust Air\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add equipment at=(0,0) level="Level 2" elevation=0` | green: op:add equipment made=equipment-f822a570822f71ff changed= ms=5 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add equipment at=(8000,0) level="Level 2" elevation=0` | green: op:add equipment made=equipment-211cd0b68b5741f5 changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 1 -> 2 (+1, expected +1) |
| `op:add duct from=(1200,0) to=(6800,0) level="Level 2" width=600 height=300 elevation=1200 system="Exhaust Air"` | green: op:add duct made=duct-bd5efd4e1b3c1cf4,system-0dbc81647919ce10 changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |

### The result

The model holds: Duct Systems 1,Ducts 1,Levels 2,Mechanical Equipment 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3027. Feed two corridors from two air handling units: each unit gets its own 500 x 250 supply duct, 10 m long, with a diffuser in the middle.

- Starts from: a new Mechanical project
- Ends with: Two air handling units, each with a supply duct 10 m long and one diffuser.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add equipment at=(-1500,0) level=\"Level 1\" elevation=0",
  "op:add equipment at=(-1500,6000) level=\"Level 1\" elevation=0",
  "op:add duct from=(0,0) to=(10000,0) level=\"Level 1\" width=500 height=250 elevation=2700",
  "op:add duct from=(0,6000) to=(10000,6000) level=\"Level 1\" width=500 height=250 elevation=2700",
  "op:add terminal at=(5000,0) level=\"Level 1\"",
  "op:add terminal at=(5000,6000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add equipment at=(-1500,0) level="Level 1" elevation=0` | green: op:add equipment made=equipment-8aec808643e555cc changed= ms=4 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add equipment at=(-1500,6000) level="Level 1" elevation=0` | green: op:add equipment made=equipment-bf2606c895a656be changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 1 -> 2 (+1, expected +1) |
| `op:add duct from=(0,0) to=(10000,0) level="Level 1" width=500 height=250 elevation=2700` | green: op:add duct made=duct-07f47496804819fb,system-acb232f4849499d7 changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(0,6000) to=(10000,6000) level="Level 1" width=500 height=250 elevation=2700` | green: op:add duct made=duct-ff62821ee2e752ce,system-bf9d4d17eb8388d0 changed= ms=3 Check "Ducts +1 and Duct Systems +1": Ducts 1 -> 2 (+1, expected +1); [green] Duct Systems 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(5000,0) level="Level 1"` | green: op:add terminal made=terminal-ae34d6934888bde6 changed=system-acb232f4849499d7 ms=2 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(5000,6000) level="Level 1"` | green: op:add terminal made=terminal-6690e4746cb9bba3 changed=system-bf9d4d17eb8388d0 ms=2 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |

### The result

The model holds: Air Terminals 2,Duct Systems 2,Ducts 2,Levels 2,Mechanical Equipment 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3028. Run a 400 mm round extract main 9 m long and take three 150 mm round branches off it at 2, 5 and 8 m.

- Starts from: a new Mechanical project
- Ends with: A 400 mm round extract main with three 150 mm round branches.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(9000,0) level=\"Level 1\" diameter=400 elevation=2800 system=\"Exhaust Air\"",
  "op:add duct from=(2000,0) to=(2000,2500) level=\"Level 1\" diameter=150 elevation=2800 system=\"Exhaust Air\"",
  "op:add duct from=(5000,0) to=(5000,2500) level=\"Level 1\" diameter=150 elevation=2800 system=\"Exhaust Air\"",
  "op:add duct from=(8000,0) to=(8000,2500) level=\"Level 1\" diameter=150 elevation=2800 system=\"Exhaust Air\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(9000,0) level="Level 1" diameter=400 elevation=2800 system="Exhaust Air"` | green: op:add duct made=duct-02bdd91749926007,system-6cca971fffa3073f changed= ms=4 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add duct from=(2000,0) to=(2000,2500) level="Level 1" diameter=150 elevation=2800 system="Exhaust Air"` | green: op:add duct made=duct-f73db54d1385794e,duct-02bdd91749926007,duct-63bf7c8f423f5ccc,fitting-6fdff2cfd23d30a4,system-0f90460a18b377d5 changed=system-6cca971fffa3073f ms=5 Check "Ducts +2 and Duct Fittings +1": Ducts 1 -> 3 (+2, expected +2); [green] Duct Fittings 0 -> 1 (+1, expected +1) |
| `op:add duct from=(5000,0) to=(5000,2500) level="Level 1" diameter=150 elevation=2800 system="Exhaust Air"` | green: op:add duct made=duct-887f55e6ed0ffcc8,duct-63bf7c8f423f5ccc,duct-fb88a90f5c0e9ab5,fitting-c57d1bcec5c358ee,system-1ae972400e16fa02 changed=system-0f90460a18b377d5 ms=5 Check "Ducts +2 and Duct Fittings +1": Ducts 3 -> 5 (+2, expected +2); [green] Duct Fittings 1 -> 2 (+1, expected +1) |
| `op:add duct from=(8000,0) to=(8000,2500) level="Level 1" diameter=150 elevation=2800 system="Exhaust Air"` | green: op:add duct made=duct-b663c9be8d1c8a28,duct-fb88a90f5c0e9ab5,duct-b3d40a5b9905f12c,fitting-dd7e473e6fa6fc40,system-0a796b89f46256f3 changed=system-1ae972400e16fa02 ms=4 Check "Ducts +2 and Duct Fittings +1": Ducts 5 -> 7 (+2, expected +2); [green] Duct Fittings 2 -> 3 (+1, expected +1) |

### The result

The model holds: Duct Fittings 3,Duct Systems 1,Ducts 7,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3029. Draw a 5 x 4 m server room and place a cooled space in it with four people and a 4000 power load.

- Starts from: a new Architectural project
- Ends with: Four server room walls and one space set to Cooled.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(5000,0) level=Ground",
  "op:add wall from=(5000,0) to=(5000,4000) level=Ground",
  "op:add wall from=(5000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(5000,0) level=Ground` | green: op:add wall made=wall-96de7667ac5ef9e6 changed= ms=10 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(5000,0) to=(5000,4000) level=Ground` | green: op:add wall made=wall-ba337abfb70d91b5 changed=wall-96de7667ac5ef9e6 ms=7 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(5000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-7c41adb863a4f1f8 changed=wall-ba337abfb70d91b5 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-8771e934e7a5bae6 changed=wall-96de7667ac5ef9e6,wall-7c41adb863a4f1f8 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Space · picks (2500,2000) · keys Escape Escape · fields Options Strip: Condition Type=Cooled; People=4; Power Load=4000 · expect Spaces +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Space · picks (2500,2000) · keys Escape Escape · fields Options Strip: Condition Type=Cooled; People=4; Power Load=4000 · expect Spaces +1` | green: pressed 'Space' on Systems's Spaces & Zones panel (through its fold): the tool 'Space' stands \| fields: Condition Type=Cooled reads 'Cooled'; People=4 reads '4.00'; Power Load=4000 reads '4000.00' \| picks: (2500,2000) mm at px (721.3,368.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Space -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Spaces +1": Spaces 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Spaces 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 3030. Run a 100 mm cold water main 10 m along the north wall at 2500 mm with three 25 mm branches going south at 2, 5 and 8 m.

- Starts from: a new Hydraulic project
- Ends with: A 100 mm cold water main split by three 25 mm branches, 3 m long.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(10000,0) level=\"Level 1\" diameter=100 elevation=2500 system=\"Domestic Cold Water\"",
  "op:add pipe from=(2000,0) to=(2000,-3000) level=\"Level 1\" diameter=25 elevation=2500 system=\"Domestic Cold Water\"",
  "op:add pipe from=(5000,0) to=(5000,-3000) level=\"Level 1\" diameter=25 elevation=2500 system=\"Domestic Cold Water\"",
  "op:add pipe from=(8000,0) to=(8000,-3000) level=\"Level 1\" diameter=25 elevation=2500 system=\"Domestic Cold Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(10000,0) level="Level 1" diameter=100 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-8f422a04b42fc66a,system-1e76fac043089b27 changed= ms=184 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(2000,0) to=(2000,-3000) level="Level 1" diameter=25 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-2c360becb98f9d98,fitting-4f784fa5b631a9e3,pipe-71c42752010e709a changed=system-1e76fac043089b27,pipe-8f422a04b42fc66a ms=3 Check "Pipes +2 and Pipe Fittings +1": Pipes 1 -> 3 (+2, expected +2); [green] Pipe Fittings 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(5000,0) to=(5000,-3000) level="Level 1" diameter=25 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-1016fe1a6e6c9fe8,fitting-fe08fd83aa53b14f,pipe-93c618c5c367d86d changed=system-1e76fac043089b27,pipe-71c42752010e709a ms=5 Check "Pipes +2 and Pipe Fittings +1": Pipes 3 -> 5 (+2, expected +2); [green] Pipe Fittings 1 -> 2 (+1, expected +1) |
| `op:add pipe from=(8000,0) to=(8000,-3000) level="Level 1" diameter=25 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-7b99854c2ee72903,fitting-62a24e4a32b8b828,pipe-97e79b5582b4c765 changed=system-1e76fac043089b27,pipe-93c618c5c367d86d ms=3 Check "Pipes +2 and Pipe Fittings +1": Pipes 5 -> 7 (+2, expected +2); [green] Pipe Fittings 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipe Fittings 3,Pipes 7,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3031. Run a 40 mm hot water pipe and a 50 mm cold water pipe side by side down the service corridor, 300 mm apart.

- Starts from: a new Hydraulic project
- Ends with: A 50 mm cold water pipe and a 40 mm hot water pipe 300 mm apart, each in its own piping system.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(14000,0) level=\"Level 1\" diameter=50 elevation=2600 system=\"Domestic Cold Water\"",
  "op:add pipe from=(0,300) to=(14000,300) level=\"Level 1\" diameter=40 elevation=2600 system=\"Domestic Hot Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(14000,0) level="Level 1" diameter=50 elevation=2600 system="Domestic Cold Water"` | green: op:add pipe made=pipe-887cbec9dd91db66,system-ae4d87546c15fa41 changed= ms=5 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(0,300) to=(14000,300) level="Level 1" diameter=40 elevation=2600 system="Domestic Hot Water"` | green: op:add pipe made=pipe-6b4bab97128e945c,system-623caa9f23136358 changed= ms=2 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 2,Piping Systems 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3032. Draw a hydronic heating flow pipe and return pipe around a 6 x 4 m room with the Pipe tool, 50 mm, each turning one corner.

- Starts from: a new Hydraulic project
- Ends with: A hydronic supply run and a hydronic return run, each with one corner fitting.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (0,0) (6000,0) (6000,4000) · keys Escape Escape · fields Options Strip: Diameter=50; Middle Elevation=2600; System Type=Hydronic Supply · expect Pipes +2 and Pipe Fittings +1",
  "ribbon:Systems:Pipe · picks (0,500) (5500,500) (5500,4000) · keys Escape Escape · fields Options Strip: Diameter=50; Middle Elevation=2600; System Type=Hydronic Return · expect Pipes +2 and Pipe Fittings +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (0,0) (6000,0) (6000,4000) · keys Escape Escape · fields Options Strip: Diameter=50; Middle Elevation=2600; System Type=Hydronic Supply · expect Pipes +2 and Pipe Fittings +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=50 reads '50 mm'; Middle Elevation=2600 reads '2600 mm'; System Type=Hydronic Supply reads 'Hydronic Supply' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (6000,0) mm at px (759.7,427.0) on the plan view \| (6000,4000) mm at px (759.7,352.6) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +2 and Pipe Fittings +1": Pipes 0 -> 2 (+2, expected +2); [green] Pipe Fittings 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Pipe · picks (0,500) (5500,500) (5500,4000) · keys Escape Escape · fields Options Strip: Diameter=50; Middle Elevation=2600; System Type=Hydronic Return · expect Pipes +2 and Pipe Fittings +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=50 reads '50 mm'; Middle Elevation=2600 reads '2600 mm'; System Type=Hydronic Return reads 'Hydronic Return' \| picks: (0,500) mm at px (648.0,417.7) on the plan view \| (5500,500) mm at px (750.4,417.7) on the plan view \| (5500,4000) mm at px (750.4,352.6) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +2 and Pipe Fittings +1": Pipes 2 -> 4 (+2, expected +2); [green] Pipe Fittings 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipe Fittings 2,Pipes 4,Piping Systems 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3033. Run a 100 mm sanitary drain 8 m long at 1 per cent fall and put three fixtures along it.

- Starts from: a new Hydraulic project
- Ends with: A 100 mm sanitary drain with a 1.00 per cent fall and three plumbing fixtures.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (0,0) (8000,0) · keys Escape Escape · fields Options Strip: Diameter=100; Slope=1; System Type=Sanitary · expect Pipes +1 and Piping Systems +1",
  "ribbon:Systems:Plumbing Fixture · picks (1500,1000) (4000,1000) (6500,1000) · keys Escape Escape · fields — · expect Plumbing Fixtures +3"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (0,0) (8000,0) · keys Escape Escape · fields Options Strip: Diameter=100; Slope=1; System Type=Sanitary · expect Pipes +1 and Piping Systems +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=100 reads '100 mm'; Slope=1 reads '1.00 %'; System Type=Sanitary reads 'Sanitary' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (8000,0) mm at px (796.9,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Plumbing Fixture · picks (1500,1000) (4000,1000) (6500,1000) · keys Escape Escape · fields — · expect Plumbing Fixtures +3` | green: pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands \| picks: (1500,1000) mm at px (675.9,408.4) on the plan view \| (4000,1000) mm at px (722.4,408.4) on the plan view \| (6500,1000) mm at px (769.0,408.4) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Fixtures +3": Plumbing Fixtures 0 -> 3 (+3, expected +3) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,Plumbing Fixtures 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3034. Run a 50 mm vent pipe 5 m at 2800 mm and a 100 mm sanitary pipe 5 m beside it.

- Starts from: a new Hydraulic project
- Ends with: A vent pipe and a sanitary pipe, 5 m long, side by side.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(5000,0) level=\"Level 1\" diameter=50 elevation=2800 system=\"Vent\"",
  "op:add pipe from=(0,400) to=(5000,400) level=\"Level 1\" diameter=100 elevation=2000 system=\"Sanitary\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(5000,0) level="Level 1" diameter=50 elevation=2800 system="Vent"` | green: op:add pipe made=pipe-79a70ec6f6749ec8,system-8869c5266ab833de changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(0,400) to=(5000,400) level="Level 1" diameter=100 elevation=2000 system="Sanitary"` | green: op:add pipe made=pipe-68b7ad432e1866a3,system-2a2454df35117ff4 changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 2,Piping Systems 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3035. Place a water tank, run a 50 mm outlet pipe 6 m from it and put an isolating valve in the pipe.

- Starts from: a new Hydraulic project
- Ends with: A tank, a 50 mm pipe leaving it and a valve in the pipe.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Tank · picks (0,0) · keys Escape Escape · fields — · expect Plumbing Equipment +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Tank · picks (0,0) · keys Escape Escape · fields — · expect Plumbing Equipment +1` | green: pressed 'Tank' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Tank'; the press stood 136 ms (the menu stood at 20 ms; its row ran 91 ms; it made 0 child widgets native)): the tool 'Tank' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Tank -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Equipment +1": Plumbing Equipment 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add pipe from=(1500,0) to=(7500,0) level=\"Level 1\" diameter=50 elevation=1000 system=\"Domestic Cold Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(1500,0) to=(7500,0) level="Level 1" diameter=50 elevation=1000 system="Domestic Cold Water"` | green: op:add pipe made=pipe-0522c34d7eda6f37,system-50f188c47618232f changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe Accessory · picks (3500,0) · keys Escape Escape · fields — · expect Pipe Accessories +1 and Pipes +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe Accessory · picks (3500,0) · keys Escape Escape · fields — · expect Pipe Accessories +1 and Pipes +1` | green: pressed 'Pipe Accessory' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe Accessory' stands \| picks: (3500,0) mm at px (713.1,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Pipe Accessory -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Pipe Accessories +1 and Pipes +1": Pipe Accessories 0 -> 1 (+1, expected +1); [green] Pipes 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipe Accessories 1,Pipes 2,Piping Systems 1,Plumbing Equipment 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3036. Run a 32 mm cold water pipe 7 m along the wall and put four basins on the other side of it.

- Starts from: a new Hydraulic project
- Ends with: A 32 mm cold water pipe and four plumbing fixtures.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(7000,0) level=\"Level 1\" diameter=32 elevation=800 system=\"Domestic Cold Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(7000,0) level="Level 1" diameter=32 elevation=800 system="Domestic Cold Water"` | green: op:add pipe made=pipe-7d3487f31315e4ba,system-1b134dd57f7f7523 changed= ms=5 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Plumbing Fixture · picks (700,900) (2400,900) (4100,900) (5800,900) · keys Escape Escape · fields — · expect Plumbing Fixtures +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Plumbing Fixture · picks (700,900) (2400,900) (4100,900) (5800,900) · keys Escape Escape · fields — · expect Plumbing Fixtures +4` | green: pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands \| picks: (700,900) mm at px (661.0,410.3) on the plan view \| (2400,900) mm at px (692.7,410.3) on the plan view \| (4100,900) mm at px (724.3,410.3) on the plan view \| (5800,900) mm at px (755.9,410.3) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Fixtures +4": Plumbing Fixtures 0 -> 4 (+4, expected +4) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,Plumbing Fixtures 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3037. Draw a 65 mm pipe 6 m long, put a valve in it at 1.5 m and a pipe fitting at 4.5 m.

- Starts from: a new Hydraulic project
- Ends with: A 65 mm pipe carrying one valve and one fitting.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(6000,0) level=\"Level 1\" diameter=65 elevation=2500 system=\"Domestic Cold Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(6000,0) level="Level 1" diameter=65 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-4f2c7e0ddd0b2896,system-629f8bd8042eb8b6 changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe Accessory · picks (1500,0) · keys Escape Escape · fields — · expect Pipe Accessories +1 and Pipes +1",
  "ribbon:Systems:Pipe Fitting · picks (4500,0) · keys Escape Escape · fields — · expect Pipe Fittings +1 and Pipes +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe Accessory · picks (1500,0) · keys Escape Escape · fields — · expect Pipe Accessories +1 and Pipes +1` | green: pressed 'Pipe Accessory' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe Accessory' stands \| picks: (1500,0) mm at px (675.9,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Pipe Accessory -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Pipe Accessories +1 and Pipes +1": Pipe Accessories 0 -> 1 (+1, expected +1); [green] Pipes 1 -> 2 (+1, expected +1) |
| `ribbon:Systems:Pipe Fitting · picks (4500,0) · keys Escape Escape · fields — · expect Pipe Fittings +1 and Pipes +1` | green: pressed 'Pipe Fitting' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe Fitting' stands \| picks: (4500,0) mm at px (731.7,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Pipe Fitting -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Pipe Fittings +1 and Pipes +1": Pipe Fittings 0 -> 1 (+1, expected +1); [green] Pipes 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipe Accessories 1,Pipe Fittings 1,Pipes 3,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3038. Take a 100 mm cold water pipe up 3 m from the floor in a riser, then carry it 5 m east along the ceiling void.

- Starts from: a new Hydraulic project
- Ends with: A vertical 100 mm riser from 0 to 3000 mm and a horizontal pipe at 3000 mm leaving its top, joined by a fitting.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (0,0) · keys — · fields Options Strip: Diameter=100; Middle Elevation=0; System Type=Domestic Cold Water · expect every count unchanged",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields Options Strip: Middle Elevation=3000; Apply= · expect Pipes +1 and Piping Systems +1",
  "chrome:Canvas Zoom to Fit · picks (5000,0) · keys Escape Escape · fields — · expect Pipes +1 and Pipe Fittings +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (0,0) · keys — · fields Options Strip: Diameter=100; Middle Elevation=0; System Type=Domestic Cold Water · expect every count unchanged` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=100 reads '100 mm'; Middle Elevation=0 reads '0 mm'; System Type=Domestic Cold Water reads 'Domestic Cold Water' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 1, selection unchanged Check "every count unchanged": the counts: no count changed |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields Options Strip: Middle Elevation=3000; Apply= · expect Pipes +1 and Piping Systems +1` | green: PlanNavBarZoomToFit pressed; a command ran; tool Pipe standing \| fields: Middle Elevation=3000 reads '3000 mm'; 'Apply' pressed Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks (5000,0) · keys Escape Escape · fields — · expect Pipes +1 and Pipe Fittings +1` | green: PlanNavBarZoomToFit pressed; a command ran; tool Pipe standing \| picks: (5000,0) mm at px (741.1,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1 and Pipe Fittings +1": Pipes 1 -> 2 (+1, expected +1); [green] Pipe Fittings 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipe Fittings 1,Pipes 2,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3039. Run a 65 mm cold water pipe 8 m on Level 1 and the same pipe on Level 2 above it.

- Starts from: a new Hydraulic project
- Ends with: A 65 mm cold water pipe on Level 1 and one on Level 2, each in its own system.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(8000,0) level=\"Level 1\" diameter=65 elevation=2500 system=\"Domestic Cold Water\"",
  "op:add pipe from=(0,0) to=(8000,0) level=\"Level 2\" diameter=65 elevation=2500 system=\"Domestic Cold Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(8000,0) level="Level 1" diameter=65 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-212456be65ca8dab,system-b81b8e8a601b355c changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(0,0) to=(8000,0) level="Level 2" diameter=65 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-4bff6d169c5af6bb,system-b28c8f95a9e46513 changed= ms=70 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 2,Piping Systems 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3040. Run a 150 mm stormwater pipe 12 m long at a 1.5 per cent fall.

- Starts from: a new Hydraulic project
- Ends with: A 150 mm stormwater pipe with a 1.50 per cent fall.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (0,0) (12000,0) · keys Escape Escape · fields Options Strip: Diameter=150; Slope=1.5; System Type=Other · expect Pipes +1 and Piping Systems +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (0,0) (12000,0) · keys Escape Escape · fields Options Strip: Diameter=150; Slope=1.5; System Type=Other · expect Pipes +1 and Piping Systems +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=150 reads '150 mm'; Slope=1.5 reads '1.50 %'; System Type=Other reads 'Other' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (12000,0) mm at px (871.3,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3041. Draw the cold water and the hot water pipes and put a pipe legend beside them.

- Starts from: a new Hydraulic project
- Ends with: A cold water pipe, a hot water pipe and a pipe legend on the plan.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(8000,0) level=\"Level 1\" diameter=50 elevation=2500 system=\"Domestic Cold Water\"",
  "op:add pipe from=(0,500) to=(8000,500) level=\"Level 1\" diameter=40 elevation=2500 system=\"Domestic Hot Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(8000,0) level="Level 1" diameter=50 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-23f70a89467b4f8c,system-8d131be39d5e6f48 changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(0,500) to=(8000,500) level="Level 1" diameter=40 elevation=2500 system="Domestic Hot Water"` | green: op:add pipe made=pipe-8ce670b832724d96,system-5ee95298cdb2d1d4 changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe Legend · picks (10000,0) · keys Escape Escape · fields — · expect Pipe Legends +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe Legend · picks (10000,0) · keys Escape Escape · fields — · expect Pipe Legends +1` | green: pressed 'Pipe Legend' on Systems's Check Systems panel (through its fold): the tool 'Pipe Legend' stands \| picks: (10000,0) mm at px (834.1,427.0) on the plan view \| presses to the tool 1 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Pipe Legends +1": Pipe Legends 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipe Legends 1,Pipes 2,Piping Systems 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3042. Draw three pipes of 100, 50 and 25 mm and make a pipe schedule by type with a count.

- Starts from: a new Hydraulic project
- Ends with: Three pipes of different sizes and a Pipe Schedule.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(8000,0) level=\"Level 1\" diameter=100 elevation=2500 system=\"Domestic Cold Water\"",
  "op:add pipe from=(0,1000) to=(8000,1000) level=\"Level 1\" diameter=50 elevation=2500 system=\"Domestic Cold Water\"",
  "op:add pipe from=(0,2000) to=(8000,2000) level=\"Level 1\" diameter=25 elevation=2500 system=\"Domestic Hot Water\"",
  "op:add schedule category=Pipes fields=Type,Count name=\"Pipe Schedule\" itemize=no"
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(8000,0) level="Level 1" diameter=100 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-e638e61534a7eec2,system-5b459989733cbce7 changed= ms=9 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(0,1000) to=(8000,1000) level="Level 1" diameter=50 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-c7ccc18d8775416e,system-21363250d7f3fbd5 changed= ms=4 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |
| `op:add pipe from=(0,2000) to=(8000,2000) level="Level 1" diameter=25 elevation=2500 system="Domestic Hot Water"` | green: op:add pipe made=pipe-58e7ea19ea1f160d,system-c94e8c71db517250 changed= ms=2 Check "Pipes +1 and Piping Systems +1": Pipes 2 -> 3 (+1, expected +1); [green] Piping Systems 2 -> 3 (+1, expected +1) |
| `op:add schedule category=Pipes fields=Type,Count name="Pipe Schedule" itemize=no` | green: op:add schedule made=80ef2bff3bc64cd194bbda5186a6d2e8 changed= ms=16 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 3,Piping Systems 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 3043. Place three plumbing fixtures and schedule them by type with a count.

- Starts from: a new Hydraulic project
- Ends with: Three plumbing fixtures and a Fixture Schedule.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Plumbing Fixture · picks (0,0) (1500,0) (3000,0) · keys Escape Escape · fields — · expect Plumbing Fixtures +3"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Plumbing Fixture · picks (0,0) (1500,0) (3000,0) · keys Escape Escape · fields — · expect Plumbing Fixtures +3` | green: pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (1500,0) mm at px (675.9,427.0) on the plan view \| (3000,0) mm at px (703.8,427.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Fixtures +3": Plumbing Fixtures 0 -> 3 (+3, expected +3) |

```json
ops_run {"lines":[
  "op:add schedule category=\"Plumbing Fixtures\" fields=Type,Count name=\"Fixture Schedule\" itemize=no"
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category="Plumbing Fixtures" fields=Type,Count name="Fixture Schedule" itemize=no` | green: op:add schedule made=898cf274bf554a999c16a433b37990b4 changed= ms=385 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Plumbing Fixtures 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 3044. Draw a 100 mm hot water riser up to 3000 mm, take it back, then bring it back again.

- Starts from: a new Hydraulic project
- Ends with: One 100 mm hot water riser, drawn, undone and redone.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (0,0) · keys — · fields Options Strip: Diameter=100; Middle Elevation=0; System Type=Domestic Hot Water · expect every count unchanged",
  "chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields Options Strip: Middle Elevation=3000; Apply= · expect Pipes +1 and Piping Systems +1",
  "qa:Undo · picks — · keys — · fields — · expect Pipes -1 and Piping Systems -1",
  "qa:Redo · picks — · keys — · fields — · expect Pipes +1 and Piping Systems +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (0,0) · keys — · fields Options Strip: Diameter=100; Middle Elevation=0; System Type=Domestic Hot Water · expect every count unchanged` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=100 reads '100 mm'; Middle Elevation=0 reads '0 mm'; System Type=Domestic Hot Water reads 'Domestic Hot Water' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 1, selection unchanged Check "every count unchanged": the counts: no count changed |
| `chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields Options Strip: Middle Elevation=3000; Apply= · expect Pipes +1 and Piping Systems +1` | green: PlanNavBarZoomToFit pressed; a command ran; tool Pipe standing \| fields: Middle Elevation=3000 reads '3000 mm'; 'Apply' pressed \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `qa:Undo · picks — · keys — · fields — · expect Pipes -1 and Piping Systems -1` | green: QToolButton pressed; a command ran Check "Pipes -1 and Piping Systems -1": Pipes 1 -> 0 (-1, expected -1); [green] Piping Systems 1 -> 0 (-1, expected -1) |
| `qa:Redo · picks — · keys — · fields — · expect Pipes +1 and Piping Systems +1` | green: QToolButton pressed; a command ran Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3045. Draw two cold water pipes 1 m apart and delete the upper one.

- Starts from: a new Hydraulic project
- Ends with: One cold water pipe left at y = 0.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(6000,0) level=\"Level 1\" diameter=50 elevation=2500 system=\"Domestic Cold Water\"",
  "op:add pipe from=(0,1000) to=(6000,1000) level=\"Level 1\" diameter=50 elevation=2500 system=\"Domestic Cold Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(6000,0) level="Level 1" diameter=50 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-8edf70fccfddd32e,system-f1805954bf01d154 changed= ms=20 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(0,1000) to=(6000,1000) level="Level 1" diameter=50 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-225352bf3f764d59,system-fab9432c22b415a7 changed= ms=5 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (3000,1000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Pipes -1"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (3000,1000) · keys — · fields — · expect 1 selected` | green: select: (3000,1000) mm at px (703.8,408.4) on the plan view; picked 'pipe-225352bf3f764d59'; selected 0 -> 1 [pipe-225352bf3f764d59] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-225352bf3f764d59) (expected exactly 1) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Pipes -1` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Pipes -1": Pipes 2 -> 1 (-1, expected -1) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3046. Draw a cold water main with two branches and run the pipe system check.

- Starts from: a new Hydraulic project
- Ends with: A cold water main with two branches and the Check Pipe Systems report run on it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(9000,0) level=\"Level 1\" diameter=65 elevation=2500 system=\"Domestic Cold Water\"",
  "op:add pipe from=(3000,0) to=(3000,3000) level=\"Level 1\" diameter=32 elevation=2500 system=\"Domestic Cold Water\"",
  "op:add pipe from=(6000,0) to=(6000,3000) level=\"Level 1\" diameter=32 elevation=2500 system=\"Domestic Cold Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(9000,0) level="Level 1" diameter=65 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-cdca6fff4768f524,system-742e4328ee8e5343 changed= ms=7 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(3000,0) to=(3000,3000) level="Level 1" diameter=32 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-1b2e8568a8747562,fitting-f84d6df2ca23af8c,pipe-780df8d0e1859e9f changed=system-742e4328ee8e5343,pipe-cdca6fff4768f524 ms=7 Check "Pipes +2 and Pipe Fittings +1": Pipes 1 -> 3 (+2, expected +2); [green] Pipe Fittings 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(6000,0) to=(6000,3000) level="Level 1" diameter=32 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-c677e0e897991bca,fitting-b496412b6fc83a92,pipe-034c160b32ffb6b5 changed=system-742e4328ee8e5343,pipe-780df8d0e1859e9f ms=6 Check "Pipes +2 and Pipe Fittings +1": Pipes 3 -> 5 (+2, expected +2); [green] Pipe Fittings 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Check Pipe Systems · picks — · keys — · fields — · expect status: Check Pipe Systems"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Check Pipe Systems · picks — · keys — · fields — · expect status: Check Pipe Systems` | green: pressed 'Check Pipe Systems' on Systems's Check Systems panel (through its fold) (the window's first paint at 72 ms in QDialog#servicesCheckReport:Check Pipe Systems): the command 'Check Pipe Systems' ran; status 'Check Pipe Systems: 4 found -- selected' Check "status: Check Pipe Systems": status 'Check Pipe Systems' read; now 'Check Pipe Systems: 4 found -- selected', since the step began 'Check Pipe Systems: 4 found -- selected' |

### The result

The model holds: Levels 2,Pipe Fittings 2,Pipes 5,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3047. Place a hot water tank and run a 40 mm hot water flow and return pair 8 m out from it, with a valve in the flow pipe.

- Starts from: a new Hydraulic project
- Ends with: A tank, a hot water flow pipe and return pipe, and a valve in the flow.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Tank · picks (0,0) · keys Escape Escape · fields — · expect Plumbing Equipment +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Tank · picks (0,0) · keys Escape Escape · fields — · expect Plumbing Equipment +1` | green: pressed 'Tank' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Tank'; the press stood 195 ms (the menu stood at 41 ms; its row ran 153 ms; it made 0 child widgets native)): the tool 'Tank' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Tank -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Equipment +1": Plumbing Equipment 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add pipe from=(1500,-300) to=(9500,-300) level=\"Level 1\" diameter=40 elevation=1000 system=\"Domestic Hot Water\"",
  "op:add pipe from=(1500,300) to=(9500,300) level=\"Level 1\" diameter=40 elevation=1000 system=\"Domestic Hot Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(1500,-300) to=(9500,-300) level="Level 1" diameter=40 elevation=1000 system="Domestic Hot Water"` | green: op:add pipe made=pipe-10592928f541d869,system-2cff8217664a3b08 changed= ms=2 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(1500,300) to=(9500,300) level="Level 1" diameter=40 elevation=1000 system="Domestic Hot Water"` | green: op:add pipe made=pipe-00452525d0362142,system-a0b0fd7e5004b528 changed= ms=2 Check "Pipes +1": Pipes 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe Accessory · picks (3000,-300) · keys Escape Escape · fields — · expect Pipe Accessories +1 and Pipes +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe Accessory · picks (3000,-300) · keys Escape Escape · fields — · expect Pipe Accessories +1 and Pipes +1` | green: pressed 'Pipe Accessory' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe Accessory' stands \| picks: (3000,-300) mm at px (703.8,432.6) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Pipe Accessory -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Pipe Accessories +1 and Pipes +1": Pipe Accessories 0 -> 1 (+1, expected +1); [green] Pipes 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipe Accessories 1,Pipes 3,Piping Systems 2,Plumbing Equipment 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3048. Put a row of three basins along the north wall and a row of three along the south wall of a 6 m washroom.

- Starts from: a new Hydraulic project
- Ends with: Six plumbing fixtures in two rows.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Plumbing Fixture · picks (1000,3500) (3000,3500) (5000,3500) · keys Escape Escape · fields — · expect Plumbing Fixtures +3",
  "ribbon:Systems:Plumbing Fixture · picks (1000,500) (3000,500) (5000,500) · keys Escape Escape · fields — · expect Plumbing Fixtures +3"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Plumbing Fixture · picks (1000,3500) (3000,3500) (5000,3500) · keys Escape Escape · fields — · expect Plumbing Fixtures +3` | green: pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands \| picks: (1000,3500) mm at px (666.6,361.9) on the plan view \| (3000,3500) mm at px (703.8,361.9) on the plan view \| (5000,3500) mm at px (741.1,361.9) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Fixtures +3": Plumbing Fixtures 0 -> 3 (+3, expected +3) |
| `ribbon:Systems:Plumbing Fixture · picks (1000,500) (3000,500) (5000,500) · keys Escape Escape · fields — · expect Plumbing Fixtures +3` | green: pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands \| picks: (1000,500) mm at px (666.6,417.7) on the plan view \| (3000,500) mm at px (703.8,417.7) on the plan view \| (5000,500) mm at px (741.1,417.7) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Fixtures +3": Plumbing Fixtures 3 -> 6 (+3, expected +3) |

### The result

The model holds: Levels 2,Plumbing Fixtures 6,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3049. Draw 100, 65 and 40 mm cold water pipes 1 m apart with the Pipe tool.

- Starts from: a new Hydraulic project
- Ends with: Three cold water pipes of 100, 65 and 40 mm.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (0,0) (9000,0) · keys Escape Escape · fields Options Strip: Diameter=100; Middle Elevation=2500; System Type=Domestic Cold Water · expect Pipes +1 and Piping Systems +1",
  "ribbon:Systems:Pipe · picks (0,1000) (9000,1000) · keys Escape Escape · fields Options Strip: Diameter=65; Middle Elevation=2500; System Type=Domestic Cold Water · expect Pipes +1 and Piping Systems +1",
  "ribbon:Systems:Pipe · picks (0,2000) (9000,2000) · keys Escape Escape · fields Options Strip: Diameter=40; Middle Elevation=2500; System Type=Domestic Cold Water · expect Pipes +1 and Piping Systems +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (0,0) (9000,0) · keys Escape Escape · fields Options Strip: Diameter=100; Middle Elevation=2500; System Type=Domestic Cold Water · expect Pipes +1 and Piping Systems +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=100 reads '100 mm'; Middle Elevation=2500 reads '2500 mm'; System Type=Domestic Cold Water reads 'Domestic Cold Water' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (9000,0) mm at px (815.5,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Pipe · picks (0,1000) (9000,1000) · keys Escape Escape · fields Options Strip: Diameter=65; Middle Elevation=2500; System Type=Domestic Cold Water · expect Pipes +1 and Piping Systems +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=65 reads '65 mm'; Middle Elevation=2500 reads '2500 mm'; System Type=Domestic Cold Water reads 'Domestic Cold Water' \| picks: (0,1000) mm at px (648.0,408.4) on the plan view \| (9000,1000) mm at px (815.5,408.4) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |
| `ribbon:Systems:Pipe · picks (0,2000) (9000,2000) · keys Escape Escape · fields Options Strip: Diameter=40; Middle Elevation=2500; System Type=Domestic Cold Water · expect Pipes +1 and Piping Systems +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=40 reads '40 mm'; Middle Elevation=2500 reads '2500 mm'; System Type=Domestic Cold Water reads 'Domestic Cold Water' \| picks: (0,2000) mm at px (648.0,389.8) on the plan view \| (9000,2000) mm at px (815.5,389.8) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1 and Piping Systems +1": Pipes 2 -> 3 (+1, expected +1); [green] Piping Systems 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 3,Piping Systems 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3050. Run a 100 mm wet sprinkler main 9 m long with three 40 mm branches at 1.5, 4.5 and 7.5 m, and put four sprinklers on each branch.

- Starts from: a new Fire Protection project
- Ends with: A 100 mm sprinkler main, three 40 mm branches and twelve sprinklers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(9000,0) level=\"Level 1\" diameter=100 elevation=3200 system=\"Fire Protection Wet\"",
  "op:add pipe from=(1500,0) to=(1500,6000) level=\"Level 1\" diameter=40 elevation=3200 system=\"Fire Protection Wet\"",
  "op:add pipe from=(4500,0) to=(4500,6000) level=\"Level 1\" diameter=40 elevation=3200 system=\"Fire Protection Wet\"",
  "op:add pipe from=(7500,0) to=(7500,6000) level=\"Level 1\" diameter=40 elevation=3200 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(9000,0) level="Level 1" diameter=100 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-b2a691b14500c401,system-254118cbffb6624b changed= ms=9 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(1500,0) to=(1500,6000) level="Level 1" diameter=40 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-632f43fddf06550b,fitting-1ba25f6dcd037bfb,pipe-4b821eb829bd2a0c changed=system-254118cbffb6624b,pipe-b2a691b14500c401 ms=8 Check "Pipes +2 and Pipe Fittings +1": Pipes 1 -> 3 (+2, expected +2); [green] Pipe Fittings 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(4500,0) to=(4500,6000) level="Level 1" diameter=40 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-fa41eb68df7401d1,fitting-c63691445f9a3b35,pipe-8c9575113ea10a98 changed=system-254118cbffb6624b,pipe-4b821eb829bd2a0c ms=5 Check "Pipes +2 and Pipe Fittings +1": Pipes 3 -> 5 (+2, expected +2); [green] Pipe Fittings 1 -> 2 (+1, expected +1) |
| `op:add pipe from=(7500,0) to=(7500,6000) level="Level 1" diameter=40 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-73fcadd0813b165c,fitting-8784cf6daea2bfa7,pipe-5cd5adecd688681d changed=system-254118cbffb6624b,pipe-8c9575113ea10a98 ms=8 Check "Pipes +2 and Pipe Fittings +1": Pipes 5 -> 7 (+2, expected +2); [green] Pipe Fittings 2 -> 3 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Sprinkler · picks (1500,1500) (1500,3000) (1500,4500) (1500,6000) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4",
  "ribbon:Systems:Sprinkler · picks (4500,1500) (4500,3000) (4500,4500) (4500,6000) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4",
  "ribbon:Systems:Sprinkler · picks (7500,1500) (7500,3000) (7500,4500) (7500,6000) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Sprinkler · picks (1500,1500) (1500,3000) (1500,4500) (1500,6000) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3000 reads '3000 mm' \| picks: (1500,1500) mm at px (675.9,399.1) on the plan view \| (1500,3000) mm at px (675.9,371.2) on the plan view \| (1500,4500) mm at px (675.9,343.3) on the plan view \| (1500,6000) mm at px (675.9,315.3) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +4": Sprinklers 0 -> 4 (+4, expected +4) |
| `ribbon:Systems:Sprinkler · picks (4500,1500) (4500,3000) (4500,4500) (4500,6000) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3000 reads '3000 mm' \| picks: (4500,1500) mm at px (731.7,399.1) on the plan view \| (4500,3000) mm at px (731.7,371.2) on the plan view \| (4500,4500) mm at px (731.7,343.3) on the plan view \| (4500,6000) mm at px (731.7,315.3) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +4": Sprinklers 4 -> 8 (+4, expected +4) |
| `ribbon:Systems:Sprinkler · picks (7500,1500) (7500,3000) (7500,4500) (7500,6000) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3000 reads '3000 mm' \| picks: (7500,1500) mm at px (787.6,399.1) on the plan view \| (7500,3000) mm at px (787.6,371.2) on the plan view \| (7500,4500) mm at px (787.6,343.3) on the plan view \| (7500,6000) mm at px (787.6,315.3) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +4": Sprinklers 8 -> 12 (+4, expected +4) |

### The result

The model holds: Levels 2,Pipe Fittings 3,Pipes 7,Piping Systems 1,Sprinklers 12,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3051. Lay out sprinklers for a 12 x 9 m office at 3 m spacing, three branch lines off a riser main on the west wall.

- Starts from: a new Fire Protection project
- Ends with: A 100 mm main, three 32 mm branch lines and twelve sprinklers on a 3 m grid.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(-500,0) to=(-500,9000) level=\"Level 1\" diameter=100 elevation=3200 system=\"Fire Protection Wet\"",
  "op:add pipe from=(-500,1500) to=(11500,1500) level=\"Level 1\" diameter=32 elevation=3200 system=\"Fire Protection Wet\"",
  "op:add pipe from=(-500,4500) to=(11500,4500) level=\"Level 1\" diameter=32 elevation=3200 system=\"Fire Protection Wet\"",
  "op:add pipe from=(-500,7500) to=(11500,7500) level=\"Level 1\" diameter=32 elevation=3200 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(-500,0) to=(-500,9000) level="Level 1" diameter=100 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-a87d1ffedc369587,system-5f049cf960fe5b44 changed= ms=7 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(-500,1500) to=(11500,1500) level="Level 1" diameter=32 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-59218fcefb6ce6e6,fitting-85620f35466b963e,pipe-f257f83b2b2911bf changed=system-5f049cf960fe5b44,pipe-a87d1ffedc369587 ms=5 Check "Pipes +2 and Pipe Fittings +1": Pipes 1 -> 3 (+2, expected +2); [green] Pipe Fittings 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(-500,4500) to=(11500,4500) level="Level 1" diameter=32 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-990c27e694d3cfc7,fitting-b2cada6e669de983,pipe-caa562183dadaba5 changed=system-5f049cf960fe5b44,pipe-f257f83b2b2911bf ms=4 Check "Pipes +2 and Pipe Fittings +1": Pipes 3 -> 5 (+2, expected +2); [green] Pipe Fittings 1 -> 2 (+1, expected +1) |
| `op:add pipe from=(-500,7500) to=(11500,7500) level="Level 1" diameter=32 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-b458921b89987199,fitting-860f7e8ab52eb086,pipe-d6a80649070b12f3 changed=system-5f049cf960fe5b44,pipe-caa562183dadaba5 ms=4 Check "Pipes +2 and Pipe Fittings +1": Pipes 5 -> 7 (+2, expected +2); [green] Pipe Fittings 2 -> 3 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Sprinkler · picks (1500,1500) (4500,1500) (7500,1500) (10500,1500) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4",
  "ribbon:Systems:Sprinkler · picks (1500,4500) (4500,4500) (7500,4500) (10500,4500) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4",
  "ribbon:Systems:Sprinkler · picks (1500,7500) (4500,7500) (7500,7500) (10500,7500) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Sprinkler · picks (1500,1500) (4500,1500) (7500,1500) (10500,1500) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3000 reads '3000 mm' \| picks: (1500,1500) mm at px (675.9,399.1) on the plan view \| (4500,1500) mm at px (731.7,399.1) on the plan view \| (7500,1500) mm at px (787.6,399.1) on the plan view \| (10500,1500) mm at px (843.4,399.1) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +4": Sprinklers 0 -> 4 (+4, expected +4) |
| `ribbon:Systems:Sprinkler · picks (1500,4500) (4500,4500) (7500,4500) (10500,4500) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3000 reads '3000 mm' \| picks: (1500,4500) mm at px (675.9,343.3) on the plan view \| (4500,4500) mm at px (731.7,343.3) on the plan view \| (7500,4500) mm at px (787.6,343.3) on the plan view \| (10500,4500) mm at px (843.4,343.3) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +4": Sprinklers 4 -> 8 (+4, expected +4) |
| `ribbon:Systems:Sprinkler · picks (1500,7500) (4500,7500) (7500,7500) (10500,7500) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +4` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3000 reads '3000 mm' \| picks: (1500,7500) mm at px (675.9,287.4) on the plan view \| (4500,7500) mm at px (731.7,287.4) on the plan view \| (7500,7500) mm at px (787.6,287.4) on the plan view \| (10500,7500) mm at px (843.4,287.4) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +4": Sprinklers 8 -> 12 (+4, expected +4) |

### The result

The model holds: Levels 2,Pipe Fittings 3,Pipes 7,Piping Systems 1,Sprinklers 12,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3052. Put sprinklers every 3 m down a 24 m corridor on a 65 mm pipe at 3000 mm.

- Starts from: a new Fire Protection project
- Ends with: A 65 mm wet pipe 24 m long with eight sprinklers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(24000,0) level=\"Level 1\" diameter=65 elevation=3000 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(24000,0) level="Level 1" diameter=65 elevation=3000 system="Fire Protection Wet"` | green: op:add pipe made=pipe-d043f64b6a6590a5,system-1f729f117625c65c changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Sprinkler · picks (1500,0) (4500,0) (7500,0) (10500,0) (13500,0) (16500,0) (19500,0) (22500,0) · keys Escape Escape · fields Options Strip: Offset=2900 · expect Sprinklers +8"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Sprinkler · picks (1500,0) (4500,0) (7500,0) (10500,0) (13500,0) (16500,0) (19500,0) (22500,0) · keys Escape Escape · fields Options Strip: Offset=2900 · expect Sprinklers +8` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=2900 reads '2900 mm' \| picks: (1500,0) mm at px (650.3,427.0) on the plan view \| (4500,0) mm at px (706.1,427.0) on the plan view \| (7500,0) mm at px (761.9,427.0) on the plan view \| (10500,0) mm at px (817.8,427.0) on the plan view \| (13500,0) mm at px (873.6,427.0) on the plan view \| (16500,0) mm at px (929.4,427.0) on the plan view \| (19500,0) mm at px (985.3,427.0) on the plan view \| (22500,0) mm at px (1041.1,427.0) on the plan view \| presses to the tool 8, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +8": Sprinklers 0 -> 8 (+8, expected +8) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,Sprinklers 8,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3053. Run a 100 mm wet main for the offices and a 100 mm dry main for the car park, 5 m apart, and give each three sprinklers.

- Starts from: a new Fire Protection project
- Ends with: A wet pipe and a dry pipe, each with three sprinklers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(12000,0) level=\"Level 1\" diameter=100 elevation=3200 system=\"Fire Protection Wet\"",
  "op:add pipe from=(0,5000) to=(12000,5000) level=\"Level 1\" diameter=100 elevation=3200 system=\"Fire Protection Dry\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(12000,0) level="Level 1" diameter=100 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-c50d75010b6ad6e6,system-f7ce6f49bce8ae3d changed= ms=4 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(0,5000) to=(12000,5000) level="Level 1" diameter=100 elevation=3200 system="Fire Protection Dry"` | green: op:add pipe made=pipe-786c784c7653942c,system-218f0af1d23a68b8 changed= ms=4 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Sprinkler · picks (2000,0) (6000,0) (10000,0) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +3",
  "ribbon:Systems:Sprinkler · picks (2000,5000) (6000,5000) (10000,5000) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +3"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Sprinkler · picks (2000,0) (6000,0) (10000,0) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +3` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3000 reads '3000 mm' \| picks: (2000,0) mm at px (685.2,427.0) on the plan view \| (6000,0) mm at px (759.7,427.0) on the plan view \| (10000,0) mm at px (834.1,427.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +3": Sprinklers 0 -> 3 (+3, expected +3) |
| `ribbon:Systems:Sprinkler · picks (2000,5000) (6000,5000) (10000,5000) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +3` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3000 reads '3000 mm' \| picks: (2000,5000) mm at px (685.2,333.9) on the plan view \| (6000,5000) mm at px (759.7,333.9) on the plan view \| (10000,5000) mm at px (834.1,333.9) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +3": Sprinklers 3 -> 6 (+3, expected +3) |

### The result

The model holds: Levels 2,Pipes 2,Piping Systems 2,Sprinklers 6,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3054. Run a pre-action sprinkler pipe through a 6 x 4 m server room and put four sprinklers on it.

- Starts from: a new Fire Protection project
- Ends with: A pre-action pipe 6 m long with four sprinklers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,2000) to=(6000,2000) level=\"Level 1\" diameter=50 elevation=2900 system=\"Fire Protection Pre-Action\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,2000) to=(6000,2000) level="Level 1" diameter=50 elevation=2900 system="Fire Protection Pre-Action"` | green: op:add pipe made=pipe-24840cb5fdb530e5,system-b326e82facbe1898 changed= ms=4 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Sprinkler · picks (1000,2000) (2500,2000) (4000,2000) (5500,2000) · keys Escape Escape · fields Options Strip: Offset=2800 · expect Sprinklers +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Sprinkler · picks (1000,2000) (2500,2000) (4000,2000) (5500,2000) · keys Escape Escape · fields Options Strip: Offset=2800 · expect Sprinklers +4` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=2800 reads '2800 mm' \| picks: (1000,2000) mm at px (666.6,389.8) on the plan view \| (2500,2000) mm at px (694.5,389.8) on the plan view \| (4000,2000) mm at px (722.4,389.8) on the plan view \| (5500,2000) mm at px (750.4,389.8) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +4": Sprinklers 0 -> 4 (+4, expected +4) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,Sprinklers 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3055. Lay a 150 mm hydrant ring main around the building, 30 x 20 m, with a hydrant at each corner.

- Starts from: a new Fire Protection project
- Ends with: Four 150 mm ring main pipes in a closed loop and four hydrants.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(30000,0) level=\"Level 1\" diameter=150 elevation=-900 system=\"Fire Protection Wet\"",
  "op:add pipe from=(30000,0) to=(30000,20000) level=\"Level 1\" diameter=150 elevation=-900 system=\"Fire Protection Wet\"",
  "op:add pipe from=(30000,20000) to=(0,20000) level=\"Level 1\" diameter=150 elevation=-900 system=\"Fire Protection Wet\"",
  "op:add pipe from=(0,20000) to=(0,0) level=\"Level 1\" diameter=150 elevation=-900 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(30000,0) level="Level 1" diameter=150 elevation=-900 system="Fire Protection Wet"` | green: op:add pipe made=pipe-7170af391de7296b,system-3f308978d09c166f changed= ms=4 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(30000,0) to=(30000,20000) level="Level 1" diameter=150 elevation=-900 system="Fire Protection Wet"` | green: op:add pipe made=pipe-7ec8ab89d0e07302,fitting-f03ef2f248b4ee28 changed=system-3f308978d09c166f,pipe-7170af391de7296b ms=3 Check "Pipes +1 and Pipe Fittings +1": Pipes 1 -> 2 (+1, expected +1); [green] Pipe Fittings 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(30000,20000) to=(0,20000) level="Level 1" diameter=150 elevation=-900 system="Fire Protection Wet"` | green: op:add pipe made=pipe-aeecd8a3d4d8499a,fitting-7b205c3996223e9c changed=system-3f308978d09c166f,pipe-7ec8ab89d0e07302 ms=5 Check "Pipes +1 and Pipe Fittings +1": Pipes 2 -> 3 (+1, expected +1); [green] Pipe Fittings 1 -> 2 (+1, expected +1) |
| `op:add pipe from=(0,20000) to=(0,0) level="Level 1" diameter=150 elevation=-900 system="Fire Protection Wet"` | green: op:add pipe made=pipe-20344fc4f3aca348,fitting-c63ac561bb999419,fitting-532513b631caaa34 changed=system-3f308978d09c166f,pipe-7170af391de7296b,pipe-aeecd8a3d4d8499a ms=5 Check "Pipes +1 and Pipe Fittings +2": Pipes 3 -> 4 (+1, expected +1); [green] Pipe Fittings 2 -> 4 (+2, expected +2) |

```json
steps_run {"steps":[
  "ribbon:Systems:Hydrant · picks (0,0) (30000,0) (30000,20000) (0,20000) · keys Escape Escape · fields — · expect Fire Protection +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Hydrant · picks (0,0) (30000,0) (30000,20000) (0,20000) · keys Escape Escape · fields — · expect Fire Protection +4` | green: pressed 'Hydrant' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Hydrant'; the press stood 332 ms (the menu stood at 35 ms; its row ran 296 ms; it made 0 child widgets native)): the tool 'Hydrant' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (30000,0) mm at px (1206.3,427.0) on the plan view \| (30000,20000) mm at px (1206.3,54.8) on the plan view \| (0,20000) mm at px (648.0,54.8) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Hydrant -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fire Protection +4": Fire Protection 0 -> 4 (+4, expected +4) |

### The result

The model holds: Fire Protection 4,Levels 2,Pipe Fittings 4,Pipes 4,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3056. Run a 50 mm fire supply pipe down a 20 m corridor and put three hose reels on it.

- Starts from: a new Fire Protection project
- Ends with: A 50 mm fire protection pipe and three hose reels.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(20000,0) level=\"Level 1\" diameter=50 elevation=1200 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(20000,0) level="Level 1" diameter=50 elevation=1200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-2a806aad8e59db73,system-9343008e93494829 changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Hose Reel · picks (4000,300) (10000,300) (16000,300) · keys Escape Escape · fields — · expect Fire Protection +3"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Hose Reel · picks (4000,300) (10000,300) (16000,300) · keys Escape Escape · fields — · expect Fire Protection +3` | green: pressed 'Hose Reel' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Hose Reel'; the press stood 100 ms (the menu stood at 58 ms; its row ran 41 ms; it made 0 child widgets native)): the tool 'Hose Reel' stands \| picks: (4000,300) mm at px (722.4,421.4) on the plan view \| (10000,300) mm at px (834.1,421.4) on the plan view \| (16000,300) mm at px (945.8,421.4) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Hose Reel -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fire Protection +3": Fire Protection 0 -> 3 (+3, expected +3) |

### The result

The model holds: Fire Protection 3,Levels 2,Pipes 1,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3057. Put the fire pump in the pump room and connect a 150 mm suction pipe on one side and a 100 mm discharge pipe on the other.

- Starts from: a new Fire Protection project
- Ends with: A fire pump with a 150 mm suction pipe and a 100 mm discharge pipe.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Fire Pump · picks (0,0) · keys Escape Escape · fields — · expect Mechanical Equipment +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Fire Pump · picks (0,0) · keys Escape Escape · fields — · expect Mechanical Equipment +1` | green: pressed 'Fire Pump' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Fire Pump'; the press stood 70 ms (the menu stood at 24 ms; its row ran 26 ms; it made 0 child widgets native)): the tool 'Fire Pump' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Fire Pump -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add pipe from=(-5000,0) to=(-1000,0) level=\"Level 1\" diameter=150 elevation=500 system=\"Fire Protection Wet\"",
  "op:add pipe from=(1000,0) to=(6000,0) level=\"Level 1\" diameter=100 elevation=500 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(-5000,0) to=(-1000,0) level="Level 1" diameter=150 elevation=500 system="Fire Protection Wet"` | green: op:add pipe made=pipe-0899d5151a8e68e7,system-5c7fdf6b1642a0de changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(1000,0) to=(6000,0) level="Level 1" diameter=100 elevation=500 system="Fire Protection Wet"` | green: op:add pipe made=pipe-953266d7fc674946,system-c89870dac6af5213 changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 2,Mechanical Equipment 1,Pipes 2,Piping Systems 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3058. Put three pendant sprinklers at 2800 mm below the ceiling and three upright sprinklers at 3300 mm in the ceiling void on the same pipe.

- Starts from: a new Fire Protection project
- Ends with: A 65 mm pipe at 3200 mm with three heads at 2800 mm and three at 3300 mm.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(12000,0) level=\"Level 1\" diameter=65 elevation=3200 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(12000,0) level="Level 1" diameter=65 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-286b6ae0569f8eed,system-dc0dbcb57978134f changed= ms=4 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Sprinkler · picks (1500,0) (5500,0) (9500,0) · keys Escape Escape · fields Options Strip: Offset=2800 · expect Sprinklers +3",
  "ribbon:Systems:Sprinkler · picks (3500,0) (7500,0) (11500,0) · keys Escape Escape · fields Options Strip: Offset=3300 · expect Sprinklers +3"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Sprinkler · picks (1500,0) (5500,0) (9500,0) · keys Escape Escape · fields Options Strip: Offset=2800 · expect Sprinklers +3` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=2800 reads '2800 mm' \| picks: (1500,0) mm at px (675.9,427.0) on the plan view \| (5500,0) mm at px (750.4,427.0) on the plan view \| (9500,0) mm at px (824.8,427.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +3": Sprinklers 0 -> 3 (+3, expected +3) |
| `ribbon:Systems:Sprinkler · picks (3500,0) (7500,0) (11500,0) · keys Escape Escape · fields Options Strip: Offset=3300 · expect Sprinklers +3` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3300 reads '3300 mm' \| picks: (3500,0) mm at px (713.1,427.0) on the plan view \| (7500,0) mm at px (787.6,427.0) on the plan view \| (11500,0) mm at px (862.0,427.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +3": Sprinklers 3 -> 6 (+3, expected +3) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,Sprinklers 6,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3059. Put six sprinklers on a branch line and schedule them by type with a count.

- Starts from: a new Fire Protection project
- Ends with: A branch pipe with six sprinklers and a Sprinkler Schedule.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(18000,0) level=\"Level 1\" diameter=40 elevation=3000 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(18000,0) level="Level 1" diameter=40 elevation=3000 system="Fire Protection Wet"` | green: op:add pipe made=pipe-fb79f5758a0714b1,system-53acc2792443c079 changed= ms=5 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Sprinkler · picks (1500,0) (4500,0) (7500,0) (10500,0) (13500,0) (16500,0) · keys Escape Escape · fields Options Strip: Offset=2900 · expect Sprinklers +6"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Sprinkler · picks (1500,0) (4500,0) (7500,0) (10500,0) (13500,0) (16500,0) · keys Escape Escape · fields Options Strip: Offset=2900 · expect Sprinklers +6` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=2900 reads '2900 mm' \| picks: (1500,0) mm at px (675.9,427.0) on the plan view \| (4500,0) mm at px (731.7,427.0) on the plan view \| (7500,0) mm at px (787.6,427.0) on the plan view \| (10500,0) mm at px (843.4,427.0) on the plan view \| (13500,0) mm at px (899.2,427.0) on the plan view \| (16500,0) mm at px (955.1,427.0) on the plan view \| presses to the tool 6, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +6": Sprinklers 0 -> 6 (+6, expected +6) |

```json
ops_run {"lines":[
  "op:add schedule category=Sprinklers fields=Type,Count name=\"Sprinkler Schedule\" itemize=no"
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category=Sprinklers fields=Type,Count name="Sprinkler Schedule" itemize=no` | green: op:add schedule made=e8a39a0d06fe46e489e4b00ff23758bb changed= ms=20 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,Sprinklers 6,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 3060. Put three sprinklers on a pipe, then take the last one back out with Undo.

- Starts from: a new Fire Protection project
- Ends with: A 65 mm pipe with two sprinklers after the Undo.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(9000,0) level=\"Level 1\" diameter=65 elevation=3000 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(9000,0) level="Level 1" diameter=65 elevation=3000 system="Fire Protection Wet"` | green: op:add pipe made=pipe-3aed70c4f0487360,system-6f894ad6468593bf changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Sprinkler · picks (1500,0) (4500,0) (7500,0) · keys Escape Escape · fields Options Strip: Offset=2900 · expect Sprinklers +3",
  "qa:Undo · picks — · keys — · fields — · expect Sprinklers -1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Sprinkler · picks (1500,0) (4500,0) (7500,0) · keys Escape Escape · fields Options Strip: Offset=2900 · expect Sprinklers +3` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=2900 reads '2900 mm' \| picks: (1500,0) mm at px (675.9,427.0) on the plan view \| (4500,0) mm at px (731.7,427.0) on the plan view \| (7500,0) mm at px (787.6,427.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +3": Sprinklers 0 -> 3 (+3, expected +3) |
| `qa:Undo · picks — · keys — · fields — · expect Sprinklers -1` | green: QToolButton pressed; a command ran Check "Sprinklers -1": Sprinklers 3 -> 2 (-1, expected -1) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,Sprinklers 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3061. Run a 100 mm wet main on each floor, 10 m long, and put two sprinklers on the Level 1 main.

- Starts from: a new Fire Protection project
- Ends with: A wet main on Level 1 and one on Level 2, with two sprinklers on the Level 1 main.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(10000,0) level=\"Level 1\" diameter=100 elevation=3200 system=\"Fire Protection Wet\"",
  "op:add pipe from=(0,0) to=(10000,0) level=\"Level 2\" diameter=100 elevation=3200 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(10000,0) level="Level 1" diameter=100 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-7fe443e881baa5f8,system-9f7ff9100b191d33 changed= ms=18 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(0,0) to=(10000,0) level="Level 2" diameter=100 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-a4ed0477c797852c,system-4d369f226b3d3bd2 changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Sprinkler · picks (3000,0) (7000,0) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +2"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Sprinkler · picks (3000,0) (7000,0) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +2` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3000 reads '3000 mm' \| picks: (3000,0) mm at px (703.8,427.0) on the plan view \| (7000,0) mm at px (778.3,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +2": Sprinklers 0 -> 2 (+2, expected +2) |

### The result

The model holds: Levels 2,Pipes 2,Piping Systems 2,Sprinklers 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3062. Run a sprinkler main with a branch and check the pipe systems.

- Starts from: a new Fire Protection project
- Ends with: A sprinkler main and branch and the Check Pipe Systems report run on them.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(9000,0) level=\"Level 1\" diameter=100 elevation=3200 system=\"Fire Protection Wet\"",
  "op:add pipe from=(4500,0) to=(4500,5000) level=\"Level 1\" diameter=40 elevation=3200 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(9000,0) level="Level 1" diameter=100 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-a347266c52a259f6,system-0db56a2d99ec55d1 changed= ms=5 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(4500,0) to=(4500,5000) level="Level 1" diameter=40 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-07331cb215f469d4,fitting-00cab059b5199860,pipe-a2c32ffd4a7a6862 changed=system-0db56a2d99ec55d1,pipe-a347266c52a259f6 ms=4 Check "Pipes +2 and Pipe Fittings +1": Pipes 1 -> 3 (+2, expected +2); [green] Pipe Fittings 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Check Pipe Systems · picks — · keys — · fields — · expect status: Check Pipe Systems"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Check Pipe Systems · picks — · keys — · fields — · expect status: Check Pipe Systems` | green: pressed 'Check Pipe Systems' on Systems's Check Systems panel (through its fold) (the window's first paint at 24 ms in QDialog#servicesCheckReport:Check Pipe Systems): the command 'Check Pipe Systems' ran; status 'Check Pipe Systems: 3 found -- selected' Check "status: Check Pipe Systems": status 'Check Pipe Systems' read; now 'Check Pipe Systems: 3 found -- selected', since the step began 'Check Pipe Systems: 3 found -- selected' |

### The result

The model holds: Levels 2,Pipe Fittings 1,Pipes 3,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3063. Run a 150 mm fire main 16 m along the loading dock, put two hydrants on it and two hose reels on the wall behind.

- Starts from: a new Fire Protection project
- Ends with: A 150 mm fire main, two hydrants and two hose reels.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(16000,0) level=\"Level 1\" diameter=150 elevation=-900 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(16000,0) level="Level 1" diameter=150 elevation=-900 system="Fire Protection Wet"` | green: op:add pipe made=pipe-e729c35b2f98a5c3,system-9ebbb3feb3ea7b96 changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Hydrant · picks (4000,0) (12000,0) · keys Escape Escape · fields — · expect Fire Protection +2",
  "ribbon:Systems:Hose Reel · picks (6000,1500) (10000,1500) · keys Escape Escape · fields — · expect Fire Protection +2"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Hydrant · picks (4000,0) (12000,0) · keys Escape Escape · fields — · expect Fire Protection +2` | green: pressed 'Hydrant' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Hydrant'; the press stood 563 ms (the menu stood at 24 ms; its row ran 538 ms; it made 0 child widgets native)): the tool 'Hydrant' stands \| picks: (4000,0) mm at px (722.4,427.0) on the plan view \| (12000,0) mm at px (871.3,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Hydrant -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fire Protection +2": Fire Protection 0 -> 2 (+2, expected +2) |
| `ribbon:Systems:Hose Reel · picks (6000,1500) (10000,1500) · keys Escape Escape · fields — · expect Fire Protection +2` | green: pressed 'Hose Reel' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Hose Reel'; the press stood 57 ms (the menu stood at 20 ms; its row ran 15 ms; it made 0 child widgets native)): the tool 'Hose Reel' stands \| picks: (6000,1500) mm at px (759.7,399.1) on the plan view \| (10000,1500) mm at px (834.1,399.1) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Hose Reel -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fire Protection +2": Fire Protection 2 -> 4 (+2, expected +2) |

### The result

The model holds: Fire Protection 4,Levels 2,Pipes 1,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3064. Draw a 100 mm sprinkler main with the Pipe tool and a 40 mm branch off it, then add two sprinklers on the branch.

- Starts from: a new Fire Protection project
- Ends with: A 100 mm wet main, a 40 mm branch and two sprinklers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (0,0) (9000,0) · keys Escape Escape · fields Options Strip: Diameter=100; Middle Elevation=3200; System Type=Fire Protection Wet · expect Pipes +1 and Piping Systems +1",
  "ribbon:Systems:Pipe · picks (4500,0) (4500,6000) · keys Escape Escape · fields Options Strip: Diameter=40; Middle Elevation=3200; System Type=Fire Protection Wet · expect Pipes +2 and Pipe Fittings +1",
  "ribbon:Systems:Sprinkler · picks (4500,2000) (4500,4500) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +2"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (0,0) (9000,0) · keys Escape Escape · fields Options Strip: Diameter=100; Middle Elevation=3200; System Type=Fire Protection Wet · expect Pipes +1 and Piping Systems +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=100 reads '100 mm'; Middle Elevation=3200 reads '3200 mm'; System Type=Fire Protection Wet reads 'Fire Protection Wet' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (9000,0) mm at px (815.5,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Pipe · picks (4500,0) (4500,6000) · keys Escape Escape · fields Options Strip: Diameter=40; Middle Elevation=3200; System Type=Fire Protection Wet · expect Pipes +2 and Pipe Fittings +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| fields: Diameter=40 reads '40 mm'; Middle Elevation=3200 reads '3200 mm'; System Type=Fire Protection Wet reads 'Fire Protection Wet' \| picks: (4500,0) mm at px (731.7,427.0) on the plan view \| (4500,6000) mm at px (731.7,315.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +2 and Pipe Fittings +1": Pipes 1 -> 3 (+2, expected +2); [green] Pipe Fittings 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Sprinkler · picks (4500,2000) (4500,4500) · keys Escape Escape · fields Options Strip: Offset=3000 · expect Sprinklers +2` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=3000 reads '3000 mm' \| picks: (4500,2000) mm at px (731.7,389.8) on the plan view \| (4500,4500) mm at px (731.7,343.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +2": Sprinklers 0 -> 2 (+2, expected +2) |

### The result

The model holds: Levels 2,Pipe Fittings 1,Pipes 3,Piping Systems 1,Sprinklers 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3065. Draw a 6 m supply duct with a diffuser and name its duct system SA-01.

- Starts from: a new Mechanical project
- Ends with: A supply duct with a diffuser, in a duct system named SA-01.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(0,0) to=(6000,0) level=\"Level 1\" width=500 height=250 elevation=2700 system=\"Supply Air\"",
  "op:add terminal at=(3000,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(0,0) to=(6000,0) level="Level 1" width=500 height=250 elevation=2700 system="Supply Air"` | green: op:add duct made=duct-81f2f7f658e8369e,system-414087b04da21ac7 changed= ms=6 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(3000,0) level="Level 1"` | green: op:add terminal made=terminal-7b1dfc45d3e0a4d8 changed=system-414087b04da21ac7 ms=3 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (5500,0) · keys — · fields — · expect 1 selected",
  "contextual:Duct System · picks — · keys — · fields Create Duct System: System Type=Supply Air; System Name=SA-01; OK= · expect Duct Systems +1 and dialog closed"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (5500,0) · keys — · fields — · expect 1 selected` | green: select: (5500,0) mm at px (750.4,427.0) on the plan view; picked 'duct-81f2f7f658e8369e'; selected 0 -> 1 [duct-81f2f7f658e8369e] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (duct-81f2f7f658e8369e) (expected exactly 1) |
| `contextual:Duct System · picks — · keys — · fields Create Duct System: System Type=Supply Air; System Name=SA-01; OK= · expect Duct Systems +1 and dialog closed` | green: contextual 'Duct System' on 'Modify \| Ducts': pressed 'Duct System' on Modify \| Ducts's DynamicSelect_Ducts panel (through its fold) (the window's first paint at 66 ms in QDialog#CreateSystemDialog): the dialog 'Create Duct System' opened and stood; closed by the player \| inside the modal 'Create Duct System' \| fields: System Type=Supply Air reads 'Supply Air'; System Name=SA-01 reads 'SA-01'; 'OK' pressed; the dialog closed Check "Duct Systems +1 and dialog closed": Duct Systems 1 -> 2 (+1, expected +1); [green] no modal dialog stands, and no non-modal dialog window |

### The result

The model holds: Air Terminals 1,Duct Systems 2,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3066. Draw a 9 m cold water pipe and name its piping system CW-01.

- Starts from: a new Hydraulic project
- Ends with: A cold water pipe in a piping system named CW-01.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(9000,0) level=\"Level 1\" diameter=50 elevation=2500 system=\"Domestic Cold Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(9000,0) level="Level 1" diameter=50 elevation=2500 system="Domestic Cold Water"` | green: op:add pipe made=pipe-412567c591d9bf5b,system-9205cd22263d70ea changed= ms=4 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (8000,0) · keys — · fields — · expect 1 selected",
  "contextual:Piping System · picks — · keys — · fields Create Piping System: System Type=Domestic Cold Water; System Name=CW-01; OK= · expect dialog closed"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (8000,0) · keys — · fields — · expect 1 selected` | green: select: (8000,0) mm at px (796.9,427.0) on the plan view; picked 'pipe-412567c591d9bf5b'; selected 0 -> 1 [pipe-412567c591d9bf5b] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-412567c591d9bf5b) (expected exactly 1) |
| `contextual:Piping System · picks — · keys — · fields Create Piping System: System Type=Domestic Cold Water; System Name=CW-01; OK= · expect dialog closed` | green: contextual 'Piping System' on 'Modify \| Pipes': pressed 'Piping System' on Modify \| Pipes's DynamicSelect_Pipes panel (through its fold) (the window's first paint at 64 ms in QDialog#CreateSystemDialog): the dialog 'Create Piping System' opened and stood; closed by the player \| inside the modal 'Create Piping System' \| fields: System Type=Domestic Cold Water reads 'Domestic Cold Water'; System Name=CW-01 reads 'CW-01'; 'OK' pressed; the dialog closed Check "dialog closed": no modal dialog stands, and no non-modal dialog window |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3067. Run a 32 mm cold water pipe 5 m along the wall and connect a flexible pipe from its end to a basin 800 mm away.

- Starts from: a new Hydraulic project
- Ends with: A 32 mm pipe, a flex pipe leaving its end and a plumbing fixture at the flex pipe's end.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(0,0) to=(5000,0) level=\"Level 1\" diameter=32 elevation=800 system=\"Domestic Cold Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(0,0) to=(5000,0) level="Level 1" diameter=32 elevation=800 system="Domestic Cold Water"` | green: op:add pipe made=pipe-1d94066062fd8ec1,system-53e614357cf51e69 changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Flex Pipe · picks (5000,0) (5000,800) · keys Escape Escape · fields — · expect Flex Pipes +1",
  "ribbon:Systems:Plumbing Fixture · picks (5000,1000) · keys Escape Escape · fields — · expect Plumbing Fixtures +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Flex Pipe · picks (5000,0) (5000,800) · keys Escape Escape · fields — · expect Flex Pipes +1` | green: pressed 'Flex Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Flex Pipe' stands \| picks: (5000,0) mm at px (741.1,427.0) on the plan view \| (5000,800) mm at px (741.1,412.1) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Flex Pipe -> tool Flex Pipe, 'Flex Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Flex Pipe -> no tool) Check "Flex Pipes +1": Flex Pipes 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Plumbing Fixture · picks (5000,1000) · keys Escape Escape · fields — · expect Plumbing Fixtures +1` | green: pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands \| picks: (5000,1000) mm at px (741.1,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Fixtures +1": Plumbing Fixtures 0 -> 1 (+1, expected +1) |

### The result

The model holds: Flex Pipes 1,Levels 2,Pipes 1,Piping Systems 1,Plumbing Fixtures 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3068. Draw a 6 x 4 m office, place a space in it and put a thermostat on the wall beside the door position.

- Starts from: a new Mechanical project
- Ends with: Four office walls, a space and a mechanical control device.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=\"Level 1\"",
  "op:add wall from=(6000,0) to=(6000,4000) level=\"Level 1\"",
  "op:add wall from=(6000,4000) to=(0,4000) level=\"Level 1\"",
  "op:add wall from=(0,4000) to=(0,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level="Level 1"` | green: op:add wall made=wall-3630444f62f80a44 changed= ms=42 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level="Level 1"` | green: op:add wall made=wall-2eb494a9dbd7e3b1 changed=wall-3630444f62f80a44 ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level="Level 1"` | green: op:add wall made=wall-5b0435402ff36d5e changed=wall-2eb494a9dbd7e3b1 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level="Level 1"` | green: op:add wall made=wall-0bb9961f1690ea5b changed=wall-3630444f62f80a44,wall-5b0435402ff36d5e ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Space · picks (3000,2000) · keys Escape Escape · fields — · expect Spaces +1",
  "ribbon:Systems:Mechanical Control Device · picks (1000,150) · keys Escape Escape · fields — · expect Mechanical Control Devices +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Space · picks (3000,2000) · keys Escape Escape · fields — · expect Spaces +1` | green: pressed 'Space' on Systems's Spaces & Zones panel (through its fold): the tool 'Space' stands \| picks: (3000,2000) mm at px (703.8,389.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Space -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Spaces +1": Spaces 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Mechanical Control Device · picks (1000,150) · keys Escape Escape · fields — · expect Mechanical Control Devices +1` | green: pressed 'Mechanical Control Device' on Systems's Mechanical panel: the tool 'Mechanical Control Device' stands \| picks: (1000,150) mm at px (666.6,424.2) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Mechanical Control Device -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Mechanical Control Devices +1": Mechanical Control Devices 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Mechanical Control Devices 1,Spaces 1,Walls 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3069. Rough in a supply duct run as a single-line placeholder duct 12 m long before it is sized.

- Starts from: a new Mechanical project
- Ends with: One single-line placeholder duct 12 m long.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Duct Placeholder · picks (0,0) (12000,0) · keys Escape Escape · fields — · expect Ducts +1 and Duct Systems +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Duct Placeholder · picks (0,0) (12000,0) · keys Escape Escape · fields — · expect Ducts +1 and Duct Systems +1` | green: pressed 'Duct Placeholder' on Systems's HVAC panel: the tool 'Duct Placeholder' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (12000,0) mm at px (871.3,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Duct Placeholder -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |

### The result

The model holds: Duct Systems 1,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3070. Run a 300 x 100 cable tray 15 m down the corridor at 3000 mm.

- Starts from: a new Electrical project
- Ends with: One 300 x 100 cable tray 15 m long at 3000 mm.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Cable Tray · picks (0,0) (15000,0) · keys Escape Escape · fields Options Strip: Width=300; Height=100; Offset=3000 · expect Cable Trays +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Cable Tray · picks (0,0) (15000,0) · keys Escape Escape · fields Options Strip: Width=300; Height=100; Offset=3000 · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| fields: Width=300 reads '300 mm'; Height=100 reads '100 mm'; Offset=3000 reads '3000 mm' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (15000,0) mm at px (927.2,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 0 -> 1 (+1, expected +1) |

### The result

The model holds: Cable Trays 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3071. Run a 450 mm main cable tray 12 m long and branch a 300 mm tray off it at 6 m going north for 5 m.

- Starts from: a new Electrical project
- Ends with: A 450 x 100 main tray and a 300 x 100 branch tray.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Cable Tray · picks (0,0) (12000,0) · keys Escape Escape · fields Options Strip: Width=450; Height=100; Offset=3000 · expect Cable Trays +1",
  "ribbon:Systems:Cable Tray · picks (6000,0) (6000,5000) · keys Escape Escape · fields Options Strip: Width=300; Height=100; Offset=3000 · expect Cable Trays +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Cable Tray · picks (0,0) (12000,0) · keys Escape Escape · fields Options Strip: Width=450; Height=100; Offset=3000 · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| fields: Width=450 reads '450 mm'; Height=100 reads '100 mm'; Offset=3000 reads '3000 mm' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (12000,0) mm at px (871.3,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Cable Tray · picks (6000,0) (6000,5000) · keys Escape Escape · fields Options Strip: Width=300; Height=100; Offset=3000 · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| fields: Width=300 reads '300 mm'; Height=100 reads '100 mm'; Offset=3000 reads '3000 mm' \| picks: (6000,0) mm at px (759.7,427.0) on the plan view \| (6000,5000) mm at px (759.7,333.9) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 1 -> 2 (+1, expected +1) |

### The result

The model holds: Cable Trays 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3072. Run a 450 mm power tray at 3000 mm and a 150 mm data tray at 2700 mm side by side down a 15 m corridor.

- Starts from: a new Electrical project
- Ends with: A power tray and a data tray 600 mm apart.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Cable Tray · picks (0,0) (15000,0) · keys Escape Escape · fields Options Strip: Width=450; Height=100; Offset=3000 · expect Cable Trays +1",
  "ribbon:Systems:Cable Tray · picks (0,600) (15000,600) · keys Escape Escape · fields Options Strip: Width=150; Height=60; Offset=2700 · expect Cable Trays +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Cable Tray · picks (0,0) (15000,0) · keys Escape Escape · fields Options Strip: Width=450; Height=100; Offset=3000 · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| fields: Width=450 reads '450 mm'; Height=100 reads '100 mm'; Offset=3000 reads '3000 mm' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (15000,0) mm at px (927.2,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Cable Tray · picks (0,600) (15000,600) · keys Escape Escape · fields Options Strip: Width=150; Height=60; Offset=2700 · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| fields: Width=150 reads '150 mm'; Height=60 reads '60 mm'; Offset=2700 reads '2700 mm' \| picks: (0,600) mm at px (648.0,415.8) on the plan view \| (15000,600) mm at px (927.2,415.8) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 1 -> 2 (+1, expected +1) |

### The result

The model holds: Cable Trays 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3073. Put a distribution board on the wall and run three 25 mm conduits from it to the first three outlet positions.

- Starts from: a new Electrical project
- Ends with: A distribution board, three 25 mm conduits and three outlets.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Electrical Equipment · picks (0,0) · keys Escape Escape · fields — · expect Electrical Equipment +1",
  "ribbon:Systems:Conduit · picks (500,0) (3000,0) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=300 · expect Conduits +1",
  "ribbon:Systems:Conduit · picks (500,200) (5000,200) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=300 · expect Conduits +1",
  "ribbon:Systems:Conduit · picks (500,400) (7000,400) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=300 · expect Conduits +1",
  "ribbon:Systems:Outlet · picks (3000,0) (5000,200) (7000,400) · keys Escape Escape · fields — · expect Electrical Fixtures +3"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Electrical Equipment · picks (0,0) · keys Escape Escape · fields — · expect Electrical Equipment +1` | green: pressed 'Electrical Equipment' on Systems's Electrical panel (through its fold): the tool 'Electrical Equipment' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Electrical Equipment -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Equipment +1": Electrical Equipment 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Conduit · picks (500,0) (3000,0) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=300 · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| fields: Diameter=25 reads '25 mm'; Offset=300 reads '300 mm' \| picks: (500,0) mm at px (657.3,427.0) on the plan view \| (3000,0) mm at px (703.8,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Conduit · picks (500,200) (5000,200) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=300 · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| fields: Diameter=25 reads '25 mm'; Offset=300 reads '300 mm' \| picks: (500,200) mm at px (657.3,423.3) on the plan view \| (5000,200) mm at px (741.1,423.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 1 -> 2 (+1, expected +1) |
| `ribbon:Systems:Conduit · picks (500,400) (7000,400) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=300 · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| fields: Diameter=25 reads '25 mm'; Offset=300 reads '300 mm' \| picks: (500,400) mm at px (657.3,419.6) on the plan view \| (7000,400) mm at px (778.3,419.6) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 2 -> 3 (+1, expected +1) |
| `ribbon:Systems:Outlet · picks (3000,0) (5000,200) (7000,400) · keys Escape Escape · fields — · expect Electrical Fixtures +3` | green: pressed 'Outlet' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Outlet'; the press stood 320 ms (the menu stood at 11 ms; its row ran 307 ms; it made 0 child widgets native)): the tool 'Outlet' stands \| picks: (3000,0) mm at px (703.8,427.0) on the plan view \| (5000,200) mm at px (741.1,423.3) on the plan view \| (7000,400) mm at px (778.3,419.6) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Outlet -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Fixtures +3": Electrical Fixtures 0 -> 3 (+3, expected +3) |

### The result

The model holds: Conduits 3,Electrical Equipment 1,Electrical Equipment Tags 1,Electrical Fixtures 3,Levels 2,Tags 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3074. Draw a 6 x 4 m switchboard room and put a main switchboard against the east wall.

- Starts from: a new Electrical project
- Ends with: Four walls and a switchboard inside them.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=\"Level 1\"",
  "op:add wall from=(6000,0) to=(6000,4000) level=\"Level 1\"",
  "op:add wall from=(6000,4000) to=(0,4000) level=\"Level 1\"",
  "op:add wall from=(0,4000) to=(0,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level="Level 1"` | green: op:add wall made=wall-10c86db763b567f2 changed= ms=7 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level="Level 1"` | green: op:add wall made=wall-3fb89662041e0b2c changed=wall-10c86db763b567f2 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level="Level 1"` | green: op:add wall made=wall-1b30460af0db0e2d changed=wall-3fb89662041e0b2c ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level="Level 1"` | green: op:add wall made=wall-6a1d08fe9fa9a771 changed=wall-1b30460af0db0e2d,wall-10c86db763b567f2 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Electrical Equipment · picks (5600,2000) · keys Escape Escape · fields — · expect Electrical Equipment +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Electrical Equipment · picks (5600,2000) · keys Escape Escape · fields — · expect Electrical Equipment +1` | green: pressed 'Electrical Equipment' on Systems's Electrical panel (through its fold): the tool 'Electrical Equipment' stands \| picks: (5600,2000) mm at px (752.2,389.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Electrical Equipment -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Equipment +1": Electrical Equipment 0 -> 1 (+1, expected +1) |

### The result

The model holds: Electrical Equipment 1,Electrical Equipment Tags 1,Levels 2,Tags 1,Walls 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3075. Lay out six luminaires on a 3 m grid in a 9 x 6 m office, three across and two down.

- Starts from: a new Electrical project
- Ends with: Six lighting fixtures on a 3 m grid.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Lighting Fixture · picks (1500,1500) (4500,1500) (7500,1500) (1500,4500) (4500,4500) (7500,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +6"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Lighting Fixture · picks (1500,1500) (4500,1500) (7500,1500) (1500,4500) (4500,4500) (7500,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +6` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (1500,1500) mm at px (675.9,399.1) on the plan view \| (4500,1500) mm at px (731.7,399.1) on the plan view \| (7500,1500) mm at px (787.6,399.1) on the plan view \| (1500,4500) mm at px (675.9,343.3) on the plan view \| (4500,4500) mm at px (731.7,343.3) on the plan view \| (7500,4500) mm at px (787.6,343.3) on the plan view \| presses to the tool 6, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +6": Lighting Fixtures 0 -> 6 (+6, expected +6) |

### The result

The model holds: Levels 2,Lighting Fixtures 6,Lighting Fixtures Tags 6,Tags 6,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3076. Put a luminaire every 3 m down a 24 m corridor.

- Starts from: a new Electrical project
- Ends with: Eight lighting fixtures 3 m apart.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Lighting Fixture · picks (1500,0) (4500,0) (7500,0) (10500,0) (13500,0) (16500,0) (19500,0) (22500,0) · keys Escape Escape · fields — · expect Lighting Fixtures +8"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Lighting Fixture · picks (1500,0) (4500,0) (7500,0) (10500,0) (13500,0) (16500,0) (19500,0) (22500,0) · keys Escape Escape · fields — · expect Lighting Fixtures +8` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (1500,0) mm at px (675.9,427.0) on the plan view \| (4500,0) mm at px (731.7,427.0) on the plan view \| (7500,0) mm at px (787.6,427.0) on the plan view \| (10500,0) mm at px (843.4,427.0) on the plan view \| (13500,0) mm at px (899.2,427.0) on the plan view \| (16500,0) mm at px (955.1,427.0) on the plan view \| (19500,0) mm at px (1010.9,427.0) on the plan view \| (22500,0) mm at px (1066.7,427.0) on the plan view \| presses to the tool 8, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +8": Lighting Fixtures 0 -> 8 (+8, expected +8) |

### The result

The model holds: Levels 2,Lighting Fixtures 8,Lighting Fixtures Tags 8,Tags 8,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3077. Draw an 8 m wall and put six power outlets along it at 300 mm from the floor line.

- Starts from: a new Electrical project
- Ends with: One 8 m wall and six outlets along it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level="Level 1"` | green: op:add wall made=wall-6b3f8cdea557a08c changed= ms=10 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Outlet · picks (500,100) (2000,100) (3500,100) (5000,100) (6500,100) (7800,100) · keys Escape Escape · fields — · expect Electrical Fixtures +6"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Outlet · picks (500,100) (2000,100) (3500,100) (5000,100) (6500,100) (7800,100) · keys Escape Escape · fields — · expect Electrical Fixtures +6` | green: pressed 'Outlet' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Outlet'; the press stood 5379 ms (the menu stood at 164 ms; its row ran 5214 ms; it made 0 child widgets native)): the tool 'Outlet' stands \| picks: (500,100) mm at px (657.3,425.1) on the plan view \| (2000,100) mm at px (685.2,425.1) on the plan view \| (3500,100) mm at px (713.1,425.1) on the plan view \| (5000,100) mm at px (741.1,425.1) on the plan view \| (6500,100) mm at px (769.0,425.1) on the plan view \| (7800,100) mm at px (793.2,425.1) on the plan view \| presses to the tool 6, selection unchanged \| keys: Escape (tool Outlet -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Fixtures +6": Electrical Fixtures 0 -> 6 (+6, expected +6) |

### The result

The model holds: Electrical Fixtures 6,Levels 2,Walls 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3078. Put three light switches and three data points along the corridor wall.

- Starts from: a new Electrical project
- Ends with: Three switch points and three data points.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Switch Point · picks (1000,0) (6000,0) (11000,0) · keys Escape Escape · fields — · expect Lighting Devices +3",
  "ribbon:Systems:Data Point · picks (3000,0) (8000,0) (13000,0) · keys Escape Escape · fields — · expect Data Devices +3"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Switch Point · picks (1000,0) (6000,0) (11000,0) · keys Escape Escape · fields — · expect Lighting Devices +3` | green: pressed 'Switch Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Switch Point'; the press stood 115 ms (the menu stood at 40 ms; its row ran 73 ms; it made 0 child widgets native)): the tool 'Switch Point' stands \| picks: (1000,0) mm at px (666.6,427.0) on the plan view \| (6000,0) mm at px (759.7,427.0) on the plan view \| (11000,0) mm at px (852.7,427.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Switch Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Devices +3": Lighting Devices 0 -> 3 (+3, expected +3) |
| `ribbon:Systems:Data Point · picks (3000,0) (8000,0) (13000,0) · keys Escape Escape · fields — · expect Data Devices +3` | green: pressed 'Data Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Data Point'; the press stood 334 ms (the menu stood at 18 ms; its row ran 304 ms; it made 0 child widgets native)): the tool 'Data Point' stands \| picks: (3000,0) mm at px (703.8,427.0) on the plan view \| (8000,0) mm at px (796.9,427.0) on the plan view \| (13000,0) mm at px (889.9,427.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Data Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Data Devices +3": Data Devices 0 -> 3 (+3, expected +3) |

### The result

The model holds: Data Devices 3,Levels 2,Lighting Devices 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3079. Put the fire alarm panel at the entry and five detection points down the corridor.

- Starts from: a new Electrical project
- Ends with: One electrical panel and five fire alarm devices.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Electrical Equipment · picks (-1000,0) · keys Escape Escape · fields — · expect Electrical Equipment +1",
  "ribbon:Systems:Fire Alarm Point · picks (2000,0) (6000,0) (10000,0) (14000,0) (18000,0) · keys Escape Escape · fields — · expect Fire Alarm Devices +5"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Electrical Equipment · picks (-1000,0) · keys Escape Escape · fields — · expect Electrical Equipment +1` | green: pressed 'Electrical Equipment' on Systems's Electrical panel (through its fold): the tool 'Electrical Equipment' stands \| picks: (-1000,0) mm at px (629.4,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Electrical Equipment -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Equipment +1": Electrical Equipment 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Fire Alarm Point · picks (2000,0) (6000,0) (10000,0) (14000,0) (18000,0) · keys Escape Escape · fields — · expect Fire Alarm Devices +5` | green: pressed 'Fire Alarm Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Fire Alarm Point'; the press stood 179 ms (the menu stood at 16 ms; its row ran 149 ms; it made 0 child widgets native)): the tool 'Fire Alarm Point' stands \| picks: (2000,0) mm at px (685.2,427.0) on the plan view \| (6000,0) mm at px (759.7,427.0) on the plan view \| (10000,0) mm at px (834.1,427.0) on the plan view \| (14000,0) mm at px (908.5,427.0) on the plan view \| (18000,0) mm at px (983.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Fire Alarm Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fire Alarm Devices +5": Fire Alarm Devices 0 -> 5 (+5, expected +5) |

### The result

The model holds: Electrical Equipment 1,Electrical Equipment Tags 1,Fire Alarm Devices 5,Levels 2,Tags 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3080. Run 20, 25 and 32 mm conduits 8 m long side by side, 200 mm apart.

- Starts from: a new Electrical project
- Ends with: Three conduits of 20, 25 and 32 mm.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Conduit · picks (0,0) (8000,0) · keys Escape Escape · fields Options Strip: Diameter=20; Offset=2800 · expect Conduits +1",
  "ribbon:Systems:Conduit · picks (0,200) (8000,200) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=2800 · expect Conduits +1",
  "ribbon:Systems:Conduit · picks (0,400) (8000,400) · keys Escape Escape · fields Options Strip: Diameter=32; Offset=2800 · expect Conduits +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Conduit · picks (0,0) (8000,0) · keys Escape Escape · fields Options Strip: Diameter=20; Offset=2800 · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| fields: Diameter=20 reads '20 mm'; Offset=2800 reads '2800 mm' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (8000,0) mm at px (796.9,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Conduit · picks (0,200) (8000,200) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=2800 · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| fields: Diameter=25 reads '25 mm'; Offset=2800 reads '2800 mm' \| picks: (0,200) mm at px (648.0,423.3) on the plan view \| (8000,200) mm at px (796.9,423.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 1 -> 2 (+1, expected +1) |
| `ribbon:Systems:Conduit · picks (0,400) (8000,400) · keys Escape Escape · fields Options Strip: Diameter=32; Offset=2800 · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| fields: Diameter=32 reads '32 mm'; Offset=2800 reads '2800 mm' \| picks: (0,400) mm at px (648.0,419.6) on the plan view \| (8000,400) mm at px (796.9,419.6) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 2 -> 3 (+1, expected +1) |

### The result

The model holds: Conduits 3,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3081. Wire the distribution board to the outlet 3 m away.

- Starts from: a new Electrical project
- Ends with: A board, an outlet and a wire between them.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Electrical Equipment · picks (0,0) · keys Escape Escape · fields — · expect Electrical Equipment +1",
  "ribbon:Systems:Outlet · picks (3000,0) · keys Escape Escape · fields — · expect Electrical Fixtures +1",
  "ribbon:Systems:Wire · picks (0,0) (3000,0) · keys Escape Escape · fields — · expect Wires +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Electrical Equipment · picks (0,0) · keys Escape Escape · fields — · expect Electrical Equipment +1` | green: pressed 'Electrical Equipment' on Systems's Electrical panel (through its fold): the tool 'Electrical Equipment' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Electrical Equipment -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Equipment +1": Electrical Equipment 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Outlet · picks (3000,0) · keys Escape Escape · fields — · expect Electrical Fixtures +1` | green: pressed 'Outlet' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Outlet'; the press stood 1139 ms (the menu stood at 27 ms; its row ran 1110 ms; it made 0 child widgets native)): the tool 'Outlet' stands \| picks: (3000,0) mm at px (703.8,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Outlet -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Fixtures +1": Electrical Fixtures 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Wire · picks (0,0) (3000,0) · keys Escape Escape · fields — · expect Wires +1` | green: pressed 'Wire' on Systems's Electrical panel (through its fold): the tool 'Wire' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (3000,0) mm at px (703.8,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Wire -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Wires +1": Wires 0 -> 1 (+1, expected +1) |

### The result

The model holds: Electrical Equipment 1,Electrical Equipment Tags 1,Electrical Fixtures 1,Levels 2,Tags 1,Wires 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3082. Run a 600 x 100 cable tray 10 m to the main switchboard at its end.

- Starts from: a new Electrical project
- Ends with: A 600 x 100 tray 10 m long ending at a switchboard.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Cable Tray · picks (0,0) (10000,0) · keys Escape Escape · fields Options Strip: Width=600; Height=100; Offset=2600 · expect Cable Trays +1",
  "ribbon:Systems:Electrical Equipment · picks (10800,0) · keys Escape Escape · fields — · expect Electrical Equipment +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Cable Tray · picks (0,0) (10000,0) · keys Escape Escape · fields Options Strip: Width=600; Height=100; Offset=2600 · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| fields: Width=600 reads '600 mm'; Height=100 reads '100 mm'; Offset=2600 reads '2600 mm' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (10000,0) mm at px (834.1,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Electrical Equipment · picks (10800,0) · keys Escape Escape · fields — · expect Electrical Equipment +1` | green: pressed 'Electrical Equipment' on Systems's Electrical panel (through its fold): the tool 'Electrical Equipment' stands \| picks: (10800,0) mm at px (849.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Electrical Equipment -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Equipment +1": Electrical Equipment 0 -> 1 (+1, expected +1) |

### The result

The model holds: Cable Trays 1,Electrical Equipment 1,Electrical Equipment Tags 1,Levels 2,Tags 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3083. Put four emergency luminaires in the corridor and two fire alarm call points at the exits.

- Starts from: a new Electrical project
- Ends with: Four lighting fixtures and two fire alarm devices.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Lighting Fixture · picks (3000,0) (9000,0) (15000,0) (21000,0) · keys Escape Escape · fields — · expect Lighting Fixtures +4",
  "ribbon:Systems:Fire Alarm Point · picks (0,500) (24000,500) · keys Escape Escape · fields — · expect Fire Alarm Devices +2"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Lighting Fixture · picks (3000,0) (9000,0) (15000,0) (21000,0) · keys Escape Escape · fields — · expect Lighting Fixtures +4` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (3000,0) mm at px (703.8,427.0) on the plan view \| (9000,0) mm at px (815.5,427.0) on the plan view \| (15000,0) mm at px (927.2,427.0) on the plan view \| (21000,0) mm at px (1038.8,427.0) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +4": Lighting Fixtures 0 -> 4 (+4, expected +4) |
| `ribbon:Systems:Fire Alarm Point · picks (0,500) (24000,500) · keys Escape Escape · fields — · expect Fire Alarm Devices +2` | green: pressed 'Fire Alarm Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Fire Alarm Point'; the press stood 162 ms (the menu stood at 53 ms; its row ran 21 ms; it made 0 child widgets native)): the tool 'Fire Alarm Point' stands \| picks: (0,500) mm at px (648.0,417.7) on the plan view \| (24000,500) mm at px (1094.7,417.7) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Fire Alarm Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fire Alarm Devices +2": Fire Alarm Devices 0 -> 2 (+2, expected +2) |

### The result

The model holds: Fire Alarm Devices 2,Levels 2,Lighting Fixtures 4,Lighting Fixtures Tags 4,Tags 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3084. Draw a 300 mm cable tray, take it back, then bring it back again.

- Starts from: a new Electrical project
- Ends with: One 300 mm cable tray, drawn, undone and redone.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Cable Tray · picks (0,0) (9000,0) · keys Escape Escape · fields Options Strip: Width=300; Height=100; Offset=3000 · expect Cable Trays +1",
  "qa:Undo · picks — · keys — · fields — · expect Cable Trays -1",
  "qa:Redo · picks — · keys — · fields — · expect Cable Trays +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Cable Tray · picks (0,0) (9000,0) · keys Escape Escape · fields Options Strip: Width=300; Height=100; Offset=3000 · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| fields: Width=300 reads '300 mm'; Height=100 reads '100 mm'; Offset=3000 reads '3000 mm' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (9000,0) mm at px (815.5,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 0 -> 1 (+1, expected +1) |
| `qa:Undo · picks — · keys — · fields — · expect Cable Trays -1` | green: QToolButton pressed; a command ran Check "Cable Trays -1": Cable Trays 1 -> 0 (-1, expected -1) |
| `qa:Redo · picks — · keys — · fields — · expect Cable Trays +1` | green: QToolButton pressed; a command ran Check "Cable Trays +1": Cable Trays 0 -> 1 (+1, expected +1) |

### The result

The model holds: Cable Trays 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3085. Put four luminaires in a room and schedule them by type with a count.

- Starts from: a new Electrical project
- Ends with: Four lighting fixtures and a Luminaire Schedule.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Lighting Fixture · picks (1500,1500) (4500,1500) (1500,4500) (4500,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Lighting Fixture · picks (1500,1500) (4500,1500) (1500,4500) (4500,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +4` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (1500,1500) mm at px (675.9,399.1) on the plan view \| (4500,1500) mm at px (731.7,399.1) on the plan view \| (1500,4500) mm at px (675.9,343.3) on the plan view \| (4500,4500) mm at px (731.7,343.3) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +4": Lighting Fixtures 0 -> 4 (+4, expected +4) |

```json
ops_run {"lines":[
  "op:add schedule category=\"Lighting Fixtures\" fields=Type,Count name=\"Luminaire Schedule\" itemize=no"
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category="Lighting Fixtures" fields=Type,Count name="Luminaire Schedule" itemize=no` | green: op:add schedule made=8ad8ed22a3e64be8a6854f2d9ee6ea7d changed= ms=8 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Lighting Fixtures 4,Lighting Fixtures Tags 4,Tags 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 3086. Run two conduits 500 mm apart and delete the lower one.

- Starts from: a new Electrical project
- Ends with: One conduit left at y = 500.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Conduit · picks (0,0) (8000,0) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=2800 · expect Conduits +1",
  "ribbon:Systems:Conduit · picks (0,500) (8000,500) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=2800 · expect Conduits +1",
  "plan:select · picks (4000,0) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Conduits -1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Conduit · picks (0,0) (8000,0) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=2800 · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| fields: Diameter=25 reads '25 mm'; Offset=2800 reads '2800 mm' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (8000,0) mm at px (796.9,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Conduit · picks (0,500) (8000,500) · keys Escape Escape · fields Options Strip: Diameter=25; Offset=2800 · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| fields: Diameter=25 reads '25 mm'; Offset=2800 reads '2800 mm' \| picks: (0,500) mm at px (648.0,417.7) on the plan view \| (8000,500) mm at px (796.9,417.7) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 1 -> 2 (+1, expected +1) |
| `plan:select · picks (4000,0) · keys — · fields — · expect 1 selected` | green: select: (4000,0) mm at px (722.4,427.0) on the plan view; picked 'conduit-c2d7635bd2189264'; selected 0 -> 1 [conduit-c2d7635bd2189264] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (conduit-c2d7635bd2189264) (expected exactly 1) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Conduits -1` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Conduits -1": Conduits 2 -> 1 (-1, expected -1) |

### The result

The model holds: Conduits 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3087. Draw a 450 mm cable tray 10 m long and copy it 1 m north.

- Starts from: a new Electrical project
- Ends with: Two 450 mm trays 1 m apart.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Cable Tray · picks (0,0) (10000,0) · keys Escape Escape · fields Options Strip: Width=450; Height=100; Offset=3000 · expect Cable Trays +1",
  "plan:select · picks (5000,0) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Copy · picks (0,0) (0,1000) · keys Return · fields — · expect Cable Trays +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Cable Tray · picks (0,0) (10000,0) · keys Escape Escape · fields Options Strip: Width=450; Height=100; Offset=3000 · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| fields: Width=450 reads '450 mm'; Height=100 reads '100 mm'; Offset=3000 reads '3000 mm' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (10000,0) mm at px (834.1,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 0 -> 1 (+1, expected +1) |
| `plan:select · picks (5000,0) · keys — · fields — · expect 1 selected` | green: select: (5000,0) mm at px (741.1,427.0) on the plan view; picked 'tray-bc4f583cd4c05541'; selected 0 -> 1 [tray-bc4f583cd4c05541] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (tray-bc4f583cd4c05541) (expected exactly 1) |
| `ribbon:Modify:Copy · picks (0,0) (0,1000) · keys Return · fields — · expect Cable Trays +1` | green: pressed 'Copy' on Modify's Modify panel (through its fold): the tool 'Copy' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (0,1000) mm at px (648.0,408.4) on the plan view \| presses to the tool 2 (the tool ended on the press), selection changed \| keys: Return (no tool -> tool Copy, nothing standing to end) Check "Cable Trays +1": Cable Trays 1 -> 2 (+1, expected +1) |

### The result

The model holds: Cable Trays 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3088. Run a 300 mm cable tray down a 20 m corridor, hang six luminaires under it and put two light switches at the ends.

- Starts from: a new Electrical project
- Ends with: A cable tray, six lighting fixtures and two switch points.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Cable Tray · picks (0,0) (20000,0) · keys Escape Escape · fields Options Strip: Width=300; Height=100; Offset=3000 · expect Cable Trays +1",
  "ribbon:Systems:Lighting Fixture · picks (2000,0) (5500,0) (9000,0) (12500,0) (16000,0) (19000,0) · keys Escape Escape · fields — · expect Lighting Fixtures +6",
  "ribbon:Systems:Switch Point · picks (0,800) (20000,800) · keys Escape Escape · fields — · expect Lighting Devices +2"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Cable Tray · picks (0,0) (20000,0) · keys Escape Escape · fields Options Strip: Width=300; Height=100; Offset=3000 · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| fields: Width=300 reads '300 mm'; Height=100 reads '100 mm'; Offset=3000 reads '3000 mm' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (20000,0) mm at px (1020.2,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Lighting Fixture · picks (2000,0) (5500,0) (9000,0) (12500,0) (16000,0) (19000,0) · keys Escape Escape · fields — · expect Lighting Fixtures +6` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (2000,0) mm at px (685.2,427.0) on the plan view \| (5500,0) mm at px (750.4,427.0) on the plan view \| (9000,0) mm at px (815.5,427.0) on the plan view \| (12500,0) mm at px (880.6,427.0) on the plan view \| (16000,0) mm at px (945.8,427.0) on the plan view \| (19000,0) mm at px (1001.6,427.0) on the plan view \| presses to the tool 6, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +6": Lighting Fixtures 0 -> 6 (+6, expected +6) |
| `ribbon:Systems:Switch Point · picks (0,800) (20000,800) · keys Escape Escape · fields — · expect Lighting Devices +2` | green: pressed 'Switch Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Switch Point'; the press stood 243 ms (the menu stood at 18 ms; its row ran 210 ms; it made 0 child widgets native)): the tool 'Switch Point' stands \| picks: (0,800) mm at px (648.0,412.1) on the plan view \| (20000,800) mm at px (1020.2,412.1) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Switch Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Devices +2": Lighting Devices 0 -> 2 (+2, expected +2) |

### The result

The model holds: Cable Trays 1,Levels 2,Lighting Devices 2,Lighting Fixtures 6,Lighting Fixtures Tags 6,Tags 6,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3089. Draw a 6 x 5 m meeting room and place a space in it that is heated and cooled for twelve people.

- Starts from: a new Mechanical project
- Ends with: Four meeting room walls and one space set to Heated and cooled with twelve people.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=\"Level 1\"",
  "op:add wall from=(6000,0) to=(6000,5000) level=\"Level 1\"",
  "op:add wall from=(6000,5000) to=(0,5000) level=\"Level 1\"",
  "op:add wall from=(0,5000) to=(0,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level="Level 1"` | green: op:add wall made=wall-8e26c4888f5216ed changed= ms=4 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,5000) level="Level 1"` | green: op:add wall made=wall-1f6dfc9490b1edec changed=wall-8e26c4888f5216ed ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,5000) to=(0,5000) level="Level 1"` | green: op:add wall made=wall-13deba677af4f84c changed=wall-1f6dfc9490b1edec ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level="Level 1"` | green: op:add wall made=wall-57e4b9e4dba4a8c6 changed=wall-8e26c4888f5216ed,wall-13deba677af4f84c ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Space · picks (3000,2500) · keys Escape Escape · fields Options Strip: Condition Type=Heated and cooled; People=12 · expect Spaces +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Space · picks (3000,2500) · keys Escape Escape · fields Options Strip: Condition Type=Heated and cooled; People=12 · expect Spaces +1` | green: pressed 'Space' on Systems's Spaces & Zones panel (through its fold): the tool 'Space' stands \| fields: Condition Type=Heated and cooled reads 'Heated and cooled'; People=12 reads '12.00' \| picks: (3000,2500) mm at px (703.8,380.5) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Space -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Spaces +1": Spaces 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Spaces 1,Walls 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 3090. Draw an 8 x 6 m office, run a supply duct through it with two diffusers and place a space.

- Starts from: a new Architectural project
- Ends with: Four office walls, a supply duct with two diffusers and a space.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add duct from=(500,3000) to=(7500,3000) level=Ground width=400 height=200 elevation=2700",
  "op:add terminal at=(2500,3000) level=Ground",
  "op:add terminal at=(5500,3000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-6aa0ac9232c290d8 changed= ms=490 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-02d1795cc5708b2e changed=wall-6aa0ac9232c290d8 ms=35 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-5669a027c9ddcdc3 changed=wall-02d1795cc5708b2e ms=11 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-7a72f01067819aa9 changed=wall-6aa0ac9232c290d8,wall-5669a027c9ddcdc3 ms=33 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add duct from=(500,3000) to=(7500,3000) level=Ground width=400 height=200 elevation=2700` | green: op:add duct made=duct-3073e16ad873a907,system-de7bea98a0e42d87 changed= ms=16 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(2500,3000) level=Ground` | green: op:add terminal made=terminal-ae03c29b8f1daf64 changed=system-de7bea98a0e42d87 ms=4 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(5500,3000) level=Ground` | green: op:add terminal made=terminal-b2074f74bd8a35f4 changed=system-de7bea98a0e42d87 ms=3 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Space · picks (4000,1500) · keys Escape Escape · fields — · expect Spaces +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Space · picks (4000,1500) · keys Escape Escape · fields — · expect Spaces +1` | green: pressed 'Space' on Systems's Spaces & Zones panel (through its fold): the tool 'Space' stands \| picks: (4000,1500) mm at px (765.3,383.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Space -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Spaces +1": Spaces 0 -> 1 (+1, expected +1) |

### The result

The model holds: Air Terminals 2,Duct Systems 1,Ducts 1,Levels 3,Spaces 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 3091. Draw a 9 x 6 m room with a ceiling at 3000 mm and run a supply duct above it with three diffusers.

- Starts from: a new Architectural project
- Ends with: Four walls, a ceiling at 3000 mm and a supply duct with three diffusers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(9000,0) level=Ground",
  "op:add wall from=(9000,0) to=(9000,6000) level=Ground",
  "op:add wall from=(9000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add ceiling boundary=(0,0) (9000,0) (9000,6000) (0,6000) level=Ground height=3000",
  "op:add duct from=(500,3000) to=(8500,3000) level=Ground width=400 height=200 elevation=2750",
  "op:add terminal at=(1500,3000) level=Ground",
  "op:add terminal at=(4500,3000) level=Ground",
  "op:add terminal at=(7500,3000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(9000,0) level=Ground` | green: op:add wall made=wall-12d51a090002e790 changed= ms=362 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,6000) level=Ground` | green: op:add wall made=wall-d46a3fef6659152d changed=wall-12d51a090002e790 ms=118 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(9000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-a0ae1b88100f9cc3 changed=wall-d46a3fef6659152d ms=40 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-8837702101453ae6 changed=wall-a0ae1b88100f9cc3,wall-12d51a090002e790 ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add ceiling boundary=(0,0) (9000,0) (9000,6000) (0,6000) level=Ground height=3000` | green: op:add ceiling made=ceiling-77b83db00870d960 changed= ms=26 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |
| `op:add duct from=(500,3000) to=(8500,3000) level=Ground width=400 height=200 elevation=2750` | green: op:add duct made=duct-8c0981df0231b9f4,system-d63f12350072ccb4 changed= ms=4 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(1500,3000) level=Ground` | green: op:add terminal made=terminal-4ef6b076020a16d1 changed=system-d63f12350072ccb4 ms=3 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(4500,3000) level=Ground` | green: op:add terminal made=terminal-49f2c4adb73c1b67 changed=system-d63f12350072ccb4 ms=4 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(7500,3000) level=Ground` | green: op:add terminal made=terminal-f4180ca673b10da6 changed=system-d63f12350072ccb4 ms=3 Check "Air Terminals +1": Air Terminals 2 -> 3 (+1, expected +1) |

### The result

The model holds: Air Terminals 3,Ceilings 1,Duct Systems 1,Ducts 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 3092. Draw a 6 x 5 m boiler room with a boiler and a pump in it and run hydronic flow and return pipes out through the east wall.

- Starts from: a new Architectural project
- Ends with: Four plant room walls, two pieces of equipment and a hydronic flow pipe and return pipe.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,5000) level=Ground",
  "op:add wall from=(6000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground",
  "op:add equipment at=(1500,2500) level=Ground elevation=0",
  "op:add equipment at=(3500,2500) level=Ground elevation=0",
  "op:add pipe from=(2300,2000) to=(9000,2000) level=Ground diameter=65 elevation=1200 system=\"Hydronic Supply\"",
  "op:add pipe from=(2300,3000) to=(9000,3000) level=Ground diameter=65 elevation=1200 system=\"Hydronic Return\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-4d0501b033c2618f changed= ms=451 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,5000) level=Ground` | green: op:add wall made=wall-48e713e4dd8960ba changed=wall-4d0501b033c2618f ms=114 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-3a3bc4b2cf6c9a95 changed=wall-48e713e4dd8960ba ms=11 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-08b479dce74ebaff changed=wall-3a3bc4b2cf6c9a95,wall-4d0501b033c2618f ms=6 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add equipment at=(1500,2500) level=Ground elevation=0` | green: op:add equipment made=equipment-3f5b1aae06522870 changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add equipment at=(3500,2500) level=Ground elevation=0` | green: op:add equipment made=equipment-4eb07987b29963c2 changed= ms=3 Check "Mechanical Equipment +1": Mechanical Equipment 1 -> 2 (+1, expected +1) |
| `op:add pipe from=(2300,2000) to=(9000,2000) level=Ground diameter=65 elevation=1200 system="Hydronic Supply"` | green: op:add pipe made=pipe-bc3d7fecde39d50f,system-0b9297a2cd424a56 changed= ms=5 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(2300,3000) to=(9000,3000) level=Ground diameter=65 elevation=1200 system="Hydronic Return"` | green: op:add pipe made=pipe-2980636da76cd691,system-7ceb487e5d7a5ae8 changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Mechanical Equipment 2,Pipes 2,Piping Systems 2,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 3093. Draw a 9 x 6 m office with a ceiling at 3000 mm and put six sprinklers in it on a 3 m grid with a branch line above.

- Starts from: a new Architectural project
- Ends with: Four walls, a ceiling, two sprinkler branch pipes and six sprinklers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(9000,0) level=Ground",
  "op:add wall from=(9000,0) to=(9000,6000) level=Ground",
  "op:add wall from=(9000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add ceiling boundary=(0,0) (9000,0) (9000,6000) (0,6000) level=Ground height=3000",
  "op:add pipe from=(500,1500) to=(8500,1500) level=Ground diameter=32 elevation=3200 system=\"Fire Protection Wet\"",
  "op:add pipe from=(500,4500) to=(8500,4500) level=Ground diameter=32 elevation=3200 system=\"Fire Protection Wet\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(9000,0) level=Ground` | green: op:add wall made=wall-1574985510c2a82c changed= ms=116 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,6000) level=Ground` | green: op:add wall made=wall-32fa6f5821ee11eb changed=wall-1574985510c2a82c ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(9000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-da7bd234185359d5 changed=wall-32fa6f5821ee11eb ms=13 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-b90b1c1facc4100e changed=wall-1574985510c2a82c,wall-da7bd234185359d5 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add ceiling boundary=(0,0) (9000,0) (9000,6000) (0,6000) level=Ground height=3000` | green: op:add ceiling made=ceiling-8bbd063d7054d53d changed= ms=11 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(500,1500) to=(8500,1500) level=Ground diameter=32 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-f1d2f2e1fedf21b3,system-97f85b0bbeefe8a9 changed= ms=4 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(500,4500) to=(8500,4500) level=Ground diameter=32 elevation=3200 system="Fire Protection Wet"` | green: op:add pipe made=pipe-5c9ee7784ed9cccb,system-2a90aa71cc167298 changed= ms=4 Check "Pipes +1 and Piping Systems +1": Pipes 1 -> 2 (+1, expected +1); [green] Piping Systems 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Sprinkler · picks (1500,1500) (4500,1500) (7500,1500) · keys Escape Escape · fields Options Strip: Offset=2900 · expect Sprinklers +3",
  "ribbon:Systems:Sprinkler · picks (1500,4500) (4500,4500) (7500,4500) · keys Escape Escape · fields Options Strip: Offset=2900 · expect Sprinklers +3"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Sprinkler · picks (1500,1500) (4500,1500) (7500,1500) · keys Escape Escape · fields Options Strip: Offset=2900 · expect Sprinklers +3` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=2900 reads '2900 mm' \| picks: (1500,1500) mm at px (692.0,383.0) on the plan view \| (4500,1500) mm at px (780.0,383.0) on the plan view \| (7500,1500) mm at px (868.0,383.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +3": Sprinklers 0 -> 3 (+3, expected +3) |
| `ribbon:Systems:Sprinkler · picks (1500,4500) (4500,4500) (7500,4500) · keys Escape Escape · fields Options Strip: Offset=2900 · expect Sprinklers +3` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=2900 reads '2900 mm' \| picks: (1500,4500) mm at px (692.0,295.0) on the plan view \| (4500,4500) mm at px (780.0,295.0) on the plan view \| (7500,4500) mm at px (868.0,295.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +3": Sprinklers 3 -> 6 (+3, expected +3) |

### The result

The model holds: Ceilings 1,Levels 3,Pipes 2,Piping Systems 2,Sprinklers 6,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 3094. Draw a 9 x 6 m office with a ceiling at 2700 mm and put six luminaires in it on a 3 m grid.

- Starts from: a new Architectural project
- Ends with: Four walls, a ceiling and six lighting fixtures.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(9000,0) level=Ground",
  "op:add wall from=(9000,0) to=(9000,6000) level=Ground",
  "op:add wall from=(9000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add ceiling boundary=(0,0) (9000,0) (9000,6000) (0,6000) level=Ground height=2700"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(9000,0) level=Ground` | green: op:add wall made=wall-2544fc39b2262735 changed= ms=306 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,6000) level=Ground` | green: op:add wall made=wall-b743feec258cd89a changed=wall-2544fc39b2262735 ms=6 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(9000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-4fd1f7a90d80d622 changed=wall-b743feec258cd89a ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-ed7687240885cb38 changed=wall-4fd1f7a90d80d622,wall-2544fc39b2262735 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add ceiling boundary=(0,0) (9000,0) (9000,6000) (0,6000) level=Ground height=2700` | green: op:add ceiling made=ceiling-ddac7d2deee26185 changed= ms=15 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Lighting Fixture · picks (1500,1500) (4500,1500) (7500,1500) (1500,4500) (4500,4500) (7500,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +6"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Lighting Fixture · picks (1500,1500) (4500,1500) (7500,1500) (1500,4500) (4500,4500) (7500,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +6` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (1500,1500) mm at px (692.0,383.0) on the plan view \| (4500,1500) mm at px (780.0,383.0) on the plan view \| (7500,1500) mm at px (868.0,383.0) on the plan view \| (1500,4500) mm at px (692.0,295.0) on the plan view \| (4500,4500) mm at px (780.0,295.0) on the plan view \| (7500,4500) mm at px (868.0,295.0) on the plan view \| presses to the tool 6, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +6": Lighting Fixtures 0 -> 6 (+6, expected +6) |

### The result

The model holds: Ceilings 1,Levels 3,Lighting Fixtures 6,Lighting Fixtures Tags 6,Tags 6,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 3095. Draw a 6 x 4 m toilet block, put four fixtures along the north wall and run a 100 mm sanitary pipe behind them.

- Starts from: a new Architectural project
- Ends with: Four toilet block walls, four plumbing fixtures and a 100 mm sanitary pipe.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-11a3b6c077939579 changed= ms=497 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-9ce66121db9d019a changed=wall-11a3b6c077939579 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-b685ac1dc37f9c2a changed=wall-9ce66121db9d019a ms=97 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-1d239b4dc9d82eb2 changed=wall-b685ac1dc37f9c2a,wall-11a3b6c077939579 ms=9 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Plumbing Fixture · picks (750,3400) (2250,3400) (3750,3400) (5250,3400) · keys Escape Escape · fields — · expect Plumbing Fixtures +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Plumbing Fixture · picks (750,3400) (2250,3400) (3750,3400) (5250,3400) · keys Escape Escape · fields — · expect Plumbing Fixtures +4` | green: pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands \| picks: (750,3400) mm at px (670.0,327.3) on the plan view \| (2250,3400) mm at px (714.0,327.3) on the plan view \| (3750,3400) mm at px (758.0,327.3) on the plan view \| (5250,3400) mm at px (802.0,327.3) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Fixtures +4": Plumbing Fixtures 0 -> 4 (+4, expected +4) |

```json
ops_run {"lines":[
  "op:add pipe from=(300,3800) to=(5700,3800) level=Ground diameter=100 elevation=0 system=\"Sanitary\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(300,3800) to=(5700,3800) level=Ground diameter=100 elevation=0 system="Sanitary"` | green: op:add pipe made=pipe-e308c3503f087555,system-073de77e4e29c155 changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Pipes 1,Piping Systems 1,Plumbing Fixtures 4,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 3096. Draw a 5 x 4 m server room, put two cooling units in it and run a supply duct with two diffusers across it.

- Starts from: a new Architectural project
- Ends with: Four server room walls, two cooling units and a supply duct with two diffusers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(5000,0) level=Ground",
  "op:add wall from=(5000,0) to=(5000,4000) level=Ground",
  "op:add wall from=(5000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground",
  "op:add equipment at=(600,600) level=Ground elevation=0",
  "op:add equipment at=(600,3400) level=Ground elevation=0",
  "op:add duct from=(1500,2000) to=(4500,2000) level=Ground width=400 height=200 elevation=2600",
  "op:add terminal at=(2300,2000) level=Ground",
  "op:add terminal at=(3700,2000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(5000,0) level=Ground` | green: op:add wall made=wall-045cfc372d6d772e changed= ms=265 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(5000,0) to=(5000,4000) level=Ground` | green: op:add wall made=wall-6dfdc08434c4eeab changed=wall-045cfc372d6d772e ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(5000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-b9ec97c6648d1912 changed=wall-6dfdc08434c4eeab ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-1d0f4c46d5784b4c changed=wall-b9ec97c6648d1912,wall-045cfc372d6d772e ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add equipment at=(600,600) level=Ground elevation=0` | green: op:add equipment made=equipment-0a887008d9c8fe5e changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add equipment at=(600,3400) level=Ground elevation=0` | green: op:add equipment made=equipment-d0ebf43b6c325be0 changed= ms=1 Check "Mechanical Equipment +1": Mechanical Equipment 1 -> 2 (+1, expected +1) |
| `op:add duct from=(1500,2000) to=(4500,2000) level=Ground width=400 height=200 elevation=2600` | green: op:add duct made=duct-0d1db5bc54da8359,system-77787bd774f0d3ea changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(2300,2000) level=Ground` | green: op:add terminal made=terminal-eff9aec3e9ab3364 changed=system-77787bd774f0d3ea ms=2 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(3700,2000) level=Ground` | green: op:add terminal made=terminal-abf1a19a0488d500 changed=system-77787bd774f0d3ea ms=2 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |

### The result

The model holds: Air Terminals 2,Duct Systems 1,Ducts 1,Levels 3,Mechanical Equipment 2,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 3097. Draw a 7 x 5 m plant room with an air handling unit, run its supply duct east and a chilled water flow pipe beside it.

- Starts from: a new Architectural project
- Ends with: Four plant room walls, an air handling unit, a supply duct and a hydronic supply pipe.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(7000,0) level=Ground",
  "op:add wall from=(7000,0) to=(7000,5000) level=Ground",
  "op:add wall from=(7000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground",
  "op:add equipment at=(2000,2500) level=Ground elevation=0",
  "op:add duct from=(3300,2000) to=(11000,2000) level=Ground width=600 height=300 elevation=2700 system=\"Supply Air\"",
  "op:add pipe from=(3300,3200) to=(11000,3200) level=Ground diameter=80 elevation=2400 system=\"Hydronic Supply\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(7000,0) level=Ground` | green: op:add wall made=wall-b4ed7cdda26f4641 changed= ms=9 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(7000,0) to=(7000,5000) level=Ground` | green: op:add wall made=wall-eb871ad78d7993b3 changed=wall-b4ed7cdda26f4641 ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(7000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-de89bb47ef193c95 changed=wall-eb871ad78d7993b3 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-5d3facb9ef73b049 changed=wall-b4ed7cdda26f4641,wall-de89bb47ef193c95 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add equipment at=(2000,2500) level=Ground elevation=0` | green: op:add equipment made=equipment-1c0386403292a687 changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add duct from=(3300,2000) to=(11000,2000) level=Ground width=600 height=300 elevation=2700 system="Supply Air"` | green: op:add duct made=duct-1a86405d37f7d0e3,system-596c38ddae8a5939 changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(3300,3200) to=(11000,3200) level=Ground diameter=80 elevation=2400 system="Hydronic Supply"` | green: op:add pipe made=pipe-54124d5a9c63f52d,system-0657a9ce9672560e changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

### The result

The model holds: Duct Systems 1,Ducts 1,Levels 3,Mechanical Equipment 1,Pipes 1,Piping Systems 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 3098. Draw an 8 x 6 m office with a ceiling at 2800 mm and put four luminaires and four sprinklers in it, alternating on a 2 m by 3 m grid.

- Starts from: a new Architectural project
- Ends with: Four walls, a ceiling, four lighting fixtures and four sprinklers.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add ceiling boundary=(0,0) (8000,0) (8000,6000) (0,6000) level=Ground height=2800"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-f9677a23df0862bb changed= ms=12 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-2d62cda7e1a8fdf1 changed=wall-f9677a23df0862bb ms=56 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-6c19571bb0452005 changed=wall-2d62cda7e1a8fdf1 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-6a38172049b69cd0 changed=wall-6c19571bb0452005,wall-f9677a23df0862bb ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add ceiling boundary=(0,0) (8000,0) (8000,6000) (0,6000) level=Ground height=2800` | green: op:add ceiling made=ceiling-d9484ea1a4363d10 changed= ms=5 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Lighting Fixture · picks (2000,1500) (6000,1500) (2000,4500) (6000,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +4",
  "ribbon:Systems:Sprinkler · picks (4000,1500) (4000,4500) (1000,3000) (7000,3000) · keys Escape Escape · fields Options Strip: Offset=2700 · expect Sprinklers +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Lighting Fixture · picks (2000,1500) (6000,1500) (2000,4500) (6000,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +4` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (2000,1500) mm at px (706.7,383.0) on the plan view \| (6000,1500) mm at px (824.0,383.0) on the plan view \| (2000,4500) mm at px (706.7,295.0) on the plan view \| (6000,4500) mm at px (824.0,295.0) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +4": Lighting Fixtures 0 -> 4 (+4, expected +4) |
| `ribbon:Systems:Sprinkler · picks (4000,1500) (4000,4500) (1000,3000) (7000,3000) · keys Escape Escape · fields Options Strip: Offset=2700 · expect Sprinklers +4` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| fields: Offset=2700 reads '2700 mm' \| picks: (4000,1500) mm at px (765.3,383.0) on the plan view \| (4000,4500) mm at px (765.3,295.0) on the plan view \| (1000,3000) mm at px (677.3,339.0) on the plan view \| (7000,3000) mm at px (853.3,339.0) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +4": Sprinklers 0 -> 4 (+4, expected +4) |

### The result

The model holds: Ceilings 1,Levels 3,Lighting Fixtures 4,Lighting Fixtures Tags 4,Sprinklers 4,Tags 4,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 3099. Draw a 20 m corridor with its two walls and stack a duct, a pipe and a cable tray down it at different heights.

- Starts from: a new Architectural project
- Ends with: Two corridor walls, a supply duct at 2700 mm, a cold water pipe at 2400 mm and a cable tray at 2900 mm.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,-1200) to=(20000,-1200) level=Ground",
  "op:add wall from=(0,1200) to=(20000,1200) level=Ground",
  "op:add duct from=(0,-600) to=(20000,-600) level=Ground width=500 height=250 elevation=2700 system=\"Supply Air\"",
  "op:add pipe from=(0,0) to=(20000,0) level=Ground diameter=50 elevation=2400 system=\"Domestic Cold Water\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,-1200) to=(20000,-1200) level=Ground` | green: op:add wall made=wall-6a3fff133ff67480 changed= ms=303 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(0,1200) to=(20000,1200) level=Ground` | green: op:add wall made=wall-b861ed2428cac30d changed= ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add duct from=(0,-600) to=(20000,-600) level=Ground width=500 height=250 elevation=2700 system="Supply Air"` | green: op:add duct made=duct-8794fc9f20cf0565,system-524f026dc707959a changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(0,0) to=(20000,0) level=Ground diameter=50 elevation=2400 system="Domestic Cold Water"` | green: op:add pipe made=pipe-7d5cfd34d1ce58e4,system-5d3644a866e132e4 changed= ms=5 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Systems:Cable Tray · picks (0,600) (20000,600) · keys Escape Escape · fields Options Strip: Width=300; Height=100; Offset=2900 · expect Cable Trays +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Cable Tray · picks (0,600) (20000,600) · keys Escape Escape · fields Options Strip: Width=300; Height=100; Offset=2900 · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| fields: Width=300 reads '300 mm'; Height=100 reads '100 mm'; Offset=2900 reads '2900 mm' \| picks: (0,600) mm at px (648.0,409.4) on the plan view \| (20000,600) mm at px (1234.7,409.4) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 0 -> 1 (+1, expected +1) |

### The result

The model holds: Cable Trays 1,Duct Systems 1,Ducts 1,Levels 3,Pipes 1,Piping Systems 1,Walls 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

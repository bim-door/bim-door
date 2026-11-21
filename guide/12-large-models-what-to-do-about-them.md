# 12. Large models: what to do about them


In this part: what drives the cost, and what to do about it.

**What costs**

- With the 3D view in front, every write rebuilds it.

**What to do**

- Edit with a plan view in front: `views_list {}`, then `view_activate` the plan by its id (a name two views share is refused). Show the 3D view once after a run of writes with `view_activate {"view":"{3D}"}`, then take several pictures with `view_camera` and `view_image`.
- Send 25 to 35 op lines per `ops_run` on a big model; the tool takes up to 500.

Look it up: `document_info {"categories":true}`; `views_list {}`; `get_guide {"part":"guide > 6. See your work"}` for part 6 (See your work).

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.

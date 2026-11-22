---
name: set-direction
description: Guide the user on what objectives to acquire based on the context provided and allow him to select those which he deems worth pursuing. 
metadata:
  version: 1.3.0
  author: egrzeszczak
---

# Skill: `set-direction`

### Description

A direction is a defined set of objectives with similar propevrties. Guide the user on what objectives to acquire based on the context provided. Allow the user to select those which he deems worth pursuing. 

### Arguments

|Name|Requirement|Description|
|-|:-:|-|
|`context`|REQUIRED|User has established `context` using `/establish-context` skill in this plugin and now wants this skill to suggest direction for the project based on his provided `context`.|
|`text`|OPTIONAL|Text that the user has provided as input. May contain additional information. This argument is implied because anything the user inputs is considered content for the argument `text`.|

### Outputs

|Name|Description|
|-|-|
|`DIRECTION.js`|Structurized direction in compliance with the direction data model available in `resources/data-models/direction/model.md` (available by invoking the `/use-shared-resources` skill in this plugin), preferably stored in projects memory and returned to the user in chat as well.|

### Procedure

1. Check if user has provided the `context`.
1. If the user hasn't provided the `context`, check if `context` is already stored in memory (`CONTEXT.json`) file.
1. If there is no `context` available, return an error `To set direction a context is REQUIRED. Ask me how to establish context and invoke /how-to-manage-risks to learn more.`
1. Analyze the `context` and `text` provided by the user, and based on the `context` and `text` suggest:
    1. **5 directions** (objective group) with **4 objective suggestions** each, with one to fill out by the user himself if he wants 
    1. **Display these suggestions as a set of multiselect options** for the user to select from.
    1. User selects the objective suggestions and sends them as a reply to the skill.
    1. **List the suggestions out** to the user
    1. **Provide a file `DIRECTION.json` with the selected possible objectives** structured in the direction data model available in `resources/data-models/direction/model.md` (available by invoking the `/use-shared-resources` skill in this plugin).
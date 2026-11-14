---
name: set-direction
description: A helper skill that will guide the user on what objectives to set.
metadata:
  version: 1.1.2
  author: egrzeszczak
---

# Skill: `set-direction`

### Description

A helper skill that will guide the user on what objectives to set. A direction is a defined set of objectives. Objectives can overlap a couple of directions.

### Arguments

|Name|Requirement|Description|
|-|:-:|-|
|`context`|REQUIRED|User has established `context` using `/establish-context` skill in this plugin and now wants the skill to suggest direction for the project based on his provided `context`.|

### Usage

1. Check if user has provided the `context`.
1. If the user hasn't provided the `context`, check if `context` is already stored in memory (`CONTEXT.json`) file.
1. If there is no `context` available, return an error `To set direction a context is REQUIRED. Ask me how to establish context and invoke /how-to-manage-risks to learn more.`
1. Analyze the `context` provided by the user, and based on the `context` suggest:
    1. **5 directions** (objective group) with **4 objective suggestions** each, with one to fill out by the user himself if he wants 
    1. These suggestions should be a multiselect option fo the user.
    1. User selects the objcetive suggestions and sends them as a reply.
    1. List the suggestions out to the user as well as provide a file `DIRECTION.json` with the selected possible objectives structured in the direction data model available in `direction_data_model.md`** (available by invoking the `/use-shared-resources` skill in this plugin).
---
name: establish-context
description: Allows the user to structurize detailed information about the project into context in JSON format for risk management purposes.
metadata:
  version: 1.2.2
  author: egrzeszczak
---

# Skill: `establish-context`

### Description

Allows the user to structurize detailed information about the project into context in JSON format for risk management purposes.

### Arguments

|Name|Requirement|Description|
|-|:-:|-|
|`text`|REQUIRED|User provides `text` containing information about the project. This can be long and detailed or short and condensed, however MUST NOT be empty. This argument is implied because anything the user inputs is considered content for the argument `text`. The user can with the text also provide his previous `CONTEXT.json` file as a reference.|

### Outputs

|Name|Description|
|-|-|
|`CONTEXT.js`|Structurized context in compliance with the context data model available in `context_data_model.md` (available by invoking the `/use-shared-resources` skill in this plugin), preferably stored in projects memory and returned to the user in chat as well.|

### Procedure

1. Take the `text` provided by the user and **check if the information provided in the `text` loosely answers questions asked in `help_on_establishing_context.md`** (available by invoking the `/use-shared-resources` skill in this plugin).
1. If it does loosely answer the questions:
    1. **Structurize the context** in compliance with the context data model available in `context_data_model.md`** (available by invoking the `/use-shared-resources` skill in this plugin).
    1. **Return a CONTEXT.json** file containing the structurized context.
1. If it does NOT loosely answer the questions (too vague or too little information provided):
    1. **Structurize the context anyway** in compliance with the context data model available in `context_data_model.md`** (available by invoking the `/use-shared-resources` skill in this plugin).
    1. **Return a CONTEXT.json** file containing the structurized context anyway.
    1. **Return a warning to the user** that insufficient information has been provided. 
    1. **Suggest which questions should the user answer** to make the context more detailed.
1. **Store the `CONTEXT.json` in the project's memory** if possible. Replace the existing `CONTEXT.json` if it already exists.
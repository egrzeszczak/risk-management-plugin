---
name: establish-context
description: A skill to use by the model to structurize the context into a JSON data model from information given my the user. 
metadata:
  version: 1.1.1
  author: egrzeszczak
---

# Skill: `establish-context`

### Description

A skill to use by the model to structurize the context into a JSON data model from information given my the user.

### Arguments

|Name|Requirement|Description|
|-|:-:|-|
|`text`|REQUIRED|User provides `text` containing information about the project. This can be long and detailed or short and condensed, however MUST NOT be empty.|

### Usage

1. Take the `text` provided by the user and **check if the information provided in the `text` loosely answers questions asked in `help_on_establishing_context.md`** (available by invoking the `/use-shared-resources` skill in this plugin).
1. If it does loosely answer the questions:
    1. **Structurize the context** in compliance with the context data model available in `context_data_model.md`** (available by invoking the `/use-shared-resources` skill in this plugin).
    1. **Return a CONTEXT.json** file containing the structurized context.
1. If it does NOT loosely answer the questions (too vague or too little information provided):
    1. **Structurize the context anyway** in compliance with the context data model available in `context_data_model.md`** (available by invoking the `/use-shared-resources` skill in this plugin).
    1. **Return a CONTEXT.json** file containing the structurized context anyway.
    1. **Return a warning to the user** that insufficient information has been provided. 
    1. **Suggest which questions should the user answer** to make the context more detailed.
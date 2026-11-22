---
name: help
description: A skill to use by the model to explain each step of the risk management process to the user and which skills to use next. Use when the user asks how to proceed with risk management steps or when user asks how to use this plugin in the first place.
metadata:
  version: 1.3.0
  author: egrzeszczak
---

# Skill: `help`

### Description

A skill to use by the model to explain each step of the risk management process to the user and which skills to use next. Use when the user asks how to proceed with risk management steps or when user asks how to use this plugin in the first place.

### Arguments

There are neither required arguments nor optional arguments required for this skill.

### Outputs

|Name|Description|
|-|-|
|`text`|Skill returns the text it was asked to provide in the procedure steps.|

### Procedure

* If user wants to know the general information about the plugin itself or has just invoked `/help` without additional information, present the contents of `resources/wiki/about.md` document (available by invoking the `/use-shared-resources` skill in this plugin) to the user. 
    * You MUST present the contents of the file and you MUSTN'T modify the content when digesting and displaying to the user.

* If user wants to start the risk management process, the first thing he establish is the `context`. On how to establish a context present the contents of `resources/wiki/establishing-context.md` document (available by invoking the `/use-shared-resources` skill in this plugin) to the user.
    * You MUST present the contents of the file and you MUSTN'T modify the content when digesting and displaying to the user.

* If user has established the `context`, but doesn't know what he wants to achieve, the user then need to select a direction for his project. On how to set the direction present the contents of `resources/wiki/setting-direction.md` document (available by invoking the `/use-shared-resources` skill in this plugin) to the user.
    * You MUST present the contents of the file and you MUSTN'T modify the content when digesting and displaying to the user.

* If user has established the `context` and a `direction`, but hasn't set the objectives for the project, present the contents of `resources/wiki/setting-objectives.md` document (available by invoking the `/use-shared-resources` skill in this plugin) to the user.
    * You MUST present the contents of the file and you MUSTN'T modify the content when digesting and displaying to the user.
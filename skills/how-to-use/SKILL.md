---
name: how-to-use
description: A utility skill to use by the model to explain each step of the risk management process to the user and which skills to use next. Use when the user asks how to proceed with risk management steps.
metadata:
  version: 1.1.0
  author: egrzeszczak
---

# Skill: `how-to-use`

### Description

A utility skill to use by the model to explain each step of the risk management process to the user and which skills to use next. Use when the user asks how to proceed with risk management steps.

### Arguments

There are neither required arguments nor optional arguments required for this skill.

### Usage

If user wants to know the general information about the plugin itself, present the contents of `help_on_plugin.md` document (available by invoking the `/use-shared-resources` skill in this plugin) to the user.

If user wants to start the risk management process, the first thing he establish is the `context`. On how to establish a context present the contents of `help_on_establishing_context.md` document (available by invoking the `/use-shared-resources` skill in this plugin) to the user.

If user has established the `context`, but doesn't know what he wants to achieve, the user then need to select a direction for his project. On how to set the direction present the contents of `help_on_setting_direction.md` document (available by invoking the `/use-shared-resources` skill in this plugin) to the user.

If user has established the `context` and a `direction`, but hasn't set the objectives for the project, present the contents of `help_on_setting_objectives.md` document (available by invoking the `/use-shared-resources` skill in this plugin) to the user.
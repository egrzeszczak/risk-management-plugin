---
name: set-objectives
description: Start the risk management process in the project by structuring the context and objectives into a data model provided by the plugin. Use this skill when the user plans to start a project and is interested in managing risks. The first step is to structure the objectives and context for the second step, which is handled by the skill called 'identify-risks'. 
metadata:
  version: 1.3.2
  author: egrzeszczak
---

# Skill: `set-objectives`

### Description

Answers the first question of the risk management process described in `resources/wiki/risk-management-process.md` (available by invoking the `/use-shared-resources` skill in this plugin). 

This skill takes the `context` and `objectives` (or `direction`) described in the input by the user or available in the project, and structures objectives into the `objective` JSON model in `resources/data-models/objective/model.md` (available by invoking the `/use-shared-resources` skill in this plugin). 

This model will be later used by other skills in this plugin.

### Arguments

|name|requirement|description|
|-|:-:|-|
|`context`|REQUIRED|Contains situation, environment, scope, constraints and any other detailed information about the project. `context` MUST be structed in accordance with `resources/data-models/context/model.md` available by invoking the `/use-shared-resources` skill in this plugin. Usually delivered in a `CONTEXT.json` file.|
|`objectives`|RECOMMENDED|User SHOULD to provide his objectives in natural language to be then parsed into correct model (`resources/data-models/objective/model.md` available by invoking the `/use-shared-resources` skill in this plugin.)|
|`direction`|RECOMMENDED|Contains vauge requirements about what needs to be achieved. Objectives are derived from that argument, if the user has not supplied any standalone objectives on his own while invoking this skill.|

### Procedure

1. Skill MUST use the RFC 2119 standard when processing the user's `objectives`.
1. Analyze provided `objectives` and the `context` supplied by the user. When no objectives have been provided, infer objectives from `direction`. If both objectives and direction are missing, guide the user to use the `set-direction` skill. 
1. If `objectives` is not provided but, the `direction` is provided, the skill MUST then infer the `objectives`  from the `direction` and structure them into a JSON object, in accordance to the model available `resources/data-models/objective/model.md` (available by invoking the `/use-shared-resources` skill in this plugin),
1. If `objectives` is not provided but or `direction` are provided, the skill MUST then structure the objectives into a JSON object, in accordance to the model available `resources/data-models/objective/model.md` (available by invoking the `/use-shared-resources` skill in this plugin),
    * `objective.description` field value MUST be based on the objective that the user has supplied,
    * `objective.name` field value SHOULD be based on the `objective.description` value (basically compacted `objective.description`)
    * `objective.id` field value SHOULD be assigned by the skill sequentially (1, 2, 3, etc.)
    * `objective.priority` field value SHOULD be assigned by the skill, based on the context and the objective implied strength
1. Finally, skill MUST then output the JSON object into a separate file called `OBJECTIVES.json` and return it to the user.
1. The skill has finished the task. User CAN invoke other skills to proceed.
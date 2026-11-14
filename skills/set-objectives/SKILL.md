---
name: set-objectives
description: Start the risk management process in the project by structuring the context and objectives into a data model provided by the plugin. Use this skill when the user plans to start a project and is interested in managing risks. The first step is to structure the objectives and context for the second step, which is handled by the skill called 'identify-risks'. 
metadata:
  version: 1.1.1
  author: egrzeszczak
---

# set-objectives

## description

Answers the first question of the risk management process described in `risk_management_process.md` (available by invoking the `/use-shared-resources` skill in this plugin). This skill takes the `context` and `objectives` described in the input by the user, and structures them into the `context` minified JSON model available in `context_model.md` (available by invoking the `/use-shared-resources` skill in this plugin) and the `objective` minified JSON model in `objective_model.md` (available by invoking the `/use-shared-resources` skill in this plugin). This model will be later used by other skills in this plugin.

## arguments

|name|requirement|description|
|-|:-:|-|
|`objectives`|REQUIRED|contains requirements about what needs to be achieved|
|`context`|REQUIRED|contains situation, environment, scope, constraints and additional information that will be taken into account later on|

## steps

1. skill MUST use the RFC 2119 standard when processing requirements (in other words - the user's `objectives`),
1. skill MUST read and understand the `objectives` and the `context` supplied by the user,
1. skill MUST then structure the context into a minified JSON array, to the model available `context_model.md` (available by invoking the `/use-shared-resources` skill in this plugin),
1. skill MUST then structure the objectives into a minified JSON array, to the model available `objective_model.md` (available by invoking the `/use-shared-resources` skill in this plugin),
    * `objective.description` field value MUST be based on the objective that the user has supplied,
    * `objective.name` field value SHOULD be based on the `objective.description` value (basically compacted `objective.description`)
    * `objective.id` field value SHOULD be assigned by the skill sequentially (1, 2, 3, etc.)
    * `objective.priority` field value SHOULD be assigned by the skill, based on the context and the objective implied strength
1. finally, skill MUST then output the minified JSON array of `objectives` and `context` to the user.
1. the work ends here. skill MUST NOT proceed with the next step. the user needs to invoke the skill himself.
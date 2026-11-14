---
name: identify-risks
description: Identify, describe and categorize risks that may affect a set of objectives within a context. Use whenever the user asks what could go wrong, what might affect objectives, project or plan, or wants a risk register or risk identification. Two required arguments MUST be supplied - objectives and context. The count argument is RECOMMENDED.
metadata:
  version: 1.1.2
  author: egrzeszczak
---

# identify-risks

## description

Answering the second question of the risk management process described in `risk_management_process.md` (available by invoking the `/use-shared-resources` skill in this plugin). Uses the `risk_data_model.md` (available by invoking the `/use-shared-resources` skill in this plugin).

## arguments

|name|requirement|description|
|-|:-:|-|
|`objectives`|REQUIRED|contains requirements about what needs to be achieved. `objectives` MUST be structed in accordance with `objective_model.md` available by invoking the `/use-shared-resources` skill in this plugin|
|`context`|REQUIRED|contains situation, environment, scope, constraints. `context` MUST be structed in accordance with `context_model.md` available by invoking the `/use-shared-resources` skill in this plugin|
|`count`|RECOMMENDED|SHOULD be provided. `count` is the ammount of risks to infer by the skill. by default the count is 10.|

## steps

1. the skill MUST NOT change the objectives (Q1) or the context, assess or rank risks (Q3), plan strategies (Q4), review the risks (Q5) or update risks (Q6). the scope of the skill is only identifying the risks (Q2).
1. if a required argument is missing, vague or not compliant with the format, the skill MUST ask the user before continuing. 
1. the skill MUST NOT assume missing required arguments.
1. if the optional argument is missing or vague, the skill SHOULD use the default value provided for the argument inside the skill.
1. analyze and understand the `objectives`, `context`, and `count` arguments.
1. think of <`count`> risks that relate to the `objectives`.
1. list out risks in correct JSON format available in `risk_model.md` (available by invoking the `/use-shared-resources` skill in this plugin) in a JSON array to the user.
1. the work ends here. skill MUST NOT proceed with the next step. the user needs to invoke the skill himself.

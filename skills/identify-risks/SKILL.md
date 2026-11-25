---
name: identify-risks
description: Identify, describe and categorize risks that may affect a set of objectives within a context. Use whenever the user asks what could go wrong, what might affect objectives, project or plan, or wants a risk register or risk identification. Two required arguments MUST be supplied, objectives and context. The count argument is OPTIONAL.
metadata:
  version: 1.3.4
  author: egrzeszczak
---

# Skill: `identify-risks`

### Description

Identify, describe and categorize risks that may affect a set of `objectives` within a `context`. Use whenever the user asks what could go wrong, what might affect objectives, project or plan, or wants a risk register or risk identification. Two required arguments MUST be supplied - `objectives` and `context`. The count argument is OPTIONAL.

This skill should answer the second question of the risk management process described in `resources/wiki/risk-management-process.md` (available by invoking the `/use-shared-resources` skill in this plugin), which is "What might affect my objectives?". Uses the `resources/data-models/risk/model.md` (available by invoking the `/use-shared-resources` skill in this plugin).

### Arguments

|name|requirement|description|
|-|:-:|-|
|`objectives`|REQUIRED|contains requirements about what needs to be achieved. `objectives` MUST be structed in accordance with `resources/data-models/objective/model.md` available by invoking the `/use-shared-resources` skill in this plugin. Usually delivered in a `OBJECTIVES.json` file.|
|`context`|REQUIRED|Contains situation, environment, scope, constraints and any other detailed information about the project. `context` MUST be structed in accordance with `resources/data-models/context/model.md` available by invoking the `/use-shared-resources` skill in this plugin. Usually delivered in a `CONTEXT.json` file.|
|`count`|OPTIONAL|The ammount of risks to infer by the skill. <br><br> DEFAULT VALUE: 10.|
|`scoring`|REQUIRED|Scoring usually provided in a `SCORING.json`|

### Procedure

1. If `scoring` is not provided or present in the `SCORING.json` file, the skill should invoke the `set-scoring-system` skill and ask it to use the default settings.
1. The skill MUST NOT change the `objectives` (Q1) or the `context`, assess or rank risks (Q3), plan strategies (Q4), review the risks (Q5) or update risks (Q6). The scope of the skill is only identifying the risks (Q2).
1. If a required argument is missing, vague or not compliant with the format, the skill MUST warn the user before continuing. 
1. The skill MUST NOT assume missing required arguments.
1. If the optional argument is missing or vague, the skill SHOULD use the default value provided for the argument inside the skill.
1. Analyze the `objectives`, `context`, and `count` arguments.
1. Infer n (n=`count`) ammount of risks that impact given `objectives`. The infered risk should follow the model described in `resources/data-models/context/model.md` available by invoking the `/use-shared-resources` skill in this plugin. Fields to infer are `risk.id`, `risk.name`, `risk.description`, and `risk.impacts`.
1. Save each risk into a JSON file into the projects memory if possible, return each file to the user. The name of the file should be the same as the risk identifier (`risk.id`), for example `RISK-15.json`. 
1. The skill has finished the task. User CAN invoke other skills to proceed.

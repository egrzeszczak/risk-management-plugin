---
name: set-scoring-system
description: Skill that creates a custom scoring system for objective priorities, risk probability and risk impact definitions.
metadata:
  version: 1.3.3
  author: egrzeszczak
---

# Skill: `set-scoring-system`

### Description

Skill that creates a custom scoring system for objective priorities, risk probability and risk impact definitions.

### Arguments

|Name|Requirement|Description|
|-|:-:|-|
|`text`|OPTIONAL|User CAN request help on how to score or provide additional instructions on what scoring system he would like for the project to use when invoking this skill.|

### Procedure

1. The process of creating a scoring system SHOULD NOT take more than one inference. Read how the scoring model SHOULD look like `resources/data-models/context/scoring/model.md` available by invoking the `use-shared-resources` skill.
1. If user has invoked the skill without any additinal instructions or has specified to use the default values: 
    1. Copy the exact contents of `resources/data-models/context/scoring/default/SCORING.json` available by invoking the `use-shared-resources` skill into `SCORING.json` file and return it to the user.
    1. The skill has finished the task. You MUSTN'T proceed further with the procedure.
1. If user has provided instructions on how to create the scoring, the skill SHOULD use labeling provided by the user. However it is RECOMMENDED that the user provide labeling the schema for:
    1. **objective priority** scoring mapping in `scoring.objective`,
    1. **risk impact** scoring mapping in `scoring.impact`, 
    1. and **risk probability** mapping in `scoring.probability`
1. If user has not provided labeling or scoring for either objective, impact or probabilities, the skill SHOULD copy the default values from `resources/data-models/context/scoring/default/SCORING.json` available by invoking the `use-shared-resources` skill for missing mappings.
1. Finally, skill MUST then output the scoring system into a separate file called `SCORING.json` and return it to the user.
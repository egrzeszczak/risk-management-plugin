---
name: use-shared-resources
description: Internal utility skill, that is invoked by other skills in this plugin to share resources, specifically Markdown documents containing instructions, data models, examples, etc.
metadata:
  version: 1.3.0
  author: egrzeszczak
---

# Skill: `use-shared-resources`

### Description

Internal utility skill, that is invoked by other skills in this plugin to share resources, specifically Markdown documents containing instructions, data models, examples, etc.

### Arguments

|Name|Requirement|Description|
|-|:-:|-|
|`resource_name`|RECOMMENDED|Skill SHOULD know and provide the name of the file it wants to fetch.|

### Procedure

1. Check the `resource_name` against the contents in the `resources/` directory. 
1. Return that resource if it exists. If not, throw an error `"Missing resource. The plugin's creator is at fault here. Raise an issue at https://github.com/egrzeszczak/risk-management-plugin/issues"`
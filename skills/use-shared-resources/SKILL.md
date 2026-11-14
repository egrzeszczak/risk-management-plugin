---
name: use-shared-resources
description: Internal utility skill for the plugin used by others skills. Mainly used to fetch resources shared across the plugin. When there is a reference to a shared resource, the skill will invoke this skill to get the information it needs. 
metadata:
  version: 1.0.4
  author: egrzeszczak
---

# use-shared-resources

## description

this skill is invoked by other skills in this plugin to use shared resources across the plugin.

## arguments

|name|requirement|description|
|-|:-:|-|
|`resource`|RECOMMENDED|skill provides the name of the file|

## steps

1. check the resource in the `resources/` directory the skill is asking for,
1. return the data the skill is requesting.
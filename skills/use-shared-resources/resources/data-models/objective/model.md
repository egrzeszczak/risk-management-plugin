# Data Model: `objective`

The common model for the objectives.

## Structure

|Field name|Type|Description|
|-|-|-|
|`objective.id`|keyword|A unique id for the objective. The id consists of a prefix `OBJ` and a unique number `n`.<br><br>example: `OBJ-1`, `OBJ-252`, `OBJ-150`, `OBJ-n`|
|`objective.name`|text|Short name for the objective.<br><br>example: "To keep the know-how secret"|
|`objective.description`|text|Description for the objective.<br><br>example: "Our know-how MUST be kept secret, since this is how we achieve our other goals, such as securing stable income. If the know-how is revealed to the public, it would have a significant impact on our project."|
|`objective.priority`|keyword|Priority of the objectives.<br><br>RECOMMENDED values: `highest`, `high`, `medium`, `low`, `lowest`<br>example: `highest`|

## examples

### example A

```json
[{"objective.id":"OBJ-4","objective.name":"Know-how MUST be kept secret","objective.description":"Our know-how MUST be kept secret, since this is how we achieve our other goals, such as securing stable income. If the know-how is revealed to the public, it would have a significant impact on our project.","objective.priority":"highest"}]
```

### example B

```json
[{"objective.id":"OBJ-1","objective.name":"ability MUST NOT be disclosed","objective.description":"the ability MUST NOT be disclosed to anyone under any circumstances. we MUST NOT leave anything that identifies our identity, and MUST NOT say or do anything that raises questions or suggests we possess the ability. no organisation SHOULD ever discover the ability.","objective.priority":"highest"},{"objective.id":"OBJ-2","objective.name":"safe travel to popular cities","objective.description":"we SHOULD travel safely to the most popular cities in the world (tokyo, new york, los angeles, etc.).","objective.priority":"medium"}]
```
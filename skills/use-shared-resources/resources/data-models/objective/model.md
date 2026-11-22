# Data Model: `objective`

The model for a objective.

## Structure

|Field name|Type|Description|
|-|-|-|
|`type`|keyword|The type of the object. <br><br>REQUIRED VALUE: "objective"|
|`objective.id`|keyword|A unique id for the objective. The id consists of a prefix `OBJ` and a unique number `n`.<br><br>EXAMPLE VALUES: `OBJ-1`, `OBJ-252`, `OBJ-150`|
|`objective.name`|text|Short name for the objective.<br><br>EXAMPLE VALUE: "To keep the know-how secret"|
|`objective.description`|text|Description for the objective.<br><br>EXAMPLE VALUE: "Our know-how MUST be kept secret, since this is how we achieve our other goals, such as securing stable income. If the know-how is revealed to the public, it would have a significant impact on our project."|
|`objective.priority`|keyword|Priority of the objectives.<br><br>RECOMMENDED values: `critical`, `high`, `medium`, `low`, `lowest`<br>example: `critical`|

## examples

### example A

```json
[{"objective.id":"OBJ-4","objective.name":"Know-how MUST be kept secret","objective.description":"Our know-how MUST be kept secret, since this is how we achieve our other goals, such as securing stable income. If the know-how is revealed to the public, it would have a significant impact on our project.","objective.priority":"critical"}]
```

### example B

```json
[{"objective.id":"OBJ-1","objective.name":"ability MUST NOT be disclosed","objective.description":"the ability MUST NOT be disclosed to anyone under any circumstances. we MUST NOT leave anything that identifies our identity, and MUST NOT say or do anything that raises questions or suggests we possess the ability. no organisation SHOULD ever discover the ability.","objective.priority":"critical"},{"objective.id":"OBJ-2","objective.name":"safe travel to popular cities","objective.description":"we SHOULD travel safely to the most popular cities in the world (tokyo, new york, los angeles, etc.).","objective.priority":"medium"}]
```
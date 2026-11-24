# Data Model: `objective`

The model for an objective.

### Structure

|Field name|Type|Description|
|-|-|-|
|`type`|keyword|The type of the object. <br><br>REQUIRED VALUE: "objective"|
|`objective.id`|keyword|A unique id for the objective. The id consists of a prefix `OBJ` and a unique number `n`.<br><br>EXAMPLE VALUES: `OBJ-1`, `OBJ-252`, `OBJ-150`|
|`objective.name`|text|Short name for the objective.<br><br>EXAMPLE VALUE: "To keep the know-how secret"|
|`objective.description`|text|Description for the objective.<br><br>EXAMPLE VALUE: "Our know-how MUST be kept secret, since this is how we achieve our other goals, such as securing stable income. If the know-how is revealed to the public, it would have a significant impact on our project."|
|`objective.priority`|keyword|Priority of the objectives.<br><br>RECOMMENDED values: `critical`, `high`, `medium`, `low`, `lowest`<br>example: `critical`|

### Example

#### A

```json
[
    {
        "type": "objective",
        "objective": {
            "id": "OBJ-4",
            "name": "Know-how MUST be kept secret",
            "description": "Our know-how MUST be kept secret, since this is how we achieve our other goals, such as securing stable income. If the know-how is revealed to the public, it would have a significant impact on our project.",
            "priority": "critical"
        }
    }
]
```
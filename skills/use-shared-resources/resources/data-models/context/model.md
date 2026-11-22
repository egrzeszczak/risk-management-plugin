# Data model: `context`

Data model for the `context` object used in risk management process.

### Structure

The table below defined the field names, types and describes each field.
|Name|Type|Description|
|-|-|-|
|`type`|string|Data model type.<br><br>REQUIRED VALUES: `context`|
|`context`|array of strings|An array of texts describing the context. The more concise and descriptive the information the better. Quantity does not mean quality.<br><br>EXAMPLE VALUES: `["upgrading red hat from version 8 to version 9", "working in the high-availablity environment", "operating systems are management by ansible", "upgrading a non-production system", "system is running in the 'dev' evironment"]`|

### Examples

#### A
```json
[{
    "type": "context", 
    "context": [
        "upgrading red hat from version 8 to version 9", 
        "working in the high-availablity environment", 
        "operating systems are managed by ansible", 
        "upgrading a non-production system", 
        "system is running in the 'dev' evironment", 
        "no change acceptance board approval required"
    ]
}]
```

#### B

```json
[{
    "type": "context", 
    "context": [
        "risk management excercise", 
        "ability to teleport anywhere on earth, at any time", 
        "teleport is impossible to space, earth only", 
        "trigger: squeeze right ring finger, close eyes, think of the destination", 
        "teleport requires no energy", 
        "destination must have been visited in person or seen via live video", 
        "a picture is not enough to teleport", 
        "ability is currently known only to me"
    ]
}]
`````
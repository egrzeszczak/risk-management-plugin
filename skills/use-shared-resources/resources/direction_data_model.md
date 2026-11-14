# Data model: `direction`

Data model for the `direction` object used in risk management process.

### Structure

The table below defined the field names, types and describes each field.
|Name|Type|Description|
|-|-|-|
|`type`|string|Data model type.<br><br>REQUIRED VALUES: `direction`|
|`direction`|array of strings|An array of texts describing the possible objectives. The more concise and descriptive the information the better. Quantity does not mean quality.<br><br>EXAMPLE VALUES: `["red hat upgrade from version 8 to version 9 MUST BE successful", "high-availablity environment MUST be created", "the update SHOULD BE performed via ansible", "rollback MUST be available after update"]`|

### Examples

#### A
```json
[{
    "type": "direction", 
    "direction": [
        "red hat upgrade from version 8 to version 9 MUST BE successful", 
        "high-availablity environment MUST be created", 
        "the update SHOULD BE performed via ansible", 
        "rollback MUST be available after update"
    ]
}]
```
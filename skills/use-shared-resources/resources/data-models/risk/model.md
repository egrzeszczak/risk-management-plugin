# Data Model: `risk`

The model for the risk object.

### Structure

|Field|Type|Description|
|-|-|-|
|`type`|keyword|Type of the object. <br><br>REQUIRED VALUE: `risk`|
|`risk.id`|keyword|A unique identifier for the risk. It consists of a prefix `RISK` and a unique number `n`.<br><br>EXAMPLE VALUES: `RISK-1`, `RISK-252`, `RISK-150`|
|`risk.name`|text|A short description of the risk. SHOULD be one sentence.<br><br>EXAMPLE VALUE: "Accidental disclosure via screen-share"|
|`risk.description`|text|Description for the risk.<br><br>EXAMPLE VALUE: "Sharing your screen in a meeting could result in unintentional information exposure about the project"|
|`risk.impacts`|array of keywords|Array of unique identifiers of objectives that this risk has an effect on.<br><br>EXAMPLE VALUES: `OBJ-4`, `OBJ-1`, `OBJ-14`|

### Example

```json
{
    "type": "risk",
    "risk": {
        "id": "RISK-4",
        "name": "Accidental disclosure via screen-share",
        "description": "Sharing your screen in a meeting could result in unintentional information exposure about the project",
        "impacts": ["OBJ-1", "OBJ-2", "OBJ-3"]
    }
}
```
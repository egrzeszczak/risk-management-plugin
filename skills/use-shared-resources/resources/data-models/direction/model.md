# Data Model: `direction`

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

#### B
```json
[{
    "type": "direction",
    "direction": [
        "authentication logs MUST reach on-prem from Azure Event Hub without loss",
        "the pipeline MUST handle about 1 TB per day, with headroom for growth",
        "the pipeline SHOULD recover automatically from outages and replay missed events",
        "delivery delay SHOULD stay within an agreed limit",
        "logs MUST be searchable through a data analysis platform",
        "the log structure MUST be discovered and documented before the design is finalized",
        "logs SHOULD be transformed into a consistent format using JavaScript",
        "business analytics use cases SHOULD be supported (for example dashboards and reports)",
        "logs MUST be retained and searchable for at least 5 years",
        "log integrity MUST be preserved (tamper-evident or immutable storage)",
        "authorities MUST be able to get controlled, read-only access to search the logs",
        "legal retention requirements SHOULD be confirmed with the relevant legal or compliance owner",
        "data MUST be encrypted in transit and at rest",
        "access to the logs MUST be restricted and audited",
        "sensitive content in the logs SHOULD be identified and protected once a sample has been reviewed",
        "the data SHOULD support security monitoring (for example detecting suspicious authentication activity)",
        "the solution MUST be operational as soon as possible, with an agreed first milestone",
        "total cost MUST stay within about 500K USD per year",
        "the solution MUST be operable by one person (automation, monitoring, documentation)",
        "the solution SHOULD be assembled from market solutions that fit a JavaScript-based toolset"
    ]
}]
```
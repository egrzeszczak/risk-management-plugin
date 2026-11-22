# Data model: `context`

Data model for the `context` object used in risk management process.

### Structure

The table below defined the field names, types and describes each field.
|Name|Type|Description|
|-|-|-|
|`type`|string|Data model type.<br><br>REQUIRED VALUES: `context`|
|`context`|array of strings|An array of texts describing the context. The more concise and descriptive the information the better. Quantity does not mean quality.<br><br>EXAMPLE VALUES: `["upgrading red hat from version 8 to version 9", "working in the high-availablity environment", "operating systems are management by ansible", "upgrading a non-production system", "system is running in the 'dev' evironment"]`|

### Examples

#### A (insufficient details)
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

#### B (insufficient details)

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
```

#### C (sufficient details)

```json
[{
    "type": "context",
    "context": [
        "tasked with creating a simple data stream solution",
        "one source data stream containing logs of client authentication with X509 certificates",
        "stream is owned by and important to the Security Team",
        "source: stream is fetched from Azure Event Hub (cloud)",
        "logs are currently saved to Azure Blob Storage, and saving is already in progress",
        "destination: on-prem infrastructure",
        "data leaving the cloud has been approved by the manager",
        "considering a log filter/router solution combined with a data analysis platform to enable searching the data later",
        "no decision yet on the filter/router or analysis platform, the solution must be built from solutions available on the market",
        "log transformation capability in code is recommended",
        "preferred toolset is JavaScript, as other technology in use also relies on JavaScript",
        "log volume is about 1 TB per day",
        "log structure is unknown, could be structured or unstructured, and nobody on the team has seen the logs",
        "purposes: business analytics, security and legal requirements",
        "logs must be searchable by the team and by authorities for at least 5 years",
        "budget is about 500K USD per year",
        "one person (the requester) builds the solution and will run it afterwards",
        "urgency: needs to be set up as soon as possible"
    ]
}]
```
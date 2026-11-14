# `context` data model

common model for the context object used in risk management process

## structure

|Field name|Type|Description|
|-|-|-|
|`context.data`|array of text|An array of texts describing the context. The more concise and descriptive the information the better. Quantity does not mean quality.<br><br>example: `["upgrading red hat from version 8 to version 9", "working in the high-availablity environment", "operating systems are management by ansible", "upgrading a non-production system", "system is running in the 'dev' evironment"]`|

## examples

### example A

```json
[{"context.data": ["upgrading red hat from version 8 to version 9", "working in the high-availablity environment", "operating systems are management by ansible", "upgrading a non-production system", "system is running in the 'dev' evironment"]}]
```

### example B

```json
[{"context.data":["risk management excercise", "ability to teleport anywhere on earth, at any time","teleport is impossible to space, earth only","trigger: squeeze right ring finger, close eyes, think of the destination","teleport requires no energy","destination must have been visited in person or seen via live video","a picture is not enough to teleport","ability is currently known only to us"]}]
```
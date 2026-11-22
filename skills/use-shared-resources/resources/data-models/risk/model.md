# Data Model: `risk`

The common model for the risk.

## Structure

|Field name|Type|Description|
|-|-|-|
|`risk.id`|keyword|A unique id for the risk.<br>The id consists of a prefix `RISK` and a unique number `n`<br><br>example: `RISK-1`, `RISK-252`, `RISK-150`, `RISK-n`|
|`risk.name`|text|Short name for the risk.<br><br>example: "Accidental disclosure via voicechat"|
|`risk.description`|text|Description for the risk.<br><br>example: "A significant impact will apply to objectives, if anyone with the knowledge of the know-how mentions any details of it during a voice call."|
|`risk.impacts_objectives`|array of keywords|Which objective id does the risk relate to.<br><br>RECOMMENDED values: `highest`, `high`, `medium`, `low`, `lowest`<br>example: `highest`|

## examples

### example A

```json
[{"risk.id":"RISK-4","risk.name":"Accidental disclosure via voicechat","risk.description":"A significant impact will apply to objectives, if anyone with the knowledge of the know-how mentions any details of it during a voice call.","risk.impacts_objectives":["OBJ-2","OBJ-6"]}]
```

### example B
```json
[{"risk.id":"RISK-1","risk.name":"teleport witnessed in person","risk.description":"a person sees us appear or vanish, e.g. on arrival in a crowded city or when leaving a spot.","risk.impacts_objectives":["OBJ-1","OBJ-2"]},{"risk.id":"RISK-2","risk.name":"teleport captured on camera","risk.description":"cctv, phone, dashcam or live stream records us appearing or disappearing, and the footage is analysed or goes viral.","risk.impacts_objectives":["OBJ-1","OBJ-2","OBJ-3"]}]
```
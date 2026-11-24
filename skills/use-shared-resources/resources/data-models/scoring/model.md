# Data Model: `scoring` 

A qualitative system for scoring objectives, risk impacts and risk probabilities. Usually stored in `SCORING.json`

### Structure

|Field name|Type|Description|
|-|-|-|
|`type`|keyword|The type of the object. <br><br>REQUIRED VALUE: "scoring"|
|`scoring.objective`|object|Scoring of the importance of objectives. The higher the numer the more imporant the objective is. <br><br>EXAMPLE VALUE: `{"critical": 5, "significant": 4, ...}`|
|`scoring.impact`|object|Scoring for risk impact. The higher the numer the higher the effect on objectives.<br><br>EXAMPLE VALUE: `{"severe": 5, "substantial": 4, ...}`|
|`scoring.probability`|object|Scoring for risk probability. The higher the number the higher chances of an event happening.<br><br>EXAMPLE VALUE: `{"high": 3, "medium": 2, "low": 1}`|

### Default

```json
{
    "type": "scoring",
    "scoring": {
        "objective": {
            "high": 3,
            "medium": 2,
            "low": 1
        },
        "impact": {
            "severe": 5,
            "substancial": 4,
            "moderate": 3,
            "limited": 2,
            "minor": 1
        },
        "probability": {
            "certain": 5,
            "lilely": 4,
            "possible": 3,
            "unlikely": 2,
            "rare": 1
        }
    }
}
```
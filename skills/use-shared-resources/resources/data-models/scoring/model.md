# Data Model: `scoring` 

A qualitative system for scoring objectives, risk impacts and risk probabilities. Usually stored in `SCORING.json`

### Structure

|Field name|Type|Description|
|-|-|-|
|`type`|keyword|The type of the object. <br><br>REQUIRED VALUE: "scoring"|
|`scoring.objective`|array of objects|Scoring of the importance of objectives. The higher the numer the more imporant the objective is.|
|`scoring.impact`|array of objects|Scoring for risk impact. The higher the numer the higher the effect on objectives.|
|`scoring.probability`|array of objects|Scoring for risk probability. The higher the number the higher chances of an event happening.|

### Rules

1. IMPORTANT! The keys of the object for `scoring.objective`, `scoring.impact` and `scoring.probability` in this model SHOULD match the /[a-z_]+/ regular expression. It is NOT RECOMMENDED to use any other characters in the keys of the object.

### Example

```json
{
    "type": "scoring",
    "scoring": {
        "objective": [
            {
                "key": "high",
                "score": 5 
            },
            {
                "key": "medium",
                "score": 3
            },
            {
                "key": "low",
                "score": 1
            }
        ],
        "impact": [
            {
                "name": "severe",
                "score": 5
            },
            {
                "name": "substancial",
                "score": 4
            },
            {
                "name": "moderate",
                "score": 3
            },
            {
                "name": "limited",
                "score": 2
            },
            {
                "name": "minor",
                "score": 1
            }
        ],
        "probability": [
            {
                "name": "certain",
                "score": 5
            },
            {
                "name": "likely",
                "score": 4
            },
            {
                "name": "possible",
                "score": 3
            },
            {
                "name": "unlikely",
                "score": 2
            },
            {
                "name": "rare",
                "score": 1
            }
        ]
    }
}
```
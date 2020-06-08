# Hiscores API

## Endpoint
GET https://deceit-live.baseline.gg/hiscores

## Parameters
`type`: string (required) Either `elo`, `xp` or `rep` - daily XP or reputation highscores respectively.

## Example
https://deceit-live.baseline.gg/hiscores?type=elo

# Return:
200 (OK): JSON array of objects, each object holds the userId, rank and value of the highscore. Currently only returns the top 10.
Example:
```
[
  {
    "userId": 3,
    "rank": 0,
    "value": 79
  }
]
```
400 (Bad Request): JSON object with an `error` field, usually indicates the `type` provided was incorrect.
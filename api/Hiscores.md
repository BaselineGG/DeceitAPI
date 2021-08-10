# Hiscores API

## Endpoint
GET https://live.deceit.gg/hiscores

## Parameters
`type`: string (required) Either `elo`, `xp` or `rep` - daily XP or reputation highscores respectively.

## Example
https://live.deceit.gg/hiscores?type=elo

# Return:
200 (OK): JSON array of objects, each object holds the username, userId, rank and value of the highscore. Currently returns the top 100.

Example:
```JSON
[
  {
    "username": "RakTheGoose",
    "userId": 3,
    "rank": 0,
    "value": 79
  }
]
```

400 (Bad Request): JSON object with an `error` field, usually indicates the `type` provided was incorrect.

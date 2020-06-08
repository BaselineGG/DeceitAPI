# Stats API

## Endpoint
GET https://deceit-live.baseline.gg/stats

## Parameters
`userId`: integer (optional) the players userId .
`steamId`: integer (optional) the players steamID64 (64 bit integer).
Having one of these parameters specified is required.

## Example
https://deceit-live.baseline.gg/stats?userId=10

# Return:
200 (OK): A JSON object containing information about the player.
_TODO: Add more information on the return format of this object._
400 (Bad Request): JSON object with an `error` field, usually indicates the id was malformed or not provided.
404 (Not Found): JSON object with an `error` field, usually indicates the player could not be found.
 
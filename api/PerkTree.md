# Perk Tree API

## Endpoint
GET https://live.deceit.gg/perkTree

## Parameters
`id`: integer (optional) The ID of the perk tree to get.

## Example
https://live.deceit.gg/perkTree?id=3

# Return:
200 (OK): JSON object containing two fields, `id` and `tree`. 
The `tree` field is a 2D array that contains each row of the perk tree and the perks in that row.
Full description on the perks can be found in [perks.json](../resources/perks.json).

Example response:
```JSON
{
    "id": 3,
    "tree":[
        [5],
        [56,13],
        [42,50],
        [19],
        [24,72,69],
        [23,43],
        [67,60,65],
        [37,49,27],
        [7,39],
        [32,30,70],
        [1,40],
        [57,61,66],
        [52,54]
    ]
}
```

400 (Bad Request): JSON object with an `error` field, usually indicates the `id` provided was malformed.

403 (Forbidden): JSON object with an `error` field, usually indicates that the ip is rate limited.

404 (Not Found): JSON object with an `error` field, usually indicates the `id` provided was incorrect.
# Stats API

## Endpoint
GET https://deceit-live.baseline.gg/stats

## Parameters
`userId`: integer (optional) the players userId.

`steamId`: integer (optional) the players steamID64.

**Having one of these parameters specified is required.**

## Example
https://deceit-live.baseline.gg/stats?userId=10

# Return:
200 (OK): A JSON object containing information about the player.

###### Player Structure
| Field       | Type                                                                | Description                                               |
| ----------- | ------------------------------------------------------------------- | --------------------------------------------------------- |
| userId      | unsigned long                                                       | Deceit Id                                                 |
| name        | string                                                              | In-game username                                          |
| elo         | double                                                              | Ranked elo                                                |
| rank        | byte                                                                | Current rank (offset from bronze 20)                      |
| marks       | byte                                                                | Ranked marks (0 if rank is 20)                            |
| experience  | unsigned long                                                       | All-time experience                                       |
| level       | unsigned int                                                        | Current level (Without prestige)                          |  
| prestige    | byte                                                                | Current prestige (max is 9)                               |
| emblem      | unsigned short                                                      | Emblem Id                                                 |
| reputation  | unsigned int                                                        | Reputation                                                |
| dailyXp     | unsigned int                                                        | Experience received today                                 |
| dailyXpRank | unsigned int                                                        | Position on the daily xp leaderboard                      |
| eloRank     | unsigned int                                                        | Position on the elo leaderboard                           |
| repRank     | unsigned int                                                        | Position on the reputation leaderboard                    |
| banner      | byte                                                                | Last season rank (offset from bronze 20)                  |
| character   | [character enum](#character-enum)                                    | Currently selected character                              |
| perks       | unsigned short array                                                | Array of currently selected perk ids                      |
| loadout?    | [character enum](#character-enum) to [loadout](#user-loadout-format) | Key-value pair of character id to an unsigned short array |
| stats?      | [stats struct](#user-stats-structure)                               | User statistics                                           |
###### User Stats Structure
<!---
1) Challenges
2) Game Outcomes
3) Gameplay
4) Miscellaneous
--->
| Field                       | Type          | Description                                |
| --------------------------- | ------------- | ------------------------------------------ |
| s_challenges_completed_0    | unsigned int  | Easy challenges completed                  |
| s_challenges_completed_1    | unsigned int  | Medium challenges completed                |
| s_challenges_completed_2    | unsigned int  | Hard challenges completed                  |
| s_challenges_completed_3    | unsigned int  | Very Hard challenges completed             |
| s_challenge_chips_used_0    | unsigned int  | Challenges shared                          |
| s_challenge_chips_used_1    | unsigned int  | Challenges boosted                         |
| s_challenge_chips_used_2    | unsigned int  | Challenges rerolled                        |
| s_challenge_chips_used_3    | unsigned int  | Challenges extended                        |
| s_challenge_rewards_0       | unsigned int  | XP received from challenges                |
| s_challenge_rewards_1       | unsigned int  | Loot booth tokens received from challenges |
| s_challenge_rewards_2       | unsigned int  | GM credits received from challenges        |
| s_challenge_rewards_4       | unsigned int  | Cosmetics received from challenges         |
| s_challenge_rewards_5       | unsigned int  | Emblems received from challenges           |
| s_challenge_rewards_6       | unsigned int  | Challenge chips received from challenges   |
| s_challenge_rewards_7       | unsigned int  | Event points received from challenges      |
| games_played                | unsigned int  | Total games played                         |
| games_as_innocent           | unsigned int  | Games played as innocent                   |
| escapes                     | unsigned int  | Times escaped                              |
| s_total_wins_inno           | unsigned int  | Total wins as innocent                     |
| failed_escapes              | unsigned int  | Total escapes failed                       |
| s_total_losses_inno         | unsigned int  | Total losses as innocent                   |
| games_as_infected           | unsigned int  | Infected games played                      |
| escapes_prevented           | unsigned int  | Escapes Prevented                          |
| s_total_wins_inf            | unsigned int  | Total wins as infected                     |
| escapes_allowed             | unsigned int  | Innocents escaped from player              |
| s_total_losses_inf          | unsigned int  | Total losses as infected                   |
| innocent_killed_as_infected | unsigned int  | Innocents killed                           |
| s_blood_drank               | unsigned int  | Blood drank                                |
| s_fuses_used                | unsigned int  | Fuses used                                 |
| s_lever_pulled              | unsigned int  | Levers pulled                              |
| s_lever_broke               | unsigned int  | Levers broken                              |
| s_obj_centre                | unsigned int  | Centre objectives taken                    |
| s_obj_shoot                 | unsigned int  | Target practice objectives taken           |
| s_obj_double                | unsigned int  | Double objectives taken                    |
| s_obj_stolen                | unsigned int  | Objectives stolen                          |
| s_executed                  | unsigned int  | Times executed                             |
| s_executions                | unsigned int  | Innocents executed                         |
| s_lethal_correct            | unsigned int  | Players correctly lethaled                 |
| s_lethal_incorrect          | unsigned int  | Incorrectly lethaled players               |
| s_lethald_correct           | unsigned int  | Times correctly lethaled                   |
| s_lethald_incorrect         | unsigned int  | Times lethaled incorrectly                 |
| s_votes_cast                | unsigned int  | Votes cast                                 |
| s_votes_correct             | unsigned int  | Correctly voted out players                |
| s_votes_incorrect           | unsigned int  | Incorrectly voted out players              |
| s_voted_on_correct          | unsigned int  | Times voted out correctly                  |
| s_voted_on_incorrect        | unsigned int  | Times voted out incorrectly                |
| s_times_downed              | unsigned int  | Times downed                               |
| s_downs                     | unsigned int  | Players downed                             |
| down_infected_on_innocent   | unsigned int  | Infected downed as innocent                |
| down_infected_on_infected   | unsigned int  | Infected downed as infected                |
| down_innocent_on_innocent   | unsigned int  | Innocents downed as innocent               |
| down_innocent_on_infected   | unsigned int  | Total downed innocents as infected         |
| s_meters_moved              | unsigned long | Distance travelled in meters               |
| time_played_in_game         | unsigned int  | Time played in-game (in seconds)           |
| s_time_dark                 | unsigned int  | Time spent in dark (in seconds)            |
###### User Loadout Format
| Index | Type  | Description  |
| ----- | ----- | ------------ |
| 0     | short | Hair         |
| 1     | short | Accessory    |
| 2     | short | Clothes      |
| 3     | short | Wristband    |
| 4     | short | Pistol       |
| 5     | short | Knife        |
| 6     | short | Victory Pose |
| 7     | short | Defeat Pose  |
###### Character Enum
| Character  | Value |
| ---------- | ----- |
| Alex       | 0     |
| Chang      | 1     |
| Lisa       | 2     |
| Rachel     | 3     |
| Hans       | 4     |
| Nina       | 5     |
| Experiment | 6     |
| Yeti       | 7     |
| Werewolf   | 8     |
| Vampire    | 9     |

400 (Bad Request): JSON object with an `error` field, usually indicates the id was malformed or not provided.

404 (Not Found): JSON object with an `error` field, usually indicates the player could not be found.
 

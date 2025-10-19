- [← Back to Main Docs](../README.md)

  
# All stats

| **Category**                | **Stat Key**                      | **Description**                 | **Example**                         |
| --------------------------- | --------------------------------- | ------------------------------- | ----------------------------------- |
| **Core**                    | identifier                        | Player unique identifier        | `"license:xyz123"`                  |
|                             | id                                | Player internal ID              | `42`                                |
|                             | name                              | Player name                     | `"JohnDoe"`                         |
|                             | level                             | Player level                    | `4`                                 |
|                             | points                            | Points earned from level        | `300`                               |
|                             | rank                              | Rank, usually same as level     | `4`                                 |
|                             | prestige                          | Current prestige level          | `1`                                 |
|                             | prestigeLabel                     | Display label                   | `"Prestige 1"`                      |
|                             | prestigeIcon                      | Icon path                       | `"html/achievements/prestige1.png"` |
|                             | playtime                          | Total time played (seconds)     | `3600`                              |
|                             | mugshot                           | Player avatar                   | `"default.png"`                     |
| **Combat**                  | kills                             | Player kills                    | `50`                                |
|                             | npcKills                          | NPC kills                       | `15`                                |
|                             | deaths                            | Deaths                          | `5`                                 |
|                             | killstreak                        | Current killstreak              | `3`                                 |
|                             | killstreakLabel                   | Label for killstreak            | `"3 Kills"`                         |
|                             | accuracy                          | Shooting accuracy %             | `78`                                |
|                             | BuffType                          | Active buffs                    | `{ "damageBoost": true }`           |
|                             | headshots                         | Total headshots                 | `20`                                |
|                             | shotsFired                        | Total shots fired               | `1000`                              |
|                             | shotsHit                          | Total shots hit                 | `780`                               |
|                             | duelsWon                          | PvP duels won                   | `12`                                |
| **Economy / Reputation**    | cash                              | Money balance                   | `1200`                              |
|                             | tokens                            | XP points from levels           | `300`                               |
|                             | reputation                        | Total reputation                | `2`                                 |
|                             | reputationTitles                  | Titles unlocked via reputation  | `["Novice","Apprentice"]`           |
|                             | tradesCompleted                   | Successful trades               | `62`                                |
|                             | tradesCancelled                   | Failed trades                   | `5`                                 |
|                             | bountiesClaimed                   | Claimed bounties                | `3`                                 |
|                             | bountiesPlaced                    | Placed bounties                 | `2`                                 |
|                             | businessesOwned                   | Owned businesses                | `1`                                 |
| **Exploration / World**     | distanceTraveled                  | Total distance (meters)         | `15240`                             |
|                             | distanceOnFoot                    | Distance walked                 | `3021`                              |
|                             | distanceDriven                    | Distance driven                 | `8804`                              |
|                             | distanceFlown                     | Distance flown                  | `1415`                              |
|                             | distanceSwum                      | Distance swum                   | `512`                               |
|                             | zonesDiscovered                   | Number of unique zones          | `14`                                |
|                             | vehiclesOwned                     | List of owned vehicles          | `["car1","bike1"]`                  |
|                             | hiddenLocationsFound              | Secrets found                   | `3`                                 |
|                             | explorationXP                     | XP earned from exploring        | `250`                               |
|                             | animalsHunted                     | Number of hunted animals        | `12`                                |
|                             | failedHunts                       | Failed hunts                    | `3`                                 |
| **Crafting / Economy**      | itemsCrafted                      | Crafted items count             | `154`                               |
|                             | itemsFailed                       | Failed crafts                   | `12`                                |
|                             | craftingXP                        | XP earned from crafting         | `890`                               |
|                             | craftingLevel                     | Crafting skill level            | `4`                                 |
|                             | craftingQualityAvg                | Avg. quality of items           | `87.2`                              |
|                             | craftingTimeTotal                 | Total crafting time (seconds)   | `4200`                              |
|                             | bestCraftingStreak                | Longest successful craft streak | `19`                                |
|                             | craftingSkill                     | Crafting skill                  | `42`                                |
|                             | engineeringSkill                  | Engineering / repair skill      | `37`                                |
|                             | lootingSkill                      | Looting / scavenging            | `33`                                |
|                             | miningSkill                       | Mining skill                    | `29`                                |
|                             | fishingSkill                      | Fishing skill                   | `22`                                |
| **Missions / Jobs / Tasks** | missionsCompleted                 | Completed missions              | `7`                                 |
|                             | rewardsClaimed                    | Rewards claimed                 | `6`                                 |
|                             | jobType                           | Job/faction                     | `"Police"`                          |
|                             | jobRank                           | Rank in job                     | `2`                                 |
|                             | gangType                          | Gang/faction                    | `"Families"`                        |
|                             | gangRank                          | Rank in gang                    | `1`                                 |
|                             | tasksCompleted                    | Completed tasks                 | `15`                                |
|                             | objectivesCompleted               | Completed objectives            | `34`                                |
| **Skills**                  | drivingSkill                      | Driving skill level             | `5`                                 |
|                             | survivalSkill                     | Survival skill                  | `3`                                 |
|                             | combatSkill                       | Combat skill                    | `4`                                 |
|                             | defenseSkill                      | Defense skill                   | `3`                                 |
|                             | staminaSkill                      | Stamina                         | `2`                                 |
|                             | stressSkill                       | Stress resistance               | `1`                                 |
|                             | pilotingSkill                     | Piloting / flying skill         | `3`                                 |
|                             | stealthSkill                      | Stealth skill                   | `4`                                 |
| **Last Played Session**     | lastPlayedStats.level             | Level at last session           | `3`                                 |
|                             | lastPlayedStats.kills             | Kills at last session           | `40`                                |
|                             | lastPlayedStats.npcKills          | NPC kills at last session       | `12`                                |
|                             | lastPlayedStats.deaths            | Deaths at last session          | `3`                                 |
|                             | lastPlayedStats.killstreak        | Killstreak at last session      | `2`                                 |
|                             | lastPlayedStats.missionsCompleted | Missions completed              | `5`                                 |
|                             | lastPlayedStats.rewardsClaimed    | Rewards claimed                 | `4`                                 |
| **Meta / Session**          | lastLogin                         | Last login timestamp            | `"2025-10-15 16:00:00"`             |
|                             | loginCount                        | Total sessions played           | `42`                                |
|                             | distanceByVehicleType             | Distance broken by vehicle      | `{car=5200,bike=3600,plane=1400}`   |
|                             | timeInVehicle                     | Seconds in vehicles             | `1800`                              |
|                             | timeOnFoot                        | Seconds walking                 | `1200`                              |
|                             | timeInAir                         | Seconds flying                  | `450`                               |
|                             | timeUnderwater                    | Seconds swimming                | `300`                               |


---


[Top of page](#All-stats)

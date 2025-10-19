- [← Back to Main Docs](../README.md)

  
# 📝 Mobz-Prestiged Player Stats Cheatsheet

| **Stat Key**              | **Example Value**        |
|----------------------------|-------------------------|
| identifier                 | `"license:xyz123"`       |
| id                         | `42`                     |
| name                       | `"JohnDoe"`              |
| level                      | `15`                     |
| points                     | `1450`                   |
| rank                       | `15`                     |
| prestige                   | `2`                      |
| prestigeLabel              | `"Prestige II"`          |
| prestigeIcon               | `"html/achievements/prestige2.png"` |
| playtime                   | `36000`                  |
| mugshot                    | `"mugshots/default.png"` |
| kills                      | `56`                     |
| npcKills                   | `21`                     |
| deaths                     | `12`                     |
| killstreak                 | `4`                      |
| killstreakLabel            | `"4 Kills"`              |
| accuracy                   | `81.2`                   |
| BuffType                   | `{ "damageBoost": true }`|
| headshots                  | `89`                     |
| shotsFired                 | `1000`                   |
| shotsHit                   | `812`                    |
| duelsWon                   | `5`                      |
| cash                       | `12000`                  |
| tokens                     | `250`                    |
| reputation                 | `4`                      |
| reputationTitles           | `["Citizen","Respected"]`|
| tradesCompleted            | `62`                     |
| tradesCancelled            | `3`                      |
| bountiesClaimed            | `5`                      |
| bountiesPlaced             | `2`                      |
| businessesOwned            | `3`                      |
| distanceTraveled           | `25400`                  |
| distanceOnFoot             | `3200`                   |
| distanceDriven             | `15800`                  |
| distanceFlown              | `2400`                   |
| distanceSwum               | `800`                    |
| zonesDiscovered            | `19`                     |
| vehiclesOwned              | `["car1","truck2"]`      |
| hiddenLocationsFound       | `4`                      |
| animalsHunted              | `12`                     |
| failedHunts                | `3`                      |
| itemsCrafted               | `154`                    |
| itemsFailed                | `12`                     |
| craftingXP                 | `890`                    |
| craftingLevel              | `4`                      |
| craftingQualityAvg         | `87.2`                   |
| craftingTimeTotal          | `4200`                   |
| bestCraftingStreak         | `19`                     |
| craftingSkill              | `42`                     |
| engineeringSkill           | `37`                     |
| lootingSkill               | `33`                     |
| miningSkill                | `29`                     |
| fishingSkill               | `22`                     |
| drivingSkill               | `35`                     |
| pilotingSkill              | `19`                     |
| survivalSkill              | `42`                     |
| staminaSkill               | `28`                     |
| defenseSkill               | `31`                     |
| combatSkill                | `46`                     |
| stressSkill                | `25`                     |
| stealthSkill               | `12`                     |
| missionsCompleted          | `7`                      |
| rewardsClaimed             | `6`                      |
| jobType                    | `"Police"`               |
| jobRank                    | `2`                      |
| gangType                   | `"Families"`             |
| gangRank                   | `1`                      |
| tasksCompleted             | `15`                     |
| objectivesCompleted        | `34`                     |
| lastLogin                  | `"2025-10-15 16:00:00"`  |
| loginCount                 | `42`                     |
| timeOnFoot                 | `1200`                   |
| timeInVehicle              | `1800`                   |
| timeInAir                  | `450`                    |
| timeUnderwater             | `300`                    |
| distanceByVehicleType      | `{car=5200,bike=3600,plane=1400}` |
| activeLabels               | `["Sharpshooter","Explorer"]` |
| achievements               | `{1=true,2=false,...}`    |
| titles                     | `["Veteran","Legend"]`    |


### Core
| **Stat Key** | **Description** | **Example** |
|--------------|----------------|------------|
| name | Player display name | `"JohnDoe"` |
| identifier | Unique player identifier (Steam, license, etc.) | `"license:xyz123"` |
| id | Player source ID | `42` |
| level | Player level | `15` |
| points | XP or score | `1450` |
| rank | Rank number (often same as level) | `15` |
| prestige | Prestige tier | `2` |
| prestigeLabel | Prestige display name | `"Prestige II"` |
| prestigeIcon | Prestige badge icon | `"html/achievements/prestige2.png"` |
| playtime | Total seconds played | `36000` |
| mugshot | Avatar or icon | `"mugshots/default.png"` |

### Combat
| **Stat Key** | **Description** | **Example** |
|--------------|----------------|------------|
| kills | Total player kills | `56` |
| npcKills | NPC kills | `21` |
| deaths | Deaths | `12` |
| killstreak | Current killstreak | `4` |
| killstreakLabel | Label for streak | `"4 Kills"` |
| headshots | Successful headshots | `89` |
| shotsFired | Bullets fired | `1000` |
| shotsHit | Bullets that hit targets | `812` |
| accuracy | Shooting accuracy % | `81.2` |
| duelsWon | PvP duels won | `5` |
| BuffType | Active combat buffs | `{ "damageBoost": true }` |

### Economy / Reputation
| **Stat Key** | **Description** | **Example** |
|--------------|----------------|------------|
| cash | Money balance | `12000` |
| tokens | Tokens or prestige points | `250` |
| reputation | Global reputation | `4` |
| reputationTitles | Reputation rank names | `["Citizen","Respected"]` |
| tradesCompleted | Successful trades | `62` |
| tradesCancelled | Cancelled/failed trades | `3` |
| bountiesClaimed | Completed bounty targets | `5` |
| bountiesPlaced | Bounties placed by player | `2` |
| businessesOwned | Businesses owned | `3` |

### Exploration / World
| **Stat Key** | **Description** | **Example** |
|--------------|----------------|------------|
| distanceTraveled | Total distance (m) | `25400` |
| distanceOnFoot | Distance walked | `3200` |
| distanceDriven | Distance driven | `15800` |
| distanceFlown | Distance flown | `2400` |
| distanceSwum | Distance swum | `800` |
| zonesDiscovered | Unique map areas found | `19` |
| vehiclesOwned | Vehicle list | `["car1","truck2"]` |
| hiddenLocationsFound | Secrets found | `4` |
| animalsHunted | Animals successfully hunted | `12` |
| failedHunts | Failed hunting attempts | `3` |

### Crafting / Professions
| **Stat Key** | **Description** | **Example** |
|--------------|----------------|------------|
| itemsCrafted | Crafted items | `154` |
| itemsFailed | Failed crafts | `12` |
| craftingXP | Crafting XP | `890` |
| craftingLevel | Crafting skill level | `4` |
| craftingQualityAvg | Avg. crafted item quality | `87.2` |
| craftingTimeTotal | Total crafting time (seconds) | `4200` |
| bestCraftingStreak | Longest success streak | `19` |
| craftingSkill | Skill in crafting profession | `42` |
| engineeringSkill | Engineering/tech proficiency | `37` |
| lootingSkill | Loot recovery proficiency | `33` |
| miningSkill | Mining efficiency | `29` |
| fishingSkill | Fishing proficiency | `22` |

### Driving / Piloting / Survival
| **Stat Key** | **Description** | **Example** |
|--------------|----------------|------------|
| drivingSkill | Driving experience / XP | `35` |
| pilotingSkill | Flying / piloting experience | `19` |
| survivalSkill | Endurance in wilderness | `42` |
| staminaSkill | Physical stamina | `28` |
| defenseSkill | Defensive combat ability | `31` |
| combatSkill | Overall combat performance | `46` |
| stressSkill | Stress resistance | `25` |
| stealthSkill | Sneaking / stealth ability | `12` |

### Missions / Tasks / Jobs
| **Stat Key** | **Description** | **Example** |
|--------------|----------------|------------|
| missionsCompleted | Finished missions | `7` |
| rewardsClaimed | Claimed mission rewards | `6` |
| jobType | Player job/faction | `"Police"` |
| jobRank | Player rank within job | `2` |
| gangType | Gang/faction type (QB only) | `"Families"` |
| gangRank | Rank in gang | `1` |
| tasksCompleted | Completed small tasks | `15` |
| objectivesCompleted | Objectives achieved | `34` |

### Meta / Session / Utility
| **Stat Key** | **Description** | **Example** |
|--------------|----------------|------------|
| lastLogin | Last login timestamp | `"2025-10-15 16:00:00"` |
| loginCount | Total logins | `42` |
| timeOnFoot | Seconds on foot | `1200` |
| timeInVehicle | Seconds in vehicles | `1800` |
| timeInAir | Seconds flying | `450` |
| timeUnderwater | Seconds swimming | `300` |
| distanceByVehicleType | Breakdown by vehicle type | `{car=5200,bike=3600,plane=1400}` |
| activeLabels | Active buffs/titles list | `["Sharpshooter","Explorer"]` |
| achievements | Table of all unlocked achievements | `{1=true,2=false,...}` |
| titles | Player title list | `["Veteran","Legend"]` |

---


# 📝 Mobz-Prestiged Player Stats Cheatsheet

| **Stat Key**              | **Example Value**        |
|----------------------------|-------------------------|
| identifier                 | `"license:xyz123"`       |
| id                         | `42`                     |
| name                       | `"JohnDoe"`              |
| level                      | `15`                     |
| points                     | `1450`                   |
| rank                       | `15`                     |
| prestige                   | `2`                      |
| prestigeLabel              | `"Prestige II"`          |
| prestigeIcon               | `"html/achievements/prestige2.png"` |
| playtime                   | `36000`                  |
| mugshot                    | `"mugshots/default.png"` |
| kills                      | `56`                     |
| npcKills                   | `21`                     |
| deaths                     | `12`                     |
| killstreak                 | `4`                      |
| killstreakLabel            | `"4 Kills"`              |
| accuracy                   | `81.2`                   |
| BuffType                   | `{ "damageBoost": true }`|
| headshots                  | `89`                     |
| shotsFired                 | `1000`                   |
| shotsHit                   | `812`                    |
| duelsWon                   | `5`                      |
| cash                       | `12000`                  |
| tokens                     | `250`                    |
| reputation                 | `4`                      |
| reputationTitles           | `["Citizen","Respected"]`|
| tradesCompleted            | `62`                     |
| tradesCancelled            | `3`                      |
| bountiesClaimed            | `5`                      |
| bountiesPlaced             | `2`                      |
| businessesOwned            | `3`                      |
| distanceTraveled           | `25400`                  |
| distanceOnFoot             | `3200`                   |
| distanceDriven             | `15800`                  |
| distanceFlown              | `2400`                   |
| distanceSwum               | `800`                    |
| zonesDiscovered            | `19`                     |
| vehiclesOwned              | `["car1","truck2"]`      |
| hiddenLocationsFound       | `4`                      |
| animalsHunted              | `12`                     |
| failedHunts                | `3`                      |
| itemsCrafted               | `154`                    |
| itemsFailed                | `12`                     |
| craftingXP                 | `890`                    |
| craftingLevel              | `4`                      |
| craftingQualityAvg         | `87.2`                   |
| craftingTimeTotal          | `4200`                   |
| bestCraftingStreak         | `19`                     |
| craftingSkill              | `42`                     |
| engineeringSkill           | `37`                     |
| lootingSkill               | `33`                     |
| miningSkill                | `29`                     |
| fishingSkill               | `22`                     |
| drivingSkill               | `35`                     |
| pilotingSkill              | `19`                     |
| survivalSkill              | `42`                     |
| staminaSkill               | `28`                     |
| defenseSkill               | `31`                     |
| combatSkill                | `46`                     |
| stressSkill                | `25`                     |
| stealthSkill               | `12`                     |
| missionsCompleted          | `7`                      |
| rewardsClaimed             | `6`                      |
| jobType                    | `"Police"`               |
| jobRank                    | `2`                      |
| gangType                   | `"Families"`             |
| gangRank                   | `1`                      |
| tasksCompleted             | `15`                     |
| objectivesCompleted        | `34`                     |
| lastLogin                  | `"2025-10-15 16:00:00"`  |
| loginCount                 | `42`                     |
| timeOnFoot                 | `1200`                   |
| timeInVehicle              | `1800`                   |
| timeInAir                  | `450`                    |
| timeUnderwater             | `300`                    |
| distanceByVehicleType      | `{car=5200,bike=3600,plane=1400}` |
| activeLabels               | `["Sharpshooter","Explorer"]` |
| achievements               | `{1=true,2=false,...}`    |
| titles                     | `["Veteran","Legend"]`    |


---
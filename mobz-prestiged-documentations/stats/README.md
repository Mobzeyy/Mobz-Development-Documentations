
* [Back](mobz-prestiged-documentations/README.md)

  
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




# 🏆 Mobz-Prestiged Player Stats Reference

## 1️⃣ MAIN STATS (With Real Logic / Event Hooks)

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

### ✅ NEW EXPORTS SYNCED TO DOCUMENTATION
| **Export Function** | **Description** |
|----------------------|----------------|
| `AddTradeCompleted`, `GetTradesCompleted` | Track successful trades |
| `AddTradeCancelled`, `GetTradesCancelled` | Track cancelled trades |
| `AddBountyClaimed`, `GetBountiesClaimed` | Track claimed bounties |
| `AddBountyPlaced`, `GetBountiesPlaced` | Track placed bounties |
| `AddTaskCompleted`, `GetTasksCompleted` | Track completed tasks |
| `AddObjectiveCompleted`, `GetObjectivesCompleted` | Track objectives |
| `SetAccuracy`, `GetAccuracy` | Manage accuracy % |
| `AddHeadshot`, `AddShotFired`, `AddShotHit`, `AddDuelWon` | Update shooting stats |
| `AddBusinessOwned`, `GetBusinessesOwned` | Track owned businesses |
| `AddCraftedItem`, `AddFailedCraft`, `GetCraftingStats` | Manage crafting progression |
| `AddHuntedAnimal`, `FailedHunt`, `GetHuntingStats` | Manage hunting progression |
| `AddDrivingXP`, `AddDrivingStunt`, `AddDrivingAccident`, `GetDrivingStats` | Manage driving stats |



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

## Adding Dynamic Stat 
##  Mobz-Prestiged Dynamic Stat Example adding: Health

---
##### Using server-side export through:
```lua
local prestigeAPI = exports["mobz-prestiged"]
```
---

## STEP 1: Register the stat on resource start

```lua
AddEventHandler("onResourceStart", function(resourceName)
    if resourceName ~= GetCurrentResourceName() then return end

    -- Register a new dynamic stat called "health"
    prestigeAPI:RegisterStat("health", 100)

    print("^2[Prestiged-Health]^7 Registered dynamic stat: ^3health (default = 100)^7")
end)

-- ==========================================
--  STEP 2: Helper function to get identifier
-- ==========================================
local function GetLicense(source)
    for _, id in ipairs(GetPlayerIdentifiers(source)) do
        if id:find("license:") then
            return id
        end
    end
    return nil
end

-- ==========================================
--  STEP 3: Initialize stat when player joins
-- ==========================================
AddEventHandler("playerJoining", function(source)
    local license = GetLicense(source)
    if not license then return end

    local currentHealth = prestigeAPI:GetStat(license, "health")
    if currentHealth == nil then
        prestigeAPI:SetStat(license, "health", 100)
    end

    print(("[Prestiged-Health] %s joined with health: %d"):format(GetPlayerName(source), currentHealth or 100))
end)

-- ==========================================
--  STEP 4: Example command to simulate damage/healing
-- ==========================================

RegisterCommand("damage", function(source, args)
    local license = GetLicense(source)
    if not license then return end

    local amount = tonumber(args[1]) or 10
    prestigeAPI:AddStat(license, "health", -amount)

    local newHealth = prestigeAPI:GetStat(license, "health")
    print(("[Prestiged-Health] %s took %d damage → new health: %d"):format(GetPlayerName(source), amount, newHealth))
end, false)

RegisterCommand("heal", function(source, args)
    local license = GetLicense(source)
    if not license then return end

    local amount = tonumber(args[1]) or 10
    prestigeAPI:AddStat(license, "health", amount)

    local newHealth = prestigeAPI:GetStat(license, "health")
    print(("[Prestiged-Health] %s healed %d → new health: %d"):format(GetPlayerName(source), amount, newHealth))
end, false)

-- ==========================================
--  STEP 5: Example command to check health
-- ==========================================
RegisterCommand("myhealth", function(source)
    local license = GetLicense(source)
    if not license then return end

    local health = prestigeAPI:GetStat(license, "health")
    TriggerClientEvent("chat:addMessage", source, {
        color = { 0, 255, 0 },
        args = { "[Health]", "Your saved prestige health is: " .. (health or 0) }
    })
end, false)


-- ==========================================
--  STEP 6: Auto-save every few minutes (optional)
-- ==========================================
CreateThread(function()
    while true do
        Wait(300000) -- every 5 minutes
        print("[Prestiged-Health] Auto-saving all health stats...")
        prestigeAPI:SavePlayer() -- optional, ensures persistence
    end
end)
```
---

JSON file (stats.json)

```json
"license:abcd1234": {
  "name": "John",
  "level": 5,
  "points": 1200,
  "kills": 50,
  "dynamicStats": {
    "health": 85
  }
}
```

⚙️ What This Script Does

| Feature             | Description                                                    |
| ------------------- | -------------------------------------------------------------- |
| 🩸 **RegisterStat** | Adds a new dynamic stat `health` to your Mobz-prestiged system |
| ⚙️ **Auto-init**    | Ensures every player gets a default value of 100 on join       |
| 💥 **/damage**      | Command that decreases the player’s prestige health stat       |
| 💊 **/heal**        | Command that increases the prestige health stat                |
| ❤️ **/myhealth**    | Shows player’s current prestige health stat                    |
| 💾 **Auto-save**    | Saves periodically using your existing persistence system      |

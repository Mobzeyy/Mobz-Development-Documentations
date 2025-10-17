1. [Server-exports-reference api](#server-exports-reference-api)
   * [Core Data Functions](#core-data-functions)
   * [Basic Getters](#basic-getters)
   * [Modifiers](#modifiers)
   * [Buff System](#buff-system)
   * [Achievements & Titles](#achievements--titles)
   * [Visuals & Prestige Info](#visuals--prestige-info)
   * [Multipliers](#multipliers)
   * [Leaderboards](#leaderboards)
   * [Online / Offline Data](#online--offline-data)
   * [Saving Progression](#saving-progression)
   * [Developer Tips](#developer-tips)
2. [Client Exports Reference-API](#Client-Exports-Reference-API)
   * [Core Data Functions](#core-data-functions-1)
   * [Stats Getters](#stats-getters)
   * [Stats Modifiers](#stats-modifiers)
   * [Buff System](#buff-system-1)
   * [Visuals & Effects](#visuals--effects)
   * [Multipliers](#multipliers-1)
   * [Data Sync](#data-sync)
   * [Developer Tips](#developer-tips-1)


# Server Side

Below is a full list of server-side/client-side exports available through:

```lua
exports["mobz-prestiged"]:ExportName(...)
```

---

# Core Data Functions

### ✅ EnsurePlayerDataServer(identifier)

Ensures a player's data exists and returns it (used internally).


```lua
local data = exports["mobz-prestiged"]:GetLevel_sv("steam:110000112345678")
print(data.level)
```

---

#  Basic Getters

| Export                                | Description                           | Returns  |
| ------------------------------------- | ------------------------------------- | -------- |
| `GetLevel_sv(identifier)`             | Returns player’s current level        | `number` |
| `GetPoints_sv(identifier)`            | Returns total points                  | `number` |
| `GetKills_sv(identifier)`             | Returns total player kills            | `number` |
| `GetNpcKills_sv(identifier)`          | Returns total NPC kills               | `number` |
| `GetDeaths_sv(identifier)`            | Returns total deaths                  | `number` |
| `GetKillstreak_sv(identifier)`        | Returns current killstreak            | `number` |
| `GetPrestige_sv(identifier)`          | Returns prestige rank                 | `number` |
| `GetPlaytime_sv(identifier)`          | Total playtime in seconds             | `number` |
| `GetPlaytimeFormatted_sv(identifier)` | Returns formatted playtime as `HH:MM` | `string` |

**Example:**

```lua
local kills = exports["mobz-prestiged"]:GetKills_sv(identifier)
print(("Player has %d kills"):format(kills))
```

---

# Modifiers

| Export                                 | Description                                  |
| -------------------------------------- | -------------------------------------------- |
| `AddKill_sv(identifier, isNpc)`        | Adds a kill to either player or NPC category |
| `AddDeath_sv(identifier)`              | Adds a death and resets killstreak           |
| `SetPrestige_sv(identifier, prestige)` | Sets prestige and updates labels/icons       |

**Example:**

```lua
local id = GetPrimaryIdentifier(source)
exports["mobz-prestiged"]:AddKill_sv(id, false)
exports["mobz-prestiged"]:AddDeath_sv(id)
exports["mobz-prestiged"]:SetPrestige_sv(id, 2)
```

---

# Buff System

| Export                                    | Description                     |
| ----------------------------------------- | ------------------------------- |
| `AddBuff_sv(identifier, buffName, label)` | Adds a buff with optional label |
| `RemoveBuff_sv(identifier, buffName)`     | Removes a specific buff         |
| `ClearBuffs_sv(identifier)`               | Removes all buffs               |

**Example:**

```lua
local id = GetPrimaryIdentifier(source)
exports["mobz-prestiged"]:AddBuff_sv(id, "damage_boost", "🔥 Damage Boost")
exports["mobz-prestiged"]:RemoveBuff_sv(id, "damage_boost")
```

---

# Achievements & Titles

| Export                                          | Description                   |
| ----------------------------------------------- | ----------------------------- |
| `UnlockAchievement_sv(identifier, achievement)` | Unlocks specific achievement  |
| `UnlockTitle_sv(identifier, title)`             | Unlocks a title               |
| `GetAchievements_sv(identifier)`                | Returns all achievements data |
| `GetTitles_sv(identifier)`                      | Returns all unlocked titles   |

**Example:**

```lua
local id = GetPrimaryIdentifier(source)
exports["mobz-prestiged"]:UnlockAchievement_sv(id, 5)
exports["mobz-prestiged"]:UnlockTitle_sv(id, "Elite Slayer")

local achievements = exports["mobz-prestiged"]:GetAchievements_sv(id)
for lvl, data in pairs(achievements) do
    print(("Achievement %s: %s"):format(lvl, data.unlocked and "Unlocked" or "Locked"))
end
```

---

# Visuals & Prestige Info

| Export                            | Description                                       |
| --------------------------------- | ------------------------------------------------- |
| `GetPlayerVisuals_sv(identifier)` | Returns mugshot, prestige icon, and active effect |

**Example:**

```lua
local visuals = exports["mobz-prestiged"]:GetPlayerVisuals_sv(identifier)
print(json.encode(visuals))
```

---

# Multipliers

| Export                                 | Description                                      |
| -------------------------------------- | ------------------------------------------------ |
| `GetMultiplier_sv(identifier, factor)` | Returns dynamic multiplier based on player level |

**Example:**

```lua
local id = GetPrimaryIdentifier(source)
local mult = exports["mobz-prestiged"]:GetMultiplier_sv(id, 0.02)
print("XP Multiplier:", mult)
```

---

# Leaderboards

| Export                         | Sorted By             | Example Return                              |
| ------------------------------ | --------------------- | ------------------------------------------- |
| `GetTopPoints_sv(limit)`       | Points                | `{ {identifier, name, points}, ... }`       |
| `GetTopLevels_sv(limit)`       | Level                 | `{ {identifier, name, level}, ... }`        |
| `GetTopKills_sv(limit)`        | Kills                 | `{ {identifier, name, kills}, ... }`        |
| `GetTopAchievements_sv(limit)` | Achievements unlocked | `{ {identifier, name, achievements}, ... }` |

**Example:**

```lua
local topKills = exports["mobz-prestiged"]:GetTopKills_sv(5)
for _, player in ipairs(topKills) do
    print(("[%s] %s - %d kills"):format(player.identifier, player.name, player.kills))
end
```

---

# Online / Offline Data

| Export                        | Description                           |
| ----------------------------- | ------------------------------------- |
| `GetOnlinePlayersStats_sv()`  | Returns stats for all online players  |
| `GetOfflinePlayersStats_sv()` | Returns stats for all offline players |

**Example:**

```lua
local online = exports["mobz-prestiged"]:GetOnlinePlayersStats_sv()
print(json.encode(online))
```

---

# Saving Progression

| Export              | Description                                                        |
| ------------------- | ------------------------------------------------------------------ |
| `SaveProgress_sv()` | Triggers manual data save (optional override for JSON persistence) |

**Example:**

```lua
exports["mobz-prestiged"]:SaveProgress_sv()
```

---


# Client Exports Reference API

Below is a full list of client-side exports available through:

```lua
exports["mobz-prestiged"]:ExportName(...)
```

---

# Mobz-Prestiged Documentation (Client Exports)

# Client Exports Reference

Below is a full list of client-side exports available through:

```lua
exports["mobz-prestiged"]:ExportName(...)
```

---
# Client Side
# Core Data Functions

### ✅ EnsurePlayerDataClient(identifier)

Ensures local player data exists and initializes defaults if missing.

**Example:**

```lua
local id = GetPlayerServerId(PlayerId())
local pdata = EnsurePlayerDataClient(id)
print(pdata.level) -- prints current level
```

---

# Stats Getters

| Export                           | Description        | Returns  |
| -------------------------------- | ------------------ | -------- |
| `GetKills_cl(identifier)`        | Total player kills | `number` |
| `GetNpcKills_cl(identifier)`     | Total NPC kills    | `number` |
| `GetDeaths_cl(identifier)`       | Total deaths       | `number` |
| `GetKillstreak_cl(identifier)`   | Current killstreak | `number` |
| `GetAchievements_cl(identifier)` | Achievements table | `table`  |
| `GetTitles_cl(identifier)`       | Titles table       | `table`  |
| `GetLevel_cl()`                  | Current level      | `number` |
| `GetPoints_cl()`                 | Current points     | `number` |

**Example:**

```lua
local kills = exports["mobz-prestiged"]:GetKills_cl(identifier)
print("You have " .. kills .. " kills!")
```

---

# Stats Modifiers

| Export                                              | Description                        |
| --------------------------------------------------- | ---------------------------------- |
| `AddKill_cl(identifier, isNpc)`                     | Adds a kill (player or NPC)        |
| `AddDeath_cl(identifier)`                           | Adds a death and resets killstreak |
| `UnlockAchievement_cl(identifier, achievementName)` | Unlocks an achievement locally     |
| `UnlockTitle_cl(identifier, titleName)`             | Unlocks a title locally            |
| `SetPrestige_cl(identifier, prestige)`              | Updates prestige level and icon    |

**Example:**

```lua
local id = GetPlayerServerId(PlayerId())
exports["mobz-prestiged"]:AddKill_cl(id, false)
exports["mobz-prestiged"]:AddDeath_cl(id)
exports["mobz-prestiged"]:UnlockAchievement_cl(id, "First Blood")
exports["mobz-prestiged"]:SetPrestige_cl(id, 2)
```

---

# Buff System 

| Export                                    | Description                    |
| ----------------------------------------- | ------------------------------ |
| `AddBuff_cl(identifier, buffName, label)` | Add a buff with optional label |
| `RemoveBuff_cl(identifier, buffName)`     | Remove a buff                  |
| `ClearBuffs_cl(identifier)`               | Remove all buffs               |

**Example:**

```lua
exports["mobz-prestiged"]:AddBuff_cl(id, "speed_boost", "🏎️ Speed Boost")
exports["mobz-prestiged"]:RemoveBuff_cl(id, "speed_boost")
exports["mobz-prestiged"]:ClearBuffs_cl(id)
```

---

# Visuals & Effects

### `GetPlayerVisuals_cl(playerId)`

Returns visual info like active foot effects and killstreak labels.

**Returns Table Example:**

```lua
{
    activeEffect = {
        particleDict = "core",
        particleName = "fire_trail",
        scale = 1.0
    },
    label = {
        label = "Rampage",
        color = {255,0,0},
        scale = 0.5,
        heightOffset = 2.0
    }
}
```

**Example:**

```lua
local visuals = exports["mobz-prestiged"]:GetPlayerVisuals_cl(id)
if visuals.label then
    print("Current Killstreak Label:", visuals.label.label)
end
```

---

# Multipliers 

```lua
GetLevelMultiplier_cl(factor, callback)
```

Requests a multiplier from the server based on player level.

**Example:**

```lua
exports["mobz-prestiged"]:GetLevelMultiplier_cl(0.02, function(mult)
    print("XP multiplier:", mult)
end)
```

---

# Data Sync

### `mobz-prestiged:syncPlayerData`

Event used to update client data from the server.

**Example:**

```lua
RegisterNetEvent("mobz-prestiged:syncPlayerData")
AddEventHandler("mobz-prestiged:syncPlayerData", function(identifier, newData)
    print("Data synced for:", identifier)
end)
```


# Source of truth - Access the API

* You can access the exported API using:
* 
```lua
local PrestigeAPI = exports["mobz-prestiged"]:PrestigeAPI()
```

---

Now PrestigeAPI contains all the functions you defined in the export.

# Get Player Stats

Get full stats of a player:

```lua
  local playerId = "license:1234567890abcdef"
  local pdata = PrestigeAPI.GetFullStats(playerId)
  
  print("Player Level: " .. pdata.level)
  print("Player Tokens: " .. pdata.tokens)
  print("Player Reputation: " .. pdata.reputation)
  print("Reputation Titles: " .. table.concat(pdata.reputationTitles, ", "))
  
  Or shorthand:
  
  local tokens = PrestigeAPI.GetTokens(playerId)
  local cash = PrestigeAPI.GetCash(playerId)
  local reputation = PrestigeAPI.GetReputation(playerId)
  local titles = PrestigeAPI.GetReputationTitles(playerId)
```

---

# Modify Cash
```lua
Add, remove, or reset cash:

-- Add 500 cash
PrestigeAPI.AddCash(playerId, 500)

-- Remove 200 cash
PrestigeAPI.RemoveCash(playerId, 200)

-- Reset cash to 0
PrestigeAPI.ResetCash(playerId)

-- Get current cash


local currentCash = PrestigeAPI.GetCash(playerId)
print("Player Cash: " .. currentCash)
```

---

# Update Tokens / Reputation

If you manually modify a player’s level and want to sync tokens and reputation:

```lua
-- Suppose player levels up
local pdata = PrestigeAPI.GetFullStats(playerId)
pdata.level = pdata.level + 1

-- Update derived stats
PrestigeAPI.UpdateTokens(playerId)

-- Check updated stats
print("New Tokens: " .. PrestigeAPI.GetTokens(playerId))
print("New Reputation Titles: " .. table.concat(PrestigeAPI.GetReputationTitles(playerId), ", "))
```

Note: This is usually automatic via auto-save or if you call it inside level-up logic.

---

# Unlock Reputation Titles Manually

If you want to grant a special title based on custom logic:

```lua
local pdata = PrestigeAPI.GetFullStats(playerId)
table.insert(pdata.reputationTitles, "Champion")
pdata.reputation = #pdata.reputationTitles
`

-- Save the update
PrestigeAPI.SavePlayer(playerId)
```

---

# Example: Reward Script
Suppose a mini-game awards cash and XP:

```lua
RegisterNetEvent("myMiniGame:RewardPlayer")
AddEventHandler("myMiniGame:RewardPlayer", function(playerId, cashReward)
    local pdata = PrestigeAPI.GetFullStats(playerId)
    
    -- Give cash
    PrestigeAPI.AddCash(playerId, cashReward)
    
    -- Give a level (XP)
    pdata.level = pdata.level + 1
    
    -- Update tokens and reputation automatically
    PrestigeAPI.UpdateTokens(playerId)

    print("Player " .. pdata.name .. " now has " .. pdata.cash .. " cash and " .. pdata.tokens .. " tokens.")
end)
```

---

# Step-by-step guide 

## showing how to make a new export that modifies stats, directly using EnsurePlayerDataServer, without touching the core logic:

* main.lua is locked
* EnsurePlayerDataServer is the source of truth
* Admins can make new exports for other scripts safely

### Step-by-Step: New Export Using EnsurePlayerDataServer

# Step.1 ADD/CREATE a new export file

Add to: mobz-prestiged/server/exports.lua

-- ===========================
-- Example: Cash Management Export
-- ===========================

```lua
-- Function to add money to a player
local function AddMoney(identifier, amount)
    if not identifier or not amount then return false end

    -- Use EnsurePlayerDataServer to fetch canonical player data
    local pdata = EnsurePlayerDataServer(identifier)
    if not pdata then return false end

    -- Update cash safely
    pdata.cash = (pdata.cash or 0) + amount

    -- Optional: save after update (calls main SaveProgression)
    SaveProgression()

    return true
end



-- Function to remove money
local function RemoveMoney(identifier, amount)
    if not identifier or not amount then return false end

    local pdata = EnsurePlayerDataServer(identifier)
    if not pdata then return false end

    pdata.cash = math.max(0, (pdata.cash or 0) - amount)
    SaveProgression()

    return true
end



-- Function to reset cash
local function ResetMoney(identifier)
    if not identifier then return false end

    local pdata = EnsurePlayerDataServer(identifier)
    if not pdata then return false end

    pdata.cash = 0
    SaveProgression()

    return true
end


-- ===========================
-- Export functions
-- ===========================
exports("AddMoney", AddMoney)
exports("RemoveMoney", RemoveMoney)
exports("ResetMoney", ResetMoney)
```
---


# Step.2 Add to fxmanifest.lua
```lua
server_scripts {
    "server/main.lua",           -- locked core
    "server/exports_cash.lua",   -- new export
}
```
---

# Step.3 Usage in other scripts
-- Add cash to a player
```lua
exports["mobz-prestiged"]:AddMoney("license:abc123", 500)

-- Remove cash
exports["mobz-prestiged"]:RemoveMoney("license:abc123", 200)

-- Reset cash
exports["mobz-prestiged"]:ResetMoney("license:abc123")
```

---



# 🖥️ Mobz-Prestiged Exports Reference (Server & Client)

| Export                                              | Arguments                             | Returns | Description                                                                                  |
| --------------------------------------------------- | ------------------------------------- | ------- | -------------------------------------------------------------------------------------------- |
| `AddPoints_sv(identifier, amount)`                  | string, number                        | nil     | Add XP points to a player on the server.                                                     |
| `RemovePoints_sv(identifier, amount)`               | string, number                        | nil     | Remove XP points from a player on the server.                                                |
| `SetLevel_sv(identifier, level)`                    | string, number                        | nil     | Set player level directly on the server.                                                    |
| `SaveProgress_sv(identifier)`                       | string                                | nil     | Save the player’s progression on the server.                                                |
| `AddKill_sv(identifier, isNpc)`                     | string, bool                          | nil     | Add a kill for the player or NPC, updates killstreak.                                        |
| `AddDeath_sv(identifier)`                           | string                                 | nil     | Add a death and reset the killstreak.                                                       |
| `UnlockAchievement_sv(identifier, achievementName)` | string, string                        | nil     | Unlock a specific achievement for the player.                                               |
| `UnlockTitle_sv(identifier, titleName)`             | string, string                        | nil     | Unlock a specific title for the player.                                                     |
| `AddBuff_sv(identifier, buffName, label)`           | string, string, string                 | nil     | Add a buff to the player.                                                                   |
| `RemoveBuff_sv(identifier, buffName)`               | string, string                        | nil     | Remove a buff from the player by name.                                                      |
| `ClearBuffs_sv(identifier)`                         | string                                 | nil     | Clear all buffs from the player.                                                            |
| `SetPrestige_sv(identifier, prestige)`              | string, number                        | nil     | Set player prestige directly on the server.                                                 |
| `GetLevel_sv(identifier)`                           | string                                 | number  | Returns the player’s level.                                                                |
| `GetPoints_sv(identifier)`                          | string                                 | number  | Returns the player’s points.                                                               |
| `GetKills_sv(identifier)`                           | string                                 | number  | Returns the player’s kills.                                                                |
| `GetNpcKills_sv(identifier)`                        | string                                 | number  | Returns the player’s NPC kills.                                                            |
| `GetDeaths_sv(identifier)`                          | string                                 | number  | Returns the player’s deaths.                                                               |
| `GetKillstreak_sv(identifier)`                      | string                                 | number  | Returns the player’s current killstreak.                                                   |
| `GetAchievements_sv(identifier)`                    | string                                 | table   | Returns unlocked achievements for the player.                                              |
| `GetTitles_sv(identifier)`                          | string                                 | table   | Returns unlocked titles for the player.                                                    |
| `GetPlayerVisuals_sv(identifier)`                   | string                                 | table   | Returns foot effects, active labels, killstreak label, and buffs.                          |
| `EnsurePlayerDataServer(identifier)`               | string                                 | table   | Returns full player data (main source of truth).                                           |
| `LoadPlayer(identifier)`                             | string                                 | table   | Load player progression from saved data.                                                   |
| `SavePlayer(identifier)`                             | string                                 | nil     | Save player progression to file/server.                                                    |
| `SaveProgression()`                                 | nil                                    | nil     | Save all player progression to file/server.                                                |
| `LoadProgression()`                                 | nil                                    | nil     | Load all player progression from file.                                                     |
| `AddReputationXP(identifier, amount)`               | string, number                        | nil     | Add reputation XP to a player.                                                             |
| `SetReputation(identifier, amount)`                 | string, number                        | nil     | Set player reputation directly.                                                            |
| `GetReputation(identifier)`                          | string                                 | number  | Get the player’s current reputation.                                                      |
| `GetPlayerJobGang(identifier)`                       | string                                 | table   | Returns current job/gang and ranks (supports QB-Core + ESX).                                |
| `GetCraftingStats(identifier)`                       | string                                 | table   | Returns crafting stats (level, XP, items crafted/failed, best streak).                     |
| `AddFailedCraft(identifier)`                         | string                                 | nil     | Increment failed crafts count.                                                            |
| `AddCraftedItem(identifier)`                         | string                                 | nil     | Increment crafted items count.                                                            |
| `AddHuntedAnimal(identifier)`                        | string                                 | nil     | Increment animals hunted count.                                                           |
| `FailedHunt(identifier)`                              | string                                 | nil     | Increment failed hunts count.                                                             |
| `GetHuntingStats(identifier)`                        | string                                 | table   | Returns hunting stats.                                                                    |
| `GetDrivingStats(identifier)`                        | string                                 | table   | Returns driving stats (XP, stunts, accidents).                                           |
| `AddDrivingStunt(identifier)`                         | string                                 | nil     | Add driving stunt XP.                                                                     |
| `AddDrivingAccident(identifier)`                     | string                                 | nil     | Increment driving accidents count.                                                        |
| `AddDrivingXP(identifier, amount)`                   | string, number                        | nil     | Add driving skill XP.                                                                    |
| `RecordShotFired(identifier)`                         | string                                 | nil     | Increment shots fired count.                                                              |
| `RecordShotHit(identifier)`                            | string                                 | nil     | Increment shots hit count.                                                                |
| `RecordShotMissed(identifier)`                          | string                                 | nil     | Increment shots missed count.                                                            |
| `GetTradesCompleted(identifier)`                       | string                                 | number  | Get trades completed.                                                                     |
| `AddTradeCompleted(identifier)`                        | string                                 | nil     | Increment trades completed.                                                              |
| `GetTradesCancelled(identifier)`                       | string                                 | number  | Get trades cancelled.                                                                     |
| `AddTradeCancelled(identifier)`                        | string                                 | nil     | Increment trades cancelled.                                                              |
| `GetAccuracyStats(identifier)`                          | string                                 | table   | Returns shots fired, shots hit, headshots, accuracy %, streaks.                            |
| `GetBountiesClaimed(identifier)`                        | string                                 | number  | Get bounties claimed.                                                                     |
| `AddBountyClaimed(identifier)`                          | string                                 | nil     | Increment bounties claimed.                                                              |
| `GetBountiesPlaced(identifier)`                         | string                                 | number  | Get bounties placed.                                                                      |
| `AddBountyPlaced(identifier)`                            | string                                 | nil     | Increment bounties placed.                                                               |
| `AddObjectiveCompleted(identifier)`                     | string                                 | nil     | Increment objectives completed.                                                          |
| `GetObjectivesCompleted(identifier)`                    | string                                 | number  | Get completed objectives count.                                                          |
| `AddTaskCompleted(identifier)`                           | string                                 | nil     | Increment tasks completed.                                                              |
| `GetTasksCompleted(identifier)`                          | string                                 | number  | Get completed tasks count.                                                              |
| `AddBusinessOwned(identifier)`                           | string                                 | nil     | Increment businesses owned.                                                              |
| `GetBusinessesOwned(identifier)`                         | string                                 | number  | Get number of businesses owned.                                                         |
| `AddDuelWon(identifier)`                                 | string                                 | nil     | Increment duels won.                                                                    |
| `AddHeadshot(identifier)`                                | string                                 | nil     | Increment headshots count.                                                               |
| `AddShotHit(identifier)`                                  | string                                 | nil     | Increment shots hit.                                                                     |
| `AddShotFired(identifier)`                                | string                                 | nil     | Increment shots fired.                                                                   |
| `SetAccuracy(identifier, value)`                          | string, number                        | nil     | Set shooting accuracy %.                                                                  |
| `GetAccuracy(identifier)`                                  | string                                 | number  | Returns shooting accuracy %.                                                             |
| `GiveRewardByRank(identifier, rank)`                       | string, number                        | nil     | Give reward based on player rank.                                                        |
| `GiveReward(identifier, rewardName)`                        | string, string                        | nil     | Give a specific reward.                                                                  |
| `GetPlayerProgression(identifier)`                          | string                                 | table   | Returns full player progression.                                                         |
| **Client Versions**                                     |                                       |         |                                                                                             |
| `AddPoints_cl(identifier, amount)`                  | string, number                        | nil     | Add XP to a player (syncs to server).                                                    |
| `RemovePoints_cl(identifier, amount)`               | string, number                        | nil     | Remove XP from a player (syncs to server).                                               |
| `SetLevel_cl(identifier, level)`                    | string, number                        | nil     | Set player level directly (syncs to server).                                             |
| `SaveProgress_cl(identifier)`                       | string                                 | nil     | Save current player progression to server.                                               |
| `AddKill_cl(identifier, isNpc)`                     | string, bool                           | nil     | Add kill for player or NPC, updates killstreak locally.                                  |
| `AddDeath_cl(identifier)`                           | string                                 | nil     | Add death and reset killstreak locally.                                                 |
| `UnlockAchievement_cl(identifier, achievementName)` | string, string                        | nil     | Unlock a specific achievement locally.                                                  |
| `UnlockTitle_cl(identifier, titleName)`             | string, string                        | nil     | Unlock a specific title locally.                                                       |
| `SetMugshot_cl(identifier, mugshot)`                | string, string                        | nil     | Set a custom mugshot locally.                                                          |
| `AddBuff_cl(identifier, buffName, label)`           | string, string, string                 | nil     | Add a buff to player locally.                                                          |
| `RemoveBuff_cl(identifier, buffName)`               | string, string                        | nil     | Remove a buff locally by name.                                                         |
| `ClearBuffs_cl(identifier)`                         | string                                 | nil     | Clear all buffs locally.                                                               |
| `SetPrestige_cl(identifier, prestige)`              | string, number                        | nil     | Set player prestige locally.                                                           |
| `GetLevel_cl(identifier)`                           | string                                 | number  | Returns player level locally.                                                          |
| `GetPoints_cl(identifier)`                          | string                                 | number  | Returns player points locally.                                                         |
| `GetKills_cl(identifier)`                           | string                                 | number  | Returns player kills locally.                                                          |
| `GetNpcKills_cl(identifier)`                        | string                                 | number  | Returns player NPC kills locally.                                                      |
| `GetDeaths_cl(identifier)`                          | string                                 | number  | Returns player deaths locally.                                                        |
| `GetKillstreak_cl(identifier)`                      | string                                 | number  | Returns current killstreak locally.                                                   |
| `GetAchievements_cl(identifier)`                    | string                                 | table   | Returns unlocked achievements locally.                                               |
| `GetTitles_cl(identifier)`                          | string                                 | table   | Returns unlocked titles locally.                                                     |
| `GetMugshot_cl(identifier)`                         | string                                 | string  | Returns mugshot path locally.                                                        |
| `GetPlayerVisuals_cl(identifier)`                   | string                                 | table   | Returns foot effects + killstreak label locally.                                      |
| `ToggleUI(identifier, state)`                        | string, bool                           | nil     | Show or hide client UI.                                                               |



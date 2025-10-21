

# 🖥️ Mobz-Prestiged Exports (Server & Client)

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



---




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


## 🖥️ Server Exports Reference

| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| AddKill_sv | Adds a kill to the player | Updated kills count |
| AddDeath_sv | Adds a death to the player | Updated deaths count |
| SetPrestige_sv | Sets player prestige rank | Updated prestige value |
| AddBuff_sv | Adds a buff to a player | Buff object |
| RemoveBuff_sv | Removes a specific buff | Success boolean |
| ClearBuffs_sv | Clears all active buffs | Success boolean |
| UnlockAchievement_sv | Unlocks a specific achievement | Updated achievement list |
| UnlockTitle_sv | Unlocks a new title | Updated titles list |
| GetAchievements_sv | Gets player achievements | Array of achievements |
| GetTitles_sv | Gets player titles | Array of titles |
| GetPlayerVisuals_sv | Gets player visual settings | Visual object |
| GetLevel_sv | Gets player level | Number |
| GetPoints_sv | Gets player points | Number |
| GetKills_sv | Gets player kills | Number |
| GetNpcKills_sv | Gets NPC kills | Number |
| GetDeaths_sv | Gets player deaths | Number |
| GetKillstreak_sv | Gets current killstreak | Number |
| GetPrestige_sv | Gets player prestige | Number |
| GetMultiplier_sv | Gets XP / points multiplier | Number |
| GetPlaytime_sv | Gets total playtime in seconds | Number |
| GetPlaytimeFormatted_sv | Gets total playtime formatted | String (HH:MM:SS) |
| SaveProgress_sv | Saves player progression | Success boolean |
| AddPoints_sv | Adds points to player | Updated points count |
| RemovePoints_sv | Removes points from player | Updated points count |
| SetLevel_sv | Sets player level | Updated level |
| GetTopPoints_sv | Gets top players by points | Array of player data |
| GetTopLevels_sv | Gets top players by level | Array of player data |
| GetTopKills_sv | Gets top players by kills | Array of player data |
| GetTopAchievements_sv | Gets top players by achievements | Array of player data |
| GetOnlinePlayersStats_sv | Gets stats for all online players | Array of stats objects |
| GetOfflinePlayersStats_sv | Gets stats for offline players | Array of stats objects |
| CheckLevelAchievements | Checks if player qualifies for level achievements | Boolean |
| HasAchievement | Checks if player has a specific achievement | Boolean |
| GetAchievements | Gets achievements (general) | Array of achievements |
| ResetPlayerStats | Resets a player’s stats | Success boolean |
| ResetLastPlayedStats | Resets stats from last session | Success boolean |
| EnsurePlayerDataServer | Ensures player data exists | Player data object |
| LoadPlayer | Loads a player’s data | Player data object |
| SavePlayer | Saves a player’s data | Success boolean |
| SaveProgression | Saves overall progression | Success boolean |
| LoadProgression | Loads overall progression | Success boolean |
| RewardClaimed | Marks a reward as claimed | Success boolean |
| MissionCompleted | Marks a mission as completed | Success boolean |


---


# Client Exports Reference API

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


## 💻 Client Exports Reference

| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| SaveProgress_cl | Saves client-side progression | Success boolean |
| AddKill_cl | Adds a kill to the local player | Updated kills count |
| AddDeath_cl | Adds a death to the local player | Updated deaths count |
| UnlockAchievement_cl | Unlocks a specific achievement locally | Updated achievement list |
| UnlockTitle_cl | Unlocks a new title locally | Updated titles list |
| AddBuff_cl | Adds a buff to the local player | Buff object |
| RemoveBuff_cl | Removes a specific buff | Success boolean |
| ClearBuffs_cl | Clears all active buffs | Success boolean |
| SetPrestige_cl | Sets player prestige rank | Updated prestige value |
| GetKills_cl | Gets player kills | Number |
| GetNpcKills_cl | Gets NPC kills | Number |
| GetDeaths_cl | Gets player deaths | Number |
| GetKillstreak_cl | Gets current killstreak | Number |
| GetAchievements_cl | Gets player achievements | Array of achievements |
| GetTitles_cl | Gets player titles | Array of titles |
| GetPlayerVisuals_cl | Gets player visual settings | Visual object |
| GetLevelMultiplier_cl | Gets XP / points multiplier | Number |
| GetLevel_cl | Gets player level | Number |
| SetLevel_cl | Sets player level | Updated level |
| GetPoints_cl | Gets player points | Number |
| AddPoints_cl | Adds points to player | Updated points count |
| RemovePoints_cl | Removes points from player | Updated points count |
| ToggleUI | Shows or hides the UI | Success boolean |
| EnsurePlayerDataClient | Ensures player data exists locally | Player data object |
| Save_cl | Saves client data | Success boolean |
| GiveRewardByRank_cl | Gives a reward based on rank | Success boolean |
| GiveReward_cl | Gives a generic reward | Success boolean |

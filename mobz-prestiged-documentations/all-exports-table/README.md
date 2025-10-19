## 🖥️ Server Exports Full Reference

### 🧍 Player Stats
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| AddKill_sv | Adds a kill to a player | Updated kills count |
| AddDeath_sv | Adds a death to a player | Updated deaths count |
| SetLevel_sv | Sets player level | Updated level |
| GetLevel_sv | Gets player level | Number |
| AddPoints_sv | Adds points to player | Updated points |
| RemovePoints_sv | Removes points from player | Updated points |
| GetPoints_sv | Gets player points | Number |
| GetKillstreak_sv | Gets current killstreak | Number |
| GetPlaytime_sv | Gets total playtime in seconds | Number |
| GetPlaytimeFormatted_sv | Gets formatted playtime (HH:MM:SS) | String |
| ResetPlayerStats | Resets all player stats | Success boolean |
| ResetLastPlayedStats | Resets last session stats | Success boolean |
| EnsurePlayerDataServer | Ensures player data exists | Player object |
| LoadPlayer | Loads a player’s data | Player object |
| SavePlayer | Saves a player’s data | Success boolean |

### 🏅 Achievements & Titles
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| UnlockAchievement_sv | Unlock a specific achievement | Updated list |
| UnlockTitle_sv | Unlock a title | Updated titles |
| GetAchievements_sv | Get player achievements | Array |
| GetTitles_sv | Get player titles | Array |
| HasAchievement | Check if player has an achievement | Boolean |
| GetAchievements | Generic achievement fetch | Array |
| CheckLevelAchievements | Checks for level-based achievements | Boolean |

### 🏗 Progression & Prestige
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| SetPrestige_sv | Sets player prestige rank | Updated prestige |
| GetPrestige_sv | Gets player prestige | Number |
| GetPrestigeData | Get full prestige info | Object |
| SaveProgress_sv | Saves player progression | Success boolean |
| SaveProgression | Saves progression | Success boolean |
| SaveProgression_sv | Saves progression (alias) | Success boolean |
| LoadProgression | Loads progression | Object |
| GetPlayerProgression | Full progression info | Object |

### ✨ Buffs / Rewards
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| AddBuff_sv | Adds a buff to player | Buff object |
| RemoveBuff_sv | Removes a specific buff | Success boolean |
| ClearBuffs_sv | Clears all active buffs | Success boolean |
| RewardClaimed | Marks a reward claimed | Success boolean |
| MissionCompleted | Marks mission complete | Success boolean |
| GiveRewardByRank | Give reward based on rank | Success boolean |
| GiveReward | Give generic reward | Success boolean |

### 📈 Stats / Custom
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| AddPlayerStat | Add stat values (level, kills, etc.) | Success boolean |
| UpdateLastPlayedStats | Update last played stats | Success boolean |
| RemovePlayerStat | Remove stat values | Success boolean |
| GetStat | Get specific stat | Value |
| AddStat | Add to stat | Updated value |
| SetStat | Set stat | Updated value |
| RegisterStat | Register new stat type | Success boolean |
| DeleteStat | Delete stat | Success boolean |
| AddField | Add field to stat | Success boolean |
| SetField | Set field value | Updated value |
| GetField | Get field value | Value |

### 🏛 Reputation & Jobs
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| AddReputationXP | Add reputation XP | Updated reputation |
| SetReputation | Set reputation | Updated value |
| GetReputation | Get reputation | Number |
| GetPlayerJobGang | Get player's job/gang | Object |

### 🛠 Crafting / Hunting / Driving
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| GetCraftingStats | Get crafting stats | Object |
| AddFailedCraft | Add failed craft | Updated stats |
| AddCraftedItem | Add crafted item | Updated stats |
| AddHuntedAnimal | Add hunted animal | Updated stats |
| FailedHunt | Register failed hunt | Updated stats |
| GetHuntingStats | Get hunting stats | Object |
| GetDrivingStats | Get driving stats | Object |
| AddDrivingStunt | Add stunt points | Updated stats |
| AddDrivingAccident | Record driving accident | Updated stats |
| AddDrivingXP | Add driving XP | Updated XP |

### 🔫 Combat & Accuracy
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| RecordShotFired | Increment shots fired | Updated stat |
| RecordShotHit | Increment shots hit | Updated stat |
| RecordShotMissed | Increment shots missed | Updated stat |
| AddShotFired | Increment shots fired | Updated stat |
| AddShotHit | Increment shots hit | Updated stat |
| AddHeadshot | Increment headshots | Updated stat |
| AddDuelWon | Increment duel wins | Updated stat |
| SetAccuracy | Set accuracy | Updated stat |
| GetAccuracy | Get accuracy stats | Object |
| GetAccuracyStats | Full accuracy breakdown | Object |

### 💰 Trades, Bounties, Tasks & Objectives
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| GetTradesCompleted | Get completed trades | Array |
| AddTradeCompleted | Add completed trade | Success boolean |
| GetTradesCancelled | Get cancelled trades | Array |
| AddTradeCancelled | Add cancelled trade | Success boolean |
| GetBountiesClaimed | Get claimed bounties | Array |
| AddBountyClaimed | Add claimed bounty | Success boolean |
| GetBountiesPlaced | Get placed bounties | Array |
| AddBountyPlaced | Add placed bounty | Success boolean |
| AddObjectiveCompleted | Increment objectives completed | Updated stats |
| GetObjectivesCompleted | Get completed objectives | Array |
| AddTaskCompleted | Increment tasks completed | Updated stats |
| GetTasksCompleted | Get completed tasks | Array |

### 🏢 Business / Misc
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| AddBusinessOwned | Add business owned by player | Updated list |
| GetBusinessesOwned | Get owned businesses | Array |
| PrestigeAPI | Main API export | Table of API functions |


---


## 💻 Client Exports Full Reference

### 🧍 Player Stats
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| AddKill_cl | Adds a kill to the local player | Updated kills count |
| AddDeath_cl | Adds a death to the local player | Updated deaths count |
| GetKills_cl | Get current kills | Number |
| GetNpcKills_cl | Get NPC kills | Number |
| GetDeaths_cl | Get current deaths | Number |
| GetKillstreak_cl | Get current killstreak | Number |
| GetLevel_cl | Get player level | Number |
| SetLevel_cl | Set player level | Updated level |
| GetPoints_cl | Get current points | Number |
| AddPoints_cl | Add points to player | Updated points |
| RemovePoints_cl | Remove points from player | Updated points |
| GetLevelMultiplier_cl | Get XP/points multiplier | Number |

### 🏅 Achievements & Titles
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| UnlockAchievement_cl | Unlock a specific achievement locally | Updated achievement list |
| UnlockTitle_cl | Unlock a title locally | Updated titles list |
| GetAchievements_cl | Get player achievements | Array |
| GetTitles_cl | Get player titles | Array |

### ✨ Buffs / Rewards
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| AddBuff_cl | Add a buff to the local player | Buff object |
| RemoveBuff_cl | Remove a specific buff | Success boolean |
| ClearBuffs_cl | Clear all buffs | Success boolean |
| SetPrestige_cl | Set prestige rank | Updated prestige value |
| GiveRewardByRank_cl | Give reward by rank | Success boolean |
| GiveReward_cl | Give a generic reward | Success boolean |

### 🖥️ UI & Client Data
| Export Name | Description | Return / Notes |
|------------|-------------|----------------|
| SaveProgress_cl | Save client-side progression | Success boolean |
| ToggleUI | Show or hide UI | Success boolean |
| EnsurePlayerDataClient | Ensure local player data exists | Player data object |
| Save_cl | Save client data | Success boolean |
| GetPlayerVisuals_cl | Get player visuals locally | Visual object |




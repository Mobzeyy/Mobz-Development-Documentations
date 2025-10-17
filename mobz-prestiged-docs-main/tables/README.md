# Mobz-Prestiged PrestigeAPI Full tables

# Core API Functions

| Export / Function                                | Description                      | Example Usage                                                                             | Notes                               |
| ------------------------------------------------ | -------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------- |
| `PrestigeAPI().LoadAll()`                        | Loads all player stats from JSON | `local all = exports["mobz-prestiged"]:PrestigeAPI().LoadAll()`                           | Returns a table keyed by identifier |
| `PrestigeAPI().LoadPlayer(identifier)`           | Loads stats for a single player  | `local pdata = exports["mobz-prestiged"]:PrestigeAPI().LoadPlayer("license:123")`         | Does not save changes automatically |
| `PrestigeAPI().SavePlayer(identifier)`           | Saves a single player to JSON    | `exports["mobz-prestiged"]:PrestigeAPI().SavePlayer("license:123")`                       | Call after modifying any stats      |
| `PrestigeAPI().GetFullStats(identifier)`         | Returns full player stats        | `local stats = exports["mobz-prestiged"]:PrestigeAPI().GetFullStats("license:123")`       | Useful for leaderboards or UI       |
| `PrestigeAPI().GetLevel(identifier)`             | Returns player level             | `local lvl = exports["mobz-prestiged"]:PrestigeAPI().GetLevel("license:123")`             |                                     |
| `PrestigeAPI().GetPoints(identifier)`            | Returns player points            | `local pts = exports["mobz-prestiged"]:PrestigeAPI().GetPoints("license:123")`            | `tokens` is derived from level      |
| `PrestigeAPI().GetKills(identifier)`             | Returns PvP kills                | `local kills = exports["mobz-prestiged"]:PrestigeAPI().GetKills("license:123")`           |                                     |
| `PrestigeAPI().GetNpcKills(identifier)`          | Returns NPC kills                | `local npc = exports["mobz-prestiged"]:PrestigeAPI().GetNpcKills("license:123")`          |                                     |
| `PrestigeAPI().GetDeaths(identifier)`            | Returns deaths                   | `local deaths = exports["mobz-prestiged"]:PrestigeAPI().GetDeaths("license:123")`         |                                     |
| `PrestigeAPI().GetKillstreak(identifier)`        | Returns current killstreak       | `local ks = exports["mobz-prestiged"]:PrestigeAPI().GetKillstreak("license:123")`         |                                     |
| `PrestigeAPI().GetPrestige(identifier)`          | Returns prestige level           | `local pr = exports["mobz-prestiged"]:PrestigeAPI().GetPrestige("license:123")`           |                                     |
| `PrestigeAPI().GetPlaytime(identifier)`          | Returns playtime in seconds      | `local time = exports["mobz-prestiged"]:PrestigeAPI().GetPlaytime("license:123")`         |                                     |
| `PrestigeAPI().GetPlaytimeFormatted(identifier)` | Returns playtime in HH:MM        | `local fmt = exports["mobz-prestiged"]:PrestigeAPI().GetPlaytimeFormatted("license:123")` |      |

---

# Modifiers / Event-Driven Functions


| Function                            | Description                           | Example Usage                                                           | Notes                              |
| ----------------------------------- | ------------------------------------- | ----------------------------------------------------------------------- | ---------------------------------- |
| `AddKill(identifier, isNpc)`        | Adds a kill and increments killstreak | `exports["mobz-prestiged"]:PrestigeAPI().AddKill("license:123", false)` | `isNpc=true` for NPC kills         |
| `AddDeath(identifier)`              | Adds a death and resets killstreak    | `exports["mobz-prestiged"]:PrestigeAPI().AddDeath("license:123")`       |                                    |
| `SetPrestige(identifier, prestige)` | Sets prestige level                   | `exports["mobz-prestiged"]:PrestigeAPI().SetPrestige("license:123", 2)` | Updates label & icon automatically |



---

# Buff Functions

| Function                               | Description           | Example Usage                                                                                | Notes             |
| -------------------------------------- | --------------------- | -------------------------------------------------------------------------------------------- | ----------------- |
| `AddBuff(identifier, buffName, label)` | Adds a buff to player | `exports["mobz-prestiged"]:PrestigeAPI().AddBuff("license:123","damageBoost","Damage +10%")` | Label is optional |
| `RemoveBuff(identifier, buffName)`     | Removes a buff        | `exports["mobz-prestiged"]:PrestigeAPI().RemoveBuff("license:123","damageBoost")`            |                   |
| `ClearBuffs(identifier)`               | Clears all buffs      | `exports["mobz-prestiged"]:PrestigeAPI().ClearBuffs("license:123")`                          |                   |


---


# Achievements & Titles

| Function                               | Description                | Example Usage                                                                        | Notes                                       |
| -------------------------------------- | -------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------- |
| `UnlockAchievement(identifier, level)` | Unlocks achievement        | `exports["mobz-prestiged"]:PrestigeAPI().UnlockAchievement("license:123", 5)`        | Achievement reward logic runs automatically |
| `UnlockTitle(identifier, titleName)`   | Unlocks a title            | `exports["mobz-prestiged"]:PrestigeAPI().UnlockTitle("license:123","Veteran")`       |                                             |
| `GetAchievements(identifier)`          | Returns achievements table | `local ach = exports["mobz-prestiged"]:PrestigeAPI().GetAchievements("license:123")` |                                             |
| `GetTitles(identifier)`                | Returns titles table       | `local titles = exports["mobz-prestiged"]:PrestigeAPI().GetTitles("license:123")`    |                                             |


---

# Leaderboards

| Function              | Description                   | Example Usage                                                          | Notes                               |
| --------------------- | ----------------------------- | ---------------------------------------------------------------------- | ----------------------------------- |
| `GetTopPoints(limit)` | Returns top players by points | `local top = exports["mobz-prestiged"]:PrestigeAPI().GetTopPoints(10)` | Returns array of `{id,name,points}` |
| `GetTopLevels(limit)` | Returns top players by level  | `local top = exports["mobz-prestiged"]:PrestigeAPI().GetTopLevels(10)` | Returns array of `{id,name,level}`  |



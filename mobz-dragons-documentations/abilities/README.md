# Source of truth Access the API


[![← Back to Main Docs](https://img.shields.io/badge/←_Back_to_Main_Docs-9c2590?style=for-the-badge&logo=mobz%20development)](../README.md)


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

[Top of page](#Source-of-truth-Access-the-API)


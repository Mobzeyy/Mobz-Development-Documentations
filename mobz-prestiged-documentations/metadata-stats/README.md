
## Adding Dynamic Stat 

[![← Back to Main Docs](https://img.shields.io/badge/←_Back_to_Main_Docs-9c2590?style=for-the-badge&logo=mobz%20development)](../README.md#Advanced-Usage-Custom-API-integration-&-expansion-Advanced)


Advanced Usage Custom API integration & expansion Advanced
---

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

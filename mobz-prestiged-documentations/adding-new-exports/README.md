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
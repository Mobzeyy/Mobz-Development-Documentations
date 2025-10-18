# 🏆 Mobz-Prestiged

> The Ultimate Prestige, XP, and Progression Framework for FiveM

A fully modular prestige and XP system for FiveM.  
Includes **dynamic XP/UI bars, prestige ranks, killstreaks, rewards, Discord logs, admin tools, and advanced exports**.  
Supports **QB-Core**, **ESX**, **Ox_Inventory**, and standalone frameworks.

---

## 📑 Table of Contents
1. [Overview](#overview)
2. [Features](#features)
   - [XP System and Prestige Overview](#xp-system-and-prestige-overview)
   - [Rewards and Killstreaks](#rewards-and-killstreaks)
   - [Mugshot UI](#mugshot-ui)
   - [Discord Logs](#discord-logs)
   - [Prestige Badges](#prestige-badges)
   - [Admin Management](#admin-management)
   - [Leaderboards](#leaderboards)
   - [Full Sync](#full-sync)
3. [API Reference](api/README.md)
     - [Server Exports](api/README.md#Server-Side)
     - [Client Exports](api/README.md#Client-Side)
4. [Developer Tips](#developer-tips)
5. [Notes and Best Practices](#notes-and-best-practices)
6. [License & Credits](#license--credits)


---

##  Overview
A complete **Prestige, XP, Level, and Buff System** for FiveM.  
Standalone, fully customizable, and compatible with all major frameworks.  
Includes **dynamic UI**, **prestige badges**, **killstreak tracking**, **Discord integration**, **leaderboards**, and **modular API exports**.

---

## Features
- Dynamic XP & Prestige UI with smooth progress animation  
- Prestige rewards, badges, and ranking logic  
- Integrated **killstreak effects**, **glowing footsteps**, and **mugshot UI**
- Admin panel with configurable permissions  
- Ox_Lib leaderboard system  
- Discord webhook integration  
- Full server/client API exports for developers  
- JSON persistence with automatic saving  
- Extendable stats & progression logic  

---

## XP System and Prestige Overview
Displays a dynamically colored XP progress bar on UI.  
Progression syncs automatically as players gain XP.

![UI Example](https://github.com/user-attachments/assets/e42a1503-4417-47fb-a100-5b5315df9dcd)

![UI Gif Example](https://github.com/user-attachments/assets/54f9d95b-7427-4a7b-b7a7-be3606657733)


```lua
🛡️ Level 2
[█████░░░░░░░░░] 200 / 250 POINTS
```

---

## Rewards and Killstreaks
Gain prestige points from **player or NPC kills**.  
Reward tiers are open-source via `rewards.lua`.  
Supports QB-Core, ESX, Ox_Inventory, Ox_Lib, or standalone.

Feet glow effects, unique streak titles, and broadcasted achievements.

---

## Mugshot UI
Custom UI popup when a player achieves a killstreak.  
Displays player name, streak, and broadcasts globally.

---

## Discord Logs
Prestige updates, rewards, and killstreaks are logged via Discord webhooks.

---

## Prestige Badges
200 preconfigured prestige badges (`prestiged1` → `prestiged200`).  
Roman numerals, animated display, and texture dictionary support.

![Prestige Badges1](https://github.com/user-attachments/assets/33b64d70-961c-4b7b-8982-d028218a50d1)
![Prestige Badges2](https://github.com/user-attachments/assets/cde29ab6-2023-4821-bf66-f40da368637b)


---

## Admin Management
Admins can add/remove points, set prestige levels, and reset players.

Configured via permissions in `config.lua`.

---

## Leaderboards
Prestige leaderboard integrated via Ox_Lib menu.  
Displays top players dynamically.

---

## Full Sync
Server broadcast ensures prestige levels, buffs, and titles are synced in real time.

---


## Developer Notes

 Fully standalone but integrates with core frameworks  
- Exports allow developers to extend features without modifying core logic  
- Buffs and rewards systems are intentionally open for customization  

---

## Developer Tips

* Always ensure `GetPrimaryIdentifier(source)` returns valid identifiers (`steam:`, `license:`, etc.).
* Use `EnsurePlayerDataServer` only internally.
* Hook this system with your own XP/leveling logic and UI displays.
* Add persistence by implementing JSON saving in `SaveProgression()`.


---

## Server Exports Reference

```lua
exports["mobz-prestiged"]:GetLevel_sv("steam:110000112345678")
exports["mobz-prestiged"]:AddKill_sv(identifier, false)
exports["mobz-prestiged"]:AddBuff_sv(identifier, "damage_boost", "🔥 Damage Boost")
```

Full list includes:
- Core Data Functions
- Basic Getters
- Modifiers
- Buff System
- Achievements & Titles
- Visuals & Prestige Info
- Multipliers
- Leaderboards
- Data Sync
- Developer Tips

(See full code in the Table of Contents Exports API.)

[Server exports](README.md#server-side)

---

## Client Exports Reference

Client-side API mirrors the server version for UI and local effects.

```lua
exports["mobz-prestiged"]:AddKill_cl(id, false)
exports["mobz-prestiged"]:AddBuff_cl(id, "speed_boost", "🏎️ Speed Boost")
exports["mobz-prestiged"]:ClearBuffs_cl(id)
```

(See full code in the Table of Contents Exports API.)

* [Client-Exports-Reference-API](#client-exports-reference-api)


---

## PrestigeAPI Advanced Usage

```lua
local PrestigeAPI = exports["mobz-prestiged"]:PrestigeAPI()
local data = PrestigeAPI.GetFullStats("license:1234567890abcdef")
PrestigeAPI.AddCash("license:1234567890abcdef", 500)
PrestigeAPI.UpdateTokens("license:1234567890abcdef")
```

Supports dynamic updates for cash, XP, reputation, tokens, and titles.

1. [All stats](#all-stats)
---

## Player Stats Reference

| Category | Key | Description | Example |
|-----------|-----|-------------|----------|
| Core | level | Player level | 4 |
| Core | prestige | Prestige rank | 1 |
| Combat | kills | Player kills | 50 |
| Combat | npcKills | NPC kills | 15 |
| Economy | cash | Player balance | 1200 |
| Reputation | reputationTitles | Titles unlocked | ["Novice","Apprentice"] |
| Exploration | distanceTraveled | Distance traveled | 15240 |

(Full table continues in All Stats.)

1. [All stats](#all-stats)


---

## Notes and Best Practices
- Always use `EnsurePlayerDataServer()` before editing data  
- Save changes via `SavePlayer()`  
- Tokens are derived automatically from level  
- Other scripts can expand stats freely  

---

## License & Credits
**MIT License**  
Developed by **Mobz Development**  
[Tebex Store → mobz.tebex.io](https://mobz.tebex.io/)

---

> © 2025 Mobz Development. All rights reserved.

![Mobz](https://i.postimg.cc/RZrBFgCH/ZOMBIEWAR.png)

![Build](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Version](https://img.shields.io/badge/version-1.0.0-yellow)

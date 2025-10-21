# 🏆 Mobz-Prestiged

> The Ultimate Prestige, XP, and Progression Framework for FiveM

A fully modular prestige and XP system for FiveM.  
Includes **dynamic XP/UI bars, prestige ranks, killstreaks, rewards, Discord logs, admin tools, and advanced exports**.  
Supports **QB-Core**, **ESX**, **Ox_Inventory**, and standalone frameworks.

---

## 📑 Table of Contents

<div align="center">

[![Overview](https://img.shields.io/badge/📖_Overview-9b59b6?style=for-the-badge)](#overview)
[![Features](https://img.shields.io/badge/⚙️_Features-8e44ad?style=for-the-badge)](#features)
[![API](https://img.shields.io/badge/🧩_API_Reference-6c5ce7?style=for-the-badge)](exports/README.md)
[![Server Exports](https://img.shields.io/badge/🖥️_Server_Exports-2980b9?style=for-the-badge)](exports/README.md#server-side)
[![Client Exports](https://img.shields.io/badge/💻_Client_Exports-27ae60?style=for-the-badge)](exports/README.md#client-side)

</div>

### 📊 Data & Tables
[![Stats](https://img.shields.io/badge/📊_Stats-00b894?style=for-the-badge)](player-stats/README.md)
[![Tables](https://img.shields.io/badge/📋_Tables-00cec9?style=for-the-badge)](all-exports-table/README.md)

[![License](https://img.shields.io/badge/⚖️_License-3498db?style=for-the-badge)](#license--credits)


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

(See full code in API Sever Full Reference)


### 🧩 API Server Full Reference
[![Server Exports](https://img.shields.io/badge/🖥️_Server_Exports-2980b9?style=for-the-badge)](exports/README.md#server-side)

---

## Client Exports Reference

Client-side API mirrors the server version for UI and local effects.

```lua
exports["mobz-prestiged"]:AddKill_cl(id, false)
exports["mobz-prestiged"]:AddBuff_cl(id, "speed_boost", "🏎️ Speed Boost")
exports["mobz-prestiged"]:ClearBuffs_cl(id)
```

(See full code in the API Client Full Reference)

### 🧩 API Client Full Reference
[![Client Exports](https://img.shields.io/badge/💻_Client_Exports-27ae60?style=for-the-badge)](exports/README.md#client-side)

---

## PrestigeAPI Advanced Usage

```lua
local PrestigeAPI = exports["mobz-prestiged"]:PrestigeAPI()
local data = PrestigeAPI.GetFullStats("license:1234567890abcdef")
PrestigeAPI.AddCash("license:1234567890abcdef", 500)
PrestigeAPI.UpdateTokens("license:1234567890abcdef")

```

Supports dynamic updates for cash, XP, reputation, tokens, and titles.

[![Main Source](https://img.shields.io/badge/🖥️_Main_Source-e81515?style=for-the-badge)](main-source/README.md)


# Advanced Usage	Custom API integration & expansion	Advanced 

##### example:

[![Metadata Stats](https://img.shields.io/badge/🖥️_Metadata_stats-e81515?style=for-the-badge)](metadata-stats/README.md)

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


[![All Stats](https://img.shields.io/badge/🖥️_All_Stats-9c4525?style=for-the-badge)](player-stats/README.md)

---

## 📚 Table of Contents

| 📁 Section | 📝 Description | 🔗 Link |
|------------|----------------|---------|
| 🏠 **Main Docs** | Overview of all features, setup & structure | [Open Main Docs](README.md#features) |
| ⚙️ **API Docs** | Full developer reference for server & client exports | [Go to API Docs](api/README.md) |
| 🖥️ Server Exports | API functions for server-side scripts | [View Server Exports](api/README.md#server-exports) |
| 💻 Client Exports | API functions for client-side scripts | [View Client Exports](api/README.md#client-exports) |
| 📊 **Player Stats** | Trackable stats, progression & dynamic updates | [View Stats](stats/README.md#all-stats) |
| 📋 **Tables Reference** | Data tables, config & level requirements | [Go to Tables](tables/README.md) |
| 🧠 **Advanced Usage** | Custom API integration & expansion | [Advanced Section](README.md#advanced-usage) |
| 🧑‍💻 **Developers** | Credits, license & authors | [Meet the Team](README.md#license--credits) |
[![Config Tables](https://img.shields.io/badge/Tables-Config%20Data-orange?style=for-the-badge)](tables-stats/README.md)

---

## 🚀 Quick Access Badges

<div align="center">

[![API Server](https://img.shields.io/badge/API-Server%20Exports-8A2BE2?style=for-the-badge)](exports/README.md#server-side)
[![API Client](https://img.shields.io/badge/API-Client%20Exports-8A2BE2?style=for-the-badge)](exports/README.md#client-side)
[![All Stats](https://img.shields.io/badge/Stats-All%20Stats-00b894?style=for-the-badge)](player-stats/README.md)
[![Config Tables](https://img.shields.io/badge/Tables-Config%20Data-orange?style=for-the-badge)](table-stats/README.md)
[![All Exports](https://img.shields.io/badge/All-Exports%20Data-yellow?style=for-the-badge)](all-exports-table/README.md)

---

## 🧾 About Mobz Development

>> A modular, open framework for prestige progression, player stats,  
>> and game-wide expansion — designed for flexibility and integration.

---

## Notes and Best Practices
>> Always use `EnsurePlayerDataServer()` before editing data  
>> Save changes via `SavePlayer()`  
>> Tokens are derived automatically from level  
>> Other scripts can expand stats freely  


---


## ⚖️ License

Licensed under **MIT License**  
© 2025 **Mobz Development** All rights reserved.

---

<div align="center">

<!-- Logo -->
<img src="https://i.postimg.cc/RZrBFgCH/ZOMBIEWAR.png" alt="Mobz Logo" width="200" style="border-radius:15px; margin-bottom:10px;" />

# 🏆 **Mobz-Prestiged**
### *The Ultimate Prestige, XP, and Progression Framework for FiveM*

---

<!-- Team / Credits -->
[![Mobz & Mez](https://img.shields.io/badge/Mobz%20%26%20Mez-Lead%20Developers-8A2BE2?style=for-the-badge&logo=github)](README.md#license--credits)
[![Mobz Development](https://img.shields.io/badge/Mobz%20Development-Official-purple?style=for-the-badge)](README.md)

---

<!-- Frameworks -->
[![QB-Core](https://img.shields.io/badge/Framework-QB--Core-orange?style=for-the-badge)](https://github.com/qbcore-framework/qb-core)
[![ESX](https://img.shields.io/badge/Framework-ESX-red?style=for-the-badge)](https://github.com/esx-framework/es_extended)
[![Standalone](https://img.shields.io/badge/Standalone-Compatible-green?style=for-the-badge)](#overview)

<!-- Quick Actions -->
[![Discord](https://img.shields.io/badge/Discord-Join%20Us-5865F2?logo=discord&logoColor=white&style=for-the-badge)](https://discord.gg/YOURINVITE)
[![Tebex](https://img.shields.io/badge/Tebex-Store-00b894?style=for-the-badge)](https://mobz.tebex.io)
[![FiveM](https://img.shields.io/badge/FiveM-Framework-orange?style=for-the-badge&logo=fivem)](https://fivem.net)

---

![Build](https://img.shields.io/badge/Build-Passing-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)
![Version](https://img.shields.io/badge/Version-1.0.0-yellow?style=flat-square)

</div>

---

<div align="center">

### 🧭 Navigation & Links

---

<!-- Primary Navigation -->
[![⬆️ Back to Top](https://img.shields.io/badge/⬆️_Back_to_Top-9b59b6?style=for-the-badge)](../mobz-prestiged-documentations/README.md)

[![🏠 Main Docs](https://img.shields.io/badge/🏠_Main_Documentation-8e44ad?style=for-the-badge)](../README.md)

---

<!-- Community & Support -->
[![💬 Discord](https://img.shields.io/badge/💬_Join_Our_Discord-5865F2?logo=discord&logoColor=white&style=for-the-badge)](https://discord.gg/a6qECrxuCg)
[![🛒 Tebex](https://img.shields.io/badge/🛒_Visit_Our_Store-00b894?style=for-the-badge)](https://mobz.tebex.io)

---

**© 2025 Mobz & Mez Development**  
*Crafted with 💜 by developers, for developers.*

</div>

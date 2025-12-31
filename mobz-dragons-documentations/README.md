###### top of page

<div align="center">

<!-- Logo -->
<img src="https://i.postimg.cc/RZrBFgCH/ZOMBIEWAR.png" alt="Mobz Logo" width="200" style="border-radius:15px; margin-bottom:10px;" />

---

# 🐉 Mobz Dragons - FiveM Dragon Companion System
**Version:** 2.x
**Author:** [mobz]
**Frameworks Supported:** QB-Core, ESX, Ox-Inventory
**Dependencies:** ox_lib, mobz-dependencies, MySQL

---

## A fully-featured dragon companion system for FiveM servers, with advanced stats, flying, combat, and growth mechanics. Designed for **immersive gameplay**, **multiplayer sync**, and **server-authoritative persistence**.

---

## 📚 Table of Contents
[![Overview](https://img.shields.io/badge/📖_Overview-9b59b6?style=for-the-badge)](#overview)
[![Features](https://img.shields.io/badge/⚙️_Features-8e44ad?style=for-the-badge)](#features)
[![API](https://img.shields.io/badge/🧩_API_Reference-6c5ce7?style=for-the-badge)](exports/README.md)
 * [![Server Exports](https://img.shields.io/badge/🖥️_Server_Exports-2980b9?style=for-the-badge)](exports/README.md#server-side)
 * [![Client Exports](https://img.shields.io/badge/💻_Client_Exports-27ae60?style=for-the-badge)](exports/README.md#client-side)


---

### 📊 Data & Tables
[![Stats](https://img.shields.io/badge/📊_Stats-00b894?style=for-the-badge)](player-stats/README.md)
[![Tables](https://img.shields.io/badge/📋_Tables-00cec9?style=for-the-badge)](all-exports-table/README.md)

---

 ### ⚙️ Installation Guide
[![Installation](https://img.shields.io/badge/⚙️_Installation-00b894?style=for-the-badge)](installation/README.md)

</div>

---

| 📁 Section | 📝 Description | 🔗 Link |
|------------|----------------|---------|
| ⚙️ **Installation** | Please follow the installation steps carefully to ensure proper setup.| [Installation Steps](installation/README.md) |
| 🏠 **Main Docs** | Overview of all features, setup & structure | [Open Main Docs](README.md#features) |
| 🧩 **API Docs** | Full developer reference for server & client exports | [Go to API Docs](exports/README.md) |
| 🖥️ Server Exports | API functions for server-side scripts | [View Server Exports](exports/README.md#server-side) |
| 💻 Client Exports | API functions for client-side scripts | [View Client Exports](exports/README.md#client-side) |
| 📊 **Player Stats** | Trackable stats, progression & dynamic updates | [View Stats](player-stats/README.md) |
| 📋 **Tables Reference** | Data tables, config & level requirements | [Go to Tables](tables-stats/README.md) |
| 🧠 **Advanced Usage** | Custom API integration & expansion | [Advanced Section](main-source/README.md) |
| 🧑‍💻 **Developers** | Credits, license & authors | [Meet the Team](README.md#mobz-team) |


---

## 📦 Features Overview
# Overview

---

### 🐲 Dragon Lifecycle
 # Mount & Dismount System

  * Server-authoritative mounting with proper seat management
  * Smooth animations for rider and dragon
  * Flying state management: grounded → takeoff → hover → fly → glide → landing

 **Dragon Stats & Growth**

  * XP-based leveling and stage system
  * Max health, stamina, speed, damage scaling per stage
  * Upgrade system with persistent buffs and custom effects

 **Vitals System**

  * Hunger and health mechanics
  * Hunger drains only while mounted
  * Health drains automatically if hunger falls below threshold
  * Feeding system with items that restore health or hunger
  * XP-lock mechanics for advanced food (requires a certain dragon experience)


### ✈️ Flight & Movement

* Full flight physics (hover, fly, glide)
* Takeoff and landing animations
* Speed levels with controls:

  * **W** – forward
  * **S** – stop / descend
  * **SPACEBAR** – takeoff
  * **Shift** – glide boost
* Automatic landing when dragon is exhausted or hunger low
* Gestures while riding (forward, left, right, down) with seat-awareness


### 💀 Combat & Abilities (Optional Expansion)

* Dragon abilities synchronized across all players
* Damage multipliers scale with stage and upgrades
* Abilities can have multi-stage effects for progression


### 🍗 Feeding & Inventory

* Configurable food items with different restore amounts
* Server checks for actual inventory items before consumption
* XP requirements per food item
* Fully compatible with:

  * **QB-Core** inventory
  * **ESX** inventory
  * **Ox-Inventory**

---

### 🛠 Admin & Server Features
# Admin & Server Features

* Server-authoritative dragon vitals & stats
* Automatic hunger and health drain via server tick
* Admin-friendly dragon spawning, stage reset, and XP addition
* Mounted dragon tracking per player
* Full database persistence: health, hunger, XP, upgrades, stage

--- 

## 🔧 Controls Summary
# Controls Summary

| Action           | Key / Control | Notes                               |
| ---------------- | ------------- | ----------------------------------- |
| Forward          | W             | Moves dragon forward (ground & air) |
| Back / Descend   | S             | Stop movement / descent             |
| Takeoff          | SPACE         | Launch dragon if hunger > threshold |
| Speed Up / Down  | 1 / 3         | Adjust flight speed                 |
| Gestures         | W/A/S/D       | Animated gestures while flying      |
| Mount / Dismount | E (example)   | Attach or detach dragon from player |

> ⚠️ Hunger < 15 → Dragon cannot take off

---

## 🏗 Configurable Options
# Configurable Options

 **DragonVitals**

  * Max health & hunger
  * Hunger drain rates
  * Health drain when starving
  * Flight lock thresholds

 **XP & Stage Config**

  * XP per action (flight, landing, takeoff)
  * Stage upgrades with stat multipliers

 **Feeding Items**

  * Customizable restore values for hunger & health
  * XP requirements per item

 **Animations & Gestures**

  * Rider gestures per key
  * Dragon flight animations per mode

---

## 💾 Database Structure
# Database Structure
* `mobz_dragons` – stores dragon stats, health, hunger, XP, stage, and unique key
* `mobz_dragon_upgrades` – stores applied upgrades per dragon
* Fully compatible with **MySQL** and **async/await** pattern for server-side operations

---

## ⚡ Advanced Features
# Advanced Features
* **Server-authoritative mechanics** for true multiplayer consistency
* **Dynamic dragon stats** per stage with upgrades applied automatically
* **Statebag sync** for other players to see your dragon stats in real-time
* **Configurable flight physics & gestures** for immersive RPG experience
* **XP-based feeding** locks for progression-based gameplay

---

## 🎮 Player Experience
# Player Experience
* Own, ride, and grow your dragon companion
* Train your dragon to fly higher, fight harder, and survive longer
* Customize feeding and abilities for optimal performance
* Experience a fully immersive dragon companion system synced across the server

---

## 📌 Installation
# Installation
1. Copy the `mobz-dragons` resource to your server resources folder
2. Ensure dependencies are installed: `ox_lib`, `mobz-dependencies`, `MySQL-async`
3. Add to server.cfg:

```cfg
ensure mobz-dependencies
ensure mobz-dragons
```

4. Configure dragon items, stats, XP, and animations in `config.lua`
5. Restart server

---

## 📄 Notes
# Notes
* Fully **multiplayer-safe**: All stats, vitals, and mounts are synced via server events
* Designed for **high performance**, using async DB calls and server-side ticks
* Compatible with **QB-Core, ESX, Ox-Inventory**

---

## 📊 Advanced Visuals & Flowcharts
# Advanced Visuals & Flowcharts

For a quick visual overview:

### Dragon Lifecycle Flow

---

```
Grounded --> Takeoff --> Hover --> Fly --> Glide --> Landing --> Grounded
```
---

### Vitals Flow

---

```
Mounted? --> Yes: Hunger drains per tick --> Hunger < threshold? --> Apply Health Damage
```

---

### Stats Upgrade Chart

* Stage 1: Base Health, Speed, Damage
* Stage 2+: Incremental buffs applied automatically per XP + upgrades
* Upgrades modify base stats dynamically


---
```
| Stage | Health | Speed | Damage |
|-------|--------|-------|--------|
| 1     | 1000   | 1.0x  | 1.0x   |
| 2     | 1200   | 1.1x  | 1.2x   |
| 3     | 1500   | 1.2x  | 1.5x   |
```

> These charts are fully configurable in `Config.lua` for server customization.

----


### 🧩 API Server Full Reference
[![Server Exports](https://img.shields.io/badge/🖥️_Server_Exports-2980b9?style=for-the-badge)](exports/README.md#server-side)

---

[![🛡️ Main Source](https://img.shields.io/badge/🛡️%20Main%20Source-e32614?style=for-the-badge)](main-source/README.md)


---

## 🚀 Quick Access

<div align="center">

[![API Server](https://img.shields.io/badge/API-Server%20Exports-2980b9?style=for-the-badge)](exports/README.md#server-side)
[![API Client](https://img.shields.io/badge/API-Client%20Exports-27ae60?style=for-the-badge)](exports/README.md#client-side)
[![All Stats](https://img.shields.io/badge/Stats-All%20Stats-e81798?style=for-the-badge)](player-stats/README.md)
[![Config Tables](https://img.shields.io/badge/Tables-Config%20Data-orange?style=for-the-badge)](table-stats/README.md)
[![All Exports](https://img.shields.io/badge/All-Exports%20Data-yellow?style=for-the-badge)](all-exports-table/README.md)

---

<!-- Team / Credits -->
[![Mobz & Mez](https://img.shields.io/badge/Mobz%20%26%20Mez-Lead%20Developers-8A2BE2?style=for-the-badge&logo=github)](README.md#license--credits)
[![Mobz Development](https://img.shields.io/badge/Mobz%20Development-Official-purple?style=for-the-badge)](../README.md)

---

<!-- Frameworks -->
[![QB-Core](https://img.shields.io/badge/Framework-QB--Core-orange?style=for-the-badge)](https://github.com/qbcore-framework/qb-core)
[![ESX](https://img.shields.io/badge/Framework-ESX-red?style=for-the-badge)](https://www.esx-framework.org)
[![Standalone](https://img.shields.io/badge/Standalone-Compatible-green?style=for-the-badge)](#overview)

<!-- Quick Actions -->
[![Discord](https://img.shields.io/badge/Discord-Join%20Us-5865F2?logo=discord&logoColor=white&style=for-the-badge)](https://discord.gg/a6qECrxuCg)
[![Tebex](https://img.shields.io/badge/Tebex-Store-00b894?style=for-the-badge)](https:/zombie-war.tebex.io)
[![FiveM](https://img.shields.io/badge/FiveM-Framework-orange?style=for-the-badge&logo=fivem)](https://fivem.net)

---

![Build](https://img.shields.io/badge/Build-Passing-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)
![Version](https://img.shields.io/badge/Version-1.0.0-yellow?style=flat-square)

 ---

## 🧠 About Mobz Development
##### mobz team

> **Mobz Development** is powered by a shared vision — building modular, open-source frameworks that connect every part of gameplay.  
> From prestige progression to player stats and crafting, our goal is to make development simpler, smarter, and more powerful.

This project — and everything we’ve built together — exists because of **trust, dedication, and teamwork**.  
A special thank you to **Mez**, who’s always had my back since day one. 💜  

[![Mobz & Mez](https://img.shields.io/badge/Mobz%20%26%20Mez-Lead%20Developers-8A2BE2?style=for-the-badge&logo=github)](README.md#license--credits)
[![Mobz Development](https://img.shields.io/badge/Mobz%20Development-Official-purple?style=for-the-badge)](../README.md)

---

## 🔒 License & Distribution (Commercial / Tebex)

**Important:** This resource is sold as a paid, **closed-source** product through **Tebex**.  
It is **not** released under an open-source license.

- Redistribution, modification, or sharing of this resource without a valid purchase and explicit permission from Mobz Development is **strictly prohibited**.
- If you purchased this resource, your purchase grants you a license to use it according to the terms shown on the Tebex store page and the license file included with your download.
- For license questions, refunds, or support, please contact the seller through the Tebex store listing or the contact information provided with your purchase.

---

<!-- Community & Support -->
[![💬 Discord](https://img.shields.io/badge/💬_Join_Our_Discord-5865F2?logo=discord&logoColor=white&style=for-the-badge)](https://discord.gg/a6qECrxuCg)
[![🛒 Tebex](https://img.shields.io/badge/🛒_Visit_Our_Store-00b894?style=for-the-badge)](https://zombie-war.tebex.io)


---

**© 2025 Mobz & Mez Development**  
*Crafted with 💜 by developers, for developers.*

---

<!-- Primary Navigation -->
[![⬆️ Back to Top](https://img.shields.io/badge/⬆️_Back_to_Top-9b59b6?style=for-the-badge)](README.md#top-of-page)

</div>

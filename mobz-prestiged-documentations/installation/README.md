[![← Back to Main Docs](https://img.shields.io/badge/←_Back_to_Main_Docs-9c2590?style=for-the-badge&logo=mobz%20development)](../README.md)



## 📂 Installation

## Step 1. 

- Download and place mobz-prestiged into your server’s resources folder.

2.  Add **prestiged** group t0 cfg

---

```	
add_ace group.prestiged group.prestiged allow
```lua

---

3. Assign *group* on cfg

**EXAMPLE ADD TO CFG**
##### Assign specific people to the group. - add to cfg Use license or steam or both with your real license or steam

```add_principal identifier.license:132ff6c5376744059dd3cb8ed8571b4c54f0f579 group.prestiged```

- REPLACE WITH YOUR REAL ` license:132ff6c5376744059dd3cb8ed8571b4c54f0f579 `

---
## Step 2.

**Ensure dependencies:
- mobz-dependecies
- ox_lib

- Add **dependencies**: 

  * mobz-dependecies
  * ox_lib
  
- mobz-dependecies -  https://github.com/Mobzeyy/Mobz-Development-Scripts/tree/main/mobz-dependencies

---
## Step 3.
- Add to your server.cfg:

**Add to your server.cfg:
ensure oxmysql
ensure ox_lib
ensure mobz-dependencies
ensure mobz-prestiged

---

---

# ⚙️ Mobz-Prestiged — Installation Guide

A modular prestige and rewards framework designed for FiveM servers.  
Before using, please follow the installation steps carefully to ensure proper setup.

---

## 🧩 Step 1. Dependencies

Make sure you have the required dependency installed:  
```
mobz-dependencies
```

This resource is required for all Mobz systems to function properly.

---

## 🪄 Step 2. Resource Order

In your **server.cfg**, ensure resources are started in this order:
```cfg
ensure mobz-dependencies
ensure mobz-prestiged
```

> ⚠️ The order is **important** — `mobz-dependencies` must start before `mobz-prestiged`.

---

## ⚙️ Step 3. Configure mobz-dependencies

Navigate to:
```
mobz-dependencies/config.lua
```
Adjust any required configuration values (framework detection, logging, etc.) to match your server’s setup (ESX, QBCore, custom framework, etc.).

---

## 🧠 Step 4. Configure mobz-prestiged

Open and edit:
```
mobz-prestiged/config.lua
```
Customize settings such as:
- Prestige levels  
- Level rewards  
- Themes and UI options  
- Export toggles  

---

## 📂 Open Source Files

The following files are open and customizable for developers:
```
mobz-prestiged/server/rewards.lua     -- Manage reward logic
mobz-prestiged/server/exports.lua     -- Server-side exports
mobz-prestiged/client/exports.lua     -- Client-side exports
```

These are intentionally left editable to allow you to expand or integrate the system with your own logic.

---

## ✅ Done!

Once everything is configured:
1. Restart your server  
2. Join the game  
3. Enjoy your new prestige system! 🎉  

---

## 🧾 Optional

You may also explore other Mobz modules for full ecosystem integration:
- `mobz-driving`
- `mobz-reputation`
- `mobz-achievements`
- `mobz-crafting`

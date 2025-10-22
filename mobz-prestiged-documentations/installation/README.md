[![← Back to Main Docs](https://img.shields.io/badge/←_Back_to_Main_Docs-9c2590?style=for-the-badge&logo=mobz%20development)](../README.md)


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

[![← Back to Main Docs](https://img.shields.io/badge/←_Back_to_Main_Docs-9c2590?style=for-the-badge&logo=mobz%20development)](../README.md)

# ⚙️ Mobz-Prestiged — Installation Guide
# Installation Guide

A modular prestige and rewards framework designed for FiveM servers.  
Before using, please follow the installation steps carefully to ensure proper setup.

---

#  📂 Installation

# Step 1. 

- Download and place mobz-prestiged into your server’s resources folder.

# Step 2  Add **prestiged** group to cfg

---

```
add_ace group.prestiged group.prestiged allow
```

---

# Step 3. Assign *group* on cfg

---

```
add_principal identifier.license:132ff6c5376744059dd3cb8ed8571b4c54f0f579 group.prestiged
```

---

- REPLACE WITH YOUR REAL ` license:132ff6c5376744059dd3cb8ed8571b4c54f0f579 `

---

# Step 4. Required dependency installed:  

- Add **dependencies**:
  
- mobz-dependecies -  https://github.com/Mobzeyy/Mobz-Development-Scripts/tree/main/mobz-dependencies

- Add to your server.cfg:

---

```
ensure ox_lib
ensure mobz-dependencies
ensure mobz-prestiged
```
---

## This resource is required for all Mobz systems to function properly.

---

---

layout: ../../../../layouts/Main.astro
title: "Portal Plugin"
description: "This Plugin creates portal gates where the player can port or beam from one place to another."
author: "j0n4s"
version: "3.0.0+"
images: ["https://i.imgur.com/ChQzzPI.png"]
keywords: ["free", "client", "server", "data"]
url: "https://github.com/jonasesser/altv-athena-plugin-portal"
discord: "j0n4s#8301"

---

# Portal Plugin

This Plugin creates portals where the player can port/beam from one place to another.

# Features

- Create Portal with two gates

# Features in progress

- Create Portals with multiple gates (e.g. for lifts)
- Player menu
- Admin menu
- Dimension and IPL Support

# Installation

1. Get plugin here

https://mygp.gumroad.com/l/portalplugin
    
2. Copy Folder plugins/gpPortal/ to your athena project under src/core/plugins/
3. Import server plugin in src/core/plugins/imports.ts:

    ```import './gpPortal/index';```

# Usage

1. In-Game as administrator

    ```/addportal [name] - Adds a portal at current position```

2. See video

https://youtu.be/7Nygyl0uFA0
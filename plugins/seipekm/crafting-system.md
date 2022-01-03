---

layout: ../../../../layouts/Main.astro
title: "Crafting System Premium Plugin"
description: "Crafting Spots and Crafting Items"
author: "SeipekM"
version: "3.0.0+"
images: ["https://i.imgur.com/XXdxm6i.png"]
keywords: ["premium", "server", "player", "system"]
url: "seipekm.gumroad.com/l/byzby"
price: "15.00"
discord: "seipekm#0300"

---

# Crafting System Premium Plugin

## Features
- Add Crafting Points and Crafting Item over config file (craftingList.ts)
- Consumables are checked if they are available

# Installation Instructions

- Drop the plugins files into plugins.
- Crafting Points change over craftingList.ts
- Item change over item.ts

### imports.ts (Serverside)
```ts
import './seipekm-crafting-system/index';
```
---

layout: ../../../../layouts/Main.astro
title: "Crafting System Premium Plugin"
description: "Crafting Spots and Crafting Items"
author: "SeipekM"
version: "2.0.3"
images: ["https://i.imgur.com/XXdxm6i.png"]
keywords: ["premium", "server", "player", "system"]
url: "https://shoppy.gg/product/e7taL5J"
price: "15.00"
discord: "seipekm#0300"

---

# Farming System Premium Plugin

## Features
- Add Crafting Points and Crafting Item over config file (craftingList.ts)
- Consumables are checked if they are available

# Installation Instructions

- Drop the plugins files into plugins.
- Crafting Points change over craftingList.ts
- Item change over item.ts

### imports.ts (Serverside)
```ts
'./craftingsystem/index',
'./craftingsystem/items',
```
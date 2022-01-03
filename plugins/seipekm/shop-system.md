---

layout: ../../../../layouts/Main.astro
title: "Shop System Premium Plugin"
description: "Shop System"
author: "SeipekM"
version: "3.0.0+"
images: ["https://i.imgur.com/D36ox7s.png"]
keywords: ["premium", "server", "player", "system"]
url: "seipekm.gumroad.com/l/yeysa"
price: "30.00"
discord: "seipekm#0300"

---

# Shop System Premium Plugin

## Features
- Buying items
- Create store pos. via file
- Create store items via file 
- Create store type via file
- Distinction card or cash payment

# Installation Instructions

- Drop the plugins files into plugins.
- Drop the client-plugins files into client-plugins.
- Drop the webview files into webview.
- Store type and items adjustable via shopInfoList.ts
- Store position adjustable via shopList.ts

### imports.ts (Serverside)
```ts
import './seipekm-shop-system/index';
```

### imports.ts (Clientside)
```ts
import './seipekm-shop-system/index';
```
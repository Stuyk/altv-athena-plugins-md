---
layout: ../../../../layouts/Main.astro
title: 'PedController'
description: "PedController which allows you to spawn Peds with Textlabels Ingame."
author: 'Der Lord!'
version: '3.0.0+'
images: ['https://imgur.com/a/fwYk3VA', 'https://user-images.githubusercontent.com/82890183/147367516-091263a4-a68b-4deb-81b3-18040cf00bd6.png']
keywords: ['premium', 'player', 'system', 'client', 'interface']
url: 'https://holylord.gumroad.com/l/osfel'
price: "5.00"
discord: "Der Lord!#6021"
---

## Features
* Allows you to add Peds Ingame
* Allows you to add Textlabels to Peds as well

## To Follow
* Remove Peds Ingame

## Known Bugs
- None yet

## SETUP

- Drop the client-plugins files into client-plugins.
- Drop the plugins files into plugins.

imports.ts (Clientside)

```ts 
import './AthenaPeds/index';
```

imports.ts (Serverside)
```ts
'./AthenaPeds/index',
```


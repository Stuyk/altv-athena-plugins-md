---
layout: ../../../../layouts/Main.astro
title: 'Athena Doorlock System'
description: "Doorsystem which enables you to lock/unlock door based on a player or faction."
author: 'Der Lord!'
version: '3.0.0+'
images: ['https://user-images.githubusercontent.com/82890183/136729801-b86dc411-56e7-4d90-b8fb-a308143823b4.png']
keywords: ['free', 'player', 'system', 'streamer', 'client']
url: 'https://github.com/Booster1212/AthenaDoorlock'
---

### Features
* Add Doors Ingame
* Remove Doors Ingame
* Bind to factions
* Database over hardcoded JSON-List files.
* Interface has options to expand it with keys, player binding and whatever you want.

### HOW TO USE
* Press NUM8 Ingame to open the doormenu (no admin check right now, everyone can use it actually, maybe ill add it next few days.)
* Put in a name in the input menu, name of the prop (gets hashed automatically) and maybe some faction id. (0 means everyone can use the door-interaction.)
* Doors can be removed in the wheelmenu of NUM8 as well.

### SETUP

- Drop the client-plugins files into client-plugins.
- Drop the plugins files into plugins.
- Add “doors” to your MONGO_COLLECTIONS= in the .env file.

imports.ts (Clientside)
```typescript 
import './AthenaDoorlock/main';
import './AthenaDoorlock/wheelmenu';
```
imports.ts (Serverside)
```typescript
'./AthenaDoorlock/main',
'./AthenaDoorlock/streamer',
'./AthenaDoorlock/interface',
```


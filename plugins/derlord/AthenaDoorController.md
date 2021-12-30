---
layout: ../../../../layouts/Main.astro
title: 'Athena DoorController v3'
description: 'Full dynamic DoorController which allows you to manage doors ingame.'
author: 'Der Lord!'
version: '3.0.0+'
images: ['https://user-images.githubusercontent.com/82890183/147709903-28af3180-38fe-4aa0-b11e-70813c11df79.png', 'https://user-images.githubusercontent.com/82890183/147631180-c26ff168-ab1c-4ae8-83ab-fa152e2e665d.png', 'https://user-images.githubusercontent.com/82890183/147631218-c2468894-1b0a-4a6b-ac0a-a5f7cb6a5f5f.png']
keywords: ['free', 'player', 'system', 'streamer', 'client']
url: 'https://github.com/Booster1212/AthenaDoorlock'
discord: 'Der Lord!#6021'
---

# Athena Framework - DoorController v3


![Fichier 22mdpi](https://user-images.githubusercontent.com/82890183/147709903-28af3180-38fe-4aa0-b11e-70813c11df79.png)

### Features
- Build on the Athena Framework <3
- Completly manage doors ingame, add, remove, read data, change lockstates
- GTA V default doors will be automatically found. No need to search through Codewalker. All door props should be inside of the doors-props.json.
- Full Database Integration. No Hardcoded .ts files or either JSON Lists.
- Integrated database Keys (changeable locks soon.)
- Configurable to your likings for example disableTextlabel, set range for all Labels, custom collection and more.

## Setup - General
- Just import the stuff from AthenaDoorController_Client in a new folder here -> src/core/client-plugins/newFolderName

- Import the stuff from AthenaDoorController_Server in a new folder here -> src/core/plugins/newFolderName

## Setup (MongoDB) 
- Add a new collection in your MongoDB Compass call it 'doors-props', add "doors-props" there. Just import the Database File i've added here. Key to open the Vue Menu is ","

## Setup Vue / Athena Page
- Go to /src-webivews/pages and create a new Folder called "DoorController" in there.
- Copy the DoorController.vue file of the repos Webview folder inside of that folder.
- Add to components.ts (src-webviews/) -> import DoorController from './DoorController/DoorController.vue';
- Add to components.ts (src-webviews/) -> DoorController: shallowRef(DoorController)

##Imports Server/Client
```typescript
// Imports on plugin/imports.ts
import './AthenaDoorController/index';

// Imports on client-plugins/import.ts
import './AthenaDoorController/index';
import './AthenaDoorController/src/doors-vue';
import './AthenaDoorController/src/client-events-vue';
import './AthenaDoorController/src/client-functions';
import './AthenaDoorController/src/client-streamer';
import './AthenaDoorController/src/client-events';
```

## Events - Scripting - Not available yet.
```typescript
// Clientside Events

// Serverside Events

// Vue To Client Events

// Client To Client Events

// Server To Server Events
```

## Images
  
![image](https://user-images.githubusercontent.com/82890183/147631180-c26ff168-ab1c-4ae8-83ab-fa152e2e665d.png)
  
![image](https://user-images.githubusercontent.com/82890183/147631218-c2468894-1b0a-4a6b-ac0a-a5f7cb6a5f5f.png)

Join my plugin discord -> https://discord.gg/Pk6gQ2agbQ
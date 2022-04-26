---
layout: ../../../../layouts/Main.astro
title: 'AthenaPlantController'
description: "Be some funny weed gardener and manage your plants."
author: 'Der Lord!'
version: '3.0.0+'
images: ['https://user-images.githubusercontent.com/82890183/148577251-49ab503c-c795-4bb3-896a-99b4d04c6910.png', 'https://user-images.githubusercontent.com/82890183/147868854-2354f997-12f6-41a4-a6d0-993f96a208e6.png', 'https://user-images.githubusercontent.com/82890183/147867739-5123726b-0c8a-4e42-8cbe-4bd6e34835c9.png', 'https://user-images.githubusercontent.com/82890183/147867743-d105fedf-f559-4136-acfd-bc585d7a9c61.png']
keywords: ['free', 'player', 'system']
url: 'https://github.com/Booster1212/AthenaPlantController'
discord: 'Der Lord!#6021'
---
# Athena Framework - PlantController

![Fichier 29mdpi](https://user-images.githubusercontent.com/82890183/147866518-ca690889-0a1a-4ac8-9831-54b3b762b1ec.png)

## Have you always wanted to be a weed gardener? This is your chance! 
This plugin for the Athena Framework allows you to grow different strains with different times! 
The harvest of your plant is freely determinable, depending on how long your plant needs to grow.

## Features
- Different varieties with different adjustable yields!
- Sow, fertilize, water and harvest your plants!
- Adjustable according to your wishes!
- Create as many plant spots as you like!
- Custom animations for sowing, fertilizing, watering and harvesting!

## Setup & Imports
- Create a new folder called "AthenaPlantController" and drop stuff from this branch there.
- Since this is an serverside plugin we just need to import the index.ts file.
- Database and default items will be created on the first bootup of the Athena Framework.
```typescript
// src/core/plugins/import.ts ->
import './AthenaPlantController/index';
```

## Setup Items
- Be careful that you'll need same type & variety!
- Seeds need to be in Toolbar Slot 0 for now!

```typescript
// Seeds (Build a new Plant)
export const seeds = [
    { name: 'Northern Haze Seeds', description: 'Casual seeds for the casual grower.', type: 'Indica', variety: 'Northern Haze', time: 10 },
    { name: 'OG Kush Seeds', description: 'Casual seeds for the casual grower.', type: 'Indica', variety: 'OG Kush', time: 10 },
    { name: 'Purple Haze Seeds', description: 'Casual seeds for the casual grower.', type: 'Indica', variety: 'Purple Haze', time: 10 },
    { name: 'Lemon Haze Seeds', description: 'Casual seeds for the casual grower.', type: 'Sativa', variety: 'Lemon Haze', time: 10, },
    { name: 'Mango Kush Seeds', description: 'Casual seeds for the casual grower.', type: 'Ruderalis', variety: 'Mango Kush', time: 10 }
]

// Buds (Harvesting a Plant)
export const buds = [
    { name: 'Northern Haze Buds', description: 'Result of harvesting Northern Haze seeds.', type: 'Indica', variety: 'Northern Haze', amount: 100 },
    { name: 'OG Kush Buds', description: 'Result of harvesting OG Kush seeds.', type: 'Indica', variety: 'OG Kush', amount: 50 },
    { name: 'Purple Haze Buds', description: 'Result of harvesting Purple Haze seeds.', type: 'Indica', variety: 'Purple Haze', amount: 100 },
    { name: 'Lemon Haze Buds', description: 'Result of harvesting Lemon Haze seeds.', type: 'Sativa', variety: 'Lemon Haze', amount: 100 },
    { name: 'Mango Kush Buds', description: 'Result of harvesting Mango Kush seeds.', type: 'Ruderalis', variety: 'Mango Kush', amount: 100 }
]
```

## Default Settings

```typescript
export const ATHENA_PLANTCONTROLLER = {
    name: 'PlantController',
    version: 'v1.0',
    useDiscordLogs: false,
    discordChannel: 'someChannelId',
};

export const PLANTCONTROLLER_DATABASE = {
    collectionName: 'plants', // Change me before booting if you need to.
};

export const PLANTCONTROLLER_SETTINGS = {
    smallPot: 'bkr_prop_weed_01_small_01a', // LEAVE ME ALONE
    mediumPot: 'bkr_prop_weed_med_01a', // LEAVE ME ALONE
    largePot: 'bkr_prop_weed_lrg_01a', // LEAVE ME ALONE
    updateInterval: 3000, // Used to set the timer's update Interval.
    distanceToSpot: 10,
    interactionRange: 1,
    textLabelDistance: 3,
};

// use 'default' to skip animations.
// Example ->
// seedingAnimName: 'default',
// seedingAnimDict: 'default',
export const PLANTCONTROLLER_ANIMATIONS = {
    seedingAnimName: 'base',
    seedingAnimDict: 'amb@world_human_gardener_plant@male@base',
    seedingAnimDuration: 3000,

    fertilizingAnimName: 'base',
    fertilizingAnimDict: 'amb@world_human_gardener_plant@male@base',
    fertilizingAnimDuration: 3000,

    waterAnimName: 'base',
    waterAnimDict: 'amb@world_human_gardener_plant@male@base',
    waterAnimDuration: 3000,

    harvestAnimName: 'base',
    harvestAnimDict: 'amb@world_human_gardener_plant@male@base',
    harvestAnimDuration: 3000,
};

/**
* The `PLANTCONTROLLER_SPOTS` array contains the locations of the spots where the plants
can be placed.
*/
export const PLANTCONTROLLER_SPOTS: alt.Vector3[] = [
    { x: -1625.6290283203125, y: 3165.891357421875, z: 29.933713912963867 } as alt.Vector3,
    { x: 3705.656982421875, y: 3079.053955078125, z: 13.06076717376709 } as alt.Vector3,
    { x: 3693.6142578125, y: 4932.6845703125, z: 18.710264205932617 } as alt.Vector3,
    { x: 2505.236328125, y: -2110.73095703125, z: 30.00033950805664 } as alt.Vector3,
];

/**
 * The `PLANTCONTROLLER_TRANSLATIONS` enum is used to store the text that will be displayed in the
 * UI when the player interacts with a plant.
 */
export enum PLANTCONTROLLER_TRANSLATIONS {
    // Related to general
    notInRange = 'Not in range of a valid plant spot!',
    // Related to Interaction Controllers.
    seedsRequired = 'Requires Seeds.',
    fertilizerRequired = 'Requires Fertilizer.',
    waterRequired = `Requires Water.`,
    seedingInteraction = 'Plant Seeds',
    fertilizingInteraction = 'Fertilize',
    waterInteraction = 'Water Plant',
    harvestable = 'Harvestable',
}
```
## Scripting Example 
```typescript
alt.on('PlantController:Server:CreatePot', (player: alt.Player, data: Item) => {
    PlantController.addPlant(player, {
        model: PLANTCONTROLLER_SETTINGS.smallPot,
        shaIdentifier: PlantController.generateShaId(player),
        data: {
            owner: player.data.name,
            variety: '',
            type: '',
            seeds: false,
            fertilized: false,
            state: PLANTCONTROLLER_TRANSLATIONS.seedsRequired,
            remaining: 1337, // Don't touch. Different Times for Different Seeds? ;)
            startTime: 1337, // Don't touch.
            water: 0,
            harvestable: false,
        },
        position: { x: player.pos.x + 1, y: player.pos.y, z: player.pos.z - 1 } as alt.Vector3,
    });
});
```

## Issues
- A few left i guess ;)


## Images

![image](https://user-images.githubusercontent.com/82890183/147868854-2354f997-12f6-41a4-a6d0-993f96a208e6.png)

![image](https://user-images.githubusercontent.com/82890183/147867739-5123726b-0c8a-4e42-8cbe-4bd6e34835c9.png)

![image](https://user-images.githubusercontent.com/82890183/147867743-d105fedf-f559-4136-acfd-bc585d7a9c61.png)

![image](https://user-images.githubusercontent.com/82890183/147868683-79228be4-8144-4fa6-bde4-5935c219e672.png)


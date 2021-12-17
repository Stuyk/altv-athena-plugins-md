---
layout: ../../../../layouts/Main.astro
title: 'Plant System'
description: "Plant system which lets players place weed plants and also harvest them based on Athena's Interaction Controllers."
author: 'Der Lord!'
version: '3.0.0+'
images: ['https://user-images.githubusercontent.com/82890183/131876685-13775cce-d8ee-4eb5-b95e-b3ad8520a3cf.png']
keywords: ['free', 'player', 'system']
url: 'https://github.com/Booster1212/AthenaPlantsystem'
discord: "Der Lord!#6021"
---

# Plantsystem for the Athena Framework by Der Lord!

# Features:

- Now fully translateable into your native language
- Now based on Athena's InteractionController
- Now you can still plant weed pots by Toolbar but now for fertilizing, watering and so on you'll only need to have stuff in inventory.
- Now with maximum Plant support for each player individually
- Customize scenarios & the time for each.
- Customize the updateInterval & also the states of the plants.
- Customize the range to a spot players can have
- Customizie the outcome of the plant harvesting (only tried randomized outcome there so far)
- Customize the water loss per minute .. and a lot more.

# Installation Instructions

- Grab from github (https://github.com/Booster1212/AthenaPlantsystem)
- This is a serverside plugin! It has to be added in your local athena repository here: (/src/core/plugins/Plantsystem)
- Configuration Options can be found below.
- Setup should be pretty much the same actually.
- Plants collection will be auto generated at Athena v3.0

# Default Settings (Configuration)

You can always find the default settings for this plugin here.

```ts
import * as alt from 'alt-server';
/**
 * An Array all the valid plant placing spots are going here.
 * Just press F1 Ingame with some administrative permissions, then press F8 and copy here and add "as alt.Vector3"
 * @type {alt.Vector3}
 * @memberof main
 */
export const plantSpots: alt.Vector3[] = [
  { x: -1625.6290283203125, y: 3165.891357421875, z: 29.933713912963867 } as alt.Vector3,
  // { x: 0, y: 0, z: 0 } as alt.Vector3, .. More Positions.
];

// Translate whatever you need here to your native language

export enum Translations {
  STATE = 'State:',
  WATER = 'Water:',
  TIME = 'Time:',
  FERTILIZER = 'Fertilizer:',
  HARVESTABLE = 'Harvestable:',

  NO_SEEDS_IN_INVENTORY = 'You do not have any weedseeds in your inventory',
  NO_FERTILIZER_IN_INVENTORY = 'You do not have any plant fertilizer in your inventory',
  NO_PLANTWATER_IN_INVENTORY = 'You do not have any plant water in your inventory',

  NOT_IN_RANGE_OF_SPOT = 'You are not in the range of a valid planting spot',
  NOT_ALLOWED_TO_INTERACT = 'You are not allowed to interact with this plant.',
  PLANT_SUCCESSFULLY_CREATED = 'Successfully created a plant.',

  INTERACTION_PLACESEEDS = 'Place Weedseeds',
  INTERACTION_FERTILIZE = 'Fertilize this plant',
  INTERACTION_WATER = 'Water this plant',
  INTERACTION_HARVEST = 'Harvest this plant',
  waitTillWateringFinished = "Wait until you've finished the process of watering",
}

// Settings for the main.ts - file
export const defaultSettings = {
  plantSystemEnabled: true, // is the PlantSystem enabled? default: true
  plantUpdateInterval: 1000, // updateInterval for all Plants? default: 60000 (1 Minute)
  createBlips: true, // will blips be created on the bootup of the Athena Framework? Maybe you want to make it harder to find some spots.
};

export const blipSettings = {
  sprite: 469, // Sprite of the Spot Blips
  color: 2, // Color of the Spot Blips
  scale: 1, // Scale of the Blips
  shortRange: true, // ShortRange - N/A idk have to look alt:V imagine insane emoji here. kekw.
  text: 'Weed-Plant Spot', // Text for all generated Blips?
};

// Settings for the database.ts - file
export const dbSettings = {
  logsEnabled: true, // logsystem of this plantsystem enabled? default: false
  useItems: true, // will player need items to place, fertilize, water plants? default: true - i'd suggest to keep this.

  allowEveryoneToInteract: false, // can everyone harvest plant of anyone? default: false,
  plantLimit: true, // plantLimit for players enabled? default: true
  maximumAllowedPlants: 10, // maximumAllowedPlants for a player? default: 10

  plantRequiredWaterToGrowh: 20, // Minium amount of water needed for the plant to grow. default: 20 (%)
  plantWaterLossPerMinute: 0.25, // How much Water will this plant remove per minute?
  destroyPlantsWithLowWater: false, // Will plants which result in zero water before finished be destroyed? Don't use for now. Not integrated.

  beginngStateText: 'Beginning...', // Text right after placing a pot.
  plantBeginningState: 60, // This does not matter too much tbh.

  mediumStateText: 'Growth...', // Text for the mediumState.
  plantMediumState: 30, // At what state should the plant switch into "mediumState"? default: 30 (minutes).

  endStateText: 'End of growth...', // Text for the endState.
  plantEndState: 15, // At what state should the plant switch into "endState"? default: 15 (minutes).

  harvestableText: 'Harvestable',

  seedPlacingTime: 5000, // Time it takes to place a seed
  seedPlacingScenario: 'WORLD_HUMAN_GARDENER_PLANT', // scenario for placing Plants

  wateringTime: 5000, // Time it takes to water a plant
  wateringScenario: 'WORLD_HUMAN_GARDENER_LEAF_BLOWER', // scenario for watering Plants

  fertilizeTime: 5000, // Time it takes to fertilize a plant
  fertilizeScenario: 'WORLD_HUMAN_GARDENER_LEAF_BLOWER', // scenario for fertilizing Plants

  harvestTime: 5000, // Time it takes to harvest plant
  harvestScenario: 'WORLD_HUMAN_GARDENER_PLANT', // scenario for harvesting Plants
  randomizeHarvestOutcome: true,
  minOutcome: 20,
  maxOutcome: 40,

  rangeToSpot: 20, // how far can a player be away from a plant spot and still plant a pot?
};

// DO NOT CHANGE THESE IF YOU DONT KNOW WHAT YOU ARE DOING HERE!
export const db_plantObjects = {
  small: 'bkr_prop_weed_01_small_01a',
  medium: 'bkr_prop_weed_med_01a',
  large: 'bkr_prop_weed_lrg_01a',
};
```

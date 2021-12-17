---

layout: ../../../../layouts/Main.astro
title: "Vehicle Damage Plugin"
description: "This Plugin saves the vehicle damage on wheels, windows and lights in the athena database."
author: "j0n4s"
version: "3.0.0+"
images: ["https://i.imgur.com/0Z4VZnC.png"]
keywords: ["premium", "client", "player", "system"]
url: "https://mygp.gumroad.com/l/vehicledamage"
price: "9.99"
discord: "j0n4s#8301"

---

# Vehicle Damage Plugin

This Plugin saves the vehicle damage on wheels, windows and lights in the athena database.
A player can no longer repair the vehicle by parking in and out. He is forced to drive to a workshop or call the towing service.

# Installation

1. Purchase the repo access

https://mygp.gumroad.com/l/vehicledamage

2. Copy folder plugins/gpVehicleDamage/ to your athena project under src/core/plugins/
3. Import server plugin in src/core/plugins/imports.ts:

    `import './gpVehicleDamage/index';`
    
4. One change at the athena core is necessary (currently not found a good way around it):

    Add the line 2 and 64 from the snippet below to the file src/cire/server/systems/tick.ts

    ```
    1:  import * as alt from 'alt-server';
    2:  import { GpDamage } from '../../plugins/gpVehicleDamage/gpVehicleDamage';  //Import Vehicle Damage Plugin
    ...
    63: VehicleFuncs.update(player.vehicle);
    64: GpDamage.saveDamageForVehicle(player.vehicle); //Save Damage

    ```

# Deinstallation

1. Remove the folder gpVehicleDamage under src/core/plugins/
2. Remove line 2 and line 64 from athena core file src/cire/server/systems/tick.ts

# Notes

1. The athena vehicle database will be extended by a property named "damage", which includes several damage informations.
2. Some damage data can be potentially crash the game after a GTA Update. Therefore these data will automatically erased and updated by the plugin. However, this leads to the fact that not all damages can be restored after an update.
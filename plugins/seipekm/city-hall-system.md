---

layout: ../../../../layouts/Main.astro
title: "City Hall System Premium Plugin"
description: "Buy license and change car plate text"
author: "SeipekM"
version: "2.0.3"
images: ["https://i.imgur.com/MR1PvP5.png"]
keywords: ["premium", "server", "player", "system"]
url: "https://shoppy.gg/product/dSDfRco"
price: "25.00"
discord: "seipekm#0300"

---

# City Hall System Premium Plugin

## Features
- Purchase of identity card
- Purchase of provisional driver’s license
- Change of car license plate

# Installation Instructions

- Drop the plugins files into plugins.
- Drop the client-plugins files into client-plugins.
- Drop the webview files into webview.

### imports.ts (Serverside)
```ts
'./cityhall/index',
'./cityhall/items',
```

### imports.ts (Clientside)
```ts
import './cityhall/index';
```

### items.ts (Serverside)
```ts
import { ITEM_TYPE } from '../../shared/enums/itemTypes';
import { Item } from '../../shared/interfaces/Item';
import { appendToItemRegistry } from '../../shared/items/itemRegistry';
import { deepCloneObject } from '../../shared/utility/deepCopy';

// >> ID Card
const commonIdcardItem: Item = {
    name: 'Personalausweis',
    description: 'Dein Personalausweis',
    icon: 'idcard',
    slot: 0,
    quantity: 1,
    behavior:
        ITEM_TYPE.SKIP_CONSUMABLE |
        ITEM_TYPE.CONSUMABLE |
        ITEM_TYPE.CAN_TRADE |
        ITEM_TYPE.CAN_DROP,
    data: {
        name: 'Max_Mustermann',
        birthDay: '1992-02-18',
        gender: "M",
        height: 169

    }
}
const registerCommonIdcard: Item = deepCloneObject<Item>(commonIdcardItem);
appendToItemRegistry(registerCommonIdcard);


// >> Temp Licence Card
const commonTemporaryDrivingLicenseItem: Item = {
    name: 'Vorläufiger-Führerschein',
    description: 'Dein vorläufiger Führerschein',
    icon: 'licencecard',
    slot: 0,
    quantity: 1,
    behavior:
        ITEM_TYPE.SKIP_CONSUMABLE |
        ITEM_TYPE.CONSUMABLE |
        ITEM_TYPE.CAN_TRADE |
        ITEM_TYPE.CAN_DROP,
    data: {
        name: 'Max_Mustermann',
        birthDay: '1992-02-18',
        gender: "M",
        height: 169,
        expirationDate: '2021-12-01'
    }
}
const registerTemporaryDrivingLicense: Item = deepCloneObject<Item>(commonTemporaryDrivingLicenseItem);
appendToItemRegistry(registerTemporaryDrivingLicense);
```
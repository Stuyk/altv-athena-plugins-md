---
layout: ../../../../layouts/Main.astro
title: 'Door Lock System'
description: 'Door system which enables you to lock/unlock door based on a player or faction.'
author: 'Der Lord!'
version: '3.0.0+'
images:
['https://user-images.githubusercontent.com/82890183/147381214-0e993fe0-1d9c-48dc-8751-65a46696c4d1.png', 'https://user-images.githubusercontent.com/82890183/147381524-93c23c14-1c1b-4ba7-8b8b-067a18921167.png', 'https://user-images.githubusercontent.com/82890183/147381220-b48ebfc4-b6a7-4759-b995-382c99c7c59b.png', 'https://user-images.githubusercontent.com/82890183/147381230-4340e69b-ce00-48c8-92ea-fec27845489d.png', 'https://user-images.githubusercontent.com/82890183/147381159-b57320c1-1f3a-495e-8055-bd5b3e8cf860.png']
keywords: ['free', 'player', 'system', 'streamer', 'client']
url: 'https://github.com/Booster1212/AthenaDoorlock'
discord: 'Der Lord!#6021'
---

# Athena Framework - DoorController V2

![image](https://user-images.githubusercontent.com/82890183/147381214-0e993fe0-1d9c-48dc-8751-65a46696c4d1.png)

![image](https://user-images.githubusercontent.com/82890183/147381524-93c23c14-1c1b-4ba7-8b8b-067a18921167.png)

![image](https://user-images.githubusercontent.com/82890183/147381220-b48ebfc4-b6a7-4759-b995-382c99c7c59b.png)

![image](https://user-images.githubusercontent.com/82890183/147381230-4340e69b-ce00-48c8-92ea-fec27845489d.png)

![image](https://user-images.githubusercontent.com/82890183/147381159-b57320c1-1f3a-495e-8055-bd5b3e8cf860.png)

## READ First!

- Do not Reupload this Plugin or claim it is yours.
- This is the development branch, so there will be still a few bugs left which will be fixed in the next few days.
- Permission to use this plugin is only granted to people which have a legal license of the Athena Framework by Stuyk!

## Features

- Add / Remove Doors In-Game by Pressing "."-Key (DOT)
- Full Database Integration (Collection will be auto-created)
- Full integrated Key System (Keys with names)
- Automatically hashes every submitted door prop name

## SETUP

- Drop the client-plugins files into client-plugins.
- Drop the plugins files into plugins.

## CHANGELOG

- Added Keys, removed faction option from input menu.
- Fixed lot of bugs
- doors are waiting to be closed before they are locking now
- Textlabels are now in center of the door. Boolean Status is gone also.

## HOW TO CREATE KEY

- Keys have actually still be created inside of src/keys.ts - Hopefully we will have database based items soon. <3
- Just copy the example key and make changes to your likings for example name, quantity and so on.
- Be careful that the key must have the exact equal name which is stored inside of the doors-collection.

```typescript
// *** Door Keys can be created here. *** //

import { ITEM_TYPE } from '../../../shared/enums/itemTypes';
import { Item } from '../../../shared/interfaces/item';
import { appendToItemRegistry } from '../../../shared/items/itemRegistry';
import { deepCloneObject } from '../../../shared/utility/deepCopy';

// Just some Example Key which can be used if database keyname equals "LSPD Master Key"
const someKey: Item = {
name: `LSPD Master Key`,
uuid: `LSPD-MasterKey`,
description: `Probably used to unlock/lock all doors of the Mission Row Police Department.`,
icon: 'crate',
quantity: 1,
behavior: ITEM_TYPE.CAN_DROP | ITEM_TYPE.CAN_TRADE | ITEM_TYPE.CONSUMABLE,
data: {},
rarity: 3,
};
const registerLSPDKey: Item = deepCloneObject<Item>(someKey);
appendToItemRegistry(registerLSPDKey);
```

imports.ts (Clientside)

```typescript
import './AthenaDoorlock/index';
import './AthenaDoorlock/src/wheelmenu';
```

imports.ts (Serverside)

```typescript
import './AthenaDoorlock/index';
import './AthenaDoorlock/src/keys';
```

### Want to support some open source activity? - Go ahead and use the Sponsor Button. ;)

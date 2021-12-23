---

layout: ../../../../layouts/Main.astro
title: "Hotel Plugin"
description: "The Hotel Plugin adds a hotel function to Athena's Interior System."
author: "j0n4s"
version: "3.0.0+"
images: ["https://i.imgur.com/NOBWMXT.png"]
keywords: ["premium", "client", "player", "system"]
url: "https://mygp.gumroad.com/l/hotelplugin"
price: "14.99"

---

# Hotel Plugin Premium

The Hotel Plugin adds a hotel function to Athena's Interior System. Administrators can create hotels with any number of apartments.
The hotels can be offered for sale and the apartments can be rented.

Feature overview:

- Configrure rent price per appartment/unit
- Configure Hotel contact informations
- Payment System
- Rent a appartment
- Moveout from appartment
- Storage System
- Reception in Hotel Lobby

Included but in progress:

- Bell
- Moveout

# Installation

1. Purchase the repo access
2. Copy Folder client-plugins/hotels to your athena project under src/core/client-plugins/
3. Import client plugin in src/core/client-plugins/imports.ts:

    ```import './hotels/index';```

4. Copy Folder plugins/hotels to your athena project under src/core/plugins/
5. Import server plugin in src/core/plugins/imports.ts:

    ```import './hotels/index';```

6. Copy folder src-webviews/pages/ to your athena project under src-webviews/src/pages
7. Import VUE Page in src-webviews/pages/components.ts

    ```import Hotel from './hotels/Hotel.vue'```

8. Add to component list in src-webviews/pages/components.ts

    ```Hotel: shallowRef(Hotel),```

9. (optional) Install Interior plugin

https://github.com/jonasesser/altv-athena-plugin-interior

# Example Hotel:

- NAME OF PROPERTY: Hilton
- PRICE OF HOTEL: 150000
- NUMBER OF UNITS: 50
- DEFAULT PRICE FOR UNIT PER DAY: 40
- POSITION OF RECEPTION: {"x":-141.5361, "y":-620.9186, "z":168.8204}
- OPTIONAL IPL FOR RECEPTION: ex_dt1_02_office_01c
- OPTIONAL PED POSITION FOR RECEPTION: {"x":-139.13621520996094,"y":-633.8536987304688,"z":168.82054138183594}
- OPTIONAL PED ROTATION FOR RECEPTION: {"x":0,"y":0,"z":-0.05012647807598114}
- POSTITION OF DEFAULT INTERIOR: {"x":152.2605,"y":-1004.471,"z":-98.99999}
- OPTIONAL IPL FOR INTERIOR: null
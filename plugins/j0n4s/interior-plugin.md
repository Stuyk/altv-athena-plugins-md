---

layout: ../../../../layouts/Main.astro
title: "Interior Plugin"
description: "This Plugin helps you to find an interior including position and ipl informations"
author: "j0n4s"
version: "3.0.0+"
images: ["https://i.imgur.com/K4QjdzE.png"]
keywords: ["free", "client", "server", "data"]
url: "https://github.com/jonasesser/altv-athena-plugin-interior"
discord: "j0n4s#8301"

---

# Interior Plugin

This Plugin helps you to find an interior including position and ipl informations.
You can use it ingame as admin or for development as interior database.

# Installation Instructions

1. Grab from github
2. Copy Folder plugins/gpInteriors/ to your athena project under src/core/plugins/
3. Import server plugin in src/core/plugins/imports.ts:

    `import './gpInteriors/index';`

# Usage

1. In-Game as administrator

    `/gotointerior [name] - Goto Interior (try /gotointerior Movie Theatre)`

2. In-Code as developer

```ts
import { GpInteriors, GpInteriors_Category } from '../gpInteriors/gpInteriors';

// Get Interiors    
let interior = GpInteriors.getInterior("Movie Theatre");
let allInteriors = GpInteriors.getInteriors();
let interiorByCat = GpInteriors.getInteriorsByCategory(GpInteriors_Category.Office);

// Get Interior names only
let allInteriorNames = GpInteriors.getInteriorNames();
let interiorNamesByCat = GpInteriors.getInteriorNamesByCategory(GpInteriors_Category.Office);

// Get Interior position by name
let position = GpInteriors.getInteriorPosition(interior.Name);  //returns alt.Vector3
let ipl = GpInteriors.getInteriorIPL(interior.Name); //returns IPL name to be load or null
```

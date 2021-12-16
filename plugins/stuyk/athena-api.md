---

layout: ../../../../layouts/Main.astro
title: "Athena API"
description: "A REST service for Athena internal gamemode. Can be used to get various player data."
author: "Stuyk"
version: "3.0.0+"
images: ["https://i.imgur.com/ScnIFEt.png"]
keywords: ["free", "server", "utility", "data"]
url: "https://github.com/Stuyk/altv-athena-api"

---

# Athena API

This feeds data from the Server to anyone who would like to access the endpoint. It's a relatively simple plugin that is more data centric.

It is highly recommended that if you plan on using this plugin that you limit who can access the port `9090` by IP.

**You as the end-user are responsible for securing data.**

# GET

`:variable` means you provide the data to get the result. Everything is case sensitive.

_\* Some sensitive data removed from response._ 

## Account Specific

| Request                            | Description | Response     |
| ---------------------------------- | ----------- | ------------ |
| `localhost:9090/accounts/:discord` | Get Account | `<Account>`* |

## Player Specific

| Request                                   | Description                  | Response            |
| ----------------------------------------- | ---------------------------- | ------------------- |
| `localhost:9090/players/all`              | Get Players                  | `Array<alt.Player>` |
| `localhost:9090/players/name/:name`       | Get Character by Name        | `Character`         |
| `localhost:9090/players/discord/:discord` | Get Characters by Discord ID | `Array<Character>`  |

## Vehicle Specific

| Request                                 | Description            | Response             |
| --------------------------------------- | ---------------------- | -------------------- |
| `localhost:9090/vehicles/all`           | Get Vehicles           | `Array<alt.Vehicle>` |
| `localhost:9090/vehicles/character/:id` | Get Character Vehicles | `Array<IVehicle>`    |

All `GET` Requests Return a JSON Response Object

```ts
{
    "version": number,
    "data": Array<SomeObjectType>
}
```

# Installation

Download that latest version of this archive.

Drag / drop `src` in the root directory of `Athena`.

Add the following to `src/core/server/plugins/imports.ts`

```ts
import './altv-athena-api/index'
```

Run the following in a Terminal:

```
npm i fastify
```

# Verification of Installation

![](https://i.imgur.com/Tqa77vQ.png)

Open Browser and Visit

```
localhost:9090
```

# Uninstallation

Delete the folder `src/core/server/plugins/altv-athena-api`

Run the following in a Terminal:

```
npm uninstall fastify
```
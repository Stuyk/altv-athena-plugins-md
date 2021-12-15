# Athena Plugins MD

Contribute your plugins by making a pull request to this repository.

Inside of the folder `plugins` you should do the following:

1. Create a folder with your name. The name must be hyphenated and not contain spaces. Please make sure that it is entirely lowercase as well. The continuous integration will run checks against your PR when you submit your changes.

2. Create an `.md` file with all the front matter listed below and ensure you update all front matter so that it fits your plugin.

# Front Matter

When you are creating the markdown file you will need to use one of the two templates below depending on how you are distributing the resource. Keep in mind that you are entirely responsible for your own customers. Providing or posting premium plugins in this repository that do not work will get you and your license key de-activated from Athena. 

Act responsibly.

## Free

```md
---

layout: ../../../layouts/Main.astro
title: "Example Plugin"
description: "Really cool plant system that does plant things."
author: "Stuyk"
version: "3.0.0+"
images: ["https://i.imgur.com/BZOzE6L.png", "https://i.imgur.com/Vqqe582.png", "https://i.imgur.com/sqKwAai.png"]
keywords: ["free", "client", "player", "system"]
url: "https://github.com/"

---

# Example Free Plugin

Wow, look at my cool plugin. I can talk about all these amazing features it has.

# Installation Instructions

1. Grab from github
2. Put folder somewhere.

```

## Premium

Ensure that your front matter is 

```md
---

layout: ../../../layouts/Main.astro
title: "Example Premium Plugin"
description: "Really cool plant system that does plant things."
author: "Stuyk"
version: "3.0.0+"
images: ["https://i.imgur.com/BZOzE6L.png", "https://i.imgur.com/Vqqe582.png", "https://i.imgur.com/sqKwAai.png"]
keywords: ["premium", "client", "player", "system"]
url: "https://whatever.provider.com"
price: "5.99"

---

# Example Premium Plugin

Wow, look at my cool plugin. I can talk about all these amazing features it has.

# Installation Instructions

1. Purchase the repo access.
2. Download it.
3. Do something else.

```

# Categories

This is a list of the currently valid category names. Ensure they are lower case or the PR bot will make you change it. Use the category names on the right-hand side of the enum.

```ts
export enum CATEGORY {
    CLIENT = 'client',
    DATA = 'data',
    FREE = 'free',
    INTERFACE = 'interface',
    ITEM = 'item',
    PLAYER = 'player',
    PREMIUM = 'premium',
    SERVER = 'server',
    STREAMER = 'streamer',
    SYSTEM = 'system',
    TOOL = 'tool',
    UTILITY = 'utility',
    VEHICLE = 'vehicle',
    VOICE = 'voice',
}
```
---

layout: ../../../../layouts/Main.astro
title: "Moderator Commands"
description: "Adds the much needed in-game commands for moderators and administrators."
author: "Stuyk"
version: "3.0.0+"
images: ["https://i.imgur.com/ScnIFEt.png"]
keywords: ["free", "server", "system", "utility"]
url: "https://github.com/Stuyk/athena-moderator-commands"
discord: "stuyk#0001"

---

# Moderator Commands

Adds the much needed in-game commands for moderators and administrators.

-   /apm - Admin Private Message (Send Directly to another Player)
-   /kick - Kick a Player
-   /ban - Ban a Player
-   /unban - Unban a Player
-   /info - Get Player Account Info
-   /tpto - Teleport to a Player
-   /tphere - Teleport a Player Here
-   /freeze - Freeze a Player
-   /unfreeze - Unfreeze a Player

# Installation

### Download

[Download the Archive](https://github.com/Stuyk/athena-moderator-commands/archive/refs/heads/main.zip)

[Source Code](https://github.com/Stuyk/athena-moderator-commands)

### Move Folder

Extract the top level folder `athena-moderator-commands-main` into `src/core/plugins`.

Your final path should be `src/core/plugins/athena-moderator-commands-main`.

See _usage_ to see how to import and use this plugin.

### Verify Installation

Navigate to `src/core/plugins/athena-moderator-commands-main/index` and open the file.

Double check that the top-level imports are not underlined in **red**. If they are **red** then you installed this plugin wrong.

### Add to Imports

After checking the placement of the files.

Modify `src/core/plugins/imports.ts` and append the following in your `filePaths` variable inside `imports.ts`.

What to Append:

```ts
import './athena-moderator-commands-main/index';
```

# Usage

### Admin Private Message

```ts
/apm [in-game id] [?...message]
```

### Kick

```ts
/kick [in-game id] [?...reason]
```

### Ban

```ts
/ban [in-game id] [?...reason]'
```

### Unban

```ts
/unban [discord id] [?...reason]
```

### Info

```ts
/info [in-game id]
```

### Teleport to Player

```ts
/tpto [in-game id]
```

### Teleport Player to You

```ts
/tphere [in-game id]
```

### Freeze Target

Also kicks the player out of their vehicle if they are in one.

```ts
/freeze [in-game id]
```

### Unfreeze Target

```ts
/unfreeze [in-game id]
```

# Uninstalling

Delete the folder in `src/core/plugins/athena-moderator-commands-main`.

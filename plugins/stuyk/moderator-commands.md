---

layout: ../../../layouts/Main.astro
title: "Moderator Commands"
description: "Adds the much needed in-game commands for moderators and administrators."
author: "Stuyk"
version: "3.0.0+"
images: ["https://i.imgur.com/ScnIFEt.png"]
keywords: ["free", "server", "system", "utility"]
url: "https://github.com/Stuyk/athena-moderator-commands"

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

```typescript
import './athena-moderator-commands-main/index';
```

# Usage

### Admin Private Message

```typescript
/apm [in-game id] [?...message]
```

### Kick

```typescript
/kick [in-game id] [?...reason]
```

### Ban

```typescript
/ban [in-game id] [?...reason]'
```

### Unban

```typescript
/unban [discord id] [?...reason]
```

### Info

```typescript
/info [in-game id]
```

### Teleport to Player

```typescript
/tpto [in-game id]
```

### Teleport Player to You

```typescript
/tphere [in-game id]
```

### Freeze Target

Also kicks the player out of their vehicle if they are in one.

```typescript
/freeze [in-game id]
```

### Unfreeze Target

```typescript
/unfreeze [in-game id]
```

# Uninstalling

Delete the folder in `src/core/plugins/athena-moderator-commands-main`.

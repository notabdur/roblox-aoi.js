---

# Roblox NPM Package

![npm version](https://img.shields.io/npm/v/roblox-aoi.js)
![license](https://img.shields.io/npm/l/roblox-aoi.js)
![npm downloads](https://img.shields.io/npm/dm/roblox-aoi.js)

Welcome to the documentation for the "roblox-aoi.js." This package provides a set of functions to interact with the Roblox API and perform various operations related to groups, games, users, and assets.

## Installation

To use the Roblox NPM package in your Node.js project, you can install it via npm:

```bash
npm install roblox-aoi.js
```

## Initialization

Before using the package, make sure to require and initialize it with your Roblox API credentials:

```javascript
const roblox = require('roblox-aoi.js');

// Replace the 'apiKey' and 'apiSecret' with your Roblox API credentials
roblox.init({
  apiKey: 'YOUR_ROBLOX_API_KEY',
  apiSecret: 'YOUR_ROBLOX_API_SECRET',
});
```

Replace `'YOUR_ROBLOX_API_KEY'` and `'YOUR_ROBLOX_API_SECRET'` with your Roblox API key and secret, which you can obtain from your Roblox developer account.

## Functions

### 1. Greet User

**Description**: Returns a greeting message for the specified username.

**Usage**:
```javascript
const greeting = await roblox.greetUser(username);
console.log(greeting);
```

### 2. Get User Information

**Description**: Fetches user information from Roblox API based on the provided username.

**Usage**:
```javascript
const userInfo = await roblox.getUserInfo(username);
console.log(userInfo);
```

### 3. Get User Friends

**Description**: Fetches a list of user friends from the Roblox API based on the provided user ID.

**Usage**:
```javascript
const userFriends = await roblox.getUserFriends(userId);
console.log(userFriends);
```

### 4. Get Group Information

**Description**: Fetches group information from the Roblox API based on the provided group ID.

**Usage**:
```javascript
const groupInfo = await roblox.getGroupInfo(groupId);
console.log(groupInfo);
```

### 5. Promote User

**Description**: Promotes a user in a group on Roblox.

**Usage**:
```javascript
await roblox.promoteUser(groupId, targetUserId);
console.log('User promoted successfully in the group.');
```

### 6. Pay Robux

**Description**: Pays Robux to a user from the authenticated user's balance.

**Usage**:
```javascript
await roblox.payRobux(targetUserId, amount);
console.log(`${amount} robux paid successfully to user with ID ${targetUserId}.`);
```

### 7. Pay From Group

**Description**: Pays Robux from a group to a user.

**Usage**:
```javascript
await roblox.payFromGroup(groupId, targetUserId, amount);
console.log(`Successfully paid ${amount} robux to user with ID ${targetUserId} from the group.`);
```

### 8. Get Game Information

**Description**: Fetches information about a specific game from the Roblox API based on the provided game ID.

**Usage**:
```javascript
const gameInfo = await roblox.getGameInfo(gameId);
console.log(gameInfo);
```

### 9. Get Game Badges

**Description**: Fetches a list of badges available in a specific game from the Roblox API based on the provided game ID.

**Usage**:
```javascript
const gameBadges = await roblox.getGameBadges(gameId);
console.log(gameBadges);
```

### 10. Get Asset Information

**Description**: Fetches information about a specific asset from the Roblox API based on the provided asset ID.

**Usage**:
```javascript
const assetInfo = await roblox.getAssetInfo(assetId);
console.log(assetInfo);
```

### 11. Get All Assets

**Description**: Fetches a list of all assets available on Roblox.

**Usage**:
```javascript
const allAssets = await roblox.getAllAssets();
console.log(allAssets);
```

## Example Bot Usage

Here's an example of how you can integrate the Roblox npm package into your Discord.js bot:

```javascript
// Require the Discord.js library and your Roblox npm package
const Discord = require('discord.js');
const roblox = require('roblox-aoi.js');

// Initialize the Roblox npm package with your API credentials
roblox.init({
  apiKey: 'YOUR_ROBLOX_API_KEY',
  apiSecret: 'YOUR_ROBLOX_API_SECRET',
});

// Your Discord bot setup and login code
const client = new Discord.Client();
const token = 'YOUR_DISCORD_BOT_TOKEN';

client.login(token);

// Example commands in your Discord bot
client.on('message', async (message) => {
  if (!message.content.startsWith('!') || message.author.bot) return;

  const args = message.content.slice(1).trim().split(/ +/);
  const commandName = args.shift().toLowerCase();

  if (commandName === 'userinfo') {
    // ... Code for fetching and displaying user info using roblox.getUserInfo() ...

  } else if (commandName === 'pay') {
    // ... Code for paying robux from group to user using roblox.payFromGroup() ...

  } else if (commandName === 'gameinfo') {
    // ... Code for fetching and displaying game info using roblox.getGameInfo() ...

  } else if (commandName === 'assetinfo') {
    // ... Code for fetching and displaying asset info using roblox.getAssetInfo() ...

  }

  // Add more commands using other functions...
});
```

---

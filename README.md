# Roblox NPM Package

![npm version](https://img.shields.io/npm/v/roblox-aoi.js)
![license](https://img.shields.io/npm/l/roblox-aoi.js)
![npm downloads](https://img.shields.io/npm/dm/roblox-aoi.js)

Welcome to the documentation for the "roblox-aoi.js." This package provides a set of functions to interact with the Roblox API and perform various operations related to groups, games, users, and assets.

## Installation

```bash
npm install roblox-aoi.js
```

## Usage

To use the functions provided by this package, require it in your Node.js project:

```javascript
const robloxPackage = require('roblox-aoi.js');
```

## Functions

### `greetUser(username)`

A simple function to greet the user with their username.

**Parameters:**
- `username` (string): The username of the user.

**Returns:**
- (string): A greeting message.

### `getUserInfo(username)`

Get information about a user using their username.

**Parameters:**
- `username` (string): The username of the user.

**Returns:**
- (object): An object containing user information.

### `getUserFriends(userId)`

Get a user's friends.

**Parameters:**
- `userId` (number): The user ID of the user.

**Returns:**
- (array): An array of user friends.

### `getGroupInfo(groupId)`

Get information about a group using its ID.

**Parameters:**
- `groupId` (number): The ID of the group.

**Returns:**
- (object): An object containing group information.

### `promoteUser(groupId, targetUserId)`

Promote a user in a group.

**Parameters:**
- `groupId` (number): The ID of the group.
- `targetUserId` (number): The user ID of the user to be promoted.

**Returns:**
- (object): An object confirming the promotion.

### `demoteUser(groupId, targetUserId)`

Demote a user in a group.

**Parameters:**
- `groupId` (number): The ID of the group.
- `targetUserId` (number): The user ID of the user to be demoted.

**Returns:**
- (object): An object confirming the demotion.

### `exileUser(groupId, targetUserId)`

Exile a user from a group.

**Parameters:**
- `groupId` (number): The ID of the group.
- `targetUserId` (number): The user ID of the user to be exiled.

**Returns:**
- (object): An object confirming the exile.

### `payRobux(targetUserId, amount)`

Pay robux to a user from the authenticated user's balance.

**Parameters:**
- `targetUserId` (number): The user ID of the user to receive robux.
- `amount` (number): The amount of robux to be paid.

**Returns:**
- (object): An object confirming the payment.

### `getGameInfo(gameId)`

Get game information by its ID.

**Parameters:**
- `gameId` (number): The ID of the game.

**Returns:**
- (object): An object containing game information.

### `getGameBadgesInfo(gameId)`

Get game badges information by game ID.

**Parameters:**
- `gameId` (number): The ID of the game.

**Returns:**
- (array): An array of game badges information.

### `getUserInfoById(userId)`

Get user information by their user ID.

**Parameters:**
- `userId` (number): The ID of the user.

**Returns:**
- (object): An object containing user information.

### `getUserBadges(userId)`

Get user badges information by their user ID.

**Parameters:**
- `userId` (number): The ID of the user.

**Returns:**
- (array): An array of user badges information.

### `getUserAssets(userId)`

Get user assets by their user ID.

**Parameters:**
- `userId` (number): The ID of the user.

**Returns:**
- (array): An array of user assets information.

### `getAllAssetsInfo(assetIds)`

Get all assets information by asset IDs.

**Parameters:**
- `assetIds` (array): An array of asset IDs.

**Returns:**
- (array): An array of assets information.

## Examples

```javascript
const { greetUser, getUserInfo, promoteUser, payRobux } = require('roblox-aoi.js');

const username = 'RobloxUser123';
console.log(greetUser(username));

(async () => {
  try {
    const userInfo = await getUserInfo(username);
    console.log(userInfo);

    const groupId = 123456; // Replace with your group ID
    const targetUserId = 7890123; // Replace with your target user ID

    await promoteUser(groupId, targetUserId);
    console.log(`${targetUserId} promoted successfully.`);

    const robuxAmount = 100;
    await payRobux(targetUserId, robuxAmount);
    console.log(`${robuxAmount} robux paid successfully to user with ID ${targetUserId}.`);
  } catch (error) {
    console.error(error.message);
  }
})();
```

## License

MIT License. See the [LICENSE](LICENSE) file for more details.

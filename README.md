# roblox-aoi.js

npm install
```
npm i roblox-aoi.js
```

## Usage
```
const {
  greetUser,
  getUserInfo,
  getUserFriends,
  getGroupInfo,
  promoteUser,
  demoteUser,
  exileUser,
  payRobux,
  getGameInfo,
  getGameBadgesInfo,
  getUserInfoById,
  getUserBadges,
  getUserAssets,
  getAllAssetsInfo,
} = require('roblox-aoi.js');

// Example usage
const username = 'Robloxusername';
const targetUsername = 'targetusername';
const groupId = 123456; // Replace with your group ID
const gameId = 789012; // Replace with your game ID
const targetUserId = USER_ID; // Replace with your target user ID
const assetIds = [123, 456, 789]; // Replace with the asset IDs you want to fetch information for

(async () => {
  try {
    // Greet the user
    console.log(greetUser(username));

    // Get user info
    const userInfo = await getUserInfo(username);
    console.log(userInfo);

    // Get user friends
    const userFriends = await getUserFriends(userInfo.Id);
    console.log(userFriends);

    // Get group info
    const groupInfo = await getGroupInfo(groupId);
    console.log(groupInfo);

    // Promote user in the group
    await promoteUser(groupId, targetUserId);
    console.log(`${targetUserId} promoted successfully.`);

    // Demote user in the group
    await demoteUser(groupId, targetUserId);
    console.log(`${targetUserId} demoted successfully.`);

    // Exile user from the group
    await exileUser(groupId, targetUserId);
    console.log(`${targetUserId} exiled successfully.`);

    // Pay robux to a user
    const robuxAmount = 100;
    await payRobux(targetUserId, robuxAmount);
    console.log(`${robuxAmount} robux paid successfully to user with ID ${targetUserId}.`);

    // Get game information
    const gameInfo = await getGameInfo(gameId);
    console.log(gameInfo);

    // Get game badges information
    const gameBadgesInfo = await getGameBadgesInfo(gameId);
    console.log(gameBadgesInfo);

    // Get user information by ID
    const userInfoById = await getUserInfoById(targetUserId);
    console.log(userInfoById);

    // Get user badges information
    const userBadges = await getUserBadges(targetUserId);
    console.log(userBadges);

    // Get user assets information
    const userAssets = await getUserAssets(targetUserId);
    console.log(userAssets);

    // Get all assets information
    const allAssetsInfo = await getAllAssetsInfo(assetIds);
    console.log(allAssetsInfo);
  } catch (error) {
    console.error(error.message);
  }
})();


```

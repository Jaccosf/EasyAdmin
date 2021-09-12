# Plugin API

Since 5.9 EasyAdmin Supports creating custom Plugins which allow Developers to create new Items in the Menu and add custom Functions, this is a Quick-Start Guide for Developers.


## Foreword

EasyAdmin is based on [Frazzle's NativeUILua](https://github.com/FrazzIe/NativeUILua), so when creating Menus, make sure that you follow it's API Properly.

Menu Items are generated when the Button for it is pressed, do note that the menu can and WILL be generated multiple times, so do not store any variables which may affect the menu generation on later iterations.


## Boilerplate Script

You can find a few Example Scripts in the "plugins" folder inside EasyAdmin, here some of the functionality is explained in more Detail.

## Recieving Events

These are the Events that your Script can recieve and use, but should never trigger.


|                 Event                  | Arguments |                                                                                                Function                                                                                                |
|----------------------------------------|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EasyAdmin:BuildPlayerOptions           | playerId  | This event is meant to be used if new Menu options are meant to be created inside a player's submenu, the playerId is passed, you can use the "thisPlayer" variable to access the Menu.                         |
| EasyAdmin:BuildCachedOptions           | cachedId  | This event is for adding Menu Options to cached players, do note that these are not real players and the Id cannot be interacted with with Natives. Menu is "thisPlayer".                              |
| EasyAdmin:BuildServerManagementOptions | none      | This event is meant to be used for adding menu options to the "Server Management" Submenu, the menu is called "servermanagement"                                                                       |
| EasyAdmin:BuildSettingsOptions         | none      | This event is meant to be used for adding menu options to the "Settings" Submenu, the menu is called "settingsMenu"                                                                                    |
| EasyAdmin:MenuRemoved                  | none      | This event is used when the EasyAdmin Menu is closed and/or Removed, this happens if the menu is closed and not active. This can trigger multiple times in a row so be careful what code you put here. |

## Sending Events

EasyAdmin has a powerful API with which you can already do lots of things, here are a few Server Events which you can Trigger:


|              Event              |             Arguments              |      Returns       |                                                                            Function                                                                                                                                    |
|---------------------------------|------------------------------------|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EasyAdmin:amiadmin              | none                               | none               | Re-send Permissions list on a Player, this also gets done sometimes if a player opens the menu.                                                                                                                        |
| EasyAdmin:GetInfinityPlayerList | none                               | Table(PlayerCache) | This Event sends a Clientside event with the same name back, containing a Table of all Players                                                                                                                         |
| EasyAdmin:requestCachedPlayers  | none                               | Table(PlayerCache) | This Event sends an Event called `EasyAdmin:fillCachedPlayers` back which is a table of all cached Players, this includes active and not active players.                                                               |
| EasyAdmin:kickPlayer            | playerId,reason                    | none               | This Event Kicks a Player if the User has permissions to do so and sends a Webhook Message with it.                                                                                                                    |
| EasyAdmin:addBan                | playerId,reason,expireTime,offline | none               | This Event Bans a player (both online and cached) using EasyAdmin's Ban Feature, "Expires" has to be a timeframe(for ex. 1 week) in Unix Time. If the player is not on the Server make sure to pass "offline" as true. |
| EasyAdmin:requestBanlist        | none                               | table(banlist)     | This Event sends an event called `EasyAdmin:fillBanlist` back with a table of all Bans.                                                                                                                                |
| EasyAdmin:SlapPlayer            | playerId,slapAmount                | none               | This Event Slaps a player, taking away HP according to "SlapAmount".                                                                                                                                                   |
| EasyAdmin:TakeScreenshot        | playerId                           | httpResponse       | This Event Takes a screenshot of the player's screen and once successful, triggers `EasyAdmin:TookScreenshot` with the HTTP Response, screenshot-basic is required.                                                    |
| EasyAdmin:unbanPlayer           | banId                              | none               | Unbans a Player according to their Ban Id                                                                                                                                                                              |
| EasyAdmin:mutePlayer   		  | playerId                           | none               | Toggles a Mute on a Player.                                                                                                                                                                                            |



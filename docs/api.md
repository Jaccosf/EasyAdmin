# Lua API

EasyAdmin offers an API to interact with certain EasyAdmin Features from code, below are some Events/Functions which can be used:


# Triggerable Events
### EasyAdmin:kickPlayer(playerId, reason)

Kicks a Player with the EasyAdmin Template + Webhook Notification

```lua
TriggerEvent("EasyAdmin:kickPlayer", 1, "being rude")
```
***
### EasyAdmin:addBan(playerId,reason,expires)

Bans a player using the EasyAdmin System + Webhook, expires is in seconds

Arguments:

playerId - the player to ban

reason (optional) - a reason, as a string

expires (optional) - a timeframe in seconds for how long the ban should be




```lua
TriggerEvent("EasyAdmin:addBan", 1, "being rude", 604800)
```
***
### EasyAdmin:TakeScreenshot(playerId)

Will take a screenshot of the player's game and upload it to the configured image uploader, then post a notification to the Webhook.

***
### EasyAdmin:mutePlayer(playerId)

Toggles whether a player is muted.


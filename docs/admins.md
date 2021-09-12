# Using ACE

ACE uses your server config file or commands to add / remove admins and set permissions, here is an example:

```
add_principal identifier.ip:127.0.0.1 group.admin
add_principal identifier.license:aaaabbbbcccddeeeeeeffff group.moderator
add_principal identifier.steam:1100001021asfd5 group.moderator
```
Layout of this command is

```
add_principal identifier.IDENTIFIER group.GROUP_NAME
```

Identifier in this case can be anything FiveM recognizes, e.g. steam, license, discord and whatnot, there are no restrictions on which identifier can be used.



Although it is not confirmed, We recommend only using lowercase letters in the identifiers, as uppercase letters may not work correctly.

# Steam WebApiKey (Only read this if you're using Steam)

You'll need to take one extra step and set up a webApiKey in your server config.

**Note: you will need a full steam account to be able to do this, it'll require purchasing a game of £5+ to change your account from limited to full access**

Head over to https://steamcommunity.com/dev/apikey and log in to your account.

Then you'll want to enter your server IP address in the `Domain Name` field **without** the port. Next agree to the Terms of Use and click Register.

Open your server.cfg and scroll down till you see `steam_WebApiKey` then copy the key you just generated and paste it between the speech marks.

E.G
```
steam_WebApiKey "ECBB82291CEF372F0CBC66DD11D66DA5"
```
#### If you're hosting your server on your local machine (your PC) then you can enter `localhost` into the Domain Name field.


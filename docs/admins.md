# Adding Admins

ACEs use your server config file or commands to add / remove admins and set permissions, here is an example:

```
add_principal identifier.ip:127.0.0.1 group.admin
add_principal identifier.license:aaaabbbbcccddeeeeeeffff group.moderator
add_principal identifier.steam:1100001021asfd5 group.moderator
```
Layout of this command is

```
add_principal identifier.IDENTIFIER group.GROUP_NAME
```

Identifier in this case can be anything FiveM recognizes, for exmaple, steam, license, discord and so on, there are no restrictions on which identifier can be used.



Although it is not confirmed, We recommend only using lowercase letters in the identifiers, as uppercase letters may not work correctly.

# Steam WebApiKey

When using Steam as an Identifier, a Steam WebAPIKey is Required.

**Note: you will need a full steam account to be able to do this, it'll require purchasing a game of £5+ to change your account from limited to full access**

Head over to https://steamcommunity.com/dev/apikey and log in to your account.

Then enter your Server's IP Address (without Port) in the `Domain Name` field.

Then agree to the Terms of Use and click Register.

Open your server.cfg and scroll down until you see a `steam_WebApiKey` line, then copy the key you just generated and paste it between the quotes.

If no such line exists then it can simply be added.

E.G
```
steam_WebApiKey "ECBB82291CEF372F0CBC66DD11D66DA5"
```

> If you're hosting your server on your local machine (your PC) then you can enter `localhost` into the Domain Name field.


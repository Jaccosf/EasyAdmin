# Installing EasyAdmin

Install it like any other Resource, no other Resources are Required for it to Run.

## Configuration
Add this to your server.cfg

```
ensure EasyAdmin

setr ea_LanguageName "en"                # set our language to english
setr ea_MenuButton "F2"		 # set our menu button to F2, this is a one-time setting!

add_ace group.admin easyadmin allow
```

## Adding Yourself as Admin - ZAP Hosting (non-txAdmin)
Enter yourself in the Settings Page under Admins, new line for each steamid.

## Adding Yourself as Admin - ZAP Hosting (txAdmin)

See [Adding Yourself as Admin - DIY](install.md)

## Adding Yourself as Admin - DIY
```
add_principal identifier.steam:STEAMHEXID group.admin
```
You can grab your `HexID` from [vacbanned.com](http://www.vacbanned.com/) by typing in your steam URL.

To use Steam HexIDs as an identifier, you'll need to have a Steam WebAPIKey setup. Follow this [guide](admins.md) to create one.

You can also use other identifiers, EasyAdmin is not specifically limited to SteamIDs, all available identifiers can be used, such as `discord`, `xbl` or `license`, to name a few examples.

**Done**
Getting any issues or have further questions? read the rest of the wiki, or join our 
### [Support Discord](https://discord.gg/GugyRU8)
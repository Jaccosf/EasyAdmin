# Installing EasyAdmin

Install it like any other Resource.

Simply Drag&Drop your `EasyAdmin` folder into the `resources` folder of your Server.

## Configuration
Add this to your server.cfg

```
ensure EasyAdmin

setr ea_LanguageName "en"                # set our language to english
setr ea_MenuButton "F2"		 # set our menu button to F2, this is a one-time setting!

add_ace group.admin easyadmin allow
```

## Adding yourself as an Admin

### ZAP Hosting (non-txAdmin)
Enter your in the Settings Page under Admins, add a new line for each SteamId.

### ZAP Hosting (txAdmin)

See the DIY Section

### Do it Yourself (self-hosted, txAdmin)

You can use this template to fill out your desired Values

```
add_principal identifier.IDENTIFIER:STEAMHEXID group.admin
```

For example, when using a STEAM ID

```
add_principal identifier.steam:1100001000056ba
```

You can use any Identifier available in FiveM for this, however, in this guide we will describe how to use your Steam ID.

To use Steam IDs as an identifier, a Steam WebAPIKey needs to be set up. Follow this [guide](steamapikey.md) to create one.

### Security Notice: Using this _will_ expose your webhook to players in form of code, if you are concerned about security for your webhook this method is not recommended.

By Default, wew.wtf is configured as the standard Image Uploader, as this Service no longer exists an alternative will have to be set, EasyAdmin Supports setting Discord as an Uploader, this will upload the image to a Discord Channel using Webhooks

Configuring the Screenshot Uploader is easy, simply paste the following in your Server Config File:

```
setr ea_screenshoturl "https://discordapp.com/api/webhooks/YOUR_WEBHOOK/URL"
setr ea_screenshotfield "files[]"
```

Make sure to enter your full Webhook URL in `ea_screenshoturl`.


After a Server Restart, screenshots should show as follows:

![](https://i.shol.it/aq62w/8h9rb.png)
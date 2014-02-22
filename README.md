# ![ModInfo](http://i.imgur.com/sCEmgbV.png) ModInfo

Thank you for supporting your Minecraft mod developer!

ModInfo is a library which allows a mod for Minecraft to provide some simple, **anonymous** information to the mod developer about Minecraft and their mod. This is done by sending a simple HTTP message to a Google Analytics server. 

Some of the really useful information for a mod developer is:
* Knowing what version of their mod is being used
* Knowing which versions of Minecraft needs to be supported
* Learning what the preferred language of their users may be
* Getting error reports when something goes wrong in their code

## Privacy Guaranteed

No personally identifiable information is sent by ModInfo at any time. We take adhere strictly to [Google's Privacy Policy](https://developers.google.com/analytics/devguides/collection/protocol/policy).  Your username, game server addresses, etc. will **never** be transmitted.

Here is a typical sample message sent by ModInfo:

    POST /collect HTTP/1.1
    Host: www.google-analytics.com
    
    v=1&tid=UA-XXXXXXXX-1&cid=b432-026d-08239-29ba&t=appview&an=CoolMod&av=1.0.0
    &cd=Minecraft+1.7.2%2C+Singleplayer&sr=1920x1200&ul=en_US


The message above includes:
* The mod developer's Google Analytics id (tid)
* An anonymous client id (cid)
* The mod id (an) and version (av)
* Minecraft version, game mode (cd), screen size (sr), and language (ul)

### Error Reporting

In software, it is very common for bugs to go unreported. With ModInfo, a mod developer can choose to have a message sent when his mod experiences an error.  This kind of error reporting is common with commercial games and consoles, but it has never been readily available to Minecraft mod developers until now.

Real-time error reporting by ModInfo means the mod developer can react to problems quickly and start preparing fixes right away.

### Anonymous ID

The anonymous id (cid in the sample message above) is constructed using a random "salt" value placed within the **.minecraft/config/(modname)_ModInfo.cfg** file.  

This anonymous id can be altered at anytime by changing the _salt_ value in the **(modname)_ModInfo.cfg** file, or by deleting the file altogether.  A new salt value will be generated the next time the file is created.

### Verbose messages

If you want to see exactly what messages are being sent by a mod, set the _verbose_ value in the **.minecraft/config/(modname)_ModInfo.cfg** file to "true".  The messages will be shown in your console window or log files.  

Note: The mod developer decides when messages are sent. If you have questions about the frequency of messages sent by a mod, contact the mod developer directly.

### You Can Opt Out

But please don't!  Mod developers rarely get good information on how their hard work is being used.  ModInfo is a simple, no-hassle, anonymous way for them to get basic information on how they can support you.

But if you really don't want that helpful message sent, here is how to Opt Out:

1. Find the name of the mod in the **.minecraft/config/(modname)_ModInfo.cfg** file
2. Change the enabled value for the mod's name from **true** to **false**.  
3. The next time the mod tries to use ModInfo, a final "opt-out" message will be sent and a confirmation number will be added to the mod's property value.
4. If you change your mind, simply set the property value to **true** to let ModInfo send a message again.

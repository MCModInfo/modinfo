# ![ModInfo](http://i.imgur.com/sCEmgbV.png) ModInfo

Thank you for supporting your mod developer!

ModInfo is a library which allows a mod for Minecraft to provide some simple, **anonymous** information to the mod developer about Minecraft and their mod. This is done by sending a simple HTTP message to a Google Analytics server. 

Some of the really useful information for a mod developer is knowing what version of their mod is being used, the version of Minecraft which needs to be supported, and what language translations may be needed.

## Privacy Guaranteed

No personally identifiable information is sent by ModInfo at any time. We take adhere strictly to [Google's Privacy Policy](https://developers.google.com/analytics/devguides/collection/protocol/policy).  Your username, game server addresses, etc. will **never** be transmitted.

Here is a typical sample message sent by ModInfo:

    http://www.google-analytics.com/collect?v=1&tid=UA-XXXXXXXX-1&cid=94e4597e&t=appview&sr=1920x1200&ul=en_US&an=coolmod&av=1.0&cd=Windows+7,Minecraft+1.7.2,Singleplayer

The message above includes:
* The mod developer's Google Analytics id (tid)
* An anonymous client id (cid) which can be altered by you at any time (see Anonymous ID below)
* The mod id (an) and version (av)
* Minecraft screen size (sr) and language (ul)
* OS name, Minecraft version, and game mode (cd)

### Anonymous ID

The anonymous id (cid in the sample message above) is constructed using a random "salt" value placed within the **.minecraft/config/ModInfo.cfg** file.  

This anonymous id can be altered at anytime by changing the _salt_ value in the **ModInfo.cfg** file, or by deleting the file altogether.  A new salt value will be generated the next time the file is created.

### You Can Opt Out

But please don't!  Mod developers rarely get good information on how their hard work is being used.  ModInfo is a simple, no-hassle, anonymous way for them to get basic information on how they can support you.

But if you really don't want that helpful message sent, here is how to Opt Out:

1. Find the name of the mod in the **.minecraft/config/ModInfo.cfg** file
2. Change the enabled value for the mod's name from **true** to **false**.  
3. The next time the mod tries to use ModInfo, a final "opt-out" message will be sent and a confirmation number will be added to the mod's property value.
4. If you change your mind, simply set the property value to **true** to let ModInfo send a message again.

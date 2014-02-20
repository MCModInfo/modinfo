ModInfo
=======

ModInfo is a library which allows a mod for Minecraft to provide basic, anonymous information to the mod developer about how their mod is being used.  This is done by sending a simple HTTP message to a Google Analytics server. The information uses no personally identifiable information and is limited the following:

* The mod name and version
* The version, language, and screen size of Minecraft
* Whether Minecraft is in Singleplayer or Multiplayer mode

No personally identifiable information is sent by ModInfo at any time.  An anonymous id is constructed and placed within a .minecraft/config/ModInfo.cfg file.  This id can be reset at anytime by simply deleting the ModInfo.cfg file.  A new id will be constructed the next time the file is created.

Opt Out
=======

Please don't!  Mod developers rarely get good information on how their hard work is being used.  ModInfo is a simple, no-hassle, anonymous way for them to know that somebody out there likes their work.

But if you really don't want that tiny anonymous message sent, here is how to Opt Out:

1. Find the name of the mod in the .minecraft/config/ModInfo.cfg file
2. Change the property value for the mod's name from "true" to "false" (without the quotes).  
3. The next time the mod tries to use ModInfo, a final "opt-out" message will be sent and a confirmation number will be added to the mod's property value.
4. If you change your mind, simply set the property value to "true" to let ModInfo send a message again.

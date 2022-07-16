## Valheim+
Getting Valheim Plus working on Deck requires some additional tweaks, and some that don't quite make any sense.

1. Download the `UnixServer.Zip` from the latest releases from [here](https://github.com/valheimPlus/ValheimPlus)
1. Download the newest version of `BepInEx` by selecting `BepInEx_unix_VERSION.zip` from [here](https://github.com/BepInEx/BepInEx) 
1. Open Steam in Desktop mode, go the properties for Valheim, then select "Browse local files"
1. Extract the contents  of `UnixServer.zip` to this directory 
1. Then Extract and overwrite the contents of `BepInEx_unix_VERSION.zip` to the same directory
1. Once the contents are extracted open `Konsole` in this directory by right clicking and selecting `Open in Konsole`
1. Then run this command, `chmod u+x start_game_bepinex.sh`
1. Back in Steam go back to the Properties for Valheim and under `Launch Options` add the following `/start_game_bepinex.sh ; echo %command%` 
    * NOTE: DO NOT enable 'Force compatibility for this game'
1. Try launching the game, it should now be Valheim+ 

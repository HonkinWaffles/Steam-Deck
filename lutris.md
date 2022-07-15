## Lutris
Install games from EA, GOG, EGS, and Ubisoft


1. Open the console using the `Konsole` application
1. Enter the following: `flatpak install flathub org.gnome.Platform.Compat.i386 org.freedesktop.Platform.GL32.default org.freedesktop.Platform.GL.default`
1. Download `Lutris` from the Discover Store
1. Login to the specific service you'd like and download the game
    * Note: Some games may require additional tweaks
1. The first time you do this you will need to install the specific launcher
1. Once the install is finished right click the game and select `Create steam shortcut`
1. If you'd like to add artwork for the game to Steam use `SteamGridDB (Guide coming soon)`




### Ubisoft Specific Games
Games installed via Ubisoft will not launch once installed due to the shortcut pointing to the wrong location. 

1. Open `Ubisoft Connect`
1. Find the game you just installed
1. Right click and select `Create Desktop Shortcut`
1. Close `Ubisosft Connect` and open your file manager
1. Navigate to `~/games/ubisoft-connect/drive_c/users/deck/Desktop`
1. Right click the shortcut with the extension `.url` in your text editor
1. Copy the line and everything after `URL=`
1. Go back to Lutris and right click the game selecting `Configure` then `Game options`
1. Past the `uplay` url into the `Arguments` field replacing what exists
    * It should look like this `URL=uplay://launch/5705/0`
1. Try launching the game

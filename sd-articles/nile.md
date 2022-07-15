## Nile

Install games from the Amazon game store


# WARNING!! MUST READ!!!
This application does not have a GUI and is still in early stages of development. This means a few different things 
1. Some of the tasks require a good level of understanding of `Linux`, `Python` and the Terminal
1. Information on how the application works is always changing meaning this guide can be outdate quickly always check the github page for the [Nile](https://github.com/imLinguin/nile) project for updates
1. This requires you to make changes to the Linux filesystem that Valve has specifically blocked. 
    * This means OS updates may break this application
1. MOST IMPORTANTLY - If you make changes without knowing what you are doing you could damage your OS and have to start over completely. 
1. BACKUP YOUR DATA!! 
1. BACKUP YOUR DATA!!

## Preparation  

Disable read ONLY filesystem:
1. Open the terminal
1. Set a password with `passwd`
1. Run `sudo steamos-readonly disable` 

Pip3 Installation:
1. Install page can be found [here](https://pip.pypa.io/en/stable/installation/)
1. Download `get-pip.py` from [here](https://bootstrap.pypa.io/get-pip.py)
1. Add execute with `chomod +x get-pip.py`
1. Run installation with `python get-pip.py`

## Installation 
1. Download the application `git clone https://github.com/imLinguin/nile`
1. CD into the newly create directory `cd nile`
1. Login `./bin/nile auth --login`

Optional Steps (Add alias for nile):
1. Get the current directory (Example: `/home/deck/Documents/Nile/bin/nile`) 
1. Edit `~/.bashrc`
1. At the bottom add `alias nile='/home/deck/Documents/Nile/bin/nile'` and save
1. Restart your terminal 

## Usage 
Note: Replace `./bin/nile` with `nile` if you completed the optional steps in the installation

The `nile` application takes multiple arguments for each section it has; this will go over everything.


1. `auth` - Used for Amazon account management
    * `-login`
        * Opens the browser to log into your Amazon account 
    * `-logout`
        * Logs out of the currently logged in account

    Example: `./bin/nile auth -login` 
1. `library` - Manages available and installed games
    * `--installed` or `-i`
        * Only lists installed games
    * `list` 
        * Shows available games
    * `sync`
        * Gets updated list of games

    Examples: 
    ```
    ./bin/nile library list 
    ./bin/nile library list --installed
    ./bin/nile library sync
    ```

1. `install`
    * `--max-workers MAX_WORKERS`
        * Number of maximum threads for downloads
    * `--base-path BASE_PATH`
        * Specify base installation path e.g., /home/USERNAME/Games/nile It'll append save filename to that path
    * `--path EXACT_PATH` 
        * Specify exact install location
    * `id`
        * The idea of the game found in the library
    
    Examples:
    ```
    ./bin/nile install id GAME_ID 
    ./bin/nile install --base-path /home/deck/Games/Game/ id GAME_ID
    ```

1. `launch`
This is to launch games directly from the terminal, personally I find it better to launch them from Steam for game mode support. I will go over that afterwards. 
    * `--bottle` 
        * To run the application in bottles
    * `--wine-prefix`
        * Specify wineprefix to be used
    * `--wine`
        * Specify wine binary
    * `--no-wine`
        * Don't use wine
    * `--wrapper`
        * Wrapper to be used when launching a game
    * id
        * The game ID to run

1. `uninstall`
    * id
        * The ID of the game to uninstall 


## Compatibility with Deck
Since this is designed around a Linux experience and not the deck there is a few different methods that could be taken to get things working properly. In this guide I will cover the simpler way of installing a game once `nile` is installed.

1. Login to `nile` with `./bin/nile auth -login`
1. Find the game to install with `./bin/nile library list`
1. Install the game `./bin/nile install id GAME_ID`
1. The game will automatically save to `~/Games/nile`
1. Open Steam and click `Add non-steam game` (Make sure to change to all file types)
1. Find and select the EXE for the game
1. Tell Steam to force compatibility in the settings to enable Proton
1. Try launching the game

In most cases this should work, some games act strangely and may not. At that point it may require some additional troubleshooting specific to that game.


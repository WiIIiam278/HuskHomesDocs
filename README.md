![](https://www.spigotmc.org/attachments/banner-png.553176/)
# HuskHomes
HuskHomes is a simple, hassle-free mySQL-based homes, player warps and teleportation suite. Supports teleporting across multiple servers through a Bungee network.

## Features
* Runs on a mySQL database with easy setup.
* Simple and intuitive interface; no clunky chest GUIs. Instead, a robust clickable JSON chat link system to view and edit homes. 
* Supports teleporting across multiple servers on a single network.
* Teleports and teleport request command support, cross-server.
* Has a /back command allowing players to go back to where they were before they teleported, or return to where they died.
* Set a spawn location with /setspawn and go there with /spawn (can be enabled/disabled)
* Randomly teleport into the wild with /rtp (can be enabled/disabled)
* Customisable; customise messages (with custom color support) and change the configuration to suit your needs.
* Full tab completion support across all commands.
* Supports migration from EssentialsX (more in the future/on request if viable)

## Setup
From the [Setup page](https://github.com/WiIIiam278/HuskHomesDocs/wiki/Setup)
### Setting up for a single server
1. Download HuskHomes.jar from the resource page.
2. Place in your server's plugin folder. 
3. Restart the server and navigate to `HuskHomes/config.yml`
4. Fill in the configuration file with your SQL database details and change the options to suit your setup
5. Restart the server and you should be good to go.

### Setting up on Waterfall or Bungee
> **⚠️ Warning**: Do NOT install HuskHomes on the proxy server! It is a **Spigot** (and by extension Paper) plugin.
1. Download HuskHomes.jar from the resource page.
2. Place the plugin in the plugin folders of **all** the servers you wish to run HuskHomes on.
3. Restart all the servers you added HuskHomes.jar to. Then, turn them back off.
4. For each server, navigate to `HuskHomes/config.yml` and change the following settings
    1. Fill in the SQL database details
    1. Change `bungee: false` to `bungee: true`
    1. Replace `server` in the `server_name: server` setting to be the name of that server on the bungee network (e.g if your server is called "lobby" put "lobby")
    1. Modify other settings as appropriate
5. Start the servers you installed HuskHomes on and you should be good to go.
  
## Wiki
For more help and information, check the [HuskHomes Wiki](https://github.com/WiIIiam278/HuskHomesDocs/wiki)  

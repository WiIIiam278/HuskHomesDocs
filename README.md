# HuskHomes
A simple, hassle-free mySQL-based homes and player warps system. Supports homes across multiple servers through a Bungee network.

## Features
* Customisable; permission node support.
* Runs on a mySQL database with easy setup.
* Simple and intuitive interface; no clunky chest GUIs. Instead, a robust clickable JSON chat link system to view and edit homes. 
* Supports teleporting across multiple servers on a single network.
* Teleports and teleport request command support, cross-server.
* Has a /back command allowing players to go back to where they were before they teleported, or return to where they died.
* Set a spawn location with /setspawn and go there with /spawn
* Randomly teleport into the wild with /rtp
* Full tab completion support across all commands.

## Commands
Command | Description | Permission
------------ | ------------- | -------------
/home | Return to a home | `huskhomes.home`
/sethome | Set a new home | `huskhomes.sethome`
/delhome | Delete a home | `huskhomes.delhome`
/edithome | Edit a home, set a description and make it public |  `huskhomes.edithome`, `huskhomes.edithome.public` (to allow making a public home)
/publichome | Teleport to a public home | `huskhomes.publichome`
/homelist | List your homes | `huskhomes.home`
/publichomelist | List all public homes | `huskhomes.publichome`
/back | Return to your previous position | `huskhomes.back`, `huskhomes.back.death` (to allow /back from where you died)
/tp | Teleport to a player | `huskhomes.tp`
/tphere | Teleport another player to you | `huskhomes.tp`
/tpa | Request teleport another player | `huskhomes.tprequest`
/tpahere | Request teleport another player to you | `huskhomes.tprequest`
/tpaccept | Accept a teleport request | `huskhomes.tprequest`
/tpdeny | Deny a teleport request | `huskhomes.tprequest`
/spawn | Go to spawn | `huskhomes.spawn`
/setspawn | Update the location of spawn | `huskhomes.setspawn`
/rtp | Randomly teleport to the wild | `huskhomes.rtp`
/huskhomes | View plugin info, check for updates, reload config | `huskhomes.about`, `huskhomes.version_checker`, `huskhomes.reload`

## Setup
### Single server setup
1. Download HuskHomes.jar
2. Place in your server's plugin folder. 
3. Restart the server and navigate to `HuskHomes/config.yml`
4. Fill in the configuration file with your SQL database details and change the options to suit your setup (see below)
5. Restart the server and you should be good to go.

### BungeeCord setup
1. Download HuskHomes.jar
2. Place the plugin in the plugin folders of **all** the servers you wish to run HuskHomes on.
3. Restart all the servers you added HuskHomes.jar to. Then, turn them back off.
4. For each server, navigate to `HuskHomes/config.yml` and change the following settings
  * Fill in the SQL database details
  * Change `bungee: false` to `bungee: true`
  * Replace `server` in the `server_name: server` setting to be the name of that server on the bungee network (e.g if your server is called "lobby" put "lobby")
  * Modify other settings as appropriate (see below)

## Config.yml
* `host:` 
  * MySQL database server IP
* `port: 3306` 
  * MySQL database port
  * Default: 3306
* `database:` 
  * MySQL database name
* `username:` 
  * MySQL database username
* `password:` 
  * MySQL database password
* `player_data_table: huskhomes_players` 
  * Name of the player data table to be used in the database
  * Default: huskhomes_players
* `home_data_table: huskhomes_homes` 
  * Name of the home data table to be used in the database
  * Default: huskhomes_homes
* `teleport_warmup: 5`
  * A number; the amount of time players need to stand still for before teleporting.
  * Set to 0 to disable teleport warmup for all players.
  * The warmup time can be bypassed by players with the `huskhomes.bypass_timer` permission node.
  * Default: 5
* `do_spawn_command:`
  * `true` or `false`; whether or not to enable the /spawn command. 
  * Default: true
* `spawn_world:`
  * Location of /spawn command: world. Set with /setspawn
* `spawn_x:`
  * Location of /spawn command: x co-ordinate. Set with /setspawn
* `spawn_y:`
  * Location of /spawn command: y co-ordinate. Set with /setspawn
* `spawn_z:`
  * Location of /spawn command: z co-ordinate. Set with /setspawn
* `spawn_pitch:`
  * Location of /spawn command: pitch. Set with /setspawn
* `spawn_yaw:`
  * Location of /spawn command: yaw. Set with /setspawn
* `bungee:`
  * `true` or `false`; whether or not to enable bungee mode. Enable if you are running on a BungeeCord, Waterfall, etc network.
  * Default: false
* `server_name:`
  * If bungee mode is enabled, put the name of the server you are running here (the one you specify in the BungeeCord config and use to connect with the /server command).
  * For example, if this is the "survival" server on the bungee network, put "survival" here.
* `do_rtp_command:`
  * `true` or `false`; whether or not to enable the /rtp command. 
  * Default: false
* `rtp_boundary:`
  * A number; the maximum distance from 0,0 a player can be randomly teleported.
  * Default: 5000
* `do_dynmap:`
  * `true` or `false`; whether or not to enable integration with the Dynamic Map plugin.
  * Requires dynmap being installed on your server.
  * Default: false
* `do_economy:`
  * `true` or `false`; whether or not to enable economy features.
  * Requires Vault being installed on your server.
  * Default: false
* `public_home_cost:`
  * A number; how much should be charged for making a home public
  * Requires Vault being installed on your server and `do_economy` set to true.
  * Default: 50.0
* `set_home_cost:`
  * A number; how much should be charged to buy another set home
  * Requires Vault being installed on your server and `do_economy` set to true.
  * Default: 500.0
* `free_sethomes:`
  * A number; the number of free set home slots the player gets (after which additional homes will cost money)
  * Requires Vault being installed on your server and `do_economy` set to true.
  * Default: 3

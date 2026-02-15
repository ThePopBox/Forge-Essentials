![Minecraft](https://img.shields.io/badge/Minecraft-1.20.1-green)
![Forge](https://img.shields.io/badge/Forge-47.3.0-orange)
![License](https://img.shields.io/badge/License-MIT-blue)

# Minecraft Forge Essentials 1.20.1
Server Utilities &amp; Management for Minecraft Forge 1.20.1 (47.3.0)
<br>This mod provides essentials for server administration and quality of life improvements using a fully modular configuration script
<hr>

# Installation
This mod is desgined to be installed on the server-side only (Clients do <b>not</b> require this mod)
<br>Fully integrable into any Minecraft Forge 1.20.1 server
<ol>
  <li>Configure the inital forge server</li>
  <li>Stop the server</li>
  <li>Place the Forge Essentials jar into the mods folder</li>
  <li>Launch the server</li>
  <li>Configure the mod in the generated config file located in root/configs/eutills-config.toml</li>
</ol>
<hr>

# Core Features & Systems
Forge Essentials is developed in a modular style, where each feature/system can be completely ignored if you don't want to integrate it into your server

# 🏰 Land Protection (Claims System)
<ol>
  <li>Chunk-based selection system</li>
  <li>Claim preview visualizaion</li>
  <li>Trust levels (Visitor / Builder / Officer</li>
  <li>Claim flags</li>
  <li>Claim block balance tracking</li>
  <li>Admin claim controls</li>
</ol>
<details>
<summary><b>Click to expand section</b></summary>
<b>Chunk-based Selection</b>
<br>Claiming land is done by going to opposite corners of your land and typing /claim pos1 or /claim pos2 (similar to WorldEdit)
  <br>Claims will automatically round to the closest full chunk, and claim the entire vertical height of the world
<br><b><u>Claim preview visualizaion</b></u>
  <br>After setting the two positions for your land claim, enter /claim preview, which will give you details about your claim
  <ul>
    <li>Amount of chunks</li>
    <li>Block cost (each chunk is 256 blocks 16x16 </li>
    <li>If the claim overlaps exisiting claims</li>
  </ul>
![Optional Alt Text](path/to/image.png)
<br><br><b>Trust Levels</b>
  <br>After finishing previewing the selection you made, enter /claim confirm, this will create your claim.
  <br>PS. When players enter or leave your claim, you will receive a chat notification 
  <br>Now that your claim is complete, you can trust players to it. To review your claim settings, type /claim info (while standing inside the claim)
![Optional Alt Text](path/to/image.png)
  <br><br>Let's now add players to your claim using the command /claim trust [player] [level] Example:/claim trust thepopbox officer 
  <br>To remove a trusted player, you can issue the command /claim untrust [player]
  <br>There are three different trust levels
    <ol>
      <li>Visitor: can only interact with objects, such as open doors, switch levers, etc...</li>
      <li>Builder: Inherits all visitor permissions. Has access to break/place blocks inside the claim</li>
      <li>Officer: Inherits all builder permissions. Has access to edit claim flags</li>
    </ol>
<br><b>Claim Flags (All Six Explained)</b>
    <br>Each claim has configurable flags; these flags override the trust level access. For example, user A has a builder trust level, the claim has build set to off, and user A can no longer build inside the claim
    <br>List of the flags and descriptions
    <ol>
      <li>Build: toggles the ability to place and break blocks inside a claim</li>
      <li>Containers: toggle the ability to interact with containers</li>
      <li>Interact: toggle the ability to interact with doors, levers, button etc...</li>
      <li>Fire: toggle fire spread, and toggles the ability to spark flames inside the claim</li>
      <li>Mob Griefing: toggles mob griefing on and off inside the claim</li>
      <li>TNT: toggle if TNT can damage blocks inside the claim</li>
    </ol>
<br><b>All Commands for Claim System</b>
    <ul>
      <li>/claim pos1</li>
      <li>/claim pos2</li>
      <li>/claim confirm</li>
      <li>/claim preview</li>
      <li>/claim info</li>
      <li>/claim trust [player] [level]</li>
      <li>/claim untrust [player]</li>
      <li>/claim list</li>
      <li>/claim balance</li>
      <li>/claim remove</li>
      <li>/claim admin</li>
    </ul>
</details>
        
# 🔱 Rank & Permission System
<ol>
  <li>Config-driven rank definitions</li>
  <li>Rank inheritances</li>
  <li>Command-base permission control</li>
  <li>Runtime config reload</li>
  <li>No hardcoded rank restrictions</li>
</ol>
<details>
<summary><b>Click to expand section</b></summary>
This mod allows you to create as many ranks as you want and connect there permissions using inhertance, Example: Member -> Mod -> Admin, the member rank will have most of the basic funcationally permission which you have configured, then the mod rank will inherit those permission and have a set of their own permission unqiue to them, then the admin rank will inherit the mod and member permissions with their own set of permissions.
<br>An example setup is already preconfigured within the mods config file, which can be found inside the root/configs/eutills-config.toml
![Optional Alt Text](path/to/image.png)
<br><br><b>All Commands for Rank System</b>
  <ul>
    <li>/whoami: Shows the user what rank they are and the commands they have access to</li>
    <li>/setrank [player] [rank]</li>
  </ul>
</details>

# 🏠 Homes System
<ol>
  <li>Configurable amount of homes per rank</li>
  <li>Teleport back to last death </li>
</ol>
<details>
<summary><b>Click to expand section</b></summary>
This mod allows you to configure the number of homes each rank can set, and provides a default amount of  homes if a rank system module is not enabled. Players can perform /back to return to their death location if they have permission. 
<br><br><b>All Commands for Homes System</b>
  <ul>
    <li>/sethome [name]</li>
    <li>/home [name]</li>
    <li>/delhome [name]</li>
    <li>/homes</li>
    <li>/back</li>
  </ul>
![Optional Alt Text](path/to/image.png)
</details>

# 🌏 Warps System
<ol>
  <li>Server-definded warp locations</li>
  <li>Optional rank requirement per warp</li>
  <li>Spawn management</li>
</ol>
<details>
<summary><b>Click to expand section</b></summary>
This mod allows you to configure a server spawn location for all players to spawn on when they first join, die without a bed, or execute /spawn. There are also server warps; these warps will automatically be assigned to the member rank (default rank configured) if no rank requirement is added when setting the warp. When a player first joins the server, they will receive a first join welcome message if enabled; it is fully configurable inside the config file. 
  <br><br><b>All Commands for Warps System</b>
  <ul>
    <li>/warp [name]</li>
    <li>/setwarp [name] [rank]</li>
    <li>/warps</li>
    <li>/spawn</li>
    <li>/setspawn</li>
  </ul>
![Optional Alt Text](path/to/image.png)
</details>

# 🤝 Teleport System
<ol>
  <li>Player to player teleport requests</li>
  <li>Accept / deny workflow</li>
</ol>
<details>
<summary><b>Click to expand section</b></summary>
This mod allows players to request to teleport to eachother or request a player to teleport to them. Giving the reviving player options to accept or deny the request. 
  <br><br><b>All Commands for Teleport System</b>
  <ul>
    <li>/tpa [player]</li>
    <li>/tpahere [player]</li>
    <li>/tpaccept</li>
    <li>/tpdeny</li>
  </ul>
![Optional Alt Text](path/to/image.png)
</details>

# 🗳 Voting System (Day/Night Cycle)
<ol>
  <li>Day/Night vote system</li>
  <li>Cycle pause/resume support</li>
</ol>
<details>
<summary><b>Click to expand section</b></summary>
This mod allows players to vote on whether the day/night cycle should be paused on either day, night, or resume normal flow. This was implemented as a fair way for players using MineColonies to pause the cycle during the day to allow their civs to work 24/7.
<br><br><b>All Commands for Voting System (Day/Night Cycle</b>
  <ul>
    <li>/vote</li>
    <li>/voteday</li>
    <li>/votenight</li>
    <li>/voteresume</li>
  </ul>
![Optional Alt Text](path/to/image.png)
</details>

# ⚙ Admin Utilities
<ol>
  <li>Scheuled broadcast messages</li>
  <li>Qauilty of Life imrpovements for Admins</li>
  <li>Gamemode short cut commands</li>
</ol>
<details>
<summary><b>Click to expand section</b></summary>
This mod provides multiple administrative utilities.
<br><br><b>All Commands for Admin Utilities</b>
<ul>
  <li>/fly: Enables flight</li>
  <li>/heal: Restores all the players health</li>
  <li>/feed: Restores all the player hunger</li>
  <li>/repair: Restores the held items' durability to full</li>
  <li>/gms: Enables gamemode survival</li>
  <li>gmc: Enables gamemode creative</li>
  <li>/spectator or /spec: Enables free cam of 250blocks around the player and returns them to their starting location one exit of spectator</li>
  <li>/smite [player]: Cast lightning on a player</li>
  <li>/skull: Gives the player their head as an item</li>
  <li>/estop: Safely shuts the server down</li>
  <li>/broadcast [message]: Send a manual broadcast. In the config files, you are able to configure scheduled broadcasts to appear</li>
  <li>/ext: Extiginishs the players negitive effects</li>
</ul>
![Optional Alt Text](path/to/image.png)
</details>

# 🎨 Item Utilities
<ol>
  <li>Rename items (supports formatting codes)</li>
  <li>Add/remove/list item lore</li>
  <li>Custom enchant application (any mods, enchants)</li>
  <li>Post held item to chat</li>
</ol>
<details>
<summary><b>Click to expand section</b></summary>
This mod allows you to change item names and lore using formatting codes and share your currently held item in the chat for the rest of the server to see.
<br><br><b>All Commands for Item Utilites</b>
<ul>
  <li>/rename [name]</li>
  <li>/lore [add|list|clear]</li>
  <li>/eenchant [enchantment] [level]</li>
  <li>/i: Posts held item into chat</li>
</ul>
![Optional Alt Text](path/to/image.png)
</details>

# 💬 Informational Utilities
<ol>
  <li>Promote server social platforms</li>
  <li>Ensure players under server rules</li>
</ol>
<details>
<summary><b>Click to expand section</b></summary>
This mod provides a few ways to share information with your players using built-in commands and configure them to your liking.
<br><br><b>All Commands for Informational Utilities</b>
  <ul>
    <li>/ehelp: Shows all the commands this mod offers</li>
    <li>/near: Shows all players within 1000 blocks and their coordinates</li>
    <li>/discord: Shows the player the server's official Discord link</li>
    <li>/rules: Shows the player the server rules</li>
    <li>/exp: Shows the player their current experience level and amount of experience</li>
    <li>/afk: Puts a player into /afk state, the player will not take any damage until they move, interact with something, or talk in chat</li>
  </ul>
![Optional Alt Text](path/to/image.png)
</details>
<hr>

# Technical Details
<ul>
  <li>Built using Forge 47.3.0</li>
  <li>Minecraft 1.20.1</li>
  <li>Brigadier-based command registration</li>
  <li>Modular manager-based architecture</li>
  <li>Config driven permission system</li>
  <li>Designed for moduality and scalbilty</li>
</ul>

<hr>

# Roadmap
planned features for the next update
<ol>
  <li>Discord bridge integration: Two-way system where Discord and chat to Minecraft and vice versa </li>
  <li>Economy framework: Allowing players to sell items to the server for currency</li>
  <li>Custom gear framework: Allowing players to implement their custom datapack and apply custom visuals to existing gear</li>
  <li>Cross-loader support (neo-forge / possible fabric if the rewrite isn't a lot)</li>
</ol>

<hr>

# Design Philosophy & Develpment Status
Forge Essentials is built as a server framework; it is meant to be implemented into any Forge server and does not require clients to also install it
<br>Each system built is isolated into its own manager and command layers. This allows
<ul>
  <li>Independent expansion</li>
  <li>Clean maintenance</li>
  <li>Reduced coupling</li>
  <li>Enchanced end user configureabiltiy</li>
</ul>
<br>Forge Essentials is evolving, and active development is underway. 
<br>Contributions and suggestions are welcome 

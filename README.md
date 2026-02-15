![Minecraft](https://img.shields.io/badge/Minecraft-1.20.1-green)
![Forge](https://img.shields.io/badge/Forge-47.3.0-orange)
![License](https://img.shields.io/badge/License-MIT-blue)

# Minecraft Forge Essentials 1.20.1
Server Utilities &amp; Management for Minecraft Forge 1.20.1 (47.3.0)
<br>This mod provides essentials for server administion and qauilty of life improvements using a fully modular configuration script
<hr>

# Installation
This mod is desgined to be installed on the server-side only (Clients do <b>not</b> require this mod)
<br>Fully intergratable into any Minecraft Forge 1.20.1 server
<ol>
  <li>Configure the inital forge server</li>
  <li>Stop the server</li>
  <li>Place the Forge Essentials jar into the mods folder</li>
  <li>Launch the server</li>
  <li>Configure the mod in generated config file located in root/configs/eutills-config.toml</li>
</ol>
<hr>

# Core Features & Systems
Forge Essentials is developed in a modular style where each feature/system can be completely ignored if you don't want to integrate it into your server

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
<summary>Click to expand section</summary>
<b>Chunk-based Selection</b>
<br>Claiming land is done by going to opposite corners of your land and typing /claim pos1 or /claim pos2 (simmilar to WorldEdit)
  <br>Claims will automatically round to the closest full chunk, and claim the entire vertical height of the world
<br><b><u>Claim preview visualizaion</b></u>
  <br>After setting the two positions for your land claim enter /claim preview, this will give you details about your claim
  <ul>
    <li>Amount of chunks</li>
    <li>Block cost (each chunk is 256 blocks 16x16 </li>
    <li>If the claim overlaps exisiting claims</li>
  </ul>
![Optional Alt Text](path/to/image.png)
<br><br><b>Trust Levels</b>
  <br>After finishing previewing the selection you made enter /claim confirm, this will create your claim.
  <br>PS. When players enter or leave your claim you will recieve a chat notifcation 
  <br>Now that your claim is complete, you can trust players to it. To review your claim settings type /claim info (while standing inside the claim)
![Optional Alt Text](path/to/image.png)
  <br><br>Let's now add players to your claim using the command /claim trust <player> [level] Example; /claim trust thepopbox officer 
  <br>There are three different trust levels
    <ol>
      <li>Visitor: can only interact with objects, such as open doors, switch levers etc..</li>
      <li>Builder: Inherits all visitor permission. Has access to break/place blocks inside the claim</li>
      <li>Officer: Inherits all builder permissions. Has access to edit claim flags</li>
    </ol>
<br><b>Claim Flags (All Six Explained)</b>
    <br>Each claim has configurable flags, these flags override the trust level access. Example, user A has builder trust level, however the claim has build set to off, user A can no longer build inside the claim
    <br>List of the flags and descriptions
    <ol>
      <li>Build: toggles the ability to place and break blocks inside a claim</li>
      <li>Containers: toggle the ability to interact with containers</li>
      <li>Interact: toggle the ability to interact with doors, levers, button etc..</li>
      <li>Fire: toggle fire spread, and toggles the ability to spark flames inside the claim</li>
      <li>Mob Griefing: toggles mob griefing on and off inside the claim</li>
      <li>TNT: toggle if tnt can damage blocks inside the claim</li>
    </ol>
</details>


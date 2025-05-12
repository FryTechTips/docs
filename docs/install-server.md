# How to make a H1 Dedicated Server

A step-by-step guide on setting up a Dedicated Server for H1-Mod.
:::warning

**We do not provide the official Call of Duty: Modern Warfare Remastered game files. You must own and install the game separately before setting up the server. This guide assumes you have already installed the game on your machine.**

At the current point in time, the dedicated server can be run on Windows only. (Dedicated Server CPU compatibility is undergoing upgrades, as some older Xeon processors have issues with the MWR binary)

### Prerequisites

* The server requires the base game of Modern Warfare Remastered Multiplayer onlny installed via [steam only!](https://store.steampowered.com/agecheck/app/393080/)
* The server requires a static ip address.
* The server requires port forwarding. A tutorial can be found [here](port-forwarding).
* The server requires some redists which can be easily installed via this [Redist Installer](https://chse.dev/redists)

### Installation

Grab the latest [h1-mod.exe Github](https://github.com/auroramod/h1-mod/releases) if you haven't already.
![](/img/releases.png)
copy the h1-mod.exe from your downloads page/folder and paste it to the root of your MWR game folder

<center><img src="/img/results.png"/></center>

Now we are repeating the same step but we need to grab the [latest server configuration files](https://github.com/FryTechTips/h1-mod-server-config/releases) from source code (zip) and extract main folder and bat file to the root of your MWR game folder just like you did the same way with h1-mod.exe. 

Now file explorer may prompt you to overwrite main folder. If do so just hit yes and progress box should disappeared

You can open StartServer.bat file and confirm that it loads by typing status within ~2 mins of the server loading.

Each time if you feel like your server not running you can always check your server by typing "status" and enter on the console window.

### Customization of your server

Custom your server can be very easily. All you have to do is go to your main folder and open server.cfg with either your regular windows notepad or what we recommend is [Notepad++](https://notepad-plus-plus.org/)

I give you a few basic samples..

* sv_hostname

Giving your server a identity to recongize a server when you open h1-mod and looking at the serverlist. You can use [color codes](colorcodes) To make your hostname more fancy...

* sv_motd

This will give you the option to have a message of the day on the loading screen from your server during a new user connecting or map rotation to the next match.

*rcon_password

This is handy for tools like in-game console to control your server. [IW4MAdmin monitoring system](https://github.com/RaidMax/IW4M-Admin) to control, ban and change maps within a breeze of your game chat.

*scr_war_scorelimit

To reach the limit of scoring on Teamdeath Match

*scr_war_timelimit

Whenever the time runs out per map before it rotates to the next map and match.

*g_gametype

If you want something else besides Teamdeath Match. You can change it to different modes. like dm for free-for-all or dom for Domination. Just look over the gametypes list.

*scr_game_hodgepodgeMode

Custom gamemodes that the base MWR supported. 2 for Slasher or 4 for Snipers only or 6-7 for RPG Only and 9 for Prophunt.

*sv_maprotation

This is map rotation. So each gametype or map will start order. Lets say you don't want shipment. Then remove map mp_shipment. If you want a mix varity of TDM and dom then put gametype dom before map mp_xyz. 
Make sure your rotation is correct you will ended having problems keeping your server online.

Save changes and restart/start your server.

### Running multiable servers

Running multiable servers is a easy process. Copy StartServer.bat and paste it in the same game folder. You should have a StartServer - Copy.bat. You can right click and rename the file to something more simple. Like StartServer2.bat

Right click and edit StartServer2.bat with notepad.

Change H1M Dedicated - Defualt to whatever name you want to call it.

Change server.cfg to server2.cfg

Change Port 27016 with a 1+ higher number. Lets say 2017! You would need to also [here](port-forwarding) that as well or you will not see it on the list.

save changes on notepad and exit.

Go to your main folder and copy and paste server.cfg the same way you did with other file and right click and rename that server - Copy.cfg to server2.cfg

Right click and edit server2.cfg. 

Make sure sv_hostname is different then your orginal server you have up and running. 

Change g_log h1-mod\logs\games_mp.log to h1-mod\logs\games_mp2.log or you will get a conflect on logs espically if you have [IW4MAdmin monitoring system](https://github.com/RaidMax/IW4M-Admin).

For a additional security I would recommend changing rcon_password as well but that is very optional if you want to do it. However you can leave it the same and still will not conflect between the 2 servers but I highly don't recommend it!

Now you can change your g_gametype to something else and sv_maprotation. After you done save and exit notepad!

Now you should be able to StartServer2.bat and now you have 2 server lobbies going!

# SoftBot-Auto-PCB
SoftEther VPN Discord Bot – PCB Slot Tracker
=============================================
A Python bot that watches your SoftEther VPN logs over SSH and keeps your Discord server updated with who's connected and which PCB slots are in use. Super handy for setups where you’ve got limited "slots" (like PCBs for arcade games) and need to keep track of who's using what in real time.
======================================================================
  What it does:

1.Watches the logs: Connects to your VPN server over SSH and tails the log to spot when someone connects or disconnects.
2.Assigns slots: As users connect, the bot gives them the next free PCB slot (1–4). When they disconnect, the slot is freed up.
3.Posts to Discord: It sends a clean, single embed message in your Discord with the current status:
4.Who’s using which slot
5.Which slots are still open
6.Keeps track of users even if there’s a hiccup or the connection drops. It also automatically switches to the next day’s log file when the date changes.
========================================================================================================================================================
  Instructions:

Before running the bot, install the requirements with this command (on Windows):
pip install discord.py paramiko

After that, open the script and set a few variables at the top to match your setup — like your server IP, VPN hub name, and Discord token.
Edit the Python file (VersusBpt.py) and look for these lines:
===============================================================
REMOTE_SERVER = "your-server-ip"
REMOTE_USER = "your-user"
REMOTE_PASSWORD = "your-password"
REMOTE_LOG_PATH = "/usr/local/softether/server_log"
VIRTUAL_HUB_NAME = "your-hub-name"
DISCORD_TOKEN = "token"
DISCORD_CHANNEL_ID = your-channel-id
==============================================================
REMOTE_SERVER =	The IP address or hostname of your server
REMOTE_USER =	The SSH username used to connect to your server
REMOTE_PASSWORD =	The SSH password for that user (consider using key auth for security!)
REMOTE_LOG_PATH =	The full path to your SoftEther log folder (usually /usr/local/softether/server_log) or wherever your logfiles output to.
VIRTUAL_HUB_NAME =	Your SoftEther virtual hub name (case-sensitive)
DISCORD_TOKEN =	Your Discord bot token from the Discord Developer Portal
DISCORD_CHANNEL_ID = The numeric channel ID of where you want the bot to post


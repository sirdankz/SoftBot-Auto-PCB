# 🎮 SoftBot-Auto-PCB  
### SoftEther VPN Discord Bot – PCB Slot Tracker

A Python bot that watches your SoftEther VPN logs over SSH and keeps your Discord server updated with who's connected and which PCB slots are in use. Super handy for setups where you’ve got limited "slots" (like PCBs for arcade games) and need to track who’s using what — in real time.

---

## 🔧 What It Does

1. **Watches the logs**  
   Connects to your VPN server over SSH and tails the SoftEther log file to detect when users connect or disconnect.

2. **Assigns slots automatically**  
   As users connect, it gives them the next free PCB slot (1–4). When they disconnect, the slot gets freed up.

3. **Posts updates to Discord**  
   It sends a clean, single embedded message that shows:
   - Who’s using which slot
   - Which slots are still open

4. **Keeps tracking even if things drop**  
   Handles network hiccups, reconnects, and automatically switches to the next log file each day.

---

## 🚀 Setup Instructions

### Step 1: Install Requirements

Make sure Python and `pip` are installed.  
Then install the required packages:

```bash
pip install discord.py paramiko

# Setup-And-Use-A-Firewall-On-Windows
Task 4

# Windows Firewall Configuration:

This repository provides step-by-step instructions to configure and test basic firewall rules on **Windows** using both the **Windows Defender Firewall GUI** and **Command Line (netsh)**.

## Tools Used:
- Windows Defender Firewall
- Command Prompt (Administrator)

## Open Firewall Configuration:
For this, I used the command: wf.msc

## Current Firewall rules
The file is attached. I used the following command to list them:
netsh advfirewall firewall show rule name=all

## Add a rule to block inbound traffic on a specific port (e.g., 23 for Telnet).
For this, I used the command:
netsh advfirewall firewall add rule name="Block Telnet" dir=in action=block protocol=TCP localport=23

## Test the Block Rule:
For this, I first enables the **Telnet Client** from **"Turn Windows features on or off"**.
To test the block rule, I ran the following command:
telnet localhost 23

## Remove the Test Block Rule:
To achieve this, I used the following command:
netsh advfirewall firewall delete rule name="Block Telnet"

## How Firewalls Work:
Firewalls are based on:
- Port Numbers
- Protocols (TCP/UDP)
- Direction(Inbound/Outbound)
- Application Rules

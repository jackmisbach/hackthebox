# HackTheBox - OpenVPN Setup

## Overview

To connect to HackTheBox machines, you need to establish a VPN connection to their private network. There are two ways to do this:

- **OpenVPN** *(covered in this guide)* - free, runs on your Kali VM
- **Pwnbox** - HTB's built-in VNC browser-based machine, no setup required, but requires a **Premium subscription** after 2 hours of usage

---

## Part 1 - Installing OpenVPN

Open a terminal in Kali and run:

```bash
sudo apt update && sudo apt install openvpn -y
```

---

## Part 2 - Downloading Your VPN Config

Log in to https://app.hackthebox.com/machines and navigate to the machine you'd like to do
1. Above the machine's IP address, or the start machine button, is the VPN config download
2. Before downloading, switch the protocol to **TCP**
3. Download your `.ovpn` config file


<img width="1920" height="911" alt="LUuUsUsvqD" src="https://github.com/user-attachments/assets/fcc57fc3-8f7b-4cd4-afb8-6ac68cf85984" />

> **Why TCP?** TCP is more reliable on restrictive networks and firewalls. HTB defaults to UDP, but TCP tends to have fewer connection issues.

---

## Part 3 - Copying the Config to Your VM

Once downloaded on your host machine, you need to get the `.ovpn` file into your Kali VM. The easiest way is to just right-click, copy the file, and then you can easily paste it into Thunar, the default Kali file manager.

---

## Part 4 - Connecting

Run the following, replacing the filename with whatever your `.ovpn` file is actually named:

```bash
sudo openvpn --config yourfile.ovpn
```

A successful connection will end with this line in the output:

```
Initialization Sequence Completed
```

> **Note:** Keep this terminal open - closing it will disconnect the VPN. If you want to free up the terminal, you can run it inside a `tmux` or `screen` session.

---

## Part 5 - Verifying the Connection

To confirm you're connected, open a new terminal tab and run:

```bash
ip a | grep tun0
```

You should see a `tun0` interface with a `10.10.x.x` IP address. If you see it, you're in and ready.
The HackTheBox site will also make the Connect in the top right turn green, and say Connected instead of Connect.

---

## Troubleshooting - Fixing the Reconnect Loop

If your VPN connection repeatedly connects, disconnects, and restarts on its own, you need to add one line to the top of your `.ovpn` file.

Open the file in a text editor:

```bash
vi yourfile.ovpn
```

Add this as the **first line**:

```
pull-filter ignore "explicit-exit-notify"
```

This prevents OpenVPN from mishandling the exit notification that HTB sends over TCP, which is what causes the loop.

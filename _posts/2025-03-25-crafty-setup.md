---
title: Crafty Controller Set Up
date: 2025-03-25 15:00:00
update: 2025-03-25 21:00:00
enable_toc: true
categories: [game, setup]
tags: [documentation, crafty-controller, server-configuration]
---

# Crafty Server Setup Guide!

This documentation guide assumes that Proxmox VE is already installed. You should also have a copy of ubuntu server. I will be using the [LTS 24.04.2 version](https://ubuntu.com/download/server/thank-you?version=24.04.2&architecture=amd64&lts=true).

Skip to step 2 if you already have a Linux server ready to go~

## Step 1: Setting up new VM in Proxmox
In the Proxmox web interface, let's create a new VM by selecting the Create VM button on the top right.
![](/assets/lib/craftysetup/1.gif)

### 1.1 General
In the general tab, enter the name you desire and for me, I'll also check the 'Start at boot' option.
![](/assets/lib/craftysetup/2.png)

### 1.2 OS
Under the ISO image dropdown let's select our ubuntu server we have just downloaded.
We can leave the rest as default.
![](/assets/lib/craftysetup/3.png)

### 1.3 System
Not much to say here, you can leave all of the settings as default
![](/assets/lib/craftysetup/4.png)

### 1.4 Disk
The disk portion is where we want to store our Ubuntu image in, and add any additional virtual drives if needed.

For the most straightforward approach, I'd just select my largest drive (1tb HDD) and allocate 100gb to this VM.

Do add more/less storage as you deem fit. I added 100gb as I plan to have BlueMap installed too.

You can leave the rest as default.

![](/assets/lib/craftysetup/5.png)

### 1.5 CPU
In CPU, we can customize how many sockets and cores we allocate our VM. We can also select the type of CPU (keep as default if you are using consumer grade CPU ie Ryzen/Intel I series CPU).

There should only be 1 socket on most, if not all, consumer grade motherboards, so just stick to 1 (Even if you do have more I would highly recommend against > 1).

Minecraft typically utilizes only 1 core of a CPU (Do correct me if I am wrong!), so we'll just default to 1 here as well. Depending on the number of servers you plan to run concurrently tho, it might be a good idea to allocate up to 4 cores.

Do leave the rest as default unless you are sure of what you are doing!

![](/assets/lib/craftysetup/6.png)

### 1.6 Memory
Pretty much the most important section!

This is where we'll allocate our RAM. The amount needed depends on several factors: the number of players, whether you are using mods or plugins, and the complexity of your world. Insufficient RAM => lag and crashes.

Here's a general guide:

#### Vanilla Servers: For a vanilla server (no mods or plugins), a good starting point is 4GB of RAM.

| Players   | RAM  |
| --------- | ---- |
| Up to 5   | 2GB  |
| Up to 10  | 4GB  |
| Up to 15  | 6GB  |
| Up to 20  | 8GB  |
| Up to 30+ | 10GB |

#### Modded Servers: Modpacks and individual mods increase RAM usage because they add items and change game mechanics. Modded servers generally require more RAM than vanilla servers.

| Mods       | RAM |
| ---------- | --- |
| < 100      | 4GB |
| 101 - 200  | 6GB |
| 201 - 300+ | 8GB |

For large modpacks, consider

| Players | RAM          |
| ------- | ------------ |
| 10 - 20 | 12GB - 16GB  |
| 20 - 50 | 16GB - 20GB+ |

#### Additional Considerations:

If you are running a vanilla server, consider using PurPur/Paper to improve efficiency and allow more players with less RAM.

![](/assets/lib/craftysetup/7.png)

<!-- Youtube Videos {% include embed/youtube.html id='37kjcyBDJ7s' %} -->

<!-- Local Images and GIF ![Bababoi](/assets/lib/Circle.png) -->

<!-- Local Video
<div class="video_wrapper">
  <video controls>
    <source src="/assets/lib/craftysetup/1.mp4" type="video/mp4">
    Your browser does not support video playback.
  </video>
</div>
-->


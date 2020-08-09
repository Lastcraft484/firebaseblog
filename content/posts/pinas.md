---
title: "Raspberry Pi Nas"
date: 2020-08-04T12:42:02-04:00
draft: false
type: post
categories: [projects]
---

# Raspberry Pi NAS

I was wondering what I could do with an old Raspberry pi A+ that I had from when I used a Raspberry Pi to run octoprint. I started trying to look for projects to do with my pi until I came across [OpenMediaVault](https://www.openmediavault.org/) and discovered they have a package for the pi. Here is the steps I followed to get my pi running OpenMediaVault

## Procedure 

###  Download Raspberry Pi OS
There are 3 versions of Raspberry Pi OS available

- [Raspberry Pi OS (32-bit) with desktop and recommended software](https://downloads.raspberrypi.org/raspios_full_armhf_latest)
- [Raspberry Pi OS (32-bit) with desktop](https://downloads.raspberrypi.org/raspios_armhf_latest)
-  [Raspberry Pi OS (32-bit) Lite](https://downloads.raspberrypi.org/raspios_lite_armhf_latest)

For my case I went with Raspberry Pi OS(32-bit) with desktop as I have some other plans for this device. You would be perfectly fine with running Lite if you are okay with a **CLI**. I used [balenaEtcher](https://www.balena.io/etcher/) to burn my 8gb sd card with the iso. 

### Booting up
If you are using the desktop installation all of this setup with be gui based. 
1. Change password 
2. Set up wifi or ethernet connection
3. When it asks to `Update Software` click `skip`, we will update through terminal later. 
4. Next restart your Pi

### Installing OMV
Once your Pi has rebooted open up a terminal window and run `sudo apt update` then run `sudo apt upgrade`. Now we are ready to install OMV, to install run:
```
wget -O - https://raw.githubusercontent.com/OpenMediaVault-Plugin-Developers/installScript/master/install | sudo bash
``` 
This script will install and set up everything needed to run OpenMediaVault on the Raspberry Pi. Please note this will take quite a long time as it is installing many packages along with OpenMediaVault. Once the script is done, run:
```
sudo reboot
```
If you know your Raspberry Pi hostname then you can run headless from now but if not, to find the hostname run:
```
hostname -I
```

This will return the Pi's hostname. From here go into a web browser and enter: 
```
http://[Pi's address]
```

### Configuring OpenMediaVault

Enter the Pi's address from above and it will bring you to this page:

![login](https://cdn.discordapp.com/attachments/738107316200669368/738148696696553512/unknown.png) The default **username** is `admin` and the default **password** is `openmediavault`.

Once you login you will be brought to the OpenMediaVault dashboard

![dash](https://cdn.discordapp.com/attachments/738107316200669368/738149665114947774/unknown.png)This is where you will control OpenMediaVault

The first thing I recommend changing is the default password. To do so `click` **General Settings** on the top left then click **Web Administrator Password**. Once done make sure to save.

###  Creating a Shared Folder in OpenMediaVault

First we are going to add a file system to our drive. This is where our shared folder is going to exist. Click the "**File Systems**" option on the left 

![left](https://cdn.discordapp.com/attachments/738107316200669368/738154386085380224/unknown.png)

From here, find your drive and then click mount.

![mount](https://cdn.discordapp.com/attachments/738107316200669368/738155078405324800/unknown.png)

Next click on **Shared Folders** on the left under the **Access Rights Management** tab, This will bring you to this page

![rights](https://cdn.discordapp.com/attachments/738107316200669368/738155945833529424/unknown.png)Here, click **add** This will open up a form. Here you will fill out the name and where the shared folder is stored. Here is an example: 

![example](https://cdn.discordapp.com/attachments/738107316200669368/738157958373834822/unknown.png)

I am using a windows pc so I am going to cover how to create a **SAMBA/CIFS** share.  First click the **SAMBA/FIFS** tab on the left side 

![left](https://cdn.discordapp.com/attachments/738107316200669368/738158667056152647/unknown.png)

This will bring you to a page that looks like this:

![share](https://cdn.discordapp.com/attachments/738107316200669368/738159077061951488/unknown.png)

All you need to do here is click **Enable**

![enable](https://cdn.discordapp.com/attachments/738107316200669368/738159296637960212/unknown.png)

Now click the **shares** tab on top.

![shares](https://cdn.discordapp.com/attachments/738107316200669368/738159882578034728/unknown.png)

Now click **Add**. This will bring up a window where you will fill out the requirements for the share.  After that is done make sure to click apply changes at the top.


### Conclusion

Congratulations, you have successfully created a SAMBA share using omv on a Raspberry Pi. Look for a post in the near future where I show how I have connected my drive and a 3d printed enclosure I am going to make.





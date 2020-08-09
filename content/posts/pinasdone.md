---
title: "Raspberry Pi Nas Build"
date: 2020-08-08T12:42:02-04:00
draft: false
type: post
categories: [projects]
---


# Raspberry Pi NAS Build

In a [previous post](https://aidanbustosblog.web.app/posts/pinas/) we installed OpenMediaVault on a Raspberry Pi. Now if you are like me you just had everything laying out on a desk. In this post we are going to try and clean up the build and make it look somewhat organized. 

## Making the bracket.

I have access to a 3d printed so I used that to produce a bracket that I used to attach the Pi to the 2.5in drive.  The drive is attached to the plate with m3 screws and the Pi is connected with m2.5 screws. 

![fusion](https://cdn.discordapp.com/attachments/659897604871553065/741815211253825696/unknown.png)
Part in Fusion.

![irl](https://cdn.discordapp.com/attachments/659897604871553065/741814909725311026/image2.jpg)
Here is the completed part with the Pi and drive connected.

## Connecting the drive

I chose to connect my drive over usb A as my Pi A+ had one port and I am only using one drive. I had an old usb 3.0 sata to usb adapter that I am using for this project.  First I attached the drive directly to the Pi but then quickly realized that the Pi would not deliver enough power for the drive. I decided to patch power into the usb cable going to the drive and have it attach to the usb power lines going to the drive so it is not taking power from the Pi over usb. 

![https://cdn.discordapp.com/attachments/659897604871553065/741814909146365972/image1.jpg](https://cdn.discordapp.com/attachments/659897604871553065/741814909146365972/image1.jpg) 
Finished cable

![https://cdn.discordapp.com/attachments/659897604871553065/741814908772941884/image0.jpg](https://cdn.discordapp.com/attachments/659897604871553065/741814908772941884/image0.jpg)
Cable attached to Pi



## Sources

- OpenMediaVault: https://www.openmediavault.org/

- 2.5in dimensions: https://www.intel.com/content/dam/www/public/us/en/documents/product-specifications/ssd-530-sata-specification.pdf

- Raspberry Pi dimensions: https://www.raspberrypi-spy.co.uk/2018/11/introducing-raspberry-pi-3-model-a-computer/

## Thingiverse link
https://www.thingiverse.com/thing:4564942


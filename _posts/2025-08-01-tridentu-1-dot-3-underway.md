---
layout: post
title: Tridentu 2 1.3.0 underway
author: Aerodos12
---

**NOTE:** This article will be updated from time to time to give out progress reports.

As of July 27th, Tridentu 2 1.2.5 has been released. However, Tridentu 2 1.3 is in the works. Here's what will be different:

## KDE Plasma 6.4

KDE Plasma 6.4 will be used instead of 6.3. Also, the issues that came with the 6.3 upgrade will be remedied as 6.4 **will remain** when developing this version of the distro.

### Update

Plasma 6.4 will be reserved for either 1.3.5 or 1.4 due to the BLFS book not including it in their cadre of software packages. It will probably be in by September as a result. Nevertheless, Plasma 6.3.4 has been installed into the main copy of the OS (for making the ISO file) and everything works except for pinning to the taskbar (likely a KDE bug).
The following programs have been updated to reflected the previous changes:

- Kvantum
- Sierra Breeze Enhanced

## Better Caravel
Caravel PM's development will continue as planned. Caravel will also receive the following features:

- dependency support
- repo db tools

### UPDATE

Caravel-PM Dependencies are now possible.

## Improved Manual
Tridentu 2 1.3 will receive a newer, improved manual that will be more readable and better suited to the distro. It will include information about using Caravel, using the distro's builtin themes (KDE) and more.

## Improved Theming

I will admit, the theming in Tridentu 2 1.2.5 was messy at worst. So, to make up for it, the themes will be handcrafted instead of automated like before. It will also feature a better layout.

### Update 1

Rounded corners and Sierra Breeze Enhanced have been reinstated. This means better looking windows and round corners return.


## Flatpak Install 

There will be an attempt to add flatpak packages to your copy of Tridentu 2 in 1.3 (via installer). The packages will be handpicked from a group of them and there could even be (depends on the software tested) config packages for customization.

## Touchpad support 

Yes - there will be another attempt to make touchpads work on HP devices.

## Update

The touchpad has been turned back on in the main copy. LPSS (Low Power SubSystems) was the culprit behind the touchpad not working (when turned off). As a result, the ISO will contain the new kernel and config.

## Orca (hardbuilt)

Orca will be hardbuilt (installed by default) on Tridentu 2 1.3. That means that out of the box, you get screen reader support for all of your accessibility needs. There might even be SOPS installed (plugin system).

There is so much more that could be covered here. However, it would take a while to cover it all, so I'm going to keep it brief. Anyways, that's the scoop on Tridentu 2 (1.2.5 and 1.3).

### Update

Orca has been installed on the main copy of Tridentu 2. This means that the compilation of the sofware was successful, and that Orca **will certainly** be shipped with Tridentu 2 1.3.

## ExFAT support (UPDATE)

As of August 3rd, 2025, ExFAT support is installed on the main copy. No more problems with this filesystem type on Tridentu 2 1.3.

## Online Accounts (UPDATE)

Online Accounts (the KCM) has been added into Tridentu 2 (1.3) as of August 4th, 2025. It allows users to connect to OwnCloud or NextCloud. Currently, Google is unsupported due to an unknown glitch.

## A More Secure Distro (UPDATE)

SGX and Shadow Stack are now enabled on the Tridentu Linux kernel. Also, AppArmor has been enabled by default. This all means that hackers will have a harder time trying to brick your computer.


## Thunderbolt! (UPDATE)

The program boltd has been installed on the main copy of Tridentu 2 (1.3). this allows for the use of Thunderbolt on PCs and Macs with Tridentu 2 installed.

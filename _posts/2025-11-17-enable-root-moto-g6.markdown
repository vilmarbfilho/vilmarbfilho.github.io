---
layout: post
title:  "How to Root a Motorola G6 Device"
date:   2025-11-17 19:18:00 -0300
categories: android root moto g6
---


In this post I'll explain how to root a Motorola G6 device.

## Begin
Enable developer mode on device. 

To enable follow this steps:

1 - Go to Settings of device

2 - Scroll down and select System

3 - Select About phone

4 - Scroll down and tap 7 times on Builder number

A message "You are now a developer" will be displayed.

Now in the follow path there will be a Developer options menu:
Settings > System > Advanced > Developer options

## Unlock bootloader

#### USB Drivers
Install [drivers](https://en-us.support.motorola.com/app/usb-drivers) for your Motorola G6 on your computer. You can download the necessary USB drivers from the official [Motorola website](https://en-us.support.motorola.com/app/standalone/bootloader/unlock-your-device-a).

#### SDK Platform Tools
Install [SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools) on your computer. You can download it from the official Android developer website.

1. Extract the downloaded ZIP file to a convenient location on your computer.

2. Open a command prompt or terminal window in the extracted folder.

3. Connect your Motorola G6 to your computer using a USB cable.

4. In the command prompt or terminal, type the following command to check if your device is recognized:
   ```
   adb devices
   ```

#### Fastboot Mode
Put your device into Fastboot mode by following these steps:

1. Power off your Motorola G6.
2. Press and hold the Volume Down button and the Power button simultaneously until the Fastboot menu appears.

![Moto G6 Fastboot Mode](/assets/img/moto-g6-root/moto_g6_fastboot_mode.png){:class="img-responsive"}

#### Unlocking

1. In the command prompt or terminal, type the following command to unlock the bootloader:
   ```
   fastboot oem get_unlock_data 
   ```

2. Copy the output from the command and paste it into a text file. This will be your unlock code.

3. Visit the [Motorola Unlock Bootloader](https://www.motorola.com/us/support/unlock-bootloader) page and follow the instructions to unlock your bootloader using the code you obtained.

4. After receiving the unique code, go back to the command prompt or terminal and type the following command to unlock the bootloader:
   ```
   fastboot oem unlock [your unlock code]
   ```

5. Once your bootloader is unlocked, you can proceed to root your device.

![Moto G6 Unlocked](/assets/img/moto-g6-root/moto_g6_unlocked.png){:class="img-responsive"}

## Root device

### Magisk 
1. Download Magisk apk from [github](https://github.com/topjohnwu/Magisk)

2. Change the extension of the downloaded Magisk apk file from `.apk` to `.zip`.

3. Copy the Magisk zip file to your device's flash card

4. Go to TWRP Recovery step

#### TWRP Recovery
1. Download the TWRP recovery image for Motorola G6 from [here](https://dl.twrp.me/ali)

2. Rename the downloaded TWRP image file to `twrp.img` and move it to the folder where you have the ADB and Fastboot tools.

3. Put device into Fastboot mode.

4. In the command prompt or terminal, type the following command to flash TWRP recovery:
   ```
   fastboot flash recovery twrp.img
   ```

5. Once the flashing process is complete, use the volume buttons to navigate to the "Recovery Mode" option in the Fastboot menu and press the Power button to select it. This will boot your device into TWRP recovery mode. 

6. Wipe data in TWRP.
   - Go to Wipe > Format Data (confirm with yes)
   - After formatting, press home button of device
   - Click on reboot > Recovery

7. In TWRP, go to Install and select the Magisk zip file you copied earlier.
   - Swipe to confirm the installation.


Now reboot your device into the system.

Open Magisk Manager to complete the setup. To ensure proper functionality, grant Magisk Manager the necessary permissions and follow any on-screen instructions.

Download root checker from the Play Store to verify if your device is successfully rooted.

✌🏾